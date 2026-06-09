# Microsoft.Crm.Service.ObjectModel.EntitltmentPluginHelper::GetValidEntitlement

- ea: `0x11890`
- end: `0x119d0`
- name: `Microsoft.Crm.Service.ObjectModel.EntitltmentPluginHelper::GetValidEntitlement`
- size: `320`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x10830`
- `0x10900`
- `0x10b10`
- `0x10bc0`
- `0x11f70`

## callees

- `0x11470`
- `0x11890`
- `0x11c70`

## string_xrefs

- `0x119a5`: `You can't create a case for this entitlement because the entitlement is not in active state.`

## pseudocode

```c

```

## disassembly

```asm
0x11890  ldarg.0
0x11891  castclass [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext
0x11896  stloc.0
0x11897  ldarg.0
0x11898  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_InputParameters()
0x1189d  ldstr    aTarget// "Target"
0x118a2  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x118a7  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity
0x118ac  stloc.1
0x118ad  ldloc.1
0x118ae  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x118b3  ldstr    aEntitlementid// "entitlementid"
0x118b8  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x118bd  brfalse.s loc_118D1
0x118bf  ldloc.1
0x118c0  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x118c5  ldstr    aEntitlementid// "entitlementid"
0x118ca  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x118cf  brtrue.s loc_118D6
0x118d1  ldarg.2
0x118d2  brtrue.s loc_118D6
0x118d4  ldnull
0x118d5  ret
0x118d6  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x118db  stloc.2
0x118dc  ldnull
0x118dd  stloc.3
0x118de  ldarg.2
0x118df  brfalse.s loc_118FC
0x118e1  ldloc.0
0x118e2  callvirt instance int32 [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_Stage()
0x118e7  ldc.i4.s 0x28
0x118e9  bne.un.s loc_118FC
0x118eb  ldarg.0
0x118ec  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityImageCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_PreEntityImages()
0x118f1  ldstr    aPrebusinessent// "PreBusinessEntity"
0x118f6  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Item(void)
0x118fb  stloc.3
0x118fc  ldloc.3
0x118fd  ldloc.1
0x118fe  ldloca.s 2
0x11900  ldloca.s 0
0x11902  ldarg.2
0x11903  call     void Microsoft.Crm.Service.ObjectModel.EntitltmentPluginHelper::GetValidEntitlementId(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity preEntity, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity pageEntity, [out] valuetype [mscorlib]System.Guid& EntitlementId, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext& pipelineContext, bool isUpdate)
0x11908  ldloc.2
0x11909  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1190e  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x11913  brfalse.s loc_11917
0x11915  ldnull
0x11916  ret
0x11917  ldloc.2
0x11918  ldstr    aEntitlement// "Entitlement"
0x1191d  ldnull
0x1191e  ldc.i4.8
0x1191f  newarr   [mscorlib]System.String
0x11924  dup
0x11925  ldc.i4.0
0x11926  ldstr    aStatecode// "statecode"
0x1192b  stelem.ref
0x1192c  dup
0x1192d  ldc.i4.1
0x1192e  ldstr    aRestrictcasecr// "restrictcasecreation"
0x11933  stelem.ref
0x11934  dup
0x11935  ldc.i4.2
0x11936  ldstr    aRemainingterms// "remainingterms"
0x1193b  stelem.ref
0x1193c  dup
0x1193d  ldc.i4.3
0x1193e  ldstr    aTotalterms// "totalterms"
0x11943  stelem.ref
0x11944  dup
0x11945  ldc.i4.4
0x11946  ldstr    aDecreaseremain// "decreaseremainingon"
0x1194b  stelem.ref
0x1194c  dup
0x1194d  ldc.i4.5
0x1194e  ldstr    aAllocationtype// "allocationtypecode"
0x11953  stelem.ref
0x11954  dup
0x11955  ldc.i4.6
0x11956  ldstr    aSlaid// "slaid"
0x1195b  stelem.ref
0x1195c  dup
0x1195d  ldc.i4.7
0x1195e  ldstr    aOwnerid// "ownerid"
0x11963  stelem.ref
0x11964  ldloc.0
0x11965  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PlatformContext()
0x1196a  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.Service.ObjectModel.CasePluginHelper::GetBusinessEntity(valuetype [mscorlib]System.Guid id, string entityName, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> conditionalAtttributes, string[] requiredFields, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x1196f  castclass [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Entitlement
0x11974  stloc.s  4
0x11976  ldloc.s  4
0x11978  brtrue.s loc_1197C
0x1197a  ldnull
0x1197b  ret
0x1197c  ldarg.2
0x1197d  brfalse.s loc_119B5
0x1197f  ldloc.1
0x11980  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x11985  ldstr    aEntitlementid// "entitlementid"
0x1198a  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x1198f  brfalse.s loc_119B5
0x11991  ldloc.s  4
0x11993  ldstr    aStatecode// "statecode"
0x11998  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1199d  unbox.any [mscorlib]System.Int32
0x119a2  ldc.i4.1
0x119a3  beq.s    loc_119B5
0x119a5  ldstr    aYouCanTCreateA// "You can't create a case for this entitl"...
0x119aa  ldc.i4   0x80060609
0x119af  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x119b4  throw
0x119b5  ldarg.1
0x119b6  brfalse.s loc_119CD
0x119b8  ldloc.s  4
0x119ba  ldstr    aRestrictcasecr// "restrictcasecreation"
0x119bf  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x119c4  unbox.any [mscorlib]System.Boolean
0x119c9  brtrue.s loc_119CD
0x119cb  ldnull
0x119cc  ret
0x119cd  ldloc.s  4
0x119cf  ret
```
