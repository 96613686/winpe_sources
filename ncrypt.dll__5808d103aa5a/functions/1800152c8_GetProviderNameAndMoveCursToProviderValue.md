# _GetProviderNameAndMoveCursToProviderValue

- ea: `0x1800152c8`
- end: `0x1800153f4`
- name: `_GetProviderNameAndMoveCursToProviderValue`
- size: `300`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180009ecc`

## callees

- `0x18000d02c`
- `0x18000e120`
- `0x1800152c8`

## string_xrefs

- `0x180015359`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\descriptor.c`
- `0x1800153cc`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\descriptor.c`

## pseudocode

```c
__int64 __fastcall GetProviderNameAndMoveCursToProviderValue(_WORD **a1, _QWORD *a2)
{
  _WORD *i; // r8
  unsigned int v5; // ebx
  _WORD *v6; // rdx
  __int16 v7; // cx

  for ( i = *a1; *i == 32; ++i )
    ;
  v5 = 0;
  if ( *i )
  {
    v6 = i;
    while ( 1 )
    {
      v7 = *i;
      if ( *i == 61 || v7 == 32 )
      {
        *i++ = 0;
        if ( v7 == 32 )
        {
          while ( *i == 32 )
            ++i;
          if ( *i != 61 )
          {
            v5 = -2146893819;
            DebugTraceError(
              2148073477LL,
              "hr",
              "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\descriptor.c",
              580);
            return v5;
          }
          ++i;
        }
LABEL_11:
        *a1 = i;
        *a2 = v6;
        return v5;
      }
      if ( !v7 )
        goto LABEL_11;
      if ( v7 == 34 )
        break;
      ++i;
    }
    v5 = -2146893819;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)v6,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\descriptor.c",
        (unsigned int)"hr",
        5,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\descriptor.c",
        39);
  }
  else
  {
    v5 = -2146893819;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\descriptor.c",
        (unsigned int)"hr",
        5,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\descriptor.c",
        22);
  }
  return v5;
}

```

## disassembly

```asm
0x1800152c8  push    rbx
0x1800152ca  sub     rsp, 40h
0x1800152ce  mov     r8, [rcx]
0x1800152d1  mov     r10, rdx
0x1800152d4  mov     r9, rcx
0x1800152d7  mov     r11w, 20h ; ' '
0x1800152dc  movzx   eax, word ptr [r8]
0x1800152e0  cmp     ax, r11w
0x1800152e4  jz      loc_1800153A9
0x1800152ea  xor     ebx, ebx
0x1800152ec  test    ax, ax
0x1800152ef  jz      short loc_18001532F
0x1800152f1  mov     rdx, r8
0x1800152f4  movzx   ecx, word ptr [r8]
0x1800152f8  cmp     cx, 3Dh ; '='
0x1800152fc  jz      short loc_180015315
0x1800152fe  cmp     cx, r11w
0x180015302  jz      short loc_180015315
0x180015304  test    cx, cx
0x180015307  jz      short loc_180015327
0x180015309  cmp     cx, 22h ; '"'
0x18001530d  jz      short loc_180015381
0x18001530f  add     r8, 2
0x180015313  jmp     short loc_1800152F4
0x180015315  mov     [r8], bx
0x180015319  add     r8, 2
0x18001531d  cmp     cx, r11w
0x180015321  jz      loc_1800153B6
0x180015327  mov     [r9], r8
0x18001532a  mov     [r10], rdx
0x18001532d  jmp     short loc_180015379
0x18001532f  mov     ebx, 80090005h
0x180015334  mov     rcx, cs:WPP_GLOBAL_Control
0x18001533b  lea     rax, WPP_GLOBAL_Control
0x180015342  cmp     rcx, rax
0x180015345  jz      short loc_180015379
0x180015347  test    byte ptr [rcx+1Ch], 1
0x18001534b  jz      short loc_180015379
0x18001534d  mov     [rsp+48h+var_18], 216h
0x180015355  mov     rcx, [rcx+10h]
0x180015359  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180015360  mov     [rsp+48h+var_20], r8
0x180015365  lea     r9, aHr; "hr"
0x18001536c  mov     [rsp+48h+var_28], 80090005h
0x180015374  call    WPP_SF_sDsd
0x180015379  mov     eax, ebx
0x18001537b  add     rsp, 40h
0x18001537f  pop     rbx
0x180015380  retn
0x180015381  mov     ebx, 80090005h
0x180015386  mov     rcx, cs:WPP_GLOBAL_Control
0x18001538d  lea     rax, WPP_GLOBAL_Control
0x180015394  cmp     rcx, rax
0x180015397  jz      short loc_180015379
0x180015399  test    byte ptr [rcx+1Ch], 1
0x18001539d  jz      short loc_180015379
0x18001539f  mov     [rsp+48h+var_18], 227h
0x1800153a7  jmp     short loc_180015355
0x1800153a9  add     r8, 2
0x1800153ad  jmp     loc_1800152DC
0x1800153b2  add     r8, 2
0x1800153b6  movzx   eax, word ptr [r8]
0x1800153ba  cmp     ax, r11w
0x1800153be  jz      short loc_1800153B2
0x1800153c0  cmp     ax, 3Dh ; '='
0x1800153c4  jz      short loc_1800153EB
0x1800153c6  mov     r9d, 244h
0x1800153cc  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800153d3  lea     rdx, aHr; "hr"
0x1800153da  mov     ecx, 80090005h
0x1800153df  mov     ebx, 80090005h
0x1800153e4  call    DebugTraceError
0x1800153e9  jmp     short loc_180015379
0x1800153eb  add     r8, 2
0x1800153ef  jmp     loc_180015327
```
