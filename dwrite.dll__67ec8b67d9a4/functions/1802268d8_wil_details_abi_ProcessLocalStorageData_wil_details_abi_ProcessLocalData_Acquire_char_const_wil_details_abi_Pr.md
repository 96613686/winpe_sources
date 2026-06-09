# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1802268d8`
- end: `0x180226a3e`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180227828`

## callees

- `0x180210b78`
- `0x180212490`
- `0x180226608`
- `0x180226624`
- `0x1802268d8`
- `0x180227fa4`
- `0x180228eec`
- `0x1802295b8`
- `0x180229a0c`
- `0x18022a194`
- `0x18022a320`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180226910`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180226910`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180226955`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180226955`

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
0x1802268d8  mov     [rsp-8+arg_10], rbx
0x1802268dd  mov     [rsp-8+arg_18], rdi
0x1802268e2  push    rbp
0x1802268e3  lea     rbp, [rsp-170h]
0x1802268eb  sub     rsp, 270h
0x1802268f2  mov     rax, cs:__security_cookie
0x1802268f9  xor     rax, rsp
0x1802268fc  mov     [rbp+170h+var_10], rax
0x180226903  mov     rdi, rdx
0x180226906  mov     qword ptr [rdx], 0
0x18022690d  mov     rbx, rcx
0x180226910  call    cs:__imp_GetCurrentProcessId
0x180226916  mov     [rsp+270h+var_248], rbx
0x18022691b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180226922  mov     r9d, eax
0x180226925  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18022692d  mov     edx, 104h; unsigned __int64
0x180226932  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180226937  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18022693c  mov     r9d, 1F0001h; dwDesiredAccess
0x180226942  mov     [rsp+270h+var_240], 0
0x18022694b  xor     r8d, r8d; dwFlags
0x18022694e  lea     rdx, [rsp+270h+Name]; lpName
0x180226953  xor     ecx, ecx; lpMutexAttributes
0x180226955  call    cs:__imp_CreateMutexExW
0x18022695b  mov     rdx, rax
0x18022695e  lea     rcx, [rsp+270h+var_240]
0x180226963  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180226968  cmp     [rsp+270h+var_240], 0
0x18022696e  jnz     short loc_180226979
0x180226970  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180226975  mov     ebx, eax
0x180226977  jmp     short loc_1802269EC
0x180226979  lea     rdx, [rsp+270h+var_238]
0x18022697e  lea     rcx, [rsp+270h+var_240]
0x180226983  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180226988  lea     rdx, [rsp+270h+var_230]; void **
0x18022698d  mov     [rsp+270h+var_230], 0
0x180226996  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18022699b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x1802269a0  mov     ebx, eax
0x1802269a2  test    eax, eax
0x1802269a4  jns     short loc_1802269CD
0x1802269a6  mov     edx, 12Eh; void *
0x1802269ab  mov     rcx, [rbp+178h]; this
0x1802269b2  lea     r8, aWil; "wil"
0x1802269b9  mov     r9d, eax; char *
0x1802269bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802269c1  lea     rcx, [rsp+270h+var_238]
0x1802269c6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1802269cb  jmp     short loc_1802269EC
0x1802269cd  mov     rcx, [rsp+270h+var_230]
0x1802269d2  test    rcx, rcx
0x1802269d5  jz      short loc_180226A1C
0x1802269d7  mov     [rdi], rcx
0x1802269da  mov     eax, [rcx]
0x1802269dc  inc     eax
0x1802269de  mov     [rcx], eax
0x1802269e0  lea     rcx, [rsp+270h+var_238]
0x1802269e5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1802269ea  xor     ebx, ebx
0x1802269ec  lea     rcx, [rsp+270h+var_240]
0x1802269f1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1802269f6  mov     eax, ebx
0x1802269f8  mov     rcx, [rbp+170h+var_10]
0x1802269ff  xor     rcx, rsp; StackCookie
0x180226a02  call    __security_check_cookie
0x180226a07  lea     r11, [rsp+270h+var_s0]
0x180226a0f  mov     rbx, [r11+20h]
0x180226a13  mov     rdi, [r11+28h]
0x180226a17  mov     rsp, r11
0x180226a1a  pop     rbp
0x180226a1b  retn
0x180226a1c  mov     r8, rdi
0x180226a1f  lea     rdx, [rsp+270h+var_240]
0x180226a24  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180226a29  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180226a2e  mov     ebx, eax
0x180226a30  test    eax, eax
0x180226a32  jns     short loc_1802269E0
0x180226a34  mov     edx, 137h
0x180226a39  jmp     loc_1802269AB
```
