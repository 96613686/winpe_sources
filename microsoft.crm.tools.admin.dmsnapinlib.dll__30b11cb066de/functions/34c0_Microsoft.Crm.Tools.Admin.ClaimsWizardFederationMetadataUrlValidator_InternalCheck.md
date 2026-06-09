# Microsoft.Crm.Tools.Admin.ClaimsWizardFederationMetadataUrlValidator::InternalCheck

- ea: `0x34c0`
- end: `0x358f`
- name: `Microsoft.Crm.Tools.Admin.ClaimsWizardFederationMetadataUrlValidator::InternalCheck`
- size: `207`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x30a0`
- `0x3110`
- `0x3180`
- `0x34c0`

## string_xrefs

- `0x34cd`: `ClaimsInfo.ClaimsFederationMetadataUrlProperty`

## pseudocode

```c

```

## disassembly

```asm
0x34c0  ldarg.1
0x34c1  newobj   instance void Microsoft.Crm.Tools.Admin.ClaimsInfo::.ctor(class [mscorlib]System.Collections.IDictionary data)
0x34c6  stloc.0
0x34c7  ldloc.0
0x34c8  callvirt instance class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::get_Data()
0x34cd  ldstr    aClaimsinfoClai_0// "ClaimsInfo.ClaimsFederationMetadataUrlP"...
0x34d2  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x34d7  brtrue.s loc_34F1
0x34d9  ldc.i4.2
0x34da  ldarg.0
0x34db  ldstr    aFederationmeta// "FederationMetadataUrlValidator.Failure."...
0x34e0  ldc.i4.0
0x34e1  newarr   [mscorlib]System.Object
0x34e6  call     instance string [Microsoft.Crm.Setup.Common]Microsoft.Crm.Setup.Common.Validator::GetResourceString(string, object[])
0x34eb  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0x34f0  ret
0x34f1  ldloc.0
0x34f2  callvirt instance string Microsoft.Crm.Tools.Admin.ClaimsInfo::get_ClaimsFederationMetadataUrl()
0x34f7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x34fc  brfalse.s loc_3516
0x34fe  ldc.i4.2
0x34ff  ldarg.0
0x3500  ldstr    aFederationmeta// "FederationMetadataUrlValidator.Failure."...
0x3505  ldc.i4.0
0x3506  newarr   [mscorlib]System.Object
0x350b  call     instance string [Microsoft.Crm.Setup.Common]Microsoft.Crm.Setup.Common.Validator::GetResourceString(string, object[])
0x3510  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0x3515  ret
0x3516  nop
0x3517  ldloc.0
0x3518  callvirt instance string Microsoft.Crm.Tools.Admin.ClaimsInfo::get_ClaimsFederationMetadataUrl()
0x351d  newobj   instance void [System]System.Uri::.ctor(string)
0x3522  call     class [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.Claims.MetadataParser Microsoft.Crm.Tools.Admin.ClaimsConfiguration::ResolveFederationMetadataUrl(class [System]System.Uri stsUrl)
0x3527  pop
0x3528  leave.s  loc_3586
0x352a  stloc.1
0x352b  ldc.i4.2
0x352c  ldarg.0
0x352d  ldstr    aFederationmeta_0// "FederationMetadataUrlValidator.Failure."...
0x3532  ldc.i4.2
0x3533  newarr   [mscorlib]System.Object
0x3538  dup
0x3539  ldc.i4.0
0x353a  ldloc.0
0x353b  callvirt instance string Microsoft.Crm.Tools.Admin.ClaimsInfo::get_ClaimsFederationMetadataUrl()
0x3540  stelem.ref
0x3541  dup
0x3542  ldc.i4.1
0x3543  ldarg.0
0x3544  ldloc.1
0x3545  call     instance string [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ConditionBase::BuildExceptionMessage(class [mscorlib]System.Exception)
0x354a  stelem.ref
0x354b  call     instance string [Microsoft.Crm.Setup.Common]Microsoft.Crm.Setup.Common.Validator::GetResourceString(string, object[])
0x3550  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0x3555  stloc.2
0x3556  leave.s  loc_358D
0x3558  stloc.3
0x3559  ldc.i4.2
0x355a  ldarg.0
0x355b  ldstr    aFederationmeta_0// "FederationMetadataUrlValidator.Failure."...
0x3560  ldc.i4.2
0x3561  newarr   [mscorlib]System.Object
0x3566  dup
0x3567  ldc.i4.0
0x3568  ldloc.0
0x3569  callvirt instance string Microsoft.Crm.Tools.Admin.ClaimsInfo::get_ClaimsFederationMetadataUrl()
0x356e  stelem.ref
0x356f  dup
0x3570  ldc.i4.1
0x3571  ldarg.0
0x3572  ldloc.3
0x3573  call     instance string [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ConditionBase::BuildExceptionMessage(class [mscorlib]System.Exception)
0x3578  stelem.ref
0x3579  call     instance string [Microsoft.Crm.Setup.Common]Microsoft.Crm.Setup.Common.Validator::GetResourceString(string, object[])
0x357e  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0x3583  stloc.2
0x3584  leave.s  loc_358D
0x3586  ldc.i4.0
0x3587  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult)
0x358c  ret
0x358d  ldloc.2
0x358e  ret
```
