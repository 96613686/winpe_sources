# wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)

- ea: `0x18001527c`
- end: `0x1800152d7`
- name: `?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z`
- size: `91`
- prototype: `bool(wil::details_abi::heap_buffer *__hidden this, const void *, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x18000dcf0`
- `0x180011488`
- `0x1800115c8`
- `0x180012fe0`
- `0x180014608`
- `0x18001486c`

## callees

- `0x18001524c`
- `0x18001527c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800152bb`
- `msvcrt!memcpy_s` at `0x1800152bb`

## pseudocode

```c
bool __fastcall wil::details_abi::heap_buffer::push_back(void **this, const void *a2, unsigned __int64 a3)
{
  bool result; // al

  result = wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)this, a3);
  if ( result )
  {
    memcpy_s(this[1], ((_BYTE *)this[2] - (_BYTE *)this[1]) & -(__int64)(this[1] < this[2]), a2, a3);
    this[1] = (char *)this[1] + a3;
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x18001527c  mov     [rsp+arg_0], rbx
0x180015281  mov     [rsp+arg_8], rsi
0x180015286  push    rdi
0x180015287  sub     rsp, 20h
0x18001528b  mov     rsi, rdx
0x18001528e  mov     rdi, r8
0x180015291  mov     rdx, r8; unsigned __int64
0x180015294  mov     rbx, rcx
0x180015297  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18001529c  test    al, al
0x18001529e  jz      short loc_1800152C7
0x1800152a0  mov     rcx, [rbx+8]; Destination
0x1800152a4  mov     r9, rdi; SourceSize
0x1800152a7  mov     rax, [rbx+10h]
0x1800152ab  mov     r8, rsi; Source
0x1800152ae  sub     rax, rcx
0x1800152b1  cmp     rcx, [rbx+10h]
0x1800152b5  sbb     rdx, rdx
0x1800152b8  and     rdx, rax; DestinationSize
0x1800152bb  call    cs:__imp_memcpy_s
0x1800152c1  add     [rbx+8], rdi
0x1800152c5  mov     al, 1
0x1800152c7  mov     rbx, [rsp+28h+arg_0]
0x1800152cc  mov     rsi, [rsp+28h+arg_8]
0x1800152d1  add     rsp, 20h
0x1800152d5  pop     rdi
0x1800152d6  retn
```
