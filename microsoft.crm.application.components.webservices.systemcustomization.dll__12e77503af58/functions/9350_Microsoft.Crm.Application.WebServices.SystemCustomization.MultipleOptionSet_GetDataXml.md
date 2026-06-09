# Microsoft.Crm.Application.WebServices.SystemCustomization.MultipleOptionSet::GetDataXml

- ea: `0x9350`
- end: `0x9536`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.MultipleOptionSet::GetDataXml`
- size: `486`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xb460`

## callees

- `0x9350`

## pseudocode

```c

```

## disassembly

```asm
0x9350  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPicklistEdit::.ctor()
0x9355  stloc.0
0x9356  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x935b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x9360  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x9365  stloc.1
0x9366  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::LoadMetadataCache()
0x936b  stloc.2
0x936c  ldnull
0x936d  stloc.3
0x936e  ldarg.2
0x936f  brtrue.s loc_9384
0x9371  ldloc.2
0x9372  ldc.i4.1
0x9373  ldc.i4.1
0x9374  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IOptionSetByIdDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetOptionSets(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetGlobalFilters, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetTypeFilters)
0x9379  ldarg.0
0x937a  ldloca.s 3
0x937c  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata>::TryGetValue(var<u1>, !!T0)
0x9381  pop
0x9382  br.s     loc_9399
0x9384  ldloc.2
0x9385  ldarg.0
0x9386  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetOptionSet(valuetype [mscorlib]System.Guid)
0x938b  stloc.s  5
0x938d  ldloc.s  5
0x938f  callvirt instance valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.OptionSetType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata::get_OptionSetType()
0x9394  brtrue.s loc_9399
0x9396  ldloc.s  5
0x9398  stloc.3
0x9399  ldloc.0
0x939a  ldarg.1
0x939b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext::GetSolutionContext(valuetype [mscorlib]System.Guid)
0x93a0  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext::get_OptionValuePrefix()
0x93a5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.PicklistEdit::set_PrefixValue(int32)
0x93aa  ldloc.0
0x93ab  callvirt instance int32 [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.PicklistEdit::get_PrefixValue()
0x93b0  ldc.i4   0x2710
0x93b5  mul
0x93b6  stloc.s  4
0x93b8  ldloc.0
0x93b9  ldc.i4   0x80000000
0x93be  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x93c3  ldstr    aSystemcustomiz_3// "SystemCustomization.Picklist.Values.Una"...
0x93c8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x93cd  ldc.i4.0
0x93ce  ldsfld   string [mscorlib]System.String::Empty
0x93d3  ldstr    a0000ff// "#0000ff"
0x93d8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.PicklistEdit::AddValue(int32, string, bool, string, string)
0x93dd  ldloc.3
0x93de  brfalse  loc_94F8
0x93e3  ldloc.0
0x93e4  ldc.i4   0x7FFFFFFE
0x93e9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.PicklistEdit::set_MaxValue(int32)
0x93ee  ldloc.0
0x93ef  ldc.i4   0x80000000
0x93f4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.PicklistEdit::set_DefaultValue(int32)
0x93f9  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x93fe  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_OrganizationId()
0x9403  ldc.i4.0
0x9404  ldc.i4.0
0x9405  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x940a  stloc.s  6
0x940c  ldloc.s  6
0x940e  ldc.i4.1
0x940f  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(bool)
0x9414  ldarg.0
0x9415  ldloc.s  6
0x9417  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x941c  call     int32 [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EnumOptionService::GetNextAvailableEnumValue(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x9421  stloc.s  4
0x9423  ldloc.s  6
0x9425  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnEndRequest()
0x942a  leave.s  loc_9438
0x942c  ldloc.s  6
0x942e  brfalse.s loc_9437
0x9430  ldloc.s  6
0x9432  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9437  endfinally
0x9438  ldloc.3
0x9439  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEnumOptionByValueDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata::get_Options()
0x943e  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [mscorlib]System.Collections.Generic.IDictionary`2<int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::get_Values()
0x9443  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::GetEnumerator()
0x9448  stloc.s  7
0x944a  br       loc_94DE
0x944f  ldloc.s  7
0x9451  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::get_Current()
0x9456  stloc.s  8
0x9458  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ListItemValue::.ctor()
0x945d  stloc.s  9
0x945f  ldloc.s  9
0x9461  ldloc.s  8
0x9463  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Value()
0x9468  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ListItemValue::set_Value(int32)
0x946d  ldloc.s  8
0x946f  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Color()
0x9474  stloc.s  0xA
0x9476  ldloc.s  9
0x9478  ldloc.s  8
0x947a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Labels()
0x947f  ldloc.1
0x9480  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Util::GetLabelString(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9485  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ListItemValue::set_Label(string)
0x948a  ldloc.s  9
0x948c  ldloc.s  8
0x948e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Descriptions()
0x9493  ldloc.1
0x9494  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Util::GetLabelString(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9499  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ListItemValue::set_Description(string)
0x949e  ldloc.s  9
0x94a0  ldc.i4.1
0x94a1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ListItemValue::set_Editable(bool)
0x94a6  ldloc.s  0xA
0x94a8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x94ad  brfalse.s loc_94B6
0x94af  ldstr    a0000ff// "#0000ff"
0x94b4  stloc.s  0xA
0x94b6  ldloc.s  8
0x94b8  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<int32> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_ParentValues()
0x94bd  brfalse.s loc_94CD
0x94bf  ldloc.s  9
0x94c1  ldloc.s  8
0x94c3  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<int32> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_ParentValues()
0x94c8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ListItemValue::set_ParentValues(class [mscorlib]System.Collections.Generic.IList`1<int32>)
0x94cd  ldloc.s  9
0x94cf  ldloc.s  0xA
0x94d1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ListItemValue::set_Color(string)
0x94d6  ldloc.0
0x94d7  ldloc.s  9
0x94d9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.PicklistEdit::AddValue(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ListItemValue)
0x94de  ldloc.s  7
0x94e0  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x94e5  brtrue   loc_944F
0x94ea  leave.s  loc_9517
0x94ec  ldloc.s  7
0x94ee  brfalse.s loc_94F7
0x94f0  ldloc.s  7
0x94f2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x94f7  endfinally
0x94f8  ldarga.s 0
0x94fa  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x94ff  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0x9504  brtrue.s loc_9517
0x9506  ldc.i4   0x80040363
0x950b  ldc.i4.0
0x950c  newarr   [mscorlib]System.Object
0x9511  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x9516  throw
0x9517  ldloc.0
0x9518  ldloc.s  4
0x951a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.PicklistEdit::set_NextValue(int32)
0x951f  ldloc.0
0x9520  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.PicklistEdit::get_DataXml()
0x9525  stloc.s  0xB
0x9527  leave.s  loc_9533
0x9529  ldloc.0
0x952a  brfalse.s loc_9532
0x952c  ldloc.0
0x952d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9532  endfinally
0x9533  ldloc.s  0xB
0x9535  ret
```
