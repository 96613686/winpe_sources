# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180003918`
- end: `0x180003a77`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000471c`

## callees

- `0x180003418`
- `0x180003434`
- `0x180003918`
- `0x1800044e8`
- `0x18000526c`
- `0x18000630c`
- `0x180006a8c`
- `0x180006f2c`
- `0x180007804`
- `0x180007f90`
- `0x180035b40`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x180003995`
- `KERNEL32!CreateMutexExW` at `0x180003995`
- `KERNEL32!GetCurrentProcessId` at `0x180003950`
- `KERNEL32!GetCurrentProcessId` at `0x180003950`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  unsigned int v8; // r8d
  __int64 v9; // rdx
  _DWORD *v10; // rcx
  __int64 v12; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v13[8]; // [rsp+38h] [rbp-C8h] BYREF
  void *v14; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v12 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v12,
    Mutex);
  if ( v12 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v12,
      v13);
    v14 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v14);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v9 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v13);
      goto LABEL_9;
    }
    v10 = v14;
    if ( v14 )
    {
      *a2 = v14;
      ++*v10;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v9 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v13);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180003918  mov     [rsp-8+arg_10], rbx
0x18000391d  mov     [rsp-8+arg_18], rdi
0x180003922  push    rbp
0x180003923  lea     rbp, [rsp-170h]
0x18000392b  sub     rsp, 270h
0x180003932  mov     rax, cs:__security_cookie
0x180003939  xor     rax, rsp
0x18000393c  mov     [rbp+170h+var_10], rax
0x180003943  mov     rdi, rdx
0x180003946  mov     qword ptr [rdx], 0
0x18000394d  mov     rbx, rcx
0x180003950  call    cs:__imp_GetCurrentProcessId
0x180003956  mov     [rsp+270h+var_248], rbx
0x18000395b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180003962  mov     r9d, eax
0x180003965  mov     [rsp+270h+var_250], 130h; int
0x18000396d  mov     edx, 104h; unsigned __int64
0x180003972  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180003977  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000397c  mov     r9d, 1F0001h; dwDesiredAccess
0x180003982  mov     [rsp+270h+var_240], 0
0x18000398b  xor     r8d, r8d; dwFlags
0x18000398e  lea     rdx, [rsp+270h+Name]; lpName
0x180003993  xor     ecx, ecx; lpMutexAttributes
0x180003995  call    cs:__imp_CreateMutexExW
0x18000399b  mov     rdx, rax
0x18000399e  lea     rcx, [rsp+270h+var_240]
0x1800039a3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800039a8  cmp     [rsp+270h+var_240], 0
0x1800039ae  jnz     short loc_1800039B9
0x1800039b0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800039b5  mov     ebx, eax
0x1800039b7  jmp     short loc_180003A25
0x1800039b9  lea     rdx, [rsp+270h+var_238]
0x1800039be  lea     rcx, [rsp+270h+var_240]
0x1800039c3  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800039c8  lea     rdx, [rsp+270h+var_230]; void **
0x1800039cd  mov     [rsp+270h+var_230], 0
0x1800039d6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800039db  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800039e0  mov     ebx, eax
0x1800039e2  test    eax, eax
0x1800039e4  jns     short loc_180003A06
0x1800039e6  mov     edx, 12Eh; void *
0x1800039eb  mov     rcx, [rbp+178h]; this
0x1800039f2  mov     r9d, eax; char *
0x1800039f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800039fa  lea     rcx, [rsp+270h+var_238]
0x1800039ff  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180003a04  jmp     short loc_180003A25
0x180003a06  mov     rcx, [rsp+270h+var_230]
0x180003a0b  test    rcx, rcx
0x180003a0e  jz      short loc_180003A55
0x180003a10  mov     [rdi], rcx
0x180003a13  mov     eax, [rcx]
0x180003a15  inc     eax
0x180003a17  mov     [rcx], eax
0x180003a19  lea     rcx, [rsp+270h+var_238]
0x180003a1e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180003a23  xor     ebx, ebx
0x180003a25  lea     rcx, [rsp+270h+var_240]
0x180003a2a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180003a2f  mov     eax, ebx
0x180003a31  mov     rcx, [rbp+170h+var_10]
0x180003a38  xor     rcx, rsp; StackCookie
0x180003a3b  call    __security_check_cookie
0x180003a40  lea     r11, [rsp+270h+var_s0]
0x180003a48  mov     rbx, [r11+20h]
0x180003a4c  mov     rdi, [r11+28h]
0x180003a50  mov     rsp, r11
0x180003a53  pop     rbp
0x180003a54  retn
0x180003a55  mov     r8, rdi
0x180003a58  lea     rdx, [rsp+270h+var_240]
0x180003a5d  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180003a62  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180003a67  mov     ebx, eax
0x180003a69  test    eax, eax
0x180003a6b  jns     short loc_180003A19
0x180003a6d  mov     edx, 137h
0x180003a72  jmp     loc_1800039EB
```
