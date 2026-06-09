# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180158d9c`
- end: `0x180158f63`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `455`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18022aed0`

## callees

- `0x18002b954`
- `0x18002be34`
- `0x18004fce4`
- `0x180158ab0`
- `0x180158d9c`
- `0x180158fc4`
- `0x180159498`
- `0x180200488`
- `0x180200520`
- `0x180202120`
- `0x18021ddb8`
- `0x1802284b0`
- `0x18022b1b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180158e41`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180158e41`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180158e17`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180158e17`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180158dd2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180158dd2`

## string_xrefs

- `0x180158f23`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  DWORD v6; // eax
  bool v7; // dl
  char *v8; // r9
  wil::details *v9; // rbx
  int ValueInternal; // eax
  unsigned int v11; // edi
  void *v12; // rdx
  _DWORD *v14; // rcx
  int v15; // eax
  unsigned int v16; // ebx
  int v17; // [rsp+20h] [rbp-E0h]
  int v18; // [rsp+20h] [rbp-E0h]
  HANDLE hHandle; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v20; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v21[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  hHandle = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &hHandle,
    Mutex);
  if ( !hHandle )
    return wil::details::GetLastErrorFailHr(v5);
  v6 = WaitForSingleObjectEx(hHandle, 0xFFFFFFFF, 0);
  if ( v6 == 258 )
  {
    v9 = 0;
  }
  else
  {
    if ( (v6 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v8);
    v9 = (wil::details *)hHandle;
  }
  v21[0] = v9;
  v20 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v7, &v20, (bool *)v8);
  v11 = ValueInternal;
  if ( ValueInternal >= 0 )
  {
    v14 = (_DWORD *)(4 * v20);
    if ( 4 * v20 )
    {
      *a2 = v14;
      ++*v14;
    }
    else
    {
      v15 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
      v16 = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x137,
          (unsigned int)"wil",
          (const char *)(unsigned int)v15,
          304);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v21);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hHandle);
        return v16;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v21);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hHandle);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v11, v17);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v11, v18);
    if ( v9 )
      wil::details::ReleaseMutex(v9, v12);
    wil::details::CloseHandle((wil::details *)hHandle, v12);
    return v11;
  }
}

```

## disassembly

```asm
0x180158d9c  mov     [rsp-8+arg_10], rbx
0x180158da1  push    rbp
0x180158da2  push    rdi
0x180158da3  push    r14
0x180158da5  lea     rbp, [rsp-170h]
0x180158dad  sub     rsp, 270h
0x180158db4  mov     rax, cs:__security_cookie
0x180158dbb  xor     rax, rsp
0x180158dbe  mov     [rbp+180h+var_20], rax
0x180158dc5  mov     r14, rdx
0x180158dc8  mov     qword ptr [rdx], 0
0x180158dcf  mov     rbx, rcx
0x180158dd2  call    cs:__imp_GetCurrentProcessId
0x180158dd8  mov     [rsp+280h+var_258], rbx
0x180158ddd  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180158de4  mov     r9d, eax
0x180158de7  mov     [rsp+280h+var_260], 130h; int
0x180158def  mov     edx, 104h; unsigned __int64
0x180158df4  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180158df9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180158dfe  mov     r9d, 1F0001h; dwDesiredAccess
0x180158e04  mov     [rsp+280h+hHandle], 0
0x180158e0d  xor     r8d, r8d; dwFlags
0x180158e10  lea     rdx, [rsp+280h+Name]; lpName
0x180158e15  xor     ecx, ecx; lpMutexAttributes
0x180158e17  call    cs:__imp_CreateMutexExW
0x180158e1d  mov     rdx, rax
0x180158e20  lea     rcx, [rsp+280h+hHandle]
0x180158e25  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180158e2a  cmp     [rsp+280h+hHandle], 0
0x180158e30  jz      loc_180158F0E
0x180158e36  mov     rcx, [rsp+280h+hHandle]; hHandle
0x180158e3b  xor     r8d, r8d; bAlertable
0x180158e3e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180158e41  call    cs:__imp_WaitForSingleObjectEx
0x180158e47  cmp     eax, 102h
0x180158e4c  jz      loc_180158F15
0x180158e52  test    eax, 0FFFFFF7Fh
0x180158e57  jnz     loc_180158F1C
0x180158e5d  mov     rbx, [rsp+280h+hHandle]
0x180158e62  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x180158e67  mov     [rsp+280h+var_240], rbx
0x180158e6c  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180158e71  mov     [rsp+280h+var_248], 0
0x180158e7a  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x180158e7f  mov     edi, eax
0x180158e81  test    eax, eax
0x180158e83  jns     loc_180158F3F
0x180158e89  mov     rcx, [rbp+188h]; this
0x180158e90  lea     r8, aWil; "wil"
0x180158e97  mov     r9d, eax; char *
0x180158e9a  mov     edx, 66h ; 'f'; void *
0x180158e9f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180158ea4  mov     rcx, [rbp+188h]; this
0x180158eab  lea     r8, aWil; "wil"
0x180158eb2  mov     r9d, edi; char *
0x180158eb5  mov     edx, 6Fh ; 'o'; void *
0x180158eba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180158ebf  mov     rcx, [rbp+188h]; this
0x180158ec6  lea     r8, aWil; "wil"
0x180158ecd  mov     r9d, edi; char *
0x180158ed0  mov     edx, 12Eh; void *
0x180158ed5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180158eda  test    rbx, rbx
0x180158edd  jnz     short loc_180158F35
0x180158edf  mov     rcx, [rsp+280h+hHandle]; this
0x180158ee4  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180158ee9  mov     eax, edi
0x180158eeb  mov     rcx, [rbp+180h+var_20]
0x180158ef2  xor     rcx, rsp; StackCookie
0x180158ef5  call    __security_check_cookie
0x180158efa  mov     rbx, [rsp+280h+arg_10]
0x180158f02  add     rsp, 270h
0x180158f09  pop     r14
0x180158f0b  pop     rdi
0x180158f0c  pop     rbp
0x180158f0d  retn
0x180158f0e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180158f13  jmp     short loc_180158EEB
0x180158f15  xor     ebx, ebx
0x180158f17  jmp     loc_180158E62
0x180158f1c  mov     rcx, [rbp+188h]; this
0x180158f23  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180158f2a  mov     edx, 0E01h; void *
0x180158f2f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180158f35  mov     rcx, rbx; this
0x180158f38  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x180158f3d  jmp     short loc_180158EDF
0x180158f3f  mov     rax, [rsp+280h+var_248]
0x180158f44  lea     rcx, ds:0[rax*4]
0x180158f4c  test    rcx, rcx
0x180158f4f  jz      loc_1802A9730
0x180158f55  mov     [r14], rcx
0x180158f58  mov     eax, [rcx]
0x180158f5a  inc     eax
0x180158f5c  mov     [rcx], eax
0x180158f5e  jmp     loc_1802A977E
0x1802a9730  mov     r8, r14
0x1802a9733  lea     rdx, [rsp+280h+hHandle]
0x1802a9738  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1802a973d  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1802a9742  mov     ebx, eax
0x1802a9744  test    eax, eax
0x1802a9746  jns     short loc_1802A977E
0x1802a9748  mov     rcx, [rbp+188h]; this
0x1802a974f  lea     r8, aWil; "wil"
0x1802a9756  mov     r9d, eax; char *
0x1802a9759  mov     edx, 137h; void *
0x1802a975e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802a9763  lea     rcx, [rsp+280h+var_240]
0x1802a9768  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1802a976d  lea     rcx, [rsp+280h+hHandle]
0x1802a9772  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1802a9777  mov     eax, ebx
0x1802a9779  jmp     loc_180158EEB
0x1802a977e  lea     rcx, [rsp+280h+var_240]
0x1802a9783  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1802a9788  lea     rcx, [rsp+280h+hHandle]
0x1802a978d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1802a9792  xor     eax, eax
0x1802a9794  jmp     loc_180158EEB
```
