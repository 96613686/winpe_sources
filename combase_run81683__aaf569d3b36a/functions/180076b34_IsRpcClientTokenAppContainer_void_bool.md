# IsRpcClientTokenAppContainer(void *,bool *)

- ea: `0x180076b34`
- end: `0x180076cb7`
- name: `?IsRpcClientTokenAppContainer@@YAJPEAXPEA_N@Z`
- size: `387`
- prototype: `HRESULT __fastcall(void *hRpcServerCall, bool *pbClientIsAppContainer)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180076720`
- `0x1800768b0`
- `0x1800e1718`

## callees

- `0x18005cde8`
- `0x18005ce60`
- `0x180076b34`
- `0x180087660`
- `0x18008db2c`
- `0x180117250`

## import_xrefs

- `RPCRT4!RpcRevertToSelfEx` at `0x180076c8a`
- `RPCRT4!RpcRevertToSelfEx` at `0x180076c8a`
- `RPCRT4!RpcImpersonateClient2` at `0x180076b67`
- `RPCRT4!RpcImpersonateClient2` at `0x180076b67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076bad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076c4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076bad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076c4a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180076c15`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180076c15`
- `api-ms-win-security-base-l1-1-0!ImpersonateAnonymousToken` at `0x180076c1e`
- `api-ms-win-security-base-l1-1-0!ImpersonateAnonymousToken` at `0x180076c1e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180076b9f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180076b9f`

## string_xrefs

- `0x180076bf9`: `onecore\com\combase\common\internal\tokenproperties.cpp`
- `0x180076bed`: `IsTokenBoolPresent`

## pseudocode

```c
__int64 __fastcall IsRpcClientTokenAppContainer(void *hRpcServerCall, bool *pbClientIsAppContainer)
{
  HRESULT v4; // ebx
  RPC_STATUS v5; // eax
  BOOL v6; // ebp
  signed int LastError; // eax
  HANDLE CurrentThread; // rax
  bool v9; // zf
  signed int v10; // eax
  unsigned int ReturnLength; // [rsp+30h] [rbp-28h] BYREF
  void *hPreviousThreadToken; // [rsp+38h] [rbp-20h] BYREF
  int fTokenIsAppContainer; // [rsp+70h] [rbp+18h] BYREF
  int TokenInformation; // [rsp+78h] [rbp+20h] BYREF

  hPreviousThreadToken = 0;
  v4 = SuspendImpersonate(&hPreviousThreadToken);
  if ( v4 >= 0 )
  {
    v5 = RpcImpersonateClient2(hRpcServerCall);
    v4 = v5;
    if ( v5 )
    {
      if ( v5 > 0 )
        v4 = (unsigned __int16)v5 | 0x80070000;
      goto LABEL_27;
    }
    v6 = 0;
    TokenInformation = 0;
    ReturnLength = 0;
    fTokenIsAppContainer = 0;
    if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFBLL, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) )
    {
      v4 = 0;
      v6 = TokenInformation != 0;
    }
    else
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
        ComTraceMessageT<long>(
          "onecore\\com\\combase\\common\\internal\\tokenproperties.cpp",
          "IsTokenBoolPresent",
          58,
          ERRORS,
          L"hr:%!HRESULT!",
          v4);
      if ( v4 < 0 )
      {
        if ( v4 != -2147023549 )
          goto LABEL_24;
        CurrentThread = GetCurrentThread();
        if ( !ImpersonateAnonymousToken(CurrentThread) )
        {
          v10 = GetLastError();
          if ( gfAccessDeniedFromImpersonateAnonymousTokenExpected && v10 == 5 )
          {
            *pbClientIsAppContainer = 0;
          }
          else if ( v10 > 0 )
          {
            v4 = (unsigned __int16)v10 | 0x80070000;
          }
          else
          {
            v4 = v10;
          }
          goto LABEL_24;
        }
        v4 = IsTokenBoolPresent((void *)0xFFFFFFFFFFFFFFFBLL, TokenIsAppContainer, &fTokenIsAppContainer);
        if ( v4 < 0 )
        {
LABEL_24:
          RpcRevertToSelfEx(hRpcServerCall);
LABEL_27:
          ResumeImpersonate(hPreviousThreadToken);
          return (unsigned int)v4;
        }
        v9 = fTokenIsAppContainer == 0;
LABEL_23:
        *pbClientIsAppContainer = !v9;
        goto LABEL_24;
      }
    }
    v9 = !v6;
    goto LABEL_23;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180076b34  mov     [rsp+arg_0], rbx
0x180076b39  push    rbp
0x180076b3a  push    rsi
0x180076b3b  push    r14
0x180076b3d  sub     rsp, 40h
0x180076b41  mov     r14, hRpcServerCall
0x180076b44  mov     [rsp+58h+hPreviousThreadToken], 0
0x180076b4d  lea     hRpcServerCall, [rsp+58h+hPreviousThreadToken]; pHandle
0x180076b52  mov     rsi, pbClientIsAppContainer
0x180076b55  call    ?SuspendImpersonate@@YAJPEAPEAX@Z; SuspendImpersonate(void * *)
0x180076b5a  mov     ebx, eax
0x180076b5c  test    eax, eax
0x180076b5e  js      loc_180076CA7
0x180076b64  mov     hRpcServerCall, r14; BindingHandle
0x180076b67  call    cs:__imp_RpcImpersonateClient2
0x180076b6d  mov     ebx, eax
0x180076b6f  test    eax, eax
0x180076b71  jnz     loc_180076C92
0x180076b77  xor     ebp, ebp
0x180076b79  mov     [rsp+58h+TokenInformation], eax
0x180076b7d  mov     [rsp+58h+var_28], eax
0x180076b81  lea     r9d, [rbx+4]; TokenInformationLength
0x180076b85  lea     rax, [rsp+58h+var_28]
0x180076b8a  mov     [rsp+58h+fTokenIsAppContainer], ebp
0x180076b8e  lea     r8, [rsp+58h+TokenInformation]; TokenInformation
0x180076b93  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180076b98  lea     hRpcServerCall, [rbp-5]; TokenHandle
0x180076b9c  lea     edx, [rbx+1Dh]; TokenInformationClass
0x180076b9f  call    cs:__imp_GetTokenInformation
0x180076ba5  test    eax, eax
0x180076ba7  jnz     loc_180076C75
0x180076bad  call    cs:__imp_GetLastError
0x180076bb3  mov     ebx, eax
0x180076bb5  test    eax, eax
0x180076bb7  jle     short loc_180076BC2
0x180076bb9  movzx   ebx, ax
0x180076bbc  or      ebx, 80070000h
0x180076bc2  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x180076bc8  test    eax, eax
0x180076bca  jnz     short loc_180076BDF
0x180076bcc  cmp     cs:?gfEnableTracing@@3HA, ebp; int gfEnableTracing
0x180076bd2  jz      short loc_180076C09
0x180076bd4  xor     ecx, ecx; level
0x180076bd6  call    IsWppLevelEnabled
0x180076bdb  test    al, al
0x180076bdd  jz      short loc_180076C09
0x180076bdf  xor     r9d, r9d; level
0x180076be2  mov     [rsp+58h+var_30], ebx; <args_0>
0x180076be6  lea     rax, aHrHresult; "hr:%!HRESULT!"
0x180076bed  lea     pbClientIsAppContainer, aIstokenboolpre; "IsTokenBoolPresent"
0x180076bf4  mov     [rsp+58h+ReturnLength], rax; format
0x180076bf9  lea     hRpcServerCall, aOnecoreComComb_24; "onecore\\com\\combase\\common\\internal"...
0x180076c00  lea     r8d, [r9+3Ah]; line
0x180076c04  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x180076c09  test    ebx, ebx
0x180076c0b  jns     short loc_180076C80
0x180076c0d  cmp     ebx, 80070543h
0x180076c13  jnz     short loc_180076C87
0x180076c15  call    cs:__imp_GetCurrentThread
0x180076c1b  mov     hRpcServerCall, rax; ThreadHandle
0x180076c1e  call    cs:__imp_ImpersonateAnonymousToken
0x180076c24  test    eax, eax
0x180076c26  jz      short loc_180076C4A
0x180076c28  lea     r8, [rsp+58h+fTokenIsAppContainer]; isPresent
0x180076c2d  mov     edx, 1Dh; type
0x180076c32  mov     hRpcServerCall, 0FFFFFFFFFFFFFFFBh; hToken
0x180076c39  call    ?IsTokenBoolPresent@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@PEAH@Z; IsTokenBoolPresent(void *,_TOKEN_INFORMATION_CLASS,int *)
0x180076c3e  mov     ebx, eax
0x180076c40  test    eax, eax
0x180076c42  js      short loc_180076C87
0x180076c44  cmp     [rsp+58h+fTokenIsAppContainer], ebp
0x180076c48  jmp     short loc_180076C82
0x180076c4a  call    cs:__imp_GetLastError
0x180076c50  cmp     cs:?gfAccessDeniedFromImpersonateAnonymousTokenExpected@@3HA, ebp; int gfAccessDeniedFromImpersonateAnonymousTokenExpected
0x180076c56  jz      short loc_180076C62
0x180076c58  cmp     eax, 5
0x180076c5b  jnz     short loc_180076C62
0x180076c5d  mov     [rsi], bpl
0x180076c60  jmp     short loc_180076C87
0x180076c62  test    eax, eax
0x180076c64  jg      short loc_180076C6A
0x180076c66  mov     ebx, eax
0x180076c68  jmp     short loc_180076C87
0x180076c6a  movzx   ebx, ax
0x180076c6d  or      ebx, 80070000h
0x180076c73  jmp     short loc_180076C87
0x180076c75  xor     ebx, ebx
0x180076c77  cmp     [rsp+58h+TokenInformation], ebp
0x180076c7b  jz      short loc_180076C80
0x180076c7d  lea     ebp, [rbx+1]
0x180076c80  test    ebp, ebp
0x180076c82  setnz   al
0x180076c85  mov     [rsi], al
0x180076c87  mov     hRpcServerCall, r14; BindingHandle
0x180076c8a  call    cs:__imp_RpcRevertToSelfEx
0x180076c90  jmp     short loc_180076C9D
0x180076c92  jle     short loc_180076C9D
0x180076c94  movzx   ebx, ax
0x180076c97  or      ebx, 80070000h
0x180076c9d  mov     hRpcServerCall, [rsp+58h+hPreviousThreadToken]; hToken
0x180076ca2  call    ?ResumeImpersonate@@YAXPEAX@Z; ResumeImpersonate(void *)
0x180076ca7  mov     eax, ebx
0x180076ca9  mov     rbx, [rsp+58h+arg_0]
0x180076cae  add     rsp, 40h
0x180076cb2  pop     r14
0x180076cb4  pop     rsi
0x180076cb5  pop     rbp
0x180076cb6  retn
```
