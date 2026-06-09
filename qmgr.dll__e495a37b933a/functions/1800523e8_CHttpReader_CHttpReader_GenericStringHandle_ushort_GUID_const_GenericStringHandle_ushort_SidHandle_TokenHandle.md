# CHttpReader::CHttpReader(GenericStringHandle<ushort>,_GUID const &,GenericStringHandle<ushort>,SidHandle,TokenHandle const &,TokenHandle const &,ulong,bool *,_GUID const &,PROXY_SETTINGS const *,CCredentialsContainer const *,bool,ulong,GenericStringHandle<ushort>,CNetworkMonitor *,CClientCertificate *,CCustomHeaders const *,ulong,_TP_CALLBACK_ENVIRON_V3 *,IHttpInterface *,bool,IServerCertificateValidator *)

- ea: `0x1800523e8`
- end: `0x180052eed`
- name: `??0CHttpReader@@QEAA@V?$GenericStringHandle@G@@AEBU_GUID@@0VSidHandle@@AEBVTokenHandle@@3KPEA_N1PEBUPROXY_SETTINGS@@PEBVCCredentialsContainer@@_NK0PEAVCNetworkMonitor@@PEAVCClientCertificate@@PEBVCCustomHeaders@@KPEAU_TP_CALLBACK_ENVIRON_V3@@PEAVIHttpInterface@@7PEAUIServerCertificateValidator@@@Z`
- size: `2821`
- prototype: `char *__fastcall(char *pv, void **, __int64, void **, void *, struct TokenHandle *, HANDLE **, int, __int64, __int64, enum BG_JOB_PROXY_USAGE *, CCredentialsContainer *, char, int, void **, int, __int64, __int64, unsigned int, int, int, char, __int64)`
- caller_count: `2`
- callee_count: `24`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001fab8`
- `0x1800dd394`

## callees

- `0x1800065ac`
- `0x180008b70`
- `0x18000f5f0`
- `0x180016d60`
- `0x1800523e8`
- `0x180052ef4`
- `0x180052f90`
- `0x180053924`
- `0x180057cac`
- `0x180065da0`
- `0x18007aaf0`
- `0x18008de70`
- `0x18008df60`
- `0x18009a9d0`
- `0x18009d024`
- `0x18009d2e8`
- `0x18009e9c8`
- `0x1800a0738`
- `0x1800a3420`
- `0x1800a3444`
- `0x1800ab7fc`
- `0x1800c0a68`
- `0x1800c0fac`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800524b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800524be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800524c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005271a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052724`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005272e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800527d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800527e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800527ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052a12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052a1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052a26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052a8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052a99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052aa3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052df1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052dfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052e05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800524b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800524be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800524c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005271a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052724`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005272e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800527d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800527e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800527ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052a12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052a1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052a26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052a8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052a99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052aa3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052df1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052dfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052e05`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800524a5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180052a00`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180052a7d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800524a5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180052a00`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180052a7d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180052ddf`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180052ddf`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180052ba9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180052ba9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180052710`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800527cf`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180052710`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800527cf`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char *__fastcall CHttpReader::CHttpReader(
        char *pv,
        void **a2,
        __int64 a3,
        void **a4,
        void *a5,
        struct TokenHandle *a6,
        HANDLE **a7,
        int a8,
        __int64 a9,
        __int64 a10,
        enum BG_JOB_PROXY_USAGE *a11,
        CCredentialsContainer *a12,
        char a13,
        int a14,
        void **a15,
        int a16,
        __int64 a17,
        __int64 a18,
        unsigned int a19,
        int a20,
        int a21,
        char a22,
        __int64 a23)
{
  HANDLE EventW; // rax
  unsigned int LastError; // ecx
  unsigned int v28; // esi
  bool v29; // dl
  __int128 v30; // xmm0
  __int64 v31; // rdx
  struct TokenHandle *v32; // rbx
  unsigned int v33; // ecx
  unsigned int v34; // ecx
  struct _LUID v35; // rax
  CEncryptedCredentials **v36; // rax
  CEncryptedCredentials *v37; // rbx
  unsigned int updated; // eax
  __int64 v39; // rax
  EVENT_LOG *v40; // rcx
  __int64 v41; // rdx
  HANDLE v42; // rax
  unsigned int v43; // ecx
  HANDLE v44; // rax
  unsigned int v45; // ecx
  SidHandle *v46; // r13
  volatile signed __int32 *v47; // rax
  HANDLE *v48; // rax
  HANDLE *v49; // rax
  int v50; // r8d
  int v51; // edx
  struct _TP_CALLBACK_ENVIRON_V3 *v52; // r8
  PTP_WORK ThreadpoolWork; // rax
  unsigned int v54; // ecx
  void *v56; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE **v57; // [rsp+38h] [rbp-C8h]
  DWORD ReturnLength[4]; // [rsp+40h] [rbp-C0h] BYREF
  void **v59; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v60; // [rsp+58h] [rbp-A8h]
  int v61; // [rsp+68h] [rbp-98h]
  int v62; // [rsp+6Ch] [rbp-94h]
  int v63; // [rsp+70h] [rbp-90h]
  struct TokenHandle *v64; // [rsp+B0h] [rbp-50h]
  PSID pSid[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v66; // [rsp+C8h] [rbp-38h]
  char *v67; // [rsp+D0h] [rbp-30h]
  void **v68; // [rsp+D8h] [rbp-28h]
  void **v69; // [rsp+E0h] [rbp-20h]
  void *v70; // [rsp+E8h] [rbp-18h]
  void **v71; // [rsp+F0h] [rbp-10h]
  _OWORD pExceptionObject[2]; // [rsp+100h] [rbp+0h] BYREF
  __int128 v73; // [rsp+120h] [rbp+20h]
  struct _LUID v74; // [rsp+130h] [rbp+30h]

  v66 = a3;
  v57 = a7;
  v64 = a6;
  v67 = pv;
  v68 = a2;
  v69 = a4;
  pSid[0] = a5;
  v70 = a5;
  v71 = a15;
  _InterlockedAdd((volatile signed __int32 *)*a2 + 2, 1u);
  v56 = *a2;
  *(_QWORD *)ReturnLength = &v56;
  *(_QWORD *)pv = &CAbstractFile::`vftable';
  CCritSec2::CCritSec2((CCritSec2 *)(pv + 8), (bool)a2);
  *((_WORD *)pv + 28) = 0;
  EventW = CreateEventW(0, 1, 1, 0);
  *((_QWORD *)pv + 12) = EventW;
  if ( !EventW )
  {
    if ( (int)GetLastError() > 0 )
      LastError = (unsigned __int16)GetLastError() | 0x80070000;
    else
      LastError = GetLastError();
    *(_OWORD *)((char *)pExceptionObject + 8) = 0;
    *(_QWORD *)&pExceptionObject[0] = &ComError::`vftable';
    *((_QWORD *)&pExceptionObject[1] + 1) = LastError | 0x8D000000000LL;
    LODWORD(v73) = 1;
    throw (ComError *)pExceptionObject;
  }
  _InterlockedAdd((volatile signed __int32 *)v56 + 2, 1u);
  *((_QWORD *)pv + 13) = v56;
  _InterlockedAdd(&dword_180145058, 1u);
  *((_QWORD *)pv + 14) = &GenericStringHandle<unsigned short>::s_EmptyString;
  pv[120] = a13;
  *((_DWORD *)pv + 31) = 0;
  *((_QWORD *)pv + 17) = 0;
  *((_DWORD *)pv + 36) = 0;
  *((_QWORD *)pv + 19) = -1;
  *((_QWORD *)pv + 20) = 0;
  pv[168] = 0;
  *((_QWORD *)pv + 24) = 0;
  v28 = -1;
  *((_DWORD *)pv + 52) = -1;
  *((_DWORD *)pv + 53) = -1;
  _InterlockedIncrement(&dword_180145058);
  *((_QWORD *)pv + 27) = &GenericStringHandle<unsigned short>::s_EmptyString;
  pv[224] = 0;
  *(_OWORD *)(pv + 232) = 0;
  *((_QWORD *)pv + 31) = 0;
  *((_QWORD *)pv + 32) = 0;
  std::wstring::_Construct_empty(pv + 232);
  *((_QWORD *)pv + 33) = 0;
  *((_QWORD *)pv + 34) = 0;
  *((_QWORD *)pv + 35) = 0;
  *((_QWORD *)pv + 36) = 0;
  *((_WORD *)pv + 148) = 0;
  pv[298] = 0;
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_ea395acca3983a8d0e1ee0207f77ef75_Traceguids, pv);
  if ( v56 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v56 + 2, 0xFFFFFFFF) == 1 )
      operator delete(v56, 0x10u);
    v56 = 0;
  }
  AbstractIoThreadAwareWinHttpCallbackHandler::AbstractIoThreadAwareWinHttpCallbackHandler((AbstractIoThreadAwareWinHttpCallbackHandler *)(pv + 304));
  *((_QWORD *)pv + 65) = &AbstractHttpServerCertificateHandler::`vftable';
  *((_QWORD *)pv + 66) = a23;
  CCritSec2::CCritSec2((CCritSec2 *)(pv + 536), v29);
  pv[584] = 0;
  *(_QWORD *)(pv + 588) = 0;
  *(_QWORD *)pv = &CHttpReader::`vftable'{for `CAbstractFile'};
  *((_QWORD *)pv + 38) = &CHttpReader::`vftable'{for `AbstractIoThreadAwareWinHttpCallbackHandler'};
  *((_QWORD *)pv + 65) = &CHttpReader::`vftable'{for `AbstractHttpServerCertificateHandler'};
  v30 = 0;
  *(_OWORD *)(pv + 600) = 0;
  *((_QWORD *)pv + 77) = 0;
  *((_QWORD *)pv + 78) = 0;
  *(double *)&v30 = std::wstring::_Construct_empty(pv + 600);
  *((_DWORD *)pv + 158) = v31;
  *((_QWORD *)pv + 80) = v31;
  *((_QWORD *)pv + 81) = v31;
  *((_QWORD *)pv + 82) = g_WinHttpInterface;
  *((_QWORD *)pv + 83) = v31;
  *((_DWORD *)pv + 168) = v31;
  ReturnLength[0] = v31;
  pExceptionObject[0] = v30;
  pExceptionObject[1] = v30;
  v73 = v30;
  v74 = 0;
  v32 = v64;
  if ( !GetTokenInformation(
          **(HANDLE **)v64,
          (TOKEN_INFORMATION_CLASS)(v31 + 10),
          pExceptionObject,
          v31 + 56,
          ReturnLength) )
  {
    if ( (int)GetLastError() > 0 )
      v33 = (unsigned __int16)GetLastError() | 0x80070000;
    else
      v33 = GetLastError();
    v60 = 0;
    v59 = &ComError::`vftable';
    v61 = v33;
    v62 = 783;
    v63 = 1;
    throw (ComError *)&v59;
  }
  *(struct _LUID *)(pv + 676) = v74;
  if ( (a8 & 2) != 0 )
  {
    ReturnLength[0] = 0;
    memset(pExceptionObject, 0, sizeof(pExceptionObject));
    v73 = 0;
    v74 = 0;
    if ( !GetTokenInformation(**v57, TokenStatistics, pExceptionObject, 0x38u, ReturnLength) )
    {
      if ( (int)GetLastError() > 0 )
        v34 = (unsigned __int16)GetLastError() | 0x80070000;
      else
        v34 = GetLastError();
      v60 = 0;
      v59 = &ComError::`vftable';
      v61 = v34;
      v62 = 783;
      v63 = 1;
      throw (ComError *)&v59;
    }
    v35 = v74;
  }
  else
  {
    v35 = g_nullLuid;
  }
  *(struct _LUID *)(pv + 684) = v35;
  *((_DWORD *)pv + 173) = a19;
  *(_OWORD *)(pv + 700) = 0;
  *((_DWORD *)pv + 179) = 0;
  pv[720] = CCredentialsContainer::IsPassportAuthSet(a12);
  CNestedImpersonation::CNestedImpersonation((CNestedImpersonation *)pExceptionObject, v32);
  v36 = **(CEncryptedCredentials ****)a12;
  v56 = v36;
  while ( v36 != *(CEncryptedCredentials ***)a12 )
  {
    ReturnLength[0] = *((_DWORD *)v36 + 8);
    v37 = v36[5];
    updated = UpdateCRC32((const unsigned __int8 *)ReturnLength, 4, v28);
    v28 = updated;
    if ( v37 )
      v28 = CEncryptedCredentials::UpdateCrc32(v37, updated);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,CEncryptedCredentials *>>>,std::_Iterator_base0>::operator++(&v56);
    v36 = (CEncryptedCredentials **)v56;
  }
  *((_DWORD *)pv + 174) = ~v28;
  CNestedImpersonation::~CNestedImpersonation((CNestedImpersonation *)pExceptionObject);
  if ( !a17 )
  {
    v40 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 )
      goto LABEL_46;
    v41 = 12;
LABEL_45:
    WPP_SF_(*((_QWORD *)v40 + 2), v41, WPP_f564cdc5d2433e52f9a3270eb457e218_Traceguids);
    goto LABEL_46;
  }
  if ( !*(_DWORD *)(a17 + 40) )
  {
    v40 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 )
      goto LABEL_46;
    v41 = 10;
    goto LABEL_45;
  }
  if ( *(_DWORD *)(a17 + 24) != 20 )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_f564cdc5d2433e52f9a3270eb457e218_Traceguids, 1359);
    v60 = 0;
    v59 = &ComError::`vftable';
    v61 = -2147023537;
    v62 = 132;
    v63 = 1;
    throw (ComError *)&v59;
  }
  v39 = *(_QWORD *)(a17 + 16);
  *(_OWORD *)(pv + 700) = *(_OWORD *)v39;
  *((_DWORD *)pv + 179) = *(_DWORD *)(v39 + 16);
LABEL_46:
  v42 = CreateEventW(0, 1, 1, 0);
  *((_QWORD *)pv + 91) = v42;
  if ( !v42 )
  {
    if ( (int)GetLastError() > 0 )
      v43 = (unsigned __int16)GetLastError() | 0x80070000;
    else
      v43 = GetLastError();
    v60 = 0;
    v59 = &ComError::`vftable';
    v61 = v43;
    v62 = 2256;
    v63 = 1;
    throw (ComError *)&v59;
  }
  v44 = CreateEventW(0, 1, 1, 0);
  *((_QWORD *)pv + 92) = v44;
  if ( !v44 )
  {
    if ( (int)GetLastError() > 0 )
      v45 = (unsigned __int16)GetLastError() | 0x80070000;
    else
      v45 = GetLastError();
    v60 = 0;
    v59 = &ComError::`vftable';
    v61 = v45;
    v62 = 2256;
    v63 = 1;
    throw (ComError *)&v59;
  }
  v56 = 0;
  *((_QWORD *)pv + 93) = 0;
  *((_QWORD *)pv + 99) = a11;
  *((_QWORD *)pv + 100) = a12;
  *((_QWORD *)pv + 101) = a17;
  *((_QWORD *)pv + 102) = a18;
  *((_DWORD *)pv + 206) = a19 & 0x700;
  *((_DWORD *)pv + 207) = a19;
  *((_DWORD *)pv + 208) = (a19 >> 11) & 1;
  *((_DWORD *)pv + 209) = 0;
  _InterlockedIncrement(&dword_180145058);
  *((_QWORD *)pv + 107) = &GenericStringHandle<unsigned short>::s_EmptyString;
  _InterlockedIncrement(&dword_180145058);
  *((_QWORD *)pv + 110) = &GenericStringHandle<unsigned short>::s_EmptyString;
  pv[896] = 0;
  *((_DWORD *)pv + 65766) = 0;
  *((_QWORD *)pv + 32884) = 0;
  *(_WORD *)(pv + 263097) = 0;
  pv[263099] = ShouldUseLowPriorityTcp(0);
  *((_QWORD *)pv + 32888) = 0;
  pv[263112] = 0;
  *((_QWORD *)pv + 32890) = GetTickCount64();
  *((_WORD *)pv + 131566) = 0;
  EidAsyncHelper::EidAsyncHelper((EidAsyncHelper *)(pv + 263136));
  _InterlockedIncrement((volatile signed __int32 *)*a15 + 2);
  *((_QWORD *)pv + 32906) = *a15;
  *((_QWORD *)pv + 32907) = a9;
  *((_QWORD *)pv + 32908) = v66;
  _InterlockedIncrement((volatile signed __int32 *)*a4 + 2);
  *((_QWORD *)pv + 32909) = *a4;
  v46 = (SidHandle *)pSid[0];
  *((_QWORD *)pv + 32910) = *(_QWORD *)pSid[0];
  v47 = (volatile signed __int32 *)*((_QWORD *)v46 + 1);
  *((_QWORD *)pv + 32911) = v47;
  _InterlockedIncrement(v47);
  *((_QWORD *)pv + 32912) = a10;
  v48 = *(HANDLE **)v64;
  *((_QWORD *)pv + 32913) = *(_QWORD *)v64;
  _InterlockedIncrement((volatile signed __int32 *)v48 + 2);
  v49 = *v57;
  *((_QWORD *)pv + 32914) = *v57;
  _InterlockedIncrement((volatile signed __int32 *)v49 + 2);
  *((_DWORD *)pv + 65830) = a8;
  *((_DWORD *)pv + 65831) = a14;
  pv[263328] = a22;
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_f564cdc5d2433e52f9a3270eb457e218_Traceguids, pv, pv);
  InitSessionCache();
  if ( *((_DWORD *)pv + 65830) )
  {
    TokenHandle::GetSid(pv + 263312, pSid);
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_D_sid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, v50, *((_DWORD *)pv + 65830), pSid[0]);
    SidHandle::~SidHandle((SidHandle *)pSid);
  }
  *((_DWORD *)pv + 43) = *(_DWORD *)*a2 + 500;
  *((_DWORD *)pv + 50) = 376;
  v57 = (HANDLE **)*((_QWORD *)pv + 93);
  v51 = (int)v57;
  *((_QWORD *)pv + 94) = v57;
  HIDWORD(v57) = *((_DWORD *)pv + 187);
  LODWORD(v57) = v51;
  *((_QWORD *)pv + 95) = v57;
  HIDWORD(v57) = *((_DWORD *)pv + 187);
  LODWORD(v57) = v51;
  *((_QWORD *)pv + 96) = v57;
  HIDWORD(v57) = *((_DWORD *)pv + 187);
  LODWORD(v57) = v51;
  *((_QWORD *)pv + 97) = v57;
  *((_DWORD *)pv + 196) = 128;
  if ( a11 && !ProxyUsageFromJobProxyUsage(*a11) )
  {
    v52 = (struct _TP_CALLBACK_ENVIRON_V3 *)*((_QWORD *)pv + 35);
    if ( !v52 )
      v52 = (struct _TP_CALLBACK_ENVIRON_V3 *)((char *)g_Manager + 992);
    ThreadpoolWork = CreateThreadpoolWork(CHttpReader::StaticProxyResolutionRoutine, pv, v52);
    *((_QWORD *)pv + 81) = ThreadpoolWork;
    if ( !ThreadpoolWork )
    {
      if ( (int)GetLastError() > 0 )
        v54 = (unsigned __int16)GetLastError() | 0x80070000;
      else
        v54 = GetLastError();
      v60 = 0;
      v59 = &ComError::`vftable';
      v61 = v54;
      v62 = 436;
      v63 = 1;
      throw (ComError *)&v59;
    }
  }
  if ( *a2 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)*a2 + 2, 0xFFFFFFFF) == 1 )
      operator delete(*a2, 0x10u);
    *a2 = 0;
  }
  if ( *a4 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)*a4 + 2, 0xFFFFFFFF) == 1 )
      operator delete(*a4, 0x10u);
    *a4 = 0;
  }
  SidHandle::~SidHandle(v46);
  if ( *a15 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)*a15 + 2, 0xFFFFFFFF) == 1 )
      operator delete(*a15, 0x10u);
    *a15 = 0;
  }
  return pv;
}

```

## disassembly

```asm
0x1800523e8  mov     [rsp-8+arg_10], rbx
0x1800523ed  push    rbp
0x1800523ee  push    rsi
0x1800523ef  push    rdi
0x1800523f0  push    r12
0x1800523f2  push    r13
0x1800523f4  push    r14
0x1800523f6  push    r15
0x1800523f8  lea     rbp, [rsp-70h]
0x1800523fd  sub     rsp, 170h
0x180052404  mov     rax, cs:__security_cookie
0x18005240b  xor     rax, rsp
0x18005240e  mov     [rbp+0A0h+var_40], rax
0x180052412  mov     r15, r9
0x180052415  mov     [rbp+0A0h+var_D8], r8
0x180052419  mov     r14, rdx
0x18005241c  mov     rdi, rcx
0x18005241f  mov     r13, [rbp+0A0h+arg_58]
0x180052426  mov     rax, [rbp+0A0h+arg_30]
0x18005242d  mov     [rsp+1A0h+var_168], rax
0x180052432  mov     rax, [rbp+0A0h+arg_28]
0x180052439  mov     [rbp+0A0h+var_F0], rax
0x18005243d  mov     [rbp+0A0h+var_D0], rcx
0x180052441  mov     [rbp+0A0h+var_C8], rdx
0x180052445  mov     [rbp+0A0h+var_C0], r9
0x180052449  mov     rax, [rbp+0A0h+arg_20]
0x180052450  mov     [rbp+0A0h+pSid], rax
0x180052454  mov     [rbp+0A0h+var_B8], rax
0x180052458  mov     r12, [rbp+0A0h+arg_70]
0x18005245f  mov     [rbp+0A0h+var_B0], r12
0x180052463  mov     rax, [rdx]
0x180052466  mov     esi, 1
0x18005246b  lock add [rax+8], esi
0x18005246f  mov     rax, [rdx]
0x180052472  mov     [rsp+1A0h+var_170], rax
0x180052477  lea     rax, [rsp+1A0h+var_170]
0x18005247c  mov     qword ptr [rsp+1A0h+var_160], rax
0x180052481  lea     rax, ??_7CAbstractFile@@6B@; const CAbstractFile::`vftable'
0x180052488  mov     [rcx], rax
0x18005248b  add     rcx, 8; this
0x18005248f  call    ??0CCritSec2@@QEAA@_N@Z; CCritSec2::CCritSec2(bool)
0x180052494  nop
0x180052495  xor     ebx, ebx
0x180052497  mov     [rdi+38h], bx
0x18005249b  xor     r9d, r9d; lpName
0x18005249e  mov     r8d, esi; bInitialState
0x1800524a1  mov     edx, esi; bManualReset
0x1800524a3  xor     ecx, ecx; lpEventAttributes
0x1800524a5  call    cs:__imp_CreateEventW
0x1800524ab  mov     [rdi+60h], rax
0x1800524af  test    rax, rax
0x1800524b2  jnz     short loc_180052507
0x1800524b4  call    cs:__imp_GetLastError
0x1800524ba  test    eax, eax
0x1800524bc  jg      short loc_1800524C8
0x1800524be  call    cs:__imp_GetLastError
0x1800524c4  mov     ecx, eax
0x1800524c6  jmp     short loc_1800524D7
0x1800524c8  call    cs:__imp_GetLastError
0x1800524ce  movzx   ecx, ax
0x1800524d1  or      ecx, 80070000h
0x1800524d7  xorps   xmm0, xmm0
0x1800524da  movups  [rbp+0A0h+pExceptionObject+8], xmm0
0x1800524de  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800524e5  mov     qword ptr [rbp+0A0h+pExceptionObject], rax
0x1800524e9  mov     [rbp+0A0h+var_88], ecx
0x1800524ec  mov     [rbp+0A0h+var_84], 8D0h
0x1800524f3  mov     dword ptr [rbp+0A0h+var_80], esi
0x1800524f6  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800524fd  lea     rcx, [rbp+0A0h+pExceptionObject]; pExceptionObject
0x180052501  call    _CxxThrowException_0
0x180052507  mov     rax, [rsp+1A0h+var_170]
0x18005250c  lock add [rax+8], esi
0x180052510  mov     rax, [rsp+1A0h+var_170]
0x180052515  mov     [rdi+68h], rax
0x180052519  lock add cs:dword_180145058, esi
0x180052520  lea     rcx, ?s_EmptyString@?$GenericStringHandle@G@@0UStringData@1@A; GenericStringHandle<ushort>::StringData GenericStringHandle<ushort>::s_EmptyString
0x180052527  mov     [rdi+70h], rcx
0x18005252b  mov     al, [rbp+0A0h+arg_60]
0x180052531  mov     [rdi+78h], al
0x180052534  mov     [rdi+7Ch], ebx
0x180052537  mov     [rdi+88h], rbx
0x18005253e  mov     [rdi+90h], ebx
0x180052544  mov     qword ptr [rdi+98h], 0FFFFFFFFFFFFFFFFh
0x18005254f  mov     [rdi+0A0h], rbx
0x180052556  mov     [rdi+0A8h], bl
0x18005255c  mov     [rdi+0C0h], rbx
0x180052563  or      esi, 0FFFFFFFFh
0x180052566  mov     [rdi+0D0h], esi
0x18005256c  mov     [rdi+0D4h], esi
0x180052572  lock inc cs:dword_180145058
0x180052579  mov     [rdi+0D8h], rcx
0x180052580  mov     [rdi+0E0h], bl
0x180052586  lea     rcx, [rdi+0E8h]
0x18005258d  xorps   xmm0, xmm0
0x180052590  movups  xmmword ptr [rcx], xmm0
0x180052593  mov     [rcx+10h], rbx
0x180052597  mov     [rcx+18h], rbx
0x18005259b  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x1800525a0  mov     [rdi+108h], rbx
0x1800525a7  mov     [rdi+110h], rbx
0x1800525ae  mov     [rdi+118h], rbx
0x1800525b5  mov     [rdi+120h], rbx
0x1800525bc  mov     [rdi+128h], bx
0x1800525c3  mov     [rdi+12Ah], bl
0x1800525c9  lea     rax, WPP_GLOBAL_Control
0x1800525d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800525d7  cmp     rcx, rax
0x1800525da  jz      short loc_1800525FE
0x1800525dc  test    dword ptr [rcx+1Ch], 800h
0x1800525e3  jz      short loc_1800525FE
0x1800525e5  mov     edx, 0Ah
0x1800525ea  mov     r9, rdi
0x1800525ed  lea     r8, WPP_ea395acca3983a8d0e1ee0207f77ef75_Traceguids
0x1800525f4  mov     rcx, [rcx+10h]
0x1800525f8  call    WPP_SF_q
0x1800525fd  nop
0x1800525fe  mov     rcx, [rsp+1A0h+var_170]
0x180052603  test    rcx, rcx
0x180052606  jz      short loc_180052627
0x180052608  or      eax, 0FFFFFFFFh
0x18005260b  lock xadd [rcx+8], eax
0x180052610  cmp     eax, 1
0x180052613  jnz     short loc_180052622
0x180052615  lea     edx, [rax+0Fh]; unsigned __int64
0x180052618  mov     rcx, [rsp+1A0h+var_170]; void *
0x18005261d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180052622  mov     [rsp+1A0h+var_170], rbx
0x180052627  lea     rbx, [rdi+130h]
0x18005262e  mov     rcx, rbx; this
0x180052631  call    ??0AbstractIoThreadAwareWinHttpCallbackHandler@@QEAA@XZ; AbstractIoThreadAwareWinHttpCallbackHandler::AbstractIoThreadAwareWinHttpCallbackHandler(void)
0x180052636  nop
0x180052637  lea     rax, ??_7AbstractHttpServerCertificateHandler@@6B@; const AbstractHttpServerCertificateHandler::`vftable'
0x18005263e  mov     [rdi+208h], rax
0x180052645  mov     rax, [rbp+0A0h+arg_B0]
0x18005264c  mov     [rdi+210h], rax
0x180052653  lea     rcx, [rdi+218h]; this
0x18005265a  call    ??0CCritSec2@@QEAA@_N@Z; CCritSec2::CCritSec2(bool)
0x18005265f  xor     edx, edx
0x180052661  mov     [rdi+248h], dl
0x180052667  mov     [rdi+24Ch], rdx
0x18005266e  lea     rax, ??_7CHttpReader@@6BCAbstractFile@@@; const CHttpReader::`vftable'{for `CAbstractFile'}
0x180052675  mov     [rdi], rax
0x180052678  lea     rax, ??_7CHttpReader@@6BAbstractIoThreadAwareWinHttpCallbackHandler@@@; const CHttpReader::`vftable'{for `AbstractIoThreadAwareWinHttpCallbackHandler'}
0x18005267f  mov     [rbx], rax
0x180052682  lea     rax, ??_7CHttpReader@@6BAbstractHttpServerCertificateHandler@@@; const CHttpReader::`vftable'{for `AbstractHttpServerCertificateHandler'}
0x180052689  mov     [rdi+208h], rax
0x180052690  lea     rcx, [rdi+258h]
0x180052697  xorps   xmm0, xmm0
0x18005269a  movups  xmmword ptr [rcx], xmm0
0x18005269d  mov     [rcx+10h], rdx
0x1800526a1  mov     [rcx+18h], rdx
0x1800526a5  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x1800526aa  nop
0x1800526ab  mov     [rdi+278h], edx
0x1800526b1  mov     [rdi+280h], rdx
0x1800526b8  mov     [rdi+288h], rdx
0x1800526bf  mov     rax, cs:?g_WinHttpInterface@@3REAVIHttpInterface@@EA; IHttpInterface * g_WinHttpInterface
0x1800526c6  mov     [rdi+290h], rax
0x1800526cd  mov     [rdi+298h], rdx
0x1800526d4  mov     [rdi+2A0h], edx
0x1800526da  mov     [rsp+1A0h+var_160], edx
0x1800526de  xor     eax, eax
0x1800526e0  movups  [rbp+0A0h+pExceptionObject], xmm0
0x1800526e4  movups  xmmword ptr [rbp+10h], xmm0
0x1800526e8  movups  [rbp+0A0h+var_80], xmm0
0x1800526ec  mov     [rbp+0A0h+var_70], rax
0x1800526f0  mov     rbx, [rbp+0A0h+var_F0]
0x1800526f4  mov     rcx, [rbx]
0x1800526f7  lea     rax, [rsp+1A0h+var_160]
0x1800526fc  mov     [rsp+1A0h+ReturnLength], rax; ReturnLength
0x180052701  lea     r9d, [rdx+38h]; TokenInformationLength
0x180052705  lea     r8, [rbp+0A0h+pExceptionObject]; TokenInformation
0x180052709  lea     edx, [r9-2Eh]; TokenInformationClass
0x18005270d  mov     rcx, [rcx]; TokenHandle
0x180052710  call    cs:__imp_GetTokenInformation
0x180052716  test    eax, eax
0x180052718  jnz     short loc_180052777
0x18005271a  call    cs:__imp_GetLastError
0x180052720  test    eax, eax
0x180052722  jg      short loc_18005272E
0x180052724  call    cs:__imp_GetLastError
0x18005272a  mov     ecx, eax
0x18005272c  jmp     short loc_18005273D
0x18005272e  call    cs:__imp_GetLastError
0x180052734  movzx   ecx, ax
0x180052737  or      ecx, 80070000h
0x18005273d  xorps   xmm0, xmm0
0x180052740  movups  [rsp+1A0h+var_148], xmm0
0x180052745  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18005274c  mov     [rsp+1A0h+var_150], rax
0x180052751  mov     [rsp+1A0h+var_138], ecx
0x180052755  mov     [rsp+1A0h+var_134], 30Fh
0x18005275d  mov     [rsp+1A0h+var_130], 1
0x180052765  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18005276c  lea     rcx, [rsp+1A0h+var_150]; pExceptionObject
0x180052771  call    _CxxThrowException_0
0x180052777  mov     rax, [rbp+0A0h+var_70]
0x18005277b  mov     [rdi+2A4h], rax
0x180052782  test    byte ptr [rbp+0A0h+arg_38], 2
0x180052789  jz      loc_18005283C
0x18005278f  mov     [rsp+1A0h+var_160], 0
0x180052797  xorps   xmm0, xmm0
0x18005279a  xor     eax, eax
0x18005279c  movups  [rbp+0A0h+pExceptionObject], xmm0
0x1800527a0  movups  xmmword ptr [rbp+10h], xmm0
0x1800527a4  movups  [rbp+0A0h+var_80], xmm0
0x1800527a8  mov     [rbp+0A0h+var_70], rax
0x1800527ac  mov     rcx, [rsp+1A0h+var_168]
0x1800527b1  mov     rcx, [rcx]
0x1800527b4  lea     rax, [rsp+1A0h+var_160]
0x1800527b9  mov     [rsp+1A0h+ReturnLength], rax; ReturnLength
0x1800527be  mov     r9d, 38h ; '8'; TokenInformationLength
0x1800527c4  lea     r8, [rbp+0A0h+pExceptionObject]; TokenInformation
0x1800527c8  lea     edx, [r9-2Eh]; TokenInformationClass
0x1800527cc  mov     rcx, [rcx]; TokenHandle
0x1800527cf  call    cs:__imp_GetTokenInformation
0x1800527d5  test    eax, eax
0x1800527d7  jnz     short loc_180052836
0x1800527d9  call    cs:__imp_GetLastError
0x1800527df  test    eax, eax
0x1800527e1  jg      short loc_1800527ED
0x1800527e3  call    cs:__imp_GetLastError
0x1800527e9  mov     ecx, eax
0x1800527eb  jmp     short loc_1800527FC
0x1800527ed  call    cs:__imp_GetLastError
0x1800527f3  movzx   ecx, ax
0x1800527f6  or      ecx, 80070000h
0x1800527fc  xorps   xmm0, xmm0
0x1800527ff  movups  [rsp+1A0h+var_148], xmm0
0x180052804  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x18005280b  mov     [rsp+1A0h+var_150], rax
0x180052810  mov     [rsp+1A0h+var_138], ecx
0x180052814  mov     [rsp+1A0h+var_134], 30Fh
0x18005281c  mov     [rsp+1A0h+var_130], 1
0x180052824  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18005282b  lea     rcx, [rsp+1A0h+var_150]; pExceptionObject
0x180052830  call    _CxxThrowException_0
0x180052836  mov     rax, [rbp+0A0h+var_70]
0x18005283a  jmp     short loc_180052843
0x18005283c  mov     rax, cs:?g_nullLuid@@3U_LUID@@B; _LUID const g_nullLuid
0x180052843  mov     [rdi+2ACh], rax
0x18005284a  mov     eax, [rbp+0A0h+arg_90]
0x180052850  mov     [rdi+2B4h], eax
0x180052856  xorps   xmm0, xmm0
0x180052859  xor     eax, eax
0x18005285b  movups  xmmword ptr [rdi+2BCh], xmm0
0x180052862  mov     [rdi+2CCh], eax
0x180052868  mov     rcx, r13; this
0x18005286b  call    ?IsPassportAuthSet@CCredentialsContainer@@QEBA_NXZ; CCredentialsContainer::IsPassportAuthSet(void)
0x180052870  mov     [rdi+2D0h], al
0x180052876  mov     rdx, rbx; struct TokenHandle *
0x180052879  lea     rcx, [rbp+0A0h+pExceptionObject]; this
0x18005287d  call    ??0CNestedImpersonation@@QEAA@AEBVTokenHandle@@@Z; CNestedImpersonation::CNestedImpersonation(TokenHandle const &)
0x180052882  nop
0x180052883  mov     rax, [r13+0]
0x180052887  mov     rax, [rax]
0x18005288a  mov     [rsp+1A0h+var_170], rax
0x18005288f  cmp     rax, [r13+0]
0x180052893  jz      short loc_1800528D6
0x180052895  mov     ecx, [rax+20h]
0x180052898  mov     [rsp+1A0h+var_160], ecx
0x18005289c  mov     rbx, [rax+28h]
0x1800528a0  mov     r8d, esi; unsigned int
0x1800528a3  mov     edx, 4; int
0x1800528a8  lea     rcx, [rsp+1A0h+var_160]; unsigned __int8 *
0x1800528ad  call    ?UpdateCRC32@@YAKPEBEHK@Z; UpdateCRC32(uchar const *,int,ulong)
0x1800528b2  mov     esi, eax
0x1800528b4  test    rbx, rbx
0x1800528b7  jz      short loc_1800528C5
0x1800528b9  mov     edx, eax; unsigned int
0x1800528bb  mov     rcx, rbx; this
0x1800528be  call    ?UpdateCrc32@CEncryptedCredentials@@QEBAKK@Z; CEncryptedCredentials::UpdateCrc32(ulong)
0x1800528c3  mov     esi, eax
0x1800528c5  lea     rcx, [rsp+1A0h+var_170]
0x1800528ca  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKPEAVCEncryptedCredentials@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,CEncryptedCredentials *>>>,std::_Iterator_base0>::operator++(void)
0x1800528cf  mov     rax, [rsp+1A0h+var_170]
0x1800528d4  jmp     short loc_18005288F
0x1800528d6  not     esi
0x1800528d8  mov     [rdi+2B8h], esi
0x1800528de  lea     rcx, [rbp+0A0h+pExceptionObject]; this
0x1800528e2  call    ??1CNestedImpersonation@@QEAA@XZ; CNestedImpersonation::~CNestedImpersonation(void)
0x1800528e7  lea     rax, WPP_f564cdc5d2433e52f9a3270eb457e218_Traceguids
0x1800528ee  mov     rbx, [rbp+0A0h+arg_80]
0x1800528f5  xor     esi, esi
0x1800528f7  test    rbx, rbx
0x1800528fa  jz      loc_1800529C5
0x180052900  cmp     [rbx+28h], esi
0x180052903  jz      loc_1800529A2
0x180052909  cmp     dword ptr [rbx+18h], 14h
0x18005290d  jz      short loc_180052989
0x18005290f  mov     rcx, cs:WPP_GLOBAL_Control
0x180052916  lea     rdx, WPP_GLOBAL_Control
0x18005291d  cmp     rcx, rdx
0x180052920  jz      short loc_18005293D
0x180052922  test    byte ptr [rcx+1Ch], 4
0x180052926  jz      short loc_18005293D
0x180052928  lea     edx, [rsi+0Bh]
0x18005292b  mov     r9d, 54Fh
0x180052931  mov     r8, rax
  ... truncated ...
```
