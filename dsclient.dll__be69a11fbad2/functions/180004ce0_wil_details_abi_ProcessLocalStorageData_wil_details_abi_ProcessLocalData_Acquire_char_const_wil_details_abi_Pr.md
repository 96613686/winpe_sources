# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180004ce0`
- end: `0x180004e3f`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180005d98`

## callees

- `0x180001e80`
- `0x1800024a4`
- `0x18000499c`
- `0x1800049b8`
- `0x180004ce0`
- `0x1800065dc`
- `0x180007948`
- `0x1800082e4`
- `0x180008b14`
- `0x180008e10`
- `0x180009950`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004d18`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004d18`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004d5d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180004d5d`

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
  __int64 v10; // rdx
  _DWORD *v11; // rcx
  wil::details *v13; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v14; // [rsp+38h] [rbp-C8h] BYREF
  void *v15; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v13 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v13,
    Mutex);
  if ( v13 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      (HANDLE *)&v13,
      &v14);
    v15 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v15);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v10 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v10, v9, (const char *)(unsigned int)Pointer, 120);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v14);
      goto LABEL_9;
    }
    v11 = v15;
    if ( v15 )
    {
      *a2 = v15;
      ++*v11;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v10 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v14);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v13,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180004ce0  mov     [rsp-8+arg_10], rbx
0x180004ce5  mov     [rsp-8+arg_18], rdi
0x180004cea  push    rbp
0x180004ceb  lea     rbp, [rsp-170h]
0x180004cf3  sub     rsp, 270h
0x180004cfa  mov     rax, cs:__security_cookie
0x180004d01  xor     rax, rsp
0x180004d04  mov     [rbp+170h+var_10], rax
0x180004d0b  mov     rdi, rdx
0x180004d0e  mov     qword ptr [rdx], 0
0x180004d15  mov     rbx, rcx
0x180004d18  call    cs:__imp_GetCurrentProcessId
0x180004d1e  mov     [rsp+270h+var_248], rbx
0x180004d23  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180004d2a  mov     r9d, eax
0x180004d2d  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180004d35  mov     edx, 104h; unsigned __int64
0x180004d3a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180004d3f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004d44  mov     r9d, 1F0001h; dwDesiredAccess
0x180004d4a  mov     [rsp+270h+var_240], 0
0x180004d53  xor     r8d, r8d; dwFlags
0x180004d56  lea     rdx, [rsp+270h+Name]; lpName
0x180004d5b  xor     ecx, ecx; lpMutexAttributes
0x180004d5d  call    cs:__imp_CreateMutexExW
0x180004d63  mov     rdx, rax
0x180004d66  lea     rcx, [rsp+270h+var_240]
0x180004d6b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180004d70  cmp     [rsp+270h+var_240], 0
0x180004d76  jnz     short loc_180004D81
0x180004d78  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180004d7d  mov     ebx, eax
0x180004d7f  jmp     short loc_180004DED
0x180004d81  lea     rdx, [rsp+270h+var_238]
0x180004d86  lea     rcx, [rsp+270h+var_240]
0x180004d8b  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180004d90  lea     rdx, [rsp+270h+var_230]; void **
0x180004d95  mov     [rsp+270h+var_230], 0
0x180004d9e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180004da3  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180004da8  mov     ebx, eax
0x180004daa  test    eax, eax
0x180004dac  jns     short loc_180004DCE
0x180004dae  mov     edx, 12Eh; void *
0x180004db3  mov     rcx, [rbp+178h]; this
0x180004dba  mov     r9d, eax; char *
0x180004dbd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004dc2  lea     rcx, [rsp+270h+var_238]
0x180004dc7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180004dcc  jmp     short loc_180004DED
0x180004dce  mov     rcx, [rsp+270h+var_230]
0x180004dd3  test    rcx, rcx
0x180004dd6  jz      short loc_180004E1D
0x180004dd8  mov     [rdi], rcx
0x180004ddb  mov     eax, [rcx]
0x180004ddd  inc     eax
0x180004ddf  mov     [rcx], eax
0x180004de1  lea     rcx, [rsp+270h+var_238]
0x180004de6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180004deb  xor     ebx, ebx
0x180004ded  lea     rcx, [rsp+270h+var_240]
0x180004df2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180004df7  mov     eax, ebx
0x180004df9  mov     rcx, [rbp+170h+var_10]
0x180004e00  xor     rcx, rsp; StackCookie
0x180004e03  call    __security_check_cookie
0x180004e08  lea     r11, [rsp+270h+var_s0]
0x180004e10  mov     rbx, [r11+20h]
0x180004e14  mov     rdi, [r11+28h]
0x180004e18  mov     rsp, r11
0x180004e1b  pop     rbp
0x180004e1c  retn
0x180004e1d  mov     r8, rdi
0x180004e20  lea     rdx, [rsp+270h+var_240]
0x180004e25  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180004e2a  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180004e2f  mov     ebx, eax
0x180004e31  test    eax, eax
0x180004e33  jns     short loc_180004DE1
0x180004e35  mov     edx, 137h
0x180004e3a  jmp     loc_180004DB3
```
