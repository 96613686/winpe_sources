# memmove_s

- ea: `0x180060c10`
- end: `0x180060c74`
- name: `memmove_s`
- size: `100`
- prototype: `static errno_t __cdecl(void *const Destination, const rsize_t DestinationSize, const void *const Source, const rsize_t SourceSize)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180007f00`
- `0x18002f050`
- `0x180060c10`
- `0x180079c80`

## pseudocode

```c
errno_t __cdecl memmove_s(
        void *const Destination,
        const rsize_t DestinationSize,
        const void *const Source,
        const rsize_t SourceSize)
{
  int *v4; // rax
  int v5; // ebx

  if ( SourceSize )
  {
    if ( !Destination || !Source )
    {
      v4 = errno();
      v5 = 22;
      goto LABEL_4;
    }
    if ( DestinationSize < SourceSize )
    {
      v4 = errno();
      v5 = 34;
LABEL_4:
      *v4 = v5;
      invalid_parameter(0, 0, 0, 0, 0);
    }
    memmove(Destination, Source, SourceSize);
  }
  return 0;
}

```

## disassembly

```asm
0x180060c10  push    rbx
0x180060c12  sub     rsp, 30h
0x180060c16  mov     rax, r8
0x180060c19  test    r9, r9
0x180060c1c  jz      short loc_180060C6C
0x180060c1e  test    rcx, rcx
0x180060c21  jnz     short loc_180060C4B
0x180060c23  call    _errno
0x180060c28  mov     ebx, 16h
0x180060c2d  xor     r9d, r9d; LineNo
0x180060c30  mov     [rax], ebx
0x180060c32  xor     r8d, r8d; FileName
0x180060c35  mov     [rsp+38h+Reserved], 0; Reserved
0x180060c3e  xor     edx, edx; FunctionName
0x180060c40  xor     ecx, ecx; Expression
0x180060c42  call    _invalid_parameter
0x180060c47  mov     eax, ebx
0x180060c49  jmp     short loc_180060C6E
0x180060c4b  test    rax, rax
0x180060c4e  jz      short loc_180060C23
0x180060c50  cmp     rdx, r9
0x180060c53  jnb     short loc_180060C61
0x180060c55  call    _errno
0x180060c5a  mov     ebx, 22h ; '"'
0x180060c5f  jmp     short loc_180060C2D
0x180060c61  mov     r8, r9; Size
0x180060c64  mov     rdx, rax; Src
0x180060c67  call    memmove
0x180060c6c  xor     eax, eax
0x180060c6e  add     rsp, 30h
0x180060c72  pop     rbx
0x180060c73  retn
```
