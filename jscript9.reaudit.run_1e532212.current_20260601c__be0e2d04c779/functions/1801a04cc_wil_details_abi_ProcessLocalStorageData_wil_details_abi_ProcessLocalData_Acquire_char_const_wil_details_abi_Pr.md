# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1801a04cc`
- end: `0x1801a0660`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `404`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1801cc598`

## callees

- `0x1801a04cc`
- `0x1801a0688`
- `0x1801a06b0`
- `0x1801a06e4`
- `0x1801a071c`
- `0x1801a3c60`
- `0x1801a3d4c`
- `0x1801ae624`
- `0x1801b3ac0`
- `0x1801cd094`
- `0x180341dd0`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x1801a051d`
- `KERNEL32!GetCurrentProcessId` at `0x1801a051d`
- `KERNEL32!CreateMutexExW` at `0x1801a0562`
- `KERNEL32!CreateMutexExW` at `0x1801a0562`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v6; // rcx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  __int64 v9; // rdx
  _DWORD *v10; // rcx
  int bAlertable; // [rsp+28h] [rbp-E0h]
  __int64 v13; // [rsp+38h] [rbp-D0h] BYREF
  int v14[2]; // [rsp+40h] [rbp-C8h] BYREF
  void *v15[2]; // [rsp+48h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+58h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+280h] [rbp+178h]

  v15[1] = (void *)-2LL;
  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId, 120, a1);
  v13 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v13,
    Mutex);
  if ( v13 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      (int)&v13,
      (int)v14,
      0,
      -1,
      0);
    v15[0] = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, v15);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v9 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"wil",
        (const char *)(unsigned int)Pointer,
        bAlertable);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v14);
      goto LABEL_9;
    }
    v10 = v15[0];
    if ( v15[0] )
    {
      *a2 = v15[0];
      ++*v10;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(
                  Name,
                  &v13,
                  a2);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v9 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v14);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v6);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v13);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x1801a04cc  mov     rax, rsp
0x1801a04cf  mov     [rax+10h], rdx
0x1801a04d3  mov     [rax+8], rcx
0x1801a04d7  push    rbp
0x1801a04d8  lea     rbp, [rax-178h]
0x1801a04df  sub     rsp, 270h
0x1801a04e6  mov     qword ptr [rsp+270h+var_228], 0FFFFFFFFFFFFFFFEh
0x1801a04ef  mov     [rax+18h], rbx
0x1801a04f3  mov     [rax+20h], rdi
0x1801a04f7  mov     rax, cs:__security_cookie
0x1801a04fe  xor     rax, rsp
0x1801a0501  mov     [rbp+170h+var_10], rax
0x1801a0508  mov     rbx, [rbp+170h+arg_0]
0x1801a050f  mov     rdi, [rbp+170h+arg_8]
0x1801a0516  mov     qword ptr [rdi], 0
0x1801a051d  call    cs:__imp_GetCurrentProcessId
0x1801a0523  mov     r9d, eax
0x1801a0526  mov     [rsp+270h+var_248], rbx
0x1801a052b  mov     [rsp+270h+bAlertable], 78h ; 'x'
0x1801a0533  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1801a053a  mov     edx, 104h; unsigned __int64
0x1801a053f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1801a0544  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801a0549  mov     [rsp+270h+var_240], 0
0x1801a0552  mov     r9d, 1F0001h; dwDesiredAccess
0x1801a0558  xor     r8d, r8d; dwFlags
0x1801a055b  lea     rdx, [rsp+270h+Name]; lpName
0x1801a0560  xor     ecx, ecx; lpMutexAttributes
0x1801a0562  call    cs:__imp_CreateMutexExW
0x1801a0568  mov     rdx, rax
0x1801a056b  lea     rcx, [rsp+270h+var_240]
0x1801a0570  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1801a0575  cmp     [rsp+270h+var_240], 0
0x1801a057b  jnz     short loc_1801A0589
0x1801a057d  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1801a0582  mov     ebx, eax
0x1801a0584  jmp     loc_1801A060D
0x1801a0589  mov     [rsp+270h+bAlertable], 0; int
0x1801a0591  or      r9d, 0FFFFFFFFh; int
0x1801a0595  xor     r8d, r8d; int
0x1801a0598  lea     rdx, [rsp+270h+var_238]; int
0x1801a059d  lea     rcx, [rsp+270h+var_240]; int
0x1801a05a2  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1801a05a7  nop
0x1801a05a8  mov     [rsp+270h+var_230], 0
0x1801a05b1  lea     rdx, [rsp+270h+var_230]; void **
0x1801a05b6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1801a05bb  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1801a05c0  mov     ebx, eax
0x1801a05c2  test    eax, eax
0x1801a05c4  jns     short loc_1801A05EE
0x1801a05c6  mov     edx, 12Eh; void *
0x1801a05cb  lea     r8, aWil; "wil"
0x1801a05d2  mov     r9d, eax; char *
0x1801a05d5  mov     rcx, [rbp+178h]; this
0x1801a05dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a05e1  nop
0x1801a05e2  lea     rcx, [rsp+270h+var_238]
0x1801a05e7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801a05ec  jmp     short loc_1801A060D
0x1801a05ee  mov     rcx, [rsp+270h+var_230]
0x1801a05f3  test    rcx, rcx
0x1801a05f6  jz      short loc_1801A063D
0x1801a05f8  mov     [rdi], rcx
0x1801a05fb  mov     eax, [rcx]
0x1801a05fd  inc     eax
0x1801a05ff  mov     [rcx], eax
0x1801a0601  lea     rcx, [rsp+270h+var_238]
0x1801a0606  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801a060b  xor     ebx, ebx
0x1801a060d  lea     rcx, [rsp+270h+var_240]
0x1801a0612  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801a0617  mov     eax, ebx
0x1801a0619  mov     rcx, [rbp+170h+var_10]
0x1801a0620  xor     rcx, rsp; StackCookie
0x1801a0623  call    __security_check_cookie
0x1801a0628  lea     r11, [rsp+270h+var_s0]
0x1801a0630  mov     rbx, [r11+20h]
0x1801a0634  mov     rdi, [r11+28h]
0x1801a0638  mov     rsp, r11
0x1801a063b  pop     rbp
0x1801a063c  retn
0x1801a063d  mov     r8, rdi
0x1801a0640  lea     rdx, [rsp+270h+var_240]
0x1801a0645  lea     rcx, [rsp+270h+Name]
0x1801a064a  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1801a064f  mov     ebx, eax
0x1801a0651  test    eax, eax
0x1801a0653  jns     short loc_1801A0601
0x1801a0655  mov     edx, 137h
0x1801a065a  jmp     loc_1801A05CB
```
