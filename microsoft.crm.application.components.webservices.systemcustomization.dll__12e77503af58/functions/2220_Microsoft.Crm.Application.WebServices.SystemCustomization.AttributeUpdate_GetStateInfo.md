# Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeUpdate::GetStateInfo

- ea: `0x2220`
- end: `0x23c2`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeUpdate::GetStateInfo`
- size: `418`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x20e0`

## callees

- `0x1a0`
- `0x1c0`
- `0x270`
- `0x2220`

## pseudocode

```c

```

## disassembly

```asm
0x2220  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2225  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x222a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x222f  stloc.0
0x2230  ldloc.0
0x2231  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.StateAttributeInfo::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2236  stloc.1
0x2237  ldarg.0
0x2238  ldstr    aStates// "states"
0x223d  callvirt instance class Microsoft.Crm.Application.WebServices.ParameterBag Microsoft.Crm.Application.WebServices.ParameterBag::GetBag(string name)
0x2242  ldstr    aState// "state"
0x2247  callvirt instance class Microsoft.Crm.Application.WebServices.ParameterBag[] Microsoft.Crm.Application.WebServices.ParameterBag::GetBagArray(string name)
0x224c  stloc.2
0x224d  ldc.i4.0
0x224e  stloc.3
0x224f  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x2254  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x2259  stloc.s  4
0x225b  ldloc.1
0x225c  ldarg.1
0x225d  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PhysicalName()
0x2262  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo::set_Name(string)
0x2267  ldloc.1
0x2268  ldarg.1
0x2269  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Locked()
0x226e  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo::set_Locked(bool)
0x2273  ldloc.1
0x2274  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x2279  ldarg.1
0x227a  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_DisplayMask()
0x227f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_DisplayMask(int32)
0x2284  ldloc.1
0x2285  ldarg.1
0x2286  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_IsSecured()
0x228b  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo::set_IsSecured(bool)
0x2290  ldloc.1
0x2291  ldarg.1
0x2292  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_AttributeRequiredLevelId()
0x2297  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel>::.ctor(var<u1>)
0x229c  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo::set_RequiredLevel(valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel>)
0x22a1  ldloc.1
0x22a2  ldarg.1
0x22a3  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeIMEMode [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_AttributeImeModeId()
0x22a8  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo::set_IMEMode(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeIMEMode)
0x22ad  ldloc.1
0x22ae  ldarg.1
0x22af  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_IsAuditEnabled()
0x22b4  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo::set_IsAuditEnabled(bool)
0x22b9  ldloc.1
0x22ba  ldarg.1
0x22bb  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_IsGlobalFilterEnabled()
0x22c0  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo::set_IsGlobalFilterEnabled(bool)
0x22c5  ldloc.1
0x22c6  ldarg.1
0x22c7  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_IsSortableEnabled()
0x22cc  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo::set_IsSortableEnabled(bool)
0x22d1  ldarg.1
0x22d2  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StateAttributeMetadata
0x22d7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IStateOptionsByValueCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StateAttributeMetadata::get_StateOptions()
0x22dc  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StateOption>::GetEnumerator()
0x22e1  stloc.s  5
0x22e3  br       loc_23A6
0x22e8  ldloc.s  5
0x22ea  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StateOption>::get_Current()
0x22ef  stloc.s  6
0x22f1  ldloc.2
0x22f2  ldloc.3
0x22f3  ldelem.ref
0x22f4  ldstr    aValue// "value"
0x22f9  callvirt instance int32 Microsoft.Crm.Application.WebServices.ParameterBag::GetInt(string name)
0x22fe  ldloc.s  6
0x2300  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Value()
0x2305  beq.s    loc_2312
0x2307  ldstr    aInvalidStateOr// "Invalid state or state order"
0x230c  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x2311  throw
0x2312  ldloc.2
0x2313  ldloc.3
0x2314  ldelem.ref
0x2315  ldstr    aValues// "values"
0x231a  callvirt instance class Microsoft.Crm.Application.WebServices.ParameterBag Microsoft.Crm.Application.WebServices.ParameterBag::GetBag(string name)
0x231f  ldloc.s  6
0x2321  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Labels()
0x2326  ldloc.s  4
0x2328  ldloc.0
0x2329  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x232e  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0x2333  stloc.s  7
0x2335  ldloc.s  6
0x2337  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Value()
0x233c  stloc.s  8
0x233e  ldstr    aDefault// "default"
0x2343  callvirt instance int32 Microsoft.Crm.Application.WebServices.ParameterBag::GetInt(string name)
0x2348  stloc.s  9
0x234a  ldloc.s  4
0x234c  ldloc.s  7
0x234e  ldloc.0
0x234f  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::.ctor(int32, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2354  stloc.s  0xA
0x2356  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::.ctor()
0x235b  stloc.s  0xB
0x235d  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::.ctor()
0x2362  stloc.s  0xC
0x2364  ldloc.s  0xB
0x2366  ldloc.s  0xA
0x2368  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label)
0x236d  ldloc.s  8
0x236f  ldloc.s  9
0x2371  ldloc.s  6
0x2373  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StateOption::get_InvariantName()
0x2378  ldloc.s  0xB
0x237a  ldloc.s  0xC
0x237c  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PreloadedEnumOptionMetadataDataProviderFull::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection)
0x2381  ldloc.0
0x2382  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StateOption::.ctor(int32, int32, string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEnumOptionMetadataDataProvider, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2387  stloc.s  0xD
0x2389  ldloc.1
0x238a  callvirt instance class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetInfo [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EnumAttributeInfo::get_OptionSet()
0x238f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOptionByValueDictionary [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetInfo::get_Options()
0x2394  ldloc.s  0xD
0x2396  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Value()
0x239b  ldloc.s  0xD
0x239d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::Add(var<u1>, !!T0)
0x23a2  ldloc.3
0x23a3  ldc.i4.1
0x23a4  add
0x23a5  stloc.3
0x23a6  ldloc.s  5
0x23a8  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x23ad  brtrue   loc_22E8
0x23b2  leave.s  loc_23C0
0x23b4  ldloc.s  5
0x23b6  brfalse.s loc_23BF
0x23b8  ldloc.s  5
0x23ba  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x23bf  endfinally
0x23c0  ldloc.1
0x23c1  ret
```
