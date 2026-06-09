# Microsoft.Crm.Common.Application.Platform.Fax::HasRecipients

- ea: `0x4130`
- end: `0x4150`
- name: `Microsoft.Crm.Common.Application.Platform.Fax::HasRecipients`
- size: `32`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x6ca0`

## callees

- `0x4130`

## pseudocode

```c

```

## disassembly

```asm
0x4130  ldarg.0
0x4131  ldstr    aTo// "to"
0x4136  call     instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x413b  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection
0x4140  stloc.0
0x4141  ldloc.0
0x4142  brfalse.s loc_414E
0x4144  ldloc.0
0x4145  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x414a  ldc.i4.0
0x414b  cgt
0x414d  ret
0x414e  ldc.i4.0
0x414f  ret
```
