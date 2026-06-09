# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180076374`
- end: `0x1800764d3`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800776fc`

## callees

- `0x180075ff8`
- `0x180076014`
- `0x180076374`
- `0x180077528`
- `0x1800783a8`
- `0x180079cec`
- `0x18007a308`
- `0x18007a724`
- `0x18007af40`
- `0x18007b218`
- `0x180091140`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x1800763ac`
- `KERNEL32!GetCurrentProcessId` at `0x1800763ac`
- `KERNEL32!CreateMutexExW` at `0x1800763f1`
- `KERNEL32!CreateMutexExW` at `0x1800763f1`

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
0x180076374  mov     [rsp-8+arg_10], rbx
0x180076379  mov     [rsp-8+arg_18], rdi
0x18007637e  push    rbp
0x18007637f  lea     rbp, [rsp-170h]
0x180076387  sub     rsp, 270h
0x18007638e  mov     rax, cs:__security_cookie
0x180076395  xor     rax, rsp
0x180076398  mov     [rbp+170h+var_10], rax
0x18007639f  mov     rdi, rdx
0x1800763a2  mov     qword ptr [rdx], 0
0x1800763a9  mov     rbx, rcx
0x1800763ac  call    cs:__imp_GetCurrentProcessId
0x1800763b2  mov     [rsp+270h+var_248], rbx
0x1800763b7  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800763be  mov     r9d, eax
0x1800763c1  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800763c9  mov     edx, 104h; unsigned __int64
0x1800763ce  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800763d3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800763d8  mov     r9d, 1F0001h; dwDesiredAccess
0x1800763de  mov     [rsp+270h+var_240], 0
0x1800763e7  xor     r8d, r8d; dwFlags
0x1800763ea  lea     rdx, [rsp+270h+Name]; lpName
0x1800763ef  xor     ecx, ecx; lpMutexAttributes
0x1800763f1  call    cs:__imp_CreateMutexExW
0x1800763f7  mov     rdx, rax
0x1800763fa  lea     rcx, [rsp+270h+var_240]
0x1800763ff  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180076404  cmp     [rsp+270h+var_240], 0
0x18007640a  jnz     short loc_180076415
0x18007640c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180076411  mov     ebx, eax
0x180076413  jmp     short loc_180076481
0x180076415  lea     rdx, [rsp+270h+var_238]
0x18007641a  lea     rcx, [rsp+270h+var_240]
0x18007641f  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180076424  lea     rdx, [rsp+270h+var_230]; void **
0x180076429  mov     [rsp+270h+var_230], 0
0x180076432  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180076437  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18007643c  mov     ebx, eax
0x18007643e  test    eax, eax
0x180076440  jns     short loc_180076462
0x180076442  mov     edx, 12Eh; void *
0x180076447  mov     rcx, [rbp+178h]; this
0x18007644e  mov     r9d, eax; char *
0x180076451  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180076456  lea     rcx, [rsp+270h+var_238]
0x18007645b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180076460  jmp     short loc_180076481
0x180076462  mov     rcx, [rsp+270h+var_230]
0x180076467  test    rcx, rcx
0x18007646a  jz      short loc_1800764B1
0x18007646c  mov     [rdi], rcx
0x18007646f  mov     eax, [rcx]
0x180076471  inc     eax
0x180076473  mov     [rcx], eax
0x180076475  lea     rcx, [rsp+270h+var_238]
0x18007647a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18007647f  xor     ebx, ebx
0x180076481  lea     rcx, [rsp+270h+var_240]
0x180076486  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18007648b  mov     eax, ebx
0x18007648d  mov     rcx, [rbp+170h+var_10]
0x180076494  xor     rcx, rsp; StackCookie
0x180076497  call    __security_check_cookie
0x18007649c  lea     r11, [rsp+270h+var_s0]
0x1800764a4  mov     rbx, [r11+20h]
0x1800764a8  mov     rdi, [r11+28h]
0x1800764ac  mov     rsp, r11
0x1800764af  pop     rbp
0x1800764b0  retn
0x1800764b1  mov     r8, rdi
0x1800764b4  lea     rdx, [rsp+270h+var_240]
0x1800764b9  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800764be  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800764c3  mov     ebx, eax
0x1800764c5  test    eax, eax
0x1800764c7  jns     short loc_180076475
0x1800764c9  mov     edx, 137h
0x1800764ce  jmp     loc_180076447
```
