# CCAPIStm::VerifySignedMessage(void)

- ea: `0x18005be40`
- end: `0x18005ca66`
- name: `?VerifySignedMessage@CCAPIStm@@AEAAJXZ`
- size: `3110`
- prototype: `__int64 __fastcall(CCAPIStm *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x18005a374`

## callees

- `0x180023b48`
- `0x1800247c8`
- `0x18002c4b0`
- `0x18005a2bc`
- `0x18005a5f0`
- `0x18005a9b0`
- `0x18005b1f0`
- `0x18005b8b8`
- `0x18005be40`
- `0x180092cfc`
- `0x1800cc996`
- `0x1800cc9a2`
- `0x1800cc9ba`
- `0x1800cc9c6`
- `0x1800cd010`

## import_xrefs

- `msvcrt!free` at `0x18005c654`
- `msvcrt!free` at `0x18005c654`
- `MSOERT2!HrGetMsgParam` at `0x18005c07c`
- `MSOERT2!HrGetMsgParam` at `0x18005c07c`
- `MSOERT2!PVGetMsgParam` at `0x18005c286`
- `MSOERT2!PVGetMsgParam` at `0x18005c7bb`
- `MSOERT2!PVGetMsgParam` at `0x18005c286`
- `MSOERT2!PVGetMsgParam` at `0x18005c7bb`
- `KERNEL32!lstrcmpA` at `0x18005c2a3`
- `KERNEL32!lstrcmpA` at `0x18005c2a3`
- `CRYPT32!CryptMsgControl` at `0x18005c11b`
- `CRYPT32!CryptMsgControl` at `0x18005c11b`
- `CRYPT32!CryptMsgGetParam` at `0x18005bf05`
- `CRYPT32!CryptMsgGetParam` at `0x18005bfc1`
- `CRYPT32!CryptMsgGetParam` at `0x18005bf05`
- `CRYPT32!CryptMsgGetParam` at `0x18005bfc1`
- `CRYPT32!CryptDecodeObjectEx` at `0x18005c46b`
- `CRYPT32!CryptDecodeObjectEx` at `0x18005c724`
- `CRYPT32!CryptDecodeObjectEx` at `0x18005c46b`
- `CRYPT32!CryptDecodeObjectEx` at `0x18005c724`
- `CRYPT32!CertOpenStore` at `0x18005bfeb`
- `CRYPT32!CertOpenStore` at `0x18005bfeb`
- `CRYPT32!CertFindCertificateInStore` at `0x18005c0c1`
- `CRYPT32!CertFindCertificateInStore` at `0x18005c1f6`
- `CRYPT32!CertFindCertificateInStore` at `0x18005c0c1`
- `CRYPT32!CertFindCertificateInStore` at `0x18005c1f6`
- `CRYPT32!CertFreeCertificateContext` at `0x18005c8bd`
- `CRYPT32!CertFreeCertificateContext` at `0x18005ca4a`
- `CRYPT32!CertFreeCertificateContext` at `0x18005c8bd`
- `CRYPT32!CertFreeCertificateContext` at `0x18005ca4a`
- `CRYPT32!CertCloseStore` at `0x18005c903`
- `CRYPT32!CertCloseStore` at `0x18005c99c`
- `CRYPT32!CertCloseStore` at `0x18005c9ad`
- `CRYPT32!CertCloseStore` at `0x18005c9be`
- `CRYPT32!CertCloseStore` at `0x18005c9cf`
- `CRYPT32!CertCloseStore` at `0x18005c9df`
- `CRYPT32!CertCloseStore` at `0x18005ca3c`
- `CRYPT32!CertCloseStore` at `0x18005c903`
- `CRYPT32!CertCloseStore` at `0x18005c99c`
- `CRYPT32!CertCloseStore` at `0x18005c9ad`
- `CRYPT32!CertCloseStore` at `0x18005c9be`
- `CRYPT32!CertCloseStore` at `0x18005c9cf`
- `CRYPT32!CertCloseStore` at `0x18005c9df`
- `CRYPT32!CertCloseStore` at `0x18005ca3c`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18005c0e5`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18005c0e5`
- `CRYPT32!CryptEncodeObjectEx` at `0x18005c2f0`
- `CRYPT32!CryptEncodeObjectEx` at `0x18005c78e`
- `CRYPT32!CryptEncodeObjectEx` at `0x18005c828`
- `CRYPT32!CryptEncodeObjectEx` at `0x18005c89c`
- `CRYPT32!CryptEncodeObjectEx` at `0x18005c2f0`
- `CRYPT32!CryptEncodeObjectEx` at `0x18005c78e`
- `CRYPT32!CryptEncodeObjectEx` at `0x18005c828`
- `CRYPT32!CryptEncodeObjectEx` at `0x18005c89c`
- `CRYPT32!CertDuplicateStore` at `0x18005c00a`
- `CRYPT32!CertDuplicateStore` at `0x18005c00a`

## pseudocode

```c
__int64 __fastcall CCAPIStm::VerifySignedMessage(CCAPIStm *this)
{
  void *v1; // r12
  void *v2; // r15
  void *v4; // rcx
  const CERT_CONTEXT *v5; // r13
  int MsgParam; // ebx
  __int64 v7; // rax
  DWORD *v8; // rdi
  __int64 i; // rdx
  __int64 v10; // rcx
  HCERTSTORE v11; // rax
  unsigned int v12; // r14d
  __int64 v13; // rcx
  unsigned int v14; // r8d
  unsigned int LastError; // eax
  HCERTSTORE v16; // rax
  int v17; // eax
  bool v18; // zf
  const CHAR *v19; // rax
  __int64 j; // r12
  const char *v21; // rcx
  int v22; // eax
  __int64 v23; // rcx
  __int64 v24; // rax
  unsigned int v25; // edx
  __int64 v26; // r8
  __int64 v27; // rcx
  const struct _CERT_CONTEXT *v28; // r9
  __int64 v29; // rax
  __int64 v30; // r15
  const char *v31; // rcx
  unsigned int v32; // r12d
  unsigned int v33; // edi
  __int64 v34; // r15
  __int64 v35; // r14
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // rax
  void *v39; // rcx
  __int64 v41; // [rsp+40h] [rbp-C0h] BYREF
  HCERTSTORE v42; // [rsp+48h] [rbp-B8h]
  int v43; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pcbEncoded; // [rsp+54h] [rbp-ACh] BYREF
  DWORD v45; // [rsp+58h] [rbp-A8h]
  int v46; // [rsp+5Ch] [rbp-A4h]
  HCERTSTORE v47; // [rsp+60h] [rbp-A0h]
  void *Block; // [rsp+68h] [rbp-98h] BYREF
  struct _SMIME_SECURITY_LABEL *v49; // [rsp+70h] [rbp-90h] BYREF
  size_t Size[2]; // [rsp+78h] [rbp-88h] BYREF
  DWORD pcbStructInfo; // [rsp+88h] [rbp-78h] BYREF
  DWORD v52; // [rsp+8Ch] [rbp-74h] BYREF
  HCERTSTORE hCertStore; // [rsp+90h] [rbp-70h] BYREF
  HCERTSTORE v54; // [rsp+98h] [rbp-68h] BYREF
  HCERTSTORE v55; // [rsp+A0h] [rbp-60h] BYREF
  HCERTSTORE v56; // [rsp+A8h] [rbp-58h] BYREF
  const CHAR *v57; // [rsp+B0h] [rbp-50h]
  void *Buf1[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 pvEncoded; // [rsp+C8h] [rbp-38h] BYREF
  PCCERT_CONTEXT CertificateInStore; // [rsp+D0h] [rbp-30h]
  __int64 v61; // [rsp+D8h] [rbp-28h] BYREF
  DWORD *v62; // [rsp+E0h] [rbp-20h]
  __int128 pvStructInfo; // [rsp+E8h] [rbp-18h] BYREF
  __int128 pvCtrlPara; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v65; // [rsp+108h] [rbp+8h]
  __int128 v66; // [rsp+118h] [rbp+18h] BYREF
  __int128 v67; // [rsp+128h] [rbp+28h]
  __int128 v68; // [rsp+138h] [rbp+38h]
  _BYTE v69[208]; // [rsp+150h] [rbp+50h] BYREF
  unsigned int pvData; // [rsp+230h] [rbp+130h] BYREF
  DWORD pcbData; // [rsp+238h] [rbp+138h] BYREF
  void *v72; // [rsp+240h] [rbp+140h] BYREF
  int v73; // [rsp+248h] [rbp+148h]

  v1 = 0;
  v43 = 0;
  pvData = 0;
  v2 = 0;
  hCertStore = 0;
  v55 = 0;
  v4 = (void *)*((_QWORD *)this + 3);
  v54 = 0;
  v56 = 0;
  v42 = 0;
  pcbStructInfo = 0;
  pvStructInfo = 0;
  v47 = 0;
  v5 = 0;
  *(_OWORD *)Size = 0;
  Block = 0;
  *(_OWORD *)Buf1 = 0;
  v49 = 0;
  v41 = 0;
  pvCtrlPara = 0;
  v72 = 0;
  v65 = 0;
  v57 = 0;
  pcbData = 4;
  if ( !CryptMsgGetParam(v4, 5u, 0, &pvData, &pcbData) )
    goto LABEL_114;
  if ( !pvData )
  {
    MsgParam = 839232;
    goto LABEL_115;
  }
  if ( !(unsigned int)MemAlloc(&v72, 96 * pvData) )
  {
    MsgParam = -2147024882;
    goto LABEL_115;
  }
  v7 = *((_QWORD *)this + 12);
  v8 = (DWORD *)v72;
  v62 = (DWORD *)v72;
  *(_QWORD *)(v7 + 24) = v72;
  *(_DWORD *)(*((_QWORD *)this + 12) + 20LL) = pvData;
  memset_0(v8, 0, 96LL * pvData);
  for ( i = 0; (unsigned int)i < pvData; v8[8 * v10] = 2 )
  {
    v10 = 3 * i;
    i = (unsigned int)(i + 1);
  }
  if ( !CryptMsgGetParam(*((HCRYPTMSG *)this + 3), 0xBu, 0, &v43, &pcbData) )
    goto LABEL_114;
  if ( v43 )
  {
    v11 = CertOpenStore((LPCSTR)1, 1u, *((_QWORD *)this + 4), 0, *((const void **)this + 3));
    v42 = v11;
    v2 = v11;
    if ( !v11 )
    {
LABEL_29:
      MsgParam = -2147467259;
      goto LABEL_115;
    }
    *((_DWORD *)this + 16) |= 0x20000u;
    *(_QWORD *)(*((_QWORD *)this + 12) + 136LL) = CertDuplicateStore(v11);
  }
  v46 = 1;
  MsgParam = 0;
  v12 = 0;
  while ( 2 )
  {
    v5 = 0;
    LODWORD(v72) = v12;
    if ( v12 >= pvData )
      goto LABEL_119;
    if ( (_BYTE *)v41 != v69 && v41 )
    {
      ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
      v41 = 0;
    }
    MsgParam = HrGetMsgParam(*((_QWORD *)this + 3), 39, v12, &v41, 0);
    if ( MsgParam < 0 || !v41 )
      goto LABEL_115;
    if ( v2 )
    {
      CertificateInStore = CertFindCertificateInStore(v2, 1u, 0, 0x100000u, (const void *)(v41 + 8), 0);
      v5 = CertificateInStore;
      if ( CertificateInStore )
      {
        *(_DWORD *)(*((_QWORD *)this + 12) + 16LL) = 1;
        goto LABEL_22;
      }
    }
    v16 = OpenAllStore(*((_DWORD *)this + 17), *((void **const *)this + 9), &hCertStore, &v55, &v54, &v56);
    v47 = v16;
    v1 = v16;
    if ( !v16 )
      goto LABEL_114;
    CertificateInStore = CertFindCertificateInStore(v16, 1u, 0, 0x100000u, (const void *)(v41 + 8), 0);
    v5 = CertificateInStore;
    if ( CertificateInStore )
    {
LABEL_22:
      *((_QWORD *)v8 + 1) = CertDuplicateCertificateContext(v5);
      LODWORD(pvCtrlPara) = 32;
      *((_QWORD *)&pvCtrlPara + 1) = 0;
      *(_QWORD *)&v65 = v12 | 0x200000000LL;
      *((_QWORD *)&v65 + 1) = v5;
      while ( 1 )
      {
        if ( CryptMsgControl(*((HCRYPTMSG *)this + 3), 0, 0x13u, &pvCtrlPara) )
        {
          *v8 &= 0xFFFFF000;
          goto LABEL_44;
        }
        LastError = HrGetLastError();
        v13 = LastError;
        if ( LastError != -2146885588 )
          break;
        if ( !v1 )
        {
          v47 = OpenAllStore(*((_DWORD *)this + 17), *((void **const *)this + 9), &hCertStore, &v55, &v54, &v56);
          v1 = v47;
          if ( !v47 )
            goto LABEL_114;
        }
        if ( (unsigned int)GetParameters(v5, v2, v1) )
          goto LABEL_38;
      }
      switch ( LastError )
      {
        case 0x80090006:
        case 0x80091007:
          *v8 = 1;
          break;
        case 0x80090008:
          *v8 = 4;
          break;
        case 0x8009100E:
LABEL_38:
          *v8 = 2;
          break;
        default:
          v17 = 128;
          v18 = (_DWORD)v13 == -2146893792;
          v13 = 1;
          if ( v18 )
            v17 = 1;
          *v8 = v17;
          break;
      }
LABEL_44:
      if ( CertVerifyTimeValidityWithDelta((struct _FILETIME *)v13, v5->pCertInfo, v14) )
        *v8 |= 0x100u;
      goto LABEL_46;
    }
    *v8 = 2;
LABEL_46:
    v19 = (const CHAR *)PVGetMsgParam(*((_QWORD *)this + 3), 4, 0);
    v57 = v19;
    if ( !v19 )
    {
      *v8 |= 0x1000000u;
      MsgParam = -2146644297;
      goto LABEL_115;
    }
    lstrcmpA("1.2.840.113549.1.7.1", v19);
    *((_QWORD *)&pvStructInfo + 1) = v41 + 48;
    LODWORD(pvStructInfo) = 1;
    if ( !CryptEncodeObjectEx(1u, (LPCSTR)0x2A, &pvStructInfo, 0x8000u, &CryptEncodeAlloc, v8 + 6, v8 + 4) )
      goto LABEL_29;
    if ( !*(_DWORD *)(v41 + 112) )
      goto LABEL_108;
    for ( j = 0; ; j = (unsigned int)(j + 1) )
    {
      v73 = j;
      if ( (unsigned int)j >= *(_DWORD *)(v41 + 112) )
        break;
      if ( (unsigned int)FIsMsasn1Loaded() )
      {
        v21 = *(const char **)(*(_QWORD *)(v41 + 120) + 24 * j);
        if ( v21 )
        {
          if ( !strcmp_0(v21, "1.2.840.113549.1.9.16.2.2") )
          {
            if ( *(_BYTE *)v8 )
            {
              v22 = DwProcessLabelWithCertError();
              if ( v22 == 1 )
              {
                MsgParam = 0;
                continue;
              }
              if ( v22 == 2 )
              {
                MsgParam = -2146644237;
                goto LABEL_115;
              }
            }
            v23 = *(_QWORD *)(v41 + 120);
            if ( *(_DWORD *)(v23 + 24 * j + 8) != 1 )
              goto LABEL_63;
            v24 = *(_QWORD *)(v23 + 24 * j + 16);
            v25 = *(_DWORD *)v24;
            if ( Buf1[1] )
            {
              if ( (LODWORD(Buf1[0]) != v25 || memcmp_0(Buf1[1], *(const void **)(v24 + 8), LODWORD(Buf1[0])))
                && FHideMsgWithDifferentLabels() )
              {
LABEL_63:
                MsgParam = -2146644235;
                goto LABEL_115;
              }
              continue;
            }
            LODWORD(Buf1[0]) = *(_DWORD *)v24;
            if ( !(unsigned int)MemAlloc(&Buf1[1], v25) )
              goto LABEL_63;
            memcpy_0(
              Buf1[1],
              *(const void **)(*(_QWORD *)(*(_QWORD *)(v41 + 120) + 24 * j + 16) + 8LL),
              LODWORD(Buf1[0]));
            if ( v49 )
              ((void (*)(void))CryptDecodeAlloc.pfnFree)();
            v26 = *(_QWORD *)(*(_QWORD *)(v41 + 120) + 24 * j + 16);
            if ( !CryptDecodeObjectEx(
                    1u,
                    "1.2.840.113549.1.9.16.2.2",
                    *(const BYTE **)(v26 + 8),
                    *(_DWORD *)v26,
                    0x8000u,
                    &CryptDecodeAlloc,
                    &v49,
                    &pcbStructInfo) )
              goto LABEL_114;
            v27 = *((_QWORD *)this + 12);
            v28 = 0;
            v29 = 0;
            if ( v27 )
              v29 = *(_QWORD *)(v27 + 152);
            while ( v29 )
            {
              if ( *(_QWORD *)(v29 + 128) )
              {
                v28 = *(const struct _CERT_CONTEXT **)(v29 + 128);
                break;
              }
              v29 = *(_QWORD *)(v29 + 152);
            }
            MsgParam = HrCheckLabelAccess(
                         (*((_DWORD *)this + 32) >> 2) & 1,
                         *((HWND *)this + 15),
                         (LPCSTR *)v49,
                         v28,
                         v5,
                         v2);
            if ( MsgParam < 0 )
              goto LABEL_115;
          }
        }
      }
      if ( (unsigned int)FIsMsasn1Loaded() && v46 && (*v8 & 0xFFF) == 0 )
      {
        v30 = *(_QWORD *)(v41 + 120);
        v31 = *(const char **)(v30 + 24 * j);
        if ( !v31 || strcmp_0(v31, "1.2.840.113549.1.9.16.2.1") )
          goto LABEL_92;
        if ( *(_DWORD *)(v30 + 24 * j + 8) != 1 )
        {
          if ( Size[1] )
          {
LABEL_82:
            v32 = 0;
            if ( (_DWORD)v72 )
            {
              v33 = (unsigned int)v72;
              v34 = 0;
              do
              {
                v35 = 96 * v34;
                if ( *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 12) + 24LL) + 96 * v34 + 72) )
                {
                  ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
                  *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 12) + 24LL) + v35 + 72) = 0;
                }
                if ( *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 12) + 24LL) + v35 + 88) )
                {
                  ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
                  *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 12) + 24LL) + v35 + 88) = 0;
                }
                ++v32;
                ++v34;
                *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 12) + 24LL) + v35 + 64) = 0;
                *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 12) + 24LL) + v35 + 80) = 0;
              }
              while ( v32 < v33 );
              v8 = v62;
              v5 = CertificateInStore;
            }
            LODWORD(j) = v73;
          }
          v46 = 0;
LABEL_92:
          v2 = v42;
          continue;
        }
        v52 = 0;
        pcbEncoded = 0;
        v45 = 0;
        pvEncoded = 0;
        v66 = 0;
        v67 = 0;
        v68 = 0;
        if ( Block )
          free(Block);
        if ( Size[1] )
        {
          v36 = *(_QWORD *)(*(_QWORD *)(v41 + 120) + 24 * j + 16);
          if ( LODWORD(Size[0]) != *(_DWORD *)v36
            || memcmp_0((const void *)Size[1], *(const void **)(v36 + 8), LODWORD(Size[0])) )
          {
            goto LABEL_82;
          }
        }
        else
        {
          LODWORD(Size[0]) = **(_DWORD **)(*(_QWORD *)(v41 + 120) + 24 * j + 16);
          if ( !(unsigned int)MemAlloc((void **)&Size[1], Size[0]) )
            goto LABEL_82;
          memcpy_0(
            (void *)Size[1],
            *(const void **)(*(_QWORD *)(*(_QWORD *)(v41 + 120) + 24 * j + 16) + 8LL),
            LODWORD(Size[0]));
        }
        v37 = *(_QWORD *)(*(_QWORD *)(v41 + 120) + 24 * j + 16);
        if ( !CryptDecodeObjectEx(
                1u,
                "1.2.840.113549.1.9.16.2.1",
                *(const BYTE **)(v37 + 8),
                *(_DWORD *)v37,
                0x8000u,
                &CryptDecodeAlloc,
                &Block,
                &v52) )
          goto LABEL_82;
        *((_QWORD *)&v66 + 1) = v57;
        LODWORD(v66) = 1;
        v67 = *(_OWORD *)Block;
        LODWORD(v68) = *(_DWORD *)(v41 + 96);
        *((_QWORD *)&v68 + 1) = *(_QWORD *)(v41 + 104);
        if ( !CryptEncodeObjectEx(
                1u,
                "1.2.840.113549.1.9.16.1.1",
                &v66,
                0x8000u,
                &CryptEncodeAlloc,
                &pvEncoded,
                &pcbEncoded) )
          goto LABEL_82;
        v8[16] = pcbEncoded;
        *((_QWORD *)v8 + 9) = pvEncoded;
        v38 = PVGetMsgParam(*((_QWORD *)this + 3), 22, 0);
        v2 = v42;
        if ( !v38 )
          goto LABEL_114;
        v8[20] = v45;
        *((_QWORD *)v8 + 11) = v38;
      }
    }
    pcbData = 0;
    v61 = 0;
    if ( !CryptEncodeObjectEx(
            1u,
            "1.3.6.1.4.1.311.16.1.1",
            (const void *)(v41 + 112),
            0x8000u,
            &CryptEncodeAlloc,
            &v61,
            &pcbData) )
      goto LABEL_114;
    v12 = (unsigned int)v72;
    v8[8] = pcbData;
    *((_QWORD *)v8 + 5) = v61;
LABEL_108:
    if ( !*(_DWORD *)(v41 + 128) )
    {
LABEL_111:
      CertFreeCertificateContext(v5);
      ++v12;
      v1 = v47;
      v8 += 24;
      v62 = v8;
      continue;
    }
    break;
  }
  v72 = 0;
  if ( CryptEncodeObjectEx(
         1u,
         "1.3.6.1.4.1.311.16.1.1",
         (const void *)(v41 + 128),
         0x8000u,
         &CryptEncodeAlloc,
         &v72,
         &pcbData) )
  {
    v8[12] = pcbData;
    *((_QWORD *)v8 + 7) = v72;
    goto LABEL_111;
  }
LABEL_114:
  MsgParam = HrGetLastError();
LABEL_115:
  v39 = *(void **)(*((_QWORD *)this + 12) + 136LL);
  if ( v39 )
  {
    CertCloseStore(v39, 0);
    *(_QWORD *)(*((_QWORD *)this + 12) + 136LL) = 0;
  }
  v1 = v47;
  if ( !MsgParam )
    MsgParam = -2146644298;
LABEL_119:
  if ( Block )
    ((void (*)(void))CryptDecodeAlloc.pfnFree)();
  if ( v49 )
    ((void (*)(void))CryptDecodeAlloc.pfnFree)();
  if ( Size[1] )
    ((void (__fastcall *)(LPMALLOC, size_t))g_pMalloc->lpVtbl->Free)(g_pMalloc, Size[1]);
  if ( Buf1[1] )
    ((void (__fastcall *)(LPMALLOC, void *))g_pMalloc->lpVtbl->Free)(g_pMalloc, Buf1[1]);
  if ( hCertStore )
    CertCloseStore(hCertStore, 0);
  if ( v54 )
    CertCloseStore(v54, 0);
  if ( v55 )
    CertCloseStore(v55, 0);
  if ( v56 )
    CertCloseStore(v56, 0);
  if ( v2 )
    CertCloseStore(v2, 0);
  ((void (__fastcall *)(LPMALLOC, const CHAR *))g_pMalloc->lpVtbl->Free)(g_pMalloc, v57);
  ((void (__fastcall *)(LPMALLOC, _QWORD))g_pMalloc->lpVtbl->Free)(g_pMalloc, 0);
  if ( (_BYTE *)v41 != v69 )
    ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
  if ( v1 )
    CertCloseStore(v1, 0);
  if ( v5 )
    CertFreeCertificateContext(v5);
  return (unsigned int)MsgParam;
}

```

## disassembly

```asm
0x18005be40  push    rbp
0x18005be42  push    rbx
0x18005be43  push    rsi
0x18005be44  push    rdi
0x18005be45  push    r12
0x18005be47  push    r13
0x18005be49  push    r14
0x18005be4b  push    r15
0x18005be4d  lea     rbp, [rsp-0E8h]
0x18005be55  sub     rsp, 1E8h
0x18005be5c  xor     r12d, r12d
0x18005be5f  mov     [rsp+220h+var_1D0], 0
0x18005be67  xorps   xmm0, xmm0
0x18005be6a  mov     [rbp+120h+pvData], 0
0x18005be74  xor     r15d, r15d
0x18005be77  mov     [rbp+120h+hCertStore], 0
0x18005be7f  mov     rsi, rcx
0x18005be82  mov     [rbp+120h+var_180], 0
0x18005be8a  mov     rcx, [rcx+18h]; hCryptMsg
0x18005be8e  lea     rax, [rbp+120h+arg_8]
0x18005be95  xorps   xmm1, xmm1
0x18005be98  mov     [rbp+120h+var_188], 0
0x18005bea0  lea     edx, [r15+5]; dwParamType
0x18005bea4  mov     [rbp+120h+var_178], 0
0x18005beac  lea     r9, [rbp+120h+pvData]; pvData
0x18005beb3  mov     [rsp+220h+var_1D8], r15
0x18005beb8  xor     r8d, r8d; dwIndex
0x18005bebb  mov     [rbp+120h+var_198], r15d
0x18005bebf  movups  [rbp+120h+pvStructInfo], xmm0
0x18005bec3  mov     [rsp+220h+var_1C0], r12
0x18005bec8  xor     r13d, r13d
0x18005becb  movups  xmmword ptr [rsp+220h+Size], xmm0
0x18005bed0  mov     [rsp+220h+Block], r12
0x18005bed5  movups  xmmword ptr [rbp+120h+Buf1], xmm1
0x18005bed9  mov     [rsp+220h+var_1B0], r12
0x18005bede  mov     [rsp+220h+var_1E0], r12
0x18005bee3  movups  [rbp+120h+pvCtrlPara], xmm0
0x18005bee7  mov     [rbp+120h+arg_10], r12
0x18005beee  movups  [rbp+120h+var_118], xmm0
0x18005bef2  mov     [rbp+120h+var_170], r12
0x18005bef6  mov     [rbp+120h+arg_8], 4
0x18005bf00  mov     [rsp+220h+pcbData], rax; pcbData
0x18005bf05  call    cs:__imp_CryptMsgGetParam
0x18005bf0b  test    eax, eax
0x18005bf0d  jz      loc_18005C8EA
0x18005bf13  mov     eax, [rbp+120h+pvData]
0x18005bf19  test    eax, eax
0x18005bf1b  jnz     short loc_18005BF27
0x18005bf1d  mov     ebx, 0CCE40h
0x18005bf22  jmp     loc_18005C8F1
0x18005bf27  lea     edx, [rax+rax*2]
0x18005bf2a  shl     edx, 5; unsigned int
0x18005bf2d  lea     rcx, [rbp+120h+arg_10]; void **
0x18005bf34  call    ?MemAlloc@@YAHPEAPEAXK@Z; MemAlloc(void * *,ulong)
0x18005bf39  test    eax, eax
0x18005bf3b  jnz     short loc_18005BF47
0x18005bf3d  mov     ebx, 8007000Eh
0x18005bf42  jmp     loc_18005C8F1
0x18005bf47  mov     rax, [rsi+60h]
0x18005bf4b  xor     edx, edx; Val
0x18005bf4d  mov     rdi, [rbp+120h+arg_10]
0x18005bf54  mov     [rbp+120h+var_140], rdi
0x18005bf58  mov     [rax+18h], rdi
0x18005bf5c  mov     rcx, [rsi+60h]
0x18005bf60  mov     eax, [rbp+120h+pvData]
0x18005bf66  mov     [rcx+14h], eax
0x18005bf69  mov     rcx, rdi; void *
0x18005bf6c  mov     eax, [rbp+120h+pvData]
0x18005bf72  lea     r8, [rax+rax*2]
0x18005bf76  shl     r8, 5; Size
0x18005bf7a  call    memset_0
0x18005bf7f  xor     edx, edx
0x18005bf81  lea     ebx, [rdx+1]
0x18005bf84  cmp     [rbp+120h+pvData], edx
0x18005bf8a  jbe     short loc_18005BFA5
0x18005bf8c  lea     rcx, [rdx+rdx*2]
0x18005bf90  add     edx, ebx
0x18005bf92  shl     rcx, 5
0x18005bf96  mov     dword ptr [rcx+rdi], 2
0x18005bf9d  cmp     edx, [rbp+120h+pvData]
0x18005bfa3  jb      short loc_18005BF8C
0x18005bfa5  mov     rcx, [rsi+18h]; hCryptMsg
0x18005bfa9  lea     rax, [rbp+120h+arg_8]
0x18005bfb0  xor     r8d, r8d; dwIndex
0x18005bfb3  mov     [rsp+220h+pcbData], rax; pcbData
0x18005bfb8  lea     r9, [rsp+220h+var_1D0]; pvData
0x18005bfbd  lea     edx, [r8+0Bh]; dwParamType
0x18005bfc1  call    cs:__imp_CryptMsgGetParam
0x18005bfc7  test    eax, eax
0x18005bfc9  jz      loc_18005C8EA
0x18005bfcf  cmp     [rsp+220h+var_1D0], r12d
0x18005bfd4  jz      short loc_18005C01B
0x18005bfd6  mov     rax, [rsi+18h]
0x18005bfda  xor     r9d, r9d; dwFlags
0x18005bfdd  mov     r8, [rsi+20h]; hCryptProv
0x18005bfe1  mov     edx, ebx; dwEncodingType
0x18005bfe3  mov     rcx, rbx; lpszStoreProvider
0x18005bfe6  mov     [rsp+220h+pcbData], rax; pvPara
0x18005bfeb  call    cs:__imp_CertOpenStore
0x18005bff1  mov     [rsp+220h+var_1D8], rax
0x18005bff6  mov     r15, rax
0x18005bff9  test    rax, rax
0x18005bffc  jz      loc_18005C18E
0x18005c002  bts     dword ptr [rsi+40h], 11h
0x18005c007  mov     rcx, rax; hCertStore
0x18005c00a  call    cs:__imp_CertDuplicateStore
0x18005c010  mov     rcx, [rsi+60h]
0x18005c014  mov     [rcx+88h], rax
0x18005c01b  mov     [rsp+220h+var_1C4], ebx
0x18005c01f  xor     ebx, ebx
0x18005c021  xor     r14d, r14d
0x18005c024  xor     r13d, r13d
0x18005c027  mov     dword ptr [rbp+120h+arg_10], r14d
0x18005c02e  cmp     r14d, [rbp+120h+pvData]
0x18005c035  jnb     loc_18005C927
0x18005c03b  mov     rdx, [rsp+220h+var_1E0]
0x18005c040  lea     rax, [rbp+120h+var_D0]
0x18005c044  cmp     rdx, rax
0x18005c047  jz      short loc_18005C066
0x18005c049  test    rdx, rdx
0x18005c04c  jz      short loc_18005C066
0x18005c04e  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18005c055  mov     rax, [rcx]
0x18005c058  mov     rax, [rax+28h]
0x18005c05c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c061  mov     [rsp+220h+var_1E0], r13
0x18005c066  mov     rcx, [rsi+18h]
0x18005c06a  lea     r9, [rsp+220h+var_1E0]
0x18005c06f  mov     r8d, r14d
0x18005c072  mov     [rsp+220h+pcbData], r13
0x18005c077  mov     edx, 27h ; '''
0x18005c07c  call    cs:__imp_HrGetMsgParam
0x18005c082  mov     ebx, eax
0x18005c084  test    eax, eax
0x18005c086  js      loc_18005C8F1
0x18005c08c  mov     rcx, [rsp+220h+var_1E0]
0x18005c091  test    rcx, rcx
0x18005c094  jz      loc_18005C8F1
0x18005c09a  test    r15, r15
0x18005c09d  jz      loc_18005C198
0x18005c0a3  add     rcx, 8
0x18005c0a7  mov     [rsp+220h+pPrevCertContext], r13; pPrevCertContext
0x18005c0ac  xor     r8d, r8d; dwFindFlags
0x18005c0af  mov     [rsp+220h+pcbData], rcx; pvFindPara
0x18005c0b4  mov     r9d, 100000h; dwFindType
0x18005c0ba  mov     rcx, r15; hCertStore
0x18005c0bd  lea     edx, [r8+1]; dwCertEncodingType
0x18005c0c1  call    cs:__imp_CertFindCertificateInStore
0x18005c0c7  mov     [rbp+120h+var_150], rax
0x18005c0cb  mov     r13, rax
0x18005c0ce  test    rax, rax
0x18005c0d1  jz      loc_18005C198
0x18005c0d7  mov     rcx, [rsi+60h]
0x18005c0db  mov     dword ptr [rcx+10h], 1
0x18005c0e2  mov     rcx, r13; pCertContext
0x18005c0e5  call    cs:__imp_CertDuplicateCertificateContext
0x18005c0eb  mov     [rdi+8], rax
0x18005c0ef  mov     dword ptr [rbp+120h+pvCtrlPara], 20h ; ' '
0x18005c0f6  mov     qword ptr [rbp+120h+pvCtrlPara+8], 0
0x18005c0fe  mov     dword ptr [rbp+120h+var_118], r14d
0x18005c102  mov     dword ptr [rbp+120h+var_118+4], 2
0x18005c109  mov     qword ptr [rbp+120h+var_118+8], r13
0x18005c10d  mov     rcx, [rsi+18h]; hCryptMsg
0x18005c111  lea     r9, [rbp+120h+pvCtrlPara]; pvCtrlPara
0x18005c115  xor     edx, edx; dwFlags
0x18005c117  lea     r8d, [rdx+13h]; dwCtrlType
0x18005c11b  call    cs:__imp_CryptMsgControl
0x18005c121  test    eax, eax
0x18005c123  jnz     loc_18005C261
0x18005c129  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x18005c12e  mov     ecx, eax
0x18005c130  cmp     eax, 8009202Ch
0x18005c135  jnz     loc_18005C214
0x18005c13b  test    r12, r12
0x18005c13e  jnz     short loc_18005C177
0x18005c140  mov     rdx, [rsi+48h]; void **
0x18005c144  lea     rax, [rbp+120h+var_178]
0x18005c148  mov     ecx, [rsi+44h]; unsigned int
0x18005c14b  lea     r9, [rbp+120h+var_180]; void **
0x18005c14f  mov     [rsp+220h+pPrevCertContext], rax; void **
0x18005c154  lea     r8, [rbp+120h+hCertStore]; void **
0x18005c158  lea     rax, [rbp+120h+var_188]
0x18005c15c  mov     [rsp+220h+pcbData], rax; void **
0x18005c161  call    ?OpenAllStore@@YAPEAXKQEAPEAXPEAPEAX111@Z; OpenAllStore(ulong,void * * const,void * *,void * *,void * *,void * *)
0x18005c166  mov     [rsp+220h+var_1C0], rax
0x18005c16b  mov     r12, rax
0x18005c16e  test    rax, rax
0x18005c171  jz      loc_18005C8EA
0x18005c177  mov     r8, r12; void *
0x18005c17a  mov     rdx, r15; void *
0x18005c17d  mov     rcx, r13; pSubject
0x18005c180  call    ?GetParameters@@YAJPEBU_CERT_CONTEXT@@PEAX1@Z; GetParameters(_CERT_CONTEXT const *,void *,void *)
0x18005c185  test    eax, eax
0x18005c187  jz      short loc_18005C10D
0x18005c189  jmp     loc_18005C23C
0x18005c18e  mov     ebx, 80004005h
0x18005c193  jmp     loc_18005C8F1
0x18005c198  mov     rdx, [rsi+48h]; void **
0x18005c19c  lea     rax, [rbp+120h+var_178]
0x18005c1a0  mov     ecx, [rsi+44h]; unsigned int
0x18005c1a3  lea     r9, [rbp+120h+var_180]; void **
0x18005c1a7  mov     [rsp+220h+pPrevCertContext], rax; void **
0x18005c1ac  lea     r8, [rbp+120h+hCertStore]; void **
0x18005c1b0  lea     rax, [rbp+120h+var_188]
0x18005c1b4  mov     [rsp+220h+pcbData], rax; void **
0x18005c1b9  call    ?OpenAllStore@@YAPEAXKQEAPEAXPEAPEAX111@Z; OpenAllStore(ulong,void * * const,void * *,void * *,void * *,void * *)
0x18005c1be  mov     [rsp+220h+var_1C0], rax
0x18005c1c3  mov     r12, rax
0x18005c1c6  test    rax, rax
0x18005c1c9  jz      loc_18005C8EA
0x18005c1cf  mov     rcx, [rsp+220h+var_1E0]
0x18005c1d4  xor     r8d, r8d; dwFindFlags
0x18005c1d7  add     rcx, 8
0x18005c1db  mov     [rsp+220h+pPrevCertContext], 0; pPrevCertContext
0x18005c1e4  mov     [rsp+220h+pcbData], rcx; pvFindPara
0x18005c1e9  mov     r9d, 100000h; dwFindType
0x18005c1ef  mov     rcx, rax; hCertStore
0x18005c1f2  lea     edx, [r8+1]; dwCertEncodingType
0x18005c1f6  call    cs:__imp_CertFindCertificateInStore
0x18005c1fc  mov     [rbp+120h+var_150], rax
0x18005c200  mov     r13, rax
0x18005c203  test    rax, rax
0x18005c206  jnz     loc_18005C0E2
0x18005c20c  mov     dword ptr [rdi], 2
0x18005c212  jmp     short loc_18005C278
0x18005c214  cmp     ecx, 80090006h
0x18005c21a  jz      short loc_18005C259
0x18005c21c  cmp     ecx, 80091007h
0x18005c222  jz      short loc_18005C259
0x18005c224  cmp     ecx, 80090008h
0x18005c22a  jnz     short loc_18005C234
0x18005c22c  mov     dword ptr [rdi], 4
0x18005c232  jmp     short loc_18005C267
0x18005c234  cmp     ecx, 8009100Eh
0x18005c23a  jnz     short loc_18005C244
0x18005c23c  mov     dword ptr [rdi], 2
0x18005c242  jmp     short loc_18005C267
0x18005c244  mov     eax, 80h
0x18005c249  cmp     ecx, 80090020h
0x18005c24f  lea     ecx, [rax-7Fh]
0x18005c252  cmovz   eax, ecx
0x18005c255  mov     [rdi], eax
0x18005c257  jmp     short loc_18005C267
0x18005c259  mov     dword ptr [rdi], 1
0x18005c25f  jmp     short loc_18005C267
0x18005c261  and     dword ptr [rdi], 0FFFFF000h
0x18005c267  mov     rdx, [r13+18h]; struct _CERT_INFO *
0x18005c26b  call    ?CertVerifyTimeValidityWithDelta@@YAJPEAU_FILETIME@@PEAU_CERT_INFO@@K@Z; CertVerifyTimeValidityWithDelta(_FILETIME *,_CERT_INFO *,ulong)
0x18005c270  test    eax, eax
0x18005c272  jz      short loc_18005C278
0x18005c274  bts     dword ptr [rdi], 8
0x18005c278  mov     rcx, [rsi+18h]
0x18005c27c  xor     r9d, r9d
0x18005c27f  xor     r8d, r8d
0x18005c282  lea     edx, [r9+4]
0x18005c286  call    cs:__imp_PVGetMsgParam
0x18005c28c  mov     [rbp+120h+var_170], rax
0x18005c290  test    rax, rax
0x18005c293  jz      loc_18005C8DF
0x18005c299  mov     rdx, rax; lpString2
0x18005c29c  lea     rcx, String1; "1.2.840.113549.1.7.1"
0x18005c2a3  call    cs:__imp_lstrcmpA
0x18005c2a9  mov     rcx, [rsp+220h+var_1E0]
0x18005c2ae  lea     rax, ?CryptEncodeAlloc@@3U_CRYPT_ENCODE_PARA@@A; _CRYPT_ENCODE_PARA CryptEncodeAlloc
0x18005c2b5  add     rcx, 30h ; '0'
0x18005c2b9  lea     r8, [rbp+120h+pvStructInfo]; pvStructInfo
0x18005c2bd  mov     qword ptr [rbp+120h+pvStructInfo+8], rcx
0x18005c2c1  mov     r12d, 1
0x18005c2c7  lea     rcx, [rdi+10h]
0x18005c2cb  mov     dword ptr [rbp+120h+pvStructInfo], r12d
0x18005c2cf  lea     rdx, [rcx+8]
0x18005c2d3  mov     [rsp+220h+pcbEncoded], rcx; pcbEncoded
0x18005c2d8  mov     [rsp+220h+pPrevCertContext], rdx; pvEncoded
0x18005c2dd  mov     r9d, 8000h; dwFlags
0x18005c2e3  lea     edx, [r12+29h]; lpszStructType
0x18005c2e8  mov     [rsp+220h+pcbData], rax; pEncodePara
0x18005c2ed  mov     ecx, r12d; dwCertEncodingType
0x18005c2f0  call    cs:__imp_CryptEncodeObjectEx
0x18005c2f6  test    eax, eax
0x18005c2f8  jz      loc_18005C18E
0x18005c2fe  mov     rax, [rsp+220h+var_1E0]
0x18005c303  cmp     dword ptr [rax+70h], 0
0x18005c307  jz      loc_18005C84E
0x18005c30d  xor     r12d, r12d
0x18005c310  mov     r8, [rsp+220h+var_1E0]
0x18005c315  add     r8, 70h ; 'p'; pvStructInfo
0x18005c319  mov     [rbp+120h+arg_18], r12d
0x18005c320  cmp     r12d, [r8]
0x18005c323  jnb     loc_18005C7DF
0x18005c329  call    ?FIsMsasn1Loaded@@YAHXZ; FIsMsasn1Loaded(void)
0x18005c32e  test    eax, eax
0x18005c330  jz      loc_18005C4D8
0x18005c336  mov     rax, [rsp+220h+var_1E0]
0x18005c33b  lea     r14, [r12+r12*2]
0x18005c33f  mov     rcx, [rax+78h]
0x18005c343  mov     rcx, [rcx+r14*8]; Str1
0x18005c347  test    rcx, rcx
0x18005c34a  jz      loc_18005C4D8
0x18005c350  lea     rdx, Str2; "1.2.840.113549.1.9.16.2.2"
0x18005c357  call    strcmp_0
  ... truncated ...
```
