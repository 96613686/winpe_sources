# Microsoft.Crm.ObjectModel.ProcessServiceInternalHandler`1::CompletePublishing

- ea: `0x1dc2a0`
- end: `0x1dc718`
- name: `Microsoft.Crm.ObjectModel.ProcessServiceInternalHandler`1::CompletePublishing`
- size: `1144`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1dc2a0`

## string_xrefs

- `0x1dc3f8`: `asyncautodelete`
- `0x1dc3fe`: `asyncautodelete`
- `0x1dc361`: `triggeroncreate`
- `0x1dc367`: `triggeroncreate`
- `0x1dc378`: `triggerondelete`
- `0x1dc37e`: `triggerondelete`
- `0x1dc38f`: `triggeronupdateattributelist`
- `0x1dc395`: `triggeronupdateattributelist`
- `0x1dc499`: `createstage`
- `0x1dc49f`: `createstage`
- `0x1dc4b0`: `updatestage`
- `0x1dc4b6`: `updatestage`
- `0x1dc4c7`: `deletestage`
- `0x1dc4cd`: `deletestage`

## pseudocode

```c

```

## disassembly

```asm
0x1dc2a0  ldarg.1
0x1dc2a1  ldstr    aWorkflowid// "workflowid"
0x1dc2a6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1dc2ab  unbox.any [mscorlib]System.Guid
0x1dc2b0  stloc.0
0x1dc2b1  ldarg.1
0x1dc2b2  ldstr    aType// "type"
0x1dc2b7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1dc2bc  unbox.any [mscorlib]System.Int32
0x1dc2c1  ldc.i4.3
0x1dc2c2  ceq
0x1dc2c4  stloc.1
0x1dc2c5  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x1dc2ca  stloc.2
0x1dc2cb  ldloc.1
0x1dc2cc  brtrue   loc_1DC642
0x1dc2d1  ldarg.s  4
0x1dc2d3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1dc2d8  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.WorkflowEntity::.ctor(valuetype [mscorlib]System.Guid)
0x1dc2dd  stloc.s  5
0x1dc2df  ldloc.s  5
0x1dc2e1  ldstr    aWorkflowid// "workflowid"
0x1dc2e6  ldloc.2
0x1dc2e7  box      [mscorlib]System.Guid
0x1dc2ec  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1dc2f1  ldloc.s  5
0x1dc2f3  ldstr    aStatecode// "statecode"
0x1dc2f8  ldc.i4.1
0x1dc2f9  box      [mscorlib]System.Int32
0x1dc2fe  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1dc303  ldloc.s  5
0x1dc305  ldstr    aName// "name"
0x1dc30a  ldarg.1
0x1dc30b  ldstr    aName// "name"
0x1dc310  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1dc315  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1dc31a  ldloc.s  5
0x1dc31c  ldstr    aDescription// "description"
0x1dc321  ldarg.1
0x1dc322  ldstr    aDescription// "description"
0x1dc327  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1dc32c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1dc331  ldloc.s  5
0x1dc333  ldstr    aIscrmuiworkflo// "iscrmuiworkflow"
0x1dc338  ldarg.1
0x1dc339  ldstr    aIscrmuiworkflo// "iscrmuiworkflow"
0x1dc33e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1dc343  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1dc348  ldloc.s  5
0x1dc34a  ldstr    aXaml// "xaml"
0x1dc34f  ldarg.1
0x1dc350  ldstr    aXaml// "xaml"
0x1dc355  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1dc35a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1dc35f  ldloc.s  5
0x1dc361  ldstr    aTriggeroncreat// "triggeroncreate"
0x1dc366  ldarg.1
0x1dc367  ldstr    aTriggeroncreat// "triggeroncreate"
0x1dc36c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1dc371  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1dc376  ldloc.s  5
0x1dc378  ldstr    aTriggerondelet// "triggerondelete"
0x1dc37d  ldarg.1
0x1dc37e  ldstr    aTriggerondelet// "triggerondelete"
0x1dc383  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1dc388  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1dc38d  ldloc.s  5
0x1dc38f  ldstr    aTriggeronupdat// "triggeronupdateattributelist"
0x1dc394  ldarg.1
0x1dc395  ldstr    aTriggeronupdat// "triggeronupdateattributelist"
0x1dc39a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1dc39f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1dc3a4  ldloc.s  5
0x1dc3a6  ldstr    aParentworkflow// "parentworkflowid"
0x1dc3ab  ldarg.1
0x1dc3ac  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PrimaryKey()
0x1dc3b1  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1dc3b6  ldloc.s  5
0x1dc3b8  ldstr    aType// "type"
0x1dc3bd  ldc.i4.2
0x1dc3be  box      [mscorlib]System.Int32
0x1dc3c3  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1dc3c8  ldloc.s  5
0x1dc3ca  ldstr    aPrimaryentity// "primaryentity"
0x1dc3cf  ldarg.1
0x1dc3d0  ldstr    aPrimaryentity// "primaryentity"
0x1dc3d5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1dc3da  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1dc3df  ldloc.s  5
0x1dc3e1  ldstr    aScope// "scope"
0x1dc3e6  ldarg.1
0x1dc3e7  ldstr    aScope// "scope"
0x1dc3ec  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1dc3f1  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1dc3f6  ldloc.s  5
0x1dc3f8  ldstr    aAsyncautodelet// "asyncautodelete"
0x1dc3fd  ldarg.1
0x1dc3fe  ldstr    aAsyncautodelet// "asyncautodelete"
0x1dc403  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1dc408  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1dc40d  ldloc.s  5
0x1dc40f  ldstr    aSyncworkflowlo// "syncworkflowlogonfailure"
0x1dc414  ldarg.1
0x1dc415  ldstr    aSyncworkflowlo// "syncworkflowlogonfailure"
0x1dc41a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1dc41f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1dc424  ldloc.s  5
0x1dc426  ldstr    aCategory// "category"
0x1dc42b  ldarg.1
0x1dc42c  ldstr    aCategory// "category"
0x1dc431  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1dc436  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1dc43b  ldloc.s  5
0x1dc43d  ldstr    aInputparameter_0// "inputparameters"
0x1dc442  ldarg.1
0x1dc443  ldstr    aInputparameter_0// "inputparameters"
0x1dc448  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1dc44d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1dc452  ldloc.s  5
0x1dc454  ldstr    aLanguagecode// "languagecode"
0x1dc459  ldarg.1
0x1dc45a  ldstr    aLanguagecode// "languagecode"
0x1dc45f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1dc464  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1dc469  ldloc.s  5
0x1dc46b  ldstr    aOndemand// "ondemand"
0x1dc470  ldarg.1
0x1dc471  ldstr    aOndemand// "ondemand"
0x1dc476  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1dc47b  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1dc480  ldloc.s  5
0x1dc482  ldstr    aSubprocess// "subprocess"
0x1dc487  ldarg.1
0x1dc488  ldstr    aSubprocess// "subprocess"
0x1dc48d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1dc492  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1dc497  ldloc.s  5
0x1dc499  ldstr    aCreatestage// "createstage"
0x1dc49e  ldarg.1
0x1dc49f  ldstr    aCreatestage// "createstage"
0x1dc4a4  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1dc4a9  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1dc4ae  ldloc.s  5
0x1dc4b0  ldstr    aUpdatestage// "updatestage"
0x1dc4b5  ldarg.1
0x1dc4b6  ldstr    aUpdatestage// "updatestage"
0x1dc4bb  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1dc4c0  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1dc4c5  ldloc.s  5
0x1dc4c7  ldstr    aDeletestage// "deletestage"
0x1dc4cc  ldarg.1
0x1dc4cd  ldstr    aDeletestage// "deletestage"
0x1dc4d2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1dc4d7  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1dc4dc  ldloc.s  5
0x1dc4de  ldstr    aRank// "rank"
0x1dc4e3  ldarg.1
0x1dc4e4  ldstr    aRank// "rank"
0x1dc4e9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1dc4ee  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1dc4f3  ldloc.s  5
0x1dc4f5  ldstr    aRunas// "runas"
0x1dc4fa  ldarg.1
0x1dc4fb  ldstr    aRunas// "runas"
0x1dc500  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1dc505  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1dc50a  ldloc.s  5
0x1dc50c  ldstr    aSdkmessageid// "sdkmessageid"
0x1dc511  ldarg.1
0x1dc512  ldstr    aSdkmessageid// "sdkmessageid"
0x1dc517  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1dc51c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1dc521  ldloc.s  5
0x1dc523  ldstr    aUniquename// "uniquename"
0x1dc528  ldarg.1
0x1dc529  ldstr    aUniquename// "uniquename"
0x1dc52e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1dc533  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1dc538  ldloc.s  5
0x1dc53a  ldstr    aIstransacted// "istransacted"
0x1dc53f  ldarg.1
0x1dc540  ldstr    aIstransacted// "istransacted"
0x1dc545  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1dc54a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1dc54f  ldloc.s  5
0x1dc551  ldstr    aMode// "mode"
0x1dc556  ldarg.1
0x1dc557  ldstr    aMode// "mode"
0x1dc55c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1dc561  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1dc566  ldloc.s  5
0x1dc568  ldstr    aRendererobject// "rendererobjecttypecode"
0x1dc56d  ldarg.1
0x1dc56e  ldstr    aRendererobject// "rendererobjecttypecode"
0x1dc573  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1dc578  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1dc57d  ldarg.s  4
0x1dc57f  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.AutoBasicSolutionContextModifier::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1dc584  stloc.s  6
0x1dc586  ldarg.0
0x1dc587  ldloc.s  5
0x1dc589  ldarg.s  4
0x1dc58b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker class Microsoft.Crm.ObjectModel.ProcessServiceInternalHandler`1<var<u1>>::PublishCreateInternal(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1dc590  pop
0x1dc591  leave.s  loc_1DC59F
0x1dc593  ldloc.s  6
0x1dc595  brfalse.s loc_1DC59E
0x1dc597  ldloc.s  6
0x1dc599  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1dc59e  endfinally
0x1dc59f  ldarg.2
0x1dc5a0  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.WorkflowDependency>::GetEnumerator()
0x1dc5a5  stloc.s  7
0x1dc5a7  br.s     loc_1DC609
0x1dc5a9  ldloc.s  7
0x1dc5ab  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.WorkflowDependency>::get_Current()
0x1dc5b0  stloc.s  8
0x1dc5b2  ldloc.s  8
0x1dc5b4  ldstr    aWorkflowdepend_1// "workflowdependencyid"
0x1dc5b9  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::ClearAttribute(string)
0x1dc5be  ldloc.s  8
0x1dc5c0  ldstr    aWorkflowdepend_2// "workflowdependencyidunique"
0x1dc5c5  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::ClearAttribute(string)
0x1dc5ca  ldloc.s  8
0x1dc5cc  ldstr    aWorkflowid// "workflowid"
0x1dc5d1  ldloc.2
0x1dc5d2  box      [mscorlib]System.Guid
0x1dc5d7  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1dc5dc  ldarg.s  4
0x1dc5de  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1dc5e3  stloc.s  9
0x1dc5e5  ldarg.0
0x1dc5e6  call     instance class Microsoft.Crm.ObjectModel.IPublishHelper`1<var<u1>> class Microsoft.Crm.ObjectModel.ProcessServiceInternalHandler`1<var<u1>>::get_Helper()
0x1dc5eb  callvirt instance class Microsoft.Crm.ObjectModel.WorkflowDependencyServiceInternal`1<var<u1>> class Microsoft.Crm.ObjectModel.IPublishHelper`1<var<u1>>::get_GetWorkflowDependencyService()
0x1dc5f0  ldloc.s  8
0x1dc5f2  ldarg.s  4
0x1dc5f4  ldc.i4.1
0x1dc5f5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker class Microsoft.Crm.ObjectModel.WorkflowDependencyServiceInternal`1<var<u1>>::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, bool)
0x1dc5fa  pop
0x1dc5fb  leave.s  loc_1DC609
0x1dc5fd  ldloc.s  9
0x1dc5ff  brfalse.s loc_1DC608
0x1dc601  ldloc.s  9
0x1dc603  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1dc608  endfinally
0x1dc609  ldloc.s  7
0x1dc60b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1dc610  brtrue.s loc_1DC5A9
0x1dc612  leave.s  loc_1DC620
0x1dc614  ldloc.s  7
0x1dc616  brfalse.s loc_1DC61F
0x1dc618  ldloc.s  7
0x1dc61a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1dc61f  endfinally
0x1dc620  ldarg.0
0x1dc621  ldarg.0
0x1dc622  call     instance class Microsoft.Crm.ObjectModel.IPublishHelper`1<var<u1>> class Microsoft.Crm.ObjectModel.ProcessServiceInternalHandler`1<var<u1>>::get_Helper()
0x1dc627  newobj   instance void class Microsoft.Crm.ObjectModel.ProcessServiceInternalPublisher`1<var<u1>>::.ctor(class Microsoft.Crm.ObjectModel.ProcessServiceInternalHandler`1<var<u1>>, !!T0)
0x1dc62c  dup
0x1dc62d  ldarg.1
0x1dc62e  ldloc.s  5
0x1dc630  ldarg.2
0x1dc631  ldarg.3
0x1dc632  ldarg.s  4
0x1dc634  callvirt instance void class Microsoft.Crm.ObjectModel.ProcessServiceInternalPublisher`1<var<u1>>::CreateSdkSteps(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.WorkflowDependency>, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1dc639  ldloc.2
0x1dc63a  ldloc.0
0x1dc63b  ldarg.s  4
0x1dc63d  callvirt instance void class Microsoft.Crm.ObjectModel.ProcessServiceInternalPublisher`1<var<u1>>::CopyAttachment(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1dc642  ldarg.s  4
0x1dc644  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1dc649  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.WorkflowEntity::.ctor(valuetype [mscorlib]System.Guid)
0x1dc64e  stloc.3
0x1dc64f  ldloc.3
0x1dc650  ldarg.1
0x1dc651  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0x1dc656  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x1dc65b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PlatformName()
0x1dc660  ldloc.0
0x1dc661  box      [mscorlib]System.Guid
0x1dc666  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1dc66b  ldloc.3
0x1dc66c  ldstr    aStatecode// "statecode"
0x1dc671  ldc.i4.1
0x1dc672  box      [mscorlib]System.Int32
0x1dc677  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1dc67c  ldarg.1
0x1dc67d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0x1dc682  ldstr    aStatecode// "statecode"
0x1dc687  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x1dc68c  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StateAttributeMetadata
0x1dc691  stloc.s  4
0x1dc693  ldloc.3
0x1dc694  ldstr    aStatuscode// "statuscode"
0x1dc699  ldloc.s  4
0x1dc69b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IStateOptionsByValueCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StateAttributeMetadata::get_StateOptions()
0x1dc6a0  ldc.i4.1
0x1dc6a1  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEnumOptionsByValueCollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StateOption>::get_Item(!!T0)
0x1dc6a6  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StateOption::get_DefaultStatus()
0x1dc6ab  box      [mscorlib]System.Int32
  ... truncated ...
```
