# memcpy_s

- ea: `0x180007de8`
- end: `0x180007e71`
- name: `memcpy_s`
- size: `137`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180004968`
- `0x1800068d8`
- `0x18000773c`
- `0x1800078bc`

## callees

- `0x180001eae`
- `0x180001ef0`
- `0x180007de8`
- `0x18000f99c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007e0e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007e4f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007e0e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007e4f`

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
0x180007de8  mov     [rsp+arg_0], rbx
0x180007ded  mov     [rsp+arg_8], rsi
0x180007df2  push    rdi
0x180007df3  sub     rsp, 20h
0x180007df7  mov     rbx, r9
0x180007dfa  mov     rsi, r8
0x180007dfd  mov     rdi, rdx
0x180007e00  test    r9, r9
0x180007e03  jnz     short loc_180007E09
0x180007e05  xor     eax, eax
0x180007e07  jmp     short loc_180007E61
0x180007e09  test    rcx, rcx
0x180007e0c  jnz     short loc_180007E24
0x180007e0e  call    cs:__imp__o__errno
0x180007e14  mov     ebx, 16h
0x180007e19  mov     [rax], ebx
0x180007e1b  call    _invalid_parameter_noinfo
0x180007e20  mov     eax, ebx
0x180007e22  jmp     short loc_180007E61
0x180007e24  test    rsi, rsi
0x180007e27  jz      short loc_180007E3B
0x180007e29  cmp     rdi, rbx
0x180007e2c  jb      short loc_180007E3B
0x180007e2e  mov     r8, rbx; Size
0x180007e31  mov     rdx, rsi; Src
0x180007e34  call    memcpy_0
0x180007e39  jmp     short loc_180007E05
0x180007e3b  mov     r8, rdi; Size
0x180007e3e  xor     edx, edx; Val
0x180007e40  call    memset_0
0x180007e45  test    rsi, rsi
0x180007e48  jz      short loc_180007E0E
0x180007e4a  cmp     rdi, rbx
0x180007e4d  jnb     short loc_180007E5C
0x180007e4f  call    cs:__imp__o__errno
0x180007e55  mov     ebx, 22h ; '"'
0x180007e5a  jmp     short loc_180007E19
0x180007e5c  mov     eax, 16h
0x180007e61  mov     rbx, [rsp+28h+arg_0]
0x180007e66  mov     rsi, [rsp+28h+arg_8]
0x180007e6b  add     rsp, 20h
0x180007e6f  pop     rdi
0x180007e70  retn
```
