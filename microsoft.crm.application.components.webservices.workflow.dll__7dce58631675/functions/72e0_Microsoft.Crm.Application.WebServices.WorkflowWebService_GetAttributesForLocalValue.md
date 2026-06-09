# Microsoft.Crm.Application.WebServices.WorkflowWebService::GetAttributesForLocalValue

- ea: `0x72e0`
- end: `0x74e6`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::GetAttributesForLocalValue`
- size: `518`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ab0`
- `0x72e0`
- `0x83c0`

## pseudocode

```c

```

## disassembly

```asm
0x72e0  ldarg.1
0x72e1  ldstr    aLocalvaluekey// "localValueKey"
0x72e6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x72eb  ldarg.1
0x72ec  ldc.i4.1
0x72ed  newarr   [mscorlib]System.Char
0x72f2  dup
0x72f3  ldc.i4.0
0x72f4  ldc.i4.s 0x23
0x72f6  stelem.i2
0x72f7  ldc.i4.1
0x72f8  callvirt instance string[] [mscorlib]System.String::Split(char[], valuetype [mscorlib]System.StringSplitOptions)
0x72fd  stloc.0
0x72fe  ldloc.0
0x72ff  ldlen
0x7300  conv.i4
0x7301  ldc.i4.3
0x7302  ceq
0x7304  ldstr    aLocalvaluekeyH// "localValueKey has invalid format"
0x7309  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x730e  ldloc.0
0x730f  ldc.i4.0
0x7310  ldelem.ref
0x7311  pop
0x7312  ldloc.0
0x7313  ldc.i4.2
0x7314  ldelem.ref
0x7315  stloc.1
0x7316  ldarg.0
0x7317  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x731c  ldloc.0
0x731d  ldc.i4.1
0x731e  ldelem.ref
0x731f  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x7324  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x7329  stloc.2
0x732a  ldloc.2
0x732b  ldloc.1
0x732c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x7331  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.DataSourceCollection [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_DataSources()
0x7336  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IDataSource> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.DataSourceCollection::GetEnumerator()
0x733b  stloc.3
0x733c  br       loc_74BC
0x7341  ldloc.3
0x7342  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IDataSource>::get_Current()
0x7347  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ValuesCreatedByStep
0x734c  stloc.s  4
0x734e  ldloc.s  4
0x7350  brfalse  loc_74BC
0x7355  ldarg.1
0x7356  ldloc.s  4
0x7358  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ValuesCreatedByStep::get_Key()
0x735d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7362  brfalse  loc_74BC
0x7367  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x736c  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x7371  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_AnyChanelToAnyEntityRecordCreation()
0x7376  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x737b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x7380  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationBuildVersionCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationBuildVersionCache::Instance()
0x7385  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x738a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x738f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x7394  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x7399  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x739e  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.BasicCrmCache`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.VersionCacheData>::LookupEntry(void, var<u1>)
0x73a3  callvirt instance class [mscorlib]System.Version [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.VersionCacheData::get_CrmVersion()
0x73a8  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::IsEnabled(valuetype [mscorlib]System.Guid, class [mscorlib]System.Version)
0x73ad  brfalse.s loc_73F7
0x73af  ldloc.s  4
0x73b1  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ValuesCreatedByStep::get_Key()
0x73b6  ldstr    aUiscript// "UIScript"
0x73bb  callvirt instance bool [mscorlib]System.String::Contains(string)
0x73c0  brfalse.s loc_73F7
0x73c2  ldloc.2
0x73c3  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PublicationParameters()
0x73c8  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::get_WorkflowRendererObjectTypeCode()
0x73cd  brfalse.s loc_73F7
0x73cf  ldloc.2
0x73d0  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PublicationParameters()
0x73d5  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::get_WorkflowRendererObjectTypeCode()
0x73da  ldstr    aConvertruleite// "ConvertRuleItem"
0x73df  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x73e4  call     instance string [mscorlib]System.String::ToLower(class [mscorlib]System.Globalization.CultureInfo)
0x73e9  callvirt instance bool [mscorlib]System.String::Equals(string)
0x73ee  brfalse.s loc_73F7
0x73f0  ldloc.s  4
0x73f2  call     void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.Any2AnyUtilities::RemoveOOBParameters(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ValuesCreatedByStep)
0x73f7  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x73fc  stloc.s  5
0x73fe  ldloc.s  4
0x7400  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.DataValueCollection [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ValuesCreatedByStep::get_AllDataValues()
0x7405  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.DataValue> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.DataValueCollection::GetEnumerator()
0x740a  stloc.s  6
0x740c  br       loc_7497
0x7411  ldloc.s  6
0x7413  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.DataValue>::get_Current()
0x7418  stloc.s  7
0x741a  ldarg.2
0x741b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7420  brfalse.s loc_744E
0x7422  ldloc.s  7
0x7424  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.DataValue::get_Key()
0x7429  ldstr    asc_BD0A// "#"
0x742e  ldc.i4.3
0x742f  stloc.s  8
0x7431  ldloca.s 8
0x7433  constrained. [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.PredefinedDataValue
0x7439  callvirt instance string [mscorlib]System.Object::ToString()
0x743e  call     string [mscorlib]System.String::Concat(string, string)
0x7443  ldc.i4.4
0x7444  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x7449  ldc.i4.0
0x744a  blt.s    loc_7486
0x744c  br.s     loc_7497
0x744e  ldarg.2
0x744f  ldstr    aTimeoutonly// "timeoutonly"
0x7454  ldc.i4.4
0x7455  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x745a  brtrue.s loc_7486
0x745c  ldloc.s  7
0x745e  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.DataValue::get_Key()
0x7463  ldstr    asc_BD0A// "#"
0x7468  ldc.i4.3
0x7469  stloc.s  8
0x746b  ldloca.s 8
0x746d  constrained. [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.PredefinedDataValue
0x7473  callvirt instance string [mscorlib]System.Object::ToString()
0x7478  call     string [mscorlib]System.String::Concat(string, string)
0x747d  ldc.i4.4
0x747e  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x7483  ldc.i4.0
0x7484  blt.s    loc_7497
0x7486  ldloc.s  5
0x7488  ldarg.0
0x7489  ldloc.2
0x748a  ldloc.s  7
0x748c  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::FormatLocalValueAsAttributeXml(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.DataValue value)
0x7491  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x7496  pop
0x7497  ldloc.s  6
0x7499  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x749e  brtrue   loc_7411
0x74a3  leave.s  loc_74B1
0x74a5  ldloc.s  6
0x74a7  brfalse.s loc_74B0
0x74a9  ldloc.s  6
0x74ab  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x74b0  endfinally
0x74b1  ldloc.s  5
0x74b3  callvirt instance string [mscorlib]System.Object::ToString()
0x74b8  stloc.s  9
0x74ba  leave.s  loc_74E3
0x74bc  ldloc.3
0x74bd  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x74c2  brtrue   loc_7341
0x74c7  leave.s  loc_74D3
0x74c9  ldloc.3
0x74ca  brfalse.s loc_74D2
0x74cc  ldloc.3
0x74cd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x74d2  endfinally
0x74d3  ldnull
0x74d4  stloc.s  9
0x74d6  leave.s  loc_74E3
0x74d8  stloc.s  0xA
0x74da  ldarg.0
0x74db  ldloc.s  0xA
0x74dd  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x74e2  throw
0x74e3  ldloc.s  9
0x74e5  ret
```
