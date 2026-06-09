# Microsoft.Crm.Application.Platform.ImportFile::GetMatchedHeaderColumns

- ea: `0x66cc0`
- end: `0x66def`
- name: `Microsoft.Crm.Application.Platform.ImportFile::GetMatchedHeaderColumns`
- size: `303`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x63c40`

## callees

- `0x2fb90`
- `0x2fbc0`
- `0x3aa00`
- `0x5bab0`
- `0x65ee0`
- `0x66cc0`
- `0x6a2d0`

## string_xrefs

- `0x66d41`: `createdon`
- `0x66d33`: `overriddencreatedon`

## pseudocode

```c

```

## disassembly

```asm
0x66cc0  call     class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x66cc5  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x66cca  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x66ccf  stloc.0
0x66cd0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x66cd5  stloc.1
0x66cd6  ldarg.1
0x66cd7  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x66cdc  stloc.2
0x66cdd  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x66ce2  stloc.3
0x66ce3  call     class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x66ce8  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x66ced  stloc.s  4
0x66cef  ldloc.0
0x66cf0  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x66cf5  ldarg.2
0x66cf6  ldc.i4.1
0x66cf7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x66cfc  stloc.s  5
0x66cfe  ldloc.s  5
0x66d00  ldarg.3
0x66d01  ldarg.0
0x66d02  call     instance class Microsoft.Crm.Application.Platform.EntityType Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x66d07  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.EntityType::get_Context()
0x66d0c  call     class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.Crm.Application.Platform.ImportEntity::GetImportableAttributes(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entity, bool isUpdateViaImport, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x66d11  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x66d16  stloc.s  6
0x66d18  br       loc_66D9E
0x66d1d  ldloc.s  6
0x66d1f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x66d24  stloc.s  7
0x66d26  ldloc.s  5
0x66d28  ldloc.s  7
0x66d2a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x66d2f  stloc.s  8
0x66d31  ldloc.s  7
0x66d33  ldstr    aOverriddencrea// "overriddencreatedon"
0x66d38  callvirt instance bool [mscorlib]System.String::Equals(string)
0x66d3d  brfalse.s loc_66D4D
0x66d3f  ldloc.s  5
0x66d41  ldstr    aCreatedon// "createdon"
0x66d46  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x66d4b  stloc.s  8
0x66d4d  ldloc.s  8
0x66d4f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_DisplayNames()
0x66d54  ldloc.s  4
0x66d56  ldloc.0
0x66d57  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::TryGetDescription(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x66d5c  callvirt instance string [mscorlib]System.String::Trim()
0x66d61  stloc.s  9
0x66d63  ldloc.s  9
0x66d65  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x66d6a  brtrue.s loc_66D9E
0x66d6c  ldloc.2
0x66d6d  ldloc.s  9
0x66d6f  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x66d74  brfalse.s loc_66D9E
0x66d76  ldloc.1
0x66d77  ldloc.s  9
0x66d79  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x66d7e  brfalse.s loc_66D94
0x66d80  ldloc.3
0x66d81  ldloc.s  9
0x66d83  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x66d88  brtrue.s loc_66D9E
0x66d8a  ldloc.3
0x66d8b  ldloc.s  9
0x66d8d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x66d92  br.s     loc_66D9E
0x66d94  ldloc.1
0x66d95  ldloc.s  9
0x66d97  ldloc.s  7
0x66d99  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x66d9e  ldloc.s  6
0x66da0  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x66da5  brtrue   loc_66D1D
0x66daa  leave.s  loc_66DB8
0x66dac  ldloc.s  6
0x66dae  brfalse.s loc_66DB7
0x66db0  ldloc.s  6
0x66db2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x66db7  endfinally
0x66db8  ldloc.3
0x66db9  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<string>::GetEnumerator()
0x66dbe  stloc.s  0xA
0x66dc0  br.s     loc_66DD4
0x66dc2  ldloca.s 0xA
0x66dc4  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::get_Current()
0x66dc9  stloc.s  0xB
0x66dcb  ldloc.1
0x66dcc  ldloc.s  0xB
0x66dce  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Remove(var<u1>)
0x66dd3  pop
0x66dd4  ldloca.s 0xA
0x66dd6  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::MoveNext()
0x66ddb  brtrue.s loc_66DC2
0x66ddd  leave.s  loc_66DED
0x66ddf  ldloca.s 0xA
0x66de1  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>
0x66de7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x66dec  endfinally
0x66ded  ldloc.1
0x66dee  ret
```
