# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800e9028`
- end: `0x1800e919b`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `371`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800eac20`

## callees

- `0x180019080`
- `0x1800e7eb8`
- `0x1800e7ed8`
- `0x1800e9028`
- `0x1800eaa50`
- `0x1800eba88`
- `0x1800ed46c`
- `0x1800edd78`
- `0x1800ee248`
- `0x1800f0034`
- `0x1800f1c18`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800e90ab`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800e90ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800e9060`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800e9060`

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
0x1800e9028  mov     [rsp-8+arg_10], rbx
0x1800e902d  mov     [rsp-8+arg_18], rdi
0x1800e9032  push    rbp
0x1800e9033  lea     rbp, [rsp-170h]
0x1800e903b  sub     rsp, 270h
0x1800e9042  mov     rax, cs:__security_cookie
0x1800e9049  xor     rax, rsp
0x1800e904c  mov     [rbp+170h+var_10], rax
0x1800e9053  mov     rdi, rdx
0x1800e9056  mov     qword ptr [rdx], 0
0x1800e905d  mov     rbx, rcx
0x1800e9060  call    cs:__imp_GetCurrentProcessId
0x1800e9067  nop     dword ptr [rax+rax+00h]
0x1800e906c  mov     [rsp+270h+var_248], rbx
0x1800e9071  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800e9078  mov     r9d, eax
0x1800e907b  mov     [rsp+270h+var_250], 130h; int
0x1800e9083  mov     edx, 104h; unsigned __int64
0x1800e9088  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800e908d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800e9092  mov     r9d, 1F0001h; dwDesiredAccess
0x1800e9098  mov     [rsp+270h+var_240], 0
0x1800e90a1  xor     r8d, r8d; dwFlags
0x1800e90a4  lea     rdx, [rsp+270h+Name]; lpName
0x1800e90a9  xor     ecx, ecx; lpMutexAttributes
0x1800e90ab  call    cs:__imp_CreateMutexExW
0x1800e90b2  nop     dword ptr [rax+rax+00h]
0x1800e90b7  mov     rdx, rax
0x1800e90ba  lea     rcx, [rsp+270h+var_240]
0x1800e90bf  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800e90c4  cmp     [rsp+270h+var_240], 0
0x1800e90ca  jnz     short loc_1800E90D5
0x1800e90cc  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800e90d1  mov     ebx, eax
0x1800e90d3  jmp     short loc_1800E9148
0x1800e90d5  lea     rdx, [rsp+270h+var_238]
0x1800e90da  lea     rcx, [rsp+270h+var_240]
0x1800e90df  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800e90e4  lea     rdx, [rsp+270h+var_230]; void **
0x1800e90e9  mov     [rsp+270h+var_230], 0
0x1800e90f2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800e90f7  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800e90fc  mov     ebx, eax
0x1800e90fe  test    eax, eax
0x1800e9100  jns     short loc_1800E9129
0x1800e9102  mov     edx, 12Eh; void *
0x1800e9107  mov     rcx, [rbp+178h]; this
0x1800e910e  lea     r8, aWil; "wil"
0x1800e9115  mov     r9d, eax; char *
0x1800e9118  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e911d  lea     rcx, [rsp+270h+var_238]
0x1800e9122  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800e9127  jmp     short loc_1800E9148
0x1800e9129  mov     rcx, [rsp+270h+var_230]
0x1800e912e  test    rcx, rcx
0x1800e9131  jz      short loc_1800E9179
0x1800e9133  mov     [rdi], rcx
0x1800e9136  mov     eax, [rcx]
0x1800e9138  inc     eax
0x1800e913a  mov     [rcx], eax
0x1800e913c  lea     rcx, [rsp+270h+var_238]
0x1800e9141  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800e9146  xor     ebx, ebx
0x1800e9148  lea     rcx, [rsp+270h+var_240]
0x1800e914d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800e9152  mov     eax, ebx
0x1800e9154  mov     rcx, [rbp+170h+var_10]
0x1800e915b  xor     rcx, rsp; StackCookie
0x1800e915e  call    __security_check_cookie
0x1800e9163  lea     r11, [rsp+270h+var_s0]
0x1800e916b  mov     rbx, [r11+20h]
0x1800e916f  mov     rdi, [r11+28h]
0x1800e9173  mov     rsp, r11
0x1800e9176  pop     rbp
0x1800e9177  retn
0x1800e9179  mov     r8, rdi
0x1800e917c  lea     rdx, [rsp+270h+var_240]
0x1800e9181  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800e9186  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800e918b  mov     ebx, eax
0x1800e918d  test    eax, eax
0x1800e918f  jns     short loc_1800E913C
0x1800e9191  mov     edx, 137h
0x1800e9196  jmp     loc_1800E9107
```
