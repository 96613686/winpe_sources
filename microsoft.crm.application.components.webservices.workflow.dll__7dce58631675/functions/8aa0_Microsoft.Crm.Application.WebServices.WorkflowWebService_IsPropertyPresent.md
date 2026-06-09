# Microsoft.Crm.Application.WebServices.WorkflowWebService::IsPropertyPresent

- ea: `0x8aa0`
- end: `0x8ae3`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::IsPropertyPresent`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x8a30`

## callees

- `0x8aa0`

## pseudocode

```c

```

## disassembly

```asm
0x8aa0  ldarg.0
0x8aa1  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep::get_Entity()
0x8aa6  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification> [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::get_Properties()
0x8aab  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification>::GetEnumerator()
0x8ab0  stloc.0
0x8ab1  br.s     loc_8ACB
0x8ab3  ldloc.0
0x8ab4  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification>::get_Current()
0x8ab9  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification::get_Name()
0x8abe  ldarg.1
0x8abf  ldc.i4.5
0x8ac0  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x8ac5  brfalse.s loc_8ACB
0x8ac7  ldc.i4.1
0x8ac8  stloc.1
0x8ac9  leave.s  loc_8AE1
0x8acb  ldloc.0
0x8acc  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x8ad1  brtrue.s loc_8AB3
0x8ad3  leave.s  loc_8ADF
0x8ad5  ldloc.0
0x8ad6  brfalse.s loc_8ADE
0x8ad8  ldloc.0
0x8ad9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8ade  endfinally
0x8adf  ldc.i4.0
0x8ae0  ret
0x8ae1  ldloc.1
0x8ae2  ret
```
