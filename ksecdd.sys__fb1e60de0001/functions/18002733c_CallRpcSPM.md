# CallRpcSPM

- ea: `0x18002733c`
- end: `0x18002745f`
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
- `0x180010a00`
- `0x18002733c`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x1800273c8`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1800273c8`
- `ntoskrnl!PsGetCurrentProcess` at `0x1800273a9`
- `ntoskrnl!PsGetCurrentProcess` at `0x1800273a9`
- `ntoskrnl!PsGetProcessId` at `0x1800273b8`
- `ntoskrnl!PsGetProcessId` at `0x1800273b8`
- `msrpc!I_RpcExceptionFilter` at `0x180028239`
- `msrpc!I_RpcExceptionFilter` at `0x180028239`

## pseudocode

```c
__int64 __fastcall CallRpcSPM(__int64 a1, __int64 a2, __int64 a3, void *a4)
{
  unsigned int v5; // edi
  int v7; // r14d
  int v8; // ebx
  struct _KPROCESS *CurrentProcess; // rax
  void *Src; // [rsp+38h] [rbp-50h] BYREF
  _BYTE v12[72]; // [rsp+40h] [rbp-48h] BYREF
  size_t Size; // [rsp+90h] [rbp+8h] BYREF
  int v14; // [rsp+A0h] [rbp+18h]
  void *v15; // [rsp+A8h] [rbp+20h]

  v15 = a4;
  v14 = a3;
  v5 = a3;
  v7 = a1;
  LODWORD(Size) = 0;
  Src = 0;
  memset(v12, 0, 48);
  if ( a1 )
  {
    CurrentProcess = (struct _KPROCESS *)PsGetCurrentProcess(a1, a2, a3, a4);
    *(_QWORD *)(a2 + 8) = PsGetProcessId(CurrentProcess);
    *(_QWORD *)(a2 + 16) = PsGetCurrentThreadId();
    v8 = SspirCallRpc(v7, *(__int16 *)(a2 + 2), a2, (unsigned int)&Size, (__int64)&Src, (__int64)v12);
    if ( v8 >= 0 )
    {
      if ( (unsigned int)Size <= v5 )
        memmove(a4, Src, (unsigned int)Size);
      else
        v8 = -1073741789;
    }
  }
  else
  {
    v8 = -1073741504;
  }
  if ( Src )
    SspiLocalFree(Src);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18002733c  mov     rax, rsp
0x18002733f  mov     [rax+10h], rbx
0x180027343  mov     [rax+20h], r9
0x180027347  mov     [rax+18h], r8d
0x18002734b  push    rsi
0x18002734c  push    rdi
0x18002734d  push    r14
0x18002734f  sub     rsp, 70h
0x180027353  mov     rsi, r9
0x180027356  mov     edi, r8d
0x180027359  mov     rbx, rdx
0x18002735c  mov     r14, rcx
0x18002735f  mov     dword ptr [rax+8], 0
0x180027366  mov     qword ptr [rax-50h], 0
0x18002736e  xorps   xmm0, xmm0
0x180027371  movups  xmmword ptr [rax-48h], xmm0
0x180027375  movups  xmmword ptr [rax-38h], xmm0
0x180027379  movups  xmmword ptr [rax-28h], xmm0
0x18002737d  test    rcx, rcx
0x180027380  jnz     short loc_1800273A9
0x180027382  mov     ebx, 0C0000140h
0x180027387  mov     rcx, [rsp+88h+Src]; DataBuffer
0x18002738c  test    rcx, rcx
0x18002738f  jnz     loc_180027455
0x180027395  mov     eax, ebx
0x180027397  mov     rbx, [rsp+88h+arg_8]
0x18002739f  add     rsp, 70h
0x1800273a3  pop     r14
0x1800273a5  pop     rdi
0x1800273a6  pop     rsi
0x1800273a7  retn
0x1800273a9  call    cs:__imp_PsGetCurrentProcess
0x1800273b0  nop     dword ptr [rax+rax+00h]
0x1800273b5  mov     rcx, rax; Process
0x1800273b8  call    cs:__imp_PsGetProcessId
0x1800273bf  nop     dword ptr [rax+rax+00h]
0x1800273c4  mov     [rbx+8], rax
0x1800273c8  call    cs:__imp_PsGetCurrentThreadId
0x1800273cf  nop     dword ptr [rax+rax+00h]
0x1800273d4  mov     [rbx+10h], rax
0x1800273d8  movsx   edx, word ptr [rbx+2]
0x1800273dc  lea     rax, [rsp+88h+var_48]
0x1800273e1  mov     [rsp+88h+var_60], rax
0x1800273e6  lea     rax, [rsp+88h+Src]
0x1800273eb  mov     [rsp+88h+var_68], rax
0x1800273f0  lea     r9, [rsp+88h+Size]
0x1800273f8  mov     r8, rbx
0x1800273fb  mov     rcx, r14
0x1800273fe  call    SspirCallRpc
0x180027403  mov     ebx, eax
0x180027405  mov     [rsp+88h+var_58], eax
0x180027409  jmp     short loc_180027420
0x18002740b  mov     ebx, eax
0x18002740d  mov     [rsp+88h+var_58], eax
0x180027411  mov     rsi, [rsp+88h+arg_18]
0x180027419  mov     edi, [rsp+88h+arg_10]
0x180027420  test    ebx, ebx
0x180027422  js      loc_180027387
0x180027428  cmp     dword ptr [rsp+88h+Size], edi
0x18002742f  jbe     short loc_18002743B
0x180027431  mov     ebx, 0C0000023h
0x180027436  jmp     loc_180027387
0x18002743b  mov     r8d, dword ptr [rsp+88h+Size]; Size
0x180027443  mov     rdx, [rsp+88h+Src]; Src
0x180027448  mov     rcx, rsi; void *
0x18002744b  call    memmove
0x180027450  jmp     loc_180027387
0x180027455  call    SspiLocalFree
0x18002745a  jmp     loc_180027395
0x18002822b  push    rbp
0x18002822d  sub     rsp, 30h
0x180028231  mov     rbp, rdx
0x180028234  mov     rcx, [rcx]
0x180028237  mov     ecx, [rcx]; ExceptionCode
0x180028239  call    cs:__imp_I_RpcExceptionFilter
0x180028240  nop     dword ptr [rax+rax+00h]
0x180028245  nop
0x180028246  add     rsp, 30h
0x18002824a  pop     rbp
0x18002824b  retn
```
