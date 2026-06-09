# Microsoft.Crm.PackageDeployment.CrmTraceListener::EventTypeToCrmLevel

- ea: `0x120`
- end: `0x199`
- name: `Microsoft.Crm.PackageDeployment.CrmTraceListener::EventTypeToCrmLevel`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xc0`

## callees

- `0x120`

## pseudocode

```c

```

## disassembly

```asm
0x120  ldarg.0
0x121  ldc.i4   0x100
0x126  bgt.s    loc_159
0x128  ldarg.0
0x129  ldc.i4.8
0x12a  bgt.s    loc_14A
0x12c  ldarg.0
0x12d  ldc.i4.1
0x12e  sub
0x12f  switch   loc_185, loc_185, loc_195, loc_189
0x144  ldarg.0
0x145  ldc.i4.8
0x146  beq.s    loc_18D
0x148  br.s     loc_195
0x14a  ldarg.0
0x14b  ldc.i4.s 0x10
0x14d  beq.s    loc_191
0x14f  ldarg.0
0x150  ldc.i4   0x100
0x155  beq.s    loc_191
0x157  br.s     loc_195
0x159  ldarg.0
0x15a  ldc.i4   0x400
0x15f  bgt.s    loc_173
0x161  ldarg.0
0x162  ldc.i4   0x200
0x167  beq.s    loc_191
0x169  ldarg.0
0x16a  ldc.i4   0x400
0x16f  beq.s    loc_191
0x171  br.s     loc_195
0x173  ldarg.0
0x174  ldc.i4   0x800
0x179  beq.s    loc_191
0x17b  ldarg.0
0x17c  ldc.i4   0x1000
0x181  beq.s    loc_191
0x183  br.s     loc_195
0x185  ldc.i4.1
0x186  stloc.0
0x187  br.s     loc_197
0x189  ldc.i4.2
0x18a  stloc.0
0x18b  br.s     loc_197
0x18d  ldc.i4.3
0x18e  stloc.0
0x18f  br.s     loc_197
0x191  ldc.i4.4
0x192  stloc.0
0x193  br.s     loc_197
0x195  ldc.i4.4
0x196  stloc.0
0x197  ldloc.0
0x198  ret
```
