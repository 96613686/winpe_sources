# memcpy_s_0

- ea: `0x140011fb8`
- end: `0x14001203f`
- name: `memcpy_s_0`
- size: `135`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x14000f51c`
- `0x1400103dc`
- `0x140010614`
- `0x140010810`
- `0x140010870`

## callees

- `0x140002c8e`
- `0x140002cd6`
- `0x140002d98`
- `0x140011fb8`
- `0x140029bf4`

## pseudocode

```c
errno_t __cdecl memcpy_s_0(
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
    v8 = (errno_t *)o__errno_0();
    v9 = 22;
LABEL_5:
    *v8 = v9;
    invalid_parameter_noinfo();
    return v9;
  }
  if ( DestinationSize < SourceSize )
  {
    v8 = (errno_t *)o__errno_0();
    v9 = 34;
    goto LABEL_5;
  }
  return 22;
}

```

## disassembly

```asm
0x140011fb8  mov     [rsp+arg_0], rbx
0x140011fbd  mov     [rsp+arg_8], rsi
0x140011fc2  push    rdi
0x140011fc3  sub     rsp, 20h
0x140011fc7  mov     rbx, r9
0x140011fca  mov     rsi, r8
0x140011fcd  mov     rdi, rdx
0x140011fd0  test    r9, r9
0x140011fd3  jnz     short loc_140011FD9
0x140011fd5  xor     eax, eax
0x140011fd7  jmp     short loc_14001202F
0x140011fd9  test    rcx, rcx
0x140011fdc  jnz     short loc_140011FF3
0x140011fde  call    _o__errno_0
0x140011fe3  mov     ebx, 16h
0x140011fe8  mov     [rax], ebx
0x140011fea  call    _invalid_parameter_noinfo
0x140011fef  mov     eax, ebx
0x140011ff1  jmp     short loc_14001202F
0x140011ff3  test    rsi, rsi
0x140011ff6  jz      short loc_14001200A
0x140011ff8  cmp     rdi, rbx
0x140011ffb  jb      short loc_14001200A
0x140011ffd  mov     r8, rbx; Size
0x140012000  mov     rdx, rsi; Src
0x140012003  call    memcpy_0
0x140012008  jmp     short loc_140011FD5
0x14001200a  mov     r8, rdi; Size
0x14001200d  xor     edx, edx; Val
0x14001200f  call    memset_0
0x140012014  test    rsi, rsi
0x140012017  jz      short loc_140011FDE
0x140012019  cmp     rdi, rbx
0x14001201c  jnb     short loc_14001202A
0x14001201e  call    _o__errno_0
0x140012023  mov     ebx, 22h ; '"'
0x140012028  jmp     short loc_140011FE8
0x14001202a  mov     eax, 16h
0x14001202f  mov     rbx, [rsp+28h+arg_0]
0x140012034  mov     rsi, [rsp+28h+arg_8]
0x140012039  add     rsp, 20h
0x14001203d  pop     rdi
0x14001203e  retn
```
