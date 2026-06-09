# SPSslComputeSessionHash

- ea: `0x180008b80`
- end: `0x180009155`
- name: `SPSslComputeSessionHash`
- size: `1493`
- prototype: `__int64 __fastcall(_DWORD *, __int64, int, UCHAR *, unsigned int, unsigned int *, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180008b80`
- `0x180009160`
- `0x18000b594`
- `0x18000b654`
- `0x180018ac0`
- `0x180024ef0`
- `0x180026010`

## import_xrefs

- `bcrypt!BCryptDuplicateHash` at `0x180008cc7`
- `bcrypt!BCryptDuplicateHash` at `0x180009088`
- `bcrypt!BCryptDuplicateHash` at `0x180008cc7`
- `bcrypt!BCryptDuplicateHash` at `0x180009088`
- `bcrypt!BCryptFinishHash` at `0x180008d35`
- `bcrypt!BCryptFinishHash` at `0x180008f18`
- `bcrypt!BCryptFinishHash` at `0x180008d35`
- `bcrypt!BCryptFinishHash` at `0x180008f18`
- `bcrypt!BCryptDestroyHash` at `0x180008d50`
- `bcrypt!BCryptDestroyHash` at `0x180009139`
- `bcrypt!BCryptDestroyHash` at `0x180008d50`
- `bcrypt!BCryptDestroyHash` at `0x180009139`

## string_xrefs

- `0x180008f9b`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x1800090b8`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x1800090e5`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18000911d`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180008c00`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180008e24`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180008e6a`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180008f5c`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180008fe8`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18000901b`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall SPSslComputeSessionHash(
        _DWORD *a1,
        __int64 a2,
        int a3,
        UCHAR *a4,
        unsigned int a5,
        unsigned int *a6,
        int a7)
{
  UCHAR *p_phNewHash; // rbx
  ULONG v10; // edi
  _QWORD *v11; // rcx
  __int64 v12; // rcx
  unsigned __int64 v13; // rcx
  void *v14; // rsp
  void *v15; // rsp
  void *v16; // rcx
  BCRYPT_HASH_HANDLE v17; // rcx
  ULONG v18; // edi
  unsigned int v19; // eax
  __int64 v20; // r14
  BCRYPT_HASH_HANDLE v21; // r13
  NTSTATUS v22; // eax
  NTSTATUS v23; // esi
  __int64 v25; // r14
  __int64 v26; // r9
  __int64 v27; // rcx
  __int64 v28; // r9
  UCHAR *v29; // rax
  NTSTATUS v30; // eax
  __int64 v31; // [rsp+0h] [rbp-40h] BYREF
  ULONG dwFlags; // [rsp+20h] [rbp-20h]
  const char *v33; // [rsp+28h] [rbp-18h]
  int v34; // [rsp+30h] [rbp-10h]
  BCRYPT_HASH_HANDLE phNewHash; // [rsp+40h] [rbp+0h] BYREF
  BCRYPT_HASH_HANDLE hHash[2]; // [rsp+48h] [rbp+8h] BYREF

  phNewHash = 0;
  hHash[0] = 0;
  p_phNewHash = 0;
  if ( a1 && *a1 >= 0x310u && a1[1] == 1936944177 )
  {
    if ( !a2 || *(_DWORD *)a2 < 0x30u || *(_DWORD *)(a2 + 4) != 1936944178 )
    {
      v10 = -2146893786;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v10;
      v34 = 982;
      goto LABEL_7;
    }
    if ( (unsigned int)(a3 - 769) > 3 && a3 != 65277 && a3 != 65279 )
    {
      v10 = -2146893783;
      DebugTraceError(2148073513LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", 994);
      goto LABEL_28;
    }
    if ( !a6 )
    {
      v26 = 1001;
      goto LABEL_47;
    }
    if ( a7 )
    {
      v10 = -2146893815;
      DebugTraceError(2148073481LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", 1008);
      goto LABEL_28;
    }
    v25 = (unsigned int)(*(_DWORD *)(a2 + 24) + *(_DWORD *)(a2 + 40));
    if ( (unsigned int)v25 < *(_DWORD *)(a2 + 24) )
    {
      v26 = 1020;
LABEL_47:
      v10 = -2146893785;
      v27 = 2148073511LL;
LABEL_48:
      DebugTraceError(v27, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", v26);
      goto LABEL_28;
    }
    if ( !(_DWORD)v25
      || (unsigned int)v25 > (unsigned __int64)g_ulMaxStackAllocSize
      || (unsigned __int64)(unsigned int)v25 + g_ulAdditionalProbeSize + 8 < (unsigned int)v25
      || !(unsigned int)VerifyStackAvailable() )
    {
      goto LABEL_85;
    }
    v12 = v25 + 23;
    if ( v25 + 23 <= (unsigned __int64)(v25 + 8) )
      v12 = 0xFFFFFFFFFFFFFF0LL;
    v13 = v12 & 0xFFFFFFFFFFFFFFF0uLL;
    v14 = alloca(v13);
    v15 = alloca(v13);
    p_phNewHash = (UCHAR *)&phNewHash;
    if ( &v31 == (__int64 *)-64LL || (LODWORD(phNewHash) = 1801679955, (p_phNewHash = (UCHAR *)hHash) == 0) )
    {
LABEL_85:
      if ( v25 + 8 >= (unsigned __int64)(unsigned int)v25 )
      {
        v29 = (UCHAR *)((__int64 (*)(void))g_pfnAllocate)();
        p_phNewHash = v29;
        if ( v29 )
        {
          *(_DWORD *)v29 = 1885431112;
          p_phNewHash = v29 + 8;
        }
      }
    }
    if ( !p_phNewHash )
    {
      v10 = -2146893810;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_28;
      v34 = 1028;
      v33 = "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c";
      dwFlags = -2146893810;
      goto LABEL_8;
    }
    v10 = BCryptDuplicateHash(*(BCRYPT_HASH_HANDLE *)(a2 + 16), &phNewHash, p_phNewHash, *(_DWORD *)(a2 + 24), 0);
    if ( (v10 & 0x80000000) != 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_28;
      v34 = 1040;
      v33 = "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c";
      dwFlags = v10;
      goto LABEL_8;
    }
    v16 = *(void **)(a2 + 32);
    if ( v16 )
    {
      v30 = BCryptDuplicateHash(v16, hHash, &p_phNewHash[*(unsigned int *)(a2 + 24)], *(_DWORD *)(a2 + 40), 0);
      v10 = v30;
      if ( v30 < 0 )
      {
        v26 = 1054;
        v27 = (unsigned int)v30;
        goto LABEL_48;
      }
    }
    v17 = hHash[0];
    v18 = *(_DWORD *)(a2 + 28);
    if ( hHash[0] )
    {
      if ( v18 != 20 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            a2,
            (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
            (unsigned int)"Status",
            39,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
            212);
        goto LABEL_60;
      }
      v19 = 36;
      v20 = 16;
    }
    else
    {
      if ( v18 > 0x40 )
      {
        v23 = -2146893785;
        v10 = -2146893785;
        goto LABEL_57;
      }
      v19 = *(_DWORD *)(a2 + 28);
      v20 = 0;
    }
    v21 = phNewHash;
    *a6 = v19;
    if ( a5 < v19 )
    {
      *a6 = 0;
      v23 = -2146893784;
      v10 = -2146893784;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          a2,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
          (unsigned int)"Status",
          40,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
          234);
    }
    else
    {
      if ( a4 )
      {
        if ( v17 && (v23 = BCryptFinishHash(v17, a4, 0x10u, 0), v23 < 0) )
        {
          v28 = 3330;
        }
        else
        {
          v22 = BCryptFinishHash(v21, &a4[v20], v18, 0);
          v23 = v22;
          if ( v22 >= 0 )
          {
            v10 = v22;
            goto LABEL_28;
          }
          v28 = 3342;
        }
        DebugTraceError(
          (unsigned int)v23,
          "Status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
          v28);
        v10 = v23;
        goto LABEL_57;
      }
      v23 = -2146893785;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_60:
        v10 = -2146893785;
        v26 = 1073;
        v27 = 2148073511LL;
        goto LABEL_48;
      }
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
        (unsigned int)"Status",
        39,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
        241);
      v10 = -2146893785;
    }
LABEL_57:
    v26 = 1073;
    v27 = (unsigned int)v23;
    goto LABEL_48;
  }
  v10 = -2146893786;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    return v10;
  v34 = 974;
LABEL_7:
  v33 = "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c";
  dwFlags = -2146893786;
LABEL_8:
  WPP_SF_sDsd(v11[2], a2, a3, (unsigned int)"Status", dwFlags, (__int64)v33, v34);
LABEL_28:
  if ( phNewHash )
    BCryptDestroyHash(phNewHash);
  if ( hHash[0] )
    BCryptDestroyHash(hHash[0]);
  if ( p_phNewHash && *((_DWORD *)p_phNewHash - 2) == 1885431112 )
    ((void (__fastcall *)(UCHAR *))g_pfnFree)(p_phNewHash - 8);
  return v10;
}

```

## disassembly

```asm
0x180008b80  push    rbp
0x180008b82  push    rbx
0x180008b83  push    rsi
0x180008b84  push    rdi
0x180008b85  push    r12
0x180008b87  push    r13
0x180008b89  push    r14
0x180008b8b  push    r15
0x180008b8d  sub     rsp, 68h
0x180008b91  lea     rbp, [rsp+40h]
0x180008b96  mov     rax, cs:__security_cookie
0x180008b9d  xor     rax, rbp
0x180008ba0  mov     [rbp+60h+var_48], rax
0x180008ba4  xor     r13d, r13d
0x180008ba7  mov     r15, r9
0x180008baa  mov     [rbp+60h+phNewHash], r13
0x180008bae  mov     rsi, rdx
0x180008bb1  mov     [rbp+60h+hHash], r13
0x180008bb5  mov     ebx, r13d
0x180008bb8  test    rcx, rcx
0x180008bbb  jz      short loc_180008BD2
0x180008bbd  cmp     dword ptr [rcx], 310h
0x180008bc3  jb      short loc_180008BD2
0x180008bc5  cmp     dword ptr [rcx+4], 73736C31h
0x180008bcc  jz      loc_180008D98
0x180008bd2  mov     edi, 80090026h
0x180008bd7  mov     rcx, cs:WPP_GLOBAL_Control
0x180008bde  lea     rax, WPP_GLOBAL_Control
0x180008be5  cmp     rcx, rax
0x180008be8  jz      loc_180008D79
0x180008bee  test    byte ptr [rcx+1Ch], 1
0x180008bf2  jz      loc_180008D79
0x180008bf8  mov     [rsp+0A0h+var_70], 3CEh
0x180008c00  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180008c07  mov     [rsp+0A0h+var_78], rax
0x180008c0c  mov     [rsp+0A0h+dwFlags], 80090026h
0x180008c14  mov     rcx, [rcx+10h]
0x180008c18  lea     r9, aStatus; "Status"
0x180008c1f  call    WPP_SF_sDsd
0x180008c24  jmp     loc_180008D47
0x180008c29  test    r14d, r14d
0x180008c2c  jz      loc_18000903D
0x180008c32  mov     edi, r14d
0x180008c35  cmp     rdi, cs:g_ulMaxStackAllocSize
0x180008c3c  ja      loc_18000903D
0x180008c42  mov     rcx, cs:g_ulAdditionalProbeSize
0x180008c49  add     rcx, 8
0x180008c4d  add     rcx, rdi
0x180008c50  cmp     rcx, rdi
0x180008c53  jb      loc_18000903D
0x180008c59  call    VerifyStackAvailable
0x180008c5e  test    eax, eax
0x180008c60  jz      loc_18000903D
0x180008c66  lea     rax, [r14+8]
0x180008c6a  lea     rcx, [rax+0Fh]
0x180008c6e  cmp     rcx, rax
0x180008c71  ja      short loc_180008C7D
0x180008c73  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180008c7d  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180008c81  mov     rax, rcx
0x180008c84  call    _alloca_probe
0x180008c89  sub     rsp, rcx
0x180008c8c  lea     rbx, [rsp+0A0h+phNewHash]
0x180008c91  test    rbx, rbx
0x180008c94  jz      loc_18000903D
0x180008c9a  mov     dword ptr [rbx], 6B637453h
0x180008ca0  add     rbx, 8
0x180008ca4  jz      loc_18000903D
0x180008caa  test    rbx, rbx
0x180008cad  jz      loc_180008E3C
0x180008cb3  mov     r9d, [rsi+18h]; cbHashObject
0x180008cb7  lea     rdx, [rbp+60h+phNewHash]; phNewHash
0x180008cbb  mov     rcx, [rsi+10h]; hHash
0x180008cbf  mov     r8, rbx; pbHashObject
0x180008cc2  mov     [rsp+0A0h+dwFlags], r13d; dwFlags
0x180008cc7  call    cs:__imp_BCryptDuplicateHash
0x180008ccd  mov     edi, eax
0x180008ccf  test    eax, eax
0x180008cd1  js      loc_180008F33
0x180008cd7  mov     rcx, [rsi+20h]; hHash
0x180008cdb  test    rcx, rcx
0x180008cde  jnz     loc_180009074
0x180008ce4  mov     rcx, [rbp+60h+hHash]; hHash
0x180008ce8  mov     edi, [rsi+1Ch]
0x180008ceb  test    rcx, rcx
0x180008cee  jnz     loc_180008E83
0x180008cf4  cmp     edi, 40h ; '@'
0x180008cf7  ja      loc_1800090A5
0x180008cfd  mov     eax, edi
0x180008cff  mov     r14, r13
0x180008d02  mov     r13, [rbp+60h+phNewHash]
0x180008d06  mov     [r12], eax
0x180008d0a  cmp     [rbp+60h+arg_20], eax
0x180008d10  jb      loc_180008E9C
0x180008d16  test    r15, r15
0x180008d19  jz      loc_180008ED8
0x180008d1f  test    rcx, rcx
0x180008d22  jnz     loc_180008F0C
0x180008d28  lea     rdx, [r14+r15]; pbOutput
0x180008d2c  xor     r9d, r9d; dwFlags
0x180008d2f  mov     r8d, edi; cbOutput
0x180008d32  mov     rcx, r13; hHash
0x180008d35  call    cs:__imp_BCryptFinishHash
0x180008d3b  mov     esi, eax
0x180008d3d  test    eax, eax
0x180008d3f  js      loc_180009117
0x180008d45  mov     edi, eax
0x180008d47  mov     rcx, [rbp+60h+phNewHash]; hHash
0x180008d4b  test    rcx, rcx
0x180008d4e  jz      short loc_180008D56
0x180008d50  call    cs:__imp_BCryptDestroyHash
0x180008d56  mov     rcx, [rbp+60h+hHash]; hHash
0x180008d5a  test    rcx, rcx
0x180008d5d  jnz     loc_180009139
0x180008d63  test    rbx, rbx
0x180008d66  jz      short loc_180008D79
0x180008d68  cmp     dword ptr [rbx-8], 70616548h
0x180008d6f  lea     rcx, [rbx-8]
0x180008d73  jz      loc_180009144
0x180008d79  mov     eax, edi
0x180008d7b  mov     rcx, [rbp+60h+var_48]
0x180008d7f  xor     rcx, rbp; StackCookie
0x180008d82  call    __security_check_cookie
0x180008d87  lea     rsp, [rbp+28h]
0x180008d8b  pop     r15
0x180008d8d  pop     r14
0x180008d8f  pop     r13
0x180008d91  pop     r12
0x180008d93  pop     rdi
0x180008d94  pop     rsi
0x180008d95  pop     rbx
0x180008d96  pop     rbp
0x180008d97  retn
0x180008d98  test    rsi, rsi
0x180008d9b  jz      short loc_180008DAB
0x180008d9d  cmp     dword ptr [rdx], 30h ; '0'
0x180008da0  jb      short loc_180008DAB
0x180008da2  cmp     dword ptr [rdx+4], 73736C32h
0x180008da9  jz      short loc_180008DD6
0x180008dab  mov     edi, 80090026h
0x180008db0  mov     rcx, cs:WPP_GLOBAL_Control
0x180008db7  lea     rax, WPP_GLOBAL_Control
0x180008dbe  cmp     rcx, rax
0x180008dc1  jz      short loc_180008D79
0x180008dc3  test    byte ptr [rcx+1Ch], 1
0x180008dc7  jz      short loc_180008D79
0x180008dc9  mov     [rsp+0A0h+var_70], 3D6h
0x180008dd1  jmp     loc_180008C00
0x180008dd6  lea     eax, [r8-301h]
0x180008ddd  cmp     eax, 3
0x180008de0  ja      loc_180008FC8
0x180008de6  mov     r12, [rbp+60h+arg_28]
0x180008ded  test    r12, r12
0x180008df0  jz      loc_18000900A
0x180008df6  cmp     [rbp+60h+arg_30], ebx
0x180008dfc  jnz     loc_180009015
0x180008e02  mov     r14d, [rdx+28h]
0x180008e06  add     r14d, [rdx+18h]
0x180008e0a  cmp     r14d, [rdx+18h]
0x180008e0e  jnb     loc_180008C29
0x180008e14  mov     r9d, 3FCh
0x180008e1a  mov     edi, 80090027h
0x180008e1f  mov     ecx, 80090027h
0x180008e24  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180008e2b  lea     rdx, aStatus; "Status"
0x180008e32  call    DebugTraceError
0x180008e37  jmp     loc_180008D47
0x180008e3c  mov     edi, 8009000Eh
0x180008e41  mov     rcx, cs:WPP_GLOBAL_Control
0x180008e48  lea     rax, WPP_GLOBAL_Control
0x180008e4f  cmp     rcx, rax
0x180008e52  jz      loc_180008D47
0x180008e58  test    byte ptr [rcx+1Ch], 1
0x180008e5c  jz      loc_180008D47
0x180008e62  mov     [rsp+0A0h+var_70], 404h
0x180008e6a  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180008e71  mov     [rsp+0A0h+var_78], rax
0x180008e76  mov     [rsp+0A0h+dwFlags], 8009000Eh
0x180008e7e  jmp     loc_180008C14
0x180008e83  cmp     edi, 14h
0x180008e86  jnz     loc_180008F71
0x180008e8c  mov     eax, 24h ; '$'
0x180008e91  mov     r14d, 10h
0x180008e97  jmp     loc_180008D02
0x180008e9c  mov     dword ptr [r12], 0
0x180008ea4  mov     esi, 80090028h
0x180008ea9  mov     rcx, cs:WPP_GLOBAL_Control
0x180008eb0  lea     rax, WPP_GLOBAL_Control
0x180008eb7  mov     edi, 80090028h
0x180008ebc  cmp     rcx, rax
0x180008ebf  jz      short loc_180008ECB
0x180008ec1  test    byte ptr [rcx+1Ch], 1
0x180008ec5  jnz     loc_1800090B4
0x180008ecb  mov     r9d, 431h
0x180008ed1  mov     ecx, esi
0x180008ed3  jmp     loc_180008E24
0x180008ed8  mov     esi, 80090027h
0x180008edd  mov     rcx, cs:WPP_GLOBAL_Control
0x180008ee4  lea     rax, WPP_GLOBAL_Control
0x180008eeb  cmp     rcx, rax
0x180008eee  jz      short loc_180008EFA
0x180008ef0  test    byte ptr [rcx+1Ch], 1
0x180008ef4  jnz     loc_1800090E1
0x180008efa  mov     edi, 80090027h
0x180008eff  mov     r9d, 431h
0x180008f05  mov     ecx, esi
0x180008f07  jmp     loc_180008E24
0x180008f0c  xor     r9d, r9d; dwFlags
0x180008f0f  mov     r8d, 10h; cbOutput
0x180008f15  mov     rdx, r15; pbOutput
0x180008f18  call    cs:__imp_BCryptFinishHash
0x180008f1e  mov     esi, eax
0x180008f20  test    eax, eax
0x180008f22  jns     loc_180008D28
0x180008f28  mov     r9d, 0D02h
0x180008f2e  jmp     loc_18000911D
0x180008f33  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f3a  lea     rax, WPP_GLOBAL_Control
0x180008f41  cmp     rcx, rax
0x180008f44  jz      loc_180008D47
0x180008f4a  test    byte ptr [rcx+1Ch], 1
0x180008f4e  jz      loc_180008D47
0x180008f54  mov     [rsp+0A0h+var_70], 410h
0x180008f5c  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180008f63  mov     [rsp+0A0h+var_78], rax
0x180008f68  mov     [rsp+0A0h+dwFlags], edi
0x180008f6c  jmp     loc_180008C14
0x180008f71  mov     esi, 80090027h
0x180008f76  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f7d  lea     rax, WPP_GLOBAL_Control
0x180008f84  cmp     rcx, rax
0x180008f87  jz      loc_180008EFA
0x180008f8d  test    byte ptr [rcx+1Ch], 1
0x180008f91  jz      loc_180008EFA
0x180008f97  mov     rcx, [rcx+10h]
0x180008f9b  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180008fa2  mov     [rsp+0A0h+var_70], 0CD4h
0x180008faa  lea     r9, aStatus; "Status"
0x180008fb1  mov     [rsp+0A0h+var_78], r8
0x180008fb6  mov     [rsp+0A0h+dwFlags], 80090027h
0x180008fbe  call    WPP_SF_sDsd
0x180008fc3  jmp     loc_180008EFA
0x180008fc8  cmp     r8d, 0FEFDh
0x180008fcf  jz      loc_180008DE6
0x180008fd5  cmp     r8d, 0FEFFh
0x180008fdc  jz      loc_180008DE6
0x180008fe2  mov     r9d, 3E2h
0x180008fe8  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180008fef  lea     rdx, aStatus; "Status"
0x180008ff6  mov     ecx, 80090029h
0x180008ffb  mov     edi, 80090029h
0x180009000  call    DebugTraceError
0x180009005  jmp     loc_180008D47
0x18000900a  mov     r9d, 3E9h
0x180009010  jmp     loc_180008E1A
0x180009015  mov     r9d, 3F0h
0x18000901b  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009022  lea     rdx, aStatus; "Status"
0x180009029  mov     ecx, 80090009h
0x18000902e  mov     edi, 80090009h
0x180009033  call    DebugTraceError
0x180009038  jmp     loc_180008D47
0x18000903d  mov     eax, r14d
0x180009040  lea     rcx, [r14+8]
0x180009044  cmp     rcx, rax
0x180009047  jb      loc_180008CAA
0x18000904d  mov     rax, cs:g_pfnAllocate
0x180009054  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009059  mov     rbx, rax
0x18000905c  test    rax, rax
0x18000905f  jz      loc_180008CAA
0x180009065  mov     dword ptr [rax], 70616548h
0x18000906b  add     rbx, 8
0x18000906f  jmp     loc_180008CAA
0x180009074  mov     r8d, [rsi+18h]
0x180009078  lea     rdx, [rbp+60h+hHash]; phNewHash
0x18000907c  mov     r9d, [rsi+28h]; cbHashObject
0x180009080  add     r8, rbx; pbHashObject
0x180009083  mov     [rsp+0A0h+dwFlags], r13d; dwFlags
0x180009088  call    cs:__imp_BCryptDuplicateHash
0x18000908e  mov     edi, eax
0x180009090  test    eax, eax
0x180009092  jns     loc_180008CE4
0x180009098  mov     r9d, 41Eh
0x18000909e  mov     ecx, eax
0x1800090a0  jmp     loc_180008E24
0x1800090a5  mov     esi, 80090027h
0x1800090aa  mov     edi, 80090027h
0x1800090af  jmp     loc_180008ECB
0x1800090b4  mov     rcx, [rcx+10h]
0x1800090b8  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800090bf  mov     [rsp+0A0h+var_70], 0CEAh
0x1800090c7  lea     r9, aStatus; "Status"
0x1800090ce  mov     [rsp+0A0h+var_78], r8
0x1800090d3  mov     [rsp+0A0h+dwFlags], edi
0x1800090d7  call    WPP_SF_sDsd
0x1800090dc  jmp     loc_180008ECB
0x1800090e1  mov     rcx, [rcx+10h]
0x1800090e5  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800090ec  mov     [rsp+0A0h+var_70], 0CF1h
  ... truncated ...
```
