# wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)

- ea: `0x180015b2c`
- end: `0x180015b86`
- name: `?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z`
- size: `90`
- prototype: `bool __fastcall(void **this, const void *, unsigned __int64)`
- caller_count: `14`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ef04`
- `0x180012fa8`
- `0x1800130e8`
- `0x180013228`
- `0x180013368`
- `0x1800134a8`
- `0x1800135e8`
- `0x180013728`
- `0x180013868`
- `0x1800139a8`
- `0x180013ae8`
- `0x180013c28`
- `0x1800152fc`
- `0x180015490`

## callees

- `0x18000f160`
- `0x180015afc`
- `0x180015b2c`

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
0x180015b2c  mov     [rsp+arg_0], rbx
0x180015b31  mov     [rsp+arg_8], rsi
0x180015b36  push    rdi
0x180015b37  sub     rsp, 20h
0x180015b3b  mov     rsi, rdx
0x180015b3e  mov     rdi, r8
0x180015b41  mov     rdx, r8; unsigned __int64
0x180015b44  mov     rbx, rcx
0x180015b47  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180015b4c  test    al, al
0x180015b4e  jz      short loc_180015B76
0x180015b50  mov     rcx, [rbx+8]; Destination
0x180015b54  mov     r9, rdi; SourceSize
0x180015b57  mov     rax, [rbx+10h]
0x180015b5b  mov     r8, rsi; Source
0x180015b5e  sub     rax, rcx
0x180015b61  cmp     rcx, [rbx+10h]
0x180015b65  sbb     rdx, rdx
0x180015b68  and     rdx, rax; DestinationSize
0x180015b6b  call    memcpy_s
0x180015b70  add     [rbx+8], rdi
0x180015b74  mov     al, 1
0x180015b76  mov     rbx, [rsp+28h+arg_0]
0x180015b7b  mov     rsi, [rsp+28h+arg_8]
0x180015b80  add     rsp, 20h
0x180015b84  pop     rdi
0x180015b85  retn
```
