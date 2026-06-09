# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18002104c`
- end: `0x1800211ab`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180022010`

## callees

- `0x1800031e8`
- `0x18001acf4`
- `0x18001afa4`
- `0x180020ebc`
- `0x180020ed8`
- `0x18002104c`
- `0x180021d18`
- `0x180023b74`
- `0x180024324`
- `0x180024518`
- `0x1800265b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180021084`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180021084`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800210c9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800210c9`

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
  _BYTE v14[8]; // [rsp+38h] [rbp-C8h] BYREF
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
      &v13,
      v14);
    v15 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v15);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v10 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v10, v9, (const char *)(unsigned int)Pointer, 120);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v14);
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
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v14);
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
0x18002104c  mov     [rsp-8+arg_10], rbx
0x180021051  mov     [rsp-8+arg_18], rdi
0x180021056  push    rbp
0x180021057  lea     rbp, [rsp-170h]
0x18002105f  sub     rsp, 270h
0x180021066  mov     rax, cs:__security_cookie
0x18002106d  xor     rax, rsp
0x180021070  mov     [rbp+170h+var_10], rax
0x180021077  mov     rdi, rdx
0x18002107a  mov     qword ptr [rdx], 0
0x180021081  mov     rbx, rcx
0x180021084  call    cs:__imp_GetCurrentProcessId
0x18002108a  mov     [rsp+270h+var_248], rbx
0x18002108f  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180021096  mov     r9d, eax
0x180021099  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800210a1  mov     edx, 104h; unsigned __int64
0x1800210a6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800210ab  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800210b0  mov     r9d, 1F0001h; dwDesiredAccess
0x1800210b6  mov     [rsp+270h+var_240], 0
0x1800210bf  xor     r8d, r8d; dwFlags
0x1800210c2  lea     rdx, [rsp+270h+Name]; lpName
0x1800210c7  xor     ecx, ecx; lpMutexAttributes
0x1800210c9  call    cs:__imp_CreateMutexExW
0x1800210cf  mov     rdx, rax
0x1800210d2  lea     rcx, [rsp+270h+var_240]
0x1800210d7  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800210dc  cmp     [rsp+270h+var_240], 0
0x1800210e2  jnz     short loc_1800210ED
0x1800210e4  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800210e9  mov     ebx, eax
0x1800210eb  jmp     short loc_180021159
0x1800210ed  lea     rdx, [rsp+270h+var_238]
0x1800210f2  lea     rcx, [rsp+270h+var_240]
0x1800210f7  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800210fc  lea     rdx, [rsp+270h+var_230]; void **
0x180021101  mov     [rsp+270h+var_230], 0
0x18002110a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002110f  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180021114  mov     ebx, eax
0x180021116  test    eax, eax
0x180021118  jns     short loc_18002113A
0x18002111a  mov     edx, 12Eh; void *
0x18002111f  mov     rcx, [rbp+178h]; this
0x180021126  mov     r9d, eax; char *
0x180021129  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002112e  lea     rcx, [rsp+270h+var_238]
0x180021133  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180021138  jmp     short loc_180021159
0x18002113a  mov     rcx, [rsp+270h+var_230]
0x18002113f  test    rcx, rcx
0x180021142  jz      short loc_180021189
0x180021144  mov     [rdi], rcx
0x180021147  mov     eax, [rcx]
0x180021149  inc     eax
0x18002114b  mov     [rcx], eax
0x18002114d  lea     rcx, [rsp+270h+var_238]
0x180021152  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180021157  xor     ebx, ebx
0x180021159  lea     rcx, [rsp+270h+var_240]
0x18002115e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180021163  mov     eax, ebx
0x180021165  mov     rcx, [rbp+170h+var_10]
0x18002116c  xor     rcx, rsp; StackCookie
0x18002116f  call    __security_check_cookie
0x180021174  lea     r11, [rsp+270h+var_s0]
0x18002117c  mov     rbx, [r11+20h]
0x180021180  mov     rdi, [r11+28h]
0x180021184  mov     rsp, r11
0x180021187  pop     rbp
0x180021188  retn
0x180021189  mov     r8, rdi
0x18002118c  lea     rdx, [rsp+270h+var_240]
0x180021191  lea     rcx, [rsp+270h+Name]
0x180021196  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18002119b  mov     ebx, eax
0x18002119d  test    eax, eax
0x18002119f  jns     short loc_18002114D
0x1800211a1  mov     edx, 137h
0x1800211a6  jmp     loc_18002111F
```
