# ProvAgent::ProvAgent(void)

- ea: `0x180032c84`
- end: `0x180032e4d`
- name: `??0ProvAgent@@QEAA@XZ`
- size: `457`
- prototype: `ProvAgent *__fastcall(ProvAgent *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180008ab0`
- `0x180023680`

## callees

- `0x180001a70`
- `0x180024508`
- `0x180032c84`
- `0x18003307c`
- `0x1800358a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032d08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032d08`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180032d2c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180032d2c`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x180032d1e`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x180032e0a`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x180032d1e`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x180032e0a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180032ce4`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180032ce4`

## string_xrefs

- `0x180032d69`: `Global\ProvisioningAgentMutex`
- `0x180032e3b`: `onecoreuap\admin\prov\lib\provagent.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
ProvAgent *__fastcall ProvAgent::ProvAgent(ProvAgent *this)
{
  int v2; // r8d
  const char *v3; // r9
  BOOL v4; // r12d
  PSECURITY_DESCRIPTOR v5; // r15
  void **v6; // rsi
  void *v7; // r14
  DWORD LastError; // ebx
  int v9; // r8d
  int v10; // r9d
  void *v12; // [rsp+30h] [rbp-49h] BYREF
  PSECURITY_DESCRIPTOR ObjectDescriptor; // [rsp+38h] [rbp-41h] BYREF
  struct _SECURITY_ATTRIBUTES MutexAttributes; // [rsp+40h] [rbp-39h] BYREF
  ProvAgent *v15; // [rsp+58h] [rbp-21h]
  void **v16; // [rsp+60h] [rbp-19h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+68h] [rbp-11h] BYREF
  char v18; // [rsp+70h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v15 = this;
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  v12 = 0;
  v16 = &v12;
  SecurityDescriptor = 0;
  v18 = 1;
  v4 = ConvertStringSecurityDescriptorToSecurityDescriptorW(L"D:(A;;GA;;;BA)(A;;GA;;;SY)", 1u, &SecurityDescriptor, 0);
  if ( v18 )
  {
    v5 = SecurityDescriptor;
    v6 = v16;
    v7 = *v16;
    if ( *v16 )
    {
      LastError = GetLastError();
      ObjectDescriptor = v7;
      DestroyPrivateObjectSecurity(&ObjectDescriptor);
      SetLastError(LastError);
    }
    *v6 = v5;
  }
  if ( !v4 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x19,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provagent.cpp",
      v3);
  *(_QWORD *)&MutexAttributes.nLength = 24;
  *(_QWORD *)&MutexAttributes.bInheritHandle = 0;
  MutexAttributes.lpSecurityDescriptor = v12;
  _create___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXPEBGKKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    (int)this,
    (int)L"Global\\ProvisioningAgentMutex",
    v2,
    (int)v3,
    &MutexAttributes);
  if ( (unsigned int)dword_1800495B0 > 4 )
    tlgWriteTransfer_EventWriteTransfer(&dword_1800495B0, byte_180041AEB, 0, 0, 2, &v16);
  _create___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXPEBGKKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    (_DWORD)this + 8,
    (int)L"Global\\ProvisioningTurnMutex",
    v9,
    v10,
    &MutexAttributes);
  if ( (unsigned int)dword_1800495B0 > 4 )
    tlgWriteTransfer_EventWriteTransfer(&dword_1800495B0, &dword_180041AC4, 0, 0, 2, &v16);
  if ( v12 )
  {
    ObjectDescriptor = v12;
    DestroyPrivateObjectSecurity(&ObjectDescriptor);
  }
  return this;
}

```

## disassembly

```asm
0x180032c84  push    rbp
0x180032c86  push    rbx
0x180032c87  push    rsi
0x180032c88  push    rdi
0x180032c89  push    r12
0x180032c8b  push    r13
0x180032c8d  push    r14
0x180032c8f  push    r15
0x180032c91  lea     rbp, [rsp-1Fh]
0x180032c96  sub     rsp, 98h
0x180032c9d  mov     rax, cs:__security_cookie
0x180032ca4  xor     rax, rsp
0x180032ca7  mov     [rbp+57h+var_50], rax
0x180032cab  mov     rdi, rcx
0x180032cae  mov     [rbp+57h+var_78], rcx
0x180032cb2  xor     ebx, ebx
0x180032cb4  mov     [rcx], rbx
0x180032cb7  mov     [rcx+8], rbx
0x180032cbb  mov     [rcx+10h], rbx
0x180032cbf  mov     [rbp+57h+var_A0], rbx
0x180032cc3  lea     rax, [rbp+57h+var_A0]
0x180032cc7  mov     [rbp+57h+var_70], rax
0x180032ccb  mov     [rbp+57h+SecurityDescriptor], rbx
0x180032ccf  mov     [rbp+57h+var_60], 1
0x180032cd3  xor     r9d, r9d; SecurityDescriptorSize
0x180032cd6  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x180032cda  lea     edx, [rbx+1]; StringSDRevision
0x180032cdd  lea     rcx, StringSecurityDescriptor; "D:(A;;GA;;;BA)(A;;GA;;;SY)"
0x180032ce4  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180032ceb  nop     dword ptr [rax+rax+00h]
0x180032cf0  mov     r12d, eax
0x180032cf3  cmp     [rbp+57h+var_60], bl
0x180032cf6  jz      short loc_180032D3B
0x180032cf8  mov     r15, [rbp+57h+SecurityDescriptor]
0x180032cfc  mov     rsi, [rbp+57h+var_70]
0x180032d00  mov     r14, [rsi]
0x180032d03  test    r14, r14
0x180032d06  jz      short loc_180032D38
0x180032d08  call    cs:__imp_GetLastError
0x180032d0f  nop     dword ptr [rax+rax+00h]
0x180032d14  mov     ebx, eax
0x180032d16  mov     [rbp+57h+ObjectDescriptor], r14
0x180032d1a  lea     rcx, [rbp+57h+ObjectDescriptor]; ObjectDescriptor
0x180032d1e  call    cs:__imp_DestroyPrivateObjectSecurity
0x180032d25  nop     dword ptr [rax+rax+00h]
0x180032d2a  mov     ecx, ebx; dwErrCode
0x180032d2c  call    cs:__imp_SetLastError
0x180032d33  nop     dword ptr [rax+rax+00h]
0x180032d38  mov     [rsi], r15
0x180032d3b  mov     rcx, [rbp+5Fh]; this
0x180032d3f  test    r12d, r12d
0x180032d42  jz      loc_180032E3B
0x180032d48  mov     qword ptr [rbp+57h+MutexAttributes.nLength], 18h
0x180032d50  mov     qword ptr [rbp+57h+MutexAttributes.bInheritHandle], 0
0x180032d58  mov     rax, [rbp+57h+var_A0]
0x180032d5c  mov     [rbp+57h+MutexAttributes.lpSecurityDescriptor], rax
0x180032d60  lea     rax, [rbp+57h+MutexAttributes]
0x180032d64  mov     [rsp+0D0h+lpMutexAttributes], rax; lpMutexAttributes
0x180032d69  lea     rdx, ?c_provMutexName@@3QBGB; "Global\\ProvisioningAgentMutex"
0x180032d70  mov     rcx, rdi; int
0x180032d73  call    ?create@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180032d78  mov     eax, cs:dword_1800495B0
0x180032d7e  mov     esi, 2
0x180032d83  cmp     eax, 4
0x180032d86  jbe     short loc_180032DAE
0x180032d88  lea     rax, [rbp+57h+var_70]
0x180032d8c  mov     [rsp+0D0h+var_A8], rax
0x180032d91  mov     dword ptr [rsp+0D0h+lpMutexAttributes], esi
0x180032d95  xor     r9d, r9d
0x180032d98  xor     r8d, r8d
0x180032d9b  lea     rdx, byte_180041AEB
0x180032da2  lea     rcx, dword_1800495B0
0x180032da9  call    _tlgWriteTransfer_EventWriteTransfer
0x180032dae  lea     rax, [rbp+57h+MutexAttributes]
0x180032db2  mov     [rsp+0D0h+lpMutexAttributes], rax; lpMutexAttributes
0x180032db7  lea     rdx, ?c_turnMutexName@@3QBGB; "Global\\ProvisioningTurnMutex"
0x180032dbe  lea     rcx, [rdi+8]; int
0x180032dc2  call    ?create@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180032dc7  mov     eax, cs:dword_1800495B0
0x180032dcd  cmp     eax, 4
0x180032dd0  jbe     short loc_180032DF9
0x180032dd2  lea     rax, [rbp+57h+var_70]
0x180032dd6  mov     [rsp+0D0h+var_A8], rax
0x180032ddb  mov     dword ptr [rsp+0D0h+lpMutexAttributes], esi
0x180032ddf  xor     r9d, r9d
0x180032de2  xor     r8d, r8d
0x180032de5  lea     rdx, dword_180041AC4
0x180032dec  lea     rcx, dword_1800495B0
0x180032df3  call    _tlgWriteTransfer_EventWriteTransfer
0x180032df8  nop
0x180032df9  mov     rcx, [rbp+57h+var_A0]
0x180032dfd  test    rcx, rcx
0x180032e00  jz      short loc_180032E17
0x180032e02  mov     [rbp+57h+ObjectDescriptor], rcx
0x180032e06  lea     rcx, [rbp+57h+ObjectDescriptor]; ObjectDescriptor
0x180032e0a  call    cs:__imp_DestroyPrivateObjectSecurity
0x180032e11  nop     dword ptr [rax+rax+00h]
0x180032e16  nop
0x180032e17  mov     rax, rdi
0x180032e1a  mov     rcx, [rbp+57h+var_50]
0x180032e1e  xor     rcx, rsp; StackCookie
0x180032e21  call    __security_check_cookie
0x180032e26  add     rsp, 98h
0x180032e2d  pop     r15
0x180032e2f  pop     r14
0x180032e31  pop     r13
0x180032e33  pop     r12
0x180032e35  pop     rdi
0x180032e36  pop     rsi
0x180032e37  pop     rbx
0x180032e38  pop     rbp
0x180032e39  retn
0x180032e3b  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\prov\\lib\\provagent"...
0x180032e42  mov     edx, 19h; void *
0x180032e47  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
