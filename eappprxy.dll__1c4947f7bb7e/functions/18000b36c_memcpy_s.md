# memcpy_s

- ea: `0x18000b36c`
- end: `0x18000b402`
- name: `memcpy_s`
- size: `150`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180002bf8`
- `0x180003ca8`
- `0x180004d2c`
- `0x180005138`

## callees

- `0x1800020d6`
- `0x180002106`
- `0x18000b36c`
- `0x18000df2c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b392`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b3d9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b392`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b3d9`

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
0x18000b36c  mov     [rsp+arg_0], rbx
0x18000b371  mov     [rsp+arg_8], rsi
0x18000b376  push    rdi
0x18000b377  sub     rsp, 20h
0x18000b37b  mov     rbx, r9
0x18000b37e  mov     rsi, r8
0x18000b381  mov     rdi, rdx
0x18000b384  test    r9, r9
0x18000b387  jnz     short loc_18000B38D
0x18000b389  xor     eax, eax
0x18000b38b  jmp     short loc_18000B3F1
0x18000b38d  test    rcx, rcx
0x18000b390  jnz     short loc_18000B3AE
0x18000b392  call    cs:__imp__o__errno
0x18000b399  nop     dword ptr [rax+rax+00h]
0x18000b39e  mov     ebx, 16h
0x18000b3a3  mov     [rax], ebx
0x18000b3a5  call    _invalid_parameter_noinfo
0x18000b3aa  mov     eax, ebx
0x18000b3ac  jmp     short loc_18000B3F1
0x18000b3ae  test    rsi, rsi
0x18000b3b1  jz      short loc_18000B3C5
0x18000b3b3  cmp     rdi, rbx
0x18000b3b6  jb      short loc_18000B3C5
0x18000b3b8  mov     r8, rbx; Size
0x18000b3bb  mov     rdx, rsi; Src
0x18000b3be  call    memcpy_0
0x18000b3c3  jmp     short loc_18000B389
0x18000b3c5  mov     r8, rdi; Size
0x18000b3c8  xor     edx, edx; Val
0x18000b3ca  call    memset_0
0x18000b3cf  test    rsi, rsi
0x18000b3d2  jz      short loc_18000B392
0x18000b3d4  cmp     rdi, rbx
0x18000b3d7  jnb     short loc_18000B3EC
0x18000b3d9  call    cs:__imp__o__errno
0x18000b3e0  nop     dword ptr [rax+rax+00h]
0x18000b3e5  mov     ebx, 22h ; '"'
0x18000b3ea  jmp     short loc_18000B3A3
0x18000b3ec  mov     eax, 16h
0x18000b3f1  mov     rbx, [rsp+28h+arg_0]
0x18000b3f6  mov     rsi, [rsp+28h+arg_8]
0x18000b3fb  add     rsp, 20h
0x18000b3ff  pop     rdi
0x18000b400  retn
```
