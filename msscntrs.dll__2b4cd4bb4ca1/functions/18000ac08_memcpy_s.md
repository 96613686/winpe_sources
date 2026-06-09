# memcpy_s

- ea: `0x18000ac08`
- end: `0x18000ac91`
- name: `memcpy_s`
- size: `137`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x18000686c`
- `0x180008c84`
- `0x180008fa8`
- `0x18000a2cc`
- `0x18000a54c`
- `0x18000a78c`

## callees

- `0x1800032b2`
- `0x180003320`
- `0x18000ac08`
- `0x1800156c8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ac2e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ac6f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ac2e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ac6f`

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
    v8 = (errno_t *)_o__errno(Destination, DestinationSize, Source);
    v9 = 22;
LABEL_5:
    *v8 = v9;
    invalid_parameter_noinfo();
    return v9;
  }
  if ( DestinationSize < SourceSize )
  {
    v8 = (errno_t *)_o__errno(Destination, DestinationSize, Source);
    v9 = 34;
    goto LABEL_5;
  }
  return 22;
}

```

## disassembly

```asm
0x18000ac08  mov     [rsp+arg_0], rbx
0x18000ac0d  mov     [rsp+arg_8], rsi
0x18000ac12  push    rdi
0x18000ac13  sub     rsp, 20h
0x18000ac17  mov     rbx, r9
0x18000ac1a  mov     rsi, r8
0x18000ac1d  mov     rdi, rdx
0x18000ac20  test    r9, r9
0x18000ac23  jnz     short loc_18000AC29
0x18000ac25  xor     eax, eax
0x18000ac27  jmp     short loc_18000AC81
0x18000ac29  test    rcx, rcx
0x18000ac2c  jnz     short loc_18000AC44
0x18000ac2e  call    cs:__imp__o__errno
0x18000ac34  mov     ebx, 16h
0x18000ac39  mov     [rax], ebx
0x18000ac3b  call    _invalid_parameter_noinfo
0x18000ac40  mov     eax, ebx
0x18000ac42  jmp     short loc_18000AC81
0x18000ac44  test    rsi, rsi
0x18000ac47  jz      short loc_18000AC5B
0x18000ac49  cmp     rdi, rbx
0x18000ac4c  jb      short loc_18000AC5B
0x18000ac4e  mov     r8, rbx; Size
0x18000ac51  mov     rdx, rsi; Src
0x18000ac54  call    memcpy_0
0x18000ac59  jmp     short loc_18000AC25
0x18000ac5b  mov     r8, rdi; Size
0x18000ac5e  xor     edx, edx; Val
0x18000ac60  call    memset_0
0x18000ac65  test    rsi, rsi
0x18000ac68  jz      short loc_18000AC2E
0x18000ac6a  cmp     rdi, rbx
0x18000ac6d  jnb     short loc_18000AC7C
0x18000ac6f  call    cs:__imp__o__errno
0x18000ac75  mov     ebx, 22h ; '"'
0x18000ac7a  jmp     short loc_18000AC39
0x18000ac7c  mov     eax, 16h
0x18000ac81  mov     rbx, [rsp+28h+arg_0]
0x18000ac86  mov     rsi, [rsp+28h+arg_8]
0x18000ac8b  add     rsp, 20h
0x18000ac8f  pop     rdi
0x18000ac90  retn
```
