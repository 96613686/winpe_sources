# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800eb438`
- end: `0x1800eb59e`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800ebb00`

## callees

- `0x1800d3390`
- `0x1800e9380`
- `0x1800eaf94`
- `0x1800eafb4`
- `0x1800eb438`
- `0x1800ec5cc`
- `0x1800ed7e0`
- `0x1800ee92c`
- `0x1800ef2a4`
- `0x1800efc54`
- `0x1800eff18`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800eb4b5`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800eb4b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800eb46d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800eb46d`

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
      v9 = 299;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v13);
      goto LABEL_9;
    }
    v10 = v14;
    if ( v14 )
    {
      *a2 = v14;
      *(_DWORD *)*a2 = *v10 + 1;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v9 = 308;
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
0x1800eb438  mov     [rsp-8+arg_10], rbx
0x1800eb43d  mov     [rsp-8+arg_18], rdi
0x1800eb442  push    rbp
0x1800eb443  lea     rbp, [rsp-170h]
0x1800eb44b  sub     rsp, 270h
0x1800eb452  mov     rax, cs:__security_cookie
0x1800eb459  xor     rax, rsp
0x1800eb45c  mov     [rbp+170h+var_10], rax
0x1800eb463  and     qword ptr [rdx], 0
0x1800eb467  mov     rdi, rdx
0x1800eb46a  mov     rbx, rcx
0x1800eb46d  call    cs:__imp_GetCurrentProcessId
0x1800eb474  nop     dword ptr [rax+rax+00h]
0x1800eb479  mov     [rsp+270h+var_248], rbx
0x1800eb47e  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800eb485  mov     r9d, eax
0x1800eb488  mov     [rsp+270h+var_250], 130h; int
0x1800eb490  mov     edx, 104h; unsigned __int64
0x1800eb495  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800eb49a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800eb49f  and     [rsp+270h+var_240], 0
0x1800eb4a5  lea     rdx, [rsp+270h+Name]; lpName
0x1800eb4aa  mov     r9d, 1F0001h; dwDesiredAccess
0x1800eb4b0  xor     r8d, r8d; dwFlags
0x1800eb4b3  xor     ecx, ecx; lpMutexAttributes
0x1800eb4b5  call    cs:__imp_CreateMutexExW
0x1800eb4bc  nop     dword ptr [rax+rax+00h]
0x1800eb4c1  mov     rdx, rax
0x1800eb4c4  lea     rcx, [rsp+270h+var_240]
0x1800eb4c9  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800eb4ce  cmp     [rsp+270h+var_240], 0
0x1800eb4d4  jnz     short loc_1800EB4DF
0x1800eb4d6  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800eb4db  mov     ebx, eax
0x1800eb4dd  jmp     short loc_1800EB54B
0x1800eb4df  lea     rdx, [rsp+270h+var_238]
0x1800eb4e4  lea     rcx, [rsp+270h+var_240]
0x1800eb4e9  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800eb4ee  and     [rsp+270h+var_230], 0
0x1800eb4f4  lea     rdx, [rsp+270h+var_230]; void **
0x1800eb4f9  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800eb4fe  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800eb503  mov     ebx, eax
0x1800eb505  test    eax, eax
0x1800eb507  jns     short loc_1800EB529
0x1800eb509  mov     edx, 12Bh; void *
0x1800eb50e  mov     rcx, [rbp+178h]; this
0x1800eb515  mov     r9d, eax; char *
0x1800eb518  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800eb51d  lea     rcx, [rsp+270h+var_238]
0x1800eb522  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800eb527  jmp     short loc_1800EB54B
0x1800eb529  mov     rcx, [rsp+270h+var_230]
0x1800eb52e  test    rcx, rcx
0x1800eb531  jz      short loc_1800EB57C
0x1800eb533  mov     [rdi], rcx
0x1800eb536  mov     ecx, [rcx]
0x1800eb538  mov     rax, [rdi]
0x1800eb53b  inc     ecx
0x1800eb53d  mov     [rax], ecx
0x1800eb53f  lea     rcx, [rsp+270h+var_238]
0x1800eb544  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800eb549  xor     ebx, ebx
0x1800eb54b  lea     rcx, [rsp+270h+var_240]
0x1800eb550  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800eb555  mov     eax, ebx
0x1800eb557  mov     rcx, [rbp+170h+var_10]
0x1800eb55e  xor     rcx, rsp; StackCookie
0x1800eb561  call    __security_check_cookie
0x1800eb566  lea     r11, [rsp+270h+var_s0]
0x1800eb56e  mov     rbx, [r11+20h]
0x1800eb572  mov     rdi, [r11+28h]
0x1800eb576  mov     rsp, r11
0x1800eb579  pop     rbp
0x1800eb57a  retn
0x1800eb57c  mov     r8, rdi
0x1800eb57f  lea     rdx, [rsp+270h+var_240]
0x1800eb584  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800eb589  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800eb58e  mov     ebx, eax
0x1800eb590  test    eax, eax
0x1800eb592  jns     short loc_1800EB53F
0x1800eb594  mov     edx, 134h
0x1800eb599  jmp     loc_1800EB50E
```
