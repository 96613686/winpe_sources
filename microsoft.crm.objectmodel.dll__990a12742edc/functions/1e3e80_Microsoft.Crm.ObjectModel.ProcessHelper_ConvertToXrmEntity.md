# Microsoft.Crm.ObjectModel.ProcessHelper::ConvertToXrmEntity

- ea: `0x1e3e80`
- end: `0x1e424b`
- name: `Microsoft.Crm.ObjectModel.ProcessHelper::ConvertToXrmEntity`
- size: `971`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1e1c50`
- `0x1e4250`
- `0x21f970`

## callees

- `0x1e3e80`

## string_xrefs

- `0x1e3f56`: `asyncautodelete`
- `0x1e3f5c`: `asyncautodelete`
- `0x1e3f69`: `asyncautodelete`
- `0x1e3f00`: `triggeroncreate`
- `0x1e3f06`: `triggeroncreate`
- `0x1e3f16`: `triggerondelete`
- `0x1e3f1c`: `triggerondelete`
- `0x1e3f2c`: `triggeronupdateattributelist`
- `0x1e3f32`: `triggeronupdateattributelist`
- `0x1e3f3f`: `triggeronupdateattributelist`
- `0x1e416b`: `createstage`
- `0x1e4178`: `createstage`
- `0x1e417e`: `createstage`
- `0x1e4198`: `updatestage`
- `0x1e41a5`: `updatestage`
- `0x1e41ab`: `updatestage`
- `0x1e41c5`: `deletestage`
- `0x1e41d2`: `deletestage`
- `0x1e41d8`: `deletestage`

## pseudocode

```c

```

## disassembly

```asm
0x1e3e80  ldarg.0
0x1e3e81  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0x1e3e86  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x1e3e8b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x1e3e90  stloc.0
0x1e3e91  ldloc.0
0x1e3e92  ldstr    aXaml// "xaml"
0x1e3e97  ldarg.0
0x1e3e98  ldstr    aXaml// "xaml"
0x1e3e9d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1e3ea2  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x1e3ea7  ldloc.0
0x1e3ea8  ldstr    aWorkflowid// "workflowid"
0x1e3ead  ldarg.0
0x1e3eae  ldstr    aWorkflowid// "workflowid"
0x1e3eb3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1e3eb8  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x1e3ebd  ldloc.0
0x1e3ebe  ldstr    aName// "name"
0x1e3ec3  ldarg.0
0x1e3ec4  ldstr    aName// "name"
0x1e3ec9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1e3ece  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x1e3ed3  ldloc.0
0x1e3ed4  ldstr    aOndemand// "ondemand"
0x1e3ed9  ldarg.0
0x1e3eda  ldstr    aOndemand// "ondemand"
0x1e3edf  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1e3ee4  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x1e3ee9  ldloc.0
0x1e3eea  ldstr    aSubprocess// "subprocess"
0x1e3eef  ldarg.0
0x1e3ef0  ldstr    aSubprocess// "subprocess"
0x1e3ef5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1e3efa  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x1e3eff  ldloc.0
0x1e3f00  ldstr    aTriggeroncreat// "triggeroncreate"
0x1e3f05  ldarg.0
0x1e3f06  ldstr    aTriggeroncreat// "triggeroncreate"
0x1e3f0b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1e3f10  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x1e3f15  ldloc.0
0x1e3f16  ldstr    aTriggerondelet// "triggerondelete"
0x1e3f1b  ldarg.0
0x1e3f1c  ldstr    aTriggerondelet// "triggerondelete"
0x1e3f21  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1e3f26  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x1e3f2b  ldloc.0
0x1e3f2c  ldstr    aTriggeronupdat// "triggeronupdateattributelist"
0x1e3f31  ldarg.0
0x1e3f32  ldstr    aTriggeronupdat// "triggeronupdateattributelist"
0x1e3f37  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1e3f3c  brfalse.s loc_1E3F4B
0x1e3f3e  ldarg.0
0x1e3f3f  ldstr    aTriggeronupdat// "triggeronupdateattributelist"
0x1e3f44  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1e3f49  br.s     loc_1E3F50
0x1e3f4b  ldsfld   string [mscorlib]System.String::Empty
0x1e3f50  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x1e3f55  ldloc.0
0x1e3f56  ldstr    aAsyncautodelet// "asyncautodelete"
0x1e3f5b  ldarg.0
0x1e3f5c  ldstr    aAsyncautodelet// "asyncautodelete"
0x1e3f61  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1e3f66  brfalse.s loc_1E3F75
0x1e3f68  ldarg.0
0x1e3f69  ldstr    aAsyncautodelet// "asyncautodelete"
0x1e3f6e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1e3f73  br.s     loc_1E3F7B
0x1e3f75  ldc.i4.0
0x1e3f76  box      [mscorlib]System.Boolean
0x1e3f7b  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x1e3f80  ldloc.0
0x1e3f81  ldstr    aSyncworkflowlo// "syncworkflowlogonfailure"
0x1e3f86  ldarg.0
0x1e3f87  ldstr    aSyncworkflowlo// "syncworkflowlogonfailure"
0x1e3f8c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1e3f91  brfalse.s loc_1E3FA0
0x1e3f93  ldarg.0
0x1e3f94  ldstr    aSyncworkflowlo// "syncworkflowlogonfailure"
0x1e3f99  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1e3f9e  br.s     loc_1E3FA6
0x1e3fa0  ldc.i4.0
0x1e3fa1  box      [mscorlib]System.Boolean
0x1e3fa6  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x1e3fab  ldloc.0
0x1e3fac  ldstr    aLanguagecode// "languagecode"
0x1e3fb1  ldarg.0
0x1e3fb2  ldstr    aLanguagecode// "languagecode"
0x1e3fb7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1e3fbc  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x1e3fc1  ldloc.0
0x1e3fc2  ldstr    aInputparameter_0// "inputparameters"
0x1e3fc7  ldarg.0
0x1e3fc8  ldstr    aInputparameter_0// "inputparameters"
0x1e3fcd  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1e3fd2  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x1e3fd7  ldloc.0
0x1e3fd8  ldstr    aIstransacted// "istransacted"
0x1e3fdd  ldarg.0
0x1e3fde  ldstr    aIstransacted// "istransacted"
0x1e3fe3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1e3fe8  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x1e3fed  ldarg.0
0x1e3fee  ldstr    aCategory// "category"
0x1e3ff3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1e3ff8  brfalse.s loc_1E401C
0x1e3ffa  ldloc.0
0x1e3ffb  ldstr    aCategory// "category"
0x1e4000  ldarg.0
0x1e4001  ldstr    aCategory// "category"
0x1e4006  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1e400b  unbox.any [mscorlib]System.Int32
0x1e4010  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x1e4015  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x1e401a  br.s     loc_1E402D
0x1e401c  ldloc.0
0x1e401d  ldstr    aCategory// "category"
0x1e4022  ldc.i4.0
0x1e4023  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x1e4028  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x1e402d  ldarg.0
0x1e402e  ldstr    aBusinessproces_1// "businessprocesstype"
0x1e4033  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x1e4038  brtrue.s loc_1E405A
0x1e403a  ldloc.0
0x1e403b  ldstr    aBusinessproces_1// "businessprocesstype"
0x1e4040  ldarg.0
0x1e4041  ldstr    aBusinessproces_1// "businessprocesstype"
0x1e4046  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1e404b  unbox.any [mscorlib]System.Int32
0x1e4050  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x1e4055  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x1e405a  ldarg.0
0x1e405b  ldstr    aMode// "mode"
0x1e4060  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1e4065  brfalse.s loc_1E4089
0x1e4067  ldloc.0
0x1e4068  ldstr    aMode// "mode"
0x1e406d  ldarg.0
0x1e406e  ldstr    aMode// "mode"
0x1e4073  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1e4078  unbox.any [mscorlib]System.Int32
0x1e407d  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x1e4082  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x1e4087  br.s     loc_1E409A
0x1e4089  ldloc.0
0x1e408a  ldstr    aMode// "mode"
0x1e408f  ldc.i4.0
0x1e4090  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x1e4095  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x1e409a  ldarg.0
0x1e409b  ldstr    aWorkflowid// "workflowid"
0x1e40a0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1e40a5  brfalse.s loc_1E40BD
0x1e40a7  ldloc.0
0x1e40a8  ldarg.0
0x1e40a9  ldstr    aWorkflowid// "workflowid"
0x1e40ae  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1e40b3  unbox.any [mscorlib]System.Guid
0x1e40b8  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Id(valuetype [mscorlib]System.Guid)
0x1e40bd  ldarg.0
0x1e40be  ldstr    aType// "type"
0x1e40c3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1e40c8  brfalse.s loc_1E40EA
0x1e40ca  ldloc.0
0x1e40cb  ldstr    aType// "type"
0x1e40d0  ldarg.0
0x1e40d1  ldstr    aType// "type"
0x1e40d6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1e40db  unbox.any [mscorlib]System.Int32
0x1e40e0  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x1e40e5  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x1e40ea  ldarg.0
0x1e40eb  ldstr    aScope// "scope"
0x1e40f0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1e40f5  brfalse.s loc_1E4117
0x1e40f7  ldloc.0
0x1e40f8  ldstr    aScope// "scope"
0x1e40fd  ldarg.0
0x1e40fe  ldstr    aScope// "scope"
0x1e4103  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1e4108  unbox.any [mscorlib]System.Int32
0x1e410d  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x1e4112  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x1e4117  ldarg.0
0x1e4118  ldstr    aPrimaryentity// "primaryentity"
0x1e411d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1e4122  brfalse.s loc_1E416A
0x1e4124  ldarg.0
0x1e4125  ldstr    aPrimaryentity// "primaryentity"
0x1e412a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1e412f  unbox.any [mscorlib]System.Int32
0x1e4134  brfalse.s loc_1E416A
0x1e4136  ldarg.2
0x1e4137  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1e413c  brfalse.s loc_1E415C
0x1e413e  ldarg.1
0x1e413f  ldarg.0
0x1e4140  ldstr    aPrimaryentity// "primaryentity"
0x1e4145  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1e414a  unbox.any [mscorlib]System.Int32
0x1e414f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x1e4154  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x1e4159  stloc.1
0x1e415a  br.s     loc_1E415E
0x1e415c  ldarg.2
0x1e415d  stloc.1
0x1e415e  ldloc.0
0x1e415f  ldstr    aPrimaryentity// "primaryentity"
0x1e4164  ldloc.1
0x1e4165  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x1e416a  ldarg.0
0x1e416b  ldstr    aCreatestage// "createstage"
0x1e4170  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1e4175  brfalse.s loc_1E4197
0x1e4177  ldloc.0
0x1e4178  ldstr    aCreatestage// "createstage"
0x1e417d  ldarg.0
0x1e417e  ldstr    aCreatestage// "createstage"
0x1e4183  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1e4188  unbox.any [mscorlib]System.Int32
0x1e418d  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x1e4192  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x1e4197  ldarg.0
0x1e4198  ldstr    aUpdatestage// "updatestage"
0x1e419d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1e41a2  brfalse.s loc_1E41C4
0x1e41a4  ldloc.0
0x1e41a5  ldstr    aUpdatestage// "updatestage"
0x1e41aa  ldarg.0
0x1e41ab  ldstr    aUpdatestage// "updatestage"
0x1e41b0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1e41b5  unbox.any [mscorlib]System.Int32
0x1e41ba  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x1e41bf  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x1e41c4  ldarg.0
0x1e41c5  ldstr    aDeletestage// "deletestage"
0x1e41ca  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1e41cf  brfalse.s loc_1E41F1
0x1e41d1  ldloc.0
0x1e41d2  ldstr    aDeletestage// "deletestage"
0x1e41d7  ldarg.0
0x1e41d8  ldstr    aDeletestage// "deletestage"
0x1e41dd  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1e41e2  unbox.any [mscorlib]System.Int32
0x1e41e7  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x1e41ec  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x1e41f1  ldarg.0
0x1e41f2  ldstr    aDescription// "description"
0x1e41f7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1e41fc  brfalse.s loc_1E4226
0x1e41fe  ldarg.0
0x1e41ff  ldstr    aDescription// "description"
0x1e4204  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1e4209  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x1e420e  beq.s    loc_1E4226
0x1e4210  ldloc.0
0x1e4211  ldstr    aDescription// "description"
0x1e4216  ldarg.0
0x1e4217  ldstr    aDescription// "description"
0x1e421c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1e4221  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x1e4226  ldarg.0
0x1e4227  ldstr    aFormid// "formid"
0x1e422c  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x1e4231  brtrue.s loc_1E4249
0x1e4233  ldloc.0
0x1e4234  ldstr    aFormid// "formid"
0x1e4239  ldarg.0
0x1e423a  ldstr    aFormid// "formid"
0x1e423f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1e4244  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x1e4249  ldloc.0
0x1e424a  ret
```
