# OSF_CCALL::ActuallyProcessPDU(rpcconn_common *,uint,_RPC_MESSAGE *,int,int *)

- ea: `0x180057464`
- end: `0x1800578f5`
- name: `?ActuallyProcessPDU@OSF_CCALL@@AEAAJPEAUrpcconn_common@@IPEAU_RPC_MESSAGE@@HPEAH@Z`
- size: `1169`
- prototype: `__int64 __usercall@<rax>(OSF_CCALL *__hidden this@<rcx>, struct rpcconn_common *@<rdx>, unsigned int@<r8d>, struct _RPC_MESSAGE *@<r9>, int, int *)`
- caller_count: `3`
- callee_count: `19`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800548f8`
- `0x1800562bc`
- `0x1800615f0`

## callees

- `0x1800191d0`
- `0x180021ce0`
- `0x180021e70`
- `0x180025280`
- `0x18002b7c0`
- `0x180054d08`
- `0x1800568f0`
- `0x180057464`
- `0x180058b5c`
- `0x180058b8c`
- `0x180059700`
- `0x18005a81c`
- `0x180061ce0`
- `0x18009a780`
- `0x1800a27e4`
- `0x1800ac898`
- `0x1800ae764`
- `0x1800aeb50`
- `0x1800ca025`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180057591`
- `ntdll!RtlLeaveCriticalSection` at `0x1800575db`
- `ntdll!RtlLeaveCriticalSection` at `0x1800576d1`
- `ntdll!RtlLeaveCriticalSection` at `0x1800576e9`
- `ntdll!RtlLeaveCriticalSection` at `0x180057740`
- `ntdll!RtlLeaveCriticalSection` at `0x1800577c8`
- `ntdll!RtlLeaveCriticalSection` at `0x1800577f8`
- `ntdll!RtlLeaveCriticalSection` at `0x180057829`
- `ntdll!RtlLeaveCriticalSection` at `0x18005786e`
- `ntdll!RtlLeaveCriticalSection` at `0x180057591`
- `ntdll!RtlLeaveCriticalSection` at `0x1800575db`
- `ntdll!RtlLeaveCriticalSection` at `0x1800576d1`
- `ntdll!RtlLeaveCriticalSection` at `0x1800576e9`
- `ntdll!RtlLeaveCriticalSection` at `0x180057740`
- `ntdll!RtlLeaveCriticalSection` at `0x1800577c8`
- `ntdll!RtlLeaveCriticalSection` at `0x1800577f8`
- `ntdll!RtlLeaveCriticalSection` at `0x180057829`
- `ntdll!RtlLeaveCriticalSection` at `0x18005786e`
- `ntdll!RtlEnterCriticalSection` at `0x18005757f`
- `ntdll!RtlEnterCriticalSection` at `0x1800576a7`
- `ntdll!RtlEnterCriticalSection` at `0x180057793`
- `ntdll!RtlEnterCriticalSection` at `0x18005757f`
- `ntdll!RtlEnterCriticalSection` at `0x1800576a7`
- `ntdll!RtlEnterCriticalSection` at `0x180057793`

## pseudocode

```c

```
