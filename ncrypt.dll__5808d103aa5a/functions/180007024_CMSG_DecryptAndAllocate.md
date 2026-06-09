# CMSG_DecryptAndAllocate

- ea: `0x180007024`
- end: `0x180007090`
- name: `CMSG_DecryptAndAllocate`
- size: `108`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180007420`

## callees

- `0x180006c9c`
- `0x180007024`
- `0x18000d02c`

## string_xrefs

- `0x180007060`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\cmsg.c`

## pseudocode

```c
__int64 __fastcall CMSG_DecryptAndAllocate(__int64 a1, UCHAR *a2, ULONG a3, UCHAR **a4, ULONG *a5)
{
  int v5; // edx
  unsigned int v6; // ebx
  int v7; // r8d

  v6 = CNG_DecryptAndAllocate(a1 + 88, a2, a3, a4, a5);
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v5,
        v7,
        (unsigned int)"Status",
        v6,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\cmsg.c",
        63);
  }
  else
  {
    return 0;
  }
  return v6;
}

```

## disassembly

```asm
0x180007024  push    rbx
0x180007026  sub     rsp, 40h
0x18000702a  mov     rax, [rsp+48h+arg_20]
0x18000702f  add     rcx, 58h ; 'X'
0x180007033  mov     [rsp+48h+var_28], rax
0x180007038  call    CNG_DecryptAndAllocate
0x18000703d  mov     ebx, eax
0x18000703f  test    eax, eax
0x180007041  jz      short loc_18000708C
0x180007043  mov     rcx, cs:WPP_GLOBAL_Control
0x18000704a  lea     rax, WPP_GLOBAL_Control
0x180007051  cmp     rcx, rax
0x180007054  jz      short loc_180007084
0x180007056  test    byte ptr [rcx+1Ch], 1
0x18000705a  jz      short loc_180007084
0x18000705c  mov     rcx, [rcx+10h]
0x180007060  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007067  mov     [rsp+48h+var_18], 23Fh
0x18000706f  lea     r9, aStatus; "Status"
0x180007076  mov     [rsp+48h+var_20], rax
0x18000707b  mov     dword ptr [rsp+48h+var_28], ebx
0x18000707f  call    WPP_SF_sDsd
0x180007084  mov     eax, ebx
0x180007086  add     rsp, 40h
0x18000708a  pop     rbx
0x18000708b  retn
0x18000708c  xor     ebx, ebx
0x18000708e  jmp     short loc_180007084
```
