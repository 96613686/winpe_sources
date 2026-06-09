# Microsoft.Xrm.Async.Bridges.FromCommonAuth.ApplicationInfo::.ctor_0

- ea: `0x2340`
- end: `0x2368`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonAuth.ApplicationInfo::.ctor_0`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x22f0`
- `0x25f0`

## string_xrefs

- `0x2358`: `AppUri`

## pseudocode

```c

```

## disassembly

```asm
0x2340  ldarg.0
0x2341  ldarg.1
0x2342  ldstr    aClientid// "ClientId"
0x2347  callvirt instance string Microsoft.Xrm.Async.Bridges.FromCommonAuth.ConnectionString::get_Item(string key)
0x234c  ldarg.1
0x234d  ldstr    aAuthorityurl// "AuthorityUrl"
0x2352  callvirt instance string Microsoft.Xrm.Async.Bridges.FromCommonAuth.ConnectionString::get_Item(string key)
0x2357  ldarg.1
0x2358  ldstr    aAppuri// "AppUri"
0x235d  callvirt instance string Microsoft.Xrm.Async.Bridges.FromCommonAuth.ConnectionString::get_Item(string key)
0x2362  call     instance void Microsoft.Xrm.Async.Bridges.FromCommonAuth.ApplicationInfo::.ctor(string clientId, string authorityUrl, string appUri)
0x2367  ret
```
