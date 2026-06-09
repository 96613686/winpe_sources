# ProvAgent::ProvAgent(void)

- ea: `0x18002a170`
- end: `0x18002a312`
- name: `??0ProvAgent@@QEAA@XZ`
- size: `418`
- prototype: `ProvAgent *__fastcall(ProvAgent *__hidden this)`
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000f8d0`
- `0x180010b40`
- `0x180016840`
- `0x180017020`

## callees

- `0x180001678`
- `0x180020710`
- `0x18002a170`
- `0x18002b020`
- `0x180033ed0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a1ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a1ee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a206`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a206`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002a1d0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002a1d0`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18002a1fe`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18002a2d6`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18002a1fe`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18002a2d6`

## string_xrefs

- `0x18002a23d`: `Global\ProvisioningAgentMutex`
- `0x18002a300`: `onecoreuap\admin\prov\lib\provagent.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
  void **v16; // [rsp+60h] [rbp-19h]
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
  if ( *(_DWORD *)g_hProvTraceProvider > 4u )
    tlgWriteTransfer_EventWriteTransfer(g_hProvTraceProvider, &word_180041556, 0, 0);
  _create___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXPEBGKKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    (_DWORD)this + 8,
    (int)L"Global\\ProvisioningTurnMutex",
    v9,
    v10,
    &MutexAttributes);
  if ( *(_DWORD *)g_hProvTraceProvider > 4u )
    tlgWriteTransfer_EventWriteTransfer(g_hProvTraceProvider, &byte_18004152F, 0, 0);
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
0x18002a170  push    rbp
0x18002a172  push    rbx
0x18002a173  push    rsi
0x18002a174  push    rdi
0x18002a175  push    r12
0x18002a177  push    r13
0x18002a179  push    r14
0x18002a17b  push    r15
0x18002a17d  lea     rbp, [rsp-1Fh]
0x18002a182  sub     rsp, 98h
0x18002a189  mov     rax, cs:__security_cookie
0x18002a190  xor     rax, rsp
0x18002a193  mov     [rbp+57h+var_50], rax
0x18002a197  mov     rdi, rcx
0x18002a19a  mov     [rbp+57h+var_78], rcx
0x18002a19e  xor     ebx, ebx
0x18002a1a0  mov     [rcx], rbx
0x18002a1a3  mov     [rcx+8], rbx
0x18002a1a7  mov     [rcx+10h], rbx
0x18002a1ab  mov     [rbp+57h+var_A0], rbx
0x18002a1af  lea     rax, [rbp+57h+var_A0]
0x18002a1b3  mov     [rbp+57h+var_70], rax
0x18002a1b7  mov     [rbp+57h+SecurityDescriptor], rbx
0x18002a1bb  mov     [rbp+57h+var_60], 1
0x18002a1bf  xor     r9d, r9d; SecurityDescriptorSize
0x18002a1c2  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18002a1c6  lea     edx, [rbx+1]; StringSDRevision
0x18002a1c9  lea     rcx, StringSecurityDescriptor; "D:(A;;GA;;;BA)(A;;GA;;;SY)"
0x18002a1d0  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18002a1d6  mov     r12d, eax
0x18002a1d9  cmp     [rbp+57h+var_60], bl
0x18002a1dc  jz      short loc_18002A20F
0x18002a1de  mov     r15, [rbp+57h+SecurityDescriptor]
0x18002a1e2  mov     rsi, [rbp+57h+var_70]
0x18002a1e6  mov     r14, [rsi]
0x18002a1e9  test    r14, r14
0x18002a1ec  jz      short loc_18002A20C
0x18002a1ee  call    cs:__imp_GetLastError
0x18002a1f4  mov     ebx, eax
0x18002a1f6  mov     [rbp+57h+ObjectDescriptor], r14
0x18002a1fa  lea     rcx, [rbp+57h+ObjectDescriptor]; ObjectDescriptor
0x18002a1fe  call    cs:__imp_DestroyPrivateObjectSecurity
0x18002a204  mov     ecx, ebx; dwErrCode
0x18002a206  call    cs:__imp_SetLastError
0x18002a20c  mov     [rsi], r15
0x18002a20f  mov     rcx, [rbp+5Fh]; this
0x18002a213  test    r12d, r12d
0x18002a216  jz      loc_18002A300
0x18002a21c  mov     qword ptr [rbp+57h+MutexAttributes.nLength], 18h
0x18002a224  mov     qword ptr [rbp+57h+MutexAttributes.bInheritHandle], 0
0x18002a22c  mov     rax, [rbp+57h+var_A0]
0x18002a230  mov     [rbp+57h+MutexAttributes.lpSecurityDescriptor], rax
0x18002a234  lea     rax, [rbp+57h+MutexAttributes]
0x18002a238  mov     [rsp+0D0h+lpMutexAttributes], rax; lpMutexAttributes
0x18002a23d  lea     rdx, ?c_provMutexName@@3QBGB; "Global\\ProvisioningAgentMutex"
0x18002a244  mov     rcx, rdi; int
0x18002a247  call    ?create@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18002a24c  mov     rcx, cs:g_hProvTraceProvider
0x18002a253  mov     eax, [rcx]
0x18002a255  mov     esi, 2
0x18002a25a  cmp     eax, 4
0x18002a25d  jbe     short loc_18002A27E
0x18002a25f  lea     rax, [rbp+57h+var_70]
0x18002a263  mov     [rsp+0D0h+var_A8], rax
0x18002a268  mov     dword ptr [rsp+0D0h+lpMutexAttributes], esi
0x18002a26c  xor     r9d, r9d
0x18002a26f  xor     r8d, r8d
0x18002a272  lea     rdx, word_180041556
0x18002a279  call    _tlgWriteTransfer_EventWriteTransfer
0x18002a27e  lea     rax, [rbp+57h+MutexAttributes]
0x18002a282  mov     [rsp+0D0h+lpMutexAttributes], rax; lpMutexAttributes
0x18002a287  lea     rdx, ?c_turnMutexName@@3QBGB; "Global\\ProvisioningTurnMutex"
0x18002a28e  lea     rcx, [rdi+8]; int
0x18002a292  call    ?create@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXPEBGKKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18002a297  mov     rcx, cs:g_hProvTraceProvider
0x18002a29e  mov     eax, [rcx]
0x18002a2a0  cmp     eax, 4
0x18002a2a3  jbe     short loc_18002A2C5
0x18002a2a5  lea     rax, [rbp+57h+var_70]
0x18002a2a9  mov     [rsp+0D0h+var_A8], rax
0x18002a2ae  mov     dword ptr [rsp+0D0h+lpMutexAttributes], esi
0x18002a2b2  xor     r9d, r9d
0x18002a2b5  xor     r8d, r8d
0x18002a2b8  lea     rdx, byte_18004152F
0x18002a2bf  call    _tlgWriteTransfer_EventWriteTransfer
0x18002a2c4  nop
0x18002a2c5  mov     rcx, [rbp+57h+var_A0]
0x18002a2c9  test    rcx, rcx
0x18002a2cc  jz      short loc_18002A2DD
0x18002a2ce  mov     [rbp+57h+ObjectDescriptor], rcx
0x18002a2d2  lea     rcx, [rbp+57h+ObjectDescriptor]; ObjectDescriptor
0x18002a2d6  call    cs:__imp_DestroyPrivateObjectSecurity
0x18002a2dc  nop
0x18002a2dd  mov     rax, rdi
0x18002a2e0  mov     rcx, [rbp+57h+var_50]
0x18002a2e4  xor     rcx, rsp; StackCookie
0x18002a2e7  call    __security_check_cookie
0x18002a2ec  add     rsp, 98h
0x18002a2f3  pop     r15
0x18002a2f5  pop     r14
0x18002a2f7  pop     r13
0x18002a2f9  pop     r12
0x18002a2fb  pop     rdi
0x18002a2fc  pop     rsi
0x18002a2fd  pop     rbx
0x18002a2fe  pop     rbp
0x18002a2ff  retn
0x18002a300  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\prov\\lib\\provagent"...
0x18002a307  mov     edx, 19h; void *
0x18002a30c  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
