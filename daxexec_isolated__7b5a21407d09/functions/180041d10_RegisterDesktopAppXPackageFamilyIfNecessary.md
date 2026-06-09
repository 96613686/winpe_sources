# RegisterDesktopAppXPackageFamilyIfNecessary

- ea: `0x180041d10`
- end: `0x18004250c`
- name: `RegisterDesktopAppXPackageFamilyIfNecessary`
- size: `2044`
- prototype: `__int64 __fastcall(unsigned __int16 *, int, UINT32 *, WCHAR *, int *)`
- caller_count: `0`
- callee_count: `27`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800016e4`
- `0x180004f70`
- `0x1800059a8`
- `0x180007bdc`
- `0x18000e074`
- `0x18000ff24`
- `0x180011e9c`
- `0x1800125f4`
- `0x180012fb8`
- `0x180013510`
- `0x180014e74`
- `0x180016434`
- `0x1800164f8`
- `0x180016b18`
- `0x180016b98`
- `0x180018fc0`
- `0x1800190e0`
- `0x18001f6a0`
- `0x180039efc`
- `0x18003c4a0`
- `0x18003f050`
- `0x180040478`
- `0x180040628`
- `0x180040718`
- `0x180041ce0`
- `0x180041d10`
- `0x18009db10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800420db`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800420db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800420bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800420bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800420cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800421b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800420cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800421b0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180041db3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180041e0f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180041e38`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800423c3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180041db3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180041e0f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180041e38`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800423c3`
- `api-ms-win-appmodel-runtime-l1-1-1!FindPackagesByPackageFamily` at `0x180041ead`
- `api-ms-win-appmodel-runtime-l1-1-1!FindPackagesByPackageFamily` at `0x18004224c`
- `api-ms-win-appmodel-runtime-l1-1-1!FindPackagesByPackageFamily` at `0x180041ead`
- `api-ms-win-appmodel-runtime-l1-1-1!FindPackagesByPackageFamily` at `0x18004224c`
- `api-ms-win-appmodel-runtime-internal-l1-1-2!GetEffectivePackageStatusForUser` at `0x180041ee6`
- `api-ms-win-appmodel-runtime-internal-l1-1-2!GetEffectivePackageStatusForUser` at `0x180041ee6`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!GetPackageStatus` at `0x180041fd8`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!GetPackageStatus` at `0x180041fd8`
- `ext-ms-win-appxdeploymentclient-appxdeploy-l1-1-1!CheckForUpdatesAndWaitForInstallerIfNeeded` at `0x180042082`
- `ext-ms-win-appxdeploymentclient-appxdeploy-l1-1-1!CheckForUpdatesAndWaitForInstallerIfNeeded` at `0x180042082`

## string_xrefs

- `0x180042009`: `AppInstallerPromptForUpdate`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall RegisterDesktopAppXPackageFamilyIfNecessary(
        unsigned __int16 *a1,
        int a2,
        UINT32 *a3,
        WCHAR *a4,
        int *a5)
{
  WCHAR *v5; // r15
  int *v9; // r12
  int v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // r9
  __int64 v13; // rcx
  __int64 result; // rax
  int v15; // eax
  unsigned int v16; // ebx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // r14
  unsigned int PackagesByPackageFamily; // eax
  bool v21; // bl
  unsigned int EffectivePackageStatusForUser; // eax
  __int64 v23; // rdx
  _DWORD *v24; // rcx
  int v25; // r9d
  int v26; // eax
  int v27; // esi
  int v28; // eax
  __int64 v29; // r12
  _QWORD *v30; // rdi
  void *v31; // rsi
  DWORD LastError; // ebx
  WCHAR *v33; // rdx
  WCHAR *v34; // r8
  const char *v35; // r9
  __int64 v36; // rdi
  _WORD *v37; // rcx
  __int64 v38; // rax
  WCHAR *v39; // rdx
  WCHAR v40; // r9
  __int64 v41; // rbx
  __int64 v42; // rax
  unsigned int v43; // eax
  unsigned __int64 v44; // rdx
  WCHAR *v45; // rax
  WCHAR v46; // cx
  WCHAR *v47; // rcx
  __int64 v48; // rcx
  unsigned int v49; // eax
  int bufferLength; // [rsp+20h] [rbp-318h]
  int *bufferLengtha; // [rsp+20h] [rbp-318h]
  int v52; // [rsp+40h] [rbp-2F8h] BYREF
  int v53; // [rsp+44h] [rbp-2F4h] BYREF
  UINT32 count; // [rsp+48h] [rbp-2F0h] BYREF
  UINT32 v55; // [rsp+4Ch] [rbp-2ECh] BYREF
  __int64 v56; // [rsp+50h] [rbp-2E8h] BYREF
  PWSTR packageFullNames; // [rsp+58h] [rbp-2E0h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-2D8h] BYREF
  int v59[2]; // [rsp+68h] [rbp-2D0h] BYREF
  __int64 v60; // [rsp+70h] [rbp-2C8h] BYREF
  __int128 v61; // [rsp+78h] [rbp-2C0h] BYREF
  __int128 v62; // [rsp+88h] [rbp-2B0h]
  _QWORD v63[34]; // [rsp+A0h] [rbp-298h] BYREF
  __int64 v64; // [rsp+1B0h] [rbp-188h]
  WCHAR buffer[128]; // [rsp+1F0h] [rbp-148h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+338h] [rbp+0h]

  try
  {
    v5 = a4;
    v9 = a5;
    *(_QWORD *)v59 = a5;
    if ( (a4 != 0) != (a3 != 0) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x159,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
        (const char *)0x80070057LL,
        bufferLength);
    v56 = 0;
    v10 = StateRepository::Cache::Manager_NoThrow::Open((StateRepository::Cache::Manager_NoThrow *)&v56);
    v11 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x15F,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
        (const char *)(unsigned int)v10,
        bufferLength);
      v13 = v56;
      v56 = 0;
      if ( v13 )
        SRCacheManager_Close();
      return v11;
    }
    v60 = 0;
    v15 = StateRepository::Cache::Entity::PackageFamily_NoThrow::GetByPackageFamilyName(
            (struct StateRepository::Cache::Manager_NoThrow *)&v56,
            a1,
            &v60);
    v16 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x161,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
        (const char *)(unsigned int)v15,
        bufferLength);
      v17 = v56;
      v56 = 0;
      if ( v17 )
        SRCacheManager_Close();
      return v16;
    }
    if ( !v60 )
    {
      v18 = v56;
      v56 = 0;
      if ( v18 )
        SRCacheManager_Close();
      return 2147958001LL;
    }
    packageFullNames = 0;
    count = 1;
    memset_0(buffer, 0, sizeof(buffer));
    v19 = 128;
    v55 = 128;
    PackagesByPackageFamily = FindPackagesByPackageFamily(a1, 0x20010u, &count, &packageFullNames, &v55, buffer, 0);
    if ( PackagesByPackageFamily )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x16F,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
        (const char *)PackagesByPackageFamily,
        (unsigned int)bufferLengtha);
    v21 = 0;
    if ( count )
    {
      v53 = 0;
      EffectivePackageStatusForUser = GetEffectivePackageStatusForUser(0, packageFullNames, &v53);
      if ( EffectivePackageStatusForUser != 1168 )
      {
        if ( EffectivePackageStatusForUser )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x184,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
            (const char *)EffectivePackageStatusForUser,
            (unsigned int)bufferLengtha);
        if ( (v53 & 0x400800) == 0 )
        {
          if ( !a2 || (v52 = 0, (unsigned int)GetPackageStatus(packageFullNames, &v52)) )
          {
            v27 = 0;
          }
          else
          {
            v27 = 0;
            if ( (v52 & 0x20000) != 0 && (unsigned __int8)IsCheckForUpdatesAndWaitForInstallerIfNeededPresent() )
            {
              wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
                v63,
                "AppInstallerPromptForUpdate");
              v63[0] = &DesktopAppXProvider::AppInstallerPromptForUpdate::`vftable';
              DesktopAppXProvider::AppInstallerPromptForUpdate::StartActivity(
                (DesktopAppXProvider::AppInstallerPromptForUpdate *)v63,
                a1);
              pv = 0;
              v52 = 0;
              v53 = 0;
              *(_QWORD *)&v61 = &pv;
              *((_QWORD *)&v61 + 1) = 0;
              LOBYTE(v62) = 1;
              bufferLengtha = &v53;
              v28 = CheckForUpdatesAndWaitForInstallerIfNeeded(packageFullNames, 0, (char *)&v61 + 8, &v52);
              if ( v28 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x1CA,
                  (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
                  (const char *)(unsigned int)v28,
                  (int)&v53);
              if ( (_BYTE)v62 )
              {
                v29 = *((_QWORD *)&v61 + 1);
                v30 = (_QWORD *)v61;
                v31 = *(void **)v61;
                if ( *(_QWORD *)v61 )
                {
                  LastError = GetLastError();
                  CoTaskMemFree(v31);
                  SetLastError(LastError);
                }
                *v30 = v29;
                v9 = *(int **)v59;
              }
              DesktopAppXProvider::AppInstallerPromptForUpdate::Stop(
                (DesktopAppXProvider::AppInstallerPromptForUpdate *)v63,
                v52 != 0,
                v53 != 0);
              v36 = 2147483646;
              v37 = pv;
              if ( v53 )
              {
                v38 = 2147483646;
                v39 = (WCHAR *)pv;
                v34 = buffer;
                do
                {
                  if ( !v38 )
                    break;
                  v40 = *v39;
                  if ( !*v39 )
                    break;
                  ++v39;
                  *v34++ = v40;
                  --v38;
                  --v19;
                }
                while ( v19 );
                v35 = v19 == 0 ? (const char *)0x8007007ALL : 0LL;
                v33 = v34 - 1;
                if ( v19 )
                  v33 = v34;
                *v33 = 0;
                if ( !v19 )
                  wil::details::in1diag3::Throw_Hr(
                    retaddr,
                    (void *)0x1D3,
                    (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
                    v35,
                    (int)&v53);
                v41 = -1;
                v42 = -1;
                do
                  ++v42;
                while ( v37[v42] );
                v55 = v42 + 1;
                v27 = 1;
              }
              else
              {
                v27 = 0;
                v41 = -1;
              }
              if ( v37 )
                CoTaskMemFree(v37);
              v63[0] = &DesktopAppXProvider::AppInstallerPromptForUpdate::`vftable';
              wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(
                v63,
                v33,
                v34,
                v35);
              wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v63);
              goto LABEL_58;
            }
          }
          v41 = -1;
LABEL_57:
          v36 = 2147483646;
LABEL_58:
          if ( !packageFullNames )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x1D8,
              (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
              (const char *)0x8000FFFFLL,
              (int)bufferLengtha);
          v61 = 0;
          v62 = 0;
          do
            ++v41;
          while ( packageFullNames[v41] );
          std::wstring::_Construct<1,unsigned short const *>(&v61, packageFullNames, v41);
          CompleteCustomInstallIfNeeded((unsigned __int16 *)&v61);
          std::wstring::~wstring(&v61);
          if ( a3 && v5 )
          {
            v44 = *a3;
            if ( *a3 )
            {
              if ( v44 <= 0x7FFFFFFF )
              {
                v45 = buffer;
                do
                {
                  if ( !v36 )
                    break;
                  v46 = *v45;
                  if ( !*v45 )
                    break;
                  ++v45;
                  *v5++ = v46;
                  --v36;
                  --v44;
                }
                while ( v44 );
                v47 = v5 - 1;
                if ( v44 )
                  v47 = v5;
                *v47 = 0;
                v12 = v44 == 0 ? 0x8007007A : 0;
              }
              else
              {
                v12 = 2147942487LL;
                *v5 = 0;
              }
            }
            else
            {
              v12 = 2147942487LL;
            }
            if ( (int)v12 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x1DE,
                (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
                (const char *)v12,
                (int)bufferLengtha);
            *a3 = v55;
          }
          if ( v9 )
            *v9 = v27;
          v48 = v56;
          v56 = 0;
          if ( v48 )
            SRCacheManager_Close();
          return 0;
        }
        v21 = (v53 & 0x8000) != 0;
      }
    }
    wil::ActivityBase<DesktopAppXProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopAppXProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(
      v63,
      "PreActivationPackageRegistration");
    v63[0] = &DesktopAppXProvider::PreActivationPackageRegistration::`vftable';
    DesktopAppXProvider::PreActivationPackageRegistration::StartActivity(
      (DesktopAppXProvider::PreActivationPackageRegistration *)v63,
      a1);
    v23 = 0xFFFFFFFFLL;
    if ( v21 )
    {
      v24 = (_DWORD *)*((_QWORD *)DesktopAppXProvider::Instance() + 1);
      if ( *v24 > 5u )
      {
        *(_QWORD *)v59 = packageFullNames;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (_DWORD)v24,
          (unsigned int)&byte_1800E5907,
          v64 + 8,
          v25,
          (__int64)v59);
      }
      v23 = 0;
    }
    v52 = 0;
    v26 = RegisterDesktopAppXPackageFamily(a1, v23, &v52);
    if ( v26 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1A6,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
        (const char *)(unsigned int)v26,
        (int)bufferLengtha);
    if ( v21 )
    {
      v52 = -2147009280;
      DesktopAppXProvider::PreActivationPackageRegistration::InplaceFastUnwind<unsigned short * &,long &>(
        v63,
        &packageFullNames,
        &v52);
      v49 = wil::verify_hresult(2147958016LL);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1AB,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
        (const char *)v49,
        (int)bufferLengtha);
    }
    wil::ActivityBase<DesktopAppXProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v63);
    v55 = 128;
    count = 1;
    v43 = FindPackagesByPackageFamily(a1, 0x20010u, &count, &packageFullNames, &v55, buffer, 0);
    if ( v43 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x1B4,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
        (const char *)v43,
        (unsigned int)bufferLengtha);
    if ( !count )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1B7,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
        (const char *)0x80073CF1LL,
        (int)bufferLengtha);
    v63[0] = &DesktopAppXProvider::PreActivationPackageRegistration::`vftable';
    wil::ActivityBase<DesktopAppXProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v63);
    wil::ActivityBase<DesktopAppXProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DesktopAppXProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(v63);
    v27 = 1;
    v41 = -1;
    goto LABEL_57;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1E8,
                           (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
                           (const char *)v12);
  }
  return result;
}

```

## disassembly

```asm
0x180041d10  push    rbx
0x180041d12  push    rsi
0x180041d13  push    rdi
0x180041d14  push    r12
0x180041d16  push    r13
0x180041d18  push    r14
0x180041d1a  push    r15
0x180041d1c  sub     rsp, 300h
0x180041d23  mov     rax, cs:__security_cookie
0x180041d2a  xor     rax, rsp
0x180041d2d  mov     [rsp+338h+var_48], rax
0x180041d35  mov     r15, r9
0x180041d38  mov     r13, r8
0x180041d3b  mov     esi, edx
0x180041d3d  mov     rdi, rcx
0x180041d40  mov     r12, [rsp+338h+arg_20]
0x180041d48  mov     qword ptr [rsp+338h+var_2D0], r12
0x180041d4d  xor     r14d, r14d
0x180041d50  mov     edx, r14d
0x180041d53  test    r9, r9
0x180041d56  setnz   dl
0x180041d59  mov     eax, r14d
0x180041d5c  test    r8, r8
0x180041d5f  setnz   al
0x180041d62  mov     rcx, [rsp+338h]; this
0x180041d6a  cmp     edx, eax
0x180041d6c  jnz     loc_1800423FB
0x180041d72  mov     [rsp+338h+var_2E8], r14
0x180041d77  lea     rcx, [rsp+338h+var_2E8]; this
0x180041d7c  call    ?Open@Manager_NoThrow@Cache@StateRepository@@QEAAJXZ; StateRepository::Cache::Manager_NoThrow::Open(void)
0x180041d81  mov     ebx, eax
0x180041d83  test    eax, eax
0x180041d85  jns     short loc_180041DC6
0x180041d87  mov     rcx, [rsp+338h]; this
0x180041d8f  mov     r9d, eax; char *
0x180041d92  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appmodel\\execmodel\\des"...
0x180041d99  mov     edx, 15Fh; void *
0x180041d9e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041da3  nop
0x180041da4  mov     rcx, [rsp+338h+var_2E8]
0x180041da9  mov     [rsp+338h+var_2E8], r14
0x180041dae  test    rcx, rcx
0x180041db1  jz      short loc_180041DBF
0x180041db3  call    cs:__imp_SRCacheManager_Close
0x180041dba  nop     dword ptr [rax+rax+00h]
0x180041dbf  mov     eax, ebx
0x180041dc1  jmp     loc_1800423D7
0x180041dc6  mov     [rsp+338h+var_2C8], r14
0x180041dcb  lea     r8, [rsp+338h+var_2C8]; __int64 *
0x180041dd0  mov     rdx, rdi; unsigned __int16 *
0x180041dd3  lea     rcx, [rsp+338h+var_2E8]; struct StateRepository::Cache::Manager_NoThrow *
0x180041dd8  call    ?GetByPackageFamilyName@PackageFamily_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::PackageFamily_NoThrow::GetByPackageFamilyName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x180041ddd  mov     ebx, eax
0x180041ddf  test    eax, eax
0x180041de1  jns     short loc_180041E22
0x180041de3  mov     rcx, [rsp+338h]; this
0x180041deb  mov     r9d, eax; char *
0x180041dee  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appmodel\\execmodel\\des"...
0x180041df5  mov     edx, 161h; void *
0x180041dfa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041dff  nop
0x180041e00  mov     rcx, [rsp+338h+var_2E8]
0x180041e05  mov     [rsp+338h+var_2E8], r14
0x180041e0a  test    rcx, rcx
0x180041e0d  jz      short loc_180041E1B
0x180041e0f  call    cs:__imp_SRCacheManager_Close
0x180041e16  nop     dword ptr [rax+rax+00h]
0x180041e1b  mov     eax, ebx
0x180041e1d  jmp     loc_1800423D7
0x180041e22  cmp     [rsp+338h+var_2C8], r14
0x180041e27  jnz     short loc_180041E4E
0x180041e29  mov     rcx, [rsp+338h+var_2E8]
0x180041e2e  mov     [rsp+338h+var_2E8], r14
0x180041e33  test    rcx, rcx
0x180041e36  jz      short loc_180041E44
0x180041e38  call    cs:__imp_SRCacheManager_Close
0x180041e3f  nop     dword ptr [rax+rax+00h]
0x180041e44  mov     eax, 80073CF1h
0x180041e49  jmp     loc_1800423D7
0x180041e4e  mov     [rsp+338h+packageFullNames], r14
0x180041e53  mov     [rsp+338h+count], 1
0x180041e5b  xor     edx, edx; Val
0x180041e5d  mov     r8d, 100h; Size
0x180041e63  lea     rcx, [rsp+338h+var_148]; void *
0x180041e6b  call    memset_0
0x180041e70  mov     r14d, 80h
0x180041e76  mov     [rsp+338h+var_2EC], r14d
0x180041e7b  mov     [rsp+338h+packageProperties], 0; packageProperties
0x180041e84  lea     rax, [rsp+338h+var_148]
0x180041e8c  mov     [rsp+338h+buffer], rax; buffer
0x180041e91  lea     rax, [rsp+338h+var_2EC]
0x180041e96  mov     [rsp+338h+bufferLength], rax; unsigned int
0x180041e9b  lea     r9, [rsp+338h+packageFullNames]; packageFullNames
0x180041ea0  lea     r8, [rsp+338h+count]; count
0x180041ea5  mov     edx, 20010h; packageFilters
0x180041eaa  mov     rcx, rdi; packageFamilyName
0x180041ead  call    cs:__imp_FindPackagesByPackageFamily
0x180041eb4  nop     dword ptr [rax+rax+00h]
0x180041eb9  mov     rcx, [rsp+338h]; this
0x180041ec1  test    eax, eax
0x180041ec3  jnz     loc_180042413
0x180041ec9  xor     bl, bl
0x180041ecb  cmp     [rsp+338h+count], 0
0x180041ed0  jz      short loc_180041F1F
0x180041ed2  mov     [rsp+338h+var_2F4], 0
0x180041eda  lea     r8, [rsp+338h+var_2F4]
0x180041edf  mov     rdx, [rsp+338h+packageFullNames]
0x180041ee4  xor     ecx, ecx
0x180041ee6  call    cs:__imp_GetEffectivePackageStatusForUser
0x180041eed  nop     dword ptr [rax+rax+00h]
0x180041ef2  cmp     eax, 490h
0x180041ef7  jz      short loc_180041F1F
0x180041ef9  mov     rcx, [rsp+338h]; this
0x180041f01  test    eax, eax
0x180041f03  jnz     loc_180042427
0x180041f09  mov     ebx, [rsp+338h+var_2F4]
0x180041f0d  test    ebx, 400800h
0x180041f13  jz      loc_180041FC0
0x180041f19  shr     ebx, 0Fh
0x180041f1c  and     bl, 1
0x180041f1f  lea     rdx, aPreactivationp; "PreActivationPackageRegistration"
0x180041f26  lea     rcx, [rsp+338h+var_298]
0x180041f2e  call    ??0?$ActivityBase@VDesktopAppXProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<DesktopAppXProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopAppXProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180041f33  lea     rax, ??_7PreActivationPackageRegistration@DesktopAppXProvider@@6B@; const DesktopAppXProvider::PreActivationPackageRegistration::`vftable'
0x180041f3a  mov     [rsp+338h+var_298], rax
0x180041f42  mov     rdx, rdi; unsigned __int16 *
0x180041f45  lea     rcx, [rsp+338h+var_298]; this
0x180041f4d  call    ?StartActivity@PreActivationPackageRegistration@DesktopAppXProvider@@QEAAXPEBG@Z; DesktopAppXProvider::PreActivationPackageRegistration::StartActivity(ushort const *)
0x180041f52  nop
0x180041f53  or      edx, 0FFFFFFFFh
0x180041f56  xor     esi, esi
0x180041f58  test    bl, bl
0x180041f5a  jz      short loc_180041F9A
0x180041f5c  call    ?Instance@DesktopAppXProvider@@KAPEAV1@XZ; DesktopAppXProvider::Instance(void)
0x180041f61  mov     rcx, [rax+8]
0x180041f65  mov     eax, [rcx]
0x180041f67  cmp     eax, 5
0x180041f6a  jbe     short loc_180041F98
0x180041f6c  mov     rax, [rsp+338h+packageFullNames]
0x180041f71  mov     qword ptr [rsp+338h+var_2D0], rax
0x180041f76  mov     r8, [rsp+338h+var_188]
0x180041f7e  add     r8, 8
0x180041f82  lea     rax, [rsp+338h+var_2D0]
0x180041f87  mov     [rsp+338h+bufferLength], rax; int
0x180041f8c  lea     rdx, byte_1800E5907
0x180041f93  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180041f98  mov     edx, esi
0x180041f9a  mov     [rsp+338h+var_2F8], esi
0x180041f9e  lea     r8, [rsp+338h+var_2F8]
0x180041fa3  mov     rcx, rdi
0x180041fa6  call    RegisterDesktopAppXPackageFamily
0x180041fab  mov     rcx, [rsp+338h]; this
0x180041fb3  test    eax, eax
0x180041fb5  js      loc_18004243C
0x180041fbb  jmp     loc_1800421F9
0x180041fc0  xor     ebx, ebx
0x180041fc2  test    esi, esi
0x180041fc4  jz      loc_1800421EB
0x180041fca  mov     [rsp+338h+var_2F8], ebx
0x180041fce  lea     rdx, [rsp+338h+var_2F8]
0x180041fd3  mov     rcx, [rsp+338h+packageFullNames]
0x180041fd8  call    cs:__imp_GetPackageStatus
0x180041fdf  nop     dword ptr [rax+rax+00h]
0x180041fe4  test    eax, eax
0x180041fe6  jnz     loc_1800421EB
0x180041fec  mov     esi, ebx
0x180041fee  test    [rsp+338h+var_2F8], 20000h
0x180041ff6  jz      loc_1800421ED
0x180041ffc  call    IsCheckForUpdatesAndWaitForInstallerIfNeededPresent
0x180042001  test    al, al
0x180042003  jz      loc_1800421ED
0x180042009  lea     rdx, aAppinstallerpr; "AppInstallerPromptForUpdate"
0x180042010  lea     rcx, [rsp+338h+var_298]
0x180042018  call    ??0?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18004201d  lea     rax, ??_7AppInstallerPromptForUpdate@DesktopAppXProvider@@6B@; const DesktopAppXProvider::AppInstallerPromptForUpdate::`vftable'
0x180042024  mov     [rsp+338h+var_298], rax
0x18004202c  mov     rdx, rdi; unsigned __int16 *
0x18004202f  lea     rcx, [rsp+338h+var_298]; this
0x180042037  call    ?StartActivity@AppInstallerPromptForUpdate@DesktopAppXProvider@@QEAAXPEBG@Z; DesktopAppXProvider::AppInstallerPromptForUpdate::StartActivity(ushort const *)
0x18004203c  nop
0x18004203d  mov     [rsp+338h+pv], rbx
0x180042042  mov     [rsp+338h+var_2F8], ebx
0x180042046  mov     [rsp+338h+var_2F4], ebx
0x18004204a  lea     rax, [rsp+338h+pv]
0x18004204f  mov     qword ptr [rsp+338h+var_2C0], rax
0x180042054  mov     qword ptr [rsp+338h+var_2C0+8], rbx
0x18004205c  mov     byte ptr [rsp+338h+var_2B0], 1
0x180042064  lea     rax, [rsp+338h+var_2F4]
0x180042069  mov     [rsp+338h+bufferLength], rax; int
0x18004206e  lea     r9, [rsp+338h+var_2F8]
0x180042073  lea     r8, [rsp+338h+var_2C0+8]
0x18004207b  xor     edx, edx
0x18004207d  mov     rcx, [rsp+338h+packageFullNames]
0x180042082  call    cs:__imp_CheckForUpdatesAndWaitForInstallerIfNeeded
0x180042089  nop     dword ptr [rax+rax+00h]
0x18004208e  mov     rcx, [rsp+338h]; this
0x180042096  test    eax, eax
0x180042098  js      loc_180042451
0x18004209e  cmp     byte ptr [rsp+338h+var_2B0], bl
0x1800420a5  jz      short loc_1800420F1
0x1800420a7  mov     r12, qword ptr [rsp+338h+var_2C0+8]
0x1800420af  mov     rdi, qword ptr [rsp+338h+var_2C0]
0x1800420b4  mov     rsi, [rdi]
0x1800420b7  test    rsi, rsi
0x1800420ba  jz      short loc_1800420E9
0x1800420bc  call    cs:__imp_GetLastError
0x1800420c3  nop     dword ptr [rax+rax+00h]
0x1800420c8  mov     ebx, eax
0x1800420ca  mov     rcx, rsi; pv
0x1800420cd  call    cs:__imp_CoTaskMemFree
0x1800420d4  nop     dword ptr [rax+rax+00h]
0x1800420d9  mov     ecx, ebx; dwErrCode
0x1800420db  call    cs:__imp_SetLastError
0x1800420e2  nop     dword ptr [rax+rax+00h]
0x1800420e7  xor     ebx, ebx
0x1800420e9  mov     [rdi], r12
0x1800420ec  mov     r12, qword ptr [rsp+338h+var_2D0]
0x1800420f1  cmp     [rsp+338h+var_2F4], ebx
0x1800420f5  setnz   r8b; bool
0x1800420f9  cmp     [rsp+338h+var_2F8], ebx
0x1800420fd  setnz   dl; bool
0x180042100  lea     rcx, [rsp+338h+var_298]; this
0x180042108  call    ?Stop@AppInstallerPromptForUpdate@DesktopAppXProvider@@QEAAX_N0@Z; DesktopAppXProvider::AppInstallerPromptForUpdate::Stop(bool,bool)
0x18004210d  mov     edi, 7FFFFFFEh
0x180042112  mov     rcx, [rsp+338h+pv]; pv
0x180042117  cmp     [rsp+338h+var_2F4], ebx
0x18004211b  jz      loc_1800421A2
0x180042121  mov     eax, edi
0x180042123  mov     rdx, rcx
0x180042126  lea     r8, [rsp+338h+var_148]
0x18004212e  test    rax, rax
0x180042131  jz      short loc_180042152
0x180042133  movzx   r9d, word ptr [rdx]
0x180042137  test    r9w, r9w
0x18004213b  jz      short loc_180042152
0x18004213d  add     rdx, 2
0x180042141  mov     [r8], r9w
0x180042145  add     r8, 2
0x180042149  dec     rax
0x18004214c  sub     r14, 1
0x180042150  jnz     short loc_18004212E
0x180042152  mov     rax, r14
0x180042155  neg     rax
0x180042158  sbb     r9d, r9d
0x18004215b  not     r9d
0x18004215e  and     r9d, 8007007Ah; char *
0x180042165  lea     rdx, [r8-2]
0x180042169  test    r14, r14
0x18004216c  cmovnz  rdx, r8
0x180042170  mov     [rdx], bx
0x180042173  mov     rax, [rsp+338h]
0x18004217b  jz      loc_180042466
0x180042181  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180042185  mov     rax, rbx
0x180042188  xor     r14d, r14d
0x18004218b  inc     rax
0x18004218e  cmp     [rcx+rax*2], r14w
0x180042193  jnz     short loc_18004218B
0x180042195  inc     eax
0x180042197  mov     [rsp+338h+var_2EC], eax
0x18004219b  mov     esi, 1
0x1800421a0  jmp     short loc_1800421AB
0x1800421a2  mov     esi, ebx
0x1800421a4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800421a8  xor     r14d, r14d
0x1800421ab  test    rcx, rcx
0x1800421ae  jz      short loc_1800421BD
0x1800421b0  call    cs:__imp_CoTaskMemFree
0x1800421b7  nop     dword ptr [rax+rax+00h]
0x1800421bc  nop
0x1800421bd  lea     rax, ??_7AppInstallerPromptForUpdate@DesktopAppXProvider@@6B@; const DesktopAppXProvider::AppInstallerPromptForUpdate::`vftable'
0x1800421c4  mov     [rsp+338h+var_298], rax
0x1800421cc  lea     rcx, [rsp+338h+var_298]
0x1800421d4  call    ?Destroy@?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800421d9  lea     rcx, [rsp+338h+var_298]
0x1800421e1  call    ??1?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800421e6  jmp     loc_1800422B7
0x1800421eb  mov     esi, ebx
0x1800421ed  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800421f1  xor     r14d, r14d
0x1800421f4  jmp     loc_1800422B2
0x1800421f9  lea     rcx, [rsp+338h+var_298]
0x180042201  test    bl, bl
0x180042203  jnz     loc_18004247B
0x180042209  call    ?Stop@?$ActivityBase@VDesktopAppXProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<DesktopAppXProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18004220e  mov     [rsp+338h+var_2EC], r14d
0x180042213  mov     [rsp+338h+count], 1
0x18004221b  xor     r14d, r14d
0x18004221e  mov     [rsp+338h+packageProperties], r14; packageProperties
0x180042223  lea     rax, [rsp+338h+var_148]
0x18004222b  mov     [rsp+338h+buffer], rax; buffer
0x180042230  lea     rax, [rsp+338h+var_2EC]
0x180042235  mov     [rsp+338h+bufferLength], rax; int
0x18004223a  lea     r9, [rsp+338h+packageFullNames]; packageFullNames
0x18004223f  lea     r8, [rsp+338h+count]; count
0x180042244  mov     edx, 20010h; packageFilters
0x180042249  mov     rcx, rdi; packageFamilyName
0x18004224c  call    cs:__imp_FindPackagesByPackageFamily
0x180042253  nop     dword ptr [rax+rax+00h]
0x180042258  mov     rcx, [rsp+338h]; this
  ... truncated ...
```
