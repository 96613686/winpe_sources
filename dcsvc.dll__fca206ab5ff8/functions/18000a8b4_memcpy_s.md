# memcpy_s

- ea: `0x18000a8b4`
- end: `0x18000a93d`
- name: `memcpy_s`
- size: `137`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x180005bec`
- `0x1800085d0`
- `0x1800088f4`
- `0x18000a03c`
- `0x18000a270`

## callees

- `0x180002666`
- `0x1800026c8`
- `0x18000a8b4`
- `0x180011c6c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a8da`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a91b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a8da`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a91b`

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
0x18000a8b4  mov     [rsp+arg_0], rbx
0x18000a8b9  mov     [rsp+arg_8], rsi
0x18000a8be  push    rdi
0x18000a8bf  sub     rsp, 20h
0x18000a8c3  mov     rbx, r9
0x18000a8c6  mov     rsi, r8
0x18000a8c9  mov     rdi, rdx
0x18000a8cc  test    r9, r9
0x18000a8cf  jnz     short loc_18000A8D5
0x18000a8d1  xor     eax, eax
0x18000a8d3  jmp     short loc_18000A92D
0x18000a8d5  test    rcx, rcx
0x18000a8d8  jnz     short loc_18000A8F0
0x18000a8da  call    cs:__imp__o__errno
0x18000a8e0  mov     ebx, 16h
0x18000a8e5  mov     [rax], ebx
0x18000a8e7  call    _invalid_parameter_noinfo
0x18000a8ec  mov     eax, ebx
0x18000a8ee  jmp     short loc_18000A92D
0x18000a8f0  test    rsi, rsi
0x18000a8f3  jz      short loc_18000A907
0x18000a8f5  cmp     rdi, rbx
0x18000a8f8  jb      short loc_18000A907
0x18000a8fa  mov     r8, rbx; Size
0x18000a8fd  mov     rdx, rsi; Src
0x18000a900  call    memcpy_0
0x18000a905  jmp     short loc_18000A8D1
0x18000a907  mov     r8, rdi; Size
0x18000a90a  xor     edx, edx; Val
0x18000a90c  call    memset_0
0x18000a911  test    rsi, rsi
0x18000a914  jz      short loc_18000A8DA
0x18000a916  cmp     rdi, rbx
0x18000a919  jnb     short loc_18000A928
0x18000a91b  call    cs:__imp__o__errno
0x18000a921  mov     ebx, 22h ; '"'
0x18000a926  jmp     short loc_18000A8E5
0x18000a928  mov     eax, 16h
0x18000a92d  mov     rbx, [rsp+28h+arg_0]
0x18000a932  mov     rsi, [rsp+28h+arg_8]
0x18000a937  add     rsp, 20h
0x18000a93b  pop     rdi
0x18000a93c  retn
```
