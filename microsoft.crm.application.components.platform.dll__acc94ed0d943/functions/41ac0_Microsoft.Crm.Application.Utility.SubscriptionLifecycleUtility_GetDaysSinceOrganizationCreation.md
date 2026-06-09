# Microsoft.Crm.Application.Utility.SubscriptionLifecycleUtility::GetDaysSinceOrganizationCreation

- ea: `0x41ac0`
- end: `0x41b65`
- name: `Microsoft.Crm.Application.Utility.SubscriptionLifecycleUtility::GetDaysSinceOrganizationCreation`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x41920`

## callees

- `0x41ac0`

## string_xrefs

- `0x41ae9`: `CreatedOn`
- `0x41b09`: `CreatedOn`
- `0x41b16`: `CreatedOn`
- `0x41b3f`: `CreatedOn property not found for org: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x41ac0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x41ac5  stloc.0
0x41ac6  ldloc.0
0x41ac7  ldstr    aCrmorganizatio// "CrmOrganizationId"
0x41acc  ldarg.0
0x41acd  box      [mscorlib]System.Guid
0x41ad2  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x41ad7  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x41adc  ldstr    aOrganizationli// "OrganizationLifecycle"
0x41ae1  ldc.i4.1
0x41ae2  newarr   [mscorlib]System.String
0x41ae7  dup
0x41ae8  ldc.i4.0
0x41ae9  ldstr    aCreatedon_0// "CreatedOn"
0x41aee  stelem.ref
0x41aef  ldloc.0
0x41af0  ldc.i4   0xBC
0x41af5  ldstr    aGetdayssinceor// "GetDaysSinceOrganizationCreation"
0x41afa  ldstr    aDDbsShDccm2110_2// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\2"...
0x41aff  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::RetrieveSingleRow(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x41b04  stloc.1
0x41b05  ldloc.1
0x41b06  brfalse.s loc_41B3A
0x41b08  ldloc.1
0x41b09  ldstr    aCreatedon_0// "CreatedOn"
0x41b0e  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x41b13  brfalse.s loc_41B3A
0x41b15  ldloc.1
0x41b16  ldstr    aCreatedon_0// "CreatedOn"
0x41b1b  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x41b20  unbox.any [mscorlib]System.DateTime
0x41b25  stloc.2
0x41b26  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x41b2b  ldloc.2
0x41b2c  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x41b31  stloc.3
0x41b32  ldloca.s 3
0x41b34  call     instance int32 [mscorlib]System.TimeSpan::get_Days()
0x41b39  ret
0x41b3a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x41b3f  ldstr    aCreatedonPrope// "CreatedOn property not found for org: {"...
0x41b44  ldc.i4.1
0x41b45  newarr   [mscorlib]System.Object
0x41b4a  dup
0x41b4b  ldc.i4.0
0x41b4c  ldarga.s 0
0x41b4e  constrained. [mscorlib]System.Guid
0x41b54  callvirt instance string [mscorlib]System.Object::ToString()
0x41b59  stelem.ref
0x41b5a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x41b5f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x41b64  throw
```
