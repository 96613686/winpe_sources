# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180078418`
- end: `0x180078584`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `364`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180079950`

## callees

- `0x180078090`
- `0x1800780b0`
- `0x180078418`
- `0x180079760`
- `0x18007a6cc`
- `0x18007c104`
- `0x18007c744`
- `0x18007ca74`
- `0x18007d2f0`
- `0x18007d554`
- `0x180093c00`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180078450`
- `KERNEL32!GetCurrentProcessId` at `0x180078450`
- `KERNEL32!CreateMutexExW` at `0x18007849b`
- `KERNEL32!CreateMutexExW` at `0x18007849b`

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
0x180078418  mov     [rsp-8+arg_10], rbx
0x18007841d  mov     [rsp-8+arg_18], rdi
0x180078422  push    rbp
0x180078423  lea     rbp, [rsp-170h]
0x18007842b  sub     rsp, 270h
0x180078432  mov     rax, cs:__security_cookie
0x180078439  xor     rax, rsp
0x18007843c  mov     [rbp+170h+var_10], rax
0x180078443  mov     rdi, rdx
0x180078446  mov     qword ptr [rdx], 0
0x18007844d  mov     rbx, rcx
0x180078450  call    cs:__imp_GetCurrentProcessId
0x180078457  nop     dword ptr [rax+rax+00h]
0x18007845c  mov     [rsp+270h+var_248], rbx
0x180078461  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180078468  mov     r9d, eax
0x18007846b  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180078473  mov     edx, 104h; unsigned __int64
0x180078478  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18007847d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180078482  mov     r9d, 1F0001h; dwDesiredAccess
0x180078488  mov     [rsp+270h+var_240], 0
0x180078491  xor     r8d, r8d; dwFlags
0x180078494  lea     rdx, [rsp+270h+Name]; lpName
0x180078499  xor     ecx, ecx; lpMutexAttributes
0x18007849b  call    cs:__imp_CreateMutexExW
0x1800784a2  nop     dword ptr [rax+rax+00h]
0x1800784a7  mov     rdx, rax
0x1800784aa  lea     rcx, [rsp+270h+var_240]
0x1800784af  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800784b4  cmp     [rsp+270h+var_240], 0
0x1800784ba  jnz     short loc_1800784C5
0x1800784bc  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800784c1  mov     ebx, eax
0x1800784c3  jmp     short loc_180078531
0x1800784c5  lea     rdx, [rsp+270h+var_238]
0x1800784ca  lea     rcx, [rsp+270h+var_240]
0x1800784cf  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800784d4  lea     rdx, [rsp+270h+var_230]; void **
0x1800784d9  mov     [rsp+270h+var_230], 0
0x1800784e2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800784e7  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800784ec  mov     ebx, eax
0x1800784ee  test    eax, eax
0x1800784f0  jns     short loc_180078512
0x1800784f2  mov     edx, 12Eh; void *
0x1800784f7  mov     rcx, [rbp+178h]; this
0x1800784fe  mov     r9d, eax; char *
0x180078501  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180078506  lea     rcx, [rsp+270h+var_238]
0x18007850b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180078510  jmp     short loc_180078531
0x180078512  mov     rcx, [rsp+270h+var_230]
0x180078517  test    rcx, rcx
0x18007851a  jz      short loc_180078562
0x18007851c  mov     [rdi], rcx
0x18007851f  mov     eax, [rcx]
0x180078521  inc     eax
0x180078523  mov     [rcx], eax
0x180078525  lea     rcx, [rsp+270h+var_238]
0x18007852a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18007852f  xor     ebx, ebx
0x180078531  lea     rcx, [rsp+270h+var_240]
0x180078536  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18007853b  mov     eax, ebx
0x18007853d  mov     rcx, [rbp+170h+var_10]
0x180078544  xor     rcx, rsp; StackCookie
0x180078547  call    __security_check_cookie
0x18007854c  lea     r11, [rsp+270h+var_s0]
0x180078554  mov     rbx, [r11+20h]
0x180078558  mov     rdi, [r11+28h]
0x18007855c  mov     rsp, r11
0x18007855f  pop     rbp
0x180078560  retn
0x180078562  mov     r8, rdi
0x180078565  lea     rdx, [rsp+270h+var_240]
0x18007856a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18007856f  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180078574  mov     ebx, eax
0x180078576  test    eax, eax
0x180078578  jns     short loc_180078525
0x18007857a  mov     edx, 137h
0x18007857f  jmp     loc_1800784F7
```
