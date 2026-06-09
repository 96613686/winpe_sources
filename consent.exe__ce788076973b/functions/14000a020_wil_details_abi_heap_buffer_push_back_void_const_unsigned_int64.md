# wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)

- ea: `0x14000a020`
- end: `0x14000a0ac`
- name: `?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z`
- size: `140`
- prototype: `bool __fastcall(wil::details_abi::heap_buffer *this, const void *, rsize_t)`
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x14000d6e4`
- `0x140014f60`
- `0x140015178`
- `0x1400152a8`
- `0x1400153d8`
- `0x140015508`
- `0x140015638`
- `0x140015768`
- `0x140015898`
- `0x1400159c8`
- `0x140015af8`
- `0x140017a74`

## callees

- `0x14000a020`
- `0x14000ec00`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14000a090`
- `msvcrt!memcpy_s` at `0x14000a090`

## pseudocode

```c
bool __fastcall wil::details_abi::heap_buffer::push_back(
        wil::details_abi::heap_buffer *this,
        const void *a2,
        rsize_t a3)
{
  rsize_t v5; // r9
  unsigned __int64 v7; // rdx
  bool result; // al
  void *v9; // rcx
  rsize_t v10; // rdx

  v5 = *((_QWORD *)this + 2) - *(_QWORD *)this;
  if ( a3 + *((_QWORD *)this + 1) - *(_QWORD *)this < v5 )
    goto LABEL_5;
  v7 = a3;
  if ( a3 < 2 * v5 )
    v7 = 2 * v5;
  result = wil::details_abi::heap_buffer::reserve(this, v7);
  if ( result )
  {
LABEL_5:
    v9 = (void *)*((_QWORD *)this + 1);
    v10 = 0;
    if ( (unsigned __int64)v9 < *((_QWORD *)this + 2) )
      v10 = *((_QWORD *)this + 2) - (_QWORD)v9;
    memcpy_s(v9, v10, a2, a3);
    *((_QWORD *)this + 1) += a3;
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x14000a020  mov     [rsp+arg_0], rbx
0x14000a025  mov     [rsp+arg_8], rsi
0x14000a02a  push    rdi
0x14000a02b  sub     rsp, 20h
0x14000a02f  mov     rax, [rcx+8]
0x14000a033  mov     rdi, r8
0x14000a036  sub     rax, [rcx]
0x14000a039  mov     rsi, rdx
0x14000a03c  mov     r9, [rcx+10h]
0x14000a040  add     rax, r8
0x14000a043  sub     r9, [rcx]
0x14000a046  mov     rbx, rcx
0x14000a049  cmp     rax, r9
0x14000a04c  jb      short loc_14000A075
0x14000a04e  lea     rax, [r9+r9]
0x14000a052  mov     rdx, r8
0x14000a055  cmp     r8, rax
0x14000a058  cmovb   rdx, rax; unsigned __int64
0x14000a05c  call    ?reserve@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::reserve(unsigned __int64)
0x14000a061  test    al, al
0x14000a063  jnz     short loc_14000A075
0x14000a065  mov     rbx, [rsp+28h+arg_0]
0x14000a06a  mov     rsi, [rsp+28h+arg_8]
0x14000a06f  add     rsp, 20h
0x14000a073  pop     rdi
0x14000a074  retn
0x14000a075  mov     rcx, [rbx+8]; Destination
0x14000a079  xor     edx, edx
0x14000a07b  mov     rax, [rbx+10h]
0x14000a07f  mov     r9, rdi; SourceSize
0x14000a082  sub     rax, rcx
0x14000a085  mov     r8, rsi; Source
0x14000a088  cmp     rcx, [rbx+10h]
0x14000a08c  cmovb   rdx, rax; DestinationSize
0x14000a090  call    cs:__imp_memcpy_s
0x14000a096  add     [rbx+8], rdi
0x14000a09a  mov     al, 1
0x14000a09c  mov     rbx, [rsp+28h+arg_0]
0x14000a0a1  mov     rsi, [rsp+28h+arg_8]
0x14000a0a6  add     rsp, 20h
0x14000a0aa  pop     rdi
0x14000a0ab  retn
```
