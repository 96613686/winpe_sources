# NCryptMsgCreate

- ea: `0x180003a68`
- end: `0x180003cdd`
- name: `NCryptMsgCreate`
- size: `629`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180003460`

## callees

- `0x180003a68`
- `0x180004a70`
- `0x1800050d0`
- `0x18000d02c`
- `0x18001f175`
- `0x180020010`

## string_xrefs

- `0x180003b9f`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\ncryptcms.c`
- `0x180003beb`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\ncryptcms.c`
- `0x180003c3d`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\ncryptcms.c`
- `0x180003c7d`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\ncryptcms.c`
- `0x180003cc4`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\ncryptcms.c`

## pseudocode

```c
__int64 __fastcall NCryptMsgCreate(__int64 a1, __int64 a2, int a3, _DWORD *a4, __int64 a5, unsigned int a6, _QWORD *a7)
{
  _DWORD *v9; // rax
  int v10; // edx
  int v11; // r8d
  _DWORD *v12; // rdi
  int v13; // r8d
  int v14; // edx
  unsigned int inited; // ebx
  int v16; // r8d

  if ( a7 && a2 && *(_DWORD *)a2 == 24 )
  {
    v9 = (_DWORD *)(*(__int64 (__fastcall **)(__int64))(a2 + 8))(368);
    v12 = v9;
    if ( v9 )
    {
      memset_0(v9, 0, 0x170u);
      *v12 = 368;
      v12[1] = 1;
      v12[4] = 24;
      *((_QWORD *)v12 + 3) = *(_QWORD *)(a2 + 8);
      *((_QWORD *)v12 + 4) = *(_QWORD *)(a2 + 16);
      v12[2] = 0;
      *((_QWORD *)v12 + 8) = &off_180021000;
      if ( *((_QWORD *)v12 + 8) )
      {
        if ( a4 && *a4 == 64 )
        {
          inited = CMSG_InitEnveloped(v12, a4, a5, a6);
          if ( !inited )
          {
            *((_QWORD *)v12 + 27) = v12 + 56;
            *a7 = v12;
            return inited;
          }
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v14,
              v16,
              (unsigned int)"Status",
              inited,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\ncryptcms.c",
              176);
        }
        else
        {
          inited = -2146893785;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              (unsigned int)&off_180021000,
              v13,
              (unsigned int)"Status",
              39,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\ncryptcms.c",
              164);
        }
      }
      else
      {
        inited = -2146893783;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            (unsigned int)&off_180021000,
            v13,
            (unsigned int)"Status",
            41,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\ncryptcms.c",
            151);
      }
      I_CMsgFree(v12);
      return inited;
    }
    inited = -2146893810;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v10,
        v11,
        (unsigned int)"Status",
        14,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\ncryptcms.c",
        122);
  }
  else
  {
    inited = -2146893785;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        a3,
        (unsigned int)"Status",
        39,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\ncryptcms.c",
        109);
  }
  return inited;
}

```

## disassembly

```asm
0x180003a68  push    rbx
0x180003a6a  push    rsi
0x180003a6b  push    rdi
0x180003a6c  push    r14
0x180003a6e  sub     rsp, 48h
0x180003a72  mov     r14, [rsp+68h+arg_30]
0x180003a7a  mov     rsi, r9
0x180003a7d  mov     rbx, rdx
0x180003a80  test    r14, r14
0x180003a83  jz      loc_180003B79
0x180003a89  test    rdx, rdx
0x180003a8c  jz      loc_180003B79
0x180003a92  cmp     dword ptr [rdx], 18h
0x180003a95  jnz     loc_180003B79
0x180003a9b  mov     rax, [rdx+8]
0x180003a9f  mov     ecx, 170h
0x180003aa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003aa9  mov     rdi, rax
0x180003aac  test    rax, rax
0x180003aaf  jz      loc_180003C4F
0x180003ab5  xor     edx, edx; Val
0x180003ab7  mov     r8d, 170h; Size
0x180003abd  mov     rcx, rax; void *
0x180003ac0  call    memset_0
0x180003ac5  mov     dword ptr [rdi], 170h
0x180003acb  lea     rdx, off_180021000; "1.2.840.113549.1.7.3"
0x180003ad2  mov     dword ptr [rdi+4], 1
0x180003ad9  mov     dword ptr [rdi+10h], 18h
0x180003ae0  mov     rax, [rbx+8]
0x180003ae4  mov     [rdi+18h], rax
0x180003ae8  mov     rax, [rbx+10h]
0x180003aec  mov     [rdi+20h], rax
0x180003af0  xor     eax, eax
0x180003af2  mov     dword ptr [rdi+8], 0
0x180003af9  cmp     rax, 1
0x180003afd  jnb     short loc_180003B1A
0x180003aff  mov     rcx, rax
0x180003b02  shl     rcx, 5
0x180003b06  cmp     dword ptr [rcx+rdx+1Ch], 3
0x180003b0b  jz      short loc_180003B12
0x180003b0d  inc     rax
0x180003b10  jmp     short loc_180003AF9
0x180003b12  lea     rax, [rcx+rdx]
0x180003b16  mov     [rdi+40h], rax
0x180003b1a  cmp     qword ptr [rdi+40h], 0
0x180003b1f  jz      loc_180003C96
0x180003b25  test    rsi, rsi
0x180003b28  jz      loc_180003BC5
0x180003b2e  cmp     dword ptr [rsi], 40h ; '@'
0x180003b31  jnz     loc_180003BC5
0x180003b37  mov     r9d, [rsp+68h+arg_28]
0x180003b3f  mov     rdx, rsi
0x180003b42  mov     r8, [rsp+68h+arg_20]
0x180003b4a  mov     rcx, rdi
0x180003b4d  call    CMSG_InitEnveloped
0x180003b52  mov     ebx, eax
0x180003b54  test    eax, eax
0x180003b56  jnz     loc_180003C1C
0x180003b5c  lea     rax, [rdi+0E0h]
0x180003b63  mov     [rdi+0D8h], rax
0x180003b6a  mov     [r14], rdi
0x180003b6d  mov     eax, ebx
0x180003b6f  add     rsp, 48h
0x180003b73  pop     r14
0x180003b75  pop     rdi
0x180003b76  pop     rsi
0x180003b77  pop     rbx
0x180003b78  retn
0x180003b79  mov     ebx, 80090027h
0x180003b7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003b85  lea     rax, WPP_GLOBAL_Control
0x180003b8c  cmp     rcx, rax
0x180003b8f  jz      short loc_180003B6D
0x180003b91  test    byte ptr [rcx+1Ch], 1
0x180003b95  jz      short loc_180003B6D
0x180003b97  mov     [rsp+68h+var_38], 16Dh
0x180003b9f  lea     rax, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180003ba6  mov     [rsp+68h+var_40], rax
0x180003bab  mov     [rsp+68h+var_48], 80090027h
0x180003bb3  mov     rcx, [rcx+10h]
0x180003bb7  lea     r9, aStatus; "Status"
0x180003bbe  call    WPP_SF_sDsd
0x180003bc3  jmp     short loc_180003B6D
0x180003bc5  mov     ebx, 80090027h
0x180003bca  mov     rcx, cs:WPP_GLOBAL_Control
0x180003bd1  lea     rax, WPP_GLOBAL_Control
0x180003bd8  cmp     rcx, rax
0x180003bdb  jz      short loc_180003C0F
0x180003bdd  test    byte ptr [rcx+1Ch], 1
0x180003be1  jz      short loc_180003C0F
0x180003be3  mov     [rsp+68h+var_38], 1A4h
0x180003beb  lea     rax, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180003bf2  mov     [rsp+68h+var_40], rax
0x180003bf7  mov     [rsp+68h+var_48], 80090027h
0x180003bff  mov     rcx, [rcx+10h]
0x180003c03  lea     r9, aStatus; "Status"
0x180003c0a  call    WPP_SF_sDsd
0x180003c0f  mov     rcx, rdi
0x180003c12  call    I_CMsgFree
0x180003c17  jmp     loc_180003B6D
0x180003c1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180003c23  lea     rax, WPP_GLOBAL_Control
0x180003c2a  cmp     rcx, rax
0x180003c2d  jz      short loc_180003C0F
0x180003c2f  test    byte ptr [rcx+1Ch], 1
0x180003c33  jz      short loc_180003C0F
0x180003c35  mov     [rsp+68h+var_38], 1B0h
0x180003c3d  lea     rax, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180003c44  mov     [rsp+68h+var_40], rax
0x180003c49  mov     [rsp+68h+var_48], ebx
0x180003c4d  jmp     short loc_180003BFF
0x180003c4f  mov     ebx, 8009000Eh
0x180003c54  mov     rcx, cs:WPP_GLOBAL_Control
0x180003c5b  lea     rax, WPP_GLOBAL_Control
0x180003c62  cmp     rcx, rax
0x180003c65  jz      loc_180003B6D
0x180003c6b  test    byte ptr [rcx+1Ch], 1
0x180003c6f  jz      loc_180003B6D
0x180003c75  mov     [rsp+68h+var_38], 17Ah
0x180003c7d  lea     rax, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180003c84  mov     [rsp+68h+var_40], rax
0x180003c89  mov     [rsp+68h+var_48], 8009000Eh
0x180003c91  jmp     loc_180003BB3
0x180003c96  mov     ebx, 80090029h
0x180003c9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180003ca2  lea     rax, WPP_GLOBAL_Control
0x180003ca9  cmp     rcx, rax
0x180003cac  jz      loc_180003C0F
0x180003cb2  test    byte ptr [rcx+1Ch], 1
0x180003cb6  jz      loc_180003C0F
0x180003cbc  mov     [rsp+68h+var_38], 197h
0x180003cc4  lea     rax, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180003ccb  mov     [rsp+68h+var_40], rax
0x180003cd0  mov     [rsp+68h+var_48], 80090029h
0x180003cd8  jmp     loc_180003BFF
```
