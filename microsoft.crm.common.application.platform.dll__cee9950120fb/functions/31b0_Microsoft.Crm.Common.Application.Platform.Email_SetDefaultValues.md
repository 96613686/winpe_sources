# Microsoft.Crm.Common.Application.Platform.Email::SetDefaultValues

- ea: `0x31b0`
- end: `0x32cd`
- name: `Microsoft.Crm.Common.Application.Platform.Email::SetDefaultValues`
- size: `285`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x2850`
- `0x31b0`

## pseudocode

```c

```

## disassembly

```asm
0x31b0  ldarg.0
0x31b1  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::SetDefaultValues()
0x31b6  ldarg.0
0x31b7  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Metadata()
0x31bc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x31c1  ldstr    aDirectioncode// "directioncode"
0x31c6  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::get_Item(!!T0)
0x31cb  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_DefaultValueAsObject()
0x31d0  unbox.any [mscorlib]System.Boolean
0x31d5  brfalse.s loc_3239
0x31d7  ldarg.0
0x31d8  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Metadata()
0x31dd  ldstr    aFrom// "from"
0x31e2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x31e7  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_IsSecured()
0x31ec  brfalse.s loc_322C
0x31ee  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x31f3  ldarg.0
0x31f4  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Metadata()
0x31f9  ldstr    aFrom// "from"
0x31fe  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x3203  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0x3208  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::HasAttributeReadPrivilege(valuetype [mscorlib]System.Guid)
0x320d  brtrue.s loc_322C
0x320f  ldarg.0
0x3210  ldarg.0
0x3211  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Metadata()
0x3216  ldstr    aFrom// "from"
0x321b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x3220  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0x3225  call     instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::HasSharedReadPrivilege(valuetype [mscorlib]System.Guid)
0x322a  brfalse.s loc_3299
0x322c  ldarg.0
0x322d  ldstr    aFrom// "from"
0x3232  callvirt instance void Microsoft.Crm.Common.Application.Platform.ActivityBase::PrePopulatePartyToCurrentUser(string participationTypeName)
0x3237  br.s     loc_3299
0x3239  ldarg.0
0x323a  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Metadata()
0x323f  ldstr    aTo// "to"
0x3244  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x3249  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_IsSecured()
0x324e  brfalse.s loc_328E
0x3250  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x3255  ldarg.0
0x3256  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Metadata()
0x325b  ldstr    aTo// "to"
0x3260  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x3265  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0x326a  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::HasAttributeReadPrivilege(valuetype [mscorlib]System.Guid)
0x326f  brtrue.s loc_328E
0x3271  ldarg.0
0x3272  ldarg.0
0x3273  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Metadata()
0x3278  ldstr    aTo// "to"
0x327d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x3282  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0x3287  call     instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::HasSharedReadPrivilege(valuetype [mscorlib]System.Guid)
0x328c  brfalse.s loc_3299
0x328e  ldarg.0
0x328f  ldstr    aTo// "to"
0x3294  callvirt instance void Microsoft.Crm.Common.Application.Platform.ActivityBase::PrePopulatePartyToCurrentUser(string participationTypeName)
0x3299  ldarg.0
0x329a  call     instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_IsNew()
0x329f  brfalse.s loc_32CC
0x32a1  ldarg.0
0x32a2  ldstr    aStatuscode// "statuscode"
0x32a7  ldc.i4.1
0x32a8  box      [mscorlib]System.Int32
0x32ad  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x32b2  ldarg.0
0x32b3  ldstr    aStatecode// "statecode"
0x32b8  ldc.i4.0
0x32b9  stloc.0
0x32ba  ldloca.s 0
0x32bc  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.EmailState
0x32c2  callvirt instance string [mscorlib]System.Object::ToString()
0x32c7  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x32cc  ret
```
