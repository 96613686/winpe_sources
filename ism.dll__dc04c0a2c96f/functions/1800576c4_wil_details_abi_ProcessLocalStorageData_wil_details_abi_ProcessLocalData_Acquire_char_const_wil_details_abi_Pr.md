# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800576c4`
- end: `0x1800578dc`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `536`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180079a04`

## callees

- `0x1800576c4`
- `0x180057a9c`
- `0x180057bec`
- `0x180058078`
- `0x18008db50`
- `0x18008e194`
- `0x18008ead4`
- `0x180099dd4`
- `0x180099df0`
- `0x1800afa30`
- `0x1800f0990`
- `0x1800f4448`
- `0x1800f4b04`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800576ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800576ff`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180057776`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180057776`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180057744`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180057744`

## string_xrefs

- `0x180057791`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  wil::details *v6; // rbx
  unsigned int LastErrorFailHr; // ebx
  DWORD v8; // eax
  bool v9; // dl
  char *v10; // r9
  wil::details *v11; // rdi
  int ValueInternal; // eax
  void *v13; // rdx
  unsigned int v14; // esi
  _DWORD *v15; // rcx
  int v16; // eax
  int v18; // [rsp+20h] [rbp-E0h]
  int v19; // [rsp+20h] [rbp-E0h]
  HANDLE hHandle; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v21; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v22[2]; // [rsp+40h] [rbp-C0h] BYREF
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
  v6 = (wil::details *)hHandle;
  if ( !hHandle )
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_14:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hHandle);
    return LastErrorFailHr;
  }
  v8 = WaitForSingleObjectEx(hHandle, 0xFFFFFFFF, 0);
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
  v22[0] = v11;
  v21 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v9, &v21, (bool *)v10);
  v14 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      120);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v14, v18);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v14, v19);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v22);
    LastErrorFailHr = v14;
    goto LABEL_14;
  }
  v15 = (_DWORD *)(4 * v21);
  if ( 4 * v21 )
  {
    *a2 = v15;
    ++*v15;
  }
  else
  {
    v16 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
    LastErrorFailHr = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x137,
        (unsigned int)"wil",
        (const char *)(unsigned int)v16,
        120);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v22);
      goto LABEL_14;
    }
    v6 = (wil::details *)hHandle;
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
0x1800576c4  mov     [rsp-8+arg_10], rbx
0x1800576c9  mov     [rsp-8+arg_18], rsi
0x1800576ce  push    rbp
0x1800576cf  push    rdi
0x1800576d0  push    r14
0x1800576d2  lea     rbp, [rsp-170h]
0x1800576da  sub     rsp, 270h
0x1800576e1  mov     rax, cs:__security_cookie
0x1800576e8  xor     rax, rsp
0x1800576eb  mov     [rbp+180h+var_20], rax
0x1800576f2  mov     r14, rdx
0x1800576f5  mov     qword ptr [rdx], 0
0x1800576fc  mov     rbx, rcx
0x1800576ff  call    cs:__imp_GetCurrentProcessId
0x180057705  mov     [rsp+280h+var_258], rbx
0x18005770a  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180057711  mov     r9d, eax
0x180057714  mov     [rsp+280h+var_260], 78h ; 'x'; int
0x18005771c  mov     edx, 104h; unsigned __int64
0x180057721  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180057726  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005772b  mov     r9d, 1F0001h; dwDesiredAccess
0x180057731  mov     [rsp+280h+hHandle], 0
0x18005773a  xor     r8d, r8d; dwFlags
0x18005773d  lea     rdx, [rsp+280h+Name]; lpName
0x180057742  xor     ecx, ecx; lpMutexAttributes
0x180057744  call    cs:__imp_CreateMutexExW
0x18005774a  mov     rdx, rax
0x18005774d  lea     rcx, [rsp+280h+hHandle]
0x180057752  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180057757  mov     rbx, [rsp+280h+hHandle]
0x18005775c  test    rbx, rbx
0x18005775f  jnz     short loc_18005776D
0x180057761  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180057766  mov     ebx, eax
0x180057768  jmp     loc_180057886
0x18005776d  xor     r8d, r8d; bAlertable
0x180057770  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180057773  mov     rcx, rbx; hHandle
0x180057776  call    cs:__imp_WaitForSingleObjectEx
0x18005777c  cmp     eax, 102h
0x180057781  jz      short loc_1800577A8
0x180057783  test    eax, 0FFFFFF7Fh
0x180057788  jz      short loc_1800577A3
0x18005778a  mov     rcx, [rbp+188h]; this
0x180057791  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180057798  mov     edx, 0E01h; void *
0x18005779d  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800577a3  mov     rdi, rbx
0x1800577a6  jmp     short loc_1800577AA
0x1800577a8  xor     edi, edi
0x1800577aa  lea     r8, [rsp+280h+var_248]; unsigned __int64 *
0x1800577af  mov     [rsp+280h+var_240], rdi
0x1800577b4  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800577b9  mov     [rsp+280h+var_248], 0
0x1800577c2  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x1800577c7  mov     esi, eax
0x1800577c9  test    eax, eax
0x1800577cb  jns     short loc_18005782C
0x1800577cd  mov     rcx, [rbp+188h]; this
0x1800577d4  lea     r8, aWil; "wil"
0x1800577db  mov     r9d, eax; char *
0x1800577de  mov     edx, 66h ; 'f'; void *
0x1800577e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800577e8  mov     rcx, [rbp+188h]; this
0x1800577ef  lea     r8, aWil; "wil"
0x1800577f6  mov     r9d, esi; char *
0x1800577f9  mov     edx, 6Fh ; 'o'; void *
0x1800577fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180057803  mov     rcx, [rbp+188h]; this
0x18005780a  lea     r8, aWil; "wil"
0x180057811  mov     r9d, esi; char *
0x180057814  mov     edx, 12Eh; void *
0x180057819  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005781e  lea     rcx, [rsp+280h+var_240]
0x180057823  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180057828  mov     ebx, esi
0x18005782a  jmp     short loc_180057886
0x18005782c  mov     rax, [rsp+280h+var_248]
0x180057831  lea     rcx, ds:0[rax*4]
0x180057839  test    rcx, rcx
0x18005783c  jz      short loc_180057849
0x18005783e  mov     [r14], rcx
0x180057841  mov     eax, [rcx]
0x180057843  inc     eax
0x180057845  mov     [rcx], eax
0x180057847  jmp     short loc_180057899
0x180057849  mov     r8, r14
0x18005784c  lea     rdx, [rsp+280h+hHandle]
0x180057851  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180057856  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18005785b  mov     ebx, eax
0x18005785d  test    eax, eax
0x18005785f  jns     short loc_180057894
0x180057861  mov     rcx, [rbp+188h]; this
0x180057868  lea     r8, aWil; "wil"
0x18005786f  mov     r9d, eax; char *
0x180057872  mov     edx, 137h; void *
0x180057877  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005787c  lea     rcx, [rsp+280h+var_240]
0x180057881  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180057886  lea     rcx, [rsp+280h+hHandle]
0x18005788b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180057890  mov     eax, ebx
0x180057892  jmp     short loc_1800578B5
0x180057894  mov     rbx, [rsp+280h+hHandle]
0x180057899  test    rdi, rdi
0x18005789c  jz      short loc_1800578A6
0x18005789e  mov     rcx, rdi; this
0x1800578a1  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x1800578a6  test    rbx, rbx
0x1800578a9  jz      short loc_1800578B3
0x1800578ab  mov     rcx, rbx; this
0x1800578ae  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800578b3  xor     eax, eax
0x1800578b5  mov     rcx, [rbp+180h+var_20]
0x1800578bc  xor     rcx, rsp; StackCookie
0x1800578bf  call    __security_check_cookie
0x1800578c4  lea     r11, [rsp+280h+var_10]
0x1800578cc  mov     rbx, [r11+30h]
0x1800578d0  mov     rsi, [r11+38h]
0x1800578d4  mov     rsp, r11
0x1800578d7  pop     r14
0x1800578d9  pop     rdi
0x1800578da  pop     rbp
0x1800578db  retn
```
