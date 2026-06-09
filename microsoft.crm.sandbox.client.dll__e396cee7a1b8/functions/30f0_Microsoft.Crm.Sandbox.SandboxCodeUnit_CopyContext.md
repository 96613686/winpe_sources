# Microsoft.Crm.Sandbox.SandboxCodeUnit::CopyContext

- ea: `0x30f0`
- end: `0x3255`
- name: `Microsoft.Crm.Sandbox.SandboxCodeUnit::CopyContext`
- size: `357`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x2c40`
- `0x30f0`

## callees

- `0x30f0`
- `0x3320`

## pseudocode

```c

```

## disassembly

```asm
0x30f0  ldarg.0
0x30f1  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_InputParameters()
0x30f6  brfalse  loc_31CA
0x30fb  ldarg.1
0x30fc  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_InputParameters()
0x3101  brfalse  loc_31CA
0x3106  ldarg.0
0x3107  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_InputParameters()
0x310c  ldstr    aTarget// "Target"
0x3111  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::ContainsKey(var<u1>)
0x3116  brfalse  loc_31CA
0x311b  ldarg.1
0x311c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_InputParameters()
0x3121  ldstr    aTarget// "Target"
0x3126  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::ContainsKey(var<u1>)
0x312b  brfalse  loc_31CA
0x3130  ldarg.0
0x3131  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_InputParameters()
0x3136  ldstr    aTarget// "Target"
0x313b  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x3140  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity
0x3145  brfalse  loc_31CA
0x314a  ldarg.1
0x314b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_InputParameters()
0x3150  ldstr    aTarget// "Target"
0x3155  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x315a  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity
0x315f  brfalse.s loc_31CA
0x3161  ldarg.0
0x3162  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_InputParameters()
0x3167  ldstr    aTarget// "Target"
0x316c  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x3171  ldarg.1
0x3172  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_InputParameters()
0x3177  ldstr    aTarget// "Target"
0x317c  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x3181  beq.s    loc_31CA
0x3183  ldarg.0
0x3184  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_InputParameters()
0x3189  ldstr    aTarget// "Target"
0x318e  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x3193  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity
0x3198  ldarg.1
0x3199  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_InputParameters()
0x319e  ldstr    aTarget// "Target"
0x31a3  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x31a8  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity
0x31ad  call     void Microsoft.Crm.Sandbox.SandboxCodeUnit::CopyEntity(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity sourceEntity, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity destEntity)
0x31b2  ldarg.0
0x31b3  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_InputParameters()
0x31b8  ldarg.1
0x31b9  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_InputParameters()
0x31be  ldstr    aTarget// "Target"
0x31c3  call     T0x2B000006
0x31c8  br.s     loc_31DB
0x31ca  ldarg.0
0x31cb  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_InputParameters()
0x31d0  ldarg.1
0x31d1  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_InputParameters()
0x31d6  call     T0x2B000007
0x31db  ldarg.0
0x31dc  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OutputParameters()
0x31e1  ldarg.1
0x31e2  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OutputParameters()
0x31e7  call     T0x2B000007
0x31ec  ldarg.0
0x31ed  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityImageCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_PostEntityImages()
0x31f2  ldarg.1
0x31f3  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityImageCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_PostEntityImages()
0x31f8  call     T0x2B000008
0x31fd  ldarg.0
0x31fe  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityImageCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_PreEntityImages()
0x3203  ldarg.1
0x3204  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityImageCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_PreEntityImages()
0x3209  call     T0x2B000008
0x320e  ldarg.0
0x320f  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_SharedVariables()
0x3214  ldarg.1
0x3215  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_SharedVariables()
0x321a  call     T0x2B000007
0x321f  ldarg.0
0x3220  isinst   [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext
0x3225  stloc.0
0x3226  ldarg.1
0x3227  isinst   [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext
0x322c  stloc.1
0x322d  ldloc.0
0x322e  brfalse.s loc_3254
0x3230  ldloc.0
0x3231  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_ParentContext()
0x3236  brfalse.s loc_3254
0x3238  ldloc.1
0x3239  brfalse.s loc_3254
0x323b  ldloc.1
0x323c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_ParentContext()
0x3241  brfalse.s loc_3254
0x3243  ldloc.0
0x3244  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_ParentContext()
0x3249  ldloc.1
0x324a  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExecutionContext::get_ParentContext()
0x324f  call     void Microsoft.Crm.Sandbox.SandboxCodeUnit::CopyContext(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext sourceContext, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext destContext)
0x3254  ret
```
