# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140078088`
- end: `0x1400781e7`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1400790a4`

## callees

- `0x140074f78`
- `0x140075228`
- `0x140075de0`
- `0x140077da4`
- `0x140077dc0`
- `0x140078088`
- `0x140078d78`
- `0x14007ad48`
- `0x14007afe8`
- `0x14007b7d4`
- `0x14007b9fc`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x1400780c0`
- `KERNEL32!GetCurrentProcessId` at `0x1400780c0`
- `KERNEL32!CreateMutexExW` at `0x140078105`
- `KERNEL32!CreateMutexExW` at `0x140078105`

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
0x140078088  mov     [rsp-8+arg_10], rbx
0x14007808d  mov     [rsp-8+arg_18], rdi
0x140078092  push    rbp
0x140078093  lea     rbp, [rsp-170h]
0x14007809b  sub     rsp, 270h
0x1400780a2  mov     rax, cs:__security_cookie
0x1400780a9  xor     rax, rsp
0x1400780ac  mov     [rbp+170h+var_10], rax
0x1400780b3  mov     rdi, rdx
0x1400780b6  mov     qword ptr [rdx], 0
0x1400780bd  mov     rbx, rcx
0x1400780c0  call    cs:__imp_GetCurrentProcessId
0x1400780c6  mov     [rsp+270h+var_248], rbx
0x1400780cb  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1400780d2  mov     r9d, eax
0x1400780d5  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1400780dd  mov     edx, 104h; unsigned __int64
0x1400780e2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1400780e7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400780ec  mov     r9d, 1F0001h; dwDesiredAccess
0x1400780f2  mov     [rsp+270h+var_240], 0
0x1400780fb  xor     r8d, r8d; dwFlags
0x1400780fe  lea     rdx, [rsp+270h+Name]; lpName
0x140078103  xor     ecx, ecx; lpMutexAttributes
0x140078105  call    cs:__imp_CreateMutexExW
0x14007810b  mov     rdx, rax
0x14007810e  lea     rcx, [rsp+270h+var_240]
0x140078113  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140078118  cmp     [rsp+270h+var_240], 0
0x14007811e  jnz     short loc_140078129
0x140078120  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140078125  mov     ebx, eax
0x140078127  jmp     short loc_140078195
0x140078129  lea     rdx, [rsp+270h+var_238]
0x14007812e  lea     rcx, [rsp+270h+var_240]
0x140078133  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x140078138  lea     rdx, [rsp+270h+var_230]; void **
0x14007813d  mov     [rsp+270h+var_230], 0
0x140078146  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x14007814b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x140078150  mov     ebx, eax
0x140078152  test    eax, eax
0x140078154  jns     short loc_140078176
0x140078156  mov     edx, 12Eh; void *
0x14007815b  mov     rcx, [rbp+178h]; this
0x140078162  mov     r9d, eax; char *
0x140078165  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14007816a  lea     rcx, [rsp+270h+var_238]
0x14007816f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140078174  jmp     short loc_140078195
0x140078176  mov     rcx, [rsp+270h+var_230]
0x14007817b  test    rcx, rcx
0x14007817e  jz      short loc_1400781C5
0x140078180  mov     [rdi], rcx
0x140078183  mov     eax, [rcx]
0x140078185  inc     eax
0x140078187  mov     [rcx], eax
0x140078189  lea     rcx, [rsp+270h+var_238]
0x14007818e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140078193  xor     ebx, ebx
0x140078195  lea     rcx, [rsp+270h+var_240]
0x14007819a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14007819f  mov     eax, ebx
0x1400781a1  mov     rcx, [rbp+170h+var_10]
0x1400781a8  xor     rcx, rsp; StackCookie
0x1400781ab  call    __security_check_cookie
0x1400781b0  lea     r11, [rsp+270h+var_s0]
0x1400781b8  mov     rbx, [r11+20h]
0x1400781bc  mov     rdi, [r11+28h]
0x1400781c0  mov     rsp, r11
0x1400781c3  pop     rbp
0x1400781c4  retn
0x1400781c5  mov     r8, rdi
0x1400781c8  lea     rdx, [rsp+270h+var_240]
0x1400781cd  lea     rcx, [rsp+270h+Name]
0x1400781d2  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1400781d7  mov     ebx, eax
0x1400781d9  test    eax, eax
0x1400781db  jns     short loc_140078189
0x1400781dd  mov     edx, 137h
0x1400781e2  jmp     loc_14007815B
```
