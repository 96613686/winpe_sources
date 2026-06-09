# NfsRdrpInitializeOutboundGssContext

- ea: `0x1400298b0`
- end: `0x140029983`
- name: `NfsRdrpInitializeOutboundGssContext`
- size: `211`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140001f10`
- `0x14002998c`

## callees

- `0x140028d14`
- `0x1400298b0`

## import_xrefs

- `rpcxdr!OncRpcDestroyOutboundGssContext` at `0x140029960`
- `rpcxdr!OncRpcDestroyOutboundGssContext` at `0x140029960`
- `rpcxdr!OncRpcDisestablishOutboundGssContext` at `0x140029951`
- `rpcxdr!OncRpcDisestablishOutboundGssContext` at `0x140029951`
- `rpcxdr!OncRpcEstablishOutboundGssContext` at `0x14002991b`
- `rpcxdr!OncRpcEstablishOutboundGssContext` at `0x14002991b`
- `rpcxdr!OncRpcCreateOutboundGssContext` at `0x1400298df`
- `rpcxdr!OncRpcCreateOutboundGssContext` at `0x1400298df`

## pseudocode

```c
__int64 __fastcall NfsRdrpInitializeOutboundGssContext(__int64 a1, _QWORD *a2, __int64 a3, _QWORD *a4)
{
  __int64 v5; // rbp
  _QWORD *v7; // rsi
  __int64 v8; // rcx
  __int64 v9; // r15
  int OutboundGssContext; // edi
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rax

  v5 = a2[5];
  v7 = (_QWORD *)a2[13];
  v8 = *(_QWORD *)(a2[4] + 32LL);
  v9 = *(_QWORD *)(v8 + 32);
  OutboundGssContext = OncRpcCreateOutboundGssContext(*(_QWORD *)(v8 + 64), v5 + 124);
  if ( OutboundGssContext < 0
    || (!v7 ? (v11 = 0, v12 = 0, v13 = 0) : (v11 = v7[4], v12 = v7[2], v13 = v7[3]),
        (OutboundGssContext = OncRpcEstablishOutboundGssContext(*a4, v5 + 168, v11, v12, v13), OutboundGssContext < 0)
     || (OutboundGssContext = NfsRdrpEstablishGssContextWithRemoteServer(a1, *a4, v9 + 72), OutboundGssContext < 0)) )
  {
    if ( *a4 )
    {
      if ( (*(_DWORD *)(*a4 + 60LL) & 1) != 0 )
        OncRpcDisestablishOutboundGssContext();
      OncRpcDestroyOutboundGssContext(*a4);
    }
    *a4 = 0;
  }
  return (unsigned int)OutboundGssContext;
}

```

## disassembly

```asm
0x1400298b0  push    rbx
0x1400298b2  push    rbp
0x1400298b3  push    rsi
0x1400298b4  push    rdi
0x1400298b5  push    r14
0x1400298b7  push    r15
0x1400298b9  sub     rsp, 38h
0x1400298bd  mov     rax, [rdx+20h]
0x1400298c1  mov     r14, rcx
0x1400298c4  mov     rbp, [rdx+28h]
0x1400298c8  mov     rbx, r9
0x1400298cb  mov     rsi, [rdx+68h]
0x1400298cf  mov     rcx, [rax+20h]
0x1400298d3  lea     rdx, [rbp+7Ch]
0x1400298d7  mov     r15, [rcx+20h]
0x1400298db  mov     rcx, [rcx+40h]
0x1400298df  call    cs:__imp_OncRpcCreateOutboundGssContext
0x1400298e6  nop     dword ptr [rax+rax+00h]
0x1400298eb  mov     edi, eax
0x1400298ed  test    eax, eax
0x1400298ef  js      short loc_140029942
0x1400298f1  test    rsi, rsi
0x1400298f4  jz      short loc_140029904
0x1400298f6  mov     r8, [rsi+20h]
0x1400298fa  mov     r9, [rsi+10h]
0x1400298fe  mov     rax, [rsi+18h]
0x140029902  jmp     short loc_14002990C
0x140029904  xor     r8d, r8d
0x140029907  xor     r9d, r9d
0x14002990a  xor     eax, eax
0x14002990c  mov     rcx, [rbx]
0x14002990f  lea     rdx, [rbp+0A8h]
0x140029916  mov     [rsp+68h+var_48], rax
0x14002991b  call    cs:__imp_OncRpcEstablishOutboundGssContext
0x140029922  nop     dword ptr [rax+rax+00h]
0x140029927  mov     edi, eax
0x140029929  test    eax, eax
0x14002992b  js      short loc_140029942
0x14002992d  mov     rdx, [rbx]
0x140029930  lea     r8, [r15+48h]
0x140029934  mov     rcx, r14
0x140029937  call    NfsRdrpEstablishGssContextWithRemoteServer
0x14002993c  mov     edi, eax
0x14002993e  test    eax, eax
0x140029940  jns     short loc_140029973
0x140029942  mov     rcx, [rbx]
0x140029945  test    rcx, rcx
0x140029948  jz      short loc_14002996C
0x14002994a  mov     eax, [rcx+3Ch]
0x14002994d  test    al, 1
0x14002994f  jz      short loc_14002995D
0x140029951  call    cs:__imp_OncRpcDisestablishOutboundGssContext
0x140029958  nop     dword ptr [rax+rax+00h]
0x14002995d  mov     rcx, [rbx]
0x140029960  call    cs:__imp_OncRpcDestroyOutboundGssContext
0x140029967  nop     dword ptr [rax+rax+00h]
0x14002996c  mov     qword ptr [rbx], 0
0x140029973  mov     eax, edi
0x140029975  add     rsp, 38h
0x140029979  pop     r15
0x14002997b  pop     r14
0x14002997d  pop     rdi
0x14002997e  pop     rsi
0x14002997f  pop     rbp
0x140029980  pop     rbx
0x140029981  retn
```
