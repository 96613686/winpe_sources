# KerbCreateDummyLogonSession(int,_LUID *,_KERB_LOGON_SESSION * *,_SECURITY_IMPERSONATION_LEVEL,uchar,void *)

- ea: `0x180048a28`
- end: `0x180048ce7`
- name: `?KerbCreateDummyLogonSession@@YAJHPEAU_LUID@@PEAPEAU_KERB_LOGON_SESSION@@W4_SECURITY_IMPERSONATION_LEVEL@@EPEAX@Z`
- size: `703`
- prototype: `int(int, struct _LUID *, struct _KERB_LOGON_SESSION **, enum _SECURITY_IMPERSONATION_LEVEL, unsigned __int8, void *)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18005d250`
- `0x1800a3ed0`

## callees

- `0x18000a630`
- `0x180048a28`
- `0x180048cf0`
- `0x180054508`
- `0x18008b70c`
- `0x18009e288`
- `0x1800f5010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180048abf`
- `ntdll!RtlInitUnicodeString` at `0x180048ad0`
- `ntdll!RtlInitUnicodeString` at `0x180048bae`
- `ntdll!RtlInitUnicodeString` at `0x180048bc6`
- `ntdll!RtlInitUnicodeString` at `0x180048abf`
- `ntdll!RtlInitUnicodeString` at `0x180048ad0`
- `ntdll!RtlInitUnicodeString` at `0x180048bae`
- `ntdll!RtlInitUnicodeString` at `0x180048bc6`
- `ntdll!RtlEnterCriticalSection` at `0x180048c08`
- `ntdll!RtlEnterCriticalSection` at `0x180048c08`
- `ntdll!RtlLeaveCriticalSection` at `0x180048c31`
- `ntdll!RtlLeaveCriticalSection` at `0x180048c31`
- `LSASRV!LsaIGetNameFromLuid` at `0x180048b47`
- `LSASRV!LsaIGetNameFromLuid` at `0x180048b6b`
- `LSASRV!LsaIGetNameFromLuid` at `0x180048b47`
- `LSASRV!LsaIGetNameFromLuid` at `0x180048b6b`

## string_xrefs

- `0x180048a7b`: `KerbCreateDummyLogonSession creating logon session for %#x:%#x\n`
- `0x180048a82`: `KerbCreateDummyLogonSession`
- `0x180048c5c`: `KerbCreateDummyLogonSession`
- `0x180048c50`: `KerbCreateDummyLogonSession created logon session for %#x:%#x - %p\n`

## pseudocode

```c

```
