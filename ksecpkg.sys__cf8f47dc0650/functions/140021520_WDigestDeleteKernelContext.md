# WDigestDeleteKernelContext

- ea: `0x140021520`
- end: `0x14002157b`
- name: `WDigestDeleteKernelContext`
- size: `91`
- prototype: `__int64 __fastcall(unsigned __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x14000936c`
- `0x140021520`
- `0x1400285b8`

## pseudocode

```c
__int64 __fastcall WDigestDeleteKernelContext(unsigned __int64 a1, _QWORD *a2)
{
  __int64 result; // rax
  unsigned int v5; // edi

  result = WDigestReferenceContext();
  v5 = result;
  if ( (int)result >= 0 )
  {
    if ( *(int *)(a1 + 28) > 0 )
    {
      *a2 = *(_QWORD *)(a1 + 8);
      WDigestDerefContext(a1);
      return v5;
    }
    else
    {
      WDigestDerefContext(a1);
      return 3221225524LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140021520  mov     [rsp+arg_0], rbx
0x140021525  mov     [rsp+arg_8], rsi
0x14002152a  push    rdi
0x14002152b  sub     rsp, 20h
0x14002152f  mov     rsi, rdx
0x140021532  mov     rbx, rcx
0x140021535  call    WDigestReferenceContext
0x14002153a  mov     edi, eax
0x14002153c  test    eax, eax
0x14002153e  js      short loc_14002156A
0x140021540  cmp     dword ptr [rbx+1Ch], 0
0x140021544  mov     rcx, rbx; unsigned __int64
0x140021547  jg      short loc_140021557
0x140021549  xor     edx, edx
0x14002154b  call    WDigestDerefContext
0x140021550  mov     eax, 0C0000034h
0x140021555  jmp     short loc_14002156A
0x140021557  mov     rax, [rbx+8]
0x14002155b  mov     edx, 1
0x140021560  mov     [rsi], rax
0x140021563  call    WDigestDerefContext
0x140021568  mov     eax, edi
0x14002156a  mov     rbx, [rsp+28h+arg_0]
0x14002156f  mov     rsi, [rsp+28h+arg_8]
0x140021574  add     rsp, 20h
0x140021578  pop     rdi
0x140021579  retn
```
