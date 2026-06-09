# cdp::ConnectionUpgrader::HandleUpgradeRequest(cdp::BigEndianStreamReader &)

- ea: `0x18010b66c`
- end: `0x18010c821`
- name: `?HandleUpgradeRequest@ConnectionUpgrader@cdp@@AEAAXAEAVBigEndianStreamReader@2@@Z`
- size: `4533`
- prototype: `void __fastcall(cdp::ConnectionUpgrader *__hidden this, struct cdp::BigEndianStreamReader *)`
- caller_count: `1`
- callee_count: `68`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1802ab770`

## callees

- `0x180003c74`
- `0x18000d02c`
- `0x180010ee0`
- `0x1800110f8`
- `0x180013da0`
- `0x18001e740`
- `0x180030190`
- `0x180035df8`
- `0x18003a060`
- `0x18003d0e0`
- `0x18004e170`
- `0x18008539c`
- `0x180088fa0`
- `0x18008a6fc`
- `0x18008ab6c`
- `0x18008acc0`
- `0x18008dbc0`
- `0x1800d9040`
- `0x1800f4d54`
- `0x1800fd440`
- `0x18010a1cc`
- `0x18010a704`
- `0x18010a834`
- `0x18010a864`
- `0x18010a88c`
- `0x18010a8b0`
- `0x18010a8d8`
- `0x18010a90c`
- `0x18010a950`
- `0x18010a96c`
- `0x18010b2e0`
- `0x18010b580`
- `0x18010b66c`
- `0x18010d558`
- `0x18010d598`
- `0x18010d5d0`
- `0x18010d608`
- `0x18010d640`
- `0x18010dd48`
- `0x180110034`
- `0x180110094`
- `0x180110954`
- `0x180112288`
- `0x1801125a0`
- `0x180112fb4`
- `0x18011ac6c`
- `0x180135544`
- `0x180187acc`
- `0x1801cc670`
- `0x1801f6fb0`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18010c7ee`
- `msvcp_win!_Mtx_unlock` at `0x18010c7ee`
- `IPHLPAPI!ConvertInterfaceIndexToLuid` at `0x18010c279`
- `IPHLPAPI!ConvertInterfaceIndexToLuid` at `0x18010c279`
- `IPHLPAPI!GetBestInterface` at `0x18010c25b`
- `IPHLPAPI!GetBestInterface` at `0x18010c25b`
- `WS2_32!__imp_inet_addr` at `0x18010c24e`
- `WS2_32!__imp_inet_addr` at `0x18010c24e`

## string_xrefs

- `0x18010bf82`: `Host side session=0x%016llx upgradeId=%s candidate endpointType=%s was unavailable, discarding.`
- `0x18010c1e6`: `{"text":"HandleUpgradeRequest Attempting firewall configuration for Tcp transport on Public network"}`

## pseudocode

```c

```
