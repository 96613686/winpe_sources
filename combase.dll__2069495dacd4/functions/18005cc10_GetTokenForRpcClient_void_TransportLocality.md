# GetTokenForRpcClient(void *,TransportLocality)

- ea: `0x18005cc10`
- end: `0x18005cde2`
- name: `?GetTokenForRpcClient@@YAPEAXPEAXW4TransportLocality@@@Z`
- size: `466`
- prototype: `void *__fastcall(void *hRpc, TransportLocality locality)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180165ef0`

## callees

- `0x18000712c`
- `0x18000833c`
- `0x18005a880`
- `0x18005b528`
- `0x18005cc10`
- `0x18005cde8`
- `0x18005ce60`
- `0x18005ce9c`
- `0x1800b4c18`
- `0x18018909c`

## import_xrefs

- `RPCRT4!RpcRevertToSelfEx` at `0x18005ccce`
- `RPCRT4!RpcRevertToSelfEx` at `0x18024757d`
- `RPCRT4!RpcRevertToSelfEx` at `0x18005ccce`
- `RPCRT4!RpcRevertToSelfEx` at `0x18024757d`
- `RPCRT4!RpcImpersonateClient` at `0x18005cc81`
- `RPCRT4!RpcImpersonateClient` at `0x18005cc81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cd48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cd77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cd48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cd77`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005cd5b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005cd5b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005cd3d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005cd53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005cd66`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005cd3d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005cd53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005cd66`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005cca5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005cd88`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1802475ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18024760f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180247647`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005cca5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005cd88`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1802475ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18024760f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180247647`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005ccbd`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1802475d2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18024765f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005ccbd`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1802475d2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18024765f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180247574`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18024759a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1802475dc`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18024766d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180247574`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18024759a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1802475dc`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18024766d`
- `api-ms-win-security-base-l1-1-0!ImpersonateAnonymousToken` at `0x18005cd91`
- `api-ms-win-security-base-l1-1-0!ImpersonateAnonymousToken` at `0x180247618`
- `api-ms-win-security-base-l1-1-0!ImpersonateAnonymousToken` at `0x18005cd91`
- `api-ms-win-security-base-l1-1-0!ImpersonateAnonymousToken` at `0x180247618`

## string_xrefs

- `0x18005cc4c`: `onecore\com\combase\dcomrem\security.cxx`
- `0x18005cd0e`: `onecore\com\combase\dcomrem\security.cxx`
- `0x180247551`: `onecore\com\combase\dcomrem\security.cxx`
- `0x180247563`: `onecore\com\combase\dcomrem\security.cxx`
- `0x180247589`: `onecore\com\combase\dcomrem\security.cxx`
- `0x1802475f6`: `onecore\com\combase\dcomrem\security.cxx`
- `0x180247626`: `onecore\com\combase\dcomrem\security.cxx`

## pseudocode

```c
void *__fastcall GetTokenForRpcClient(void *hRpc, TransportLocality locality)
{
  HRESULT v4; // eax
  RPC_STATUS v6; // eax
  void *m_ptr; // rsi
  HANDLE v8; // rax
  void *v9; // rbx
  DWORD LastError; // ebx
  HANDLE v11; // rax
  unsigned int v12; // edx
  HANDLE v13; // rax
  HANDLE CurrentThread; // rax
  HANDLE v15; // rax
  void *retaddr; // [rsp+38h] [rbp+18h]
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (__cdecl*)(void *),&CloseHandle> > > clientToken; // [rsp+50h] [rbp+30h] BYREF
  void *hSave; // [rsp+58h] [rbp+38h] BYREF

  clientToken.m_ptr = 0;
  hSave = 0;
  v4 = SuspendImpersonate(&hSave);
  if ( v4 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(retaddr, 0x7B4u, "onecore\\com\\combase\\dcomrem\\security.cxx", v4);
LABEL_3:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (__cdecl*)(void *),&CloseHandle> > *)&clientToken);
    return 0;
  }
  v6 = RpcImpersonateClient(hRpc);
  if ( v6 )
  {
    if ( v6 != 1764 )
    {
      wil::details::in1diag3::Log_Win32(retaddr, 0x7FAu, "onecore\\com\\combase\\dcomrem\\security.cxx", v6);
      ResumeImpersonate(hSave);
      if ( (unsigned __int64)clientToken.m_ptr - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(clientToken.m_ptr);
      return 0;
    }
    if ( !gAnonymousAccessAllowed && !gfLogCallFailure && (!gEnableContainerDCOM || gIncomingContainerAuthnSvc) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( locality )
    {
      CurrentThread = GetCurrentThread();
      if ( ImpersonateAnonymousToken(CurrentThread) )
      {
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          &clientToken,
          0);
        v15 = GetCurrentThread();
        if ( OpenThreadToken(v15, 0x20008u, 1, &clientToken.m_ptr) )
        {
          RevertToSelf();
          goto LABEL_10;
        }
        wil::details::in1diag3::_Log_GetLastError(retaddr, 0x7F4u, "onecore\\com\\combase\\dcomrem\\security.cxx");
        RevertToSelf();
      }
      else
      {
        wil::details::in1diag3::_Log_GetLastError(retaddr, 0x7ECu, "onecore\\com\\combase\\dcomrem\\security.cxx");
      }
    }
    else
    {
      wil::details::in1diag3::Log_Hr(retaddr, 0x7E6u, "onecore\\com\\combase\\dcomrem\\security.cxx", -2147024891);
    }
LABEL_30:
    ResumeImpersonate(hSave);
    goto LABEL_3;
  }
  m_ptr = clientToken.m_ptr;
  if ( (unsigned __int64)clientToken.m_ptr - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    CloseHandle(m_ptr);
    SetLastError(LastError);
  }
  clientToken.m_ptr = 0;
  v8 = GetCurrentThread();
  if ( OpenThreadToken(v8, 0x20008u, 1, &clientToken.m_ptr) )
    goto LABEL_9;
  if ( locality || GetLastError() != 1347 )
  {
    v12 = 2008;
    goto LABEL_26;
  }
  v11 = GetCurrentThread();
  if ( !ImpersonateAnonymousToken(v11) )
  {
    v12 = 1994;
LABEL_26:
    wil::details::in1diag3::_Log_GetLastError(retaddr, v12, "onecore\\com\\combase\\dcomrem\\security.cxx");
LABEL_28:
    RpcRevertToSelfEx(hRpc);
    goto LABEL_30;
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &clientToken,
    0);
  v13 = GetCurrentThread();
  if ( !OpenThreadToken(v13, 0x20008u, 1, &clientToken.m_ptr) )
  {
    wil::details::in1diag3::_Log_GetLastError(retaddr, 0x7D2u, "onecore\\com\\combase\\dcomrem\\security.cxx");
    RevertToSelf();
    goto LABEL_28;
  }
  RevertToSelf();
LABEL_9:
  RpcRevertToSelfEx(hRpc);
LABEL_10:
  v9 = clientToken.m_ptr;
  clientToken.m_ptr = 0;
  ResumeImpersonate(hSave);
  if ( (unsigned __int64)clientToken.m_ptr - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(clientToken.m_ptr);
  return v9;
}

```

## disassembly

```asm
0x18005cc10  mov     [rsp-18h+arg_0], rbx
0x18005cc15  mov     [rsp-18h+arg_8], rsi
0x18005cc1a  push    rbp
0x18005cc1b  push    rdi
0x18005cc1c  push    r14
0x18005cc1e  mov     rbp, rsp
0x18005cc21  sub     rsp, 20h
0x18005cc25  mov     rdi, hRpc
0x18005cc28  mov     [rbp+clientToken.m_ptr], 0
0x18005cc30  lea     hRpc, [rbp+hSave]; pHandle
0x18005cc34  mov     [rbp+hSave], 0
0x18005cc3c  mov     r14d, locality
0x18005cc3f  call    ?SuspendImpersonate@@YAJPEAPEAX@Z; SuspendImpersonate(void * *)
0x18005cc44  test    eax, eax
0x18005cc46  jns     short loc_18005CC7E
0x18005cc48  mov     hRpc, [rbp+18h]; callerReturnAddress
0x18005cc4c  lea     r8, fileName; "onecore\\com\\combase\\dcomrem\\securit"...
0x18005cc53  mov     r9d, eax; hr
0x18005cc56  mov     locality, 7B4h; lineNumber
0x18005cc5b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005cc60  lea     hRpc, [rbp+clientToken]; this
0x18005cc64  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18005cc69  xor     eax, eax
0x18005cc6b  mov     rbx, [rsp+20h+arg_0]
0x18005cc70  mov     rsi, [rsp+20h+arg_8]
0x18005cc75  add     rsp, 20h
0x18005cc79  pop     r14
0x18005cc7b  pop     rdi
0x18005cc7c  pop     rbp
0x18005cc7d  retn
0x18005cc7e  mov     hRpc, rdi; BindingHandle
0x18005cc81  call    cs:__imp_RpcImpersonateClient
0x18005cc87  test    eax, eax
0x18005cc89  jnz     short loc_18005CCFF
0x18005cc8b  mov     rsi, [rbp+clientToken.m_ptr]
0x18005cc8f  lea     rax, [rsi-1]
0x18005cc93  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005cc97  jbe     loc_18005CD48
0x18005cc9d  mov     [rbp+clientToken.m_ptr], 0
0x18005cca5  call    cs:__imp_GetCurrentThread
0x18005ccab  lea     r9, [rbp+clientToken]; TokenHandle
0x18005ccaf  mov     locality, 20008h; DesiredAccess
0x18005ccb4  mov     hRpc, rax; ThreadHandle
0x18005ccb7  mov     r8d, 1; OpenAsSelf
0x18005ccbd  call    cs:__imp_OpenThreadToken
0x18005ccc3  test    eax, eax
0x18005ccc5  jz      loc_18005CD6E
0x18005cccb  mov     hRpc, rdi; BindingHandle
0x18005ccce  call    cs:__imp_RpcRevertToSelfEx
0x18005ccd4  mov     rbx, [rbp+clientToken.m_ptr]
0x18005ccd8  mov     hRpc, [rbp+hSave]; hToken
0x18005ccdc  mov     [rbp+clientToken.m_ptr], 0
0x18005cce4  call    ?ResumeImpersonate@@YAXPEAX@Z; ResumeImpersonate(void *)
0x18005cce9  mov     hRpc, [rbp+clientToken.m_ptr]; hObject
0x18005cced  lea     rdx, [hRpc-1]
0x18005ccf1  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18005ccf5  jbe     short loc_18005CD66
0x18005ccf7  mov     rax, rbx
0x18005ccfa  jmp     loc_18005CC6B
0x18005ccff  cmp     eax, 6E4h
0x18005cd04  jz      loc_18005CDA9
0x18005cd0a  mov     hRpc, [rbp+18h]; callerReturnAddress
0x18005cd0e  lea     r8, fileName; "onecore\\com\\combase\\dcomrem\\securit"...
0x18005cd15  mov     r9d, eax; err
0x18005cd18  mov     locality, 7FAh; lineNumber
0x18005cd1d  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18005cd22  mov     hRpc, [rbp+hSave]; hToken
0x18005cd26  call    ?ResumeImpersonate@@YAXPEAX@Z; ResumeImpersonate(void *)
0x18005cd2b  mov     hRpc, [rbp+clientToken.m_ptr]; hObject
0x18005cd2f  lea     rax, [hRpc-1]
0x18005cd33  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005cd37  ja      loc_18005CC69
0x18005cd3d  call    cs:__imp_CloseHandle
0x18005cd43  jmp     loc_18005CC69
0x18005cd48  call    cs:__imp_GetLastError
0x18005cd4e  mov     hRpc, rsi; hObject
0x18005cd51  mov     ebx, eax
0x18005cd53  call    cs:__imp_CloseHandle
0x18005cd59  mov     ecx, ebx; dwErrCode
0x18005cd5b  call    cs:__imp_SetLastError
0x18005cd61  jmp     loc_18005CC9D
0x18005cd66  call    cs:__imp_CloseHandle
0x18005cd6c  jmp     short loc_18005CCF7
0x18005cd6e  test    r14d, r14d
0x18005cd71  jnz     loc_180247548
0x18005cd77  call    cs:__imp_GetLastError
0x18005cd7d  cmp     eax, 543h
0x18005cd82  jnz     loc_180247548
0x18005cd88  call    cs:__imp_GetCurrentThread
0x18005cd8e  mov     hRpc, rax; ThreadHandle
0x18005cd91  call    cs:__imp_ImpersonateAnonymousToken
0x18005cd97  test    eax, eax
0x18005cd99  jnz     loc_1802475AF
0x18005cd9f  mov     locality, 7CAh
0x18005cda4  jmp     loc_18024754D
0x18005cda9  cmp     cs:?gAnonymousAccessAllowed@@3HA, 0; int gAnonymousAccessAllowed
0x18005cdb0  jnz     loc_1802475ED
0x18005cdb6  cmp     cs:?gfLogCallFailure@@3HA, 0; int gfLogCallFailure
0x18005cdbd  jnz     loc_1802475ED
0x18005cdc3  cmp     cs:?gEnableContainerDCOM@@3HA, 0; int gEnableContainerDCOM
0x18005cdca  jz      loc_1802475E8
0x18005cdd0  cmp     cs:?gIncomingContainerAuthnSvc@@3KA, 0; ulong gIncomingContainerAuthnSvc
0x18005cdd7  jnz     loc_1802475E8
0x18005cddd  jmp     loc_1802475ED
0x180247548  mov     edx, 7D8h; lineNumber
0x18024754d  mov     rcx, [rbp+18h]; callerReturnAddress
0x180247551  lea     r8, fileName; "onecore\\com\\combase\\dcomrem\\securit"...
0x180247558  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18024755d  jmp     short loc_18024757A
0x18024755f  mov     rcx, [rbp+18h]; callerReturnAddress
0x180247563  lea     r8, fileName; "onecore\\com\\combase\\dcomrem\\securit"...
0x18024756a  mov     edx, 7D2h; lineNumber
0x18024756f  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180247574  call    cs:__imp_RevertToSelf
0x18024757a  mov     rcx, rdi; BindingHandle
0x18024757d  call    cs:__imp_RpcRevertToSelfEx
0x180247583  jmp     short loc_1802475A0
0x180247585  mov     rcx, [rbp+18h]; callerReturnAddress
0x180247589  lea     r8, fileName; "onecore\\com\\combase\\dcomrem\\securit"...
0x180247590  mov     edx, 7F4h; lineNumber
0x180247595  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18024759a  call    cs:__imp_RevertToSelf
0x1802475a0  mov     rcx, [rbp+hSave]; hToken
0x1802475a4  call    ?ResumeImpersonate@@YAXPEAX@Z; ResumeImpersonate(void *)
0x1802475a9  nop
0x1802475aa  jmp     loc_18005CC60
0x1802475af  xor     edx, edx; ptr
0x1802475b1  lea     rcx, [rbp+clientToken]; this
0x1802475b5  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1802475ba  call    cs:__imp_GetCurrentThread
0x1802475c0  lea     r9, [rbp+clientToken]; TokenHandle
0x1802475c4  mov     edx, 20008h; DesiredAccess
0x1802475c9  mov     rcx, rax; ThreadHandle
0x1802475cc  mov     r8d, 1; OpenAsSelf
0x1802475d2  call    cs:__imp_OpenThreadToken
0x1802475d8  test    eax, eax
0x1802475da  jz      short loc_18024755F
0x1802475dc  call    cs:__imp_RevertToSelf
0x1802475e2  nop
0x1802475e3  jmp     loc_18005CCCB
0x1802475e8  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "gAnonymousAccessAllowed || gfLogCallFailure || (gEnableContainerDCOM && gIncomingContainerAuthnSvc == RPC_C_AUTHN_NONE)")
0x1802475ed  test    r14d, r14d
0x1802475f0  jnz     short loc_18024760F
0x1802475f2  mov     rcx, [rbp+18h]; callerReturnAddress
0x1802475f6  lea     r8, fileName; "onecore\\com\\combase\\dcomrem\\securit"...
0x1802475fd  mov     r9d, 80070005h; hr
0x180247603  mov     edx, 7E6h; lineNumber
0x180247608  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18024760d  jmp     short loc_1802475A0
0x18024760f  call    cs:__imp_GetCurrentThread
0x180247615  mov     rcx, rax; ThreadHandle
0x180247618  call    cs:__imp_ImpersonateAnonymousToken
0x18024761e  test    eax, eax
0x180247620  jnz     short loc_18024763C
0x180247622  mov     rcx, [rbp+18h]; callerReturnAddress
0x180247626  lea     r8, fileName; "onecore\\com\\combase\\dcomrem\\securit"...
0x18024762d  mov     edx, 7ECh; lineNumber
0x180247632  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180247637  jmp     loc_1802475A0
0x18024763c  xor     edx, edx; ptr
0x18024763e  lea     rcx, [rbp+clientToken]; this
0x180247642  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180247647  call    cs:__imp_GetCurrentThread
0x18024764d  lea     r9, [rbp+clientToken]; TokenHandle
0x180247651  mov     edx, 20008h; DesiredAccess
0x180247656  mov     rcx, rax; ThreadHandle
0x180247659  mov     r8d, 1; OpenAsSelf
0x18024765f  call    cs:__imp_OpenThreadToken
0x180247665  test    eax, eax
0x180247667  jz      loc_180247585
0x18024766d  call    cs:__imp_RevertToSelf
0x180247673  nop
0x180247674  jmp     loc_18005CCD4
```
