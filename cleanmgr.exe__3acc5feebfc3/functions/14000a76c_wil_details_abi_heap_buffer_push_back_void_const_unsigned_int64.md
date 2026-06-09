# wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)

- ea: `0x14000a76c`
- end: `0x14000a7c6`
- name: `?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z`
- size: `90`
- prototype: `bool __fastcall(void **this, const void *, unsigned __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140008584`
- `0x140008670`
- `0x1400096d0`
- `0x14000988c`

## callees

- `0x1400069a8`
- `0x14000a73c`
- `0x14000a76c`

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
0x14000a76c  mov     [rsp+arg_0], rbx
0x14000a771  mov     [rsp+arg_8], rsi
0x14000a776  push    rdi
0x14000a777  sub     rsp, 20h
0x14000a77b  mov     rsi, rdx
0x14000a77e  mov     rdi, r8
0x14000a781  mov     rdx, r8; unsigned __int64
0x14000a784  mov     rbx, rcx
0x14000a787  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x14000a78c  test    al, al
0x14000a78e  jz      short loc_14000A7B6
0x14000a790  mov     rcx, [rbx+8]; Destination
0x14000a794  mov     r9, rdi; SourceSize
0x14000a797  mov     rax, [rbx+10h]
0x14000a79b  mov     r8, rsi; Source
0x14000a79e  sub     rax, rcx
0x14000a7a1  cmp     rcx, [rbx+10h]
0x14000a7a5  sbb     rdx, rdx
0x14000a7a8  and     rdx, rax; DestinationSize
0x14000a7ab  call    memcpy_s
0x14000a7b0  add     [rbx+8], rdi
0x14000a7b4  mov     al, 1
0x14000a7b6  mov     rbx, [rsp+28h+arg_0]
0x14000a7bb  mov     rsi, [rsp+28h+arg_8]
0x14000a7c0  add     rsp, 20h
0x14000a7c4  pop     rdi
0x14000a7c5  retn
```
