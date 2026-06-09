# NlpChainSetClientAttributes(ushort *,ushort *,ushort *,_NETLOGON_AUTHENTICATOR *,_NETLOGON_AUTHENTICATOR *,ulong,__MIDL_logon_0001 *,ulong *,__MIDL_logon_0002 *)

- ea: `0x18002e03c`
- end: `0x18002e5f5`
- name: `?NlpChainSetClientAttributes@@YAJPEAG00PEAU_NETLOGON_AUTHENTICATOR@@1KPEAT__MIDL_logon_0001@@PEAKPEAT__MIDL_logon_0002@@@Z`
- size: `1465`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, unsigned __int16 *@<rdx>, unsigned __int16 *@<r8>, struct _NETLOGON_AUTHENTICATOR *@<r9>, struct _NETLOGON_AUTHENTICATOR *, unsigned int, union __MIDL_logon_0001 *, unsigned int *, union __MIDL_logon_0002 *)`
- caller_count: `2`
- callee_count: `16`
- tags: `loader_planting, installer_update`

## callers

- `0x180034510`
- `0x180034590`

## callees

- `0x180007518`
- `0x18000dd00`
- `0x18000e910`
- `0x18000f3e4`
- `0x1800110ac`
- `0x1800267ec`
- `0x1800271d4`
- `0x1800276ac`
- `0x18002e03c`
- `0x180040928`
- `0x1800409c4`
- `0x180057174`
- `0x18005cdb4`
- `0x1800639bc`
- `0x18008a5c0`
- `0x180090204`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002e5a6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002e5a6`
- `LSASRV!LsaIVerifyCachability` at `0x18002e25e`
- `LSASRV!LsaIVerifyCachability` at `0x18002e25e`
- `LSASRV!LsaISetClientDnsHostName` at `0x18002e47b`
- `LSASRV!LsaISetClientDnsHostName` at `0x18002e47b`
- `ntdll!RtlLeaveCriticalSection` at `0x18002e183`
- `ntdll!RtlLeaveCriticalSection` at `0x18002e1f5`
- `ntdll!RtlLeaveCriticalSection` at `0x18002e231`
- `ntdll!RtlLeaveCriticalSection` at `0x18002e52c`
- `ntdll!RtlLeaveCriticalSection` at `0x18002e183`
- `ntdll!RtlLeaveCriticalSection` at `0x18002e1f5`
- `ntdll!RtlLeaveCriticalSection` at `0x18002e231`
- `ntdll!RtlLeaveCriticalSection` at `0x18002e52c`
- `ntdll!RtlEnterCriticalSection` at `0x18002e161`
- `ntdll!RtlEnterCriticalSection` at `0x18002e161`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!DNSHostNameValueCheckForNetlogon` at `0x18002e438`
- `ext-ms-win-ntdsa-activedirectoryserver-l1-1-0!DNSHostNameValueCheckForNetlogon` at `0x18002e438`

## string_xrefs

- `0x18002e407`: `onecore\ds\netapi\svcdlls\logonsrv\server\logonapi.cxx`
- `0x18002e538`: `NetrChainSetClientAttributes: only valid to a Writable DC from a read only server (RODC/ROGC).\n`
- `0x18002e41f`: `NetrChainSetClientAttributes: DNSHostNameValueCheck extension not present\n`
- `0x18002e48d`: `NetrChainSetClientAttributes: couldn't update object, status 0x%lx\n`

## pseudocode

```c

```
