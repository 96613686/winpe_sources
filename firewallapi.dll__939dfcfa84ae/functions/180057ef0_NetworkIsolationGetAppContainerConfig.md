# NetworkIsolationGetAppContainerConfig

- ea: `0x180057ef0`
- end: `0x18005809e`
- name: `NetworkIsolationGetAppContainerConfig`
- size: `430`
- prototype: `DWORD __stdcall(DWORD *pdwNumPublicAppCs, PSID_AND_ATTRIBUTES *appContainerSids)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180005e0c`
- `0x18000ea10`
- `0x180026798`
- `0x1800294b0`
- `0x180057ef0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180058004`
- `RPCRT4!NdrClientCall3` at `0x180058004`
- `RPCRT4!RpcBindingFree` at `0x180058066`
- `RPCRT4!RpcBindingFree` at `0x180058066`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180057f1e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180057f1e`

## pseudocode

```c

```
