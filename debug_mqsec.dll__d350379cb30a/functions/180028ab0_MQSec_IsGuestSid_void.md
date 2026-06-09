# MQSec_IsGuestSid(void *)

- ea: `0x180028ab0`
- end: `0x180028ae6`
- name: `?MQSec_IsGuestSid@@YAHPEAX@Z`
- size: `54`
- prototype: `__int64 __fastcall(PSID pSid2)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180025cd0`
- `0x1800288c0`
- `0x180028b30`

## callees

- `0x180020fe0`
- `0x180028ab0`

## import_xrefs

- `ADVAPI32!EqualSid` at `0x180028acd`
- `ADVAPI32!EqualSid` at `0x180028acd`

## pseudocode

```c
_BOOL8 __fastcall MQSec_IsGuestSid(PSID pSid2)
{
  InitializeGuestSid();
  return g_pGuestSid && EqualSid(g_pGuestSid, pSid2);
}

```

## disassembly

```asm
0x180028ab0  push    rbx
0x180028ab2  sub     rsp, 20h
0x180028ab6  mov     rbx, rcx
0x180028ab9  call    ?InitializeGuestSid@@YAXXZ; InitializeGuestSid(void)
0x180028abe  mov     rcx, cs:?g_pGuestSid@@3PEAXEA; pSid1
0x180028ac5  test    rcx, rcx
0x180028ac8  jz      short loc_180028ADE
0x180028aca  mov     rdx, rbx; pSid2
0x180028acd  call    cs:__imp_EqualSid
0x180028ad3  test    eax, eax
0x180028ad5  jz      short loc_180028ADE
0x180028ad7  mov     eax, 1
0x180028adc  jmp     short loc_180028AE0
0x180028ade  xor     eax, eax
0x180028ae0  add     rsp, 20h
0x180028ae4  pop     rbx
0x180028ae5  retn
```
