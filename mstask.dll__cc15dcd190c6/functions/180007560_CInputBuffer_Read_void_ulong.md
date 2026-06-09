# CInputBuffer::Read(void *,ulong)

- ea: `0x180007560`
- end: `0x1800075a2`
- name: `?Read@CInputBuffer@@QEAAHPEAXK@Z`
- size: `66`
- prototype: `int(CInputBuffer *__hidden this, void *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002ea0`

## callees

- `0x180007560`
- `0x18001aa82`

## pseudocode

```c
__int64 __fastcall CInputBuffer::Read(CInputBuffer *this, void *a2, unsigned int a3)
{
  __int64 v3; // rdi

  v3 = a3;
  if ( *(_QWORD *)this + (unsigned __int64)a3 > *((_QWORD *)this + 1) )
    return 0;
  memcpy_0(a2, *(const void **)this, a3);
  *(_QWORD *)this += v3;
  return 1;
}

```

## disassembly

```asm
0x180007560  mov     [rsp+arg_0], rbx
0x180007565  push    rdi
0x180007566  sub     rsp, 20h
0x18000756a  mov     r9, rdx
0x18000756d  mov     edi, r8d
0x180007570  mov     rdx, [rcx]; Src
0x180007573  mov     rbx, rcx
0x180007576  lea     rax, [rdx+rdi]
0x18000757a  cmp     rax, [rcx+8]
0x18000757e  ja      short loc_18000759E
0x180007580  mov     r8d, edi; Size
0x180007583  mov     rcx, r9; void *
0x180007586  call    memcpy_0
0x18000758b  add     [rbx], rdi
0x18000758e  mov     eax, 1
0x180007593  mov     rbx, [rsp+28h+arg_0]
0x180007598  add     rsp, 20h
0x18000759c  pop     rdi
0x18000759d  retn
0x18000759e  xor     eax, eax
0x1800075a0  jmp     short loc_180007593
```
