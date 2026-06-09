# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18003dec0`
- end: `0x18003e0ec`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `556`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18003de64`

## callees

- `0x18003dec0`
- `0x18003e0f4`
- `0x18003e17c`
- `0x18003e5d0`
- `0x18003e5fc`
- `0x18003e6e4`
- `0x18003e710`
- `0x18003e8f8`
- `0x180067d2c`
- `0x180075fa0`
- `0x18007d2e8`
- `0x18007daa8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18003df8b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18003df8b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18003df37`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18003df37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003defb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003defb`

## string_xrefs

- `0x18003e082`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  wil::details *Mutex; // rax
  wil::details *v5; // rcx
  wil::details *v6; // rbx
  DWORD v8; // eax
  bool v9; // dl
  char *v10; // r9
  wil::details *v11; // rdi
  int ValueInternal; // eax
  void *v13; // rdx
  unsigned int v14; // esi
  _DWORD *v15; // rcx
  void *v16; // rdx
  int v17; // eax
  unsigned int v18; // ebx
  int v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+20h] [rbp-E0h]
  wil::details *v21; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v23; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = (wil::details *)CreateMutexExW(0, Name, 0, 0x1F0001u);
  v21 = Mutex;
  v6 = Mutex;
  if ( !Mutex )
    return wil::details::GetLastErrorFailHr(v5);
  v8 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v8 == 258 )
  {
    v11 = 0;
  }
  else
  {
    if ( (v8 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v10);
    v11 = v6;
  }
  v23 = v11;
  v22 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v9, &v22, (bool *)v10);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v19);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v20);
    if ( v11 )
      wil::details::ReleaseMutex(v11, v16);
    wil::details::CloseHandle(v6, v16);
    return v14;
  }
  else
  {
    v15 = (_DWORD *)(4 * v22);
    if ( 4 * v22 )
    {
      *a2 = v15;
      ++*v15;
    }
    else
    {
      v17 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
      v18 = v17;
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x137,
          (unsigned int)"wil",
          (const char *)(unsigned int)v17,
          304);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
        return v18;
      }
      v6 = v21;
    }
    if ( v11 )
      wil::details::ReleaseMutex(v11, v13);
    if ( v6 )
      wil::details::CloseHandle(v6, v13);
    return 0;
  }
}

```

## disassembly

```asm
0x18003dec0  mov     [rsp-8+arg_10], rbx
0x18003dec5  mov     [rsp-8+arg_18], rsi
0x18003deca  push    rbp
0x18003decb  push    rdi
0x18003decc  push    r14
0x18003dece  lea     rbp, [rsp-170h]
0x18003ded6  sub     rsp, 270h
0x18003dedd  mov     rax, cs:__security_cookie
0x18003dee4  xor     rax, rsp
0x18003dee7  mov     [rbp+180h+var_20], rax
0x18003deee  mov     r14, rdx
0x18003def1  mov     qword ptr [rdx], 0
0x18003def8  mov     rbx, rcx
0x18003defb  call    cs:__imp_GetCurrentProcessId
0x18003df01  mov     [rsp+280h+var_258], rbx
0x18003df06  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18003df0d  mov     r9d, eax
0x18003df10  mov     [rsp+280h+var_260], 130h; int
0x18003df18  mov     edx, 104h; unsigned __int64
0x18003df1d  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18003df22  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003df27  mov     r9d, 1F0001h; dwDesiredAccess
0x18003df2d  lea     rdx, [rsp+280h+Name]; lpName
0x18003df32  xor     r8d, r8d; dwFlags
0x18003df35  xor     ecx, ecx; lpMutexAttributes
0x18003df37  call    cs:__imp_CreateMutexExW
0x18003df3d  mov     [rsp+280h+var_250], rax
0x18003df42  mov     rbx, rax
0x18003df45  test    rax, rax
0x18003df48  jnz     short loc_18003DF82
0x18003df4a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18003df4f  jmp     short loc_18003DF5B
0x18003df51  mov     rcx, rbx; this
0x18003df54  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18003df59  xor     eax, eax
0x18003df5b  mov     rcx, [rbp+180h+var_20]
0x18003df62  xor     rcx, rsp; StackCookie
0x18003df65  call    __security_check_cookie
0x18003df6a  lea     r11, [rsp+280h+var_10]
0x18003df72  mov     rbx, [r11+30h]
0x18003df76  mov     rsi, [r11+38h]
0x18003df7a  mov     rsp, r11
0x18003df7d  pop     r14
0x18003df7f  pop     rdi
0x18003df80  pop     rbp
0x18003df81  retn
0x18003df82  xor     r8d, r8d; bAlertable
0x18003df85  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18003df88  mov     rcx, rbx; hHandle
0x18003df8b  call    cs:__imp_WaitForSingleObjectEx
0x18003df91  cmp     eax, 102h
0x18003df96  jz      loc_18003E074
0x18003df9c  test    eax, 0FFFFFF7Fh
0x18003dfa1  jnz     loc_18003E07B
0x18003dfa7  mov     rdi, rbx
0x18003dfaa  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x18003dfaf  mov     [rsp+280h+var_240], rdi
0x18003dfb4  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18003dfb9  mov     [rsp+280h+var_248], 0
0x18003dfc2  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18003dfc7  mov     esi, eax
0x18003dfc9  test    eax, eax
0x18003dfcb  js      short loc_18003E007
0x18003dfcd  mov     rax, [rsp+280h+var_248]
0x18003dfd2  lea     rcx, ds:0[rax*4]
0x18003dfda  test    rcx, rcx
0x18003dfdd  jz      loc_18003E094
0x18003dfe3  mov     [r14], rcx
0x18003dfe6  mov     eax, [rcx]
0x18003dfe8  inc     eax
0x18003dfea  mov     [rcx], eax
0x18003dfec  test    rdi, rdi
0x18003dfef  jz      short loc_18003DFF9
0x18003dff1  mov     rcx, rdi; this
0x18003dff4  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18003dff9  test    rbx, rbx
0x18003dffc  jz      loc_18003DF59
0x18003e002  jmp     loc_18003DF51
0x18003e007  mov     rcx, [rbp+188h]; this
0x18003e00e  lea     r8, aWil; "wil"
0x18003e015  mov     r9d, esi; char *
0x18003e018  mov     edx, 66h ; 'f'; void *
0x18003e01d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e022  mov     rcx, [rbp+188h]; this
0x18003e029  lea     r8, aWil; "wil"
0x18003e030  mov     r9d, esi; char *
0x18003e033  mov     edx, 6Fh ; 'o'; void *
0x18003e038  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e03d  mov     rcx, [rbp+188h]; this
0x18003e044  lea     r8, aWil; "wil"
0x18003e04b  mov     r9d, esi; char *
0x18003e04e  mov     edx, 12Eh; void *
0x18003e053  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e058  test    rdi, rdi
0x18003e05b  jz      short loc_18003E065
0x18003e05d  mov     rcx, rdi; this
0x18003e060  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18003e065  mov     rcx, rbx; this
0x18003e068  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18003e06d  mov     eax, esi
0x18003e06f  jmp     loc_18003DF5B
0x18003e074  xor     edi, edi
0x18003e076  jmp     loc_18003DFAA
0x18003e07b  mov     rcx, [rbp+188h]; this
0x18003e082  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003e089  mov     edx, 0E01h; void *
0x18003e08e  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18003e094  mov     r8, r14
0x18003e097  lea     rdx, [rsp+280h+var_250]
0x18003e09c  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18003e0a1  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18003e0a6  mov     ebx, eax
0x18003e0a8  test    eax, eax
0x18003e0aa  jns     short loc_18003E0E2
0x18003e0ac  mov     rcx, [rbp+188h]; this
0x18003e0b3  lea     r8, aWil; "wil"
0x18003e0ba  mov     r9d, eax; char *
0x18003e0bd  mov     edx, 137h; void *
0x18003e0c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e0c7  lea     rcx, [rsp+280h+var_240]
0x18003e0cc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003e0d1  lea     rcx, [rsp+280h+var_250]
0x18003e0d6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003e0db  mov     eax, ebx
0x18003e0dd  jmp     loc_18003DF5B
0x18003e0e2  mov     rbx, [rsp+280h+var_250]
0x18003e0e7  jmp     loc_18003DFEC
```
