# Microsoft.Crm.Sandbox.LocalConfigStoreProvider::GetData

- ea: `0x850`
- end: `0x887`
- name: `Microsoft.Crm.Sandbox.LocalConfigStoreProvider::GetData`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x5790`

## pseudocode

```c

```

## disassembly

```asm
0x850  newobj   instance void <>c__DisplayClass2_0::.ctor()
0x855  stloc.0
0x856  ldloc.0
0x857  ldarg.0
0x858  stfld    class Microsoft.Crm.Sandbox.LocalConfigStoreProvider <>c__DisplayClass2_0::<>4__this
0x85d  ldloc.0
0x85e  ldarg.1
0x85f  stfld    string <>c__DisplayClass2_0::keyName
0x864  ldloc.0
0x865  ldfld    string <>c__DisplayClass2_0::keyName
0x86a  ldstr    aKeyname// "keyName"
0x86f  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x874  ldarg.0
0x875  ldloc.0
0x876  ldftn    instance unsigned int8[] <>c__DisplayClass2_0::<GetData>b__0(class Microsoft.Crm.Sandbox.SandboxSdkClient client)
0x87c  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Crm.Sandbox.SandboxSdkClient, unsigned int8[]>::.ctor(object, native int)
0x881  call     T0x2B000004
0x886  ret
```
