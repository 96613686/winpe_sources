# memcpy_s

- ea: `0x180007eac`
- end: `0x180007f35`
- name: `memcpy_s`
- size: `137`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `51`
- callee_count: `4`
- tags: ``

## callers

- `0x180005a2c`
- `0x180006c94`
- `0x180006eb4`
- `0x18000c3fc`
- `0x18000c544`
- `0x18000c61c`
- `0x18000d500`
- `0x18000e740`
- `0x18000f480`
- `0x18000f4d0`
- `0x18000f520`
- `0x18000f570`
- `0x180012050`
- `0x1800120a0`
- `0x1800120f0`
- `0x180017e44`
- `0x180017fb8`
- `0x18001a704`
- `0x18001aee0`
- `0x18001c070`
- `0x18001c0c0`
- `0x18001c110`
- `0x18001c160`
- `0x18001c1b0`
- `0x18001c3f4`
- `0x18001d6d0`
- `0x18001e980`
- `0x18001ebb4`
- `0x18001eda4`
- `0x180024770`
- `0x180024800`
- `0x1800253d0`
- `0x180025954`
- `0x1800266d0`
- `0x180027a08`
- `0x180027f70`
- `0x180027fc0`
- `0x180028010`
- `0x180028060`
- `0x1800280b0`
- `0x180029814`
- `0x180029aa4`
- `0x18002a2a8`
- `0x18002b0b0`
- `0x18002b28c`
- `0x18002ba80`
- `0x18002bb70`
- `0x18002c670`
- `0x18002c6c0`
- `0x18002c710`

## callees

- `0x180002b1a`
- `0x180002b78`
- `0x180003936`
- `0x180007eac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007ed2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007f13`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007ed2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007f13`

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
0x180007eac  mov     [rsp+arg_0], rbx
0x180007eb1  mov     [rsp+arg_8], rsi
0x180007eb6  push    rdi
0x180007eb7  sub     rsp, 20h
0x180007ebb  mov     rbx, r9
0x180007ebe  mov     rsi, r8
0x180007ec1  mov     rdi, rdx
0x180007ec4  test    r9, r9
0x180007ec7  jnz     short loc_180007ECD
0x180007ec9  xor     eax, eax
0x180007ecb  jmp     short loc_180007F25
0x180007ecd  test    rcx, rcx
0x180007ed0  jnz     short loc_180007EE8
0x180007ed2  call    cs:__imp__o__errno
0x180007ed8  mov     ebx, 16h
0x180007edd  mov     [rax], ebx
0x180007edf  call    _invalid_parameter_noinfo
0x180007ee4  mov     eax, ebx
0x180007ee6  jmp     short loc_180007F25
0x180007ee8  test    rsi, rsi
0x180007eeb  jz      short loc_180007EFF
0x180007eed  cmp     rdi, rbx
0x180007ef0  jb      short loc_180007EFF
0x180007ef2  mov     r8, rbx; Size
0x180007ef5  mov     rdx, rsi; Src
0x180007ef8  call    memcpy_0
0x180007efd  jmp     short loc_180007EC9
0x180007eff  mov     r8, rdi; Size
0x180007f02  xor     edx, edx; Val
0x180007f04  call    memset_0
0x180007f09  test    rsi, rsi
0x180007f0c  jz      short loc_180007ED2
0x180007f0e  cmp     rdi, rbx
0x180007f11  jnb     short loc_180007F20
0x180007f13  call    cs:__imp__o__errno
0x180007f19  mov     ebx, 22h ; '"'
0x180007f1e  jmp     short loc_180007EDD
0x180007f20  mov     eax, 16h
0x180007f25  mov     rbx, [rsp+28h+arg_0]
0x180007f2a  mov     rsi, [rsp+28h+arg_8]
0x180007f2f  add     rsp, 20h
0x180007f33  pop     rdi
0x180007f34  retn
```
