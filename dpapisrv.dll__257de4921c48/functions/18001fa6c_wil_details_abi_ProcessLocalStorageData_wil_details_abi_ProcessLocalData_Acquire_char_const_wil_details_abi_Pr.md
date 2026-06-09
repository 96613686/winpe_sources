# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18001fa6c`
- end: `0x18001fbdf`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `371`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180020fac`

## callees

- `0x18000c450`
- `0x18001be38`
- `0x18001c490`
- `0x18001c760`
- `0x18001d810`
- `0x18001f810`
- `0x18001f830`
- `0x18001fa6c`
- `0x180023488`
- `0x180023dc0`
- `0x180023f84`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001faef`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18001faef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001faa4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001faa4`

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
0x18001fa6c  mov     [rsp-8+arg_10], rbx
0x18001fa71  mov     [rsp-8+arg_18], rdi
0x18001fa76  push    rbp
0x18001fa77  lea     rbp, [rsp-170h]
0x18001fa7f  sub     rsp, 270h
0x18001fa86  mov     rax, cs:__security_cookie
0x18001fa8d  xor     rax, rsp
0x18001fa90  mov     [rbp+170h+var_10], rax
0x18001fa97  mov     rdi, rdx
0x18001fa9a  mov     qword ptr [rdx], 0
0x18001faa1  mov     rbx, rcx
0x18001faa4  call    cs:__imp_GetCurrentProcessId
0x18001faab  nop     dword ptr [rax+rax+00h]
0x18001fab0  mov     [rsp+270h+var_248], rbx
0x18001fab5  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18001fabc  mov     r9d, eax
0x18001fabf  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18001fac7  mov     edx, 104h; unsigned __int64
0x18001facc  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001fad1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001fad6  mov     r9d, 1F0001h; dwDesiredAccess
0x18001fadc  mov     [rsp+270h+var_240], 0
0x18001fae5  xor     r8d, r8d; dwFlags
0x18001fae8  lea     rdx, [rsp+270h+Name]; lpName
0x18001faed  xor     ecx, ecx; lpMutexAttributes
0x18001faef  call    cs:__imp_CreateMutexExW
0x18001faf6  nop     dword ptr [rax+rax+00h]
0x18001fafb  mov     rdx, rax
0x18001fafe  lea     rcx, [rsp+270h+var_240]
0x18001fb03  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001fb08  cmp     [rsp+270h+var_240], 0
0x18001fb0e  jnz     short loc_18001FB19
0x18001fb10  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18001fb15  mov     ebx, eax
0x18001fb17  jmp     short loc_18001FB8C
0x18001fb19  lea     rdx, [rsp+270h+var_238]
0x18001fb1e  lea     rcx, [rsp+270h+var_240]
0x18001fb23  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18001fb28  lea     rdx, [rsp+270h+var_230]; void **
0x18001fb2d  mov     [rsp+270h+var_230], 0
0x18001fb36  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001fb3b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x18001fb40  mov     ebx, eax
0x18001fb42  test    eax, eax
0x18001fb44  jns     short loc_18001FB6D
0x18001fb46  mov     edx, 12Eh; void *
0x18001fb4b  mov     rcx, [rbp+178h]; this
0x18001fb52  lea     r8, aWil; "wil"
0x18001fb59  mov     r9d, eax; char *
0x18001fb5c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fb61  lea     rcx, [rsp+270h+var_238]
0x18001fb66  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001fb6b  jmp     short loc_18001FB8C
0x18001fb6d  mov     rcx, [rsp+270h+var_230]
0x18001fb72  test    rcx, rcx
0x18001fb75  jz      short loc_18001FBBD
0x18001fb77  mov     [rdi], rcx
0x18001fb7a  mov     eax, [rcx]
0x18001fb7c  inc     eax
0x18001fb7e  mov     [rcx], eax
0x18001fb80  lea     rcx, [rsp+270h+var_238]
0x18001fb85  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001fb8a  xor     ebx, ebx
0x18001fb8c  lea     rcx, [rsp+270h+var_240]
0x18001fb91  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001fb96  mov     eax, ebx
0x18001fb98  mov     rcx, [rbp+170h+var_10]
0x18001fb9f  xor     rcx, rsp; StackCookie
0x18001fba2  call    __security_check_cookie
0x18001fba7  lea     r11, [rsp+270h+var_s0]
0x18001fbaf  mov     rbx, [r11+20h]
0x18001fbb3  mov     rdi, [r11+28h]
0x18001fbb7  mov     rsp, r11
0x18001fbba  pop     rbp
0x18001fbbb  retn
0x18001fbbd  mov     r8, rdi
0x18001fbc0  lea     rdx, [rsp+270h+var_240]
0x18001fbc5  lea     rcx, [rsp+270h+Name]
0x18001fbca  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18001fbcf  mov     ebx, eax
0x18001fbd1  test    eax, eax
0x18001fbd3  jns     short loc_18001FB80
0x18001fbd5  mov     edx, 137h
0x18001fbda  jmp     loc_18001FB4B
```
