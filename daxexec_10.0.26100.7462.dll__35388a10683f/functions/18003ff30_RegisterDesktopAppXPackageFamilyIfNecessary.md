# RegisterDesktopAppXPackageFamilyIfNecessary

- ea: `0x18003ff30`
- end: `0x180040780`
- name: `RegisterDesktopAppXPackageFamilyIfNecessary`
- size: `2128`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, __int64)`
- caller_count: `0`
- callee_count: `27`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1800016e0`
- `0x1800053a0`
- `0x180006158`
- `0x18000821c`
- `0x18000c37c`
- `0x18000e234`
- `0x18001031c`
- `0x180010a84`
- `0x180011300`
- `0x180011820`
- `0x180013100`
- `0x1800148e8`
- `0x180014ed8`
- `0x180014f4c`
- `0x180017374`
- `0x18001748c`
- `0x18001eb48`
- `0x1800384f0`
- `0x180038e54`
- `0x18003a7fc`
- `0x18003d314`
- `0x18003e4e8`
- `0x18003e694`
- `0x18003e77c`
- `0x18003ff00`
- `0x18003ff30`
- `0x18009c0d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004043a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004043a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18003ffd1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18004002d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180040056`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180040637`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18003ffd1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18004002d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180040056`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180040637`
- `api-ms-win-appmodel-runtime-l1-1-1!FindPackagesByPackageFamily` at `0x1800400c7`
- `api-ms-win-appmodel-runtime-l1-1-1!FindPackagesByPackageFamily` at `0x1800404cd`
- `api-ms-win-appmodel-runtime-l1-1-1!FindPackagesByPackageFamily` at `0x1800400c7`
- `api-ms-win-appmodel-runtime-l1-1-1!FindPackagesByPackageFamily` at `0x1800404cd`
- `api-ms-win-appmodel-runtime-internal-l1-1-2!GetEffectivePackageStatusForUser` at `0x1800400fc`
- `api-ms-win-appmodel-runtime-internal-l1-1-2!GetEffectivePackageStatusForUser` at `0x1800400fc`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!GetPackageStatus` at `0x1800402a6`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!GetPackageStatus` at `0x1800402a6`
- `ext-ms-win-appxdeploymentclient-appxdeploy-l1-1-1!CheckForUpdatesAndWaitForInstallerIfNeeded` at `0x180040350`
- `ext-ms-win-appxdeploymentclient-appxdeploy-l1-1-1!CheckForUpdatesAndWaitForInstallerIfNeeded` at `0x180040350`

## string_xrefs

- `0x1800402d5`: `AppInstallerPromptForUpdate`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall RegisterDesktopAppXPackageFamilyIfNecessary(
        unsigned __int16 *a1,
        int a2,
        UINT32 *a3,
        char *a4,
        int *a5)
{
  char *v5; // rsi
  int v9; // edi
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
  int v27; // eax
  _WORD *v28; // rcx
  WCHAR *v29; // rdx
  signed __int64 v30; // r8
  WCHAR v31; // ax
  WCHAR *v32; // rax
  __int64 v33; // rbx
  __int64 v34; // rax
  unsigned int v35; // eax
  __int64 v36; // rcx
  __int64 v37; // rdx
  char *v38; // r8
  __int16 v39; // ax
  char *v40; // rax
  __int64 v41; // rcx
  unsigned int v42; // eax
  int bufferLength; // [rsp+20h] [rbp-318h]
  int *bufferLengtha; // [rsp+20h] [rbp-318h]
  int v45; // [rsp+40h] [rbp-2F8h] BYREF
  int v46; // [rsp+44h] [rbp-2F4h] BYREF
  UINT32 count; // [rsp+48h] [rbp-2F0h] BYREF
  UINT32 v48; // [rsp+4Ch] [rbp-2ECh] BYREF
  __int64 v49; // [rsp+50h] [rbp-2E8h] BYREF
  PWSTR packageFullNames; // [rsp+58h] [rbp-2E0h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-2D8h] BYREF
  __int64 v52; // [rsp+68h] [rbp-2D0h] BYREF
  int *v53; // [rsp+70h] [rbp-2C8h]
  unsigned __int16 v54[8]; // [rsp+78h] [rbp-2C0h] BYREF
  __int128 v55; // [rsp+88h] [rbp-2B0h]
  void **v56; // [rsp+A0h] [rbp-298h] BYREF
  int v57; // [rsp+A8h] [rbp-290h] BYREF
  char v58; // [rsp+ACh] [rbp-28Ch]
  int v59; // [rsp+D0h] [rbp-268h] BYREF
  const char *v60; // [rsp+D8h] [rbp-260h]
  __int64 v61; // [rsp+E0h] [rbp-258h]
  char v62; // [rsp+E8h] [rbp-250h]
  int v63; // [rsp+F0h] [rbp-248h]
  char v64[152]; // [rsp+F8h] [rbp-240h] BYREF
  __int128 v65; // [rsp+190h] [rbp-1A8h]
  int v66; // [rsp+1A0h] [rbp-198h]
  __int64 v67; // [rsp+1A8h] [rbp-190h]
  int *v68; // [rsp+1B0h] [rbp-188h]
  __int64 v69; // [rsp+1B8h] [rbp-180h]
  __int64 v70; // [rsp+1C0h] [rbp-178h]
  void ***v71; // [rsp+1C8h] [rbp-170h]
  __int64 v72; // [rsp+1D0h] [rbp-168h]
  int v73; // [rsp+1D8h] [rbp-160h]
  int *v74; // [rsp+1E0h] [rbp-158h]
  WCHAR buffer[128]; // [rsp+1F0h] [rbp-148h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+338h] [rbp+0h]

  try
  {
    v5 = a4;
    v53 = a5;
    v9 = 0;
    if ( (a4 != 0) != (a3 != 0) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x159,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
        (const char *)0x80070057LL,
        bufferLength);
    v49 = 0;
    v10 = StateRepository::Cache::Manager_NoThrow::Open((StateRepository::Cache::Manager_NoThrow *)&v49);
    v11 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x15F,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
        (const char *)(unsigned int)v10,
        bufferLength);
      v13 = v49;
      v49 = 0;
      if ( v13 )
        SRCacheManager_Close();
      return v11;
    }
    v52 = 0;
    v15 = StateRepository::Cache::Entity::PackageFamily_NoThrow::GetByPackageFamilyName(
            (struct StateRepository::Cache::Manager_NoThrow *)&v49,
            a1,
            &v52);
    v16 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x161,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
        (const char *)(unsigned int)v15,
        bufferLength);
      v17 = v49;
      v49 = 0;
      if ( v17 )
        SRCacheManager_Close();
      return v16;
    }
    if ( !v52 )
    {
      v18 = v49;
      v49 = 0;
      if ( v18 )
        SRCacheManager_Close();
      return 2147958001LL;
    }
    packageFullNames = 0;
    count = 1;
    memset_0(buffer, 0, sizeof(buffer));
    v19 = 128;
    v48 = 128;
    PackagesByPackageFamily = FindPackagesByPackageFamily(a1, 0x20010u, &count, &packageFullNames, &v48, buffer, 0);
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
      v46 = 0;
      EffectivePackageStatusForUser = GetEffectivePackageStatusForUser(0, packageFullNames, &v46);
      if ( EffectivePackageStatusForUser != 1168 )
      {
        if ( EffectivePackageStatusForUser )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x184,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
            (const char *)EffectivePackageStatusForUser,
            (unsigned int)bufferLengtha);
        if ( (v46 & 0x400800) == 0 )
        {
          if ( a2 )
          {
            v45 = 0;
            v9 = 0;
            if ( !(unsigned int)GetPackageStatus(packageFullNames, &v45)
              && (v45 & 0x20000) != 0
              && (unsigned __int8)IsCheckForUpdatesAndWaitForInstallerIfNeededPresent() )
            {
              wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
                &v56,
                "AppInstallerPromptForUpdate");
              v56 = &DesktopAppXProvider::AppInstallerPromptForUpdate::`vftable';
              DesktopAppXProvider::AppInstallerPromptForUpdate::StartActivity(
                (DesktopAppXProvider::AppInstallerPromptForUpdate *)&v56,
                a1);
              pv = 0;
              v45 = 0;
              v46 = 0;
              *(_QWORD *)v54 = &pv;
              *(_QWORD *)&v54[4] = 0;
              LOBYTE(v55) = 1;
              bufferLengtha = &v46;
              v27 = CheckForUpdatesAndWaitForInstallerIfNeeded(packageFullNames, 0, &v54[4], &v45);
              if ( v27 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x1CA,
                  (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
                  (const char *)(unsigned int)v27,
                  (int)&v46);
              wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(v54);
              DesktopAppXProvider::AppInstallerPromptForUpdate::Stop(
                (DesktopAppXProvider::AppInstallerPromptForUpdate *)&v56,
                v45 != 0,
                v46 != 0);
              v28 = pv;
              if ( v46 )
              {
                v29 = buffer;
                v30 = (_BYTE *)pv - (_BYTE *)buffer;
                do
                {
                  if ( v19 == -2147483518 )
                    break;
                  v31 = *(WCHAR *)((char *)v29 + v30);
                  if ( !v31 )
                    break;
                  *v29++ = v31;
                  --v19;
                }
                while ( v19 );
                v32 = v29 - 1;
                if ( v19 )
                  v32 = v29;
                *v32 = 0;
                if ( !v19 )
                  wil::details::in1diag3::Throw_Hr(
                    retaddr,
                    (void *)0x1D3,
                    (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
                    (const char *)0x8007007ALL,
                    (int)&v46);
                v33 = -1;
                v34 = -1;
                do
                  ++v34;
                while ( v28[v34] );
                v48 = v34 + 1;
                v9 = 1;
              }
              else
              {
                v9 = 0;
                v33 = -1;
              }
              if ( v28 )
                CoTaskMemFree(v28);
              v56 = &DesktopAppXProvider::AppInstallerPromptForUpdate::`vftable';
              wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v56);
              wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(&v56);
              goto LABEL_52;
            }
          }
LABEL_51:
          v33 = -1;
LABEL_52:
          if ( !packageFullNames )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x1D8,
              (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
              (const char *)0x8000FFFFLL,
              (int)bufferLengtha);
          *(_OWORD *)v54 = 0;
          v55 = 0;
          do
            ++v33;
          while ( packageFullNames[v33] );
          std::wstring::_Construct<1,unsigned short const *>(v54, packageFullNames, v33);
          CompleteCustomInstallIfNeeded(v54);
          std::wstring::~wstring(v54);
          if ( a3 && v5 )
          {
            v36 = *a3;
            if ( (unsigned __int64)(v36 - 1) > 0x7FFFFFFE )
            {
              v12 = 2147942487LL;
              if ( *a3 )
                *(_WORD *)v5 = 0;
            }
            else
            {
              v37 = 2147483646 - v36;
              v38 = (char *)((char *)buffer - v5);
              do
              {
                if ( !(v36 + v37) )
                  break;
                v39 = *(_WORD *)&v38[(_QWORD)v5];
                if ( !v39 )
                  break;
                *(_WORD *)v5 = v39;
                v5 += 2;
                --v36;
              }
              while ( v36 );
              v40 = v5 - 2;
              if ( v36 )
                v40 = v5;
              *(_WORD *)v40 = 0;
              v12 = v36 == 0 ? 0x8007007A : 0;
            }
            if ( (int)v12 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x1DE,
                (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
                (const char *)v12,
                (int)bufferLengtha);
            *a3 = v48;
          }
          if ( v53 )
            *v53 = v9;
          v41 = v49;
          v49 = 0;
          if ( v41 )
            SRCacheManager_Close();
          return 0;
        }
        v21 = (v46 & 0x8000) != 0;
      }
    }
    v57 = 0;
    v58 = 0;
    v62 = 0;
    v59 = 0;
    v60 = "PreActivationPackageRegistration";
    v61 = 0;
    v63 = 0;
    v65 = 0;
    memset_0(v64, 0, sizeof(v64));
    v66 = 1;
    v67 = 0;
    v68 = &v57;
    v69 = 0;
    v70 = 0;
    v71 = &v56;
    v72 = 0;
    v73 = 0;
    v74 = &v59;
    v56 = &DesktopAppXProvider::PreActivationPackageRegistration::`vftable';
    DesktopAppXProvider::PreActivationPackageRegistration::StartActivity(
      (DesktopAppXProvider::PreActivationPackageRegistration *)&v56,
      a1);
    v23 = 0xFFFFFFFFLL;
    if ( v21 )
    {
      v24 = (_DWORD *)*((_QWORD *)DesktopAppXProvider::Instance() + 1);
      if ( *v24 > 5u )
      {
        pv = packageFullNames;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (_DWORD)v24,
          (unsigned int)&unk_1800E3ECF,
          (_DWORD)v68 + 8,
          v25,
          (__int64)&pv);
      }
      v23 = 0;
    }
    v45 = 0;
    v26 = RegisterDesktopAppXPackageFamily(a1, v23, &v45);
    if ( v26 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1A6,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
        (const char *)(unsigned int)v26,
        (int)bufferLengtha);
    if ( v21 )
    {
      v45 = -2147009280;
      DesktopAppXProvider::PreActivationPackageRegistration::InplaceFastUnwind<unsigned short * &,long &>(
        &v56,
        &packageFullNames,
        &v45);
      v42 = wil::verify_hresult(2147958016LL);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1AB,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
        (const char *)v42,
        (int)bufferLengtha);
    }
    wil::ActivityBase<DesktopAppXProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v56);
    v48 = 128;
    count = 1;
    v35 = FindPackagesByPackageFamily(a1, 0x20010u, &count, &packageFullNames, &v48, buffer, 0);
    if ( v35 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x1B4,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
        (const char *)v35,
        (unsigned int)bufferLengtha);
    if ( !count )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1B7,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
        (const char *)0x80073CF1LL,
        (int)bufferLengtha);
    v56 = &DesktopAppXProvider::PreActivationPackageRegistration::`vftable';
    wil::ActivityBase<DesktopAppXProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v56);
    wil::ActivityBase<DesktopAppXProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DesktopAppXProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(&v56);
    v9 = 1;
    goto LABEL_51;
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
0x18003ff30  push    rbx
0x18003ff32  push    rsi
0x18003ff33  push    rdi
0x18003ff34  push    r12
0x18003ff36  push    r13
0x18003ff38  push    r14
0x18003ff3a  push    r15
0x18003ff3c  sub     rsp, 300h
0x18003ff43  mov     rax, cs:__security_cookie
0x18003ff4a  xor     rax, rsp
0x18003ff4d  mov     [rsp+338h+var_48], rax
0x18003ff55  mov     rsi, r9
0x18003ff58  mov     r13, r8
0x18003ff5b  mov     r12d, edx
0x18003ff5e  mov     r15, rcx
0x18003ff61  mov     rax, [rsp+338h+arg_20]
0x18003ff69  mov     [rsp+338h+var_2C8], rax
0x18003ff6e  mov     rcx, [rsp+338h]; this
0x18003ff76  xor     edi, edi
0x18003ff78  mov     edx, edi
0x18003ff7a  test    r9, r9
0x18003ff7d  setnz   dl
0x18003ff80  mov     eax, edi
0x18003ff82  test    r8, r8
0x18003ff85  setnz   al
0x18003ff88  cmp     edx, eax
0x18003ff8a  jnz     loc_18004066F
0x18003ff90  mov     [rsp+338h+var_2E8], rdi
0x18003ff95  lea     rcx, [rsp+338h+var_2E8]; this
0x18003ff9a  call    ?Open@Manager_NoThrow@Cache@StateRepository@@QEAAJXZ; StateRepository::Cache::Manager_NoThrow::Open(void)
0x18003ff9f  mov     ebx, eax
0x18003ffa1  test    eax, eax
0x18003ffa3  jns     short loc_18003FFE4
0x18003ffa5  mov     rcx, [rsp+338h]; this
0x18003ffad  mov     r9d, eax; char *
0x18003ffb0  lea     r8, aOnecoreBaseApp_62; "onecore\\base\\appmodel\\execmodel\\des"...
0x18003ffb7  mov     edx, 15Fh; void *
0x18003ffbc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ffc1  nop
0x18003ffc2  mov     rcx, [rsp+338h+var_2E8]
0x18003ffc7  mov     [rsp+338h+var_2E8], rdi
0x18003ffcc  test    rcx, rcx
0x18003ffcf  jz      short loc_18003FFDD
0x18003ffd1  call    cs:__imp_SRCacheManager_Close
0x18003ffd8  nop     dword ptr [rax+rax+00h]
0x18003ffdd  mov     eax, ebx
0x18003ffdf  jmp     loc_18004064B
0x18003ffe4  mov     [rsp+338h+var_2D0], rdi
0x18003ffe9  lea     r8, [rsp+338h+var_2D0]; __int64 *
0x18003ffee  mov     rdx, r15; unsigned __int16 *
0x18003fff1  lea     rcx, [rsp+338h+var_2E8]; struct StateRepository::Cache::Manager_NoThrow *
0x18003fff6  call    ?GetByPackageFamilyName@PackageFamily_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::PackageFamily_NoThrow::GetByPackageFamilyName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x18003fffb  mov     ebx, eax
0x18003fffd  test    eax, eax
0x18003ffff  jns     short loc_180040040
0x180040001  mov     rcx, [rsp+338h]; this
0x180040009  mov     r9d, eax; char *
0x18004000c  lea     r8, aOnecoreBaseApp_62; "onecore\\base\\appmodel\\execmodel\\des"...
0x180040013  mov     edx, 161h; void *
0x180040018  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004001d  nop
0x18004001e  mov     rcx, [rsp+338h+var_2E8]
0x180040023  mov     [rsp+338h+var_2E8], rdi
0x180040028  test    rcx, rcx
0x18004002b  jz      short loc_180040039
0x18004002d  call    cs:__imp_SRCacheManager_Close
0x180040034  nop     dword ptr [rax+rax+00h]
0x180040039  mov     eax, ebx
0x18004003b  jmp     loc_18004064B
0x180040040  cmp     [rsp+338h+var_2D0], rdi
0x180040045  jnz     short loc_18004006C
0x180040047  mov     rcx, [rsp+338h+var_2E8]
0x18004004c  mov     [rsp+338h+var_2E8], rdi
0x180040051  test    rcx, rcx
0x180040054  jz      short loc_180040062
0x180040056  call    cs:__imp_SRCacheManager_Close
0x18004005d  nop     dword ptr [rax+rax+00h]
0x180040062  mov     eax, 80073CF1h
0x180040067  jmp     loc_18004064B
0x18004006c  mov     [rsp+338h+packageFullNames], rdi
0x180040071  mov     [rsp+338h+count], 1
0x180040079  xor     edx, edx; Val
0x18004007b  mov     r8d, 100h; Size
0x180040081  lea     rcx, [rsp+338h+var_148]; void *
0x180040089  call    memset_0
0x18004008e  mov     r14d, 80h
0x180040094  mov     [rsp+338h+var_2EC], r14d
0x180040099  mov     [rsp+338h+packageProperties], rdi; packageProperties
0x18004009e  lea     rax, [rsp+338h+var_148]
0x1800400a6  mov     [rsp+338h+buffer], rax; buffer
0x1800400ab  lea     rax, [rsp+338h+var_2EC]
0x1800400b0  mov     [rsp+338h+bufferLength], rax; unsigned int
0x1800400b5  lea     r9, [rsp+338h+packageFullNames]; packageFullNames
0x1800400ba  lea     r8, [rsp+338h+count]; count
0x1800400bf  mov     edx, 20010h; packageFilters
0x1800400c4  mov     rcx, r15; packageFamilyName
0x1800400c7  call    cs:__imp_FindPackagesByPackageFamily
0x1800400ce  nop     dword ptr [rax+rax+00h]
0x1800400d3  mov     rcx, [rsp+338h]; this
0x1800400db  test    eax, eax
0x1800400dd  jnz     loc_180040687
0x1800400e3  mov     bl, dil
0x1800400e6  cmp     [rsp+338h+count], edi
0x1800400ea  jz      short loc_180040135
0x1800400ec  mov     [rsp+338h+var_2F4], edi
0x1800400f0  lea     r8, [rsp+338h+var_2F4]
0x1800400f5  mov     rdx, [rsp+338h+packageFullNames]
0x1800400fa  xor     ecx, ecx
0x1800400fc  call    cs:__imp_GetEffectivePackageStatusForUser
0x180040103  nop     dword ptr [rax+rax+00h]
0x180040108  cmp     eax, 490h
0x18004010d  jz      short loc_180040135
0x18004010f  mov     rcx, [rsp+338h]; this
0x180040117  test    eax, eax
0x180040119  jnz     loc_18004069B
0x18004011f  mov     ebx, [rsp+338h+var_2F4]
0x180040123  test    ebx, 400800h
0x180040129  jz      loc_180040288
0x18004012f  shr     ebx, 0Fh
0x180040132  and     bl, 1
0x180040135  xor     r12d, r12d
0x180040138  mov     [rsp+338h+var_290], r12d
0x180040140  mov     [rsp+338h+var_28C], r12b
0x180040148  mov     [rsp+338h+var_250], r12b
0x180040150  mov     [rsp+338h+var_268], r12d
0x180040158  lea     rax, aPreactivationp; "PreActivationPackageRegistration"
0x18004015f  mov     [rsp+338h+var_260], rax
0x180040167  mov     [rsp+338h+var_258], r12
0x18004016f  mov     [rsp+338h+var_248], r12d
0x180040177  xorps   xmm0, xmm0
0x18004017a  movdqa  [rsp+338h+var_1A8], xmm0
0x180040183  xor     edx, edx; Val
0x180040185  mov     r8d, 98h; Size
0x18004018b  lea     rcx, [rsp+338h+var_240]; void *
0x180040193  call    memset_0
0x180040198  mov     [rsp+338h+var_198], 1
0x1800401a3  xor     eax, eax
0x1800401a5  mov     [rsp+338h+var_190], rax
0x1800401ad  lea     rax, [rsp+338h+var_290]
0x1800401b5  mov     [rsp+338h+var_188], rax
0x1800401bd  mov     [rsp+338h+var_180], r12
0x1800401c5  mov     [rsp+338h+var_178], r12
0x1800401cd  lea     rax, [rsp+338h+var_298]
0x1800401d5  mov     [rsp+338h+var_170], rax
0x1800401dd  mov     [rsp+338h+var_168], r12
0x1800401e5  mov     [rsp+338h+var_160], r12d
0x1800401ed  lea     rax, [rsp+338h+var_268]
0x1800401f5  mov     [rsp+338h+var_158], rax
0x1800401fd  lea     rdi, ??_7PreActivationPackageRegistration@DesktopAppXProvider@@6B@; const DesktopAppXProvider::PreActivationPackageRegistration::`vftable'
0x180040204  mov     [rsp+338h+var_298], rdi
0x18004020c  mov     rdx, r15; unsigned __int16 *
0x18004020f  lea     rcx, [rsp+338h+var_298]; this
0x180040217  call    ?StartActivity@PreActivationPackageRegistration@DesktopAppXProvider@@QEAAXPEBG@Z; DesktopAppXProvider::PreActivationPackageRegistration::StartActivity(ushort const *)
0x18004021c  nop
0x18004021d  or      edx, 0FFFFFFFFh
0x180040220  test    bl, bl
0x180040222  jz      short loc_180040261
0x180040224  call    ?Instance@DesktopAppXProvider@@KAPEAV1@XZ; DesktopAppXProvider::Instance(void)
0x180040229  mov     rcx, [rax+8]
0x18004022d  cmp     dword ptr [rcx], 5
0x180040230  jbe     short loc_18004025E
0x180040232  mov     rax, [rsp+338h+packageFullNames]
0x180040237  mov     [rsp+338h+pv], rax
0x18004023c  mov     r8, [rsp+338h+var_188]
0x180040244  add     r8, 8
0x180040248  lea     rax, [rsp+338h+pv]
0x18004024d  mov     [rsp+338h+bufferLength], rax; int
0x180040252  lea     rdx, unk_1800E3ECF
0x180040259  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18004025e  mov     edx, r12d
0x180040261  mov     [rsp+338h+var_2F8], r12d
0x180040266  lea     r8, [rsp+338h+var_2F8]
0x18004026b  mov     rcx, r15
0x18004026e  call    RegisterDesktopAppXPackageFamily
0x180040273  mov     rcx, [rsp+338h]; this
0x18004027b  test    eax, eax
0x18004027d  js      loc_1800406B0
0x180040283  jmp     loc_18004047D
0x180040288  test    r12d, r12d
0x18004028b  jz      loc_180040475
0x180040291  xor     r12d, r12d
0x180040294  mov     [rsp+338h+var_2F8], r12d
0x180040299  mov     edi, r12d
0x18004029c  lea     rdx, [rsp+338h+var_2F8]
0x1800402a1  mov     rcx, [rsp+338h+packageFullNames]
0x1800402a6  call    cs:__imp_GetPackageStatus
0x1800402ad  nop     dword ptr [rax+rax+00h]
0x1800402b2  test    eax, eax
0x1800402b4  jnz     loc_180040528
0x1800402ba  test    [rsp+338h+var_2F8], 20000h
0x1800402c2  jz      loc_180040528
0x1800402c8  call    IsCheckForUpdatesAndWaitForInstallerIfNeededPresent
0x1800402cd  test    al, al
0x1800402cf  jz      loc_180040528
0x1800402d5  lea     rdx, aAppinstallerpr; "AppInstallerPromptForUpdate"
0x1800402dc  lea     rcx, [rsp+338h+var_298]
0x1800402e4  call    ??0?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800402e9  lea     rax, ??_7AppInstallerPromptForUpdate@DesktopAppXProvider@@6B@; const DesktopAppXProvider::AppInstallerPromptForUpdate::`vftable'
0x1800402f0  mov     [rsp+338h+var_298], rax
0x1800402f8  mov     rdx, r15; unsigned __int16 *
0x1800402fb  lea     rcx, [rsp+338h+var_298]; this
0x180040303  call    ?StartActivity@AppInstallerPromptForUpdate@DesktopAppXProvider@@QEAAXPEBG@Z; DesktopAppXProvider::AppInstallerPromptForUpdate::StartActivity(ushort const *)
0x180040308  nop
0x180040309  mov     [rsp+338h+pv], r12
0x18004030e  mov     [rsp+338h+var_2F8], r12d
0x180040313  mov     [rsp+338h+var_2F4], r12d
0x180040318  lea     rax, [rsp+338h+pv]
0x18004031d  mov     qword ptr [rsp+338h+var_2C0], rax
0x180040322  mov     qword ptr [rsp+338h+var_2C0+8], r12
0x18004032a  mov     byte ptr [rsp+338h+var_2B0], 1
0x180040332  lea     rax, [rsp+338h+var_2F4]
0x180040337  mov     [rsp+338h+bufferLength], rax; int
0x18004033c  lea     r9, [rsp+338h+var_2F8]
0x180040341  lea     r8, [rsp+338h+var_2C0+8]
0x180040349  xor     edx, edx
0x18004034b  mov     rcx, [rsp+338h+packageFullNames]
0x180040350  call    cs:__imp_CheckForUpdatesAndWaitForInstallerIfNeeded
0x180040357  nop     dword ptr [rax+rax+00h]
0x18004035c  mov     rcx, [rsp+338h]; this
0x180040364  test    eax, eax
0x180040366  js      loc_1800406C5
0x18004036c  lea     rcx, [rsp+338h+var_2C0]
0x180040371  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180040376  cmp     [rsp+338h+var_2F4], r12d
0x18004037b  setnz   r8b; bool
0x18004037f  cmp     [rsp+338h+var_2F8], r12d
0x180040384  setnz   dl; bool
0x180040387  lea     rcx, [rsp+338h+var_298]; this
0x18004038f  call    ?Stop@AppInstallerPromptForUpdate@DesktopAppXProvider@@QEAAX_N0@Z; DesktopAppXProvider::AppInstallerPromptForUpdate::Stop(bool,bool)
0x180040394  mov     rcx, [rsp+338h+pv]; pv
0x180040399  cmp     [rsp+338h+var_2F4], r12d
0x18004039e  jz      loc_18004042E
0x1800403a4  lea     rdx, [rsp+338h+var_148]
0x1800403ac  lea     rax, [rsp+338h+var_148]
0x1800403b4  mov     r8, rcx
0x1800403b7  sub     r8, rax
0x1800403ba  lea     rax, [r14+7FFFFF7Eh]
0x1800403c1  test    rax, rax
0x1800403c4  jz      short loc_1800403DD
0x1800403c6  movzx   eax, word ptr [rdx+r8]
0x1800403cb  test    ax, ax
0x1800403ce  jz      short loc_1800403DD
0x1800403d0  mov     [rdx], ax
0x1800403d3  add     rdx, 2
0x1800403d7  sub     r14, 1
0x1800403db  jnz     short loc_1800403BA
0x1800403dd  lea     rax, [rdx-2]
0x1800403e1  test    r14, r14
0x1800403e4  cmovnz  rax, rdx
0x1800403e8  mov     [rax], r12w
0x1800403ec  mov     rax, r14
0x1800403ef  neg     rax
0x1800403f2  sbb     r9d, r9d
0x1800403f5  not     r9d
0x1800403f8  and     r9d, 8007007Ah; char *
0x1800403ff  mov     rax, [rsp+338h]
0x180040407  test    r14, r14
0x18004040a  jz      loc_1800406DA
0x180040410  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180040414  mov     rax, rbx
0x180040417  inc     rax
0x18004041a  cmp     [rcx+rax*2], r12w
0x18004041f  jnz     short loc_180040417
0x180040421  inc     eax
0x180040423  mov     [rsp+338h+var_2EC], eax
0x180040427  mov     edi, 1
0x18004042c  jmp     short loc_180040435
0x18004042e  mov     edi, r12d
0x180040431  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180040435  test    rcx, rcx
0x180040438  jz      short loc_180040447
0x18004043a  call    cs:__imp_CoTaskMemFree
0x180040441  nop     dword ptr [rax+rax+00h]
0x180040446  nop
0x180040447  lea     rax, ??_7AppInstallerPromptForUpdate@DesktopAppXProvider@@6B@; const DesktopAppXProvider::AppInstallerPromptForUpdate::`vftable'
0x18004044e  mov     [rsp+338h+var_298], rax
0x180040456  lea     rcx, [rsp+338h+var_298]
0x18004045e  call    ?Destroy@?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180040463  lea     rcx, [rsp+338h+var_298]
0x18004046b  call    ??1?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180040470  jmp     loc_18004052C
0x180040475  xor     r12d, r12d
0x180040478  jmp     loc_180040528
0x18004047d  lea     rcx, [rsp+338h+var_298]
0x180040485  test    bl, bl
0x180040487  jnz     loc_1800406EF
0x18004048d  call    ?Stop@?$ActivityBase@VDesktopAppXProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<DesktopAppXProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180040492  mov     [rsp+338h+var_2EC], r14d
0x180040497  mov     [rsp+338h+count], 1
0x18004049f  mov     [rsp+338h+packageProperties], r12; packageProperties
0x1800404a4  lea     rax, [rsp+338h+var_148]
0x1800404ac  mov     [rsp+338h+buffer], rax; buffer
0x1800404b1  lea     rax, [rsp+338h+var_2EC]
0x1800404b6  mov     [rsp+338h+bufferLength], rax; int
0x1800404bb  lea     r9, [rsp+338h+packageFullNames]; packageFullNames
0x1800404c0  lea     r8, [rsp+338h+count]; count
0x1800404c5  mov     edx, 20010h; packageFilters
0x1800404ca  mov     rcx, r15; packageFamilyName
0x1800404cd  call    cs:__imp_FindPackagesByPackageFamily
0x1800404d4  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
