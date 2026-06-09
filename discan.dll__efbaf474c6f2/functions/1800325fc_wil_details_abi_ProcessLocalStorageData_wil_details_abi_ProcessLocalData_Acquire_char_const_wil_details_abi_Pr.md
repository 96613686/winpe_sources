# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800325fc`
- end: `0x18003275b`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800335f4`

## callees

- `0x18003233c`
- `0x180032358`
- `0x1800325fc`
- `0x1800332c8`
- `0x180033f2c`
- `0x180034ff4`
- `0x1800354d4`
- `0x180035ad0`
- `0x180036274`
- `0x18003654c`
- `0x180037620`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x180032679`
- `KERNEL32!CreateMutexExW` at `0x180032679`
- `KERNEL32!GetCurrentProcessId` at `0x180032634`
- `KERNEL32!GetCurrentProcessId` at `0x180032634`

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
0x1800325fc  mov     [rsp-8+arg_10], rbx
0x180032601  mov     [rsp-8+arg_18], rdi
0x180032606  push    rbp
0x180032607  lea     rbp, [rsp-170h]
0x18003260f  sub     rsp, 270h
0x180032616  mov     rax, cs:__security_cookie
0x18003261d  xor     rax, rsp
0x180032620  mov     [rbp+170h+var_10], rax
0x180032627  mov     rdi, rdx
0x18003262a  mov     qword ptr [rdx], 0
0x180032631  mov     rbx, rcx
0x180032634  call    cs:__imp_GetCurrentProcessId
0x18003263a  mov     [rsp+270h+var_248], rbx
0x18003263f  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180032646  mov     r9d, eax
0x180032649  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180032651  mov     edx, 104h; unsigned __int64
0x180032656  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003265b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180032660  mov     r9d, 1F0001h; dwDesiredAccess
0x180032666  mov     [rsp+270h+var_240], 0
0x18003266f  xor     r8d, r8d; dwFlags
0x180032672  lea     rdx, [rsp+270h+Name]; lpName
0x180032677  xor     ecx, ecx; lpMutexAttributes
0x180032679  call    cs:__imp_CreateMutexExW
0x18003267f  mov     rdx, rax
0x180032682  lea     rcx, [rsp+270h+var_240]
0x180032687  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18003268c  cmp     [rsp+270h+var_240], 0
0x180032692  jnz     short loc_18003269D
0x180032694  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180032699  mov     ebx, eax
0x18003269b  jmp     short loc_180032709
0x18003269d  lea     rdx, [rsp+270h+var_238]
0x1800326a2  lea     rcx, [rsp+270h+var_240]
0x1800326a7  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800326ac  lea     rdx, [rsp+270h+var_230]; void **
0x1800326b1  mov     [rsp+270h+var_230], 0
0x1800326ba  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800326bf  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800326c4  mov     ebx, eax
0x1800326c6  test    eax, eax
0x1800326c8  jns     short loc_1800326EA
0x1800326ca  mov     edx, 12Eh; void *
0x1800326cf  mov     rcx, [rbp+178h]; this
0x1800326d6  mov     r9d, eax; char *
0x1800326d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800326de  lea     rcx, [rsp+270h+var_238]
0x1800326e3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800326e8  jmp     short loc_180032709
0x1800326ea  mov     rcx, [rsp+270h+var_230]
0x1800326ef  test    rcx, rcx
0x1800326f2  jz      short loc_180032739
0x1800326f4  mov     [rdi], rcx
0x1800326f7  mov     eax, [rcx]
0x1800326f9  inc     eax
0x1800326fb  mov     [rcx], eax
0x1800326fd  lea     rcx, [rsp+270h+var_238]
0x180032702  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180032707  xor     ebx, ebx
0x180032709  lea     rcx, [rsp+270h+var_240]
0x18003270e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180032713  mov     eax, ebx
0x180032715  mov     rcx, [rbp+170h+var_10]
0x18003271c  xor     rcx, rsp; StackCookie
0x18003271f  call    __security_check_cookie
0x180032724  lea     r11, [rsp+270h+var_s0]
0x18003272c  mov     rbx, [r11+20h]
0x180032730  mov     rdi, [r11+28h]
0x180032734  mov     rsp, r11
0x180032737  pop     rbp
0x180032738  retn
0x180032739  mov     r8, rdi
0x18003273c  lea     rdx, [rsp+270h+var_240]
0x180032741  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180032746  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18003274b  mov     ebx, eax
0x18003274d  test    eax, eax
0x18003274f  jns     short loc_1800326FD
0x180032751  mov     edx, 137h
0x180032756  jmp     loc_1800326CF
```
