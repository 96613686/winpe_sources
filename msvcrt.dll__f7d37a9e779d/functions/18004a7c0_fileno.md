# _fileno

- ea: `0x18004a7c0`
- end: `0x18004a7f9`
- name: `_fileno`
- size: `57`
- prototype: `int __cdecl(FILE *Stream)`
- caller_count: `38`
- callee_count: `3`
- tags: ``

## callers

- `0x18003b204`
- `0x18003c568`
- `0x18003d404`
- `0x18003d5b0`
- `0x18004a650`
- `0x18004a800`
- `0x18004a974`
- `0x18004a9c8`
- `0x18004ac50`
- `0x18004af24`
- `0x18004b0c4`
- `0x18004da80`
- `0x18004dcfc`
- `0x180050580`
- `0x18005063c`
- `0x180050800`
- `0x180050980`
- `0x180050afc`
- `0x180050e50`
- `0x180050f80`
- `0x1800510a4`
- `0x1800513d8`
- `0x18005186c`
- `0x1800519f0`
- `0x180051c28`
- `0x180051e54`
- `0x1800520d0`
- `0x180052250`
- `0x180052afc`
- `0x180052e60`
- `0x180053b40`
- `0x180054e40`
- `0x180057260`
- `0x1800576b0`
- `0x1800587f0`
- `0x180059690`
- `0x18005de10`
- `0x18005df78`

## callees

- `0x180007f00`
- `0x18002f050`
- `0x18004a7c0`

## pseudocode

```c
int __cdecl fileno(FILE *Stream)
{
  if ( !Stream )
  {
    *errno() = 22;
    invalid_parameter(0, 0, 0, 0, 0);
  }
  return Stream->_file;
}

```

## disassembly

```asm
0x18004a7c0  sub     rsp, 38h
0x18004a7c4  test    rcx, rcx
0x18004a7c7  jnz     short loc_18004A7F1
0x18004a7c9  call    _errno
0x18004a7ce  xor     r9d, r9d; LineNo
0x18004a7d1  mov     [rsp+38h+Reserved], 0; Reserved
0x18004a7da  xor     r8d, r8d; FileName
0x18004a7dd  xor     edx, edx; FunctionName
0x18004a7df  xor     ecx, ecx; Expression
0x18004a7e1  mov     dword ptr [rax], 16h
0x18004a7e7  call    _invalid_parameter
0x18004a7ec  or      eax, 0FFFFFFFFh
0x18004a7ef  jmp     short loc_18004A7F4
0x18004a7f1  mov     eax, [rcx+1Ch]
0x18004a7f4  add     rsp, 38h
0x18004a7f8  retn
```
