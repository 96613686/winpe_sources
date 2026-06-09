# RpcNrpGetAddrInfo

- ea: `0x18001f310`
- end: `0x18001f64f`
- name: `RpcNrpGetAddrInfo`
- size: `831`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, service_task`

## callees

- `0x180008870`
- `0x18000b130`
- `0x18001f310`
- `0x18001f658`
- `0x18001fff8`
- `0x180046ec0`
- `0x180079518`
- `0x180086b1c`
- `0x180088198`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x18001f609`
- `RPCRT4!RpcRevertToSelf` at `0x18001f609`
- `RPCRT4!RpcImpersonateClient` at `0x18001f5ef`
- `RPCRT4!RpcImpersonateClient` at `0x18001f5ef`
- `RPCRT4!RpcRaiseException` at `0x18001f62a`
- `RPCRT4!RpcRaiseException` at `0x18001f62a`
- `WS2_32!FreeAddrInfoExW` at `0x18001f4d8`
- `WS2_32!FreeAddrInfoExW` at `0x18001f4d8`
- `WS2_32!GetAddrInfoExW` at `0x18001f496`
- `WS2_32!GetAddrInfoExW` at `0x18001f496`

## pseudocode

```c
__int64 __fastcall RpcNrpGetAddrInfo(
        void *a1,
        __int16 a2,
        const void *a3,
        unsigned __int16 a4,
        unsigned __int16 a5,
        PCWSTR pServiceName,
        unsigned __int16 a7,
        unsigned __int16 a8,
        DWORD dwNameSpace,
        GUID *a10,
        const ADDRINFOEXW *hints,
        __int64 *a12)
{
  const void *v12; // r14
  __int64 *v13; // rax
  const WCHAR *v14; // r15
  size_t v15; // rbx
  void *v16; // rsi
  void *v17; // rax
  WCHAR *v18; // rdi
  int v19; // ebp
  unsigned int AddrInfo; // ebx
  __int64 v21; // rax
  WCHAR *v23; // rax
  RPC_STATUS v24; // eax
  PADDRINFOEXW pAddrInfoEx; // [rsp+98h] [rbp-50h] BYREF

  v12 = a3;
  v13 = a12;
  v14 = pServiceName;
  pAddrInfoEx = 0;
  v15 = a4;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
  {
    WPP_SF_qDSDDSDDI_guid_q(a8, 0, (_DWORD)a3, (_DWORD)a1, a2);
    v13 = a12;
  }
  if ( !v12 || !(_WORD)v15 )
  {
    if ( !pServiceName || !a7 )
      goto LABEL_33;
    if ( !v12 )
      goto LABEL_36;
  }
  if ( a5 < (unsigned __int16)v15 )
  {
LABEL_33:
    AddrInfo = 10022;
    goto LABEL_29;
  }
  if ( pServiceName )
  {
LABEL_36:
    if ( a8 < a7 )
      goto LABEL_33;
  }
  if ( !v13 )
    goto LABEL_33;
  v16 = 0;
  if ( v12 )
  {
    if ( a5 < v15 + 2 )
    {
      v17 = (void *)Dns_Allocate(v15 + 2);
      v16 = v17;
      if ( !v17 )
      {
        AddrInfo = 8;
        goto LABEL_29;
      }
      memcpy_0(v17, v12, v15);
      v12 = v16;
    }
    *((_WORD *)v12 + (v15 >> 1)) = 0;
  }
  v18 = 0;
  v19 = 0;
  if ( !pServiceName )
    goto LABEL_16;
  if ( a8 >= (unsigned __int64)a7 + 2 )
  {
LABEL_15:
    v14[(unsigned __int64)a7 >> 1] = 0;
LABEL_16:
    if ( a2 && (AddrInfo = RpcImpersonateClient(a1)) != 0 )
    {
      v19 = 1;
    }
    else
    {
      AddrInfo = GetAddrInfoExW((PCWSTR)v12, v14, dwNameSpace, a10, hints, &pAddrInfoEx, 0, 0, 0, 0);
      if ( a2 )
        RpcRevertToSelf();
      if ( pAddrInfoEx )
      {
        v21 = CopyNrpAddrInfoW();
        if ( v21 )
          *a12 = v21;
        else
          AddrInfo = 8;
        if ( pAddrInfoEx )
          FreeAddrInfoExW(pAddrInfoEx);
      }
    }
    goto LABEL_24;
  }
  v23 = (WCHAR *)Dns_Allocate(a7 + 2LL);
  v18 = v23;
  if ( v23 )
  {
    memcpy_0(v23, pServiceName, a7);
    v14 = v18;
    goto LABEL_15;
  }
  AddrInfo = 8;
LABEL_24:
  if ( v16 )
    MIDL_user_free(v16);
  if ( v18 )
    MIDL_user_free(v18);
  if ( v19 )
  {
    v24 = SocketErrorToNtStatus(AddrInfo);
    RpcRaiseException(v24);
  }
LABEL_29:
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 31, WPP_f7a7b403e64b309f267ad22af7388cf2_Traceguids, AddrInfo);
  return SocketErrorToNtStatus(AddrInfo);
}

```

## disassembly

```asm
0x18001f310  push    rbx
0x18001f312  push    rbp
0x18001f313  push    rsi
0x18001f314  push    rdi
0x18001f315  push    r12
0x18001f317  push    r14
0x18001f319  push    r15
0x18001f31b  sub     rsp, 0B0h
0x18001f322  mov     rax, cs:__security_cookie
0x18001f329  xor     rax, rsp
0x18001f32c  mov     [rsp+0E8h+var_48], rax
0x18001f334  mov     rsi, [rsp+0E8h+arg_48]
0x18001f33c  mov     r14, r8
0x18001f33f  mov     rbp, [rsp+0E8h+arg_50]
0x18001f347  mov     r11, rcx
0x18001f34a  mov     rax, [rsp+0E8h+arg_58]
0x18001f352  mov     r15, [rsp+0E8h+pServiceName]
0x18001f35a  movzx   r12d, [rsp+0E8h+arg_30]
0x18001f363  movzx   r10d, dx
0x18001f367  xor     edx, edx
0x18001f369  mov     [rsp+0E8h+pAddrInfoEx], rdx
0x18001f371  movzx   ebx, r9w
0x18001f375  mov     [rsp+0E8h+var_78], r10w
0x18001f37b  mov     [rsp+0E8h+BindingHandle], rcx
0x18001f383  mov     [rsp+0E8h+lpNspId], rsi
0x18001f38b  mov     [rsp+0E8h+var_60], rbp
0x18001f393  mov     [rsp+0E8h+var_70], rax
0x18001f398  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18001f39f  movzx   edi, [rsp+0E8h+arg_20]
0x18001f3a7  jnz     loc_18001F55E
0x18001f3ad  test    r14, r14
0x18001f3b0  jz      loc_18001F532
0x18001f3b6  test    bx, bx
0x18001f3b9  jz      loc_18001F532
0x18001f3bf  cmp     di, bx
0x18001f3c2  jb      loc_18001F537
0x18001f3c8  test    r15, r15
0x18001f3cb  jnz     loc_18001F54D
0x18001f3d1  test    rax, rax
0x18001f3d4  jz      loc_18001F537
0x18001f3da  mov     rsi, rdx
0x18001f3dd  test    r14, r14
0x18001f3e0  jz      short loc_18001F417
0x18001f3e2  lea     rcx, [rbx+2]
0x18001f3e6  cmp     rdi, rcx
0x18001f3e9  jnb     short loc_18001F40F
0x18001f3eb  call    Dns_Allocate
0x18001f3f0  mov     rsi, rax
0x18001f3f3  test    rax, rax
0x18001f3f6  jz      loc_18001F5B0
0x18001f3fc  mov     r8, rbx; Size
0x18001f3ff  mov     rdx, r14; Src
0x18001f402  mov     rcx, rax; void *
0x18001f405  call    memcpy_0
0x18001f40a  xor     edx, edx
0x18001f40c  mov     r14, rsi
0x18001f40f  shr     rbx, 1
0x18001f412  mov     [r14+rbx*2], dx
0x18001f417  mov     rdi, rdx
0x18001f41a  mov     ebp, edx
0x18001f41c  test    r15, r15
0x18001f41f  jz      short loc_18001F442
0x18001f421  movzx   eax, [rsp+0E8h+arg_38]
0x18001f429  lea     rcx, [r12+2]
0x18001f42e  mov     rbx, r12
0x18001f431  cmp     rax, rcx
0x18001f434  jb      loc_18001F5BA
0x18001f43a  shr     rbx, 1
0x18001f43d  mov     [r15+rbx*2], dx
0x18001f442  movzx   r12d, [rsp+0E8h+var_78]
0x18001f448  test    r12w, r12w
0x18001f44c  jnz     loc_18001F5E7
0x18001f452  mov     r9, [rsp+0E8h+lpNspId]; lpNspId
0x18001f45a  lea     rax, [rsp+0E8h+pAddrInfoEx]
0x18001f462  mov     r8d, [rsp+0E8h+dwNameSpace]; dwNameSpace
0x18001f46a  mov     rcx, r14; pName
0x18001f46d  mov     [rsp+0E8h+lpHandle], rdx; lpHandle
0x18001f472  mov     [rsp+0E8h+lpCompletionRoutine], rdx; lpCompletionRoutine
0x18001f477  mov     [rsp+0E8h+lpOverlapped], rdx; lpOverlapped
0x18001f47c  mov     [rsp+0E8h+timeout], rdx; timeout
0x18001f481  mov     rdx, r15; pServiceName
0x18001f484  mov     [rsp+0E8h+ppResult], rax; ppResult
0x18001f489  mov     rax, [rsp+0E8h+var_60]
0x18001f491  mov     [rsp+0E8h+hints], rax; hints
0x18001f496  call    cs:__imp_GetAddrInfoExW
0x18001f49c  mov     ebx, eax
0x18001f49e  test    r12w, r12w
0x18001f4a2  jnz     loc_18001F609
0x18001f4a8  mov     rcx, [rsp+0E8h+pAddrInfoEx]
0x18001f4b0  test    rcx, rcx
0x18001f4b3  jz      short loc_18001F4DE
0x18001f4b5  call    CopyNrpAddrInfoW
0x18001f4ba  test    rax, rax
0x18001f4bd  jz      loc_18001F5A6
0x18001f4c3  mov     rcx, [rsp+0E8h+var_70]
0x18001f4c8  mov     [rcx], rax
0x18001f4cb  mov     rcx, [rsp+0E8h+pAddrInfoEx]; pAddrInfoEx
0x18001f4d3  test    rcx, rcx
0x18001f4d6  jz      short loc_18001F4DE
0x18001f4d8  call    cs:__imp_FreeAddrInfoExW
0x18001f4de  test    rsi, rsi
0x18001f4e1  jz      short loc_18001F4EB
0x18001f4e3  mov     rcx, rsi; void *
0x18001f4e6  call    MIDL_user_free
0x18001f4eb  test    rdi, rdi
0x18001f4ee  jnz     loc_18001F614
0x18001f4f4  test    ebp, ebp
0x18001f4f6  jnz     loc_18001F621
0x18001f4fc  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18001f503  jnz     loc_18001F631
0x18001f509  mov     ecx, ebx
0x18001f50b  call    SocketErrorToNtStatus
0x18001f510  mov     rcx, [rsp+0E8h+var_48]
0x18001f518  xor     rcx, rsp; StackCookie
0x18001f51b  call    __security_check_cookie
0x18001f520  add     rsp, 0B0h
0x18001f527  pop     r15
0x18001f529  pop     r14
0x18001f52b  pop     r12
0x18001f52d  pop     rdi
0x18001f52e  pop     rsi
0x18001f52f  pop     rbp
0x18001f530  pop     rbx
0x18001f531  retn
0x18001f532  test    r15, r15
0x18001f535  jnz     short loc_18001F53E
0x18001f537  mov     ebx, 2726h
0x18001f53c  jmp     short loc_18001F4FC
0x18001f53e  test    r12w, r12w
0x18001f542  jz      short loc_18001F537
0x18001f544  test    r14, r14
0x18001f547  jnz     loc_18001F3BF
0x18001f54d  cmp     [rsp+0E8h+arg_38], r12w
0x18001f556  jnb     loc_18001F3D1
0x18001f55c  jmp     short loc_18001F537
0x18001f55e  mov     eax, [rsp+0E8h+dwNameSpace]
0x18001f565  mov     r9, r11
0x18001f568  movzx   ecx, [rsp+0E8h+arg_38]
0x18001f570  mov     [rsp+0E8h+var_80], rbp
0x18001f575  mov     [rsp+0E8h+var_88], rsi
0x18001f57a  mov     [rsp+0E8h+var_90], rax
0x18001f57f  mov     [rsp+0E8h+var_98], ecx
0x18001f583  mov     dword ptr [rsp+0E8h+lpHandle], r12d
0x18001f588  mov     dword ptr [rsp+0E8h+lpOverlapped], edi
0x18001f58c  mov     dword ptr [rsp+0E8h+timeout], ebx
0x18001f590  mov     dword ptr [rsp+0E8h+hints], r10d
0x18001f595  call    WPP_SF_qDSDDSDDI_guid_q
0x18001f59a  mov     rax, [rsp+0E8h+var_70]
0x18001f59f  xor     edx, edx
0x18001f5a1  jmp     loc_18001F3AD
0x18001f5a6  mov     ebx, 8
0x18001f5ab  jmp     loc_18001F4CB
0x18001f5b0  mov     ebx, 8
0x18001f5b5  jmp     loc_18001F4FC
0x18001f5ba  call    Dns_Allocate
0x18001f5bf  mov     rdi, rax
0x18001f5c2  test    rax, rax
0x18001f5c5  jnz     short loc_18001F5CF
0x18001f5c7  lea     ebx, [rax+8]
0x18001f5ca  jmp     loc_18001F4DE
0x18001f5cf  mov     r8, rbx; Size
0x18001f5d2  mov     rdx, r15; Src
0x18001f5d5  mov     rcx, rdi; void *
0x18001f5d8  call    memcpy_0
0x18001f5dd  xor     edx, edx
0x18001f5df  mov     r15, rdi
0x18001f5e2  jmp     loc_18001F43A
0x18001f5e7  mov     rcx, [rsp+0E8h+BindingHandle]; BindingHandle
0x18001f5ef  call    cs:__imp_RpcImpersonateClient
0x18001f5f5  xor     edx, edx
0x18001f5f7  mov     ebx, eax
0x18001f5f9  test    eax, eax
0x18001f5fb  jz      loc_18001F452
0x18001f601  lea     ebp, [rdx+1]
0x18001f604  jmp     loc_18001F4DE
0x18001f609  call    cs:__imp_RpcRevertToSelf
0x18001f60f  jmp     loc_18001F4A8
0x18001f614  mov     rcx, rdi; void *
0x18001f617  call    MIDL_user_free
0x18001f61c  jmp     loc_18001F4F4
0x18001f621  mov     ecx, ebx
0x18001f623  call    SocketErrorToNtStatus
0x18001f628  mov     ecx, eax; exception
0x18001f62a  call    cs:__imp_RpcRaiseException
0x18001f630  int     3; Trap to Debugger
0x18001f631  mov     edx, 1Fh
0x18001f636  lea     r8, WPP_f7a7b403e64b309f267ad22af7388cf2_Traceguids
0x18001f63d  mov     ecx, 40Bh
0x18001f642  mov     r9d, ebx
0x18001f645  call    WPP_SF_d
0x18001f64a  jmp     loc_18001F509
```
