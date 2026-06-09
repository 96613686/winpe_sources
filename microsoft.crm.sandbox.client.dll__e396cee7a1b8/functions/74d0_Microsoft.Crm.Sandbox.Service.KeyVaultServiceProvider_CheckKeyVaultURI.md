# Microsoft.Crm.Sandbox.Service.KeyVaultServiceProvider::CheckKeyVaultURI

- ea: `0x74d0`
- end: `0x7516`
- name: `Microsoft.Crm.Sandbox.Service.KeyVaultServiceProvider::CheckKeyVaultURI`
- size: `70`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x7520`

## callees

- `0x74d0`

## string_xrefs

- `0x74fb`: `Invalid KeyVault URI: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x74d0  ldarg.1
0x74d1  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x74d6  brtrue.s loc_74FB
0x74d8  ldarg.0
0x74d9  ldfld    string[] Microsoft.Crm.Sandbox.Service.KeyVaultServiceProvider::ValidKeyVaultSuffix
0x74de  stloc.0
0x74df  ldc.i4.0
0x74e0  stloc.1
0x74e1  br.s     loc_74F5
0x74e3  ldloc.0
0x74e4  ldloc.1
0x74e5  ldelem.ref
0x74e6  stloc.2
0x74e7  ldarg.1
0x74e8  ldloc.2
0x74e9  callvirt instance bool [mscorlib]System.String::EndsWith(string)
0x74ee  brfalse.s loc_74F1
0x74f0  ret
0x74f1  ldloc.1
0x74f2  ldc.i4.1
0x74f3  add
0x74f4  stloc.1
0x74f5  ldloc.1
0x74f6  ldloc.0
0x74f7  ldlen
0x74f8  conv.i4
0x74f9  blt.s    loc_74E3
0x74fb  ldstr    aInvalidKeyvaul// "Invalid KeyVault URI: {0}"
0x7500  ldarg.1
0x7501  brfalse.s loc_7506
0x7503  ldarg.1
0x7504  br.s     loc_750B
0x7506  ldsfld   string [mscorlib]System.String::Empty
0x750b  call     string [mscorlib]System.String::Format(string, object)
0x7510  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x7515  throw
```
