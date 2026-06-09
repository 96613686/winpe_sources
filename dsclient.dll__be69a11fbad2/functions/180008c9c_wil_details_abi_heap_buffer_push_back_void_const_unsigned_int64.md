# wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)

- ea: `0x180008c9c`
- end: `0x180008cf7`
- name: `?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z`
- size: `91`
- prototype: `bool __fastcall(void **this, const void *, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180006bb0`
- `0x180007fd8`
- `0x180008194`

## callees

- `0x180008c6c`
- `0x180008c9c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180008cdb`
- `msvcrt!memcpy_s` at `0x180008cdb`

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
0x180008c9c  mov     [rsp+arg_0], rbx
0x180008ca1  mov     [rsp+arg_8], rsi
0x180008ca6  push    rdi
0x180008ca7  sub     rsp, 20h
0x180008cab  mov     rsi, rdx
0x180008cae  mov     rdi, r8
0x180008cb1  mov     rdx, r8; unsigned __int64
0x180008cb4  mov     rbx, rcx
0x180008cb7  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180008cbc  test    al, al
0x180008cbe  jz      short loc_180008CE7
0x180008cc0  mov     rcx, [rbx+8]; Destination
0x180008cc4  mov     r9, rdi; SourceSize
0x180008cc7  mov     rax, [rbx+10h]
0x180008ccb  mov     r8, rsi; Source
0x180008cce  sub     rax, rcx
0x180008cd1  cmp     rcx, [rbx+10h]
0x180008cd5  sbb     rdx, rdx
0x180008cd8  and     rdx, rax; DestinationSize
0x180008cdb  call    cs:__imp_memcpy_s
0x180008ce1  add     [rbx+8], rdi
0x180008ce5  mov     al, 1
0x180008ce7  mov     rbx, [rsp+28h+arg_0]
0x180008cec  mov     rsi, [rsp+28h+arg_8]
0x180008cf1  add     rsp, 20h
0x180008cf5  pop     rdi
0x180008cf6  retn
```
