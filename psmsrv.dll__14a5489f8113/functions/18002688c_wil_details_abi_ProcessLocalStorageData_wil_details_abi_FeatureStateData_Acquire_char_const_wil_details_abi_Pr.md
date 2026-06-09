# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18002688c`
- end: `0x1800269eb`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800275d8`

## callees

- `0x18001a6a8`
- `0x18001a804`
- `0x18001a850`
- `0x18001b2d0`
- `0x18001b7e0`
- `0x180026550`
- `0x18002656c`
- `0x18002688c`
- `0x1800294c0`
- `0x180029d04`
- `0x180029ef4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800268c4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800268c4`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180026909`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180026909`

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
      v9 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 304);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
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
0x18002688c  mov     [rsp-8+arg_10], rbx
0x180026891  mov     [rsp-8+arg_18], rdi
0x180026896  push    rbp
0x180026897  lea     rbp, [rsp-170h]
0x18002689f  sub     rsp, 270h
0x1800268a6  mov     rax, cs:__security_cookie
0x1800268ad  xor     rax, rsp
0x1800268b0  mov     [rbp+170h+var_10], rax
0x1800268b7  mov     rdi, rdx
0x1800268ba  mov     qword ptr [rdx], 0
0x1800268c1  mov     rbx, rcx
0x1800268c4  call    cs:__imp_GetCurrentProcessId
0x1800268ca  mov     [rsp+270h+var_248], rbx
0x1800268cf  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800268d6  mov     r9d, eax
0x1800268d9  mov     [rsp+270h+var_250], 130h; int
0x1800268e1  mov     edx, 104h; unsigned __int64
0x1800268e6  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800268eb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800268f0  mov     r9d, 1F0001h; dwDesiredAccess
0x1800268f6  mov     [rsp+270h+var_240], 0
0x1800268ff  xor     r8d, r8d; dwFlags
0x180026902  lea     rdx, [rsp+270h+Name]; lpName
0x180026907  xor     ecx, ecx; lpMutexAttributes
0x180026909  call    cs:__imp_CreateMutexExW
0x18002690f  mov     rdx, rax
0x180026912  lea     rcx, [rsp+270h+var_240]
0x180026917  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18002691c  cmp     [rsp+270h+var_240], 0
0x180026922  jnz     short loc_18002692D
0x180026924  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180026929  mov     ebx, eax
0x18002692b  jmp     short loc_180026999
0x18002692d  lea     rdx, [rsp+270h+var_238]
0x180026932  lea     rcx, [rsp+270h+var_240]
0x180026937  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18002693c  lea     rdx, [rsp+270h+var_230]; void **
0x180026941  mov     [rsp+270h+var_230], 0
0x18002694a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002694f  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180026954  mov     ebx, eax
0x180026956  test    eax, eax
0x180026958  jns     short loc_18002697A
0x18002695a  mov     edx, 12Eh; void *
0x18002695f  mov     rcx, [rbp+178h]; this
0x180026966  mov     r9d, eax; char *
0x180026969  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002696e  lea     rcx, [rsp+270h+var_238]
0x180026973  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180026978  jmp     short loc_180026999
0x18002697a  mov     rcx, [rsp+270h+var_230]
0x18002697f  test    rcx, rcx
0x180026982  jz      short loc_1800269C9
0x180026984  mov     [rdi], rcx
0x180026987  mov     eax, [rcx]
0x180026989  inc     eax
0x18002698b  mov     [rcx], eax
0x18002698d  lea     rcx, [rsp+270h+var_238]
0x180026992  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180026997  xor     ebx, ebx
0x180026999  lea     rcx, [rsp+270h+var_240]
0x18002699e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800269a3  mov     eax, ebx
0x1800269a5  mov     rcx, [rbp+170h+var_10]
0x1800269ac  xor     rcx, rsp; StackCookie
0x1800269af  call    __security_check_cookie
0x1800269b4  lea     r11, [rsp+270h+var_s0]
0x1800269bc  mov     rbx, [r11+20h]
0x1800269c0  mov     rdi, [r11+28h]
0x1800269c4  mov     rsp, r11
0x1800269c7  pop     rbp
0x1800269c8  retn
0x1800269c9  mov     r8, rdi
0x1800269cc  lea     rdx, [rsp+270h+var_240]
0x1800269d1  lea     rcx, [rsp+270h+Name]
0x1800269d6  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800269db  mov     ebx, eax
0x1800269dd  test    eax, eax
0x1800269df  jns     short loc_18002698D
0x1800269e1  mov     edx, 137h
0x1800269e6  jmp     loc_18002695F
```
