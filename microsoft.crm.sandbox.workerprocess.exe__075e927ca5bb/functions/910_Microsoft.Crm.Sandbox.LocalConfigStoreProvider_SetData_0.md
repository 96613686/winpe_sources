# Microsoft.Crm.Sandbox.LocalConfigStoreProvider::SetData_0

- ea: `0x910`
- end: `0x95f`
- name: `Microsoft.Crm.Sandbox.LocalConfigStoreProvider::SetData_0`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x5880`

## pseudocode

```c

```

## disassembly

```asm
0x910  newobj   instance void <>c__DisplayClass5_0::.ctor()
0x915  stloc.0
0x916  ldloc.0
0x917  ldarg.0
0x918  stfld    class Microsoft.Crm.Sandbox.LocalConfigStoreProvider <>c__DisplayClass5_0::<>4__this
0x91d  ldloc.0
0x91e  ldarg.1
0x91f  stfld    string <>c__DisplayClass5_0::keyName
0x924  ldloc.0
0x925  ldarg.2
0x926  stfld    unsigned int8[] <>c__DisplayClass5_0::data
0x92b  ldloc.0
0x92c  ldfld    string <>c__DisplayClass5_0::keyName
0x931  ldstr    aKeyname// "keyName"
0x936  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x93b  ldloc.0
0x93c  ldfld    unsigned int8[] <>c__DisplayClass5_0::data
0x941  ldstr    aData// "data"
0x946  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x94b  ldarg.0
0x94c  ldloc.0
0x94d  ldftn    instance object <>c__DisplayClass5_0::<SetData>b__0(class Microsoft.Crm.Sandbox.SandboxSdkClient client)
0x953  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Crm.Sandbox.SandboxSdkClient, object>::.ctor(object, native int)
0x958  call     T0x2B000002
0x95d  pop
0x95e  ret
```
