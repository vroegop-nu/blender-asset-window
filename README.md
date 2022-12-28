# Node groups

## Window Frame

This node group can be used for generating window frames. A window frame can be horizontally and
vertically subdivided. The faces inside the frame are marked as window panes.

### Parameters

| Parameter          | Description                                                             |
| ------------------ | ----------------------------------------------------------------------- |
| Width              | The total width of the window frame                                     |
| Height             | The total height of the window frame                                    |
| Frame Width        | Width of the horizontal and vertical window frame parts                 |
| Frame Depth        | Depth, or thickness of the window frame parts                           |
| Horizontal Subdivs | Number of horizontal subdivisions                                       |
| Vertical Subdivs   | Number of vertical subdivisions                                         |
| Frame Material     | Material applied to the frame parts                                     |
| Pane Material      | Material applied to the window panes                                    |
| Frame Vertex Color | Vertex color applied to the face corners of the window frame parts      |
| Pane Vertex Color  | Vertex color applied to the face corners of the window pane window pane |
| Create Back Faces  | Boolean to toggle the generation of back faces                          |
| Create Edge Faces  | Boolean to toggle the generation of side faces                          |

### Attributes

| Attribute | Type    | Description                                               |
| --------- | ------- | --------------------------------------------------------- |
| v_origin  | vector  | Origin point of window frame part. Stored on every vertex |
| is_pane   | boolean | Stored as True on every window pane vertex                |
| is_frame  | boolean | Stored as True on every window frame vertex               |

## Window

The window node group can be used to generate windows. The node group uses the Window Frame node
group to create a window. Windows can have an optional outer frame. A window sill and lintel are
also optional parts of the window.

## Parameters

| Parameter           | Description                                                         |
| ------------------- | ------------------------------------------------------------------- |
| Width               | Total width of the window, EXCLUDING the lintel and window sill     |
| Height              | Total height of the window INCLUDING the lintel and window sill     |
| Frame Width         | Width of the inner frame parts                                      |
| Frame Depth         | Depth of the inner frame parts                                      |
| Horizontal Divides  | Number horizontal subdivisions                                      |
| Vertical Divides    | Number of vertical subdivisions                                     |
| Frame Material      | Material assigned to the inner and outer frame                      |
| Frame Vertex Color  | Vertex color assigned to the face corners of every frame part       |
| Pane Material       | Material assigned to the window panes                               |
| Pane Vertex Color   | Vertex color assigned to the face corners of every window pane part |
| Outer Frame         | Boolean to toggle the generation of the outer frame                 |
| Outer Frame Width   | Width of the outer frame parts                                      |
| Outer Frame Depth   | Depth of the outer frame parts                                      |
| Create Back Faces   | Boolean to toggle the generation of back faces                      |
| Create Edge Faces   | Boolean to toggle the generation of side faces                      |
| Lintel Extension    | How much the lintel is wider than the window width                  |
| Lintel Height       | Height of the lintel                                                |
| Lintel Depth        | Depth of the lintel                                                 |
| Lintel Bevel Fac    | Amount the bottom side edges of the lintel are bevelled             |
| Lintel Vertex Color | Vertex color assigned to the face corners of the lintel             |
| Lintel Material     | Material assigned to the lintel                                     |
| Sill Extension      | How much the window sill is wider than the window                   |
| Sill Height         | Total height of the window sill                                     |
| Sill Depth          | Depth of the window sill                                            |
| Sill Bevel Fac      | Amount the top front edge of the window sill is bevelled            |
| Sill Vertex Color   | Vertex color assigned to every face corner of the window sill       |
| Sill Material       | Material assigned to the window sill                                |

### Attributes

| Attribute             | Type    | Description                                                      |
| --------------------- | ------- | ---------------------------------------------------------------- |
| v_origin              | vector  | Origin point of window frame part. Stored on every vertex        |
| is_pane               | boolean | Stored as True on every window pane vertex and face              |
| is_frame              | boolean | Stored as True on every window frame vertex                      |
| is_window_inner_frame | boolean | Stored as True on every inner frame window frame vertex          |
| is_window_outer_frame | boolean | Stored as True on every outer window frame vertex                |
| is_lintel             | boolean | Stored as True on every lintel vertex                            |
| is_window_sill        | boolean | Stored as True on every sill vertex                              |
| is_outer_edge         | boolean | Stored on the outer edges of the window frames (inner and outer) |

# Materials

## Window Pane Glass

A high gloss material that uses the vertex color as a base color and combines the object position with the v_origin attribute to randomly generate a normal rotation. The material makes the panes have a slightly different reflection angle.

## Window Concrete

A concrete material that can be applied to the window sill and lintel. A has a slightly rough surface and some speckles to break the surface color. The base color can be set by adjusting the vertex color.