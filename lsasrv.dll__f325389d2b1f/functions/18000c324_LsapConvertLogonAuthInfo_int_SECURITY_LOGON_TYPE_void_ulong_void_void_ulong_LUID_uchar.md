# LsapConvertLogonAuthInfo(int,_SECURITY_LOGON_TYPE,void *,ulong,void *,void * *,ulong *,_LUID *,uchar *)

- ea: `0x18000c324`
- end: `0x18000ce84`
- name: `?LsapConvertLogonAuthInfo@@YAJHW4_SECURITY_LOGON_TYPE@@PEAXK1PEAPEAXPEAKPEAU_LUID@@PEAE@Z`
- size: `2912`
- prototype: `__int64 __fastcall(int, enum _SECURITY_LOGON_TYPE, void *, unsigned int, void *, void **, unsigned int *, struct _LUID *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `22`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180028cb0`

## callees

- `0x180003214`
- `0x18000c300`
- `0x18000c324`
- `0x18000dd90`
- `0x18000f2b0`
- `0x180011278`
- `0x18005faf0`
- `0x18005ff14`
- `0x180060c8c`
- `0x180063c24`
- `0x180079d94`
- `0x18007a4f0`
- `0x18007cc54`
- `0x18007e61c`
- `0x180095d28`
- `0x1800ada18`
- `0x1800bd6e0`
- `0x1800c7e28`
- `0x1800cb8e0`
- `0x1800cd0c0`
- `0x180143620`
- `0x18014396c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c64c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c65c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c66c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ca7b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c64c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c65c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c66c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ca7b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000cd7a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000cd7a`
- `ntdll!RtlEqualUnicodeString` at `0x18000c5d2`
- `ntdll!RtlEqualUnicodeString` at `0x18000c5f7`
- `ntdll!RtlEqualUnicodeString` at `0x18000c5d2`
- `ntdll!RtlEqualUnicodeString` at `0x18000c5f7`
- `ntdll!RtlInitUnicodeString` at `0x18000c549`
- `ntdll!RtlInitUnicodeString` at `0x18000c88c`
- `ntdll!RtlInitUnicodeString` at `0x18000c549`
- `ntdll!RtlInitUnicodeString` at `0x18000c88c`
- `api-ms-win-security-credentials-l1-1-0!CredFree` at `0x18000cdfa`
- `api-ms-win-security-credentials-l1-1-0!CredFree` at `0x18000cdfa`
- `api-ms-win-security-credentials-l1-1-0!CredUnmarshalCredentialW` at `0x18000c7e8`
- `api-ms-win-security-credentials-l1-1-0!CredUnmarshalCredentialW` at `0x18000c7e8`
- `SspiCli!SspiValidateAuthIdentity` at `0x18000cc04`
- `SspiCli!SspiValidateAuthIdentity` at `0x18000cc04`
- `SspiCli!SspiFreeAuthIdentity` at `0x18000ce46`
- `SspiCli!SspiFreeAuthIdentity` at `0x18000ce46`

## pseudocode

```c

```
