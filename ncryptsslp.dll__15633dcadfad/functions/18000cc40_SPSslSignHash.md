# SPSslSignHash

- ea: `0x18000cc40`
- end: `0x18000cfa6`
- name: `SPSslSignHash`
- size: `870`
- prototype: `__int64 __fastcall(_DWORD *, __int64, BYTE *, DWORD, BYTE *pbSignature, DWORD cbSignature, DWORD *pcbResult, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000b594`
- `0x18000b654`
- `0x18000cc40`
- `0x180024ef0`
- `0x180025660`

## import_xrefs

- `ncrypt!NCryptSignHash` at `0x18000ce3e`
- `ncrypt!NCryptSignHash` at `0x18000ce3e`

## string_xrefs

- `0x18000cce2`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000ce98`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000cedf`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000cf26`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000cf6d`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000cf8c`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall SPSslSignHash(
        _DWORD *a1,
        __int64 a2,
        BYTE *a3,
        DWORD a4,
        BYTE *pbSignature,
        DWORD cbSignature,
        DWORD *pcbResult,
        int a8)
{
  unsigned int v11; // r14d
  int v13; // edx
  int v14; // r8d
  unsigned int v15; // ebx
  __int64 *p_pPaddingInfo; // r11
  DWORD dwFlags; // esi
  __int64 i; // rax
  __int64 v20; // r8
  BYTE v21; // r9
  SECURITY_STATUS v22; // eax
  __int64 v23; // [rsp+40h] [rbp-E8h] BYREF
  __int128 pPaddingInfo; // [rsp+48h] [rbp-E0h] BYREF
  _BYTE v25[128]; // [rsp+60h] [rbp-C8h] BYREF

  v23 = 0;
  v11 = 128;
  pPaddingInfo = 0;
  memset(v25, 0, sizeof(v25));
  if ( !a1 || *a1 < 0x310u || a1[1] != 1936944177 )
  {
    v15 = -2146893786;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v13,
        v14,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        100);
    return v15;
  }
  if ( !a2 || *(_DWORD *)a2 < 0x20u || *(_DWORD *)(a2 + 4) != 1936944180 )
  {
    v15 = -2146893786;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v13,
        v14,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        109);
    return v15;
  }
  if ( !pcbResult )
  {
    v15 = -2146893785;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v13,
        v14,
        (unsigned int)"Status",
        39,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        116);
    return v15;
  }
  if ( *(_DWORD *)(a2 + 8) != 196609 )
  {
    if ( (a8 & 3) != 0 )
    {
      v15 = -2146893785;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v13,
          v14,
          (unsigned int)"Status",
          39,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
          202);
      return v15;
    }
    dwFlags = 0;
    p_pPaddingInfo = 0;
LABEL_34:
    v22 = NCryptSignHash(*(_QWORD *)(a2 + 24), p_pPaddingInfo, a3, a4, pbSignature, cbSignature, pcbResult, dwFlags);
    v15 = v22;
    if ( v22 < 0 )
      DebugTraceError(
        (unsigned int)v22,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        5338);
    else
      return 0;
    return v15;
  }
  if ( (a8 & 0xFFFFFFFC) != 0 || (a8 & 2) != 0 && (a8 & 1) != 0 )
  {
    v15 = -2146893785;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v13,
        v14,
        (unsigned int)"Status",
        39,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        128);
    return v15;
  }
  p_pPaddingInfo = &v23;
  dwFlags = 8;
  if ( (a8 & 2) != 0 )
    p_pPaddingInfo = (__int64 *)&pPaddingInfo;
  else
    dwFlags = 2;
  if ( (a8 & 3) == 0 )
    goto LABEL_34;
  if ( a4 <= 0x80 )
    v11 = a4;
  for ( i = 0; ; i = (unsigned int)(i + 2) )
  {
    v20 = (unsigned int)(i + 1);
    if ( (unsigned int)v20 >= v11 )
      break;
    v13 = *a3;
    a4 -= 2;
    v21 = a3[1];
    a3 += 2;
    v25[i] = v13;
    v25[v20] = v21;
    if ( !(_BYTE)v13 && !v21 )
    {
      *p_pPaddingInfo = (__int64)v25;
      break;
    }
  }
  if ( *p_pPaddingInfo )
  {
    if ( (a8 & 2) != 0 )
      DWORD2(pPaddingInfo) = a4;
    goto LABEL_34;
  }
  v15 = -2146893785;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v13,
      v20,
      (unsigned int)"Status",
      39,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
      185);
  return v15;
}

```

## disassembly

```asm
0x18000cc40  push    rbx
0x18000cc42  push    rbp
0x18000cc43  push    rsi
0x18000cc44  push    rdi
0x18000cc45  push    r12
0x18000cc47  push    r14
0x18000cc49  push    r15
0x18000cc4b  sub     rsp, 0F0h
0x18000cc52  mov     rax, cs:__security_cookie
0x18000cc59  xor     rax, rsp
0x18000cc5c  mov     [rsp+128h+var_48], rax
0x18000cc64  mov     r12, [rsp+128h+arg_20]
0x18000cc6c  mov     rbx, r8
0x18000cc6f  mov     r15, [rsp+128h+arg_30]
0x18000cc77  mov     rdi, rdx
0x18000cc7a  mov     rsi, rcx
0x18000cc7d  mov     [rsp+128h+var_E8], 0
0x18000cc86  xorps   xmm0, xmm0
0x18000cc89  lea     rcx, [rsp+128h+var_C8]; void *
0x18000cc8e  mov     r14d, 80h
0x18000cc94  xor     edx, edx; Val
0x18000cc96  mov     r8d, r14d; Size
0x18000cc99  mov     ebp, r9d
0x18000cc9c  movups  [rsp+128h+pPaddingInfo], xmm0
0x18000cca1  call    memset
0x18000cca6  test    rsi, rsi
0x18000cca9  jz      short loc_18000CCBC
0x18000ccab  cmp     dword ptr [rsi], 310h
0x18000ccb1  jb      short loc_18000CCBC
0x18000ccb3  cmp     dword ptr [rsi+4], 73736C31h
0x18000ccba  jz      short loc_18000CD2A
0x18000ccbc  mov     ebx, 80090026h
0x18000ccc1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ccc8  lea     rax, WPP_GLOBAL_Control
0x18000cccf  cmp     rcx, rax
0x18000ccd2  jz      short loc_18000CD06
0x18000ccd4  test    byte ptr [rcx+1Ch], 1
0x18000ccd8  jz      short loc_18000CD06
0x18000ccda  mov     dword ptr [rsp+128h+pcbResult], 1464h
0x18000cce2  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000cce9  mov     qword ptr [rsp+128h+cbSignature], rax
0x18000ccee  mov     dword ptr [rsp+128h+pbSignature], 80090026h
0x18000ccf6  mov     rcx, [rcx+10h]
0x18000ccfa  lea     r9, aStatus; "Status"
0x18000cd01  call    WPP_SF_sDsd
0x18000cd06  mov     eax, ebx
0x18000cd08  mov     rcx, [rsp+128h+var_48]
0x18000cd10  xor     rcx, rsp; StackCookie
0x18000cd13  call    __security_check_cookie
0x18000cd18  add     rsp, 0F0h
0x18000cd1f  pop     r15
0x18000cd21  pop     r14
0x18000cd23  pop     r12
0x18000cd25  pop     rdi
0x18000cd26  pop     rsi
0x18000cd27  pop     rbp
0x18000cd28  pop     rbx
0x18000cd29  retn
0x18000cd2a  test    rdi, rdi
0x18000cd2d  jz      short loc_18000CD3D
0x18000cd2f  cmp     dword ptr [rdi], 20h ; ' '
0x18000cd32  jb      short loc_18000CD3D
0x18000cd34  cmp     dword ptr [rdi+4], 73736C34h
0x18000cd3b  jz      short loc_18000CD68
0x18000cd3d  mov     ebx, 80090026h
0x18000cd42  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cd49  lea     rax, WPP_GLOBAL_Control
0x18000cd50  cmp     rcx, rax
0x18000cd53  jz      short loc_18000CD06
0x18000cd55  test    byte ptr [rcx+1Ch], 1
0x18000cd59  jz      short loc_18000CD06
0x18000cd5b  mov     dword ptr [rsp+128h+pcbResult], 146Dh
0x18000cd63  jmp     loc_18000CCE2
0x18000cd68  test    r15, r15
0x18000cd6b  jz      loc_18000CEB1
0x18000cd71  cmp     dword ptr [rdi+8], 30001h
0x18000cd78  jnz     loc_18000CE55
0x18000cd7e  mov     eax, [rsp+128h+arg_38]
0x18000cd85  test    eax, 0FFFFFFFCh
0x18000cd8a  jnz     loc_18000CE6A
0x18000cd90  mov     r10d, eax
0x18000cd93  and     r10d, 2
0x18000cd97  jz      short loc_18000CDA1
0x18000cd99  test    al, 1
0x18000cd9b  jnz     loc_18000CE6A
0x18000cda1  test    r10d, r10d
0x18000cda4  lea     rcx, [rsp+128h+pPaddingInfo]
0x18000cda9  lea     r11, [rsp+128h+var_E8]
0x18000cdae  mov     esi, 8
0x18000cdb3  cmovnz  r11, rcx
0x18000cdb7  mov     ecx, 2
0x18000cdbc  cmovz   esi, ecx
0x18000cdbf  test    al, 3
0x18000cdc1  jz      short loc_18000CE18
0x18000cdc3  cmp     ebp, r14d
0x18000cdc6  cmovbe  r14d, ebp
0x18000cdca  xor     eax, eax
0x18000cdcc  nop     dword ptr [rax+00h]
0x18000cdd0  lea     r8d, [rax+1]
0x18000cdd4  cmp     r8d, r14d
0x18000cdd7  jnb     short loc_18000CE05
0x18000cdd9  movzx   edx, byte ptr [rbx]
0x18000cddc  add     ebp, 0FFFFFFFEh
0x18000cddf  movzx   r9d, byte ptr [rbx+1]
0x18000cde4  add     rbx, rcx
0x18000cde7  mov     [rsp+rax+128h+var_C8], dl
0x18000cdeb  mov     [rsp+r8+128h+var_C8], r9b
0x18000cdf0  test    dl, dl
0x18000cdf2  jz      short loc_18000CDF8
0x18000cdf4  add     eax, ecx
0x18000cdf6  jmp     short loc_18000CDD0
0x18000cdf8  test    r9b, r9b
0x18000cdfb  jnz     short loc_18000CDF4
0x18000cdfd  lea     rax, [rsp+128h+var_C8]
0x18000ce02  mov     [r11], rax
0x18000ce05  cmp     qword ptr [r11], 0
0x18000ce09  jz      loc_18000CF3F
0x18000ce0f  test    r10d, r10d
0x18000ce12  jz      short loc_18000CE18
0x18000ce14  mov     dword ptr [rsp+128h+pPaddingInfo+8], ebp
0x18000ce18  mov     eax, [rsp+128h+arg_28]
0x18000ce1f  mov     r9d, ebp; cbHashValue
0x18000ce22  mov     rcx, [rdi+18h]; hKey
0x18000ce26  mov     r8, rbx; pbHashValue
0x18000ce29  mov     [rsp+128h+dwFlags], esi; dwFlags
0x18000ce2d  mov     rdx, r11; pPaddingInfo
0x18000ce30  mov     [rsp+128h+pcbResult], r15; pcbResult
0x18000ce35  mov     [rsp+128h+cbSignature], eax; cbSignature
0x18000ce39  mov     [rsp+128h+pbSignature], r12; pbSignature
0x18000ce3e  call    cs:__imp_NCryptSignHash
0x18000ce44  mov     ebx, eax
0x18000ce46  test    eax, eax
0x18000ce48  js      loc_18000CF86
0x18000ce4e  xor     ebx, ebx
0x18000ce50  jmp     loc_18000CD06
0x18000ce55  test    byte ptr [rsp+128h+arg_38], 3
0x18000ce5d  jnz     loc_18000CEF8
0x18000ce63  xor     esi, esi
0x18000ce65  xor     r11d, r11d
0x18000ce68  jmp     short loc_18000CE18
0x18000ce6a  mov     ebx, 80090027h
0x18000ce6f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ce76  lea     rax, WPP_GLOBAL_Control
0x18000ce7d  cmp     rcx, rax
0x18000ce80  jz      loc_18000CD06
0x18000ce86  test    byte ptr [rcx+1Ch], 1
0x18000ce8a  jz      loc_18000CD06
0x18000ce90  mov     dword ptr [rsp+128h+pcbResult], 1480h
0x18000ce98  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000ce9f  mov     qword ptr [rsp+128h+cbSignature], rax
0x18000cea4  mov     dword ptr [rsp+128h+pbSignature], 80090027h
0x18000ceac  jmp     loc_18000CCF6
0x18000ceb1  mov     ebx, 80090027h
0x18000ceb6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cebd  lea     rax, WPP_GLOBAL_Control
0x18000cec4  cmp     rcx, rax
0x18000cec7  jz      loc_18000CD06
0x18000cecd  test    byte ptr [rcx+1Ch], 1
0x18000ced1  jz      loc_18000CD06
0x18000ced7  mov     dword ptr [rsp+128h+pcbResult], 1474h
0x18000cedf  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000cee6  mov     qword ptr [rsp+128h+cbSignature], rax
0x18000ceeb  mov     dword ptr [rsp+128h+pbSignature], 80090027h
0x18000cef3  jmp     loc_18000CCF6
0x18000cef8  mov     ebx, 80090027h
0x18000cefd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cf04  lea     rax, WPP_GLOBAL_Control
0x18000cf0b  cmp     rcx, rax
0x18000cf0e  jz      loc_18000CD06
0x18000cf14  test    byte ptr [rcx+1Ch], 1
0x18000cf18  jz      loc_18000CD06
0x18000cf1e  mov     dword ptr [rsp+128h+pcbResult], 14CAh
0x18000cf26  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000cf2d  mov     qword ptr [rsp+128h+cbSignature], rax
0x18000cf32  mov     dword ptr [rsp+128h+pbSignature], 80090027h
0x18000cf3a  jmp     loc_18000CCF6
0x18000cf3f  mov     ebx, 80090027h
0x18000cf44  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cf4b  lea     rax, WPP_GLOBAL_Control
0x18000cf52  cmp     rcx, rax
0x18000cf55  jz      loc_18000CD06
0x18000cf5b  test    byte ptr [rcx+1Ch], 1
0x18000cf5f  jz      loc_18000CD06
0x18000cf65  mov     dword ptr [rsp+128h+pcbResult], 14B9h
0x18000cf6d  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000cf74  mov     qword ptr [rsp+128h+cbSignature], rax
0x18000cf79  mov     dword ptr [rsp+128h+pbSignature], 80090027h
0x18000cf81  jmp     loc_18000CCF6
0x18000cf86  mov     r9d, 14DAh
0x18000cf8c  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000cf93  lea     rdx, aStatus; "Status"
0x18000cf9a  mov     ecx, eax
0x18000cf9c  call    DebugTraceError
0x18000cfa1  jmp     loc_18000CD06
```
