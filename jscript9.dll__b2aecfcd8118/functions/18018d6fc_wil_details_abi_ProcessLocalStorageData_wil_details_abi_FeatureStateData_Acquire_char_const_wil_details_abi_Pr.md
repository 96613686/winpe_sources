# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18018d6fc`
- end: `0x18018d90e`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `530`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1801cf0dc`

## callees

- `0x18018d6fc`
- `0x18018d914`
- `0x1801a29fc`
- `0x1801a2a24`
- `0x1801a2a90`
- `0x1801a6d90`
- `0x1801b0ba4`
- `0x1801b61e0`
- `0x1801cd924`
- `0x1801cfcb8`
- `0x1801d0d0c`
- `0x1803481f0`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x18018d74b`
- `KERNEL32!GetCurrentProcessId` at `0x18018d74b`
- `KERNEL32!CreateMutexExW` at `0x18018d796`
- `KERNEL32!CreateMutexExW` at `0x18018d796`

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
0x18018d6fc  mov     rax, rsp
0x18018d6ff  mov     [rax+10h], rdx
0x18018d703  mov     [rax+8], rcx
0x18018d707  push    rbp
0x18018d708  push    rsi
0x18018d709  push    rdi
0x18018d70a  lea     rbp, [rax-188h]
0x18018d711  sub     rsp, 270h
0x18018d718  mov     qword ptr [rsp+280h+var_238], 0FFFFFFFFFFFFFFFEh
0x18018d721  mov     [rax+18h], rbx
0x18018d725  mov     rax, cs:__security_cookie
0x18018d72c  xor     rax, rsp
0x18018d72f  mov     [rbp+180h+var_20], rax
0x18018d736  mov     rbx, [rbp+180h+arg_0]
0x18018d73d  mov     rdi, [rbp+180h+arg_8]
0x18018d744  mov     qword ptr [rdi], 0
0x18018d74b  call    cs:__imp_GetCurrentProcessId
0x18018d752  nop     dword ptr [rax+rax+00h]
0x18018d757  mov     r9d, eax
0x18018d75a  mov     [rsp+280h+var_258], rbx
0x18018d75f  mov     [rsp+280h+bAlertable], 130h
0x18018d767  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18018d76e  mov     edx, 104h; unsigned __int64
0x18018d773  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18018d778  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18018d77d  mov     qword ptr [rsp+280h+var_250], 0
0x18018d786  mov     r9d, 1F0001h; dwDesiredAccess
0x18018d78c  xor     r8d, r8d; dwFlags
0x18018d78f  lea     rdx, [rsp+280h+Name]; lpName
0x18018d794  xor     ecx, ecx; lpMutexAttributes
0x18018d796  call    cs:__imp_CreateMutexExW
0x18018d79d  nop     dword ptr [rax+rax+00h]
0x18018d7a2  mov     rbx, rax
0x18018d7a5  mov     qword ptr [rsp+280h+var_250], rax
0x18018d7aa  test    rax, rax
0x18018d7ad  jnz     short loc_18018D7BB
0x18018d7af  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18018d7b4  mov     ebx, eax
0x18018d7b6  jmp     loc_18018D8B9
0x18018d7bb  mov     [rsp+280h+bAlertable], 0; int
0x18018d7c3  or      r9d, 0FFFFFFFFh; int
0x18018d7c7  xor     r8d, r8d; int
0x18018d7ca  lea     rdx, [rsp+280h+var_248]; int
0x18018d7cf  lea     rcx, [rsp+280h+var_250]; int
0x18018d7d4  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18018d7d9  nop
0x18018d7da  mov     [rsp+280h+var_240], 0
0x18018d7e3  xor     r9d, r9d; bool *
0x18018d7e6  lea     r8, [rsp+280h+var_240]; unsigned __int64 *
0x18018d7eb  mov     dl, 1; bool
0x18018d7ed  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18018d7f2  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18018d7f7  mov     esi, eax
0x18018d7f9  test    eax, eax
0x18018d7fb  jns     short loc_18018D85D
0x18018d7fd  mov     rcx, [rbp+188h]; this
0x18018d804  mov     r9d, eax; char *
0x18018d807  lea     r8, aWil; "wil"
0x18018d80e  mov     edx, 66h ; 'f'; void *
0x18018d813  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018d818  mov     rcx, [rbp+188h]; this
0x18018d81f  mov     r9d, esi; char *
0x18018d822  lea     r8, aWil; "wil"
0x18018d829  mov     edx, 6Fh ; 'o'; void *
0x18018d82e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018d833  mov     rcx, [rbp+188h]; this
0x18018d83a  mov     r9d, esi; char *
0x18018d83d  lea     r8, aWil; "wil"
0x18018d844  mov     edx, 12Eh; void *
0x18018d849  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018d84e  nop
0x18018d84f  lea     rcx, [rsp+280h+var_248]
0x18018d854  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18018d859  mov     ebx, esi
0x18018d85b  jmp     short loc_18018D8B9
0x18018d85d  mov     rax, [rsp+280h+var_240]
0x18018d862  lea     rcx, ds:0[rax*4]
0x18018d86a  test    rcx, rcx
0x18018d86d  jz      short loc_18018D87A
0x18018d86f  mov     [rdi], rcx
0x18018d872  mov     eax, [rcx]
0x18018d874  inc     eax
0x18018d876  mov     [rcx], eax
0x18018d878  jmp     short loc_18018D8CC
0x18018d87a  mov     r8, rdi
0x18018d87d  lea     rdx, [rsp+280h+var_250]
0x18018d882  lea     rcx, [rsp+280h+Name]
0x18018d887  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18018d88c  mov     ebx, eax
0x18018d88e  test    eax, eax
0x18018d890  jns     short loc_18018D8C7
0x18018d892  mov     rcx, [rbp+188h]; this
0x18018d899  mov     r9d, eax; char *
0x18018d89c  lea     r8, aWil; "wil"
0x18018d8a3  mov     edx, 137h; void *
0x18018d8a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018d8ad  nop
0x18018d8ae  lea     rcx, [rsp+280h+var_248]
0x18018d8b3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18018d8b8  nop
0x18018d8b9  lea     rcx, [rsp+280h+var_250]
0x18018d8be  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18018d8c3  mov     eax, ebx
0x18018d8c5  jmp     short loc_18018D8EB
0x18018d8c7  mov     rbx, qword ptr [rsp+280h+var_250]
0x18018d8cc  mov     rcx, [rsp+280h+var_248]; this
0x18018d8d1  test    rcx, rcx
0x18018d8d4  jz      short loc_18018D8DC
0x18018d8d6  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18018d8db  nop
0x18018d8dc  test    rbx, rbx
0x18018d8df  jz      short loc_18018D8E9
0x18018d8e1  mov     rcx, rbx; this
0x18018d8e4  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18018d8e9  xor     eax, eax
0x18018d8eb  mov     rcx, [rbp+180h+var_20]
0x18018d8f2  xor     rcx, rsp; StackCookie
0x18018d8f5  call    __security_check_cookie
0x18018d8fa  mov     rbx, [rsp+280h+arg_10]
0x18018d902  add     rsp, 270h
0x18018d909  pop     rdi
0x18018d90a  pop     rsi
0x18018d90b  pop     rbp
0x18018d90c  retn
```
