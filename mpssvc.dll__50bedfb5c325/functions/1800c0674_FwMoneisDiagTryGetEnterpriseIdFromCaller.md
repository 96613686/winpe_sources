# FwMoneisDiagTryGetEnterpriseIdFromCaller

- ea: `0x1800c0674`
- end: `0x1800c0905`
- name: `FwMoneisDiagTryGetEnterpriseIdFromCaller`
- size: `657`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180029d04`

## callees

- `0x18000a710`
- `0x1800192e0`
- `0x1800729c0`
- `0x1800a7458`
- `0x1800c0674`
- `0x1800c0fd8`
- `0x1800e389c`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800c0808`
- `ntdll!RtlNtStatusToDosError` at `0x1800c0808`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c0735`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c0735`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800c074f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800c074f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c075f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c075f`
- `RPCRT4!RpcImpersonateClient` at `0x1800c06e8`
- `RPCRT4!RpcImpersonateClient` at `0x1800c06e8`
- `RPCRT4!RpcRevertToSelf` at `0x1800c08ac`
- `RPCRT4!RpcRevertToSelf` at `0x1800c08ac`
- `fwbase!FwCloseHandle` at `0x1800c088b`
- `fwbase!FwCloseHandle` at `0x1800c088b`
- `fwbase!FwFree` at `0x1800c089b`
- `fwbase!FwFree` at `0x1800c089b`

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
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 84, WPP_c82a0d1b11b03f6aea8fb1592911dce6_Traceguids);
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
      WPP_SF_d(*(_QWORD *)(v7 + 16), v8, WPP_c82a0d1b11b03f6aea8fb1592911dce6_Traceguids, v9);
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
              (unsigned int)WPP_c82a0d1b11b03f6aea8fb1592911dce6_Traceguids,
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
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 90, WPP_c82a0d1b11b03f6aea8fb1592911dce6_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x1800c0674  mov     [rsp-38h+arg_10], rbx
0x1800c0679  push    rbp
0x1800c067a  push    rsi
0x1800c067b  push    rdi
0x1800c067c  push    r12
0x1800c067e  push    r13
0x1800c0680  push    r14
0x1800c0682  push    r15
0x1800c0684  mov     rbp, rsp
0x1800c0687  sub     rsp, 60h
0x1800c068b  mov     rax, cs:__security_cookie
0x1800c0692  xor     rax, rsp
0x1800c0695  mov     [rbp+var_8], rax
0x1800c0699  mov     rsi, rdx
0x1800c069c  mov     rbx, rcx
0x1800c069f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c06a6  lea     r12, WPP_GLOBAL_Control
0x1800c06ad  lea     r13, WPP_c82a0d1b11b03f6aea8fb1592911dce6_Traceguids
0x1800c06b4  cmp     rcx, r12
0x1800c06b7  jz      short loc_1800C06D0
0x1800c06b9  test    byte ptr [rcx+1Ch], 8
0x1800c06bd  jz      short loc_1800C06D0
0x1800c06bf  mov     rcx, [rcx+10h]
0x1800c06c3  mov     edx, 54h ; 'T'
0x1800c06c8  mov     r8, r13
0x1800c06cb  call    WPP_SF_
0x1800c06d0  xor     r15d, r15d
0x1800c06d3  xorps   xmm0, xmm0
0x1800c06d6  mov     rcx, rbx; BindingHandle
0x1800c06d9  mov     [rbp+var_30], r15b
0x1800c06dd  mov     [rbp+TokenHandle], r15
0x1800c06e1  movups  [rbp+var_18], xmm0
0x1800c06e5  mov     [rsi], r15
0x1800c06e8  call    cs:__imp_RpcImpersonateClient
0x1800c06ef  nop     dword ptr [rax+rax+00h]
0x1800c06f4  mov     ebx, eax
0x1800c06f6  test    eax, eax
0x1800c06f8  jz      short loc_1800C072F
0x1800c06fa  mov     r14d, r15d
0x1800c06fd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c0704  cmp     rcx, r12
0x1800c0707  jz      loc_1800C0887
0x1800c070d  test    byte ptr [rcx+1Ch], 1
0x1800c0711  jz      loc_1800C0887
0x1800c0717  lea     edx, [r15+55h]
0x1800c071b  mov     r9d, eax
0x1800c071e  mov     rcx, [rcx+10h]
0x1800c0722  mov     r8, r13
0x1800c0725  call    WPP_SF_d
0x1800c072a  jmp     loc_1800C0887
0x1800c072f  mov     r14d, 1
0x1800c0735  call    cs:__imp_GetCurrentThread
0x1800c073c  nop     dword ptr [rax+rax+00h]
0x1800c0741  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800c0745  mov     r8d, r14d; OpenAsSelf
0x1800c0748  mov     rcx, rax; ThreadHandle
0x1800c074b  lea     edx, [r14+7]; DesiredAccess
0x1800c074f  call    cs:__imp_OpenThreadToken
0x1800c0756  nop     dword ptr [rax+rax+00h]
0x1800c075b  test    eax, eax
0x1800c075d  jnz     short loc_1800C078D
0x1800c075f  call    cs:__imp_GetLastError
0x1800c0766  nop     dword ptr [rax+rax+00h]
0x1800c076b  mov     ebx, eax
0x1800c076d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c0774  cmp     rcx, r12
0x1800c0777  jz      loc_1800C0887
0x1800c077d  test    [rcx+1Ch], r14b
0x1800c0781  jz      loc_1800C0887
0x1800c0787  lea     edx, [r14+55h]
0x1800c078b  jmp     short loc_1800C071B
0x1800c078d  call    FwMoneisGetEnterpriseIdReference
0x1800c0792  mov     rdi, rax
0x1800c0795  test    rax, rax
0x1800c0798  jnz     short loc_1800C07C2
0x1800c079a  mov     ebx, r15d
0x1800c079d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c07a4  cmp     rcx, r12
0x1800c07a7  jz      loc_1800C0887
0x1800c07ad  test    [rcx+1Ch], r14b
0x1800c07b1  jz      loc_1800C0887
0x1800c07b7  lea     edx, [rax+57h]
0x1800c07ba  xor     r9d, r9d
0x1800c07bd  jmp     loc_1800C071E
0x1800c07c2  mov     qword ptr [rbp+var_18+8], rdi
0x1800c07c6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800c07ca  inc     rax
0x1800c07cd  cmp     [rdi+rax*2], r15w
0x1800c07d2  jnz     short loc_1800C07CA
0x1800c07d4  add     ax, ax
0x1800c07d7  lea     r8, [rbp+var_30]
0x1800c07db  mov     word ptr [rbp+var_18], ax
0x1800c07df  lea     rdx, [rbp+var_18]
0x1800c07e3  mov     word ptr [rbp+var_18+2], ax
0x1800c07e7  mov     rcx, 0FFFFFFFFFFFFFFFAh
0x1800c07ee  mov     rax, [rbp+TokenHandle]
0x1800c07f2  test    rax, rax
0x1800c07f5  cmovz   rax, rcx
0x1800c07f9  lea     rcx, [rbp+var_28]
0x1800c07fd  mov     [rbp+var_28], rax
0x1800c0801  call    IsSubjectEnterprise
0x1800c0806  mov     ecx, eax; Status
0x1800c0808  call    cs:__imp_RtlNtStatusToDosError
0x1800c080f  nop     dword ptr [rax+rax+00h]
0x1800c0814  mov     ebx, eax
0x1800c0816  test    eax, eax
0x1800c0818  jz      short loc_1800C0836
0x1800c081a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c0821  cmp     rcx, r12
0x1800c0824  jz      short loc_1800C0887
0x1800c0826  test    [rcx+1Ch], r14b
0x1800c082a  jz      short loc_1800C0887
0x1800c082c  mov     edx, 58h ; 'X'
0x1800c0831  jmp     loc_1800C071B
0x1800c0836  movzx   edx, [rbp+var_30]
0x1800c083a  test    dl, dl
0x1800c083c  jz      short loc_1800C0849
0x1800c083e  mov     rax, qword ptr [rbp+var_18+8]
0x1800c0842  mov     [rsi], rax
0x1800c0845  mov     qword ptr [rbp+var_18+8], r15
0x1800c0849  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c0850  cmp     rcx, r12
0x1800c0853  jz      short loc_1800C0887
0x1800c0855  test    byte ptr [rcx+1Ch], 4
0x1800c0859  jz      short loc_1800C0887
0x1800c085b  cmp     [rsi], r15
0x1800c085e  lea     rax, aNull; "<null>"
0x1800c0865  mov     rcx, [rcx+10h]
0x1800c0869  mov     r9d, edx
0x1800c086c  cmovnz  rax, [rsi]
0x1800c0870  mov     edx, 59h ; 'Y'
0x1800c0875  mov     [rsp+60h+var_38], rax
0x1800c087a  mov     r8, r13
0x1800c087d  mov     [rsp+60h+var_40], rdi
0x1800c0882  call    WPP_SF_dSS
0x1800c0887  mov     rcx, [rbp+TokenHandle]
0x1800c088b  call    cs:__imp_FwCloseHandle
0x1800c0892  nop     dword ptr [rax+rax+00h]
0x1800c0897  mov     rcx, qword ptr [rbp+var_18+8]
0x1800c089b  call    cs:__imp_FwFree
0x1800c08a2  nop     dword ptr [rax+rax+00h]
0x1800c08a7  test    r14d, r14d
0x1800c08aa  jz      short loc_1800C08B8
0x1800c08ac  call    cs:__imp_RpcRevertToSelf
0x1800c08b3  nop     dword ptr [rax+rax+00h]
0x1800c08b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c08bf  cmp     rcx, r12
0x1800c08c2  jz      short loc_1800C08DE
0x1800c08c4  test    byte ptr [rcx+1Ch], 8
0x1800c08c8  jz      short loc_1800C08DE
0x1800c08ca  mov     rcx, [rcx+10h]
0x1800c08ce  mov     edx, 5Ah ; 'Z'
0x1800c08d3  mov     r9d, ebx
0x1800c08d6  mov     r8, r13
0x1800c08d9  call    WPP_SF_d
0x1800c08de  mov     eax, ebx
0x1800c08e0  mov     rcx, [rbp+var_8]
0x1800c08e4  xor     rcx, rsp; StackCookie
0x1800c08e7  call    __security_check_cookie
0x1800c08ec  mov     rbx, [rsp+60h+arg_10]
0x1800c08f4  add     rsp, 60h
0x1800c08f8  pop     r15
0x1800c08fa  pop     r14
0x1800c08fc  pop     r13
0x1800c08fe  pop     r12
0x1800c0900  pop     rdi
0x1800c0901  pop     rsi
0x1800c0902  pop     rbp
0x1800c0903  retn
```
