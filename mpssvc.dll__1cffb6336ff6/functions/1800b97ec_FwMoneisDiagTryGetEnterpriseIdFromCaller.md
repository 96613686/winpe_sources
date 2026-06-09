# FwMoneisDiagTryGetEnterpriseIdFromCaller

- ea: `0x1800b97ec`
- end: `0x1800b9a4c`
- name: `FwMoneisDiagTryGetEnterpriseIdFromCaller`
- size: `608`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800055a8`

## callees

- `0x18000af3c`
- `0x180017110`
- `0x18006f520`
- `0x1800a1c9c`
- `0x1800b97ec`
- `0x1800ba0a4`
- `0x1800dd6f0`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800b9968`
- `ntdll!RtlNtStatusToDosError` at `0x1800b9968`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800b98bb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800b98bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800b98a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800b98a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b98c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b98c5`
- `RPCRT4!RpcRevertToSelf` at `0x1800b99fa`
- `RPCRT4!RpcRevertToSelf` at `0x1800b99fa`
- `RPCRT4!RpcImpersonateClient` at `0x1800b9860`
- `RPCRT4!RpcImpersonateClient` at `0x1800b9860`
- `fwbase!FwCloseHandle` at `0x1800b99e5`
- `fwbase!FwCloseHandle` at `0x1800b99e5`
- `fwbase!FwFree` at `0x1800b99ef`
- `fwbase!FwFree` at `0x1800b99ef`

## pseudocode

```c
__int64 __fastcall FwMoneisDiagTryGetEnterpriseIdFromCaller(RPC_BINDING_HANDLE BindingHandle, const char **a2)
{
  ULONG LastError; // eax
  ULONG v5; // ebx
  int v6; // r14d
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  HANDLE CurrentThread; // rax
  __int64 EnterpriseIdReference; // rax
  __int64 v12; // rdi
  __int64 v13; // rax
  __int64 v14; // rax
  NTSTATUS v15; // eax
  int v16; // edx
  const char *v17; // rax
  _BYTE v19[8]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v20; // [rsp+38h] [rbp-28h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-20h] BYREF
  __int128 v22; // [rsp+48h] [rbp-18h] BYREF

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 84, WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids);
  v19[0] = 0;
  TokenHandle = 0;
  v22 = 0;
  *a2 = 0;
  LastError = RpcImpersonateClient(BindingHandle);
  v5 = LastError;
  if ( LastError )
  {
    v6 = 0;
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v8 = 85;
LABEL_8:
      v9 = LastError;
LABEL_9:
      WPP_SF_d(*(_QWORD *)(v7 + 16), v8, WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids, v9);
    }
  }
  else
  {
    v6 = 1;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    {
      EnterpriseIdReference = FwMoneisGetEnterpriseIdReference();
      v12 = EnterpriseIdReference;
      if ( EnterpriseIdReference )
      {
        *((_QWORD *)&v22 + 1) = EnterpriseIdReference;
        v13 = -1;
        do
          ++v13;
        while ( *(_WORD *)(v12 + 2 * v13) );
        LOWORD(v22) = 2 * v13;
        WORD1(v22) = 2 * v13;
        v14 = (__int64)TokenHandle;
        if ( !TokenHandle )
          v14 = -6;
        v20 = v14;
        v15 = IsSubjectEnterprise(&v20, &v22, v19);
        LastError = RtlNtStatusToDosError(v15);
        v5 = LastError;
        if ( LastError )
        {
          v7 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v8 = 88;
            goto LABEL_8;
          }
        }
        else
        {
          v16 = v19[0];
          if ( v19[0] )
          {
            *a2 = (const char *)*((_QWORD *)&v22 + 1);
            *((_QWORD *)&v22 + 1) = 0;
          }
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
          {
            v17 = L"<null>";
            if ( *a2 )
              v17 = *a2;
            WPP_SF_dSS(
              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
              89,
              (unsigned int)WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids,
              v16,
              v12,
              (__int64)v17);
          }
        }
      }
      else
      {
        v5 = 0;
        v7 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          v8 = 87;
          v9 = 0;
          goto LABEL_9;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v5 = LastError;
      v7 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v8 = 86;
        goto LABEL_8;
      }
    }
  }
  FwCloseHandle(TokenHandle);
  FwFree(*((_QWORD *)&v22 + 1));
  if ( v6 )
    RpcRevertToSelf();
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 90, WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x1800b97ec  mov     [rsp-38h+arg_10], rbx
0x1800b97f1  push    rbp
0x1800b97f2  push    rsi
0x1800b97f3  push    rdi
0x1800b97f4  push    r12
0x1800b97f6  push    r13
0x1800b97f8  push    r14
0x1800b97fa  push    r15
0x1800b97fc  mov     rbp, rsp
0x1800b97ff  sub     rsp, 60h
0x1800b9803  mov     rax, cs:__security_cookie
0x1800b980a  xor     rax, rsp
0x1800b980d  mov     [rbp+var_8], rax
0x1800b9811  mov     rsi, rdx
0x1800b9814  mov     rbx, rcx
0x1800b9817  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b981e  lea     r12, WPP_GLOBAL_Control
0x1800b9825  lea     r13, WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids
0x1800b982c  cmp     rcx, r12
0x1800b982f  jz      short loc_1800B9848
0x1800b9831  test    byte ptr [rcx+1Ch], 8
0x1800b9835  jz      short loc_1800B9848
0x1800b9837  mov     rcx, [rcx+10h]
0x1800b983b  mov     edx, 54h ; 'T'
0x1800b9840  mov     r8, r13
0x1800b9843  call    WPP_SF_
0x1800b9848  xor     r15d, r15d
0x1800b984b  xorps   xmm0, xmm0
0x1800b984e  mov     rcx, rbx; BindingHandle
0x1800b9851  mov     [rbp+var_30], r15b
0x1800b9855  mov     [rbp+TokenHandle], r15
0x1800b9859  movups  [rbp+var_18], xmm0
0x1800b985d  mov     [rsi], r15
0x1800b9860  call    cs:__imp_RpcImpersonateClient
0x1800b9866  mov     ebx, eax
0x1800b9868  test    eax, eax
0x1800b986a  jz      short loc_1800B98A1
0x1800b986c  mov     r14d, r15d
0x1800b986f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9876  cmp     rcx, r12
0x1800b9879  jz      loc_1800B99E1
0x1800b987f  test    byte ptr [rcx+1Ch], 1
0x1800b9883  jz      loc_1800B99E1
0x1800b9889  lea     edx, [r15+55h]
0x1800b988d  mov     r9d, eax
0x1800b9890  mov     rcx, [rcx+10h]
0x1800b9894  mov     r8, r13
0x1800b9897  call    WPP_SF_d
0x1800b989c  jmp     loc_1800B99E1
0x1800b98a1  mov     r14d, 1
0x1800b98a7  call    cs:__imp_GetCurrentThread
0x1800b98ad  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800b98b1  mov     r8d, r14d; OpenAsSelf
0x1800b98b4  mov     rcx, rax; ThreadHandle
0x1800b98b7  lea     edx, [r14+7]; DesiredAccess
0x1800b98bb  call    cs:__imp_OpenThreadToken
0x1800b98c1  test    eax, eax
0x1800b98c3  jnz     short loc_1800B98ED
0x1800b98c5  call    cs:__imp_GetLastError
0x1800b98cb  mov     ebx, eax
0x1800b98cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b98d4  cmp     rcx, r12
0x1800b98d7  jz      loc_1800B99E1
0x1800b98dd  test    [rcx+1Ch], r14b
0x1800b98e1  jz      loc_1800B99E1
0x1800b98e7  lea     edx, [r14+55h]
0x1800b98eb  jmp     short loc_1800B988D
0x1800b98ed  call    FwMoneisGetEnterpriseIdReference
0x1800b98f2  mov     rdi, rax
0x1800b98f5  test    rax, rax
0x1800b98f8  jnz     short loc_1800B9922
0x1800b98fa  mov     ebx, r15d
0x1800b98fd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9904  cmp     rcx, r12
0x1800b9907  jz      loc_1800B99E1
0x1800b990d  test    [rcx+1Ch], r14b
0x1800b9911  jz      loc_1800B99E1
0x1800b9917  lea     edx, [rax+57h]
0x1800b991a  xor     r9d, r9d
0x1800b991d  jmp     loc_1800B9890
0x1800b9922  mov     qword ptr [rbp+var_18+8], rdi
0x1800b9926  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800b992a  inc     rax
0x1800b992d  cmp     [rdi+rax*2], r15w
0x1800b9932  jnz     short loc_1800B992A
0x1800b9934  add     ax, ax
0x1800b9937  lea     r8, [rbp+var_30]
0x1800b993b  mov     word ptr [rbp+var_18], ax
0x1800b993f  lea     rdx, [rbp+var_18]
0x1800b9943  mov     word ptr [rbp+var_18+2], ax
0x1800b9947  mov     rcx, 0FFFFFFFFFFFFFFFAh
0x1800b994e  mov     rax, [rbp+TokenHandle]
0x1800b9952  test    rax, rax
0x1800b9955  cmovz   rax, rcx
0x1800b9959  lea     rcx, [rbp+var_28]
0x1800b995d  mov     [rbp+var_28], rax
0x1800b9961  call    IsSubjectEnterprise
0x1800b9966  mov     ecx, eax; Status
0x1800b9968  call    cs:__imp_RtlNtStatusToDosError
0x1800b996e  mov     ebx, eax
0x1800b9970  test    eax, eax
0x1800b9972  jz      short loc_1800B9990
0x1800b9974  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b997b  cmp     rcx, r12
0x1800b997e  jz      short loc_1800B99E1
0x1800b9980  test    [rcx+1Ch], r14b
0x1800b9984  jz      short loc_1800B99E1
0x1800b9986  mov     edx, 58h ; 'X'
0x1800b998b  jmp     loc_1800B988D
0x1800b9990  movzx   edx, [rbp+var_30]
0x1800b9994  test    dl, dl
0x1800b9996  jz      short loc_1800B99A3
0x1800b9998  mov     rax, qword ptr [rbp+var_18+8]
0x1800b999c  mov     [rsi], rax
0x1800b999f  mov     qword ptr [rbp+var_18+8], r15
0x1800b99a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b99aa  cmp     rcx, r12
0x1800b99ad  jz      short loc_1800B99E1
0x1800b99af  test    byte ptr [rcx+1Ch], 4
0x1800b99b3  jz      short loc_1800B99E1
0x1800b99b5  cmp     [rsi], r15
0x1800b99b8  lea     rax, aNull; "<null>"
0x1800b99bf  mov     rcx, [rcx+10h]
0x1800b99c3  mov     r9d, edx
0x1800b99c6  cmovnz  rax, [rsi]
0x1800b99ca  mov     edx, 59h ; 'Y'
0x1800b99cf  mov     [rsp+60h+var_38], rax
0x1800b99d4  mov     r8, r13
0x1800b99d7  mov     [rsp+60h+var_40], rdi
0x1800b99dc  call    WPP_SF_dSS
0x1800b99e1  mov     rcx, [rbp+TokenHandle]
0x1800b99e5  call    cs:__imp_FwCloseHandle
0x1800b99eb  mov     rcx, qword ptr [rbp+var_18+8]
0x1800b99ef  call    cs:__imp_FwFree
0x1800b99f5  test    r14d, r14d
0x1800b99f8  jz      short loc_1800B9A00
0x1800b99fa  call    cs:__imp_RpcRevertToSelf
0x1800b9a00  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9a07  cmp     rcx, r12
0x1800b9a0a  jz      short loc_1800B9A26
0x1800b9a0c  test    byte ptr [rcx+1Ch], 8
0x1800b9a10  jz      short loc_1800B9A26
0x1800b9a12  mov     rcx, [rcx+10h]
0x1800b9a16  mov     edx, 5Ah ; 'Z'
0x1800b9a1b  mov     r9d, ebx
0x1800b9a1e  mov     r8, r13
0x1800b9a21  call    WPP_SF_d
0x1800b9a26  mov     eax, ebx
0x1800b9a28  mov     rcx, [rbp+var_8]
0x1800b9a2c  xor     rcx, rsp; StackCookie
0x1800b9a2f  call    __security_check_cookie
0x1800b9a34  mov     rbx, [rsp+60h+arg_10]
0x1800b9a3c  add     rsp, 60h
0x1800b9a40  pop     r15
0x1800b9a42  pop     r14
0x1800b9a44  pop     r13
0x1800b9a46  pop     r12
0x1800b9a48  pop     rdi
0x1800b9a49  pop     rsi
0x1800b9a4a  pop     rbp
0x1800b9a4b  retn
```
