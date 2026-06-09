# Microsoft.Crm.Application.Platform.AppFormFilter::SetLastViewedForm

- ea: `0x6c150`
- end: `0x6c39a`
- name: `Microsoft.Crm.Application.Platform.AppFormFilter::SetLastViewedForm`
- size: `586`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x6bf10`

## callees

- `0x1c120`
- `0x1c1d0`
- `0x30130`
- `0x31310`
- `0x47920`
- `0x47940`
- `0x595f0`
- `0x59690`
- `0x5be40`
- `0x5c2b0`
- `0x6c150`
- `0x6c420`
- `0x6c500`
- `0x6c5f0`
- `0x6c620`

## string_xrefs

- `0x6c22a`: `userentityuisettingsid`
- `0x6c1fd`: `lastviewedformxml`
- `0x6c2e3`: `Duplicate record is found when inserts lastviewedformxml for user: {0} with objectTypeCode: {1}`
- `0x6c35b`: `User: {0} doesn't have create privilege in UserEntityUISettings table when inserts lastviewedformxml with objectTypeCode: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x6c150  ldarg.0
0x6c151  ldfld    class Microsoft.Crm.Application.Platform.FormFilterInformation Microsoft.Crm.Application.Platform.AppFormFilter::_formFilterInformation
0x6c156  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Platform.FormFilterInformation::get_UserId()
0x6c15b  ldarg.0
0x6c15c  ldfld    class Microsoft.Crm.Application.Platform.FormFilterInformation Microsoft.Crm.Application.Platform.AppFormFilter::_formFilterInformation
0x6c161  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.FormFilterInformation::get_Context()
0x6c166  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x6c16b  call     bool [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::IsSupportUser(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6c170  brfalse.s loc_6C173
0x6c172  ret
0x6c173  ldarg.1
0x6c174  ldarg.0
0x6c175  ldfld    class Microsoft.Crm.Application.Platform.FormFilterInformation Microsoft.Crm.Application.Platform.AppFormFilter::_formFilterInformation
0x6c17a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.FormFilterInformation::get_Context()
0x6c17f  call     class Microsoft.Crm.Application.FormDescriptor Microsoft.Crm.Application.Forms.FormDescriptorCache::GetFormDescriptor(valuetype [mscorlib]System.Guid formId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x6c184  dup
0x6c185  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Application.FormDescriptor::get_EntityMetadata()
0x6c18a  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x6c18f  stloc.0
0x6c190  callvirt instance valuetype Microsoft.Crm.Application.FormType Microsoft.Crm.Application.FormDescriptor::get_FormType()
0x6c195  stloc.1
0x6c196  ldarg.0
0x6c197  ldloc.0
0x6c198  ldloc.1
0x6c199  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Application.Platform.AppFormFilter::GetLastViewedForm(int32 objectTypeCode, valuetype Microsoft.Crm.Application.FormType formType)
0x6c19e  stloc.2
0x6c19f  ldloca.s 2
0x6c1a1  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x6c1a6  brfalse.s loc_6C1BA
0x6c1a8  ldloca.s 2
0x6c1aa  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x6c1af  ldarg.1
0x6c1b0  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6c1b5  brfalse  loc_6C399
0x6c1ba  ldloc.0
0x6c1bb  ldarg.0
0x6c1bc  ldfld    class Microsoft.Crm.Application.Platform.FormFilterInformation Microsoft.Crm.Application.Platform.AppFormFilter::_formFilterInformation
0x6c1c1  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Platform.FormFilterInformation::get_UserId()
0x6c1c6  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserEntityUISettingsCache::CreateKey(int32, valuetype [mscorlib]System.Guid)
0x6c1cb  stloc.3
0x6c1cc  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserEntityUISettingsCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserEntityUISettingsCache::Instance()
0x6c1d1  ldloc.3
0x6c1d2  ldarg.0
0x6c1d3  ldfld    class Microsoft.Crm.Application.Platform.FormFilterInformation Microsoft.Crm.Application.Platform.AppFormFilter::_formFilterInformation
0x6c1d8  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.FormFilterInformation::get_Context()
0x6c1dd  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUserEntityUISettings>::LookupEntry(void, var<u1>)
0x6c1e2  stloc.s  4
0x6c1e4  ldstr    aUserentityuise// "userentityuisettings"
0x6c1e9  ldarg.0
0x6c1ea  ldfld    class Microsoft.Crm.Application.Platform.FormFilterInformation Microsoft.Crm.Application.Platform.AppFormFilter::_formFilterInformation
0x6c1ef  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.FormFilterInformation::get_Context()
0x6c1f4  call     class Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(string entityName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x6c1f9  stloc.s  5
0x6c1fb  ldloc.s  5
0x6c1fd  ldstr    aLastviewedform// "lastviewedformxml"
0x6c202  ldarg.1
0x6c203  ldloc.1
0x6c204  ldloc.s  4
0x6c206  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUserEntityUISettings::get_LastViewedFormXml()
0x6c20b  call     string Microsoft.Crm.Application.Platform.AppFormFilter::CreateLastViewedFormXml(valuetype [mscorlib]System.Guid formId, valuetype Microsoft.Crm.Application.FormType formType, string existingXml)
0x6c210  callvirt instance void Microsoft.Crm.Application.Platform.EntityBase::set_Item(string name, object value)
0x6c215  ldloc.s  4
0x6c217  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUserEntityUISettings::get_UserEntityUISettingsId()
0x6c21c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6c221  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6c226  brfalse.s loc_6C26A
0x6c228  ldloc.s  5
0x6c22a  ldstr    aUserentityuise_0// "userentityuisettingsid"
0x6c22f  ldloc.s  4
0x6c231  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUserEntityUISettings::get_UserEntityUISettingsId()
0x6c236  box      [mscorlib]System.Guid
0x6c23b  callvirt instance void Microsoft.Crm.Application.Platform.EntityBase::set_Item(string name, object value)
0x6c240  newobj   instance void Microsoft.Crm.Application.Security.WrpcValidationBypass::.ctor()
0x6c245  stloc.s  6
0x6c247  ldloc.s  5
0x6c249  ldarg.0
0x6c24a  ldfld    class Microsoft.Crm.Application.Platform.FormFilterInformation Microsoft.Crm.Application.Platform.AppFormFilter::_formFilterInformation
0x6c24f  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.FormFilterInformation::get_Context()
0x6c254  call     void Microsoft.Crm.Application.Platform.DataSource::Update(class Microsoft.Crm.Application.Platform.EntityProxy entity, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x6c259  leave    loc_6C399
0x6c25e  ldloc.s  6
0x6c260  brfalse.s loc_6C269
0x6c262  ldloc.s  6
0x6c264  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6c269  endfinally
0x6c26a  ldloc.s  5
0x6c26c  ldstr    aObjecttypecode// "objecttypecode"
0x6c271  ldloc.0
0x6c272  box      [mscorlib]System.Int32
0x6c277  callvirt instance void Microsoft.Crm.Application.Platform.EntityBase::set_Item(string name, object value)
0x6c27c  ldloc.s  5
0x6c27e  ldstr    aOwnerid// "ownerid"
0x6c283  ldarg.0
0x6c284  ldfld    class Microsoft.Crm.Application.Platform.FormFilterInformation Microsoft.Crm.Application.Platform.AppFormFilter::_formFilterInformation
0x6c289  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Platform.FormFilterInformation::get_UserId()
0x6c28e  box      [mscorlib]System.Guid
0x6c293  callvirt instance void Microsoft.Crm.Application.Platform.EntityBase::set_Item(string name, object value)
0x6c298  ldloc.s  5
0x6c29a  ldstr    aOwneridtype// "owneridtype"
0x6c29f  ldc.i4.8
0x6c2a0  box      [mscorlib]System.Int32
0x6c2a5  callvirt instance void Microsoft.Crm.Application.Platform.EntityBase::set_Item(string name, object value)
0x6c2aa  newobj   instance void Microsoft.Crm.Application.Security.WrpcValidationBypass::.ctor()
0x6c2af  stloc.s  6
0x6c2b1  ldloc.s  5
0x6c2b3  ldarg.0
0x6c2b4  ldfld    class Microsoft.Crm.Application.Platform.FormFilterInformation Microsoft.Crm.Application.Platform.AppFormFilter::_formFilterInformation
0x6c2b9  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.FormFilterInformation::get_Context()
0x6c2be  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Platform.DataSource::Create(class Microsoft.Crm.Application.Platform.EntityProxy entity, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x6c2c3  pop
0x6c2c4  leave    loc_6C399
0x6c2c9  stloc.s  7
0x6c2cb  ldloc.s  7
0x6c2cd  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x6c2d2  ldc.i4   0x80040237
0x6c2d7  bne.un.s loc_6C311
0x6c2d9  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Utility.Util::get_TraceOrganizationId()
0x6c2de  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x6c2e3  ldstr    aDuplicateRecor// "Duplicate record is found when inserts "...
0x6c2e8  ldc.i4.2
0x6c2e9  newarr   [mscorlib]System.Object
0x6c2ee  dup
0x6c2ef  ldc.i4.0
0x6c2f0  ldarg.0
0x6c2f1  ldfld    class Microsoft.Crm.Application.Platform.FormFilterInformation Microsoft.Crm.Application.Platform.AppFormFilter::_formFilterInformation
0x6c2f6  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Platform.FormFilterInformation::get_UserId()
0x6c2fb  box      [mscorlib]System.Guid
0x6c300  stelem.ref
0x6c301  dup
0x6c302  ldc.i4.1
0x6c303  ldloc.0
0x6c304  box      [mscorlib]System.Int32
0x6c309  stelem.ref
0x6c30a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6c30f  br.s     loc_6C38B
0x6c311  ldloc.s  7
0x6c313  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x6c318  ldc.i4   0x80048306
0x6c31d  bne.un.s loc_6C389
0x6c31f  ldloc.s  7
0x6c321  callvirt instance string [mscorlib]System.Exception::get_Message()
0x6c326  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6c32b  ldstr    aObjecttypecode_2// "ObjectTypeCode: {0}"
0x6c330  ldc.i4.1
0x6c331  newarr   [mscorlib]System.Object
0x6c336  dup
0x6c337  ldc.i4.0
0x6c338  ldc.i4   0x9C4
0x6c33d  box      [mscorlib]System.Int32
0x6c342  stelem.ref
0x6c343  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6c348  ldc.i4.5
0x6c349  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x6c34e  ldc.i4.0
0x6c34f  ble.s    loc_6C389
0x6c351  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Utility.Util::get_TraceOrganizationId()
0x6c356  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x6c35b  ldstr    aUser0DoesnTHav// "User: {0} doesn't have create privilege"...
0x6c360  ldc.i4.2
0x6c361  newarr   [mscorlib]System.Object
0x6c366  dup
0x6c367  ldc.i4.0
0x6c368  ldarg.0
0x6c369  ldfld    class Microsoft.Crm.Application.Platform.FormFilterInformation Microsoft.Crm.Application.Platform.AppFormFilter::_formFilterInformation
0x6c36e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Platform.FormFilterInformation::get_UserId()
0x6c373  box      [mscorlib]System.Guid
0x6c378  stelem.ref
0x6c379  dup
0x6c37a  ldc.i4.1
0x6c37b  ldloc.0
0x6c37c  box      [mscorlib]System.Int32
0x6c381  stelem.ref
0x6c382  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6c387  br.s     loc_6C38B
0x6c389  rethrow
0x6c38b  leave.s  loc_6C399
0x6c38d  ldloc.s  6
0x6c38f  brfalse.s loc_6C398
0x6c391  ldloc.s  6
0x6c393  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6c398  endfinally
0x6c399  ret
```
