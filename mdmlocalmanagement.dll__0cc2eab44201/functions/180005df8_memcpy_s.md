# memcpy_s

- ea: `0x180005df8`
- end: `0x180005e8e`
- name: `memcpy_s`
- size: `150`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x1800029fc`
- `0x180003988`
- `0x1800049ac`
- `0x180004db8`

## callees

- `0x180001fae`
- `0x180001fea`
- `0x180005df8`
- `0x180006afc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005e1e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005e65`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005e1e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180005e65`

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
0x180005df8  mov     [rsp+arg_0], rbx
0x180005dfd  mov     [rsp+arg_8], rsi
0x180005e02  push    rdi
0x180005e03  sub     rsp, 20h
0x180005e07  mov     rbx, r9
0x180005e0a  mov     rsi, r8
0x180005e0d  mov     rdi, rdx
0x180005e10  test    r9, r9
0x180005e13  jnz     short loc_180005E19
0x180005e15  xor     eax, eax
0x180005e17  jmp     short loc_180005E7D
0x180005e19  test    rcx, rcx
0x180005e1c  jnz     short loc_180005E3A
0x180005e1e  call    cs:__imp__o__errno
0x180005e25  nop     dword ptr [rax+rax+00h]
0x180005e2a  mov     ebx, 16h
0x180005e2f  mov     [rax], ebx
0x180005e31  call    _invalid_parameter_noinfo
0x180005e36  mov     eax, ebx
0x180005e38  jmp     short loc_180005E7D
0x180005e3a  test    rsi, rsi
0x180005e3d  jz      short loc_180005E51
0x180005e3f  cmp     rdi, rbx
0x180005e42  jb      short loc_180005E51
0x180005e44  mov     r8, rbx; Size
0x180005e47  mov     rdx, rsi; Src
0x180005e4a  call    memcpy_0
0x180005e4f  jmp     short loc_180005E15
0x180005e51  mov     r8, rdi; Size
0x180005e54  xor     edx, edx; Val
0x180005e56  call    memset_0
0x180005e5b  test    rsi, rsi
0x180005e5e  jz      short loc_180005E1E
0x180005e60  cmp     rdi, rbx
0x180005e63  jnb     short loc_180005E78
0x180005e65  call    cs:__imp__o__errno
0x180005e6c  nop     dword ptr [rax+rax+00h]
0x180005e71  mov     ebx, 22h ; '"'
0x180005e76  jmp     short loc_180005E2F
0x180005e78  mov     eax, 16h
0x180005e7d  mov     rbx, [rsp+28h+arg_0]
0x180005e82  mov     rsi, [rsp+28h+arg_8]
0x180005e87  add     rsp, 20h
0x180005e8b  pop     rdi
0x180005e8c  retn
```
