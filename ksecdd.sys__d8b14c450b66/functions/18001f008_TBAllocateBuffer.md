# TBAllocateBuffer

- ea: `0x18001f008`
- end: `0x18001f04f`
- name: `TBAllocateBuffer`
- size: `71`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800049e8`
- `0x180023760`
- `0x180023a28`

## callees

- `0x18001f058`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18001f029`
- `ntoskrnl!ExAllocatePool2` at `0x18001f029`

## pseudocode

```c
_BOOL8 __fastcall TBAllocateBuffer(void **a1, unsigned int a2)
{
  __int64 Pool2; // rax

  TBFreeBuffer(a1);
  Pool2 = ExAllocatePool2(256, a2, 1765961556);
  *a1 = (void *)Pool2;
  return Pool2 != 0;
}

```

## disassembly

```asm
0x18001f008  mov     [rsp+arg_0], rbx
0x18001f00d  push    rdi
0x18001f00e  sub     rsp, 20h
0x18001f012  mov     ebx, edx
0x18001f014  mov     rdi, rcx
0x18001f017  call    TBFreeBuffer
0x18001f01c  mov     edx, ebx
0x18001f01e  mov     ecx, 100h
0x18001f023  mov     r8d, 69426F54h
0x18001f029  call    cs:__imp_ExAllocatePool2
0x18001f030  nop     dword ptr [rax+rax+00h]
0x18001f035  mov     rbx, [rsp+28h+arg_0]
0x18001f03a  mov     rdx, rax
0x18001f03d  mov     [rdi], rax
0x18001f040  xor     eax, eax
0x18001f042  test    rdx, rdx
0x18001f045  setnz   al
0x18001f048  add     rsp, 20h
0x18001f04c  pop     rdi
0x18001f04d  retn
```
