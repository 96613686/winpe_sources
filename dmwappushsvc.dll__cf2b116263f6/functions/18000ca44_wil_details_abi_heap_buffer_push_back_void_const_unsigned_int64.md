# wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)

- ea: `0x18000ca44`
- end: `0x18000ca9e`
- name: `?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z`
- size: `90`
- prototype: `bool __fastcall(void **this, const void *, unsigned __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180009dd8`
- `0x180009ec4`
- `0x18000b604`
- `0x18000b85c`

## callees

- `0x180006094`
- `0x18000c6ec`
- `0x18000ca44`

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
0x18000ca44  mov     [rsp+arg_0], rbx
0x18000ca49  mov     [rsp+arg_8], rsi
0x18000ca4e  push    rdi
0x18000ca4f  sub     rsp, 20h
0x18000ca53  mov     rsi, rdx
0x18000ca56  mov     rdi, r8
0x18000ca59  mov     rdx, r8; unsigned __int64
0x18000ca5c  mov     rbx, rcx
0x18000ca5f  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000ca64  test    al, al
0x18000ca66  jz      short loc_18000CA8E
0x18000ca68  mov     rcx, [rbx+8]; Destination
0x18000ca6c  mov     r9, rdi; SourceSize
0x18000ca6f  mov     rax, [rbx+10h]
0x18000ca73  mov     r8, rsi; Source
0x18000ca76  sub     rax, rcx
0x18000ca79  cmp     rcx, [rbx+10h]
0x18000ca7d  sbb     rdx, rdx
0x18000ca80  and     rdx, rax; DestinationSize
0x18000ca83  call    memcpy_s
0x18000ca88  add     [rbx+8], rdi
0x18000ca8c  mov     al, 1
0x18000ca8e  mov     rbx, [rsp+28h+arg_0]
0x18000ca93  mov     rsi, [rsp+28h+arg_8]
0x18000ca98  add     rsp, 20h
0x18000ca9c  pop     rdi
0x18000ca9d  retn
```
