# NetworkIsolationSetAppContainerConfig

- ea: `0x180058570`
- end: `0x18005869e`
- name: `NetworkIsolationSetAppContainerConfig`
- size: `302`
- prototype: `DWORD __stdcall(DWORD dwNumPublicAppCs, PSID_AND_ATTRIBUTES appContainerSids)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180005e0c`
- `0x18000ea10`
- `0x180026798`
- `0x1800294b0`
- `0x180058570`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180058605`
- `RPCRT4!NdrClientCall3` at `0x180058605`
- `RPCRT4!RpcBindingFree` at `0x180058667`
- `RPCRT4!RpcBindingFree` at `0x180058667`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005859c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005859c`

## pseudocode

```c

```
