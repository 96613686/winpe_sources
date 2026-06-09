# CJobManager::CloneUserToken(SidHandle,AppPackageInfo *,int,ulong,unsigned __int64 *,GenericStringHandle<ushort>,TokenHandle *)

- ea: `0x18001a6fc`
- end: `0x18001b44e`
- name: `?CloneUserToken@CJobManager@@QEAAJVSidHandle@@PEAUAppPackageInfo@@HKPEA_KV?$GenericStringHandle@G@@PEAVTokenHandle@@@Z`
- size: `3410`
- prototype: `__int64 __fastcall(__int64, SidHandle *, AppPackageInfo *, int, unsigned int, __int64 *, void **, TokenHandle *)`
- caller_count: `8`
- callee_count: `31`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180013b70`
- `0x180013ddc`
- `0x180016ee0`
- `0x180019040`
- `0x18001a130`
- `0x18001b460`
- `0x1800286b4`
- `0x1800c365c`

## callees

- `0x180006640`
- `0x180008b70`
- `0x18000db20`
- `0x18000f5f0`
- `0x180013368`
- `0x180014310`
- `0x180016d60`
- `0x180018880`
- `0x18001a6fc`
- `0x18001d7f0`
- `0x18002d330`
- `0x1800377b8`
- `0x18003a1fc`
- `0x1800586f0`
- `0x18007a604`
- `0x18007c29c`
- `0x180081228`
- `0x180099740`
- `0x18009d024`
- `0x18009e9c8`
- `0x1800a1114`
- `0x1800a3420`
- `0x1800a3444`
- `0x1800a400c`
- `0x1800a41f0`
- `0x1800ac6c0`
- `0x1800b15a8`
- `0x1800b1638`
- `0x1800b16e8`
- `0x1800b1980`
- `0x1800f9948`

## import_xrefs

- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18001b17b`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18001b187`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18001b18f`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18001b17b`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18001b187`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18001b18f`
- `ntdll!NtCreateLowBoxToken` at `0x18001afee`
- `ntdll!NtCreateLowBoxToken` at `0x18001afee`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001b2c8`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001b2c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ab36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ab40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ab48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ab36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ab40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ab48`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a8f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b22f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b269`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b2f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a8f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b22f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b269`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b2f4`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001ab2c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001ab2c`
- `ext-ms-win-com-psmregister-l1-2-0!PsmAdjustActivationToken` at `0x18001b16a`
- `ext-ms-win-com-psmregister-l1-2-0!PsmAdjustActivationToken` at `0x18001b16a`
- `ext-ms-win-kernel32-package-l1-1-0!AppXFreeMemory` at `0x18001b0b3`
- `ext-ms-win-kernel32-package-l1-1-0!AppXFreeMemory` at `0x18001b0d2`
- `ext-ms-win-kernel32-package-l1-1-0!AppXFreeMemory` at `0x18001b0b3`
- `ext-ms-win-kernel32-package-l1-1-0!AppXFreeMemory` at `0x18001b0d2`
- `ext-ms-win-kernel32-package-l1-1-0!AppXGetPackageCapabilities` at `0x18001ae28`
- `ext-ms-win-kernel32-package-l1-1-0!AppXGetPackageCapabilities` at `0x18001ae28`
- `ext-ms-win-kernel32-package-l1-1-0!AppXGetPackageSid` at `0x18001ad1c`
- `ext-ms-win-kernel32-package-l1-1-0!AppXGetPackageSid` at `0x18001ad1c`

## pseudocode

```c
// Hidden C++ exception states: #wind=13 #try_helpers=1
__int64 __fastcall CJobManager::CloneUserToken(
        __int64 a1,
        SidHandle *a2,
        AppPackageInfo *a3,
        int a4,
        DWORD a5,
        unsigned __int64 *a6,
        void **a7,
        TokenHandle *a8)
{
  void **v10; // r15
  unsigned int v11; // r12d
  unsigned __int64 v12; // r8
  const wchar_t *v13; // rcx
  const wchar_t *v14; // rax
  _DWORD *v15; // rax
  _DWORD *v16; // rax
  int ServiceToken; // eax
  volatile signed __int32 *v18; // rbx
  volatile signed __int32 *v20; // rdi
  int v21; // eax
  AppPackageInfo *v22; // rbx
  unsigned int LastError; // eax
  char v24; // bl
  char v25; // al
  AppPackageInfo *v26; // r9
  _QWORD *v27; // r9
  volatile signed __int32 *v28; // rbx
  EVENT_LOG *v29; // rcx
  _QWORD *v30; // rcx
  int v31; // r14d
  _QWORD *v32; // rcx
  int v33; // r14d
  __int64 v34; // r8
  unsigned int v35; // r14d
  unsigned int v36; // eax
  EVENT_LOG *v37; // rcx
  _DWORD *v38; // rax
  __int64 v39; // rbx
  unsigned int v40; // esi
  CJobManager *v41; // r14
  HANDLE v42; // r15
  void **RawBuffer; // rax
  NTSTATUS v44; // eax
  int v45; // eax
  __int64 v46; // rax
  CJobManager *v47; // rax
  LPVOID v48; // r14
  _QWORD *v49; // rax
  _QWORD *v50; // r9
  NTSTATUS v51; // eax
  NTSTATUS v52; // esi
  signed int v53; // eax
  TokenHandle *v54; // rsi
  void **v55; // rbx
  int v56; // [rsp+50h] [rbp-468h] BYREF
  char v57; // [rsp+54h] [rbp-464h]
  unsigned int v58; // [rsp+58h] [rbp-460h] BYREF
  void *v59; // [rsp+60h] [rbp-458h] BYREF
  CJobManager *v60; // [rsp+68h] [rbp-450h] BYREF
  __int64 v61; // [rsp+70h] [rbp-448h] BYREF
  volatile signed __int32 *v62; // [rsp+78h] [rbp-440h] BYREF
  volatile signed __int32 *v63; // [rsp+80h] [rbp-438h]
  AppPackageInfo *v64; // [rsp+88h] [rbp-430h]
  CUserSession *UserSession; // [rsp+90h] [rbp-428h] BYREF
  volatile signed __int32 *v66; // [rsp+98h] [rbp-420h] BYREF
  HANDLE *v67; // [rsp+A0h] [rbp-418h] BYREF
  void **v68; // [rsp+A8h] [rbp-410h]
  __int64 v69; // [rsp+B0h] [rbp-408h] BYREF
  __int64 v70; // [rsp+B8h] [rbp-400h] BYREF
  __int64 v71; // [rsp+C0h] [rbp-3F8h]
  __int64 v72; // [rsp+C8h] [rbp-3F0h]
  __int128 v73; // [rsp+D0h] [rbp-3E8h]
  TokenHandle *v74; // [rsp+E0h] [rbp-3D8h]
  SidHandle *v75; // [rsp+E8h] [rbp-3D0h]
  SidHandle *v76; // [rsp+F8h] [rbp-3C0h]
  void **v77; // [rsp+100h] [rbp-3B8h]
  CUserSession **p_UserSession; // [rsp+108h] [rbp-3B0h]
  char v79; // [rsp+110h] [rbp-3A8h]
  void **pExceptionObject; // [rsp+120h] [rbp-398h] BYREF
  __int128 v81; // [rsp+128h] [rbp-390h]
  int v82; // [rsp+138h] [rbp-380h]
  int v83; // [rsp+13Ch] [rbp-37Ch]
  int v84; // [rsp+140h] [rbp-378h]
  void **v85; // [rsp+180h] [rbp-338h] BYREF
  __int128 v86; // [rsp+188h] [rbp-330h]
  int v87; // [rsp+198h] [rbp-320h]
  int v88; // [rsp+19Ch] [rbp-31Ch]
  int v89; // [rsp+1A0h] [rbp-318h]
  void **v90; // [rsp+1E0h] [rbp-2D8h] BYREF
  __int128 v91; // [rsp+1E8h] [rbp-2D0h]
  unsigned int v92; // [rsp+1F8h] [rbp-2C0h]
  int v93; // [rsp+1FCh] [rbp-2BCh]
  int v94; // [rsp+200h] [rbp-2B8h]
  void **v95; // [rsp+240h] [rbp-278h] BYREF
  __int128 v96; // [rsp+248h] [rbp-270h]
  int v97; // [rsp+258h] [rbp-260h]
  int v98; // [rsp+25Ch] [rbp-25Ch]
  int v99; // [rsp+260h] [rbp-258h]
  void **v100; // [rsp+2A0h] [rbp-218h] BYREF
  __int128 v101; // [rsp+2A8h] [rbp-210h]
  int v102; // [rsp+2B8h] [rbp-200h]
  int v103; // [rsp+2BCh] [rbp-1FCh]
  int v104; // [rsp+2C0h] [rbp-1F8h]
  void **v105; // [rsp+300h] [rbp-1B8h] BYREF
  __int128 v106; // [rsp+308h] [rbp-1B0h]
  int v107; // [rsp+318h] [rbp-1A0h]
  int v108; // [rsp+31Ch] [rbp-19Ch]
  int v109; // [rsp+320h] [rbp-198h]
  void **v110; // [rsp+360h] [rbp-158h] BYREF
  __int128 v111; // [rsp+368h] [rbp-150h]
  signed int v112; // [rsp+378h] [rbp-140h]
  int v113; // [rsp+37Ch] [rbp-13Ch]
  int v114; // [rsp+380h] [rbp-138h]
  void **v115; // [rsp+3C0h] [rbp-F8h] BYREF
  __int128 v116; // [rsp+3C8h] [rbp-F0h]
  int v117; // [rsp+3D8h] [rbp-E0h]
  int v118; // [rsp+3DCh] [rbp-DCh]
  int v119; // [rsp+3E0h] [rbp-D8h]
  _BYTE v120[56]; // [rsp+420h] [rbp-98h] BYREF
  _QWORD v121[2]; // [rsp+458h] [rbp-60h] BYREF
  __m128i si128; // [rsp+468h] [rbp-50h]

  v56 = a4;
  v64 = a3;
  v75 = a2;
  v74 = a8;
  v76 = a2;
  v10 = a7;
  v68 = a7;
  v77 = a7;
  v60 = g_Manager;
  v11 = 0;
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v12 = 0;
    if ( a6 )
      v12 = *a6;
    v13 = L"YES";
    v14 = L"YES";
    if ( a6 )
      v14 = L"NO";
    if ( !a3 )
      v13 = L"NO";
    WPP_SF__sid_SdLSiS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      WPP_GLOBAL_Control,
      v12,
      *(_QWORD *)a2,
      v13,
      a4,
      a5,
      v14,
      v12,
      (char *)*a7 + 12);
  }
  if ( **(_QWORD **)a8 )
  {
    v15 = operator new(0x10u);
    v59 = v15;
    v15[2] = 1;
    *(_QWORD *)v15 = 0;
    TokenHandle::operator=(a8, &v59);
    TokenHandle::Decrement((TokenHandle *)&v59);
  }
  if ( *(_QWORD *)*a7 )
  {
    v16 = operator new(0x10u);
    v59 = v16;
    v16[2] = 1;
    *(_QWORD *)v16 = 0;
    ServiceToken = ServiceUserTokenHelper::CreateServiceToken((const unsigned __int16 *)*a7 + 6, (char ***)&v59);
    if ( ServiceToken < 0 )
    {
      v81 = 0;
      pExceptionObject = &ComError::`vftable';
      v82 = ServiceToken;
      v83 = 1576;
      v84 = 1;
      throw (ComError *)&pExceptionObject;
    }
    v18 = (volatile signed __int32 *)v59;
    if ( **(_QWORD **)a8 != *(_QWORD *)v59 )
    {
      TokenHandle::Decrement(a8);
      *(_QWORD *)a8 = v18;
      _InterlockedAdd(v18 + 2, 1u);
    }
    if ( _InterlockedExchangeAdd(v18 + 2, 0xFFFFFFFF) == 1 )
    {
      if ( (unsigned __int64)(*(_QWORD *)v18 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        CloseHandle(*(HANDLE *)v18);
        *(_QWORD *)v18 = 0;
      }
      operator delete((void *)v18, 0x10u);
    }
    SidHandle::~SidHandle(a2);
    if ( *a7 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)*a7 + 2, 0xFFFFFFFF) == 1 )
        operator delete(*a7, 0x10u);
      *a7 = 0;
    }
    return 0;
  }
  v62 = *(volatile signed __int32 **)a2;
  v63 = (volatile signed __int32 *)*((_QWORD *)a2 + 1);
  _InterlockedAdd(v63, 1u);
  UserSession = (CUserSession *)CLoggedOnUsers::FindUserSession((__int64)v60 + 784, (PSID *)&v62, a6);
  if ( !UserSession )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids);
    SidHandle::~SidHandle(a2);
    GenericStringHandle<unsigned short>::FreeIt(a7);
    return 2147943645LL;
  }
  p_UserSession = &UserSession;
  v79 = 1;
  v20 = (volatile signed __int32 *)operator new(0x10u);
  v66 = v20;
  *((_DWORD *)v20 + 2) = 1;
  *(_QWORD *)v20 = 0;
  v21 = CUserSession::CopyToken((PSID *)UserSession, v56, a5, (void **)v20);
  if ( v21 < 0 )
  {
    v86 = 0;
    v85 = &ComError::`vftable';
    v87 = v21;
    v88 = 1598;
    v89 = 1;
    throw (ComError *)&v85;
  }
  v22 = v64;
  if ( !v64 )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)((_DWORD)v64 + 62),
        &WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids);
    TokenHandle::operator=(a8, &v66);
    TokenHandle::Decrement((TokenHandle *)&v66);
    CUserSession::DecrementRefCount(UserSession);
    SidHandle::~SidHandle(a2);
    GenericStringHandle<unsigned short>::FreeIt(a7);
    return 0;
  }
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, &WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids);
  AppPackageInfo::Dump(v22);
  CSaveThreadToken::CSaveThreadToken((CSaveThreadToken *)&v67);
  if ( !RevertToSelf() )
  {
    if ( (int)GetLastError() > 0 )
      LastError = (unsigned __int16)GetLastError() | 0x80070000;
    else
      LastError = GetLastError();
    v91 = 0;
    v90 = &ComError::`vftable';
    v92 = LastError;
    v93 = 1627;
    v94 = 1;
    throw (ComError *)&v90;
  }
  v57 = IsAppXGetPackageCapabilitiesPresent();
  v24 = IsAppXGetPackageCapabilitiesPresent();
  v25 = IsPsmAdjustActivationTokenPresent();
  if ( !v57 || !v24 || !v25 )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      LOBYTE(v11) = v57 != 0;
      WPP_SF_DDD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        64,
        &WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids,
        v11,
        v24 != 0,
        v25 != 0);
    }
    v116 = 0;
    v115 = &ComError::`vftable';
    v117 = -2145386389;
    v118 = 1643;
    v119 = 1;
    throw (ComError *)&v115;
  }
  if ( *((_QWORD *)v64 + 3) <= 7u )
    v26 = v64;
  else
    v26 = *(AppPackageInfo **)v64;
  v62 = *(volatile signed __int32 **)a2;
  v63 = (volatile signed __int32 *)*((_QWORD *)a2 + 1);
  _InterlockedAdd(v63, 1u);
  CJobManager::GetPackageFullNameFromPackageFamilyName(v60, v121, &v62, v26);
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v27 = v121;
    if ( si128.m128i_i64[1] > 7uLL )
      v27 = (_QWORD *)v121[0];
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids, v27);
  }
  v28 = v20;
  v62 = v20;
  _InterlockedAdd(v20 + 2, 1u);
  if ( !*((_BYTE *)v64 + 68) )
  {
    v56 = 0;
    v58 = 0;
    v60 = 0;
    v61 = 0;
    CNestedImpersonation::CNestedImpersonation((CNestedImpersonation *)v120, (const struct TokenHandle *)&v66);
    v69 = (__int64)&v60;
    v70 = 0;
    LOBYTE(v71) = 1;
    v30 = v121;
    if ( si128.m128i_i64[1] > 7uLL )
      v30 = (_QWORD *)v121[0];
    v31 = AppXGetPackageSid(v30, &v70);
    wil::details::out_param_t<wistd::unique_ptr<_SID_AND_ATTRIBUTES [0],wil::function_deleter<void (*)(void *),&void AppXFreeMemory(void *)>>>::~out_param_t<wistd::unique_ptr<_SID_AND_ATTRIBUTES [0],wil::function_deleter<void (*)(void *),&void AppXFreeMemory(void *)>>>(&v69);
    if ( v31 < 0 )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          67,
          &WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids,
          (unsigned int)v31);
      v96 = 0;
      v95 = &ComError::`vftable';
      v97 = -2145386390;
      v98 = 1671;
      v99 = 1;
      throw (ComError *)&v95;
    }
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF__sid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, &WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids, v60);
    v69 = (__int64)&v61;
    v70 = 0;
    LOBYTE(v71) = 1;
    v32 = v121;
    if ( si128.m128i_i64[1] > 7uLL )
      v32 = (_QWORD *)v121[0];
    v33 = AppXGetPackageCapabilities(v32, &v56, &v70, &v58);
    wil::details::out_param_t<wistd::unique_ptr<_SID_AND_ATTRIBUTES [0],wil::function_deleter<void (*)(void *),&void AppXFreeMemory(void *)>>>::~out_param_t<wistd::unique_ptr<_SID_AND_ATTRIBUTES [0],wil::function_deleter<void (*)(void *),&void AppXFreeMemory(void *)>>>(&v69);
    if ( v33 < 0 )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          69,
          &WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids,
          (unsigned int)v33);
      v101 = 0;
      v100 = &ComError::`vftable';
      v102 = -2145386390;
      v103 = 1683;
      v104 = 1;
      throw (ComError *)&v100;
    }
    v35 = 0;
    v36 = v58;
    if ( v58 )
    {
      v37 = WPP_GLOBAL_Control;
      do
      {
        if ( v37 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)v37 + 28) & 1) != 0 )
        {
          WPP_SF__sid_L(
            *((_QWORD *)v37 + 2),
            2LL * v35,
            v34,
            *(_QWORD *)(v61 + 16LL * v35),
            *(_DWORD *)(v61 + 16LL * v35 + 8));
          v37 = WPP_GLOBAL_Control;
          v36 = v58;
        }
        ++v35;
      }
      while ( v35 < v36 );
    }
    CNestedImpersonation::~CNestedImpersonation((CNestedImpersonation *)v120);
    if ( v56 )
    {
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_95;
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, &WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids);
    }
    else
    {
      v69 = 48;
      v72 = 0;
      v70 = 0;
      v71 = 0;
      v73 = 0;
      v38 = operator new(0x10u);
      v59 = v38;
      v38[2] = 1;
      *(_QWORD *)v38 = 0;
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, &WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids);
      v39 = v61;
      v40 = v58;
      v41 = v60;
      v42 = *(HANDLE *)v20;
      RawBuffer = TokenHandle::GetRawBuffer((TokenHandle *)&v59);
      v44 = NtCreateLowBoxToken(RawBuffer, v42, 0x2000000, &v69, v41, v40, v39, 0, 0);
      v45 = NtStatusToHResult(v44);
      if ( v45 < 0 )
      {
        v106 = 0;
        v105 = &ComError::`vftable';
        v107 = v45;
        v108 = 1711;
        v109 = 1;
        throw (ComError *)&v105;
      }
      TokenHandle::operator=(&v62, &v59);
      TokenHandle::Decrement((TokenHandle *)&v59);
      v28 = v62;
      v10 = v68;
    }
    v29 = WPP_GLOBAL_Control;
LABEL_95:
    v46 = v61;
    v61 = 0;
    if ( v46 )
    {
      AppXFreeMemory(v46);
      v29 = WPP_GLOBAL_Control;
    }
    v47 = v60;
    v60 = 0;
    if ( v47 )
    {
      AppXFreeMemory(v47);
      v29 = WPP_GLOBAL_Control;
    }
    goto LABEL_99;
  }
  v29 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids);
      v29 = WPP_GLOBAL_Control;
    }
LABEL_99:
    if ( v29 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)v29 + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)v29 + 2), 73, &WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids);
  }
  v48 = operator new(0x10u);
  v68 = (void **)v48;
  *((_DWORD *)v48 + 2) = 1;
  *(_QWORD *)v48 = 0;
  v49 = (_QWORD *)((char *)v64 + 32);
  if ( *((_QWORD *)v64 + 7) > 7u )
    v49 = (_QWORD *)*v49;
  v50 = v121;
  if ( si128.m128i_i64[1] > 7uLL )
    v50 = (_QWORD *)v121[0];
  v51 = PsmAdjustActivationToken(*(_QWORD *)v28, *((unsigned int *)v64 + 16), 1, v50, v49, 0, v48);
  v52 = v51;
  if ( v51 == -1073741801 )
  {
    v53 = -2147024882;
  }
  else if ( (int)RtlNtStatusToDosErrorNoTeb(v51) > 0 )
  {
    v53 = (unsigned __int16)RtlNtStatusToDosErrorNoTeb(v52) | 0x80070000;
  }
  else
  {
    v53 = RtlNtStatusToDosErrorNoTeb(v52);
  }
  if ( v53 < 0 )
  {
    v111 = 0;
    v110 = &ComError::`vftable';
    v112 = v53;
    v113 = 1730;
    v114 = 1;
    throw (ComError *)&v110;
  }
  v54 = v74;
  if ( **(_QWORD **)v74 != *(_QWORD *)v48 )
  {
    TokenHandle::Decrement(v74);
    *(_QWORD *)v54 = v48;
    _InterlockedAdd((volatile signed __int32 *)v48 + 2, 1u);
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v48 + 2, 0xFFFFFFFF) == 1 )
  {
    if ( (unsigned __int64)(*(_QWORD *)v48 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(*(HANDLE *)v48);
      *(_QWORD *)v48 = 0;
    }
    operator delete(v48, 0x10u);
  }
  if ( _InterlockedExchangeAdd(v28 + 2, 0xFFFFFFFF) == 1 )
  {
    if ( (unsigned __int64)(*(_QWORD *)v28 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(*(HANDLE *)v28);
      *(_QWORD *)v28 = 0;
    }
    operator delete((void *)v28, 0x10u);
  }
  if ( si128.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>(v121[0], 2 * si128.m128i_i64[1] + 2);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v121[0]) = 0;
  SetThreadToken(0, *v67);
  TokenHandle::Decrement((TokenHandle *)&v67);
  if ( _InterlockedExchangeAdd(v20 + 2, 0xFFFFFFFF) == 1 )
  {
    if ( (unsigned __int64)(*(_QWORD *)v20 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(*(HANDLE *)v20);
      *(_QWORD *)v20 = 0;
    }
    operator delete((void *)v20, 0x10u);
  }
  CUserSession::DecrementRefCount(UserSession);
  v55 = (void **)v75;
  if ( _InterlockedExchangeAdd(*((volatile signed __int32 **)v75 + 1), 0xFFFFFFFF) == 1 )
  {
    operator delete(v55[1], 4u);
    operator delete(*v55, 0);
    v55[1] = 0;
    *v55 = 0;
  }
  if ( *v10 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)*v10 + 2, 0xFFFFFFFF) == 1 )
      operator delete(*v10, 0x10u);
    *v10 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18001a6fc  push    rbx
0x18001a6fe  push    rsi
0x18001a6ff  push    rdi
0x18001a700  push    r12
0x18001a702  push    r13
0x18001a704  push    r14
0x18001a706  push    r15
0x18001a708  sub     rsp, 480h
0x18001a70f  mov     rax, cs:__security_cookie
0x18001a716  xor     rax, rsp
0x18001a719  mov     [rsp+4B8h+var_40], rax
0x18001a721  mov     r10d, r9d
0x18001a724  mov     [rsp+4B8h+var_468], r9d
0x18001a729  mov     r11, r8
0x18001a72c  mov     [rsp+4B8h+var_430], r8
0x18001a734  mov     r14, rdx
0x18001a737  mov     [rsp+4B8h+var_3D0], rdx
0x18001a73f  mov     rsi, [rsp+4B8h+arg_38]
0x18001a747  mov     [rsp+4B8h+var_3D8], rsi
0x18001a74f  mov     [rsp+4B8h+var_3C0], rdx
0x18001a757  mov     rbx, [rsp+4B8h+arg_28]
0x18001a75f  mov     r15, [rsp+4B8h+arg_30]
0x18001a767  mov     [rsp+4B8h+var_410], r15
0x18001a76f  mov     [rsp+4B8h+var_3B8], r15
0x18001a777  mov     rax, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x18001a77e  mov     [rsp+4B8h+var_450], rax
0x18001a783  lea     rax, WPP_GLOBAL_Control
0x18001a78a  mov     rdx, cs:WPP_GLOBAL_Control
0x18001a791  mov     r13d, 1
0x18001a797  xor     r12d, r12d
0x18001a79a  cmp     rdx, rax
0x18001a79d  jz      short loc_18001A806
0x18001a79f  test    [rdx+1Ch], r13b
0x18001a7a3  jz      short loc_18001A806
0x18001a7a5  mov     r9, [r15]
0x18001a7a8  add     r9, 0Ch
0x18001a7ac  test    rbx, rbx
0x18001a7af  mov     r8d, r12d
0x18001a7b2  jz      short loc_18001A7B7
0x18001a7b4  mov     r8, [rbx]
0x18001a7b7  lea     rdi, aNo; "NO"
0x18001a7be  lea     rcx, aYes; "YES"
0x18001a7c5  mov     rax, rcx
0x18001a7c8  test    rbx, rbx
0x18001a7cb  cmovnz  rax, rdi
0x18001a7cf  test    r11, r11
0x18001a7d2  cmovz   rcx, rdi
0x18001a7d6  mov     [rsp+4B8h+var_470], r9
0x18001a7db  mov     [rsp+4B8h+var_478], r8
0x18001a7e0  mov     [rsp+4B8h+var_480], rax
0x18001a7e5  mov     eax, [rsp+4B8h+arg_20]
0x18001a7ec  mov     dword ptr [rsp+4B8h+var_488], eax
0x18001a7f0  mov     [rsp+4B8h+var_490], r10d
0x18001a7f5  mov     [rsp+4B8h+var_498], rcx
0x18001a7fa  mov     r9, [r14]
0x18001a7fd  mov     rcx, [rdx+10h]
0x18001a801  call    WPP_SF__sid_SdLSiS
0x18001a806  mov     rax, [rsi]
0x18001a809  mov     edi, 10h
0x18001a80e  cmp     [rax], r12
0x18001a811  jz      short loc_18001A83E
0x18001a813  mov     ecx, edi; dwBytes
0x18001a815  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a81a  mov     [rsp+4B8h+var_458], rax
0x18001a81f  mov     [rax+8], r13d
0x18001a823  mov     [rax], r12
0x18001a826  lea     rdx, [rsp+4B8h+var_458]
0x18001a82b  mov     rcx, rsi
0x18001a82e  call    ??4TokenHandle@@QEAAAEAV0@AEBV0@@Z; TokenHandle::operator=(TokenHandle const &)
0x18001a833  lea     rcx, [rsp+4B8h+var_458]; this
0x18001a838  call    ?Decrement@TokenHandle@@AEAAXXZ; TokenHandle::Decrement(void)
0x18001a83d  nop
0x18001a83e  mov     rax, [r15]
0x18001a841  cmp     [rax], r12
0x18001a844  jbe     loc_18001A93C
0x18001a84a  mov     rcx, rdi; dwBytes
0x18001a84d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a852  mov     [rsp+4B8h+var_458], rax
0x18001a857  mov     [rax+8], r13d
0x18001a85b  mov     [rax], r12
0x18001a85e  mov     rcx, [r15]
0x18001a861  add     rcx, 0Ch; unsigned __int16 *
0x18001a865  lea     rdx, [rsp+4B8h+var_458]; struct TokenHandle *
0x18001a86a  call    ?CreateServiceToken@ServiceUserTokenHelper@@SAJPEBGPEAVTokenHandle@@@Z; ServiceUserTokenHelper::CreateServiceToken(ushort const *,TokenHandle *)
0x18001a86f  test    eax, eax
0x18001a871  jns     short loc_18001A8BB
0x18001a873  xorps   xmm0, xmm0
0x18001a876  movups  [rsp+4B8h+var_390], xmm0
0x18001a87e  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18001a885  mov     [rsp+4B8h+pExceptionObject], rcx
0x18001a88d  mov     [rsp+4B8h+var_380], eax
0x18001a894  mov     [rsp+4B8h+var_37C], 628h
0x18001a89f  mov     [rsp+4B8h+var_378], r13d
0x18001a8a7  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18001a8ae  lea     rcx, [rsp+4B8h+pExceptionObject]; pExceptionObject
0x18001a8b6  call    _CxxThrowException_0
0x18001a8bb  mov     rcx, [rsi]
0x18001a8be  mov     rbx, [rsp+4B8h+var_458]
0x18001a8c3  mov     rax, [rbx]
0x18001a8c6  cmp     [rcx], rax
0x18001a8c9  jz      short loc_18001A8DB
0x18001a8cb  mov     rcx, rsi; this
0x18001a8ce  call    ?Decrement@TokenHandle@@AEAAXXZ; TokenHandle::Decrement(void)
0x18001a8d3  mov     [rsi], rbx
0x18001a8d6  lock add [rbx+8], r13d
0x18001a8db  or      esi, 0FFFFFFFFh
0x18001a8de  mov     eax, esi
0x18001a8e0  lock xadd [rbx+8], eax
0x18001a8e5  add     eax, esi
0x18001a8e7  jnz     short loc_18001A90B
0x18001a8e9  mov     rcx, [rbx]; hObject
0x18001a8ec  lea     rax, [rcx-1]
0x18001a8f0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001a8f4  ja      short loc_18001A8FF
0x18001a8f6  call    cs:__imp_CloseHandle
0x18001a8fc  mov     [rbx], r12
0x18001a8ff  mov     rdx, rdi; unsigned __int64
0x18001a902  mov     rcx, rbx; void *
0x18001a905  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001a90a  nop
0x18001a90b  mov     rcx, r14; this
0x18001a90e  call    ??1SidHandle@@QEAA@XZ; SidHandle::~SidHandle(void)
0x18001a913  nop
0x18001a914  mov     rcx, [r15]
0x18001a917  test    rcx, rcx
0x18001a91a  jz      short loc_18001A935
0x18001a91c  mov     eax, esi
0x18001a91e  lock xadd [rcx+8], eax
0x18001a923  add     eax, esi
0x18001a925  jnz     short loc_18001A932
0x18001a927  mov     rdx, rdi; unsigned __int64
0x18001a92a  mov     rcx, [r15]; void *
0x18001a92d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001a932  mov     [r15], r12
0x18001a935  xor     eax, eax
0x18001a937  jmp     loc_18001B42B
0x18001a93c  mov     rax, [r14]
0x18001a93f  mov     [rsp+4B8h+var_440], rax
0x18001a944  mov     rax, [r14+8]
0x18001a948  mov     [rsp+4B8h+var_438], rax
0x18001a950  lock add [rax], r13d
0x18001a954  mov     rcx, [rsp+4B8h+var_450]
0x18001a959  add     rcx, 310h
0x18001a960  mov     r8, rbx
0x18001a963  lea     rdx, [rsp+4B8h+var_440]
0x18001a968  call    ?FindUserSession@CLoggedOnUsers@@QEAAPEAVCUserSession@@VSidHandle@@PEA_K@Z; CLoggedOnUsers::FindUserSession(SidHandle,unsigned __int64 *)
0x18001a96d  mov     [rsp+4B8h+var_428], rax
0x18001a975  test    rax, rax
0x18001a978  jnz     short loc_18001A9C4
0x18001a97a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a981  lea     rax, WPP_GLOBAL_Control
0x18001a988  cmp     rcx, rax
0x18001a98b  jz      short loc_18001A9A9
0x18001a98d  test    byte ptr [rcx+1Ch], 4
0x18001a991  jz      short loc_18001A9A9
0x18001a993  mov     edx, 3Dh ; '='
0x18001a998  lea     r8, WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids
0x18001a99f  mov     rcx, [rcx+10h]
0x18001a9a3  call    WPP_SF_
0x18001a9a8  nop
0x18001a9a9  mov     rcx, r14; this
0x18001a9ac  call    ??1SidHandle@@QEAA@XZ; SidHandle::~SidHandle(void)
0x18001a9b1  nop
0x18001a9b2  mov     rcx, r15
0x18001a9b5  call    ?FreeIt@?$GenericStringHandle@G@@AEAAXXZ; GenericStringHandle<ushort>::FreeIt(void)
0x18001a9ba  mov     eax, 800704DDh
0x18001a9bf  jmp     loc_18001B42B
0x18001a9c4  lea     rax, [rsp+4B8h+var_428]
0x18001a9cc  mov     [rsp+4B8h+var_3B0], rax
0x18001a9d4  mov     [rsp+4B8h+var_3A8], r13b
0x18001a9dc  mov     rcx, rdi; dwBytes
0x18001a9df  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a9e4  mov     rdi, rax
0x18001a9e7  mov     [rsp+4B8h+var_420], rax
0x18001a9ef  mov     [rax+8], r13d
0x18001a9f3  mov     [rax], r12
0x18001a9f6  mov     r9, rax; void **
0x18001a9f9  mov     r8d, [rsp+4B8h+arg_20]; unsigned int
0x18001aa01  mov     edx, [rsp+4B8h+var_468]; int
0x18001aa05  mov     rcx, [rsp+4B8h+var_428]; this
0x18001aa0d  call    ?CopyToken@CUserSession@@QEAAJHKPEAPEAX@Z; CUserSession::CopyToken(int,ulong,void * *)
0x18001aa12  test    eax, eax
0x18001aa14  jns     short loc_18001AA5E
0x18001aa16  xorps   xmm0, xmm0
0x18001aa19  movups  [rsp+4B8h+var_330], xmm0
0x18001aa21  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18001aa28  mov     [rsp+4B8h+var_338], rcx
0x18001aa30  mov     [rsp+4B8h+var_320], eax
0x18001aa37  mov     [rsp+4B8h+var_31C], 63Eh
0x18001aa42  mov     [rsp+4B8h+var_318], r13d
0x18001aa4a  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18001aa51  lea     rcx, [rsp+4B8h+var_338]; pExceptionObject
0x18001aa59  call    _CxxThrowException_0
0x18001aa5e  mov     rbx, [rsp+4B8h+var_430]
0x18001aa66  test    rbx, rbx
0x18001aa69  jnz     short loc_18001AADC
0x18001aa6b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aa72  lea     rax, WPP_GLOBAL_Control
0x18001aa79  cmp     rcx, rax
0x18001aa7c  jz      short loc_18001AA97
0x18001aa7e  test    [rcx+1Ch], r13b
0x18001aa82  jz      short loc_18001AA97
0x18001aa84  lea     edx, [rbx+3Eh]
0x18001aa87  lea     r8, WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids
0x18001aa8e  mov     rcx, [rcx+10h]
0x18001aa92  call    WPP_SF_
0x18001aa97  lea     rdx, [rsp+4B8h+var_420]
0x18001aa9f  mov     rcx, rsi
0x18001aaa2  call    ??4TokenHandle@@QEAAAEAV0@AEBV0@@Z; TokenHandle::operator=(TokenHandle const &)
0x18001aaa7  nop
0x18001aaa8  lea     rcx, [rsp+4B8h+var_420]; this
0x18001aab0  call    ?Decrement@TokenHandle@@AEAAXXZ; TokenHandle::Decrement(void)
0x18001aab5  nop
0x18001aab6  mov     rcx, [rsp+4B8h+var_428]; this
0x18001aabe  call    ?DecrementRefCount@CUserSession@@QEAAJXZ; CUserSession::DecrementRefCount(void)
0x18001aac3  nop
0x18001aac4  mov     rcx, r14; this
0x18001aac7  call    ??1SidHandle@@QEAA@XZ; SidHandle::~SidHandle(void)
0x18001aacc  nop
0x18001aacd  mov     rcx, r15
0x18001aad0  call    ?FreeIt@?$GenericStringHandle@G@@AEAAXXZ; GenericStringHandle<ushort>::FreeIt(void)
0x18001aad5  xor     eax, eax
0x18001aad7  jmp     loc_18001B42B
0x18001aadc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aae3  lea     rax, WPP_GLOBAL_Control
0x18001aaea  cmp     rcx, rax
0x18001aaed  jz      short loc_18001AB0F
0x18001aaef  test    [rcx+1Ch], r13b
0x18001aaf3  jz      short loc_18001AB0F
0x18001aaf5  mov     edx, 3Fh ; '?'
0x18001aafa  lea     rsi, WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids
0x18001ab01  mov     r8, rsi
0x18001ab04  mov     rcx, [rcx+10h]
0x18001ab08  call    WPP_SF_
0x18001ab0d  jmp     short loc_18001AB16
0x18001ab0f  lea     rsi, WPP_edc275ac94ff3ff596a452e9d8bd5b7d_Traceguids
0x18001ab16  mov     rcx, rbx; this
0x18001ab19  call    ?Dump@AppPackageInfo@@QEBAXXZ; AppPackageInfo::Dump(void)
0x18001ab1e  lea     rcx, [rsp+4B8h+var_418]; this
0x18001ab26  call    ??0CSaveThreadToken@@QEAA@XZ; CSaveThreadToken::CSaveThreadToken(void)
0x18001ab2b  nop
0x18001ab2c  call    cs:__imp_RevertToSelf
0x18001ab32  test    eax, eax
0x18001ab34  jnz     short loc_18001AB9E
0x18001ab36  call    cs:__imp_GetLastError
0x18001ab3c  test    eax, eax
0x18001ab3e  jg      short loc_18001AB48
0x18001ab40  call    cs:__imp_GetLastError
0x18001ab46  jmp     short loc_18001AB56
0x18001ab48  call    cs:__imp_GetLastError
0x18001ab4e  movzx   eax, ax
0x18001ab51  or      eax, 80070000h
0x18001ab56  xorps   xmm0, xmm0
0x18001ab59  movups  [rsp+4B8h+var_2D0], xmm0
0x18001ab61  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18001ab68  mov     [rsp+4B8h+var_2D8], rcx
0x18001ab70  mov     [rsp+4B8h+var_2C0], eax
0x18001ab77  mov     [rsp+4B8h+var_2BC], 65Bh
0x18001ab82  mov     [rsp+4B8h+var_2B8], r13d
0x18001ab8a  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18001ab91  lea     rcx, [rsp+4B8h+var_2D8]; pExceptionObject
0x18001ab99  call    _CxxThrowException_0
0x18001ab9e  call    IsAppXGetPackageCapabilitiesPresent
0x18001aba3  mov     [rsp+4B8h+var_464], al
0x18001aba7  call    IsAppXGetPackageCapabilitiesPresent
0x18001abac  mov     bl, al
0x18001abae  call    IsPsmAdjustActivationTokenPresent
0x18001abb3  mov     dl, [rsp+4B8h+var_464]
0x18001abb7  test    dl, dl
0x18001abb9  jz      loc_18001B372
0x18001abbf  test    bl, bl
0x18001abc1  jz      loc_18001B372
0x18001abc7  test    al, al
0x18001abc9  jz      loc_18001B372
0x18001abcf  mov     rax, [rsp+4B8h+var_430]
0x18001abd7  cmp     qword ptr [rax+18h], 7
0x18001abdc  jbe     short loc_18001ABE3
0x18001abde  mov     r9, [rax]
0x18001abe1  jmp     short loc_18001ABE6
0x18001abe3  mov     r9, rax
0x18001abe6  mov     rax, [r14]
0x18001abe9  mov     [rsp+4B8h+var_440], rax
0x18001abee  mov     rax, [r14+8]
0x18001abf2  mov     [rsp+4B8h+var_438], rax
0x18001abfa  lock add [rax], r13d
0x18001abfe  lea     r8, [rsp+4B8h+var_440]
0x18001ac03  lea     rdx, [rsp+4B8h+var_60]
0x18001ac0b  mov     rcx, [rsp+4B8h+var_450]
0x18001ac10  call    ?GetPackageFullNameFromPackageFamilyName@CJobManager@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VSidHandle@@PEBG@Z; CJobManager::GetPackageFullNameFromPackageFamilyName(SidHandle,ushort const *)
0x18001ac15  nop
0x18001ac16  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ac1d  lea     rax, WPP_GLOBAL_Control
0x18001ac24  cmp     rcx, rax
0x18001ac27  jz      short loc_18001AC5A
0x18001ac29  test    [rcx+1Ch], r13b
0x18001ac2d  jz      short loc_18001AC5A
0x18001ac2f  lea     r9, [rsp+4B8h+var_60]
0x18001ac37  cmp     [rsp+4B8h+var_48], 7
0x18001ac40  cmova   r9, [rsp+4B8h+var_60]
0x18001ac49  mov     edx, 41h ; 'A'
  ... truncated ...
```
