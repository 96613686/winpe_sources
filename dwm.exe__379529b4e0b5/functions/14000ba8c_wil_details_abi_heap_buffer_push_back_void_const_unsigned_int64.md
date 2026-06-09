# wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)

- ea: `0x14000ba8c`
- end: `0x14000bae6`
- name: `?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z`
- size: `90`
- prototype: `bool(wil::details_abi::heap_buffer *__hidden this, const void *, unsigned __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140009c24`
- `0x14000aeac`
- `0x14000af4c`
- `0x14000d124`

## callees

- `0x14000b9a0`
- `0x14000ba8c`
- `0x14000bebc`

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
0x14000ba8c  mov     [rsp+arg_0], rbx
0x14000ba91  mov     [rsp+arg_8], rsi
0x14000ba96  push    rdi
0x14000ba97  sub     rsp, 20h
0x14000ba9b  mov     rsi, rdx
0x14000ba9e  mov     rdi, r8
0x14000baa1  mov     rdx, r8; unsigned __int64
0x14000baa4  mov     rbx, rcx
0x14000baa7  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x14000baac  test    al, al
0x14000baae  jz      short loc_14000BAD6
0x14000bab0  mov     rcx, [rbx+8]; Destination
0x14000bab4  mov     r9, rdi; SourceSize
0x14000bab7  mov     rax, [rbx+10h]
0x14000babb  mov     r8, rsi; Source
0x14000babe  sub     rax, rcx
0x14000bac1  cmp     rcx, [rbx+10h]
0x14000bac5  sbb     rdx, rdx
0x14000bac8  and     rdx, rax; DestinationSize
0x14000bacb  call    memcpy_s
0x14000bad0  add     [rbx+8], rdi
0x14000bad4  mov     al, 1
0x14000bad6  mov     rbx, [rsp+28h+arg_0]
0x14000badb  mov     rsi, [rsp+28h+arg_8]
0x14000bae0  add     rsp, 20h
0x14000bae4  pop     rdi
0x14000bae5  retn
```
