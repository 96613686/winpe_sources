# memmove_s

- ea: `0x18000a3a0`
- end: `0x18000a3f3`
- name: `memmove_s`
- size: `83`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180007ddc`

## callees

- `0x180002efe`
- `0x18000a3a0`
- `0x180012a8c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a3b3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a3d3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a3b3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a3d3`

## pseudocode

```c
errno_t __cdecl memmove_s(
        void *const Destination,
        const rsize_t DestinationSize,
        const void *const Source,
        const rsize_t SourceSize)
{
  errno_t *v4; // rax
  errno_t v5; // ebx

  if ( SourceSize )
  {
    if ( !Destination || !Source )
    {
      v4 = (errno_t *)_o__errno(Destination, DestinationSize);
      v5 = 22;
LABEL_4:
      *v4 = v5;
      invalid_parameter_noinfo();
      return v5;
    }
    if ( DestinationSize < SourceSize )
    {
      v4 = (errno_t *)((__int64 (*)(void))_o__errno)();
      v5 = 34;
      goto LABEL_4;
    }
    memmove_0(Destination, Source, SourceSize);
  }
  return 0;
}

```

## disassembly

```asm
0x18000a3a0  push    rbx
0x18000a3a2  sub     rsp, 20h
0x18000a3a6  mov     rax, r8
0x18000a3a9  test    r9, r9
0x18000a3ac  jz      short loc_18000A3EB
0x18000a3ae  test    rcx, rcx
0x18000a3b1  jnz     short loc_18000A3C9
0x18000a3b3  call    cs:__imp__o__errno
0x18000a3b9  mov     ebx, 16h
0x18000a3be  mov     [rax], ebx
0x18000a3c0  call    _invalid_parameter_noinfo
0x18000a3c5  mov     eax, ebx
0x18000a3c7  jmp     short loc_18000A3ED
0x18000a3c9  test    rax, rax
0x18000a3cc  jz      short loc_18000A3B3
0x18000a3ce  cmp     rdx, r9
0x18000a3d1  jnb     short loc_18000A3E0
0x18000a3d3  call    cs:__imp__o__errno
0x18000a3d9  mov     ebx, 22h ; '"'
0x18000a3de  jmp     short loc_18000A3BE
0x18000a3e0  mov     r8, r9; Size
0x18000a3e3  mov     rdx, rax; Src
0x18000a3e6  call    memmove_0
0x18000a3eb  xor     eax, eax
0x18000a3ed  add     rsp, 20h
0x18000a3f1  pop     rbx
0x18000a3f2  retn
```
