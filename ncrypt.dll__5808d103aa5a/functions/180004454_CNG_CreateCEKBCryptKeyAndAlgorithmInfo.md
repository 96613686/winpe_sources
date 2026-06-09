# CNG_CreateCEKBCryptKeyAndAlgorithmInfo

- ea: `0x180004454`
- end: `0x180004a6a`
- name: `CNG_CreateCEKBCryptKeyAndAlgorithmInfo`
- size: `1558`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800050d0`

## callees

- `0x180004454`
- `0x180005fa0`
- `0x180006be4`
- `0x18000d02c`
- `0x18000e120`
- `0x180015c4c`
- `0x18001f145`
- `0x18001f175`
- `0x18001f18d`
- `0x18001f1b0`
- `0x180020010`

## import_xrefs

- `bcrypt!BCryptGenRandom` at `0x1800045fa`
- `bcrypt!BCryptGenRandom` at `0x1800048dd`
- `bcrypt!BCryptGenRandom` at `0x1800049ae`
- `bcrypt!BCryptGenRandom` at `0x1800045fa`
- `bcrypt!BCryptGenRandom` at `0x1800048dd`
- `bcrypt!BCryptGenRandom` at `0x1800049ae`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18000476a`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18000476a`
- `bcrypt!BCryptSetProperty` at `0x180004502`
- `bcrypt!BCryptSetProperty` at `0x180004a55`
- `bcrypt!BCryptSetProperty` at `0x180004502`
- `bcrypt!BCryptSetProperty` at `0x180004a55`
- `NTASN1!__imp_RtlAsn1EncodeAndAllocate` at `0x180004648`
- `NTASN1!__imp_RtlAsn1EncodeAndAllocate` at `0x180004a1c`
- `NTASN1!__imp_RtlAsn1EncodeAndAllocate` at `0x180004648`
- `NTASN1!__imp_RtlAsn1EncodeAndAllocate` at `0x180004a1c`

## string_xrefs

- `0x1800046a8`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\util.c`
- `0x180004730`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\util.c`
- `0x1800048b2`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\util.c`
- `0x1800049c8`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\util.c`

## pseudocode

```c
__int64 __fastcall CNG_CreateCEKBCryptKeyAndAlgorithmInfo(unsigned int *a1, __int64 a2, __int64 a3)
{
  __int64 *v3; // r14
  UCHAR *v6; // rsi
  UCHAR *v7; // r8
  __int64 v8; // r9
  int v9; // edx
  unsigned int SymmetricKey; // ebx
  __int64 v11; // r14
  const wchar_t *v12; // rbx
  unsigned int v13; // eax
  void *v14; // rax
  size_t v15; // r8
  __int64 v16; // r14
  __int64 v17; // rax
  int v18; // eax
  _QWORD *v19; // rcx
  UCHAR *v21; // rax
  unsigned int BCryptOidInfo; // eax
  __int64 v23; // r9
  __int64 v24; // rcx
  ULONG v25; // r8d
  unsigned __int64 v26; // rbx
  __int64 v27; // rcx
  unsigned __int64 v28; // rcx
  void *v29; // rsp
  void *v30; // rsp
  UCHAR *v31; // rax
  unsigned int v32; // eax
  __int64 v33; // r9
  __int64 v34; // rax
  __int64 v35; // r9
  int v36; // eax
  void *v37; // rcx
  __int64 v38; // [rsp+0h] [rbp-40h] BYREF
  ULONG dwFlags[2]; // [rsp+20h] [rbp-20h]
  ULONG cbSecret[2]; // [rsp+28h] [rbp-18h]
  ULONG v41[4]; // [rsp+30h] [rbp-10h]
  __int64 v42; // [rsp+40h] [rbp+0h] BYREF
  __int128 v43; // [rsp+48h] [rbp+8h] BYREF
  int v44; // [rsp+58h] [rbp+18h]
  __int128 v45; // [rsp+60h] [rbp+20h] BYREF

  *(_QWORD *)a3 = a2;
  v3 = (__int64 *)(a3 + 24);
  v42 = 0;
  v45 = 0;
  if ( !*(_QWORD *)(a3 + 24) )
  {
    BCryptOidInfo = CNG_FindBCryptOidInfo(*((_QWORD *)a1 + 1), *a1, 1, a3 + 24);
    SymmetricKey = BCryptOidInfo;
    if ( BCryptOidInfo )
    {
      v23 = 605;
LABEL_51:
      v24 = BCryptOidInfo;
LABEL_53:
      DebugTraceError(v24, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\util.c", v23);
      return SymmetricKey;
    }
  }
  if ( *(_QWORD *)(a3 + 8) || (SymmetricKey = CNG_GetBCryptHandle(*(_QWORD *)(*v3 + 8), a3 + 8)) == 0 )
  {
    if ( !*(_QWORD *)(a3 + 40) )
    {
      *(_DWORD *)(a3 + 32) = *(_DWORD *)(*v3 + 56) >> 3;
      v21 = (UCHAR *)(*(__int64 (**)(void))(a2 + 8))();
      *(_QWORD *)(a3 + 40) = v21;
      if ( !v21 )
      {
        SymmetricKey = -2146893810;
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return SymmetricKey;
        v41[0] = 631;
        goto LABEL_33;
      }
      v25 = *(_DWORD *)(a3 + 32);
      *(_DWORD *)(a3 + 112) |= 4u;
      BCryptOidInfo = BCryptGenRandom(0, v21, v25, 2u);
      SymmetricKey = BCryptOidInfo;
      if ( BCryptOidInfo )
      {
        v23 = 645;
        goto LABEL_51;
      }
    }
    if ( !*(_QWORD *)(a3 + 16) )
    {
      SymmetricKey = BCryptGenerateSymmetricKey(
                       *(BCRYPT_ALG_HANDLE *)(a3 + 8),
                       (BCRYPT_KEY_HANDLE *)(a3 + 16),
                       0,
                       0,
                       *(PUCHAR *)(a3 + 40),
                       *(_DWORD *)(a3 + 32),
                       0);
      if ( SymmetricKey )
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return SymmetricKey;
        v41[0] = 663;
LABEL_24:
        *(_QWORD *)cbSecret = "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\util.c";
        dwFlags[0] = SymmetricKey;
LABEL_25:
        WPP_SF_sDsd(
          v19[2],
          v9,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\util.c",
          (unsigned int)"Status",
          dwFlags[0],
          *(__int64 *)cbSecret,
          v41[0]);
        return SymmetricKey;
      }
    }
    v6 = 0;
    if ( *(_DWORD *)(*v3 + 16) != 1 )
      goto LABEL_18;
    v7 = *(UCHAR **)(*v3 + 64);
    if ( v7 )
    {
      v8 = -1;
      do
        ++v8;
      while ( *(_WORD *)&v7[2 * v8] );
      SymmetricKey = BCryptSetProperty(*(BCRYPT_HANDLE *)(a3 + 16), L"ChainingMode", v7, 2 * v8 + 2, 0);
      if ( SymmetricKey )
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return SymmetricKey;
        v41[0] = 681;
        goto LABEL_24;
      }
    }
    v11 = *v3;
    v12 = *(const wchar_t **)(v11 + 64);
    if ( !v12 || !*v12 || !wcscmp_0(*(const wchar_t **)(v11 + 64), L"ChainingModeCBC") )
    {
      v26 = *(unsigned int *)(v11 + 60);
      if ( !*(_DWORD *)(v11 + 60)
        || v26 > g_ulMaxStackAllocSize
        || v26 + g_ulAdditionalProbeSize + 8 < v26
        || !(unsigned int)VerifyStackAvailable() )
      {
        goto LABEL_78;
      }
      v27 = v26 + 23;
      if ( v26 + 23 <= v26 + 8 )
        v27 = 0xFFFFFFFFFFFFFF0LL;
      v28 = v27 & 0xFFFFFFFFFFFFFFF0uLL;
      v29 = alloca(v28);
      v30 = alloca(v28);
      v6 = (UCHAR *)&v42;
      if ( &v38 == (__int64 *)-64LL || (LODWORD(v42) = 1801679955, (v6 = (UCHAR *)&v43) == 0) )
      {
LABEL_78:
        if ( v26 + 8 >= v26 )
        {
          v31 = (UCHAR *)((__int64 (*)(void))g_pfnAllocate)();
          v6 = v31;
          if ( v31 )
          {
            *(_DWORD *)v31 = 1885431112;
            v6 = v31 + 8;
          }
        }
      }
      if ( !v6 )
      {
        SymmetricKey = -2146893810;
        v23 = 698;
        v24 = 2148073486LL;
        goto LABEL_53;
      }
      v32 = BCryptGenRandom(0, v6, *(_DWORD *)(*(_QWORD *)(a3 + 24) + 60LL), 2u);
      SymmetricKey = v32;
      if ( v32 )
      {
        v33 = 710;
      }
      else
      {
        v34 = *(_QWORD *)(a3 + 24);
        *((_QWORD *)&v45 + 1) = v6;
        LODWORD(v45) = *(_DWORD *)(v34 + 60);
        v32 = RtlAsn1EncodeAndAllocate(ASN1_NCRYPT_MODULE_HANDLE, 6, 0, a2, a3 + 56, &v42, &v45);
        SymmetricKey = v32;
        if ( v32 )
        {
          v33 = 728;
        }
        else
        {
          v35 = *(_QWORD *)(a3 + 24);
          v36 = v42;
          *(_DWORD *)(a3 + 112) |= 2u;
          v37 = *(void **)(a3 + 16);
          *(_DWORD *)(a3 + 48) = v36;
          v32 = BCryptSetProperty(v37, L"IV", v6, *(_DWORD *)(v35 + 60), 0);
          SymmetricKey = v32;
          if ( !v32 )
          {
LABEL_18:
            SymmetricKey = 0;
            if ( !v6 )
              return SymmetricKey;
            goto LABEL_19;
          }
          v33 = 744;
        }
      }
      DebugTraceError(v32, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\util.c", v33);
LABEL_19:
      if ( *((_DWORD *)v6 - 2) == 1885431112 )
        ((void (*)(void))g_pfnFree)();
      return SymmetricKey;
    }
    if ( wcscmp_0(v12, L"ChainingModeGCM") )
    {
      SymmetricKey = -2146893783;
      v23 = 822;
      v24 = 2148073513LL;
      goto LABEL_53;
    }
    *(_DWORD *)(a3 + 64) = 152;
    v44 = 0;
    v43 = 0;
    v13 = *(_DWORD *)(v11 + 60) + 152;
    *(_DWORD *)(a3 + 64) = v13;
    v14 = (void *)(*(__int64 (__fastcall **)(_QWORD))(a2 + 8))(v13);
    *(_QWORD *)(a3 + 72) = v14;
    if ( v14 )
    {
      v15 = *(unsigned int *)(a3 + 64);
      *(_DWORD *)(a3 + 112) |= 8u;
      memset_0(v14, 0, v15);
      v16 = *(_QWORD *)(a3 + 72);
      *(_DWORD *)v16 = 88;
      *(_QWORD *)(v16 + 40) = v16 + 100;
      *(_DWORD *)(v16 + 4) = 1;
      *(_QWORD *)(v16 + 136) = v16 + 152;
      *(_QWORD *)(v16 + 8) = v16 + 88;
      *(_DWORD *)(v16 + 16) = 12;
      *(_DWORD *)(v16 + 48) = 16;
      *(_DWORD *)(v16 + 144) = *(_DWORD *)(*(_QWORD *)(a3 + 24) + 60LL);
      SymmetricKey = BCryptGenRandom(0, (PUCHAR)(v16 + 88), 0xCu, 2u);
      if ( SymmetricKey )
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v41[0] = 790;
          goto LABEL_24;
        }
        return SymmetricKey;
      }
      v17 = *(_QWORD *)(v16 + 8);
      *(_QWORD *)v41 = &v43;
      *((_QWORD *)&v43 + 1) = v17;
      LODWORD(v43) = *(_DWORD *)(v16 + 16);
      v44 = 16;
      SymmetricKey = RtlAsn1EncodeAndAllocate(ASN1_NCRYPT_MODULE_HANDLE, 27, 0, a2, a3 + 56, &v42, &v43);
      if ( SymmetricKey )
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return SymmetricKey;
        v41[0] = 809;
        goto LABEL_24;
      }
      v18 = v42;
      *(_DWORD *)(a3 + 112) |= 0x10000002u;
      *(_DWORD *)(a3 + 48) = v18;
      goto LABEL_18;
    }
    SymmetricKey = -2146893810;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return SymmetricKey;
    v41[0] = 764;
LABEL_33:
    *(_QWORD *)cbSecret = "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\util.c";
    dwFlags[0] = -2146893810;
    goto LABEL_25;
  }
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v41[0] = 618;
    goto LABEL_24;
  }
  return SymmetricKey;
}

```

## disassembly

```asm
0x180004454  push    rbp
0x180004456  push    rbx
0x180004457  push    rsi
0x180004458  push    rdi
0x180004459  push    r12
0x18000445b  push    r13
0x18000445d  push    r14
0x18000445f  push    r15
0x180004461  sub     rsp, 88h
0x180004468  lea     rbp, [rsp+40h]
0x18000446d  mov     rax, cs:__security_cookie
0x180004474  xor     rax, rbp
0x180004477  mov     [rbp+80h+var_48], rax
0x18000447b  xor     r12d, r12d
0x18000447e  mov     [r8], rdx
0x180004481  lea     r14, [r8+18h]
0x180004485  mov     [rbp+80h+var_80], r12
0x180004489  xorps   xmm0, xmm0
0x18000448c  mov     rdi, r8
0x18000448f  mov     r13, rdx
0x180004492  movups  [rbp+80h+var_60], xmm0
0x180004496  cmp     [r14], r12
0x180004499  jz      loc_180004872
0x18000449f  lea     rsi, [rdi+8]
0x1800044a3  cmp     [rsi], r12
0x1800044a6  jz      loc_1800047A8
0x1800044ac  cmp     [rdi+28h], r12
0x1800044b0  jz      loc_1800047EF
0x1800044b6  lea     r15, [rdi+10h]
0x1800044ba  cmp     [r15], r12
0x1800044bd  jz      loc_180004749
0x1800044c3  mov     r8, [r14]
0x1800044c6  mov     rsi, r12
0x1800044c9  cmp     dword ptr [r8+10h], 1
0x1800044ce  jnz     loc_180004665
0x1800044d4  mov     r8, [r8+40h]; pbInput
0x1800044d8  test    r8, r8
0x1800044db  jz      short loc_180004512
0x1800044dd  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800044e1  inc     r9
0x1800044e4  cmp     [r8+r9*2], r12w
0x1800044e9  jnz     short loc_1800044E1
0x1800044eb  mov     rcx, [r15]; hObject
0x1800044ee  lea     r9d, ds:2[r9*2]; cbInput
0x1800044f6  lea     rdx, pszProperty; "ChainingMode"
0x1800044fd  mov     [rsp+0C0h+dwFlags], r12d; dwFlags
0x180004502  call    cs:__imp_BCryptSetProperty
0x180004508  mov     ebx, eax
0x18000450a  test    eax, eax
0x18000450c  jnz     loc_180004687
0x180004512  mov     r14, [r14]
0x180004515  mov     rbx, [r14+40h]
0x180004519  test    rbx, rbx
0x18000451c  jz      loc_180004901
0x180004522  cmp     r12w, [rbx]
0x180004526  jz      loc_180004901
0x18000452c  lea     rdx, aChainingmodecb; "ChainingModeCBC"
0x180004533  mov     rcx, rbx; String1
0x180004536  call    wcscmp_0
0x18000453b  test    eax, eax
0x18000453d  jz      loc_180004901
0x180004543  lea     rdx, aChainingmodegc; "ChainingModeGCM"
0x18000454a  mov     rcx, rbx; String1
0x18000454d  call    wcscmp_0
0x180004552  test    eax, eax
0x180004554  jnz     loc_1800048EF
0x18000455a  xor     eax, eax
0x18000455c  mov     dword ptr [rdi+40h], 98h
0x180004563  mov     [rbp+80h+var_68], eax
0x180004566  xorps   xmm0, xmm0
0x180004569  movups  [rbp+80h+var_78], xmm0
0x18000456d  mov     eax, [r14+3Ch]
0x180004571  add     eax, 98h
0x180004576  mov     [rdi+40h], eax
0x180004579  mov     ecx, eax
0x18000457b  mov     rax, [r13+8]
0x18000457f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004584  mov     [rdi+48h], rax
0x180004588  test    rax, rax
0x18000458b  jz      loc_18000470A
0x180004591  mov     r8d, [rdi+40h]; Size
0x180004595  xor     edx, edx; Val
0x180004597  or      dword ptr [rdi+70h], 8
0x18000459b  mov     rcx, rax; void *
0x18000459e  call    memset_0
0x1800045a3  mov     r14, [rdi+48h]
0x1800045a7  mov     r8d, 0Ch; cbBuffer
0x1800045ad  mov     dword ptr [r14], 58h ; 'X'
0x1800045b4  lea     rax, [r14+64h]
0x1800045b8  mov     [r14+28h], rax
0x1800045bc  lea     rdx, [r14+58h]; pbBuffer
0x1800045c0  mov     dword ptr [r14+4], 1
0x1800045c8  lea     rax, [r14+98h]
0x1800045cf  mov     [r14+88h], rax
0x1800045d6  lea     r15d, [r8+4]
0x1800045da  mov     [r14+8], rdx
0x1800045de  lea     r9d, [r8-0Ah]; dwFlags
0x1800045e2  mov     [r14+10h], r8d
0x1800045e6  mov     [r14+30h], r15d
0x1800045ea  mov     rax, [rdi+18h]
0x1800045ee  mov     ecx, [rax+3Ch]
0x1800045f1  mov     [r14+90h], ecx
0x1800045f8  xor     ecx, ecx; hAlgorithm
0x1800045fa  call    cs:__imp_BCryptGenRandom
0x180004600  mov     ebx, eax
0x180004602  test    eax, eax
0x180004604  jnz     loc_180004844
0x18000460a  mov     rax, [r14+8]
0x18000460e  lea     rcx, [rbp+80h+var_78]
0x180004612  mov     qword ptr [rsp+0C0h+var_90], rcx
0x180004617  lea     edx, [rbx+1Bh]
0x18000461a  mov     qword ptr [rbp+80h+var_78+8], rax
0x18000461e  lea     rcx, [rbp+80h+var_80]
0x180004622  mov     eax, [r14+10h]
0x180004626  mov     r9, r13
0x180004629  mov     qword ptr [rsp+0C0h+cbSecret], rcx
0x18000462e  xor     r8d, r8d
0x180004631  mov     rcx, cs:ASN1_NCRYPT_MODULE_HANDLE
0x180004638  mov     dword ptr [rbp+80h+var_78], eax
0x18000463b  lea     rax, [rdi+38h]
0x18000463f  mov     qword ptr [rsp+0C0h+dwFlags], rax
0x180004644  mov     [rbp+80h+var_68], r15d
0x180004648  call    cs:__imp_RtlAsn1EncodeAndAllocate
0x18000464e  mov     ebx, eax
0x180004650  test    eax, eax
0x180004652  jnz     loc_1800046E7
0x180004658  mov     eax, dword ptr [rbp+80h+var_80]
0x18000465b  or      dword ptr [rdi+70h], 10000002h
0x180004662  mov     [rdi+30h], eax
0x180004665  mov     ebx, r12d
0x180004668  test    rsi, rsi
0x18000466b  jz      short loc_1800046C8
0x18000466d  lea     rcx, [rsi-8]
0x180004671  cmp     dword ptr [rcx], 70616548h
0x180004677  jnz     short loc_1800046C8
0x180004679  mov     rax, cs:g_pfnFree
0x180004680  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004685  jmp     short loc_1800046C8
0x180004687  mov     rcx, cs:WPP_GLOBAL_Control
0x18000468e  lea     rax, WPP_GLOBAL_Control
0x180004695  cmp     rcx, rax
0x180004698  jz      short loc_1800046C8
0x18000469a  test    byte ptr [rcx+1Ch], 1
0x18000469e  jz      short loc_1800046C8
0x1800046a0  mov     [rsp+0C0h+var_90], 2A9h
0x1800046a8  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800046af  mov     qword ptr [rsp+0C0h+cbSecret], r8
0x1800046b4  mov     [rsp+0C0h+dwFlags], ebx
0x1800046b8  mov     rcx, [rcx+10h]
0x1800046bc  lea     r9, aStatus; "Status"
0x1800046c3  call    WPP_SF_sDsd
0x1800046c8  mov     eax, ebx
0x1800046ca  mov     rcx, [rbp+80h+var_48]
0x1800046ce  xor     rcx, rbp; StackCookie
0x1800046d1  call    __security_check_cookie
0x1800046d6  lea     rsp, [rbp+48h]
0x1800046da  pop     r15
0x1800046dc  pop     r14
0x1800046de  pop     r13
0x1800046e0  pop     r12
0x1800046e2  pop     rdi
0x1800046e3  pop     rsi
0x1800046e4  pop     rbx
0x1800046e5  pop     rbp
0x1800046e6  retn
0x1800046e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800046ee  lea     rax, WPP_GLOBAL_Control
0x1800046f5  cmp     rcx, rax
0x1800046f8  jz      short loc_1800046C8
0x1800046fa  test    byte ptr [rcx+1Ch], 1
0x1800046fe  jz      short loc_1800046C8
0x180004700  mov     [rsp+0C0h+var_90], 329h
0x180004708  jmp     short loc_1800046A8
0x18000470a  mov     ebx, 8009000Eh
0x18000470f  mov     rcx, cs:WPP_GLOBAL_Control
0x180004716  lea     rax, WPP_GLOBAL_Control
0x18000471d  cmp     rcx, rax
0x180004720  jz      short loc_1800046C8
0x180004722  test    byte ptr [rcx+1Ch], 1
0x180004726  jz      short loc_1800046C8
0x180004728  mov     [rsp+0C0h+var_90], 2FCh
0x180004730  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180004737  mov     qword ptr [rsp+0C0h+cbSecret], r8
0x18000473c  mov     [rsp+0C0h+dwFlags], 8009000Eh
0x180004744  jmp     loc_1800046B8
0x180004749  mov     eax, [rdi+20h]
0x18000474c  xor     r9d, r9d; cbKeyObject
0x18000474f  mov     rcx, [rsi]; hAlgorithm
0x180004752  xor     r8d, r8d; pbKeyObject
0x180004755  mov     [rsp+0C0h+var_90], r12d; dwFlags
0x18000475a  mov     rdx, r15; phKey
0x18000475d  mov     [rsp+0C0h+cbSecret], eax; cbSecret
0x180004761  mov     rax, [rdi+28h]
0x180004765  mov     qword ptr [rsp+0C0h+dwFlags], rax; pbSecret
0x18000476a  call    cs:__imp_BCryptGenerateSymmetricKey
0x180004770  mov     ebx, eax
0x180004772  test    eax, eax
0x180004774  jz      loc_1800044C3
0x18000477a  mov     rcx, cs:WPP_GLOBAL_Control
0x180004781  lea     rax, WPP_GLOBAL_Control
0x180004788  cmp     rcx, rax
0x18000478b  jz      loc_1800046C8
0x180004791  test    byte ptr [rcx+1Ch], 1
0x180004795  jz      loc_1800046C8
0x18000479b  mov     [rsp+0C0h+var_90], 297h
0x1800047a3  jmp     loc_1800046A8
0x1800047a8  mov     rcx, [r14]
0x1800047ab  mov     rdx, rsi
0x1800047ae  mov     rcx, [rcx+8]
0x1800047b2  call    CNG_GetBCryptHandle
0x1800047b7  mov     ebx, eax
0x1800047b9  test    eax, eax
0x1800047bb  jz      loc_1800044AC
0x1800047c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800047c8  lea     rax, WPP_GLOBAL_Control
0x1800047cf  cmp     rcx, rax
0x1800047d2  jz      loc_1800046C8
0x1800047d8  test    byte ptr [rcx+1Ch], 1
0x1800047dc  jz      loc_1800046C8
0x1800047e2  mov     [rsp+0C0h+var_90], 26Ah
0x1800047ea  jmp     loc_1800046A8
0x1800047ef  mov     rax, [r14]
0x1800047f2  mov     ecx, [rax+38h]
0x1800047f5  shr     ecx, 3
0x1800047f8  mov     [rdi+20h], ecx
0x1800047fb  mov     rax, [r13+8]
0x1800047ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004804  mov     [rdi+28h], rax
0x180004808  test    rax, rax
0x18000480b  jnz     loc_1800048CA
0x180004811  mov     ebx, 8009000Eh
0x180004816  mov     rcx, cs:WPP_GLOBAL_Control
0x18000481d  lea     rax, WPP_GLOBAL_Control
0x180004824  cmp     rcx, rax
0x180004827  jz      loc_1800046C8
0x18000482d  test    byte ptr [rcx+1Ch], 1
0x180004831  jz      loc_1800046C8
0x180004837  mov     [rsp+0C0h+var_90], 277h
0x18000483f  jmp     loc_180004730
0x180004844  mov     rcx, cs:WPP_GLOBAL_Control
0x18000484b  lea     rax, WPP_GLOBAL_Control
0x180004852  cmp     rcx, rax
0x180004855  jz      loc_1800046C8
0x18000485b  test    byte ptr [rcx+1Ch], 1
0x18000485f  jz      loc_1800046C8
0x180004865  mov     [rsp+0C0h+var_90], 316h
0x18000486d  jmp     loc_1800046A8
0x180004872  mov     edx, [rcx]
0x180004874  mov     r9, r14
0x180004877  mov     rcx, [rcx+8]
0x18000487b  mov     r8d, 1
0x180004881  call    CNG_FindBCryptOidInfo
0x180004886  mov     ebx, eax
0x180004888  test    eax, eax
0x18000488a  jz      loc_18000449F
0x180004890  mov     r9d, 25Dh
0x180004896  jmp     short loc_18000489E
0x180004898  mov     r9d, 285h
0x18000489e  mov     ecx, eax
0x1800048a0  jmp     short loc_1800048B2
0x1800048a2  mov     ebx, 8009000Eh
0x1800048a7  mov     r9d, 2BAh
0x1800048ad  mov     ecx, 8009000Eh
0x1800048b2  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800048b9  lea     rdx, aStatus; "Status"
0x1800048c0  call    DebugTraceError
0x1800048c5  jmp     loc_1800046C8
0x1800048ca  mov     r8d, [rdi+20h]; cbBuffer
0x1800048ce  mov     r9d, 2; dwFlags
0x1800048d4  or      dword ptr [rdi+70h], 4
0x1800048d8  mov     rdx, rax; pbBuffer
0x1800048db  xor     ecx, ecx; hAlgorithm
0x1800048dd  call    cs:__imp_BCryptGenRandom
0x1800048e3  mov     ebx, eax
0x1800048e5  test    eax, eax
0x1800048e7  jz      loc_1800044B6
0x1800048ed  jmp     short loc_180004898
0x1800048ef  mov     ebx, 80090029h
0x1800048f4  mov     r9d, 336h
0x1800048fa  mov     ecx, 80090029h
0x1800048ff  jmp     short loc_1800048B2
0x180004901  mov     ebx, [r14+3Ch]
0x180004905  test    rbx, rbx
0x180004908  jz      short loc_18000496B
0x18000490a  cmp     rbx, cs:g_ulMaxStackAllocSize
0x180004911  ja      short loc_18000496B
0x180004913  mov     rcx, cs:g_ulAdditionalProbeSize
0x18000491a  add     rcx, 8
0x18000491e  add     rcx, rbx
0x180004921  cmp     rcx, rbx
0x180004924  jb      short loc_18000496B
0x180004926  call    VerifyStackAvailable
0x18000492b  test    eax, eax
0x18000492d  jz      short loc_18000496B
0x18000492f  lea     rax, [rbx+8]
0x180004933  lea     rcx, [rax+0Fh]
0x180004937  cmp     rcx, rax
0x18000493a  ja      short loc_180004946
0x18000493c  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180004946  and     rcx, 0FFFFFFFFFFFFFFF0h
  ... truncated ...
```
