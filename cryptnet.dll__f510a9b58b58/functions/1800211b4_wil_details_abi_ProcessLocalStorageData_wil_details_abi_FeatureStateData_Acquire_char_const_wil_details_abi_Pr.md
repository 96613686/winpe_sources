# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800211b4`
- end: `0x180021313`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180021e90`

## callees

- `0x1800031e8`
- `0x18001ae48`
- `0x18001afa4`
- `0x180020ebc`
- `0x180020ed8`
- `0x1800211b4`
- `0x180021d18`
- `0x180023b74`
- `0x180024324`
- `0x180024518`
- `0x1800265b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800211ec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800211ec`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180021231`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180021231`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v10, v9, (const char *)(unsigned int)Pointer, 304);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
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
0x1800211b4  mov     [rsp-8+arg_10], rbx
0x1800211b9  mov     [rsp-8+arg_18], rdi
0x1800211be  push    rbp
0x1800211bf  lea     rbp, [rsp-170h]
0x1800211c7  sub     rsp, 270h
0x1800211ce  mov     rax, cs:__security_cookie
0x1800211d5  xor     rax, rsp
0x1800211d8  mov     [rbp+170h+var_10], rax
0x1800211df  mov     rdi, rdx
0x1800211e2  mov     qword ptr [rdx], 0
0x1800211e9  mov     rbx, rcx
0x1800211ec  call    cs:__imp_GetCurrentProcessId
0x1800211f2  mov     [rsp+270h+var_248], rbx
0x1800211f7  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800211fe  mov     r9d, eax
0x180021201  mov     [rsp+270h+var_250], 130h; int
0x180021209  mov     edx, 104h; unsigned __int64
0x18002120e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180021213  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180021218  mov     r9d, 1F0001h; dwDesiredAccess
0x18002121e  mov     [rsp+270h+var_240], 0
0x180021227  xor     r8d, r8d; dwFlags
0x18002122a  lea     rdx, [rsp+270h+Name]; lpName
0x18002122f  xor     ecx, ecx; lpMutexAttributes
0x180021231  call    cs:__imp_CreateMutexExW
0x180021237  mov     rdx, rax
0x18002123a  lea     rcx, [rsp+270h+var_240]
0x18002123f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180021244  cmp     [rsp+270h+var_240], 0
0x18002124a  jnz     short loc_180021255
0x18002124c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180021251  mov     ebx, eax
0x180021253  jmp     short loc_1800212C1
0x180021255  lea     rdx, [rsp+270h+var_238]
0x18002125a  lea     rcx, [rsp+270h+var_240]
0x18002125f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180021264  lea     rdx, [rsp+270h+var_230]; void **
0x180021269  mov     [rsp+270h+var_230], 0
0x180021272  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180021277  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18002127c  mov     ebx, eax
0x18002127e  test    eax, eax
0x180021280  jns     short loc_1800212A2
0x180021282  mov     edx, 12Eh; void *
0x180021287  mov     rcx, [rbp+178h]; this
0x18002128e  mov     r9d, eax; char *
0x180021291  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021296  lea     rcx, [rsp+270h+var_238]
0x18002129b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800212a0  jmp     short loc_1800212C1
0x1800212a2  mov     rcx, [rsp+270h+var_230]
0x1800212a7  test    rcx, rcx
0x1800212aa  jz      short loc_1800212F1
0x1800212ac  mov     [rdi], rcx
0x1800212af  mov     eax, [rcx]
0x1800212b1  inc     eax
0x1800212b3  mov     [rcx], eax
0x1800212b5  lea     rcx, [rsp+270h+var_238]
0x1800212ba  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800212bf  xor     ebx, ebx
0x1800212c1  lea     rcx, [rsp+270h+var_240]
0x1800212c6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800212cb  mov     eax, ebx
0x1800212cd  mov     rcx, [rbp+170h+var_10]
0x1800212d4  xor     rcx, rsp; StackCookie
0x1800212d7  call    __security_check_cookie
0x1800212dc  lea     r11, [rsp+270h+var_s0]
0x1800212e4  mov     rbx, [r11+20h]
0x1800212e8  mov     rdi, [r11+28h]
0x1800212ec  mov     rsp, r11
0x1800212ef  pop     rbp
0x1800212f0  retn
0x1800212f1  mov     r8, rdi
0x1800212f4  lea     rdx, [rsp+270h+var_240]
0x1800212f9  lea     rcx, [rsp+270h+Name]
0x1800212fe  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180021303  mov     ebx, eax
0x180021305  test    eax, eax
0x180021307  jns     short loc_1800212B5
0x180021309  mov     edx, 137h
0x18002130e  jmp     loc_180021287
```
