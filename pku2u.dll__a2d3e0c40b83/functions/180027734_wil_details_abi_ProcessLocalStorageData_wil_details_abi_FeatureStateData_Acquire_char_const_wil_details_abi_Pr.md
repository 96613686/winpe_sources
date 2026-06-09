# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180027734`
- end: `0x18002789a`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180027910`

## callees

- `0x18001ebf8`
- `0x1800210f0`
- `0x180025394`
- `0x1800253b0`
- `0x1800264a4`
- `0x180026a3c`
- `0x180026ba8`
- `0x180026e6c`
- `0x180026f5c`
- `0x180027734`
- `0x1800283dc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002776c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002776c`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800277b1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800277b1`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
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
        304);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
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
0x180027734  mov     [rsp-8+arg_10], rbx
0x180027739  mov     [rsp-8+arg_18], rdi
0x18002773e  push    rbp
0x18002773f  lea     rbp, [rsp-170h]
0x180027747  sub     rsp, 270h
0x18002774e  mov     rax, cs:__security_cookie
0x180027755  xor     rax, rsp
0x180027758  mov     [rbp+170h+var_10], rax
0x18002775f  mov     rdi, rdx
0x180027762  mov     qword ptr [rdx], 0
0x180027769  mov     rbx, rcx
0x18002776c  call    cs:__imp_GetCurrentProcessId
0x180027772  mov     [rsp+270h+var_248], rbx
0x180027777  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18002777e  mov     r9d, eax
0x180027781  mov     [rsp+270h+var_250], 130h; int
0x180027789  mov     edx, 104h; unsigned __int64
0x18002778e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180027793  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180027798  mov     r9d, 1F0001h; dwDesiredAccess
0x18002779e  mov     [rsp+270h+var_240], 0
0x1800277a7  xor     r8d, r8d; dwFlags
0x1800277aa  lea     rdx, [rsp+270h+Name]; lpName
0x1800277af  xor     ecx, ecx; lpMutexAttributes
0x1800277b1  call    cs:__imp_CreateMutexExW
0x1800277b7  mov     rdx, rax
0x1800277ba  lea     rcx, [rsp+270h+var_240]
0x1800277bf  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800277c4  cmp     [rsp+270h+var_240], 0
0x1800277ca  jnz     short loc_1800277D5
0x1800277cc  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800277d1  mov     ebx, eax
0x1800277d3  jmp     short loc_180027848
0x1800277d5  lea     rdx, [rsp+270h+var_238]
0x1800277da  lea     rcx, [rsp+270h+var_240]
0x1800277df  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800277e4  lea     rdx, [rsp+270h+var_230]; void **
0x1800277e9  mov     [rsp+270h+var_230], 0
0x1800277f2  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800277f7  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800277fc  mov     ebx, eax
0x1800277fe  test    eax, eax
0x180027800  jns     short loc_180027829
0x180027802  mov     edx, 12Eh; void *
0x180027807  mov     rcx, [rbp+178h]; this
0x18002780e  lea     r8, aWil; "wil"
0x180027815  mov     r9d, eax; char *
0x180027818  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002781d  lea     rcx, [rsp+270h+var_238]
0x180027822  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180027827  jmp     short loc_180027848
0x180027829  mov     rcx, [rsp+270h+var_230]
0x18002782e  test    rcx, rcx
0x180027831  jz      short loc_180027878
0x180027833  mov     [rdi], rcx
0x180027836  mov     eax, [rcx]
0x180027838  inc     eax
0x18002783a  mov     [rcx], eax
0x18002783c  lea     rcx, [rsp+270h+var_238]
0x180027841  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180027846  xor     ebx, ebx
0x180027848  lea     rcx, [rsp+270h+var_240]
0x18002784d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180027852  mov     eax, ebx
0x180027854  mov     rcx, [rbp+170h+var_10]
0x18002785b  xor     rcx, rsp; StackCookie
0x18002785e  call    __security_check_cookie
0x180027863  lea     r11, [rsp+270h+var_s0]
0x18002786b  mov     rbx, [r11+20h]
0x18002786f  mov     rdi, [r11+28h]
0x180027873  mov     rsp, r11
0x180027876  pop     rbp
0x180027877  retn
0x180027878  mov     r8, rdi
0x18002787b  lea     rdx, [rsp+270h+var_240]
0x180027880  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180027885  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18002788a  mov     ebx, eax
0x18002788c  test    eax, eax
0x18002788e  jns     short loc_18002783C
0x180027890  mov     edx, 137h
0x180027895  jmp     loc_180027807
```
