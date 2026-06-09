# ??$create_global_mutex@$$V@details@fc@@YAJAEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@PEBG@Z

- ea: `0x180012bd8`
- end: `0x180012d18`
- name: `??$create_global_mutex@$$V@details@fc@@YAJAEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@PEBG@Z`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800135f8`

## callees

- `0x180003220`
- `0x180007218`
- `0x18000947c`
- `0x18000949c`
- `0x18000adb8`
- `0x180012bd8`
- `0x180012d20`
- `0x1800166f4`
- `0x18001e8c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180012ca5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180012ca5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012cb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012cb3`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180012c55`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180012c55`

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
  _SECURITY_ATTRIBUTES MutexAttributes; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR Name[128]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  global_mutex = fc::details::create_global_mutex_name<>(Name);
  LastError = global_mutex;
  if ( global_mutex >= 0 )
  {
    SecurityDescriptor = 0;
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      &SecurityDescriptor,
      0);
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
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&SecurityDescriptor);
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
0x180012bd8  mov     [rsp-8+arg_8], rbx
0x180012bdd  mov     [rsp-8+arg_10], rdi
0x180012be2  push    rbp
0x180012be3  lea     rbp, [rsp-50h]
0x180012be8  sub     rsp, 150h
0x180012bef  mov     rax, cs:__security_cookie
0x180012bf6  xor     rax, rsp
0x180012bf9  mov     [rbp+50h+var_10], rax
0x180012bfd  mov     rdi, rcx
0x180012c00  lea     rcx, [rsp+150h+Name]; unsigned __int16 *
0x180012c05  call    ??$create_global_mutex_name@$$V@details@fc@@YAJPEAG_KPEBG@Z; fc::details::create_global_mutex_name<>(ushort *,unsigned __int64,ushort const *)
0x180012c0a  mov     ebx, eax
0x180012c0c  test    eax, eax
0x180012c0e  jns     short loc_180012C2D
0x180012c10  mov     rcx, [rbp+58h]; this
0x180012c14  lea     r8, aOnecoreInterna_9; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x180012c1b  mov     r9d, eax; char *
0x180012c1e  mov     edx, 1Dh; void *
0x180012c23  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012c28  jmp     loc_180012CD0
0x180012c2d  xor     edx, edx
0x180012c2f  mov     [rsp+150h+SecurityDescriptor], 0; int
0x180012c38  lea     rcx, [rsp+150h+SecurityDescriptor]
0x180012c3d  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180012c42  xor     r9d, r9d; SecurityDescriptorSize
0x180012c45  lea     r8, [rsp+150h+SecurityDescriptor]; SecurityDescriptor
0x180012c4a  lea     rcx, StringSecurityDescriptor; "D:(A;;0x00100000;;;WD)"
0x180012c51  lea     edx, [r9+1]; StringSDRevision
0x180012c55  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180012c5b  test    eax, eax
0x180012c5d  jnz     short loc_180012C76
0x180012c5f  mov     rcx, [rbp+58h]; this
0x180012c63  lea     r8, aOnecoreInterna_9; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x180012c6a  lea     edx, [rax+29h]; void *
0x180012c6d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180012c72  mov     ebx, eax
0x180012c74  jmp     short loc_180012CC6
0x180012c76  mov     rax, [rsp+150h+SecurityDescriptor]
0x180012c7b  lea     rdx, [rsp+150h+Name]; lpName
0x180012c80  mov     r9d, 100000h; dwDesiredAccess
0x180012c86  mov     [rsp+150h+MutexAttributes.lpSecurityDescriptor], rax
0x180012c8b  xor     r8d, r8d; dwFlags
0x180012c8e  mov     qword ptr [rsp+150h+MutexAttributes.nLength], 18h
0x180012c97  lea     rcx, [rsp+150h+MutexAttributes]; lpMutexAttributes
0x180012c9c  mov     qword ptr [rsp+150h+MutexAttributes.bInheritHandle], 0
0x180012ca5  call    cs:__imp_CreateMutexExW
0x180012cab  mov     rbx, rax
0x180012cae  test    rax, rax
0x180012cb1  jz      short loc_180012CF3
0x180012cb3  call    cs:__imp_GetLastError
0x180012cb9  mov     rdx, rbx
0x180012cbc  mov     rcx, rdi
0x180012cbf  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180012cc4  xor     ebx, ebx
0x180012cc6  lea     rcx, [rsp+150h+SecurityDescriptor]
0x180012ccb  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180012cd0  mov     eax, ebx
0x180012cd2  mov     rcx, [rbp+50h+var_10]
0x180012cd6  xor     rcx, rsp; StackCookie
0x180012cd9  call    __security_check_cookie
0x180012cde  lea     r11, [rsp+150h+var_s0]
0x180012ce6  mov     rbx, [r11+18h]
0x180012cea  mov     rdi, [r11+20h]
0x180012cee  mov     rsp, r11
0x180012cf1  pop     rbp
0x180012cf2  retn
0x180012cf3  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180012cf8  mov     ebx, eax
0x180012cfa  test    eax, eax
0x180012cfc  jns     short loc_180012CC4
0x180012cfe  mov     rcx, [rbp+58h]; this
0x180012d02  lea     r8, aOnecoreInterna_9; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x180012d09  mov     r9d, eax; char *
0x180012d0c  mov     edx, 30h ; '0'; void *
0x180012d11  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012d16  jmp     short loc_180012CC6
```
