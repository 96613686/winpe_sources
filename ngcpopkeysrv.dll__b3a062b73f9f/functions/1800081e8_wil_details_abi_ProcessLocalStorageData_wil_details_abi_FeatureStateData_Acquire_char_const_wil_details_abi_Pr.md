# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800081e8`
- end: `0x180008371`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `393`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180008ff4`

## callees

- `0x180004de0`
- `0x180007968`
- `0x180007984`
- `0x1800081e8`
- `0x180008e38`
- `0x180009d44`
- `0x18000b0fc`
- `0x18000b898`
- `0x18000bd1c`
- `0x18000c624`
- `0x18000c970`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180008265`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180008265`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008220`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008220`

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
  _DWORD *v8; // rcx
  int v10; // eax
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
    if ( Pointer >= 0 )
    {
      v8 = v13;
      if ( v13 )
      {
        *a2 = v13;
        ++*v8;
      }
      else
      {
        v10 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
        LastErrorFailHr = v10;
        if ( v10 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x137,
            (unsigned int)"wil",
            (const char *)(unsigned int)v10,
            304);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v12);
          goto LABEL_8;
        }
      }
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v12);
      LastErrorFailHr = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x12E,
        (unsigned int)"wil",
        (const char *)(unsigned int)Pointer,
        304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v12);
    }
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
  }
LABEL_8:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v11);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x1800081e8  mov     [rsp-8+arg_10], rbx
0x1800081ed  mov     [rsp-8+arg_18], rdi
0x1800081f2  push    rbp
0x1800081f3  lea     rbp, [rsp-170h]
0x1800081fb  sub     rsp, 270h
0x180008202  mov     rax, cs:__security_cookie
0x180008209  xor     rax, rsp
0x18000820c  mov     [rbp+170h+var_10], rax
0x180008213  mov     rdi, rdx
0x180008216  mov     rbx, rcx
0x180008219  mov     qword ptr [rdx], 0
0x180008220  call    cs:__imp_GetCurrentProcessId
0x180008226  mov     r9d, eax
0x180008229  mov     [rsp+270h+var_248], rbx
0x18000822e  mov     [rsp+270h+var_250], 130h; int
0x180008236  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000823d  mov     edx, 104h; unsigned __int64
0x180008242  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180008247  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000824c  mov     [rsp+270h+var_240], 0
0x180008255  mov     r9d, 1F0001h; dwDesiredAccess
0x18000825b  xor     r8d, r8d; dwFlags
0x18000825e  lea     rdx, [rsp+270h+Name]; lpName
0x180008263  xor     ecx, ecx; lpMutexAttributes
0x180008265  call    cs:__imp_CreateMutexExW
0x18000826b  mov     rdx, rax
0x18000826e  lea     rcx, [rsp+270h+var_240]
0x180008273  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180008278  cmp     [rsp+270h+var_240], 0
0x18000827e  jnz     short loc_180008289
0x180008280  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180008285  mov     ebx, eax
0x180008287  jmp     short loc_180008300
0x180008289  lea     rdx, [rsp+270h+var_238]
0x18000828e  lea     rcx, [rsp+270h+var_240]
0x180008293  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180008298  nop
0x180008299  mov     [rsp+270h+var_230], 0
0x1800082a2  lea     rdx, [rsp+270h+var_230]; void **
0x1800082a7  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800082ac  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800082b1  mov     ebx, eax
0x1800082b3  test    eax, eax
0x1800082b5  jns     short loc_1800082E0
0x1800082b7  mov     rcx, [rbp+178h]; this
0x1800082be  mov     r9d, eax; char *
0x1800082c1  lea     r8, aWil; "wil"
0x1800082c8  mov     edx, 12Eh; void *
0x1800082cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800082d2  nop
0x1800082d3  lea     rcx, [rsp+270h+var_238]
0x1800082d8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800082dd  nop
0x1800082de  jmp     short loc_180008300
0x1800082e0  mov     rcx, [rsp+270h+var_230]
0x1800082e5  test    rcx, rcx
0x1800082e8  jz      short loc_180008330
0x1800082ea  mov     [rdi], rcx
0x1800082ed  mov     eax, [rcx]
0x1800082ef  inc     eax
0x1800082f1  mov     [rcx], eax
0x1800082f3  lea     rcx, [rsp+270h+var_238]
0x1800082f8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800082fd  nop
0x1800082fe  xor     ebx, ebx
0x180008300  lea     rcx, [rsp+270h+var_240]
0x180008305  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000830a  mov     eax, ebx
0x18000830c  mov     rcx, [rbp+170h+var_10]
0x180008313  xor     rcx, rsp; StackCookie
0x180008316  call    __security_check_cookie
0x18000831b  lea     r11, [rsp+270h+var_s0]
0x180008323  mov     rbx, [r11+20h]
0x180008327  mov     rdi, [r11+28h]
0x18000832b  mov     rsp, r11
0x18000832e  pop     rbp
0x18000832f  retn
0x180008330  mov     r8, rdi
0x180008333  lea     rdx, [rsp+270h+var_240]
0x180008338  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000833d  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180008342  mov     ebx, eax
0x180008344  test    eax, eax
0x180008346  jns     short loc_1800082F3
0x180008348  mov     rcx, [rbp+178h]; this
0x18000834f  mov     r9d, eax; char *
0x180008352  lea     r8, aWil; "wil"
0x180008359  mov     edx, 137h; void *
0x18000835e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008363  nop
0x180008364  lea     rcx, [rsp+270h+var_238]
0x180008369  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000836e  nop
0x18000836f  jmp     short loc_180008300
```
