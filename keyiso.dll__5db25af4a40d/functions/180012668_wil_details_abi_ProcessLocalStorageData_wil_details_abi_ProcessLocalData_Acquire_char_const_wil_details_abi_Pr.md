# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180012668`
- end: `0x1800127ca`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `354`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800137f0`

## callees

- `0x18000bbf0`
- `0x180012390`
- `0x1800123ac`
- `0x180012668`
- `0x18001420c`
- `0x18001539c`
- `0x180015ad8`
- `0x180015f58`
- `0x180016780`
- `0x18001690c`
- `0x180018950`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800126e5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800126e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800126a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800126a0`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rdx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  void *v9; // rdx
  unsigned int v10; // r8d
  __int64 v11; // rdx
  void *v12; // rdx
  _DWORD *v13; // rcx
  wil::details *v15; // [rsp+30h] [rbp-D0h] BYREF
  wil::details *v16; // [rsp+38h] [rbp-C8h] BYREF
  void *v17; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v15 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v15,
    Mutex);
  if ( v15 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      (HANDLE *)&v15,
      &v16);
    v17 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v17);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v11 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v11, v10, (const char *)(unsigned int)Pointer, 120);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
        &v16,
        v12);
      goto LABEL_9;
    }
    v13 = v17;
    if ( v17 )
    {
      *a2 = v17;
      ++*v13;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v11 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v16,
      v9);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v15,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180012668  mov     [rsp-8+arg_10], rbx
0x18001266d  mov     [rsp-8+arg_18], rdi
0x180012672  push    rbp
0x180012673  lea     rbp, [rsp-170h]
0x18001267b  sub     rsp, 270h
0x180012682  mov     rax, cs:__security_cookie
0x180012689  xor     rax, rsp
0x18001268c  mov     [rbp+170h+var_10], rax
0x180012693  mov     rdi, rdx
0x180012696  mov     rbx, rcx
0x180012699  mov     qword ptr [rdx], 0
0x1800126a0  call    cs:__imp_GetCurrentProcessId
0x1800126a6  mov     r9d, eax
0x1800126a9  mov     [rsp+270h+var_248], rbx
0x1800126ae  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800126b6  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800126bd  mov     edx, 104h; unsigned __int64
0x1800126c2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800126c7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800126cc  mov     [rsp+270h+var_240], 0
0x1800126d5  mov     r9d, 1F0001h; dwDesiredAccess
0x1800126db  xor     r8d, r8d; dwFlags
0x1800126de  lea     rdx, [rsp+270h+Name]; lpName
0x1800126e3  xor     ecx, ecx; lpMutexAttributes
0x1800126e5  call    cs:__imp_CreateMutexExW
0x1800126eb  mov     rdx, rax
0x1800126ee  lea     rcx, [rsp+270h+var_240]
0x1800126f3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800126f8  cmp     [rsp+270h+var_240], 0
0x1800126fe  jnz     short loc_180012709
0x180012700  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180012705  mov     ebx, eax
0x180012707  jmp     short loc_180012777
0x180012709  lea     rdx, [rsp+270h+var_238]
0x18001270e  lea     rcx, [rsp+270h+var_240]
0x180012713  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180012718  nop
0x180012719  mov     [rsp+270h+var_230], 0
0x180012722  lea     rdx, [rsp+270h+var_230]; void **
0x180012727  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001272c  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180012731  mov     ebx, eax
0x180012733  test    eax, eax
0x180012735  jns     short loc_180012758
0x180012737  mov     edx, 12Eh; void *
0x18001273c  mov     r9d, eax; char *
0x18001273f  mov     rcx, [rbp+178h]; this
0x180012746  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001274b  nop
0x18001274c  lea     rcx, [rsp+270h+var_238]
0x180012751  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180012756  jmp     short loc_180012777
0x180012758  mov     rcx, [rsp+270h+var_230]
0x18001275d  test    rcx, rcx
0x180012760  jz      short loc_1800127A7
0x180012762  mov     [rdi], rcx
0x180012765  mov     eax, [rcx]
0x180012767  inc     eax
0x180012769  mov     [rcx], eax
0x18001276b  lea     rcx, [rsp+270h+var_238]
0x180012770  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180012775  xor     ebx, ebx
0x180012777  lea     rcx, [rsp+270h+var_240]
0x18001277c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180012781  mov     eax, ebx
0x180012783  mov     rcx, [rbp+170h+var_10]
0x18001278a  xor     rcx, rsp; StackCookie
0x18001278d  call    __security_check_cookie
0x180012792  lea     r11, [rsp+270h+var_s0]
0x18001279a  mov     rbx, [r11+20h]
0x18001279e  mov     rdi, [r11+28h]
0x1800127a2  mov     rsp, r11
0x1800127a5  pop     rbp
0x1800127a6  retn
0x1800127a7  mov     r8, rdi
0x1800127aa  lea     rdx, [rsp+270h+var_240]
0x1800127af  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800127b4  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800127b9  mov     ebx, eax
0x1800127bb  test    eax, eax
0x1800127bd  jns     short loc_18001276B
0x1800127bf  mov     edx, 137h
0x1800127c4  jmp     loc_18001273C
```
