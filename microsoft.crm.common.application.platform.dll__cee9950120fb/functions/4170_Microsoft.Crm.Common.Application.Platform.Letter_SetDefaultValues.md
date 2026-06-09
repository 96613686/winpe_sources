# Microsoft.Crm.Common.Application.Platform.Letter::SetDefaultValues

- ea: `0x4170`
- end: `0x4259`
- name: `Microsoft.Crm.Common.Application.Platform.Letter::SetDefaultValues`
- size: `233`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x2850`
- `0x4170`

## pseudocode

```c

```

## disassembly

```asm
0x4170  ldarg.0
0x4171  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::SetDefaultValues()
0x4176  ldarg.0
0x4177  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Metadata()
0x417c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x4181  ldstr    aDirectioncode// "directioncode"
0x4186  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::get_Item(!!T0)
0x418b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_DefaultValueAsObject()
0x4190  unbox.any [mscorlib]System.Boolean
0x4195  brfalse.s loc_41F8
0x4197  ldarg.0
0x4198  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Metadata()
0x419d  ldstr    aFrom// "from"
0x41a2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x41a7  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_IsSecured()
0x41ac  brfalse.s loc_41EC
0x41ae  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x41b3  ldarg.0
0x41b4  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Metadata()
0x41b9  ldstr    aFrom// "from"
0x41be  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x41c3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0x41c8  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::HasAttributeReadPrivilege(valuetype [mscorlib]System.Guid)
0x41cd  brtrue.s loc_41EC
0x41cf  ldarg.0
0x41d0  ldarg.0
0x41d1  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Metadata()
0x41d6  ldstr    aFrom// "from"
0x41db  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x41e0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0x41e5  call     instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::HasSharedReadPrivilege(valuetype [mscorlib]System.Guid)
0x41ea  brfalse.s loc_4258
0x41ec  ldarg.0
0x41ed  ldstr    aFrom// "from"
0x41f2  callvirt instance void Microsoft.Crm.Common.Application.Platform.ActivityBase::PrePopulatePartyToCurrentUser(string participationTypeName)
0x41f7  ret
0x41f8  ldarg.0
0x41f9  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Metadata()
0x41fe  ldstr    aTo// "to"
0x4203  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x4208  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_IsSecured()
0x420d  brfalse.s loc_424D
0x420f  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x4214  ldarg.0
0x4215  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Metadata()
0x421a  ldstr    aTo// "to"
0x421f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x4224  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0x4229  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::HasAttributeReadPrivilege(valuetype [mscorlib]System.Guid)
0x422e  brtrue.s loc_424D
0x4230  ldarg.0
0x4231  ldarg.0
0x4232  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Metadata()
0x4237  ldstr    aTo// "to"
0x423c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x4241  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0x4246  call     instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::HasSharedReadPrivilege(valuetype [mscorlib]System.Guid)
0x424b  brfalse.s loc_4258
0x424d  ldarg.0
0x424e  ldstr    aTo// "to"
0x4253  callvirt instance void Microsoft.Crm.Common.Application.Platform.ActivityBase::PrePopulatePartyToCurrentUser(string participationTypeName)
0x4258  ret
```
