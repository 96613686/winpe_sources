# memcpy_s

- ea: `0x18000cdd0`
- end: `0x18000ce59`
- name: `memcpy_s`
- size: `137`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x180006c9c`
- `0x18000a940`
- `0x18000ac64`
- `0x18000c48c`
- `0x18000c80c`

## callees

- `0x180002b62`
- `0x180002be8`
- `0x18000cdd0`
- `0x180014050`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000cdf6`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ce37`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000cdf6`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000ce37`

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
0x18000cdd0  mov     [rsp+arg_0], rbx
0x18000cdd5  mov     [rsp+arg_8], rsi
0x18000cdda  push    rdi
0x18000cddb  sub     rsp, 20h
0x18000cddf  mov     rbx, r9
0x18000cde2  mov     rsi, r8
0x18000cde5  mov     rdi, rdx
0x18000cde8  test    r9, r9
0x18000cdeb  jnz     short loc_18000CDF1
0x18000cded  xor     eax, eax
0x18000cdef  jmp     short loc_18000CE49
0x18000cdf1  test    rcx, rcx
0x18000cdf4  jnz     short loc_18000CE0C
0x18000cdf6  call    cs:__imp__o__errno
0x18000cdfc  mov     ebx, 16h
0x18000ce01  mov     [rax], ebx
0x18000ce03  call    _invalid_parameter_noinfo
0x18000ce08  mov     eax, ebx
0x18000ce0a  jmp     short loc_18000CE49
0x18000ce0c  test    rsi, rsi
0x18000ce0f  jz      short loc_18000CE23
0x18000ce11  cmp     rdi, rbx
0x18000ce14  jb      short loc_18000CE23
0x18000ce16  mov     r8, rbx; Size
0x18000ce19  mov     rdx, rsi; Src
0x18000ce1c  call    memcpy_0
0x18000ce21  jmp     short loc_18000CDED
0x18000ce23  mov     r8, rdi; Size
0x18000ce26  xor     edx, edx; Val
0x18000ce28  call    memset_0
0x18000ce2d  test    rsi, rsi
0x18000ce30  jz      short loc_18000CDF6
0x18000ce32  cmp     rdi, rbx
0x18000ce35  jnb     short loc_18000CE44
0x18000ce37  call    cs:__imp__o__errno
0x18000ce3d  mov     ebx, 22h ; '"'
0x18000ce42  jmp     short loc_18000CE01
0x18000ce44  mov     eax, 16h
0x18000ce49  mov     rbx, [rsp+28h+arg_0]
0x18000ce4e  mov     rsi, [rsp+28h+arg_8]
0x18000ce53  add     rsp, 20h
0x18000ce57  pop     rdi
0x18000ce58  retn
```
