# NlpChainSetClientAttributes(ushort *,ushort *,ushort *,_NETLOGON_AUTHENTICATOR *,_NETLOGON_AUTHENTICATOR *,ulong,__MIDL_logon_0001 *,ulong *,__MIDL_logon_0002 *)

- ea: `0x18002c5b4`
- end: `0x18002cb36`
- name: `?NlpChainSetClientAttributes@@YAJPEAG00PEAU_NETLOGON_AUTHENTICATOR@@1KPEAT__MIDL_logon_0001@@PEAKPEAT__MIDL_logon_0002@@@Z`
- size: `1410`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, unsigned __int16 *@<rdx>, unsigned __int16 *@<r8>, struct _NETLOGON_AUTHENTICATOR *@<r9>, struct _NETLOGON_AUTHENTICATOR *, unsigned int, union __MIDL_logon_0001 *, unsigned int *, union __MIDL_logon_0002 *)`
- caller_count: `2`
- callee_count: `16`
- tags: `loader_planting, installer_update`

## callers

- `0x1800326d0`
- `0x180032750`

## callees

- `0x180007278`
- `0x18000d710`
- `0x18000e270`
- `0x18000ed34`
- `0x1800109fc`
- `0x180025708`
- `0x18002601c`
- `0x18002647c`
- `0x18002c5b4`
- `0x18003e208`
- `0x18003e294`
- `0x18005378c`
- `0x180058e0c`
- `0x18005f524`
- `0x1800844d0`
- `0x180089ab4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002caee`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002caee`
- `LSASRV!LsaIVerifyCachability` at `0x18002c7be`
- `LSASRV!LsaIVerifyCachability` at `0x18002c7be`
- `LSASRV!LsaISetClientDnsHostName` at `0x18002c9cf`
- `LSASRV!LsaISetClientDnsHostName` at `0x18002c9cf`
- `ntdll!RtlLeaveCriticalSection` at `0x18002c6f5`
- `ntdll!RtlLeaveCriticalSection` at `0x18002c761`
- `ntdll!RtlLeaveCriticalSection` at `0x18002c797`
- `ntdll!RtlLeaveCriticalSection` at `0x18002ca7a`
- `ntdll!RtlLeaveCriticalSection` at `0x18002c6f5`
- `ntdll!RtlLeaveCriticalSection` at `0x18002c761`
- `ntdll!RtlLeaveCriticalSection` at `0x18002c797`
- `ntdll!RtlLeaveCriticalSection` at `0x18002ca7a`
- `ntdll!RtlEnterCriticalSection` at `0x18002c6d9`
- `ntdll!RtlEnterCriticalSection` at `0x18002c6d9`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!DNSHostNameValueCheckForNetlogon` at `0x18002c992`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!DNSHostNameValueCheckForNetlogon` at `0x18002c992`

## string_xrefs

- `0x18002c961`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x18002ca80`: `NetrChainSetClientAttributes: only valid to a Writable DC from a read only server (RODC/ROGC).\n`
- `0x18002c979`: `NetrChainSetClientAttributes: DNSHostNameValueCheck extension not present\n`
- `0x18002c9db`: `NetrChainSetClientAttributes: couldn't update object, status 0x%lx\n`

## pseudocode

```c

```
