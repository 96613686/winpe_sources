# Microsoft.Xrm.Async.Bridges.FromCommonAuth.ApplicationInfo::.ctor

- ea: `0x22f0`
- end: `0x233f`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonAuth.ApplicationInfo::.ctor`
- size: `79`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x2340`
- `0x2ab0`

## callees

- `0xab0`

## string_xrefs

- `0x2319`: `appUri`

## pseudocode

```c

```

## disassembly

```asm
0x22f0  ldarg.0
0x22f1  call     instance void [mscorlib]System.Object::.ctor()
0x22f6  ldarg.1
0x22f7  ldstr    aClientid_0// "clientId"
0x22fc  call     T0x2B000024
0x2301  call     class Microsoft.Xrm.Async.Bridges.FromCommon.ArgumentAssertion`1<string> Microsoft.Xrm.Async.Bridges.FromCommon.Args::IsNotNullOrEmpty(class Microsoft.Xrm.Async.Bridges.FromCommon.ArgumentAssertion`1<string> arg)
0x2306  pop
0x2307  ldarg.2
0x2308  ldstr    aAuthorityurl_0// "authorityUrl"
0x230d  call     T0x2B000024
0x2312  call     class Microsoft.Xrm.Async.Bridges.FromCommon.ArgumentAssertion`1<string> Microsoft.Xrm.Async.Bridges.FromCommon.Args::IsNotNullOrEmpty(class Microsoft.Xrm.Async.Bridges.FromCommon.ArgumentAssertion`1<string> arg)
0x2317  pop
0x2318  ldarg.3
0x2319  ldstr    aAppuri_0// "appUri"
0x231e  call     T0x2B000024
0x2323  call     class Microsoft.Xrm.Async.Bridges.FromCommon.ArgumentAssertion`1<string> Microsoft.Xrm.Async.Bridges.FromCommon.Args::IsNotNullOrEmpty(class Microsoft.Xrm.Async.Bridges.FromCommon.ArgumentAssertion`1<string> arg)
0x2328  pop
0x2329  ldarg.0
0x232a  ldarg.1
0x232b  stfld    string Microsoft.Xrm.Async.Bridges.FromCommonAuth.ApplicationInfo::<ClientId>k__BackingField
0x2330  ldarg.0
0x2331  ldarg.2
0x2332  stfld    string Microsoft.Xrm.Async.Bridges.FromCommonAuth.ApplicationInfo::<AuthorityUrl>k__BackingField
0x2337  ldarg.0
0x2338  ldarg.3
0x2339  stfld    string Microsoft.Xrm.Async.Bridges.FromCommonAuth.ApplicationInfo::<AppUri>k__BackingField
0x233e  ret
```
