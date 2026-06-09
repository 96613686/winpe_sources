# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000e108`
- end: `0x18000e26e`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000f150`

## callees

- `0x180005640`
- `0x18000af70`
- `0x18000b238`
- `0x18000b290`
- `0x18000be40`
- `0x18000de20`
- `0x18000de3c`
- `0x18000e108`
- `0x18001160c`
- `0x180011ed4`
- `0x180012124`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000e185`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000e185`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000e140`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000e140`

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
      v13,
      0,
      0xFFFFFFFFLL);
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
0x18000e108  mov     [rsp-8+arg_10], rbx
0x18000e10d  mov     [rsp-8+arg_18], rdi
0x18000e112  push    rbp
0x18000e113  lea     rbp, [rsp-170h]
0x18000e11b  sub     rsp, 270h
0x18000e122  mov     rax, cs:__security_cookie
0x18000e129  xor     rax, rsp
0x18000e12c  mov     [rbp+170h+var_10], rax
0x18000e133  mov     rdi, rdx
0x18000e136  mov     qword ptr [rdx], 0
0x18000e13d  mov     rbx, rcx
0x18000e140  call    cs:__imp_GetCurrentProcessId
0x18000e146  mov     [rsp+270h+var_248], rbx
0x18000e14b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000e152  mov     r9d, eax
0x18000e155  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000e15d  mov     edx, 104h; unsigned __int64
0x18000e162  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000e167  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000e16c  mov     r9d, 1F0001h; dwDesiredAccess
0x18000e172  mov     [rsp+270h+var_240], 0
0x18000e17b  xor     r8d, r8d; dwFlags
0x18000e17e  lea     rdx, [rsp+270h+Name]; lpName
0x18000e183  xor     ecx, ecx; lpMutexAttributes
0x18000e185  call    cs:__imp_CreateMutexExW
0x18000e18b  mov     rdx, rax
0x18000e18e  lea     rcx, [rsp+270h+var_240]
0x18000e193  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000e198  cmp     [rsp+270h+var_240], 0
0x18000e19e  jnz     short loc_18000E1A9
0x18000e1a0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000e1a5  mov     ebx, eax
0x18000e1a7  jmp     short loc_18000E21C
0x18000e1a9  or      r9d, 0FFFFFFFFh
0x18000e1ad  lea     rdx, [rsp+270h+var_238]
0x18000e1b2  xor     r8d, r8d
0x18000e1b5  lea     rcx, [rsp+270h+var_240]
0x18000e1ba  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000e1bf  lea     rdx, [rsp+270h+var_230]; void **
0x18000e1c4  mov     [rsp+270h+var_230], 0
0x18000e1cd  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000e1d2  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18000e1d7  mov     ebx, eax
0x18000e1d9  test    eax, eax
0x18000e1db  jns     short loc_18000E1FD
0x18000e1dd  mov     edx, 12Eh; void *
0x18000e1e2  mov     rcx, [rbp+178h]; this
0x18000e1e9  mov     r9d, eax; char *
0x18000e1ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e1f1  lea     rcx, [rsp+270h+var_238]
0x18000e1f6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000e1fb  jmp     short loc_18000E21C
0x18000e1fd  mov     rcx, [rsp+270h+var_230]
0x18000e202  test    rcx, rcx
0x18000e205  jz      short loc_18000E24C
0x18000e207  mov     [rdi], rcx
0x18000e20a  mov     eax, [rcx]
0x18000e20c  inc     eax
0x18000e20e  mov     [rcx], eax
0x18000e210  lea     rcx, [rsp+270h+var_238]
0x18000e215  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000e21a  xor     ebx, ebx
0x18000e21c  lea     rcx, [rsp+270h+var_240]
0x18000e221  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000e226  mov     eax, ebx
0x18000e228  mov     rcx, [rbp+170h+var_10]
0x18000e22f  xor     rcx, rsp; StackCookie
0x18000e232  call    __security_check_cookie
0x18000e237  lea     r11, [rsp+270h+var_s0]
0x18000e23f  mov     rbx, [r11+20h]
0x18000e243  mov     rdi, [r11+28h]
0x18000e247  mov     rsp, r11
0x18000e24a  pop     rbp
0x18000e24b  retn
0x18000e24c  mov     r8, rdi
0x18000e24f  lea     rdx, [rsp+270h+var_240]
0x18000e254  lea     rcx, [rsp+270h+Name]
0x18000e259  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000e25e  mov     ebx, eax
0x18000e260  test    eax, eax
0x18000e262  jns     short loc_18000E210
0x18000e264  mov     edx, 137h
0x18000e269  jmp     loc_18000E1E2
```
