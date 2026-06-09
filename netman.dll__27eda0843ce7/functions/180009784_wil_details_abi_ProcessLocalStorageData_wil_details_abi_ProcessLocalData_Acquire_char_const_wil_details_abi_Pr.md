# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180009784`
- end: `0x1800098ec`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `360`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001122c`

## callees

- `0x180001710`
- `0x180003d5c`
- `0x1800085c0`
- `0x1800085dc`
- `0x180009784`
- `0x180011134`
- `0x180011f60`
- `0x180016664`
- `0x1800179b8`
- `0x180018bb4`
- `0x180018f60`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x180009801`
- `KERNEL32!CreateMutexExW` at `0x180009801`
- `KERNEL32!GetCurrentProcessId` at `0x1800097bc`
- `KERNEL32!GetCurrentProcessId` at `0x1800097bc`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
  __int64 v13; // [rsp+38h] [rbp-C8h] BYREF
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
    v13 = 0;
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v12,
      &v13);
    v14 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v14);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v9 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 120);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v13);
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
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v13);
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
0x180009784  mov     [rsp-8+arg_10], rbx
0x180009789  mov     [rsp-8+arg_18], rdi
0x18000978e  push    rbp
0x18000978f  lea     rbp, [rsp-170h]
0x180009797  sub     rsp, 270h
0x18000979e  mov     rax, cs:__security_cookie
0x1800097a5  xor     rax, rsp
0x1800097a8  mov     [rbp+170h+var_10], rax
0x1800097af  mov     rdi, rdx
0x1800097b2  mov     qword ptr [rdx], 0
0x1800097b9  mov     rbx, rcx
0x1800097bc  call    cs:__imp_GetCurrentProcessId
0x1800097c2  mov     [rsp+270h+var_248], rbx
0x1800097c7  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800097ce  mov     r9d, eax
0x1800097d1  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800097d9  mov     edx, 104h; unsigned __int64
0x1800097de  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800097e3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800097e8  mov     r9d, 1F0001h; dwDesiredAccess
0x1800097ee  mov     [rsp+270h+var_240], 0
0x1800097f7  xor     r8d, r8d; dwFlags
0x1800097fa  lea     rdx, [rsp+270h+Name]; lpName
0x1800097ff  xor     ecx, ecx; lpMutexAttributes
0x180009801  call    cs:__imp_CreateMutexExW
0x180009807  mov     rdx, rax
0x18000980a  lea     rcx, [rsp+270h+var_240]
0x18000980f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180009814  cmp     [rsp+270h+var_240], 0
0x18000981a  jnz     short loc_180009825
0x18000981c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180009821  mov     ebx, eax
0x180009823  jmp     short loc_18000989A
0x180009825  lea     rdx, [rsp+270h+var_238]
0x18000982a  mov     [rsp+270h+var_238], 0
0x180009833  lea     rcx, [rsp+270h+var_240]
0x180009838  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000983d  lea     rdx, [rsp+270h+var_230]; void **
0x180009842  mov     [rsp+270h+var_230], 0
0x18000984b  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180009850  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180009855  mov     ebx, eax
0x180009857  test    eax, eax
0x180009859  jns     short loc_18000987B
0x18000985b  mov     edx, 12Eh; void *
0x180009860  mov     rcx, [rbp+178h]; this
0x180009867  mov     r9d, eax; char *
0x18000986a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000986f  lea     rcx, [rsp+270h+var_238]
0x180009874  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009879  jmp     short loc_18000989A
0x18000987b  mov     rcx, [rsp+270h+var_230]
0x180009880  test    rcx, rcx
0x180009883  jz      short loc_1800098CA
0x180009885  mov     [rdi], rcx
0x180009888  mov     eax, [rcx]
0x18000988a  inc     eax
0x18000988c  mov     [rcx], eax
0x18000988e  lea     rcx, [rsp+270h+var_238]
0x180009893  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009898  xor     ebx, ebx
0x18000989a  lea     rcx, [rsp+270h+var_240]
0x18000989f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800098a4  mov     eax, ebx
0x1800098a6  mov     rcx, [rbp+170h+var_10]
0x1800098ad  xor     rcx, rsp; StackCookie
0x1800098b0  call    __security_check_cookie
0x1800098b5  lea     r11, [rsp+270h+var_s0]
0x1800098bd  mov     rbx, [r11+20h]
0x1800098c1  mov     rdi, [r11+28h]
0x1800098c5  mov     rsp, r11
0x1800098c8  pop     rbp
0x1800098c9  retn
0x1800098ca  mov     r8, rdi
0x1800098cd  lea     rdx, [rsp+270h+var_240]
0x1800098d2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800098d7  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800098dc  mov     ebx, eax
0x1800098de  test    eax, eax
0x1800098e0  jns     short loc_18000988E
0x1800098e2  mov     edx, 137h
0x1800098e7  jmp     loc_180009860
```
