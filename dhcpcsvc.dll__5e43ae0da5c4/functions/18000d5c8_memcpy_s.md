# memcpy_s

- ea: `0x18000d5c8`
- end: `0x18000d651`
- name: `memcpy_s`
- size: `137`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180007dd0`
- `0x180009d40`
- `0x18000a4d0`
- `0x18000c540`

## callees

- `0x18000514a`
- `0x180005162`
- `0x18000d5c8`
- `0x180010aac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000d5ee`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000d62f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000d5ee`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000d62f`

## pseudocode

```c
errno_t __cdecl memcpy_s(
        void *const Destination,
        const rsize_t DestinationSize,
        const void *const Source,
        const rsize_t SourceSize)
{
  errno_t *v8; // rax
  errno_t v9; // ebx

  if ( !SourceSize )
    return 0;
  if ( !Destination )
    goto LABEL_4;
  if ( Source && DestinationSize >= SourceSize )
  {
    memcpy_0(Destination, Source, SourceSize);
    return 0;
  }
  memset_0(Destination, 0, DestinationSize);
  if ( !Source )
  {
LABEL_4:
    v8 = (errno_t *)_o__errno();
    v9 = 22;
LABEL_5:
    *v8 = v9;
    invalid_parameter_noinfo();
    return v9;
  }
  if ( DestinationSize < SourceSize )
  {
    v8 = (errno_t *)_o__errno();
    v9 = 34;
    goto LABEL_5;
  }
  return 22;
}

```

## disassembly

```asm
0x18000d5c8  mov     [rsp+arg_0], rbx
0x18000d5cd  mov     [rsp+arg_8], rsi
0x18000d5d2  push    rdi
0x18000d5d3  sub     rsp, 20h
0x18000d5d7  mov     rbx, r9
0x18000d5da  mov     rsi, r8
0x18000d5dd  mov     rdi, rdx
0x18000d5e0  test    r9, r9
0x18000d5e3  jnz     short loc_18000D5E9
0x18000d5e5  xor     eax, eax
0x18000d5e7  jmp     short loc_18000D641
0x18000d5e9  test    rcx, rcx
0x18000d5ec  jnz     short loc_18000D604
0x18000d5ee  call    cs:__imp__o__errno
0x18000d5f4  mov     ebx, 16h
0x18000d5f9  mov     [rax], ebx
0x18000d5fb  call    _invalid_parameter_noinfo
0x18000d600  mov     eax, ebx
0x18000d602  jmp     short loc_18000D641
0x18000d604  test    rsi, rsi
0x18000d607  jz      short loc_18000D61B
0x18000d609  cmp     rdi, rbx
0x18000d60c  jb      short loc_18000D61B
0x18000d60e  mov     r8, rbx; Size
0x18000d611  mov     rdx, rsi; Src
0x18000d614  call    memcpy_0
0x18000d619  jmp     short loc_18000D5E5
0x18000d61b  mov     r8, rdi; Size
0x18000d61e  xor     edx, edx; Val
0x18000d620  call    memset_0
0x18000d625  test    rsi, rsi
0x18000d628  jz      short loc_18000D5EE
0x18000d62a  cmp     rdi, rbx
0x18000d62d  jnb     short loc_18000D63C
0x18000d62f  call    cs:__imp__o__errno
0x18000d635  mov     ebx, 22h ; '"'
0x18000d63a  jmp     short loc_18000D5F9
0x18000d63c  mov     eax, 16h
0x18000d641  mov     rbx, [rsp+28h+arg_0]
0x18000d646  mov     rsi, [rsp+28h+arg_8]
0x18000d64b  add     rsp, 20h
0x18000d64f  pop     rdi
0x18000d650  retn
```
