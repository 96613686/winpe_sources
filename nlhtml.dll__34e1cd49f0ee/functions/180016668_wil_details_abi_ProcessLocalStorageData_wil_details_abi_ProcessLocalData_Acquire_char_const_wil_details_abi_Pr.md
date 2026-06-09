# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180016668`
- end: `0x1800167ce`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800176d8`

## callees

- `0x1800138ec`
- `0x1800139fc`
- `0x180013b94`
- `0x180014130`
- `0x1800161c4`
- `0x1800161e0`
- `0x180016668`
- `0x180017ed0`
- `0x180019e68`
- `0x18001a694`
- `0x18001a9c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800166e5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800166e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800166a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800166a0`

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
0x180016668  mov     [rsp-8+arg_10], rbx
0x18001666d  mov     [rsp-8+arg_18], rdi
0x180016672  push    rbp
0x180016673  lea     rbp, [rsp-170h]
0x18001667b  sub     rsp, 270h
0x180016682  mov     rax, cs:__security_cookie
0x180016689  xor     rax, rsp
0x18001668c  mov     [rbp+170h+var_10], rax
0x180016693  mov     rdi, rdx
0x180016696  mov     qword ptr [rdx], 0
0x18001669d  mov     rbx, rcx
0x1800166a0  call    cs:__imp_GetCurrentProcessId
0x1800166a6  mov     [rsp+270h+var_248], rbx
0x1800166ab  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800166b2  mov     r9d, eax
0x1800166b5  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800166bd  mov     edx, 104h; unsigned __int64
0x1800166c2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800166c7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800166cc  mov     r9d, 1F0001h; dwDesiredAccess
0x1800166d2  mov     [rsp+270h+var_240], 0
0x1800166db  xor     r8d, r8d; dwFlags
0x1800166de  lea     rdx, [rsp+270h+Name]; lpName
0x1800166e3  xor     ecx, ecx; lpMutexAttributes
0x1800166e5  call    cs:__imp_CreateMutexExW
0x1800166eb  mov     rdx, rax
0x1800166ee  lea     rcx, [rsp+270h+var_240]
0x1800166f3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800166f8  cmp     [rsp+270h+var_240], 0
0x1800166fe  jnz     short loc_180016709
0x180016700  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180016705  mov     ebx, eax
0x180016707  jmp     short loc_18001677C
0x180016709  lea     rdx, [rsp+270h+var_238]
0x18001670e  lea     rcx, [rsp+270h+var_240]
0x180016713  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180016718  lea     rdx, [rsp+270h+var_230]; void **
0x18001671d  mov     [rsp+270h+var_230], 0
0x180016726  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18001672b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x180016730  mov     ebx, eax
0x180016732  test    eax, eax
0x180016734  jns     short loc_18001675D
0x180016736  mov     edx, 12Eh; void *
0x18001673b  mov     rcx, [rbp+178h]; this
0x180016742  lea     r8, aWil; "wil"
0x180016749  mov     r9d, eax; char *
0x18001674c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016751  lea     rcx, [rsp+270h+var_238]
0x180016756  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001675b  jmp     short loc_18001677C
0x18001675d  mov     rcx, [rsp+270h+var_230]
0x180016762  test    rcx, rcx
0x180016765  jz      short loc_1800167AC
0x180016767  mov     [rdi], rcx
0x18001676a  mov     eax, [rcx]
0x18001676c  inc     eax
0x18001676e  mov     [rcx], eax
0x180016770  lea     rcx, [rsp+270h+var_238]
0x180016775  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001677a  xor     ebx, ebx
0x18001677c  lea     rcx, [rsp+270h+var_240]
0x180016781  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180016786  mov     eax, ebx
0x180016788  mov     rcx, [rbp+170h+var_10]
0x18001678f  xor     rcx, rsp; StackCookie
0x180016792  call    __security_check_cookie
0x180016797  lea     r11, [rsp+270h+var_s0]
0x18001679f  mov     rbx, [r11+20h]
0x1800167a3  mov     rdi, [r11+28h]
0x1800167a7  mov     rsp, r11
0x1800167aa  pop     rbp
0x1800167ab  retn
0x1800167ac  mov     r8, rdi
0x1800167af  lea     rdx, [rsp+270h+var_240]
0x1800167b4  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1800167b9  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800167be  mov     ebx, eax
0x1800167c0  test    eax, eax
0x1800167c2  jns     short loc_180016770
0x1800167c4  mov     edx, 137h
0x1800167c9  jmp     loc_18001673B
```
