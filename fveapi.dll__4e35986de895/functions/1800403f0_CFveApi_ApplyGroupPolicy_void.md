# CFveApi::ApplyGroupPolicy(void)

- ea: `0x1800403f0`
- end: `0x180041d1d`
- name: `?ApplyGroupPolicy@CFveApi@@QEAAJXZ`
- size: `6445`
- prototype: `__int64 __fastcall(const unsigned __int16 **this)`
- caller_count: `7`
- callee_count: `24`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180040310`
- `0x180069380`
- `0x18006be70`
- `0x18006bfb0`
- `0x18006c0e0`
- `0x18006c270`
- `0x1800ac05c`

## callees

- `0x180008d70`
- `0x1800090c0`
- `0x180009468`
- `0x180009790`
- `0x18000ce10`
- `0x18000d5a0`
- `0x180019128`
- `0x180037f50`
- `0x18003d000`
- `0x1800403f0`
- `0x180041d24`
- `0x180047a48`
- `0x180053a20`
- `0x180053a80`
- `0x180053bac`
- `0x180058cdc`
- `0x180060196`
- `0x1800b1450`
- `0x1800b6964`
- `0x1800ca70c`
- `0x1800ca8b4`
- `0x18011efc2`
- `0x18011efce`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180040d56`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800415df`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180041777`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180041924`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180041c5c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180040d56`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800415df`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180041777`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180041924`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180041c5c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180040d41`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800415cb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180041762`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180041910`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180041c48`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180040d41`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800415cb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180041762`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180041910`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180041c48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040844`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004194b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800419a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040844`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004194b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800419a1`
- `bcrypt!BCryptDestroyKey` at `0x180040e6b`
- `bcrypt!BCryptDestroyKey` at `0x18004174c`
- `bcrypt!BCryptDestroyKey` at `0x180040e6b`
- `bcrypt!BCryptDestroyKey` at `0x18004174c`
- `CRYPT32!CertCloseStore` at `0x180040e8d`
- `CRYPT32!CertCloseStore` at `0x180040e8d`
- `CRYPT32!CertOpenStore` at `0x18004082b`
- `CRYPT32!CertOpenStore` at `0x18004082b`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18004118e`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18004118e`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180041202`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18004123d`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180041202`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18004123d`
- `CRYPT32!CertFreeCertificateContext` at `0x180040d91`
- `CRYPT32!CertFreeCertificateContext` at `0x180040d91`
- `FVECERTS!FveCertGetPublicKeyHandle` at `0x180041626`
- `FVECERTS!FveCertGetPublicKeyHandle` at `0x180041626`
- `FVECERTS!FveCertIsValidCertInfo` at `0x180040f65`
- `FVECERTS!FveCertIsValidCertInfo` at `0x180040f65`
- `FVECERTS!FveCertFreeCertInfo` at `0x180040d76`
- `FVECERTS!FveCertFreeCertInfo` at `0x1800415f0`
- `FVECERTS!FveCertFreeCertInfo` at `0x180041935`
- `FVECERTS!FveCertFreeCertInfo` at `0x180040d76`
- `FVECERTS!FveCertFreeCertInfo` at `0x1800415f0`
- `FVECERTS!FveCertFreeCertInfo` at `0x180041935`
- `FVECERTS!FveCertCanCertificateBeAdded` at `0x1800413f2`
- `FVECERTS!FveCertCanCertificateBeAdded` at `0x1800413f2`
- `FVECERTS!FveCertCreateCertInfo` at `0x180041377`
- `FVECERTS!FveCertCreateCertInfo` at `0x180041377`

## pseudocode

```c
__int64 __fastcall CFveApi::ApplyGroupPolicy(const unsigned __int16 **this)
{
  signed int v2; // ebx
  __int64 v3; // r14
  void *v4; // rsi
  const CERT_CONTEXT *v5; // rdi
  _DWORD *v6; // r12
  void **v7; // r15
  PVOID *v8; // rcx
  __int64 v9; // rdx
  int v10; // ebx
  const unsigned __int16 *v11; // rax
  unsigned int v12; // eax
  HCERTSTORE v13; // rbx
  signed int LastError; // eax
  __int64 v15; // rdx
  __int64 v16; // r9
  struct _GUID *v17; // rax
  signed int AuthMethodGuids; // eax
  unsigned int v19; // r15d
  signed int AuthMethodInformation; // eax
  _OWORD *v21; // rax
  const unsigned __int16 *v22; // rax
  HANDLE v23; // rax
  __int64 j; // rdi
  void *v25; // rcx
  __int64 i; // rbx
  _DWORD *v28; // rdx
  char *v29; // rcx
  unsigned int v30; // eax
  void **v31; // rsi
  const void *v32; // r14
  unsigned __int64 v33; // rcx
  unsigned int v34; // esi
  void *v35; // rax
  _DWORD *v36; // rbx
  _QWORD *v37; // rcx
  __int64 v38; // rdx
  unsigned int v39; // r15d
  void *v40; // rax
  int v41; // r14d
  unsigned int v42; // edi
  size_t v43; // rsi
  __int64 v44; // rbx
  const void *v45; // rdx
  _DWORD *v46; // rsi
  void **v47; // rdi
  PVOID *v48; // rcx
  unsigned int v49; // eax
  int CanCertificateBeAdded; // eax
  int v51; // ebx
  CFveApi *v52; // rcx
  unsigned __int16 *v53; // rbx
  const unsigned __int16 *v54; // rdx
  __int64 v55; // rax
  HANDLE v56; // rax
  unsigned int PublicKeyHandle; // eax
  unsigned int v58; // eax
  CFveApi *v59; // rcx
  HANDLE v60; // rax
  unsigned __int16 *v61; // rbx
  const wchar_t *v62; // rdx
  __int64 v63; // rax
  HANDLE v64; // rax
  signed int v65; // eax
  __int64 v66; // rdx
  __int64 v67; // r9
  signed int v68; // eax
  const struct _GUID *v69; // r14
  int v70; // eax
  unsigned __int16 *v71; // rbx
  const wchar_t *v72; // rdx
  __int64 v73; // rax
  HANDLE ProcessHeap; // rax
  _DWORD *v75; // rbx
  unsigned int v76; // eax
  unsigned int pvPara; // [rsp+20h] [rbp-E0h]
  unsigned int pvParaa; // [rsp+20h] [rbp-E0h]
  unsigned int v79; // [rsp+30h] [rbp-D0h] BYREF
  _OWORD *v80; // [rsp+38h] [rbp-C8h]
  void **v81; // [rsp+40h] [rbp-C0h]
  _DWORD *v82; // [rsp+48h] [rbp-B8h]
  unsigned __int16 *v83; // [rsp+50h] [rbp-B0h] BYREF
  HCERTSTORE hCertStore; // [rsp+58h] [rbp-A8h]
  void *Buf1; // [rsp+60h] [rbp-A0h]
  void *v86; // [rsp+68h] [rbp-98h]
  DWORD pcbData; // [rsp+70h] [rbp-90h] BYREF
  char *v88; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 v89; // [rsp+80h] [rbp-80h] BYREF
  __int64 v90; // [rsp+88h] [rbp-78h] BYREF
  __int64 *v91; // [rsp+90h] [rbp-70h]
  _QWORD v92[2]; // [rsp+98h] [rbp-68h] BYREF
  BCRYPT_KEY_HANDLE hKey; // [rsp+A8h] [rbp-58h] BYREF
  struct _GUID v94; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v95[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v96; // [rsp+D0h] [rbp-30h] BYREF
  __int64 *v97; // [rsp+D8h] [rbp-28h]
  _QWORD **v98; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD **v99; // [rsp+E8h] [rbp-18h]
  __int64 v100; // [rsp+F0h] [rbp-10h] BYREF
  __int64 *v101; // [rsp+F8h] [rbp-8h]
  _QWORD **v102; // [rsp+100h] [rbp+0h] BYREF
  _QWORD **v103; // [rsp+108h] [rbp+8h]
  __int64 v104; // [rsp+110h] [rbp+10h] BYREF
  __int64 *v105; // [rsp+118h] [rbp+18h]
  _QWORD **v106; // [rsp+120h] [rbp+20h] BYREF
  _QWORD **v107; // [rsp+128h] [rbp+28h]
  __int128 v108; // [rsp+130h] [rbp+30h] BYREF
  LPVOID lpMem[2]; // [rsp+140h] [rbp+40h]
  __int128 v110; // [rsp+150h] [rbp+50h]
  __int64 v111; // [rsp+160h] [rbp+60h]
  _DWORD v112[4]; // [rsp+170h] [rbp+70h] BYREF
  BCRYPT_KEY_HANDLE v113; // [rsp+180h] [rbp+80h]
  int v114; // [rsp+188h] [rbp+88h]
  char *v115; // [rsp+190h] [rbp+90h]
  PCCERT_CONTEXT v116; // [rsp+3C0h] [rbp+2C0h] BYREF
  int v117; // [rsp+3C8h] [rbp+2C8h] BYREF
  _QWORD *v118; // [rsp+3D0h] [rbp+2D0h] BYREF
  __int128 *v119; // [rsp+3D8h] [rbp+2D8h]
  const wchar_t *v120; // [rsp+3E0h] [rbp+2E0h]
  const wchar_t *v121; // [rsp+3E8h] [rbp+2E8h]
  PCCERT_CONTEXT *v122; // [rsp+3F0h] [rbp+2F0h]
  __int64 v123; // [rsp+3F8h] [rbp+2F8h]
  __int128 v124; // [rsp+400h] [rbp+300h] BYREF
  __int128 v125; // [rsp+410h] [rbp+310h]
  __int128 v126; // [rsp+420h] [rbp+320h]
  _QWORD *v127; // [rsp+430h] [rbp+330h] BYREF
  __int128 *v128; // [rsp+438h] [rbp+338h]
  const wchar_t *v129; // [rsp+440h] [rbp+340h]
  const wchar_t *v130; // [rsp+448h] [rbp+348h]
  struct _GUID *v131; // [rsp+450h] [rbp+350h]
  __int64 v132; // [rsp+458h] [rbp+358h]
  __int128 v133; // [rsp+460h] [rbp+360h] BYREF
  __int128 v134; // [rsp+470h] [rbp+370h]
  _BYTE v135[24]; // [rsp+480h] [rbp+380h] BYREF
  _DWORD *v136; // [rsp+498h] [rbp+398h] BYREF

  v2 = 0;
  hCertStore = 0;
  LODWORD(v3) = 0;
  v79 = 0;
  v86 = 0;
  v4 = 0;
  v89 = 0;
  v5 = 0;
  v80 = 0;
  v6 = 0;
  v88 = 0;
  v7 = 0;
  v116 = 0;
  pcbData = 0;
  Buf1 = 0;
  v82 = 0;
  v81 = 0;
  v133 = 0;
  v134 = 0;
  memset(v135, 0, sizeof(v135));
  memset_0(v112, 0, 0x248u);
  hKey = 0;
  v136 = 0;
  v108 = 0;
  v111 = 0;
  *(_OWORD *)lpMem = 0;
  v110 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_dac461a5a0973d62c81039952891528d_Traceguids);
  if ( !(unsigned int)CFveApi::IdentificationFieldMatch((CFveApi *)this) )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_101;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      goto LABEL_9;
    v9 = 19;
    goto LABEL_8;
  }
  if ( !(unsigned int)CFveApi::AllowDraManagement((CFveApi *)this) )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_101;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
    {
LABEL_9:
      v6 = 0;
      goto LABEL_101;
    }
    v9 = 20;
LABEL_8:
    WPP_SF_(v8[2], v9, WPP_dac461a5a0973d62c81039952891528d_Traceguids);
    v8 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_9;
  }
  v10 = CFveApiBase::LicenseCheck((CFveApiBase *)this, (wchar_t *)L"SecureStartupFeature-Enabled-Premium");
  if ( v10 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        WPP_dac461a5a0973d62c81039952891528d_Traceguids,
        (unsigned int)v10);
    v90 = 0;
    *(_QWORD *)&v125 = L"hr";
    *((_QWORD *)&v125 + 1) = L"HRESULT";
    *((_QWORD *)&v124 + 1) = v92;
    *(_QWORD *)&v126 = &v117;
    v92[0] = &v124;
    v11 = this[146];
    v120 = L"IdentityGuid";
    v122 = (PCCERT_CONTEXT *)(v11 + 8);
    v121 = L"GUID";
    v118 = v92;
    *(_QWORD *)&v94.Data1 = 0;
    v119 = &v124;
    *(_QWORD *)&v124 = &v118;
    v92[1] = &v118;
    v91 = FVEAPI_PERFORMING_DRA_MANAGEMENT_NOT_SUPPORTED;
    *(_QWORD *)v94.Data4 = 0;
    v95[0] = 0;
    v117 = v10;
    *((_QWORD *)&v126 + 1) = 4;
    v123 = 16;
    FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)&v94, (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v90);
    FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v94);
    v8 = (PVOID *)WPP_GLOBAL_Control;
    v2 = 0;
    goto LABEL_101;
  }
  v117 = 0;
  if ( *((_BYTE *)this + 1158) )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_dac461a5a0973d62c81039952891528d_Traceguids);
    v2 = CFveApiBase::ResolveVolumeMountName((CFveApiBase *)this);
    if ( v2 )
    {
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          23,
          WPP_dac461a5a0973d62c81039952891528d_Traceguids,
          (unsigned int)v2);
        v8 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v2 < 0 )
        goto LABEL_94;
    }
    v12 = CFveApiBase::Open((CFveApiBase *)this, this[49], 0, 1);
    v2 = v12;
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_dac461a5a0973d62c81039952891528d_Traceguids, v12);
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v2 == -2147024891 )
    {
      v2 = 0;
      goto LABEL_94;
    }
    if ( v2 )
    {
      if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x40) != 0 )
      {
        WPP_SF_d(v8[2], 25, WPP_dac461a5a0973d62c81039952891528d_Traceguids, (unsigned int)v2);
        v8 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v2 < 0 )
      {
LABEL_94:
        if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 8) != 0 )
          WPP_SF_(v8[2], 60, WPP_dac461a5a0973d62c81039952891528d_Traceguids);
        CFveApiBase::ResolveVolumeMountName((CFveApiBase *)this);
        CFveApiBase::Open((CFveApiBase *)this, this[49], 0, 0);
        v8 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_98;
      }
    }
    v117 = 1;
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 8) != 0 )
    WPP_SF_(v8[2], 26, WPP_dac461a5a0973d62c81039952891528d_Traceguids);
  hCertStore = CertOpenStore((LPCSTR)0xD, 0, 0, 0x88000u, L"FVE");
  v13 = hCertStore;
  if ( !hCertStore )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      goto LABEL_93;
    v15 = 27;
    v16 = (unsigned int)v2;
LABEL_49:
    WPP_SF_d(v8[2], v15, WPP_dac461a5a0973d62c81039952891528d_Traceguids, v16);
    v8 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_93;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_dac461a5a0973d62c81039952891528d_Traceguids);
  if ( (unsigned int)CFveApiBase::GetAuthMethodGuids((CFveApiBase *)this, 0, 0, &v79) != 1 )
  {
    v2 = -2147467259;
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_dac461a5a0973d62c81039952891528d_Traceguids, 2147500037LL);
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
LABEL_57:
    LODWORD(v3) = v79;
    goto LABEL_93;
  }
  v3 = v79;
  if ( v79 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_dac461a5a0973d62c81039952891528d_Traceguids, v79);
    v17 = (struct _GUID *)CFveApiBase::ZeroAlloc(16 * v3);
    v86 = v17;
    if ( !v17 )
    {
      v16 = 2147942414LL;
      v2 = -2147024882;
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
        goto LABEL_93;
      v15 = 31;
      goto LABEL_49;
    }
    AuthMethodGuids = CFveApiBase::GetAuthMethodGuids((CFveApiBase *)this, v17, v3, &v79);
    v2 = AuthMethodGuids;
    if ( AuthMethodGuids == 1 )
    {
      v2 = -2147467259;
    }
    else if ( !AuthMethodGuids )
    {
      goto LABEL_73;
    }
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        32,
        WPP_dac461a5a0973d62c81039952891528d_Traceguids,
        (unsigned int)v2);
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v2 < 0 )
      goto LABEL_57;
LABEL_73:
    v3 = v79;
    v82 = CFveApiBase::ZeroAlloc(4LL * v79);
    if ( !v82 )
    {
      v16 = 2147942414LL;
      v2 = -2147024882;
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
        goto LABEL_93;
      v15 = 33;
      goto LABEL_49;
    }
    v81 = (void **)CFveApiBase::ZeroAlloc(8 * v3);
    v7 = v81;
    if ( !v81 )
    {
      v16 = 2147942414LL;
      v2 = -2147024882;
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
        goto LABEL_93;
      v15 = 34;
      goto LABEL_49;
    }
    v19 = 0;
LABEL_82:
    v80 = 0;
    if ( v19 >= (unsigned int)v3 )
    {
      v5 = v116;
      v13 = hCertStore;
      goto LABEL_171;
    }
    v89 = 56;
    *(_QWORD *)&v133 = 0x100000038LL;
    DWORD2(v133) = 1;
    *(_OWORD *)&v135[8] = *((_OWORD *)v86 + v19);
    AuthMethodInformation = CFveApiBase::GetAuthMethodInformation(
                              (CFveApiBase *)this,
                              (struct _FVE_AUTH_INFORMATION *)&v133,
                              0x38u,
                              &v89);
    v2 = AuthMethodInformation;
    if ( AuthMethodInformation && AuthMethodInformation != -2147024774 )
      goto LABEL_169;
    v21 = CFveApiBase::ZeroAlloc(v89);
    v80 = v21;
    v4 = v21;
    if ( !v21 )
    {
      v2 = -2147024882;
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_dac461a5a0973d62c81039952891528d_Traceguids, 2147942414LL);
LABEL_169:
        v8 = (PVOID *)WPP_GLOBAL_Control;
      }
LABEL_91:
      v7 = v81;
LABEL_92:
      v5 = v116;
      goto LABEL_93;
    }
    *v21 = v133;
    v21[1] = v134;
    v21[2] = *(_OWORD *)v135;
    *((_QWORD *)v21 + 6) = *(_QWORD *)&v135[16];
    v2 = CFveApiBase::GetAuthMethodInformation((CFveApiBase *)this, (struct _FVE_AUTH_INFORMATION *)v21, v89, &v89);
    if ( v2 )
    {
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          36,
          WPP_dac461a5a0973d62c81039952891528d_Traceguids,
          (unsigned int)v2);
        v8 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v2 < 0 )
        goto LABEL_91;
    }
    else
    {
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( (*((_DWORD *)v4 + 2) & 0x200000) == 0 )
      goto LABEL_159;
    if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 8) != 0 )
      WPP_SF_(v8[2], 37, WPP_dac461a5a0973d62c81039952891528d_Traceguids);
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      if ( (unsigned int)i >= *((_DWORD *)v4 + 3) )
        goto LABEL_158;
      v28 = *(_DWORD **)(*((_QWORD *)v4 + 2) + 8 * i);
      if ( v28[3] == 7 )
      {
        v29 = (char *)v28 + (unsigned int)v28[7] + 16;
        v88 = v29;
        v30 = v28[6];
        if ( v30 < 0x11 || v30 != *((_DWORD *)v29 + 1) || !(unsigned int)FveCertIsValidCertInfo(v29) )
        {
          v37 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            v38 = 38;
LABEL_156:
            WPP_SF_(v37[2], v38, WPP_dac461a5a0973d62c81039952891528d_Traceguids);
          }
LABEL_157:
          v88 = 0;
LABEL_158:
          LODWORD(v3) = v79;
LABEL_159:
          CFveApiBase::ZeroFree(v4, v89);
          v4 = 0;
          v89 = 0;
          ++v19;
          goto LABEL_82;
        }
        if ( (v88[8] & 1) == 0 )
        {
          v37 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          {
            v38 = 39;
            goto LABEL_156;
          }
          goto LABEL_157;
        }
        v31 = v81;
        v32 = v88 + 16;
        v33 = *((unsigned int *)v88 + 3);
        v88 = 0;
        if ( v81[v19] || v82[v19] )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_dac461a5a0973d62c81039952891528d_Traceguids);
          v36 = v82;
          CFveApiBase::ZeroFree(v31[v19], (unsigned int)v82[v19]);
          v36[v19] = 0;
          v31[v19] = 0;
          v4 = v80;
          goto LABEL_158;
        }
        v82[v19] = v33;
        v34 = v33;
        v35 = CFveApiBase::ZeroAlloc(v33);
        v81[v19] = v35;
        if ( !v35 )
        {
          v2 = -2147024882;
          v8 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              41,
              WPP_dac461a5a0973d62c81039952891528d_Traceguids,
              2147942414LL);
            v8 = (PVOID *)WPP_GLOBAL_Control;
          }
          v7 = v81;
          goto LABEL_164;
        }
        memcpy_0(v35, v32, v34);
        v4 = v80;
      }
    }
  }
LABEL_171:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_dac461a5a0973d62c81039952891528d_Traceguids);
  v39 = v79;
  while ( 1 )
  {
    v116 = CertEnumCertificatesInStore(v13, v5);
    v5 = v116;
    if ( !v116 )
    {
      LODWORD(v3) = v79;
      v7 = v81;
      while ( (unsigned int)v4 < (unsigned int)v3 )
      {
        if ( v7[(unsigned int)v4] )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_dac461a5a0973d62c81039952891528d_Traceguids);
          v69 = (const struct _GUID *)((char *)v86 + 16 * (unsigned int)v4);
          v70 = CFveApiBase::LicenseCheck((CFveApiBase *)this, (wchar_t *)L"SecureStartupFeature-Enabled-Premium");
          v2 = CFveApi::DeleteAuthMethod((CFveApi *)this, v69, v70 == 0);
          if ( v2 )
          {
            v8 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                57,
                WPP_dac461a5a0973d62c81039952891528d_Traceguids,
                (unsigned int)v2);
              v8 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( v2 < 0 )
            {
LABEL_164:
              LODWORD(v3) = v79;
              goto LABEL_165;
            }
          }
          v83 = 0;
          CFveApi::GetThumbprintString((CFveApi *)v8, (unsigned __int8 *)v88 + 16, *((_DWORD *)v88 + 3), &v83);
          v104 = 0;
          v105 = 0;
          v127 = &v106;
          v129 = L"ProtectorGuid";
          v128 = (__int128 *)&v106;
          v90 = 0;
          v106 = &v127;
          v91 = 0;
          v92[0] = 0;
          v71 = v83;
          v107 = &v127;
          v130 = L"GUID";
          v131 = (struct _GUID *)v69;
          v132 = 16;
          v124 = 0;
          v125 = 0;
          v126 = 0;
          FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)&v124, L"GUID", L"Thumbprint", v83, pvPara);
          if ( *v107 != &v106 )
            goto LABEL_276;
          *((_QWORD *)&v124 + 1) = v107;
          *(_QWORD *)&v124 = &v106;
          *v107 = &v124;
          v73 = (__int64)(this[146] + 8);
          v120 = L"IdentityGuid";
          v122 = (PCCERT_CONTEXT *)v73;
          v121 = v72;
          v123 = 16;
          if ( (_QWORD ***)v124 != &v106 )
            goto LABEL_276;
          v118 = &v106;
          v119 = &v124;
          *(_QWORD *)&v124 = &v118;
          v107 = &v118;
          v105 = FVEAPI_DRA_PROTECTOR_REMOVED;
          FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)&v90, (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v104);
          FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v90);
          if ( v71 )
          {
            ProcessHeap = GetProcessHeap();
            HeapFree(ProcessHeap, 0, v71);
          }
          v75 = v82;
          CFveApiBase::ZeroFree(v7[(unsigned int)v4], (unsigned int)v82[(unsigned int)v4]);
          LODWORD(v3) = v79;
          v7[(unsigned int)v4] = 0;
          v75[(unsigned int)v4] = 0;
        }
        LODWORD(v4) = (_DWORD)v4 + 1;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_dac461a5a0973d62c81039952891528d_Traceguids);
      v76 = CFveApiBase::CommitChangesHelper(this, 0, 0, 0);
      v2 = v76;
      if ( v76 )
      {
        v8 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
          goto LABEL_165;
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_dac461a5a0973d62c81039952891528d_Traceguids, v76);
      }
      v8 = (PVOID *)WPP_GLOBAL_Control;
LABEL_165:
      v4 = v80;
      goto LABEL_92;
    }
    if ( Buf1 )
    {
      CFveApiBase::ZeroFree(Buf1, pcbData);
      Buf1 = 0;
      pcbData = 0;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_dac461a5a0973d62c81039952891528d_Traceguids);
    if ( !CertGetCertificateContextProperty(v5, 3u, 0, &pcbData) )
      break;
    v40 = CFveApiBase::ZeroAlloc(pcbData);
    Buf1 = v40;
    if ( !v40 )
    {
      v67 = 2147942414LL;
      v2 = -2147024882;
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        v66 = 45;
        goto LABEL_257;
      }
      goto LABEL_258;
    }
    if ( !CertGetCertificateContextProperty(v5, 3u, v40, &pcbData) )
    {
      v65 = GetLastError();
      v2 = v65;
      if ( v65 > 0 )
        v2 = (unsigned __int16)v65 | 0x80070000;
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        v66 = 46;
        goto LABEL_256;
      }
      goto LABEL_258;
    }
    v41 = 0;
    v42 = 0;
    v43 = pcbData;
    while ( v42 < v39 )
    {
      v44 = v42;
      v45 = v81[v42];
      if ( v45 && (_DWORD)v43 == v82[v42] && !memcmp_0(Buf1, v45, v43) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_dac461a5a0973d62c81039952891528d_Traceguids);
        v46 = v82;
        v41 = 1;
        v47 = v81;
        CFveApiBase::ZeroFree(v81[v44], (unsigned int)v82[v44]);
        v47[v44] = 0;
        v46[v44] = 0;
        break;
      }
      ++v42;
    }
    v48 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_dac461a5a0973d62c81039952891528d_Traceguids);
      v48 = (PVOID *)WPP_GLOBAL_Control;
    }
    v5 = v116;
    LODWORD(v4) = 0;
    v13 = hCertStore;
    if ( !v41 )
    {
      v94 = 0;
      if ( v48 != &WPP_GLOBAL_Control && (*((_BYTE *)v48 + 28) & 8) != 0 )
        WPP_SF_(v48[2], 49, WPP_dac461a5a0973d62c81039952891528d_Traceguids);
      v49 = FveCertCreateCertInfo(v5, 1, &v88);
      v2 = v49;
      if ( v49 )
      {
        v8 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_dac461a5a0973d62c81039952891528d_Traceguids, v49);
          v8 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v2 < 0 )
          goto LABEL_258;
      }
      else
      {
        v8 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 8) != 0 )
        WPP_SF_(v8[2], 51, WPP_dac461a5a0973d62c81039952891528d_Traceguids);
      CanCertificateBeAdded = FveCertCanCertificateBeAdded(v5, 1);
      v51 = CanCertificateBeAdded;
      if ( CanCertificateBeAdded >= 0 )
      {
        v112[0] = 40;
        v112[1] = 1;
        v112[2] = 1;
        v112[3] = 5;
        PublicKeyHandle = FveCertGetPublicKeyHandle(v5, &hKey);
        v2 = PublicKeyHandle;
        if ( PublicKeyHandle )
        {
          v8 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              53,
              WPP_dac461a5a0973d62c81039952891528d_Traceguids,
              PublicKeyHandle);
            v8 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v2 < 0 )
            goto LABEL_258;
        }
        else
        {
          v8 = (PVOID *)WPP_GLOBAL_Control;
        }
        v113 = hKey;
        v115 = v88;
        v114 = *((_DWORD *)v88 + 1);
        v136 = v112;
        lpMem[0] = &v136;
        *(_QWORD *)&v108 = 0x100000038LL;
        *((_QWORD *)&v108 + 1) = 0x100200000LL;
        lpMem[1] = 0;
        if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 8) != 0 )
          WPP_SF_(v8[2], 54, WPP_dac461a5a0973d62c81039952891528d_Traceguids);
        v58 = CFveApi::AddAuthMethodInformation(
                (CFveApi *)this,
                (const struct _FVE_AUTH_INFORMATION *)&v108,
                &v94,
                0,
                0,
                0);
        v2 = v58;
        if ( v58 )
        {
          v8 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_dac461a5a0973d62c81039952891528d_Traceguids, v58);
            v8 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v2 < 0 )
            goto LABEL_258;
        }
        BCryptDestroyKey(hKey);
        hKey = 0;
        if ( lpMem[1] )
        {
          v60 = GetProcessHeap();
          HeapFree(v60, 0, lpMem[1]);
          lpMem[1] = 0;
        }
        v83 = 0;
        CFveApi::GetThumbprintString(v59, (unsigned __int8 *)v88 + 16, *((_DWORD *)v88 + 3), &v83);
        v61 = v83;
        v131 = &v94;
        v129 = L"ProtectorGuid";
        v100 = 0;
        v127 = &v102;
        v101 = 0;
        v128 = (__int128 *)&v102;
        v90 = 0;
        v102 = &v127;
        v91 = 0;
        v103 = &v127;
        v92[0] = 0;
        v130 = L"GUID";
        v132 = 16;
        v124 = 0;
        v125 = 0;
        v126 = 0;
        FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)&v124, L"GUID", L"Thumbprint", v83, pvParaa);
        if ( *v103 != &v102 )
          goto LABEL_276;
        *((_QWORD *)&v124 + 1) = v103;
        *(_QWORD *)&v124 = &v102;
        *v103 = &v124;
        v63 = (__int64)(this[146] + 8);
        v120 = L"IdentityGuid";
        v122 = (PCCERT_CONTEXT *)v63;
        v121 = v62;
        v123 = 16;
        if ( (_QWORD ***)v124 != &v102 )
LABEL_276:
          __fastfail(3u);
        v118 = &v102;
        v119 = &v124;
        *(_QWORD *)&v124 = &v118;
        v103 = &v118;
        v101 = FVEAPI_DRA_PROTECTOR_CREATED;
        FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)&v90, (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v100);
        FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v90);
        if ( v61 )
        {
          v64 = GetProcessHeap();
          HeapFree(v64, 0, v61);
        }
        FveCertFreeCertInfo(v88);
        v88 = 0;
      }
      else
      {
        v52 = (CFveApi *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            52,
            WPP_dac461a5a0973d62c81039952891528d_Traceguids,
            (unsigned int)CanCertificateBeAdded);
        v83 = 0;
        CFveApi::GetThumbprintString(v52, (unsigned __int8 *)v88 + 16, *((_DWORD *)v88 + 3), &v83);
        LODWORD(v116) = v51;
        v53 = v83;
        v120 = L"hr";
        v122 = &v116;
        v121 = L"HRESULT";
        v96 = 0;
        v118 = &v98;
        v97 = 0;
        v119 = (__int128 *)&v98;
        v90 = 0;
        v98 = &v118;
        v99 = &v118;
        v91 = 0;
        v92[0] = 0;
        v123 = 4;
        v124 = 0;
        v125 = 0;
        v126 = 0;
        FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)&v124, v54, L"Thumbprint", v83, pvPara);
        if ( *v99 != &v98 )
          goto LABEL_276;
        *((_QWORD *)&v124 + 1) = v99;
        *(_QWORD *)&v124 = &v98;
        *v99 = &v124;
        v55 = (__int64)(this[146] + 8);
        v129 = L"IdentityGuid";
        v131 = (struct _GUID *)v55;
        v130 = L"GUID";
        v132 = 16;
        if ( (_QWORD ***)v124 != &v98 )
          goto LABEL_276;
        v127 = &v98;
        v128 = &v124;
        *(_QWORD *)&v124 = &v127;
        v99 = &v127;
        v97 = FVEAPI_DRA_PROTECTOR_CREATE_FAILED;
        FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)&v90, (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v96);
        FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v90);
        if ( v53 )
        {
          v56 = GetProcessHeap();
          HeapFree(v56, 0, v53);
        }
        FveCertFreeCertInfo(v88);
      }
      v13 = hCertStore;
    }
  }
  v68 = GetLastError();
  v2 = v68;
  if ( v68 > 0 )
    v2 = (unsigned __int16)v68 | 0x80070000;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    v66 = 44;
LABEL_256:
    v67 = (unsigned int)v2;
LABEL_257:
    WPP_SF_d(v8[2], v66, WPP_dac461a5a0973d62c81039952891528d_Traceguids, v67);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_258:
  LODWORD(v3) = v79;
  v7 = v81;
  v4 = v80;
LABEL_93:
  if ( v117 )
    goto LABEL_94;
LABEL_98:
  if ( v2 < 0 )
  {
    *(_QWORD *)&v94.Data1 = 0;
    v129 = L"hr";
    v131 = (struct _GUID *)&v116;
    v130 = L"HRESULT";
    v120 = L"IdentityGuid";
    v128 = (__int128 *)v95;
    v121 = L"GUID";
    v95[0] = &v127;
    v22 = this[146];
    v90 = 0;
    v122 = (PCCERT_CONTEXT *)(v22 + 8);
    v118 = v95;
    v119 = (__int128 *)&v127;
    v127 = &v118;
    v95[1] = &v118;
    *(_QWORD *)v94.Data4 = FVEAPI_PERFORMING_DRA_MANAGEMENT_FAILED;
    v91 = 0;
    v92[0] = 0;
    LODWORD(v116) = v2;
    v132 = 4;
    v123 = 16;
    FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)&v90, (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v94);
    FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v90);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  v6 = v82;
LABEL_101:
  if ( lpMem[1] )
  {
    v23 = GetProcessHeap();
    HeapFree(v23, 0, lpMem[1]);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v88 )
  {
    FveCertFreeCertInfo(v88);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v5 )
  {
    CertFreeCertificateContext(v5);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( Buf1 )
  {
    CFveApiBase::ZeroFree(Buf1, pcbData);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 )
  {
    CFveApiBase::ZeroFree(v4, v89);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v7 )
  {
    for ( j = 0; (unsigned int)j < (unsigned int)v3; j = (unsigned int)(j + 1) )
    {
      v25 = v7[j];
      if ( v25 )
      {
        CFveApiBase::ZeroFree(v25, (unsigned int)v6[j]);
        v7[j] = 0;
        v6[j] = 0;
      }
    }
    CFveApiBase::ZeroFree(v7, 8LL * (unsigned int)v3);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v6 )
  {
    CFveApiBase::ZeroFree(v6, 4LL * (unsigned int)v3);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v86 )
  {
    CFveApiBase::ZeroFree(v86, 16LL * (unsigned int)v3);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( hKey )
  {
    BCryptDestroyKey(hKey);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( hCertStore )
  {
    CertCloseStore(hCertStore, 0);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x20) != 0 )
    WPP_SF_d(v8[2], 61, WPP_dac461a5a0973d62c81039952891528d_Traceguids, (unsigned int)v2);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800403f0  push    rbp
0x1800403f2  push    rbx
0x1800403f3  push    rsi
0x1800403f4  push    rdi
0x1800403f5  push    r12
0x1800403f7  push    r13
0x1800403f9  push    r14
0x1800403fb  push    r15
0x1800403fd  lea     rbp, [rsp-3B8h]
0x180040405  sub     rsp, 4B8h
0x18004040c  mov     rax, cs:__security_cookie
0x180040413  xor     rax, rsp
0x180040416  mov     [rbp+3F0h+var_50], rax
0x18004041d  xorps   xmm0, xmm0
0x180040420  mov     r13, rcx
0x180040423  xor     ecx, ecx
0x180040425  xor     eax, eax
0x180040427  mov     ebx, ecx
0x180040429  mov     [rsp+4F0h+hCertStore], rcx
0x18004042e  mov     r14d, ecx
0x180040431  mov     [rsp+4F0h+var_4C0], ecx
0x180040435  mov     [rsp+4F0h+var_488], rcx
0x18004043a  mov     esi, ecx
0x18004043c  mov     [rbp+3F0h+var_470], rcx
0x180040440  mov     edi, ecx
0x180040442  mov     [rsp+4F0h+var_4B8], rcx
0x180040447  mov     r12d, ecx
0x18004044a  mov     [rsp+4F0h+var_478], rcx
0x18004044f  mov     r15d, ecx
0x180040452  mov     [rbp+3F0h+var_130], rcx
0x180040459  xor     edx, edx; Val
0x18004045b  mov     [rsp+4F0h+pcbData], ecx
0x18004045f  mov     r8d, 248h; Size
0x180040465  mov     [rsp+4F0h+Buf1], rcx
0x18004046a  mov     [rsp+4F0h+var_4A8], rcx
0x18004046f  mov     [rsp+4F0h+var_4B0], rcx
0x180040474  lea     rcx, [rbp+3F0h+var_380]; void *
0x180040478  movups  [rbp+3F0h+var_90], xmm0
0x18004047f  mov     [rbp+3F0h+var_60], rax
0x180040486  movups  [rbp+3F0h+var_80], xmm0
0x18004048d  movups  [rbp+3F0h+var_70], xmm0
0x180040494  call    memset_0
0x180040499  xorps   xmm0, xmm0
0x18004049c  mov     [rbp+3F0h+hKey], rbx
0x1800404a0  xor     eax, eax
0x1800404a2  mov     [rbp+3F0h+var_58], rbx
0x1800404a9  movups  [rbp+3F0h+var_3C0], xmm0
0x1800404ad  mov     [rbp+3F0h+var_390], rax
0x1800404b1  movups  xmmword ptr [rbp+3F0h+lpMem], xmm0
0x1800404b5  movups  [rbp+3F0h+var_3A0], xmm0
0x1800404b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800404c0  lea     rax, WPP_GLOBAL_Control
0x1800404c7  cmp     rcx, rax
0x1800404ca  jz      short loc_1800404E6
0x1800404cc  test    byte ptr [rcx+1Ch], 20h
0x1800404d0  jz      short loc_1800404E6
0x1800404d2  mov     rcx, [rcx+10h]
0x1800404d6  lea     edx, [r15+12h]
0x1800404da  lea     r8, WPP_dac461a5a0973d62c81039952891528d_Traceguids
0x1800404e1  call    WPP_SF_
0x1800404e6  mov     rcx, r13; this
0x1800404e9  call    ?IdentificationFieldMatch@CFveApi@@AEAAHXZ; CFveApi::IdentificationFieldMatch(void)
0x1800404ee  test    eax, eax
0x1800404f0  jnz     short loc_180040534
0x1800404f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800404f9  lea     r13, WPP_GLOBAL_Control
0x180040500  cmp     rcx, r13
0x180040503  jz      loc_180040D3A
0x180040509  mov     r12b, 8
0x18004050c  test    [rcx+1Ch], r12b
0x180040510  jz      short loc_18004052C
0x180040512  lea     edx, [rax+13h]
0x180040515  mov     rcx, [rcx+10h]
0x180040519  lea     r8, WPP_dac461a5a0973d62c81039952891528d_Traceguids
0x180040520  call    WPP_SF_
0x180040525  mov     rcx, cs:WPP_GLOBAL_Control
0x18004052c  mov     r12, rbx
0x18004052f  jmp     loc_180040D3A
0x180040534  mov     rcx, r13; this
0x180040537  call    ?AllowDraManagement@CFveApi@@AEAAHXZ; CFveApi::AllowDraManagement(void)
0x18004053c  test    eax, eax
0x18004053e  jnz     short loc_180040565
0x180040540  mov     rcx, cs:WPP_GLOBAL_Control
0x180040547  lea     r13, WPP_GLOBAL_Control
0x18004054e  cmp     rcx, r13
0x180040551  jz      loc_180040D3A
0x180040557  mov     r12b, 8
0x18004055a  test    [rcx+1Ch], r12b
0x18004055e  jz      short loc_18004052C
0x180040560  lea     edx, [rax+14h]
0x180040563  jmp     short loc_180040515
0x180040565  lea     rdx, aSecurestartupf_0; "SecureStartupFeature-Enabled-Premium"
0x18004056c  mov     rcx, r13; this
0x18004056f  call    ?LicenseCheck@CFveApiBase@@QEAAJPEBG@Z; CFveApiBase::LicenseCheck(ushort const *)
0x180040574  mov     ebx, eax
0x180040576  test    eax, eax
0x180040578  jns     loc_1800406AA
0x18004057e  mov     rcx, cs:WPP_GLOBAL_Control
0x180040585  lea     rax, WPP_GLOBAL_Control
0x18004058c  cmp     rcx, rax
0x18004058f  jz      short loc_1800405AF
0x180040591  test    byte ptr [rcx+1Ch], 4
0x180040595  jz      short loc_1800405AF
0x180040597  mov     rcx, [rcx+10h]
0x18004059b  lea     r8, WPP_dac461a5a0973d62c81039952891528d_Traceguids
0x1800405a2  mov     edx, 15h
0x1800405a7  mov     r9d, ebx
0x1800405aa  call    WPP_SF_d
0x1800405af  lea     rax, aHr; "hr"
0x1800405b6  mov     [rbp+3F0h+var_468], rsi
0x1800405ba  mov     qword ptr [rbp+3F0h+var_E0], rax
0x1800405c1  lea     rcx, aHresult; "HRESULT"
0x1800405c8  mov     qword ptr [rbp+3F0h+var_E0+8], rcx
0x1800405cf  lea     rax, [rbp+3F0h+var_458]
0x1800405d3  mov     qword ptr [rbp+3F0h+var_F0+8], rax
0x1800405da  lea     rdx, [rbp+3F0h+var_128]
0x1800405e1  mov     qword ptr [rbp+3F0h+var_D0], rdx
0x1800405e8  lea     rax, [rbp+3F0h+var_F0]
0x1800405ef  mov     [rbp+3F0h+var_458], rax
0x1800405f3  lea     rdx, aIdentityguid; "IdentityGuid"
0x1800405fa  mov     rax, [r13+490h]
0x180040601  lea     rcx, aGuid; "GUID"
0x180040608  add     rax, 10h
0x18004060c  mov     [rbp+3F0h+var_110], rdx
0x180040613  mov     [rbp+3F0h+var_100], rax
0x18004061a  lea     rdx, [rbp+3F0h+var_468]; struct _FVEAPI_EVENT_DATA_COLLECTION *
0x18004061e  lea     rax, [rbp+3F0h+var_458]
0x180040622  mov     [rbp+3F0h+var_108], rcx
0x180040629  mov     [rbp+3F0h+var_120], rax
0x180040630  lea     rcx, [rbp+3F0h+var_440]; this
0x180040634  lea     rax, [rbp+3F0h+var_F0]
0x18004063b  mov     qword ptr [rbp+3F0h+var_440.Data1], rsi
0x18004063f  mov     [rbp+3F0h+var_118], rax
0x180040646  lea     rax, [rbp+3F0h+var_120]
0x18004064d  mov     qword ptr [rbp+3F0h+var_F0], rax
0x180040654  lea     rax, [rbp+3F0h+var_120]
0x18004065b  mov     [rbp+3F0h+var_450], rax
0x18004065f  lea     rax, FVEAPI_PERFORMING_DRA_MANAGEMENT_NOT_SUPPORTED
0x180040666  mov     [rbp+3F0h+var_460], rax
0x18004066a  mov     qword ptr [rbp+3F0h+var_440.Data4], rsi
0x18004066e  mov     [rbp+3F0h+var_430], rsi
0x180040672  mov     [rbp+3F0h+var_128], ebx
0x180040678  mov     qword ptr [rbp+3F0h+var_D0+8], 4
0x180040683  mov     [rbp+3F0h+var_F8], 10h
0x18004068e  call    ?LogFveApiEvent@FveEventLogHandle@@QEAAJPEAU_FVEAPI_EVENT_DATA_COLLECTION@@@Z; FveEventLogHandle::LogFveApiEvent(_FVEAPI_EVENT_DATA_COLLECTION *)
0x180040693  lea     rcx, [rbp+3F0h+var_440]; this
0x180040697  call    ?EventLogCleanup@FveEventLogHandle@@AEAAXXZ; FveEventLogHandle::EventLogCleanup(void)
0x18004069c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800406a3  xor     ebx, ebx
0x1800406a5  jmp     loc_180040D33
0x1800406aa  mov     r12b, 8
0x1800406ad  mov     [rbp+3F0h+var_128], esi
0x1800406b3  cmp     [r13+486h], sil
0x1800406ba  jnz     loc_1800407E3
0x1800406c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800406c7  lea     rax, WPP_GLOBAL_Control
0x1800406ce  cmp     rcx, rax
0x1800406d1  jz      short loc_1800406EE
0x1800406d3  test    [rcx+1Ch], r12b
0x1800406d7  jz      short loc_1800406EE
0x1800406d9  mov     rcx, [rcx+10h]
0x1800406dd  lea     r8, WPP_dac461a5a0973d62c81039952891528d_Traceguids
0x1800406e4  mov     edx, 16h
0x1800406e9  call    WPP_SF_
0x1800406ee  mov     rcx, r13; this
0x1800406f1  call    ?ResolveVolumeMountName@CFveApiBase@@QEAAJXZ; CFveApiBase::ResolveVolumeMountName(void)
0x1800406f6  mov     ebx, eax
0x1800406f8  test    eax, eax
0x1800406fa  jz      short loc_18004073C
0x1800406fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180040703  lea     rax, WPP_GLOBAL_Control
0x18004070a  cmp     rcx, rax
0x18004070d  jz      short loc_180040734
0x18004070f  test    byte ptr [rcx+1Ch], 40h
0x180040713  jz      short loc_180040734
0x180040715  mov     rcx, [rcx+10h]
0x180040719  lea     r8, WPP_dac461a5a0973d62c81039952891528d_Traceguids
0x180040720  mov     edx, 17h
0x180040725  mov     r9d, ebx
0x180040728  call    WPP_SF_d
0x18004072d  mov     rcx, cs:WPP_GLOBAL_Control
0x180040734  test    ebx, ebx
0x180040736  js      loc_180040BE4
0x18004073c  mov     rdx, [r13+188h]; unsigned __int16 *
0x180040743  mov     r9b, 1; bool
0x180040746  xor     r8d, r8d; unsigned int
0x180040749  mov     rcx, r13; this
0x18004074c  call    ?Open@CFveApiBase@@QEAAJPEBGK_N@Z; CFveApiBase::Open(ushort const *,ulong,bool)
0x180040751  mov     ebx, eax
0x180040753  mov     rcx, cs:WPP_GLOBAL_Control
0x18004075a  lea     rdx, WPP_GLOBAL_Control
0x180040761  cmp     rcx, rdx
0x180040764  jz      short loc_180040792
0x180040766  test    [rcx+1Ch], r12b
0x18004076a  jz      short loc_180040792
0x18004076c  mov     rcx, [rcx+10h]
0x180040770  lea     r8, WPP_dac461a5a0973d62c81039952891528d_Traceguids
0x180040777  mov     edx, 18h
0x18004077c  mov     r9d, eax
0x18004077f  call    WPP_SF_d
0x180040784  mov     rcx, cs:WPP_GLOBAL_Control
0x18004078b  lea     rdx, WPP_GLOBAL_Control
0x180040792  cmp     ebx, 80070005h
0x180040798  jnz     short loc_1800407A1
0x18004079a  xor     ebx, ebx
0x18004079c  jmp     loc_180040BE4
0x1800407a1  test    ebx, ebx
0x1800407a3  jz      short loc_1800407D7
0x1800407a5  cmp     rcx, rdx
0x1800407a8  jz      short loc_1800407CF
0x1800407aa  test    byte ptr [rcx+1Ch], 40h
0x1800407ae  jz      short loc_1800407CF
0x1800407b0  mov     rcx, [rcx+10h]
0x1800407b4  lea     r8, WPP_dac461a5a0973d62c81039952891528d_Traceguids
0x1800407bb  mov     edx, 19h
0x1800407c0  mov     r9d, ebx
0x1800407c3  call    WPP_SF_d
0x1800407c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800407cf  test    ebx, ebx
0x1800407d1  js      loc_180040BE4
0x1800407d7  mov     [rbp+3F0h+var_128], 1
0x1800407e1  jmp     short loc_1800407EA
0x1800407e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800407ea  lea     rax, WPP_GLOBAL_Control
0x1800407f1  cmp     rcx, rax
0x1800407f4  jz      short loc_180040811
0x1800407f6  test    [rcx+1Ch], r12b
0x1800407fa  jz      short loc_180040811
0x1800407fc  mov     rcx, [rcx+10h]
0x180040800  lea     r8, WPP_dac461a5a0973d62c81039952891528d_Traceguids
0x180040807  mov     edx, 1Ah
0x18004080c  call    WPP_SF_
0x180040811  xor     edx, edx; dwEncodingType
0x180040813  lea     rax, aFve; "FVE"
0x18004081a  mov     r9d, 88000h; dwFlags
0x180040820  mov     [rsp+4F0h+pvPara], rax; unsigned int
0x180040825  xor     r8d, r8d; hCryptProv
0x180040828  lea     ecx, [rdx+0Dh]; lpszStoreProvider
0x18004082b  call    cs:__imp_CertOpenStore
0x180040832  nop     dword ptr [rax+rax+00h]
0x180040837  mov     [rsp+4F0h+hCertStore], rax
0x18004083c  mov     rbx, rax
0x18004083f  test    rax, rax
0x180040842  jnz     short loc_1800408A4
0x180040844  call    cs:__imp_GetLastError
0x18004084b  nop     dword ptr [rax+rax+00h]
0x180040850  mov     ebx, eax
0x180040852  test    eax, eax
0x180040854  jle     short loc_18004085F
0x180040856  movzx   ebx, ax
0x180040859  or      ebx, 80070000h
0x18004085f  mov     rcx, cs:WPP_GLOBAL_Control
0x180040866  lea     rax, WPP_GLOBAL_Control
0x18004086d  cmp     rcx, rax
0x180040870  jz      loc_180040BDB
0x180040876  test    byte ptr [rcx+1Ch], 40h
0x18004087a  jz      loc_180040BDB
0x180040880  mov     edx, 1Bh
0x180040885  mov     r9d, ebx
0x180040888  mov     rcx, [rcx+10h]
0x18004088c  lea     r8, WPP_dac461a5a0973d62c81039952891528d_Traceguids
0x180040893  call    WPP_SF_d
0x180040898  mov     rcx, cs:WPP_GLOBAL_Control
0x18004089f  jmp     loc_180040BDB
0x1800408a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800408ab  lea     r14, WPP_GLOBAL_Control
0x1800408b2  cmp     rcx, r14
0x1800408b5  jz      short loc_1800408D2
0x1800408b7  test    [rcx+1Ch], r12b
0x1800408bb  jz      short loc_1800408D2
0x1800408bd  mov     rcx, [rcx+10h]
0x1800408c1  lea     r8, WPP_dac461a5a0973d62c81039952891528d_Traceguids
0x1800408c8  mov     edx, 1Ch
0x1800408cd  call    WPP_SF_
0x1800408d2  lea     r9, [rsp+4F0h+var_4C0]; unsigned int *
0x1800408d7  xor     r8d, r8d; unsigned int
0x1800408da  xor     edx, edx; struct _GUID *
0x1800408dc  mov     rcx, r13; this
0x1800408df  call    ?GetAuthMethodGuids@CFveApiBase@@QEAAJPEAU_GUID@@IPEAI@Z; CFveApiBase::GetAuthMethodGuids(_GUID *,uint,uint *)
0x1800408e4  cmp     eax, 1
0x1800408e7  jz      short loc_180040929
0x1800408e9  mov     ebx, 80004005h
0x1800408ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800408f5  cmp     rcx, r14
0x1800408f8  jz      short loc_18004091F
0x1800408fa  test    byte ptr [rcx+1Ch], 40h
0x1800408fe  jz      short loc_18004091F
0x180040900  mov     rcx, [rcx+10h]
0x180040904  lea     r8, WPP_dac461a5a0973d62c81039952891528d_Traceguids
0x18004090b  mov     edx, 1Dh
0x180040910  mov     r9d, ebx
0x180040913  call    WPP_SF_d
0x180040918  mov     rcx, cs:WPP_GLOBAL_Control
0x18004091f  mov     r14d, [rsp+4F0h+var_4C0]
0x180040924  jmp     loc_180040BDB
0x180040929  mov     r14d, [rsp+4F0h+var_4C0]
0x18004092e  test    r14d, r14d
0x180040931  jz      loc_180041155
0x180040937  mov     rcx, cs:WPP_GLOBAL_Control
0x18004093e  lea     rax, WPP_GLOBAL_Control
  ... truncated ...
```
