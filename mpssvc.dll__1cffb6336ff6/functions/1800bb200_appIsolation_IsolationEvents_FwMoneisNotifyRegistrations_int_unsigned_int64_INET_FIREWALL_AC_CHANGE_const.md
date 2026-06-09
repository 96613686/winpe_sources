# appIsolation::IsolationEvents::FwMoneisNotifyRegistrations(int,unsigned __int64,_INET_FIREWALL_AC_CHANGE * const)

- ea: `0x1800bb200`
- end: `0x1800bb439`
- name: `?FwMoneisNotifyRegistrations@IsolationEvents@appIsolation@@AEAAKH_KQEAU_INET_FIREWALL_AC_CHANGE@@@Z`
- size: `569`
- prototype: `unsigned int(appIsolation::IsolationEvents *__hidden this, int, unsigned __int64, struct _INET_FIREWALL_AC_CHANGE *const)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800bb620`

## callees

- `0x18000af3c`
- `0x18006f520`
- `0x1800baea0`
- `0x1800bb200`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x1800bb2b6`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800bb2b6`
- `fwbase!FwAlloc` at `0x1800bb2e0`
- `fwbase!FwAlloc` at `0x1800bb2e0`
- `fwbase!FwCriticalSectionEnter` at `0x1800bb240`
- `fwbase!FwCriticalSectionEnter` at `0x1800bb240`
- `fwbase!FwCriticalSectionLeave` at `0x1800bb3ec`
- `fwbase!FwCriticalSectionLeave` at `0x1800bb3f8`
- `fwbase!FwCriticalSectionLeave` at `0x1800bb3ec`
- `fwbase!FwCriticalSectionLeave` at `0x1800bb3f8`
- `FWPolicyIOMgr!FwAppContainerChangeFree` at `0x1800bb40c`
- `FWPolicyIOMgr!FwAppContainerChangeFree` at `0x1800bb40c`

## pseudocode

```c

```
