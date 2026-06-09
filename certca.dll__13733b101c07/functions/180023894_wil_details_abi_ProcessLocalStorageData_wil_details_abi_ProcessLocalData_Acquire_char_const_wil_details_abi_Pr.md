# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180023894`
- end: `0x180023a0f`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `379`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180024340`

## callees

- `0x18000a320`
- `0x180023418`
- `0x180023434`
- `0x180023894`
- `0x180024254`
- `0x180024bb4`
- `0x180025cd8`
- `0x180026328`
- `0x1800269c4`
- `0x180026c84`
- `0x1800382c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180023911`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180023911`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800238cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800238cc`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rdx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  unsigned int v9; // r8d
  _DWORD *v10; // rcx
  int v12; // eax
  unsigned int v13; // r8d
  wil::details *v14; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v15[8]; // [rsp+38h] [rbp-C8h] BYREF
  void *v16; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v14 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v14,
    Mutex);
  if ( v14 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v14,
      v15);
    v16 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v16);
    LastErrorFailHr = Pointer;
    if ( Pointer >= 0 )
    {
      v10 = v16;
      if ( v16 )
      {
        *a2 = v16;
        ++*v10;
      }
      else
      {
        v12 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
        LastErrorFailHr = v12;
        if ( v12 < 0 )
        {
          wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v13, (const char *)(unsigned int)v12, 120);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v15);
          goto LABEL_8;
        }
      }
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v15);
      LastErrorFailHr = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v9, (const char *)(unsigned int)Pointer, 120);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v15);
    }
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
  }
LABEL_8:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v14,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180023894  mov     [rsp-8+arg_10], rbx
0x180023899  mov     [rsp-8+arg_18], rdi
0x18002389e  push    rbp
0x18002389f  lea     rbp, [rsp-170h]
0x1800238a7  sub     rsp, 270h
0x1800238ae  mov     rax, cs:__security_cookie
0x1800238b5  xor     rax, rsp
0x1800238b8  mov     [rbp+170h+var_10], rax
0x1800238bf  mov     rdi, rdx
0x1800238c2  mov     rbx, rcx
0x1800238c5  mov     qword ptr [rdx], 0
0x1800238cc  call    cs:__imp_GetCurrentProcessId
0x1800238d2  mov     r9d, eax
0x1800238d5  mov     [rsp+270h+var_248], rbx
0x1800238da  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800238e2  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800238e9  mov     edx, 104h; unsigned __int64
0x1800238ee  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800238f3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800238f8  mov     [rsp+270h+var_240], 0
0x180023901  mov     r9d, 1F0001h; dwDesiredAccess
0x180023907  xor     r8d, r8d; dwFlags
0x18002390a  lea     rdx, [rsp+270h+Name]; lpName
0x18002390f  xor     ecx, ecx; lpMutexAttributes
0x180023911  call    cs:__imp_CreateMutexExW
0x180023917  mov     rdx, rax
0x18002391a  lea     rcx, [rsp+270h+var_240]
0x18002391f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180023924  cmp     [rsp+270h+var_240], 0
0x18002392a  jnz     short loc_180023935
0x18002392c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180023931  mov     ebx, eax
0x180023933  jmp     short loc_1800239A5
0x180023935  lea     rdx, [rsp+270h+var_238]
0x18002393a  lea     rcx, [rsp+270h+var_240]
0x18002393f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180023944  nop
0x180023945  mov     [rsp+270h+var_230], 0
0x18002394e  lea     rdx, [rsp+270h+var_230]; void **
0x180023953  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180023958  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18002395d  mov     ebx, eax
0x18002395f  test    eax, eax
0x180023961  jns     short loc_180023985
0x180023963  mov     rcx, [rbp+178h]; this
0x18002396a  mov     r9d, eax; char *
0x18002396d  mov     edx, 12Eh; void *
0x180023972  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023977  nop
0x180023978  lea     rcx, [rsp+270h+var_238]
0x18002397d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180023982  nop
0x180023983  jmp     short loc_1800239A5
0x180023985  mov     rcx, [rsp+270h+var_230]
0x18002398a  test    rcx, rcx
0x18002398d  jz      short loc_1800239D5
0x18002398f  mov     [rdi], rcx
0x180023992  mov     eax, [rcx]
0x180023994  inc     eax
0x180023996  mov     [rcx], eax
0x180023998  lea     rcx, [rsp+270h+var_238]
0x18002399d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800239a2  nop
0x1800239a3  xor     ebx, ebx
0x1800239a5  lea     rcx, [rsp+270h+var_240]
0x1800239aa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800239af  mov     eax, ebx
0x1800239b1  mov     rcx, [rbp+170h+var_10]
0x1800239b8  xor     rcx, rsp; StackCookie
0x1800239bb  call    __security_check_cookie
0x1800239c0  lea     r11, [rsp+270h+var_s0]
0x1800239c8  mov     rbx, [r11+20h]
0x1800239cc  mov     rdi, [r11+28h]
0x1800239d0  mov     rsp, r11
0x1800239d3  pop     rbp
0x1800239d4  retn
0x1800239d5  mov     r8, rdi
0x1800239d8  lea     rdx, [rsp+270h+var_240]
0x1800239dd  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800239e2  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800239e7  mov     ebx, eax
0x1800239e9  test    eax, eax
0x1800239eb  jns     short loc_180023998
0x1800239ed  mov     rcx, [rbp+178h]; this
0x1800239f4  mov     r9d, eax; char *
0x1800239f7  mov     edx, 137h; void *
0x1800239fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023a01  nop
0x180023a02  lea     rcx, [rsp+270h+var_238]
0x180023a07  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180023a0c  nop
0x180023a0d  jmp     short loc_1800239A5
```
