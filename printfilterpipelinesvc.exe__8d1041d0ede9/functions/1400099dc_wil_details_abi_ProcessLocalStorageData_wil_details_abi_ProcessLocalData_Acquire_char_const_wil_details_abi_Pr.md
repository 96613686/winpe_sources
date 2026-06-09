# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1400099dc`
- end: `0x140009b3b`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x14000b12c`

## callees

- `0x140002070`
- `0x140007654`
- `0x140009578`
- `0x140009594`
- `0x1400099dc`
- `0x14000ae58`
- `0x14000bda8`
- `0x14000d5ac`
- `0x14000e1f8`
- `0x14000ea8c`
- `0x14000eda4`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x140009a59`
- `KERNEL32!CreateMutexExW` at `0x140009a59`
- `KERNEL32!GetCurrentProcessId` at `0x140009a14`
- `KERNEL32!GetCurrentProcessId` at `0x140009a14`

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
0x1400099dc  mov     [rsp-8+arg_10], rbx
0x1400099e1  mov     [rsp-8+arg_18], rdi
0x1400099e6  push    rbp
0x1400099e7  lea     rbp, [rsp-170h]
0x1400099ef  sub     rsp, 270h
0x1400099f6  mov     rax, cs:__security_cookie
0x1400099fd  xor     rax, rsp
0x140009a00  mov     [rbp+170h+var_10], rax
0x140009a07  mov     rdi, rdx
0x140009a0a  mov     qword ptr [rdx], 0
0x140009a11  mov     rbx, rcx
0x140009a14  call    cs:__imp_GetCurrentProcessId
0x140009a1a  mov     [rsp+270h+var_248], rbx
0x140009a1f  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140009a26  mov     r9d, eax
0x140009a29  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x140009a31  mov     edx, 104h; unsigned __int64
0x140009a36  lea     rcx, [rsp+270h+Name]; wchar_t *
0x140009a3b  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x140009a40  mov     r9d, 1F0001h; dwDesiredAccess
0x140009a46  mov     [rsp+270h+var_240], 0
0x140009a4f  xor     r8d, r8d; dwFlags
0x140009a52  lea     rdx, [rsp+270h+Name]; lpName
0x140009a57  xor     ecx, ecx; lpMutexAttributes
0x140009a59  call    cs:__imp_CreateMutexExW
0x140009a5f  mov     rdx, rax
0x140009a62  lea     rcx, [rsp+270h+var_240]
0x140009a67  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140009a6c  cmp     [rsp+270h+var_240], 0
0x140009a72  jnz     short loc_140009A7D
0x140009a74  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140009a79  mov     ebx, eax
0x140009a7b  jmp     short loc_140009AE9
0x140009a7d  lea     rdx, [rsp+270h+var_238]
0x140009a82  lea     rcx, [rsp+270h+var_240]
0x140009a87  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x140009a8c  lea     rdx, [rsp+270h+var_230]; void **
0x140009a91  mov     [rsp+270h+var_230], 0
0x140009a9a  lea     rcx, [rsp+270h+Name]; wchar_t *
0x140009a9f  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x140009aa4  mov     ebx, eax
0x140009aa6  test    eax, eax
0x140009aa8  jns     short loc_140009ACA
0x140009aaa  mov     edx, 12Eh; void *
0x140009aaf  mov     rcx, [rbp+178h]; this
0x140009ab6  mov     r9d, eax; char *
0x140009ab9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009abe  lea     rcx, [rsp+270h+var_238]
0x140009ac3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140009ac8  jmp     short loc_140009AE9
0x140009aca  mov     rcx, [rsp+270h+var_230]
0x140009acf  test    rcx, rcx
0x140009ad2  jz      short loc_140009B19
0x140009ad4  mov     [rdi], rcx
0x140009ad7  mov     eax, [rcx]
0x140009ad9  inc     eax
0x140009adb  mov     [rcx], eax
0x140009add  lea     rcx, [rsp+270h+var_238]
0x140009ae2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140009ae7  xor     ebx, ebx
0x140009ae9  lea     rcx, [rsp+270h+var_240]
0x140009aee  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140009af3  mov     eax, ebx
0x140009af5  mov     rcx, [rbp+170h+var_10]
0x140009afc  xor     rcx, rsp; StackCookie
0x140009aff  call    __security_check_cookie
0x140009b04  lea     r11, [rsp+270h+var_s0]
0x140009b0c  mov     rbx, [r11+20h]
0x140009b10  mov     rdi, [r11+28h]
0x140009b14  mov     rsp, r11
0x140009b17  pop     rbp
0x140009b18  retn
0x140009b19  mov     r8, rdi
0x140009b1c  lea     rdx, [rsp+270h+var_240]
0x140009b21  lea     rcx, [rsp+270h+Name]; wchar_t *
0x140009b26  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x140009b2b  mov     ebx, eax
0x140009b2d  test    eax, eax
0x140009b2f  jns     short loc_140009ADD
0x140009b31  mov     edx, 137h
0x140009b36  jmp     loc_140009AAF
```
