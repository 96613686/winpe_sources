# MQSec_IsAnonymusSid(void *)

- ea: `0x180028a70`
- end: `0x180028a9b`
- name: `?MQSec_IsAnonymusSid@@YAHPEAX@Z`
- size: `43`
- prototype: `__int64 __fastcall(PSID pSid2)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1800288c0`

## callees

- `0x180028a70`

## import_xrefs

- `ADVAPI32!EqualSid` at `0x180028a83`
- `ADVAPI32!EqualSid` at `0x180028a83`

## pseudocode

```c
_BOOL8 __fastcall MQSec_IsAnonymusSid(PSID pSid2)
{
  return g_pAnonymSid && EqualSid(g_pAnonymSid, pSid2);
}

```

## disassembly

```asm
0x180028a70  sub     rsp, 28h
0x180028a74  mov     rdx, rcx; pSid2
0x180028a77  mov     rcx, cs:?g_pAnonymSid@@3PEAXEA; pSid1
0x180028a7e  test    rcx, rcx
0x180028a81  jz      short loc_180028A94
0x180028a83  call    cs:__imp_EqualSid
0x180028a89  test    eax, eax
0x180028a8b  jz      short loc_180028A94
0x180028a8d  mov     eax, 1
0x180028a92  jmp     short loc_180028A96
0x180028a94  xor     eax, eax
0x180028a96  add     rsp, 28h
0x180028a9a  retn
```
