# memcpy_s

- ea: `0x180006ed8`
- end: `0x180006f61`
- name: `memcpy_s`
- size: `137`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180004db0`
- `0x180008e7c`

## callees

- `0x180001f9a`
- `0x180001fe2`
- `0x180006ed8`
- `0x180009540`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006efe`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006f3f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006efe`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006f3f`

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
0x180006ed8  mov     [rsp+arg_0], rbx
0x180006edd  mov     [rsp+arg_8], rsi
0x180006ee2  push    rdi
0x180006ee3  sub     rsp, 20h
0x180006ee7  mov     rbx, r9
0x180006eea  mov     rsi, r8
0x180006eed  mov     rdi, rdx
0x180006ef0  test    r9, r9
0x180006ef3  jnz     short loc_180006EF9
0x180006ef5  xor     eax, eax
0x180006ef7  jmp     short loc_180006F51
0x180006ef9  test    rcx, rcx
0x180006efc  jnz     short loc_180006F14
0x180006efe  call    cs:__imp__o__errno
0x180006f04  mov     ebx, 16h
0x180006f09  mov     [rax], ebx
0x180006f0b  call    _invalid_parameter_noinfo
0x180006f10  mov     eax, ebx
0x180006f12  jmp     short loc_180006F51
0x180006f14  test    rsi, rsi
0x180006f17  jz      short loc_180006F2B
0x180006f19  cmp     rdi, rbx
0x180006f1c  jb      short loc_180006F2B
0x180006f1e  mov     r8, rbx; Size
0x180006f21  mov     rdx, rsi; Src
0x180006f24  call    memcpy_0
0x180006f29  jmp     short loc_180006EF5
0x180006f2b  mov     r8, rdi; Size
0x180006f2e  xor     edx, edx; Val
0x180006f30  call    memset_0
0x180006f35  test    rsi, rsi
0x180006f38  jz      short loc_180006EFE
0x180006f3a  cmp     rdi, rbx
0x180006f3d  jnb     short loc_180006F4C
0x180006f3f  call    cs:__imp__o__errno
0x180006f45  mov     ebx, 22h ; '"'
0x180006f4a  jmp     short loc_180006F09
0x180006f4c  mov     eax, 16h
0x180006f51  mov     rbx, [rsp+28h+arg_0]
0x180006f56  mov     rsi, [rsp+28h+arg_8]
0x180006f5b  add     rsp, 20h
0x180006f5f  pop     rdi
0x180006f60  retn
```
