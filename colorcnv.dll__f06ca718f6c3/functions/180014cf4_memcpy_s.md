# memcpy_s

- ea: `0x180014cf4`
- end: `0x180014d7d`
- name: `memcpy_s`
- size: `137`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18000f8f4`
- `0x180010734`
- `0x18001316c`

## callees

- `0x18000b40a`
- `0x18000b468`
- `0x180014cf4`
- `0x180029fc0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180014d1a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180014d5b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180014d1a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180014d5b`

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
0x180014cf4  mov     [rsp+arg_0], rbx
0x180014cf9  mov     [rsp+arg_8], rsi
0x180014cfe  push    rdi
0x180014cff  sub     rsp, 20h
0x180014d03  mov     rbx, r9
0x180014d06  mov     rsi, r8
0x180014d09  mov     rdi, rdx
0x180014d0c  test    r9, r9
0x180014d0f  jnz     short loc_180014D15
0x180014d11  xor     eax, eax
0x180014d13  jmp     short loc_180014D6D
0x180014d15  test    rcx, rcx
0x180014d18  jnz     short loc_180014D30
0x180014d1a  call    cs:__imp__o__errno
0x180014d20  mov     ebx, 16h
0x180014d25  mov     [rax], ebx
0x180014d27  call    _invalid_parameter_noinfo
0x180014d2c  mov     eax, ebx
0x180014d2e  jmp     short loc_180014D6D
0x180014d30  test    rsi, rsi
0x180014d33  jz      short loc_180014D47
0x180014d35  cmp     rdi, rbx
0x180014d38  jb      short loc_180014D47
0x180014d3a  mov     r8, rbx; Size
0x180014d3d  mov     rdx, rsi; Src
0x180014d40  call    memcpy_0
0x180014d45  jmp     short loc_180014D11
0x180014d47  mov     r8, rdi; Size
0x180014d4a  xor     edx, edx; Val
0x180014d4c  call    memset_0
0x180014d51  test    rsi, rsi
0x180014d54  jz      short loc_180014D1A
0x180014d56  cmp     rdi, rbx
0x180014d59  jnb     short loc_180014D68
0x180014d5b  call    cs:__imp__o__errno
0x180014d61  mov     ebx, 22h ; '"'
0x180014d66  jmp     short loc_180014D25
0x180014d68  mov     eax, 16h
0x180014d6d  mov     rbx, [rsp+28h+arg_0]
0x180014d72  mov     rsi, [rsp+28h+arg_8]
0x180014d77  add     rsp, 20h
0x180014d7b  pop     rdi
0x180014d7c  retn
```
