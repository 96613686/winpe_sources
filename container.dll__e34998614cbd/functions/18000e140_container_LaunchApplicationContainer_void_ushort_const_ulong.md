# container::LaunchApplicationContainer(void *,ushort const *,ulong)

- ea: `0x18000e140`
- end: `0x18000e592`
- name: `?LaunchApplicationContainer@container@@YAPEAXPEAXPEBGK@Z`
- size: `1106`
- prototype: `void *(container *__hidden this, void *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180012540`

## callees

- `0x180002ad0`
- `0x180002ee4`
- `0x180002f1c`
- `0x180003614`
- `0x18000362c`
- `0x180004b7c`
- `0x180005038`
- `0x180006734`
- `0x180007674`
- `0x180007c2c`
- `0x18000bdec`
- `0x18000e140`
- `0x18000ff78`
- `0x18001054c`
- `0x180011fe8`

## import_xrefs

- `ntdll!NtClose` at `0x18000e4b4`
- `ntdll!NtClose` at `0x18000e4b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e32c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e398`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e32c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e398`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e34b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e3b7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e34b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e3b7`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000e36e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000e36e`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18000e236`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x18000e236`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18000e495`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x18000e495`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18000e275`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x18000e275`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e33d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e3a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e448`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e4e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e33d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e3a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e448`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e4e5`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000e3eb`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000e3eb`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x18000e41a`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x18000e41a`

## string_xrefs

- `0x18000e2fa`: `No service session running`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
HANDLE __fastcall container::LaunchApplicationContainer(container *this, _WORD *a2, const unsigned __int16 *a3)
{
  int v3; // esi
  __int64 v5; // rbx
  unsigned __int64 v6; // rbx
  void *v7; // r15
  const char *v8; // r9
  const char *v9; // r9
  DWORD v10; // esi
  void *v11; // rdx
  void *v12; // rdx
  const char *v13; // r9
  DWORD LastError; // ebx
  const char *v15; // r9
  const char *v16; // r9
  const char *v17; // r9
  HANDLE hProcess; // rbx
  unsigned __int64 v19; // rdx
  int cbSize; // [rsp+20h] [rbp-E0h]
  const char *lpReturnSize; // [rsp+30h] [rbp-D0h]
  HANDLE phNewToken; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int TokenInformation; // [rsp+68h] [rbp-98h] BYREF
  HANDLE hObject; // [rsp+70h] [rbp-90h] BYREF
  void *Value; // [rsp+78h] [rbp-88h] BYREF
  ULONG_PTR Size; // [rsp+80h] [rbp-80h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+88h] [rbp-78h] BYREF
  void *v29; // [rsp+A0h] [rbp-60h]
  struct _STARTUPINFOW StartupInfo; // [rsp+B0h] [rbp-50h] BYREF
  _OWORD *v31; // [rsp+118h] [rbp+18h]
  _OWORD v32[3]; // [rsp+120h] [rbp+20h] BYREF
  _QWORD v33[42]; // [rsp+150h] [rbp+50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  v3 = (int)a3;
  Value = this;
  wil::ActivityBase<ContainerProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ContainerProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v33,
    "LaunchApplicationContainer");
  v33[0] = &ContainerProvider::LaunchApplicationContainer::`vftable';
  ContainerProvider::LaunchApplicationContainer::StartActivity(
    (ContainerProvider::LaunchApplicationContainer *)v33,
    Value);
  phNewToken = 0;
  memset(v32, 0, sizeof(v32));
  Size = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(&StartupInfo, 0, 0x70u);
  v29 = 0;
  v5 = -1;
  do
    ++v5;
  while ( a2[v5] );
  v6 = v5 + 1;
  v7 = operator new[](saturated_mul(v6, 2u));
  v29 = v7;
  memcpy_0(v7, a2, 2 * v6);
  Size = 48;
  if ( !InitializeProcThreadAttributeList((LPPROC_THREAD_ATTRIBUTE_LIST)v32, 1u, 0, &Size) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x1D6,
      (unsigned int)"onecore\\base\\gendrv\\silos\\container\\container_runtime_i.cpp",
      v8);
  if ( !UpdateProcThreadAttribute((LPPROC_THREAD_ATTRIBUTE_LIST)v32, 0, 0x2000Du, &Value, 8u, 0, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x1DF,
      (unsigned int)"onecore\\base\\gendrv\\silos\\container\\container_runtime_i.cpp",
      v9);
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(&StartupInfo.cb + 1, 0, 0x64u);
  StartupInfo.cb = 112;
  v31 = v32;
  v10 = v3 | 0x80000;
  if ( container_runtime::IsServerContainer((container_runtime *)Value, v11) )
  {
    TokenInformation = container_runtime::GetServiceSessionId((container_runtime *)Value, v12);
    LOBYTE(cbSize) = TokenInformation == -1;
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0x1F6,
      (unsigned int)"onecore\\base\\gendrv\\silos\\container\\container_runtime_i.cpp",
      (const char *)0x800710D2LL,
      cbSize,
      (bool)"No service session running",
      lpReturnSize);
    hObject = 0;
    if ( !OpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0xF01FFu, &hObject) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x200,
        (unsigned int)"onecore\\base\\gendrv\\silos\\container\\container_runtime_i.cpp",
        v13);
    if ( (char *)phNewToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      LastError = GetLastError();
      CloseHandle(phNewToken);
      SetLastError(LastError);
    }
    phNewToken = 0;
    if ( !DuplicateTokenEx(hObject, 0xF01FFu, 0, SecurityIdentification, TokenPrimary, &phNewToken) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x208,
        (unsigned int)"onecore\\base\\gendrv\\silos\\container\\container_runtime_i.cpp",
        v15);
    if ( !SetTokenInformation(phNewToken, TokenSessionId, &TokenInformation, 4u) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x213,
        (unsigned int)"onecore\\base\\gendrv\\silos\\container\\container_runtime_i.cpp",
        v16);
    v10 |= 0x8000000u;
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
  }
  if ( !CreateProcessAsUserW(phNewToken, 0, (LPWSTR)v7, 0, 0, 1, v10, 0, 0, &StartupInfo, &ProcessInformation) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x22B,
      (unsigned int)"onecore\\base\\gendrv\\silos\\container\\container_runtime_i.cpp",
      v17);
  NtClose(ProcessInformation.hThread);
  wil::ActivityBase<ContainerProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v33);
  hProcess = ProcessInformation.hProcess;
  operator delete(v7, v19);
  if ( (char *)phNewToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(phNewToken);
  v33[0] = &ContainerProvider::LaunchApplicationContainer::`vftable';
  wil::ActivityBase<ContainerProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v33);
  wil::ActivityBase<ContainerProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ContainerProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(v33);
  return hProcess;
}

```

## disassembly

```asm
0x18000e140  mov     [rsp-8+arg_18], rbx
0x18000e145  push    rbp
0x18000e146  push    rsi
0x18000e147  push    rdi
0x18000e148  push    r12
0x18000e14a  push    r13
0x18000e14c  push    r14
0x18000e14e  push    r15
0x18000e150  lea     rbp, [rsp-1B0h]
0x18000e158  sub     rsp, 2B0h
0x18000e15f  mov     rax, cs:__security_cookie
0x18000e166  xor     rax, rsp
0x18000e169  mov     [rbp+1E0h+var_40], rax
0x18000e170  mov     esi, r8d
0x18000e173  mov     rdi, rdx
0x18000e176  mov     [rsp+2E0h+Value], rcx
0x18000e17b  lea     rdx, aLaunchapplicat_0; "LaunchApplicationContainer"
0x18000e182  lea     rcx, [rbp+1E0h+var_190]
0x18000e186  call    ??0?$ActivityBase@VContainerProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ContainerProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ContainerProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000e18b  lea     r13, ??_7LaunchApplicationContainer@ContainerProvider@@6B@; const ContainerProvider::LaunchApplicationContainer::`vftable'
0x18000e192  mov     [rbp+1E0h+var_190], r13
0x18000e196  mov     rdx, [rsp+2E0h+Value]; void *
0x18000e19b  lea     rcx, [rbp+1E0h+var_190]; this
0x18000e19f  call    ?StartActivity@LaunchApplicationContainer@ContainerProvider@@QEAAXPEAX@Z; ContainerProvider::LaunchApplicationContainer::StartActivity(void *)
0x18000e1a4  nop
0x18000e1a5  xor     r12d, r12d
0x18000e1a8  mov     [rsp+2E0h+phNewToken], r12
0x18000e1ad  xorps   xmm0, xmm0
0x18000e1b0  movups  [rbp+1E0h+var_1C0], xmm0
0x18000e1b4  movups  [rbp+1E0h+var_1B0], xmm0
0x18000e1b8  movups  [rbp+1E0h+var_1A0], xmm0
0x18000e1bc  mov     [rbp+1E0h+Size], r12
0x18000e1c0  xor     eax, eax
0x18000e1c2  movups  xmmword ptr [rbp+1E0h+ProcessInformation.hProcess], xmm0
0x18000e1c6  mov     qword ptr [rbp+1E0h+ProcessInformation.dwProcessId], rax
0x18000e1ca  lea     r14d, [r12+70h]
0x18000e1cf  mov     r8d, r14d; Size
0x18000e1d2  xor     edx, edx; Val
0x18000e1d4  lea     rcx, [rbp+1E0h+StartupInfo]; void *
0x18000e1d8  call    memset_0
0x18000e1dd  mov     [rbp+1E0h+var_240], r12
0x18000e1e1  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000e1e5  mov     rbx, rcx
0x18000e1e8  inc     rbx
0x18000e1eb  cmp     [rdi+rbx*2], r12w
0x18000e1f0  jnz     short loc_18000E1E8
0x18000e1f2  inc     rbx
0x18000e1f5  mov     eax, 2
0x18000e1fa  mul     rbx
0x18000e1fd  cmovb   rax, rcx
0x18000e201  mov     rcx, rax; unsigned __int64
0x18000e204  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000e209  mov     r15, rax
0x18000e20c  mov     [rbp+1E0h+var_240], rax
0x18000e210  lea     r8, [rbx+rbx]; Size
0x18000e214  mov     rdx, rdi; Src
0x18000e217  mov     rcx, rax; void *
0x18000e21a  call    memcpy_0
0x18000e21f  mov     [rbp+1E0h+Size], 30h ; '0'
0x18000e227  lea     r9, [rbp+1E0h+Size]; lpSize
0x18000e22b  xor     r8d, r8d; dwFlags
0x18000e22e  lea     edx, [r8+1]; dwAttributeCount
0x18000e232  lea     rcx, [rbp+1E0h+var_1C0]; lpAttributeList
0x18000e236  call    cs:__imp_InitializeProcThreadAttributeList
0x18000e23d  nop     dword ptr [rax+rax+00h]
0x18000e242  mov     rcx, [rbp+1E8h]; this
0x18000e249  test    eax, eax
0x18000e24b  jz      loc_18000E544
0x18000e251  mov     [rsp+2E0h+lpReturnSize], r12; char *
0x18000e256  mov     [rsp+2E0h+lpPreviousValue], r12; lpPreviousValue
0x18000e25b  mov     [rsp+2E0h+cbSize], 8; cbSize
0x18000e264  lea     r9, [rsp+2E0h+Value]; lpValue
0x18000e269  xor     edx, edx; dwFlags
0x18000e26b  mov     r8d, 2000Dh; Attribute
0x18000e271  lea     rcx, [rbp+1E0h+var_1C0]; lpAttributeList
0x18000e275  call    cs:__imp_UpdateProcThreadAttribute
0x18000e27c  nop     dword ptr [rax+rax+00h]
0x18000e281  mov     rcx, [rbp+1E8h]; this
0x18000e288  test    eax, eax
0x18000e28a  jz      loc_18000E556
0x18000e290  xorps   xmm0, xmm0
0x18000e293  xor     eax, eax
0x18000e295  movups  xmmword ptr [rbp+1E0h+ProcessInformation.hProcess], xmm0
0x18000e299  mov     qword ptr [rbp+1E0h+ProcessInformation.dwProcessId], rax
0x18000e29d  xor     edx, edx; Val
0x18000e29f  lea     r8d, [rax+64h]; Size
0x18000e2a3  lea     rcx, [rbp+1E0h+StartupInfo+4]; void *
0x18000e2a7  call    memset_0
0x18000e2ac  mov     [rbp+1E0h+StartupInfo.cb], r14d
0x18000e2b0  lea     rax, [rbp+1E0h+var_1C0]
0x18000e2b4  mov     [rbp+1E0h+var_1C8], rax
0x18000e2b8  bts     esi, 13h
0x18000e2bc  mov     rcx, [rsp+2E0h+Value]; this
0x18000e2c1  call    ?IsServerContainer@container_runtime@@YA_NPEAX@Z; container_runtime::IsServerContainer(void *)
0x18000e2c6  lea     rdi, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\container"...
0x18000e2cd  test    al, al
0x18000e2cf  jz      loc_18000E45B
0x18000e2d5  mov     [rsp+2E0h+hObject], r12
0x18000e2da  mov     [rsp+2E0h+TokenInformation], r12d
0x18000e2df  mov     rcx, [rsp+2E0h+Value]; this
0x18000e2e4  call    ?GetServiceSessionId@container_runtime@@YAKPEAX@Z; container_runtime::GetServiceSessionId(void *)
0x18000e2e9  mov     [rsp+2E0h+TokenInformation], eax
0x18000e2ed  cmp     eax, 0FFFFFFFFh
0x18000e2f0  setz    al
0x18000e2f3  mov     rcx, [rbp+1E8h]; this
0x18000e2fa  lea     rdx, aNoServiceSessi; "No service session running"
0x18000e301  mov     [rsp+2E0h+lpPreviousValue], rdx; bool
0x18000e306  mov     byte ptr [rsp+2E0h+cbSize], al; int
0x18000e30a  mov     r9d, 800710D2h; char *
0x18000e310  mov     r8, rdi; unsigned int
0x18000e313  mov     edx, 1F6h; void *
0x18000e318  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18000e31d  mov     r14, [rsp+2E0h+hObject]
0x18000e322  lea     rax, [r14-1]
0x18000e326  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000e32a  ja      short loc_18000E357
0x18000e32c  call    cs:__imp_GetLastError
0x18000e333  nop     dword ptr [rax+rax+00h]
0x18000e338  mov     ebx, eax
0x18000e33a  mov     rcx, r14; hObject
0x18000e33d  call    cs:__imp_CloseHandle
0x18000e344  nop     dword ptr [rax+rax+00h]
0x18000e349  mov     ecx, ebx; dwErrCode
0x18000e34b  call    cs:__imp_SetLastError
0x18000e352  nop     dword ptr [rax+rax+00h]
0x18000e357  mov     [rsp+2E0h+hObject], r12
0x18000e35c  lea     r8, [rsp+2E0h+hObject]; TokenHandle
0x18000e361  mov     r13d, 0F01FFh
0x18000e367  mov     edx, r13d; DesiredAccess
0x18000e36a  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18000e36e  call    cs:__imp_OpenProcessToken
0x18000e375  nop     dword ptr [rax+rax+00h]
0x18000e37a  mov     rcx, [rbp+1E8h]; this
0x18000e381  test    eax, eax
0x18000e383  jz      loc_18000E568
0x18000e389  mov     r14, [rsp+2E0h+phNewToken]
0x18000e38e  lea     rax, [r14-1]
0x18000e392  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000e396  ja      short loc_18000E3C3
0x18000e398  call    cs:__imp_GetLastError
0x18000e39f  nop     dword ptr [rax+rax+00h]
0x18000e3a4  mov     ebx, eax
0x18000e3a6  mov     rcx, r14; hObject
0x18000e3a9  call    cs:__imp_CloseHandle
0x18000e3b0  nop     dword ptr [rax+rax+00h]
0x18000e3b5  mov     ecx, ebx; dwErrCode
0x18000e3b7  call    cs:__imp_SetLastError
0x18000e3be  nop     dword ptr [rax+rax+00h]
0x18000e3c3  mov     [rsp+2E0h+phNewToken], r12
0x18000e3c8  lea     rax, [rsp+2E0h+phNewToken]
0x18000e3cd  mov     [rsp+2E0h+lpPreviousValue], rax; phNewToken
0x18000e3d2  mov     dword ptr [rsp+2E0h+cbSize], 1; TokenType
0x18000e3da  mov     r9d, 1; ImpersonationLevel
0x18000e3e0  xor     r8d, r8d; lpTokenAttributes
0x18000e3e3  mov     edx, r13d; dwDesiredAccess
0x18000e3e6  mov     rcx, [rsp+2E0h+hObject]; hExistingToken
0x18000e3eb  call    cs:__imp_DuplicateTokenEx
0x18000e3f2  nop     dword ptr [rax+rax+00h]
0x18000e3f7  mov     rcx, [rbp+1E8h]; this
0x18000e3fe  test    eax, eax
0x18000e400  jz      loc_18000E576
0x18000e406  mov     r9d, 4; TokenInformationLength
0x18000e40c  lea     r8, [rsp+2E0h+TokenInformation]; TokenInformation
0x18000e411  lea     edx, [r9+8]; TokenInformationClass
0x18000e415  mov     rcx, [rsp+2E0h+phNewToken]; TokenHandle
0x18000e41a  call    cs:__imp_SetTokenInformation
0x18000e421  nop     dword ptr [rax+rax+00h]
0x18000e426  mov     rcx, [rbp+1E8h]; this
0x18000e42d  test    eax, eax
0x18000e42f  jz      loc_18000E584
0x18000e435  bts     esi, 1Bh
0x18000e439  mov     rcx, [rsp+2E0h+hObject]; hObject
0x18000e43e  lea     rax, [rcx-1]
0x18000e442  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000e446  ja      short loc_18000E454
0x18000e448  call    cs:__imp_CloseHandle
0x18000e44f  nop     dword ptr [rax+rax+00h]
0x18000e454  lea     r13, ??_7LaunchApplicationContainer@ContainerProvider@@6B@; const ContainerProvider::LaunchApplicationContainer::`vftable'
0x18000e45b  lea     rax, [rbp+1E0h+ProcessInformation]
0x18000e45f  mov     [rsp+2E0h+lpProcessInformation], rax; lpProcessInformation
0x18000e464  lea     rax, [rbp+1E0h+StartupInfo]
0x18000e468  mov     [rsp+2E0h+lpStartupInfo], rax; lpStartupInfo
0x18000e46d  mov     [rsp+2E0h+lpCurrentDirectory], r12; lpCurrentDirectory
0x18000e472  mov     [rsp+2E0h+lpEnvironment], r12; lpEnvironment
0x18000e477  mov     dword ptr [rsp+2E0h+lpReturnSize], esi; dwCreationFlags
0x18000e47b  mov     dword ptr [rsp+2E0h+lpPreviousValue], 1; bInheritHandles
0x18000e483  mov     [rsp+2E0h+cbSize], r12; lpThreadAttributes
0x18000e488  xor     r9d, r9d; lpProcessAttributes
0x18000e48b  mov     r8, r15; lpCommandLine
0x18000e48e  xor     edx, edx; lpApplicationName
0x18000e490  mov     rcx, [rsp+2E0h+phNewToken]; hToken
0x18000e495  call    cs:__imp_CreateProcessAsUserW
0x18000e49c  nop     dword ptr [rax+rax+00h]
0x18000e4a1  mov     rcx, [rbp+1E8h]; this
0x18000e4a8  test    eax, eax
0x18000e4aa  jz      loc_18000E536
0x18000e4b0  mov     rcx, [rbp+1E0h+ProcessInformation.hThread]; Handle
0x18000e4b4  call    cs:__imp_NtClose
0x18000e4bb  nop     dword ptr [rax+rax+00h]
0x18000e4c0  lea     rcx, [rbp+1E0h+var_190]
0x18000e4c4  call    ?Stop@?$ActivityBase@VContainerProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ContainerProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18000e4c9  mov     rbx, [rbp+1E0h+ProcessInformation.hProcess]
0x18000e4cd  mov     rcx, r15; void *
0x18000e4d0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e4d5  nop
0x18000e4d6  mov     rcx, [rsp+2E0h+phNewToken]; hObject
0x18000e4db  lea     rdx, [rcx-1]
0x18000e4df  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18000e4e3  ja      short loc_18000E4F2
0x18000e4e5  call    cs:__imp_CloseHandle
0x18000e4ec  nop     dword ptr [rax+rax+00h]
0x18000e4f1  nop
0x18000e4f2  mov     [rbp+1E0h+var_190], r13
0x18000e4f6  lea     rcx, [rbp+1E0h+var_190]
0x18000e4fa  call    ?Destroy@?$ActivityBase@VContainerProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ContainerProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18000e4ff  lea     rcx, [rbp+1E0h+var_190]
0x18000e503  call    ??1?$ActivityBase@VContainerProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ContainerProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ContainerProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18000e508  mov     rax, rbx
0x18000e50b  mov     rcx, [rbp+1E0h+var_40]
0x18000e512  xor     rcx, rsp; StackCookie
0x18000e515  call    __security_check_cookie
0x18000e51a  mov     rbx, [rsp+2E0h+arg_18]
0x18000e522  add     rsp, 2B0h
0x18000e529  pop     r15
0x18000e52b  pop     r14
0x18000e52d  pop     r13
0x18000e52f  pop     r12
0x18000e531  pop     rdi
0x18000e532  pop     rsi
0x18000e533  pop     rbp
0x18000e534  retn
0x18000e536  mov     r8, rdi; unsigned int
0x18000e539  mov     edx, 22Bh; void *
0x18000e53e  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000e544  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\container"...
0x18000e54b  mov     edx, 1D6h; void *
0x18000e550  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000e556  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\container"...
0x18000e55d  mov     edx, 1DFh; void *
0x18000e562  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000e568  mov     r8, rdi; unsigned int
0x18000e56b  mov     edx, 200h; void *
0x18000e570  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000e576  mov     r8, rdi; unsigned int
0x18000e579  mov     edx, 208h; void *
0x18000e57e  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000e584  mov     r8, rdi; unsigned int
0x18000e587  mov     edx, 213h; void *
0x18000e58c  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
