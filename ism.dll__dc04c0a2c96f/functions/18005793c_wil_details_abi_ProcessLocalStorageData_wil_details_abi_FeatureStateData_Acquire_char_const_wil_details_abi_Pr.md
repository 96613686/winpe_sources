# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18005793c`
- end: `0x180057a93`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `343`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800f3814`

## callees

- `0x18005793c`
- `0x180057a9c`
- `0x180057bec`
- `0x180082994`
- `0x18008db50`
- `0x18008e97c`
- `0x18008ead4`
- `0x180099dd4`
- `0x1800afa30`
- `0x1800f0990`
- `0x1800f4578`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180057974`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180057974`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800579b9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800579b9`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  int Pointer; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdx
  _DWORD *v10; // rcx
  __int64 v11; // [rsp+30h] [rbp-D0h] BYREF
  void *v12; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v13[16]; // [rsp+40h] [rbp-C0h] BYREF
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
  if ( !v11 )
    return wil::details::GetLastErrorFailHr(v5);
  _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
    &v11,
    v13);
  v12 = 0;
  Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v12);
  v8 = Pointer;
  if ( Pointer < 0 )
  {
    v9 = 302;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"wil",
      (const char *)(unsigned int)Pointer,
      304);
    goto LABEL_8;
  }
  v10 = v12;
  if ( v12 )
  {
    *a2 = v12;
    ++*v10;
  }
  else
  {
    Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
    v8 = Pointer;
    if ( Pointer < 0 )
    {
      v9 = 311;
      goto LABEL_11;
    }
  }
  v8 = 0;
LABEL_8:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v13);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v11);
  return v8;
}

```

## disassembly

```asm
0x18005793c  mov     [rsp-8+arg_10], rbx
0x180057941  mov     [rsp-8+arg_18], rdi
0x180057946  push    rbp
0x180057947  lea     rbp, [rsp-170h]
0x18005794f  sub     rsp, 270h
0x180057956  mov     rax, cs:__security_cookie
0x18005795d  xor     rax, rsp
0x180057960  mov     [rbp+170h+var_10], rax
0x180057967  mov     rdi, rdx
0x18005796a  mov     qword ptr [rdx], 0
0x180057971  mov     rbx, rcx
0x180057974  call    cs:__imp_GetCurrentProcessId
0x18005797a  mov     [rsp+270h+var_248], rbx
0x18005797f  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180057986  mov     r9d, eax
0x180057989  mov     [rsp+270h+var_250], 130h; int
0x180057991  mov     edx, 104h; unsigned __int64
0x180057996  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18005799b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800579a0  mov     r9d, 1F0001h; dwDesiredAccess
0x1800579a6  mov     [rsp+270h+var_240], 0
0x1800579af  xor     r8d, r8d; dwFlags
0x1800579b2  lea     rdx, [rsp+270h+Name]; lpName
0x1800579b7  xor     ecx, ecx; lpMutexAttributes
0x1800579b9  call    cs:__imp_CreateMutexExW
0x1800579bf  mov     rdx, rax
0x1800579c2  lea     rcx, [rsp+270h+var_240]
0x1800579c7  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800579cc  cmp     [rsp+270h+var_240], 0
0x1800579d2  jnz     short loc_1800579DB
0x1800579d4  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800579d9  jmp     short loc_180057A3A
0x1800579db  lea     rdx, [rsp+270h+var_230]
0x1800579e0  lea     rcx, [rsp+270h+var_240]
0x1800579e5  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800579ea  lea     rdx, [rsp+270h+var_238]; void **
0x1800579ef  mov     [rsp+270h+var_238], 0
0x1800579f8  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800579fd  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180057a02  mov     ebx, eax
0x180057a04  test    eax, eax
0x180057a06  jns     short loc_180057A0F
0x180057a08  mov     edx, 12Eh
0x180057a0d  jmp     short loc_180057A7B
0x180057a0f  mov     rcx, [rsp+270h+var_238]
0x180057a14  test    rcx, rcx
0x180057a17  jz      short loc_180057A5E
0x180057a19  mov     [rdi], rcx
0x180057a1c  mov     eax, [rcx]
0x180057a1e  inc     eax
0x180057a20  mov     [rcx], eax
0x180057a22  xor     ebx, ebx
0x180057a24  lea     rcx, [rsp+270h+var_230]
0x180057a29  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180057a2e  lea     rcx, [rsp+270h+var_240]
0x180057a33  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180057a38  mov     eax, ebx
0x180057a3a  mov     rcx, [rbp+170h+var_10]
0x180057a41  xor     rcx, rsp; StackCookie
0x180057a44  call    __security_check_cookie
0x180057a49  lea     r11, [rsp+270h+var_s0]
0x180057a51  mov     rbx, [r11+20h]
0x180057a55  mov     rdi, [r11+28h]
0x180057a59  mov     rsp, r11
0x180057a5c  pop     rbp
0x180057a5d  retn
0x180057a5e  mov     r8, rdi
0x180057a61  lea     rdx, [rsp+270h+var_240]
0x180057a66  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180057a6b  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180057a70  mov     ebx, eax
0x180057a72  test    eax, eax
0x180057a74  jns     short loc_180057A22
0x180057a76  mov     edx, 137h; void *
0x180057a7b  mov     rcx, [rbp+178h]; this
0x180057a82  lea     r8, aWil; "wil"
0x180057a89  mov     r9d, eax; char *
0x180057a8c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180057a91  jmp     short loc_180057A24
```
