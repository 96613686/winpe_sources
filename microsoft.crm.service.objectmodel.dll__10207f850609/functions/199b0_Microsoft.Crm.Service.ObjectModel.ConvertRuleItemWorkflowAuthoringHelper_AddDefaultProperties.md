# Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::AddDefaultProperties

- ea: `0x199b0`
- end: `0x19a2b`
- name: `Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::AddDefaultProperties`
- size: `123`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x197f0`

## callees

- `0x199b0`
- `0x19a30`
- `0x1aa60`
- `0x1aa80`

## string_xrefs

- `0x199c0`: `Microsoft.Crm.Application.Components.WebServices.Workflow`
- `0x199c5`: `Microsoft.Crm.Application.WebServices.DefaultPropertyProviderFactory`

## pseudocode

```c

```

## disassembly

```asm
0x199b0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x199b5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x199ba  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x199bf  stloc.0
0x199c0  ldstr    aMicrosoftCrmAp// "Microsoft.Crm.Application.Components.We"...
0x199c5  ldstr    aMicrosoftCrmAp_0// "Microsoft.Crm.Application.WebServices.D"...
0x199ca  call     class [mscorlib]System.Runtime.Remoting.ObjectHandle [mscorlib]System.Activator::CreateInstance(string, string)
0x199cf  callvirt instance object [mscorlib]System.Runtime.Remoting.ObjectHandle::Unwrap()
0x199d4  castclass Microsoft.Crm.Service.ObjectModel.IGetDefaultPropertiesProvider
0x199d9  ldarg.0
0x199da  callvirt instance class Microsoft.Crm.Service.ObjectModel.IDefaultPropertiesProvider Microsoft.Crm.Service.ObjectModel.IGetDefaultPropertiesProvider::GetDefaultPropertiesProvider(string rendererType)
0x199df  ldarg.1
0x199e0  ldarg.2
0x199e1  ldloc.0
0x199e2  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification> Microsoft.Crm.Service.ObjectModel.IDefaultPropertiesProvider::GetDefaultProperties(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep createStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x199e7  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification>::GetEnumerator()
0x199ec  stloc.1
0x199ed  br.s     loc_19A16
0x199ef  ldloc.1
0x199f0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification>::get_Current()
0x199f5  stloc.2
0x199f6  ldarg.1
0x199f7  ldloc.2
0x199f8  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification::get_Name()
0x199fd  call     int32 Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::IfPropertyPresent(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep createStep, string propertyName)
0x19a02  ldc.i4.m1
0x19a03  bne.un.s loc_19A16
0x19a05  ldarg.1
0x19a06  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep::get_Entity()
0x19a0b  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification> [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::get_Properties()
0x19a10  ldloc.2
0x19a11  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification>::Add(var<u1>)
0x19a16  ldloc.1
0x19a17  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x19a1c  brtrue.s loc_199EF
0x19a1e  leave.s  loc_19A2A
0x19a20  ldloc.1
0x19a21  brfalse.s loc_19A29
0x19a23  ldloc.1
0x19a24  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x19a29  endfinally
0x19a2a  ret
```
