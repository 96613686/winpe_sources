# CCAPIStm::BeginEncodeStreaming(SMIMEINFOtag * const)

- ea: `0x1800598e0`
- end: `0x18005a29d`
- name: `?BeginEncodeStreaming@CCAPIStm@@AEAAJQEAUSMIMEINFOtag@@@Z`
- size: `2493`
- prototype: `__int64 __fastcall(CCAPIStm *__hidden this, struct SMIMEINFOtag *const)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18005b5e8`
- `0x18005b70c`

## callees

- `0x1800145d0`
- `0x180023b48`
- `0x1800247c8`
- `0x1800598e0`
- `0x18005b70c`
- `0x18005cce4`
- `0x18005d024`
- `0x1800cc9ba`
- `0x1800cc9c6`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `MSOERT2!HrDecodeObject` at `0x180059cee`
- `MSOERT2!HrDecodeObject` at `0x180059d81`
- `MSOERT2!HrDecodeObject` at `0x180059df8`
- `MSOERT2!HrDecodeObject` at `0x180059fb2`
- `MSOERT2!HrDecodeObject` at `0x180059cee`
- `MSOERT2!HrDecodeObject` at `0x180059d81`
- `MSOERT2!HrDecodeObject` at `0x180059df8`
- `MSOERT2!HrDecodeObject` at `0x180059fb2`
- `MSOERT2!HrGetCertificateParam` at `0x180059e32`
- `MSOERT2!HrGetCertificateParam` at `0x180059e32`
- `ADVAPI32!CryptAcquireContextW` at `0x180059e64`
- `ADVAPI32!CryptAcquireContextW` at `0x180059e64`
- `ADVAPI32!CryptSetProvParam` at `0x180059e89`
- `ADVAPI32!CryptSetProvParam` at `0x180059e89`
- `CRYPT32!CryptMsgOpenToEncode` at `0x18005a254`
- `CRYPT32!CryptMsgOpenToEncode` at `0x18005a254`

## pseudocode

```c
__int64 __fastcall CCAPIStm::BeginEncodeStreaming(CCAPIStm *this, struct SMIMEINFOtag *const a2)
{
  struct SMIMEINFOtag *v2; // r13
  _QWORD *v4; // r12
  char *v5; // rsi
  __int64 v7; // rbx
  char v8; // r14
  void *v9; // rcx
  __int64 v10; // r14
  int inited; // ebx
  int v12; // eax
  __int64 v13; // r15
  _QWORD *v14; // r13
  struct CMimeAllocator *v15; // rcx
  __int64 j; // rdi
  _QWORD *v17; // rsi
  unsigned int k; // edi
  unsigned int m; // edi
  unsigned int v20; // ebx
  int v21; // eax
  int v22; // eax
  __int64 i; // rax
  __int64 v24; // r15
  char *v25; // rdx
  __int64 v26; // r13
  __int64 v27; // rax
  void *v28; // rdx
  __int64 v29; // r8
  __int64 v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // rcx
  void *v33; // rcx
  __int64 v34; // rdx
  _DWORD **v35; // rbx
  HCRYPTPROV *v36; // rbx
  const BYTE *v37; // r8
  __int64 v38; // rcx
  __int64 v39; // rax
  int v40; // ecx
  __int64 v41; // rcx
  char *v42; // rax
  __int64 v43; // rdx
  __int64 v44; // rax
  void *v45; // rcx
  struct CSECURITY_LAYER_DATA *v46; // r9
  __int64 v47; // r8
  const char *v48; // rdx
  const char *v49; // rcx
  const char *v50; // rdx
  CHAR *v51; // rcx
  HCRYPTMSG v52; // rax
  __int64 v53; // [rsp+40h] [rbp-C0h] BYREF
  int v54; // [rsp+48h] [rbp-B8h] BYREF
  void *v55; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwMsgType[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v57; // [rsp+60h] [rbp-A0h] BYREF
  void *v58; // [rsp+68h] [rbp-98h] BYREF
  int v59; // [rsp+70h] [rbp-90h]
  __int64 v60; // [rsp+78h] [rbp-88h] BYREF
  int *v61; // [rsp+80h] [rbp-80h] BYREF
  void *v62; // [rsp+88h] [rbp-78h] BYREF
  struct SMIMEINFOtag *v63; // [rsp+90h] [rbp-70h]
  struct _CMSG_STREAM_INFO pStreamInfo; // [rsp+98h] [rbp-68h] BYREF
  __int64 v65; // [rsp+B0h] [rbp-50h] BYREF
  _DWORD pvMsgEncodeInfo[2]; // [rsp+B8h] [rbp-48h] BYREF
  char *v67; // [rsp+C0h] [rbp-40h]
  int v68; // [rsp+C8h] [rbp-38h]
  int v69; // [rsp+CCh] [rbp-34h]
  __int64 v70; // [rsp+D0h] [rbp-30h]
  int v71; // [rsp+D8h] [rbp-28h]
  int v72; // [rsp+DCh] [rbp-24h]
  __int64 v73; // [rsp+E0h] [rbp-20h]
  int v74; // [rsp+E8h] [rbp-18h]
  __int64 v75; // [rsp+F8h] [rbp-8h]
  int v76; // [rsp+100h] [rbp+0h]
  __int64 v77; // [rsp+108h] [rbp+8h]
  int v78; // [rsp+110h] [rbp+10h]
  __int64 v79; // [rsp+118h] [rbp+18h]
  int v80; // [rsp+130h] [rbp+30h]
  __int64 v81; // [rsp+138h] [rbp+38h]
  _BYTE v82[4]; // [rsp+140h] [rbp+40h] BYREF
  int v83; // [rsp+144h] [rbp+44h]
  int v84; // [rsp+154h] [rbp+54h]

  v63 = a2;
  v2 = a2;
  v54 = 0;
  v57 = 0;
  v60 = 0;
  v61 = 0;
  v62 = 0;
  memset(&pStreamInfo, 0, sizeof(pStreamInfo));
  v4 = 0;
  v58 = 0;
  v55 = 0;
  memset_0(&v65, 0, 0x90u);
  *((_DWORD *)this + 3) = 6;
  v5 = 0;
  *(_QWORD *)dwMsgType = 0;
  if ( !v2 )
    return 2147500035LL;
  v7 = *((_QWORD *)this + 12);
  v8 = *(_DWORD *)(v7 + 12);
  if ( !v8 )
    return 2148322993LL;
  if ( (*((_DWORD *)this + 16) & 0xFFFD) != 0 )
    return 2147942487LL;
  v53 = 0;
  memset_0(pvMsgEncodeInfo, 0, 0x88u);
  if ( (v8 & 1) == 0 )
  {
    LODWORD(v10) = 0;
    *((_QWORD *)this + 4) = *((_QWORD *)v2 + 8);
    *((_QWORD *)v2 + 8) = 0;
    v41 = *((_QWORD *)this + 12);
    v42 = (char *)*((_QWORD *)this + 4);
    pvMsgEncodeInfo[0] = 136;
    v67 = v42;
    v68 = *(_DWORD *)(v41 + 40);
    v69 = *(_DWORD *)(v41 + 44);
    v70 = *(_QWORD *)(v41 + 48);
    v71 = *(_DWORD *)(v41 + 56);
    v72 = *(_DWORD *)(v41 + 60);
    v73 = *(_QWORD *)(v41 + 64);
    v74 = *(_DWORD *)(v41 + 32);
    v75 = *(_QWORD *)(v41 + 72);
    v43 = *(unsigned int *)(v41 + 80);
    if ( (_DWORD)v43 )
    {
      inited = HrDecodeObject(*(_QWORD *)(v41 + 88), v43, "1.3.6.1.4.1.311.16.1.1", 0, &v54, &v61);
      if ( inited < 0 )
        goto LABEL_12;
      v80 = *v61;
      v81 = *((_QWORD *)v61 + 1);
    }
    v44 = *((_QWORD *)this + 12);
    v59 = 0;
    dwMsgType[0] = 3;
    v45 = *(void **)(v44 + 96);
    if ( v45 )
    {
      inited = InitEncodedCert(v45, (__int64)&v57 + 4);
      if ( inited < 0 )
        goto LABEL_12;
      v13 = v53;
      v76 = v57;
      v77 = v65;
      v78 = HIDWORD(v57);
      v79 = v53;
    }
    else
    {
      v13 = v53;
    }
LABEL_73:
    v46 = *(struct CSECURITY_LAYER_DATA **)(*((_QWORD *)this + 12) + 152LL);
    if ( v46 )
    {
      inited = CCAPIStm::InitInner(this, v2, 0, v46);
      if ( inited < 0 )
        goto LABEL_13;
      if ( *((_QWORD *)this + 6) )
      {
        memset_0(v82, 0, 0xA8u);
        v83 = 1;
        v84 = 1;
        HrCreateInternetConverter((struct tagCONVINITINFO *)v82, (struct CInternetConverter **)this + 11);
        (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 6) + 32LL))(
          *((_QWORD *)this + 6),
          "Content-Type: application/x-pkcs7-mime; name=smime.p7m; smime-type=",
          67);
        if ( (*(_BYTE *)(*((_QWORD *)this + 12) + 12LL) & 2) != 0 )
        {
          v47 = 14;
          v48 = "enveloped-data";
        }
        else
        {
          v49 = (const char *)*((_QWORD *)v2 + 9);
          if ( v49 && !strcmp_0(v49, "1.2.840.113549.1.9.16.1.1") )
          {
            v47 = 14;
            v48 = "signed-receipt";
          }
          else
          {
            v47 = 11;
            v48 = "signed-data";
          }
        }
        (*(void (__fastcall **)(_QWORD, const char *, __int64, _QWORD))(**((_QWORD **)this + 6) + 32LL))(
          *((_QWORD *)this + 6),
          v48,
          v47,
          0);
        (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 6) + 32LL))(
          *((_QWORD *)this + 6),
          "\r\n",
          2);
        (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 6) + 32LL))(
          *((_QWORD *)this + 6),
          "Content-Transfer-Encoding",
          25);
        (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 6) + 32LL))(
          *((_QWORD *)this + 6),
          ": ",
          2);
        v50 = "base64";
        if ( !*((_QWORD *)this + 11) )
          v50 = "binary";
        (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 6) + 32LL))(
          *((_QWORD *)this + 6),
          v50,
          6);
        (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 6) + 32LL))(
          *((_QWORD *)this + 6),
          "\r\n",
          2);
        (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 6) + 32LL))(
          *((_QWORD *)this + 6),
          "Content-Disposition: attachment; filename=smime.p7m",
          51);
        (*(void (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 6) + 32LL))(
          *((_QWORD *)this + 6),
          "\r\n\r\n",
          4);
      }
    }
    MemAlloc((void **)this + 18, 0x1000u);
    v51 = (CHAR *)*((_QWORD *)v2 + 9);
    if ( v51 )
      pStreamInfo.cbContent = *((_DWORD *)v2 + 20);
    else
      pStreamInfo.cbContent = -1;
    pStreamInfo.pfnStreamOutput = (PFN_CMSG_STREAM_OUTPUT)CCAPIStm::CBStreamOutput;
    pStreamInfo.pvArg = this;
    v52 = CryptMsgOpenToEncode(0x10001u, v59 | 0x40u, dwMsgType[0], pvMsgEncodeInfo, v51, &pStreamInfo);
    *((_QWORD *)this + 3) = v52;
    if ( v52 )
    {
      *((_DWORD *)this + 3) = ((*((_DWORD *)this + 16) & 2) == 0) | 4;
      *((_DWORD *)this + 4) = *((_QWORD *)this + 6) != 0 ? 34 : 36;
      inited = 0;
      goto LABEL_13;
    }
LABEL_91:
    inited = HrGetLastError();
    goto LABEL_13;
  }
  v9 = *(void **)(v7 + 136);
  v10 = *(unsigned int *)(v7 + 20);
  v59 = ~(unsigned __int8)*(_DWORD *)(v7 + 12) & 4;
  if ( v9 )
  {
    inited = InitEncodedCertIncludingSigners(
               v9,
               v10,
               *(_QWORD *)(v7 + 24),
               (__int64)&v65,
               (__int64)&v57,
               (__int64)&v53,
               (__int64)&v57 + 4);
    if ( inited < 0 )
      goto LABEL_12;
  }
  v12 = MemAlloc((void **)dwMsgType, 168 * (int)v10);
  v5 = *(char **)dwMsgType;
  if ( !v12 )
  {
    inited = -2147024882;
LABEL_12:
    v13 = v53;
LABEL_13:
    v14 = v55;
    goto LABEL_14;
  }
  memset_0(*(void **)dwMsgType, 0, (unsigned int)(168 * v10));
  v20 = 8 * v10;
  v21 = MemAlloc(&v55, 8 * (int)v10);
  v14 = v55;
  if ( v21 )
  {
    memset_0(v55, 0, v20);
    if ( (unsigned int)MemAlloc(&v62, v20) )
    {
      memset_0(v62, 0, 8 * v10);
      v22 = MemAlloc(&v58, v20);
      v4 = v58;
      if ( v22 )
      {
        memset_0(v58, 0, 8 * v10);
        for ( i = 0; ; i = dwMsgType[0] + 1 )
        {
          dwMsgType[0] = i;
          if ( (unsigned int)i >= (unsigned int)v10 )
          {
            v39 = *((_QWORD *)this + 12);
            v13 = v53;
            v2 = v63;
            pvMsgEncodeInfo[0] = 48;
            v40 = *(_DWORD *)(v39 + 20);
            v68 = v57;
            v70 = v65;
            v71 = HIDWORD(v57);
            dwMsgType[0] = 2;
            pvMsgEncodeInfo[1] = v40;
            v67 = v5;
            v73 = v53;
            goto LABEL_73;
          }
          v24 = 168 * i;
          v25 = (char *)&v14[i];
          v26 = 96 * i;
          *(_DWORD *)&v5[v24] = 168;
          *(_QWORD *)&v5[v24 + 56] = 0;
          v27 = *((_QWORD *)this + 12);
          v58 = v25;
          inited = HrDecodeObject(
                     *(_QWORD *)(*(_QWORD *)(v27 + 24) + v26 + 24),
                     *(unsigned int *)(*(_QWORD *)(v27 + 24) + v26 + 16),
                     42,
                     0,
                     &v54,
                     v25);
          if ( inited < 0 )
            goto LABEL_12;
          v28 = v58;
          *(_QWORD *)&v5[v24 + 32] = **(_QWORD **)(*(_QWORD *)v58 + 8LL);
          *(_DWORD *)&v5[v24 + 40] = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v28 + 8LL) + 8LL);
          *(_QWORD *)&v5[v24 + 48] = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v28 + 8LL) + 16LL);
          v29 = *((_QWORD *)this + 12);
          if ( *(_DWORD *)(*(_QWORD *)(v29 + 24) + v26 + 32) )
          {
            v54 = 0;
            v30 = *(_QWORD *)(v29 + 24);
            v31 = *(unsigned int *)(v30 + v26 + 32);
            v32 = *(_QWORD *)(v30 + v26 + 40);
            v58 = (char *)v62 + 8 * dwMsgType[0];
            inited = HrDecodeObject(v32, v31, "1.3.6.1.4.1.311.16.1.1", 0, &v54, v58);
            if ( inited < 0 )
              goto LABEL_12;
            v33 = v58;
            if ( *(_QWORD *)v58 )
            {
              *(_DWORD *)&v5[v24 + 64] = **(_DWORD **)v58;
              *(_QWORD *)&v5[v24 + 72] = *(_QWORD *)(*(_QWORD *)v33 + 8LL);
            }
          }
          v34 = *((_QWORD *)this + 12);
          if ( *(_DWORD *)(*(_QWORD *)(v34 + 24) + v26 + 48) )
          {
            v54 = 0;
            v35 = (_DWORD **)&v4[dwMsgType[0]];
            HrDecodeObject(
              *(_QWORD *)(*(_QWORD *)(v34 + 24) + v26 + 56),
              *(unsigned int *)(*(_QWORD *)(v34 + 24) + v26 + 48),
              "1.3.6.1.4.1.311.16.1.1",
              0,
              &v54,
              v35);
            if ( *v35 )
            {
              *(_DWORD *)&v5[v24 + 80] = **v35;
              *(_QWORD *)&v5[v24 + 88] = *((_QWORD *)*v35 + 1);
            }
          }
          if ( (int)HrGetCertificateParam(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 12) + 24LL) + v26 + 8), 2, &v60) < 0 )
            break;
          v36 = (HCRYPTPROV *)((char *)this + 32);
          if ( !*((_QWORD *)this + 4)
            && !CryptAcquireContextW(
                  (HCRYPTPROV *)this + 4,
                  *(LPCWSTR *)v60,
                  *(LPCWSTR *)(v60 + 8),
                  *(_DWORD *)(v60 + 16),
                  *(_DWORD *)(v60 + 20)) )
          {
            break;
          }
          v37 = (const BYTE *)*((_QWORD *)v63 + 11);
          if ( v37 )
            CryptSetProvParam(*v36, 0x15u, v37, 0);
          v38 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 12) + 24LL) + v26 + 8) + 24LL);
          *(_QWORD *)&v5[v24 + 8] = v38;
          *(_QWORD *)&v5[v24 + 16] = *v36;
          *(_DWORD *)&v5[v24 + 24] = *(_DWORD *)(v60 + 40);
          if ( !strcmp_0(*(const char **)(v38 + 96), "1.3.14.3.2.12") )
            *(_QWORD *)&v5[v24 + 136] = "1.3.14.3.2.27";
          v14 = v55;
        }
        v13 = v53;
        goto LABEL_91;
      }
    }
  }
  v13 = v53;
  inited = -2147024882;
LABEL_14:
  ((void (__fastcall *)(LPMALLOC, __int64))g_pMalloc->lpVtbl->Free)(g_pMalloc, v60);
  v15 = g_pMoleAlloc;
  if ( v65 && g_pMoleAlloc )
  {
    (*(void (**)(void))(*(_QWORD *)g_pMoleAlloc + 40LL))();
    v15 = g_pMoleAlloc;
  }
  if ( v13 && v15 )
    (*(void (__fastcall **)(struct CMimeAllocator *, __int64))(*(_QWORD *)v15 + 40LL))(v15, v13);
  if ( v14 )
  {
    for ( j = 0; (unsigned int)j < (unsigned int)v10; j = (unsigned int)(j + 1) )
      ((void (__fastcall *)(LPMALLOC, _QWORD))g_pMalloc->lpVtbl->Free)(g_pMalloc, v14[j]);
    ((void (__fastcall *)(LPMALLOC, _QWORD *))g_pMalloc->lpVtbl->Free)(g_pMalloc, v14);
  }
  if ( v5 )
    ((void (__fastcall *)(LPMALLOC, char *))g_pMalloc->lpVtbl->Free)(g_pMalloc, v5);
  if ( v61 )
  {
    ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
    v61 = 0;
  }
  v17 = v62;
  if ( v62 )
  {
    for ( k = 0; k < (unsigned int)v10; ++k )
    {
      if ( v17[k] )
      {
        ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
        v17[k] = 0;
      }
    }
  }
  if ( v4 )
  {
    for ( m = 0; m < (unsigned int)v10; ++m )
    {
      if ( v4[m] )
      {
        ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
        v4[m] = 0;
      }
    }
  }
  if ( v17 )
    ((void (__fastcall *)(LPMALLOC, _QWORD *))g_pMalloc->lpVtbl->Free)(g_pMalloc, v17);
  if ( v4 )
    ((void (__fastcall *)(LPMALLOC, _QWORD *))g_pMalloc->lpVtbl->Free)(g_pMalloc, v4);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1800598e0  mov     [rsp-8+arg_10], rbx
0x1800598e5  push    rbp
0x1800598e6  push    rsi
0x1800598e7  push    rdi
0x1800598e8  push    r12
0x1800598ea  push    r13
0x1800598ec  push    r14
0x1800598ee  push    r15
0x1800598f0  lea     rbp, [rsp-100h]
0x1800598f8  sub     rsp, 200h
0x1800598ff  mov     rax, cs:__security_cookie
0x180059906  xor     rax, rsp
0x180059909  mov     [rbp+130h+var_40], rax
0x180059910  xor     r15d, r15d
0x180059913  mov     [rbp+130h+var_1A0], rdx
0x180059917  mov     r13, rdx
0x18005991a  mov     [rsp+230h+var_1E8], r15d
0x18005991f  mov     rdi, rcx
0x180059922  mov     dword ptr [rsp+230h+var_1D0+4], r15d
0x180059927  xorps   xmm0, xmm0
0x18005992a  mov     dword ptr [rsp+230h+var_1D0], r15d
0x18005992f  xor     eax, eax
0x180059931  mov     [rsp+230h+var_1B8], r15
0x180059936  xor     edx, edx; Val
0x180059938  mov     [rbp+130h+var_198.pvArg], rax
0x18005993c  lea     rcx, [rbp+130h+var_180]; void *
0x180059940  mov     [rbp+130h+var_1B0], r15
0x180059944  mov     r8d, 90h; Size
0x18005994a  mov     [rbp+130h+var_1A8], r15
0x18005994e  movups  xmmword ptr [rbp+130h+var_198.cbContent], xmm0
0x180059952  mov     r12d, r15d
0x180059955  mov     [rsp+230h+var_1C8], r15
0x18005995a  mov     [rsp+230h+var_1E0], r15
0x18005995f  call    memset_0
0x180059964  mov     dword ptr [rdi+0Ch], 6
0x18005996b  mov     esi, r15d
0x18005996e  mov     qword ptr [rsp+230h+dwMsgType], r15
0x180059973  test    r13, r13
0x180059976  jnz     short loc_180059982
0x180059978  mov     eax, 80004003h
0x18005997d  jmp     loc_180059BD1
0x180059982  mov     rbx, [rdi+60h]
0x180059986  mov     r14d, [rbx+0Ch]
0x18005998a  and     r14d, 0FFh
0x180059991  jnz     short loc_18005999D
0x180059993  mov     eax, 800CCEB1h
0x180059998  jmp     loc_180059BD1
0x18005999d  test    dword ptr [rdi+40h], 0FFFDh
0x1800599a4  jz      short loc_1800599B0
0x1800599a6  mov     eax, 80070057h
0x1800599ab  jmp     loc_180059BD1
0x1800599b0  xor     edx, edx; Val
0x1800599b2  mov     [rsp+230h+var_1F0], r15
0x1800599b7  mov     r8d, 88h; Size
0x1800599bd  lea     rcx, [rbp+130h+pvMsgEncodeInfo]; void *
0x1800599c1  call    memset_0
0x1800599c6  test    r14b, 1
0x1800599ca  jz      loc_180059F32
0x1800599d0  mov     eax, [rbx+0Ch]
0x1800599d3  mov     rcx, [rbx+88h]; hCertStore
0x1800599da  not     eax
0x1800599dc  mov     r14d, [rbx+14h]
0x1800599e0  and     eax, 4
0x1800599e3  mov     [rsp+230h+var_1C0], eax
0x1800599e7  test    rcx, rcx
0x1800599ea  jz      short loc_180059A20
0x1800599ec  mov     r8, [rbx+18h]
0x1800599f0  lea     rax, [rsp+230h+var_1D0+4]
0x1800599f5  mov     [rsp+230h+var_200], rax; __int64
0x1800599fa  lea     r9, [rbp+130h+var_180]
0x1800599fe  lea     rax, [rsp+230h+var_1F0]
0x180059a03  mov     edx, r14d
0x180059a06  mov     [rsp+230h+pStreamInfo], rax; __int64
0x180059a0b  lea     rax, [rsp+230h+var_1D0]
0x180059a10  mov     qword ptr [rsp+230h+dwFlags], rax; __int64
0x180059a15  call    _InitEncodedCertIncludingSigners
0x180059a1a  mov     ebx, eax
0x180059a1c  test    eax, eax
0x180059a1e  js      short loc_180059A45
0x180059a20  imul    ebx, r14d, 0A8h
0x180059a27  lea     rcx, [rsp+230h+dwMsgType]; void **
0x180059a2c  mov     edx, ebx; unsigned int
0x180059a2e  call    ?MemAlloc@@YAHPEAPEAXK@Z; MemAlloc(void * *,ulong)
0x180059a33  mov     rsi, qword ptr [rsp+230h+dwMsgType]
0x180059a38  test    eax, eax
0x180059a3a  jnz     loc_180059BFB
0x180059a40  mov     ebx, 8007000Eh
0x180059a45  mov     r15, [rsp+230h+var_1F0]
0x180059a4a  mov     r13, [rsp+230h+var_1E0]
0x180059a4f  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x180059a56  mov     rdx, [rsp+230h+var_1B8]
0x180059a5b  mov     rax, [rcx]
0x180059a5e  mov     rax, [rax+28h]
0x180059a62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059a67  mov     rdx, [rbp+130h+var_180]
0x180059a6b  mov     rcx, cs:?g_pMoleAlloc@@3PEAVCMimeAllocator@@EA; CMimeAllocator * g_pMoleAlloc
0x180059a72  test    rdx, rdx
0x180059a75  jz      short loc_180059A8F
0x180059a77  test    rcx, rcx
0x180059a7a  jz      short loc_180059A8F
0x180059a7c  mov     rax, [rcx]
0x180059a7f  mov     rax, [rax+28h]
0x180059a83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059a88  mov     rcx, cs:?g_pMoleAlloc@@3PEAVCMimeAllocator@@EA; CMimeAllocator * g_pMoleAlloc
0x180059a8f  test    r15, r15
0x180059a92  jz      short loc_180059AA8
0x180059a94  test    rcx, rcx
0x180059a97  jz      short loc_180059AA8
0x180059a99  mov     rax, [rcx]
0x180059a9c  mov     rdx, r15
0x180059a9f  mov     rax, [rax+28h]
0x180059aa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059aa8  test    r13, r13
0x180059aab  jz      short loc_180059AE9
0x180059aad  xor     edi, edi
0x180059aaf  test    r14d, r14d
0x180059ab2  jz      short loc_180059AD3
0x180059ab4  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x180059abb  mov     rdx, [r13+rdi*8+0]
0x180059ac0  mov     rax, [rcx]
0x180059ac3  mov     rax, [rax+28h]
0x180059ac7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059acc  inc     edi
0x180059ace  cmp     edi, r14d
0x180059ad1  jb      short loc_180059AB4
0x180059ad3  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x180059ada  mov     rdx, r13
0x180059add  mov     rax, [rcx]
0x180059ae0  mov     rax, [rax+28h]
0x180059ae4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059ae9  xor     r13d, r13d
0x180059aec  test    rsi, rsi
0x180059aef  jz      short loc_180059B07
0x180059af1  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x180059af8  mov     rdx, rsi
0x180059afb  mov     rax, [rcx]
0x180059afe  mov     rax, [rax+28h]
0x180059b02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059b07  mov     rdx, [rbp+130h+var_1B0]
0x180059b0b  test    rdx, rdx
0x180059b0e  jz      short loc_180059B27
0x180059b10  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x180059b17  mov     rax, [rcx]
0x180059b1a  mov     rax, [rax+28h]
0x180059b1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059b23  mov     [rbp+130h+var_1B0], r13
0x180059b27  mov     rsi, [rbp+130h+var_1A8]
0x180059b2b  test    rsi, rsi
0x180059b2e  jz      short loc_180059B62
0x180059b30  mov     edi, r13d
0x180059b33  test    r14d, r14d
0x180059b36  jz      short loc_180059B62
0x180059b38  mov     r15d, edi
0x180059b3b  mov     rdx, [rsi+r15*8]
0x180059b3f  test    rdx, rdx
0x180059b42  jz      short loc_180059B5B
0x180059b44  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x180059b4b  mov     rax, [rcx]
0x180059b4e  mov     rax, [rax+28h]
0x180059b52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059b57  mov     [rsi+r15*8], r13
0x180059b5b  inc     edi
0x180059b5d  cmp     edi, r14d
0x180059b60  jb      short loc_180059B38
0x180059b62  test    r12, r12
0x180059b65  jz      short loc_180059B99
0x180059b67  mov     edi, r13d
0x180059b6a  test    r14d, r14d
0x180059b6d  jz      short loc_180059B99
0x180059b6f  mov     r15d, edi
0x180059b72  mov     rdx, [r12+r15*8]
0x180059b76  test    rdx, rdx
0x180059b79  jz      short loc_180059B92
0x180059b7b  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x180059b82  mov     rax, [rcx]
0x180059b85  mov     rax, [rax+28h]
0x180059b89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059b8e  mov     [r12+r15*8], r13
0x180059b92  inc     edi
0x180059b94  cmp     edi, r14d
0x180059b97  jb      short loc_180059B6F
0x180059b99  test    rsi, rsi
0x180059b9c  jz      short loc_180059BB4
0x180059b9e  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x180059ba5  mov     rdx, rsi
0x180059ba8  mov     rax, [rcx]
0x180059bab  mov     rax, [rax+28h]
0x180059baf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059bb4  test    r12, r12
0x180059bb7  jz      short loc_180059BCF
0x180059bb9  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x180059bc0  mov     rdx, r12
0x180059bc3  mov     rax, [rcx]
0x180059bc6  mov     rax, [rax+28h]
0x180059bca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059bcf  mov     eax, ebx
0x180059bd1  mov     rcx, [rbp+130h+var_40]
0x180059bd8  xor     rcx, rsp; StackCookie
0x180059bdb  call    __security_check_cookie
0x180059be0  mov     rbx, [rsp+230h+arg_10]
0x180059be8  add     rsp, 200h
0x180059bef  pop     r15
0x180059bf1  pop     r14
0x180059bf3  pop     r13
0x180059bf5  pop     r12
0x180059bf7  pop     rdi
0x180059bf8  pop     rsi
0x180059bf9  pop     rbp
0x180059bfa  retn
0x180059bfb  mov     r8d, ebx; Size
0x180059bfe  xor     edx, edx; Val
0x180059c00  mov     rcx, rsi; void *
0x180059c03  call    memset_0
0x180059c08  lea     ebx, ds:0[r14*8]
0x180059c10  mov     edx, ebx; unsigned int
0x180059c12  lea     rcx, [rsp+230h+var_1E0]; void **
0x180059c17  call    ?MemAlloc@@YAHPEAPEAXK@Z; MemAlloc(void * *,ulong)
0x180059c1c  mov     r13, [rsp+230h+var_1E0]
0x180059c21  test    eax, eax
0x180059c23  jnz     short loc_180059C34
0x180059c25  mov     r15, [rsp+230h+var_1F0]
0x180059c2a  mov     ebx, 8007000Eh
0x180059c2f  jmp     loc_180059A4F
0x180059c34  mov     r8d, ebx; Size
0x180059c37  xor     edx, edx; Val
0x180059c39  mov     rcx, r13; void *
0x180059c3c  call    memset_0
0x180059c41  mov     edx, ebx; unsigned int
0x180059c43  lea     rcx, [rbp+130h+var_1A8]; void **
0x180059c47  call    ?MemAlloc@@YAHPEAPEAXK@Z; MemAlloc(void * *,ulong)
0x180059c4c  test    eax, eax
0x180059c4e  jz      short loc_180059C25
0x180059c50  mov     rcx, [rbp+130h+var_1A8]; void *
0x180059c54  mov     r15, r14
0x180059c57  shl     r15, 3
0x180059c5b  xor     edx, edx; Val
0x180059c5d  mov     r8, r15; Size
0x180059c60  call    memset_0
0x180059c65  mov     edx, ebx; unsigned int
0x180059c67  lea     rcx, [rsp+230h+var_1C8]; void **
0x180059c6c  call    ?MemAlloc@@YAHPEAPEAXK@Z; MemAlloc(void * *,ulong)
0x180059c71  mov     r12, [rsp+230h+var_1C8]
0x180059c76  test    eax, eax
0x180059c78  jz      short loc_180059C25
0x180059c7a  mov     r8, r15; Size
0x180059c7d  xor     edx, edx; Val
0x180059c7f  mov     rcx, r12; void *
0x180059c82  call    memset_0
0x180059c87  xor     eax, eax
0x180059c89  mov     [rsp+230h+dwMsgType], eax
0x180059c8d  cmp     eax, r14d
0x180059c90  jnb     loc_180059EED
0x180059c96  imul    r15, rax, 0A8h
0x180059c9d  lea     rdx, ds:0[rax*8]
0x180059ca5  xor     r9d, r9d
0x180059ca8  add     rdx, r13
0x180059cab  lea     r13, [rax+rax*2]
0x180059caf  mov     [rsp+230h+pStreamInfo], rdx
0x180059cb4  shl     r13, 5
0x180059cb8  mov     dword ptr [r15+rsi], 0A8h
0x180059cc0  lea     r8d, [r9+2Ah]
0x180059cc4  mov     qword ptr [r15+rsi+38h], 0
0x180059ccd  mov     rax, [rdi+60h]
0x180059cd1  mov     [rsp+230h+var_1C8], rdx
0x180059cd6  mov     rcx, [rax+18h]
0x180059cda  lea     rax, [rsp+230h+var_1E8]
0x180059cdf  mov     qword ptr [rsp+230h+dwFlags], rax
0x180059ce4  mov     edx, [rcx+r13+10h]
0x180059ce9  mov     rcx, [rcx+r13+18h]
0x180059cee  call    cs:__imp_HrDecodeObject
0x180059cf4  mov     ebx, eax
0x180059cf6  test    eax, eax
0x180059cf8  js      loc_180059A45
0x180059cfe  mov     rdx, [rsp+230h+var_1C8]
0x180059d03  mov     rax, [rdx]
0x180059d06  mov     rcx, [rax+8]
0x180059d0a  mov     rax, [rcx]
0x180059d0d  mov     [r15+rsi+20h], rax
0x180059d12  mov     rax, [rdx]
0x180059d15  mov     rcx, [rax+8]
0x180059d19  mov     eax, [rcx+8]
0x180059d1c  mov     [r15+rsi+28h], eax
0x180059d21  mov     rax, [rdx]
0x180059d24  mov     rcx, [rax+8]
0x180059d28  mov     rax, [rcx+10h]
0x180059d2c  mov     [r15+rsi+30h], rax
0x180059d31  mov     r8, [rdi+60h]
0x180059d35  mov     rax, [r8+18h]
0x180059d39  cmp     dword ptr [rax+r13+20h], 0
0x180059d3f  jz      short loc_180059DB1
0x180059d41  mov     edx, [rsp+230h+dwMsgType]
0x180059d45  xor     r9d, r9d
0x180059d48  mov     rax, [rbp+130h+var_1A8]
0x180059d4c  mov     [rsp+230h+var_1E8], 0
0x180059d54  mov     rcx, [r8+18h]
0x180059d58  lea     r8, szStructType; "1.3.6.1.4.1.311.16.1.1"
0x180059d5f  lea     rax, [rax+rdx*8]
0x180059d63  mov     [rsp+230h+pStreamInfo], rax
0x180059d68  mov     edx, [rcx+r13+20h]
0x180059d6d  mov     rcx, [rcx+r13+28h]
  ... truncated ...
```
