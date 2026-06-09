# tson::write_buffer::push_back(void const *,unsigned __int64)

- ea: `0x14000c584`
- end: `0x14000c5f1`
- name: `?push_back@write_buffer@tson@@QEAA_NPEBX_K@Z`
- size: `109`
- prototype: `bool(tson::write_buffer *__hidden this, const void *, unsigned __int64)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x1400036d4`
- `0x140004138`
- `0x140004190`
- `0x1400041e8`
- `0x14000c140`
- `0x14000cacc`
- `0x14000da08`
- `0x14000db3c`

## callees

- `0x14000c584`
- `0x14000c888`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14000c5d2`
- `msvcrt!memcpy_s` at `0x14000c5d2`

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
0x14000c584  mov     [rsp+arg_0], rbx
0x14000c589  mov     [rsp+arg_8], rsi
0x14000c58e  push    rdi
0x14000c58f  sub     rsp, 20h
0x14000c593  mov     rax, [rcx+820h]
0x14000c59a  mov     rdi, r8
0x14000c59d  sub     rax, [rcx+818h]
0x14000c5a4  mov     rsi, rdx
0x14000c5a7  mov     rbx, rcx
0x14000c5aa  cmp     rax, r8
0x14000c5ad  jnb     short loc_14000C5BB
0x14000c5af  mov     rdx, r8; unsigned __int64
0x14000c5b2  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x14000c5b7  test    al, al
0x14000c5b9  jz      short loc_14000C5E1
0x14000c5bb  mov     rcx, [rbx+818h]; Destination
0x14000c5c2  mov     r9, rdi; SourceSize
0x14000c5c5  mov     rdx, [rbx+820h]
0x14000c5cc  mov     r8, rsi; Source
0x14000c5cf  sub     rdx, rcx; DestinationSize
0x14000c5d2  call    cs:__imp_memcpy_s
0x14000c5d8  add     [rbx+818h], rdi
0x14000c5df  mov     al, 1
0x14000c5e1  mov     rbx, [rsp+28h+arg_0]
0x14000c5e6  mov     rsi, [rsp+28h+arg_8]
0x14000c5eb  add     rsp, 20h
0x14000c5ef  pop     rdi
0x14000c5f0  retn
```
