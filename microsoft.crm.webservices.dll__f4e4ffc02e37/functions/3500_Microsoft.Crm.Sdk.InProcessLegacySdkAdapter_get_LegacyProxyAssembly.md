# Microsoft.Crm.Sdk.InProcessLegacySdkAdapter::get_LegacyProxyAssembly

- ea: `0x3500`
- end: `0x357b`
- name: `Microsoft.Crm.Sdk.InProcessLegacySdkAdapter::get_LegacyProxyAssembly`
- size: `123`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x3590`
- `0x37c0`
- `0x3960`

## callees

- `0x3500`

## string_xrefs

- `0x350f`: `Microsoft.Crm.SdkTypeProxy, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35`
- `0x3534`: `Microsoft.Crm.SdkTypeProxy, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35`
- `0x355e`: `Microsoft.Crm.SdkTypeProxy, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35`
- `0x353f`: `Could not load legacy SDK components`
- `0x3569`: `Could not load legacy SDK components`

## pseudocode

```c

```

## disassembly

```asm
0x3500  ldarg.0
0x3501  ldfld    class [mscorlib]System.Reflection.Assembly Microsoft.Crm.Sdk.InProcessLegacySdkAdapter::_legacyProxyAssembly
0x3506  ldnull
0x3507  call     bool [mscorlib]System.Reflection.Assembly::op_Equality(class [mscorlib]System.Reflection.Assembly, class [mscorlib]System.Reflection.Assembly)
0x350c  brfalse.s loc_3574
0x350e  ldarg.0
0x350f  ldstr    aMicrosoftCrmSd_0// "Microsoft.Crm.SdkTypeProxy, Version=4.0"...
0x3514  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::Load(string)
0x3519  stfld    class [mscorlib]System.Reflection.Assembly Microsoft.Crm.Sdk.InProcessLegacySdkAdapter::_legacyProxyAssembly
0x351e  leave.s  loc_3574
0x3520  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x3525  ldc.i4.s 0x1A
0x3527  ldstr    aCouldNotLoadLe// "Could not load legacy assembly {0}"
0x352c  ldc.i4.1
0x352d  newarr   [mscorlib]System.Object
0x3532  dup
0x3533  ldc.i4.0
0x3534  ldstr    aMicrosoftCrmSd_0// "Microsoft.Crm.SdkTypeProxy, Version=4.0"...
0x3539  stelem.ref
0x353a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x353f  ldstr    aCouldNotLoadLe_0// "Could not load legacy SDK components"
0x3544  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x3549  throw
0x354a  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x354f  ldc.i4.s 0x1A
0x3551  ldstr    aCouldNotLoadLe// "Could not load legacy assembly {0}"
0x3556  ldc.i4.1
0x3557  newarr   [mscorlib]System.Object
0x355c  dup
0x355d  ldc.i4.0
0x355e  ldstr    aMicrosoftCrmSd_0// "Microsoft.Crm.SdkTypeProxy, Version=4.0"...
0x3563  stelem.ref
0x3564  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3569  ldstr    aCouldNotLoadLe_0// "Could not load legacy SDK components"
0x356e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x3573  throw
0x3574  ldarg.0
0x3575  ldfld    class [mscorlib]System.Reflection.Assembly Microsoft.Crm.Sdk.InProcessLegacySdkAdapter::_legacyProxyAssembly
0x357a  ret
```
