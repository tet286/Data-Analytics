# Monte Carlo:
The Algorithm 
1. Initialize circle_points, square_points and interval to 0. 
2. Generate random point x. 
3. Generate random point y. 
4. Calculate d = x*x + y*y. 
5. If d <= 1, increment circle_points. 
6. Increment square_points. 
7. Increment interval. 
8. If increment < NO_OF_ITERATIONS, repeat from 2. 
9. Calculate pi = 4*(circle_points/square_points). 
10. Terminate.
The code doesn’t wait for any input via stdin as the macro INTERVAL could be changed as per the required number of iterations. Number of iterations are the square of INTERVAL. Also, I’ve paused the screen for first 10 iterations with getch() and outputs are displayed for every iteration with format given below. You can change or delete them as per requirement. 

# Cubic Splice:
Splines are piecewise polynomial functions to interpolate points (xi, yi). In particular, cubic splines can be represented as
f(x) = ai + bi (x-xi) + ci (x-xi)2 + di (x-xi)3, for all x in [xi, xi+1)
f(xi)=yi

The following splines are available.

tk::spline::cspline: cubic C2 spline
twice continuously differentiable, e.g. f'(xi) and f''(xi) exist
this, together with boundary conditions uniquely determines the spline
requires solving a sparse equation system
is a global spline in the sense that changing an input point will impact the spline everywhere
setting first order derivatives at the boundary will break C2 at the boundary
tk::spline::cspline_hermite: cubic Hermite spline
once continuously differentiable (C1)
first order derivatives are specified by finite differences, e.g. on a uniform x-grid:
f'(xi) = (yi+1-yi-1)/(xi+1-xi-1)
is a local spline in the sense that changing grid points will only affect the spline around that grid point in a few adjacent segments
A function to enforce monotonicity is available as well:

tk::spline::make_monotonic(): will make the spline monotonic if input grid points are monotonic
this function can only be called after set_points(...) has been called
it will break C2 if the original spline was C2 and not already monotonic
it will break boundary conditions if it was not monotonic in the first or last segment




References:
https://kluge.in-chemnitz.de/opensource/spline/
https://www.geeksforgeeks.org/estimating-value-pi-using-monte-carlo/
