# DoUnlockWithSmartCard(tagDISPPARAMS *,tagVARIANT *)

- ea: `0x180007e20`
- end: `0x180008568`
- name: `?DoUnlockWithSmartCard@@YAJPEAUtagDISPPARAMS@@PEAUtagVARIANT@@@Z`
- size: `1864`
- prototype: `__int64 __fastcall(struct tagDISPPARAMS *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180001bb0`
- `0x180002774`
- `0x180007e20`
- `0x18000cf64`
- `0x18000d0a4`
- `0x18000d66c`
- `0x18000f370`
- `0x18002c230`

## import_xrefs

- `KERNEL32!HeapSize` at `0x180008271`
- `KERNEL32!HeapSize` at `0x180008422`
- `KERNEL32!HeapSize` at `0x180008469`
- `KERNEL32!HeapSize` at `0x180008271`
- `KERNEL32!HeapSize` at `0x180008422`
- `KERNEL32!HeapSize` at `0x180008469`
- `KERNEL32!HeapFree` at `0x18000804b`
- `KERNEL32!HeapFree` at `0x1800082a3`
- `KERNEL32!HeapFree` at `0x180008409`
- `KERNEL32!HeapFree` at `0x180008450`
- `KERNEL32!HeapFree` at `0x180008497`
- `KERNEL32!HeapFree` at `0x18000804b`
- `KERNEL32!HeapFree` at `0x1800082a3`
- `KERNEL32!HeapFree` at `0x180008409`
- `KERNEL32!HeapFree` at `0x180008450`
- `KERNEL32!HeapFree` at `0x180008497`
- `KERNEL32!HeapAlloc` at `0x180007fc1`
- `KERNEL32!HeapAlloc` at `0x180007fc1`
- `KERNEL32!GetProcessHeap` at `0x180007fb0`
- `KERNEL32!GetProcessHeap` at `0x18000803d`
- `KERNEL32!GetProcessHeap` at `0x180008263`
- `KERNEL32!GetProcessHeap` at `0x180008295`
- `KERNEL32!GetProcessHeap` at `0x1800083fb`
- `KERNEL32!GetProcessHeap` at `0x180008414`
- `KERNEL32!GetProcessHeap` at `0x180008442`
- `KERNEL32!GetProcessHeap` at `0x18000845b`
- `KERNEL32!GetProcessHeap` at `0x180008489`
- `KERNEL32!GetProcessHeap` at `0x180007fb0`
- `KERNEL32!GetProcessHeap` at `0x18000803d`
- `KERNEL32!GetProcessHeap` at `0x180008263`
- `KERNEL32!GetProcessHeap` at `0x180008295`
- `KERNEL32!GetProcessHeap` at `0x1800083fb`
- `KERNEL32!GetProcessHeap` at `0x180008414`
- `KERNEL32!GetProcessHeap` at `0x180008442`
- `KERNEL32!GetProcessHeap` at `0x18000845b`
- `KERNEL32!GetProcessHeap` at `0x180008489`
- `ADVAPI32!CryptDestroyKey` at `0x180008231`
- `ADVAPI32!CryptDestroyKey` at `0x1800084d0`
- `ADVAPI32!CryptDestroyKey` at `0x180008231`
- `ADVAPI32!CryptDestroyKey` at `0x1800084d0`
- `ADVAPI32!CryptReleaseContext` at `0x180008241`
- `ADVAPI32!CryptReleaseContext` at `0x1800084e0`
- `ADVAPI32!CryptReleaseContext` at `0x180008241`
- `ADVAPI32!CryptReleaseContext` at `0x1800084e0`
- `FVEAPI!FveUnlockVolumeWithAccessMode` at `0x1800081f1`
- `FVEAPI!FveUnlockVolumeWithAccessMode` at `0x1800081f1`
- `FVEAPI!FveDeleteAuthMethod` at `0x1800083b7`
- `FVEAPI!FveDeleteAuthMethod` at `0x1800083b7`
- `FVEAPI!FveCloseVolume` at `0x1800082d5`
- `FVEAPI!FveCloseVolume` at `0x18000850f`
- `FVEAPI!FveCloseVolume` at `0x1800082d5`
- `FVEAPI!FveCloseVolume` at `0x18000850f`
- `FVEAPI!FveCommitChanges` at `0x1800083c6`
- `FVEAPI!FveCommitChanges` at `0x1800083c6`
- `FVEAPI!FveAddAuthMethodInformation` at `0x1800083a4`
- `FVEAPI!FveAddAuthMethodInformation` at `0x1800083a4`
- `FVEAPI!FveOpenVolumeW` at `0x180007f28`
- `FVEAPI!FveOpenVolumeW` at `0x1800082fd`
- `FVEAPI!FveOpenVolumeW` at `0x180007f28`
- `FVEAPI!FveOpenVolumeW` at `0x1800082fd`
- `FVECERTS!FveCertGetCertHashFromCertContext` at `0x180007f9c`
- `FVECERTS!FveCertGetCertHashFromCertContext` at `0x180007fde`
- `FVECERTS!FveCertGetCertHashFromCertContext` at `0x180007f9c`
- `FVECERTS!FveCertGetCertHashFromCertContext` at `0x180007fde`
- `FVECERTS!FveCertIsAlternateCert` at `0x1800080e2`
- `FVECERTS!FveCertIsAlternateCert` at `0x1800080e2`
- `FVECERTS!FveCertGetPrivateKeyHandle` at `0x18000813d`
- `FVECERTS!FveCertGetPrivateKeyHandle` at `0x18000813d`
- `FVECERTS!FveCertCanCertificateBeAdded` at `0x1800082bc`
- `FVECERTS!FveCertCanCertificateBeAdded` at `0x1800082bc`
- `FVECERTS!FveCertGetPublicKeyHandle` at `0x180008328`
- `FVECERTS!FveCertGetPublicKeyHandle` at `0x180008328`
- `FVECERTS!FveCertFreeCertInfo` at `0x180008536`
- `FVECERTS!FveCertFreeCertInfo` at `0x180008536`
- `FVECERTS!FveCertCreateCertInfo` at `0x180008347`
- `FVECERTS!FveCertCreateCertInfo` at `0x180008347`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180007f80`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180007f80`
- `CRYPT32!CertFreeCertificateContext` at `0x1800084ee`
- `CRYPT32!CertFreeCertificateContext` at `0x1800084ee`
- `CRYPT32!CertCloseStore` at `0x1800084fe`
- `CRYPT32!CertCloseStore` at `0x1800084fe`
- `ncrypt!NCryptFreeObject` at `0x18000820a`
- `ncrypt!NCryptFreeObject` at `0x1800084ae`
- `ncrypt!NCryptFreeObject` at `0x18000820a`
- `ncrypt!NCryptFreeObject` at `0x1800084ae`
- `ncrypt!BCryptDestroyKey` at `0x180008527`
- `ncrypt!BCryptDestroyKey` at `0x180008527`

## pseudocode

```c
__int64 __fastcall DoUnlockWithSmartCard(struct tagDISPPARAMS *a1, struct tagVARIANT *a2)
{
  struct tagDISPPARAMS *v2; // r12
  HCERTSTORE v3; // r13
  const CERT_CONTEXT *v4; // r14
  void *v5; // rsi
  void *v6; // rdi
  VARIANTARG *rgvarg; // rcx
  LONGLONG llVal; // rax
  __int64 lVal; // r15
  LONGLONG v10; // rcx
  int CertHashFromCertContext; // ebx
  VARIANTARG *v12; // rcx
  int AuthMethodGuids; // eax
  PCCERT_CONTEXT v14; // rax
  unsigned int v15; // ebx
  HANDLE ProcessHeap; // rax
  LPVOID v17; // rax
  unsigned int i; // r15d
  __int128 *v19; // rbx
  LONGLONG v20; // rcx
  HANDLE v21; // rax
  int FveAuthInfo; // eax
  unsigned int **v23; // rax
  unsigned int *v24; // rbx
  __int64 v25; // rax
  int v26; // r12d
  __int64 v27; // rcx
  _BYTE *v28; // rax
  __int64 v29; // rcx
  __int128 *v30; // rax
  HANDLE v31; // rax
  SIZE_T v32; // rax
  _BYTE *j; // rcx
  HANDLE v34; // rax
  struct tagVARIANT *v35; // rax
  void *v36; // rbx
  HANDLE v37; // rax
  HANDLE v38; // rax
  SIZE_T v39; // rax
  _BYTE *k; // rcx
  HANDLE v41; // rax
  HANDLE v42; // rax
  SIZE_T v43; // rax
  _BYTE *m; // rcx
  HANDLE v45; // rax
  char v47[4]; // [rsp+50h] [rbp-B0h] BYREF
  int v48; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v49; // [rsp+58h] [rbp-A8h] BYREF
  SIZE_T dwBytes; // [rsp+60h] [rbp-A0h] BYREF
  HCERTSTORE hCertStore; // [rsp+68h] [rbp-98h] BYREF
  NCRYPT_HANDLE hObject; // [rsp+70h] [rbp-90h] BYREF
  HCRYPTPROV hProv; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v54; // [rsp+80h] [rbp-80h] BYREF
  int v55; // [rsp+84h] [rbp-7Ch] BYREF
  __int64 v56; // [rsp+88h] [rbp-78h] BYREF
  HCRYPTKEY hKey; // [rsp+90h] [rbp-70h] BYREF
  struct tagDISPPARAMS *v58; // [rsp+98h] [rbp-68h]
  LPVOID lpMem; // [rsp+A0h] [rbp-60h] BYREF
  BCRYPT_KEY_HANDLE v60; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v61; // [rsp+B0h] [rbp-50h] BYREF
  _DWORD *v62; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v63; // [rsp+C0h] [rbp-40h]
  _DWORD *v64; // [rsp+C8h] [rbp-38h] BYREF
  LONGLONG v65; // [rsp+D0h] [rbp-30h]
  __int128 *v66; // [rsp+D8h] [rbp-28h]
  struct tagVARIANT *v67; // [rsp+E0h] [rbp-20h]
  __int128 v68; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v69; // [rsp+F8h] [rbp-8h]
  __int128 v70; // [rsp+108h] [rbp+8h]
  __int64 v71; // [rsp+118h] [rbp+18h]
  __int128 v72; // [rsp+120h] [rbp+20h] BYREF
  __int128 v73; // [rsp+130h] [rbp+30h]
  __int128 v74; // [rsp+140h] [rbp+40h]
  __int64 v75; // [rsp+150h] [rbp+50h]
  _DWORD v76[4]; // [rsp+160h] [rbp+60h] BYREF
  BCRYPT_KEY_HANDLE v77; // [rsp+170h] [rbp+70h]
  int v78; // [rsp+178h] [rbp+78h]
  __int64 v79; // [rsp+180h] [rbp+80h]
  __int128 v80; // [rsp+3B0h] [rbp+2B0h] BYREF
  _DWORD v81[4]; // [rsp+3C0h] [rbp+2C0h] BYREF
  NCRYPT_HANDLE v82; // [rsp+3D0h] [rbp+2D0h]
  HCRYPTPROV v83; // [rsp+3D8h] [rbp+2D8h]
  HCRYPTKEY v84; // [rsp+3E0h] [rbp+2E0h]
  int v85; // [rsp+3E8h] [rbp+2E8h]

  v67 = a2;
  v58 = a1;
  v2 = a1;
  v49 = -1;
  hCertStore = 0;
  v56 = 0;
  v71 = 0;
  v3 = 0;
  v4 = 0;
  v5 = 0;
  v68 = 0;
  v69 = 0;
  v70 = 0;
  memset_0(v81, 0, 0x248u);
  hObject = 0;
  hProv = 0;
  v64 = v81;
  hKey = 0;
  v75 = 0;
  v55 = 0;
  v48 = 0;
  v6 = 0;
  lpMem = 0;
  v54 = 0;
  v47[0] = 0;
  LODWORD(dwBytes) = 0;
  v72 = 0;
  v62 = 0;
  v73 = 0;
  v74 = 0;
  memset_0(v76, 0, 0x248u);
  rgvarg = v2->rgvarg;
  v61 = 0;
  v60 = 0;
  v80 = 0;
  llVal = rgvarg[2].llVal;
  lVal = rgvarg[1].lVal;
  v10 = rgvarg->llVal;
  v65 = llVal;
  CertHashFromCertContext = FveOpenVolumeW(v10, 0, &v49);
  if ( CertHashFromCertContext >= 0 )
  {
    CertHashFromCertContext = FveuiEnumSmartCardCerts(1, &hCertStore, 0);
    if ( CertHashFromCertContext < 0 )
    {
      v3 = hCertStore;
    }
    else
    {
      v12 = v2->rgvarg;
      v63 = lVal;
      AuthMethodGuids = GetAuthMethodGuids(v12->llVal, &lpMem, &v54);
      v3 = hCertStore;
      CertHashFromCertContext = AuthMethodGuids;
      if ( AuthMethodGuids < 0 )
        goto LABEL_58;
LABEL_4:
      v14 = CertEnumCertificatesInStore(v3, v4);
      v4 = v14;
      if ( v14 )
      {
        CertHashFromCertContext = FveCertGetCertHashFromCertContext(v14, 0, &dwBytes);
        if ( CertHashFromCertContext < 0 )
          goto LABEL_56;
        v15 = dwBytes;
        ProcessHeap = GetProcessHeap();
        v17 = HeapAlloc(ProcessHeap, 8u, v15);
        v6 = v17;
        if ( !v17 )
        {
          CertHashFromCertContext = -2147024888;
          goto LABEL_58;
        }
        CertHashFromCertContext = FveCertGetCertHashFromCertContext(v4, v17, &dwBytes);
        if ( CertHashFromCertContext < 0 )
          goto LABEL_58;
        for ( i = 0; ; ++i )
        {
          if ( i >= v54 )
          {
            v31 = GetProcessHeap();
            v32 = HeapSize(v31, 0, v6);
            if ( v32 != -1 )
            {
              for ( j = v6; v32; --v32 )
                *j++ = 0;
              v34 = GetProcessHeap();
              HeapFree(v34, 0, v6);
            }
            goto LABEL_4;
          }
          v19 = (__int128 *)((char *)lpMem + 16 * i);
          v20 = v2->rgvarg->llVal;
          v66 = v19;
          if ( (int)UsesProtector(v20, v19, 0x200000, v47) >= 0 )
          {
            if ( v47[0] )
            {
              if ( v5 )
              {
                v21 = GetProcessHeap();
                HeapFree(v21, 0, v5);
                v56 = 0;
              }
              FveAuthInfo = GetFveAuthInfo(v2->rgvarg->llVal, v19, 3, &v56);
              v5 = (void *)v56;
              if ( FveAuthInfo >= 0 && *(_DWORD *)(v56 + 12) == 1 )
              {
                v23 = *(unsigned int ***)(v56 + 16);
                v24 = *v23;
                if ( (*v23)[3] == 7 )
                  break;
              }
            }
          }
LABEL_39:
          ;
        }
        v25 = v24[7];
        if ( (_DWORD)dwBytes == *(unsigned int *)((char *)v24 + v25 + 28) )
        {
          v26 = 0;
          if ( !memcmp_0(v6, (char *)v24 + v25 + 32, (unsigned int)dwBytes) )
          {
LABEL_23:
            CertHashFromCertContext = FveCertGetPrivateKeyHandle(v4, 0, 0, v63, &hObject, &hProv, &hKey, &v55, &v48);
            if ( CertHashFromCertContext < 0 )
              goto LABEL_58;
            v27 = 584;
            v28 = v81;
            do
            {
              *v28++ = 0;
              --v27;
            }
            while ( v27 );
            v82 = hObject;
            v29 = 56;
            v83 = hProv;
            v84 = hKey;
            v85 = v55;
            v30 = &v68;
            v81[0] = 48;
            v81[1] = 1;
            v81[2] = 1;
            v81[3] = 6;
            do
            {
              *(_BYTE *)v30 = 0;
              v30 = (__int128 *)((char *)v30 + 1);
              --v29;
            }
            while ( v29 );
            *(_QWORD *)&v68 = 0x100000038LL;
            *(_QWORD *)&v69 = &v64;
            *((_QWORD *)&v68 + 1) = 0x100400000LL;
            CertHashFromCertContext = FveUnlockVolumeWithAccessMode(v49, &v68, v65);
            if ( v48 && hObject )
            {
              NCryptFreeObject(hObject);
              hObject = 0;
            }
            if ( hProv && v48 )
            {
              if ( hKey )
                CryptDestroyKey(hKey);
              CryptReleaseContext(hProv, 0x40u);
            }
            if ( CertHashFromCertContext == -2146434962 )
              goto LABEL_58;
            if ( CertHashFromCertContext >= 0 )
            {
              if ( v26 && !(unsigned int)FveCertCanCertificateBeAdded(v4, 0) )
              {
                if ( v49 != -1 )
                {
                  FveCloseVolume(v49);
                  v49 = -1;
                }
                if ( !(unsigned int)FveOpenVolumeW(v58->rgvarg->llVal, 1, &v49) )
                {
                  v76[0] = 40;
                  v76[1] = 1;
                  v76[3] = 5;
                  v76[2] = 1;
                  if ( !(unsigned int)FveCertGetPublicKeyHandle(v4, &v60) )
                  {
                    v77 = v60;
                    if ( !(unsigned int)FveCertCreateCertInfo(v4, 0, &v61) )
                    {
                      v79 = v61;
                      v78 = *(_DWORD *)(v61 + 4);
                      v62 = v76;
                      v73 = (unsigned __int64)&v62;
                      *(_QWORD *)&v72 = 0x100000038LL;
                      *((_QWORD *)&v72 + 1) = 0x100200000LL;
                      if ( !(unsigned int)FveAddAuthMethodInformation(v49, &v72, &v80)
                        && !(unsigned int)FveDeleteAuthMethod(v49, v66) )
                      {
                        FveCommitChanges(v49);
                      }
                    }
                  }
                }
              }
              goto LABEL_58;
            }
            v2 = v58;
            goto LABEL_39;
          }
          v2 = v58;
        }
        LODWORD(hCertStore) = 0;
        if ( (int)FveCertIsAlternateCert(v4, v24[4], (char *)v24 + v24[5] + 16, &hCertStore) < 0 || !(_DWORD)hCertStore )
          goto LABEL_39;
        v26 = 1;
        goto LABEL_23;
      }
      CertHashFromCertContext = -2146435027;
LABEL_56:
      v6 = 0;
    }
  }
LABEL_58:
  v35 = v67;
  v67->lVal = CertHashFromCertContext;
  v36 = lpMem;
  v35->vt = 19;
  if ( v36 )
  {
    v37 = GetProcessHeap();
    HeapFree(v37, 0, v36);
  }
  if ( v5 )
  {
    v38 = GetProcessHeap();
    v39 = HeapSize(v38, 0, v5);
    if ( v39 != -1 )
    {
      for ( k = v5; v39; --v39 )
        *k++ = 0;
      v41 = GetProcessHeap();
      HeapFree(v41, 0, v5);
    }
  }
  if ( v6 )
  {
    v42 = GetProcessHeap();
    v43 = HeapSize(v42, 0, v6);
    if ( v43 != -1 )
    {
      for ( m = v6; v43; --v43 )
        *m++ = 0;
      v45 = GetProcessHeap();
      HeapFree(v45, 0, v6);
    }
  }
  if ( v48 && hObject )
  {
    NCryptFreeObject(hObject);
    hObject = 0;
  }
  if ( hProv && v48 )
  {
    if ( hKey )
      CryptDestroyKey(hKey);
    CryptReleaseContext(hProv, 0x40u);
  }
  if ( v4 )
    CertFreeCertificateContext(v4);
  if ( v3 )
    CertCloseStore(v3, 0);
  if ( v49 != -1 )
  {
    FveCloseVolume(v49);
    v49 = -1;
  }
  if ( v60 )
    BCryptDestroyKey(v60);
  if ( v61 )
    FveCertFreeCertInfo();
  return 0;
}

```

## disassembly

```asm
0x180007e20  mov     [rsp-8+arg_10], rbx
0x180007e25  push    rbp
0x180007e26  push    rsi
0x180007e27  push    rdi
0x180007e28  push    r12
0x180007e2a  push    r13
0x180007e2c  push    r14
0x180007e2e  push    r15
0x180007e30  lea     rbp, [rsp-520h]
0x180007e38  sub     rsp, 620h
0x180007e3f  mov     rax, cs:__security_cookie
0x180007e46  xor     rax, rsp
0x180007e49  mov     [rbp+550h+var_40], rax
0x180007e50  xor     ebx, ebx
0x180007e52  mov     [rbp+550h+var_570], rdx
0x180007e56  xorps   xmm0, xmm0
0x180007e59  mov     [rbp+550h+var_5B8], rcx
0x180007e5d  mov     r12, rcx
0x180007e60  mov     [rsp+650h+var_5F8], 0FFFFFFFFFFFFFFFFh
0x180007e69  xor     eax, eax
0x180007e6b  mov     [rsp+650h+hCertStore], rbx
0x180007e70  mov     r15d, 248h
0x180007e76  mov     [rbp+550h+var_5C8], rbx
0x180007e7a  mov     r8d, r15d; Size
0x180007e7d  mov     [rbp+550h+var_538], rax
0x180007e81  xor     edx, edx; Val
0x180007e83  lea     rcx, [rbp+550h+var_290]; void *
0x180007e8a  mov     r13d, ebx
0x180007e8d  mov     r14d, ebx
0x180007e90  mov     esi, ebx
0x180007e92  movups  [rbp+550h+var_568], xmm0
0x180007e96  movups  [rbp+550h+var_558], xmm0
0x180007e9a  movups  [rbp+550h+var_548], xmm0
0x180007e9e  call    memset_0
0x180007ea3  xorps   xmm0, xmm0
0x180007ea6  mov     [rsp+650h+hObject], rbx
0x180007eab  lea     rax, [rbp+550h+var_290]
0x180007eb2  mov     [rsp+650h+hProv], rbx
0x180007eb7  mov     [rbp+550h+var_588], rax
0x180007ebb  lea     rcx, [rbp+550h+var_4F0]; void *
0x180007ebf  xor     eax, eax
0x180007ec1  mov     [rbp+550h+hKey], rbx
0x180007ec5  mov     r8d, r15d; Size
0x180007ec8  mov     [rbp+550h+var_500], rax
0x180007ecc  xor     edx, edx; Val
0x180007ece  mov     [rbp+550h+var_5CC], ebx
0x180007ed1  mov     [rsp+650h+var_5FC], ebx
0x180007ed5  mov     edi, ebx
0x180007ed7  mov     [rbp+550h+lpMem], rbx
0x180007edb  mov     [rbp+550h+var_5D0], ebx
0x180007ede  mov     [rsp+650h+var_600], bl
0x180007ee2  mov     dword ptr [rsp+650h+dwBytes], ebx
0x180007ee6  movups  [rbp+550h+var_530], xmm0
0x180007eea  mov     [rbp+550h+var_598], rbx
0x180007eee  movups  [rbp+550h+var_520], xmm0
0x180007ef2  movups  [rbp+550h+var_510], xmm0
0x180007ef6  call    memset_0
0x180007efb  mov     rcx, [r12]
0x180007eff  lea     r8, [rsp+650h+var_5F8]
0x180007f04  mov     [rbp+550h+var_5A0], rbx
0x180007f08  xorps   xmm0, xmm0
0x180007f0b  mov     [rbp+550h+var_5A8], rbx
0x180007f0f  xor     edx, edx
0x180007f11  movups  [rbp+550h+var_2A0], xmm0
0x180007f18  mov     rax, [rcx+38h]
0x180007f1c  movsxd  r15, dword ptr [rcx+20h]
0x180007f20  mov     rcx, [rcx+8]
0x180007f24  mov     [rbp+550h+var_580], rax
0x180007f28  call    cs:__imp_FveOpenVolumeW
0x180007f2e  mov     ebx, eax
0x180007f30  test    eax, eax
0x180007f32  js      loc_1800083E3
0x180007f38  xor     r8d, r8d
0x180007f3b  lea     rdx, [rsp+650h+hCertStore]
0x180007f40  lea     ecx, [rdi+1]
0x180007f43  call    FveuiEnumSmartCardCerts
0x180007f48  mov     ebx, eax
0x180007f4a  test    eax, eax
0x180007f4c  js      loc_1800083DE
0x180007f52  mov     rcx, [r12]
0x180007f56  lea     r8, [rbp+550h+var_5D0]
0x180007f5a  lea     rdx, [rbp+550h+lpMem]
0x180007f5e  mov     [rbp+550h+var_590], r15
0x180007f62  mov     rcx, [rcx+8]
0x180007f66  call    _GetAuthMethodGuids
0x180007f6b  mov     r13, [rsp+650h+hCertStore]
0x180007f70  mov     ebx, eax
0x180007f72  test    eax, eax
0x180007f74  js      loc_1800083E3
0x180007f7a  mov     rdx, r14; pPrevCertContext
0x180007f7d  mov     rcx, r13; hCertStore
0x180007f80  call    cs:__imp_CertEnumCertificatesInStore
0x180007f86  mov     r14, rax
0x180007f89  test    rax, rax
0x180007f8c  jz      loc_1800083D5
0x180007f92  lea     r8, [rsp+650h+dwBytes]
0x180007f97  xor     edx, edx
0x180007f99  mov     rcx, rax
0x180007f9c  call    cs:__imp_FveCertGetCertHashFromCertContext
0x180007fa2  mov     ebx, eax
0x180007fa4  test    eax, eax
0x180007fa6  js      loc_1800083DA
0x180007fac  mov     ebx, dword ptr [rsp+650h+dwBytes]
0x180007fb0  call    cs:__imp_GetProcessHeap
0x180007fb6  mov     r8d, ebx; dwBytes
0x180007fb9  mov     edx, 8; dwFlags
0x180007fbe  mov     rcx, rax; hHeap
0x180007fc1  call    cs:__imp_HeapAlloc
0x180007fc7  mov     rdi, rax
0x180007fca  test    rax, rax
0x180007fcd  jz      loc_1800083CE
0x180007fd3  lea     r8, [rsp+650h+dwBytes]
0x180007fd8  mov     rdx, rax
0x180007fdb  mov     rcx, r14
0x180007fde  call    cs:__imp_FveCertGetCertHashFromCertContext
0x180007fe4  mov     ebx, eax
0x180007fe6  test    eax, eax
0x180007fe8  js      loc_1800083E3
0x180007fee  xor     r15d, r15d
0x180007ff1  cmp     r15d, [rbp+550h+var_5D0]
0x180007ff5  jnb     loc_180008263
0x180007ffb  mov     rcx, [r12]
0x180007fff  lea     r9, [rsp+650h+var_600]
0x180008004  mov     ebx, r15d
0x180008007  mov     r8d, 200000h
0x18000800d  shl     rbx, 4
0x180008011  add     rbx, [rbp+550h+lpMem]
0x180008015  mov     rcx, [rcx+8]
0x180008019  mov     rdx, rbx
0x18000801c  mov     [rbp+550h+var_578], rbx
0x180008020  call    _UsesProtector
0x180008025  test    eax, eax
0x180008027  js      loc_18000825B
0x18000802d  cmp     [rsp+650h+var_600], 0
0x180008032  jz      loc_18000825B
0x180008038  test    rsi, rsi
0x18000803b  jz      short loc_180008059
0x18000803d  call    cs:__imp_GetProcessHeap
0x180008043  mov     r8, rsi; lpMem
0x180008046  xor     edx, edx; dwFlags
0x180008048  mov     rcx, rax; hHeap
0x18000804b  call    cs:__imp_HeapFree
0x180008051  mov     [rbp+550h+var_5C8], 0
0x180008059  mov     rcx, [r12]
0x18000805d  lea     r9, [rbp+550h+var_5C8]
0x180008061  mov     r8d, 3
0x180008067  mov     rdx, rbx
0x18000806a  mov     rcx, [rcx+8]
0x18000806e  call    _GetFveAuthInfo
0x180008073  mov     rsi, [rbp+550h+var_5C8]
0x180008077  test    eax, eax
0x180008079  js      loc_18000825B
0x18000807f  cmp     dword ptr [rsi+0Ch], 1
0x180008083  jnz     loc_18000825B
0x180008089  mov     rax, [rsi+10h]
0x18000808d  mov     rbx, [rax]
0x180008090  cmp     dword ptr [rbx+0Ch], 7
0x180008094  jnz     loc_18000825B
0x18000809a  mov     eax, [rbx+1Ch]
0x18000809d  mov     ecx, dword ptr [rsp+650h+dwBytes]
0x1800080a1  cmp     ecx, [rax+rbx+1Ch]
0x1800080a5  jnz     short loc_1800080C4
0x1800080a7  mov     r8d, ecx; Size
0x1800080aa  lea     rdx, [rbx+20h]
0x1800080ae  add     rdx, rax; Buf2
0x1800080b1  mov     rcx, rdi; Buf1
0x1800080b4  xor     r12d, r12d
0x1800080b7  call    memcmp_0
0x1800080bc  test    eax, eax
0x1800080be  jz      short loc_180008101
0x1800080c0  mov     r12, [rbp+550h+var_5B8]
0x1800080c4  mov     dword ptr [rsp+650h+hCertStore], 0
0x1800080cc  lea     r9, [rsp+650h+hCertStore]
0x1800080d1  mov     r8d, [rbx+14h]
0x1800080d5  mov     rcx, r14
0x1800080d8  mov     edx, [rbx+10h]
0x1800080db  add     r8, 10h
0x1800080df  add     r8, rbx
0x1800080e2  call    cs:__imp_FveCertIsAlternateCert
0x1800080e8  test    eax, eax
0x1800080ea  js      loc_18000825B
0x1800080f0  cmp     dword ptr [rsp+650h+hCertStore], 0
0x1800080f5  jz      loc_18000825B
0x1800080fb  mov     r12d, 1
0x180008101  mov     r9, [rbp+550h+var_590]
0x180008105  lea     rax, [rsp+650h+var_5FC]
0x18000810a  mov     [rsp+650h+var_610], rax
0x18000810f  xor     r8d, r8d
0x180008112  lea     rax, [rbp+550h+var_5CC]
0x180008116  xor     edx, edx
0x180008118  mov     [rsp+650h+var_618], rax
0x18000811d  mov     rcx, r14
0x180008120  lea     rax, [rbp+550h+hKey]
0x180008124  mov     [rsp+650h+var_620], rax
0x180008129  lea     rax, [rsp+650h+hProv]
0x18000812e  mov     [rsp+650h+var_628], rax
0x180008133  lea     rax, [rsp+650h+hObject]
0x180008138  mov     [rsp+650h+var_630], rax
0x18000813d  call    cs:__imp_FveCertGetPrivateKeyHandle
0x180008143  mov     ebx, eax
0x180008145  test    eax, eax
0x180008147  js      loc_1800083E3
0x18000814d  mov     ecx, 248h
0x180008152  lea     rax, [rbp+550h+var_290]
0x180008159  mov     edx, 1
0x18000815e  mov     byte ptr [rax], 0
0x180008161  add     rax, rdx
0x180008164  sub     rcx, rdx
0x180008167  jnz     short loc_18000815E
0x180008169  mov     rax, [rsp+650h+hObject]
0x18000816e  lea     r8d, [rcx+38h]
0x180008172  mov     [rbp+550h+var_280], rax
0x180008179  mov     ecx, r8d
0x18000817c  mov     rax, [rsp+650h+hProv]
0x180008181  mov     [rbp+550h+var_278], rax
0x180008188  mov     rax, [rbp+550h+hKey]
0x18000818c  mov     [rbp+550h+var_270], rax
0x180008193  mov     eax, [rbp+550h+var_5CC]
0x180008196  mov     [rbp+550h+var_268], eax
0x18000819c  lea     rax, [rbp+550h+var_568]
0x1800081a0  mov     [rbp+550h+var_290], 30h ; '0'
0x1800081aa  mov     [rbp+550h+var_28C], edx
0x1800081b0  mov     [rbp+550h+var_288], edx
0x1800081b6  mov     [rbp+550h+var_284], 6
0x1800081c0  mov     byte ptr [rax], 0
0x1800081c3  add     rax, rdx
0x1800081c6  sub     rcx, rdx
0x1800081c9  jnz     short loc_1800081C0
0x1800081cb  mov     rcx, [rsp+650h+var_5F8]
0x1800081d0  lea     rax, [rbp+550h+var_588]
0x1800081d4  mov     dword ptr [rbp+550h+var_568], r8d
0x1800081d8  mov     r8, [rbp+550h+var_580]
0x1800081dc  mov     dword ptr [rbp+550h+var_568+4], edx
0x1800081df  mov     dword ptr [rbp+550h+var_568+0Ch], edx
0x1800081e2  lea     rdx, [rbp+550h+var_568]
0x1800081e6  mov     qword ptr [rbp+550h+var_558], rax
0x1800081ea  mov     dword ptr [rbp+550h+var_568+8], 400000h
0x1800081f1  call    cs:__imp_FveUnlockVolumeWithAccessMode
0x1800081f7  cmp     [rsp+650h+var_5FC], 0
0x1800081fc  mov     ebx, eax
0x1800081fe  jz      short loc_180008219
0x180008200  mov     rcx, [rsp+650h+hObject]; hObject
0x180008205  test    rcx, rcx
0x180008208  jz      short loc_180008219
0x18000820a  call    cs:__imp_NCryptFreeObject
0x180008210  mov     [rsp+650h+hObject], 0
0x180008219  cmp     [rsp+650h+hProv], 0
0x18000821f  jz      short loc_180008247
0x180008221  cmp     [rsp+650h+var_5FC], 0
0x180008226  jz      short loc_180008247
0x180008228  mov     rcx, [rbp+550h+hKey]; hKey
0x18000822c  test    rcx, rcx
0x18000822f  jz      short loc_180008237
0x180008231  call    cs:__imp_CryptDestroyKey
0x180008237  mov     rcx, [rsp+650h+hProv]; hProv
0x18000823c  mov     edx, 40h ; '@'; dwFlags
0x180008241  call    cs:__imp_CryptReleaseContext
0x180008247  cmp     ebx, 8010006Eh
0x18000824d  jz      loc_1800083E3
0x180008253  test    ebx, ebx
0x180008255  jns     short loc_1800082AE
0x180008257  mov     r12, [rbp+550h+var_5B8]
0x18000825b  inc     r15d
0x18000825e  jmp     loc_180007FF1
0x180008263  call    cs:__imp_GetProcessHeap
0x180008269  mov     r8, rdi; lpMem
0x18000826c  xor     edx, edx; dwFlags
0x18000826e  mov     rcx, rax; hHeap
0x180008271  call    cs:__imp_HeapSize
0x180008277  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000827b  jz      loc_180007F7A
0x180008281  mov     rcx, rdi
0x180008284  test    rax, rax
0x180008287  jz      short loc_180008295
0x180008289  mov     byte ptr [rcx], 0
0x18000828c  inc     rcx
0x18000828f  sub     rax, 1
0x180008293  jnz     short loc_180008289
0x180008295  call    cs:__imp_GetProcessHeap
0x18000829b  mov     r8, rdi; lpMem
0x18000829e  xor     edx, edx; dwFlags
0x1800082a0  mov     rcx, rax; hHeap
0x1800082a3  call    cs:__imp_HeapFree
0x1800082a9  jmp     loc_180007F7A
0x1800082ae  test    r12d, r12d
0x1800082b1  jz      loc_1800083E3
0x1800082b7  xor     edx, edx
0x1800082b9  mov     rcx, r14
0x1800082bc  call    cs:__imp_FveCertCanCertificateBeAdded
0x1800082c2  test    eax, eax
0x1800082c4  jnz     loc_1800083E3
0x1800082ca  mov     rcx, [rsp+650h+var_5F8]
0x1800082cf  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800082d3  jz      short loc_1800082E4
0x1800082d5  call    cs:__imp_FveCloseVolume
0x1800082db  mov     [rsp+650h+var_5F8], 0FFFFFFFFFFFFFFFFh
0x1800082e4  mov     rcx, [rbp+550h+var_5B8]
0x1800082e8  lea     r8, [rsp+650h+var_5F8]
0x1800082ed  mov     r15d, 1
0x1800082f3  mov     edx, r15d
  ... truncated ...
```
