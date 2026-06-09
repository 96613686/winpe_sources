# Microsoft::Diagnostics::ApiServer::GetRpcImpersonationToken(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x1802f2544`
- end: `0x1802f2754`
- name: `?GetRpcImpersonationToken@ApiServer@Diagnostics@Microsoft@@IEBAJAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `528`
- prototype: ``
- caller_count: `8`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1801e5828`
- `0x1801f5de0`
- `0x1801f9dc4`
- `0x1802930c0`
- `0x18029324c`
- `0x180295b60`
- `0x180295d80`
- `0x18029a310`

## callees

- `0x18002cb04`
- `0x18002df00`
- `0x180064e34`
- `0x180064e8c`
- `0x18008abf4`
- `0x1800dce08`
- `0x1800e7994`
- `0x180142fcc`
- `0x1801bbc78`
- `0x18020aac0`
- `0x1802f2544`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802f25cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802f25cc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1802f25c2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1802f25c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1802f25ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1802f25ad`
- `RPCRT4!RpcImpersonateClient` at `0x1802f256f`
- `RPCRT4!RpcImpersonateClient` at `0x1802f256f`
- `RPCRT4!RpcRevertToSelf` at `0x1802f25f1`
- `RPCRT4!RpcRevertToSelf` at `0x1802f2606`
- `RPCRT4!RpcRevertToSelf` at `0x1802f2644`
- `RPCRT4!RpcRevertToSelf` at `0x1802f26a6`
- `RPCRT4!RpcRevertToSelf` at `0x1802f26b4`
- `RPCRT4!RpcRevertToSelf` at `0x1802f25f1`
- `RPCRT4!RpcRevertToSelf` at `0x1802f2606`
- `RPCRT4!RpcRevertToSelf` at `0x1802f2644`
- `RPCRT4!RpcRevertToSelf` at `0x1802f26a6`
- `RPCRT4!RpcRevertToSelf` at `0x1802f26b4`

## string_xrefs

- `0x1802f2586`: `onecore\base\telemetry\utc\common\apiserver.cpp`
- `0x1802f25de`: `onecore\base\telemetry\utc\common\apiserver.cpp`
- `0x1802f26e5`: `onecore\base\telemetry\utc\common\apiserver.cpp`
- `0x1802f26fc`: `onecore\base\telemetry\utc\common\apiserver.cpp`
- `0x1802f2713`: `onecore\base\telemetry\utc\common\apiserver.cpp`
- `0x1802f272a`: `onecore\base\telemetry\utc\common\apiserver.cpp`
- `0x1802f2741`: `onecore\base\telemetry\utc\common\apiserver.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=2
__int64 __fastcall Microsoft::Diagnostics::ApiServer::GetRpcImpersonationToken(__int64 a1, void **a2, _QWORD *a3)
{
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  unsigned int v8; // ebx
  const char *v9; // r9
  const char *v10; // r9
  __int64 SidForToken; // rax
  const char *v12; // r9
  int v13; // r8d
  int v14; // r9d
  const char *v15; // r9
  __int64 v16; // [rsp+20h] [rbp-48h]
  _QWORD *v17; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v18[32]; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    a2,
    0);
  if ( RpcImpersonateClient(0) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16B,
      (unsigned int)"onecore\\base\\telemetry\\utc\\common\\apiserver.cpp",
      (const char *)0x80070005LL,
      v16);
    return 2147942405LL;
  }
  else
  {
    BYTE1(v17) = 1;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      a2,
      0);
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0xEu, 1, a2) )
    {
      SidForToken = Microsoft::Diagnostics::Utils::Os::GetSidForToken(v18, a2);
      std::wstring::operator=(a3, SidForToken);
      std::wstring::_Tidy_deallocate(v18);
      if ( a3[2] )
      {
        if ( (unsigned int)dword_1804543B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 0x2000) )
        {
          if ( a3[3] > 7u )
            a3 = (_QWORD *)*a3;
          v17 = a3;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
            (unsigned int)&dword_1804543B0,
            (unsigned int)&dword_1803FF66C,
            v13,
            v14,
            (__int64)&v17);
        }
        if ( RpcRevertToSelf() )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x176,
            (unsigned int)"onecore\\base\\telemetry\\utc\\common\\apiserver.cpp",
            v15);
        return 0;
      }
      else
      {
        if ( RpcRevertToSelf() )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x176,
            (unsigned int)"onecore\\base\\telemetry\\utc\\common\\apiserver.cpp",
            v12);
        return 1168;
      }
    }
    else
    {
      LastError = GetLastError();
      if ( LastError )
      {
        v8 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x17D,
               (unsigned int)"onecore\\base\\telemetry\\utc\\common\\apiserver.cpp",
               (const char *)LastError,
               v16);
        if ( RpcRevertToSelf() )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x176,
            (unsigned int)"onecore\\base\\telemetry\\utc\\common\\apiserver.cpp",
            v9);
        return v8;
      }
      else
      {
        if ( RpcRevertToSelf() )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x176,
            (unsigned int)"onecore\\base\\telemetry\\utc\\common\\apiserver.cpp",
            v10);
        return 0;
      }
    }
  }
}

```

## disassembly

```asm
0x1802f2544  mov     [rsp+arg_0], rbx
0x1802f2549  push    rdi
0x1802f254a  sub     rsp, 60h
0x1802f254e  mov     rax, cs:__security_cookie
0x1802f2555  xor     rax, rsp
0x1802f2558  mov     [rsp+68h+var_10], rax
0x1802f255d  mov     rbx, r8
0x1802f2560  mov     rdi, rdx
0x1802f2563  xor     edx, edx
0x1802f2565  mov     rcx, rdi
0x1802f2568  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1802f256d  xor     ecx, ecx; BindingHandle
0x1802f256f  call    cs:__imp_RpcImpersonateClient
0x1802f2575  test    eax, eax
0x1802f2577  jz      short loc_1802F259E
0x1802f2579  mov     rcx, [rsp+68h]; this
0x1802f257e  mov     ebx, 80070005h
0x1802f2583  mov     r9d, ebx; char *
0x1802f2586  lea     r8, aOnecoreBaseTel_263; "onecore\\base\\telemetry\\utc\\common\\"...
0x1802f258d  mov     edx, 16Bh; void *
0x1802f2592  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802f2597  mov     eax, ebx
0x1802f2599  jmp     loc_1802F26C8
0x1802f259e  mov     byte ptr [rsp+68h+var_38+1], 1
0x1802f25a3  xor     edx, edx
0x1802f25a5  mov     rcx, rdi
0x1802f25a8  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1802f25ad  call    cs:__imp_GetCurrentThread
0x1802f25b3  mov     r9, rdi; TokenHandle
0x1802f25b6  mov     edx, 0Eh; DesiredAccess
0x1802f25bb  lea     r8d, [rdx-0Dh]; OpenAsSelf
0x1802f25bf  mov     rcx, rax; ThreadHandle
0x1802f25c2  call    cs:__imp_OpenThreadToken
0x1802f25c8  test    eax, eax
0x1802f25ca  jnz     short loc_1802F261B
0x1802f25cc  call    cs:__imp_GetLastError
0x1802f25d2  test    eax, eax
0x1802f25d4  jz      short loc_1802F2606
0x1802f25d6  mov     rcx, [rsp+68h]; this
0x1802f25db  mov     r9d, eax; char *
0x1802f25de  lea     r8, aOnecoreBaseTel_263; "onecore\\base\\telemetry\\utc\\common\\"...
0x1802f25e5  mov     edx, 17Dh; void *
0x1802f25ea  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1802f25ef  mov     ebx, eax
0x1802f25f1  call    cs:__imp_RpcRevertToSelf
0x1802f25f7  test    eax, eax
0x1802f25f9  jnz     loc_1802F26E0
0x1802f25ff  mov     eax, ebx
0x1802f2601  jmp     loc_1802F26C8
0x1802f2606  call    cs:__imp_RpcRevertToSelf
0x1802f260c  test    eax, eax
0x1802f260e  jnz     loc_1802F26F7
0x1802f2614  xor     eax, eax
0x1802f2616  jmp     loc_1802F26C8
0x1802f261b  mov     rdx, rdi
0x1802f261e  lea     rcx, [rsp+68h+var_30]
0x1802f2623  call    ?GetSidForToken@Os@Utils@Diagnostics@Microsoft@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; Microsoft::Diagnostics::Utils::Os::GetSidForToken(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &)
0x1802f2628  mov     rdx, rax
0x1802f262b  mov     rcx, rbx
0x1802f262e  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1802f2633  lea     rcx, [rsp+68h+var_30]
0x1802f2638  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1802f263d  cmp     qword ptr [rbx+10h], 0
0x1802f2642  jnz     short loc_1802F2659
0x1802f2644  call    cs:__imp_RpcRevertToSelf
0x1802f264a  test    eax, eax
0x1802f264c  jnz     loc_1802F270E
0x1802f2652  mov     eax, 490h
0x1802f2657  jmp     short loc_1802F26C8
0x1802f2659  mov     eax, cs:dword_1804543B0
0x1802f265f  cmp     eax, 4
0x1802f2662  jbe     short loc_1802F26A6
0x1802f2664  mov     edx, 2000h
0x1802f2669  lea     rcx, dword_1804543B0
0x1802f2670  call    _tlgKeywordOn
0x1802f2675  test    al, al
0x1802f2677  jz      short loc_1802F26A6
0x1802f2679  cmp     qword ptr [rbx+18h], 7
0x1802f267e  jbe     short loc_1802F2683
0x1802f2680  mov     rbx, [rbx]
0x1802f2683  mov     [rsp+30h], rbx
0x1802f2688  lea     rax, [rsp+68h+var_38]
0x1802f268d  mov     [rsp+68h+var_48], rax
0x1802f2692  lea     rdx, dword_1803FF66C
0x1802f2699  lea     rcx, dword_1804543B0
0x1802f26a0  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x1802f26a5  nop
0x1802f26a6  call    cs:__imp_RpcRevertToSelf
0x1802f26ac  test    eax, eax
0x1802f26ae  jnz     short loc_1802F2725
0x1802f26b0  xor     eax, eax
0x1802f26b2  jmp     short loc_1802F26C8
0x1802f26b4  call    cs:__imp_RpcRevertToSelf
0x1802f26ba  test    eax, eax
0x1802f26bc  jnz     short loc_1802F273C
0x1802f26be  mov     eax, dword ptr [rsp+68h+var_38]
0x1802f26c2  jmp     short loc_1802F26C8
0x1802f26c4  mov     eax, dword ptr [rsp+68h+var_38]
0x1802f26c8  mov     rcx, [rsp+68h+var_10]
0x1802f26cd  xor     rcx, rsp; StackCookie
0x1802f26d0  call    __security_check_cookie
0x1802f26d5  mov     rbx, [rsp+68h+arg_0]
0x1802f26da  add     rsp, 60h
0x1802f26de  pop     rdi
0x1802f26df  retn
0x1802f26e0  mov     rcx, [rsp+68h]; this
0x1802f26e5  lea     r8, aOnecoreBaseTel_263; "onecore\\base\\telemetry\\utc\\common\\"...
0x1802f26ec  mov     edx, 176h; void *
0x1802f26f1  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1802f26f7  mov     rcx, [rsp+68h]; this
0x1802f26fc  lea     r8, aOnecoreBaseTel_263; "onecore\\base\\telemetry\\utc\\common\\"...
0x1802f2703  mov     edx, 176h; void *
0x1802f2708  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1802f270e  mov     rcx, [rsp+68h]; this
0x1802f2713  lea     r8, aOnecoreBaseTel_263; "onecore\\base\\telemetry\\utc\\common\\"...
0x1802f271a  mov     edx, 176h; void *
0x1802f271f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1802f2725  mov     rcx, [rsp+68h]; this
0x1802f272a  lea     r8, aOnecoreBaseTel_263; "onecore\\base\\telemetry\\utc\\common\\"...
0x1802f2731  mov     edx, 176h; void *
0x1802f2736  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1802f273c  mov     rcx, [rsp+68h]; this
0x1802f2741  lea     r8, aOnecoreBaseTel_263; "onecore\\base\\telemetry\\utc\\common\\"...
0x1802f2748  mov     edx, 176h; void *
0x1802f274d  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
