# Microsoft.Crm.CrmPluginAssemblyMetadata::ProcessTypeDef

- ea: `0x1e4f0`
- end: `0x1e66f`
- name: `Microsoft.Crm.CrmPluginAssemblyMetadata::ProcessTypeDef`
- size: `383`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1e050`

## callees

- `0x1e020`
- `0x1e030`
- `0x1e050`
- `0x1e140`
- `0x1e4a0`
- `0x1e4f0`
- `0x1e670`
- `0x1e8c0`
- `0x1f290`
- `0x1f2b0`
- `0x1f2c0`
- `0x1f2e0`
- `0x1f2f0`
- `0x1f310`
- `0x1f320`
- `0x1f340`
- `0x1f350`
- `0x1f380`
- `0x1f3a0`

## string_xrefs

- `0x1e5c6`: `System.Workflow.ComponentModel.Activity`
- `0x1e5ed`: `System.Workflow.ComponentModel.Activity`

## pseudocode

```c

```

## disassembly

```asm
0x1e4f0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1e4f5  ldc.i4.s 0x14
0x1e4f7  ldstr    aProcesstypedef// "ProcessTypeDef: typeDef: {0}"
0x1e4fc  ldc.i4.1
0x1e4fd  newarr   [mscorlib]System.Object
0x1e502  dup
0x1e503  ldc.i4.0
0x1e504  ldarg.0
0x1e505  ldarg.1
0x1e506  call     instance string Microsoft.Crm.CrmPluginAssemblyMetadata::Hex(unsigned int32 value)
0x1e50b  stelem.ref
0x1e50c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1e511  ldarg.1
0x1e512  call     valuetype Microsoft.Crm.CorTokenType Microsoft.Crm.CrmPluginAssemblyMetadata::TokenType(unsigned int32 token)
0x1e517  ldc.i4   0x2000000
0x1e51c  ceq
0x1e51e  ldstr    aProcesstypedef_0// "ProcessTypeDef: expected TypeDef"
0x1e523  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x1e528  ldarg.1
0x1e529  call     bool Microsoft.Crm.CrmPluginAssemblyMetadata::IsNullToken(unsigned int32 token)
0x1e52e  brfalse.s loc_1E532
0x1e530  ldnull
0x1e531  ret
0x1e532  ldarg.0
0x1e533  ldarg.1
0x1e534  ldloca.s 0
0x1e536  ldloca.s 1
0x1e538  ldloca.s 2
0x1e53a  ldloca.s 3
0x1e53c  call     instance void Microsoft.Crm.CrmPluginAssemblyMetadata::GetTypeDefProps(unsigned int32 typeDef, [out] string& typeName, [out] unsigned int32& baseType, [out] bool& isPublic, [out] bool& isAbstract)
0x1e541  ldstr    aSystemObject// "System.Object"
0x1e546  ldloc.0
0x1e547  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1e54c  brfalse.s loc_1E56F
0x1e54e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1e553  ldc.i4.s 0x14
0x1e555  ldstr    a0_0// "{0}"
0x1e55a  ldc.i4.1
0x1e55b  newarr   [mscorlib]System.Object
0x1e560  dup
0x1e561  ldc.i4.0
0x1e562  ldstr    aProcesstypedef_1// "ProcessTypeDef: reached System.Object"
0x1e567  stelem.ref
0x1e568  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1e56d  ldnull
0x1e56e  ret
0x1e56f  ldarg.0
0x1e570  ldarg.1
0x1e571  ldloc.0
0x1e572  call     instance class Microsoft.Crm.CrmPluginTypeMetadata Microsoft.Crm.CrmPluginAssemblyMetadata::GetPluginTypeMetadata(unsigned int32 token, string name)
0x1e577  stloc.s  4
0x1e579  ldloc.s  4
0x1e57b  ldloc.2
0x1e57c  callvirt instance void Microsoft.Crm.CrmPluginTypeMetadata::set_IsPublic(bool value)
0x1e581  ldloc.s  4
0x1e583  ldloc.3
0x1e584  callvirt instance void Microsoft.Crm.CrmPluginTypeMetadata::set_IsAbstract(bool value)
0x1e589  ldstr    aSystemActiviti// "System.Activities.Activity"
0x1e58e  ldloc.s  4
0x1e590  callvirt instance string Microsoft.Crm.CrmPluginTypeMetadata::get_TypeName()
0x1e595  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1e59a  brfalse.s loc_1E5C6
0x1e59c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1e5a1  ldc.i4.s 0x14
0x1e5a3  ldstr    aProcesstypedef_2// "ProcessTypeDef: reached WorkflowBaseCla"...
0x1e5a8  ldc.i4.1
0x1e5a9  newarr   [mscorlib]System.Object
0x1e5ae  dup
0x1e5af  ldc.i4.0
0x1e5b0  ldstr    aSystemActiviti// "System.Activities.Activity"
0x1e5b5  stelem.ref
0x1e5b6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1e5bb  ldloc.s  4
0x1e5bd  ldc.i4.1
0x1e5be  callvirt instance void Microsoft.Crm.CrmPluginTypeMetadata::set_IsV5WorkflowActivity(bool value)
0x1e5c3  ldloc.s  4
0x1e5c5  ret
0x1e5c6  ldstr    aSystemWorkflow// "System.Workflow.ComponentModel.Activity"
0x1e5cb  ldloc.s  4
0x1e5cd  callvirt instance string Microsoft.Crm.CrmPluginTypeMetadata::get_TypeName()
0x1e5d2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1e5d7  brfalse.s loc_1E603
0x1e5d9  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1e5de  ldc.i4.s 0x14
0x1e5e0  ldstr    aProcesstypedef_3// "ProcessTypeDef: reached WorkflowBaseCla"...
0x1e5e5  ldc.i4.1
0x1e5e6  newarr   [mscorlib]System.Object
0x1e5eb  dup
0x1e5ec  ldc.i4.0
0x1e5ed  ldstr    aSystemWorkflow// "System.Workflow.ComponentModel.Activity"
0x1e5f2  stelem.ref
0x1e5f3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1e5f8  ldloc.s  4
0x1e5fa  ldc.i4.1
0x1e5fb  callvirt instance void Microsoft.Crm.CrmPluginTypeMetadata::set_IsV4WorkflowActivity(bool value)
0x1e600  ldloc.s  4
0x1e602  ret
0x1e603  ldarg.0
0x1e604  ldloc.s  4
0x1e606  call     instance void Microsoft.Crm.CrmPluginAssemblyMetadata::CheckInterfaces(class Microsoft.Crm.CrmPluginTypeMetadata crmType)
0x1e60b  ldarg.0
0x1e60c  ldloc.1
0x1e60d  call     instance class Microsoft.Crm.CrmPluginTypeMetadata Microsoft.Crm.CrmPluginAssemblyMetadata::ProcessType(unsigned int32 token)
0x1e612  stloc.s  5
0x1e614  ldloc.s  5
0x1e616  brfalse.s loc_1E66C
0x1e618  ldloc.s  4
0x1e61a  dup
0x1e61b  callvirt instance bool Microsoft.Crm.CrmPluginTypeMetadata::get_IsV4PluginType()
0x1e620  ldloc.s  5
0x1e622  callvirt instance bool Microsoft.Crm.CrmPluginTypeMetadata::get_IsV4PluginType()
0x1e627  or
0x1e628  callvirt instance void Microsoft.Crm.CrmPluginTypeMetadata::set_IsV4PluginType(bool value)
0x1e62d  ldloc.s  4
0x1e62f  dup
0x1e630  callvirt instance bool Microsoft.Crm.CrmPluginTypeMetadata::get_IsV5PluginType()
0x1e635  ldloc.s  5
0x1e637  callvirt instance bool Microsoft.Crm.CrmPluginTypeMetadata::get_IsV5PluginType()
0x1e63c  or
0x1e63d  callvirt instance void Microsoft.Crm.CrmPluginTypeMetadata::set_IsV5PluginType(bool value)
0x1e642  ldloc.s  4
0x1e644  dup
0x1e645  callvirt instance bool Microsoft.Crm.CrmPluginTypeMetadata::get_IsV4WorkflowActivity()
0x1e64a  ldloc.s  5
0x1e64c  callvirt instance bool Microsoft.Crm.CrmPluginTypeMetadata::get_IsV4WorkflowActivity()
0x1e651  or
0x1e652  callvirt instance void Microsoft.Crm.CrmPluginTypeMetadata::set_IsV4WorkflowActivity(bool value)
0x1e657  ldloc.s  4
0x1e659  dup
0x1e65a  callvirt instance bool Microsoft.Crm.CrmPluginTypeMetadata::get_IsV5WorkflowActivity()
0x1e65f  ldloc.s  5
0x1e661  callvirt instance bool Microsoft.Crm.CrmPluginTypeMetadata::get_IsV5WorkflowActivity()
0x1e666  or
0x1e667  callvirt instance void Microsoft.Crm.CrmPluginTypeMetadata::set_IsV5WorkflowActivity(bool value)
0x1e66c  ldloc.s  4
0x1e66e  ret
```
