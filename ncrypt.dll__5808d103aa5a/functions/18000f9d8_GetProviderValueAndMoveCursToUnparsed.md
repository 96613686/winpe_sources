# _GetProviderValueAndMoveCursToUnparsed

- ea: `0x18000f9d8`
- end: `0x18000fb0e`
- name: `_GetProviderValueAndMoveCursToUnparsed`
- size: `310`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180009ecc`

## callees

- `0x18000d02c`
- `0x18000e120`
- `0x18000f9d8`

## string_xrefs

- `0x18000fa5d`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\descriptor.c`
- `0x18000faa6`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\descriptor.c`

## pseudocode

```c
__int64 __fastcall GetProviderValueAndMoveCursToUnparsed(unsigned __int16 **a1, unsigned __int16 **a2)
{
  unsigned __int16 *i; // rax
  int v4; // r8d
  unsigned __int16 *v5; // rdx
  unsigned __int16 *j; // rax
  unsigned int v7; // ebx

  for ( i = *a1; ; ++i )
  {
    v4 = *i;
    if ( (_WORD)v4 != 32 )
      break;
  }
  if ( (_WORD)v4 )
  {
    v5 = i + 1;
    if ( (_WORD)v4 != 34 )
      v5 = i;
    for ( j = v5; ; ++j )
    {
      if ( (_WORD)v4 == 34 )
      {
        if ( !*j )
        {
          v7 = -2146893819;
          DebugTraceError(
            2148073477LL,
            "hr",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\descriptor.c",
            654);
          return v7;
        }
        if ( *j == 34 )
        {
LABEL_13:
          v7 = 0;
          if ( *j )
            *j++ = 0;
          *a1 = j;
          *a2 = v5;
          return v7;
        }
      }
      else
      {
        if ( (*j & 0xFFDF) == 0 )
          goto LABEL_13;
        if ( *j == 34 )
        {
          v7 = -2146893819;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              (_DWORD)v5,
              v4,
              (unsigned int)"hr",
              5,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\descriptor.c",
              133);
          return v7;
        }
      }
    }
  }
  v7 = -2146893819;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)a2,
      v4,
      (unsigned int)"hr",
      5,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\descriptor.c",
      112);
  return v7;
}

```

## disassembly

```asm
0x18000f9d8  push    rbx
0x18000f9da  sub     rsp, 40h
0x18000f9de  mov     rax, [rcx]
0x18000f9e1  mov     r10, rdx
0x18000f9e4  mov     r9, rcx
0x18000f9e7  movzx   r8d, word ptr [rax]
0x18000f9eb  cmp     r8w, 20h ; ' '
0x18000f9f0  jz      loc_18000FAF8
0x18000f9f6  xor     r11d, r11d
0x18000f9f9  test    r8w, r8w
0x18000f9fd  jz      short loc_18000FA7C
0x18000f9ff  lea     rdx, [rax+2]
0x18000fa03  mov     bx, 22h ; '"'
0x18000fa07  cmp     r8w, bx
0x18000fa0b  cmovnz  rdx, rax
0x18000fa0f  mov     rax, rdx
0x18000fa12  cmp     r8w, bx
0x18000fa16  jz      short loc_18000FA31
0x18000fa18  mov     ecx, 0FFDFh
0x18000fa1d  test    [rax], cx
0x18000fa20  jz      short loc_18000FA3C
0x18000fa22  cmp     [rax], bx
0x18000fa25  jz      loc_18000FAC8
0x18000fa2b  add     rax, 2
0x18000fa2f  jmp     short loc_18000FA12
0x18000fa31  cmp     [rax], r11w
0x18000fa35  jz      short loc_18000FA57
0x18000fa37  cmp     [rax], bx
0x18000fa3a  jnz     short loc_18000FA2B
0x18000fa3c  mov     ebx, r11d
0x18000fa3f  cmp     [rax], r11w
0x18000fa43  jnz     loc_18000FB01
0x18000fa49  mov     [r9], rax
0x18000fa4c  mov     [r10], rdx
0x18000fa4f  mov     eax, ebx
0x18000fa51  add     rsp, 40h
0x18000fa55  pop     rbx
0x18000fa56  retn
0x18000fa57  mov     r9d, 28Eh
0x18000fa5d  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000fa64  lea     rdx, aHr; "hr"
0x18000fa6b  mov     ecx, 80090005h
0x18000fa70  mov     ebx, 80090005h
0x18000fa75  call    DebugTraceError
0x18000fa7a  jmp     short loc_18000FA4F
0x18000fa7c  mov     ebx, 80090005h
0x18000fa81  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fa88  lea     rax, WPP_GLOBAL_Control
0x18000fa8f  cmp     rcx, rax
0x18000fa92  jz      short loc_18000FA4F
0x18000fa94  test    byte ptr [rcx+1Ch], 1
0x18000fa98  jz      short loc_18000FA4F
0x18000fa9a  mov     [rsp+48h+var_18], 270h
0x18000faa2  mov     rcx, [rcx+10h]
0x18000faa6  lea     rax, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000faad  mov     [rsp+48h+var_20], rax
0x18000fab2  lea     r9, aHr; "hr"
0x18000fab9  mov     [rsp+48h+var_28], 80090005h
0x18000fac1  call    WPP_SF_sDsd
0x18000fac6  jmp     short loc_18000FA4F
0x18000fac8  mov     ebx, 80090005h
0x18000facd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fad4  lea     rax, WPP_GLOBAL_Control
0x18000fadb  cmp     rcx, rax
0x18000fade  jz      loc_18000FA4F
0x18000fae4  test    byte ptr [rcx+1Ch], 1
0x18000fae8  jz      loc_18000FA4F
0x18000faee  mov     [rsp+48h+var_18], 285h
0x18000faf6  jmp     short loc_18000FAA2
0x18000faf8  add     rax, 2
0x18000fafc  jmp     loc_18000F9E7
0x18000fb01  mov     [rax], r11w
0x18000fb05  add     rax, 2
0x18000fb09  jmp     loc_18000FA49
```
