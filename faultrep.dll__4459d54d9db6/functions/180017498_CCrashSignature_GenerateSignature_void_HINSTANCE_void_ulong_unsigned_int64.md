# CCrashSignature::GenerateSignature(void *,HINSTANCE__ *,void *,ulong,unsigned __int64)

- ea: `0x180017498`
- end: `0x1800180c4`
- name: `?GenerateSignature@CCrashSignature@@QEAAJPEAXPEAUHINSTANCE__@@0K_K@Z`
- size: `3116`
- prototype: `__int64 __fastcall(CCrashSignature *this, HANDLE ProcessHandle, HINSTANCE, void *, unsigned int, unsigned __int64)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x18001541c`

## callees

- `0x180002890`
- `0x180003474`
- `0x180003830`
- `0x180003e34`
- `0x180006b50`
- `0x180009e04`
- `0x180009ed8`
- `0x180009f00`
- `0x180017498`
- `0x180018358`
- `0x18001860c`
- `0x180018800`
- `0x180018a6c`
- `0x180018f64`
- `0x1800190a0`
- `0x180027474`
- `0x18002769c`
- `0x180027894`
- `0x18003a164`
- `0x18003a50c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180017d94`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180017d94`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180017572`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180017608`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180017572`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180017608`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x18001771f`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x18001771f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800175d7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180017e8e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800175d7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180017e8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800175ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017788`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001780d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017904`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001797f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017cae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800175ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017788`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001780d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017904`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001797f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017cae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001775b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001775b`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x1800177ec`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x180017ca0`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x1800177ec`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x180017ca0`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180017971`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180017971`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x18001773d`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x18001773d`
- `api-ms-win-core-toolhelp-l1-1-0!Module32NextW` at `0x180017e11`
- `api-ms-win-core-toolhelp-l1-1-0!Module32NextW` at `0x180017e11`
- `api-ms-win-core-toolhelp-l1-1-0!Module32FirstW` at `0x18001777e`
- `api-ms-win-core-toolhelp-l1-1-0!Module32FirstW` at `0x18001777e`
- `ext-ms-win-kernel32-package-l1-1-0!GetPackageFullName` at `0x180017645`
- `ext-ms-win-kernel32-package-l1-1-0!GetPackageFullName` at `0x180017645`
- `ext-ms-win-wer-xbox-l1-1-2!XerGetPackageIdentity` at `0x18001765a`
- `ext-ms-win-wer-xbox-l1-1-2!XerGetPackageIdentity` at `0x18001765a`

## string_xrefs

- `0x1800174ed`: `mscorwks.dll`
- `0x1800174f9`: `mscorsvr.dll`
- `0x180017504`: `clr.dll`
- `0x18001750f`: `coreclr.dll`

## pseudocode

```c
__int64 __fastcall CCrashSignature::GenerateSignature(
        CCrashSignature *this,
        HANDLE ProcessHandle,
        HINSTANCE a3,
        void *a4,
        unsigned int a5,
        unsigned __int64 a6)
{
  DWORD ProcessId; // r14d
  signed int LastError; // eax
  unsigned int v12; // ebx
  DWORD TickCount; // eax
  BOOL v14; // ecx
  bool v15; // zf
  int ProcessPackageFullName; // eax
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // r9
  __int64 v20; // rdx
  _WORD *v21; // rcx
  HANDLE Toolhelp32Snapshot; // rax
  void *v23; // rcx
  void *v24; // rcx
  signed int v25; // eax
  signed int v26; // eax
  bool v27; // sf
  __int64 v28; // rcx
  WCHAR *szExePath; // r8
  __int64 v30; // rdx
  WCHAR *v31; // rax
  WCHAR *v32; // rcx
  char *v33; // r12
  LPCWSTR *v34; // r13
  _QWORD *v35; // rcx
  __int64 v36; // rdx
  signed int v37; // eax
  signed int v38; // eax
  bool v39; // sf
  _QWORD *v40; // rcx
  __int64 v41; // rdx
  __int64 v42; // rbx
  __int64 v43; // r8
  __int64 v44; // rax
  WCHAR *v45; // rcx
  WCHAR *v46; // r9
  unsigned __int64 v47; // rax
  __int64 v48; // r8
  __int64 v49; // rcx
  char *v50; // rbx
  char *v51; // r13
  BYTE *v52; // rcx
  HMODULE hModule; // rdx
  signed int v54; // eax
  bool v55; // sf
  __int64 v56; // rcx
  WCHAR *v57; // r8
  __int64 v58; // rdx
  WCHAR *v59; // rax
  WCHAR *v60; // rcx
  __int64 i; // rbx
  unsigned __int64 v62; // rcx
  unsigned __int64 v63; // rax
  unsigned int v64; // eax
  int v65; // ecx
  DWORD v66; // eax
  __int64 v67; // r9
  int v68; // eax
  LPFILETIME lpUserTime; // [rsp+20h] [rbp-E0h]
  LPFILETIME lpUserTimea; // [rsp+20h] [rbp-E0h]
  __int64 v71; // [rsp+28h] [rbp-D8h]
  __int64 v72; // [rsp+28h] [rbp-D8h]
  int v73; // [rsp+40h] [rbp-C0h] BYREF
  UINT32 packageFullNameLength; // [rsp+44h] [rbp-BCh] BYREF
  DWORD v75; // [rsp+48h] [rbp-B8h]
  struct _FILETIME CreationTime; // [rsp+50h] [rbp-B0h] BYREF
  struct _FILETIME UserTime; // [rsp+58h] [rbp-A8h] BYREF
  struct _FILETIME KernelTime; // [rsp+60h] [rbp-A0h] BYREF
  struct _FILETIME ExitTime; // [rsp+68h] [rbp-98h] BYREF
  void *v80; // [rsp+70h] [rbp-90h]
  _QWORD v81[4]; // [rsp+78h] [rbp-88h]
  _OWORD v82[3]; // [rsp+98h] [rbp-68h] BYREF
  int v83; // [rsp+C8h] [rbp-38h]
  MODULEENTRY32W me; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR Filename[264]; // [rsp+510h] [rbp+410h] BYREF

  v80 = a4;
  memset_0(&me, 0, sizeof(me));
  v81[0] = L"mscorwks.dll";
  v81[1] = L"mscorsvr.dll";
  v81[2] = L"clr.dll";
  v81[3] = L"coreclr.dll";
  CreationTime = 0;
  ExitTime = 0;
  KernelTime = 0;
  UserTime = 0;
  v73 = 0;
  if ( ProcessHandle )
  {
    ProcessId = GetProcessId(ProcessHandle);
    if ( !ProcessId )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_dfe85b1dc90e3a8ff9b91b3f1e731dac_Traceguids);
      LastError = GetLastError();
      v12 = LastError;
      if ( LastError > 0 )
        v12 = (unsigned __int16)LastError | 0x80070000;
      if ( (v12 & 0x80000000) == 0 )
        return (unsigned int)-2147467259;
      return v12;
    }
    Filename[0] = 0;
    TickCount = GetTickCount();
    *((_DWORD *)this + 88) = a5;
    *((_QWORD *)this + 45) = a6;
    *((_QWORD *)this + 43) = a6;
    v75 = TickCount;
    *(_QWORD *)this = a3;
    *((_DWORD *)this + 31) = GetProcessId(ProcessHandle);
    *((_QWORD *)this + 1) = ProcessHandle;
    packageFullNameLength = 0;
    if ( (unsigned __int8)IsGetPackageFullNamePresent() || (unsigned __int8)IsXerGetPackageIdentityPresent() )
    {
      if ( (unsigned __int8)IsGetPackageFullNamePresent() )
        v15 = GetPackageFullName(ProcessHandle, &packageFullNameLength, 0) == 15700;
      else
        v15 = (unsigned int)XerGetPackageIdentity(ProcessHandle, &packageFullNameLength, 0, 0, 0) == -2147009196;
      v14 = !v15;
    }
    else
    {
      v14 = 0;
    }
    *((_DWORD *)this + 110) = v14;
    if ( v14 )
    {
      ProcessPackageFullName = PackageUtility::GetProcessPackageFullName(ProcessHandle);
      v12 = ProcessPackageFullName;
      if ( ProcessPackageFullName < 0 )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return v12;
        v18 = 36;
        v19 = (unsigned int)ProcessPackageFullName;
        goto LABEL_27;
      }
      if ( (int)PackageUtility::GetProcessApplicationId(ProcessHandle) >= 0
        && (int)PackageUtility::ParseApplicationId(*((_QWORD *)this + 64), v20, (char *)this + 480) < 0 )
      {
        v21 = (_WORD *)*((_QWORD *)this + 60);
        *((_QWORD *)this + 61) = v21;
        *v21 = 0;
      }
    }
    if ( GetProcessTimes(ProcessHandle, &CreationTime, &ExitTime, &KernelTime, &UserTime) )
      *((struct _FILETIME *)this + 16) = CreationTime;
    Toolhelp32Snapshot = CreateToolhelp32Snapshot(8u, ProcessId);
    v23 = (void *)*((_QWORD *)this + 82);
    *((_QWORD *)this + 82) = Toolhelp32Snapshot;
    if ( (unsigned __int64)v23 + 1 > 1 )
      CloseHandle(v23);
    v24 = (void *)*((_QWORD *)this + 82);
    if ( (unsigned __int64)v24 + 1 > 1 )
    {
      me.dwSize = 1080;
      if ( !Module32FirstW(v24, &me) )
      {
        v25 = GetLastError();
        v12 = v25;
        if ( v25 > 0 )
          v12 = (unsigned __int16)v25 | 0x80070000;
        if ( (v12 & 0x80000000) == 0 )
          v12 = -2147467259;
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return v12;
        v18 = 43;
        v19 = v12;
LABEL_27:
        WPP_SF_d(v17[2], v18, WPP_dfe85b1dc90e3a8ff9b91b3f1e731dac_Traceguids, v19);
        return v12;
      }
      if ( !K32GetModuleFileNameExW(ProcessHandle, me.hModule, Filename, 0x104u) )
      {
        v26 = GetLastError();
        v27 = v26 < 0;
        if ( v26 > 0 )
        {
          v26 = (unsigned __int16)v26 | 0x80070000;
          v27 = v26 < 0;
        }
        if ( !v27 )
          v26 = -2147467259;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            44,
            WPP_dfe85b1dc90e3a8ff9b91b3f1e731dac_Traceguids,
            (unsigned int)v26);
        v28 = 2147483646;
        szExePath = me.szExePath;
        v30 = 260;
        v31 = Filename;
        do
        {
          if ( !v28 )
            break;
          if ( !*szExePath )
            break;
          *v31++ = *szExePath++;
          --v28;
          --v30;
        }
        while ( v30 );
        v32 = v31 - 1;
        if ( v30 )
          v32 = v31;
        *v32 = 0;
      }
      v33 = (char *)this + 48;
      v34 = (LPCWSTR *)((char *)this + 16);
      v12 = CCrashSignature::SetModuleInfo(
              (char *)this + 112,
              ProcessHandle,
              Filename,
              me.hModule,
              (char *)this + 16,
              (char *)this + 48,
              (char *)this + 112,
              (char *)this + 120);
      if ( (v12 & 0x80000000) != 0 )
      {
        v35 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return v12;
        v36 = 45;
        goto LABEL_63;
      }
LABEL_109:
      UtilGetFriendlyAppName(*v34);
      CCrashSignature::UpdateSubProcessName(this, ProcessHandle, v80, *v34, v33);
      CCrashSignature::UpdateSetupProcessName(v49, *v34, v33);
      SetDirEnvironmentVariableFromPath(L"appdir", *v34);
      v50 = (char *)this + 200;
      if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                              (char *)this + 200,
                              L"unknown",
                              7) )
      {
        v51 = (char *)this + 232;
        if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                (char *)this + 232,
                                L"unknown",
                                7) )
        {
          while ( 1 )
          {
            if ( !v73 )
            {
              v52 = (BYTE *)*((_QWORD *)this + 45);
              if ( v52 >= me.modBaseAddr && v52 < &me.modBaseAddr[(unsigned __int64)me.modBaseSize] )
              {
                Filename[0] = 0;
                hModule = me.hModule;
                *((_QWORD *)this + 43) = v52 - me.modBaseAddr;
                v73 = 1;
                if ( !K32GetModuleFileNameExW(ProcessHandle, hModule, Filename, 0x104u) )
                {
                  v54 = GetLastError();
                  v55 = v54 < 0;
                  if ( v54 > 0 )
                  {
                    v54 = (unsigned __int16)v54 | 0x80070000;
                    v55 = v54 < 0;
                  }
                  if ( !v55 )
                    v54 = -2147467259;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      48,
                      WPP_dfe85b1dc90e3a8ff9b91b3f1e731dac_Traceguids,
                      (unsigned int)v54);
                  }
                  v56 = 2147483646;
                  v57 = me.szExePath;
                  v58 = 260;
                  v59 = Filename;
                  do
                  {
                    if ( !v56 )
                      break;
                    if ( !*v57 )
                      break;
                    *v59++ = *v57++;
                    --v56;
                    --v58;
                  }
                  while ( v58 );
                  v60 = v59 - 1;
                  if ( v58 )
                    v60 = v59;
                  *v60 = 0;
                }
                v12 = CCrashSignature::SetModuleInfo(
                        (char *)this + 264,
                        ProcessHandle,
                        Filename,
                        me.hModule,
                        v50,
                        v51,
                        (char *)this + 264,
                        (char *)this + 272);
                if ( (v12 & 0x80000000) != 0 )
                {
                  v35 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  {
                    v36 = 49;
                    goto LABEL_63;
                  }
                  return v12;
                }
                *((_DWORD *)this + 69) = me.modBaseSize;
              }
            }
            for ( i = 0; i != 4; ++i )
            {
              if ( !(unsigned int)_o__wcsicmp(me.szModule, v81[i]) )
              {
                v83 = 0;
                memset(v82, 0, sizeof(v82));
                if ( (int)UtilGetFileInfo(me.szExePath, (__int64)v82, 0, 0, 0) >= 0 )
                {
                  v62 = HIDWORD(v82[0]) | ((unsigned __int64)DWORD2(v82[0]) << 32);
                  v63 = *((_QWORD *)this + 81);
                  if ( !v63 || v62 < v63 )
                    *((_QWORD *)this + 81) = v62;
                }
              }
            }
            v51 = (char *)this + 232;
            if ( !Module32NextW(*((HANDLE *)this + 82), &me) )
              break;
            v50 = (char *)this + 200;
          }
          if ( !v73 )
            CCrashSignature::LookupModuleInUnloadedModules((HANDLE *)this, &v73, (unsigned __int16 *const)this + 132);
          v64 = *((_DWORD *)this + 88) + 1073741515;
          if ( v64 <= 0xD )
          {
            v65 = 8217;
            if ( _bittest(&v65, v64) )
              CCrashSignature::UpdateModuleForLoaderFailure(this);
          }
          v66 = GetTickCount();
          v67 = v66 - v75;
          if ( v75 > v66 )
            v67 = (unsigned int)(v67 - 1);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_dfe85b1dc90e3a8ff9b91b3f1e731dac_Traceguids, v67);
          SetDirEnvironmentVariableFromPath(L"moddir", *((const wchar_t **)this + 25));
          LODWORD(v71) = *((unsigned __int16 *)this + 59);
          LODWORD(lpUserTime) = *((unsigned __int16 *)this + 58);
          v68 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                  (char *)this + 136,
                  L"%u.%u.%u.%u",
                  *((unsigned __int16 *)this + 56),
                  *((unsigned __int16 *)this + 57),
                  lpUserTime,
                  v71);
          v12 = v68;
          if ( v68 >= 0 )
          {
            v68 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                    (char *)this + 168,
                    L"%08x",
                    *((unsigned int *)this + 30));
            v12 = v68;
            if ( v68 >= 0 )
            {
              LODWORD(v72) = *((unsigned __int16 *)this + 135);
              LODWORD(lpUserTimea) = *((unsigned __int16 *)this + 134);
              v68 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                      (char *)this + 280,
                      L"%u.%u.%u.%u",
                      *((unsigned __int16 *)this + 132),
                      *((unsigned __int16 *)this + 133),
                      lpUserTimea,
                      v72);
              v12 = v68;
              if ( v68 >= 0 )
              {
                v68 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                        (char *)this + 312,
                        L"%08x",
                        *((unsigned int *)this + 68));
                v12 = v68;
                if ( v68 >= 0 )
                {
                  v68 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                          (char *)this + 400,
                          L"%08x",
                          *((unsigned int *)this + 88));
                  v12 = v68;
                  if ( v68 >= 0 )
                  {
                    v68 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                            (char *)this + 368,
                            L"%016I64x",
                            *((_QWORD *)this + 43));
                    v12 = v68;
                    if ( v68 >= 0 )
                      return 0;
                    v17 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                    {
                      return v12;
                    }
                    v18 = 56;
                  }
                  else
                  {
                    v17 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                    {
                      return v12;
                    }
                    v18 = 55;
                  }
                }
                else
                {
                  v17 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                  {
                    return v12;
                  }
                  v18 = 54;
                }
              }
              else
              {
                v17 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                {
                  return v12;
                }
                v18 = 53;
              }
            }
            else
            {
              v17 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              {
                return v12;
              }
              v18 = 52;
            }
          }
          else
          {
            v17 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              return v12;
            v18 = 51;
          }
          v19 = (unsigned int)v68;
          goto LABEL_27;
        }
        v12 = -2147024882;
        v35 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return v12;
        v36 = 47;
      }
      else
      {
        v12 = -2147024882;
        v35 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return v12;
        v36 = 46;
      }
LABEL_63:
      WPP_SF_(v35[2], v36, WPP_dfe85b1dc90e3a8ff9b91b3f1e731dac_Traceguids);
      return v12;
    }
    v37 = GetLastError();
    if ( v37 > 0 )
      v37 = (unsigned __int16)v37 | 0x80070000;
    if ( v37 >= 0 )
      v37 = -2147467259;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        37,
        WPP_dfe85b1dc90e3a8ff9b91b3f1e731dac_Traceguids,
        (unsigned int)v37);
    packageFullNameLength = 260;
    if ( QueryFullProcessImageNameW(ProcessHandle, 0, me.szExePath, &packageFullNameLength) )
    {
      v42 = -1;
      v43 = -1;
      do
        ++v43;
      while ( me.szExePath[v43] );
      v34 = (LPCWSTR *)((char *)this + 16);
      if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                              (char *)this + 16,
                              me.szExePath,
                              v43) )
      {
        v33 = (char *)this + 48;
        v44 = -1;
        do
          ++v44;
        while ( me.szExePath[v44] );
        v45 = &me.szExePath[v44];
        if ( v45 <= me.szExePath )
        {
LABEL_100:
          v46 = v45;
        }
        else
        {
          while ( 1 )
          {
            v46 = v45--;
            v47 = *v45;
            LOWORD(v47) = v47 - 47;
            if ( (unsigned __int16)v47 <= 0x2Du )
            {
              v48 = 0x200000000801LL;
              if ( _bittest64(&v48, v47) )
                break;
            }
            if ( v45 <= me.szExePath )
              goto LABEL_100;
          }
        }
        if ( v46 )
        {
          do
            ++v42;
          while ( v46[v42] );
        }
        else
        {
          v42 = 0;
        }
        if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                (char *)this + 48,
                                v46,
                                v42) )
          goto LABEL_109;
        v12 = -2147024882;
        v40 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return v12;
        v41 = 42;
      }
      else
      {
        v12 = -2147024882;
        v40 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return v12;
        v41 = 41;
      }
    }
    else
    {
      v38 = GetLastError();
      v39 = v38 < 0;
      if ( v38 > 0 )
      {
        v38 = (unsigned __int16)v38 | 0x80070000;
        v39 = v38 < 0;
      }
      if ( !v39 )
        v38 = -2147467259;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          38,
          WPP_dfe85b1dc90e3a8ff9b91b3f1e731dac_Traceguids,
          (unsigned int)v38);
      v33 = (char *)this + 48;
      if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                              (char *)this + 48,
                              L"bad_module_info",
                              15) )
      {
        v34 = (LPCWSTR *)((char *)this + 16);
        if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                (char *)this + 16,
                                L"bad_module_info",
                                15) )
          goto LABEL_109;
        v12 = -2147024882;
        v40 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return v12;
        v41 = 40;
      }
      else
      {
        v12 = -2147024882;
        v40 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return v12;
        v41 = 39;
      }
    }
    WPP_SF_d(v40[2], v41, WPP_dfe85b1dc90e3a8ff9b91b3f1e731dac_Traceguids, 2147942414LL);
    return v12;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_dfe85b1dc90e3a8ff9b91b3f1e731dac_Traceguids);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180017498  mov     [rsp-8+arg_10], rbx
0x18001749d  push    rbp
0x18001749e  push    rsi
0x18001749f  push    rdi
0x1800174a0  push    r12
0x1800174a2  push    r13
0x1800174a4  push    r14
0x1800174a6  push    r15
0x1800174a8  lea     rbp, [rsp-630h]
0x1800174b0  sub     rsp, 730h
0x1800174b7  mov     rax, cs:__security_cookie
0x1800174be  xor     rax, rsp
0x1800174c1  mov     [rbp+660h+var_40], rax
0x1800174c8  mov     rbx, r8
0x1800174cb  mov     [rsp+760h+var_6F0], r9
0x1800174d0  mov     r15, rdx
0x1800174d3  mov     rdi, rcx
0x1800174d6  mov     r12d, 438h
0x1800174dc  lea     rcx, [rbp+660h+me]; void *
0x1800174e0  mov     r8d, r12d; Size
0x1800174e3  xor     edx, edx; Val
0x1800174e5  call    memset_0
0x1800174ea  xor     r13d, r13d
0x1800174ed  lea     rax, aMscorwksDll; "mscorwks.dll"
0x1800174f4  mov     [rsp+760h+var_6E8], rax
0x1800174f9  lea     rax, aMscorsvrDll; "mscorsvr.dll"
0x180017500  mov     [rbp+660h+var_6E0], rax
0x180017504  lea     rax, aClrDll; "clr.dll"
0x18001750b  mov     [rbp+660h+var_6D8], rax
0x18001750f  lea     rax, aCoreclrDll; "coreclr.dll"
0x180017516  mov     [rbp+660h+var_6D0], rax
0x18001751a  mov     qword ptr [rsp+760h+CreationTime.dwLowDateTime], r13
0x18001751f  mov     qword ptr [rsp+760h+ExitTime.dwLowDateTime], r13
0x180017524  mov     qword ptr [rsp+760h+KernelTime.dwLowDateTime], r13
0x180017529  mov     qword ptr [rsp+760h+UserTime.dwLowDateTime], r13
0x18001752e  mov     [rsp+760h+var_720], r13d
0x180017533  test    r15, r15
0x180017536  jnz     short loc_18001756F
0x180017538  mov     rcx, cs:WPP_GLOBAL_Control
0x18001753f  lea     rsi, WPP_GLOBAL_Control
0x180017546  cmp     rcx, rsi
0x180017549  jz      short loc_180017565
0x18001754b  test    byte ptr [rcx+1Ch], 1
0x18001754f  jz      short loc_180017565
0x180017551  mov     rcx, [rcx+10h]
0x180017555  lea     edx, [r13+22h]
0x180017559  lea     r8, WPP_dfe85b1dc90e3a8ff9b91b3f1e731dac_Traceguids
0x180017560  call    WPP_SF_
0x180017565  mov     eax, 80070057h
0x18001756a  jmp     loc_18001809A
0x18001756f  mov     rcx, r15; Process
0x180017572  call    cs:__imp_GetProcessId
0x180017578  mov     r14d, eax
0x18001757b  test    eax, eax
0x18001757d  jnz     short loc_1800175CF
0x18001757f  mov     rcx, cs:WPP_GLOBAL_Control
0x180017586  lea     rsi, WPP_GLOBAL_Control
0x18001758d  cmp     rcx, rsi
0x180017590  jz      short loc_1800175AB
0x180017592  test    byte ptr [rcx+1Ch], 1
0x180017596  jz      short loc_1800175AB
0x180017598  mov     rcx, [rcx+10h]
0x18001759c  lea     edx, [rax+23h]
0x18001759f  lea     r8, WPP_dfe85b1dc90e3a8ff9b91b3f1e731dac_Traceguids
0x1800175a6  call    WPP_SF_
0x1800175ab  call    cs:__imp_GetLastError
0x1800175b1  mov     ebx, eax
0x1800175b3  test    eax, eax
0x1800175b5  jle     short loc_1800175C0
0x1800175b7  movzx   ebx, ax
0x1800175ba  or      ebx, 80070000h
0x1800175c0  test    ebx, ebx
0x1800175c2  mov     eax, 80004005h
0x1800175c7  cmovns  ebx, eax
0x1800175ca  jmp     loc_180018098
0x1800175cf  mov     [rbp+660h+Filename], r13w
0x1800175d7  call    cs:__imp_GetTickCount
0x1800175dd  mov     ecx, [rbp+660h+arg_20]
0x1800175e3  mov     [rdi+160h], ecx
0x1800175e9  mov     rcx, [rbp+660h+arg_28]
0x1800175f0  mov     [rdi+168h], rcx
0x1800175f7  mov     [rdi+158h], rcx
0x1800175fe  mov     rcx, r15; Process
0x180017601  mov     [rsp+760h+var_718], eax
0x180017605  mov     [rdi], rbx
0x180017608  call    cs:__imp_GetProcessId
0x18001760e  mov     [rdi+7Ch], eax
0x180017611  mov     [rdi+8], r15
0x180017615  mov     [rsp+760h+packageFullNameLength], r13d
0x18001761a  call    IsGetPackageFullNamePresent
0x18001761f  test    al, al
0x180017621  jnz     short loc_180017631
0x180017623  call    IsXerGetPackageIdentityPresent
0x180017628  test    al, al
0x18001762a  jnz     short loc_180017631
0x18001762c  mov     ecx, r13d
0x18001762f  jmp     short loc_18001766B
0x180017631  call    IsGetPackageFullNamePresent
0x180017636  xor     r8d, r8d; packageFullName
0x180017639  lea     rdx, [rsp+760h+packageFullNameLength]; packageFullNameLength
0x18001763e  mov     rcx, r15; hProcess
0x180017641  test    al, al
0x180017643  jz      short loc_180017652
0x180017645  call    cs:__imp_GetPackageFullName
0x18001764b  cmp     eax, 3D54h
0x180017650  jmp     short loc_180017665
0x180017652  xor     r9d, r9d
0x180017655  mov     [rsp+760h+lpUserTime], r13
0x18001765a  call    cs:__imp_XerGetPackageIdentity
0x180017660  cmp     eax, 80073D54h
0x180017665  mov     ecx, r13d
0x180017668  setnz   cl
0x18001766b  mov     [rdi+1B8h], ecx
0x180017671  test    ecx, ecx
0x180017673  jz      loc_180017703
0x180017679  lea     rdx, [rdi+1C0h]
0x180017680  mov     rcx, r15; hProcess
0x180017683  call    ?GetProcessPackageFullName@PackageUtility@@SAJPEAXPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; PackageUtility::GetProcessPackageFullName(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180017688  mov     ebx, eax
0x18001768a  test    eax, eax
0x18001768c  jns     short loc_1800176CC
0x18001768e  mov     rcx, cs:WPP_GLOBAL_Control
0x180017695  lea     rsi, WPP_GLOBAL_Control
0x18001769c  cmp     rcx, rsi
0x18001769f  jz      loc_180018098
0x1800176a5  test    byte ptr [rcx+1Ch], 1
0x1800176a9  jz      loc_180018098
0x1800176af  mov     edx, 24h ; '$'
0x1800176b4  mov     r9d, eax
0x1800176b7  lea     r8, WPP_dfe85b1dc90e3a8ff9b91b3f1e731dac_Traceguids
0x1800176be  mov     rcx, [rcx+10h]
0x1800176c2  call    WPP_SF_d
0x1800176c7  jmp     loc_180018098
0x1800176cc  lea     rsi, [rdi+200h]
0x1800176d3  mov     rcx, r15; ProcessHandle
0x1800176d6  mov     rdx, rsi
0x1800176d9  call    ?GetProcessApplicationId@PackageUtility@@SAJPEAXPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; PackageUtility::GetProcessApplicationId(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x1800176de  test    eax, eax
0x1800176e0  js      short loc_180017703
0x1800176e2  mov     rcx, [rsi]
0x1800176e5  lea     rbx, [rdi+1E0h]
0x1800176ec  mov     r8, rbx
0x1800176ef  call    ?ParseApplicationId@PackageUtility@@SAJPEB_WPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@1@Z; PackageUtility::ParseApplicationId(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x1800176f4  test    eax, eax
0x1800176f6  jns     short loc_180017703
0x1800176f8  mov     rcx, [rbx]
0x1800176fb  mov     [rbx+8], rcx
0x1800176ff  mov     [rcx], r13w
0x180017703  lea     rax, [rsp+760h+UserTime]
0x180017708  mov     rcx, r15; hProcess
0x18001770b  lea     r9, [rsp+760h+KernelTime]; lpKernelTime
0x180017710  mov     [rsp+760h+lpUserTime], rax; lpUserTime
0x180017715  lea     r8, [rsp+760h+ExitTime]; lpExitTime
0x18001771a  lea     rdx, [rsp+760h+CreationTime]; lpCreationTime
0x18001771f  call    cs:__imp_GetProcessTimes
0x180017725  test    eax, eax
0x180017727  jz      short loc_180017735
0x180017729  mov     rax, qword ptr [rsp+760h+CreationTime.dwLowDateTime]
0x18001772e  mov     [rdi+80h], rax
0x180017735  mov     edx, r14d; th32ProcessID
0x180017738  mov     ecx, 8; dwFlags
0x18001773d  call    cs:__imp_CreateToolhelp32Snapshot
0x180017743  mov     rcx, [rdi+290h]; hObject
0x18001774a  mov     [rdi+290h], rax
0x180017751  lea     rax, [rcx+1]
0x180017755  cmp     rax, 1
0x180017759  jbe     short loc_180017761
0x18001775b  call    cs:__imp_CloseHandle
0x180017761  mov     rcx, [rdi+290h]; hSnapshot
0x180017768  lea     rax, [rcx+1]
0x18001776c  cmp     rax, 1
0x180017770  jbe     loc_180017904
0x180017776  lea     rdx, [rbp+660h+me]; lpme
0x18001777a  mov     [rbp+660h+me.dwSize], r12d
0x18001777e  call    cs:__imp_Module32FirstW
0x180017784  test    eax, eax
0x180017786  jnz     short loc_1800177D5
0x180017788  call    cs:__imp_GetLastError
0x18001778e  mov     ebx, eax
0x180017790  test    eax, eax
0x180017792  jle     short loc_18001779D
0x180017794  movzx   ebx, ax
0x180017797  or      ebx, 80070000h
0x18001779d  test    ebx, ebx
0x18001779f  mov     eax, 80004005h
0x1800177a4  cmovns  ebx, eax
0x1800177a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800177ae  lea     rsi, WPP_GLOBAL_Control
0x1800177b5  cmp     rcx, rsi
0x1800177b8  jz      loc_180018098
0x1800177be  test    byte ptr [rcx+1Ch], 1
0x1800177c2  jz      loc_180018098
0x1800177c8  mov     edx, 2Bh ; '+'
0x1800177cd  mov     r9d, ebx
0x1800177d0  jmp     loc_1800176B7
0x1800177d5  mov     rdx, [rbp+660h+me.hModule]; hModule
0x1800177d9  lea     r8, [rbp+660h+Filename]; lpFilename
0x1800177e0  mov     r12d, 104h
0x1800177e6  mov     rcx, r15; hProcess
0x1800177e9  mov     r9d, r12d; nSize
0x1800177ec  call    cs:__imp_K32GetModuleFileNameExW
0x1800177f2  lea     rsi, WPP_GLOBAL_Control
0x1800177f9  mov     ebx, 80004005h
0x1800177fe  lea     r14, WPP_dfe85b1dc90e3a8ff9b91b3f1e731dac_Traceguids
0x180017805  test    eax, eax
0x180017807  jnz     loc_180017893
0x18001780d  call    cs:__imp_GetLastError
0x180017813  test    eax, eax
0x180017815  jle     short loc_180017821
0x180017817  movzx   eax, ax
0x18001781a  or      eax, 80070000h
0x18001781f  test    eax, eax
0x180017821  cmovns  eax, ebx
0x180017824  mov     rcx, cs:WPP_GLOBAL_Control
0x18001782b  cmp     rcx, rsi
0x18001782e  jz      short loc_18001784A
0x180017830  test    byte ptr [rcx+1Ch], 1
0x180017834  jz      short loc_18001784A
0x180017836  mov     rcx, [rcx+10h]
0x18001783a  mov     edx, 2Ch ; ','
0x18001783f  mov     r9d, eax
0x180017842  mov     r8, r14
0x180017845  call    WPP_SF_d
0x18001784a  mov     ecx, 7FFFFFFEh
0x18001784f  lea     r8, [rbp+660h+me.szExePath]
0x180017856  mov     rdx, r12
0x180017859  lea     rax, [rbp+660h+Filename]
0x180017860  test    rcx, rcx
0x180017863  jz      short loc_180017884
0x180017865  movzx   r9d, word ptr [r8]
0x180017869  test    r9w, r9w
0x18001786d  jz      short loc_180017884
0x18001786f  mov     [rax], r9w
0x180017873  add     r8, 2
0x180017877  add     rax, 2
0x18001787b  dec     rcx
0x18001787e  sub     rdx, 1
0x180017882  jnz     short loc_180017860
0x180017884  test    rdx, rdx
0x180017887  lea     rcx, [rax-2]
0x18001788b  cmovnz  rcx, rax
0x18001788f  mov     [rcx], r13w
0x180017893  mov     r9, [rbp+660h+me.hModule]
0x180017897  lea     rax, [rdi+78h]
0x18001789b  mov     [rsp+760h+var_728], rax
0x1800178a0  lea     rcx, [rdi+70h]
0x1800178a4  mov     [rsp+760h+var_730], rcx
0x1800178a9  lea     r12, [rdi+30h]
0x1800178ad  lea     r13, [rdi+10h]
0x1800178b1  mov     [rsp+760h+var_738], r12
0x1800178b6  lea     r8, [rbp+660h+Filename]
0x1800178bd  mov     [rsp+760h+lpUserTime], r13
0x1800178c2  mov     rdx, r15
0x1800178c5  call    ?SetModuleInfo@CCrashSignature@@AEAAJPEAXPEB_WPEAUHINSTANCE__@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@3QEAGPEAK@Z; CCrashSignature::SetModuleInfo(void *,wchar_t const *,HINSTANCE__ *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,ushort * const,ulong *)
0x1800178ca  mov     ebx, eax
0x1800178cc  test    eax, eax
0x1800178ce  jns     loc_180017B68
0x1800178d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800178db  cmp     rcx, rsi
0x1800178de  jz      loc_180018098
0x1800178e4  test    byte ptr [rcx+1Ch], 1
0x1800178e8  jz      loc_180018098
0x1800178ee  mov     edx, 2Dh ; '-'
0x1800178f3  mov     rcx, [rcx+10h]
0x1800178f7  mov     r8, r14
0x1800178fa  call    WPP_SF_
0x1800178ff  jmp     loc_180018098
0x180017904  call    cs:__imp_GetLastError
0x18001790a  mov     ebx, 80070000h
0x18001790f  test    eax, eax
0x180017911  jle     short loc_180017918
0x180017913  movzx   eax, ax
0x180017916  or      eax, ebx
0x180017918  test    eax, eax
0x18001791a  mov     r12d, 80004005h
0x180017920  cmovns  eax, r12d
0x180017924  mov     rcx, cs:WPP_GLOBAL_Control
0x18001792b  lea     rsi, WPP_GLOBAL_Control
0x180017932  lea     r14, WPP_dfe85b1dc90e3a8ff9b91b3f1e731dac_Traceguids
0x180017939  cmp     rcx, rsi
0x18001793c  jz      short loc_180017958
0x18001793e  test    byte ptr [rcx+1Ch], 1
0x180017942  jz      short loc_180017958
0x180017944  mov     rcx, [rcx+10h]
0x180017948  mov     edx, 25h ; '%'
0x18001794d  mov     r9d, eax
0x180017950  mov     r8, r14
0x180017953  call    WPP_SF_d
0x180017958  lea     r9, [rsp+760h+packageFullNameLength]; lpdwSize
0x18001795d  mov     [rsp+760h+packageFullNameLength], 104h
0x180017965  lea     r8, [rbp+660h+me.szExePath]; lpExeName
0x18001796c  xor     edx, edx; dwFlags
0x18001796e  mov     rcx, r15; hProcess
0x180017971  call    cs:__imp_QueryFullProcessImageNameW
0x180017977  test    eax, eax
0x180017979  jnz     loc_180017A55
0x18001797f  call    cs:__imp_GetLastError
0x180017985  test    eax, eax
0x180017987  jle     short loc_180017990
0x180017989  movzx   eax, ax
  ... truncated ...
```
