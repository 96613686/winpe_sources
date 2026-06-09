# wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)

- ea: `0x180009e8c`
- end: `0x180009ee6`
- name: `?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z`
- size: `90`
- prototype: `bool(wil::details_abi::heap_buffer *__hidden this, const void *, unsigned __int64)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x180007608`
- `0x180007694`
- `0x180008db8`
- `0x180008f2c`
- `0x18000b454`
- `0x18000b5b0`
- `0x18000b70c`

## callees

- `0x180009e5c`
- `0x180009e8c`
- `0x18000a310`

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
0x180009e8c  mov     [rsp+arg_0], rbx
0x180009e91  mov     [rsp+arg_8], rsi
0x180009e96  push    rdi
0x180009e97  sub     rsp, 20h
0x180009e9b  mov     rsi, rdx
0x180009e9e  mov     rdi, r8
0x180009ea1  mov     rdx, r8; unsigned __int64
0x180009ea4  mov     rbx, rcx
0x180009ea7  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180009eac  test    al, al
0x180009eae  jz      short loc_180009ED6
0x180009eb0  mov     rcx, [rbx+8]; Destination
0x180009eb4  mov     r9, rdi; SourceSize
0x180009eb7  mov     rax, [rbx+10h]
0x180009ebb  mov     r8, rsi; Source
0x180009ebe  sub     rax, rcx
0x180009ec1  cmp     rcx, [rbx+10h]
0x180009ec5  sbb     rdx, rdx
0x180009ec8  and     rdx, rax; DestinationSize
0x180009ecb  call    memcpy_s
0x180009ed0  add     [rbx+8], rdi
0x180009ed4  mov     al, 1
0x180009ed6  mov     rbx, [rsp+28h+arg_0]
0x180009edb  mov     rsi, [rsp+28h+arg_8]
0x180009ee0  add     rsp, 20h
0x180009ee4  pop     rdi
0x180009ee5  retn
```
