# strcpy_s

- ea: `0x180060db0`
- end: `0x180060e1f`
- name: `strcpy_s`
- size: `111`
- prototype: `errno_t __cdecl(char *Destination, rsize_t SizeInBytes, const char *Source)`
- caller_count: `42`
- callee_count: `3`
- tags: ``

## callers

- `0x180006c90`
- `0x180006e00`
- `0x180007454`
- `0x1800075b4`
- `0x180008678`
- `0x18000acf0`
- `0x18000adb0`
- `0x18000af10`
- `0x18000b5a0`
- `0x180018cc0`
- `0x180019810`
- `0x18001b684`
- `0x180026a30`
- `0x18002bf7c`
- `0x18002c44c`
- `0x18002cc48`
- `0x18002e8e0`
- `0x18002f6a8`
- `0x18002f9b0`
- `0x1800304a0`
- `0x1800328b0`
- `0x180032ac0`
- `0x180033660`
- `0x1800368f0`
- `0x180036d94`
- `0x18003f628`
- `0x18003f8e4`
- `0x18003fcc8`
- `0x18004bb10`
- `0x180052650`
- `0x180052800`
- `0x180052904`
- `0x18005e180`
- `0x18005e75c`
- `0x18005f098`
- `0x180063240`
- `0x1800633a0`
- `0x180063510`
- `0x1800679f0`
- `0x180069f80`
- `0x18006a5b0`
- `0x18006bb10`

## callees

- `0x180007f00`
- `0x18002f050`
- `0x180060db0`

## pseudocode

```c
errno_t __cdecl strcpy_s(char *Destination, rsize_t SizeInBytes, const char *Source)
{
  int *v3; // rax
  int v4; // ebx
  char *v5; // r9
  char v6; // al

  if ( !Destination || !SizeInBytes )
    goto LABEL_5;
  if ( !Source )
  {
    *Destination = 0;
LABEL_5:
    v3 = errno();
    v4 = 22;
    goto LABEL_6;
  }
  v5 = Destination;
  while ( 1 )
  {
    v6 = *Source;
    *v5 = *Source;
    if ( !v6 )
      break;
    ++v5;
    ++Source;
    if ( !--SizeInBytes )
    {
      *Destination = 0;
      v3 = errno();
      v4 = 34;
LABEL_6:
      *v3 = v4;
      invalid_parameter(0, 0, 0, 0, 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180060db0  push    rbx
0x180060db2  sub     rsp, 30h
0x180060db6  test    rcx, rcx
0x180060db9  jz      short loc_180060DC8
0x180060dbb  test    rdx, rdx
0x180060dbe  jz      short loc_180060DC8
0x180060dc0  test    r8, r8
0x180060dc3  jnz     short loc_180060DF4
0x180060dc5  mov     [rcx], r8b
0x180060dc8  call    _errno
0x180060dcd  mov     ebx, 16h
0x180060dd2  xor     r9d, r9d; LineNo
0x180060dd5  mov     [rsp+38h+Reserved], 0; Reserved
0x180060dde  xor     r8d, r8d; FileName
0x180060de1  mov     [rax], ebx
0x180060de3  xor     edx, edx; FunctionName
0x180060de5  xor     ecx, ecx; Expression
0x180060de7  call    _invalid_parameter
0x180060dec  mov     eax, ebx
0x180060dee  add     rsp, 30h
0x180060df2  pop     rbx
0x180060df3  retn
0x180060df4  mov     r9, rcx
0x180060df7  mov     al, [r8]
0x180060dfa  mov     [r9], al
0x180060dfd  test    al, al
0x180060dff  jz      short loc_180060E1B
0x180060e01  inc     r9
0x180060e04  inc     r8
0x180060e07  sub     rdx, 1
0x180060e0b  jnz     short loc_180060DF7
0x180060e0d  mov     [rcx], dl
0x180060e0f  call    _errno
0x180060e14  mov     ebx, 22h ; '"'
0x180060e19  jmp     short loc_180060DD2
0x180060e1b  xor     eax, eax
0x180060e1d  jmp     short loc_180060DEE
```
