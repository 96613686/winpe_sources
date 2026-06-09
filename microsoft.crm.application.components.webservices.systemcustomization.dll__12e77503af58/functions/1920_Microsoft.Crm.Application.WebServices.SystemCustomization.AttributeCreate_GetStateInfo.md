# Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetStateInfo

- ea: `0x1920`
- end: `0x1a01`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetStateInfo`
- size: `225`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x430`

## callees

- `0x1920`

## pseudocode

```c

```

## disassembly

```asm
0x1920  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1925  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x192a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x192f  stloc.0
0x1930  ldloc.0
0x1931  newobj   instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.StateAttributeInfo::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1936  stloc.1
0x1937  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x193c  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x1941  stloc.2
0x1942  ldarg.0
0x1943  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StateAttributeMetadata
0x1948  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IStateOptionsByValueCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StateAttributeMetadata::get_StateOptions()
0x194d  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StateOption>::GetEnumerator()
0x1952  stloc.3
0x1953  br       loc_19E8
0x1958  ldloc.3
0x1959  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StateOption>::get_Current()
0x195e  dup
0x195f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Labels()
0x1964  ldloc.2
0x1965  ldloc.0
0x1966  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x196b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0x1970  stloc.s  4
0x1972  dup
0x1973  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Value()
0x1978  stloc.s  5
0x197a  dup
0x197b  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StateOption::get_DefaultStatus()
0x1980  stloc.s  6
0x1982  ldloc.2
0x1983  ldloc.s  4
0x1985  ldloc.0
0x1986  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::.ctor(int32, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x198b  stloc.s  7
0x198d  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::.ctor()
0x1992  stloc.s  8
0x1994  ldloc.s  8
0x1996  ldloc.s  7
0x1998  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label)
0x199d  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::.ctor()
0x19a2  stloc.s  9
0x19a4  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StateOption::get_InvariantName()
0x19a9  stloc.s  0xA
0x19ab  ldloc.s  5
0x19ad  ldloc.s  6
0x19af  ldloc.s  0xA
0x19b1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x19b6  brtrue.s loc_19BC
0x19b8  ldloc.s  0xA
0x19ba  br.s     loc_19BE
0x19bc  ldloc.s  4
0x19be  ldloc.s  8
0x19c0  ldloc.s  9
0x19c2  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PreloadedEnumOptionMetadataDataProviderFull::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection)
0x19c7  ldloc.0
0x19c8  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StateOption::.ctor(int32, int32, string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEnumOptionMetadataDataProvider, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x19cd  stloc.s  0xB
0x19cf  ldloc.1
0x19d0  callvirt instance class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetInfo [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EnumAttributeInfo::get_OptionSet()
0x19d5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOptionByValueDictionary [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.OptionSetInfo::get_Options()
0x19da  ldloc.s  0xB
0x19dc  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Value()
0x19e1  ldloc.s  0xB
0x19e3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::Add(var<u1>, !!T0)
0x19e8  ldloc.3
0x19e9  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x19ee  brtrue   loc_1958
0x19f3  leave.s  loc_19FF
0x19f5  ldloc.3
0x19f6  brfalse.s loc_19FE
0x19f8  ldloc.3
0x19f9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x19fe  endfinally
0x19ff  ldloc.1
0x1a00  ret
```
