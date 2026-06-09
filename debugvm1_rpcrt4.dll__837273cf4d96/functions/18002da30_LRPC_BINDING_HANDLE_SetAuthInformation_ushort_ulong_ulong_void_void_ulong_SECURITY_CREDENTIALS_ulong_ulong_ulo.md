# LRPC_BINDING_HANDLE::SetAuthInformation(ushort *,ulong,ulong,void *,void *,ulong,SECURITY_CREDENTIALS *,ulong,ulong,ulong,ulong,ulong,void *,void *,int,int,void *)

- ea: `0x18002da30`
- end: `0x18002dc26`
- name: `?SetAuthInformation@LRPC_BINDING_HANDLE@@UEAAJPEAGKKPEAX1KPEAVSECURITY_CREDENTIALS@@KKKKK11HH1@Z`
- size: `502`
- prototype: `__int64 __fastcall(LRPC_BINDING_HANDLE *__hidden this, unsigned __int16 *, unsigned int, unsigned int, PSEC_WINNT_AUTH_IDENTITY_OPAQUE, void *, unsigned int, struct SECURITY_CREDENTIALS *, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, void *, PSID, int, int, PSECURITY_DESCRIPTOR)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18002da30`
- `0x18002e0f0`
- `0x18002f070`
- `0x18002f4f8`
- `0x180031760`
- `0x1800b758c`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18002daae`
- `ntdll!RtlLeaveCriticalSection` at `0x18002db89`
- `ntdll!RtlLeaveCriticalSection` at `0x18002daae`
- `ntdll!RtlLeaveCriticalSection` at `0x18002db89`
- `ntdll!RtlEnterCriticalSection` at `0x18002da7c`
- `ntdll!RtlEnterCriticalSection` at `0x18002da8f`
- `ntdll!RtlEnterCriticalSection` at `0x18002da7c`
- `ntdll!RtlEnterCriticalSection` at `0x18002da8f`

## pseudocode

```c

```
