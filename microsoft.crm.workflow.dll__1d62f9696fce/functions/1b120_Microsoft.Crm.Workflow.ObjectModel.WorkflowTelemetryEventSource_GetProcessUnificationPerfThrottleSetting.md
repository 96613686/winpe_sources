# Microsoft.Crm.Workflow.ObjectModel.WorkflowTelemetryEventSource::GetProcessUnificationPerfThrottleSetting

- ea: `0x1b120`
- end: `0x1b1dc`
- name: `Microsoft.Crm.Workflow.ObjectModel.WorkflowTelemetryEventSource::GetProcessUnificationPerfThrottleSetting`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1b1e0`

## callees

- `0x1b120`

## string_xrefs

- `0x1b133`: `WorkflowProcessServiceInternalHandler.ExecuteWorkflow`

## pseudocode

```c

```

## disassembly

```asm
0x1b120  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor()
0x1b125  stloc.0
0x1b126  ldloc.0
0x1b127  ldstr    aDefault// "Default"
0x1b12c  ldc.i4.0
0x1b12d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x1b132  ldloc.0
0x1b133  ldstr    aWorkflowproces// "WorkflowProcessServiceInternalHandler.E"...
0x1b138  ldc.i4.s 0x3C
0x1b13a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x1b13f  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x1b144  ldstr    aProcessunifica// "ProcessUnificationPerfThrottling"
0x1b149  callvirt T0x2B000016
0x1b14e  stloc.1
0x1b14f  ldloc.1
0x1b150  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1b155  brtrue   loc_1B1DA
0x1b15a  ldloc.1
0x1b15b  ldc.i4.1
0x1b15c  newarr   [mscorlib]System.Char
0x1b161  dup
0x1b162  ldc.i4.0
0x1b163  ldc.i4.s 0x3B
0x1b165  stelem.i2
0x1b166  ldc.i4.1
0x1b167  callvirt instance string[] [mscorlib]System.String::Split(char[], valuetype [mscorlib]System.StringSplitOptions)
0x1b16c  stloc.2
0x1b16d  ldloc.2
0x1b16e  brfalse.s loc_1B1DA
0x1b170  ldloc.2
0x1b171  ldlen
0x1b172  brfalse.s loc_1B1DA
0x1b174  ldloc.2
0x1b175  stloc.3
0x1b176  ldc.i4.0
0x1b177  stloc.s  4
0x1b179  br.s     loc_1B1D3
0x1b17b  ldloc.3
0x1b17c  ldloc.s  4
0x1b17e  ldelem.ref
0x1b17f  ldc.i4.1
0x1b180  newarr   [mscorlib]System.Char
0x1b185  dup
0x1b186  ldc.i4.0
0x1b187  ldc.i4.s 0x3D
0x1b189  stelem.i2
0x1b18a  ldc.i4.1
0x1b18b  callvirt instance string[] [mscorlib]System.String::Split(char[], valuetype [mscorlib]System.StringSplitOptions)
0x1b190  stloc.s  5
0x1b192  ldloc.s  5
0x1b194  brfalse.s loc_1B1CD
0x1b196  ldloc.s  5
0x1b198  ldlen
0x1b199  conv.i4
0x1b19a  ldc.i4.2
0x1b19b  bne.un.s loc_1B1CD
0x1b19d  ldloc.s  5
0x1b19f  ldc.i4.0
0x1b1a0  ldelem.ref
0x1b1a1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1b1a6  brtrue.s loc_1B1CD
0x1b1a8  ldloc.s  5
0x1b1aa  ldc.i4.0
0x1b1ab  ldelem.ref
0x1b1ac  callvirt instance string [mscorlib]System.String::Trim()
0x1b1b1  stloc.s  6
0x1b1b3  ldc.i4.0
0x1b1b4  stloc.s  7
0x1b1b6  ldloc.s  5
0x1b1b8  ldc.i4.1
0x1b1b9  ldelem.ref
0x1b1ba  ldloca.s 7
0x1b1bc  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0x1b1c1  brfalse.s loc_1B1CD
0x1b1c3  ldloc.0
0x1b1c4  ldloc.s  6
0x1b1c6  ldloc.s  7
0x1b1c8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::set_Item(var<u1>, !!T0)
0x1b1cd  ldloc.s  4
0x1b1cf  ldc.i4.1
0x1b1d0  add
0x1b1d1  stloc.s  4
0x1b1d3  ldloc.s  4
0x1b1d5  ldloc.3
0x1b1d6  ldlen
0x1b1d7  conv.i4
0x1b1d8  blt.s    loc_1B17B
0x1b1da  ldloc.0
0x1b1db  ret
```
