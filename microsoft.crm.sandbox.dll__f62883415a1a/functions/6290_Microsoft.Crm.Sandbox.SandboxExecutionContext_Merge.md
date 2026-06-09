# Microsoft.Crm.Sandbox.SandboxExecutionContext::Merge

- ea: `0x6290`
- end: `0x64a5`
- name: `Microsoft.Crm.Sandbox.SandboxExecutionContext::Merge`
- size: `533`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x6040`

## callees

- `0x1450`
- `0x14a0`
- `0x6290`
- `0x6530`
- `0x6690`
- `0x66f0`
- `0x6720`
- `0x67d0`

## string_xrefs

- `0x6307`: `SandboxExecutionContext.Merge: merged OwningExtension`

## pseudocode

```c

```

## disassembly

```asm
0x6290  ldarg.1
0x6291  ldstr    aOriginalcontex// "originalContext"
0x6296  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x629b  ldarg.0
0x629c  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection Microsoft.Crm.Sandbox.SandboxExecutionContext::get_InputParameters()
0x62a1  brtrue.s loc_62C7
0x62a3  ldarg.0
0x62a4  ldarg.1
0x62a5  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_InputParameters()
0x62aa  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection Microsoft.Crm.Sandbox.SandboxExecutionContext::_inputParameters
0x62af  ldarg.0
0x62b0  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxExecutionContext::_organizationId
0x62b5  ldc.i4.s 0x27
0x62b7  ldstr    aSandboxexecuti_0// "SandboxExecutionContext.Merge: merged I"...
0x62bc  ldc.i4.0
0x62bd  newarr   [mscorlib]System.Object
0x62c2  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x62c7  ldarg.0
0x62c8  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection Microsoft.Crm.Sandbox.SandboxExecutionContext::get_OutputParameters()
0x62cd  brtrue.s loc_62F3
0x62cf  ldarg.0
0x62d0  ldarg.1
0x62d1  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OutputParameters()
0x62d6  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection Microsoft.Crm.Sandbox.SandboxExecutionContext::_outputParameters
0x62db  ldarg.0
0x62dc  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxExecutionContext::_organizationId
0x62e1  ldc.i4.s 0x27
0x62e3  ldstr    aSandboxexecuti_1// "SandboxExecutionContext.Merge: merged O"...
0x62e8  ldc.i4.0
0x62e9  newarr   [mscorlib]System.Object
0x62ee  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x62f3  ldarg.0
0x62f4  ldarg.1
0x62f5  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OwningExtension()
0x62fa  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference Microsoft.Crm.Sandbox.SandboxExecutionContext::_owningExtension
0x62ff  ldarg.0
0x6300  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxExecutionContext::_organizationId
0x6305  ldc.i4.s 0x27
0x6307  ldstr    aSandboxexecuti_2// "SandboxExecutionContext.Merge: merged O"...
0x630c  ldc.i4.0
0x630d  newarr   [mscorlib]System.Object
0x6312  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x6317  ldarg.0
0x6318  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityImageCollection Microsoft.Crm.Sandbox.SandboxExecutionContext::get_PostEntityImages()
0x631d  brtrue.s loc_6343
0x631f  ldarg.0
0x6320  ldarg.1
0x6321  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityImageCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_PostEntityImages()
0x6326  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityImageCollection Microsoft.Crm.Sandbox.SandboxExecutionContext::_postEntityImages
0x632b  ldarg.0
0x632c  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxExecutionContext::_organizationId
0x6331  ldc.i4.s 0x27
0x6333  ldstr    aSandboxexecuti_3// "SandboxExecutionContext.Merge: merged P"...
0x6338  ldc.i4.0
0x6339  newarr   [mscorlib]System.Object
0x633e  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x6343  ldarg.0
0x6344  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityImageCollection Microsoft.Crm.Sandbox.SandboxExecutionContext::get_PreEntityImages()
0x6349  brtrue.s loc_636F
0x634b  ldarg.0
0x634c  ldarg.1
0x634d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityImageCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_PreEntityImages()
0x6352  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityImageCollection Microsoft.Crm.Sandbox.SandboxExecutionContext::_preEntityImages
0x6357  ldarg.0
0x6358  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxExecutionContext::_organizationId
0x635d  ldc.i4.s 0x27
0x635f  ldstr    aSandboxexecuti_4// "SandboxExecutionContext.Merge: merged P"...
0x6364  ldc.i4.0
0x6365  newarr   [mscorlib]System.Object
0x636a  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x636f  ldarg.0
0x6370  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection Microsoft.Crm.Sandbox.SandboxExecutionContext::get_SharedVariables()
0x6375  brtrue.s loc_639C
0x6377  ldarg.0
0x6378  ldarg.1
0x6379  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_SharedVariables()
0x637e  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection Microsoft.Crm.Sandbox.SandboxExecutionContext::_sharedVariables
0x6383  ldarg.0
0x6384  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxExecutionContext::_organizationId
0x6389  ldc.i4.s 0x27
0x638b  ldstr    aSandboxexecuti_5// "SandboxExecutionContext.Merge: merged S"...
0x6390  ldc.i4.0
0x6391  newarr   [mscorlib]System.Object
0x6396  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x639b  ret
0x639c  ldarg.1
0x639d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_SharedVariables()
0x63a2  brfalse  loc_64A4
0x63a7  ldstr    aChangedentityt// "ChangedEntityTypes"
0x63ac  stloc.0
0x63ad  ldnull
0x63ae  stloc.1
0x63af  ldarg.1
0x63b0  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_SharedVariables()
0x63b5  ldloc.0
0x63b6  ldloca.s 1
0x63b8  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::TryGetValue(var<u1>, !!T0)
0x63bd  brfalse  loc_6481
0x63c2  ldarg.0
0x63c3  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection Microsoft.Crm.Sandbox.SandboxExecutionContext::_sharedVariables
0x63c8  ldloc.0
0x63c9  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::ContainsKey(var<u1>)
0x63ce  brtrue.s loc_63E2
0x63d0  ldarg.0
0x63d1  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection Microsoft.Crm.Sandbox.SandboxExecutionContext::_sharedVariables
0x63d6  ldloc.0
0x63d7  ldloc.1
0x63d8  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Add(var<u1>, !!T0)
0x63dd  br       loc_6481
0x63e2  ldnull
0x63e3  stloc.2
0x63e4  ldarg.0
0x63e5  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection Microsoft.Crm.Sandbox.SandboxExecutionContext::_sharedVariables
0x63ea  ldloc.0
0x63eb  ldloca.s 2
0x63ed  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::TryGetValue(var<u1>, !!T0)
0x63f2  pop
0x63f3  ldloc.1
0x63f4  isinst   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>
0x63f9  stloc.3
0x63fa  ldloc.2
0x63fb  isinst   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>
0x6400  stloc.s  4
0x6402  ldloc.3
0x6403  brfalse.s loc_645A
0x6405  ldloc.s  4
0x6407  brfalse.s loc_645A
0x6409  ldloc.3
0x640a  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::GetEnumerator()
0x640f  stloc.s  5
0x6411  br.s     loc_6441
0x6413  ldloca.s 5
0x6415  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>::get_Current()
0x641a  stloc.s  6
0x641c  ldloc.s  4
0x641e  ldloca.s 6
0x6420  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x6425  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x642a  brtrue.s loc_6441
0x642c  ldloc.s  4
0x642e  ldloca.s 6
0x6430  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x6435  ldloca.s 6
0x6437  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x643c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x6441  ldloca.s 5
0x6443  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>::MoveNext()
0x6448  brtrue.s loc_6413
0x644a  leave.s  loc_645A
0x644c  ldloca.s 5
0x644e  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>
0x6454  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6459  endfinally
0x645a  ldarg.0
0x645b  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxExecutionContext::_organizationId
0x6460  ldc.i4.s 0x27
0x6462  ldstr    aSandboxexecuti_6// "SandboxExecutionContext.Merge: merged C"...
0x6467  ldc.i4.1
0x6468  newarr   [mscorlib]System.Object
0x646d  dup
0x646e  ldc.i4.0
0x646f  ldstr    asc_107B8// ";"
0x6474  ldloc.s  4
0x6476  call     T0x2B000016
0x647b  stelem.ref
0x647c  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x6481  leave.s  loc_64A4
0x6483  stloc.s  7
0x6485  ldarg.0
0x6486  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxExecutionContext::_organizationId
0x648b  ldc.i4.s 0x27
0x648d  ldstr    aSandboxexecuti_7// "SandboxExecutionContext.Merge: merged C"...
0x6492  ldc.i4.1
0x6493  newarr   [mscorlib]System.Object
0x6498  dup
0x6499  ldc.i4.0
0x649a  ldloc.s  7
0x649c  stelem.ref
0x649d  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x64a2  leave.s  loc_64A4
0x64a4  ret
```
