# ReconnectCluster(_CLUSTER *,ulong,ulong,ulong,bool)

- ea: `0x18005ffe4`
- end: `0x180060486`
- name: `?ReconnectCluster@@YAKPEAU_CLUSTER@@KKK_N@Z`
- size: `1186`
- prototype: `unsigned int __usercall@<eax>(struct _CLUSTER *@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, unsigned int@<r9d>, bool)`
- caller_count: `218`
- callee_count: `7`
- tags: ``

## callers

- `0x1800150c0`
- `0x180015280`
- `0x180015440`
- `0x18001562c`
- `0x180015824`
- `0x1800159ec`
- `0x180015bec`
- `0x180015dd4`
- `0x180015fb4`
- `0x1800161a8`
- `0x1800163a0`
- `0x180016588`
- `0x180016788`
- `0x180016978`
- `0x180016b6c`
- `0x180016d58`
- `0x180016f38`
- `0x180017128`
- `0x180017310`
- `0x180017528`
- `0x180017734`
- `0x18001794c`
- `0x180017b6c`
- `0x180017d84`
- `0x180017fc8`
- `0x1800181e8`
- `0x18002f130`
- `0x18002f4d0`
- `0x180047b84`
- `0x180047d70`
- `0x180047f54`
- `0x180048164`
- `0x180048378`
- `0x180048580`
- `0x180048798`
- `0x180048978`
- `0x180048bbc`
- `0x180048df8`
- `0x18004901c`
- `0x180049244`
- `0x180049464`
- `0x18004968c`
- `0x1800498ac`
- `0x180049ab4`
- `0x180049ca0`
- `0x180049e84`
- `0x18004a070`
- `0x18004a250`
- `0x18004a468`
- `0x18004a678`

## callees

- `0x180002f50`
- `0x18001cc2c`
- `0x180029578`
- `0x18005f8d8`
- `0x18005f9a0`
- `0x18005ffe4`
- `0x18006f910`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800601aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800603a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800601aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800603a3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006016c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006016c`

## string_xrefs

- `0x1800600a1`: `LPC Cluster call on cluster handle %p failed with cluster_error %d and the node may temporarily be in an invalid state`
- `0x180060309`: `At least one candidate was up but not ready. Trying reconnect again.`

## pseudocode

```c

```
