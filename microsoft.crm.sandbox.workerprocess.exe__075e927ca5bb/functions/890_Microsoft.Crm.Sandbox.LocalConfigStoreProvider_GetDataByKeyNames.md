# Microsoft.Crm.Sandbox.LocalConfigStoreProvider::GetDataByKeyNames

- ea: `0x890`
- end: `0x8c7`
- name: `Microsoft.Crm.Sandbox.LocalConfigStoreProvider::GetDataByKeyNames`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x57e0`

## pseudocode

```c

```

## disassembly

```asm
0x890  newobj   instance void <>c__DisplayClass3_0::.ctor()
0x895  stloc.0
0x896  ldloc.0
0x897  ldarg.0
0x898  stfld    class Microsoft.Crm.Sandbox.LocalConfigStoreProvider <>c__DisplayClass3_0::<>4__this
0x89d  ldloc.0
0x89e  ldarg.1
0x89f  stfld    class [mscorlib]System.Collections.Generic.List`1<string> <>c__DisplayClass3_0::keyNames
0x8a4  ldloc.0
0x8a5  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> <>c__DisplayClass3_0::keyNames
0x8aa  ldstr    aKeynames// "keyNames"
0x8af  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x8b4  ldarg.0
0x8b5  ldloc.0
0x8b6  ldftn    instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, unsigned int8[]> <>c__DisplayClass3_0::<GetDataByKeyNames>b__0(class Microsoft.Crm.Sandbox.SandboxSdkClient client)
0x8bc  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Crm.Sandbox.SandboxSdkClient, class [mscorlib]System.Collections.Generic.Dictionary`2<string, unsigned int8[]>>::.ctor(object, native int)
0x8c1  call     T0x2B000003
0x8c6  ret
```
