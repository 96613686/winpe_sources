# appIsolation::IsolationEvents::FwMoneisNotifyRegistrations(int,unsigned __int64,_INET_FIREWALL_AC_CHANGE * const)

- ea: `0x1800c2350`
- end: `0x1800c25ac`
- name: `?FwMoneisNotifyRegistrations@IsolationEvents@appIsolation@@AEAAKH_KQEAU_INET_FIREWALL_AC_CHANGE@@@Z`
- size: `604`
- prototype: `unsigned int(appIsolation::IsolationEvents *__hidden this, int, unsigned __int64, struct _INET_FIREWALL_AC_CHANGE *const)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800c2860`

## callees

- `0x18000a710`
- `0x1800729c0`
- `0x1800c1fd0`
- `0x1800c2350`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x1800c2406`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800c2406`
- `fwbase!FwAlloc` at `0x1800c2436`
- `fwbase!FwAlloc` at `0x1800c2436`
- `fwbase!FwCriticalSectionEnter` at `0x1800c2390`
- `fwbase!FwCriticalSectionEnter` at `0x1800c2390`
- `fwbase!FwCriticalSectionLeave` at `0x1800c254c`
- `fwbase!FwCriticalSectionLeave` at `0x1800c255e`
- `fwbase!FwCriticalSectionLeave` at `0x1800c254c`
- `fwbase!FwCriticalSectionLeave` at `0x1800c255e`
- `FWPolicyIOMgr!FwAppContainerChangeFree` at `0x1800c2578`
- `FWPolicyIOMgr!FwAppContainerChangeFree` at `0x1800c2578`

## pseudocode

```c

```
