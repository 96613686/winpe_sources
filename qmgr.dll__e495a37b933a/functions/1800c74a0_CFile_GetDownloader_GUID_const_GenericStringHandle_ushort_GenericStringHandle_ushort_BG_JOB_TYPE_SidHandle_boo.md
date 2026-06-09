# CFile::GetDownloader(_GUID const &,GenericStringHandle<ushort>,GenericStringHandle<ushort>,BG_JOB_TYPE,SidHandle,bool *,_GUID const &,TokenHandle const &,TokenHandle const &,ulong,BG_JOB_PRIORITY,ulong,GenericStringHandle<ushort>,PROXY_SETTINGS const *,CCredentialsContainer const *,ulong,CClientCertificate *,CCustomHeaders const *,ulong,bool,bool,bool,bool,bool,IServerCertificateValidator *)

- ea: `0x1800c74a0`
- end: `0x1800c8533`
- name: `?GetDownloader@CFile@@UEAAPEAVIAbstractTransfer@@AEBU_GUID@@V?$GenericStringHandle@G@@1W4BG_JOB_TYPE@@VSidHandle@@PEA_N0AEBVTokenHandle@@5KW4BG_JOB_PRIORITY@@K1PEBUPROXY_SETTINGS@@PEBVCCredentialsContainer@@KPEAVCClientCertificate@@PEBVCCustomHeaders@@K_N_N_N_N_NPEAUIServerCertificateValidator@@@Z`
- size: `4243`
- prototype: `__int64 __usercall@<rax>(CFile *this@<rcx>, char, __int64, __int64, __int64, struct _TP_CALLBACK_ENVIRON_V3 *, __int64, struct _TP_CALLBACK_ENVIRON_V3 *, enum BG_JOB_PRIORITY, int, __int64, __int64, __int64, int, __int64, __int64, int, char, char, char, char, char, __int64)`
- caller_count: `0`
- callee_count: `44`
- tags: `authz_impersonation, registry_config, loader_planting`

## callees

- `0x180006640`
- `0x180012b18`
- `0x1800132d4`
- `0x180014310`
- `0x180016d60`
- `0x18001d7f0`
- `0x18001fa0c`
- `0x18001fab8`
- `0x18001fe28`
- `0x180021430`
- `0x180033814`
- `0x180035084`
- `0x18003dcb0`
- `0x1800466a4`
- `0x18004f214`
- `0x18005e894`
- `0x180072350`
- `0x18007b58c`
- `0x18007df0c`
- `0x18007e194`
- `0x180084090`
- `0x180088d5c`
- `0x180088dd8`
- `0x18008db34`
- `0x18008ddc8`
- `0x18008df30`
- `0x1800956ec`
- `0x1800977a4`
- `0x18009c798`
- `0x18009d024`
- `0x1800a3420`
- `0x1800a3de8`
- `0x1800c6b38`
- `0x1800c719c`
- `0x1800c735c`
- `0x1800c74a0`
- `0x1800c9be0`
- `0x1800cab24`
- `0x1800dd394`
- `0x1800eace4`
- `0x1800eeba4`
- `0x1800f0500`
- `0x1800f9948`
- `0x18010f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800c76a5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800c76c0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800c76a5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800c76c0`
- `ntdll!RtlReportException` at `0x1800c825e`
- `ntdll!RtlReportException` at `0x1800c825e`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800c8173`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800c8173`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x1800c81e6`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x1800c81e6`

## pseudocode

```c

```
