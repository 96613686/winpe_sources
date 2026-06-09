# memcpy_s

- ea: `0x180029fd0`
- end: `0x18002a079`
- name: `memcpy_s`
- size: `169`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x1800221b0`
- `0x180022250`
- `0x180024a20`
- `0x180027b60`
- `0x180029210`
- `0x180029710`

## callees

- `0x18001eae6`
- `0x18001eb54`
- `0x180029fd0`
- `0x18002f674`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180029ff2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002a053`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180029ff2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002a053`

## pseudocode

```c
errno_t __cdecl memcpy_s(
        void *const Destination,
        const rsize_t DestinationSize,
        const void *const Source,
        const rsize_t SourceSize)
{
  if ( !SourceSize )
    return 0;
  if ( !Destination )
  {
LABEL_3:
    *(_DWORD *)_o__errno(Destination, DestinationSize, Source) = 22;
    invalid_parameter_noinfo();
    return 22;
  }
  if ( Source && DestinationSize >= SourceSize )
  {
    memcpy_0(Destination, Source, SourceSize);
    return 0;
  }
  memset_0(Destination, 0, DestinationSize);
  if ( !Source )
    goto LABEL_3;
  if ( DestinationSize >= SourceSize )
    return 22;
  *(_DWORD *)_o__errno(Destination, DestinationSize, Source) = 34;
  invalid_parameter_noinfo();
  return 34;
}

```

## disassembly

```asm
0x180029fd0  mov     [rsp+arg_0], rbx
0x180029fd5  mov     [rsp+arg_8], rsi
0x180029fda  push    rdi
0x180029fdb  sub     rsp, 20h
0x180029fdf  mov     rbx, r9
0x180029fe2  mov     rsi, r8
0x180029fe5  mov     rdi, rdx
0x180029fe8  test    r9, r9
0x180029feb  jz      short loc_18002A02D
0x180029fed  test    rcx, rcx
0x180029ff0  jnz     short loc_18002A018
0x180029ff2  call    cs:__imp__o__errno
0x180029ff8  mov     dword ptr [rax], 16h
0x180029ffe  call    _invalid_parameter_noinfo
0x18002a003  mov     eax, 16h
0x18002a008  mov     rbx, [rsp+28h+arg_0]
0x18002a00d  mov     rsi, [rsp+28h+arg_8]
0x18002a012  add     rsp, 20h
0x18002a016  pop     rdi
0x18002a017  retn
0x18002a018  test    rsi, rsi
0x18002a01b  jz      short loc_18002A03F
0x18002a01d  cmp     rdi, rbx
0x18002a020  jb      short loc_18002A03F
0x18002a022  mov     r8, rbx; Size
0x18002a025  mov     rdx, rsi; Src
0x18002a028  call    memcpy_0
0x18002a02d  xor     eax, eax
0x18002a02f  mov     rbx, [rsp+28h+arg_0]
0x18002a034  mov     rsi, [rsp+28h+arg_8]
0x18002a039  add     rsp, 20h
0x18002a03d  pop     rdi
0x18002a03e  retn
0x18002a03f  mov     r8, rdi; Size
0x18002a042  xor     edx, edx; Val
0x18002a044  call    memset_0
0x18002a049  test    rsi, rsi
0x18002a04c  jz      short loc_180029FF2
0x18002a04e  cmp     rdi, rbx
0x18002a051  jnb     short loc_18002A003
0x18002a053  call    cs:__imp__o__errno
0x18002a059  mov     dword ptr [rax], 22h ; '"'
0x18002a05f  call    _invalid_parameter_noinfo
0x18002a064  mov     rbx, [rsp+28h+arg_0]
0x18002a069  mov     eax, 22h ; '"'
0x18002a06e  mov     rsi, [rsp+28h+arg_8]
0x18002a073  add     rsp, 20h
0x18002a077  pop     rdi
0x18002a078  retn
```
