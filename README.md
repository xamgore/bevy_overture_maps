# bevy_overture_maps
Bevy overture is an example of integration between <https://overturemaps.org> and <https://bevyengine.org/>

![v0.3.2 screenshot](https://github.com/alexichepura/bevy_overture_maps/assets/5582266/bb357732-953a-4b79-b759-ec26b343dff5)

## Howto

1. Download [OvertureMaps data](https://github.com/OvertureMaps/data). It can be done with AWS CLI:
   ```shell
   # all, full size is 200GB
   aws s3 cp --region us-west-2 --no-sign-request --recursive s3://overturemaps-us-west-2/release/2023-07-26-alpha.0/ \
     <DESTINATION>

   # only segments & buildings
   aws s3 cp --region us-west-2 --no-sign-request --recursive s3://overturemaps-us-west-2/release/2023-07-26-alpha.0/theme=transportation/type=segment/ ./theme=transportation/type=segment/
   aws s3 cp --region us-west-2 --no-sign-request --recursive s3://overturemaps-us-west-2/release/2023-07-26-alpha.0/theme=buildings/ ./theme=buildings/
   ```

2. Extract the location, assuming the maps data is in `../overture/`:
   ```sh
   # bevy_overture_maps_cli location <LON> <LAT> <NAME>
   cargo cli location 139.69170 35.68951 tokyo
   ```

3. **Fill in `.env`**, see `.env.example`

4. Run bevy. 
   ```sh
   cargo run --release -p=bevy_overture_maps_app
    # or
   cargo app
   ```

## Old
One coordinate flipped and lots of bugs but it works.

https://github.com/alexichepura/bevy_overture/assets/5582266/14a074e3-d520-4035-b78f-4d42ea2872ce

## License

This project is licensed under the terms of the
[MIT license](/LICENSE-MIT).
