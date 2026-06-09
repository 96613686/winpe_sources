# CCOMComponentRegistrar::TestUserDll(FileInfo1 *,ulong,ulong *,long *)

- ea: `0x180009f84`
- end: `0x18000a8f6`
- name: `?TestUserDll@CCOMComponentRegistrar@@AEAAJPEAUFileInfo1@@KPEAKPEAJ@Z`
- size: `2418`
- prototype: `__int64 __fastcall(CCOMComponentRegistrar *__hidden this, struct FileInfo1 *, unsigned int, unsigned int *, int *)`
- caller_count: `3`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000b640`
- `0x180031050`
- `0x1800325e0`

## callees

- `0x180001e60`
- `0x1800074d8`
- `0x180007a4c`
- `0x180009f84`
- `0x18000a8fc`
- `0x1800133d4`
- `0x180017d10`
- `0x18001c6a4`
- `0x180021720`
- `0x1800275d4`
- `0x180043b94`
- `0x180043c14`
- `0x18005583a`
- `0x180055880`
- `0x180055940`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000a72d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000a72d`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000a1b3`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000a1b3`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000a1d8`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000a1d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a118`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a66c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a6ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a118`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a66c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a6ab`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000a699`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000a699`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000a89b`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000a89b`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18000a659`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18000a659`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18000a5df`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18000a5df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a745`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a74f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a87e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a88d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a8ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a745`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a74f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a87e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a88d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a8ad`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18000a71c`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18000a71c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000a10e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000a10e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000a0f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000a0f0`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18000a73b`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18000a73b`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000a163`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000a163`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64DirectoryW` at `0x18000a204`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64DirectoryW` at `0x18000a204`
- `api-ms-win-core-com-private-l1-1-0!CoGetModuleType` at `0x18000a0c8`
- `api-ms-win-core-com-private-l1-1-0!CoGetModuleType` at `0x18000a0c8`

## string_xrefs

- `0x18000a388`: `%s\RunDll32.exe`
- `0x18000a3cd`: `%s\RunDll32 %s\catsrvut.dll,QueryUserDll "%s" %s`
- `0x18000a541`: `RunDll32.exe`
- `0x18000a570`: `RunDll32 catsrvut.dll,QueryUserDll "%s" %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CCOMComponentRegistrar::TestUserDll(
        CCOMComponentRegistrar *this,
        struct FileInfo1 *a2,
        unsigned int a3,
        unsigned int *a4,
        int *a5)
{
  unsigned int *v5; // r13
  unsigned int v6; // r12d
  int v9; // r14d
  HWND v10; // rcx
  HINSTANCE v11; // rdx
  unsigned int v12; // ecx
  unsigned __int16 *v13; // r15
  int v14; // edi
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  unsigned int v17; // eax
  UINT SystemWow64DirectoryW; // eax
  __int64 v19; // rdi
  unsigned __int64 v20; // r13
  unsigned __int16 *p_ModuleType; // rsi
  __int64 v22; // rcx
  unsigned __int64 v23; // rcx
  void *v24; // rsp
  void *v25; // rsp
  unsigned __int16 *v26; // rax
  WCHAR *v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // rax
  __int64 v30; // rax
  unsigned __int64 v31; // r15
  unsigned __int16 *p_lpEnvironment; // rdi
  unsigned __int64 v33; // rcx
  __int64 v34; // rcx
  void *v35; // rsp
  void *v36; // rsp
  unsigned __int16 *v37; // rax
  unsigned int *v38; // r15
  unsigned __int16 *v39; // rax
  __int64 v40; // rcx
  __int64 v41; // rax
  __int64 v42; // rax
  unsigned __int64 v43; // r15
  __int64 v44; // r14
  unsigned __int64 v45; // r14
  void *v46; // rsp
  void *v47; // rsp
  unsigned __int16 *v48; // rax
  __int64 v49; // r8
  HANDLE v50; // rax
  signed int v51; // eax
  unsigned int *v52; // rax
  unsigned int *v53; // r15
  signed int v54; // eax
  DWORD v55; // eax
  _BYTE v57[32]; // [rsp-20h] [rbp-90h] BYREF
  TOKEN_TYPE v58[8]; // [rsp+10h] [rbp-60h] BYREF
  DWORD dwCreationFlags[2]; // [rsp+40h] [rbp-30h] BYREF
  LPVOID lpEnvironment; // [rsp+48h] [rbp-28h] BYREF
  int ModuleType; // [rsp+70h] [rbp+0h] BYREF
  unsigned int *v62; // [rsp+78h] [rbp+8h] BYREF
  int v63; // [rsp+80h] [rbp+10h] BYREF
  DWORD ExitCode; // [rsp+84h] [rbp+14h] BYREF
  void *v65; // [rsp+88h] [rbp+18h]
  void *TokenHandle; // [rsp+90h] [rbp+20h] BYREF
  HANDLE hObject; // [rsp+98h] [rbp+28h]
  unsigned int *v68; // [rsp+A0h] [rbp+30h]
  unsigned __int16 *v69; // [rsp+A8h] [rbp+38h]
  unsigned __int16 *v70; // [rsp+B0h] [rbp+40h]
  int *v71; // [rsp+B8h] [rbp+48h]
  HANDLE hToken; // [rsp+C0h] [rbp+50h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+C8h] [rbp+58h] BYREF
  void *ppInterface; // [rsp+E0h] [rbp+70h] BYREF
  int v75; // [rsp+E8h] [rbp+78h]
  __int64 v76; // [rsp+F0h] [rbp+80h]
  unsigned int *v77; // [rsp+F8h] [rbp+88h]
  _DWORD *v78; // [rsp+100h] [rbp+90h]
  _DWORD *v79; // [rsp+108h] [rbp+98h]
  struct _SECURITY_ATTRIBUTES FileMappingAttributes; // [rsp+110h] [rbp+A0h] BYREF
  _BYTE pSecurityDescriptor[56]; // [rsp+128h] [rbp+B8h] BYREF
  struct _SYSTEM_INFO SystemInfo; // [rsp+160h] [rbp+F0h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+190h] [rbp+120h] BYREF
  GUID pguid; // [rsp+200h] [rbp+190h] BYREF
  WCHAR Name[7]; // [rsp+210h] [rbp+1A0h] BYREF
  OLECHAR sz[41]; // [rsp+21Eh] [rbp+1AEh] BYREF
  WCHAR Buffer[264]; // [rsp+270h] [rbp+200h] BYREF

  v5 = a4;
  v77 = a4;
  v6 = a3;
  v71 = a5;
  v68 = a4;
  v9 = -2147467259;
  ModuleType = -2147467259;
  TokenHandle = 0;
  hToken = 0;
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  ExitCode = 0;
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  hObject = 0;
  memset(&FileMappingAttributes, 0, sizeof(FileMappingAttributes));
  ppInterface = 0;
  v75 = 0;
  v76 = 0;
  *a5 = -2147467259;
  if ( !a2 || (v6 & 0xFFFFFC00) != 0 || !v5 )
  {
    ModuleType = -2147024809;
    goto LABEL_107;
  }
  v78 = (_DWORD *)((char *)a2 + 56);
  v10 = (HWND)*((unsigned int *)a2 + 14);
  v11 = (HINSTANCE)((char *)a2 + 60);
  v79 = (_DWORD *)((char *)a2 + 60);
  if ( (v6 & (*((_DWORD *)a2 + 15) | (unsigned int)v10)) == v6 )
  {
    ModuleType = 0;
    v12 = v6 & (unsigned int)v10;
    *v5 = v12;
    *a5 = v6 != v12 ? 0x80004005 : 0;
LABEL_107:
    v38 = 0;
    goto LABEL_108;
  }
  v13 = *(unsigned __int16 **)a2;
  v62 = *(unsigned int **)a2;
  if ( *((_DWORD *)this + 35) )
  {
    p_lpEnvironment = 0;
    p_ModuleType = 0;
    *v71 = InternalQueryUserDll(v10, v11, v13, 0, v6, v5, dwCreationFlags[0]);
    v38 = 0;
LABEL_93:
    *v78 |= *v5;
    *v79 |= *v5 ^ v6;
    v55 = ExitCode;
    if ( ExitCode && v9 >= 0 )
    {
      if ( (int)ExitCode > 0 )
        v55 = (unsigned __int16)ExitCode | 0x80070000;
      ModuleType = v55;
    }
    goto LABEL_98;
  }
  v63 = 0;
  ModuleType = CoGetModuleType(v13, &v63);
  if ( ModuleType < 0 )
    goto LABEL_107;
  v14 = v63;
  ModuleType = CImpersonate::ImpersonateClient(&ppInterface);
  if ( ModuleType < 0 )
    goto LABEL_107;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) )
    goto LABEL_10;
  ModuleType = CImpersonate::SuspendImpersonation((CImpersonate *)&ppInterface);
  if ( ModuleType < 0 )
    goto LABEL_107;
  if ( !DuplicateTokenEx(TokenHandle, 0xF01FFu, 0, SecurityImpersonation, TokenPrimary, &hToken) )
    goto LABEL_10;
  memset_0(Name, 0, 0x5Eu);
  pguid = 0;
  ModuleType = StringCchCopyW(Name, 0x2Fu, L"Global\\");
  if ( ModuleType < 0 )
    goto LABEL_107;
  ModuleType = CoCreateGuid(&pguid);
  if ( ModuleType < 0 )
    goto LABEL_107;
  v17 = StringFromGUID2(&pguid, sz, 39);
  if ( !v17 || v17 > 0x27 )
  {
    ModuleType = -2147418113;
    goto LABEL_107;
  }
  if ( v14 != 2 )
  {
    SystemWow64DirectoryW = GetSystemWow64DirectoryW(Buffer, 0x104u);
    if ( SystemWow64DirectoryW )
    {
      v19 = SystemWow64DirectoryW;
      v20 = 2LL * SystemWow64DirectoryW + 28;
      p_ModuleType = 0;
      if ( v20 > g_ulMaxStackAllocSize
        || v20 + g_ulAdditionalProbeSize + 8 < v20
        || !(unsigned int)((__int64 (*)(void))VerifyStackAvailable)() )
      {
        goto LABEL_124;
      }
      v22 = v20 + 23;
      if ( v20 + 23 <= v20 + 8 )
        v22 = 0xFFFFFFFFFFFFFF0LL;
      v23 = v22 & 0xFFFFFFFFFFFFFFF0uLL;
      v24 = alloca(v23);
      v25 = alloca(v23);
      p_ModuleType = (unsigned __int16 *)&ModuleType;
      if ( v58 == (TOKEN_TYPE *)-96LL || (ModuleType = 1801679955, (p_ModuleType = (unsigned __int16 *)&v62) == 0) )
      {
LABEL_124:
        if ( v20 + 8 >= v20 )
        {
          v26 = (unsigned __int16 *)((__int64 (*)(void))g_pfnAllocate)();
          p_ModuleType = v26;
          if ( v26 )
          {
            *(_DWORD *)v26 = 1885431112;
            p_ModuleType = v26 + 4;
          }
        }
      }
      v70 = p_ModuleType;
      v27 = Name;
      v28 = -1;
      v29 = -1;
      do
        ++v29;
      while ( Name[v29] );
      do
        ++v28;
      while ( v13[v28] );
      v30 = v28 + v29 + 2 * v19;
      v31 = 2 * v30 + 92;
      p_lpEnvironment = 0;
      if ( 2 * v30 == -92 )
        goto LABEL_125;
      if ( v31 > g_ulMaxStackAllocSize )
        goto LABEL_125;
      v33 = v31 + g_ulAdditionalProbeSize + 8;
      if ( v33 < v31 || !(unsigned int)VerifyStackAvailable(v33, Name) )
        goto LABEL_125;
      v34 = v31 + 23;
      if ( v31 + 23 <= v31 + 8 )
        v34 = 0xFFFFFFFFFFFFFF0LL;
      v35 = alloca(v34 & 0xFFFFFFFFFFFFFFF0uLL);
      v36 = alloca(v34 & 0xFFFFFFFFFFFFFFF0uLL);
      p_lpEnvironment = (unsigned __int16 *)&ModuleType;
      if ( v58 == (TOKEN_TYPE *)-96LL || (ModuleType = 1801679955, (p_lpEnvironment = (unsigned __int16 *)&v62) == 0) )
      {
LABEL_125:
        if ( v31 + 8 >= v31 )
        {
          v37 = (unsigned __int16 *)((__int64 (__fastcall *)(unsigned __int64, WCHAR *))g_pfnAllocate)(v31 + 8, v27);
          p_lpEnvironment = v37;
          if ( v37 )
          {
            *(_DWORD *)v37 = 1885431112;
            p_lpEnvironment = v37 + 4;
          }
        }
      }
      v69 = p_lpEnvironment;
      if ( p_ModuleType && p_lpEnvironment )
      {
        ModuleType = StringCbPrintfW(p_ModuleType, v20, L"%s\\RunDll32.exe", Buffer);
        if ( ModuleType >= 0 )
        {
          ModuleType = StringCbPrintfW(
                         p_lpEnvironment,
                         v31,
                         L"%s\\RunDll32 %s\\catsrvut.dll,QueryUserDll \"%s\" %s",
                         Buffer,
                         Buffer,
                         v62,
                         Name);
          if ( ModuleType >= 0 )
            goto LABEL_78;
        }
LABEL_100:
        v38 = 0;
        goto LABEL_101;
      }
LABEL_50:
      ModuleType = -2147024882;
LABEL_51:
      v38 = 0;
      goto LABEL_98;
    }
LABEL_10:
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    ModuleType = LastError;
    goto LABEL_107;
  }
  if ( (unsigned __int64)g_ulMaxStackAllocSize < 0x1C
    || (unsigned __int64)(g_ulAdditionalProbeSize + 36) < 0x1C
    || !(unsigned int)((__int64 (*)(void))VerifyStackAvailable)()
    || v57 == (_BYTE *)-96LL
    || (dwCreationFlags[0] = 1801679955, (p_ModuleType = (unsigned __int16 *)&lpEnvironment) == 0) )
  {
    v39 = (unsigned __int16 *)((__int64 (__fastcall *)(__int64))g_pfnAllocate)(36);
    p_ModuleType = v39;
    if ( v39 )
    {
      *(_DWORD *)v39 = 1885431112;
      p_ModuleType = v39 + 4;
    }
  }
  v70 = p_ModuleType;
  v40 = -1;
  do
    ++v40;
  while ( Name[v40] );
  v41 = -1;
  do
    ++v41;
  while ( v13[v41] );
  v42 = v40 + v41;
  v43 = 2 * v42 + 80;
  p_lpEnvironment = 0;
  if ( 2 * v42 == -80
    || v43 > g_ulMaxStackAllocSize
    || v43 + g_ulAdditionalProbeSize + 8 < v43
    || !(unsigned int)((__int64 (*)(void))VerifyStackAvailable)() )
  {
    goto LABEL_126;
  }
  v44 = v43 + 23;
  if ( v43 + 23 <= v43 + 8 )
    v44 = 0xFFFFFFFFFFFFFF0LL;
  v45 = v44 & 0xFFFFFFFFFFFFFFF0uLL;
  v46 = alloca(v45);
  v47 = alloca(v45);
  p_lpEnvironment = (unsigned __int16 *)dwCreationFlags;
  if ( v57 == (_BYTE *)-96LL
    || (dwCreationFlags[0] = 1801679955, (p_lpEnvironment = (unsigned __int16 *)&lpEnvironment) == 0) )
  {
LABEL_126:
    if ( v43 + 8 >= v43 )
    {
      v48 = (unsigned __int16 *)((__int64 (*)(void))g_pfnAllocate)();
      p_lpEnvironment = v48;
      if ( v48 )
      {
        *(_DWORD *)v48 = 1885431112;
        p_lpEnvironment = v48 + 4;
      }
    }
  }
  v69 = p_lpEnvironment;
  if ( !p_ModuleType || !p_lpEnvironment )
    goto LABEL_50;
  ModuleType = StringCbCopyW(p_ModuleType, 0x1Cu, L"RunDll32.exe");
  if ( ModuleType < 0 )
    goto LABEL_100;
  ModuleType = StringCbPrintfW(p_lpEnvironment, v43, L"RunDll32 catsrvut.dll,QueryUserDll \"%s\" %s", v62, Name);
  if ( ModuleType < 0 )
    goto LABEL_100;
LABEL_78:
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  StartupInfo.cb = 104;
  memset(&StartupInfo.lpReserved, 0, 24);
  StartupInfo.dwFlags = 129;
  *(_DWORD *)&StartupInfo.wShowWindow = 6;
  StartupInfo.lpReserved2 = 0;
  GetSystemInfo(&SystemInfo);
  CSystemAndUserDescriptor::CSystemAndUserDescriptor(pSecurityDescriptor, TokenHandle, v49, (unsigned int *)&ModuleType);
  v9 = ModuleType;
  if ( ModuleType < 0 )
  {
LABEL_79:
    CSystemAndUserDescriptor::~CSystemAndUserDescriptor((CSystemAndUserDescriptor *)pSecurityDescriptor);
    goto LABEL_51;
  }
  FileMappingAttributes.nLength = 24;
  FileMappingAttributes.lpSecurityDescriptor = pSecurityDescriptor;
  FileMappingAttributes.bInheritHandle = 0;
  v50 = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, &FileMappingAttributes, 4u, 0, SystemInfo.dwPageSize, Name);
  hObject = v50;
  v65 = v50;
  if ( !v50 )
  {
    v51 = GetLastError();
    if ( v51 > 0 )
      v51 = (unsigned __int16)v51 | 0x80070000;
    ModuleType = v51;
    goto LABEL_79;
  }
  v52 = (unsigned int *)MapViewOfFile(v50, 2u, 0, 0, 0x10u);
  v53 = v52;
  v62 = v52;
  if ( v52 )
  {
    *v52 = v6;
    v52[1] = -2147467259;
    if ( CreateProcessAsUserW(
           hToken,
           p_ModuleType,
           p_lpEnvironment,
           0,
           0,
           0,
           8u,
           0,
           0,
           &StartupInfo,
           &ProcessInformation) )
    {
      WaitForSingleObject(ProcessInformation.hProcess, 0xFFFFFFFF);
      GetExitCodeProcess(ProcessInformation.hProcess, &ExitCode);
      CloseHandle(ProcessInformation.hProcess);
      CloseHandle(ProcessInformation.hThread);
      try
      {
        v5 = v77;
        *v77 = *v53;
        *v71 = v53[1];
      }
      catch ( ... )
      {
        *v68 = 0;
        ModuleType = -2147467259;
        v6 = a3;
        v9 = -2147467259;
        p_lpEnvironment = v69;
        p_ModuleType = v70;
        hObject = v65;
        v5 = v68;
      }
      v38 = v62;
      CSystemAndUserDescriptor::~CSystemAndUserDescriptor((CSystemAndUserDescriptor *)pSecurityDescriptor);
      goto LABEL_93;
    }
  }
  v54 = GetLastError();
  if ( v54 > 0 )
    v54 = (unsigned __int16)v54 | 0x80070000;
  ModuleType = v54;
  CSystemAndUserDescriptor::~CSystemAndUserDescriptor((CSystemAndUserDescriptor *)pSecurityDescriptor);
  v38 = v62;
LABEL_98:
  if ( p_lpEnvironment )
  {
LABEL_101:
    if ( *((_DWORD *)p_lpEnvironment - 2) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
  }
  if ( p_ModuleType && *((_DWORD *)p_ModuleType - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
LABEL_108:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( hToken )
    CloseHandle(hToken);
  if ( v38 )
    UnmapViewOfFile(v38);
  if ( hObject )
    CloseHandle(hObject);
  CImpersonate::Cleanup((CImpersonate *)&ppInterface, &ModuleType);
  CImpersonate::~CImpersonate((CImpersonate *)&ppInterface);
  return (unsigned int)ModuleType;
}

```

## disassembly

```asm
0x180009f84  mov     [rsp-8+arg_10], r8d
0x180009f89  push    rbp
0x180009f8a  push    rsi
0x180009f8b  push    rdi
0x180009f8c  push    r12
0x180009f8e  push    r13
0x180009f90  push    r14
0x180009f92  push    r15
0x180009f94  sub     rsp, 480h
0x180009f9b  lea     rbp, [rsp+60h]
0x180009fa0  mov     [rbp+450h+arg_0], rbx
0x180009fa7  mov     rax, cs:__security_cookie
0x180009fae  xor     rax, rbp
0x180009fb1  mov     [rbp+450h+var_40], rax
0x180009fb8  mov     r13, r9
0x180009fbb  mov     [rbp+450h+var_3C8], r9
0x180009fc2  mov     r12d, r8d
0x180009fc5  mov     rdi, rdx
0x180009fc8  mov     rsi, rcx
0x180009fcb  mov     rax, [rbp+450h+arg_20]
0x180009fd2  mov     [rbp+450h+var_408], rax
0x180009fd6  mov     [rbp+450h+var_420], r9
0x180009fda  mov     r14d, 80004005h
0x180009fe0  mov     [rbp+450h+var_450], r14d
0x180009fe4  xor     ebx, ebx
0x180009fe6  mov     [rbp+450h+TokenHandle], rbx
0x180009fea  mov     [rbp+450h+hToken], rbx
0x180009fee  xor     edx, edx; Val
0x180009ff0  lea     r8d, [rbx+68h]; Size
0x180009ff4  lea     rcx, [rbp+450h+StartupInfo]; void *
0x180009ffb  call    memset_0
0x18000a000  xorps   xmm0, xmm0
0x18000a003  xor     eax, eax
0x18000a005  movups  xmmword ptr [rbp+450h+ProcessInformation.hProcess], xmm0
0x18000a009  mov     qword ptr [rbp+450h+ProcessInformation.dwProcessId], rax
0x18000a00d  mov     [rbp+450h+ExitCode], ebx
0x18000a010  movups  xmmword ptr [rbp+450h+SystemInfo], xmm0
0x18000a017  movups  xmmword ptr [rbp+450h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x18000a01e  movups  xmmword ptr [rbp+450h+SystemInfo.dwNumberOfProcessors], xmm0
0x18000a025  mov     [rbp+450h+hObject], rbx
0x18000a029  movups  xmmword ptr [rbp+450h+FileMappingAttributes.nLength], xmm0
0x18000a030  mov     qword ptr [rbp+450h+FileMappingAttributes.bInheritHandle], rax
0x18000a037  mov     [rbp+450h+ppInterface], rbx
0x18000a03b  mov     [rbp+450h+var_3D8], ebx
0x18000a03e  mov     [rbp+450h+var_3D0], rbx
0x18000a045  mov     r8, [rbp+450h+var_408]
0x18000a049  mov     [r8], r14d
0x18000a04c  test    rdi, rdi
0x18000a04f  jz      loc_18000A86B
0x18000a055  test    r12d, 0FFFFFC00h
0x18000a05c  jnz     loc_18000A86B
0x18000a062  test    r13, r13
0x18000a065  jz      loc_18000A86B
0x18000a06b  lea     rax, [rdi+38h]
0x18000a06f  mov     [rbp+450h+var_3C0], rax
0x18000a076  mov     ecx, [rax]; HWND
0x18000a078  lea     rdx, [rdi+3Ch]; HINSTANCE
0x18000a07c  mov     [rbp+450h+var_3B8], rdx
0x18000a083  mov     eax, ecx
0x18000a085  or      eax, [rdx]
0x18000a087  and     eax, r12d
0x18000a08a  cmp     eax, r12d
0x18000a08d  jnz     short loc_18000A0AB
0x18000a08f  mov     [rbp+450h+var_450], ebx
0x18000a092  and     ecx, r12d
0x18000a095  mov     [r13+0], ecx
0x18000a099  sub     ecx, r12d
0x18000a09c  neg     ecx
0x18000a09e  sbb     eax, eax
0x18000a0a0  and     eax, r14d
0x18000a0a3  mov     [r8], eax
0x18000a0a6  jmp     loc_18000A872
0x18000a0ab  mov     r15, [rdi]
0x18000a0ae  mov     [rbp+450h+var_448], r15
0x18000a0b2  cmp     [rsi+8Ch], ebx
0x18000a0b8  jnz     loc_18000A7CE
0x18000a0be  mov     [rbp+450h+var_440], ebx
0x18000a0c1  lea     rdx, [rbp+450h+var_440]
0x18000a0c5  mov     rcx, r15
0x18000a0c8  call    cs:__imp_CoGetModuleType
0x18000a0ce  mov     [rbp+450h+var_450], eax
0x18000a0d1  test    eax, eax
0x18000a0d3  js      loc_18000A872
0x18000a0d9  mov     edi, [rbp+450h+var_440]
0x18000a0dc  lea     rcx, [rbp+450h+ppInterface]; ppInterface
0x18000a0e0  call    ?ImpersonateClient@CImpersonate@@QEAAJXZ; CImpersonate::ImpersonateClient(void)
0x18000a0e5  mov     [rbp+450h+var_450], eax
0x18000a0e8  test    eax, eax
0x18000a0ea  js      loc_18000A872
0x18000a0f0  call    cs:__imp_GetCurrentThread
0x18000a0f6  mov     rcx, rax; ThreadHandle
0x18000a0f9  lea     r9, [rbp+450h+TokenHandle]; TokenHandle
0x18000a0fd  mov     esi, 1
0x18000a102  mov     r8d, esi; OpenAsSelf
0x18000a105  mov     r14d, 0F01FFh
0x18000a10b  mov     edx, r14d; DesiredAccess
0x18000a10e  call    cs:__imp_OpenThreadToken
0x18000a114  test    eax, eax
0x18000a116  jnz     short loc_18000A132
0x18000a118  call    cs:__imp_GetLastError
0x18000a11e  test    eax, eax
0x18000a120  jle     short loc_18000A12A
0x18000a122  movzx   eax, ax
0x18000a125  or      eax, 80070000h
0x18000a12a  mov     [rbp+450h+var_450], eax
0x18000a12d  jmp     loc_18000A872
0x18000a132  lea     rcx, [rbp+450h+ppInterface]; this
0x18000a136  call    ?SuspendImpersonation@CImpersonate@@QEAAJXZ; CImpersonate::SuspendImpersonation(void)
0x18000a13b  mov     [rbp+450h+var_450], eax
0x18000a13e  test    eax, eax
0x18000a140  js      loc_18000A872
0x18000a146  lea     rax, [rbp+450h+hToken]
0x18000a14a  mov     [rsp+4B0h+phNewToken], rax; phNewToken
0x18000a14f  mov     [rsp+4B0h+TokenType], esi; TokenType
0x18000a153  mov     r9d, 2; ImpersonationLevel
0x18000a159  xor     r8d, r8d; lpTokenAttributes
0x18000a15c  mov     edx, r14d; dwDesiredAccess
0x18000a15f  mov     rcx, [rbp+450h+TokenHandle]; hExistingToken
0x18000a163  call    cs:__imp_DuplicateTokenEx
0x18000a169  test    eax, eax
0x18000a16b  jz      short loc_18000A118
0x18000a16d  xor     edx, edx; Val
0x18000a16f  lea     r8d, [rdx+5Eh]; Size
0x18000a173  lea     rcx, [rbp+450h+Name]; void *
0x18000a17a  call    memset_0
0x18000a17f  xorps   xmm0, xmm0
0x18000a182  movups  xmmword ptr [rbp+450h+pguid.Data1], xmm0
0x18000a189  lea     r8, aGlobal; "Global\\"
0x18000a190  mov     edx, 2Fh ; '/'; unsigned __int64
0x18000a195  lea     rcx, [rbp+450h+Name]; unsigned __int16 *
0x18000a19c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000a1a1  mov     [rbp+450h+var_450], eax
0x18000a1a4  test    eax, eax
0x18000a1a6  js      loc_18000A872
0x18000a1ac  lea     rcx, [rbp+450h+pguid]; pguid
0x18000a1b3  call    cs:__imp_CoCreateGuid
0x18000a1b9  mov     [rbp+450h+var_450], eax
0x18000a1bc  test    eax, eax
0x18000a1be  js      loc_18000A872
0x18000a1c4  mov     r8d, 27h ; '''; cchMax
0x18000a1ca  lea     rdx, [rbp+450h+sz]; lpsz
0x18000a1d1  lea     rcx, [rbp+450h+pguid]; rguid
0x18000a1d8  call    cs:__imp_StringFromGUID2
0x18000a1de  test    eax, eax
0x18000a1e0  jz      loc_18000A7C2
0x18000a1e6  cmp     eax, 27h ; '''
0x18000a1e9  ja      loc_18000A7C2
0x18000a1ef  cmp     edi, 2
0x18000a1f2  jz      loc_18000A402
0x18000a1f8  mov     edx, 104h; uSize
0x18000a1fd  lea     rcx, [rbp+450h+Buffer]; lpBuffer
0x18000a204  call    cs:__imp_GetSystemWow64DirectoryW
0x18000a20a  test    eax, eax
0x18000a20c  jz      loc_18000A118
0x18000a212  mov     edi, eax
0x18000a214  lea     r13, ds:1Ch[rdi*2]
0x18000a21c  mov     rsi, rbx
0x18000a21f  cmp     r13, cs:g_ulMaxStackAllocSize
0x18000a226  ja      short loc_18000A285
0x18000a228  mov     rcx, cs:g_ulAdditionalProbeSize
0x18000a22f  add     rcx, 8
0x18000a233  add     rcx, r13
0x18000a236  cmp     rcx, r13
0x18000a239  jb      short loc_18000A285
0x18000a23b  call    VerifyStackAvailable
0x18000a240  mov     r14, 0FFFFFFFFFFFFFF0h
0x18000a24a  test    eax, eax
0x18000a24c  jz      short loc_18000A28F
0x18000a24e  lea     rax, [r13+8]
0x18000a252  lea     rcx, [rax+0Fh]
0x18000a256  cmp     rcx, rax
0x18000a259  ja      short loc_18000A25E
0x18000a25b  mov     rcx, r14
0x18000a25e  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18000a262  mov     rax, rcx
0x18000a265  call    _alloca_probe
0x18000a26a  sub     rsp, rcx
0x18000a26d  lea     rsi, [rsp+4B0h+var_450]
0x18000a272  test    rsi, rsi
0x18000a275  jz      short loc_18000A28F
0x18000a277  mov     dword ptr [rsi], 6B637453h
0x18000a27d  add     rsi, 8
0x18000a281  jnz     short loc_18000A2B6
0x18000a283  jmp     short loc_18000A28F
0x18000a285  mov     r14, 0FFFFFFFFFFFFFF0h
0x18000a28f  lea     rcx, [r13+8]
0x18000a293  cmp     rcx, r13
0x18000a296  jb      short loc_18000A2B6
0x18000a298  mov     rax, cs:g_pfnAllocate
0x18000a29f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2a4  mov     rsi, rax
0x18000a2a7  test    rax, rax
0x18000a2aa  jz      short loc_18000A2B6
0x18000a2ac  mov     dword ptr [rax], 70616548h
0x18000a2b2  add     rsi, 8
0x18000a2b6  mov     [rbp+450h+var_410], rsi
0x18000a2ba  lea     rdx, [rbp+450h+Name]
0x18000a2c1  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000a2c5  mov     rax, rcx
0x18000a2c8  inc     rax
0x18000a2cb  cmp     [rdx+rax*2], bx
0x18000a2cf  jnz     short loc_18000A2C8
0x18000a2d1  inc     rcx
0x18000a2d4  cmp     [r15+rcx*2], bx
0x18000a2d9  jnz     short loc_18000A2D1
0x18000a2db  lea     rax, [rax+rdi*2]
0x18000a2df  add     rax, rcx
0x18000a2e2  lea     r15, ds:5Ch[rax*2]
0x18000a2ea  mov     rdi, rbx
0x18000a2ed  test    r15, r15
0x18000a2f0  jz      short loc_18000A34C
0x18000a2f2  cmp     r15, cs:g_ulMaxStackAllocSize
0x18000a2f9  ja      short loc_18000A34C
0x18000a2fb  mov     rcx, cs:g_ulAdditionalProbeSize
0x18000a302  add     rcx, 8
0x18000a306  add     rcx, r15
0x18000a309  cmp     rcx, r15
0x18000a30c  jb      short loc_18000A34C
0x18000a30e  call    VerifyStackAvailable
0x18000a313  test    eax, eax
0x18000a315  jz      short loc_18000A34C
0x18000a317  lea     rax, [r15+8]
0x18000a31b  lea     rcx, [rax+0Fh]
0x18000a31f  cmp     rcx, rax
0x18000a322  ja      short loc_18000A327
0x18000a324  mov     rcx, r14
0x18000a327  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18000a32b  mov     rax, rcx
0x18000a32e  call    _alloca_probe
0x18000a333  sub     rsp, rcx
0x18000a336  lea     rdi, [rsp+4B0h+var_450]
0x18000a33b  test    rdi, rdi
0x18000a33e  jz      short loc_18000A34C
0x18000a340  mov     dword ptr [rdi], 6B637453h
0x18000a346  add     rdi, 8
0x18000a34a  jnz     short loc_18000A373
0x18000a34c  lea     rcx, [r15+8]
0x18000a350  cmp     rcx, r15
0x18000a353  jb      short loc_18000A373
0x18000a355  mov     rax, cs:g_pfnAllocate
0x18000a35c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a361  mov     rdi, rax
0x18000a364  test    rax, rax
0x18000a367  jz      short loc_18000A373
0x18000a369  mov     dword ptr [rax], 70616548h
0x18000a36f  add     rdi, 8
0x18000a373  mov     [rbp+450h+var_418], rdi
0x18000a377  test    rsi, rsi
0x18000a37a  jz      short loc_18000A3F3
0x18000a37c  test    rdi, rdi
0x18000a37f  jz      short loc_18000A3F3
0x18000a381  lea     r9, [rbp+450h+Buffer]
0x18000a388  lea     r8, aSRundll32Exe; "%s\\RunDll32.exe"
0x18000a38f  mov     rdx, r13; unsigned __int64
0x18000a392  mov     rcx, rsi; unsigned __int16 *
0x18000a395  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a39a  mov     [rbp+450h+var_450], eax
0x18000a39d  test    eax, eax
0x18000a39f  js      loc_18000A831
0x18000a3a5  lea     rax, [rbp+450h+Name]
0x18000a3ac  mov     qword ptr [rsp+4B0h+dwCreationFlags], rax
0x18000a3b1  mov     r9, [rbp+450h+var_448]
0x18000a3b5  mov     [rsp+4B0h+phNewToken], r9
0x18000a3ba  lea     rax, [rbp+450h+Buffer]
0x18000a3c1  mov     qword ptr [rsp+4B0h+TokenType], rax
0x18000a3c6  lea     r9, [rbp+450h+Buffer]
0x18000a3cd  lea     r8, aSRundll32SCats; "%s\\RunDll32 %s\\catsrvut.dll,QueryUser"...
0x18000a3d4  mov     rdx, r15; unsigned __int64
0x18000a3d7  mov     rcx, rdi; unsigned __int16 *
0x18000a3da  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a3df  mov     [rbp+450h+var_450], eax
0x18000a3e2  test    eax, eax
0x18000a3e4  js      loc_18000A831
0x18000a3ea  or      r13, 0FFFFFFFFFFFFFFFFh
0x18000a3ee  jmp     loc_18000A58D
0x18000a3f3  mov     [rbp+450h+var_450], 8007000Eh
0x18000a3fa  mov     r15, rbx
0x18000a3fd  jmp     loc_18000A82A
0x18000a402  cmp     cs:g_ulMaxStackAllocSize, 1Ch
0x18000a40a  jb      short loc_18000A445
0x18000a40c  mov     rcx, cs:g_ulAdditionalProbeSize
0x18000a413  add     rcx, 24h ; '$'
0x18000a417  cmp     rcx, 1Ch
0x18000a41b  jb      short loc_18000A445
0x18000a41d  call    VerifyStackAvailable
0x18000a422  test    eax, eax
0x18000a424  jz      short loc_18000A445
0x18000a426  mov     eax, [rsp+4B0h+var_4B0]
0x18000a429  sub     rsp, 30h
0x18000a42d  lea     rsi, [rsp+4E0h+dwCreationFlags]
0x18000a432  mov     eax, [rsi]
0x18000a434  test    rsi, rsi
0x18000a437  jz      short loc_18000A445
0x18000a439  mov     dword ptr [rsi], 6B637453h
0x18000a43f  add     rsi, 8
0x18000a443  jnz     short loc_18000A468
0x18000a445  mov     ecx, 24h ; '$'
0x18000a44a  mov     rax, cs:g_pfnAllocate
0x18000a451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a456  mov     rsi, rax
  ... truncated ...
```
