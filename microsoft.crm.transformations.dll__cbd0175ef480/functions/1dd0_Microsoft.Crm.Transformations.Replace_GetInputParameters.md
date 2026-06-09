# Microsoft.Crm.Transformations.Replace::GetInputParameters

- ea: `0x1dd0`
- end: `0x1df2`
- name: `Microsoft.Crm.Transformations.Replace::GetInputParameters`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1f80`
- `0x1fc0`
- `0x2000`

## pseudocode

```c

```

## disassembly

```asm
0x1dd0  ldc.i4.3
0x1dd1  newarr   [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.IInputParameterDescription
0x1dd6  dup
0x1dd7  ldc.i4.0
0x1dd8  ldarg.0
0x1dd9  call     instance class [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.IInputParameterDescription Microsoft.Crm.Transformations.Replace::GetInputString()
0x1dde  stelem.ref
0x1ddf  dup
0x1de0  ldc.i4.1
0x1de1  ldarg.0
0x1de2  call     instance class [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.IInputParameterDescription Microsoft.Crm.Transformations.Replace::GetSearchString()
0x1de7  stelem.ref
0x1de8  dup
0x1de9  ldc.i4.2
0x1dea  ldarg.0
0x1deb  call     instance class [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.IInputParameterDescription Microsoft.Crm.Transformations.Replace::GetReplaceString()
0x1df0  stelem.ref
0x1df1  ret
```
