# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800171a0`
- end: `0x18001731b`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180019f50`

## callees

- `0x1800153e8`
- `0x180016b50`
- `0x180016b6c`
- `0x1800171a0`
- `0x180019900`
- `0x18001a898`
- `0x18001bbdc`
- `0x18001c630`
- `0x18001cf54`
- `0x18001d714`
- `0x18003e5c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001721d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001721d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800171d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800171d8`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
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
  _DWORD *v9; // rcx
  int v11; // eax
  unsigned int v12; // r8d
  __int64 v13; // [rsp+30h] [rbp-D0h] BYREF
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
    if ( Pointer >= 0 )
    {
      v9 = v15;
      if ( v15 )
      {
        *a2 = v15;
        ++*v9;
      }
      else
      {
        v11 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
        LastErrorFailHr = v11;
        if ( v11 < 0 )
        {
          wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v12, (const char *)(unsigned int)v11, 120);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v14);
          goto LABEL_8;
        }
      }
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v14);
      LastErrorFailHr = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v8, (const char *)(unsigned int)Pointer, 120);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v14);
    }
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
  }
LABEL_8:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v13);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x1800171a0  mov     [rsp-8+arg_10], rbx
0x1800171a5  mov     [rsp-8+arg_18], rdi
0x1800171aa  push    rbp
0x1800171ab  lea     rbp, [rsp-170h]
0x1800171b3  sub     rsp, 270h
0x1800171ba  mov     rax, cs:__security_cookie
0x1800171c1  xor     rax, rsp
0x1800171c4  mov     [rbp+170h+var_10], rax
0x1800171cb  mov     rdi, rdx
0x1800171ce  mov     rbx, rcx
0x1800171d1  mov     qword ptr [rdx], 0
0x1800171d8  call    cs:__imp_GetCurrentProcessId
0x1800171de  mov     r9d, eax
0x1800171e1  mov     [rsp+270h+var_248], rbx
0x1800171e6  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800171ee  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800171f5  mov     edx, 104h; unsigned __int64
0x1800171fa  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800171ff  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180017204  mov     [rsp+270h+var_240], 0
0x18001720d  mov     r9d, 1F0001h; dwDesiredAccess
0x180017213  xor     r8d, r8d; dwFlags
0x180017216  lea     rdx, [rsp+270h+Name]; lpName
0x18001721b  xor     ecx, ecx; lpMutexAttributes
0x18001721d  call    cs:__imp_CreateMutexExW
0x180017223  mov     rdx, rax
0x180017226  lea     rcx, [rsp+270h+var_240]
0x18001722b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180017230  cmp     [rsp+270h+var_240], 0
0x180017236  jnz     short loc_180017241
0x180017238  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001723d  mov     ebx, eax
0x18001723f  jmp     short loc_1800172B1
0x180017241  lea     rdx, [rsp+270h+var_238]
0x180017246  lea     rcx, [rsp+270h+var_240]
0x18001724b  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180017250  nop
0x180017251  mov     [rsp+270h+var_230], 0
0x18001725a  lea     rdx, [rsp+270h+var_230]; void **
0x18001725f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180017264  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180017269  mov     ebx, eax
0x18001726b  test    eax, eax
0x18001726d  jns     short loc_180017291
0x18001726f  mov     rcx, [rbp+178h]; this
0x180017276  mov     r9d, eax; char *
0x180017279  mov     edx, 12Eh; void *
0x18001727e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017283  nop
0x180017284  lea     rcx, [rsp+270h+var_238]
0x180017289  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001728e  nop
0x18001728f  jmp     short loc_1800172B1
0x180017291  mov     rcx, [rsp+270h+var_230]
0x180017296  test    rcx, rcx
0x180017299  jz      short loc_1800172E1
0x18001729b  mov     [rdi], rcx
0x18001729e  mov     eax, [rcx]
0x1800172a0  inc     eax
0x1800172a2  mov     [rcx], eax
0x1800172a4  lea     rcx, [rsp+270h+var_238]
0x1800172a9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800172ae  nop
0x1800172af  xor     ebx, ebx
0x1800172b1  lea     rcx, [rsp+270h+var_240]
0x1800172b6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800172bb  mov     eax, ebx
0x1800172bd  mov     rcx, [rbp+170h+var_10]
0x1800172c4  xor     rcx, rsp; StackCookie
0x1800172c7  call    __security_check_cookie
0x1800172cc  lea     r11, [rsp+270h+var_s0]
0x1800172d4  mov     rbx, [r11+20h]
0x1800172d8  mov     rdi, [r11+28h]
0x1800172dc  mov     rsp, r11
0x1800172df  pop     rbp
0x1800172e0  retn
0x1800172e1  mov     r8, rdi
0x1800172e4  lea     rdx, [rsp+270h+var_240]
0x1800172e9  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800172ee  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800172f3  mov     ebx, eax
0x1800172f5  test    eax, eax
0x1800172f7  jns     short loc_1800172A4
0x1800172f9  mov     rcx, [rbp+178h]; this
0x180017300  mov     r9d, eax; char *
0x180017303  mov     edx, 137h; void *
0x180017308  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001730d  nop
0x18001730e  lea     rcx, [rsp+270h+var_238]
0x180017313  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180017318  nop
0x180017319  jmp     short loc_1800172B1
```
