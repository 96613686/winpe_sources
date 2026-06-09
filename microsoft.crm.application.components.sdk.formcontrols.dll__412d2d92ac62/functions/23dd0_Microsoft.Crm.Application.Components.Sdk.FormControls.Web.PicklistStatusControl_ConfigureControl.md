# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl::ConfigureControl

- ea: `0x23dd0`
- end: `0x23f11`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl::ConfigureControl`
- size: `321`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x17cf0`
- `0x182d0`
- `0x18670`
- `0x23c90`
- `0x23ca0`
- `0x23da0`
- `0x23dc0`
- `0x23dd0`
- `0x241b0`

## string_xrefs

- `0x23e6d`: `service`
- `0x23e84`: `serviceappointment`
- `0x23ea3`: `Scheduled`

## pseudocode

```c

```

## disassembly

```asm
0x23dd0  ldarg.0
0x23dd1  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::ConfigureControl()
0x23dd6  ldarg.0
0x23dd7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x23ddc  brtrue.s loc_23DF9
0x23dde  ldstr    aSetTheMetadata// "Set the metadata on control "
0x23de3  ldarg.0
0x23de4  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x23de9  ldstr    aFirstThisContr// " first. This control cannot be non-meta"...
0x23dee  call     string [mscorlib]System.String::Concat(string, string, string)
0x23df3  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x23df8  throw
0x23df9  ldc.i4.m1
0x23dfa  ldarg.0
0x23dfb  ldfld    int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl::_value
0x23e00  bne.un   loc_23EE5
0x23e05  ldarg.0
0x23e06  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl::get_OptionsMetadata()
0x23e0b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Entity()
0x23e10  ldstr    aStatecode// "statecode"
0x23e15  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string)
0x23e1a  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StateAttributeMetadata
0x23e1f  stloc.0
0x23e20  ldloc.0
0x23e21  brfalse.s loc_23E46
0x23e23  ldarg.0
0x23e24  ldloc.0
0x23e25  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IStateOptionsByValueCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StateAttributeMetadata::get_StateOptions()
0x23e2a  ldarg.0
0x23e2b  call     instance int32[] Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl::get_States()
0x23e30  ldc.i4.0
0x23e31  ldelem.i4
0x23e32  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEnumOptionsByValueCollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StateOption>::get_Item(!!T0)
0x23e37  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StateOption::get_DefaultStatus()
0x23e3c  stfld    int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl::_value
0x23e41  br       loc_23EE5
0x23e46  ldarg.0
0x23e47  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl::_metadata
0x23e4c  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Name()
0x23e51  ldstr    aInitialstatusc// "initialstatuscode"
0x23e56  call     bool [mscorlib]System.String::op_Equality(string, string)
0x23e5b  brfalse.s loc_23ED4
0x23e5d  ldarg.0
0x23e5e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x23e63  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Entity()
0x23e68  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x23e6d  ldstr    aService// "service"
0x23e72  call     bool [mscorlib]System.String::op_Equality(string, string)
0x23e77  brfalse.s loc_23ED4
0x23e79  ldarg.0
0x23e7a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x23e7f  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x23e84  ldstr    aServiceappoint// "serviceappointment"
0x23e89  ldc.i4.1
0x23e8a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x23e8f  ldstr    aStatuscode// "statuscode"
0x23e94  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string)
0x23e99  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl::set_OptionsMetadata(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata value)
0x23e9e  ldstr    aActivitypointe_1// "activitypointer"
0x23ea3  ldstr    aScheduled// "Scheduled"
0x23ea8  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::ConvertStateToNumber(string, string)
0x23ead  stloc.1
0x23eae  ldstr    aActivitypointe_1// "activitypointer"
0x23eb3  ldstr    aOpen// "Open"
0x23eb8  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::ConvertStateToNumber(string, string)
0x23ebd  stloc.2
0x23ebe  ldarg.0
0x23ebf  ldc.i4.2
0x23ec0  newarr   [mscorlib]System.Int32
0x23ec5  dup
0x23ec6  ldc.i4.0
0x23ec7  ldloc.1
0x23ec8  stelem.i4
0x23ec9  dup
0x23eca  ldc.i4.1
0x23ecb  ldloc.2
0x23ecc  stelem.i4
0x23ecd  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl::set_States(int32[] value)
0x23ed2  br.s     loc_23EE5
0x23ed4  ldc.i4   0x80040216
0x23ed9  ldc.i4.0
0x23eda  newarr   [mscorlib]System.Object
0x23edf  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x23ee4  throw
0x23ee5  ldarg.0
0x23ee6  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl::PopulateDefaultState()
0x23eeb  ldarg.0
0x23eec  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmFormUIControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlUIWrapper::get_InnerControl()
0x23ef1  isinst   [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select
0x23ef6  ldarg.0
0x23ef7  ldflda   int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl::_value
0x23efc  ldstr    aD// "D"
0x23f01  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x23f06  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x23f0b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::set_Selected(string)
0x23f10  ret
```
