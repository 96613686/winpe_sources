# Microsoft.Crm.Common.Application.Platform.ActivityBase::SetDisabled

- ea: `0x2b90`
- end: `0x2c35`
- name: `Microsoft.Crm.Common.Application.Platform.ActivityBase::SetDisabled`
- size: `165`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x2b90`

## pseudocode

```c

```

## disassembly

```asm
0x2b90  ldarg.0
0x2b91  ldstr    aStatecode// "statecode"
0x2b96  call     instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x2b9b  isinst   [mscorlib]System.String
0x2ba0  stloc.0
0x2ba1  ldloc.0
0x2ba2  ldc.i4.0
0x2ba3  stloc.1
0x2ba4  ldloca.s 1
0x2ba6  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.ActivityPointerState
0x2bac  callvirt instance string [mscorlib]System.Object::ToString()
0x2bb1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2bb6  brtrue.s loc_2BCF
0x2bb8  ldloc.0
0x2bb9  ldc.i4.3
0x2bba  stloc.1
0x2bbb  ldloca.s 1
0x2bbd  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.ActivityPointerState
0x2bc3  callvirt instance string [mscorlib]System.Object::ToString()
0x2bc8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2bcd  brfalse.s loc_2BD7
0x2bcf  ldarg.0
0x2bd0  ldc.i4.0
0x2bd1  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Disabled(bool)
0x2bd6  ret
0x2bd7  ldloc.0
0x2bd8  ldc.i4.2
0x2bd9  stloc.1
0x2bda  ldloca.s 1
0x2bdc  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.ActivityPointerState
0x2be2  callvirt instance string [mscorlib]System.Object::ToString()
0x2be7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2bec  brtrue.s loc_2C1C
0x2bee  ldloc.0
0x2bef  ldc.i4.1
0x2bf0  stloc.1
0x2bf1  ldloca.s 1
0x2bf3  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.ActivityPointerState
0x2bf9  callvirt instance string [mscorlib]System.Object::ToString()
0x2bfe  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2c03  brtrue.s loc_2C1C
0x2c05  ldloc.0
0x2c06  ldc.i4.1
0x2c07  stloc.2
0x2c08  ldloca.s 2
0x2c0a  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.CampaignActivityState
0x2c10  callvirt instance string [mscorlib]System.Object::ToString()
0x2c15  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2c1a  brfalse.s loc_2C24
0x2c1c  ldarg.0
0x2c1d  ldc.i4.1
0x2c1e  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Disabled(bool)
0x2c23  ret
0x2c24  ldstr    aInvalidActivit// "Invalid activity state: "
0x2c29  ldloc.0
0x2c2a  call     string [mscorlib]System.String::Concat(string, string)
0x2c2f  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x2c34  throw
```
