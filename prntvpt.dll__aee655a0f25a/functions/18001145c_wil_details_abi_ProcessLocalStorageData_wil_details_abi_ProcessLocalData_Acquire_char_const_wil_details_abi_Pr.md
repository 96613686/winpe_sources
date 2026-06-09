# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18001145c`
- end: `0x1800115bb`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800135f0`

## callees

- `0x180007660`
- `0x18000ee58`
- `0x18000f970`
- `0x18001119c`
- `0x1800111b8`
- `0x18001145c`
- `0x180013f58`
- `0x180015fd0`
- `0x180016968`
- `0x1800174f0`
- `0x18001764c`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180011494`
- `KERNEL32!GetCurrentProcessId` at `0x180011494`
- `KERNEL32!CreateMutexExW` at `0x1800114d9`
- `KERNEL32!CreateMutexExW` at `0x1800114d9`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 120);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
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
0x18001145c  mov     [rsp-8+arg_10], rbx
0x180011461  mov     [rsp-8+arg_18], rdi
0x180011466  push    rbp
0x180011467  lea     rbp, [rsp-170h]
0x18001146f  sub     rsp, 270h
0x180011476  mov     rax, cs:__security_cookie
0x18001147d  xor     rax, rsp
0x180011480  mov     [rbp+170h+var_10], rax
0x180011487  mov     rdi, rdx
0x18001148a  mov     qword ptr [rdx], 0
0x180011491  mov     rbx, rcx
0x180011494  call    cs:__imp_GetCurrentProcessId
0x18001149a  mov     [rsp+270h+var_248], rbx
0x18001149f  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800114a6  mov     r9d, eax
0x1800114a9  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800114b1  mov     edx, 104h; unsigned __int64
0x1800114b6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800114bb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800114c0  mov     r9d, 1F0001h; dwDesiredAccess
0x1800114c6  mov     [rsp+270h+var_240], 0
0x1800114cf  xor     r8d, r8d; dwFlags
0x1800114d2  lea     rdx, [rsp+270h+Name]; lpName
0x1800114d7  xor     ecx, ecx; lpMutexAttributes
0x1800114d9  call    cs:__imp_CreateMutexExW
0x1800114df  mov     rdx, rax
0x1800114e2  lea     rcx, [rsp+270h+var_240]
0x1800114e7  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800114ec  cmp     [rsp+270h+var_240], 0
0x1800114f2  jnz     short loc_1800114FD
0x1800114f4  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800114f9  mov     ebx, eax
0x1800114fb  jmp     short loc_180011569
0x1800114fd  lea     rdx, [rsp+270h+var_238]
0x180011502  lea     rcx, [rsp+270h+var_240]
0x180011507  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18001150c  lea     rdx, [rsp+270h+var_230]; void **
0x180011511  mov     [rsp+270h+var_230], 0
0x18001151a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001151f  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180011524  mov     ebx, eax
0x180011526  test    eax, eax
0x180011528  jns     short loc_18001154A
0x18001152a  mov     edx, 12Eh; void *
0x18001152f  mov     rcx, [rbp+178h]; this
0x180011536  mov     r9d, eax; char *
0x180011539  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001153e  lea     rcx, [rsp+270h+var_238]
0x180011543  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180011548  jmp     short loc_180011569
0x18001154a  mov     rcx, [rsp+270h+var_230]
0x18001154f  test    rcx, rcx
0x180011552  jz      short loc_180011599
0x180011554  mov     [rdi], rcx
0x180011557  mov     eax, [rcx]
0x180011559  inc     eax
0x18001155b  mov     [rcx], eax
0x18001155d  lea     rcx, [rsp+270h+var_238]
0x180011562  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180011567  xor     ebx, ebx
0x180011569  lea     rcx, [rsp+270h+var_240]
0x18001156e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180011573  mov     eax, ebx
0x180011575  mov     rcx, [rbp+170h+var_10]
0x18001157c  xor     rcx, rsp; StackCookie
0x18001157f  call    __security_check_cookie
0x180011584  lea     r11, [rsp+270h+var_s0]
0x18001158c  mov     rbx, [r11+20h]
0x180011590  mov     rdi, [r11+28h]
0x180011594  mov     rsp, r11
0x180011597  pop     rbp
0x180011598  retn
0x180011599  mov     r8, rdi
0x18001159c  lea     rdx, [rsp+270h+var_240]
0x1800115a1  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800115a6  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800115ab  mov     ebx, eax
0x1800115ad  test    eax, eax
0x1800115af  jns     short loc_18001155D
0x1800115b1  mov     edx, 137h
0x1800115b6  jmp     loc_18001152F
```
