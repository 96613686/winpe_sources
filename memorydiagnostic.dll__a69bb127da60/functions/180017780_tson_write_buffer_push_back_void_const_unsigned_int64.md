# tson::write_buffer::push_back(void const *,unsigned __int64)

- ea: `0x180017780`
- end: `0x1800177ec`
- name: `?push_back@write_buffer@tson@@QEAA_NPEBX_K@Z`
- size: `108`
- prototype: `bool __fastcall(void **this, const void *, rsize_t)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x1800066a8`
- `0x180006740`
- `0x180016954`
- `0x1800179fc`
- `0x18001807c`
- `0x180019308`
- `0x18001951c`

## callees

- `0x180017780`
- `0x180017944`
- `0x1800196f0`

## pseudocode

```c
bool __fastcall tson::write_buffer::push_back(void **this, const void *a2, rsize_t a3)
{
  bool result; // al

  if ( (_BYTE *)this[260] - (_BYTE *)this[259] >= a3
    || (result = tson::write_buffer::reserve((tson::write_buffer *)this, a3)) )
  {
    memcpy_s(this[259], (_BYTE *)this[260] - (_BYTE *)this[259], a2, a3);
    this[259] = (char *)this[259] + a3;
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x180017780  mov     [rsp+arg_0], rbx
0x180017785  mov     [rsp+arg_8], rsi
0x18001778a  push    rdi
0x18001778b  sub     rsp, 20h
0x18001778f  mov     rax, [rcx+820h]
0x180017796  mov     rdi, r8
0x180017799  sub     rax, [rcx+818h]
0x1800177a0  mov     rsi, rdx
0x1800177a3  mov     rbx, rcx
0x1800177a6  cmp     rax, r8
0x1800177a9  jnb     short loc_1800177B7
0x1800177ab  mov     rdx, r8; unsigned __int64
0x1800177ae  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x1800177b3  test    al, al
0x1800177b5  jz      short loc_1800177DC
0x1800177b7  mov     rcx, [rbx+818h]; Destination
0x1800177be  mov     r9, rdi; SourceSize
0x1800177c1  mov     rdx, [rbx+820h]
0x1800177c8  mov     r8, rsi; Source
0x1800177cb  sub     rdx, rcx; DestinationSize
0x1800177ce  call    memcpy_s
0x1800177d3  add     [rbx+818h], rdi
0x1800177da  mov     al, 1
0x1800177dc  mov     rbx, [rsp+28h+arg_0]
0x1800177e1  mov     rsi, [rsp+28h+arg_8]
0x1800177e6  add     rsp, 20h
0x1800177ea  pop     rdi
0x1800177eb  retn
```
