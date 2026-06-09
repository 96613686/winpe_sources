# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x14000e354`
- end: `0x14000e4ba`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x14001233c`

## callees

- `0x1400026a0`
- `0x140009310`
- `0x14000aad8`
- `0x14000e354`
- `0x14000e4c0`
- `0x14000e4dc`
- `0x14000e504`
- `0x14000e558`
- `0x14000fb48`
- `0x140012700`
- `0x14001e050`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x14000e3d1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x14000e3d1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000e38c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000e38c`

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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(
                  Name,
                  &v11,
                  a2);
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
0x14000e354  mov     [rsp-8+arg_10], rbx
0x14000e359  mov     [rsp-8+arg_18], rdi
0x14000e35e  push    rbp
0x14000e35f  lea     rbp, [rsp-170h]
0x14000e367  sub     rsp, 270h
0x14000e36e  mov     rax, cs:__security_cookie
0x14000e375  xor     rax, rsp
0x14000e378  mov     [rbp+170h+var_10], rax
0x14000e37f  mov     rdi, rdx
0x14000e382  mov     qword ptr [rdx], 0
0x14000e389  mov     rbx, rcx
0x14000e38c  call    cs:__imp_GetCurrentProcessId
0x14000e392  mov     [rsp+270h+var_248], rbx
0x14000e397  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x14000e39e  mov     r9d, eax
0x14000e3a1  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x14000e3a9  mov     edx, 104h; unsigned __int64
0x14000e3ae  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x14000e3b3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000e3b8  mov     r9d, 1F0001h; dwDesiredAccess
0x14000e3be  mov     [rsp+270h+var_240], 0
0x14000e3c7  xor     r8d, r8d; dwFlags
0x14000e3ca  lea     rdx, [rsp+270h+Name]; lpName
0x14000e3cf  xor     ecx, ecx; lpMutexAttributes
0x14000e3d1  call    cs:__imp_CreateMutexExW
0x14000e3d7  mov     rdx, rax
0x14000e3da  lea     rcx, [rsp+270h+var_240]
0x14000e3df  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x14000e3e4  cmp     [rsp+270h+var_240], 0
0x14000e3ea  jnz     short loc_14000E3F5
0x14000e3ec  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000e3f1  mov     ebx, eax
0x14000e3f3  jmp     short loc_14000E468
0x14000e3f5  lea     rdx, [rsp+270h+var_238]
0x14000e3fa  lea     rcx, [rsp+270h+var_240]
0x14000e3ff  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x14000e404  lea     rdx, [rsp+270h+var_230]; void **
0x14000e409  mov     [rsp+270h+var_230], 0
0x14000e412  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x14000e417  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x14000e41c  mov     ebx, eax
0x14000e41e  test    eax, eax
0x14000e420  jns     short loc_14000E449
0x14000e422  mov     edx, 12Eh; void *
0x14000e427  mov     rcx, [rbp+178h]; this
0x14000e42e  lea     r8, aWil; "wil"
0x14000e435  mov     r9d, eax; char *
0x14000e438  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000e43d  lea     rcx, [rsp+270h+var_238]
0x14000e442  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000e447  jmp     short loc_14000E468
0x14000e449  mov     rcx, [rsp+270h+var_230]
0x14000e44e  test    rcx, rcx
0x14000e451  jz      short loc_14000E498
0x14000e453  mov     [rdi], rcx
0x14000e456  mov     eax, [rcx]
0x14000e458  inc     eax
0x14000e45a  mov     [rcx], eax
0x14000e45c  lea     rcx, [rsp+270h+var_238]
0x14000e461  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000e466  xor     ebx, ebx
0x14000e468  lea     rcx, [rsp+270h+var_240]
0x14000e46d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000e472  mov     eax, ebx
0x14000e474  mov     rcx, [rbp+170h+var_10]
0x14000e47b  xor     rcx, rsp; StackCookie
0x14000e47e  call    __security_check_cookie
0x14000e483  lea     r11, [rsp+270h+var_s0]
0x14000e48b  mov     rbx, [r11+20h]
0x14000e48f  mov     rdi, [r11+28h]
0x14000e493  mov     rsp, r11
0x14000e496  pop     rbp
0x14000e497  retn
0x14000e498  mov     r8, rdi
0x14000e49b  lea     rdx, [rsp+270h+var_240]
0x14000e4a0  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x14000e4a5  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x14000e4aa  mov     ebx, eax
0x14000e4ac  test    eax, eax
0x14000e4ae  jns     short loc_14000E45C
0x14000e4b0  mov     edx, 137h
0x14000e4b5  jmp     loc_14000E427
```
