# NCryptMsgEncode

- ea: `0x180001c08`
- end: `0x180001e71`
- name: `NCryptMsgEncode`
- size: `617`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180003150`

## callees

- `0x180001c08`
- `0x18000d02c`
- `0x18000e120`
- `0x180020010`

## import_xrefs

- `NTASN1!__imp_RtlAsn1EncodeAndAllocate` at `0x180001cb8`
- `NTASN1!__imp_RtlAsn1EncodeAndAllocate` at `0x180001d10`
- `NTASN1!__imp_RtlAsn1EncodeAndAllocate` at `0x180001cb8`
- `NTASN1!__imp_RtlAsn1EncodeAndAllocate` at `0x180001d10`

## string_xrefs

- `0x180001d73`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\ncryptcms.c`
- `0x180001dc2`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\ncryptcms.c`
- `0x180001e02`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\ncryptcms.c`
- `0x180001e4f`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\ncryptcms.c`

## pseudocode

```c
__int64 __fastcall NCryptMsgEncode(__int64 a1, _QWORD *a2, _DWORD *a3)
{
  __int64 v6; // rdx
  __int64 v7; // rax
  unsigned int v8; // ebx
  int v9; // r8d
  __int64 v10; // rcx
  _QWORD *v12; // rdx
  char v13; // [rsp+30h] [rbp-30h]
  __int128 v14; // [rsp+40h] [rbp-20h] BYREF
  __int128 v15; // [rsp+50h] [rbp-10h]
  __int64 v16; // [rsp+90h] [rbp+30h] BYREF
  __int64 v17; // [rsp+98h] [rbp+38h] BYREF

  v17 = 0;
  v16 = 0;
  v14 = 0;
  v15 = 0;
  if ( a2 && a3 )
  {
    *a2 = 0;
    *a3 = 0;
    if ( a1 && *(_DWORD *)a1 == 368 )
    {
      v6 = *(_QWORD *)(a1 + 64);
      if ( !v6 || (v7 = *(_QWORD *)(a1 + 216)) == 0 )
      {
        v8 = -2146893783;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return v8;
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (_DWORD)WPP_GLOBAL_Control,
          (_DWORD)a3,
          (unsigned int)"Status",
          41,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\ncryptcms.c",
          9);
        goto LABEL_10;
      }
      v8 = RtlAsn1EncodeAndAllocate(ASN1_NCRYPT_MODULE_HANDLE, *(unsigned int *)(v6 + 24), 0, a1 + 16, &v17, &v16, v7);
      if ( v8 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v13 = 24;
LABEL_20:
          WPP_SF_sDsd(
            v12[2],
            (_DWORD)v12,
            v9,
            (unsigned int)"Status",
            v8,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\ncryptcms.c",
            v13);
        }
      }
      else
      {
        v10 = *(_QWORD *)(a1 + 64);
        *((_QWORD *)&v14 + 1) = *(_QWORD *)(v10 + 16);
        LODWORD(v14) = *(_DWORD *)(v10 + 8);
        *((_QWORD *)&v15 + 1) = v17;
        LODWORD(v15) = v16;
        v8 = RtlAsn1EncodeAndAllocate(ASN1_NCRYPT_MODULE_HANDLE, 20, 0, a1 + 16, a2, &v16, &v14);
        if ( !v8 )
        {
          *a3 = v16;
          goto LABEL_10;
        }
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v13 = 44;
          goto LABEL_20;
        }
      }
    }
    else
    {
      v8 = -2146893786;
      DebugTraceError(
        2148073510LL,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\ncryptcms.c",
        512);
    }
  }
  else
  {
    v8 = -2146893785;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v8;
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)WPP_GLOBAL_Control,
      (_DWORD)a3,
      (unsigned int)"Status",
      39,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\ncryptcms.c",
      244);
  }
LABEL_10:
  if ( v17 )
    (*(void (**)(void))(a1 + 32))();
  return v8;
}

```

## disassembly

```asm
0x180001c08  mov     r11, rsp
0x180001c0b  mov     [r11+18h], rbx
0x180001c0f  push    rbp
0x180001c10  push    rsi
0x180001c11  push    rdi
0x180001c12  push    r14
0x180001c14  push    r15
0x180001c16  mov     rbp, rsp
0x180001c19  sub     rsp, 60h
0x180001c1d  mov     [rbp+arg_8], 0
0x180001c25  xorps   xmm0, xmm0
0x180001c28  mov     [rbp+arg_0], 0
0x180001c30  mov     rsi, r8
0x180001c33  mov     r14, rdx
0x180001c36  mov     rdi, rcx
0x180001c39  movups  [rbp+var_20], xmm0
0x180001c3d  movups  [rbp+var_10], xmm0
0x180001c41  test    rdx, rdx
0x180001c44  jz      loc_180001D4D
0x180001c4a  test    r8, r8
0x180001c4d  jz      loc_180001D4D
0x180001c53  mov     qword ptr [rdx], 0
0x180001c5a  mov     dword ptr [r8], 0
0x180001c61  test    rcx, rcx
0x180001c64  jz      loc_180001E49
0x180001c6a  cmp     dword ptr [rcx], 170h
0x180001c70  jnz     loc_180001E49
0x180001c76  mov     rdx, [rcx+40h]
0x180001c7a  test    rdx, rdx
0x180001c7d  jz      loc_180001DD4
0x180001c83  mov     rax, [rcx+0D8h]
0x180001c8a  test    rax, rax
0x180001c8d  jz      loc_180001DD4
0x180001c93  mov     edx, [rdx+18h]
0x180001c96  lea     r9, [rcx+10h]
0x180001c9a  mov     rcx, cs:ASN1_NCRYPT_MODULE_HANDLE
0x180001ca1  xor     r8d, r8d
0x180001ca4  mov     [r11-58h], rax
0x180001ca8  lea     rax, [rbp+arg_0]
0x180001cac  mov     [r11-60h], rax
0x180001cb0  lea     rax, [rbp+arg_8]
0x180001cb4  mov     [r11-68h], rax
0x180001cb8  call    cs:__imp_RtlAsn1EncodeAndAllocate
0x180001cbe  mov     ebx, eax
0x180001cc0  test    eax, eax
0x180001cc2  jnz     loc_180001D99
0x180001cc8  mov     rcx, [rdi+40h]
0x180001ccc  lea     r9, [rdi+10h]
0x180001cd0  xor     r8d, r8d
0x180001cd3  lea     edx, [rbx+14h]
0x180001cd6  mov     rax, [rcx+10h]
0x180001cda  mov     qword ptr [rbp+var_20+8], rax
0x180001cde  mov     eax, [rcx+8]
0x180001ce1  mov     rcx, cs:ASN1_NCRYPT_MODULE_HANDLE
0x180001ce8  mov     dword ptr [rbp+var_20], eax
0x180001ceb  mov     rax, [rbp+arg_8]
0x180001cef  mov     qword ptr [rbp+var_10+8], rax
0x180001cf3  mov     eax, dword ptr [rbp+arg_0]
0x180001cf6  mov     dword ptr [rbp+var_10], eax
0x180001cf9  lea     rax, [rbp+var_20]
0x180001cfd  mov     qword ptr [rsp+60h+var_30], rax
0x180001d02  lea     rax, [rbp+arg_0]
0x180001d06  mov     [rsp+60h+var_38], rax
0x180001d0b  mov     [rsp+60h+var_40], r14
0x180001d10  call    cs:__imp_RtlAsn1EncodeAndAllocate
0x180001d16  mov     ebx, eax
0x180001d18  test    eax, eax
0x180001d1a  jnz     loc_180001E1B
0x180001d20  mov     eax, dword ptr [rbp+arg_0]
0x180001d23  mov     [rsi], eax
0x180001d25  mov     rcx, [rbp+arg_8]
0x180001d29  test    rcx, rcx
0x180001d2c  jz      short loc_180001D37
0x180001d2e  mov     rax, [rdi+20h]
0x180001d32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d37  mov     eax, ebx
0x180001d39  mov     rbx, [rsp+60h+arg_10]
0x180001d41  add     rsp, 60h
0x180001d45  pop     r15
0x180001d47  pop     r14
0x180001d49  pop     rdi
0x180001d4a  pop     rsi
0x180001d4b  pop     rbp
0x180001d4c  retn
0x180001d4d  mov     ebx, 80090027h
0x180001d52  mov     rdx, cs:WPP_GLOBAL_Control
0x180001d59  lea     rcx, WPP_GLOBAL_Control
0x180001d60  cmp     rdx, rcx
0x180001d63  jz      short loc_180001D37
0x180001d65  test    byte ptr [rdx+1Ch], 1
0x180001d69  jz      short loc_180001D37
0x180001d6b  mov     dword ptr [rsp+60h+var_30], 1F4h
0x180001d73  lea     rax, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180001d7a  mov     [rsp+60h+var_38], rax
0x180001d7f  mov     dword ptr [rsp+60h+var_40], 80090027h
0x180001d87  mov     rcx, [rdx+10h]
0x180001d8b  lea     r9, aStatus; "Status"
0x180001d92  call    WPP_SF_sDsd
0x180001d97  jmp     short loc_180001D25
0x180001d99  mov     rdx, cs:WPP_GLOBAL_Control
0x180001da0  lea     rcx, WPP_GLOBAL_Control
0x180001da7  cmp     rdx, rcx
0x180001daa  jz      loc_180001D25
0x180001db0  test    byte ptr [rdx+1Ch], 1
0x180001db4  jz      loc_180001D25
0x180001dba  mov     dword ptr [rsp+60h+var_30], 218h
0x180001dc2  lea     rax, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180001dc9  mov     [rsp+60h+var_38], rax
0x180001dce  mov     dword ptr [rsp+60h+var_40], ebx
0x180001dd2  jmp     short loc_180001D87
0x180001dd4  mov     ebx, 80090029h
0x180001dd9  mov     rdx, cs:WPP_GLOBAL_Control
0x180001de0  lea     rcx, WPP_GLOBAL_Control
0x180001de7  cmp     rdx, rcx
0x180001dea  jz      loc_180001D37
0x180001df0  test    byte ptr [rdx+1Ch], 1
0x180001df4  jz      loc_180001D37
0x180001dfa  mov     dword ptr [rsp+60h+var_30], 209h
0x180001e02  lea     rax, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180001e09  mov     [rsp+60h+var_38], rax
0x180001e0e  mov     dword ptr [rsp+60h+var_40], 80090029h
0x180001e16  jmp     loc_180001D87
0x180001e1b  mov     rdx, cs:WPP_GLOBAL_Control
0x180001e22  lea     rcx, WPP_GLOBAL_Control
0x180001e29  cmp     rdx, rcx
0x180001e2c  jz      loc_180001D25
0x180001e32  test    byte ptr [rdx+1Ch], 1
0x180001e36  jz      loc_180001D25
0x180001e3c  mov     dword ptr [rsp+60h+var_30], 22Ch
0x180001e44  jmp     loc_180001DC2
0x180001e49  mov     r9d, 200h
0x180001e4f  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180001e56  lea     rdx, aStatus; "Status"
0x180001e5d  mov     ecx, 80090026h
0x180001e62  mov     ebx, 80090026h
0x180001e67  call    DebugTraceError
0x180001e6c  jmp     loc_180001D25
```
