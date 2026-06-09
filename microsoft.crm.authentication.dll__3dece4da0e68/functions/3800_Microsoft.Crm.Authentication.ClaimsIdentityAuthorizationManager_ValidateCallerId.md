# Microsoft.Crm.Authentication.ClaimsIdentityAuthorizationManager::ValidateCallerId

- ea: `0x3800`
- end: `0x38b8`
- name: `Microsoft.Crm.Authentication.ClaimsIdentityAuthorizationManager::ValidateCallerId`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x31b0`

## callees

- `0x1cc0`
- `0x1e30`
- `0x1ee0`
- `0x3180`
- `0x3800`
- `0x3ae0`

## pseudocode

```c

```

## disassembly

```asm
0x3800  ldarg.0
0x3801  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.CrmIdentity::get_CallerId()
0x3806  stloc.0
0x3807  ldarg.0
0x3808  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.CrmIdentity::get_OrganizationId()
0x380d  stloc.1
0x380e  ldloc.0
0x380f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3814  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3819  brfalse.s loc_3827
0x381b  call     class [System.ServiceModel]System.ServiceModel.OperationContext [System.ServiceModel]System.ServiceModel.OperationContext::get_Current()
0x3820  ldloc.1
0x3821  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.UserIdentityAuthorizationManager::GetCallerId(class [System.ServiceModel]System.ServiceModel.OperationContext context, valuetype [mscorlib]System.Guid organizationId)
0x3826  stloc.0
0x3827  ldloc.0
0x3828  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x382d  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3832  brfalse.s loc_386F
0x3834  ldarg.0
0x3835  ldloc.0
0x3836  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.CrmIdentity::DoRecognizeUser(class [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.CrmIdentity, valuetype [mscorlib]System.Guid)
0x383b  brfalse.s loc_3845
0x383d  ldarg.0
0x383e  ldloc.0
0x383f  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.CrmIdentity::set_CallerId(valuetype [mscorlib]System.Guid)
0x3844  ret
0x3845  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x384a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x384f  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_OnePartyModel()
0x3854  ldloc.1
0x3855  ldloc.1
0x3856  call     class [mscorlib]System.Version Microsoft.Crm.Authentication.ClaimsIdentityAuthorizationManager::GetOrgVersion(valuetype [mscorlib]System.Guid orgId)
0x385b  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::IsEnabled(valuetype [mscorlib]System.Guid, class [mscorlib]System.Version)
0x3860  brfalse.s loc_38B7
0x3862  call     class [System.ServiceModel]System.ServiceModel.OperationContext [System.ServiceModel]System.ServiceModel.OperationContext::get_Current()
0x3867  ldarg.0
0x3868  ldloc.0
0x3869  call     void Microsoft.Crm.Authentication.ClaimsIdentityAuthorizationManager::ValidateAndSetExternalPartyParams(class [System.ServiceModel]System.ServiceModel.OperationContext operationContext, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.UserIdentity identity, valuetype [mscorlib]System.Guid callerId)
0x386e  ret
0x386f  call     class [System.ServiceModel]System.ServiceModel.OperationContext [System.ServiceModel]System.ServiceModel.OperationContext::get_Current()
0x3874  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.UserType Microsoft.Crm.Authentication.UserIdentityAuthorizationManager::GetUserType(class [System.ServiceModel]System.ServiceModel.OperationContext context)
0x3879  ldc.i4.1
0x387a  bne.un.s loc_38B7
0x387c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3881  ldstr    aInvalidExterna// "Invalid ExternalParty Parameters: Calle"...
0x3886  ldc.i4.2
0x3887  newarr   [mscorlib]System.Object
0x388c  dup
0x388d  ldc.i4.0
0x388e  ldloc.0
0x388f  box      [mscorlib]System.Guid
0x3894  stelem.ref
0x3895  dup
0x3896  ldc.i4.1
0x3897  call     class [System.ServiceModel]System.ServiceModel.OperationContext [System.ServiceModel]System.ServiceModel.OperationContext::get_Current()
0x389c  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.UserIdentityAuthorizationManager::GetCallerRegardingObjectId(class [System.ServiceModel]System.ServiceModel.OperationContext context)
0x38a1  box      [mscorlib]System.Guid
0x38a6  stelem.ref
0x38a7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x38ac  ldc.i4   0x8006110F
0x38b1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x38b6  throw
0x38b7  ret
```
