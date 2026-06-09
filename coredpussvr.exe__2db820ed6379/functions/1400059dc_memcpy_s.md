# memcpy_s

- ea: `0x1400059dc`
- end: `0x140005a72`
- name: `memcpy_s`
- size: `150`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x140002b60`
- `0x140003ab8`
- `0x140004acc`
- `0x140004ed8`
- `0x140005e4c`
- `0x140006800`

## callees

- `0x1400020a6`
- `0x14000215c`
- `0x1400059dc`
- `0x140009090`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140005a02`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140005a49`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140005a02`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140005a49`

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
    v8 = (errno_t *)_o__errno(Destination, DestinationSize, Source, SourceSize);
    v9 = 22;
LABEL_5:
    *v8 = v9;
    invalid_parameter_noinfo();
    return v9;
  }
  if ( DestinationSize < SourceSize )
  {
    v8 = (errno_t *)_o__errno(Destination, DestinationSize, Source, SourceSize);
    v9 = 34;
    goto LABEL_5;
  }
  return 22;
}

```

## disassembly

```asm
0x1400059dc  mov     [rsp+arg_0], rbx
0x1400059e1  mov     [rsp+arg_8], rsi
0x1400059e6  push    rdi
0x1400059e7  sub     rsp, 20h
0x1400059eb  mov     rbx, r9
0x1400059ee  mov     rsi, r8
0x1400059f1  mov     rdi, rdx
0x1400059f4  test    r9, r9
0x1400059f7  jnz     short loc_1400059FD
0x1400059f9  xor     eax, eax
0x1400059fb  jmp     short loc_140005A61
0x1400059fd  test    rcx, rcx
0x140005a00  jnz     short loc_140005A1E
0x140005a02  call    cs:__imp__o__errno
0x140005a09  nop     dword ptr [rax+rax+00h]
0x140005a0e  mov     ebx, 16h
0x140005a13  mov     [rax], ebx
0x140005a15  call    _invalid_parameter_noinfo
0x140005a1a  mov     eax, ebx
0x140005a1c  jmp     short loc_140005A61
0x140005a1e  test    rsi, rsi
0x140005a21  jz      short loc_140005A35
0x140005a23  cmp     rdi, rbx
0x140005a26  jb      short loc_140005A35
0x140005a28  mov     r8, rbx; Size
0x140005a2b  mov     rdx, rsi; Src
0x140005a2e  call    memcpy_0
0x140005a33  jmp     short loc_1400059F9
0x140005a35  mov     r8, rdi; Size
0x140005a38  xor     edx, edx; Val
0x140005a3a  call    memset_0
0x140005a3f  test    rsi, rsi
0x140005a42  jz      short loc_140005A02
0x140005a44  cmp     rdi, rbx
0x140005a47  jnb     short loc_140005A5C
0x140005a49  call    cs:__imp__o__errno
0x140005a50  nop     dword ptr [rax+rax+00h]
0x140005a55  mov     ebx, 22h ; '"'
0x140005a5a  jmp     short loc_140005A13
0x140005a5c  mov     eax, 16h
0x140005a61  mov     rbx, [rsp+28h+arg_0]
0x140005a66  mov     rsi, [rsp+28h+arg_8]
0x140005a6b  add     rsp, 20h
0x140005a6f  pop     rdi
0x140005a70  retn
```
