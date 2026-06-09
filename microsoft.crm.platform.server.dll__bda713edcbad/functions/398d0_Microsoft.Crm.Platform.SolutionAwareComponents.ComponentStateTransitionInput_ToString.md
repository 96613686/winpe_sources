# Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionInput::ToString

- ea: `0x398d0`
- end: `0x39965`
- name: `Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionInput::ToString`
- size: `149`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x398d6`: `ComponentStateName: {0}; `
- `0x398ed`: `ComponentOperation: {0}; `
- `0x39904`: `ComponentSolutionType: {0}; `
- `0x39949`: `FinalComponentState: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x398d0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x398d5  dup
0x398d6  ldstr    aComponentstate_4// "ComponentStateName: {0}; "
0x398db  ldarg.0
0x398dc  ldfld    valuetype Microsoft.Crm.Platform.ComponentStateNames Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionInput::_currentState
0x398e1  box      Microsoft.Crm.Platform.ComponentStateNames
0x398e6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x398eb  pop
0x398ec  dup
0x398ed  ldstr    aComponentopera// "ComponentOperation: {0}; "
0x398f2  ldarg.0
0x398f3  ldfld    valuetype Microsoft.Crm.Platform.ComponentOperation Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionInput::_operation
0x398f8  box      Microsoft.Crm.Platform.ComponentOperation
0x398fd  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x39902  pop
0x39903  dup
0x39904  ldstr    aComponentsolut// "ComponentSolutionType: {0}; "
0x39909  ldarg.0
0x3990a  ldfld    valuetype [Microsoft.Crm.Constants]Microsoft.Crm.ComponentSolutionType Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionInput::_solutionType
0x3990f  box      [Microsoft.Crm.Constants]Microsoft.Crm.ComponentSolutionType
0x39914  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x39919  pop
0x3991a  dup
0x3991b  ldstr    aSolutionoperat// "SolutionOperationContext: {0}; "
0x39920  ldarg.0
0x39921  ldfld    valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionOperationContext Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionInput::_operationContext
0x39926  box      [Microsoft.Crm.Core]Microsoft.Crm.SolutionOperationContext
0x3992b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x39930  pop
0x39931  dup
0x39932  ldstr    aIsprotected0// "IsProtected: {0}; "
0x39937  ldarg.0
0x39938  ldfld    bool Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionInput::_isProtected
0x3993d  box      [mscorlib]System.Boolean
0x39942  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x39947  pop
0x39948  dup
0x39949  ldstr    aFinalcomponent// "FinalComponentState: {0}"
0x3994e  ldarg.0
0x3994f  ldfld    valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState Microsoft.Crm.Platform.SolutionAwareComponents.ComponentStateTransitionInput::_finalComponentState
0x39954  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState
0x39959  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x3995e  pop
0x3995f  callvirt instance string [mscorlib]System.Object::ToString()
0x39964  ret
```
