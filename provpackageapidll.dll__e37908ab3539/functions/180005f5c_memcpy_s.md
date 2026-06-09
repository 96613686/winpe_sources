# memcpy_s

- ea: `0x180005f5c`
- end: `0x180005fe5`
- name: `memcpy_s`
- size: `137`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180003e4c`
- `0x180004b10`
- `0x180004d30`

## callees

- `0x180001e1e`
- `0x180001e66`
- `0x180005f5c`
- `0x18001844c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005f82`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005fc3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005f82`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005fc3`

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
0x180005f5c  mov     [rsp+arg_0], rbx
0x180005f61  mov     [rsp+arg_8], rsi
0x180005f66  push    rdi
0x180005f67  sub     rsp, 20h
0x180005f6b  mov     rbx, r9
0x180005f6e  mov     rsi, r8
0x180005f71  mov     rdi, rdx
0x180005f74  test    r9, r9
0x180005f77  jnz     short loc_180005F7D
0x180005f79  xor     eax, eax
0x180005f7b  jmp     short loc_180005FD5
0x180005f7d  test    rcx, rcx
0x180005f80  jnz     short loc_180005F98
0x180005f82  call    cs:__imp__o__errno
0x180005f88  mov     ebx, 16h
0x180005f8d  mov     [rax], ebx
0x180005f8f  call    _invalid_parameter_noinfo
0x180005f94  mov     eax, ebx
0x180005f96  jmp     short loc_180005FD5
0x180005f98  test    rsi, rsi
0x180005f9b  jz      short loc_180005FAF
0x180005f9d  cmp     rdi, rbx
0x180005fa0  jb      short loc_180005FAF
0x180005fa2  mov     r8, rbx; Size
0x180005fa5  mov     rdx, rsi; Src
0x180005fa8  call    memcpy_0
0x180005fad  jmp     short loc_180005F79
0x180005faf  mov     r8, rdi; Size
0x180005fb2  xor     edx, edx; Val
0x180005fb4  call    memset_0
0x180005fb9  test    rsi, rsi
0x180005fbc  jz      short loc_180005F82
0x180005fbe  cmp     rdi, rbx
0x180005fc1  jnb     short loc_180005FD0
0x180005fc3  call    cs:__imp__o__errno
0x180005fc9  mov     ebx, 22h ; '"'
0x180005fce  jmp     short loc_180005F8D
0x180005fd0  mov     eax, 16h
0x180005fd5  mov     rbx, [rsp+28h+arg_0]
0x180005fda  mov     rsi, [rsp+28h+arg_8]
0x180005fdf  add     rsp, 20h
0x180005fe3  pop     rdi
0x180005fe4  retn
```
