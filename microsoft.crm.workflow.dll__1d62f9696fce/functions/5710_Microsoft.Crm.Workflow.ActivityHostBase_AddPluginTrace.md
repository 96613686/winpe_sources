# Microsoft.Crm.Workflow.ActivityHostBase::AddPluginTrace

- ea: `0x5710`
- end: `0x57ef`
- name: `Microsoft.Crm.Workflow.ActivityHostBase::AddPluginTrace`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x5950`

## callees

- `0x5710`
- `0x6890`
- `0x8f40`
- `0x91f0`
- `0x15120`
- `0x15140`
- `0x15160`
- `0x15180`
- `0x1b250`
- `0x1b2d0`

## pseudocode

```c

```

## disassembly

```asm
0x5710  ldarg.3
0x5711  callvirt instance class Microsoft.Crm.Workflow.WorkflowTracingService Microsoft.Crm.Workflow.ICommonWorkflowContext::get_WorkflowTracingService()
0x5716  callvirt instance string Microsoft.Crm.Workflow.WorkflowTracingService::get_TraceInfo()
0x571b  stloc.0
0x571c  ldsfld   string [mscorlib]System.String::Empty
0x5721  stloc.1
0x5722  ldsfld   string [mscorlib]System.String::Empty
0x5727  stloc.2
0x5728  ldsfld   string [mscorlib]System.String::Empty
0x572d  stloc.3
0x572e  ldsfld   string [mscorlib]System.String::Empty
0x5733  stloc.s  4
0x5735  ldsfld   string [mscorlib]System.String::Empty
0x573a  stloc.s  5
0x573c  ldarg.2
0x573d  isinst   Microsoft.Crm.Workflow.Services.InvalidCustomActivityExecutionException
0x5742  stloc.s  6
0x5744  ldloc.s  6
0x5746  brfalse.s loc_5794
0x5748  ldloc.s  6
0x574a  callvirt instance string Microsoft.Crm.Workflow.Services.InvalidCustomActivityExecutionException::get_CustomActivityTypeName()
0x574f  stloc.3
0x5750  ldloc.3
0x5751  ldc.i4.1
0x5752  newarr   [mscorlib]System.Char
0x5757  dup
0x5758  ldc.i4.0
0x5759  ldc.i4.s 0x2C
0x575b  stelem.i2
0x575c  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x5761  ldc.i4.0
0x5762  ldelem.ref
0x5763  stloc.3
0x5764  ldloc.s  6
0x5766  callvirt instance string Microsoft.Crm.Workflow.Services.InvalidCustomActivityExecutionException::get_CustomActivityAssemblyName()
0x576b  stloc.2
0x576c  ldloc.2
0x576d  ldc.i4.1
0x576e  newarr   [mscorlib]System.Char
0x5773  dup
0x5774  ldc.i4.0
0x5775  ldc.i4.s 0x2C
0x5777  stelem.i2
0x5778  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x577d  ldc.i4.0
0x577e  ldelem.ref
0x577f  stloc.2
0x5780  ldloc.s  6
0x5782  callvirt instance string Microsoft.Crm.Workflow.Services.InvalidCustomActivityExecutionException::get_CustomActivityAssemblyQualifiedName()
0x5787  stloc.s  5
0x5789  ldloc.s  6
0x578b  callvirt instance class [mscorlib]System.Exception Microsoft.Crm.Workflow.Services.InvalidCustomActivityExecutionException::get_CustomActivityException()
0x5790  starg.s  2
0x5792  br.s     loc_57BE
0x5794  ldarg.1
0x5795  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x579a  dup
0x579b  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x57a0  callvirt instance class [mscorlib]System.Reflection.AssemblyName [mscorlib]System.Reflection.Assembly::GetName()
0x57a5  callvirt instance string [mscorlib]System.Reflection.AssemblyName::get_Name()
0x57aa  stloc.2
0x57ab  callvirt instance string [mscorlib]System.Type::get_FullName()
0x57b0  stloc.3
0x57b1  ldarg.1
0x57b2  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x57b7  callvirt instance string [mscorlib]System.Type::get_AssemblyQualifiedName()
0x57bc  stloc.s  5
0x57be  ldarg.3
0x57bf  newobj   instance void Microsoft.Crm.Workflow.AsyncCustomActivityLoaderDirect::.ctor(class Microsoft.Crm.Workflow.ICommonWorkflowContext context)
0x57c4  newobj   instance void Microsoft.Crm.Workflow.ObjectModel.WorkflowAssemblyResolverHelper::.ctor(class Microsoft.Crm.Workflow.ObjectModel.ICustomActivityLoader activityLoader)
0x57c9  ldloc.s  5
0x57cb  ldloca.s 1
0x57cd  ldloca.s 4
0x57cf  ldarg.3
0x57d0  ldc.i4.0
0x57d1  callvirt instance bool Microsoft.Crm.Workflow.ObjectModel.WorkflowAssemblyResolverHelper::RetrieveActivityNameAndGroupName(string assemblyQualifiedName, [out] string& activityName, [out] string& activityGroupName, class Microsoft.Crm.Workflow.ICommonWorkflowContext context, bool ignoreWeb)
0x57d6  brtrue.s loc_57DF
0x57d8  ldarg.1
0x57d9  callvirt instance string [System.Activities]System.Activities.Activity::get_DisplayName()
0x57de  stloc.1
0x57df  ldarg.2
0x57e0  ldloc.0
0x57e1  ldloc.2
0x57e2  ldloc.3
0x57e3  ldloc.s  4
0x57e5  ldloc.1
0x57e6  ldc.i4.1
0x57e7  ldc.i4.1
0x57e8  ldc.i4.0
0x57e9  call     class [mscorlib]System.Exception [Microsoft.Crm]Microsoft.Crm.PluginExceptionConvertor::ConvertPluginException(class [mscorlib]System.Exception, string, string, string, string, string, bool, bool, bool)
0x57ee  ret
```
