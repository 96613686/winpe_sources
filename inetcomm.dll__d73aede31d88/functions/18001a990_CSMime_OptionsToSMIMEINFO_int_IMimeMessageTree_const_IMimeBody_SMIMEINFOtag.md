# CSMime::OptionsToSMIMEINFO(int,IMimeMessageTree * const,IMimeBody *,SMIMEINFOtag *)

- ea: `0x18001a990`
- end: `0x18001b25b`
- name: `?OptionsToSMIMEINFO@CSMime@@KAJHQEAUIMimeMessageTree@@PEAUIMimeBody@@PEAUSMIMEINFOtag@@@Z`
- size: `2251`
- prototype: `static int(int, struct IMimeMessageTree *const, struct IMimeBody *, struct SMIMEINFOtag *)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18001a4bc`
- `0x180039868`

## callees

- `0x18001a990`
- `0x180023b48`
- `0x1800299d0`
- `0x18002c544`
- `0x180038534`
- `0x180038c44`
- `0x1800cc9ba`
- `0x1800cc9c6`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `MSOERT2!PszDupW` at `0x18001ab17`
- `MSOERT2!PszDupW` at `0x18001ab17`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18001adb8`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18001adb8`
- `CRYPT32!CertOpenStore` at `0x18001b20e`
- `CRYPT32!CertOpenStore` at `0x18001b20e`
- `CRYPT32!CertFreeCertificateContext` at `0x18001aba2`
- `CRYPT32!CertFreeCertificateContext` at `0x18001abf7`
- `CRYPT32!CertFreeCertificateContext` at `0x18001aba2`
- `CRYPT32!CertFreeCertificateContext` at `0x18001abf7`
- `CRYPT32!CertCloseStore` at `0x18001abd5`
- `CRYPT32!CertCloseStore` at `0x18001abd5`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18001b022`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18001b022`
- `CRYPT32!CryptEncodeObjectEx` at `0x18001adec`
- `CRYPT32!CryptEncodeObjectEx` at `0x18001adec`

## pseudocode

```c
__int64 __fastcall CSMime::OptionsToSMIMEINFO(
        int a1,
        struct IMimeMessageTree *const a2,
        __int64 (__fastcall ***a3)(struct IMimeBody *, GUID *, struct IMimeSecurity2 **),
        struct SMIMEINFOtag *a4)
{
  __int64 (__fastcall **v4)(struct IMimeBody *, GUID *, struct IMimeSecurity2 **); // rax
  struct IMimeBody *v5; // r14
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(struct IMimeBody *, GUID *, struct IMimeSecurity2 **); // rax
  __int64 v8; // r13
  __int64 v9; // rbx
  __int64 v10; // r12
  struct SMIMEINFOtag *v11; // rsi
  unsigned int v12; // r15d
  char *v13; // rbx
  __int64 v14; // rax
  int v16; // eax
  __int64 v17; // rdx
  __int64 j; // rbx
  const CERT_CONTEXT *v19; // rcx
  __int64 v20; // rdx
  unsigned int v21; // esi
  __int64 k; // rbx
  const CERT_CONTEXT *v23; // rcx
  __int64 v24; // rbx
  __int64 v25; // rsi
  __int64 v26; // rsi
  __int64 m; // rbx
  __int64 v28; // rsi
  __int64 n; // rbx
  bool v30; // sf
  __int64 v31; // rax
  __int64 v32; // rcx
  __int64 v33; // rax
  void *v34; // rcx
  __int64 v35; // rax
  __int64 v36; // rax
  CSECURITY_LAYER_DATA *v37; // rax
  CSECURITY_LAYER_DATA *v38; // rax
  CSECURITY_LAYER_DATA *v39; // r13
  __int64 v40; // rax
  int v41; // eax
  __int64 v42; // r14
  _QWORD *v43; // rsi
  int v44; // eax
  int v45; // edx
  __int64 v46; // rax
  int v47; // eax
  __int64 i; // r9
  __int64 v49; // rax
  unsigned int v51; // [rsp+40h] [rbp-C0h]
  __int128 v52; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v53; // [rsp+58h] [rbp-A8h]
  DWORD pcbEncoded; // [rsp+60h] [rbp-A0h] BYREF
  int v55; // [rsp+64h] [rbp-9Ch]
  unsigned int v56; // [rsp+68h] [rbp-98h]
  __int64 v57; // [rsp+70h] [rbp-90h]
  __int64 v58; // [rsp+78h] [rbp-88h]
  __int64 v59; // [rsp+80h] [rbp-80h]
  struct IMimeSecurity2 *v60; // [rsp+88h] [rbp-78h] BYREF
  HCERTSTORE hCertStore; // [rsp+90h] [rbp-70h]
  __int64 v62; // [rsp+98h] [rbp-68h]
  __int64 v63; // [rsp+A0h] [rbp-60h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+A8h] [rbp-58h] BYREF
  struct SMIMEINFOtag *v65; // [rsp+B0h] [rbp-50h]
  struct IMimeBody *v66; // [rsp+B8h] [rbp-48h]
  __int128 v67; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v68; // [rsp+D0h] [rbp-30h]
  __int128 *v69; // [rsp+E0h] [rbp-20h]
  char *Str1[2]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v71; // [rsp+F8h] [rbp-8h]
  _BYTE pvEncoded[56]; // [rsp+100h] [rbp+0h] BYREF

  v69 = 0;
  v53 = 0;
  v4 = *a3;
  v5 = (struct IMimeBody *)a3;
  v66 = (struct IMimeBody *)a3;
  pcbEncoded = 0;
  v56 = 0;
  v6 = 0;
  v7 = *v4;
  v8 = 0;
  SystemTimeAsFileTime = 0;
  v9 = 0;
  hCertStore = 0;
  v10 = 0;
  v57 = 0;
  v62 = 0;
  v11 = a4;
  v58 = 0;
  v63 = 0;
  v59 = 0;
  v60 = 0;
  v65 = a4;
  v68 = 0;
  v67 = 0;
  v52 = 0;
  v55 = v7((struct IMimeBody *)a3, &IID_IMimeSecurity2, &v60);
  v12 = v55;
  if ( v55 < 0 )
    goto LABEL_16;
  if ( a1
    && !(*(unsigned int (__fastcall **)(struct IMimeBody *, const char *, _QWORD))(*(_QWORD *)v5 + 176LL))(v5, "OID", 0) )
  {
    v71 = 0;
    *(_OWORD *)Str1 = 0;
    LOWORD(Str1[0]) = 30;
    if ( (*(int (__fastcall **)(struct IMimeBody *, const char *, _QWORD, char **))(*(_QWORD *)v5 + 88LL))(
           v5,
           "att:sub-content-type",
           0,
           Str1) < 0 )
      return 2147500037LL;
    v13 = Str1[1];
    if ( strcmp_0(Str1[1], "1.2.840.113549.1.7.1") )
    {
      *((_QWORD *)v11 + 9) = v13;
      if ( (*(int (__fastcall **)(struct IMimeBody *, _QWORD, __int64))(*(_QWORD *)v5 + 272LL))(
             v5,
             0,
             (__int64)v11 + 80) < 0 )
        return 2147500037LL;
    }
    v9 = 0;
  }
  if ( (*(int (__fastcall **)(struct IMimeBody *, __int64, __int128 *))(*(_QWORD *)v5 + 208LL))(v5, 4915231, &v52) < 0 )
    return 2147500037LL;
  if ( *((_QWORD *)&v52 + 1) )
  {
    v14 = PszDupW(*((_QWORD *)&v52 + 1));
    *((_QWORD *)v11 + 11) = v14;
    if ( !v14 )
      return 2147942414LL;
  }
  if ( (*(int (__fastcall **)(struct IMimeBody *, __int64, __int128 *))(*(_QWORD *)v5 + 208LL))(v5, 1572883, &v52) < 0 )
    return 2147500037LL;
  v16 = DWORD2(v52);
  *(_DWORD *)v11 = DWORD2(v52);
  if ( !a1 )
    goto LABEL_95;
  if ( v16 )
  {
    if ( !(_BYTE)v16 )
    {
      v12 = 839354;
      goto LABEL_16;
    }
    if ( (v16 & 0xFF000000) != 0 )
    {
      v12 = -2146644295;
      goto LABEL_16;
    }
    if ( *((_QWORD *)v11 + 9) && (v16 & 4) == 0 )
    {
      v12 = -2147024809;
      goto LABEL_16;
    }
    if ( (v16 & 0x2202) != 0 )
    {
      v55 = ConvertEncryptionLayer(v5, v60, v11);
      v12 = v55;
      if ( v55 < 0 )
        goto LABEL_16;
    }
    if ( (*(_DWORD *)v11 & 0x1101) != 0 )
    {
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      pcbEncoded = 50;
      if ( CryptEncodeObjectEx(1u, (LPCSTR)0x1E, &SystemTimeAsFileTime, 0, 0, pvEncoded, &pcbEncoded) )
      {
        DWORD2(v68) = 1;
        *(_QWORD *)&v68 = "1.2.840.113549.1.9.5";
        v69 = &v67;
        *((_QWORD *)&v67 + 1) = pvEncoded;
        LODWORD(v67) = pcbEncoded;
        v55 = (*(__int64 (__fastcall **)(struct IMimeSecurity2 *, __int64, __int64))(*(_QWORD *)v60 + 80LL))(
                v60,
                2,
                0xFFFFFFFFLL);
        v12 = v55;
        if ( v55 < 0 )
          goto LABEL_16;
      }
      if ( (*(int (__fastcall **)(struct IMimeBody *, __int64, __int128 *))(*(_QWORD *)v5 + 208LL))(v5, 4390931, &v52) >= 0 )
        v10 = DWORD2(v52);
      v30 = (*(int (__fastcall **)(struct IMimeBody *, __int64, __int128 *))(*(_QWORD *)v5 + 208LL))(v5, 2166805, &v52) < 0;
      v31 = *(_QWORD *)v5;
      v32 = 0;
      if ( !v30 )
        v32 = v53;
      v57 = v32;
      v30 = (*(int (__fastcall **)(struct IMimeBody *, __int64, __int128 *))(v31 + 208))(v5, 2359317, &v52) < 0;
      v33 = *(_QWORD *)v5;
      v34 = 0;
      if ( !v30 )
        v34 = (void *)*((_QWORD *)&v52 + 1);
      hCertStore = v34;
      if ( (*(int (__fastcall **)(struct IMimeBody *, __int64, __int128 *))(v33 + 208))(v5, 2428949, &v52) >= 0 )
      {
        v56 = DWORD2(v52);
        v62 = v53;
      }
      v30 = (*(int (__fastcall **)(struct IMimeBody *, __int64, __int128 *))(*(_QWORD *)v5 + 208LL))(v5, 1642508, &v52) < 0;
      v35 = *(_QWORD *)v5;
      if ( !v30 )
        v6 = v53;
      v58 = v6;
      v30 = (*(int (__fastcall **)(struct IMimeBody *, __int64, __int128 *))(v35 + 208))(v5, 2822156, &v52) < 0;
      v36 = *(_QWORD *)v5;
      if ( !v30 )
        v9 = v53;
      v59 = v9;
      if ( (*(int (__fastcall **)(struct IMimeBody *, __int64, __int128 *))(v36 + 208))(v5, 2756620, &v52) >= 0 )
        v8 = v53;
      v63 = v8;
      v37 = (CSECURITY_LAYER_DATA *)operator new(0xA8u);
      if ( !v37 )
        goto LABEL_104;
      v38 = CSECURITY_LAYER_DATA::CSECURITY_LAYER_DATA(v37);
      v39 = v38;
      if ( !v38 )
        goto LABEL_104;
      if ( !*((_QWORD *)v11 + 1) )
        *((_QWORD *)v11 + 1) = v38;
      v40 = *((_QWORD *)v11 + 3);
      *((_QWORD *)v39 + 19) = v40;
      if ( v40 )
        *(_QWORD *)(v40 + 144) = v39;
      v41 = *(_DWORD *)v11 & 0x1105;
      *((_QWORD *)v11 + 3) = v39;
      *((_DWORD *)v39 + 3) = v41;
      if ( !(unsigned int)MemAlloc((void **)v39 + 3, 96 * (int)v10) )
      {
LABEL_104:
        v12 = -2147024882;
        goto LABEL_16;
      }
      memset_0(*((void **)v39 + 3), 0, 96 * v10);
      *((_DWORD *)v39 + 5) = v10;
      v51 = 0;
      if ( (_DWORD)v10 )
      {
        v42 = 0;
        v43 = (_QWORD *)((char *)v39 + 24);
        do
        {
          *(_QWORD *)(96 * v42 + *v43 + 8) = CertDuplicateCertificateContext(*(PCCERT_CONTEXT *)(v57 + 8 * v42));
          HrCopyBlob((const struct tagBLOB *)(v6 + 8 + 24 * v42), (struct tagBLOB *)(96 * v42 + *v43 + 16LL));
          HrCopyBlob((const struct tagBLOB *)(v59 + 8 + 24 * v42), (struct tagBLOB *)(96 * v42 + *v43 + 48LL));
          HrCopyBlob((const struct tagBLOB *)(v63 + 8 + 24 * v42), (struct tagBLOB *)(96 * v42 + *v43 + 32LL));
          ++v42;
          ++v51;
        }
        while ( v51 < (unsigned int)v10 );
        v11 = v65;
        v5 = v66;
        v12 = v55;
        v6 = v58;
      }
      if ( (*(int (__fastcall **)(struct IMimeBody *, __int64, __int128 *))(*(_QWORD *)v5 + 208LL))(v5, 2359317, &v52) >= 0 )
        *((_QWORD *)v39 + 17) = *((_QWORD *)&v52 + 1);
    }
    v44 = (*(__int64 (__fastcall **)(struct IMimeBody *, __int64, __int128 *))(*(_QWORD *)v5 + 208LL))(
            v5,
            3342339,
            &v52);
    v45 = -1;
    if ( v44 >= 0 )
      v45 = DWORD2(v52);
    *((_DWORD *)v11 + 14) = v45;
LABEL_95:
    if ( (*(int (__fastcall **)(struct IMimeBody *, __int64, __int128 *))(*(_QWORD *)v5 + 208LL))(v5, 2560019, &v52) >= 0
      && v53 )
    {
      if ( DWORD2(v52) < 0x1FFFFFFF )
      {
        v46 = (*(__int64 (__fastcall **)(struct CMimeAllocator *, __int64))(*(_QWORD *)g_pMoleAlloc + 24LL))(
                g_pMoleAlloc,
                8LL * DWORD2(v52));
        *((_QWORD *)v11 + 5) = v46;
        if ( v46 )
        {
          v47 = DWORD2(v52);
          for ( i = 0; (unsigned int)i < DWORD2(v52); v47 = DWORD2(v52) )
          {
            *(_QWORD *)(*((_QWORD *)v11 + 5) + 8 * i) = *(_QWORD *)(v53 + 8 * i);
            i = (unsigned int)(i + 1);
          }
          *((_DWORD *)v11 + 8) = v47;
        }
        if ( v53 )
        {
          ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
          v53 = 0;
        }
      }
    }
    else
    {
      v49 = (*(__int64 (__fastcall **)(struct CMimeAllocator *, __int64))(*(_QWORD *)g_pMoleAlloc + 24LL))(
              g_pMoleAlloc,
              8);
      *((_QWORD *)v11 + 5) = v49;
      if ( v49 )
      {
        **((_QWORD **)v11 + 5) = CertOpenStore((LPCSTR)0xA, 0, 0, 0x11000u, L"My");
        if ( **((_QWORD **)v11 + 5) )
        {
          *((_DWORD *)v11 + 8) = 1;
        }
        else
        {
          (*(void (__fastcall **)(struct CMimeAllocator *))(*(_QWORD *)g_pMoleAlloc + 40LL))(g_pMoleAlloc);
          *((_QWORD *)v11 + 5) = 0;
        }
      }
    }
    goto LABEL_16;
  }
  v12 = 839345;
LABEL_16:
  if ( v60 )
    (*(void (__fastcall **)(struct IMimeSecurity2 *))(*(_QWORD *)v60 + 16LL))(v60);
  v17 = v57;
  if ( v57 )
  {
    for ( j = 0; (unsigned int)j < (unsigned int)v10; j = (unsigned int)(j + 1) )
    {
      v19 = *(const CERT_CONTEXT **)(v17 + 8 * j);
      if ( v19 )
      {
        CertFreeCertificateContext(v19);
        v17 = v57;
      }
    }
    ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
  }
  if ( hCertStore )
    CertCloseStore(hCertStore, 0);
  v20 = v62;
  if ( v62 )
  {
    v21 = v56;
    for ( k = 0; (unsigned int)k < v21; k = (unsigned int)(k + 1) )
    {
      v23 = *(const CERT_CONTEXT **)(v20 + 8 * k);
      if ( v23 )
      {
        CertFreeCertificateContext(v23);
        v20 = v62;
      }
    }
    ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
  }
  if ( v6 )
  {
    v24 = 0;
    if ( (_DWORD)v10 )
    {
      v25 = v58;
      do
      {
        if ( *(_QWORD *)(v25 + 24 * v24 + 16) )
        {
          ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
          *(_QWORD *)(v25 + 24 * v24 + 16) = 0;
        }
        v24 = (unsigned int)(v24 + 1);
      }
      while ( (unsigned int)v24 < (unsigned int)v10 );
      v6 = v25;
    }
    ((void (__fastcall *)(LPMALLOC, __int64))g_pMalloc->lpVtbl->Free)(g_pMalloc, v6);
  }
  v26 = v59;
  if ( v59 )
  {
    for ( m = 0; (unsigned int)m < (unsigned int)v10; m = (unsigned int)(m + 1) )
    {
      if ( *(_QWORD *)(v26 + 24 * m + 16) )
      {
        ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
        *(_QWORD *)(v26 + 24 * m + 16) = 0;
      }
    }
    ((void (__fastcall *)(LPMALLOC, __int64))g_pMalloc->lpVtbl->Free)(g_pMalloc, v26);
  }
  v28 = v63;
  if ( v63 )
  {
    for ( n = 0; (unsigned int)n < (unsigned int)v10; n = (unsigned int)(n + 1) )
    {
      if ( *(_QWORD *)(v28 + 24 * n + 16) )
      {
        ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
        *(_QWORD *)(v28 + 24 * n + 16) = 0;
      }
    }
    ((void (__fastcall *)(LPMALLOC, __int64))g_pMalloc->lpVtbl->Free)(g_pMalloc, v28);
  }
  return v12;
}

```

## disassembly

```asm
0x18001a990  mov     [rsp-8+arg_0], rbx
0x18001a995  push    rbp
0x18001a996  push    rsi
0x18001a997  push    rdi
0x18001a998  push    r12
0x18001a99a  push    r13
0x18001a99c  push    r14
0x18001a99e  push    r15
0x18001a9a0  lea     rbp, [rsp-40h]
0x18001a9a5  sub     rsp, 140h
0x18001a9ac  mov     rax, cs:__security_cookie
0x18001a9b3  xor     rax, rsp
0x18001a9b6  mov     [rbp+70h+var_38], rax
0x18001a9ba  xor     eax, eax
0x18001a9bc  mov     [rsp+170h+var_130], ecx
0x18001a9c0  xor     ecx, ecx
0x18001a9c2  mov     [rbp+70h+var_90], rax
0x18001a9c6  mov     [rsp+170h+var_118], rax
0x18001a9cb  lea     rdx, IID_IMimeSecurity2
0x18001a9d2  mov     rax, [r8]
0x18001a9d5  mov     r14, r8
0x18001a9d8  xorps   xmm0, xmm0
0x18001a9db  mov     [rbp+70h+var_B8], r8
0x18001a9df  mov     [rsp+170h+var_110], ecx
0x18001a9e3  lea     r8, [rbp+70h+var_E8]
0x18001a9e7  mov     [rsp+170h+var_108], ecx
0x18001a9eb  mov     edi, ecx
0x18001a9ed  mov     rax, [rax]
0x18001a9f0  mov     r13d, ecx
0x18001a9f3  mov     qword ptr [rbp+70h+SystemTimeAsFileTime.dwLowDateTime], rcx
0x18001a9f7  mov     ebx, ecx
0x18001a9f9  mov     [rbp+70h+hCertStore], rcx
0x18001a9fd  mov     r12d, ecx
0x18001aa00  mov     [rsp+170h+var_100], rcx
0x18001aa05  xorps   xmm1, xmm1
0x18001aa08  mov     [rbp+70h+var_D8], rcx
0x18001aa0c  mov     rsi, r9
0x18001aa0f  mov     [rsp+170h+var_F8], rcx
0x18001aa14  mov     [rbp+70h+var_D0], rcx
0x18001aa18  mov     [rbp+70h+var_F0], rcx
0x18001aa1c  mov     [rbp+70h+var_E8], rcx
0x18001aa20  mov     rcx, r14
0x18001aa23  mov     [rbp+70h+var_C0], r9
0x18001aa27  movups  [rbp+70h+var_A0], xmm0
0x18001aa2b  movups  [rbp+70h+var_B0], xmm0
0x18001aa2f  movups  [rsp+170h+var_128], xmm1
0x18001aa34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa39  mov     [rsp+170h+var_10C], eax
0x18001aa3d  mov     r15d, eax
0x18001aa40  test    eax, eax
0x18001aa42  js      loc_18001AB73
0x18001aa48  cmp     [rsp+170h+var_130], ebx
0x18001aa4c  jz      loc_18001AAE9
0x18001aa52  mov     rcx, [r14]
0x18001aa55  lea     rdx, aOid; "OID"
0x18001aa5c  xor     r8d, r8d
0x18001aa5f  mov     rax, [rcx+0B0h]
0x18001aa66  mov     rcx, r14
0x18001aa69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa6e  test    eax, eax
0x18001aa70  jnz     short loc_18001AAE9
0x18001aa72  xor     eax, eax
0x18001aa74  lea     r9, [rbp+70h+Str1]
0x18001aa78  mov     [rbp+70h+var_78], rax
0x18001aa7c  lea     rdx, STR_ATT_SUBTYPE; "att:sub-content-type"
0x18001aa83  xorps   xmm0, xmm0
0x18001aa86  lea     eax, [rbx+1Eh]
0x18001aa89  movups  xmmword ptr [rbp+70h+Str1], xmm0
0x18001aa8d  mov     word ptr [rbp+70h+Str1], ax
0x18001aa91  xor     r8d, r8d
0x18001aa94  mov     rax, [r14]
0x18001aa97  mov     rcx, r14
0x18001aa9a  mov     rax, [rax+58h]
0x18001aa9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aaa3  test    eax, eax
0x18001aaa5  js      loc_18001B251
0x18001aaab  mov     rbx, [rbp+70h+Str1+8]
0x18001aaaf  lea     rdx, String1; "1.2.840.113549.1.7.1"
0x18001aab6  mov     rcx, rbx; Str1
0x18001aab9  call    strcmp_0
0x18001aabe  test    eax, eax
0x18001aac0  jz      short loc_18001AAE6
0x18001aac2  mov     [rsi+48h], rbx
0x18001aac6  lea     r8, [rsi+50h]
0x18001aaca  mov     rax, [r14]
0x18001aacd  xor     edx, edx
0x18001aacf  mov     rcx, r14
0x18001aad2  mov     rax, [rax+110h]
0x18001aad9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aade  test    eax, eax
0x18001aae0  js      loc_18001B251
0x18001aae6  mov     rbx, rdi
0x18001aae9  mov     rax, [r14]
0x18001aaec  lea     r8, [rsp+170h+var_128]
0x18001aaf1  mov     edx, 4B001Fh
0x18001aaf6  mov     rcx, r14
0x18001aaf9  mov     rax, [rax+0D0h]
0x18001ab00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab05  test    eax, eax
0x18001ab07  js      loc_18001B251
0x18001ab0d  mov     rcx, qword ptr [rsp+170h+var_128+8]
0x18001ab12  test    rcx, rcx
0x18001ab15  jz      short loc_18001AB30
0x18001ab17  call    cs:__imp_PszDupW
0x18001ab1d  mov     [rsi+58h], rax
0x18001ab21  test    rax, rax
0x18001ab24  jnz     short loc_18001AB30
0x18001ab26  mov     eax, 8007000Eh
0x18001ab2b  jmp     loc_18001AD26
0x18001ab30  mov     rax, [r14]
0x18001ab33  lea     r8, [rsp+170h+var_128]
0x18001ab38  mov     edx, 180013h
0x18001ab3d  mov     rcx, r14
0x18001ab40  mov     rax, [rax+0D0h]
0x18001ab47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab4c  test    eax, eax
0x18001ab4e  js      loc_18001B251
0x18001ab54  mov     rax, qword ptr [rsp+170h+var_128+8]
0x18001ab59  mov     [rsi], eax
0x18001ab5b  cmp     [rsp+170h+var_130], edi
0x18001ab5f  jz      loc_18001B106
0x18001ab65  test    eax, eax
0x18001ab67  jnz     loc_18001AD4D
0x18001ab6d  mov     r15d, 0CCEB1h
0x18001ab73  mov     rcx, [rbp+70h+var_E8]
0x18001ab77  test    rcx, rcx
0x18001ab7a  jz      short loc_18001AB88
0x18001ab7c  mov     rax, [rcx]
0x18001ab7f  mov     rax, [rax+10h]
0x18001ab83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab88  mov     rdx, [rsp+170h+var_100]
0x18001ab8d  test    rdx, rdx
0x18001ab90  jz      short loc_18001ABC7
0x18001ab92  xor     ebx, ebx
0x18001ab94  test    r12d, r12d
0x18001ab97  jz      short loc_18001ABB4
0x18001ab99  mov     rcx, [rdx+rbx*8]; pCertContext
0x18001ab9d  test    rcx, rcx
0x18001aba0  jz      short loc_18001ABAD
0x18001aba2  call    cs:__imp_CertFreeCertificateContext
0x18001aba8  mov     rdx, [rsp+170h+var_100]
0x18001abad  inc     ebx
0x18001abaf  cmp     ebx, r12d
0x18001abb2  jb      short loc_18001AB99
0x18001abb4  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18001abbb  mov     rax, [rcx]
0x18001abbe  mov     rax, [rax+28h]
0x18001abc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001abc7  mov     rax, [rbp+70h+hCertStore]
0x18001abcb  test    rax, rax
0x18001abce  jz      short loc_18001ABDB
0x18001abd0  xor     edx, edx; dwFlags
0x18001abd2  mov     rcx, rax; hCertStore
0x18001abd5  call    cs:__imp_CertCloseStore
0x18001abdb  mov     rdx, [rbp+70h+var_D8]
0x18001abdf  test    rdx, rdx
0x18001abe2  jz      short loc_18001AC1A
0x18001abe4  mov     esi, [rsp+170h+var_108]
0x18001abe8  xor     ebx, ebx
0x18001abea  test    esi, esi
0x18001abec  jz      short loc_18001AC07
0x18001abee  mov     rcx, [rdx+rbx*8]; pCertContext
0x18001abf2  test    rcx, rcx
0x18001abf5  jz      short loc_18001AC01
0x18001abf7  call    cs:__imp_CertFreeCertificateContext
0x18001abfd  mov     rdx, [rbp+70h+var_D8]
0x18001ac01  inc     ebx
0x18001ac03  cmp     ebx, esi
0x18001ac05  jb      short loc_18001ABEE
0x18001ac07  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18001ac0e  mov     rax, [rcx]
0x18001ac11  mov     rax, [rax+28h]
0x18001ac15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac1a  test    rdi, rdi
0x18001ac1d  jz      short loc_18001AC75
0x18001ac1f  xor     ebx, ebx
0x18001ac21  test    r12d, r12d
0x18001ac24  jz      short loc_18001AC5F
0x18001ac26  mov     rsi, [rsp+170h+var_F8]
0x18001ac2b  lea     rdi, [rbx+rbx*2]
0x18001ac2f  mov     rdx, [rsi+rdi*8+10h]
0x18001ac34  test    rdx, rdx
0x18001ac37  jz      short loc_18001AC55
0x18001ac39  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18001ac40  mov     rax, [rcx]
0x18001ac43  mov     rax, [rax+28h]
0x18001ac47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac4c  mov     qword ptr [rsi+rdi*8+10h], 0
0x18001ac55  inc     ebx
0x18001ac57  cmp     ebx, r12d
0x18001ac5a  jb      short loc_18001AC2B
0x18001ac5c  mov     rdi, rsi
0x18001ac5f  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18001ac66  mov     rdx, rdi
0x18001ac69  mov     rax, [rcx]
0x18001ac6c  mov     rax, [rax+28h]
0x18001ac70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac75  mov     rsi, [rbp+70h+var_F0]
0x18001ac79  test    rsi, rsi
0x18001ac7c  jz      short loc_18001ACCC
0x18001ac7e  xor     ebx, ebx
0x18001ac80  test    r12d, r12d
0x18001ac83  jz      short loc_18001ACB6
0x18001ac85  lea     rdi, [rbx+rbx*2]
0x18001ac89  mov     rdx, [rsi+rdi*8+10h]
0x18001ac8e  test    rdx, rdx
0x18001ac91  jz      short loc_18001ACAF
0x18001ac93  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18001ac9a  mov     rax, [rcx]
0x18001ac9d  mov     rax, [rax+28h]
0x18001aca1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aca6  mov     qword ptr [rsi+rdi*8+10h], 0
0x18001acaf  inc     ebx
0x18001acb1  cmp     ebx, r12d
0x18001acb4  jb      short loc_18001AC85
0x18001acb6  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18001acbd  mov     rdx, rsi
0x18001acc0  mov     rax, [rcx]
0x18001acc3  mov     rax, [rax+28h]
0x18001acc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001accc  mov     rsi, [rbp+70h+var_D0]
0x18001acd0  test    rsi, rsi
0x18001acd3  jz      short loc_18001AD23
0x18001acd5  xor     ebx, ebx
0x18001acd7  test    r12d, r12d
0x18001acda  jz      short loc_18001AD0D
0x18001acdc  lea     rdi, [rbx+rbx*2]
0x18001ace0  mov     rdx, [rsi+rdi*8+10h]
0x18001ace5  test    rdx, rdx
0x18001ace8  jz      short loc_18001AD06
0x18001acea  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18001acf1  mov     rax, [rcx]
0x18001acf4  mov     rax, [rax+28h]
0x18001acf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001acfd  mov     qword ptr [rsi+rdi*8+10h], 0
0x18001ad06  inc     ebx
0x18001ad08  cmp     ebx, r12d
0x18001ad0b  jb      short loc_18001ACDC
0x18001ad0d  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18001ad14  mov     rdx, rsi
0x18001ad17  mov     rax, [rcx]
0x18001ad1a  mov     rax, [rax+28h]
0x18001ad1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad23  mov     eax, r15d
0x18001ad26  mov     rcx, [rbp+70h+var_38]
0x18001ad2a  xor     rcx, rsp; StackCookie
0x18001ad2d  call    __security_check_cookie
0x18001ad32  mov     rbx, [rsp+170h+arg_0]
0x18001ad3a  add     rsp, 140h
0x18001ad41  pop     r15
0x18001ad43  pop     r14
0x18001ad45  pop     r13
0x18001ad47  pop     r12
0x18001ad49  pop     rdi
0x18001ad4a  pop     rsi
0x18001ad4b  pop     rbp
0x18001ad4c  retn
0x18001ad4d  test    al, al
0x18001ad4f  jnz     short loc_18001AD5C
0x18001ad51  mov     r15d, 0CCEBAh
0x18001ad57  jmp     loc_18001AB73
0x18001ad5c  test    eax, 0FF000000h
0x18001ad61  jz      short loc_18001AD6E
0x18001ad63  mov     r15d, 800CCEB9h
0x18001ad69  jmp     loc_18001AB73
0x18001ad6e  cmp     [rsi+48h], rdi
0x18001ad72  jz      short loc_18001AD83
0x18001ad74  test    al, 4
0x18001ad76  jnz     short loc_18001AD83
0x18001ad78  mov     r15d, 80070057h
0x18001ad7e  jmp     loc_18001AB73
0x18001ad83  test    eax, 2202h
0x18001ad88  jz      short loc_18001ADA8
0x18001ad8a  mov     rdx, [rbp+70h+var_E8]; struct IMimeSecurity2 *
0x18001ad8e  mov     r8, rsi; struct SMIMEINFOtag *
0x18001ad91  mov     rcx, r14; struct IMimeBody *
0x18001ad94  call    ?ConvertEncryptionLayer@@YAJPEAUIMimeBody@@PEAUIMimeSecurity2@@PEAUSMIMEINFOtag@@@Z; ConvertEncryptionLayer(IMimeBody *,IMimeSecurity2 *,SMIMEINFOtag *)
0x18001ad99  mov     [rsp+170h+var_10C], eax
0x18001ad9d  mov     r15d, eax
0x18001ada0  test    eax, eax
0x18001ada2  js      loc_18001AB73
0x18001ada8  test    dword ptr [rsi], 1101h
0x18001adae  jz      loc_18001B0DD
0x18001adb4  lea     rcx, [rbp+70h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001adb8  call    cs:__imp_GetSystemTimeAsFileTime
0x18001adbe  xor     r9d, r9d; dwFlags
0x18001adc1  mov     [rsp+170h+var_110], 32h ; '2'
0x18001adc9  lea     rax, [rsp+170h+var_110]
0x18001adce  mov     [rsp+170h+pcbEncoded], rax; pcbEncoded
0x18001add3  lea     r8, [rbp+70h+SystemTimeAsFileTime]; pvStructInfo
0x18001add7  lea     rax, [rbp+70h+var_70]
0x18001addb  lea     edx, [r9+1Eh]; lpszStructType
0x18001addf  mov     [rsp+170h+pvEncoded], rax; pvEncoded
0x18001ade4  lea     ecx, [rdx-1Dh]; dwCertEncodingType
0x18001ade7  mov     [rsp+170h+pEncodePara], rdi; pEncodePara
0x18001adec  call    cs:__imp_CryptEncodeObjectEx
0x18001adf2  test    eax, eax
0x18001adf4  jz      short loc_18001AE52
0x18001adf6  mov     rcx, [rbp+70h+var_E8]
0x18001adfa  lea     rdx, [rbp+70h+var_A0]
  ... truncated ...
```
