# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x140017810`
- end: `0x140017972`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `354`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140017bc4`

## callees

- `0x1400037dc`
- `0x1400172f8`
- `0x140017314`
- `0x140017810`
- `0x140018528`
- `0x1400191dc`
- `0x14001a3bc`
- `0x14001ae20`
- `0x14001b684`
- `0x14001bdc0`
- `0x14001cf00`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x14001788d`
- `KERNEL32!CreateMutexExW` at `0x14001788d`
- `KERNEL32!GetCurrentProcessId` at `0x140017848`
- `KERNEL32!GetCurrentProcessId` at `0x140017848`

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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 304);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
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
0x140017810  mov     [rsp-8+arg_10], rbx
0x140017815  mov     [rsp-8+arg_18], rdi
0x14001781a  push    rbp
0x14001781b  lea     rbp, [rsp-170h]
0x140017823  sub     rsp, 270h
0x14001782a  mov     rax, cs:__security_cookie
0x140017831  xor     rax, rsp
0x140017834  mov     [rbp+170h+var_10], rax
0x14001783b  mov     rdi, rdx
0x14001783e  mov     rbx, rcx
0x140017841  mov     qword ptr [rdx], 0
0x140017848  call    cs:__imp_GetCurrentProcessId
0x14001784e  mov     r9d, eax
0x140017851  mov     [rsp+270h+var_248], rbx
0x140017856  mov     [rsp+270h+var_250], 130h; int
0x14001785e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140017865  mov     edx, 104h; unsigned __int64
0x14001786a  lea     rcx, [rsp+270h+Name]; wchar_t *
0x14001786f  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x140017874  mov     [rsp+270h+var_240], 0
0x14001787d  mov     r9d, 1F0001h; dwDesiredAccess
0x140017883  xor     r8d, r8d; dwFlags
0x140017886  lea     rdx, [rsp+270h+Name]; lpName
0x14001788b  xor     ecx, ecx; lpMutexAttributes
0x14001788d  call    cs:__imp_CreateMutexExW
0x140017893  mov     rdx, rax
0x140017896  lea     rcx, [rsp+270h+var_240]
0x14001789b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1400178a0  cmp     [rsp+270h+var_240], 0
0x1400178a6  jnz     short loc_1400178B1
0x1400178a8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400178ad  mov     ebx, eax
0x1400178af  jmp     short loc_14001791F
0x1400178b1  lea     rdx, [rsp+270h+var_238]
0x1400178b6  lea     rcx, [rsp+270h+var_240]
0x1400178bb  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1400178c0  nop
0x1400178c1  mov     [rsp+270h+var_230], 0
0x1400178ca  lea     rdx, [rsp+270h+var_230]; void **
0x1400178cf  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1400178d4  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x1400178d9  mov     ebx, eax
0x1400178db  test    eax, eax
0x1400178dd  jns     short loc_140017900
0x1400178df  mov     edx, 12Eh; void *
0x1400178e4  mov     r9d, eax; char *
0x1400178e7  mov     rcx, [rbp+178h]; this
0x1400178ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400178f3  nop
0x1400178f4  lea     rcx, [rsp+270h+var_238]
0x1400178f9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400178fe  jmp     short loc_14001791F
0x140017900  mov     rcx, [rsp+270h+var_230]
0x140017905  test    rcx, rcx
0x140017908  jz      short loc_14001794F
0x14001790a  mov     [rdi], rcx
0x14001790d  mov     eax, [rcx]
0x14001790f  inc     eax
0x140017911  mov     [rcx], eax
0x140017913  lea     rcx, [rsp+270h+var_238]
0x140017918  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14001791d  xor     ebx, ebx
0x14001791f  lea     rcx, [rsp+270h+var_240]
0x140017924  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140017929  mov     eax, ebx
0x14001792b  mov     rcx, [rbp+170h+var_10]
0x140017932  xor     rcx, rsp; StackCookie
0x140017935  call    __security_check_cookie
0x14001793a  lea     r11, [rsp+270h+var_s0]
0x140017942  mov     rbx, [r11+20h]
0x140017946  mov     rdi, [r11+28h]
0x14001794a  mov     rsp, r11
0x14001794d  pop     rbp
0x14001794e  retn
0x14001794f  mov     r8, rdi
0x140017952  lea     rdx, [rsp+270h+var_240]
0x140017957  lea     rcx, [rsp+270h+Name]; wchar_t *
0x14001795c  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x140017961  mov     ebx, eax
0x140017963  test    eax, eax
0x140017965  jns     short loc_140017913
0x140017967  mov     edx, 137h
0x14001796c  jmp     loc_1400178E4
```
