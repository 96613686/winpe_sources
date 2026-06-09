# memcpy_s

- ea: `0x1800094bc`
- end: `0x180009545`
- name: `memcpy_s`
- size: `137`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x1800053d8`
- `0x180007cc8`
- `0x180008dbc`
- `0x180008f3c`

## callees

- `0x180001f32`
- `0x180001f88`
- `0x1800094bc`
- `0x18000caf0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800094e2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180009523`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800094e2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180009523`

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
0x1800094bc  mov     [rsp+arg_0], rbx
0x1800094c1  mov     [rsp+arg_8], rsi
0x1800094c6  push    rdi
0x1800094c7  sub     rsp, 20h
0x1800094cb  mov     rbx, r9
0x1800094ce  mov     rsi, r8
0x1800094d1  mov     rdi, rdx
0x1800094d4  test    r9, r9
0x1800094d7  jnz     short loc_1800094DD
0x1800094d9  xor     eax, eax
0x1800094db  jmp     short loc_180009535
0x1800094dd  test    rcx, rcx
0x1800094e0  jnz     short loc_1800094F8
0x1800094e2  call    cs:__imp__o__errno
0x1800094e8  mov     ebx, 16h
0x1800094ed  mov     [rax], ebx
0x1800094ef  call    _invalid_parameter_noinfo
0x1800094f4  mov     eax, ebx
0x1800094f6  jmp     short loc_180009535
0x1800094f8  test    rsi, rsi
0x1800094fb  jz      short loc_18000950F
0x1800094fd  cmp     rdi, rbx
0x180009500  jb      short loc_18000950F
0x180009502  mov     r8, rbx; Size
0x180009505  mov     rdx, rsi; Src
0x180009508  call    memcpy_0
0x18000950d  jmp     short loc_1800094D9
0x18000950f  mov     r8, rdi; Size
0x180009512  xor     edx, edx; Val
0x180009514  call    memset_0
0x180009519  test    rsi, rsi
0x18000951c  jz      short loc_1800094E2
0x18000951e  cmp     rdi, rbx
0x180009521  jnb     short loc_180009530
0x180009523  call    cs:__imp__o__errno
0x180009529  mov     ebx, 22h ; '"'
0x18000952e  jmp     short loc_1800094ED
0x180009530  mov     eax, 16h
0x180009535  mov     rbx, [rsp+28h+arg_0]
0x18000953a  mov     rsi, [rsp+28h+arg_8]
0x18000953f  add     rsp, 20h
0x180009543  pop     rdi
0x180009544  retn
```
