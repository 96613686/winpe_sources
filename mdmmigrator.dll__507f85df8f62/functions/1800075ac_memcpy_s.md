# memcpy_s

- ea: `0x1800075ac`
- end: `0x180007635`
- name: `memcpy_s`
- size: `137`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x18000554c`
- `0x180006384`
- `0x1800065a4`
- `0x18001cc54`
- `0x18001cf8c`

## callees

- `0x180002c36`
- `0x180002cbc`
- `0x1800035e6`
- `0x1800075ac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800075d2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007613`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800075d2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007613`

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
0x1800075ac  mov     [rsp+arg_0], rbx
0x1800075b1  mov     [rsp+arg_8], rsi
0x1800075b6  push    rdi
0x1800075b7  sub     rsp, 20h
0x1800075bb  mov     rbx, r9
0x1800075be  mov     rsi, r8
0x1800075c1  mov     rdi, rdx
0x1800075c4  test    r9, r9
0x1800075c7  jnz     short loc_1800075CD
0x1800075c9  xor     eax, eax
0x1800075cb  jmp     short loc_180007625
0x1800075cd  test    rcx, rcx
0x1800075d0  jnz     short loc_1800075E8
0x1800075d2  call    cs:__imp__o__errno
0x1800075d8  mov     ebx, 16h
0x1800075dd  mov     [rax], ebx
0x1800075df  call    _invalid_parameter_noinfo
0x1800075e4  mov     eax, ebx
0x1800075e6  jmp     short loc_180007625
0x1800075e8  test    rsi, rsi
0x1800075eb  jz      short loc_1800075FF
0x1800075ed  cmp     rdi, rbx
0x1800075f0  jb      short loc_1800075FF
0x1800075f2  mov     r8, rbx; Size
0x1800075f5  mov     rdx, rsi; Src
0x1800075f8  call    memcpy_0
0x1800075fd  jmp     short loc_1800075C9
0x1800075ff  mov     r8, rdi; Size
0x180007602  xor     edx, edx; Val
0x180007604  call    memset_0
0x180007609  test    rsi, rsi
0x18000760c  jz      short loc_1800075D2
0x18000760e  cmp     rdi, rbx
0x180007611  jnb     short loc_180007620
0x180007613  call    cs:__imp__o__errno
0x180007619  mov     ebx, 22h ; '"'
0x18000761e  jmp     short loc_1800075DD
0x180007620  mov     eax, 16h
0x180007625  mov     rbx, [rsp+28h+arg_0]
0x18000762a  mov     rsi, [rsp+28h+arg_8]
0x18000762f  add     rsp, 20h
0x180007633  pop     rdi
0x180007634  retn
```
