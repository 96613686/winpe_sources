# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180226a44`
- end: `0x180226baa`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180226db4`

## callees

- `0x180210b78`
- `0x180212490`
- `0x180226608`
- `0x180226624`
- `0x180226a44`
- `0x1802280d4`
- `0x180228eec`
- `0x1802295b8`
- `0x180229a0c`
- `0x18022a194`
- `0x18022a320`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180226a7c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180226a7c`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180226ac1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180226ac1`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
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
        304);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
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
0x180226a44  mov     [rsp-8+arg_10], rbx
0x180226a49  mov     [rsp-8+arg_18], rdi
0x180226a4e  push    rbp
0x180226a4f  lea     rbp, [rsp-170h]
0x180226a57  sub     rsp, 270h
0x180226a5e  mov     rax, cs:__security_cookie
0x180226a65  xor     rax, rsp
0x180226a68  mov     [rbp+170h+var_10], rax
0x180226a6f  mov     rdi, rdx
0x180226a72  mov     qword ptr [rdx], 0
0x180226a79  mov     rbx, rcx
0x180226a7c  call    cs:__imp_GetCurrentProcessId
0x180226a82  mov     [rsp+270h+var_248], rbx
0x180226a87  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180226a8e  mov     r9d, eax
0x180226a91  mov     [rsp+270h+var_250], 130h; int
0x180226a99  mov     edx, 104h; unsigned __int64
0x180226a9e  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180226aa3  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180226aa8  mov     r9d, 1F0001h; dwDesiredAccess
0x180226aae  mov     [rsp+270h+var_240], 0
0x180226ab7  xor     r8d, r8d; dwFlags
0x180226aba  lea     rdx, [rsp+270h+Name]; lpName
0x180226abf  xor     ecx, ecx; lpMutexAttributes
0x180226ac1  call    cs:__imp_CreateMutexExW
0x180226ac7  mov     rdx, rax
0x180226aca  lea     rcx, [rsp+270h+var_240]
0x180226acf  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180226ad4  cmp     [rsp+270h+var_240], 0
0x180226ada  jnz     short loc_180226AE5
0x180226adc  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180226ae1  mov     ebx, eax
0x180226ae3  jmp     short loc_180226B58
0x180226ae5  lea     rdx, [rsp+270h+var_238]
0x180226aea  lea     rcx, [rsp+270h+var_240]
0x180226aef  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180226af4  lea     rdx, [rsp+270h+var_230]; void **
0x180226af9  mov     [rsp+270h+var_230], 0
0x180226b02  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180226b07  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x180226b0c  mov     ebx, eax
0x180226b0e  test    eax, eax
0x180226b10  jns     short loc_180226B39
0x180226b12  mov     edx, 12Eh; void *
0x180226b17  mov     rcx, [rbp+178h]; this
0x180226b1e  lea     r8, aWil; "wil"
0x180226b25  mov     r9d, eax; char *
0x180226b28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180226b2d  lea     rcx, [rsp+270h+var_238]
0x180226b32  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180226b37  jmp     short loc_180226B58
0x180226b39  mov     rcx, [rsp+270h+var_230]
0x180226b3e  test    rcx, rcx
0x180226b41  jz      short loc_180226B88
0x180226b43  mov     [rdi], rcx
0x180226b46  mov     eax, [rcx]
0x180226b48  inc     eax
0x180226b4a  mov     [rcx], eax
0x180226b4c  lea     rcx, [rsp+270h+var_238]
0x180226b51  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180226b56  xor     ebx, ebx
0x180226b58  lea     rcx, [rsp+270h+var_240]
0x180226b5d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180226b62  mov     eax, ebx
0x180226b64  mov     rcx, [rbp+170h+var_10]
0x180226b6b  xor     rcx, rsp; StackCookie
0x180226b6e  call    __security_check_cookie
0x180226b73  lea     r11, [rsp+270h+var_s0]
0x180226b7b  mov     rbx, [r11+20h]
0x180226b7f  mov     rdi, [r11+28h]
0x180226b83  mov     rsp, r11
0x180226b86  pop     rbp
0x180226b87  retn
0x180226b88  mov     r8, rdi
0x180226b8b  lea     rdx, [rsp+270h+var_240]
0x180226b90  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180226b95  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180226b9a  mov     ebx, eax
0x180226b9c  test    eax, eax
0x180226b9e  jns     short loc_180226B4C
0x180226ba0  mov     edx, 137h
0x180226ba5  jmp     loc_180226B17
```
