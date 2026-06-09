# wil::details_abi::heap_buffer::reserve(unsigned __int64)

- ea: `0x14000ec00`
- end: `0x14000ec9c`
- name: `?reserve@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `156`
- prototype: `char __fastcall(wil::details_abi::heap_buffer *this, unsigned __int64)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x140008980`
- `0x14000a020`
- `0x14000eb2c`
- `0x14000fe5c`

## callees

- `0x140009b80`
- `0x14000a6cc`
- `0x14000e938`
- `0x14000ec00`
- `0x14000f32c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14000ec61`
- `msvcrt!memcpy_s` at `0x14000ec61`

## pseudocode

```c
char __fastcall wil::details_abi::heap_buffer::reserve(wil::details_abi::heap_buffer *this, unsigned __int64 a2)
{
  unsigned __int64 v4; // r14
  char *v5; // rax
  char *v6; // rsi
  rsize_t v8; // rbx
  char v9; // [rsp+50h] [rbp+8h] BYREF

  if ( *((_QWORD *)this + 2) - *(_QWORD *)this < a2 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v9);
    v4 = (a2 & 0xFFFFFFFFFFFFFFC0uLL) + 64;
    v5 = (char *)wil::details::ProcessHeapAlloc(0, v4);
    v6 = v5;
    if ( !v5 )
    {
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v9);
      return 0;
    }
    v8 = *((_QWORD *)this + 1) - *(_QWORD *)this;
    memcpy_s(v5, v4, *(const void *const *)this, v8);
    wistd::unique_ptr<void,wil::process_heap_deleter>::reset((char *)this + 24, v6);
    *(_QWORD *)this = v6;
    *((_QWORD *)this + 1) = &v6[v8];
    *((_QWORD *)this + 2) = &v6[v4];
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v9);
  }
  return 1;
}

```

## disassembly

```asm
0x14000ec00  push    rbx
0x14000ec02  push    rsi
0x14000ec03  push    rdi
0x14000ec04  push    r14
0x14000ec06  sub     rsp, 28h
0x14000ec0a  mov     rax, [rcx+10h]
0x14000ec0e  mov     rbx, rdx
0x14000ec11  sub     rax, [rcx]
0x14000ec14  mov     rdi, rcx
0x14000ec17  cmp     rax, rdx
0x14000ec1a  jnb     short loc_14000EC90
0x14000ec1c  lea     rcx, [rsp+48h+arg_0]; this
0x14000ec21  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14000ec26  and     rbx, 0FFFFFFFFFFFFFFC0h
0x14000ec2a  xor     ecx, ecx; dwFlags
0x14000ec2c  lea     r14, [rbx+40h]
0x14000ec30  mov     rdx, r14; dwBytes
0x14000ec33  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000ec38  mov     rsi, rax
0x14000ec3b  test    rax, rax
0x14000ec3e  jnz     short loc_14000EC4E
0x14000ec40  lea     rcx, [rsp+48h+arg_0]; this
0x14000ec45  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14000ec4a  xor     al, al
0x14000ec4c  jmp     short loc_14000EC92
0x14000ec4e  mov     rbx, [rdi+8]
0x14000ec52  mov     rdx, r14; DestinationSize
0x14000ec55  sub     rbx, [rdi]
0x14000ec58  mov     rcx, rsi; Destination
0x14000ec5b  mov     r8, [rdi]; Source
0x14000ec5e  mov     r9, rbx; SourceSize
0x14000ec61  call    cs:__imp_memcpy_s
0x14000ec67  lea     rcx, [rdi+18h]
0x14000ec6b  mov     rdx, rsi
0x14000ec6e  call    ?reset@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAXPEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::reset(void *)
0x14000ec73  lea     rax, [rbx+rsi]
0x14000ec77  mov     [rdi], rsi
0x14000ec7a  mov     [rdi+8], rax
0x14000ec7e  lea     rcx, [rsp+48h+arg_0]; this
0x14000ec83  lea     rax, [r14+rsi]
0x14000ec87  mov     [rdi+10h], rax
0x14000ec8b  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14000ec90  mov     al, 1
0x14000ec92  add     rsp, 28h
0x14000ec96  pop     r14
0x14000ec98  pop     rdi
0x14000ec99  pop     rsi
0x14000ec9a  pop     rbx
0x14000ec9b  retn
```
