# memcpy_s

- ea: `0x180009fe8`
- end: `0x18000a071`
- name: `memcpy_s`
- size: `137`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x180005c5c`
- `0x180008364`
- `0x180008688`
- `0x18000995c`
- `0x180009ba0`

## callees

- `0x18000288a`
- `0x1800028dc`
- `0x180009fe8`
- `0x180014e8c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a00e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a04f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a00e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a04f`

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
    v8 = (errno_t *)_o__errno(Destination, DestinationSize, Source);
    v9 = 22;
LABEL_5:
    *v8 = v9;
    invalid_parameter_noinfo();
    return v9;
  }
  if ( DestinationSize < SourceSize )
  {
    v8 = (errno_t *)_o__errno(Destination, DestinationSize, Source);
    v9 = 34;
    goto LABEL_5;
  }
  return 22;
}

```

## disassembly

```asm
0x180009fe8  mov     [rsp+arg_0], rbx
0x180009fed  mov     [rsp+arg_8], rsi
0x180009ff2  push    rdi
0x180009ff3  sub     rsp, 20h
0x180009ff7  mov     rbx, r9
0x180009ffa  mov     rsi, r8
0x180009ffd  mov     rdi, rdx
0x18000a000  test    r9, r9
0x18000a003  jnz     short loc_18000A009
0x18000a005  xor     eax, eax
0x18000a007  jmp     short loc_18000A061
0x18000a009  test    rcx, rcx
0x18000a00c  jnz     short loc_18000A024
0x18000a00e  call    cs:__imp__o__errno
0x18000a014  mov     ebx, 16h
0x18000a019  mov     [rax], ebx
0x18000a01b  call    _invalid_parameter_noinfo
0x18000a020  mov     eax, ebx
0x18000a022  jmp     short loc_18000A061
0x18000a024  test    rsi, rsi
0x18000a027  jz      short loc_18000A03B
0x18000a029  cmp     rdi, rbx
0x18000a02c  jb      short loc_18000A03B
0x18000a02e  mov     r8, rbx; Size
0x18000a031  mov     rdx, rsi; Src
0x18000a034  call    memcpy_0
0x18000a039  jmp     short loc_18000A005
0x18000a03b  mov     r8, rdi; Size
0x18000a03e  xor     edx, edx; Val
0x18000a040  call    memset_0
0x18000a045  test    rsi, rsi
0x18000a048  jz      short loc_18000A00E
0x18000a04a  cmp     rdi, rbx
0x18000a04d  jnb     short loc_18000A05C
0x18000a04f  call    cs:__imp__o__errno
0x18000a055  mov     ebx, 22h ; '"'
0x18000a05a  jmp     short loc_18000A019
0x18000a05c  mov     eax, 16h
0x18000a061  mov     rbx, [rsp+28h+arg_0]
0x18000a066  mov     rsi, [rsp+28h+arg_8]
0x18000a06b  add     rsp, 20h
0x18000a06f  pop     rdi
0x18000a070  retn
```
