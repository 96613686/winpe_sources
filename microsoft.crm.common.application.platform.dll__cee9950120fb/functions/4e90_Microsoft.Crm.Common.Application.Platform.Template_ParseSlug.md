# Microsoft.Crm.Common.Application.Platform.Template::ParseSlug

- ea: `0x4e90`
- end: `0x4fa7`
- name: `Microsoft.Crm.Common.Application.Platform.Template::ParseSlug`
- size: `279`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4d60`

## callees

- `0x4e90`

## pseudocode

```c

```

## disassembly

```asm
0x4e90  ldarg.2
0x4e91  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x4e96  stind.ref
0x4e97  ldarg.1
0x4e98  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlDecode(string)
0x4e9d  ldc.i4.1
0x4e9e  newarr   [mscorlib]System.Char
0x4ea3  dup
0x4ea4  ldc.i4.0
0x4ea5  ldc.i4.s 0x3B
0x4ea7  stelem.i2
0x4ea8  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x4ead  stloc.0
0x4eae  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4eb3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x4eb8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x4ebd  stloc.2
0x4ebe  ldc.i4.0
0x4ebf  stloc.3
0x4ec0  br       loc_4F9C
0x4ec5  ldloc.3
0x4ec6  ldc.i4.0
0x4ec7  ble.s    loc_4EE0
0x4ec9  ldloc.3
0x4eca  ldloc.0
0x4ecb  ldlen
0x4ecc  conv.i4
0x4ecd  ldc.i4.1
0x4ece  sub
0x4ecf  bne.un.s loc_4EE0
0x4ed1  ldarg.2
0x4ed2  ldind.ref
0x4ed3  ldloc.0
0x4ed4  ldloc.3
0x4ed5  ldelem.ref
0x4ed6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x4edb  br       loc_4FA5
0x4ee0  ldloc.0
0x4ee1  ldloc.3
0x4ee2  ldelem.ref
0x4ee3  ldstr    asc_A2A4// ":"
0x4ee8  ldc.i4.4
0x4ee9  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x4eee  stloc.s  4
0x4ef0  ldsfld   string [mscorlib]System.String::Empty
0x4ef5  stloc.s  5
0x4ef7  ldsfld   string [mscorlib]System.String::Empty
0x4efc  stloc.s  6
0x4efe  ldloc.s  4
0x4f00  ldc.i4.m1
0x4f01  beq.s    loc_4F30
0x4f03  ldloc.0
0x4f04  ldloc.3
0x4f05  ldelem.ref
0x4f06  ldc.i4.0
0x4f07  ldloc.s  4
0x4f09  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x4f0e  stloc.s  5
0x4f10  ldloc.s  5
0x4f12  callvirt instance string [mscorlib]System.String::Trim()
0x4f17  stloc.s  5
0x4f19  ldloc.0
0x4f1a  ldloc.3
0x4f1b  ldelem.ref
0x4f1c  ldloc.s  4
0x4f1e  ldc.i4.1
0x4f1f  add
0x4f20  callvirt instance string [mscorlib]System.String::Substring(int32)
0x4f25  stloc.s  6
0x4f27  ldloc.s  6
0x4f29  callvirt instance string [mscorlib]System.String::Trim()
0x4f2e  stloc.s  6
0x4f30  ldloc.s  5
0x4f32  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4f37  brtrue.s loc_4F42
0x4f39  ldloc.s  6
0x4f3b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4f40  brfalse.s loc_4F44
0x4f42  ldc.i4.0
0x4f43  ret
0x4f44  ldloc.2
0x4f45  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4f4a  ldloc.s  5
0x4f4c  ldc.i4.1
0x4f4d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x4f52  stloc.1
0x4f53  ldloc.1
0x4f54  brtrue.s loc_4F58
0x4f56  ldc.i4.0
0x4f57  ret
0x4f58  ldloc.s  6
0x4f5a  ldc.i4.s 0x2F
0x4f5c  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x4f61  stloc.s  7
0x4f63  ldloc.s  7
0x4f65  ldc.i4.m1
0x4f66  beq.s    loc_4F7A
0x4f68  ldloc.1
0x4f69  ldloc.s  6
0x4f6b  ldc.i4.0
0x4f6c  ldloc.s  7
0x4f6e  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x4f73  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string)
0x4f78  br.s     loc_4F82
0x4f7a  ldloc.1
0x4f7b  ldloc.s  6
0x4f7d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string)
0x4f82  brtrue.s loc_4F86
0x4f84  ldc.i4.0
0x4f85  ret
0x4f86  ldarg.2
0x4f87  ldind.ref
0x4f88  ldloc.s  5
0x4f8a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x4f8f  ldarg.2
0x4f90  ldind.ref
0x4f91  ldloc.s  6
0x4f93  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x4f98  ldloc.3
0x4f99  ldc.i4.1
0x4f9a  add
0x4f9b  stloc.3
0x4f9c  ldloc.3
0x4f9d  ldloc.0
0x4f9e  ldlen
0x4f9f  conv.i4
0x4fa0  blt      loc_4EC5
0x4fa5  ldc.i4.1
0x4fa6  ret
```
