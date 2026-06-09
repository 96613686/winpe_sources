# Microsoft.Crm.ExceptionConverter::GetErrorCodeName

- ea: `0x1a140`
- end: `0x1a209`
- name: `Microsoft.Crm.ExceptionConverter::GetErrorCodeName`
- size: `201`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x19e60`
- `0x1a210`

## callees

- `0x1a140`

## string_xrefs

- `0x1a1d1`: `ErrorCodes.SandboxClientPluginTimeout`
- `0x1a1d9`: `ErrorCodes.SandboxHostPluginTimeout`
- `0x1a1e1`: `ErrorCodes.SandboxWorkerPluginTimeout`
- `0x1a201`: `ErrorCodes.UnableToLoadPluginAssembly`

## pseudocode

```c

```

## disassembly

```asm
0x1a140  ldstr    asc_7195A// ""
0x1a145  stloc.0
0x1a146  ldarg.0
0x1a147  ldc.i4   0x80040224
0x1a14c  bgt.s    loc_1A16B
0x1a14e  ldarg.0
0x1a14f  ldc.i4   0x80040203
0x1a154  beq.s    loc_1A1C9
0x1a156  ldarg.0
0x1a157  ldc.i4   0x80040216
0x1a15c  beq.s    loc_1A1B1
0x1a15e  ldarg.0
0x1a15f  ldc.i4   0x80040224
0x1a164  beq.s    loc_1A1C1
0x1a166  br       loc_1A207
0x1a16b  ldarg.0
0x1a16c  ldc.i4   0x80040265
0x1a171  beq.s    loc_1A1B9
0x1a173  ldarg.0
0x1a174  ldc.i4   0x80044171
0x1a179  sub
0x1a17a  switch   loc_1A1D1, loc_1A1D9, loc_1A1E1, loc_1A1E9
0x1a18f  ldarg.0
0x1a190  ldc.i4   0x8004418D
0x1a195  sub
0x1a196  switch   loc_1A1F1, loc_1A1F9, loc_1A207, loc_1A207, loc_1A201
0x1a1af  br.s     loc_1A207
0x1a1b1  ldstr    aErrorcodesUnex// "ErrorCodes.UnExpected"
0x1a1b6  stloc.0
0x1a1b7  br.s     loc_1A207
0x1a1b9  ldstr    aErrorcodesIsva// "ErrorCodes.IsvAborted"
0x1a1be  stloc.0
0x1a1bf  br.s     loc_1A207
0x1a1c1  ldstr    aErrorcodesIsvu// "ErrorCodes.IsvUnExpected"
0x1a1c6  stloc.0
0x1a1c7  br.s     loc_1A207
0x1a1c9  ldstr    aErrorcodesInva// "ErrorCodes.InvalidArgument"
0x1a1ce  stloc.0
0x1a1cf  br.s     loc_1A207
0x1a1d1  ldstr    aErrorcodesSand// "ErrorCodes.SandboxClientPluginTimeout"
0x1a1d6  stloc.0
0x1a1d7  br.s     loc_1A207
0x1a1d9  ldstr    aErrorcodesSand_0// "ErrorCodes.SandboxHostPluginTimeout"
0x1a1de  stloc.0
0x1a1df  br.s     loc_1A207
0x1a1e1  ldstr    aErrorcodesSand_1// "ErrorCodes.SandboxWorkerPluginTimeout"
0x1a1e6  stloc.0
0x1a1e7  br.s     loc_1A207
0x1a1e9  ldstr    aErrorcodesSand_2// "ErrorCodes.SandboxSdkListenerStartFaile"...
0x1a1ee  stloc.0
0x1a1ef  br.s     loc_1A207
0x1a1f1  ldstr    aErrorcodesSand_3// "ErrorCodes.SandboxWorkerNotAvailable"
0x1a1f6  stloc.0
0x1a1f7  br.s     loc_1A207
0x1a1f9  ldstr    aErrorcodesSand_4// "ErrorCodes.SandboxHostNotAvailable"
0x1a1fe  stloc.0
0x1a1ff  br.s     loc_1A207
0x1a201  ldstr    aErrorcodesUnab// "ErrorCodes.UnableToLoadPluginAssembly"
0x1a206  stloc.0
0x1a207  ldloc.0
0x1a208  ret
```
