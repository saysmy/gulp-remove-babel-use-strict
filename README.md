# gulp-remove-babel-use-strict
gulp-remove-babel-use-strict

## Usage

```
const removeUseStrict = require("./gulp-remove-babel-use-strict.js")

gulp.task('scripts', function(){
    return gulp.src(pc_src.js, {base: pc_src.base })
        .pipe(gulpif(!isRelease, changed(pc_output) ) )
        .pipe(babel()).on('error', errorHandler)
        .pipe(removeUseStrict()).on('error', errorHandler)
        .pipe( gulpif(isRelease, uglify()) )
        .on('error', errorHandler)
        .pipe(gulp.dest(pc_output));
});
```