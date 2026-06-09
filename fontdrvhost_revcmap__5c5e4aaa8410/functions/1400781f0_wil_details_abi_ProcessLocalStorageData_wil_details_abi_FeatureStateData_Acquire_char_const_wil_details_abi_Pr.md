# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1400781f0`
- end: `0x14007834f`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140078f34`

## callees

- `0x1400750cc`
- `0x140075228`
- `0x140075de0`
- `0x140077da4`
- `0x140077dc0`
- `0x1400781f0`
- `0x140078d78`
- `0x14007ad48`
- `0x14007afe8`
- `0x14007b7d4`
- `0x14007b9fc`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x140078228`
- `KERNEL32!GetCurrentProcessId` at `0x140078228`
- `KERNEL32!CreateMutexExW` at `0x14007826d`
- `KERNEL32!CreateMutexExW` at `0x14007826d`

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
0x1400781f0  mov     [rsp-8+arg_10], rbx
0x1400781f5  mov     [rsp-8+arg_18], rdi
0x1400781fa  push    rbp
0x1400781fb  lea     rbp, [rsp-170h]
0x140078203  sub     rsp, 270h
0x14007820a  mov     rax, cs:__security_cookie
0x140078211  xor     rax, rsp
0x140078214  mov     [rbp+170h+var_10], rax
0x14007821b  mov     rdi, rdx
0x14007821e  mov     qword ptr [rdx], 0
0x140078225  mov     rbx, rcx
0x140078228  call    cs:__imp_GetCurrentProcessId
0x14007822e  mov     [rsp+270h+var_248], rbx
0x140078233  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x14007823a  mov     r9d, eax
0x14007823d  mov     [rsp+270h+var_250], 130h; int
0x140078245  mov     edx, 104h; unsigned __int64
0x14007824a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x14007824f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140078254  mov     r9d, 1F0001h; dwDesiredAccess
0x14007825a  mov     [rsp+270h+var_240], 0
0x140078263  xor     r8d, r8d; dwFlags
0x140078266  lea     rdx, [rsp+270h+Name]; lpName
0x14007826b  xor     ecx, ecx; lpMutexAttributes
0x14007826d  call    cs:__imp_CreateMutexExW
0x140078273  mov     rdx, rax
0x140078276  lea     rcx, [rsp+270h+var_240]
0x14007827b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140078280  cmp     [rsp+270h+var_240], 0
0x140078286  jnz     short loc_140078291
0x140078288  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14007828d  mov     ebx, eax
0x14007828f  jmp     short loc_1400782FD
0x140078291  lea     rdx, [rsp+270h+var_238]
0x140078296  lea     rcx, [rsp+270h+var_240]
0x14007829b  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1400782a0  lea     rdx, [rsp+270h+var_230]; void **
0x1400782a5  mov     [rsp+270h+var_230], 0
0x1400782ae  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1400782b3  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1400782b8  mov     ebx, eax
0x1400782ba  test    eax, eax
0x1400782bc  jns     short loc_1400782DE
0x1400782be  mov     edx, 12Eh; void *
0x1400782c3  mov     rcx, [rbp+178h]; this
0x1400782ca  mov     r9d, eax; char *
0x1400782cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400782d2  lea     rcx, [rsp+270h+var_238]
0x1400782d7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400782dc  jmp     short loc_1400782FD
0x1400782de  mov     rcx, [rsp+270h+var_230]
0x1400782e3  test    rcx, rcx
0x1400782e6  jz      short loc_14007832D
0x1400782e8  mov     [rdi], rcx
0x1400782eb  mov     eax, [rcx]
0x1400782ed  inc     eax
0x1400782ef  mov     [rcx], eax
0x1400782f1  lea     rcx, [rsp+270h+var_238]
0x1400782f6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400782fb  xor     ebx, ebx
0x1400782fd  lea     rcx, [rsp+270h+var_240]
0x140078302  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140078307  mov     eax, ebx
0x140078309  mov     rcx, [rbp+170h+var_10]
0x140078310  xor     rcx, rsp; StackCookie
0x140078313  call    __security_check_cookie
0x140078318  lea     r11, [rsp+270h+var_s0]
0x140078320  mov     rbx, [r11+20h]
0x140078324  mov     rdi, [r11+28h]
0x140078328  mov     rsp, r11
0x14007832b  pop     rbp
0x14007832c  retn
0x14007832d  mov     r8, rdi
0x140078330  lea     rdx, [rsp+270h+var_240]
0x140078335  lea     rcx, [rsp+270h+Name]
0x14007833a  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x14007833f  mov     ebx, eax
0x140078341  test    eax, eax
0x140078343  jns     short loc_1400782F1
0x140078345  mov     edx, 137h
0x14007834a  jmp     loc_1400782C3
```
