# RpcNrpGetNameInfo

- ea: `0x180052060`
- end: `0x180052195`
- name: `RpcNrpGetNameInfo`
- size: `309`
- prototype: `__int64 __usercall@<rax>(RPC_BINDING_HANDLE BindingHandle@<rcx>, PWCHAR pNodeBuffer, __int16, PWCHAR, __int16, INT)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task`

## callees

- `0x18001f658`
- `0x180052060`
- `0x18007f2b4`
- `0x180086b1c`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x180052152`
- `RPCRT4!RpcRevertToSelf` at `0x180052152`
- `RPCRT4!RpcImpersonateClient` at `0x180052105`
- `RPCRT4!RpcImpersonateClient` at `0x180052105`
- `RPCRT4!RpcRaiseException` at `0x180052111`
- `RPCRT4!RpcRaiseException` at `0x180052111`
- `WS2_32!GetNameInfoW` at `0x180052145`
- `WS2_32!GetNameInfoW` at `0x180052145`

## pseudocode

```c
__int64 __fastcall RpcNrpGetNameInfo(
        RPC_BINDING_HANDLE BindingHandle,
        __int16 a2,
        const SOCKADDR *a3,
        socklen_t a4,
        PWCHAR pNodeBuffer,
        unsigned __int16 a6,
        PWCHAR pServiceBuffer,
        unsigned __int16 a8,
        INT Flags)
{
  RPC_STATUS v13; // eax
  unsigned int NameInfoW; // ebx

  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_qDqIqDqDI(
      a6,
      a8,
      (_DWORD)a3,
      (_DWORD)BindingHandle,
      a2,
      (__int64)a3,
      a4,
      (__int64)pNodeBuffer,
      a6,
      (__int64)pServiceBuffer,
      a8,
      Flags);
  if ( a3 && a4 && (pNodeBuffer && a6 || pServiceBuffer && a8) )
  {
    if ( a2 )
    {
      v13 = RpcImpersonateClient(BindingHandle);
      if ( v13 )
        RpcRaiseException(v13);
    }
    NameInfoW = GetNameInfoW(a3, a4, pNodeBuffer, a6, pServiceBuffer, a8, Flags);
    if ( a2 )
      RpcRevertToSelf();
  }
  else
  {
    NameInfoW = 10022;
  }
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 33, WPP_f7a7b403e64b309f267ad22af7388cf2_Traceguids, NameInfoW);
  return SocketErrorToNtStatus(NameInfoW);
}

```

## disassembly

```asm
0x180052060  mov     r11, rsp
0x180052063  push    rbx
0x180052064  push    rsi
0x180052065  push    rdi
0x180052066  push    r12
0x180052068  push    r13
0x18005206a  push    r14
0x18005206c  sub     rsp, 68h
0x180052070  mov     ebx, r9d
0x180052073  mov     rdi, r8
0x180052076  movzx   esi, dx
0x180052079  mov     r13, rcx
0x18005207c  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180052083  mov     r14, [rsp+98h+arg_30]
0x18005208b  mov     r12, [rsp+98h+pNodeBuffer]
0x180052093  jz      short loc_1800520D4
0x180052095  mov     eax, [rsp+98h+arg_40]
0x18005209c  mov     r9, r13
0x18005209f  movzx   edx, [rsp+98h+arg_38]
0x1800520a7  movzx   ecx, [rsp+98h+arg_28]
0x1800520af  mov     [r11-40h], rax
0x1800520b3  mov     [rsp+98h+var_48], edx
0x1800520b7  mov     [r11-50h], r14
0x1800520bb  mov     [rsp+98h+var_58], ecx
0x1800520bf  mov     [r11-60h], r12
0x1800520c3  mov     [r11-68h], rbx
0x1800520c7  mov     [r11-70h], r8
0x1800520cb  mov     dword ptr [rsp+98h+pServiceBuffer], esi
0x1800520cf  call    WPP_SF_qDqIqDqDI
0x1800520d4  xor     eax, eax
0x1800520d6  test    rdi, rdi
0x1800520d9  jz      short loc_18005215A
0x1800520db  test    ebx, ebx
0x1800520dd  jz      short loc_18005215A
0x1800520df  test    r12, r12
0x1800520e2  jz      short loc_1800520EE
0x1800520e4  cmp     [rsp+98h+arg_28], ax
0x1800520ec  jnz     short loc_1800520FD
0x1800520ee  test    r14, r14
0x1800520f1  jz      short loc_18005215A
0x1800520f3  cmp     [rsp+98h+arg_38], ax
0x1800520fb  jz      short loc_18005215A
0x1800520fd  test    si, si
0x180052100  jz      short loc_180052118
0x180052102  mov     rcx, r13; BindingHandle
0x180052105  call    cs:__imp_RpcImpersonateClient
0x18005210b  test    eax, eax
0x18005210d  jz      short loc_180052118
0x18005210f  mov     ecx, eax; exception
0x180052111  call    cs:__imp_RpcRaiseException
0x180052117  int     3; Trap to Debugger
0x180052118  movzx   eax, [rsp+98h+arg_38]
0x180052120  mov     r8, r12; pNodeBuffer
0x180052123  mov     ecx, [rsp+98h+arg_40]
0x18005212a  mov     edx, ebx; SockaddrLength
0x18005212c  movzx   r9d, [rsp+98h+arg_28]; NodeBufferSize
0x180052135  mov     [rsp+98h+Flags], ecx; Flags
0x180052139  mov     rcx, rdi; pSockaddr
0x18005213c  mov     [rsp+98h+ServiceBufferSize], eax; ServiceBufferSize
0x180052140  mov     [rsp+98h+pServiceBuffer], r14; pServiceBuffer
0x180052145  call    cs:__imp_GetNameInfoW
0x18005214b  mov     ebx, eax
0x18005214d  test    si, si
0x180052150  jz      short loc_18005215F
0x180052152  call    cs:__imp_RpcRevertToSelf
0x180052158  jmp     short loc_18005215F
0x18005215a  mov     ebx, 2726h
0x18005215f  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180052166  jz      short loc_180052181
0x180052168  mov     edx, 21h ; '!'
0x18005216d  lea     r8, WPP_f7a7b403e64b309f267ad22af7388cf2_Traceguids
0x180052174  mov     ecx, 40Bh
0x180052179  mov     r9d, ebx
0x18005217c  call    WPP_SF_d
0x180052181  mov     ecx, ebx
0x180052183  add     rsp, 68h
0x180052187  pop     r14
0x180052189  pop     r13
0x18005218b  pop     r12
0x18005218d  pop     rdi
0x18005218e  pop     rsi
0x18005218f  pop     rbx
0x180052190  jmp     SocketErrorToNtStatus
```
