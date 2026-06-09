# DevAuthAlloc

- ea: `0x180003320`
- end: `0x180003369`
- name: `DevAuthAlloc`
- size: `73`
- prototype: `__int64 __fastcall(size_t Size)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000258c`
- `0x1800027dc`
- `0x180002d7c`
- `0x1800049c4`
- `0x180004e58`

## callees

- `0x180003320`
- `0x180006cc0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180003339`
- `ntoskrnl!ExAllocatePool2` at `0x180003339`

## pseudocode

```c
void *__fastcall DevAuthAlloc(size_t Size)
{
  unsigned int v1; // edi
  void *Pool2; // rax
  void *v3; // rbx

  v1 = Size;
  Pool2 = (void *)ExAllocatePool2(258, (unsigned int)Size, 1967220036);
  v3 = Pool2;
  if ( Pool2 )
    memset(Pool2, 0, v1);
  return v3;
}

```

## disassembly

```asm
0x180003320  mov     [rsp+arg_0], rbx
0x180003325  push    rdi
0x180003326  sub     rsp, 20h
0x18000332a  mov     edi, ecx
0x18000332c  mov     r8d, 75416544h
0x180003332  mov     edx, ecx
0x180003334  mov     ecx, 102h
0x180003339  call    cs:__imp_ExAllocatePool2
0x180003340  nop     dword ptr [rax+rax+00h]
0x180003345  mov     rbx, rax
0x180003348  test    rax, rax
0x18000334b  jz      short loc_18000335A
0x18000334d  mov     r8d, edi; Size
0x180003350  xor     edx, edx; Val
0x180003352  mov     rcx, rax; void *
0x180003355  call    memset
0x18000335a  mov     rax, rbx
0x18000335d  mov     rbx, [rsp+28h+arg_0]
0x180003362  add     rsp, 20h
0x180003366  pop     rdi
0x180003367  retn
```
