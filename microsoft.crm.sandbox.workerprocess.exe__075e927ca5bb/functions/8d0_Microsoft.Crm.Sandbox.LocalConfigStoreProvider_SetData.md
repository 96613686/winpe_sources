# Microsoft.Crm.Sandbox.LocalConfigStoreProvider::SetData

- ea: `0x8d0`
- end: `0x908`
- name: `Microsoft.Crm.Sandbox.LocalConfigStoreProvider::SetData`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x5830`

## pseudocode

```c

```

## disassembly

```asm
0x8d0  newobj   instance void <>c__DisplayClass4_0::.ctor()
0x8d5  stloc.0
0x8d6  ldloc.0
0x8d7  ldarg.0
0x8d8  stfld    class Microsoft.Crm.Sandbox.LocalConfigStoreProvider <>c__DisplayClass4_0::<>4__this
0x8dd  ldloc.0
0x8de  ldarg.1
0x8df  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, unsigned int8[]> <>c__DisplayClass4_0::keyData
0x8e4  ldloc.0
0x8e5  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, unsigned int8[]> <>c__DisplayClass4_0::keyData
0x8ea  ldstr    aKeydata// "keyData"
0x8ef  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x8f4  ldarg.0
0x8f5  ldloc.0
0x8f6  ldftn    instance object <>c__DisplayClass4_0::<SetData>b__0(class Microsoft.Crm.Sandbox.SandboxSdkClient client)
0x8fc  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Crm.Sandbox.SandboxSdkClient, object>::.ctor(object, native int)
0x901  call     T0x2B000002
0x906  pop
0x907  ret
```
