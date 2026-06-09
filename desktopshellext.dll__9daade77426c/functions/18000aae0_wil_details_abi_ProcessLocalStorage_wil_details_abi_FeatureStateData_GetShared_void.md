# wil::details_abi::ProcessLocalStorage<wil::details_abi::FeatureStateData>::GetShared(void)

- ea: `0x18000aae0`
- end: `0x18000ad1f`
- name: `?GetShared@?$ProcessLocalStorage@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAPEAVFeatureStateData@23@XZ`
- size: `575`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180005750`
- `0x180007ab0`
- `0x180015e30`

## callees

- `0x18000aae0`
- `0x18000aeb0`
- `0x18000af40`
- `0x18000b4c0`
- `0x18000b4f0`
- `0x18001091c`
- `0x180017988`
- `0x180023214`
- `0x18002a3d0`
- `0x18002d848`
- `0x18002ed24`
- `0x180030f60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000ab4e`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000ab4e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000abad`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000abad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000ab12`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000ab12`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000acf7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000acf7`

## string_xrefs

- `0x18000abc9`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18000ad0d`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorage<wil::details_abi::FeatureStateData>::GetShared(__int64 a1)
{
  _DWORD *v2; // rsi
  DWORD CurrentProcessId; // eax
  wil::details *Mutex; // rax
  wil::details *v5; // rcx
  wil::details *v6; // rbx
  __int64 v7; // rdx
  __int64 result; // rax
  DWORD v9; // eax
  __int64 v10; // rdx
  char *v11; // r9
  wil::details *v12; // rbp
  int ValueInternal; // eax
  void *v14; // rdx
  unsigned int v15; // esi
  void *v16; // rdx
  int v17; // eax
  void *v18; // rdx
  const char *v19; // r9
  int v20; // [rsp+20h] [rbp-278h]
  int v21; // [rsp+20h] [rbp-278h]
  wil::details *v22; // [rsp+30h] [rbp-268h] BYREF
  unsigned __int64 v23; // [rsp+38h] [rbp-260h] BYREF
  _DWORD *v24; // [rsp+40h] [rbp-258h]
  WCHAR Name[264]; // [rsp+50h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+0h]

  if ( *(_QWORD *)(a1 + 8) )
    goto LABEL_6;
  v2 = 0;
  v24 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  Mutex = (wil::details *)CreateMutexExW(0, Name, 0, 0x1F0001u);
  v22 = Mutex;
  v6 = Mutex;
  if ( !Mutex )
  {
    if ( (int)wil::details::GetLastErrorFailHr(v5) < 0 )
      goto LABEL_6;
    goto LABEL_4;
  }
  v9 = WaitForSingleObjectEx(Mutex, 0xFFFFFFFF, 0);
  if ( v9 == 258 )
  {
    v12 = 0;
  }
  else
  {
    if ( (v9 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
        v11);
    v12 = v6;
  }
  v23 = 0;
  ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v10, &v23, (bool *)v11);
  v15 = ValueInternal;
  if ( ValueInternal < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueInternal,
      304);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, (unsigned int)"wil", (const char *)v15, v20);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, (unsigned int)"wil", (const char *)v15, v21);
    if ( v12 )
      wil::details::ReleaseMutex(v12, v16);
    wil::details::CloseHandle(v6, v16);
    goto LABEL_6;
  }
  v2 = (_DWORD *)(4 * v23);
  if ( 4 * v23 )
  {
    ++*v2;
LABEL_25:
    if ( v12 )
      wil::details::ReleaseMutex(v12, v14);
    if ( v6 && !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
        v19);
LABEL_4:
    if ( !*(_QWORD *)(a1 + 8) )
      *(_QWORD *)(a1 + 8) = v2;
    goto LABEL_6;
  }
  v17 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
  if ( v17 >= 0 )
  {
    v2 = v24;
    v6 = v22;
    goto LABEL_25;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, (unsigned int)"wil", (const char *)(unsigned int)v17, 304);
  if ( v12 )
    wil::details::ReleaseMutex(v12, v18);
  __1__unique_any_t_V__mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAA_XZ(&v22);
LABEL_6:
  v7 = *(_QWORD *)(a1 + 8);
  result = v7 + 32;
  if ( !v7 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x18000aae0  push    rbx
0x18000aae2  push    rbp
0x18000aae3  push    rsi
0x18000aae4  push    rdi
0x18000aae5  sub     rsp, 278h
0x18000aaec  mov     rax, cs:__security_cookie
0x18000aaf3  xor     rax, rsp
0x18000aaf6  mov     [rsp+298h+var_38], rax
0x18000aafe  cmp     qword ptr [rcx+8], 0
0x18000ab03  mov     rdi, rcx
0x18000ab06  jnz     short loc_18000AB75
0x18000ab08  mov     rbx, [rcx]
0x18000ab0b  xor     esi, esi
0x18000ab0d  mov     [rsp+298h+var_258], rsi
0x18000ab12  call    cs:__imp_GetCurrentProcessId
0x18000ab18  mov     [rsp+298h+var_270], rbx
0x18000ab1d  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000ab24  mov     r9d, eax
0x18000ab27  mov     [rsp+298h+var_278], 130h; int
0x18000ab2f  mov     edx, 104h; unsigned __int64
0x18000ab34  lea     rcx, [rsp+298h+Name]; unsigned __int16 *
0x18000ab39  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000ab3e  mov     r9d, 1F0001h; dwDesiredAccess
0x18000ab44  lea     rdx, [rsp+298h+Name]; lpName
0x18000ab49  xor     r8d, r8d; dwFlags
0x18000ab4c  xor     ecx, ecx; lpMutexAttributes
0x18000ab4e  call    cs:__imp_CreateMutexExW
0x18000ab54  mov     [rsp+298h+var_268], rax
0x18000ab59  mov     rbx, rax
0x18000ab5c  test    rax, rax
0x18000ab5f  jnz     short loc_18000ABA2
0x18000ab61  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000ab66  test    eax, eax
0x18000ab68  js      short loc_18000AB75
0x18000ab6a  cmp     qword ptr [rdi+8], 0
0x18000ab6f  jnz     short loc_18000AB75
0x18000ab71  mov     [rdi+8], rsi
0x18000ab75  mov     rdx, [rdi+8]
0x18000ab79  xor     ecx, ecx
0x18000ab7b  test    rdx, rdx
0x18000ab7e  lea     rax, [rdx+20h]
0x18000ab82  cmovz   rax, rcx
0x18000ab86  mov     rcx, [rsp+298h+var_38]
0x18000ab8e  xor     rcx, rsp; StackCookie
0x18000ab91  call    __security_check_cookie
0x18000ab96  add     rsp, 278h
0x18000ab9d  pop     rdi
0x18000ab9e  pop     rsi
0x18000ab9f  pop     rbp
0x18000aba0  pop     rbx
0x18000aba1  retn
0x18000aba2  xor     r8d, r8d; bAlertable
0x18000aba5  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x18000abaa  mov     rcx, rbx; hHandle
0x18000abad  call    cs:__imp_WaitForSingleObjectEx
0x18000abb3  cmp     eax, 102h
0x18000abb8  jz      short loc_18000ABE0
0x18000abba  test    eax, 0FFFFFF7Fh
0x18000abbf  jz      short loc_18000ABDB
0x18000abc1  mov     rcx, [rsp+298h]; this
0x18000abc9  lea     r8, aOnecoreInterna_17; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000abd0  mov     edx, 0E01h; void *
0x18000abd5  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000abdb  mov     rbp, rbx
0x18000abde  jmp     short loc_18000ABE2
0x18000abe0  xor     ebp, ebp
0x18000abe2  lea     r8, [rsp+298h+var_260]; unsigned __int64 *
0x18000abe7  mov     [rsp+298h+var_260], rsi
0x18000abec  lea     rcx, [rsp+298h+Name]; unsigned __int16 *
0x18000abf1  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x18000abf6  mov     esi, eax
0x18000abf8  test    eax, eax
0x18000abfa  jns     short loc_18000AC6A
0x18000abfc  mov     rcx, [rsp+298h]; this
0x18000ac04  lea     r8, aWil; "wil"
0x18000ac0b  mov     r9d, eax; char *
0x18000ac0e  mov     edx, 66h ; 'f'; void *
0x18000ac13  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ac18  mov     rcx, [rsp+298h]; this
0x18000ac20  lea     r8, aWil; "wil"
0x18000ac27  mov     r9d, esi; char *
0x18000ac2a  mov     edx, 6Fh ; 'o'; void *
0x18000ac2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ac34  mov     rcx, [rsp+298h]; this
0x18000ac3c  lea     r8, aWil; "wil"
0x18000ac43  mov     r9d, esi; char *
0x18000ac46  mov     edx, 12Eh; void *
0x18000ac4b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ac50  test    rbp, rbp
0x18000ac53  jz      short loc_18000AC5D
0x18000ac55  mov     rcx, rbp; this
0x18000ac58  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18000ac5d  mov     rcx, rbx; this
0x18000ac60  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000ac65  jmp     loc_18000AB75
0x18000ac6a  mov     rax, [rsp+298h+var_260]
0x18000ac6f  lea     rsi, ds:0[rax*4]
0x18000ac77  test    rsi, rsi
0x18000ac7a  jz      short loc_18000AC84
0x18000ac7c  mov     eax, [rsi]
0x18000ac7e  inc     eax
0x18000ac80  mov     [rsi], eax
0x18000ac82  jmp     short loc_18000ACDE
0x18000ac84  lea     r8, [rsp+298h+var_258]
0x18000ac89  lea     rdx, [rsp+298h+var_268]
0x18000ac8e  lea     rcx, [rsp+298h+Name]; unsigned __int16 *
0x18000ac93  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000ac98  test    eax, eax
0x18000ac9a  jns     short loc_18000ACD4
0x18000ac9c  mov     rcx, [rsp+298h]; this
0x18000aca4  lea     r8, aWil; "wil"
0x18000acab  mov     r9d, eax; char *
0x18000acae  mov     edx, 137h; void *
0x18000acb3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000acb8  test    rbp, rbp
0x18000acbb  jz      short loc_18000ACC5
0x18000acbd  mov     rcx, rbp; this
0x18000acc0  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18000acc5  lea     rcx, [rsp+298h+var_268]
0x18000acca  call    ??1?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAA@XZ
0x18000accf  jmp     loc_18000AB75
0x18000acd4  mov     rsi, [rsp+298h+var_258]
0x18000acd9  mov     rbx, [rsp+298h+var_268]
0x18000acde  test    rbp, rbp
0x18000ace1  jz      short loc_18000ACEB
0x18000ace3  mov     rcx, rbp; this
0x18000ace6  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18000aceb  test    rbx, rbx
0x18000acee  jz      loc_18000AB6A
0x18000acf4  mov     rcx, rbx; hObject
0x18000acf7  call    cs:__imp_CloseHandle
0x18000acfd  test    eax, eax
0x18000acff  jnz     loc_18000AB6A
0x18000ad05  mov     rcx, [rsp+298h]; this
0x18000ad0d  lea     r8, aOnecoreInterna_17; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000ad14  mov     edx, 0A0Bh; void *
0x18000ad19  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
