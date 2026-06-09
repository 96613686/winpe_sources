# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180005788`
- end: `0x1800058ee`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180006794`

## callees

- `0x1800025f0`
- `0x18000533c`
- `0x180005358`
- `0x180005788`
- `0x180006468`
- `0x1800070cc`
- `0x1800084ec`
- `0x180008c7c`
- `0x180009018`
- `0x1800097e4`
- `0x180009e20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005805`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180005805`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800057c0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800057c0`

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
  __int64 v8; // rdx
  _DWORD *v9; // rcx
  __int64 v11; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v12[8]; // [rsp+38h] [rbp-C8h] BYREF
  void *v13; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v11 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v11,
    Mutex);
  if ( v11 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v11,
      v12);
    v13 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v13);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v8 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"wil",
        (const char *)(unsigned int)Pointer,
        120);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v12);
      goto LABEL_9;
    }
    v9 = v13;
    if ( v13 )
    {
      *a2 = v13;
      ++*v9;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v8 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v12);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v11);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180005788  mov     [rsp-8+arg_10], rbx
0x18000578d  mov     [rsp-8+arg_18], rdi
0x180005792  push    rbp
0x180005793  lea     rbp, [rsp-170h]
0x18000579b  sub     rsp, 270h
0x1800057a2  mov     rax, cs:__security_cookie
0x1800057a9  xor     rax, rsp
0x1800057ac  mov     [rbp+170h+var_10], rax
0x1800057b3  mov     rdi, rdx
0x1800057b6  mov     qword ptr [rdx], 0
0x1800057bd  mov     rbx, rcx
0x1800057c0  call    cs:__imp_GetCurrentProcessId
0x1800057c6  mov     [rsp+270h+var_248], rbx
0x1800057cb  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800057d2  mov     r9d, eax
0x1800057d5  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800057dd  mov     edx, 104h; unsigned __int64
0x1800057e2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800057e7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800057ec  mov     r9d, 1F0001h; dwDesiredAccess
0x1800057f2  mov     [rsp+270h+var_240], 0
0x1800057fb  xor     r8d, r8d; dwFlags
0x1800057fe  lea     rdx, [rsp+270h+Name]; lpName
0x180005803  xor     ecx, ecx; lpMutexAttributes
0x180005805  call    cs:__imp_CreateMutexExW
0x18000580b  mov     rdx, rax
0x18000580e  lea     rcx, [rsp+270h+var_240]
0x180005813  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180005818  cmp     [rsp+270h+var_240], 0
0x18000581e  jnz     short loc_180005829
0x180005820  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180005825  mov     ebx, eax
0x180005827  jmp     short loc_18000589C
0x180005829  lea     rdx, [rsp+270h+var_238]
0x18000582e  lea     rcx, [rsp+270h+var_240]
0x180005833  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180005838  lea     rdx, [rsp+270h+var_230]; void **
0x18000583d  mov     [rsp+270h+var_230], 0
0x180005846  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000584b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180005850  mov     ebx, eax
0x180005852  test    eax, eax
0x180005854  jns     short loc_18000587D
0x180005856  mov     edx, 12Eh; void *
0x18000585b  mov     rcx, [rbp+178h]; this
0x180005862  lea     r8, aWil; "wil"
0x180005869  mov     r9d, eax; char *
0x18000586c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005871  lea     rcx, [rsp+270h+var_238]
0x180005876  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000587b  jmp     short loc_18000589C
0x18000587d  mov     rcx, [rsp+270h+var_230]
0x180005882  test    rcx, rcx
0x180005885  jz      short loc_1800058CC
0x180005887  mov     [rdi], rcx
0x18000588a  mov     eax, [rcx]
0x18000588c  inc     eax
0x18000588e  mov     [rcx], eax
0x180005890  lea     rcx, [rsp+270h+var_238]
0x180005895  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000589a  xor     ebx, ebx
0x18000589c  lea     rcx, [rsp+270h+var_240]
0x1800058a1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800058a6  mov     eax, ebx
0x1800058a8  mov     rcx, [rbp+170h+var_10]
0x1800058af  xor     rcx, rsp; StackCookie
0x1800058b2  call    __security_check_cookie
0x1800058b7  lea     r11, [rsp+270h+var_s0]
0x1800058bf  mov     rbx, [r11+20h]
0x1800058c3  mov     rdi, [r11+28h]
0x1800058c7  mov     rsp, r11
0x1800058ca  pop     rbp
0x1800058cb  retn
0x1800058cc  mov     r8, rdi
0x1800058cf  lea     rdx, [rsp+270h+var_240]
0x1800058d4  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800058d9  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800058de  mov     ebx, eax
0x1800058e0  test    eax, eax
0x1800058e2  jns     short loc_180005890
0x1800058e4  mov     edx, 137h
0x1800058e9  jmp     loc_18000585B
```
