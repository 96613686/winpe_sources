# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800542b4`
- end: `0x180054420`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `364`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18005a7b8`

## callees

- `0x180043a38`
- `0x180043cc0`
- `0x180043d14`
- `0x180044240`
- `0x1800519d8`
- `0x1800532d0`
- `0x180053a9c`
- `0x180053d50`
- `0x1800542b4`
- `0x180054428`
- `0x1800966e0`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x180054337`
- `KERNEL32!CreateMutexExW` at `0x180054337`
- `KERNEL32!GetCurrentProcessId` at `0x1800542ec`
- `KERNEL32!GetCurrentProcessId` at `0x1800542ec`

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
0x1800542b4  mov     [rsp-8+arg_10], rbx
0x1800542b9  mov     [rsp-8+arg_18], rdi
0x1800542be  push    rbp
0x1800542bf  lea     rbp, [rsp-170h]
0x1800542c7  sub     rsp, 270h
0x1800542ce  mov     rax, cs:__security_cookie
0x1800542d5  xor     rax, rsp
0x1800542d8  mov     [rbp+170h+var_10], rax
0x1800542df  mov     rdi, rdx
0x1800542e2  mov     qword ptr [rdx], 0
0x1800542e9  mov     rbx, rcx
0x1800542ec  call    cs:__imp_GetCurrentProcessId
0x1800542f3  nop     dword ptr [rax+rax+00h]
0x1800542f8  mov     [rsp+270h+var_248], rbx
0x1800542fd  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180054304  mov     r9d, eax
0x180054307  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18005430f  mov     edx, 104h; unsigned __int64
0x180054314  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180054319  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005431e  mov     r9d, 1F0001h; dwDesiredAccess
0x180054324  mov     [rsp+270h+var_240], 0
0x18005432d  xor     r8d, r8d; dwFlags
0x180054330  lea     rdx, [rsp+270h+Name]; lpName
0x180054335  xor     ecx, ecx; lpMutexAttributes
0x180054337  call    cs:__imp_CreateMutexExW
0x18005433e  nop     dword ptr [rax+rax+00h]
0x180054343  mov     rdx, rax
0x180054346  lea     rcx, [rsp+270h+var_240]
0x18005434b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180054350  cmp     [rsp+270h+var_240], 0
0x180054356  jnz     short loc_180054361
0x180054358  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18005435d  mov     ebx, eax
0x18005435f  jmp     short loc_1800543CD
0x180054361  lea     rdx, [rsp+270h+var_238]
0x180054366  lea     rcx, [rsp+270h+var_240]
0x18005436b  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180054370  lea     rdx, [rsp+270h+var_230]; void **
0x180054375  mov     [rsp+270h+var_230], 0
0x18005437e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180054383  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180054388  mov     ebx, eax
0x18005438a  test    eax, eax
0x18005438c  jns     short loc_1800543AE
0x18005438e  mov     edx, 12Eh; void *
0x180054393  mov     rcx, [rbp+178h]; this
0x18005439a  mov     r9d, eax; char *
0x18005439d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800543a2  lea     rcx, [rsp+270h+var_238]
0x1800543a7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800543ac  jmp     short loc_1800543CD
0x1800543ae  mov     rcx, [rsp+270h+var_230]
0x1800543b3  test    rcx, rcx
0x1800543b6  jz      short loc_1800543FE
0x1800543b8  mov     [rdi], rcx
0x1800543bb  mov     eax, [rcx]
0x1800543bd  inc     eax
0x1800543bf  mov     [rcx], eax
0x1800543c1  lea     rcx, [rsp+270h+var_238]
0x1800543c6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800543cb  xor     ebx, ebx
0x1800543cd  lea     rcx, [rsp+270h+var_240]
0x1800543d2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800543d7  mov     eax, ebx
0x1800543d9  mov     rcx, [rbp+170h+var_10]
0x1800543e0  xor     rcx, rsp; StackCookie
0x1800543e3  call    __security_check_cookie
0x1800543e8  lea     r11, [rsp+270h+var_s0]
0x1800543f0  mov     rbx, [r11+20h]
0x1800543f4  mov     rdi, [r11+28h]
0x1800543f8  mov     rsp, r11
0x1800543fb  pop     rbp
0x1800543fc  retn
0x1800543fe  mov     r8, rdi
0x180054401  lea     rdx, [rsp+270h+var_240]
0x180054406  lea     rcx, [rsp+270h+Name]
0x18005440b  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180054410  mov     ebx, eax
0x180054412  test    eax, eax
0x180054414  jns     short loc_1800543C1
0x180054416  mov     edx, 137h
0x18005441b  jmp     loc_180054393
```
