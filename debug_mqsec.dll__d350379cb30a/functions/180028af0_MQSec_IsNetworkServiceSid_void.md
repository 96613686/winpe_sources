# MQSec_IsNetworkServiceSid(void *)

- ea: `0x180028af0`
- end: `0x180028b01`
- name: `?MQSec_IsNetworkServiceSid@@YAHPEAX@Z`
- size: `17`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, service_task`

## import_xrefs

- `ADVAPI32!EqualSid` at `0x180028afa`

## pseudocode

```c
BOOL __fastcall MQSec_IsNetworkServiceSid(void *a1)
{
  return EqualSid(g_pNetworkServiceSid, a1);
}

```

## disassembly

```asm
0x180028af0  mov     rdx, rcx
0x180028af3  mov     rcx, cs:?g_pNetworkServiceSid@@3PEAXEA; void * g_pNetworkServiceSid
0x180028afa  jmp     cs:__imp_EqualSid
```
