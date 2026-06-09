# CSessionMgr::BeginAccept(void)

- ea: `0x18005b8dc`
- end: `0x18005b98c`
- name: `?BeginAccept@CSessionMgr@@QEAAXXZ`
- size: `176`
- prototype: `void __fastcall(CSessionMgr *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800381dc`

## callees

- `0x1800346dc`
- `0x18005b8dc`
- `0x18005c85c`

## import_xrefs

- `WSOCK32!__imp_htons` at `0x18005b96a`
- `WSOCK32!__imp_htons` at `0x18005b96a`
- `mqsec!GetFalconKeyValue` at `0x18005b918`
- `mqsec!GetFalconKeyValue` at `0x18005b95d`
- `mqsec!GetFalconKeyValue` at `0x18005b918`
- `mqsec!GetFalconKeyValue` at `0x18005b95d`

## string_xrefs

- `0x18005b911`: `security\EnablePingService`

## pseudocode

```c

```
