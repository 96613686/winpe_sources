# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000eea0`
- end: `0x18000efff`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000f8c8`

## callees

- `0x18000a40c`
- `0x18000a6bc`
- `0x18000a708`
- `0x18000ee0c`
- `0x18000ee28`
- `0x18000eea0`
- `0x1800104c4`
- `0x18001057c`
- `0x180010954`
- `0x180010a00`
- `0x18004c670`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000eed8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000eed8`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000ef1d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000ef1d`

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
0x18000eea0  mov     [rsp-8+arg_10], rbx
0x18000eea5  mov     [rsp-8+arg_18], rdi
0x18000eeaa  push    rbp
0x18000eeab  lea     rbp, [rsp-170h]
0x18000eeb3  sub     rsp, 270h
0x18000eeba  mov     rax, cs:__security_cookie
0x18000eec1  xor     rax, rsp
0x18000eec4  mov     [rbp+170h+var_10], rax
0x18000eecb  mov     rdi, rdx
0x18000eece  mov     qword ptr [rdx], 0
0x18000eed5  mov     rbx, rcx
0x18000eed8  call    cs:__imp_GetCurrentProcessId
0x18000eede  mov     [rsp+270h+var_248], rbx
0x18000eee3  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000eeea  mov     r9d, eax
0x18000eeed  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000eef5  mov     edx, 104h; unsigned __int64
0x18000eefa  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000eeff  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000ef04  mov     r9d, 1F0001h; dwDesiredAccess
0x18000ef0a  mov     [rsp+270h+var_240], 0
0x18000ef13  xor     r8d, r8d; dwFlags
0x18000ef16  lea     rdx, [rsp+270h+Name]; lpName
0x18000ef1b  xor     ecx, ecx; lpMutexAttributes
0x18000ef1d  call    cs:__imp_CreateMutexExW
0x18000ef23  mov     rdx, rax
0x18000ef26  lea     rcx, [rsp+270h+var_240]
0x18000ef2b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000ef30  cmp     [rsp+270h+var_240], 0
0x18000ef36  jnz     short loc_18000EF41
0x18000ef38  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000ef3d  mov     ebx, eax
0x18000ef3f  jmp     short loc_18000EFAD
0x18000ef41  lea     rdx, [rsp+270h+var_238]
0x18000ef46  lea     rcx, [rsp+270h+var_240]
0x18000ef4b  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000ef50  lea     rdx, [rsp+270h+var_230]; void **
0x18000ef55  mov     [rsp+270h+var_230], 0
0x18000ef5e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000ef63  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18000ef68  mov     ebx, eax
0x18000ef6a  test    eax, eax
0x18000ef6c  jns     short loc_18000EF8E
0x18000ef6e  mov     edx, 12Eh; void *
0x18000ef73  mov     rcx, [rbp+178h]; this
0x18000ef7a  mov     r9d, eax; char *
0x18000ef7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ef82  lea     rcx, [rsp+270h+var_238]
0x18000ef87  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000ef8c  jmp     short loc_18000EFAD
0x18000ef8e  mov     rcx, [rsp+270h+var_230]
0x18000ef93  test    rcx, rcx
0x18000ef96  jz      short loc_18000EFDD
0x18000ef98  mov     [rdi], rcx
0x18000ef9b  mov     eax, [rcx]
0x18000ef9d  inc     eax
0x18000ef9f  mov     [rcx], eax
0x18000efa1  lea     rcx, [rsp+270h+var_238]
0x18000efa6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000efab  xor     ebx, ebx
0x18000efad  lea     rcx, [rsp+270h+var_240]
0x18000efb2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000efb7  mov     eax, ebx
0x18000efb9  mov     rcx, [rbp+170h+var_10]
0x18000efc0  xor     rcx, rsp; StackCookie
0x18000efc3  call    __security_check_cookie
0x18000efc8  lea     r11, [rsp+270h+var_s0]
0x18000efd0  mov     rbx, [r11+20h]
0x18000efd4  mov     rdi, [r11+28h]
0x18000efd8  mov     rsp, r11
0x18000efdb  pop     rbp
0x18000efdc  retn
0x18000efdd  mov     r8, rdi
0x18000efe0  lea     rdx, [rsp+270h+var_240]
0x18000efe5  lea     rcx, [rsp+270h+Name]
0x18000efea  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000efef  mov     ebx, eax
0x18000eff1  test    eax, eax
0x18000eff3  jns     short loc_18000EFA1
0x18000eff5  mov     edx, 137h
0x18000effa  jmp     loc_18000EF73
```
