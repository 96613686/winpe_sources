# KerbDeleteKernelContext

- ea: `0x140020920`
- end: `0x140020976`
- name: `KerbDeleteKernelContext`
- size: `86`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140020920`
- `0x140025df0`
- `0x140025e28`

## pseudocode

```c
__int64 __fastcall KerbDeleteKernelContext(__int64 a1, _QWORD *a2)
{
  _QWORD *v2; // rbx
  __int64 v4; // rax
  int v6; // ebx

  v2 = a2;
  LOBYTE(a2) = 1;
  v4 = KerbReferenceContext(a1, a2);
  if ( v4 )
  {
    *v2 = *(_QWORD *)(v4 + 88);
    v6 = *(_DWORD *)(v4 + 156) & 0x100;
    KerbDereferenceContext((PVOID)v4);
    return v6 != 0 ? 0x90323 : 0;
  }
  else
  {
    *v2 = a1;
    return 3221225480LL;
  }
}

```

## disassembly

```asm
0x140020920  mov     [rsp+arg_0], rbx
0x140020925  push    rdi
0x140020926  sub     rsp, 20h
0x14002092a  mov     rbx, rdx
0x14002092d  mov     rdi, rcx
0x140020930  mov     dl, 1
0x140020932  call    KerbReferenceContext
0x140020937  mov     rcx, rax; P
0x14002093a  test    rax, rax
0x14002093d  jnz     short loc_140020949
0x14002093f  mov     [rbx], rdi
0x140020942  mov     eax, 0C0000008h
0x140020947  jmp     short loc_14002096A
0x140020949  mov     rax, [rax+58h]
0x14002094d  mov     [rbx], rax
0x140020950  mov     ebx, [rcx+9Ch]
0x140020956  and     ebx, 100h
0x14002095c  call    KerbDereferenceContext
0x140020961  neg     ebx
0x140020963  sbb     eax, eax
0x140020965  and     eax, 90323h
0x14002096a  mov     rbx, [rsp+28h+arg_0]
0x14002096f  add     rsp, 20h
0x140020973  pop     rdi
0x140020974  retn
```
