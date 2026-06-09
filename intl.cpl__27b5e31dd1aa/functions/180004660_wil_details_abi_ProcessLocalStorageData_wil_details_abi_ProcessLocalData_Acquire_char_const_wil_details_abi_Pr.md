# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180004660`
- end: `0x1800047bf`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800051b0`

## callees

- `0x180004538`
- `0x180004554`
- `0x180004660`
- `0x180004ec8`
- `0x1800058d8`
- `0x180005cc4`
- `0x1800062b0`
- `0x180006470`
- `0x180006af8`
- `0x180007030`
- `0x18002a150`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800046dd`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800046dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004698`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004698`

## pseudocode

```c
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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 120);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
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
0x180004660  mov     [rsp-8+arg_10], rbx
0x180004665  mov     [rsp-8+arg_18], rdi
0x18000466a  push    rbp
0x18000466b  lea     rbp, [rsp-170h]
0x180004673  sub     rsp, 270h
0x18000467a  mov     rax, cs:__security_cookie
0x180004681  xor     rax, rsp
0x180004684  mov     [rbp+170h+var_10], rax
0x18000468b  mov     rdi, rdx
0x18000468e  mov     qword ptr [rdx], 0
0x180004695  mov     rbx, rcx
0x180004698  call    cs:__imp_GetCurrentProcessId
0x18000469e  mov     [rsp+270h+var_248], rbx
0x1800046a3  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800046aa  mov     r9d, eax
0x1800046ad  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800046b5  mov     edx, 104h; unsigned __int64
0x1800046ba  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800046bf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800046c4  mov     r9d, 1F0001h; dwDesiredAccess
0x1800046ca  mov     [rsp+270h+var_240], 0
0x1800046d3  xor     r8d, r8d; dwFlags
0x1800046d6  lea     rdx, [rsp+270h+Name]; lpName
0x1800046db  xor     ecx, ecx; lpMutexAttributes
0x1800046dd  call    cs:__imp_CreateMutexExW
0x1800046e3  mov     rdx, rax
0x1800046e6  lea     rcx, [rsp+270h+var_240]
0x1800046eb  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800046f0  cmp     [rsp+270h+var_240], 0
0x1800046f6  jnz     short loc_180004701
0x1800046f8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800046fd  mov     ebx, eax
0x1800046ff  jmp     short loc_18000476D
0x180004701  lea     rdx, [rsp+270h+var_238]
0x180004706  lea     rcx, [rsp+270h+var_240]
0x18000470b  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180004710  lea     rdx, [rsp+270h+var_230]; void **
0x180004715  mov     [rsp+270h+var_230], 0
0x18000471e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180004723  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180004728  mov     ebx, eax
0x18000472a  test    eax, eax
0x18000472c  jns     short loc_18000474E
0x18000472e  mov     edx, 12Eh; void *
0x180004733  mov     rcx, [rbp+178h]; this
0x18000473a  mov     r9d, eax; char *
0x18000473d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004742  lea     rcx, [rsp+270h+var_238]
0x180004747  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000474c  jmp     short loc_18000476D
0x18000474e  mov     rcx, [rsp+270h+var_230]
0x180004753  test    rcx, rcx
0x180004756  jz      short loc_18000479D
0x180004758  mov     [rdi], rcx
0x18000475b  mov     eax, [rcx]
0x18000475d  inc     eax
0x18000475f  mov     [rcx], eax
0x180004761  lea     rcx, [rsp+270h+var_238]
0x180004766  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000476b  xor     ebx, ebx
0x18000476d  lea     rcx, [rsp+270h+var_240]
0x180004772  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180004777  mov     eax, ebx
0x180004779  mov     rcx, [rbp+170h+var_10]
0x180004780  xor     rcx, rsp; StackCookie
0x180004783  call    __security_check_cookie
0x180004788  lea     r11, [rsp+270h+var_s0]
0x180004790  mov     rbx, [r11+20h]
0x180004794  mov     rdi, [r11+28h]
0x180004798  mov     rsp, r11
0x18000479b  pop     rbp
0x18000479c  retn
0x18000479d  mov     r8, rdi
0x1800047a0  lea     rdx, [rsp+270h+var_240]
0x1800047a5  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800047aa  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800047af  mov     ebx, eax
0x1800047b1  test    eax, eax
0x1800047b3  jns     short loc_180004761
0x1800047b5  mov     edx, 137h
0x1800047ba  jmp     loc_180004733
```
