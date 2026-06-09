# CNG_SetKeyPropertiesFromAlgInfo

- ea: `0x180004c00`
- end: `0x1800050c9`
- name: `CNG_SetKeyPropertiesFromAlgInfo`
- size: `1225`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180006a70`

## callees

- `0x180004c00`
- `0x18000d02c`
- `0x18000e120`
- `0x180015c4c`
- `0x18001f145`
- `0x18001f15d`
- `0x18001f175`
- `0x18001f18d`
- `0x18001f1b0`
- `0x180020010`

## import_xrefs

- `bcrypt!BCryptSetProperty` at `0x180004c7e`
- `bcrypt!BCryptSetProperty` at `0x180004fd7`
- `bcrypt!BCryptSetProperty` at `0x180004c7e`
- `bcrypt!BCryptSetProperty` at `0x180004fd7`
- `NTASN1!__imp_RtlAsn1Decode` at `0x180004d79`
- `NTASN1!__imp_RtlAsn1Decode` at `0x180005099`
- `NTASN1!__imp_RtlAsn1Decode` at `0x180004d79`
- `NTASN1!__imp_RtlAsn1Decode` at `0x180005099`

## string_xrefs

- `0x180004cab`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\util.c`
- `0x180004e75`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\util.c`
- `0x180004eea`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\util.c`
- `0x180004fed`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\util.c`
- `0x18000504c`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\util.c`

## pseudocode

```c
__int64 __fastcall CNG_SetKeyPropertiesFromAlgInfo(__int64 a1, __int64 *a2)
{
  __int64 v2; // r8
  void **v5; // rbx
  UCHAR *v6; // r8
  __int64 v7; // r9
  int v8; // edx
  unsigned int v9; // edi
  _QWORD *v10; // rcx
  __int64 v12; // r14
  const wchar_t *v13; // rdi
  int v14; // edx
  __int64 v15; // r9
  __int64 v16; // rax
  int v17; // ecx
  __int64 v18; // rax
  void *v19; // rax
  int v20; // edx
  size_t v21; // r8
  __int64 v22; // r8
  unsigned __int64 v23; // rdi
  __int64 v24; // rcx
  unsigned __int64 v25; // rcx
  void *v26; // rsp
  void *v27; // rsp
  _DWORD *v28; // rax
  unsigned int v29; // eax
  __int64 v30; // r9
  __int64 v31; // rcx
  __int64 v32; // rax
  __int64 v33; // r9
  unsigned int v34; // ecx
  ULONG dwFlags[2]; // [rsp+20h] [rbp-20h]
  char v36; // [rsp+30h] [rbp-10h]
  __int64 *v37; // [rsp+38h] [rbp-8h]
  __int64 v38; // [rsp+40h] [rbp+0h] BYREF
  void *Src[2]; // [rsp+48h] [rbp+8h] BYREF
  unsigned int v40; // [rsp+58h] [rbp+18h]
  size_t Size[2]; // [rsp+60h] [rbp+20h] BYREF

  v2 = a2[3];
  v38 = 0;
  *(_OWORD *)Size = 0;
  v5 = 0;
  if ( *(_DWORD *)(v2 + 16) != 1 )
    goto LABEL_20;
  v6 = *(UCHAR **)(v2 + 64);
  if ( v6 )
  {
    v7 = -1;
    do
      ++v7;
    while ( *(_WORD *)&v6[2 * v7] );
    v9 = BCryptSetProperty((BCRYPT_HANDLE)a2[2], L"ChainingMode", v6, 2 * v7 + 2, 0);
    if ( v9 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v36 = -84;
LABEL_9:
        WPP_SF_sDsd(
          v10[2],
          v8,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\util.c",
          (unsigned int)"Status",
          v9,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\util.c",
          v36);
        return v9;
      }
      return v9;
    }
  }
  v12 = a2[3];
  v13 = *(const wchar_t **)(v12 + 64);
  if ( !v13 || !*v13 || !wcscmp_0(*(const wchar_t **)(v12 + 64), L"ChainingModeCBC") )
  {
    v23 = *(unsigned int *)(v12 + 60);
    if ( !*(_DWORD *)(v12 + 60)
      || v23 > g_ulMaxStackAllocSize
      || v23 + g_ulAdditionalProbeSize + 8 < v23
      || !(unsigned int)VerifyStackAvailable() )
    {
      goto LABEL_57;
    }
    v24 = v23 + 23;
    if ( v23 + 23 <= v23 + 8 )
      v24 = 0xFFFFFFFFFFFFFF0LL;
    v25 = v24 & 0xFFFFFFFFFFFFFFF0uLL;
    v26 = alloca(v25);
    v27 = alloca(v25);
    v5 = (void **)&v38;
    if ( !&v38 || (LODWORD(v38) = 1801679955, (v5 = Src) == 0) )
    {
LABEL_57:
      if ( v23 + 8 >= v23 )
      {
        v28 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
        v5 = (void **)v28;
        if ( v28 )
        {
          *v28 = 1885431112;
          v5 = (void **)(v28 + 2);
        }
      }
    }
    if ( !v5 )
    {
      v9 = -2146893810;
      v30 = 445;
      v31 = 2148073486LL;
      goto LABEL_50;
    }
    memset_0(v5, 0, *(unsigned int *)(a2[3] + 60));
    if ( *(_DWORD *)(a1 + 16) > 2u )
    {
      v32 = *(unsigned int *)(a1 + 16);
      v33 = *(_QWORD *)(a1 + 24);
      v38 = 16;
      if ( !(unsigned int)((__int64 (__fastcall *)(__int64, __int64, __int64, __int64, __int64, _QWORD, size_t *, __int64 *))RtlAsn1Decode)(
                            ASN1_NCRYPT_MODULE_HANDLE,
                            6,
                            1,
                            v33,
                            v32,
                            0,
                            Size,
                            &v38) )
      {
        v34 = *(_DWORD *)(a2[3] + 60);
        if ( LODWORD(Size[0]) < v34 )
          v34 = Size[0];
        memcpy_0(v5, (const void *)Size[1], v34);
      }
    }
    v29 = BCryptSetProperty((BCRYPT_HANDLE)a2[2], L"IV", (PUCHAR)v5, *(_DWORD *)(a2[3] + 60), 0);
    v9 = v29;
    if ( v29 )
    {
      DebugTraceError(v29, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\util.c", 487);
LABEL_46:
      if ( *((_DWORD *)v5 - 2) == 1885431112 )
        ((void (*)(void))g_pfnFree)();
      return v9;
    }
LABEL_20:
    v9 = 0;
    if ( !v5 )
      return v9;
    goto LABEL_46;
  }
  if ( wcscmp_0(v13, L"ChainingModeGCM") )
  {
    v9 = -2146893783;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v14,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\util.c",
        (unsigned int)"Status",
        41,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\util.c",
        48);
    return v9;
  }
  v15 = *(_QWORD *)(a1 + 24);
  v37 = &v38;
  v40 = 0;
  *(_QWORD *)dwFlags = *(unsigned int *)(a1 + 16);
  *(_OWORD *)Src = 0;
  v38 = 24;
  v9 = ((__int64 (__fastcall *)(__int64, __int64, __int64, __int64, _QWORD, _QWORD, void **, __int64 *))RtlAsn1Decode)(
         ASN1_NCRYPT_MODULE_HANDLE,
         27,
         1,
         v15,
         *(_QWORD *)dwFlags,
         0,
         Src,
         &v38);
  if ( !v9 )
  {
    if ( v40 <= 0x10 && LODWORD(Src[0]) <= 0xC )
    {
      v16 = a2[3];
      *((_DWORD *)a2 + 16) = 152;
      v17 = *(_DWORD *)(v16 + 60);
      v18 = *a2;
      *((_DWORD *)a2 + 16) = v17 + 152;
      v19 = (void *)(*(__int64 (**)(void))(v18 + 8))();
      a2[9] = (__int64)v19;
      if ( !v19 )
      {
        v9 = -2146893810;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v20,
            (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\util.c",
            (unsigned int)"Status",
            14,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\util.c",
            23);
        return v9;
      }
      v21 = *((unsigned int *)a2 + 16);
      *((_DWORD *)a2 + 28) |= 8u;
      memset_0(v19, 0, v21);
      v22 = a2[9];
      *(_DWORD *)v22 = 88;
      *(_QWORD *)(v22 + 8) = v22 + 88;
      *(_DWORD *)(v22 + 4) = 1;
      *(_DWORD *)(v22 + 16) = Src[0];
      *(_QWORD *)(v22 + 40) = 0;
      *(_DWORD *)(v22 + 48) = v40;
      *(_QWORD *)(v22 + 136) = v22 + 152;
      *(_DWORD *)(v22 + 144) = *(_DWORD *)(a2[3] + 60);
      memcpy_0((void *)(v22 + 88), Src[1], LODWORD(Src[0]));
      *((_DWORD *)a2 + 28) |= 0x10000000u;
      goto LABEL_20;
    }
    v9 = -2146893816;
    v30 = 524;
    v31 = 2148073480LL;
LABEL_50:
    DebugTraceError(v31, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\util.c", v30);
    return v9;
  }
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v36 = 4;
    goto LABEL_9;
  }
  return v9;
}

```

## disassembly

```asm
0x180004c00  push    rbp
0x180004c02  push    rbx
0x180004c03  push    rsi
0x180004c04  push    rdi
0x180004c05  push    r12
0x180004c07  push    r14
0x180004c09  push    r15
0x180004c0b  sub     rsp, 80h
0x180004c12  lea     rbp, [rsp+40h]
0x180004c17  mov     rax, cs:__security_cookie
0x180004c1e  xor     rax, rbp
0x180004c21  mov     [rbp+70h+var_38], rax
0x180004c25  mov     r8, [rdx+18h]
0x180004c29  xor     r12d, r12d
0x180004c2c  xorps   xmm0, xmm0
0x180004c2f  mov     [rbp+70h+var_70], r12
0x180004c33  movups  xmmword ptr [rbp+70h+Size], xmm0
0x180004c37  mov     rsi, rdx
0x180004c3a  mov     r15, rcx
0x180004c3d  cmp     dword ptr [r8+10h], 1
0x180004c42  mov     ebx, r12d
0x180004c45  jnz     loc_180004E36
0x180004c4b  mov     r8, [r8+40h]; pbInput
0x180004c4f  test    r8, r8
0x180004c52  jz      loc_180004CE8
0x180004c58  or      r9, 0FFFFFFFFFFFFFFFFh
0x180004c5c  inc     r9
0x180004c5f  cmp     [r8+r9*2], r12w
0x180004c64  jnz     short loc_180004C5C
0x180004c66  mov     rcx, [rsi+10h]; hObject
0x180004c6a  lea     r9d, ds:2[r9*2]; cbInput
0x180004c72  lea     rdx, pszProperty; "ChainingMode"
0x180004c79  mov     [rsp+0B0h+dwFlags], r12d; dwFlags
0x180004c7e  call    cs:__imp_BCryptSetProperty
0x180004c84  mov     edi, eax
0x180004c86  test    eax, eax
0x180004c88  jz      short loc_180004CE8
0x180004c8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180004c91  lea     rax, WPP_GLOBAL_Control
0x180004c98  cmp     rcx, rax
0x180004c9b  jz      short loc_180004CCB
0x180004c9d  test    byte ptr [rcx+1Ch], 1
0x180004ca1  jz      short loc_180004CCB
0x180004ca3  mov     dword ptr [rsp+0B0h+var_80], 1ACh
0x180004cab  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180004cb2  mov     [rsp+0B0h+var_88], r8
0x180004cb7  mov     [rsp+0B0h+dwFlags], edi
0x180004cbb  mov     rcx, [rcx+10h]
0x180004cbf  lea     r9, aStatus; "Status"
0x180004cc6  call    WPP_SF_sDsd
0x180004ccb  mov     eax, edi
0x180004ccd  mov     rcx, [rbp+70h+var_38]
0x180004cd1  xor     rcx, rbp; StackCookie
0x180004cd4  call    __security_check_cookie
0x180004cd9  lea     rsp, [rbp+40h]
0x180004cdd  pop     r15
0x180004cdf  pop     r14
0x180004ce1  pop     r12
0x180004ce3  pop     rdi
0x180004ce4  pop     rsi
0x180004ce5  pop     rbx
0x180004ce6  pop     rbp
0x180004ce7  retn
0x180004ce8  mov     r14, [rsi+18h]
0x180004cec  mov     rdi, [r14+40h]
0x180004cf0  test    rdi, rdi
0x180004cf3  jz      loc_180004F03
0x180004cf9  cmp     r12w, [rdi]
0x180004cfd  jz      loc_180004F03
0x180004d03  lea     rdx, aChainingmodecb; "ChainingModeCBC"
0x180004d0a  mov     rcx, rdi; String1
0x180004d0d  call    wcscmp_0
0x180004d12  test    eax, eax
0x180004d14  jz      loc_180004F03
0x180004d1a  lea     rdx, aChainingmodegc; "ChainingModeGCM"
0x180004d21  mov     rcx, rdi; String1
0x180004d24  call    wcscmp_0
0x180004d29  test    eax, eax
0x180004d2b  jnz     loc_180004EBC
0x180004d31  mov     r9, [r15+18h]
0x180004d35  lea     rcx, [rbp+70h+var_70]
0x180004d39  mov     [rsp+0B0h+var_78], rcx
0x180004d3e  xor     eax, eax
0x180004d40  mov     edx, 1Bh
0x180004d45  mov     [rbp+70h+var_58], eax
0x180004d48  mov     eax, [r15+10h]
0x180004d4c  lea     rcx, [rbp+70h+Src]
0x180004d50  mov     [rsp+0B0h+var_80], rcx
0x180004d55  xorps   xmm0, xmm0
0x180004d58  mov     rcx, cs:ASN1_NCRYPT_MODULE_HANDLE
0x180004d5f  mov     [rsp+0B0h+var_88], r12
0x180004d64  lea     r8d, [rdx-1Ah]
0x180004d68  mov     qword ptr [rsp+0B0h+dwFlags], rax
0x180004d6d  movups  xmmword ptr [rbp+70h+Src], xmm0
0x180004d71  mov     [rbp+70h+var_70], 18h
0x180004d79  call    cs:__imp_RtlAsn1Decode
0x180004d7f  mov     edi, eax
0x180004d81  test    eax, eax
0x180004d83  jnz     loc_180004E8E
0x180004d89  cmp     [rbp+70h+var_58], 10h
0x180004d8d  ja      loc_180005023
0x180004d93  cmp     dword ptr [rbp+70h+Src], 0Ch
0x180004d97  ja      loc_180005023
0x180004d9d  mov     rax, [rsi+18h]
0x180004da1  mov     dword ptr [rsi+40h], 98h
0x180004da8  mov     ecx, [rax+3Ch]
0x180004dab  mov     rax, [rsi]
0x180004dae  add     ecx, 98h
0x180004db4  mov     [rsi+40h], ecx
0x180004db7  mov     rax, [rax+8]
0x180004dbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004dc0  mov     [rsi+48h], rax
0x180004dc4  test    rax, rax
0x180004dc7  jz      short loc_180004E47
0x180004dc9  mov     r8d, [rsi+40h]; Size
0x180004dcd  xor     edx, edx; Val
0x180004dcf  or      dword ptr [rsi+70h], 8
0x180004dd3  mov     rcx, rax; void *
0x180004dd6  call    memset_0
0x180004ddb  mov     r8, [rsi+48h]
0x180004ddf  mov     dword ptr [r8], 58h ; 'X'
0x180004de6  lea     rcx, [r8+58h]; void *
0x180004dea  mov     [r8+8], rcx
0x180004dee  mov     dword ptr [r8+4], 1
0x180004df6  mov     eax, dword ptr [rbp+70h+Src]
0x180004df9  mov     [r8+10h], eax
0x180004dfd  mov     [r8+28h], r12
0x180004e01  mov     eax, [rbp+70h+var_58]
0x180004e04  mov     [r8+30h], eax
0x180004e08  lea     rax, [r8+98h]
0x180004e0f  mov     [r8+88h], rax
0x180004e16  mov     rax, [rsi+18h]
0x180004e1a  mov     edx, [rax+3Ch]
0x180004e1d  mov     [r8+90h], edx
0x180004e24  mov     r8d, dword ptr [rbp+70h+Src]; Size
0x180004e28  mov     rdx, [rbp+70h+Src+8]; Src
0x180004e2c  call    memcpy_0
0x180004e31  bts     dword ptr [rsi+70h], 1Ch
0x180004e36  mov     edi, r12d
0x180004e39  test    rbx, rbx
0x180004e3c  jz      loc_180004CCB
0x180004e42  jmp     loc_180005002
0x180004e47  mov     edi, 8009000Eh
0x180004e4c  mov     rcx, cs:WPP_GLOBAL_Control
0x180004e53  lea     rax, WPP_GLOBAL_Control
0x180004e5a  cmp     rcx, rax
0x180004e5d  jz      loc_180004CCB
0x180004e63  test    byte ptr [rcx+1Ch], 1
0x180004e67  jz      loc_180004CCB
0x180004e6d  mov     dword ptr [rsp+0B0h+var_80], 217h
0x180004e75  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180004e7c  mov     [rsp+0B0h+var_88], r8
0x180004e81  mov     [rsp+0B0h+dwFlags], 8009000Eh
0x180004e89  jmp     loc_180004CBB
0x180004e8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180004e95  lea     rax, WPP_GLOBAL_Control
0x180004e9c  cmp     rcx, rax
0x180004e9f  jz      loc_180004CCB
0x180004ea5  test    byte ptr [rcx+1Ch], 1
0x180004ea9  jz      loc_180004CCB
0x180004eaf  mov     dword ptr [rsp+0B0h+var_80], 204h
0x180004eb7  jmp     loc_180004CAB
0x180004ebc  mov     edi, 80090029h
0x180004ec1  mov     rcx, cs:WPP_GLOBAL_Control
0x180004ec8  lea     rax, WPP_GLOBAL_Control
0x180004ecf  cmp     rcx, rax
0x180004ed2  jz      loc_180004CCB
0x180004ed8  test    byte ptr [rcx+1Ch], 1
0x180004edc  jz      loc_180004CCB
0x180004ee2  mov     dword ptr [rsp+0B0h+var_80], 230h
0x180004eea  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180004ef1  mov     [rsp+0B0h+var_88], r8
0x180004ef6  mov     [rsp+0B0h+dwFlags], 80090029h
0x180004efe  jmp     loc_180004CBB
0x180004f03  mov     edi, [r14+3Ch]
0x180004f07  test    rdi, rdi
0x180004f0a  jz      short loc_180004F61
0x180004f0c  cmp     rdi, cs:g_ulMaxStackAllocSize
0x180004f13  ja      short loc_180004F61
0x180004f15  mov     rcx, cs:g_ulAdditionalProbeSize
0x180004f1c  add     rcx, 8
0x180004f20  add     rcx, rdi
0x180004f23  cmp     rcx, rdi
0x180004f26  jb      short loc_180004F61
0x180004f28  call    VerifyStackAvailable
0x180004f2d  test    eax, eax
0x180004f2f  jz      short loc_180004F61
0x180004f31  lea     rax, [rdi+8]
0x180004f35  lea     rcx, [rax+0Fh]
0x180004f39  cmp     rcx, rax
0x180004f3c  ja      short loc_180004F48
0x180004f3e  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180004f48  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180004f4c  mov     rax, rcx
0x180004f4f  call    __chkstk_0
0x180004f54  sub     rsp, rcx
0x180004f57  lea     rbx, [rsp+0B0h+var_70]
0x180004f5c  test    rbx, rbx
0x180004f5f  jnz     short loc_180004F8A
0x180004f61  lea     rcx, [rdi+8]
0x180004f65  cmp     rcx, rdi
0x180004f68  jb      short loc_180004F96
0x180004f6a  mov     rax, cs:g_pfnAllocate
0x180004f71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f76  mov     rbx, rax
0x180004f79  test    rax, rax
0x180004f7c  jz      short loc_180004F96
0x180004f7e  mov     dword ptr [rax], 70616548h
0x180004f84  add     rbx, 8
0x180004f88  jmp     short loc_180004F96
0x180004f8a  mov     dword ptr [rbx], 6B637453h
0x180004f90  add     rbx, 8
0x180004f94  jz      short loc_180004F61
0x180004f96  test    rbx, rbx
0x180004f99  jz      loc_180005035
0x180004f9f  mov     rax, [rsi+18h]
0x180004fa3  xor     edx, edx; Val
0x180004fa5  mov     rcx, rbx; void *
0x180004fa8  mov     r8d, [rax+3Ch]; Size
0x180004fac  call    memset_0
0x180004fb1  cmp     dword ptr [r15+10h], 2
0x180004fb6  ja      loc_18000505D
0x180004fbc  mov     r9, [rsi+18h]
0x180004fc0  lea     rdx, aIv; "IV"
0x180004fc7  mov     rcx, [rsi+10h]; hObject
0x180004fcb  mov     r8, rbx; pbInput
0x180004fce  mov     [rsp+0B0h+dwFlags], r12d; dwFlags
0x180004fd3  mov     r9d, [r9+3Ch]; cbInput
0x180004fd7  call    cs:__imp_BCryptSetProperty
0x180004fdd  mov     edi, eax
0x180004fdf  test    eax, eax
0x180004fe1  jz      loc_180004E36
0x180004fe7  mov     r9d, 1E7h
0x180004fed  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180004ff4  lea     rdx, aStatus; "Status"
0x180004ffb  mov     ecx, eax
0x180004ffd  call    DebugTraceError
0x180005002  lea     rcx, [rbx-8]
0x180005006  cmp     dword ptr [rcx], 70616548h
0x18000500c  jnz     loc_180004CCB
0x180005012  mov     rax, cs:g_pfnFree
0x180005019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000501e  jmp     loc_180004CCB
0x180005023  mov     edi, 80090008h
0x180005028  mov     r9d, 20Ch
0x18000502e  mov     ecx, 80090008h
0x180005033  jmp     short loc_180005045
0x180005035  mov     edi, 8009000Eh
0x18000503a  mov     r9d, 1BDh
0x180005040  mov     ecx, 8009000Eh
0x180005045  lea     rdx, aStatus; "Status"
0x18000504c  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005053  call    DebugTraceError
0x180005058  jmp     loc_180004CCB
0x18000505d  mov     eax, [r15+10h]
0x180005061  lea     rcx, [rbp+70h+var_70]
0x180005065  mov     r9, [r15+18h]
0x180005069  mov     edx, 6
0x18000506e  mov     [rsp+0B0h+var_78], rcx
0x180005073  lea     rcx, [rbp+70h+Size]
0x180005077  mov     [rsp+0B0h+var_80], rcx
0x18000507c  mov     rcx, cs:ASN1_NCRYPT_MODULE_HANDLE
0x180005083  mov     [rsp+0B0h+var_88], r12
0x180005088  lea     r8d, [rdx-5]
0x18000508c  mov     qword ptr [rsp+0B0h+dwFlags], rax
0x180005091  mov     [rbp+70h+var_70], 10h
0x180005099  call    cs:__imp_RtlAsn1Decode
0x18000509f  test    eax, eax
0x1800050a1  jnz     loc_180004FBC
0x1800050a7  mov     rax, [rsi+18h]
0x1800050ab  mov     rdx, [rbp+70h+Size+8]; Src
0x1800050af  mov     ecx, [rax+3Ch]
0x1800050b2  cmp     dword ptr [rbp+70h+Size], ecx
0x1800050b5  cmovb   ecx, dword ptr [rbp+70h+Size]
0x1800050b9  mov     r8d, ecx; Size
0x1800050bc  mov     rcx, rbx; void *
0x1800050bf  call    memcpy_0
0x1800050c4  jmp     loc_180004FBC
```
