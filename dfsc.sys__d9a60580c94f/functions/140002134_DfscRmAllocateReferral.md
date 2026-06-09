# DfscRmAllocateReferral

- ea: `0x140002134`
- end: `0x140002196`
- name: `DfscRmAllocateReferral`
- size: `98`
- prototype: `_WORD *__fastcall(size_t Size, unsigned int)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x140001df8`
- `0x140001f4c`
- `0x1400051d0`
- `0x14001935c`
- `0x14001bfe4`
- `0x14002774c`

## callees

- `0x140002134`
- `0x140006380`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000214f`
- `ntoskrnl!ExAllocatePool2` at `0x14000214f`

## pseudocode

```c
_WORD *__fastcall DfscRmAllocateReferral(size_t Size, unsigned int a2)
{
  unsigned int v2; // edi
  _WORD *result; // rax
  _WORD *v4; // rbx

  v2 = Size;
  result = (_WORD *)ExAllocatePool2(258, (unsigned int)Size, a2);
  v4 = result;
  if ( result )
  {
    memset(result, 0, v2);
    result = v4;
    *v4 = -32509;
    v4[1] = v2;
    *((_DWORD *)v4 + 1) = 1;
  }
  return result;
}

```

## disassembly

```asm
0x140002134  mov     [rsp+arg_0], rbx
0x140002139  mov     [rsp+arg_8], rsi
0x14000213e  push    rdi
0x14000213f  sub     rsp, 20h
0x140002143  mov     r8d, edx
0x140002146  mov     edi, ecx
0x140002148  mov     edx, ecx
0x14000214a  mov     ecx, 102h
0x14000214f  call    cs:__imp_ExAllocatePool2
0x140002156  nop     dword ptr [rax+rax+00h]
0x14000215b  mov     rbx, rax
0x14000215e  test    rax, rax
0x140002161  jz      short loc_140002194
0x140002163  mov     r8d, edi; Size
0x140002166  xor     edx, edx; Val
0x140002168  mov     rcx, rax; void *
0x14000216b  call    memset
0x140002170  mov     rax, rbx
0x140002173  mov     word ptr [rbx], 8103h
0x140002178  mov     [rbx+2], di
0x14000217c  mov     dword ptr [rbx+4], 1
0x140002183  mov     rbx, [rsp+28h+arg_0]
0x140002188  mov     rsi, [rsp+28h+arg_8]
0x14000218d  add     rsp, 20h
0x140002191  pop     rdi
0x140002192  retn
0x140002194  jmp     short loc_140002183
```
