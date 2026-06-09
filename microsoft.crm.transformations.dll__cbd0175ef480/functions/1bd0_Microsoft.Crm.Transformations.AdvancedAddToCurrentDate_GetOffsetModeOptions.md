# Microsoft.Crm.Transformations.AdvancedAddToCurrentDate::GetOffsetModeOptions

- ea: `0x1bd0`
- end: `0x1c4b`
- name: `Microsoft.Crm.Transformations.AdvancedAddToCurrentDate::GetOffsetModeOptions`
- size: `123`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x19a0`
- `0x1a30`
- `0x1ac0`

## callees

- `0x2740`

## pseudocode

```c

```

## disassembly

```asm
0x1bd0  ldc.i4.2
0x1bd1  newarr   [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption
0x1bd6  dup
0x1bd7  ldc.i4.0
0x1bd8  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::.ctor()
0x1bdd  stelem.ref
0x1bde  dup
0x1bdf  ldc.i4.0
0x1be0  ldelem.ref
0x1be1  ldstr    aMicrosoftCrmTr_91// "Microsoft.Crm.Transformations.AdvancedA"...
0x1be6  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x1beb  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::set_Name(string)
0x1bf0  dup
0x1bf1  ldc.i4.0
0x1bf2  ldelem.ref
0x1bf3  ldstr    aMicrosoftCrmTr_92// "Microsoft.Crm.Transformations.AdvancedA"...
0x1bf8  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x1bfd  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::set_Description(string)
0x1c02  dup
0x1c03  ldc.i4.0
0x1c04  ldelem.ref
0x1c05  ldc.i4.0
0x1c06  box      [mscorlib]System.Int32
0x1c0b  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::set_Value(object)
0x1c10  dup
0x1c11  ldc.i4.1
0x1c12  newobj   instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::.ctor()
0x1c17  stelem.ref
0x1c18  dup
0x1c19  ldc.i4.1
0x1c1a  ldelem.ref
0x1c1b  ldstr    aMicrosoftCrmTr_93// "Microsoft.Crm.Transformations.AdvancedA"...
0x1c20  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x1c25  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::set_Name(string)
0x1c2a  dup
0x1c2b  ldc.i4.1
0x1c2c  ldelem.ref
0x1c2d  ldstr    aMicrosoftCrmTr_94// "Microsoft.Crm.Transformations.AdvancedA"...
0x1c32  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x1c37  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::set_Description(string)
0x1c3c  dup
0x1c3d  ldc.i4.1
0x1c3e  ldelem.ref
0x1c3f  ldc.i4.1
0x1c40  box      [mscorlib]System.Int32
0x1c45  callvirt instance void [Microsoft.Crm.Transformations.Helper]Microsoft.Crm.Transformations.InputParameterOption::set_Value(object)
0x1c4a  ret
```
