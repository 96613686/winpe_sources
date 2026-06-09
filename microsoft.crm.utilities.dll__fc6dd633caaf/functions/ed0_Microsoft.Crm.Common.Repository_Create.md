# Microsoft.Crm.Common.Repository::Create

- ea: `0xed0`
- end: `0xefc`
- name: `Microsoft.Crm.Common.Repository::Create`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0xed0`
- `0x1e50`

## pseudocode

```c

```

## disassembly

```asm
0xed0  ldarg.1
0xed1  box      mvar<u1>
0xed6  brtrue.s loc_EE3
0xed8  ldstr    aObj// "obj"
0xedd  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xee2  throw
0xee3  ldarg.1
0xee4  call     T0x2B000006
0xee9  stloc.0
0xeea  ldarg.0
0xeeb  call     T0x2B000004
0xef0  callvirt instance class Microsoft.Crm.Common.IDataProvider TypeInformation::get_DataProvider()
0xef5  ldloc.0
0xef6  callvirt T0x2B000007
0xefb  ret
```
