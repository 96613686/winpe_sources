# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180032764`
- end: `0x1800328c3`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180033484`

## callees

- `0x18003233c`
- `0x180032358`
- `0x180032764`
- `0x1800332c8`
- `0x180034080`
- `0x180034ff4`
- `0x1800354d4`
- `0x180035ad0`
- `0x180036274`
- `0x18003654c`
- `0x180037620`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x1800327e1`
- `KERNEL32!CreateMutexExW` at `0x1800327e1`
- `KERNEL32!GetCurrentProcessId` at `0x18003279c`
- `KERNEL32!GetCurrentProcessId` at `0x18003279c`

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
0x180032764  mov     [rsp-8+arg_10], rbx
0x180032769  mov     [rsp-8+arg_18], rdi
0x18003276e  push    rbp
0x18003276f  lea     rbp, [rsp-170h]
0x180032777  sub     rsp, 270h
0x18003277e  mov     rax, cs:__security_cookie
0x180032785  xor     rax, rsp
0x180032788  mov     [rbp+170h+var_10], rax
0x18003278f  mov     rdi, rdx
0x180032792  mov     qword ptr [rdx], 0
0x180032799  mov     rbx, rcx
0x18003279c  call    cs:__imp_GetCurrentProcessId
0x1800327a2  mov     [rsp+270h+var_248], rbx
0x1800327a7  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800327ae  mov     r9d, eax
0x1800327b1  mov     [rsp+270h+var_250], 130h; int
0x1800327b9  mov     edx, 104h; unsigned __int64
0x1800327be  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800327c3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800327c8  mov     r9d, 1F0001h; dwDesiredAccess
0x1800327ce  mov     [rsp+270h+var_240], 0
0x1800327d7  xor     r8d, r8d; dwFlags
0x1800327da  lea     rdx, [rsp+270h+Name]; lpName
0x1800327df  xor     ecx, ecx; lpMutexAttributes
0x1800327e1  call    cs:__imp_CreateMutexExW
0x1800327e7  mov     rdx, rax
0x1800327ea  lea     rcx, [rsp+270h+var_240]
0x1800327ef  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800327f4  cmp     [rsp+270h+var_240], 0
0x1800327fa  jnz     short loc_180032805
0x1800327fc  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180032801  mov     ebx, eax
0x180032803  jmp     short loc_180032871
0x180032805  lea     rdx, [rsp+270h+var_238]
0x18003280a  lea     rcx, [rsp+270h+var_240]
0x18003280f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180032814  lea     rdx, [rsp+270h+var_230]; void **
0x180032819  mov     [rsp+270h+var_230], 0
0x180032822  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180032827  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18003282c  mov     ebx, eax
0x18003282e  test    eax, eax
0x180032830  jns     short loc_180032852
0x180032832  mov     edx, 12Eh; void *
0x180032837  mov     rcx, [rbp+178h]; this
0x18003283e  mov     r9d, eax; char *
0x180032841  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032846  lea     rcx, [rsp+270h+var_238]
0x18003284b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180032850  jmp     short loc_180032871
0x180032852  mov     rcx, [rsp+270h+var_230]
0x180032857  test    rcx, rcx
0x18003285a  jz      short loc_1800328A1
0x18003285c  mov     [rdi], rcx
0x18003285f  mov     eax, [rcx]
0x180032861  inc     eax
0x180032863  mov     [rcx], eax
0x180032865  lea     rcx, [rsp+270h+var_238]
0x18003286a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003286f  xor     ebx, ebx
0x180032871  lea     rcx, [rsp+270h+var_240]
0x180032876  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003287b  mov     eax, ebx
0x18003287d  mov     rcx, [rbp+170h+var_10]
0x180032884  xor     rcx, rsp; StackCookie
0x180032887  call    __security_check_cookie
0x18003288c  lea     r11, [rsp+270h+var_s0]
0x180032894  mov     rbx, [r11+20h]
0x180032898  mov     rdi, [r11+28h]
0x18003289c  mov     rsp, r11
0x18003289f  pop     rbp
0x1800328a0  retn
0x1800328a1  mov     r8, rdi
0x1800328a4  lea     rdx, [rsp+270h+var_240]
0x1800328a9  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800328ae  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800328b3  mov     ebx, eax
0x1800328b5  test    eax, eax
0x1800328b7  jns     short loc_180032865
0x1800328b9  mov     edx, 137h
0x1800328be  jmp     loc_180032837
```
