# CertPropHandleReaderActionInternal

- ea: `0x18000f240`
- end: `0x18000fe0d`
- name: `CertPropHandleReaderActionInternal`
- size: `3021`
- prototype: `void __fastcall(char *pv)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000f230`

## callees

- `0x180004600`
- `0x180006474`
- `0x18000d350`
- `0x18000f240`
- `0x1800103f0`
- `0x180015ba8`
- `0x180016090`
- `0x180016a66`
- `0x180018b58`
- `0x180018bb4`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18000f6c7`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18000f6c7`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000fd51`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000fd51`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000f314`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000f314`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000f329`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000f329`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18000f2f7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18000f2f7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f2c6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f336`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fd95`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fe05`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f2c6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f336`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fd95`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fe05`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f2a3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f3d3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f2a3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f3d3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f2b2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f2b2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000fddf`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000fddf`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000f5cd`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000f5cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000f5b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000f5b4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000f352`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000f352`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f306`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f723`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f7a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f85a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f306`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f723`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f7a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f85a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f5a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fdcc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f5a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fdcc`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000fd9b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000fd9b`
- `CRYPT32!CertFindExtension` at `0x18000f674`
- `CRYPT32!CertFindExtension` at `0x18000f69b`
- `CRYPT32!CertFindExtension` at `0x18000f674`
- `CRYPT32!CertFindExtension` at `0x18000f69b`
- `CRYPT32!CertSetCertificateContextProperty` at `0x18000f6ec`
- `CRYPT32!CertSetCertificateContextProperty` at `0x18000f769`
- `CRYPT32!CertSetCertificateContextProperty` at `0x18000f823`
- `CRYPT32!CertSetCertificateContextProperty` at `0x18000f6ec`
- `CRYPT32!CertSetCertificateContextProperty` at `0x18000f769`
- `CRYPT32!CertSetCertificateContextProperty` at `0x18000f823`
- `CRYPT32!CertCloseStore` at `0x18000fd79`
- `CRYPT32!CertCloseStore` at `0x18000fd84`
- `CRYPT32!CertCloseStore` at `0x18000fd79`
- `CRYPT32!CertCloseStore` at `0x18000fd84`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18000f5e5`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18000f8d8`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18000f5e5`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18000f8d8`
- `CRYPT32!CertOpenSystemStoreW` at `0x18000f8ab`
- `CRYPT32!CertOpenSystemStoreW` at `0x18000f8ab`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18000f88e`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18000f8c8`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18000f88e`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18000f8c8`
- `CRYPT32!CertOpenStore` at `0x18000f394`
- `CRYPT32!CertOpenStore` at `0x18000f394`
- `cryptngc!NgcQueryEffectiveCertPolicy` at `0x18000f3b8`
- `cryptngc!NgcQueryEffectiveCertPolicy` at `0x18000f3b8`

## string_xrefs

- `0x18000f54f`: `Microsoft\SmartCard\Reader\Images`

## pseudocode

```c
void __fastcall CertPropHandleReaderActionInternal(char *pv)
{
  int v2; // esi
  struct _TP_WAIT *ThreadpoolWait; // rax
  void *v4; // rdi
  HCERTSTORE v5; // r12
  struct _RTL_CRITICAL_SECTION *v6; // rbx
  PCCERT_CONTEXT i; // rdi
  HCERTSTORE v8; // r15
  __int64 v9; // rcx
  __int64 v10; // r14
  int *v11; // rbx
  int v12; // eax
  STRSAFE_LPSTR v13; // rcx
  char v14; // bl
  HANDLE CurrentThread; // rax
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // rbx
  char LastError; // al
  __int64 v21; // rcx
  __int64 v22; // rbx
  char v23; // al
  __int64 v24; // rcx
  __int64 v25; // rbx
  char v26; // al
  __int64 *v27; // rcx
  __int64 v28; // rax
  bool v29; // zf
  int v30; // eax
  int v31; // eax
  __int64 *v32; // rcx
  __int64 v33; // rax
  int v34; // eax
  __int64 *v35; // rcx
  __int64 v36; // rax
  int v37; // eax
  __int64 *v38; // rcx
  __int64 v39; // rax
  int v40; // eax
  __int64 *v41; // rcx
  __int64 v42; // rax
  int v43; // eax
  __int64 *v44; // rcx
  __int64 v45; // rax
  int v46; // eax
  __int64 *v47; // rcx
  __int64 v48; // rax
  int v49; // eax
  int v50; // eax
  int v51; // eax
  int v52; // [rsp+30h] [rbp-D0h] BYREF
  int v53; // [rsp+34h] [rbp-CCh] BYREF
  int v54; // [rsp+38h] [rbp-C8h] BYREF
  int v55; // [rsp+3Ch] [rbp-C4h] BYREF
  int v56; // [rsp+40h] [rbp-C0h] BYREF
  int v57; // [rsp+44h] [rbp-BCh] BYREF
  int v58; // [rsp+48h] [rbp-B8h] BYREF
  int v59; // [rsp+4Ch] [rbp-B4h] BYREF
  int v60; // [rsp+50h] [rbp-B0h] BYREF
  int v61; // [rsp+54h] [rbp-ACh] BYREF
  int v62; // [rsp+58h] [rbp-A8h] BYREF
  int *v63; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE hObject; // [rsp+68h] [rbp-98h] BYREF
  __int128 pvData; // [rsp+70h] [rbp-90h] BYREF
  int v66; // [rsp+80h] [rbp-80h] BYREF
  int v67; // [rsp+84h] [rbp-7Ch] BYREF
  int v68; // [rsp+88h] [rbp-78h] BYREF
  int v69; // [rsp+8Ch] [rbp-74h] BYREF
  int v70; // [rsp+90h] [rbp-70h] BYREF
  int *v71; // [rsp+98h] [rbp-68h] BYREF
  const wchar_t *v72; // [rsp+A0h] [rbp-60h] BYREF
  const wchar_t *v73; // [rsp+A8h] [rbp-58h] BYREF
  wchar_t *v74; // [rsp+B0h] [rbp-50h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v76[2]; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v77[5]; // [rsp+D8h] [rbp-28h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+100h] [rbp+0h] BYREF
  __int16 *v79; // [rsp+110h] [rbp+10h]
  int v80; // [rsp+118h] [rbp+18h]
  int v81; // [rsp+11Ch] [rbp+1Ch]
  __int64 *v82; // [rsp+120h] [rbp+20h]
  int v83; // [rsp+128h] [rbp+28h]
  int v84; // [rsp+12Ch] [rbp+2Ch]
  int *v85; // [rsp+130h] [rbp+30h]
  __int64 v86; // [rsp+138h] [rbp+38h]
  __int64 *v87; // [rsp+140h] [rbp+40h]
  int v88; // [rsp+148h] [rbp+48h]
  int v89; // [rsp+14Ch] [rbp+4Ch]
  __int64 *v90; // [rsp+150h] [rbp+50h]
  int v91; // [rsp+158h] [rbp+58h]
  int v92; // [rsp+15Ch] [rbp+5Ch]
  __int64 *v93; // [rsp+160h] [rbp+60h]
  int v94; // [rsp+168h] [rbp+68h]
  int v95; // [rsp+16Ch] [rbp+6Ch]
  __int64 *v96; // [rsp+170h] [rbp+70h]
  int v97; // [rsp+178h] [rbp+78h]
  int v98; // [rsp+17Ch] [rbp+7Ch]
  __int64 *v99; // [rsp+180h] [rbp+80h]
  int v100; // [rsp+188h] [rbp+88h]
  int v101; // [rsp+18Ch] [rbp+8Ch]
  __int64 *v102; // [rsp+190h] [rbp+90h]
  int v103; // [rsp+198h] [rbp+98h]
  int v104; // [rsp+19Ch] [rbp+9Ch]
  int *v105; // [rsp+1A0h] [rbp+A0h]
  __int64 v106; // [rsp+1A8h] [rbp+A8h]
  int *v107; // [rsp+1B0h] [rbp+B0h]
  __int64 v108; // [rsp+1B8h] [rbp+B8h]
  int *v109; // [rsp+1C0h] [rbp+C0h]
  __int64 v110; // [rsp+1C8h] [rbp+C8h]
  int *v111; // [rsp+1D0h] [rbp+D0h]
  __int64 v112; // [rsp+1D8h] [rbp+D8h]
  int *v113; // [rsp+1E0h] [rbp+E0h]
  __int64 v114; // [rsp+1E8h] [rbp+E8h]
  int *v115; // [rsp+1F0h] [rbp+F0h]
  __int64 v116; // [rsp+1F8h] [rbp+F8h]
  int *v117; // [rsp+200h] [rbp+100h]
  __int64 v118; // [rsp+208h] [rbp+108h]
  int *v119; // [rsp+210h] [rbp+110h]
  __int64 v120; // [rsp+218h] [rbp+118h]
  int *v121; // [rsp+220h] [rbp+120h]
  __int64 v122; // [rsp+228h] [rbp+128h]
  int *v123; // [rsp+230h] [rbp+130h]
  __int64 v124; // [rsp+238h] [rbp+138h]
  int *v125; // [rsp+240h] [rbp+140h]
  __int64 v126; // [rsp+248h] [rbp+148h]
  wchar_t Source[264]; // [rsp+250h] [rbp+150h] BYREF

  memset_0(Source, 0, 0x208u);
  hObject = (HANDLE)-1LL;
  v2 = 0;
  v53 = 32;
  v52 = 0;
  pvData = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)pv + 13);
  if ( WaitForSingleObject(*((HANDLE *)pv + 64), 0) == 258 )
  {
    ThreadpoolWait = (struct _TP_WAIT *)*((_QWORD *)pv + 2);
    v4 = (void *)*((_QWORD *)pv + 14);
    if ( ThreadpoolWait
      || (ThreadpoolWait = CreateThreadpoolWait(CertPropHandleReaderAction, pv, (PTP_CALLBACK_ENVIRON)(pv + 424)),
          (*((_QWORD *)pv + 2) = ThreadpoolWait) != 0) )
    {
      SetThreadpoolWait(ThreadpoolWait, v4, 0);
    }
    else if ( GetLastError() )
    {
      CloseThreadpoolWait(*((PTP_WAIT *)pv + 2));
      *((_QWORD *)pv + 2) = 0;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)pv + 13);
    if ( *((_DWORD *)pv + 141) && SetThreadToken(0, *((HANDLE *)pv + 52)) )
    {
      v5 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x10200u, L"MY");
      if ( v5 )
      {
        v62 = 0;
        v66 = 0;
        if ( (int)NgcQueryEffectiveCertPolicy(0, &v62, &v66) >= 0 )
        {
          v6 = (struct _RTL_CRITICAL_SECTION *)(pv + 72);
          i = 0;
          v8 = 0;
          EnterCriticalSection((LPCRITICAL_SECTION)(pv + 72));
          v10 = *((_QWORD *)pv + 17);
          if ( v10 )
          {
            while ( 1 )
            {
              if ( *(_QWORD *)(v10 + 168) && *(_DWORD *)(v10 + 152) != 1 )
              {
                v11 = *(int **)v10;
                WppTraceIndent(v9, 0);
                if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
                  && (WPP_GLOBAL_Control[28] & 2) != 0
                  && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
                {
                  WPP_SF_s(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    27,
                    &WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids,
                    WPP_pszIndent);
                }
                v63 = v11;
                v71 = &v53;
                v76[0] = &v63;
                v76[1] = &v71;
                v12 = errcntrctlib::WinApiErrorContract__lambda_cb03e54cbae31181fc2c1af7c2d5651c___(v76);
                v14 = v12;
                if ( v12 )
                {
                  WppTraceIndent(v13, 2);
                  v13 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
                    && (WPP_GLOBAL_Control[28] & 1) != 0
                    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
                  {
                    WPP_SF_sD(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      28,
                      (unsigned int)&WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids,
                      WPP_pszIndent,
                      v14);
                  }
                }
                WppTraceIndent(v13, 1);
                if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
                  && (WPP_GLOBAL_Control[28] & 2) != 0
                  && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
                {
                  WPP_SF_s(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    29,
                    &WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids,
                    WPP_pszIndent);
                }
                if ( v53 != 128 && v53 != 1024 )
                  v2 = 1;
                memset_0(Source, 0, 0x208u);
                LODWORD(v63) = 260;
                v74 = Source;
                v73 = L"Microsoft\\SmartCard\\Reader\\Images";
                v72 = L"%ALLUSERSPROFILE%\\";
                v71 = *(int **)v10;
                v77[0] = &v71;
                v77[1] = &v72;
                v77[2] = &v73;
                v77[3] = &v74;
                v77[4] = &v63;
                errcntrctlib::WinApiErrorContract__lambda_14ac1414830e426ed64d6213c117b8ac___(v77);
                if ( hObject != (HANDLE)-1LL )
                {
                  CloseHandle(hObject);
                  hObject = (HANDLE)-1LL;
                }
                CurrentThread = GetCurrentThread();
                if ( !OpenThreadToken(CurrentThread, 0xCu, 1, &hObject) )
                {
                  LeaveCriticalSection((LPCRITICAL_SECTION)(pv + 72));
                  goto LABEL_119;
                }
                for ( i = CertEnumCertificatesInStore(*(HCERTSTORE *)(v10 + 168), i);
                      i;
                      i = CertEnumCertificatesInStore(*(HCERTSTORE *)(v10 + 168), i) )
                {
                  if ( v62 || !(unsigned int)CertPropNgcCertExistsInStore(v5, i) )
                  {
                    if ( CertFindExtension(
                           "1.3.6.1.4.1.311.10.11.26",
                           i->pCertInfo->cExtension,
                           i->pCertInfo->rgExtension)
                      || CertFindExtension(
                           "1.3.6.1.4.1.311.10.11.87",
                           i->pCertInfo->cExtension,
                           i->pCertInfo->rgExtension) )
                    {
                      if ( v8 || (v8 = CertOpenSystemStoreW(0, L"REQUEST")) != 0 )
                        CertAddCertificateContextToStore(v8, i, 5u, 0);
                    }
                    else
                    {
                      *(_QWORD *)&pvData = 0;
                      *((_QWORD *)&pvData + 1) = Source;
                      v17 = wcsnlen(Source, 0x104u);
                      LODWORD(pvData) = 2 * v17 + 2;
                      if ( 2 * v17 != -2 && !CertSetCertificateContextProperty(i, 0x65u, 0, &pvData) )
                      {
                        WppTraceIndent(v18, 2);
                        if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
                          && (WPP_GLOBAL_Control[28] & 1) != 0
                          && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
                        {
                          v19 = *((_QWORD *)WPP_GLOBAL_Control + 2);
                          LastError = GetLastError();
                          WPP_SF_sD(
                            v19,
                            35,
                            (unsigned int)&WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids,
                            WPP_pszIndent,
                            LastError);
                        }
                      }
                      if ( !v2 )
                      {
                        *((_QWORD *)&pvData + 1) = 0;
                        LODWORD(pvData) = 0;
                        if ( !CertSetCertificateContextProperty(i, 0x6Au, 0, &pvData) )
                        {
                          WppTraceIndent(v21, 2);
                          if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
                            && (WPP_GLOBAL_Control[28] & 1) != 0
                            && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
                          {
                            v22 = *((_QWORD *)WPP_GLOBAL_Control + 2);
                            v23 = GetLastError();
                            WPP_SF_sD(
                              v22,
                              36,
                              (unsigned int)&WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids,
                              WPP_pszIndent,
                              v23);
                          }
                        }
                      }
                      switch ( v53 )
                      {
                        case 32:
                          v52 = 2;
                          break;
                        case 128:
                          v52 = 1;
                          break;
                        case 1024:
                          v52 = 5;
                          break;
                        default:
                          v52 = 0;
                          break;
                      }
                      *(_QWORD *)&pvData = 4;
                      *((_QWORD *)&pvData + 1) = &v52;
                      if ( !CertSetCertificateContextProperty(i, 0x78u, 0, &pvData) )
                      {
                        WppTraceIndent(v24, 2);
                        if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
                          && (WPP_GLOBAL_Control[28] & 1) != 0
                          && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
                        {
                          v25 = *((_QWORD *)WPP_GLOBAL_Control + 2);
                          v26 = GetLastError();
                          WPP_SF_sD(
                            v25,
                            37,
                            (unsigned int)&WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids,
                            WPP_pszIndent,
                            v26);
                        }
                      }
                      CertAddCertificateContextToStore(v5, i, 5u, 0);
                    }
                  }
                  else
                  {
                    WppTraceIndent(v16, 2);
                    if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
                      && (WPP_GLOBAL_Control[28] & 1) != 0
                      && (unsigned __int8)WPP_GLOBAL_Control[25] >= 4u )
                    {
                      WPP_SF_s(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        34,
                        &WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids,
                        WPP_pszIndent);
                    }
                  }
                }
                *(_DWORD *)(v10 + 152) = 1;
                if ( (unsigned int)dword_180031008 <= 5 )
                {
                  v2 = 0;
                }
                else
                {
                  v27 = *(__int64 **)v10;
                  if ( *(_QWORD *)v10 )
                  {
                    v28 = -1;
                    do
                      v29 = *((_WORD *)v27 + ++v28) == 0;
                    while ( !v29 );
                    v30 = 2 * v28 + 2;
                  }
                  else
                  {
                    v27 = &qword_180027F58;
                    v30 = 2;
                  }
                  v83 = v30;
                  v2 = 0;
                  v31 = *(_DWORD *)(v10 + 8);
                  v82 = v27;
                  v32 = *(__int64 **)(v10 + 16);
                  v67 = v31;
                  v85 = &v67;
                  v84 = 0;
                  v86 = 4;
                  if ( v32 )
                  {
                    v33 = -1;
                    do
                      v29 = *((_WORD *)v32 + ++v33) == 0;
                    while ( !v29 );
                    v34 = 2 * v33 + 2;
                  }
                  else
                  {
                    v32 = &qword_180027F58;
                    v34 = 2;
                  }
                  v87 = v32;
                  v35 = *(__int64 **)(v10 + 80);
                  v88 = v34;
                  v89 = 0;
                  if ( v35 )
                  {
                    v36 = -1;
                    do
                      v29 = *((_WORD *)v35 + ++v36) == 0;
                    while ( !v29 );
                    v37 = 2 * v36 + 2;
                  }
                  else
                  {
                    v35 = &qword_180027F58;
                    v37 = 2;
                  }
                  v90 = v35;
                  v38 = *(__int64 **)(v10 + 88);
                  v91 = v37;
                  v92 = 0;
                  if ( v38 )
                  {
                    v39 = -1;
                    do
                      v29 = *((_WORD *)v38 + ++v39) == 0;
                    while ( !v29 );
                    v40 = 2 * v39 + 2;
                  }
                  else
                  {
                    v38 = &qword_180027F58;
                    v40 = 2;
                  }
                  v93 = v38;
                  v41 = *(__int64 **)(v10 + 96);
                  v94 = v40;
                  v95 = 0;
                  if ( v41 )
                  {
                    v42 = -1;
                    do
                      v29 = *((_WORD *)v41 + ++v42) == 0;
                    while ( !v29 );
                    v43 = 2 * v42 + 2;
                  }
                  else
                  {
                    v41 = &qword_180027F58;
                    v43 = 2;
                  }
                  v96 = v41;
                  v44 = *(__int64 **)(v10 + 104);
                  v97 = v43;
                  v98 = 0;
                  if ( v44 )
                  {
                    v45 = -1;
                    do
                      v29 = *((_WORD *)v44 + ++v45) == 0;
                    while ( !v29 );
                    v46 = 2 * v45 + 2;
                  }
                  else
                  {
                    v44 = &qword_180027F58;
                    v46 = 2;
                  }
                  v99 = v44;
                  v47 = *(__int64 **)(v10 + 112);
                  v100 = v46;
                  v101 = 0;
                  if ( v47 )
                  {
                    v48 = -1;
                    do
                      v29 = *((_WORD *)v47 + ++v48) == 0;
                    while ( !v29 );
                    v49 = 2 * v48 + 2;
                  }
                  else
                  {
                    v47 = &qword_180027F58;
                    v49 = 2;
                  }
                  v103 = v49;
                  v68 = *(_DWORD *)(v10 + 120);
                  v105 = &v68;
                  v50 = *(_DWORD *)(v10 + 160);
                  v102 = v47;
                  v69 = v50;
                  v107 = &v69;
                  v104 = 0;
                  v106 = 4;
                  v108 = 4;
                  v110 = 4;
                  v112 = 4;
                  v114 = 4;
                  v116 = 4;
                  v118 = 4;
                  v120 = 4;
                  v122 = 4;
                  if ( pv == (char *)-24LL )
                  {
                    v54 = 0;
                    v109 = &v54;
                    v111 = &v55;
                    v113 = &v56;
                    v115 = &v57;
                    v117 = &v58;
                    v119 = &v59;
                    v121 = &v60;
                    v123 = &v61;
                    v51 = 0;
                    v55 = 0;
                    v56 = 0;
                    v57 = 0;
                    v58 = 0;
                    v59 = 0;
                    v60 = 0;
                    v61 = 0;
                  }
                  else
                  {
                    v54 = *((_DWORD *)pv + 70);
                    v109 = &v54;
                    v55 = *((_DWORD *)pv + 6);
                    v111 = &v55;
                    v56 = *((_DWORD *)pv + 7);
                    v113 = &v56;
                    v57 = *((_DWORD *)pv + 8);
                    v115 = &v57;
                    v58 = *((_DWORD *)pv + 9);
                    v117 = &v58;
                    v59 = *((_DWORD *)pv + 10);
                    v119 = &v59;
                    v60 = *((_DWORD *)pv + 11);
                    v121 = &v60;
                    v61 = *((_DWORD *)pv + 16);
                    v123 = &v61;
                    v51 = *((_DWORD *)pv + 12);
                  }
                  v70 = v51;
                  v124 = 4;
                  v125 = &v70;
                  *(_DWORD *)&EventDescriptor.Level = 5;
                  UserData.Ptr = (ULONGLONG)off_180031010;
                  v126 = 4;
                  *(_DWORD *)&EventDescriptor.Id = 184549376;
                  EventDescriptor.Keyword = 0;
                  UserData.Size = *(unsigned __int16 *)off_180031010;
                  v79 = word_18002969A;
                  UserData.Reserved = 2;
                  v80 = 625;
                  v81 = 1;
                  LODWORD(v63) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
                  EventWriteTransfer(RegHandle, &EventDescriptor, 0, (LPCGUID)(v10 + 184), 0x15u, &UserData);
                }
              }
              v10 = *(_QWORD *)(v10 + 240);
              if ( !v10 )
              {
                v6 = (struct _RTL_CRITICAL_SECTION *)(pv + 72);
                break;
              }
            }
          }
          if ( v8 )
            CertCloseStore(v8, 0);
          CertCloseStore(v5, 0);
          CertPropUpdateRootCertificates((__int64)pv);
          LeaveCriticalSection(v6);
        }
      }
      RevertToSelf();
    }
LABEL_119:
    if ( hObject != (HANDLE)-1LL )
    {
      CloseHandle(hObject);
      hObject = (HANDLE)-1LL;
    }
    SetEvent(*((HANDLE *)pv + 15));
  }
  else
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)pv + 13);
  }
}

```

## disassembly

```asm
0x18000f240  push    rbp
0x18000f242  push    rbx
0x18000f243  push    rsi
0x18000f244  push    r13
0x18000f246  lea     rbp, [rsp-378h]
0x18000f24e  sub     rsp, 478h
0x18000f255  mov     rax, cs:__security_cookie
0x18000f25c  xor     rax, rsp
0x18000f25f  mov     [rbp+390h+var_30], rax
0x18000f266  mov     r13, rcx
0x18000f269  xor     edx, edx; Val
0x18000f26b  lea     rcx, [rbp+390h+Source]; void *
0x18000f272  mov     r8d, 208h; Size
0x18000f278  call    memset_0
0x18000f27d  xorps   xmm0, xmm0
0x18000f280  mov     [rsp+490h+hObject], 0FFFFFFFFFFFFFFFFh
0x18000f289  xor     esi, esi
0x18000f28b  mov     [rsp+490h+var_45C], 20h ; ' '
0x18000f293  lea     rcx, [r13+208h]; lpCriticalSection
0x18000f29a  mov     [rsp+490h+var_460], esi
0x18000f29e  movups  [rsp+490h+pvData], xmm0
0x18000f2a3  call    cs:__imp_EnterCriticalSection
0x18000f2a9  mov     rcx, [r13+200h]; hHandle
0x18000f2b0  xor     edx, edx; dwMilliseconds
0x18000f2b2  call    cs:__imp_WaitForSingleObject
0x18000f2b8  cmp     eax, 102h
0x18000f2bd  jz      short loc_18000F2D1
0x18000f2bf  lea     rcx, [r13+208h]; lpCriticalSection
0x18000f2c6  call    cs:__imp_LeaveCriticalSection
0x18000f2cc  jmp     loc_18000FDE5
0x18000f2d1  mov     rax, [r13+10h]
0x18000f2d5  mov     [rsp+490h+arg_8], rdi
0x18000f2dd  mov     rdi, [r13+70h]
0x18000f2e1  test    rax, rax
0x18000f2e4  jnz     short loc_18000F320
0x18000f2e6  lea     r8, [r13+1A8h]; pcbe
0x18000f2ed  mov     rdx, r13; pv
0x18000f2f0  lea     rcx, CertPropHandleReaderAction; pfnwa
0x18000f2f7  call    cs:__imp_CreateThreadpoolWait
0x18000f2fd  mov     [r13+10h], rax
0x18000f301  test    rax, rax
0x18000f304  jnz     short loc_18000F320
0x18000f306  call    cs:__imp_GetLastError
0x18000f30c  test    eax, eax
0x18000f30e  jz      short loc_18000F32F
0x18000f310  mov     rcx, [r13+10h]; pwa
0x18000f314  call    cs:__imp_CloseThreadpoolWait
0x18000f31a  mov     [r13+10h], rsi
0x18000f31e  jmp     short loc_18000F32F
0x18000f320  xor     r8d, r8d; pftTimeout
0x18000f323  mov     rdx, rdi; h
0x18000f326  mov     rcx, rax; pwa
0x18000f329  call    cs:__imp_SetThreadpoolWait
0x18000f32f  lea     rcx, [r13+208h]; lpCriticalSection
0x18000f336  call    cs:__imp_LeaveCriticalSection
0x18000f33c  cmp     [r13+234h], esi
0x18000f343  jz      loc_18000FDB9
0x18000f349  mov     rdx, [r13+1A0h]; Token
0x18000f350  xor     ecx, ecx; Thread
0x18000f352  call    cs:__imp_SetThreadToken
0x18000f358  test    eax, eax
0x18000f35a  jz      loc_18000FDB9
0x18000f360  mov     [rsp+490h+arg_10], r12
0x18000f368  lea     rax, aMy; "MY"
0x18000f36f  mov     [rsp+490h+arg_18], r14
0x18000f377  mov     r9d, 10200h; dwFlags
0x18000f37d  xor     r8d, r8d; hCryptProv
0x18000f380  mov     [rsp+490h+var_20], r15
0x18000f388  xor     edx, edx; dwEncodingType
0x18000f38a  mov     [rsp+490h+pvPara], rax; pvPara
0x18000f38f  mov     ecx, 0Ah; lpszStoreProvider
0x18000f394  call    cs:__imp_CertOpenStore
0x18000f39a  mov     r12, rax
0x18000f39d  test    rax, rax
0x18000f3a0  jz      loc_18000FD9B
0x18000f3a6  lea     r8, [rbp+390h+var_410]
0x18000f3aa  mov     [rsp+490h+var_438], esi
0x18000f3ae  lea     rdx, [rsp+490h+var_438]
0x18000f3b3  mov     [rbp+390h+var_410], esi
0x18000f3b6  xor     ecx, ecx
0x18000f3b8  call    cs:__imp_NgcQueryEffectiveCertPolicy
0x18000f3be  test    eax, eax
0x18000f3c0  js      loc_18000FD9B
0x18000f3c6  lea     rbx, [r13+48h]
0x18000f3ca  mov     rdi, rsi
0x18000f3cd  mov     rcx, rbx; lpCriticalSection
0x18000f3d0  mov     r15, rsi
0x18000f3d3  call    cs:__imp_EnterCriticalSection
0x18000f3d9  mov     r14, [r13+88h]
0x18000f3e0  test    r14, r14
0x18000f3e3  jz      loc_18000FD6F
0x18000f3e9  nop     dword ptr [rax+00000000h]
0x18000f3f0  cmp     qword ptr [r14+0A8h], 0
0x18000f3f8  jz      loc_18000FD5B
0x18000f3fe  cmp     dword ptr [r14+98h], 1
0x18000f406  jz      loc_18000FD5B
0x18000f40c  mov     rbx, [r14]
0x18000f40f  xor     edx, edx
0x18000f411  call    WppTraceIndent
0x18000f416  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f41d  lea     rax, WPP_GLOBAL_Control
0x18000f424  cmp     rcx, rax
0x18000f427  jz      short loc_18000F451
0x18000f429  test    byte ptr [rcx+1Ch], 2
0x18000f42d  jz      short loc_18000F451
0x18000f42f  cmp     byte ptr [rcx+19h], 5
0x18000f433  jb      short loc_18000F451
0x18000f435  mov     r9, cs:WPP_pszIndent
0x18000f43c  lea     r8, WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids
0x18000f443  mov     rcx, [rcx+10h]
0x18000f447  mov     edx, 1Bh
0x18000f44c  call    WPP_SF_s
0x18000f451  lea     rax, [rsp+490h+var_45C]
0x18000f456  mov     [rsp+490h+var_430], rbx
0x18000f45b  mov     [rbp+390h+var_3F8], rax
0x18000f45f  lea     rcx, [rbp+390h+var_3C8]
0x18000f463  lea     rax, [rsp+490h+var_430]
0x18000f468  mov     [rbp+390h+var_3C8], rax
0x18000f46c  lea     rax, [rbp+390h+var_3F8]
0x18000f470  mov     [rbp+390h+var_3C0], rax
0x18000f474  call    errcntrctlib__WinApiErrorContract__lambda_cb03e54cbae31181fc2c1af7c2d5651c___
0x18000f479  mov     ebx, eax
0x18000f47b  test    eax, eax
0x18000f47d  jz      short loc_18000F4C8
0x18000f47f  mov     edx, 2
0x18000f484  call    WppTraceIndent
0x18000f489  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f490  lea     rax, WPP_GLOBAL_Control
0x18000f497  cmp     rcx, rax
0x18000f49a  jz      short loc_18000F4C8
0x18000f49c  test    byte ptr [rcx+1Ch], 1
0x18000f4a0  jz      short loc_18000F4C8
0x18000f4a2  cmp     byte ptr [rcx+19h], 2
0x18000f4a6  jb      short loc_18000F4C8
0x18000f4a8  mov     r9, cs:WPP_pszIndent
0x18000f4af  lea     r8, WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids
0x18000f4b6  mov     rcx, [rcx+10h]
0x18000f4ba  mov     edx, 1Ch
0x18000f4bf  mov     dword ptr [rsp+490h+pvPara], ebx
0x18000f4c3  call    WPP_SF_sD
0x18000f4c8  mov     edx, 1
0x18000f4cd  call    WppTraceIndent
0x18000f4d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f4d9  lea     rbx, WPP_GLOBAL_Control
0x18000f4e0  cmp     rcx, rbx
0x18000f4e3  jz      short loc_18000F50D
0x18000f4e5  test    byte ptr [rcx+1Ch], 2
0x18000f4e9  jz      short loc_18000F50D
0x18000f4eb  cmp     byte ptr [rcx+19h], 5
0x18000f4ef  jb      short loc_18000F50D
0x18000f4f1  mov     r9, cs:WPP_pszIndent
0x18000f4f8  lea     r8, WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids
0x18000f4ff  mov     rcx, [rcx+10h]
0x18000f503  mov     edx, 1Dh
0x18000f508  call    WPP_SF_s
0x18000f50d  mov     eax, [rsp+490h+var_45C]
0x18000f511  cmp     eax, 80h
0x18000f516  jz      short loc_18000F524
0x18000f518  cmp     eax, 400h
0x18000f51d  jz      short loc_18000F524
0x18000f51f  mov     esi, 1
0x18000f524  xor     edx, edx; Val
0x18000f526  lea     rcx, [rbp+390h+Source]; void *
0x18000f52d  mov     r8d, 208h; Size
0x18000f533  call    memset_0
0x18000f538  lea     rax, [rbp+390h+Source]
0x18000f53f  mov     dword ptr [rsp+490h+var_430], 104h
0x18000f547  mov     [rbp+390h+var_3E0], rax
0x18000f54b  lea     rcx, [rbp+390h+var_3B8]
0x18000f54f  lea     rax, aMicrosoftSmart; "Microsoft\\SmartCard\\Reader\\Images"
0x18000f556  mov     [rbp+390h+var_3E8], rax
0x18000f55a  lea     rax, aAllusersprofil; "%ALLUSERSPROFILE%\\"
0x18000f561  mov     [rbp+390h+var_3F0], rax
0x18000f565  mov     rax, [r14]
0x18000f568  mov     [rbp+390h+var_3F8], rax
0x18000f56c  lea     rax, [rbp+390h+var_3F8]
0x18000f570  mov     [rbp+390h+var_3B8], rax
0x18000f574  lea     rax, [rbp+390h+var_3F0]
0x18000f578  mov     [rbp+390h+var_3B0], rax
0x18000f57c  lea     rax, [rbp+390h+var_3E8]
0x18000f580  mov     [rbp+390h+var_3A8], rax
0x18000f584  lea     rax, [rbp+390h+var_3E0]
0x18000f588  mov     [rbp+390h+var_3A0], rax
0x18000f58c  lea     rax, [rsp+490h+var_430]
0x18000f591  mov     [rbp+390h+var_398], rax
0x18000f595  call    errcntrctlib__WinApiErrorContract__lambda_14ac1414830e426ed64d6213c117b8ac___
0x18000f59a  mov     rcx, [rsp+490h+hObject]; hObject
0x18000f59f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000f5a3  jz      short loc_18000F5B4
0x18000f5a5  call    cs:__imp_CloseHandle
0x18000f5ab  mov     [rsp+490h+hObject], 0FFFFFFFFFFFFFFFFh
0x18000f5b4  call    cs:__imp_GetCurrentThread
0x18000f5ba  lea     r9, [rsp+490h+hObject]; TokenHandle
0x18000f5bf  mov     edx, 0Ch; DesiredAccess
0x18000f5c4  mov     rcx, rax; ThreadHandle
0x18000f5c7  mov     r8d, 1; OpenAsSelf
0x18000f5cd  call    cs:__imp_OpenThreadToken
0x18000f5d3  test    eax, eax
0x18000f5d5  jz      loc_18000FE01
0x18000f5db  mov     rcx, [r14+0A8h]; hCertStore
0x18000f5e2  mov     rdx, rdi; pPrevCertContext
0x18000f5e5  call    cs:__imp_CertEnumCertificatesInStore
0x18000f5eb  mov     rdi, rax
0x18000f5ee  test    rax, rax
0x18000f5f1  jz      loc_18000F8EA
0x18000f5f7  cmp     [rsp+490h+var_438], 0
0x18000f5fc  jnz     short loc_18000F65C
0x18000f5fe  mov     rdx, rdi
0x18000f601  mov     rcx, r12
0x18000f604  call    CertPropNgcCertExistsInStore
0x18000f609  test    eax, eax
0x18000f60b  jz      short loc_18000F65C
0x18000f60d  mov     edx, 2
0x18000f612  call    WppTraceIndent
0x18000f617  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f61e  cmp     rcx, rbx
0x18000f621  jz      loc_18000F8CE
0x18000f627  test    byte ptr [rcx+1Ch], 1
0x18000f62b  jz      loc_18000F8CE
0x18000f631  cmp     byte ptr [rcx+19h], 4
0x18000f635  jb      loc_18000F8CE
0x18000f63b  mov     r9, cs:WPP_pszIndent
0x18000f642  lea     r8, WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids
0x18000f649  mov     rcx, [rcx+10h]
0x18000f64d  mov     edx, 22h ; '"'
0x18000f652  call    WPP_SF_s
0x18000f657  jmp     loc_18000F8CE
0x18000f65c  mov     rdx, [rdi+18h]
0x18000f660  lea     rcx, a13614131110112; "1.3.6.1.4.1.311.10.11.26"
0x18000f667  mov     r8, [rdx+0C8h]; rgExtensions
0x18000f66e  mov     edx, [rdx+0C0h]; cExtensions
0x18000f674  call    cs:__imp_CertFindExtension
0x18000f67a  test    rax, rax
0x18000f67d  jnz     loc_18000F89D
0x18000f683  mov     rdx, [rdi+18h]
0x18000f687  lea     rcx, a13614131110118; "1.3.6.1.4.1.311.10.11.87"
0x18000f68e  mov     r8, [rdx+0C8h]; rgExtensions
0x18000f695  mov     edx, [rdx+0C0h]; cExtensions
0x18000f69b  call    cs:__imp_CertFindExtension
0x18000f6a1  test    rax, rax
0x18000f6a4  jnz     loc_18000F89D
0x18000f6aa  mov     qword ptr [rsp+490h+pvData], rax
0x18000f6af  lea     rcx, [rbp+390h+Source]; Source
0x18000f6b6  lea     rax, [rbp+390h+Source]
0x18000f6bd  mov     edx, 104h; MaxCount
0x18000f6c2  mov     qword ptr [rsp+490h+pvData+8], rax
0x18000f6c7  call    cs:__imp_wcsnlen
0x18000f6cd  lea     eax, ds:2[rax*2]
0x18000f6d4  mov     dword ptr [rsp+490h+pvData], eax
0x18000f6d8  test    eax, eax
0x18000f6da  jz      short loc_18000F748
0x18000f6dc  lea     r9, [rsp+490h+pvData]; pvData
0x18000f6e1  xor     r8d, r8d; dwFlags
0x18000f6e4  mov     edx, 65h ; 'e'; dwPropId
0x18000f6e9  mov     rcx, rdi; pCertContext
0x18000f6ec  call    cs:__imp_CertSetCertificateContextProperty
0x18000f6f2  test    eax, eax
0x18000f6f4  jnz     short loc_18000F748
0x18000f6f6  mov     edx, 2
0x18000f6fb  call    WppTraceIndent
0x18000f700  mov     rbx, cs:WPP_GLOBAL_Control
0x18000f707  lea     rax, WPP_GLOBAL_Control
0x18000f70e  cmp     rbx, rax
0x18000f711  jz      short loc_18000F748
0x18000f713  test    byte ptr [rbx+1Ch], 1
0x18000f717  jz      short loc_18000F748
0x18000f719  cmp     byte ptr [rbx+19h], 2
0x18000f71d  jb      short loc_18000F748
0x18000f71f  mov     rbx, [rbx+10h]
0x18000f723  call    cs:__imp_GetLastError
0x18000f729  mov     r9, cs:WPP_pszIndent
0x18000f730  lea     r8, WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids
0x18000f737  mov     edx, 23h ; '#'
0x18000f73c  mov     dword ptr [rsp+490h+pvPara], eax
0x18000f740  mov     rcx, rbx
0x18000f743  call    WPP_SF_sD
0x18000f748  test    esi, esi
0x18000f74a  jnz     short loc_18000F7C5
0x18000f74c  lea     r9, [rsp+490h+pvData]; pvData
0x18000f751  mov     qword ptr [rsp+490h+pvData+8], 0
0x18000f75a  xor     r8d, r8d; dwFlags
0x18000f75d  mov     dword ptr [rsp+490h+pvData], esi
0x18000f761  mov     edx, 6Ah ; 'j'; dwPropId
0x18000f766  mov     rcx, rdi; pCertContext
0x18000f769  call    cs:__imp_CertSetCertificateContextProperty
0x18000f76f  test    eax, eax
0x18000f771  jnz     short loc_18000F7C5
0x18000f773  mov     edx, 2
0x18000f778  call    WppTraceIndent
0x18000f77d  mov     rbx, cs:WPP_GLOBAL_Control
0x18000f784  lea     rax, WPP_GLOBAL_Control
0x18000f78b  cmp     rbx, rax
0x18000f78e  jz      short loc_18000F7C5
0x18000f790  test    byte ptr [rbx+1Ch], 1
0x18000f794  jz      short loc_18000F7C5
0x18000f796  cmp     byte ptr [rbx+19h], 2
0x18000f79a  jb      short loc_18000F7C5
0x18000f79c  mov     rbx, [rbx+10h]
0x18000f7a0  call    cs:__imp_GetLastError
0x18000f7a6  mov     r9, cs:WPP_pszIndent
  ... truncated ...
```
