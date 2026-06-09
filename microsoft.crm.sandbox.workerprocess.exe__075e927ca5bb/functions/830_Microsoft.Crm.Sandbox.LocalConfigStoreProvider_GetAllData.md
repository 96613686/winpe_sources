# Microsoft.Crm.Sandbox.LocalConfigStoreProvider::GetAllData

- ea: `0x830`
- end: `0x843`
- name: `Microsoft.Crm.Sandbox.LocalConfigStoreProvider::GetAllData`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x830  ldarg.0
0x831  ldarg.0
0x832  ldftn    instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, unsigned int8[]> Microsoft.Crm.Sandbox.LocalConfigStoreProvider::<GetAllData>b__1_0(class Microsoft.Crm.Sandbox.SandboxSdkClient client)
0x838  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Crm.Sandbox.SandboxSdkClient, class [mscorlib]System.Collections.Generic.Dictionary`2<string, unsigned int8[]>>::.ctor(object, native int)
0x83d  call     T0x2B000003
0x842  ret
```
