# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180032088`
- end: `0x1800321ee`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18003d570`

## callees

- `0x180012290`
- `0x180019afc`
- `0x18002d2d8`
- `0x180032088`
- `0x1800321f4`
- `0x180032360`
- `0x18003a730`
- `0x18003cc38`
- `0x18003d7dc`
- `0x18003e22c`
- `0x18003e3c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180032105`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180032105`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800320c0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800320c0`

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
0x180032088  mov     [rsp-8+arg_10], rbx
0x18003208d  mov     [rsp-8+arg_18], rdi
0x180032092  push    rbp
0x180032093  lea     rbp, [rsp-170h]
0x18003209b  sub     rsp, 270h
0x1800320a2  mov     rax, cs:__security_cookie
0x1800320a9  xor     rax, rsp
0x1800320ac  mov     [rbp+170h+var_10], rax
0x1800320b3  mov     rdi, rdx
0x1800320b6  mov     qword ptr [rdx], 0
0x1800320bd  mov     rbx, rcx
0x1800320c0  call    cs:__imp_GetCurrentProcessId
0x1800320c6  mov     [rsp+270h+var_248], rbx
0x1800320cb  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800320d2  mov     r9d, eax
0x1800320d5  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800320dd  mov     edx, 104h; unsigned __int64
0x1800320e2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800320e7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800320ec  mov     r9d, 1F0001h; dwDesiredAccess
0x1800320f2  mov     [rsp+270h+var_240], 0
0x1800320fb  xor     r8d, r8d; dwFlags
0x1800320fe  lea     rdx, [rsp+270h+Name]; lpName
0x180032103  xor     ecx, ecx; lpMutexAttributes
0x180032105  call    cs:__imp_CreateMutexExW
0x18003210b  mov     rdx, rax
0x18003210e  lea     rcx, [rsp+270h+var_240]
0x180032113  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180032118  cmp     [rsp+270h+var_240], 0
0x18003211e  jnz     short loc_180032129
0x180032120  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180032125  mov     ebx, eax
0x180032127  jmp     short loc_18003219C
0x180032129  lea     rdx, [rsp+270h+var_238]
0x18003212e  lea     rcx, [rsp+270h+var_240]
0x180032133  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180032138  lea     rdx, [rsp+270h+var_230]; void **
0x18003213d  mov     [rsp+270h+var_230], 0
0x180032146  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003214b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180032150  mov     ebx, eax
0x180032152  test    eax, eax
0x180032154  jns     short loc_18003217D
0x180032156  mov     edx, 12Eh; void *
0x18003215b  mov     rcx, [rbp+178h]; this
0x180032162  lea     r8, aWil; "wil"
0x180032169  mov     r9d, eax; char *
0x18003216c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032171  lea     rcx, [rsp+270h+var_238]
0x180032176  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003217b  jmp     short loc_18003219C
0x18003217d  mov     rcx, [rsp+270h+var_230]
0x180032182  test    rcx, rcx
0x180032185  jz      short loc_1800321CC
0x180032187  mov     [rdi], rcx
0x18003218a  mov     eax, [rcx]
0x18003218c  inc     eax
0x18003218e  mov     [rcx], eax
0x180032190  lea     rcx, [rsp+270h+var_238]
0x180032195  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003219a  xor     ebx, ebx
0x18003219c  lea     rcx, [rsp+270h+var_240]
0x1800321a1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800321a6  mov     eax, ebx
0x1800321a8  mov     rcx, [rbp+170h+var_10]
0x1800321af  xor     rcx, rsp; StackCookie
0x1800321b2  call    __security_check_cookie
0x1800321b7  lea     r11, [rsp+270h+var_s0]
0x1800321bf  mov     rbx, [r11+20h]
0x1800321c3  mov     rdi, [r11+28h]
0x1800321c7  mov     rsp, r11
0x1800321ca  pop     rbp
0x1800321cb  retn
0x1800321cc  mov     r8, rdi
0x1800321cf  lea     rdx, [rsp+270h+var_240]
0x1800321d4  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800321d9  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800321de  mov     ebx, eax
0x1800321e0  test    eax, eax
0x1800321e2  jns     short loc_180032190
0x1800321e4  mov     edx, 137h
0x1800321e9  jmp     loc_18003215B
```
