# memcpy_s

- ea: `0x1400059cc`
- end: `0x140005a55`
- name: `memcpy_s`
- size: `137`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140003b48`
- `0x140004de0`

## callees

- `0x140001daa`
- `0x140001e52`
- `0x1400059cc`
- `0x140005b54`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400059f2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140005a33`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400059f2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140005a33`

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
0x1400059cc  mov     [rsp+arg_0], rbx
0x1400059d1  mov     [rsp+arg_8], rsi
0x1400059d6  push    rdi
0x1400059d7  sub     rsp, 20h
0x1400059db  mov     rbx, r9
0x1400059de  mov     rsi, r8
0x1400059e1  mov     rdi, rdx
0x1400059e4  test    r9, r9
0x1400059e7  jnz     short loc_1400059ED
0x1400059e9  xor     eax, eax
0x1400059eb  jmp     short loc_140005A45
0x1400059ed  test    rcx, rcx
0x1400059f0  jnz     short loc_140005A08
0x1400059f2  call    cs:__imp__o__errno
0x1400059f8  mov     ebx, 16h
0x1400059fd  mov     [rax], ebx
0x1400059ff  call    _invalid_parameter_noinfo
0x140005a04  mov     eax, ebx
0x140005a06  jmp     short loc_140005A45
0x140005a08  test    rsi, rsi
0x140005a0b  jz      short loc_140005A1F
0x140005a0d  cmp     rdi, rbx
0x140005a10  jb      short loc_140005A1F
0x140005a12  mov     r8, rbx; Size
0x140005a15  mov     rdx, rsi; Src
0x140005a18  call    memcpy_0
0x140005a1d  jmp     short loc_1400059E9
0x140005a1f  mov     r8, rdi; Size
0x140005a22  xor     edx, edx; Val
0x140005a24  call    memset_0
0x140005a29  test    rsi, rsi
0x140005a2c  jz      short loc_1400059F2
0x140005a2e  cmp     rdi, rbx
0x140005a31  jnb     short loc_140005A40
0x140005a33  call    cs:__imp__o__errno
0x140005a39  mov     ebx, 22h ; '"'
0x140005a3e  jmp     short loc_1400059FD
0x140005a40  mov     eax, 16h
0x140005a45  mov     rbx, [rsp+28h+arg_0]
0x140005a4a  mov     rsi, [rsp+28h+arg_8]
0x140005a4f  add     rsp, 20h
0x140005a53  pop     rdi
0x140005a54  retn
```
