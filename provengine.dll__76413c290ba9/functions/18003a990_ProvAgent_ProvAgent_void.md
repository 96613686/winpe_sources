# ProvAgent::ProvAgent(void)

- ea: `0x18003a990`
- end: `0x18003ac2d`
- name: `??0ProvAgent@@QEAA@XZ`
- size: `669`
- prototype: `ProvAgent *__fastcall(ProvAgent *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001eeec`

## callees

- `0x1800010c8`
- `0x18000ad18`
- `0x180021cd8`
- `0x18003a990`
- `0x180043750`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18003aa84`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18003ab17`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18003aa84`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18003ab17`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003aa3f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003aac5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ab59`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003aa3f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003aac5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ab59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003aa27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003aa96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003aaa4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ab29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ab38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003aa27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003aa96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003aaa4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ab29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ab38`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003aab0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003ab44`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003aab0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003ab44`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18003aa37`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18003aba7`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18003aa37`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18003aba7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18003aa08`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18003aa08`

## string_xrefs

- `0x18003aa79`: `Global\ProvisioningAgentMutex`
- `0x18003ac05`: `onecoreuap\admin\prov\lib\provagent.cpp`
- `0x18003abdd`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18003abf3`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
ProvAgent *__fastcall ProvAgent::ProvAgent(ProvAgent *this)
{
  const char *v2; // r9
  BOOL v3; // r12d
  PSECURITY_DESCRIPTOR v4; // r15
  void **v5; // rsi
  void *v6; // r14
  DWORD LastError; // ebx
  HANDLE v8; // rsi
  const char *v9; // r9
  void *v10; // rbx
  DWORD v11; // r14d
  unsigned int v12; // r8d
  const char *v13; // r9
  HANDLE v14; // rsi
  const char *v15; // r9
  void *v16; // rbx
  DWORD v17; // r14d
  unsigned int v18; // r8d
  const char *v19; // r9
  void *v21; // [rsp+30h] [rbp-29h] BYREF
  PSECURITY_DESCRIPTOR ObjectDescriptor; // [rsp+38h] [rbp-21h] BYREF
  struct _SECURITY_ATTRIBUTES MutexAttributes; // [rsp+40h] [rbp-19h] BYREF
  ProvAgent *v24; // [rsp+58h] [rbp-1h]
  void **v25; // [rsp+60h] [rbp+7h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+68h] [rbp+Fh] BYREF
  char v27; // [rsp+70h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v24 = this;
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  v21 = 0;
  v25 = &v21;
  SecurityDescriptor = 0;
  v27 = 1;
  v3 = ConvertStringSecurityDescriptorToSecurityDescriptorW(L"D:(A;;GA;;;BA)(A;;GA;;;SY)", 1u, &SecurityDescriptor, 0);
  if ( v27 )
  {
    v4 = SecurityDescriptor;
    v5 = v25;
    v6 = *v25;
    if ( *v25 )
    {
      LastError = GetLastError();
      ObjectDescriptor = v6;
      DestroyPrivateObjectSecurity(&ObjectDescriptor);
      SetLastError(LastError);
    }
    *v5 = v4;
  }
  if ( !v3 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x19,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provagent.cpp",
      v2);
  *(_QWORD *)&MutexAttributes.nLength = 24;
  *(_QWORD *)&MutexAttributes.bInheritHandle = 0;
  MutexAttributes.lpSecurityDescriptor = v21;
  v8 = CreateMutexExW(&MutexAttributes, L"Global\\ProvisioningAgentMutex", 0, 0x1F0001u);
  if ( !v8 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1CC8,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      v9);
  GetLastError();
  v10 = *(void **)this;
  if ( *(_QWORD *)this )
  {
    v11 = GetLastError();
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v12, v13);
    SetLastError(v11);
  }
  *(_QWORD *)this = v8;
  if ( (unsigned int)dword_18005A000 > 4 )
    tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, byte_1800503BD, 0, 0, 2, &v25);
  v14 = CreateMutexExW(&MutexAttributes, L"Global\\ProvisioningTurnMutex", 0, 0x1F0001u);
  if ( !v14 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1CC8,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      v15);
  GetLastError();
  v16 = (void *)*((_QWORD *)this + 1);
  if ( v16 )
  {
    v17 = GetLastError();
    if ( !CloseHandle(v16) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v18, v19);
    SetLastError(v17);
  }
  *((_QWORD *)this + 1) = v14;
  if ( (unsigned int)dword_18005A000 > 4 )
    tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, &dword_1800503E4, 0, 0, 2, &v25);
  if ( v21 )
  {
    ObjectDescriptor = v21;
    DestroyPrivateObjectSecurity(&ObjectDescriptor);
  }
  return this;
}

```

## disassembly

```asm
0x18003a990  mov     [rsp-8+arg_8], rbx
0x18003a995  mov     [rsp-8+arg_10], rsi
0x18003a99a  push    rbp
0x18003a99b  push    rdi
0x18003a99c  push    r12
0x18003a99e  push    r14
0x18003a9a0  push    r15
0x18003a9a2  lea     rbp, [rsp-37h]
0x18003a9a7  sub     rsp, 90h
0x18003a9ae  mov     rax, cs:__security_cookie
0x18003a9b5  xor     rax, rsp
0x18003a9b8  mov     [rbp+57h+var_30], rax
0x18003a9bc  mov     rdi, rcx
0x18003a9bf  mov     [rbp+57h+var_58], rcx
0x18003a9c3  mov     qword ptr [rcx], 0
0x18003a9ca  mov     qword ptr [rcx+8], 0
0x18003a9d2  mov     qword ptr [rcx+10h], 0
0x18003a9da  mov     [rbp+57h+var_80], 0
0x18003a9e2  lea     rax, [rbp+57h+var_80]
0x18003a9e6  mov     [rbp+57h+var_50], rax
0x18003a9ea  mov     [rbp+57h+SecurityDescriptor], 0
0x18003a9f2  mov     [rbp+57h+var_40], 1
0x18003a9f6  xor     r9d, r9d; SecurityDescriptorSize
0x18003a9f9  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18003a9fd  lea     edx, [r9+1]; StringSDRevision
0x18003aa01  lea     rcx, StringSecurityDescriptor; "D:(A;;GA;;;BA)(A;;GA;;;SY)"
0x18003aa08  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18003aa0e  mov     r12d, eax
0x18003aa11  cmp     [rbp+57h+var_40], 0
0x18003aa15  jz      short loc_18003AA48
0x18003aa17  mov     r15, [rbp+57h+SecurityDescriptor]
0x18003aa1b  mov     rsi, [rbp+57h+var_50]
0x18003aa1f  mov     r14, [rsi]
0x18003aa22  test    r14, r14
0x18003aa25  jz      short loc_18003AA45
0x18003aa27  call    cs:__imp_GetLastError
0x18003aa2d  mov     ebx, eax
0x18003aa2f  mov     [rbp+57h+ObjectDescriptor], r14
0x18003aa33  lea     rcx, [rbp+57h+ObjectDescriptor]; ObjectDescriptor
0x18003aa37  call    cs:__imp_DestroyPrivateObjectSecurity
0x18003aa3d  mov     ecx, ebx; dwErrCode
0x18003aa3f  call    cs:__imp_SetLastError
0x18003aa45  mov     [rsi], r15
0x18003aa48  mov     rcx, [rbp+5Fh]; this
0x18003aa4c  test    r12d, r12d
0x18003aa4f  jz      loc_18003AC05
0x18003aa55  mov     qword ptr [rbp+57h+MutexAttributes.nLength], 18h
0x18003aa5d  mov     qword ptr [rbp+57h+MutexAttributes.bInheritHandle], 0
0x18003aa65  mov     rax, [rbp+57h+var_80]
0x18003aa69  mov     [rbp+57h+MutexAttributes.lpSecurityDescriptor], rax
0x18003aa6d  mov     r12d, 1F0001h
0x18003aa73  mov     r9d, r12d; dwDesiredAccess
0x18003aa76  xor     r8d, r8d; dwFlags
0x18003aa79  lea     rdx, ?c_provMutexName@@3QBGB; "Global\\ProvisioningAgentMutex"
0x18003aa80  lea     rcx, [rbp+57h+MutexAttributes]; lpMutexAttributes
0x18003aa84  call    cs:__imp_CreateMutexExW
0x18003aa8a  mov     rsi, rax
0x18003aa8d  test    rax, rax
0x18003aa90  jz      loc_18003ABEF
0x18003aa96  call    cs:__imp_GetLastError
0x18003aa9c  mov     rbx, [rdi]
0x18003aa9f  test    rbx, rbx
0x18003aaa2  jz      short loc_18003AACB
0x18003aaa4  call    cs:__imp_GetLastError
0x18003aaaa  mov     r14d, eax
0x18003aaad  mov     rcx, rbx; hObject
0x18003aab0  call    cs:__imp_CloseHandle
0x18003aab6  mov     rcx, [rbp+5Fh]; this
0x18003aaba  test    eax, eax
0x18003aabc  jz      loc_18003AC17
0x18003aac2  mov     ecx, r14d; dwErrCode
0x18003aac5  call    cs:__imp_SetLastError
0x18003aacb  mov     [rdi], rsi
0x18003aace  mov     eax, cs:dword_18005A000
0x18003aad4  mov     r15d, 2
0x18003aada  cmp     eax, 4
0x18003aadd  jbe     short loc_18003AB06
0x18003aadf  lea     rax, [rbp+57h+var_50]
0x18003aae3  mov     [rsp+0B0h+var_88], rax
0x18003aae8  mov     [rsp+0B0h+var_90], r15d
0x18003aaed  xor     r9d, r9d
0x18003aaf0  xor     r8d, r8d
0x18003aaf3  lea     rdx, byte_1800503BD
0x18003aafa  lea     rcx, dword_18005A000
0x18003ab01  call    _tlgWriteTransfer_EventWriteTransfer
0x18003ab06  mov     r9d, r12d; dwDesiredAccess
0x18003ab09  xor     r8d, r8d; dwFlags
0x18003ab0c  lea     rdx, ?c_turnMutexName@@3QBGB; "Global\\ProvisioningTurnMutex"
0x18003ab13  lea     rcx, [rbp+57h+MutexAttributes]; lpMutexAttributes
0x18003ab17  call    cs:__imp_CreateMutexExW
0x18003ab1d  mov     rsi, rax
0x18003ab20  test    rax, rax
0x18003ab23  jz      loc_18003ABD9
0x18003ab29  call    cs:__imp_GetLastError
0x18003ab2f  mov     rbx, [rdi+8]
0x18003ab33  test    rbx, rbx
0x18003ab36  jz      short loc_18003AB5F
0x18003ab38  call    cs:__imp_GetLastError
0x18003ab3e  mov     r14d, eax
0x18003ab41  mov     rcx, rbx; hObject
0x18003ab44  call    cs:__imp_CloseHandle
0x18003ab4a  mov     rcx, [rbp+5Fh]; this
0x18003ab4e  test    eax, eax
0x18003ab50  jz      loc_18003AC22
0x18003ab56  mov     ecx, r14d; dwErrCode
0x18003ab59  call    cs:__imp_SetLastError
0x18003ab5f  mov     [rdi+8], rsi
0x18003ab63  mov     eax, cs:dword_18005A000
0x18003ab69  cmp     eax, 4
0x18003ab6c  jbe     short loc_18003AB96
0x18003ab6e  lea     rax, [rbp+57h+var_50]
0x18003ab72  mov     [rsp+0B0h+var_88], rax
0x18003ab77  mov     [rsp+0B0h+var_90], r15d
0x18003ab7c  xor     r9d, r9d
0x18003ab7f  xor     r8d, r8d
0x18003ab82  lea     rdx, dword_1800503E4
0x18003ab89  lea     rcx, dword_18005A000
0x18003ab90  call    _tlgWriteTransfer_EventWriteTransfer
0x18003ab95  nop
0x18003ab96  mov     rcx, [rbp+57h+var_80]
0x18003ab9a  test    rcx, rcx
0x18003ab9d  jz      short loc_18003ABAE
0x18003ab9f  mov     [rbp+57h+ObjectDescriptor], rcx
0x18003aba3  lea     rcx, [rbp+57h+ObjectDescriptor]; ObjectDescriptor
0x18003aba7  call    cs:__imp_DestroyPrivateObjectSecurity
0x18003abad  nop
0x18003abae  mov     rax, rdi
0x18003abb1  mov     rcx, [rbp+57h+var_30]
0x18003abb5  xor     rcx, rsp; StackCookie
0x18003abb8  call    __security_check_cookie
0x18003abbd  lea     r11, [rsp+0B0h+var_20]
0x18003abc5  mov     rbx, [r11+38h]
0x18003abc9  mov     rsi, [r11+40h]
0x18003abcd  mov     rsp, r11
0x18003abd0  pop     r15
0x18003abd2  pop     r14
0x18003abd4  pop     r12
0x18003abd6  pop     rdi
0x18003abd7  pop     rbp
0x18003abd8  retn
0x18003abd9  mov     rcx, [rbp+5Fh]; this
0x18003abdd  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003abe4  mov     edx, 1CC8h; void *
0x18003abe9  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18003abef  mov     rcx, [rbp+5Fh]; this
0x18003abf3  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003abfa  mov     edx, 1CC8h; void *
0x18003abff  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18003ac05  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\prov\\lib\\provagent"...
0x18003ac0c  mov     edx, 19h; void *
0x18003ac11  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18003ac17  mov     edx, 0A0Bh; void *
0x18003ac1c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18003ac22  mov     edx, 0A0Bh; void *
0x18003ac27  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
