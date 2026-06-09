# memcpy_s

- ea: `0x14000eff0`
- end: `0x14000f079`
- name: `memcpy_s`
- size: `137`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `8`
- callee_count: `4`
- tags: ``

## callers

- `0x140004c68`
- `0x140004ce0`
- `0x1400077d8`
- `0x14000952c`
- `0x14000d334`
- `0x14000d864`
- `0x14000e4d8`
- `0x14000e538`

## callees

- `0x1400039fe`
- `0x140003aa0`
- `0x140003ab8`
- `0x14000eff0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000f016`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000f057`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000f016`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000f057`

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
    v8 = (errno_t *)_o__errno(Destination);
    v9 = 22;
LABEL_5:
    *v8 = v9;
    invalid_parameter_noinfo();
    return v9;
  }
  if ( DestinationSize < SourceSize )
  {
    v8 = (errno_t *)_o__errno(Destination);
    v9 = 34;
    goto LABEL_5;
  }
  return 22;
}

```

## disassembly

```asm
0x14000eff0  mov     [rsp+arg_0], rbx
0x14000eff5  mov     [rsp+arg_8], rsi
0x14000effa  push    rdi
0x14000effb  sub     rsp, 20h
0x14000efff  mov     rbx, r9
0x14000f002  mov     rsi, r8
0x14000f005  mov     rdi, rdx
0x14000f008  test    r9, r9
0x14000f00b  jnz     short loc_14000F011
0x14000f00d  xor     eax, eax
0x14000f00f  jmp     short loc_14000F069
0x14000f011  test    rcx, rcx
0x14000f014  jnz     short loc_14000F02C
0x14000f016  call    cs:__imp__o__errno
0x14000f01c  mov     ebx, 16h
0x14000f021  mov     [rax], ebx
0x14000f023  call    _invalid_parameter_noinfo
0x14000f028  mov     eax, ebx
0x14000f02a  jmp     short loc_14000F069
0x14000f02c  test    rsi, rsi
0x14000f02f  jz      short loc_14000F043
0x14000f031  cmp     rdi, rbx
0x14000f034  jb      short loc_14000F043
0x14000f036  mov     r8, rbx; Size
0x14000f039  mov     rdx, rsi; Src
0x14000f03c  call    memcpy_0
0x14000f041  jmp     short loc_14000F00D
0x14000f043  mov     r8, rdi; Size
0x14000f046  xor     edx, edx; Val
0x14000f048  call    memset_0
0x14000f04d  test    rsi, rsi
0x14000f050  jz      short loc_14000F016
0x14000f052  cmp     rdi, rbx
0x14000f055  jnb     short loc_14000F064
0x14000f057  call    cs:__imp__o__errno
0x14000f05d  mov     ebx, 22h ; '"'
0x14000f062  jmp     short loc_14000F021
0x14000f064  mov     eax, 16h
0x14000f069  mov     rbx, [rsp+28h+arg_0]
0x14000f06e  mov     rsi, [rsp+28h+arg_8]
0x14000f073  add     rsp, 20h
0x14000f077  pop     rdi
0x14000f078  retn
```
