# Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjector::ImportRegularBpf

- ea: `0x11500`
- end: `0x115db`
- name: `Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjector::ImportRegularBpf`
- size: `219`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x11380`

## callees

- `0x11500`
- `0x115e0`
- `0x11640`
- `0x126a0`
- `0x126f0`
- `0x127b0`
- `0x12840`
- `0x128a0`

## string_xrefs

- `0x11509`: `\n		<attribute PhysicalName="bpf_{ON_ENTITY_LOGICAL_NAME}id">\n		  <Type>lookup</Type>\n		  <Name>bpf_{ON_ENTITY_PHYSICAL_NAME}id</Name>\n		  <LogicalName>bpf_{ON_ENTITY_LOGICAL_NAME}id</LogicalName>\n		  <RequiredLevel>none</RequiredLevel>\n		  <DisplayMask>ValidForAdvancedFind|ValidForForm|ValidForGrid</DisplayMask>\n		  <ValidForUpdateApi>1</ValidForUpdateApi>\n		  <ValidForReadApi>1</ValidForReadApi>\n		  <ValidForCreateApi>1</ValidForCreateApi>\n		  <IsCustomField>{IS_CUSTOM_FIELD`
- `0x1151a`: `<RootComponent type="1" schemaName="{WORKFLOW_UNIQUENAME_PLACEHOLDER}" behavior="0" />`
- `0x115a2`: `\n<EntityRelationship Name="bpf_{ON_ENTITY_LOGICAL_NAME}_{WORKFLOW_UNIQUENAME_PLACEHOLDER}">\n  <EntityRelationshipType>OneToMany</EntityRelationshipType>\n  <IsCustomizable>1</IsCustomizable>\n  <IntroducedVersion>1.0</IntroducedVersion>\n  <IsHierarchical>0</IsHierarchical>\n  <ReferencingEntityName>{WORKFLOW_UNIQUENAME_PLACEHOLDER}</ReferencingEntityName>\n  <ReferencedEntityName>{ON_ENTITY_PHYSICAL_NAME}</ReferencedEntityName>\n  <CascadeAssign>NoCascade</CascadeAssign>\n  <CascadeD`
- `0x11504`: `\n<Entity>\n  <Name LocalizedName="{ENTITYNAME_PLACEHOLDER}" OriginalName="{ENTITYNAME_PLACEHOLDER}">{WORKFLOW_UNIQUENAME_PLACEHOLDER}</Name>\n  <ObjectTypeCode>{TYPE_CODE}</ObjectTypeCode>\n  <EntityInfo>\n	<entity Name="{WORKFLOW_UNIQUENAME_PLACEHOLDER}">\n	  <LocalizedNames>\n		<LocalizedName description="{ENTITYNAME_PLACEHOLDER}" languagecode="{LANG_CODE}" />\n	  </LocalizedNames>\n	  <LocalizedCollectionNames>\n		<LocalizedCollectionName description="{ENTITYNAME_PLACEHOLDER}" lang`

## pseudocode

```c

```

## disassembly

```asm
0x11500  ldarg.0
0x11501  ldarg.1
0x11502  ldarg.2
0x11503  ldc.i4.0
0x11504  ldstr    aEntityNameLoca_0// "\r\n<Entity>\r\n  <Name LocalizedName="...
0x11509  ldstr    aAttributePhysi// "\r\n\t\t<attribute PhysicalName=\"bpf_{"...
0x1150e  call     instance void Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjector::InjectBPFEntity(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, class [mscorlib]System.Collections.Generic.List`1<string> existingParticipatingEntities, valuetype BPFType bpfType, string entityTemplate, string attributeTemplate)
0x11513  ldarg.0
0x11514  ldarg.1
0x11515  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_UniqueName()
0x1151a  ldstr    aRootcomponentT// "<RootComponent type=\"1\" schemaName=\""...
0x1151f  call     instance void Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjector::InjectRootComponent(string workflowUniqueName, string template)
0x11524  ldarg.1
0x11525  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_Steps()
0x1152a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection::GetEnumerator()
0x1152f  stloc.1
0x11530  br.s     loc_11553
0x11532  ldloc.1
0x11533  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase>::get_Current()
0x11538  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.EntityStep
0x1153d  stloc.2
0x1153e  ldloc.2
0x1153f  brfalse.s loc_11553
0x11541  ldarg.0
0x11542  ldloc.2
0x11543  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.EntityStep::get_EntityLogicalName()
0x11548  ldarg.3
0x11549  ldstr    aEntitymapEntit// "\r\n<EntityMap>\r\n  <EntitySource>{ENT"...
0x1154e  call     instance void Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjector::InjectEntityMap(string entitySource, string entityTarget, string template)
0x11553  ldloc.1
0x11554  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x11559  brtrue.s loc_11532
0x1155b  leave.s  loc_11567
0x1155d  ldloc.1
0x1155e  brfalse.s loc_11566
0x11560  ldloc.1
0x11561  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x11566  endfinally
0x11567  ldarg.0
0x11568  ldarg.3
0x11569  call     instance void Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjector::InjectEntityRelationship_FirstPass(string workflowUniqueName)
0x1156e  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x11573  stloc.0
0x11574  ldarg.1
0x11575  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_Steps()
0x1157a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection::GetEnumerator()
0x1157f  stloc.1
0x11580  br.s     loc_115B8
0x11582  ldloc.1
0x11583  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase>::get_Current()
0x11588  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.EntityStep
0x1158d  stloc.3
0x1158e  ldloc.3
0x1158f  brfalse.s loc_115B8
0x11591  ldloc.0
0x11592  ldloc.3
0x11593  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.EntityStep::get_EntityLogicalName()
0x11598  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x1159d  brtrue.s loc_115B8
0x1159f  ldarg.0
0x115a0  ldloc.3
0x115a1  ldarg.3
0x115a2  ldstr    aEntityrelation_15// "\r\n<EntityRelationship Name=\"bpf_{ON_"...
0x115a7  call     instance void Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjector::InjectEntityRelationship_Pass(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.EntityStep es, string workflowUniqueName, string template)
0x115ac  ldloc.0
0x115ad  ldloc.3
0x115ae  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.EntityStep::get_EntityLogicalName()
0x115b3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x115b8  ldloc.1
0x115b9  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x115be  brtrue.s loc_11582
0x115c0  leave.s  loc_115CC
0x115c2  ldloc.1
0x115c3  brfalse.s loc_115CB
0x115c5  ldloc.1
0x115c6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x115cb  endfinally
0x115cc  ldarg.0
0x115cd  ldarg.3
0x115ce  call     instance void Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjector::InjectEntityRelationship_LastPass(string workflowUniqueName)
0x115d3  ldarg.0
0x115d4  ldarg.1
0x115d5  call     instance void Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjector::AddFormulaFile(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep wfs)
0x115da  ret
```
