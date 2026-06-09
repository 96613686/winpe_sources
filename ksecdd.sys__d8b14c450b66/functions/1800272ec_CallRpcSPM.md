# CallRpcSPM

- ea: `0x1800272ec`
- end: `0x18002740f`
- name: `CallRpcSPM`
- size: `291`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1800018b0`
- `0x18001f610`
- `0x18001f7c0`

## callees

- `0x180004050`
- `0x1800048d8`
- `0x180010980`
- `0x1800272ec`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x180027378`
- `ntoskrnl!PsGetCurrentThreadId` at `0x180027378`
- `ntoskrnl!PsGetCurrentProcess` at `0x180027359`
- `ntoskrnl!PsGetCurrentProcess` at `0x180027359`
- `ntoskrnl!PsGetProcessId` at `0x180027368`
- `ntoskrnl!PsGetProcessId` at `0x180027368`
- `msrpc!I_RpcExceptionFilter` at `0x1800281e9`
- `msrpc!I_RpcExceptionFilter` at `0x1800281e9`

## pseudocode

```c
__int64 __fastcall CallRpcSPM(__int64 a1, __int64 a2, __int64 a3, void *a4)
{
  unsigned int v5; // edi
  int Pointer; // ebx
  struct _KPROCESS *CurrentProcess; // rax
  void *Src; // [rsp+38h] [rbp-50h] BYREF
  _BYTE v12[72]; // [rsp+40h] [rbp-48h] BYREF
  size_t Size; // [rsp+90h] [rbp+8h] BYREF
  int v14; // [rsp+A0h] [rbp+18h]
  void *v15; // [rsp+A8h] [rbp+20h]

  v15 = a4;
  v14 = a3;
  v5 = a3;
  LODWORD(Size) = 0;
  Src = 0;
  memset(v12, 0, 48);
  if ( a1 )
  {
    CurrentProcess = (struct _KPROCESS *)PsGetCurrentProcess(a1, a2, a3, a4);
    *(_QWORD *)(a2 + 8) = PsGetProcessId(CurrentProcess);
    *(_QWORD *)(a2 + 16) = PsGetCurrentThreadId();
    Pointer = (unsigned int)SspirCallRpc(a1, *(__int16 *)(a2 + 2), a2, (__int64)&Size, (__int64)&Src, (__int64)v12).Pointer;
    if ( Pointer >= 0 )
    {
      if ( (unsigned int)Size <= v5 )
        memmove(a4, Src, (unsigned int)Size);
      else
        Pointer = -1073741789;
    }
  }
  else
  {
    Pointer = -1073741504;
  }
  if ( Src )
    SspiLocalFree(Src);
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x1800272ec  mov     rax, rsp
0x1800272ef  mov     [rax+10h], rbx
0x1800272f3  mov     [rax+20h], r9
0x1800272f7  mov     [rax+18h], r8d
0x1800272fb  push    rsi
0x1800272fc  push    rdi
0x1800272fd  push    r14
0x1800272ff  sub     rsp, 70h
0x180027303  mov     rsi, r9
0x180027306  mov     edi, r8d
0x180027309  mov     rbx, rdx
0x18002730c  mov     r14, rcx
0x18002730f  mov     dword ptr [rax+8], 0
0x180027316  mov     qword ptr [rax-50h], 0
0x18002731e  xorps   xmm0, xmm0
0x180027321  movups  xmmword ptr [rax-48h], xmm0
0x180027325  movups  xmmword ptr [rax-38h], xmm0
0x180027329  movups  xmmword ptr [rax-28h], xmm0
0x18002732d  test    rcx, rcx
0x180027330  jnz     short loc_180027359
0x180027332  mov     ebx, 0C0000140h
0x180027337  mov     rcx, [rsp+88h+Src]; DataBuffer
0x18002733c  test    rcx, rcx
0x18002733f  jnz     loc_180027405
0x180027345  mov     eax, ebx
0x180027347  mov     rbx, [rsp+88h+arg_8]
0x18002734f  add     rsp, 70h
0x180027353  pop     r14
0x180027355  pop     rdi
0x180027356  pop     rsi
0x180027357  retn
0x180027359  call    cs:__imp_PsGetCurrentProcess
0x180027360  nop     dword ptr [rax+rax+00h]
0x180027365  mov     rcx, rax; Process
0x180027368  call    cs:__imp_PsGetProcessId
0x18002736f  nop     dword ptr [rax+rax+00h]
0x180027374  mov     [rbx+8], rax
0x180027378  call    cs:__imp_PsGetCurrentThreadId
0x18002737f  nop     dword ptr [rax+rax+00h]
0x180027384  mov     [rbx+10h], rax
0x180027388  movsx   edx, word ptr [rbx+2]
0x18002738c  lea     rax, [rsp+88h+var_48]
0x180027391  mov     [rsp+88h+var_60], rax
0x180027396  lea     rax, [rsp+88h+Src]
0x18002739b  mov     [rsp+88h+var_68], rax
0x1800273a0  lea     r9, [rsp+88h+Size]
0x1800273a8  mov     r8, rbx
0x1800273ab  mov     rcx, r14
0x1800273ae  call    SspirCallRpc
0x1800273b3  mov     ebx, eax
0x1800273b5  mov     [rsp+88h+var_58], eax
0x1800273b9  jmp     short loc_1800273D0
0x1800273bb  mov     ebx, eax
0x1800273bd  mov     [rsp+88h+var_58], eax
0x1800273c1  mov     rsi, [rsp+88h+arg_18]
0x1800273c9  mov     edi, [rsp+88h+arg_10]
0x1800273d0  test    ebx, ebx
0x1800273d2  js      loc_180027337
0x1800273d8  cmp     dword ptr [rsp+88h+Size], edi
0x1800273df  jbe     short loc_1800273EB
0x1800273e1  mov     ebx, 0C0000023h
0x1800273e6  jmp     loc_180027337
0x1800273eb  mov     r8d, dword ptr [rsp+88h+Size]; Size
0x1800273f3  mov     rdx, [rsp+88h+Src]; Src
0x1800273f8  mov     rcx, rsi; void *
0x1800273fb  call    memmove
0x180027400  jmp     loc_180027337
0x180027405  call    SspiLocalFree
0x18002740a  jmp     loc_180027345
0x1800281db  push    rbp
0x1800281dd  sub     rsp, 30h
0x1800281e1  mov     rbp, rdx
0x1800281e4  mov     rcx, [rcx]
0x1800281e7  mov     ecx, [rcx]; ExceptionCode
0x1800281e9  call    cs:__imp_I_RpcExceptionFilter
0x1800281f0  nop     dword ptr [rax+rax+00h]
0x1800281f5  nop
0x1800281f6  add     rsp, 30h
0x1800281fa  pop     rbp
0x1800281fb  retn
```
