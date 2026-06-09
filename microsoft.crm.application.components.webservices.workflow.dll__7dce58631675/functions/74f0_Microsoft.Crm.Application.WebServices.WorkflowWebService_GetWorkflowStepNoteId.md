# Microsoft.Crm.Application.WebServices.WorkflowWebService::GetWorkflowStepNoteId

- ea: `0x74f0`
- end: `0x7647`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::GetWorkflowStepNoteId`
- size: `343`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ab0`
- `0x74f0`
- `0x7650`

## pseudocode

```c

```

## disassembly

```asm
0x74f0  ldarg.1
0x74f1  ldstr    aActivityid// "activityId"
0x74f6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x74fb  ldarg.2
0x74fc  ldstr    aEntityid// "entityId"
0x7501  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x7506  ldarg.0
0x7507  ldarg.2
0x7508  ldarg.1
0x7509  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection Microsoft.Crm.Application.WebServices.WorkflowWebService::GetWorkflowAnnotations(string workflowId, string stepId)
0x750e  stloc.0
0x750f  ldloc.0
0x7510  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x7515  ldc.i4.0
0x7516  bgt      loc_760D
0x751b  ldarg.0
0x751c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x7521  ldarg.2
0x7522  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x7527  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x752c  ldarg.1
0x752d  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x7532  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep
0x7537  stloc.1
0x7538  ldloc.1
0x7539  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep::get_Entity()
0x753e  brfalse  loc_7608
0x7543  ldloc.1
0x7544  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep::get_Entity()
0x7549  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification> [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::get_Properties()
0x754e  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification>::get_Count()
0x7553  ldc.i4.0
0x7554  ble      loc_7608
0x7559  ldstr    aAnnotation// "annotation"
0x755e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x7563  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7568  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x756d  stloc.2
0x756e  ldarg.0
0x756f  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::_workflowAdapter
0x7574  ldloc.1
0x7575  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep::get_Entity()
0x757a  ldloc.2
0x757b  ldstr    aAnnotation// "annotation"
0x7580  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::PopulateEntityProperties(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase, string)
0x7585  pop
0x7586  ldloc.2
0x7587  ldstr    aOwnerid// "ownerid"
0x758c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x7591  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_UserId()
0x7596  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GuidToString(valuetype [mscorlib]System.Guid)
0x759b  ldc.i4.8
0x759c  ldsfld   string [mscorlib]System.String::Empty
0x75a1  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::.ctor(string, int32, string)
0x75a6  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x75ab  ldloc.2
0x75ac  ldstr    aStepid_0// "stepid"
0x75b1  ldarg.1
0x75b2  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x75b7  ldloc.2
0x75b8  ldstr    aObjectid// "objectid"
0x75bd  ldarg.2
0x75be  ldc.i4   0x125F
0x75c3  ldsfld   string [mscorlib]System.String::Empty
0x75c8  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::.ctor(string, int32, string)
0x75cd  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x75d2  ldloc.2
0x75d3  ldstr    aObjecttypecode// "objecttypecode"
0x75d8  ldc.i4   0x125F
0x75dd  box      [mscorlib]System.Int32
0x75e2  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x75e7  ldloc.2
0x75e8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x75ed  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Create(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x75f2  stloc.3
0x75f3  ldloca.s 3
0x75f5  ldstr    aB// "B"
0x75fa  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x75ff  call     instance string [mscorlib]System.Guid::ToString(string, class [mscorlib]System.IFormatProvider)
0x7604  stloc.s  4
0x7606  leave.s  loc_7644
0x7608  ldnull
0x7609  stloc.s  4
0x760b  leave.s  loc_7644
0x760d  ldloc.0
0x760e  ldc.i4.0
0x760f  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0x7614  ldstr    aAnnotationid// "annotationid"
0x7619  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x761e  unbox.any [mscorlib]System.Guid
0x7623  stloc.3
0x7624  ldloca.s 3
0x7626  ldstr    aB// "B"
0x762b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7630  call     instance string [mscorlib]System.Guid::ToString(string, class [mscorlib]System.IFormatProvider)
0x7635  stloc.s  4
0x7637  leave.s  loc_7644
0x7639  stloc.s  5
0x763b  ldarg.0
0x763c  ldloc.s  5
0x763e  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x7643  throw
0x7644  ldloc.s  4
0x7646  ret
```
