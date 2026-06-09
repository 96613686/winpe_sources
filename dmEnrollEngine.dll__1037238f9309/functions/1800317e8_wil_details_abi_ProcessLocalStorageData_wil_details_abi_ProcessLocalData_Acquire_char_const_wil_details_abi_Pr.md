# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800317e8`
- end: `0x180031955`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `365`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18003219c`

## callees

- `0x1800067a0`
- `0x18000fd8c`
- `0x180011938`
- `0x1800212dc`
- `0x18002c648`
- `0x18002c664`
- `0x18002e1a0`
- `0x1800317e8`
- `0x180032408`
- `0x1800330b8`
- `0x180033468`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180031865`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180031865`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180031820`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180031820`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
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
      v12,
      0,
      0xFFFFFFFFLL);
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
        120);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
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
0x1800317e8  mov     [rsp-8+arg_10], rbx
0x1800317ed  mov     [rsp-8+arg_18], rdi
0x1800317f2  push    rbp
0x1800317f3  lea     rbp, [rsp-170h]
0x1800317fb  sub     rsp, 270h
0x180031802  mov     rax, cs:__security_cookie
0x180031809  xor     rax, rsp
0x18003180c  mov     [rbp+170h+var_10], rax
0x180031813  mov     rdi, rdx
0x180031816  mov     qword ptr [rdx], 0
0x18003181d  mov     rbx, rcx
0x180031820  call    cs:__imp_GetCurrentProcessId
0x180031826  mov     [rsp+270h+var_248], rbx
0x18003182b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180031832  mov     r9d, eax
0x180031835  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18003183d  mov     edx, 104h; unsigned __int64
0x180031842  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180031847  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003184c  mov     r9d, 1F0001h; dwDesiredAccess
0x180031852  mov     [rsp+270h+var_240], 0
0x18003185b  xor     r8d, r8d; dwFlags
0x18003185e  lea     rdx, [rsp+270h+Name]; lpName
0x180031863  xor     ecx, ecx; lpMutexAttributes
0x180031865  call    cs:__imp_CreateMutexExW
0x18003186b  mov     rdx, rax
0x18003186e  lea     rcx, [rsp+270h+var_240]
0x180031873  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180031878  cmp     [rsp+270h+var_240], 0
0x18003187e  jnz     short loc_180031889
0x180031880  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180031885  mov     ebx, eax
0x180031887  jmp     short loc_180031903
0x180031889  or      r9d, 0FFFFFFFFh
0x18003188d  lea     rdx, [rsp+270h+var_238]
0x180031892  xor     r8d, r8d
0x180031895  lea     rcx, [rsp+270h+var_240]
0x18003189a  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18003189f  lea     rdx, [rsp+270h+var_230]; void **
0x1800318a4  mov     [rsp+270h+var_230], 0
0x1800318ad  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800318b2  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800318b7  mov     ebx, eax
0x1800318b9  test    eax, eax
0x1800318bb  jns     short loc_1800318E4
0x1800318bd  mov     edx, 12Eh; void *
0x1800318c2  mov     rcx, [rbp+178h]; this
0x1800318c9  lea     r8, aWil; "wil"
0x1800318d0  mov     r9d, eax; char *
0x1800318d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800318d8  lea     rcx, [rsp+270h+var_238]
0x1800318dd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800318e2  jmp     short loc_180031903
0x1800318e4  mov     rcx, [rsp+270h+var_230]
0x1800318e9  test    rcx, rcx
0x1800318ec  jz      short loc_180031933
0x1800318ee  mov     [rdi], rcx
0x1800318f1  mov     eax, [rcx]
0x1800318f3  inc     eax
0x1800318f5  mov     [rcx], eax
0x1800318f7  lea     rcx, [rsp+270h+var_238]
0x1800318fc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180031901  xor     ebx, ebx
0x180031903  lea     rcx, [rsp+270h+var_240]
0x180031908  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003190d  mov     eax, ebx
0x18003190f  mov     rcx, [rbp+170h+var_10]
0x180031916  xor     rcx, rsp; StackCookie
0x180031919  call    __security_check_cookie
0x18003191e  lea     r11, [rsp+270h+var_s0]
0x180031926  mov     rbx, [r11+20h]
0x18003192a  mov     rdi, [r11+28h]
0x18003192e  mov     rsp, r11
0x180031931  pop     rbp
0x180031932  retn
0x180031933  mov     r8, rdi
0x180031936  lea     rdx, [rsp+270h+var_240]
0x18003193b  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180031940  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180031945  mov     ebx, eax
0x180031947  test    eax, eax
0x180031949  jns     short loc_1800318F7
0x18003194b  mov     edx, 137h
0x180031950  jmp     loc_1800318C2
```
