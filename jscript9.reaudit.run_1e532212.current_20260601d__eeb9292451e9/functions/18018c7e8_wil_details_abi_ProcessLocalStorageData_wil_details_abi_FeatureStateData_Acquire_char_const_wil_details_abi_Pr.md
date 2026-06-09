# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18018c7e8`
- end: `0x18018c9ed`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `517`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1801cc5fc`

## callees

- `0x18018c7e8`
- `0x18018c9f4`
- `0x1801a0688`
- `0x1801a06b0`
- `0x1801a071c`
- `0x1801a3d4c`
- `0x1801ae624`
- `0x1801b3ac0`
- `0x1801caea4`
- `0x1801cd184`
- `0x1801ce140`
- `0x180341dd0`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x18018c837`
- `KERNEL32!GetCurrentProcessId` at `0x18018c837`
- `KERNEL32!CreateMutexExW` at `0x18018c87c`
- `KERNEL32!CreateMutexExW` at `0x18018c87c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  wil::details *v5; // rcx
  wil::details *Mutex; // rbx
  unsigned int LastErrorFailHr; // ebx
  int ValueInternal; // eax
  void *v9; // rdx
  unsigned int v10; // esi
  _DWORD *v11; // rcx
  int v12; // eax
  int bAlertable; // [rsp+28h] [rbp-E0h]
  int bAlertablea; // [rsp+28h] [rbp-E0h]
  int bAlertableb; // [rsp+28h] [rbp-E0h]
  int v17[2]; // [rsp+38h] [rbp-D0h] BYREF
  wil::details *v18; // [rsp+40h] [rbp-C8h] BYREF
  unsigned __int64 v19[2]; // [rsp+48h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+58h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+290h] [rbp+188h]

  v19[1] = -2;
  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId, 304, a1);
  Mutex = (wil::details *)CreateMutexExW(0, Name, 0, 0x1F0001u);
  *(_QWORD *)v17 = Mutex;
  if ( !Mutex )
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v17);
    return LastErrorFailHr;
  }
  _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
    (int)v17,
    (int)&v18,
    0,
    -1,
    0);
  v19[0] = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, 1, v19, 0);
  v10 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      bAlertable);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v10, bAlertablea);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v10, bAlertableb);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v18);
    LastErrorFailHr = v10;
    goto LABEL_9;
  }
  v11 = (_DWORD *)(4 * v19[0]);
  if ( 4 * v19[0] )
  {
    *a2 = v11;
    ++*v11;
  }
  else
  {
    v12 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(
            Name,
            v17,
            a2);
    LastErrorFailHr = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x137,
        (unsigned int)"wil",
        (const char *)(unsigned int)v12,
        bAlertable);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v18);
      goto LABEL_9;
    }
    Mutex = *(wil::details **)v17;
  }
  if ( v18 )
    wil::details::ReleaseMutex(v18, v9);
  if ( Mutex )
    wil::details::CloseHandle(Mutex, v9);
  return 0;
}

```

## disassembly

```asm
0x18018c7e8  mov     rax, rsp
0x18018c7eb  mov     [rax+10h], rdx
0x18018c7ef  mov     [rax+8], rcx
0x18018c7f3  push    rbp
0x18018c7f4  push    rsi
0x18018c7f5  push    rdi
0x18018c7f6  lea     rbp, [rax-188h]
0x18018c7fd  sub     rsp, 270h
0x18018c804  mov     qword ptr [rsp+280h+var_238], 0FFFFFFFFFFFFFFFEh
0x18018c80d  mov     [rax+18h], rbx
0x18018c811  mov     rax, cs:__security_cookie
0x18018c818  xor     rax, rsp
0x18018c81b  mov     [rbp+180h+var_20], rax
0x18018c822  mov     rbx, [rbp+180h+arg_0]
0x18018c829  mov     rdi, [rbp+180h+arg_8]
0x18018c830  mov     qword ptr [rdi], 0
0x18018c837  call    cs:__imp_GetCurrentProcessId
0x18018c83d  mov     r9d, eax
0x18018c840  mov     [rsp+280h+var_258], rbx
0x18018c845  mov     [rsp+280h+bAlertable], 130h
0x18018c84d  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18018c854  mov     edx, 104h; unsigned __int64
0x18018c859  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18018c85e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18018c863  mov     qword ptr [rsp+280h+var_250], 0
0x18018c86c  mov     r9d, 1F0001h; dwDesiredAccess
0x18018c872  xor     r8d, r8d; dwFlags
0x18018c875  lea     rdx, [rsp+280h+Name]; lpName
0x18018c87a  xor     ecx, ecx; lpMutexAttributes
0x18018c87c  call    cs:__imp_CreateMutexExW
0x18018c882  mov     rbx, rax
0x18018c885  mov     qword ptr [rsp+280h+var_250], rax
0x18018c88a  test    rax, rax
0x18018c88d  jnz     short loc_18018C89B
0x18018c88f  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18018c894  mov     ebx, eax
0x18018c896  jmp     loc_18018C999
0x18018c89b  mov     [rsp+280h+bAlertable], 0; int
0x18018c8a3  or      r9d, 0FFFFFFFFh; int
0x18018c8a7  xor     r8d, r8d; int
0x18018c8aa  lea     rdx, [rsp+280h+var_248]; int
0x18018c8af  lea     rcx, [rsp+280h+var_250]; int
0x18018c8b4  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18018c8b9  nop
0x18018c8ba  mov     [rsp+280h+var_240], 0
0x18018c8c3  xor     r9d, r9d; bool *
0x18018c8c6  lea     r8, [rsp+280h+var_240]; unsigned __int64 *
0x18018c8cb  mov     dl, 1; bool
0x18018c8cd  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18018c8d2  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18018c8d7  mov     esi, eax
0x18018c8d9  test    eax, eax
0x18018c8db  jns     short loc_18018C93D
0x18018c8dd  mov     rcx, [rbp+188h]; this
0x18018c8e4  mov     r9d, eax; char *
0x18018c8e7  lea     r8, aWil; "wil"
0x18018c8ee  mov     edx, 66h ; 'f'; void *
0x18018c8f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018c8f8  mov     rcx, [rbp+188h]; this
0x18018c8ff  mov     r9d, esi; char *
0x18018c902  lea     r8, aWil; "wil"
0x18018c909  mov     edx, 6Fh ; 'o'; void *
0x18018c90e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018c913  mov     rcx, [rbp+188h]; this
0x18018c91a  mov     r9d, esi; char *
0x18018c91d  lea     r8, aWil; "wil"
0x18018c924  mov     edx, 12Eh; void *
0x18018c929  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018c92e  nop
0x18018c92f  lea     rcx, [rsp+280h+var_248]
0x18018c934  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18018c939  mov     ebx, esi
0x18018c93b  jmp     short loc_18018C999
0x18018c93d  mov     rax, [rsp+280h+var_240]
0x18018c942  lea     rcx, ds:0[rax*4]
0x18018c94a  test    rcx, rcx
0x18018c94d  jz      short loc_18018C95A
0x18018c94f  mov     [rdi], rcx
0x18018c952  mov     eax, [rcx]
0x18018c954  inc     eax
0x18018c956  mov     [rcx], eax
0x18018c958  jmp     short loc_18018C9AC
0x18018c95a  mov     r8, rdi
0x18018c95d  lea     rdx, [rsp+280h+var_250]
0x18018c962  lea     rcx, [rsp+280h+Name]
0x18018c967  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18018c96c  mov     ebx, eax
0x18018c96e  test    eax, eax
0x18018c970  jns     short loc_18018C9A7
0x18018c972  mov     rcx, [rbp+188h]; this
0x18018c979  mov     r9d, eax; char *
0x18018c97c  lea     r8, aWil; "wil"
0x18018c983  mov     edx, 137h; void *
0x18018c988  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018c98d  nop
0x18018c98e  lea     rcx, [rsp+280h+var_248]
0x18018c993  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18018c998  nop
0x18018c999  lea     rcx, [rsp+280h+var_250]
0x18018c99e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18018c9a3  mov     eax, ebx
0x18018c9a5  jmp     short loc_18018C9CB
0x18018c9a7  mov     rbx, qword ptr [rsp+280h+var_250]
0x18018c9ac  mov     rcx, [rsp+280h+var_248]; this
0x18018c9b1  test    rcx, rcx
0x18018c9b4  jz      short loc_18018C9BC
0x18018c9b6  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18018c9bb  nop
0x18018c9bc  test    rbx, rbx
0x18018c9bf  jz      short loc_18018C9C9
0x18018c9c1  mov     rcx, rbx; this
0x18018c9c4  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18018c9c9  xor     eax, eax
0x18018c9cb  mov     rcx, [rbp+180h+var_20]
0x18018c9d2  xor     rcx, rsp; StackCookie
0x18018c9d5  call    __security_check_cookie
0x18018c9da  mov     rbx, [rsp+280h+arg_10]
0x18018c9e2  add     rsp, 270h
0x18018c9e9  pop     rdi
0x18018c9ea  pop     rsi
0x18018c9eb  pop     rbp
0x18018c9ec  retn
```
