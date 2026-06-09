# tson::write_buffer::push_back(void const *,unsigned __int64)

- ea: `0x180018458`
- end: `0x1800184c5`
- name: `?push_back@write_buffer@tson@@QEAA_NPEBX_K@Z`
- size: `109`
- prototype: `bool(tson::write_buffer *__hidden this, const void *, unsigned __int64)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x1800065b4`
- `0x18000664c`
- `0x18001758c`
- `0x180018a6c`
- `0x180019060`
- `0x18001a160`
- `0x18001a380`

## callees

- `0x180018458`
- `0x18001873c`
- `0x18001a6ac`

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
0x180018458  mov     [rsp+arg_0], rbx
0x18001845d  mov     [rsp+arg_8], rsi
0x180018462  push    rdi
0x180018463  sub     rsp, 20h
0x180018467  mov     rax, [rcx+820h]
0x18001846e  mov     rdi, r8
0x180018471  sub     rax, [rcx+818h]
0x180018478  mov     rsi, rdx
0x18001847b  mov     rbx, rcx
0x18001847e  cmp     rax, r8
0x180018481  jnb     short loc_18001848F
0x180018483  mov     rdx, r8; unsigned __int64
0x180018486  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18001848b  test    al, al
0x18001848d  jz      short loc_1800184B4
0x18001848f  mov     rcx, [rbx+818h]; Destination
0x180018496  mov     r9, rdi; SourceSize
0x180018499  mov     rdx, [rbx+820h]
0x1800184a0  mov     r8, rsi; Source
0x1800184a3  sub     rdx, rcx; DestinationSize
0x1800184a6  call    memcpy_s
0x1800184ab  add     [rbx+818h], rdi
0x1800184b2  mov     al, 1
0x1800184b4  mov     rbx, [rsp+28h+arg_0]
0x1800184b9  mov     rsi, [rsp+28h+arg_8]
0x1800184be  add     rsp, 20h
0x1800184c2  pop     rdi
0x1800184c3  retn
```
