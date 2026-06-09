# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180027f50`
- end: `0x1800280af`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18002a58c`

## callees

- `0x180027b10`
- `0x180027b2c`
- `0x180027f50`
- `0x18002a3b8`
- `0x18002b2b0`
- `0x18002cefc`
- `0x18002d6a8`
- `0x18002da8c`
- `0x18002e3d0`
- `0x18002e6f0`
- `0x180031680`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180027f88`
- `KERNEL32!GetCurrentProcessId` at `0x180027f88`
- `KERNEL32!CreateMutexExW` at `0x180027fcd`
- `KERNEL32!CreateMutexExW` at `0x180027fcd`

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
0x180027f50  mov     [rsp-8+arg_10], rbx
0x180027f55  mov     [rsp-8+arg_18], rdi
0x180027f5a  push    rbp
0x180027f5b  lea     rbp, [rsp-170h]
0x180027f63  sub     rsp, 270h
0x180027f6a  mov     rax, cs:__security_cookie
0x180027f71  xor     rax, rsp
0x180027f74  mov     [rbp+170h+var_10], rax
0x180027f7b  mov     rdi, rdx
0x180027f7e  mov     qword ptr [rdx], 0
0x180027f85  mov     rbx, rcx
0x180027f88  call    cs:__imp_GetCurrentProcessId
0x180027f8e  mov     [rsp+270h+var_248], rbx
0x180027f93  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180027f9a  mov     r9d, eax
0x180027f9d  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180027fa5  mov     edx, 104h; unsigned __int64
0x180027faa  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180027faf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180027fb4  mov     r9d, 1F0001h; dwDesiredAccess
0x180027fba  mov     [rsp+270h+var_240], 0
0x180027fc3  xor     r8d, r8d; dwFlags
0x180027fc6  lea     rdx, [rsp+270h+Name]; lpName
0x180027fcb  xor     ecx, ecx; lpMutexAttributes
0x180027fcd  call    cs:__imp_CreateMutexExW
0x180027fd3  mov     rdx, rax
0x180027fd6  lea     rcx, [rsp+270h+var_240]
0x180027fdb  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180027fe0  cmp     [rsp+270h+var_240], 0
0x180027fe6  jnz     short loc_180027FF1
0x180027fe8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180027fed  mov     ebx, eax
0x180027fef  jmp     short loc_18002805D
0x180027ff1  lea     rdx, [rsp+270h+var_238]
0x180027ff6  lea     rcx, [rsp+270h+var_240]
0x180027ffb  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180028000  lea     rdx, [rsp+270h+var_230]; void **
0x180028005  mov     [rsp+270h+var_230], 0
0x18002800e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180028013  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180028018  mov     ebx, eax
0x18002801a  test    eax, eax
0x18002801c  jns     short loc_18002803E
0x18002801e  mov     edx, 12Eh; void *
0x180028023  mov     rcx, [rbp+178h]; this
0x18002802a  mov     r9d, eax; char *
0x18002802d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028032  lea     rcx, [rsp+270h+var_238]
0x180028037  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002803c  jmp     short loc_18002805D
0x18002803e  mov     rcx, [rsp+270h+var_230]
0x180028043  test    rcx, rcx
0x180028046  jz      short loc_18002808D
0x180028048  mov     [rdi], rcx
0x18002804b  mov     eax, [rcx]
0x18002804d  inc     eax
0x18002804f  mov     [rcx], eax
0x180028051  lea     rcx, [rsp+270h+var_238]
0x180028056  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002805b  xor     ebx, ebx
0x18002805d  lea     rcx, [rsp+270h+var_240]
0x180028062  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180028067  mov     eax, ebx
0x180028069  mov     rcx, [rbp+170h+var_10]
0x180028070  xor     rcx, rsp; StackCookie
0x180028073  call    __security_check_cookie
0x180028078  lea     r11, [rsp+270h+var_s0]
0x180028080  mov     rbx, [r11+20h]
0x180028084  mov     rdi, [r11+28h]
0x180028088  mov     rsp, r11
0x18002808b  pop     rbp
0x18002808c  retn
0x18002808d  mov     r8, rdi
0x180028090  lea     rdx, [rsp+270h+var_240]
0x180028095  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002809a  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18002809f  mov     ebx, eax
0x1800280a1  test    eax, eax
0x1800280a3  jns     short loc_180028051
0x1800280a5  mov     edx, 137h
0x1800280aa  jmp     loc_180028023
```
