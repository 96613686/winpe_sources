# Microsoft.Crm.Application.WebServices.WorkflowWebService::AddDefaultProperties

- ea: `0x8a30`
- end: `0x8a96`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::AddDefaultProperties`
- size: `102`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x4b20`

## callees

- `0x16a0`
- `0x16c0`
- `0x8a30`
- `0x8aa0`

## pseudocode

```c

```

## disassembly

```asm
0x8a30  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8a35  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x8a3a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x8a3f  stloc.0
0x8a40  newobj   instance void Microsoft.Crm.Application.WebServices.DefaultPropertyProviderFactory::.ctor()
0x8a45  ldarg.0
0x8a46  call     instance class [Microsoft.Crm.Service.ObjectModel]Microsoft.Crm.Service.ObjectModel.IDefaultPropertiesProvider Microsoft.Crm.Application.WebServices.DefaultPropertyProviderFactory::GetDefaultPropertiesProvider(string rendererType)
0x8a4b  ldarg.1
0x8a4c  ldarg.2
0x8a4d  ldloc.0
0x8a4e  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification> [Microsoft.Crm.Service.ObjectModel]Microsoft.Crm.Service.ObjectModel.IDefaultPropertiesProvider::GetDefaultProperties(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8a53  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification>::GetEnumerator()
0x8a58  stloc.1
0x8a59  br.s     loc_8A81
0x8a5b  ldloc.1
0x8a5c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification>::get_Current()
0x8a61  stloc.2
0x8a62  ldarg.1
0x8a63  ldloc.2
0x8a64  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification::get_Name()
0x8a69  call     bool Microsoft.Crm.Application.WebServices.WorkflowWebService::IsPropertyPresent(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep createStep, string propertyName)
0x8a6e  brtrue.s loc_8A81
0x8a70  ldarg.1
0x8a71  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep::get_Entity()
0x8a76  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification> [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::get_Properties()
0x8a7b  ldloc.2
0x8a7c  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification>::Add(var<u1>)
0x8a81  ldloc.1
0x8a82  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x8a87  brtrue.s loc_8A5B
0x8a89  leave.s  loc_8A95
0x8a8b  ldloc.1
0x8a8c  brfalse.s loc_8A94
0x8a8e  ldloc.1
0x8a8f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8a94  endfinally
0x8a95  ret
```
