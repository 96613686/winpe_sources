# RebootCSP::Reboot::RebootNow(void)

- ea: `0x180062e54`
- end: `0x180063086`
- name: `?RebootNow@Reboot@RebootCSP@@QEAAXXZ`
- size: `562`
- prototype: `void __fastcall(RebootCSP::Reboot *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180061810`

## callees

- `0x180008de0`
- `0x180024d8c`
- `0x18004568c`
- `0x180048624`
- `0x180062e54`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180062fa5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180062fa5`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180062eb3`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180062eb3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180062e9a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180062e9a`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180062f48`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18006304e`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180062f48`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18006304e`
- `api-ms-win-core-shutdown-l1-1-0!InitiateSystemShutdownExW` at `0x180062fd2`
- `api-ms-win-core-shutdown-l1-1-0!InitiateSystemShutdownExW` at `0x180062ffe`
- `api-ms-win-core-shutdown-l1-1-0!InitiateSystemShutdownExW` at `0x180062fd2`
- `api-ms-win-core-shutdown-l1-1-0!InitiateSystemShutdownExW` at `0x180062ffe`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180062ee8`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180062ee8`

## string_xrefs

- `0x180062edf`: `SeShutdownPrivilege`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall RebootCSP::Reboot::RebootNow(HINSTANCE *this)
{
  HANDLE CurrentProcess; // rax
  const char *v3; // r9
  const char *v4; // r9
  const char *v5; // r9
  const char *v6; // r9
  const char *v7; // r9
  void *TokenHandle; // [rsp+30h] [rbp-D0h] BYREF
  LONG HighPart; // [rsp+38h] [rbp-C8h] BYREF
  struct _LUID *v10; // [rsp+40h] [rbp-C0h]
  LONG *p_HighPart; // [rsp+48h] [rbp-B8h]
  void **p_TokenHandle; // [rsp+50h] [rbp-B0h]
  char v13; // [rsp+58h] [rbp-A8h]
  struct _LUID Luid[2]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Buffer[264]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  TokenHandle = 0;
  *(_OWORD *)&Luid[0].LowPart = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &TokenHandle,
    0);
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x53,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\reboot\\reboot.cpp",
      v3);
  if ( !LookupPrivilegeValueW(0, L"SeShutdownPrivilege", (PLUID)&Luid[0].HighPart) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x55,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\reboot\\reboot.cpp",
      v4);
  Luid[0].LowPart = 1;
  HighPart = Luid[1].HighPart;
  Luid[1].HighPart = 2;
  if ( !AdjustTokenPrivileges(TokenHandle, 0, (PTOKEN_PRIVILEGES)Luid, 0, 0, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x5B,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\reboot\\reboot.cpp",
      v5);
  v10 = Luid;
  p_HighPart = &HighPart;
  p_TokenHandle = &TokenHandle;
  v13 = 1;
  if ( LoadStringW(*this, 0x65E9u, Buffer, 260) )
  {
    if ( !InitiateSystemShutdownExW(0, Buffer, 0x12Cu, 0, 1, 0x50004u) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x6B,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\reboot\\reboot.cpp",
        v7);
  }
  else if ( !InitiateSystemShutdownExW(0, 0, 0x12Cu, 0, 1, 0x50004u) )
  {
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x67,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\reboot\\reboot.cpp",
      v6);
  }
  Luid[1].HighPart = HighPart;
  AdjustTokenPrivileges(TokenHandle, 0, (PTOKEN_PRIVILEGES)Luid, 0, 0, 0);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
}

```

## disassembly

```asm
0x180062e54  mov     [rsp-8+arg_8], rbx
0x180062e59  push    rbp
0x180062e5a  lea     rbp, [rsp-190h]
0x180062e62  sub     rsp, 290h
0x180062e69  mov     rax, cs:__security_cookie
0x180062e70  xor     rax, rsp
0x180062e73  mov     [rbp+190h+var_10], rax
0x180062e7a  mov     rbx, rcx
0x180062e7d  mov     [rsp+290h+TokenHandle], 0
0x180062e86  xorps   xmm0, xmm0
0x180062e89  movups  xmmword ptr [rsp+290h+Luid.LowPart], xmm0
0x180062e8e  xor     edx, edx
0x180062e90  lea     rcx, [rsp+290h+TokenHandle]
0x180062e95  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180062e9a  call    cs:__imp_GetCurrentProcess
0x180062ea1  nop     dword ptr [rax+rax+00h]
0x180062ea6  lea     r8, [rsp+290h+TokenHandle]; TokenHandle
0x180062eab  mov     edx, 28h ; '('; DesiredAccess
0x180062eb0  mov     rcx, rax; ProcessHandle
0x180062eb3  call    cs:__imp_OpenProcessToken
0x180062eba  nop     dword ptr [rax+rax+00h]
0x180062ebf  mov     rcx, [rbp+198h]; this
0x180062ec6  test    eax, eax
0x180062ec8  jnz     short loc_180062EDA
0x180062eca  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180062ed1  lea     edx, [rax+53h]; void *
0x180062ed4  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180062eda  lea     r8, [rsp+290h+Luid.HighPart]; lpLuid
0x180062edf  lea     rdx, Name; "SeShutdownPrivilege"
0x180062ee6  xor     ecx, ecx; lpSystemName
0x180062ee8  call    cs:__imp_LookupPrivilegeValueW
0x180062eef  nop     dword ptr [rax+rax+00h]
0x180062ef4  mov     rcx, [rbp+198h]; this
0x180062efb  test    eax, eax
0x180062efd  jnz     short loc_180062F0F
0x180062eff  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180062f06  lea     edx, [rax+55h]; void *
0x180062f09  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180062f0f  mov     [rsp+290h+Luid.LowPart], 1
0x180062f17  mov     eax, [rsp+290h+Luid.HighPart+8]
0x180062f1b  mov     [rsp+290h+var_258], eax
0x180062f1f  mov     [rsp+290h+Luid.HighPart+8], 2
0x180062f27  mov     [rsp+290h+ReturnLength], 0; ReturnLength
0x180062f30  mov     [rsp+290h+PreviousState], 0; PreviousState
0x180062f39  xor     r9d, r9d; BufferLength
0x180062f3c  lea     r8, [rsp+290h+Luid]; NewState
0x180062f41  xor     edx, edx; DisableAllPrivileges
0x180062f43  mov     rcx, [rsp+290h+TokenHandle]; TokenHandle
0x180062f48  call    cs:__imp_AdjustTokenPrivileges
0x180062f4f  nop     dword ptr [rax+rax+00h]
0x180062f54  mov     rcx, [rbp+198h]; this
0x180062f5b  test    eax, eax
0x180062f5d  jnz     short loc_180062F6F
0x180062f5f  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180062f66  lea     edx, [rax+5Bh]; void *
0x180062f69  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180062f6f  lea     rax, [rsp+290h+Luid]
0x180062f74  mov     [rsp+290h+var_250], rax
0x180062f79  lea     rax, [rsp+290h+var_258]
0x180062f7e  mov     [rsp+290h+var_248], rax
0x180062f83  lea     rax, [rsp+290h+TokenHandle]
0x180062f88  mov     [rsp+290h+var_240], rax
0x180062f8d  mov     [rsp+290h+var_238], 1
0x180062f92  mov     r9d, 104h; cchBufferMax
0x180062f98  lea     r8, [rsp+290h+Buffer]; lpBuffer
0x180062f9d  mov     edx, 65E9h; uID
0x180062fa2  mov     rcx, [rbx]; hInstance
0x180062fa5  call    cs:__imp_LoadStringW
0x180062fac  nop     dword ptr [rax+rax+00h]
0x180062fb1  mov     dword ptr [rsp+290h+ReturnLength], 50004h; dwReason
0x180062fb9  xor     r9d, r9d; bForceAppsClosed
0x180062fbc  mov     r8d, 12Ch; dwTimeout
0x180062fc2  xor     ecx, ecx; lpMachineName
0x180062fc4  mov     dword ptr [rsp+290h+PreviousState], 1; bRebootAfterShutdown
0x180062fcc  test    eax, eax
0x180062fce  jnz     short loc_180062FF9
0x180062fd0  xor     edx, edx; lpMessage
0x180062fd2  call    cs:__imp_InitiateSystemShutdownExW
0x180062fd9  nop     dword ptr [rax+rax+00h]
0x180062fde  mov     rcx, [rbp+198h]; this
0x180062fe5  test    eax, eax
0x180062fe7  jnz     short loc_180063025
0x180062fe9  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180062ff0  lea     edx, [rax+67h]; void *
0x180062ff3  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180062ff9  lea     rdx, [rsp+290h+Buffer]; lpMessage
0x180062ffe  call    cs:__imp_InitiateSystemShutdownExW
0x180063005  nop     dword ptr [rax+rax+00h]
0x18006300a  mov     rcx, [rbp+198h]; this
0x180063011  test    eax, eax
0x180063013  jnz     short loc_180063025
0x180063015  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18006301c  lea     edx, [rax+6Bh]; void *
0x18006301f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180063025  mov     eax, [rsp+290h+var_258]
0x180063029  mov     [rsp+290h+Luid.HighPart+8], eax
0x18006302d  mov     [rsp+290h+ReturnLength], 0; ReturnLength
0x180063036  mov     [rsp+290h+PreviousState], 0; PreviousState
0x18006303f  xor     r9d, r9d; BufferLength
0x180063042  lea     r8, [rsp+290h+Luid]; NewState
0x180063047  xor     edx, edx; DisableAllPrivileges
0x180063049  mov     rcx, [rsp+290h+TokenHandle]; TokenHandle
0x18006304e  call    cs:__imp_AdjustTokenPrivileges
0x180063055  nop     dword ptr [rax+rax+00h]
0x18006305a  nop
0x18006305b  lea     rcx, [rsp+290h+TokenHandle]
0x180063060  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180063065  mov     rcx, [rbp+190h+var_10]
0x18006306c  xor     rcx, rsp; StackCookie
0x18006306f  call    __security_check_cookie
0x180063074  mov     rbx, [rsp+290h+arg_8]
0x18006307c  add     rsp, 290h
0x180063083  pop     rbp
0x180063084  retn
```
