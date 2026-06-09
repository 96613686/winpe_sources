# CLrpcServer::staticHintApiRpcSecurityCallback(void *,void *)

- ea: `0x14005aae0`
- end: `0x14005af57`
- name: `?staticHintApiRpcSecurityCallback@CLrpcServer@@CAJPEAX0@Z`
- size: `1143`
- prototype: `RPC_IF_CALLBACK_FN`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140004b1c`
- `0x1400056c4`
- `0x140005704`
- `0x14000cae0`
- `0x14005aae0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x14005ac5d`
- `msvcrt!_wcsicmp` at `0x14005ac5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005acdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005ad91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005adf9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005acdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005ad91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005adf9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14005ad4e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14005ad4e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14005ad63`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14005ad63`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x14005acb9`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x14005acb9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14005acad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14005acad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005aebf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005aebf`
- `RPCRT4!RpcImpersonateClient` at `0x14005ad0f`
- `RPCRT4!RpcImpersonateClient` at `0x14005ad0f`
- `RPCRT4!RpcRevertToSelf` at `0x14005aecd`
- `RPCRT4!RpcRevertToSelf` at `0x14005aecd`
- `RPCRT4!RpcStringFreeW` at `0x14005af23`
- `RPCRT4!RpcStringFreeW` at `0x14005af37`
- `RPCRT4!RpcStringFreeW` at `0x14005af23`
- `RPCRT4!RpcStringFreeW` at `0x14005af37`
- `RPCRT4!RpcStringBindingParseW` at `0x14005ac16`
- `RPCRT4!RpcStringBindingParseW` at `0x14005ac16`
- `RPCRT4!RpcBindingToStringBindingW` at `0x14005aba2`
- `RPCRT4!RpcBindingToStringBindingW` at `0x14005aba2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14005adcb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14005adcb`

## pseudocode

```c
__int64 __fastcall CLrpcServer::staticHintApiRpcSecurityCallback(RPC_IF_HANDLE InterfaceUuid, void *Context)
{
  int v3; // esi
  PVOID *v5; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v7; // eax
  unsigned int v8; // ebx
  unsigned int v9; // eax
  __int64 v10; // rdx
  unsigned int v11; // eax
  DWORD CurrentProcessId; // eax
  DWORD LastError; // ebx
  unsigned int v14; // eax
  __int64 v15; // rdx
  HANDLE CurrentThread; // rax
  int v17; // ebx
  DWORD v18; // edi
  unsigned int v19; // eax
  unsigned int v20; // eax
  RPC_STATUS v21; // edi
  unsigned int v22; // eax
  RPC_WSTR StringBinding; // [rsp+30h] [rbp-20h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-18h] BYREF
  RPC_WSTR Protseq[2]; // [rsp+40h] [rbp-10h] BYREF
  int TokenInformation; // [rsp+90h] [rbp+40h] BYREF
  DWORD pSessionId; // [rsp+A0h] [rbp+50h] BYREF
  DWORD ReturnLength; // [rsp+A8h] [rbp+58h] BYREF

  pSessionId = 0;
  v3 = 0;
  StringBinding = 0;
  Protseq[0] = 0;
  TokenHandle = 0;
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      21,
      WPP_07dbb75969773461a51251fd5f4f75a9_Traceguids,
      CurrentThreadActivityIdPrefix);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !InterfaceUuid && v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 1) != 0 && *((_BYTE *)v5 + 25) >= 2u )
  {
    v7 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_07dbb75969773461a51251fd5f4f75a9_Traceguids, v7);
  }
  v8 = RpcBindingToStringBindingW(Context, &StringBinding);
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = RdpWppGetCurrentThreadActivityIdPrefix();
      v10 = 23;
LABEL_15:
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, WPP_07dbb75969773461a51251fd5f4f75a9_Traceguids, v9, v8);
      goto LABEL_58;
    }
    goto LABEL_58;
  }
  v8 = RpcStringBindingParseW(StringBinding, 0, Protseq, 0, 0, 0);
  if ( !v8 )
  {
    if ( _wcsicmp(Protseq[0], L"ncalrpc") )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_07dbb75969773461a51251fd5f4f75a9_Traceguids, v11);
      }
      goto LABEL_26;
    }
    CurrentProcessId = GetCurrentProcessId();
    if ( ProcessIdToSessionId(CurrentProcessId, &pSessionId) )
    {
      LastError = RpcImpersonateClient(0);
      if ( LastError )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_26;
        }
        v14 = RdpWppGetCurrentThreadActivityIdPrefix();
        v15 = 27;
      }
      else
      {
        v3 = 1;
        CurrentThread = GetCurrentThread();
        if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
        {
          TokenInformation = 0;
          ReturnLength = 0;
          if ( GetTokenInformation(TokenHandle, TokenSessionId, &TokenInformation, 4u, &ReturnLength) )
          {
            v17 = TokenInformation;
            v18 = pSessionId;
            if ( TokenInformation == pSessionId )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v20 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_DdD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  31,
                  WPP_07dbb75969773461a51251fd5f4f75a9_Traceguids,
                  v20,
                  v17,
                  v18);
              }
              v8 = 0;
              goto LABEL_58;
            }
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v19 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_DdD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                30,
                WPP_07dbb75969773461a51251fd5f4f75a9_Traceguids,
                v19,
                v17,
                v18);
            }
LABEL_26:
            v8 = 5;
            goto LABEL_58;
          }
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_26;
          }
          LastError = GetLastError();
          v14 = RdpWppGetCurrentThreadActivityIdPrefix();
          v15 = 29;
        }
        else
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_26;
          }
          LastError = GetLastError();
          v14 = RdpWppGetCurrentThreadActivityIdPrefix();
          v15 = 28;
        }
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_26;
      }
      LastError = GetLastError();
      v14 = RdpWppGetCurrentThreadActivityIdPrefix();
      v15 = 26;
    }
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, WPP_07dbb75969773461a51251fd5f4f75a9_Traceguids, v14, LastError);
    goto LABEL_26;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v9 = RdpWppGetCurrentThreadActivityIdPrefix();
    v10 = 24;
    goto LABEL_15;
  }
LABEL_58:
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  if ( v3 )
  {
    v21 = RpcRevertToSelf();
    if ( v21 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v22 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_07dbb75969773461a51251fd5f4f75a9_Traceguids, v22, v21);
      }
    }
  }
  if ( StringBinding )
  {
    RpcStringFreeW(&StringBinding);
    StringBinding = 0;
  }
  if ( Protseq[0] )
    RpcStringFreeW(Protseq);
  return v8;
}

```

## disassembly

```asm
0x14005aae0  mov     [rsp-38h+arg_8], rbx
0x14005aae5  push    rbp
0x14005aae6  push    rsi
0x14005aae7  push    rdi
0x14005aae8  push    r12
0x14005aaea  push    r13
0x14005aaec  push    r14
0x14005aaee  push    r15
0x14005aaf0  mov     rbp, rsp
0x14005aaf3  sub     rsp, 50h
0x14005aaf7  xor     r14d, r14d
0x14005aafa  mov     rdi, rdx
0x14005aafd  mov     [rbp+pSessionId], r14d
0x14005ab01  mov     esi, r14d
0x14005ab04  mov     [rbp+StringBinding], r14
0x14005ab08  mov     rbx, rcx
0x14005ab0b  mov     [rbp+Protseq], r14
0x14005ab0f  mov     [rbp+TokenHandle], r14
0x14005ab13  mov     rax, cs:WPP_GLOBAL_Control
0x14005ab1a  lea     r13, WPP_GLOBAL_Control
0x14005ab21  lea     r15d, [r14+1]
0x14005ab25  mov     r12b, 2
0x14005ab28  cmp     rax, r13
0x14005ab2b  jz      short loc_14005AB63
0x14005ab2d  test    [rax+1Ch], r15b
0x14005ab31  jz      short loc_14005AB63
0x14005ab33  cmp     [rax+19h], r12b
0x14005ab37  jb      short loc_14005AB63
0x14005ab39  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005ab3e  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ab45  lea     edx, [r14+15h]
0x14005ab49  mov     r9d, eax
0x14005ab4c  lea     r8, WPP_07dbb75969773461a51251fd5f4f75a9_Traceguids
0x14005ab53  mov     rcx, [rcx+10h]
0x14005ab57  call    WPP_SF_d
0x14005ab5c  mov     rax, cs:WPP_GLOBAL_Control
0x14005ab63  test    rbx, rbx
0x14005ab66  jnz     short loc_14005AB9B
0x14005ab68  cmp     rax, r13
0x14005ab6b  jz      short loc_14005AB9B
0x14005ab6d  test    [rax+1Ch], r15b
0x14005ab71  jz      short loc_14005AB9B
0x14005ab73  cmp     [rax+19h], r12b
0x14005ab77  jb      short loc_14005AB9B
0x14005ab79  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005ab7e  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ab85  lea     edx, [rbx+16h]
0x14005ab88  mov     r9d, eax
0x14005ab8b  lea     r8, WPP_07dbb75969773461a51251fd5f4f75a9_Traceguids
0x14005ab92  mov     rcx, [rcx+10h]
0x14005ab96  call    WPP_SF_d
0x14005ab9b  lea     rdx, [rbp+StringBinding]; StringBinding
0x14005ab9f  mov     rcx, rdi; Binding
0x14005aba2  call    cs:__imp_RpcBindingToStringBindingW
0x14005aba8  mov     ebx, eax
0x14005abaa  test    eax, eax
0x14005abac  jz      short loc_14005ABFF
0x14005abae  mov     rax, cs:WPP_GLOBAL_Control
0x14005abb5  cmp     rax, r13
0x14005abb8  jz      loc_14005AEB6
0x14005abbe  test    [rax+1Ch], r15b
0x14005abc2  jz      loc_14005AEB6
0x14005abc8  cmp     [rax+19h], r12b
0x14005abcc  jb      loc_14005AEB6
0x14005abd2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005abd7  mov     edx, 17h
0x14005abdc  mov     rcx, cs:WPP_GLOBAL_Control
0x14005abe3  lea     r8, WPP_07dbb75969773461a51251fd5f4f75a9_Traceguids
0x14005abea  mov     r9d, eax
0x14005abed  mov     dword ptr [rsp+50h+Endpoint], ebx
0x14005abf1  mov     rcx, [rcx+10h]
0x14005abf5  call    WPP_SF_Dd
0x14005abfa  jmp     loc_14005AEB6
0x14005abff  mov     rcx, [rbp+StringBinding]; StringBinding
0x14005ac03  lea     r8, [rbp+Protseq]; Protseq
0x14005ac07  mov     [rsp+50h+NetworkOptions], r14; NetworkOptions
0x14005ac0c  xor     r9d, r9d; NetworkAddr
0x14005ac0f  xor     edx, edx; ObjUuid
0x14005ac11  mov     [rsp+50h+Endpoint], r14; Endpoint
0x14005ac16  call    cs:__imp_RpcStringBindingParseW
0x14005ac1c  mov     ebx, eax
0x14005ac1e  test    eax, eax
0x14005ac20  jz      short loc_14005AC52
0x14005ac22  mov     rax, cs:WPP_GLOBAL_Control
0x14005ac29  cmp     rax, r13
0x14005ac2c  jz      loc_14005AEB6
0x14005ac32  test    [rax+1Ch], r15b
0x14005ac36  jz      loc_14005AEB6
0x14005ac3c  cmp     [rax+19h], r12b
0x14005ac40  jb      loc_14005AEB6
0x14005ac46  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005ac4b  mov     edx, 18h
0x14005ac50  jmp     short loc_14005ABDC
0x14005ac52  mov     rcx, [rbp+Protseq]; String1
0x14005ac56  lea     rdx, aNcalrpc; "ncalrpc"
0x14005ac5d  call    cs:__imp__wcsicmp
0x14005ac63  test    eax, eax
0x14005ac65  jz      short loc_14005ACAD
0x14005ac67  mov     rax, cs:WPP_GLOBAL_Control
0x14005ac6e  cmp     rax, r13
0x14005ac71  jz      short loc_14005ACA3
0x14005ac73  test    [rax+1Ch], r15b
0x14005ac77  jz      short loc_14005ACA3
0x14005ac79  cmp     [rax+19h], r12b
0x14005ac7d  jb      short loc_14005ACA3
0x14005ac7f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005ac84  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ac8b  lea     r8, WPP_07dbb75969773461a51251fd5f4f75a9_Traceguids
0x14005ac92  mov     edx, 19h
0x14005ac97  mov     r9d, eax
0x14005ac9a  mov     rcx, [rcx+10h]
0x14005ac9e  call    WPP_SF_d
0x14005aca3  mov     ebx, 5
0x14005aca8  jmp     loc_14005AEB6
0x14005acad  call    cs:__imp_GetCurrentProcessId
0x14005acb3  mov     ecx, eax; dwProcessId
0x14005acb5  lea     rdx, [rbp+pSessionId]; pSessionId
0x14005acb9  call    cs:__imp_ProcessIdToSessionId
0x14005acbf  test    eax, eax
0x14005acc1  jnz     short loc_14005AD0D
0x14005acc3  mov     rax, cs:WPP_GLOBAL_Control
0x14005acca  cmp     rax, r13
0x14005accd  jz      short loc_14005ACA3
0x14005accf  test    [rax+1Ch], r15b
0x14005acd3  jz      short loc_14005ACA3
0x14005acd5  cmp     [rax+19h], r12b
0x14005acd9  jb      short loc_14005ACA3
0x14005acdb  call    cs:__imp_GetLastError
0x14005ace1  mov     ebx, eax
0x14005ace3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005ace8  mov     edx, 1Ah
0x14005aced  mov     rcx, cs:WPP_GLOBAL_Control
0x14005acf4  lea     r8, WPP_07dbb75969773461a51251fd5f4f75a9_Traceguids
0x14005acfb  mov     r9d, eax
0x14005acfe  mov     dword ptr [rsp+50h+Endpoint], ebx
0x14005ad02  mov     rcx, [rcx+10h]
0x14005ad06  call    WPP_SF_Dd
0x14005ad0b  jmp     short loc_14005ACA3
0x14005ad0d  xor     ecx, ecx; BindingHandle
0x14005ad0f  call    cs:__imp_RpcImpersonateClient
0x14005ad15  mov     ebx, eax
0x14005ad17  test    eax, eax
0x14005ad19  jz      short loc_14005AD4B
0x14005ad1b  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ad22  cmp     rcx, r13
0x14005ad25  jz      loc_14005ACA3
0x14005ad2b  test    [rcx+1Ch], r15b
0x14005ad2f  jz      loc_14005ACA3
0x14005ad35  cmp     [rcx+19h], r12b
0x14005ad39  jb      loc_14005ACA3
0x14005ad3f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005ad44  mov     edx, 1Bh
0x14005ad49  jmp     short loc_14005ACED
0x14005ad4b  mov     esi, r15d
0x14005ad4e  call    cs:__imp_GetCurrentThread
0x14005ad54  lea     r9, [rbp+TokenHandle]; TokenHandle
0x14005ad58  mov     r8d, r15d; OpenAsSelf
0x14005ad5b  mov     rcx, rax; ThreadHandle
0x14005ad5e  mov     edx, 8; DesiredAccess
0x14005ad63  call    cs:__imp_OpenThreadToken
0x14005ad69  test    eax, eax
0x14005ad6b  jnz     short loc_14005ADA8
0x14005ad6d  mov     rax, cs:WPP_GLOBAL_Control
0x14005ad74  cmp     rax, r13
0x14005ad77  jz      loc_14005ACA3
0x14005ad7d  test    [rax+1Ch], r15b
0x14005ad81  jz      loc_14005ACA3
0x14005ad87  cmp     [rax+19h], r12b
0x14005ad8b  jb      loc_14005ACA3
0x14005ad91  call    cs:__imp_GetLastError
0x14005ad97  mov     ebx, eax
0x14005ad99  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005ad9e  mov     edx, 1Ch
0x14005ada3  jmp     loc_14005ACED
0x14005ada8  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x14005adac  lea     rax, [rbp+ReturnLength]
0x14005adb0  mov     r9d, 4; TokenInformationLength
0x14005adb6  mov     [rbp+TokenInformation], r14d
0x14005adba  lea     r8, [rbp+TokenInformation]; TokenInformation
0x14005adbe  mov     [rbp+ReturnLength], r14d
0x14005adc2  mov     [rsp+50h+Endpoint], rax; ReturnLength
0x14005adc7  lea     edx, [r9+8]; TokenInformationClass
0x14005adcb  call    cs:__imp_GetTokenInformation
0x14005add1  test    eax, eax
0x14005add3  jnz     short loc_14005AE10
0x14005add5  mov     rax, cs:WPP_GLOBAL_Control
0x14005addc  cmp     rax, r13
0x14005addf  jz      loc_14005ACA3
0x14005ade5  test    [rax+1Ch], r15b
0x14005ade9  jz      loc_14005ACA3
0x14005adef  cmp     [rax+19h], r12b
0x14005adf3  jb      loc_14005ACA3
0x14005adf9  call    cs:__imp_GetLastError
0x14005adff  mov     ebx, eax
0x14005ae01  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005ae06  mov     edx, 1Dh
0x14005ae0b  jmp     loc_14005ACED
0x14005ae10  mov     ebx, [rbp+TokenInformation]
0x14005ae13  mov     edi, [rbp+pSessionId]
0x14005ae16  cmp     ebx, edi
0x14005ae18  jz      short loc_14005AE6F
0x14005ae1a  mov     rax, cs:WPP_GLOBAL_Control
0x14005ae21  cmp     rax, r13
0x14005ae24  jz      loc_14005ACA3
0x14005ae2a  test    [rax+1Ch], r15b
0x14005ae2e  jz      loc_14005ACA3
0x14005ae34  cmp     [rax+19h], r12b
0x14005ae38  jb      loc_14005ACA3
0x14005ae3e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005ae43  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ae4a  lea     r8, WPP_07dbb75969773461a51251fd5f4f75a9_Traceguids
0x14005ae51  mov     edx, 1Eh
0x14005ae56  mov     dword ptr [rsp+50h+NetworkOptions], edi
0x14005ae5a  mov     r9d, eax
0x14005ae5d  mov     dword ptr [rsp+50h+Endpoint], ebx
0x14005ae61  mov     rcx, [rcx+10h]
0x14005ae65  call    WPP_SF_DdD
0x14005ae6a  jmp     loc_14005ACA3
0x14005ae6f  mov     rax, cs:WPP_GLOBAL_Control
0x14005ae76  cmp     rax, r13
0x14005ae79  jz      short loc_14005AEB3
0x14005ae7b  test    [rax+1Ch], r15b
0x14005ae7f  jz      short loc_14005AEB3
0x14005ae81  cmp     [rax+19h], r12b
0x14005ae85  jb      short loc_14005AEB3
0x14005ae87  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005ae8c  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ae93  lea     r8, WPP_07dbb75969773461a51251fd5f4f75a9_Traceguids
0x14005ae9a  mov     edx, 1Fh
0x14005ae9f  mov     dword ptr [rsp+50h+NetworkOptions], edi
0x14005aea3  mov     r9d, eax
0x14005aea6  mov     dword ptr [rsp+50h+Endpoint], ebx
0x14005aeaa  mov     rcx, [rcx+10h]
0x14005aeae  call    WPP_SF_DdD
0x14005aeb3  mov     ebx, r14d
0x14005aeb6  mov     rcx, [rbp+TokenHandle]; hObject
0x14005aeba  test    rcx, rcx
0x14005aebd  jz      short loc_14005AEC9
0x14005aebf  call    cs:__imp_CloseHandle
0x14005aec5  mov     [rbp+TokenHandle], r14
0x14005aec9  test    esi, esi
0x14005aecb  jz      short loc_14005AF19
0x14005aecd  call    cs:__imp_RpcRevertToSelf
0x14005aed3  mov     edi, eax
0x14005aed5  test    eax, eax
0x14005aed7  jz      short loc_14005AF19
0x14005aed9  mov     rcx, cs:WPP_GLOBAL_Control
0x14005aee0  cmp     rcx, r13
0x14005aee3  jz      short loc_14005AF19
0x14005aee5  test    [rcx+1Ch], r15b
0x14005aee9  jz      short loc_14005AF19
0x14005aeeb  cmp     [rcx+19h], r12b
0x14005aeef  jb      short loc_14005AF19
0x14005aef1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005aef6  mov     rcx, cs:WPP_GLOBAL_Control
0x14005aefd  lea     r8, WPP_07dbb75969773461a51251fd5f4f75a9_Traceguids
0x14005af04  mov     edx, 20h ; ' '
0x14005af09  mov     dword ptr [rsp+50h+Endpoint], edi
0x14005af0d  mov     r9d, eax
0x14005af10  mov     rcx, [rcx+10h]
0x14005af14  call    WPP_SF_Dd
0x14005af19  cmp     [rbp+StringBinding], r14
0x14005af1d  jz      short loc_14005AF2D
0x14005af1f  lea     rcx, [rbp+StringBinding]; String
0x14005af23  call    cs:__imp_RpcStringFreeW
0x14005af29  mov     [rbp+StringBinding], r14
0x14005af2d  cmp     [rbp+Protseq], r14
0x14005af31  jz      short loc_14005AF3D
0x14005af33  lea     rcx, [rbp+Protseq]; String
0x14005af37  call    cs:__imp_RpcStringFreeW
0x14005af3d  mov     eax, ebx
0x14005af3f  mov     rbx, [rsp+50h+arg_8]
0x14005af47  add     rsp, 50h
0x14005af4b  pop     r15
0x14005af4d  pop     r14
0x14005af4f  pop     r13
0x14005af51  pop     r12
0x14005af53  pop     rdi
0x14005af54  pop     rsi
0x14005af55  pop     rbp
0x14005af56  retn
```
