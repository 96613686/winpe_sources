# Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoMetadataBase::GetActivityInfo_0

- ea: `0x1c740`
- end: `0x1c7f7`
- name: `Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoMetadataBase::GetActivityInfo_0`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1b990`

## callees

- `0x1c740`

## string_xrefs

- `0x1c7c1`: `publickeytoken`

## pseudocode

```c

```

## disassembly

```asm
0x1c740  ldarg.3
0x1c741  ldnull
0x1c742  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1c747  brfalse.s loc_1C74B
0x1c749  ldnull
0x1c74a  ret
0x1c74b  ldarg.3
0x1c74c  ldtoken  [System.Activities]System.Activities.Activity
0x1c751  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1c756  callvirt instance bool [mscorlib]System.Type::IsSubclassOf(class [mscorlib]System.Type)
0x1c75b  stloc.0
0x1c75c  ldarg.2
0x1c75d  ldstr    aName// "name"
0x1c762  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x1c767  brtrue.s loc_1C76C
0x1c769  ldnull
0x1c76a  br.s     loc_1C77C
0x1c76c  ldarg.2
0x1c76d  ldstr    aName// "name"
0x1c772  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1c777  isinst   [mscorlib]System.String
0x1c77c  ldarg.2
0x1c77d  ldstr    aWorkflowactivi// "workflowactivitygroupname"
0x1c782  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x1c787  brtrue.s loc_1C78C
0x1c789  ldnull
0x1c78a  br.s     loc_1C79C
0x1c78c  ldarg.2
0x1c78d  ldstr    aWorkflowactivi// "workflowactivitygroupname"
0x1c792  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1c797  isinst   [mscorlib]System.String
0x1c79c  stloc.1
0x1c79d  ldloc.1
0x1c79e  ldarg.2
0x1c79f  ldstr    aTypename// "typename"
0x1c7a4  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1c7a9  castclass [mscorlib]System.String
0x1c7ae  ldarg.s  4
0x1c7b0  ldarg.1
0x1c7b1  ldstr    aName// "name"
0x1c7b6  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1c7bb  castclass [mscorlib]System.String
0x1c7c0  ldarg.1
0x1c7c1  ldstr    aPublickeytoken// "publickeytoken"
0x1c7c6  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1c7cb  castclass [mscorlib]System.String
0x1c7d0  ldarg.1
0x1c7d1  ldstr    aCulture// "culture"
0x1c7d6  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1c7db  castclass [mscorlib]System.String
0x1c7e0  ldarg.1
0x1c7e1  ldstr    aVersion// "version"
0x1c7e6  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1c7eb  castclass [mscorlib]System.String
0x1c7f0  ldloc.0
0x1c7f1  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfo::.ctor(string, string, string, valuetype [mscorlib]System.Guid, string, string, string, string, bool)
0x1c7f6  ret
```
