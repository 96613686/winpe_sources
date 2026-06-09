# CMQTransaction::Commit(int,ulong,ulong)

- ea: `0x180018490`
- end: `0x180018574`
- name: `?Commit@CMQTransaction@@UEAAJHKK@Z`
- size: `228`
- prototype: `__int64 __fastcall(CMQTransaction *__hidden this, int, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180013bdc`
- `0x180013c74`
- `0x180018490`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x1800184eb`
- `RPCRT4!NdrClientCall3` at `0x1800184eb`
- `RPCRT4!I_RpcExceptionFilter` at `0x180024ec4`
- `RPCRT4!I_RpcExceptionFilter` at `0x180024ec4`
- `mqsec!ProduceRPCErrorTracing` at `0x180018525`
- `mqsec!ProduceRPCErrorTracing` at `0x180018525`

## pseudocode

```c
__int64 __fastcall CMQTransaction::Commit(CMQTransaction *this, int a2, int a3, int a4)
{
  unsigned __int16 v5; // r8
  int Pointer; // ebx

  if ( (a3 & 0xFFFFFFFD) != 0 || a4 || a2 )
  {
    v5 = 10;
    Pointer = -2147168241;
    goto LABEL_9;
  }
  if ( *((_DWORD *)this + 5) )
  {
    v5 = 1102;
    Pointer = -1072824239;
LABEL_9:
    LogMsgHR(Pointer, (wchar_t *)L"rt/XactMq", v5);
    return (unsigned int)Pointer;
  }
  Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x11u, 0, (char *)this + 40).Pointer;
  *((_DWORD *)this + 5) = 1;
  if ( Pointer < 0 )
  {
    v5 = 30;
    goto LABEL_9;
  }
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x180018490  mov     [rsp+arg_0], rbx
0x180018495  push    rdi
0x180018496  sub     rsp, 30h
0x18001849a  mov     rdi, rcx
0x18001849d  test    r8d, 0FFFFFFFDh
0x1800184a4  jnz     loc_18001854E
0x1800184aa  test    r9d, r9d
0x1800184ad  jnz     loc_18001854E
0x1800184b3  test    edx, edx
0x1800184b5  jnz     loc_18001854E
0x1800184bb  cmp     [rcx+14h], edx
0x1800184be  jz      short loc_1800184D0
0x1800184c0  mov     r8d, 44Eh
0x1800184c6  mov     ebx, 0C00E0051h
0x1800184cb  jmp     loc_180018559
0x1800184d0  mov     [rsp+38h+var_10], 0
0x1800184d9  lea     r9, [rcx+28h]
0x1800184dd  xor     r8d, r8d; pReturnValue
0x1800184e0  lea     edx, [r8+11h]; nProcNum
0x1800184e4  lea     rcx, pProxyInfo; pProxyInfo
0x1800184eb  call    cs:__imp_NdrClientCall3
0x1800184f1  mov     rbx, rax
0x1800184f4  mov     [rsp+38h+var_10], rax
0x1800184f9  mov     [rsp+38h+var_18], eax
0x1800184fd  mov     dword ptr [rdi+14h], 1
0x180018504  jmp     short loc_180018542
0x180018506  mov     edi, eax
0x180018508  mov     edx, 14h; unsigned __int16
0x18001850d  lea     rcx, aRtXactmq; "rt/XactMq"
0x180018514  call    ?LogIllegalPoint@@YAXPEA_WG@Z; LogIllegalPoint(wchar_t *,ushort)
0x180018519  mov     edx, 9Ch
0x18001851e  lea     rcx, aRtXactmq; "rt/XactMq"
0x180018525  call    cs:__imp_?ProduceRPCErrorTracing@@YAXPEA_WK@Z; ProduceRPCErrorTracing(wchar_t *,ulong)
0x18001852b  mov     ebx, 80004005h
0x180018530  mov     eax, 8004D016h
0x180018535  cmp     edi, 6BEh
0x18001853b  cmovz   ebx, eax
0x18001853e  mov     [rsp+38h+var_18], ebx
0x180018542  test    ebx, ebx
0x180018544  jns     short loc_180018567
0x180018546  mov     r8d, 1Eh
0x18001854c  jmp     short loc_180018559
0x18001854e  mov     r8d, 0Ah; unsigned __int16
0x180018554  mov     ebx, 8004D00Fh
0x180018559  lea     rdx, aRtXactmq; "rt/XactMq"
0x180018560  mov     ecx, ebx; int
0x180018562  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180018567  mov     eax, ebx
0x180018569  mov     rbx, [rsp+38h+arg_0]
0x18001856e  add     rsp, 30h
0x180018572  pop     rdi
0x180018573  retn
0x180024eb6  push    rbp
0x180024eb8  sub     rsp, 20h
0x180024ebc  mov     rbp, rdx
0x180024ebf  mov     rcx, [rcx]
0x180024ec2  mov     ecx, [rcx]; ExceptionCode
0x180024ec4  call    cs:__imp_I_RpcExceptionFilter
0x180024eca  nop
0x180024ecb  add     rsp, 20h
0x180024ecf  pop     rbp
0x180024ed0  retn
```
