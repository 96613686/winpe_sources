# Process::ProcessCreation(CInstance *,CHString,int,CHString,ushort * &,int,ulong,ulong,int,_STARTUPINFOW)

- ea: `0x180090b94`
- end: `0x18009107c`
- name: `?ProcessCreation@Process@@AEAAKPEAVCInstance@@VCHString@@H1AEAPEAGHKKHU_STARTUPINFOW@@@Z`
- size: `1256`
- prototype: `__int64 __fastcall(__int64, CInstance *, const struct CHString *, int, const struct CHString *, void **, __int64, __int64, DWORD, __int64, __int64)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18008e3a8`
- `0x18009036c`

## callees

- `0x18000bef0`
- `0x18000c910`
- `0x180030a04`
- `0x180030c98`
- `0x180031800`
- `0x180048acc`
- `0x18004d944`
- `0x18006c0a4`
- `0x18006f1d0`
- `0x180078ac8`
- `0x1800900d0`
- `0x180090b94`
- `0x1800f15b8`
- `0x1800f15d8`
- `0x1800fc980`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180090d24`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180090d24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180090e64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180090e64`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180090c23`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180090c23`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180090c0a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180090c0a`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180090c57`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180090c57`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180090c6d`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180090c7c`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180090d0a`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180090c6d`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180090c7c`
- `framedynos!??0CHString@@QEAA@XZ` at `0x180090d0a`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180090d74`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180090db8`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180090d74`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x180090db8`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x180090d65`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x180090d65`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x180090fd2`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x180090fd2`
- `framedynos!?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z` at `0x180090d92`
- `framedynos!?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z` at `0x180090d92`
- `framedynos!??0CHString@@QEAA@AEBV0@@Z` at `0x180090e97`
- `framedynos!??0CHString@@QEAA@AEBV0@@Z` at `0x180090ebb`
- `framedynos!??0CHString@@QEAA@AEBV0@@Z` at `0x180090e97`
- `framedynos!??0CHString@@QEAA@AEBV0@@Z` at `0x180090ebb`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x180090cb3`
- `framedynos!??0CHString@@QEAA@PEBG@Z` at `0x180090cb3`
- `framedynos!??H@YA?AVCHString@@AEBV0@0@Z` at `0x180090cca`
- `framedynos!??H@YA?AVCHString@@AEBV0@0@Z` at `0x180090ce4`
- `framedynos!??H@YA?AVCHString@@AEBV0@0@Z` at `0x180090cca`
- `framedynos!??H@YA?AVCHString@@AEBV0@0@Z` at `0x180090ce4`
- `framedynos!?Close@CRegistry@@QEAAXXZ` at `0x180090da6`
- `framedynos!?Close@CRegistry@@QEAAXXZ` at `0x180090da6`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180090cf0`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180090cfc`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180090fef`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180090ffe`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18009100d`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18009101c`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180091047`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180091051`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180090cf0`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180090cfc`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180090fef`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180090ffe`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18009100d`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18009101c`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180091047`
- `framedynos!??1CHString@@QEAA@XZ` at `0x180091051`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Process::ProcessCreation(
        __int64 a1,
        CInstance *a2,
        const struct CHString *a3,
        int a4,
        const struct CHString *a5,
        void **a6,
        __int64 a7,
        __int64 a8,
        DWORD a9,
        __int64 a10,
        __int64 a11)
{
  void **v12; // rbx
  HANDLE CurrentThread; // rax
  Process *v14; // rcx
  CUserEnvApi *v15; // rdi
  void **phNewToken; // rax
  Process *v17; // rcx
  unsigned int ProcessErrorCode; // ebx
  CHString *v19; // rax
  __int64 v20; // rax
  Process *v21; // rcx
  const unsigned __int16 *v22; // rax
  int v23; // esi
  Process *v24; // rcx
  void *v25; // r8
  const WCHAR *v26; // rax
  unsigned int v27; // eax
  void *v28; // r14
  CUserEnvApi *Resource; // rax
  int v30; // r9d
  CHString *v31; // rbx
  CHString *v32; // r9
  WCHAR **v33; // rcx
  __int64 v35; // [rsp+38h] [rbp-D10h]
  __int64 v36; // [rsp+40h] [rbp-D08h]
  __int64 v37; // [rsp+50h] [rbp-CF8h]
  HANDLE hExistingToken; // [rsp+68h] [rbp-CE0h] BYREF
  void *v39; // [rsp+70h] [rbp-CD8h] BYREF
  int v40; // [rsp+78h] [rbp-CD0h] BYREF
  void *v41; // [rsp+80h] [rbp-CC8h] BYREF
  int v42; // [rsp+88h] [rbp-CC0h]
  _BYTE v43[8]; // [rsp+90h] [rbp-CB8h] BYREF
  _BYTE v44[8]; // [rsp+98h] [rbp-CB0h] BYREF
  _BYTE v45[8]; // [rsp+A0h] [rbp-CA8h] BYREF
  _BYTE v46[8]; // [rsp+A8h] [rbp-CA0h] BYREF
  CUserEnvApi *v47; // [rsp+B0h] [rbp-C98h]
  _BYTE v48[8]; // [rsp+B8h] [rbp-C90h] BYREF
  _BYTE v49[8]; // [rsp+C0h] [rbp-C88h] BYREF
  CInstance *v50; // [rsp+C8h] [rbp-C80h]
  struct _GUID v51; // [rsp+D0h] [rbp-C78h] BYREF
  struct _GUID v52; // [rsp+E0h] [rbp-C68h] BYREF
  const struct CHString *v53; // [rsp+F0h] [rbp-C58h]
  const struct CHString *v54; // [rsp+F8h] [rbp-C50h]
  struct _STARTUPINFOW v55; // [rsp+100h] [rbp-C48h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+170h] [rbp-BD8h] BYREF
  __int64 v57; // [rsp+288h] [rbp-AC0h]
  __int64 v58; // [rsp+290h] [rbp-AB8h]
  int v59; // [rsp+298h] [rbp-AB0h]
  _BYTE v60[608]; // [rsp+2A0h] [rbp-AA8h] BYREF
  WCHAR SubKey[1024]; // [rsp+500h] [rbp-848h] BYREF

  v42 = a4;
  v50 = a2;
  v53 = a3;
  v54 = a5;
  v41 = (void *)-1LL;
  hExistingToken = (HANDLE)-1LL;
  v12 = (void **)SmartCloseHandle::operator&(&hExistingToken);
  CurrentThread = GetCurrentThread();
  v15 = 0;
  if ( !OpenThreadToken(CurrentThread, 0xBu, 1, v12)
    || (phNewToken = (void **)SmartCloseHandle::operator&(&v41),
        !DuplicateTokenEx(hExistingToken, 0xBu, 0, SecurityImpersonation, TokenPrimary, phNewToken)) )
  {
    ProcessErrorCode = Process::GetProcessErrorCode(v14);
    goto LABEL_32;
  }
  CHString::CHString((CHString *)v45);
  CHString::CHString((CHString *)v44);
  ProcessErrorCode = Process::GetAccount(v17, hExistingToken, (struct CHString *)v45, (struct CHString *)v44);
  if ( !ProcessErrorCode )
  {
    v19 = CHString::CHString((CHString *)&v40, L"\\");
    v20 = operator+(&v39, v45, v19);
    operator+(v46, v20, v44);
    CHString::~CHString((CHString *)&v39);
    CHString::~CHString((CHString *)&v40);
    CHString::CHString((CHString *)v43);
    VersionInformation.dwOSVersionInfoSize = 276;
    GetVersionExW(&VersionInformation);
    v57 = 0;
    v59 = 0;
    v58 = 0;
    ProcessErrorCode = Process::GetSid(v21, hExistingToken, (struct CHString *)v43);
    if ( ProcessErrorCode )
    {
LABEL_29:
      CUserHive::~CUserHive((CUserHive *)&VersionInformation);
      CHString::~CHString((CHString *)v43);
      CHString::~CHString((CHString *)v46);
      goto LABEL_30;
    }
    CRegistry::CRegistry((CRegistry *)v60);
    v22 = (const unsigned __int16 *)CHString::operator unsigned short const *(v43);
    v23 = CRegistry::Open((CRegistry *)v60, HKEY_USERS, v22, 0x20019u);
    v40 = v23;
    CRegistry::Close((CRegistry *)v60);
    if ( v23 )
    {
      v26 = (const WCHAR *)CHString::operator unsigned short const *(v46);
      ProcessErrorCode = CUserHive::LoadNT((CUserHive *)&VersionInformation, v26, SubKey, 0x400u);
      if ( ProcessErrorCode == 2 )
        v23 = 0;
      v40 = v23;
    }
    v27 = 0;
    if ( ProcessErrorCode != 2 )
      v27 = ProcessErrorCode;
    if ( v27 )
    {
      ProcessErrorCode = Process::GetProcessErrorCode(v24);
LABEL_28:
      CRegistry::~CRegistry((CRegistry *)v60);
      goto LABEL_29;
    }
    try
    {
      v28 = 0;
      v39 = 0;
      v47 = 0;
      if ( !*a6 )
      {
        v52 = g_guidUserEnvApi;
        Resource = CResourceManager::GetResource(v24, &v52, v25);
        v15 = Resource;
        v47 = Resource;
        if ( !Resource || !(unsigned int)CUserEnvApi::CreateEnvironmentBlock(Resource, &v39, v41, v30) )
        {
          ProcessErrorCode = 8;
          GetLastError();
LABEL_21:
          if ( v39 )
            CUserEnvApi::DestroyEnvironmentBlock(v15, v39);
          if ( v15 )
          {
            v51 = g_guidUserEnvApi;
            CResourceManager::ReleaseResource((CResourceManager *)&CResourceManager::sm_TheResourceManager, &v51, v15);
          }
          goto LABEL_38;
        }
        v28 = v39;
      }
      if ( *a6 )
        v28 = *a6;
      *(_QWORD *)&v51.Data1 = v48;
      v31 = CHString::CHString((CHString *)v48, a5);
      *(_QWORD *)&v52.Data1 = v49;
      v32 = CHString::CHString((CHString *)v49, a3);
      *(_OWORD *)&v55.cb = *(_OWORD *)a11;
      *(_OWORD *)&v55.lpDesktop = *(_OWORD *)(a11 + 16);
      *(_OWORD *)&v55.dwX = *(_OWORD *)(a11 + 32);
      *(_OWORD *)&v55.dwXCountChars = *(_OWORD *)(a11 + 48);
      *(_OWORD *)&v55.wShowWindow = *(_OWORD *)(a11 + 64);
      *(_OWORD *)&v55.hStdInput = *(_OWORD *)(a11 + 80);
      v55.hStdError = *(HANDLE *)(a11 + 96);
      ProcessErrorCode = Process::Creation(v33, v50, v41, v32, v42, v31, v28, v35, v36, a9, v37, &v55);
      goto LABEL_21;
    }
    catch ( ... )
    {
      if ( v40 )
        CUserHive::Unload((CUserHive *)&VersionInformation, SubKey);
      throw;
    }
LABEL_38:
    if ( v23 )
      CUserHive::Unload((CUserHive *)&VersionInformation, SubKey);
    goto LABEL_28;
  }
LABEL_30:
  CHString::~CHString((CHString *)v44);
  CHString::~CHString((CHString *)v45);
LABEL_32:
  SmartCloseHandle::~SmartCloseHandle((SmartCloseHandle *)&hExistingToken);
  SmartCloseHandle::~SmartCloseHandle((SmartCloseHandle *)&v41);
  CHString::~CHString(a3);
  CHString::~CHString(a5);
  return ProcessErrorCode;
}

```

## disassembly

```asm
0x180090b94  push    rbx
0x180090b96  push    rsi
0x180090b97  push    rdi
0x180090b98  push    r12
0x180090b9a  push    r13
0x180090b9c  push    r14
0x180090b9e  push    r15
0x180090ba0  sub     rsp, 0D10h
0x180090ba7  mov     rax, cs:__security_cookie
0x180090bae  xor     rax, rsp
0x180090bb1  mov     [rsp+0D48h+var_48], rax
0x180090bb9  mov     [rsp+0D48h+var_CC0], r9d
0x180090bc1  mov     r15, r8
0x180090bc4  mov     [rsp+0D48h+var_C80], rdx
0x180090bcc  mov     [rsp+0D48h+var_C58], r8
0x180090bd4  mov     r12, [rsp+0D48h+arg_20]
0x180090bdc  mov     [rsp+0D48h+var_C50], r12
0x180090be4  mov     r13, [rsp+0D48h+arg_50]
0x180090bec  or      rax, 0FFFFFFFFFFFFFFFFh
0x180090bf0  mov     [rsp+0D48h+var_CC8], rax
0x180090bf8  mov     [rsp+0D48h+hExistingToken], rax
0x180090bfd  lea     rcx, [rsp+0D48h+hExistingToken]
0x180090c02  call    ??ISmartCloseHandle@@QEAAPEAPEAXXZ; SmartCloseHandle::operator&(void)
0x180090c07  mov     rbx, rax
0x180090c0a  call    cs:__imp_GetCurrentThread
0x180090c10  mov     r9, rbx; TokenHandle
0x180090c13  mov     ebx, 1
0x180090c18  mov     r8d, ebx; OpenAsSelf
0x180090c1b  lea     esi, [rbx+0Ah]
0x180090c1e  mov     edx, esi; DesiredAccess
0x180090c20  mov     rcx, rax; ThreadHandle
0x180090c23  call    cs:__imp_OpenThreadToken
0x180090c29  xor     edi, edi
0x180090c2b  test    eax, eax
0x180090c2d  jz      loc_180091024
0x180090c33  lea     rcx, [rsp+0D48h+var_CC8]
0x180090c3b  call    ??ISmartCloseHandle@@QEAAPEAPEAXXZ; SmartCloseHandle::operator&(void)
0x180090c40  mov     [rsp+0D48h+phNewToken], rax; phNewToken
0x180090c45  mov     [rsp+0D48h+TokenType], ebx; TokenType
0x180090c49  lea     r9d, [rbx+1]; ImpersonationLevel
0x180090c4d  xor     r8d, r8d; lpTokenAttributes
0x180090c50  mov     edx, esi; dwDesiredAccess
0x180090c52  mov     rcx, [rsp+0D48h+hExistingToken]; hExistingToken
0x180090c57  call    cs:__imp_DuplicateTokenEx
0x180090c5d  test    eax, eax
0x180090c5f  jz      loc_180091024
0x180090c65  lea     rcx, [rsp+0D48h+var_CA8]
0x180090c6d  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x180090c73  nop
0x180090c74  lea     rcx, [rsp+0D48h+var_CB0]
0x180090c7c  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x180090c82  nop
0x180090c83  lea     r9, [rsp+0D48h+var_CB0]; struct CHString *
0x180090c8b  lea     r8, [rsp+0D48h+var_CA8]; struct CHString *
0x180090c93  mov     rdx, [rsp+0D48h+hExistingToken]; void *
0x180090c98  call    ?GetAccount@Process@@AEAAKPEAXAEAVCHString@@1@Z; Process::GetAccount(void *,CHString &,CHString &)
0x180090c9d  mov     ebx, eax
0x180090c9f  test    eax, eax
0x180090ca1  jnz     loc_180091005
0x180090ca7  lea     rdx, SubBlock; "\\"
0x180090cae  lea     rcx, [rsp+0D48h+var_CD0]
0x180090cb3  call    cs:__imp_??0CHString@@QEAA@PEBG@Z; CHString::CHString(ushort const *)
0x180090cb9  nop
0x180090cba  mov     r8, rax
0x180090cbd  lea     rdx, [rsp+0D48h+var_CA8]
0x180090cc5  lea     rcx, [rsp+0D48h+var_CD8]
0x180090cca  call    cs:__imp_??H@YA?AVCHString@@AEBV0@0@Z; operator+(CHString const &,CHString const &)
0x180090cd0  nop
0x180090cd1  lea     r8, [rsp+0D48h+var_CB0]
0x180090cd9  mov     rdx, rax
0x180090cdc  lea     rcx, [rsp+0D48h+var_CA0]
0x180090ce4  call    cs:__imp_??H@YA?AVCHString@@AEBV0@0@Z; operator+(CHString const &,CHString const &)
0x180090cea  nop
0x180090ceb  lea     rcx, [rsp+0D48h+var_CD8]
0x180090cf0  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x180090cf6  nop
0x180090cf7  lea     rcx, [rsp+0D48h+var_CD0]
0x180090cfc  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x180090d02  lea     rcx, [rsp+0D48h+var_CB8]
0x180090d0a  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x180090d10  nop
0x180090d11  mov     [rsp+0D48h+VersionInformation.dwOSVersionInfoSize], 114h
0x180090d1c  lea     rcx, [rsp+0D48h+VersionInformation]; lpVersionInformation
0x180090d24  call    cs:__imp_GetVersionExW
0x180090d2a  mov     [rsp+0D48h+var_AC0], rdi
0x180090d32  mov     [rsp+0D48h+var_AB0], edi
0x180090d39  mov     [rsp+0D48h+var_AB8], rdi
0x180090d41  lea     r8, [rsp+0D48h+var_CB8]; struct CHString *
0x180090d49  mov     rdx, [rsp+0D48h+hExistingToken]; void *
0x180090d4e  call    ?GetSid@Process@@AEAAKPEAXAEAVCHString@@@Z; Process::GetSid(void *,CHString &)
0x180090d53  mov     ebx, eax
0x180090d55  test    eax, eax
0x180090d57  jnz     loc_180090FD9
0x180090d5d  lea     rcx, [rsp+0D48h+var_AA8]
0x180090d65  call    cs:__imp_??0CRegistry@@QEAA@XZ; CRegistry::CRegistry(void)
0x180090d6b  nop
0x180090d6c  lea     rcx, [rsp+0D48h+var_CB8]
0x180090d74  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x180090d7a  mov     r8, rax
0x180090d7d  mov     rdx, 0FFFFFFFF80000003h
0x180090d84  mov     r9d, 20019h
0x180090d8a  lea     rcx, [rsp+0D48h+var_AA8]
0x180090d92  call    cs:__imp_?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z; CRegistry::Open(HKEY__ *,ushort const *,ulong)
0x180090d98  mov     esi, eax
0x180090d9a  mov     [rsp+0D48h+var_CD0], eax
0x180090d9e  lea     rcx, [rsp+0D48h+var_AA8]
0x180090da6  call    cs:__imp_?Close@CRegistry@@QEAAXXZ; CRegistry::Close(void)
0x180090dac  test    esi, esi
0x180090dae  jz      short loc_180090DE8
0x180090db0  lea     rcx, [rsp+0D48h+var_CA0]
0x180090db8  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x180090dbe  mov     r9d, 400h; unsigned __int64
0x180090dc4  lea     r8, [rsp+0D48h+SubKey]; unsigned __int16 *
0x180090dcc  mov     rdx, rax; lpAccountName
0x180090dcf  lea     rcx, [rsp+0D48h+VersionInformation]; this
0x180090dd7  call    ?LoadNT@CUserHive@@AEAAKPEBGPEAG_K@Z; CUserHive::LoadNT(ushort const *,ushort *,unsigned __int64)
0x180090ddc  mov     ebx, eax
0x180090dde  cmp     eax, 2
0x180090de1  cmovz   esi, edi
0x180090de4  mov     [rsp+0D48h+var_CD0], esi
0x180090de8  mov     eax, edi
0x180090dea  cmp     ebx, 2
0x180090ded  cmovnz  eax, ebx
0x180090df0  test    eax, eax
0x180090df2  jnz     loc_180090FC3
0x180090df8  mov     r14, rdi
0x180090dfb  mov     [rsp+0D48h+var_CD8], rdi
0x180090e00  mov     [rsp+0D48h+var_C98], rdi
0x180090e08  mov     rbx, [rsp+0D48h+arg_28]
0x180090e10  cmp     [rbx], rdi
0x180090e13  jnz     short loc_180090E74
0x180090e15  movups  xmm0, xmmword ptr cs:?g_guidUserEnvApi@@3U_GUID@@B.Data1; _GUID const g_guidUserEnvApi ...
0x180090e1c  movdqu  xmmword ptr [rsp+0D48h+var_C68.Data1], xmm0
0x180090e25  lea     rdx, [rsp+0D48h+var_C68]; struct _GUID
0x180090e2d  call    ?GetResource@CResourceManager@@QEAAPEAVCResource@@U_GUID@@PEAX@Z; CResourceManager::GetResource(_GUID,void *)
0x180090e32  mov     rdi, rax
0x180090e35  mov     [rsp+0D48h+var_C98], rax
0x180090e3d  test    rax, rax
0x180090e40  jz      short loc_180090E5B
0x180090e42  mov     r8, [rsp+0D48h+var_CC8]; void *
0x180090e4a  lea     rdx, [rsp+0D48h+var_CD8]; void **
0x180090e4f  mov     rcx, rax; this
0x180090e52  call    ?CreateEnvironmentBlock@CUserEnvApi@@QEAAHPEAPEAXPEAXH@Z; CUserEnvApi::CreateEnvironmentBlock(void * *,void *,int)
0x180090e57  test    eax, eax
0x180090e59  jnz     short loc_180090E6F
0x180090e5b  mov     ebx, 8
0x180090e60  mov     [rsp+0D48h+var_CE8], ebx
0x180090e64  call    cs:__imp_GetLastError
0x180090e6a  jmp     loc_180090F69
0x180090e6f  mov     r14, [rsp+0D48h+var_CD8]
0x180090e74  cmp     qword ptr [rbx], 0
0x180090e78  cmovnz  r14, [rbx]
0x180090e7c  lea     rax, [rsp+0D48h+var_C90]
0x180090e84  mov     qword ptr [rsp+0D48h+var_C78.Data1], rax
0x180090e8c  mov     rdx, r12
0x180090e8f  lea     rcx, [rsp+0D48h+var_C90]
0x180090e97  call    cs:__imp_??0CHString@@QEAA@AEBV0@@Z; CHString::CHString(CHString const &)
0x180090e9d  mov     rbx, rax
0x180090ea0  lea     rax, [rsp+0D48h+var_C88]
0x180090ea8  mov     qword ptr [rsp+0D48h+var_C68.Data1], rax
0x180090eb0  mov     rdx, r15
0x180090eb3  lea     rcx, [rsp+0D48h+var_C88]
0x180090ebb  call    cs:__imp_??0CHString@@QEAA@AEBV0@@Z; CHString::CHString(CHString const &)
0x180090ec1  mov     r9, rax
0x180090ec4  mov     r8, [rsp+0D48h+var_CC8]
0x180090ecc  movaps  xmm0, xmmword ptr [r13+0]
0x180090ed1  movaps  [rsp+0D48h+var_C48], xmm0
0x180090ed9  movaps  xmm1, xmmword ptr [r13+10h]
0x180090ede  movaps  [rsp+0D48h+var_C38], xmm1
0x180090ee6  movaps  xmm0, xmmword ptr [r13+20h]
0x180090eeb  movaps  [rsp+0D48h+var_C28], xmm0
0x180090ef3  movaps  xmm1, xmmword ptr [r13+30h]
0x180090ef8  movaps  [rsp+0D48h+var_C18], xmm1
0x180090f00  movaps  xmm0, xmmword ptr [r13+40h]
0x180090f05  movaps  [rsp+0D48h+var_C08], xmm0
0x180090f0d  movaps  xmm1, xmmword ptr [r13+50h]
0x180090f12  movaps  [rsp+0D48h+var_BF8], xmm1
0x180090f1a  movsd   xmm0, qword ptr [r13+60h]
0x180090f20  movsd   [rsp+0D48h+var_BE8], xmm0
0x180090f29  lea     rax, [rsp+0D48h+var_C48]
0x180090f31  mov     [rsp+0D48h+var_CF0], rax
0x180090f36  mov     eax, [rsp+0D48h+arg_40]
0x180090f3d  mov     [rsp+0D48h+var_D00], eax
0x180090f41  mov     [rsp+0D48h+var_D18], r14
0x180090f46  mov     [rsp+0D48h+phNewToken], rbx
0x180090f4b  mov     eax, [rsp+0D48h+var_CC0]
0x180090f52  mov     [rsp+0D48h+TokenType], eax
0x180090f56  mov     rdx, [rsp+0D48h+var_C80]
0x180090f5e  call    ?Creation@Process@@AEAAKPEAVCInstance@@PEAXVCHString@@H2PEAGHKKHU_STARTUPINFOW@@@Z; Process::Creation(CInstance *,void *,CHString,int,CHString,ushort *,int,ulong,ulong,int,_STARTUPINFOW)
0x180090f63  mov     ebx, eax
0x180090f65  mov     [rsp+0D48h+var_CE8], eax
0x180090f69  mov     rdx, [rsp+0D48h+var_CD8]; void *
0x180090f6e  test    rdx, rdx
0x180090f71  jz      short loc_180090F7B
0x180090f73  mov     rcx, rdi; this
0x180090f76  call    ?DestroyEnvironmentBlock@CUserEnvApi@@QEAAHPEAX@Z; CUserEnvApi::DestroyEnvironmentBlock(void *)
0x180090f7b  test    rdi, rdi
0x180090f7e  jz      short loc_180090FA8
0x180090f80  movups  xmm0, xmmword ptr cs:?g_guidUserEnvApi@@3U_GUID@@B.Data1; _GUID const g_guidUserEnvApi ...
0x180090f87  movdqu  xmmword ptr [rsp+0D48h+var_C78.Data1], xmm0
0x180090f90  mov     r8, rdi; struct CResource *
0x180090f93  lea     rdx, [rsp+0D48h+var_C78]; struct _GUID
0x180090f9b  lea     rcx, ?sm_TheResourceManager@CResourceManager@@2V1@A; this
0x180090fa2  call    ?ReleaseResource@CResourceManager@@QEAAKU_GUID@@PEAVCResource@@@Z; CResourceManager::ReleaseResource(_GUID,CResource *)
0x180090fa7  nop
0x180090fa8  test    esi, esi
0x180090faa  jz      short loc_180090FCA
0x180090fac  lea     rdx, [rsp+0D48h+SubKey]; lpSubKey
0x180090fb4  lea     rcx, [rsp+0D48h+VersionInformation]; this
0x180090fbc  call    ?Unload@CUserHive@@QEAAKPEBG@Z; CUserHive::Unload(ushort const *)
0x180090fc1  jmp     short loc_180090FCA
0x180090fc3  call    ?GetProcessErrorCode@Process@@AEAAKXZ; Process::GetProcessErrorCode(void)
0x180090fc8  mov     ebx, eax
0x180090fca  lea     rcx, [rsp+0D48h+var_AA8]
0x180090fd2  call    cs:__imp_??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x180090fd8  nop
0x180090fd9  lea     rcx, [rsp+0D48h+VersionInformation]; this
0x180090fe1  call    ??1CUserHive@@QEAA@XZ; CUserHive::~CUserHive(void)
0x180090fe6  nop
0x180090fe7  lea     rcx, [rsp+0D48h+var_CB8]
0x180090fef  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x180090ff5  nop
0x180090ff6  lea     rcx, [rsp+0D48h+var_CA0]
0x180090ffe  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x180091004  nop
0x180091005  lea     rcx, [rsp+0D48h+var_CB0]
0x18009100d  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x180091013  nop
0x180091014  lea     rcx, [rsp+0D48h+var_CA8]
0x18009101c  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x180091022  jmp     short loc_18009102B
0x180091024  call    ?GetProcessErrorCode@Process@@AEAAKXZ; Process::GetProcessErrorCode(void)
0x180091029  mov     ebx, eax
0x18009102b  lea     rcx, [rsp+0D48h+hExistingToken]; this
0x180091030  call    ??1SmartCloseHandle@@QEAA@XZ; SmartCloseHandle::~SmartCloseHandle(void)
0x180091035  nop
0x180091036  lea     rcx, [rsp+0D48h+var_CC8]; this
0x18009103e  call    ??1SmartCloseHandle@@QEAA@XZ; SmartCloseHandle::~SmartCloseHandle(void)
0x180091043  nop
0x180091044  mov     rcx, r15
0x180091047  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x18009104d  nop
0x18009104e  mov     rcx, r12
0x180091051  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x180091057  mov     eax, ebx
0x180091059  mov     rcx, [rsp+0D48h+var_48]
0x180091061  xor     rcx, rsp; StackCookie
0x180091064  call    __security_check_cookie
0x180091069  add     rsp, 0D10h
0x180091070  pop     r15
0x180091072  pop     r14
0x180091074  pop     r13
0x180091076  pop     r12
0x180091078  pop     rdi
0x180091079  pop     rsi
0x18009107a  pop     rbx
0x18009107b  retn
```
