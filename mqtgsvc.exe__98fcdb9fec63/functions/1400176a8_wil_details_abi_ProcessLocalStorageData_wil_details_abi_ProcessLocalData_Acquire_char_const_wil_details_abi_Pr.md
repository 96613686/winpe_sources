# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1400176a8`
- end: `0x14001780a`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `354`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140018794`

## callees

- `0x1400037dc`
- `0x1400172f8`
- `0x140017314`
- `0x1400176a8`
- `0x140018528`
- `0x1400190b0`
- `0x14001a3bc`
- `0x14001ae20`
- `0x14001b684`
- `0x14001bdc0`
- `0x14001cf00`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x140017725`
- `KERNEL32!CreateMutexExW` at `0x140017725`
- `KERNEL32!GetCurrentProcessId` at `0x1400176e0`
- `KERNEL32!GetCurrentProcessId` at `0x1400176e0`

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
0x1400176a8  mov     [rsp-8+arg_10], rbx
0x1400176ad  mov     [rsp-8+arg_18], rdi
0x1400176b2  push    rbp
0x1400176b3  lea     rbp, [rsp-170h]
0x1400176bb  sub     rsp, 270h
0x1400176c2  mov     rax, cs:__security_cookie
0x1400176c9  xor     rax, rsp
0x1400176cc  mov     [rbp+170h+var_10], rax
0x1400176d3  mov     rdi, rdx
0x1400176d6  mov     rbx, rcx
0x1400176d9  mov     qword ptr [rdx], 0
0x1400176e0  call    cs:__imp_GetCurrentProcessId
0x1400176e6  mov     r9d, eax
0x1400176e9  mov     [rsp+270h+var_248], rbx
0x1400176ee  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1400176f6  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1400176fd  mov     edx, 104h; unsigned __int64
0x140017702  lea     rcx, [rsp+270h+Name]; wchar_t *
0x140017707  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x14001770c  mov     [rsp+270h+var_240], 0
0x140017715  mov     r9d, 1F0001h; dwDesiredAccess
0x14001771b  xor     r8d, r8d; dwFlags
0x14001771e  lea     rdx, [rsp+270h+Name]; lpName
0x140017723  xor     ecx, ecx; lpMutexAttributes
0x140017725  call    cs:__imp_CreateMutexExW
0x14001772b  mov     rdx, rax
0x14001772e  lea     rcx, [rsp+270h+var_240]
0x140017733  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140017738  cmp     [rsp+270h+var_240], 0
0x14001773e  jnz     short loc_140017749
0x140017740  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140017745  mov     ebx, eax
0x140017747  jmp     short loc_1400177B7
0x140017749  lea     rdx, [rsp+270h+var_238]
0x14001774e  lea     rcx, [rsp+270h+var_240]
0x140017753  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x140017758  nop
0x140017759  mov     [rsp+270h+var_230], 0
0x140017762  lea     rdx, [rsp+270h+var_230]; void **
0x140017767  lea     rcx, [rsp+270h+Name]; wchar_t *
0x14001776c  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x140017771  mov     ebx, eax
0x140017773  test    eax, eax
0x140017775  jns     short loc_140017798
0x140017777  mov     edx, 12Eh; void *
0x14001777c  mov     r9d, eax; char *
0x14001777f  mov     rcx, [rbp+178h]; this
0x140017786  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001778b  nop
0x14001778c  lea     rcx, [rsp+270h+var_238]
0x140017791  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140017796  jmp     short loc_1400177B7
0x140017798  mov     rcx, [rsp+270h+var_230]
0x14001779d  test    rcx, rcx
0x1400177a0  jz      short loc_1400177E7
0x1400177a2  mov     [rdi], rcx
0x1400177a5  mov     eax, [rcx]
0x1400177a7  inc     eax
0x1400177a9  mov     [rcx], eax
0x1400177ab  lea     rcx, [rsp+270h+var_238]
0x1400177b0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400177b5  xor     ebx, ebx
0x1400177b7  lea     rcx, [rsp+270h+var_240]
0x1400177bc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400177c1  mov     eax, ebx
0x1400177c3  mov     rcx, [rbp+170h+var_10]
0x1400177ca  xor     rcx, rsp; StackCookie
0x1400177cd  call    __security_check_cookie
0x1400177d2  lea     r11, [rsp+270h+var_s0]
0x1400177da  mov     rbx, [r11+20h]
0x1400177de  mov     rdi, [r11+28h]
0x1400177e2  mov     rsp, r11
0x1400177e5  pop     rbp
0x1400177e6  retn
0x1400177e7  mov     r8, rdi
0x1400177ea  lea     rdx, [rsp+270h+var_240]
0x1400177ef  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1400177f4  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1400177f9  mov     ebx, eax
0x1400177fb  test    eax, eax
0x1400177fd  jns     short loc_1400177AB
0x1400177ff  mov     edx, 137h
0x140017804  jmp     loc_14001777C
```
