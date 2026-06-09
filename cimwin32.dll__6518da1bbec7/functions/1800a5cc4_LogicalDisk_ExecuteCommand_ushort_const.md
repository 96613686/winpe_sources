# LogicalDisk::ExecuteCommand(ushort const *)

- ea: `0x1800a5cc4`
- end: `0x1800a629a`
- name: `?ExecuteCommand@LogicalDisk@@AEAAJPEBG@Z`
- size: `1494`
- prototype: `__int64 __fastcall(LogicalDisk *this, WCHAR *)`
- caller_count: `2`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800a5a80`
- `0x1800a5c00`

## callees

- `0x18000ab30`
- `0x18000bef0`
- `0x18000c910`
- `0x180013ae0`
- `0x1800226b4`
- `0x180030a04`
- `0x180030c98`
- `0x180031800`
- `0x180032fd8`
- `0x18004d944`
- `0x180051dd8`
- `0x18005dbac`
- `0x18006f1d0`
- `0x1800a5cc4`
- `0x1800f15b8`
- `0x1800f15d8`
- `0x1800fc902`
- `0x1800fc980`
- `0x180110010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1800a5df3`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1800a5df3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a61e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a61f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a61e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a61f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5e70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5f4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5f65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5f86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a6286`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5e70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5f4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5f65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5f86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a6286`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800a61bd`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800a61bd`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800a5d2e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800a5d2e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a5d18`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a5d18`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1800a6132`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1800a6132`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800a5e62`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800a5eb8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800a5e62`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800a5eb8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800a619b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800a619b`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800a5e19`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800a5e28`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800a5e19`
- `framedynos!??0CHString@@QEAA@XZ` at `0x1800a5e28`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800a5fb1`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800a5ff5`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800a5fb1`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x1800a5ff5`
- `framedynos!??4CHString@@QEAAAEBV0@AEBV0@@Z` at `0x1800a5f06`
- `framedynos!??4CHString@@QEAAAEBV0@AEBV0@@Z` at `0x1800a5f36`
- `framedynos!??4CHString@@QEAAAEBV0@AEBV0@@Z` at `0x1800a5f06`
- `framedynos!??4CHString@@QEAAAEBV0@AEBV0@@Z` at `0x1800a5f36`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x1800a5fa2`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x1800a5fa2`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x1800a603b`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x1800a603b`
- `framedynos!?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z` at `0x1800a5fcf`
- `framedynos!?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z` at `0x1800a5fcf`
- `framedynos!?Close@CRegistry@@QEAAXXZ` at `0x1800a5fe3`
- `framedynos!?Close@CRegistry@@QEAAXXZ` at `0x1800a5fe3`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800a5f12`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800a5f42`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800a621d`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800a622c`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800a5f12`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800a5f42`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800a621d`
- `framedynos!??1CHString@@QEAA@XZ` at `0x1800a622c`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
__int64 __fastcall LogicalDisk::ExecuteCommand(LogicalDisk *this, WCHAR *a2)
{
  unsigned int v3; // esi
  unsigned int LastError; // edi
  void **v5; // rbx
  HANDLE CurrentThread; // rax
  CResourceManager *v7; // rcx
  void *v8; // r8
  int v9; // r14d
  struct CResource *Resource; // rbx
  __int64 v11; // rcx
  __int64 (__fastcall *v12)(HANDLE, __int64, _QWORD, __int64, int, __int64); // rax
  void **v13; // rbx
  __int64 SidString; // rax
  __int64 AccountName; // rax
  const unsigned __int16 *v16; // rax
  int v17; // ebx
  const WCHAR *v18; // rax
  CResourceManager *v19; // rcx
  void *v20; // r8
  struct CResource *v21; // rax
  int v22; // r9d
  CUserEnvApi *v23; // r14
  int v24; // eax
  DWORD TokenInformationLength; // [rsp+64h] [rbp-D04h] BYREF
  BOOL TokenInformation; // [rsp+68h] [rbp-D00h]
  LPVOID lpEnvironment; // [rsp+70h] [rbp-CF8h] BYREF
  HANDLE TokenHandle; // [rsp+78h] [rbp-CF0h] BYREF
  DWORD ExitCode[2]; // [rsp+80h] [rbp-CE8h] BYREF
  struct CResource *v31; // [rsp+88h] [rbp-CE0h]
  HANDLE hToken; // [rsp+90h] [rbp-CD8h] BYREF
  _BYTE v33[8]; // [rsp+98h] [rbp-CD0h] BYREF
  struct _GUID v34; // [rsp+A0h] [rbp-CC8h] BYREF
  int v35; // [rsp+B0h] [rbp-CB8h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+B8h] [rbp-CB0h] BYREF
  int v37; // [rsp+E0h] [rbp-C88h]
  struct _GUID v38; // [rsp+F0h] [rbp-C78h] BYREF
  struct _GUID v39; // [rsp+100h] [rbp-C68h] BYREF
  GUID v40; // [rsp+110h] [rbp-C58h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+120h] [rbp-C48h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+190h] [rbp-BD8h] BYREF
  __int64 v43; // [rsp+2A8h] [rbp-AC0h]
  __int64 v44; // [rsp+2B0h] [rbp-AB8h]
  int v45; // [rsp+2B8h] [rbp-AB0h]
  _BYTE v46[608]; // [rsp+2C0h] [rbp-AA8h] BYREF
  WCHAR SubKey[1024]; // [rsp+520h] [rbp-848h] BYREF

  v3 = -2147217407;
  LastError = 0;
  hToken = (HANDLE)-1LL;
  TokenHandle = (HANDLE)-1LL;
  v5 = (void **)SmartCloseHandle::operator&(&TokenHandle);
  CurrentThread = GetCurrentThread();
  v9 = OpenThreadToken(CurrentThread, 0xBu, 1, v5);
  if ( v9 )
  {
    v34 = g_guidAdvApi32Api;
    Resource = CResourceManager::GetResource(v7, &v34, v8);
    if ( !Resource )
      goto LABEL_43;
    v11 = SmartCloseHandle::operator&(&hToken);
    v12 = (__int64 (__fastcall *)(HANDLE, __int64, _QWORD, __int64, int, __int64))*((_QWORD *)Resource + 16);
    if ( v12 )
      v9 = v12(TokenHandle, 11, 0, 2, 1, v11);
    v34 = g_guidAdvApi32Api;
    CResourceManager::ReleaseResource((CResourceManager *)&CResourceManager::sm_TheResourceManager, &v34, Resource);
  }
  else
  {
    v9 = 0;
  }
  if ( v9 )
  {
    VersionInformation.dwOSVersionInfoSize = 276;
    GetVersionExW(&VersionInformation);
    v43 = 0;
    v45 = 0;
    v44 = 0;
    CHString::CHString((CHString *)&v34);
    CHString::CHString((CHString *)v33);
    memset_0(SubKey, 0, sizeof(SubKey));
    TokenInformationLength = 0;
    if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) || GetLastError() != 122 )
    {
      LastError = GetLastError();
    }
    else
    {
      v13 = (void **)operator new(TokenInformationLength);
      *(_QWORD *)ExitCode = v13;
      if ( v13 )
      {
        try
        {
          TokenInformation = GetTokenInformation(
                               TokenHandle,
                               TokenUser,
                               v13,
                               TokenInformationLength,
                               &TokenInformationLength);
          if ( TokenInformation )
          {
            CSid::CSid((CSid *)&ProcessInformation, *v13, 0);
            if ( v37 )
            {
              LastError = GetLastError();
            }
            else
            {
              SidString = CSid::GetSidString(&ProcessInformation, &lpEnvironment);
              CHString::operator=(&v34, SidString);
              CHString::~CHString((CHString *)&lpEnvironment);
              AccountName = CSid::GetAccountName(&ProcessInformation, &lpEnvironment);
              CHString::operator=(v33, AccountName);
              CHString::~CHString((CHString *)&lpEnvironment);
            }
            CSid::~CSid((CSid *)&ProcessInformation);
          }
          else
          {
            LastError = GetLastError();
          }
        }
        catch ( ... )
        {
          if ( *(_QWORD *)ExitCode )
            operator delete(*(void **)ExitCode);
          throw;
        }
        operator delete(v13);
      }
      else
      {
        LastError = 8;
      }
    }
    if ( !LastError )
    {
      CRegistry::CRegistry((CRegistry *)v46);
      v16 = (const unsigned __int16 *)CHString::operator unsigned short const *(&v34);
      v17 = CRegistry::Open((CRegistry *)v46, HKEY_USERS, v16, 0x20019u);
      TokenInformation = v17;
      CRegistry::Close((CRegistry *)v46);
      if ( v17 )
      {
        v18 = (const WCHAR *)CHString::operator unsigned short const *(v33);
        LastError = CUserHive::LoadNT((CUserHive *)&VersionInformation, v18, SubKey, 0x400u);
        if ( LastError == 2 )
        {
          LastError = 0;
          v17 = 0;
          TokenInformation = 0;
        }
      }
      CRegistry::~CRegistry((CRegistry *)v46);
      if ( !LastError )
      {
        try
        {
          memset_0(&StartupInfo, 0, sizeof(StartupInfo));
          StartupInfo.cb = 104;
          StartupInfo.dwFlags = 1;
          StartupInfo.wShowWindow = 0;
          memset(&ProcessInformation, 0, sizeof(ProcessInformation));
          v31 = 0;
          lpEnvironment = 0;
          v38 = g_guidUserEnvApi;
          v21 = CResourceManager::GetResource(v19, &v38, v20);
          v23 = v21;
          v31 = v21;
          if ( v21 )
          {
            try
            {
              if ( (unsigned int)CUserEnvApi::CreateEnvironmentBlock(v21, &lpEnvironment, hToken, v22) )
              {
                LastError = CreateProcessAsUserW(
                              hToken,
                              0,
                              a2,
                              0,
                              0,
                              0,
                              0x1000420u,
                              lpEnvironment,
                              0,
                              &StartupInfo,
                              &ProcessInformation);
                if ( lpEnvironment )
                  CUserEnvApi::DestroyEnvironmentBlock(v23, lpEnvironment);
              }
            }
            catch ( ... )
            {
              v40 = g_guidUserEnvApi;
              CResourceManager::ReleaseResource((CResourceManager *)&CResourceManager::sm_TheResourceManager, &v40, v31);
              v31 = 0;
              throw;
            }
            v39 = g_guidUserEnvApi;
            CResourceManager::ReleaseResource((CResourceManager *)&CResourceManager::sm_TheResourceManager, &v39, v23);
            v31 = 0;
            if ( LastError )
            {
              LastError = 0;
              if ( !WaitForSingleObject(ProcessInformation.hProcess, 0xFFFFFFFF) )
              {
                ExitCode[0] = 0;
                if ( GetExitCodeProcess(ProcessInformation.hProcess, ExitCode) )
                {
                  v24 = 0;
                  if ( ExitCode[0] == 2 )
                    v24 = -2147217407;
                  v3 = v24;
                  v35 = v24;
                }
                CloseHandle(ProcessInformation.hProcess);
                CloseHandle(ProcessInformation.hThread);
              }
            }
            else
            {
              LastError = GetLastError();
            }
          }
        }
        catch ( ... )
        {
          if ( TokenInformation )
            CUserHive::Unload((CUserHive *)&VersionInformation, SubKey);
          throw;
        }
        if ( v17 )
          CUserHive::Unload((CUserHive *)&VersionInformation, SubKey);
      }
    }
    CHString::~CHString((CHString *)v33);
    CHString::~CHString((CHString *)&v34);
    CUserHive::~CUserHive((CUserHive *)&VersionInformation);
    if ( LastError == 5 )
      v3 = -2147024891;
  }
LABEL_43:
  SmartCloseHandle::~SmartCloseHandle((SmartCloseHandle *)&TokenHandle);
  SmartCloseHandle::~SmartCloseHandle((SmartCloseHandle *)&hToken);
  return v3;
}

```

## disassembly

```asm
0x1800a5cc4  push    rbx
0x1800a5cc6  push    rsi
0x1800a5cc7  push    rdi
0x1800a5cc8  push    r12
0x1800a5cca  push    r14
0x1800a5ccc  push    r15
0x1800a5cce  sub     rsp, 0D38h
0x1800a5cd5  mov     rax, cs:__security_cookie
0x1800a5cdc  xor     rax, rsp
0x1800a5cdf  mov     [rsp+0D68h+var_48], rax
0x1800a5ce7  mov     r15, rdx
0x1800a5cea  mov     esi, 80041001h
0x1800a5cef  xor     r12d, r12d
0x1800a5cf2  mov     edi, r12d
0x1800a5cf5  mov     [rsp+0D68h+var_D08], r12d
0x1800a5cfa  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a5cfe  mov     [rsp+0D68h+hToken], rax
0x1800a5d06  mov     [rsp+0D68h+TokenHandle], rax
0x1800a5d0b  lea     rcx, [rsp+0D68h+TokenHandle]
0x1800a5d10  call    ??ISmartCloseHandle@@QEAAPEAPEAXXZ; SmartCloseHandle::operator&(void)
0x1800a5d15  mov     rbx, rax
0x1800a5d18  call    cs:__imp_GetCurrentThread
0x1800a5d1e  mov     r9, rbx; TokenHandle
0x1800a5d21  lea     edx, [r12+0Bh]; DesiredAccess
0x1800a5d26  lea     r8d, [r12+1]; OpenAsSelf
0x1800a5d2b  mov     rcx, rax; ThreadHandle
0x1800a5d2e  call    cs:__imp_OpenThreadToken
0x1800a5d34  mov     r14d, eax
0x1800a5d37  test    eax, eax
0x1800a5d39  jz      loc_1800A5DD4
0x1800a5d3f  movups  xmm0, xmmword ptr cs:?g_guidAdvApi32Api@@3U_GUID@@B.Data1; _GUID const g_guidAdvApi32Api ...
0x1800a5d46  movdqu  xmmword ptr [rsp+0D68h+var_CC8.Data1], xmm0
0x1800a5d4f  lea     rdx, [rsp+0D68h+var_CC8]; struct _GUID
0x1800a5d57  call    ?GetResource@CResourceManager@@QEAAPEAVCResource@@U_GUID@@PEAX@Z; CResourceManager::GetResource(_GUID,void *)
0x1800a5d5c  mov     rbx, rax
0x1800a5d5f  test    rax, rax
0x1800a5d62  jz      loc_1800A624B
0x1800a5d68  lea     rcx, [rsp+0D68h+hToken]
0x1800a5d70  call    ??ISmartCloseHandle@@QEAAPEAPEAXXZ; SmartCloseHandle::operator&(void)
0x1800a5d75  mov     rcx, rax
0x1800a5d78  mov     rax, [rbx+80h]
0x1800a5d7f  test    rax, rax
0x1800a5d82  jz      short loc_1800A5DAB
0x1800a5d84  mov     qword ptr [rsp+0D68h+bInheritHandles], rcx
0x1800a5d89  mov     dword ptr [rsp+0D68h+ReturnLength], 1
0x1800a5d91  lea     r9d, [r12+2]
0x1800a5d96  xor     r8d, r8d
0x1800a5d99  lea     edx, [r12+0Bh]
0x1800a5d9e  mov     rcx, [rsp+0D68h+TokenHandle]
0x1800a5da3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5da8  mov     r14d, eax
0x1800a5dab  movups  xmm0, xmmword ptr cs:?g_guidAdvApi32Api@@3U_GUID@@B.Data1; _GUID const g_guidAdvApi32Api ...
0x1800a5db2  movdqu  xmmword ptr [rsp+0D68h+var_CC8.Data1], xmm0
0x1800a5dbb  mov     r8, rbx; struct CResource *
0x1800a5dbe  lea     rdx, [rsp+0D68h+var_CC8]; struct _GUID
0x1800a5dc6  lea     rcx, ?sm_TheResourceManager@CResourceManager@@2V1@A; this
0x1800a5dcd  call    ?ReleaseResource@CResourceManager@@QEAAKU_GUID@@PEAVCResource@@@Z; CResourceManager::ReleaseResource(_GUID,CResource *)
0x1800a5dd2  jmp     short loc_1800A5DD7
0x1800a5dd4  mov     r14d, r12d
0x1800a5dd7  test    r14d, r14d
0x1800a5dda  jz      loc_1800A624B
0x1800a5de0  mov     [rsp+0D68h+VersionInformation.dwOSVersionInfoSize], 114h
0x1800a5deb  lea     rcx, [rsp+0D68h+VersionInformation]; lpVersionInformation
0x1800a5df3  call    cs:__imp_GetVersionExW
0x1800a5df9  mov     [rsp+0D68h+var_AC0], r12
0x1800a5e01  mov     [rsp+0D68h+var_AB0], r12d
0x1800a5e09  mov     [rsp+0D68h+var_AB8], r12
0x1800a5e11  lea     rcx, [rsp+0D68h+var_CC8]
0x1800a5e19  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x1800a5e1f  nop
0x1800a5e20  lea     rcx, [rsp+0D68h+var_CD0]
0x1800a5e28  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x1800a5e2e  nop
0x1800a5e2f  xor     edx, edx; Val
0x1800a5e31  mov     r8d, 800h; Size
0x1800a5e37  lea     rcx, [rsp+0D68h+SubKey]; void *
0x1800a5e3f  call    memset_0
0x1800a5e44  mov     [rsp+0D68h+TokenInformationLength], r12d
0x1800a5e49  lea     rax, [rsp+0D68h+TokenInformationLength]
0x1800a5e4e  mov     [rsp+0D68h+ReturnLength], rax; ReturnLength
0x1800a5e53  xor     r9d, r9d; TokenInformationLength
0x1800a5e56  xor     r8d, r8d; TokenInformation
0x1800a5e59  lea     edx, [r9+1]; TokenInformationClass
0x1800a5e5d  mov     rcx, [rsp+0D68h+TokenHandle]; TokenHandle
0x1800a5e62  call    cs:__imp_GetTokenInformation
0x1800a5e68  test    eax, eax
0x1800a5e6a  jnz     loc_1800A5F86
0x1800a5e70  call    cs:__imp_GetLastError
0x1800a5e76  cmp     eax, 7Ah ; 'z'
0x1800a5e79  jnz     loc_1800A5F86
0x1800a5e7f  mov     ecx, [rsp+0D68h+TokenInformationLength]; unsigned __int64
0x1800a5e83  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800a5e88  mov     rbx, rax
0x1800a5e8b  mov     qword ptr [rsp+0D68h+ExitCode], rax
0x1800a5e93  test    rax, rax
0x1800a5e96  jz      loc_1800A5F7B
0x1800a5e9c  lea     rax, [rsp+0D68h+TokenInformationLength]
0x1800a5ea1  mov     [rsp+0D68h+ReturnLength], rax; ReturnLength
0x1800a5ea6  mov     r9d, [rsp+0D68h+TokenInformationLength]; TokenInformationLength
0x1800a5eab  mov     r8, rbx; TokenInformation
0x1800a5eae  mov     edx, 1; TokenInformationClass
0x1800a5eb3  mov     rcx, [rsp+0D68h+TokenHandle]; TokenHandle
0x1800a5eb8  call    cs:__imp_GetTokenInformation
0x1800a5ebe  mov     [rsp+0D68h+var_D00], eax
0x1800a5ec2  test    eax, eax
0x1800a5ec4  jz      loc_1800A5F65
0x1800a5eca  xor     r8d, r8d; unsigned __int16 *
0x1800a5ecd  mov     rdx, [rbx]; void *
0x1800a5ed0  lea     rcx, [rsp+0D68h+ProcessInformation]; this
0x1800a5ed8  call    ??0CSid@@QEAA@PEAXPEBG@Z; CSid::CSid(void *,ushort const *)
0x1800a5edd  nop
0x1800a5ede  cmp     [rsp+0D68h+var_C88], r12d
0x1800a5ee6  jnz     short loc_1800A5F4A
0x1800a5ee8  lea     rdx, [rsp+0D68h+var_CF8]
0x1800a5eed  lea     rcx, [rsp+0D68h+ProcessInformation]
0x1800a5ef5  call    ?GetSidString@CSid@@QEBA?AVCHString@@XZ; CSid::GetSidString(void)
0x1800a5efa  nop
0x1800a5efb  mov     rdx, rax
0x1800a5efe  lea     rcx, [rsp+0D68h+var_CC8]
0x1800a5f06  call    cs:__imp_??4CHString@@QEAAAEBV0@AEBV0@@Z; CHString::operator=(CHString const &)
0x1800a5f0c  nop
0x1800a5f0d  lea     rcx, [rsp+0D68h+var_CF8]
0x1800a5f12  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800a5f18  lea     rdx, [rsp+0D68h+var_CF8]
0x1800a5f1d  lea     rcx, [rsp+0D68h+ProcessInformation]
0x1800a5f25  call    ?GetAccountName@CSid@@QEBA?AVCHString@@XZ; CSid::GetAccountName(void)
0x1800a5f2a  nop
0x1800a5f2b  mov     rdx, rax
0x1800a5f2e  lea     rcx, [rsp+0D68h+var_CD0]
0x1800a5f36  call    cs:__imp_??4CHString@@QEAAAEBV0@AEBV0@@Z; CHString::operator=(CHString const &)
0x1800a5f3c  nop
0x1800a5f3d  lea     rcx, [rsp+0D68h+var_CF8]
0x1800a5f42  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800a5f48  jmp     short loc_1800A5F56
0x1800a5f4a  call    cs:__imp_GetLastError
0x1800a5f50  mov     edi, eax
0x1800a5f52  mov     [rsp+0D68h+var_D08], eax
0x1800a5f56  lea     rcx, [rsp+0D68h+ProcessInformation]; this
0x1800a5f5e  call    ??1CSid@@QEAA@XZ; CSid::~CSid(void)
0x1800a5f63  jmp     short loc_1800A5F71
0x1800a5f65  call    cs:__imp_GetLastError
0x1800a5f6b  mov     edi, eax
0x1800a5f6d  mov     [rsp+0D68h+var_D08], eax
0x1800a5f71  mov     rcx, rbx; void *
0x1800a5f74  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800a5f79  jmp     short loc_1800A5F92
0x1800a5f7b  mov     edi, 8
0x1800a5f80  mov     [rsp+0D68h+var_D08], edi
0x1800a5f84  jmp     short loc_1800A5F92
0x1800a5f86  call    cs:__imp_GetLastError
0x1800a5f8c  mov     edi, eax
0x1800a5f8e  mov     [rsp+0D68h+var_D08], eax
0x1800a5f92  test    edi, edi
0x1800a5f94  jnz     loc_1800A6215
0x1800a5f9a  lea     rcx, [rsp+0D68h+var_AA8]
0x1800a5fa2  call    cs:__imp_??0CRegistry@@QEAA@XZ; CRegistry::CRegistry(void)
0x1800a5fa8  nop
0x1800a5fa9  lea     rcx, [rsp+0D68h+var_CC8]
0x1800a5fb1  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x1800a5fb7  mov     r8, rax
0x1800a5fba  mov     rdx, 0FFFFFFFF80000003h
0x1800a5fc1  mov     r9d, 20019h
0x1800a5fc7  lea     rcx, [rsp+0D68h+var_AA8]
0x1800a5fcf  call    cs:__imp_?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z; CRegistry::Open(HKEY__ *,ushort const *,ulong)
0x1800a5fd5  mov     ebx, eax
0x1800a5fd7  mov     [rsp+0D68h+var_D00], eax
0x1800a5fdb  lea     rcx, [rsp+0D68h+var_AA8]
0x1800a5fe3  call    cs:__imp_?Close@CRegistry@@QEAAXXZ; CRegistry::Close(void)
0x1800a5fe9  test    ebx, ebx
0x1800a5feb  jz      short loc_1800A6033
0x1800a5fed  lea     rcx, [rsp+0D68h+var_CD0]
0x1800a5ff5  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x1800a5ffb  mov     r9d, 400h; unsigned __int64
0x1800a6001  lea     r8, [rsp+0D68h+SubKey]; unsigned __int16 *
0x1800a6009  mov     rdx, rax; lpAccountName
0x1800a600c  lea     rcx, [rsp+0D68h+VersionInformation]; this
0x1800a6014  call    ?LoadNT@CUserHive@@AEAAKPEBGPEAG_K@Z; CUserHive::LoadNT(ushort const *,ushort *,unsigned __int64)
0x1800a6019  mov     edi, eax
0x1800a601b  mov     [rsp+0D68h+var_D08], eax
0x1800a601f  cmp     eax, 2
0x1800a6022  jnz     short loc_1800A6033
0x1800a6024  mov     edi, r12d
0x1800a6027  mov     [rsp+0D68h+var_D08], r12d
0x1800a602c  mov     ebx, r12d
0x1800a602f  mov     [rsp+0D68h+var_D00], ebx
0x1800a6033  lea     rcx, [rsp+0D68h+var_AA8]
0x1800a603b  call    cs:__imp_??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x1800a6041  test    edi, edi
0x1800a6043  jnz     loc_1800A6215
0x1800a6049  lea     r14d, [rdi+68h]
0x1800a604d  mov     r8d, r14d; Size
0x1800a6050  xor     edx, edx; Val
0x1800a6052  lea     rcx, [rsp+0D68h+StartupInfo]; void *
0x1800a605a  call    memset_0
0x1800a605f  mov     [rsp+0D68h+StartupInfo.cb], r14d
0x1800a6067  mov     [rsp+0D68h+StartupInfo.dwFlags], 1
0x1800a6072  mov     [rsp+0D68h+StartupInfo.wShowWindow], r12w
0x1800a607b  xorps   xmm0, xmm0
0x1800a607e  xor     eax, eax
0x1800a6080  movups  xmmword ptr [rsp+0D68h+ProcessInformation.hProcess], xmm0
0x1800a6088  mov     qword ptr [rsp+0D68h+ProcessInformation.dwProcessId], rax
0x1800a6090  mov     [rsp+0D68h+var_CE0], r12
0x1800a6098  mov     [rsp+0D68h+var_CF8], r12
0x1800a609d  movups  xmm0, xmmword ptr cs:?g_guidUserEnvApi@@3U_GUID@@B.Data1; _GUID const g_guidUserEnvApi ...
0x1800a60a4  movdqu  xmmword ptr [rsp+0D68h+var_C78.Data1], xmm0
0x1800a60ad  lea     rdx, [rsp+0D68h+var_C78]; struct _GUID
0x1800a60b5  call    ?GetResource@CResourceManager@@QEAAPEAVCResource@@U_GUID@@PEAX@Z; CResourceManager::GetResource(_GUID,void *)
0x1800a60ba  mov     r14, rax
0x1800a60bd  mov     [rsp+0D68h+var_CE0], rax
0x1800a60c5  test    rax, rax
0x1800a60c8  jz      loc_1800A61FB
0x1800a60ce  mov     r8, [rsp+0D68h+hToken]; void *
0x1800a60d6  lea     rdx, [rsp+0D68h+var_CF8]; void **
0x1800a60db  mov     rcx, rax; this
0x1800a60de  call    ?CreateEnvironmentBlock@CUserEnvApi@@QEAAHPEAPEAXPEAXH@Z; CUserEnvApi::CreateEnvironmentBlock(void * *,void *,int)
0x1800a60e3  test    eax, eax
0x1800a60e5  jz      short loc_1800A6151
0x1800a60e7  mov     rax, [rsp+0D68h+var_CF8]
0x1800a60ec  lea     rcx, [rsp+0D68h+ProcessInformation]
0x1800a60f4  mov     [rsp+0D68h+lpProcessInformation], rcx; lpProcessInformation
0x1800a60f9  lea     rcx, [rsp+0D68h+StartupInfo]
0x1800a6101  mov     [rsp+0D68h+lpStartupInfo], rcx; lpStartupInfo
0x1800a6106  mov     [rsp+0D68h+lpCurrentDirectory], r12; lpCurrentDirectory
0x1800a610b  mov     [rsp+0D68h+lpEnvironment], rax; lpEnvironment
0x1800a6110  mov     [rsp+0D68h+dwCreationFlags], 1000420h; dwCreationFlags
0x1800a6118  mov     [rsp+0D68h+bInheritHandles], r12d; bInheritHandles
0x1800a611d  mov     [rsp+0D68h+ReturnLength], r12; lpThreadAttributes
0x1800a6122  xor     r9d, r9d; lpProcessAttributes
0x1800a6125  mov     r8, r15; lpCommandLine
0x1800a6128  xor     edx, edx; lpApplicationName
0x1800a612a  mov     rcx, [rsp+0D68h+hToken]; hToken
0x1800a6132  call    cs:__imp_CreateProcessAsUserW
0x1800a6138  mov     edi, eax
0x1800a613a  mov     [rsp+0D68h+var_D08], eax
0x1800a613e  mov     rdx, [rsp+0D68h+var_CF8]; void *
0x1800a6143  test    rdx, rdx
0x1800a6146  jz      short loc_1800A6151
0x1800a6148  mov     rcx, r14; this
0x1800a614b  call    ?DestroyEnvironmentBlock@CUserEnvApi@@QEAAHPEAX@Z; CUserEnvApi::DestroyEnvironmentBlock(void *)
0x1800a6150  nop
0x1800a6151  movups  xmm0, xmmword ptr cs:?g_guidUserEnvApi@@3U_GUID@@B.Data1; _GUID const g_guidUserEnvApi ...
0x1800a6158  movdqu  xmmword ptr [rsp+0D68h+var_C68.Data1], xmm0
0x1800a6161  mov     r8, r14; struct CResource *
0x1800a6164  lea     rdx, [rsp+0D68h+var_C68]; struct _GUID
0x1800a616c  lea     rcx, ?sm_TheResourceManager@CResourceManager@@2V1@A; this
0x1800a6173  call    ?ReleaseResource@CResourceManager@@QEAAKU_GUID@@PEAVCResource@@@Z; CResourceManager::ReleaseResource(_GUID,CResource *)
0x1800a6178  mov     [rsp+0D68h+var_CE0], r12
0x1800a6180  test    edi, edi
0x1800a6182  jz      loc_1800A6286
0x1800a6188  mov     edi, r12d
0x1800a618b  mov     [rsp+0D68h+var_D08], r12d
0x1800a6190  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800a6193  mov     rcx, [rsp+0D68h+ProcessInformation.hProcess]; hHandle
0x1800a619b  call    cs:__imp_WaitForSingleObject
0x1800a61a1  test    eax, eax
0x1800a61a3  jnz     short loc_1800A61FB
0x1800a61a5  mov     [rsp+0D68h+ExitCode], r12d
0x1800a61ad  lea     rdx, [rsp+0D68h+ExitCode]; lpExitCode
0x1800a61b5  mov     rcx, [rsp+0D68h+ProcessInformation.hProcess]; hProcess
0x1800a61bd  call    cs:__imp_GetExitCodeProcess
0x1800a61c3  test    eax, eax
0x1800a61c5  jz      short loc_1800A61DE
0x1800a61c7  mov     eax, r12d
0x1800a61ca  cmp     [rsp+0D68h+ExitCode], 2
0x1800a61d2  cmovz   eax, esi
0x1800a61d5  mov     esi, eax
0x1800a61d7  mov     [rsp+0D68h+var_CB8], eax
0x1800a61de  mov     rcx, [rsp+0D68h+ProcessInformation.hProcess]; hObject
0x1800a61e6  call    cs:__imp_CloseHandle
0x1800a61ec  mov     rcx, [rsp+0D68h+ProcessInformation.hThread]; hObject
0x1800a61f4  call    cs:__imp_CloseHandle
0x1800a61fa  nop
0x1800a61fb  test    ebx, ebx
0x1800a61fd  jz      short loc_1800A6215
0x1800a61ff  lea     rdx, [rsp+0D68h+SubKey]; lpSubKey
0x1800a6207  lea     rcx, [rsp+0D68h+VersionInformation]; this
0x1800a620f  call    ?Unload@CUserHive@@QEAAKPEBG@Z; CUserHive::Unload(ushort const *)
0x1800a6214  nop
0x1800a6215  lea     rcx, [rsp+0D68h+var_CD0]
0x1800a621d  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800a6223  nop
0x1800a6224  lea     rcx, [rsp+0D68h+var_CC8]
0x1800a622c  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x1800a6232  nop
0x1800a6233  lea     rcx, [rsp+0D68h+VersionInformation]; this
0x1800a623b  call    ??1CUserHive@@QEAA@XZ; CUserHive::~CUserHive(void)
0x1800a6240  mov     eax, 80070005h
0x1800a6245  cmp     edi, 5
0x1800a6248  cmovz   esi, eax
0x1800a624b  lea     rcx, [rsp+0D68h+TokenHandle]; this
0x1800a6250  call    ??1SmartCloseHandle@@QEAA@XZ; SmartCloseHandle::~SmartCloseHandle(void)
0x1800a6255  nop
0x1800a6256  lea     rcx, [rsp+0D68h+hToken]; this
0x1800a625e  call    ??1SmartCloseHandle@@QEAA@XZ; SmartCloseHandle::~SmartCloseHandle(void)
0x1800a6263  mov     eax, esi
0x1800a6265  mov     rcx, [rsp+0D68h+var_48]
0x1800a626d  xor     rcx, rsp; StackCookie
0x1800a6270  call    __security_check_cookie
0x1800a6275  add     rsp, 0D38h
0x1800a627c  pop     r15
  ... truncated ...
```
