# memcpy_s

- ea: `0x14000bebc`
- end: `0x14000bf45`
- name: `memcpy_s`
- size: `137`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `8`
- callee_count: `4`
- tags: ``

## callers

- `0x1400072fc`
- `0x140008f14`
- `0x140009cc0`
- `0x14000a924`
- `0x14000b2c4`
- `0x14000b798`
- `0x14000ba8c`
- `0x14000baec`

## callees

- `0x1400060f8`
- `0x1400061b8`
- `0x140006965`
- `0x14000bebc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000bee2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000bf23`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000bee2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000bf23`

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
0x14000bebc  mov     [rsp+arg_0], rbx
0x14000bec1  mov     [rsp+arg_8], rsi
0x14000bec6  push    rdi
0x14000bec7  sub     rsp, 20h
0x14000becb  mov     rbx, r9
0x14000bece  mov     rsi, r8
0x14000bed1  mov     rdi, rdx
0x14000bed4  test    r9, r9
0x14000bed7  jnz     short loc_14000BEDD
0x14000bed9  xor     eax, eax
0x14000bedb  jmp     short loc_14000BF35
0x14000bedd  test    rcx, rcx
0x14000bee0  jnz     short loc_14000BEF8
0x14000bee2  call    cs:__imp__o__errno
0x14000bee8  mov     ebx, 16h
0x14000beed  mov     [rax], ebx
0x14000beef  call    _invalid_parameter_noinfo
0x14000bef4  mov     eax, ebx
0x14000bef6  jmp     short loc_14000BF35
0x14000bef8  test    rsi, rsi
0x14000befb  jz      short loc_14000BF0F
0x14000befd  cmp     rdi, rbx
0x14000bf00  jb      short loc_14000BF0F
0x14000bf02  mov     r8, rbx; Size
0x14000bf05  mov     rdx, rsi; Src
0x14000bf08  call    memcpy_0
0x14000bf0d  jmp     short loc_14000BED9
0x14000bf0f  mov     r8, rdi; Size
0x14000bf12  xor     edx, edx; Val
0x14000bf14  call    memset_0
0x14000bf19  test    rsi, rsi
0x14000bf1c  jz      short loc_14000BEE2
0x14000bf1e  cmp     rdi, rbx
0x14000bf21  jnb     short loc_14000BF30
0x14000bf23  call    cs:__imp__o__errno
0x14000bf29  mov     ebx, 22h ; '"'
0x14000bf2e  jmp     short loc_14000BEED
0x14000bf30  mov     eax, 16h
0x14000bf35  mov     rbx, [rsp+28h+arg_0]
0x14000bf3a  mov     rsi, [rsp+28h+arg_8]
0x14000bf3f  add     rsp, 20h
0x14000bf43  pop     rdi
0x14000bf44  retn
```
