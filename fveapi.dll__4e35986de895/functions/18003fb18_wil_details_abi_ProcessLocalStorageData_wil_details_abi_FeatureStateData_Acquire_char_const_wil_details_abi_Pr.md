# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x18003fb18`
- end: `0x18003fd0f`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `503`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18003fac0`

## callees

- `0x18000aae0`
- `0x18003fb18`
- `0x18003fd9c`
- `0x180040240`
- `0x18004845c`
- `0x18004c678`
- `0x18004d984`
- `0x18004d9a4`
- `0x18004f1b8`
- `0x18006141c`
- `0x180061e84`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18003fbc1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18003fbc1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18003fb95`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18003fb95`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003fb53`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003fb53`

## string_xrefs

- `0x18003fbe2`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  wil::details *v11; // rsi
  int ValueInternal; // eax
  void *v13; // rdx
  unsigned int v14; // edi
  unsigned __int64 v15; // r9
  __int64 v16; // rdx
  _DWORD *v17; // rcx
  int v18; // eax
  int v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+20h] [rbp-E0h]
  wil::details *v21; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v23; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v19 = 304;
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
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v20);
    v15 = v14;
    v16 = 302;
LABEL_14:
    wil::details::in1diag3::Return_Hr(retaddr, (void *)v16, (unsigned int)"wil", (const char *)v15, v19);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
    return v14;
  }
  v17 = (_DWORD *)(4 * v22);
  if ( 4 * v22 )
  {
    *a2 = v17;
    ++*v17;
  }
  else
  {
    v18 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
    v14 = v18;
    if ( v18 < 0 )
    {
      v15 = (unsigned int)v18;
      v16 = 311;
      goto LABEL_14;
    }
    v6 = v21;
  }
  if ( v11 )
    wil::details::ReleaseMutex(v11, v13);
  if ( v6 )
    wil::details::CloseHandle(v6, v13);
  return 0;
}

```

## disassembly

```asm
0x18003fb18  mov     [rsp-8+arg_10], rbx
0x18003fb1d  mov     [rsp-8+arg_18], rsi
0x18003fb22  push    rbp
0x18003fb23  push    rdi
0x18003fb24  push    r14
0x18003fb26  lea     rbp, [rsp-170h]
0x18003fb2e  sub     rsp, 270h
0x18003fb35  mov     rax, cs:__security_cookie
0x18003fb3c  xor     rax, rsp
0x18003fb3f  mov     [rbp+180h+var_20], rax
0x18003fb46  mov     r14, rdx
0x18003fb49  mov     qword ptr [rdx], 0
0x18003fb50  mov     rbx, rcx
0x18003fb53  call    cs:__imp_GetCurrentProcessId
0x18003fb5a  nop     dword ptr [rax+rax+00h]
0x18003fb5f  mov     [rsp+280h+var_258], rbx
0x18003fb64  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18003fb6b  mov     r9d, eax
0x18003fb6e  mov     [rsp+280h+var_260], 130h; int
0x18003fb76  mov     edx, 104h; unsigned __int64
0x18003fb7b  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18003fb80  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003fb85  mov     r9d, 1F0001h; dwDesiredAccess
0x18003fb8b  lea     rdx, [rsp+280h+Name]; lpName
0x18003fb90  xor     r8d, r8d; dwFlags
0x18003fb93  xor     ecx, ecx; lpMutexAttributes
0x18003fb95  call    cs:__imp_CreateMutexExW
0x18003fb9c  nop     dword ptr [rax+rax+00h]
0x18003fba1  mov     [rsp+280h+var_250], rax
0x18003fba6  mov     rbx, rax
0x18003fba9  test    rax, rax
0x18003fbac  jnz     short loc_18003FBB8
0x18003fbae  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18003fbb3  jmp     loc_18003FCE7
0x18003fbb8  xor     r8d, r8d; bAlertable
0x18003fbbb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18003fbbe  mov     rcx, rbx; hHandle
0x18003fbc1  call    cs:__imp_WaitForSingleObjectEx
0x18003fbc8  nop     dword ptr [rax+rax+00h]
0x18003fbcd  cmp     eax, 102h
0x18003fbd2  jz      short loc_18003FBF9
0x18003fbd4  test    eax, 0FFFFFF7Fh
0x18003fbd9  jz      short loc_18003FBF4
0x18003fbdb  mov     rcx, [rbp+188h]; this
0x18003fbe2  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003fbe9  mov     edx, 0E01h; void *
0x18003fbee  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18003fbf4  mov     rsi, rbx
0x18003fbf7  jmp     short loc_18003FBFB
0x18003fbf9  xor     esi, esi
0x18003fbfb  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x18003fc00  mov     [rsp+280h+var_240], rsi
0x18003fc05  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18003fc0a  mov     [rsp+280h+var_248], 0
0x18003fc13  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18003fc18  mov     edi, eax
0x18003fc1a  test    eax, eax
0x18003fc1c  jns     short loc_18003FC5E
0x18003fc1e  mov     rcx, [rbp+188h]; this
0x18003fc25  lea     r8, aWil; "wil"
0x18003fc2c  mov     r9d, eax; char *
0x18003fc2f  mov     edx, 66h ; 'f'; void *
0x18003fc34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003fc39  mov     rcx, [rbp+188h]; this
0x18003fc40  lea     r8, aWil; "wil"
0x18003fc47  mov     r9d, edi; char *
0x18003fc4a  mov     edx, 6Fh ; 'o'; void *
0x18003fc4f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003fc54  mov     r9d, edi
0x18003fc57  mov     edx, 12Eh
0x18003fc5c  jmp     short loc_18003FC9B
0x18003fc5e  mov     rax, [rsp+280h+var_248]
0x18003fc63  lea     rcx, ds:0[rax*4]
0x18003fc6b  test    rcx, rcx
0x18003fc6e  jz      short loc_18003FC7B
0x18003fc70  mov     [r14], rcx
0x18003fc73  mov     eax, [rcx]
0x18003fc75  inc     eax
0x18003fc77  mov     [rcx], eax
0x18003fc79  jmp     short loc_18003FCCB
0x18003fc7b  mov     r8, r14
0x18003fc7e  lea     rdx, [rsp+280h+var_250]
0x18003fc83  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18003fc88  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18003fc8d  mov     edi, eax
0x18003fc8f  test    eax, eax
0x18003fc91  jns     short loc_18003FCC6
0x18003fc93  mov     r9d, eax; char *
0x18003fc96  mov     edx, 137h; void *
0x18003fc9b  mov     rcx, [rbp+188h]; this
0x18003fca2  lea     r8, aWil; "wil"
0x18003fca9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003fcae  lea     rcx, [rsp+280h+var_240]
0x18003fcb3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003fcb8  lea     rcx, [rsp+280h+var_250]
0x18003fcbd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003fcc2  mov     eax, edi
0x18003fcc4  jmp     short loc_18003FCE7
0x18003fcc6  mov     rbx, [rsp+280h+var_250]
0x18003fccb  test    rsi, rsi
0x18003fcce  jz      short loc_18003FCD8
0x18003fcd0  mov     rcx, rsi; this
0x18003fcd3  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18003fcd8  test    rbx, rbx
0x18003fcdb  jz      short loc_18003FCE5
0x18003fcdd  mov     rcx, rbx; this
0x18003fce0  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18003fce5  xor     eax, eax
0x18003fce7  mov     rcx, [rbp+180h+var_20]
0x18003fcee  xor     rcx, rsp; StackCookie
0x18003fcf1  call    __security_check_cookie
0x18003fcf6  lea     r11, [rsp+280h+var_10]
0x18003fcfe  mov     rbx, [r11+30h]
0x18003fd02  mov     rsi, [r11+38h]
0x18003fd06  mov     rsp, r11
0x18003fd09  pop     r14
0x18003fd0b  pop     rdi
0x18003fd0c  pop     rbp
0x18003fd0d  retn
```
