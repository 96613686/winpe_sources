# MQSec_IsSystemSid(void *)

- ea: `0x180028b10`
- end: `0x180028b21`
- name: `?MQSec_IsSystemSid@@YAHPEAX@Z`
- size: `17`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, installer_update`

## import_xrefs

- `ADVAPI32!EqualSid` at `0x180028b1a`

## pseudocode

```c
BOOL __fastcall MQSec_IsSystemSid(void *a1)
{
  return EqualSid(g_pSystemSid, a1);
}

```

## disassembly

```asm
0x180028b10  mov     rdx, rcx
0x180028b13  mov     rcx, cs:?g_pSystemSid@@3PEAXEA; void * g_pSystemSid
0x180028b1a  jmp     cs:__imp_EqualSid
```
