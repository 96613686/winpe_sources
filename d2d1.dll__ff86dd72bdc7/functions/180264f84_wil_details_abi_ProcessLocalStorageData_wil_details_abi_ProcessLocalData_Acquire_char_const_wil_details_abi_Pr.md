# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180264f84`
- end: `0x1802650e3`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180265f98`

## callees

- `0x1801b0294`
- `0x180237100`
- `0x1802373b0`
- `0x18023ccc8`
- `0x18025b100`
- `0x180264db8`
- `0x180264dd4`
- `0x180264f84`
- `0x180267b94`
- `0x180268444`
- `0x180268628`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180265001`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180265001`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180264fbc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180264fbc`

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
0x180264f84  mov     [rsp-8+arg_10], rbx
0x180264f89  mov     [rsp-8+arg_18], rdi
0x180264f8e  push    rbp
0x180264f8f  lea     rbp, [rsp-170h]
0x180264f97  sub     rsp, 270h
0x180264f9e  mov     rax, cs:__security_cookie
0x180264fa5  xor     rax, rsp
0x180264fa8  mov     [rbp+170h+var_10], rax
0x180264faf  mov     rdi, rdx
0x180264fb2  mov     qword ptr [rdx], 0
0x180264fb9  mov     rbx, rcx
0x180264fbc  call    cs:__imp_GetCurrentProcessId
0x180264fc2  mov     [rsp+270h+var_248], rbx
0x180264fc7  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180264fce  mov     r9d, eax
0x180264fd1  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180264fd9  mov     edx, 104h; unsigned __int64
0x180264fde  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180264fe3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180264fe8  mov     r9d, 1F0001h; dwDesiredAccess
0x180264fee  mov     [rsp+270h+var_240], 0
0x180264ff7  xor     r8d, r8d; dwFlags
0x180264ffa  lea     rdx, [rsp+270h+Name]; lpName
0x180264fff  xor     ecx, ecx; lpMutexAttributes
0x180265001  call    cs:__imp_CreateMutexExW
0x180265007  mov     rdx, rax
0x18026500a  lea     rcx, [rsp+270h+var_240]
0x18026500f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180265014  cmp     [rsp+270h+var_240], 0
0x18026501a  jnz     short loc_180265025
0x18026501c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180265021  mov     ebx, eax
0x180265023  jmp     short loc_180265091
0x180265025  lea     rdx, [rsp+270h+var_238]
0x18026502a  lea     rcx, [rsp+270h+var_240]
0x18026502f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180265034  lea     rdx, [rsp+270h+var_230]; void **
0x180265039  mov     [rsp+270h+var_230], 0
0x180265042  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180265047  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18026504c  mov     ebx, eax
0x18026504e  test    eax, eax
0x180265050  jns     short loc_180265072
0x180265052  mov     edx, 12Eh; void *
0x180265057  mov     rcx, [rbp+178h]; this
0x18026505e  mov     r9d, eax; char *
0x180265061  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180265066  lea     rcx, [rsp+270h+var_238]
0x18026506b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180265070  jmp     short loc_180265091
0x180265072  mov     rcx, [rsp+270h+var_230]
0x180265077  test    rcx, rcx
0x18026507a  jz      short loc_1802650C1
0x18026507c  mov     [rdi], rcx
0x18026507f  mov     eax, [rcx]
0x180265081  inc     eax
0x180265083  mov     [rcx], eax
0x180265085  lea     rcx, [rsp+270h+var_238]
0x18026508a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18026508f  xor     ebx, ebx
0x180265091  lea     rcx, [rsp+270h+var_240]
0x180265096  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18026509b  mov     eax, ebx
0x18026509d  mov     rcx, [rbp+170h+var_10]
0x1802650a4  xor     rcx, rsp; StackCookie
0x1802650a7  call    __security_check_cookie
0x1802650ac  lea     r11, [rsp+270h+var_s0]
0x1802650b4  mov     rbx, [r11+20h]
0x1802650b8  mov     rdi, [r11+28h]
0x1802650bc  mov     rsp, r11
0x1802650bf  pop     rbp
0x1802650c0  retn
0x1802650c1  mov     r8, rdi
0x1802650c4  lea     rdx, [rsp+270h+var_240]
0x1802650c9  lea     rcx, [rsp+270h+Name]
0x1802650ce  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1802650d3  mov     ebx, eax
0x1802650d5  test    eax, eax
0x1802650d7  jns     short loc_180265085
0x1802650d9  mov     edx, 137h
0x1802650de  jmp     loc_180265057
```
