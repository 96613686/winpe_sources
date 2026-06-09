# memcpy_s

- ea: `0x180007aa8`
- end: `0x180007b31`
- name: `memcpy_s`
- size: `137`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800049dc`
- `0x180005d60`
- `0x180005f80`

## callees

- `0x1800025ca`
- `0x180002612`
- `0x180007aa8`
- `0x180007ec4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007ace`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007b0f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007ace`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007b0f`

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
0x180007aa8  mov     [rsp+arg_0], rbx
0x180007aad  mov     [rsp+arg_8], rsi
0x180007ab2  push    rdi
0x180007ab3  sub     rsp, 20h
0x180007ab7  mov     rbx, r9
0x180007aba  mov     rsi, r8
0x180007abd  mov     rdi, rdx
0x180007ac0  test    r9, r9
0x180007ac3  jnz     short loc_180007AC9
0x180007ac5  xor     eax, eax
0x180007ac7  jmp     short loc_180007B21
0x180007ac9  test    rcx, rcx
0x180007acc  jnz     short loc_180007AE4
0x180007ace  call    cs:__imp__o__errno
0x180007ad4  mov     ebx, 16h
0x180007ad9  mov     [rax], ebx
0x180007adb  call    _invalid_parameter_noinfo
0x180007ae0  mov     eax, ebx
0x180007ae2  jmp     short loc_180007B21
0x180007ae4  test    rsi, rsi
0x180007ae7  jz      short loc_180007AFB
0x180007ae9  cmp     rdi, rbx
0x180007aec  jb      short loc_180007AFB
0x180007aee  mov     r8, rbx; Size
0x180007af1  mov     rdx, rsi; Src
0x180007af4  call    memcpy_0
0x180007af9  jmp     short loc_180007AC5
0x180007afb  mov     r8, rdi; Size
0x180007afe  xor     edx, edx; Val
0x180007b00  call    memset_0
0x180007b05  test    rsi, rsi
0x180007b08  jz      short loc_180007ACE
0x180007b0a  cmp     rdi, rbx
0x180007b0d  jnb     short loc_180007B1C
0x180007b0f  call    cs:__imp__o__errno
0x180007b15  mov     ebx, 22h ; '"'
0x180007b1a  jmp     short loc_180007AD9
0x180007b1c  mov     eax, 16h
0x180007b21  mov     rbx, [rsp+28h+arg_0]
0x180007b26  mov     rsi, [rsp+28h+arg_8]
0x180007b2b  add     rsp, 20h
0x180007b2f  pop     rdi
0x180007b30  retn
```
