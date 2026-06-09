# ??$create_global_mutex@$$V@details@fc@@YAJAEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@PEBG@Z

- ea: `0x18005c0ec`
- end: `0x18005c220`
- name: `??$create_global_mutex@$$V@details@fc@@YAJAEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@PEBG@Z`
- size: `308`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18005cfb8`

## callees

- `0x1800104b0`
- `0x180017988`
- `0x1800179ac`
- `0x180023214`
- `0x18002a3d0`
- `0x18005c0ec`
- `0x18005c228`
- `0x18005ed50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18005c1ad`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18005c1ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c1bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c1bb`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18005c15d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18005c15d`

## pseudocode

```c
__int64 __fastcall fc::details::create_global_mutex<>(__int64 a1)
{
  int global_mutex; // eax
  unsigned int LastError; // ebx
  const char *v4; // r9
  wil::details *v5; // rcx
  HANDLE v6; // rbx
  int LastErrorFailHr; // eax
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+20h] [rbp-E0h] BYREF
  struct _SECURITY_ATTRIBUTES MutexAttributes; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR Name[128]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  global_mutex = fc::details::create_global_mutex_name<>(Name);
  LastError = global_mutex;
  if ( global_mutex >= 0 )
  {
    SecurityDescriptor = 0;
    if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(L"D:(A;;0x00100000;;;WD)", 1u, &SecurityDescriptor, 0) )
    {
      MutexAttributes.lpSecurityDescriptor = SecurityDescriptor;
      *(_QWORD *)&MutexAttributes.nLength = 24;
      *(_QWORD *)&MutexAttributes.bInheritHandle = 0;
      v6 = CreateMutexExW(&MutexAttributes, Name, 0, 0x100000u);
      if ( v6 )
      {
        GetLastError();
        _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
          a1,
          v6);
      }
      else
      {
        LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
        LastError = LastErrorFailHr;
        if ( LastErrorFailHr < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x30,
            (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\fc\\fc_win32_utilities.h",
            (const char *)(unsigned int)LastErrorFailHr,
            (int)SecurityDescriptor);
          goto LABEL_8;
        }
      }
      LastError = 0;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x29,
                    (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\fc\\fc_win32_utilities.h",
                    v4);
    }
LABEL_8:
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&SecurityDescriptor);
    return LastError;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1D,
    (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\fc\\fc_win32_utilities.h",
    (const char *)(unsigned int)global_mutex,
    (int)SecurityDescriptor);
  return LastError;
}

```

## disassembly

```asm
0x18005c0ec  mov     [rsp-8+arg_8], rbx
0x18005c0f1  mov     [rsp-8+arg_10], rdi
0x18005c0f6  push    rbp
0x18005c0f7  lea     rbp, [rsp-50h]
0x18005c0fc  sub     rsp, 150h
0x18005c103  mov     rax, cs:__security_cookie
0x18005c10a  xor     rax, rsp
0x18005c10d  mov     [rbp+50h+var_10], rax
0x18005c111  mov     rdi, rcx
0x18005c114  lea     rcx, [rsp+150h+Name]; unsigned __int16 *
0x18005c119  call    ??$create_global_mutex_name@$$V@details@fc@@YAJPEAG_KPEBG@Z; fc::details::create_global_mutex_name<>(ushort *,unsigned __int64,ushort const *)
0x18005c11e  mov     ebx, eax
0x18005c120  test    eax, eax
0x18005c122  jns     short loc_18005C141
0x18005c124  mov     rcx, [rbp+58h]; this
0x18005c128  lea     r8, aOnecoreInterna_14; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x18005c12f  mov     r9d, eax; char *
0x18005c132  mov     edx, 1Dh; void *
0x18005c137  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c13c  jmp     loc_18005C1D8
0x18005c141  xor     r9d, r9d; SecurityDescriptorSize
0x18005c144  mov     [rsp+150h+SecurityDescriptor], 0; int
0x18005c14d  lea     r8, [rsp+150h+SecurityDescriptor]; SecurityDescriptor
0x18005c152  lea     rcx, StringSecurityDescriptor; "D:(A;;0x00100000;;;WD)"
0x18005c159  lea     edx, [r9+1]; StringSDRevision
0x18005c15d  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18005c163  test    eax, eax
0x18005c165  jnz     short loc_18005C17E
0x18005c167  mov     rcx, [rbp+58h]; this
0x18005c16b  lea     r8, aOnecoreInterna_14; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x18005c172  lea     edx, [rax+29h]; void *
0x18005c175  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005c17a  mov     ebx, eax
0x18005c17c  jmp     short loc_18005C1CE
0x18005c17e  mov     rax, [rsp+150h+SecurityDescriptor]
0x18005c183  lea     rdx, [rsp+150h+Name]; lpName
0x18005c188  mov     r9d, 100000h; dwDesiredAccess
0x18005c18e  mov     [rsp+150h+MutexAttributes.lpSecurityDescriptor], rax
0x18005c193  xor     r8d, r8d; dwFlags
0x18005c196  mov     qword ptr [rsp+150h+MutexAttributes.nLength], 18h
0x18005c19f  lea     rcx, [rsp+150h+MutexAttributes]; lpMutexAttributes
0x18005c1a4  mov     qword ptr [rsp+150h+MutexAttributes.bInheritHandle], 0
0x18005c1ad  call    cs:__imp_CreateMutexExW
0x18005c1b3  mov     rbx, rax
0x18005c1b6  test    rax, rax
0x18005c1b9  jz      short loc_18005C1FB
0x18005c1bb  call    cs:__imp_GetLastError
0x18005c1c1  mov     rdx, rbx
0x18005c1c4  mov     rcx, rdi
0x18005c1c7  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18005c1cc  xor     ebx, ebx
0x18005c1ce  lea     rcx, [rsp+150h+SecurityDescriptor]
0x18005c1d3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18005c1d8  mov     eax, ebx
0x18005c1da  mov     rcx, [rbp+50h+var_10]
0x18005c1de  xor     rcx, rsp; StackCookie
0x18005c1e1  call    __security_check_cookie
0x18005c1e6  lea     r11, [rsp+150h+var_s0]
0x18005c1ee  mov     rbx, [r11+18h]
0x18005c1f2  mov     rdi, [r11+20h]
0x18005c1f6  mov     rsp, r11
0x18005c1f9  pop     rbp
0x18005c1fa  retn
0x18005c1fb  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18005c200  mov     ebx, eax
0x18005c202  test    eax, eax
0x18005c204  jns     short loc_18005C1CC
0x18005c206  mov     rcx, [rbp+58h]; this
0x18005c20a  lea     r8, aOnecoreInterna_14; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x18005c211  mov     r9d, eax; char *
0x18005c214  mov     edx, 30h ; '0'; void *
0x18005c219  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c21e  jmp     short loc_18005C1CE
```
