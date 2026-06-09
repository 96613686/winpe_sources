# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140005730`
- end: `0x140005896`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140006cc0`

## callees

- `0x140005154`
- `0x140005170`
- `0x140005730`
- `0x1400068d8`
- `0x1400077fc`
- `0x14000966c`
- `0x140009f28`
- `0x14000a6f8`
- `0x14000b2f4`
- `0x14000c9cc`
- `0x140025d70`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x1400057ad`
- `KERNEL32!CreateMutexExW` at `0x1400057ad`
- `KERNEL32!GetCurrentProcessId` at `0x140005768`
- `KERNEL32!GetCurrentProcessId` at `0x140005768`

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
0x140005730  mov     [rsp-8+arg_10], rbx
0x140005735  mov     [rsp-8+arg_18], rdi
0x14000573a  push    rbp
0x14000573b  lea     rbp, [rsp-170h]
0x140005743  sub     rsp, 270h
0x14000574a  mov     rax, cs:__security_cookie
0x140005751  xor     rax, rsp
0x140005754  mov     [rbp+170h+var_10], rax
0x14000575b  mov     rdi, rdx
0x14000575e  mov     qword ptr [rdx], 0
0x140005765  mov     rbx, rcx
0x140005768  call    cs:__imp_GetCurrentProcessId
0x14000576e  mov     [rsp+270h+var_248], rbx
0x140005773  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x14000577a  mov     r9d, eax
0x14000577d  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x140005785  mov     edx, 104h; unsigned __int64
0x14000578a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x14000578f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140005794  mov     r9d, 1F0001h; dwDesiredAccess
0x14000579a  mov     [rsp+270h+var_240], 0
0x1400057a3  xor     r8d, r8d; dwFlags
0x1400057a6  lea     rdx, [rsp+270h+Name]; lpName
0x1400057ab  xor     ecx, ecx; lpMutexAttributes
0x1400057ad  call    cs:__imp_CreateMutexExW
0x1400057b3  mov     rdx, rax
0x1400057b6  lea     rcx, [rsp+270h+var_240]
0x1400057bb  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1400057c0  cmp     [rsp+270h+var_240], 0
0x1400057c6  jnz     short loc_1400057D1
0x1400057c8  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1400057cd  mov     ebx, eax
0x1400057cf  jmp     short loc_140005844
0x1400057d1  lea     rdx, [rsp+270h+var_238]
0x1400057d6  lea     rcx, [rsp+270h+var_240]
0x1400057db  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1400057e0  lea     rdx, [rsp+270h+var_230]; void **
0x1400057e5  mov     [rsp+270h+var_230], 0
0x1400057ee  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1400057f3  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1400057f8  mov     ebx, eax
0x1400057fa  test    eax, eax
0x1400057fc  jns     short loc_140005825
0x1400057fe  mov     edx, 12Eh; void *
0x140005803  mov     rcx, [rbp+178h]; this
0x14000580a  lea     r8, aWil; "wil"
0x140005811  mov     r9d, eax; char *
0x140005814  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005819  lea     rcx, [rsp+270h+var_238]
0x14000581e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140005823  jmp     short loc_140005844
0x140005825  mov     rcx, [rsp+270h+var_230]
0x14000582a  test    rcx, rcx
0x14000582d  jz      short loc_140005874
0x14000582f  mov     [rdi], rcx
0x140005832  mov     eax, [rcx]
0x140005834  inc     eax
0x140005836  mov     [rcx], eax
0x140005838  lea     rcx, [rsp+270h+var_238]
0x14000583d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140005842  xor     ebx, ebx
0x140005844  lea     rcx, [rsp+270h+var_240]
0x140005849  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000584e  mov     eax, ebx
0x140005850  mov     rcx, [rbp+170h+var_10]
0x140005857  xor     rcx, rsp; StackCookie
0x14000585a  call    __security_check_cookie
0x14000585f  lea     r11, [rsp+270h+var_s0]
0x140005867  mov     rbx, [r11+20h]
0x14000586b  mov     rdi, [r11+28h]
0x14000586f  mov     rsp, r11
0x140005872  pop     rbp
0x140005873  retn
0x140005874  mov     r8, rdi
0x140005877  lea     rdx, [rsp+270h+var_240]
0x14000587c  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140005881  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x140005886  mov     ebx, eax
0x140005888  test    eax, eax
0x14000588a  jns     short loc_140005838
0x14000588c  mov     edx, 137h
0x140005891  jmp     loc_140005803
```
