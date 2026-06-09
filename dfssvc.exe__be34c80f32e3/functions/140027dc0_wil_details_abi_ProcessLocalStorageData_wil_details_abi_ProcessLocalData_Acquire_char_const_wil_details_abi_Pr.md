# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140027dc0`
- end: `0x140027f26`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x14002b38c`

## callees

- `0x14000aed8`
- `0x140027a34`
- `0x140027a54`
- `0x140027dc0`
- `0x14002b118`
- `0x14002ca60`
- `0x14002f044`
- `0x14003081c`
- `0x140031c84`
- `0x140031f00`
- `0x14005ce70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140027e3d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140027e3d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140027df5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140027df5`

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
      v9 = 299;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 120);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v13);
      goto LABEL_9;
    }
    v10 = v14;
    if ( v14 )
    {
      *a2 = v14;
      *(_DWORD *)*a2 = *v10 + 1;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v9 = 308;
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
0x140027dc0  mov     [rsp-8+arg_10], rbx
0x140027dc5  mov     [rsp-8+arg_18], rdi
0x140027dca  push    rbp
0x140027dcb  lea     rbp, [rsp-170h]
0x140027dd3  sub     rsp, 270h
0x140027dda  mov     rax, cs:__security_cookie
0x140027de1  xor     rax, rsp
0x140027de4  mov     [rbp+170h+var_10], rax
0x140027deb  and     qword ptr [rdx], 0
0x140027def  mov     rdi, rdx
0x140027df2  mov     rbx, rcx
0x140027df5  call    cs:__imp_GetCurrentProcessId
0x140027dfc  nop     dword ptr [rax+rax+00h]
0x140027e01  mov     [rsp+270h+var_248], rbx
0x140027e06  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140027e0d  mov     r9d, eax
0x140027e10  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x140027e18  mov     edx, 104h; unsigned __int64
0x140027e1d  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140027e22  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140027e27  and     [rsp+270h+var_240], 0
0x140027e2d  lea     rdx, [rsp+270h+Name]; lpName
0x140027e32  mov     r9d, 1F0001h; dwDesiredAccess
0x140027e38  xor     r8d, r8d; dwFlags
0x140027e3b  xor     ecx, ecx; lpMutexAttributes
0x140027e3d  call    cs:__imp_CreateMutexExW
0x140027e44  nop     dword ptr [rax+rax+00h]
0x140027e49  mov     rdx, rax
0x140027e4c  lea     rcx, [rsp+270h+var_240]
0x140027e51  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140027e56  cmp     [rsp+270h+var_240], 0
0x140027e5c  jnz     short loc_140027E67
0x140027e5e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140027e63  mov     ebx, eax
0x140027e65  jmp     short loc_140027ED3
0x140027e67  lea     rdx, [rsp+270h+var_238]
0x140027e6c  lea     rcx, [rsp+270h+var_240]
0x140027e71  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x140027e76  and     [rsp+270h+var_230], 0
0x140027e7c  lea     rdx, [rsp+270h+var_230]; void **
0x140027e81  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140027e86  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x140027e8b  mov     ebx, eax
0x140027e8d  test    eax, eax
0x140027e8f  jns     short loc_140027EB1
0x140027e91  mov     edx, 12Bh; void *
0x140027e96  mov     rcx, [rbp+178h]; this
0x140027e9d  mov     r9d, eax; char *
0x140027ea0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140027ea5  lea     rcx, [rsp+270h+var_238]
0x140027eaa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140027eaf  jmp     short loc_140027ED3
0x140027eb1  mov     rcx, [rsp+270h+var_230]
0x140027eb6  test    rcx, rcx
0x140027eb9  jz      short loc_140027F04
0x140027ebb  mov     [rdi], rcx
0x140027ebe  mov     ecx, [rcx]
0x140027ec0  mov     rax, [rdi]
0x140027ec3  inc     ecx
0x140027ec5  mov     [rax], ecx
0x140027ec7  lea     rcx, [rsp+270h+var_238]
0x140027ecc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140027ed1  xor     ebx, ebx
0x140027ed3  lea     rcx, [rsp+270h+var_240]
0x140027ed8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140027edd  mov     eax, ebx
0x140027edf  mov     rcx, [rbp+170h+var_10]
0x140027ee6  xor     rcx, rsp; StackCookie
0x140027ee9  call    __security_check_cookie
0x140027eee  lea     r11, [rsp+270h+var_s0]
0x140027ef6  mov     rbx, [r11+20h]
0x140027efa  mov     rdi, [r11+28h]
0x140027efe  mov     rsp, r11
0x140027f01  pop     rbp
0x140027f02  retn
0x140027f04  mov     r8, rdi
0x140027f07  lea     rdx, [rsp+270h+var_240]
0x140027f0c  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140027f11  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x140027f16  mov     ebx, eax
0x140027f18  test    eax, eax
0x140027f1a  jns     short loc_140027EC7
0x140027f1c  mov     edx, 134h
0x140027f21  jmp     loc_140027E96
```
