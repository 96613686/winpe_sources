# DigestAllocateMemory

- ea: `0x140008a70`
- end: `0x140008ac8`
- name: `DigestAllocateMemory`
- size: `88`
- prototype: `__int64 __fastcall(size_t Size)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x1400087d0`
- `0x140008f9c`
- `0x1400093fc`
- `0x140009460`
- `0x140009508`
- `0x140009678`
- `0x140009e7c`
- `0x140021590`

## callees

- `0x140008a70`
- `0x1400105c0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140008a98`
- `ntoskrnl!ExAllocatePool2` at `0x140008a98`

## pseudocode

```c
void *__fastcall DigestAllocateMemory(size_t Size)
{
  unsigned int v1; // edi
  __int64 v2; // rcx
  void *Pool2; // rax
  void *v4; // rbx

  v1 = Size;
  v2 = 64;
  if ( WDigestPoolType == PagedPool )
    v2 = 256;
  Pool2 = (void *)ExAllocatePool2(v2, v1, 1131836237);
  v4 = Pool2;
  if ( Pool2 )
    memset(Pool2, 0, v1);
  return v4;
}

```

## disassembly

```asm
0x140008a70  mov     [rsp+arg_0], rbx
0x140008a75  push    rdi
0x140008a76  sub     rsp, 20h
0x140008a7a  cmp     cs:?WDigestPoolType@@3W4_POOL_TYPE@@A, 1; _POOL_TYPE WDigestPoolType
0x140008a81  mov     eax, 100h
0x140008a86  mov     edi, ecx
0x140008a88  mov     r8d, 4376734Dh
0x140008a8e  mov     ecx, 40h ; '@'
0x140008a93  mov     edx, edi
0x140008a95  cmovz   ecx, eax
0x140008a98  call    cs:__imp_ExAllocatePool2
0x140008a9f  nop     dword ptr [rax+rax+00h]
0x140008aa4  mov     rbx, rax
0x140008aa7  test    rax, rax
0x140008aaa  jz      short loc_140008AB9
0x140008aac  mov     r8d, edi; Size
0x140008aaf  xor     edx, edx; Val
0x140008ab1  mov     rcx, rax; void *
0x140008ab4  call    memset
0x140008ab9  mov     rax, rbx
0x140008abc  mov     rbx, [rsp+28h+arg_0]
0x140008ac1  add     rsp, 20h
0x140008ac5  pop     rdi
0x140008ac6  retn
```
