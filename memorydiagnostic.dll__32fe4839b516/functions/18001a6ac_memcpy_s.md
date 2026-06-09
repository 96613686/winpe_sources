# memcpy_s

- ea: `0x18001a6ac`
- end: `0x18001a742`
- name: `memcpy_s`
- size: `150`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `9`
- callee_count: `4`
- tags: ``

## callers

- `0x180005b78`
- `0x18000da04`
- `0x180011660`
- `0x18001199c`
- `0x1800161cc`
- `0x1800183b4`
- `0x180018458`
- `0x18001864c`
- `0x18001873c`

## callees

- `0x180003306`
- `0x180003374`
- `0x18001a6ac`
- `0x180021ffc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001a6d2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001a719`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001a6d2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001a719`

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
0x18001a6ac  mov     [rsp+arg_0], rbx
0x18001a6b1  mov     [rsp+arg_8], rsi
0x18001a6b6  push    rdi
0x18001a6b7  sub     rsp, 20h
0x18001a6bb  mov     rbx, r9
0x18001a6be  mov     rsi, r8
0x18001a6c1  mov     rdi, rdx
0x18001a6c4  test    r9, r9
0x18001a6c7  jnz     short loc_18001A6CD
0x18001a6c9  xor     eax, eax
0x18001a6cb  jmp     short loc_18001A731
0x18001a6cd  test    rcx, rcx
0x18001a6d0  jnz     short loc_18001A6EE
0x18001a6d2  call    cs:__imp__o__errno
0x18001a6d9  nop     dword ptr [rax+rax+00h]
0x18001a6de  mov     ebx, 16h
0x18001a6e3  mov     [rax], ebx
0x18001a6e5  call    _invalid_parameter_noinfo
0x18001a6ea  mov     eax, ebx
0x18001a6ec  jmp     short loc_18001A731
0x18001a6ee  test    rsi, rsi
0x18001a6f1  jz      short loc_18001A705
0x18001a6f3  cmp     rdi, rbx
0x18001a6f6  jb      short loc_18001A705
0x18001a6f8  mov     r8, rbx; Size
0x18001a6fb  mov     rdx, rsi; Src
0x18001a6fe  call    memcpy_0
0x18001a703  jmp     short loc_18001A6C9
0x18001a705  mov     r8, rdi; Size
0x18001a708  xor     edx, edx; Val
0x18001a70a  call    memset_0
0x18001a70f  test    rsi, rsi
0x18001a712  jz      short loc_18001A6D2
0x18001a714  cmp     rdi, rbx
0x18001a717  jnb     short loc_18001A72C
0x18001a719  call    cs:__imp__o__errno
0x18001a720  nop     dword ptr [rax+rax+00h]
0x18001a725  mov     ebx, 22h ; '"'
0x18001a72a  jmp     short loc_18001A6E3
0x18001a72c  mov     eax, 16h
0x18001a731  mov     rbx, [rsp+28h+arg_0]
0x18001a736  mov     rsi, [rsp+28h+arg_8]
0x18001a73b  add     rsp, 20h
0x18001a73f  pop     rdi
0x18001a740  retn
```
