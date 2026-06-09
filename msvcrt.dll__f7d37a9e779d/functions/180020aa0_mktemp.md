# _mktemp

- ea: `0x180020aa0`
- end: `0x180020afa`
- name: `_mktemp`
- size: `90`
- prototype: `char *__cdecl(char *TemplateName)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180007f00`
- `0x180020aa0`
- `0x180020b14`
- `0x18002f050`

## pseudocode

```c
char *__cdecl mktemp(char *TemplateName)
{
  char *v1; // rbx
  __int64 v2; // rdx

  v1 = TemplateName;
  if ( !TemplateName )
  {
    *errno() = 22;
    invalid_parameter(0, 0, 0, 0, 0);
  }
  v2 = -1;
  do
    ++v2;
  while ( TemplateName[v2] );
  if ( (unsigned int)mktemp_s_X(TemplateName, v2 + 1, 0) )
    return 0;
  return v1;
}

```

## disassembly

```asm
0x180020aa0  push    rbx
0x180020aa2  sub     rsp, 30h
0x180020aa6  mov     rbx, rcx
0x180020aa9  test    rcx, rcx
0x180020aac  jnz     short loc_180020AD1
0x180020aae  call    _errno
0x180020ab3  xor     r9d, r9d; LineNo
0x180020ab6  mov     [rsp+38h+Reserved], rbx; Reserved
0x180020abb  xor     r8d, r8d; FileName
0x180020abe  xor     edx, edx; FunctionName
0x180020ac0  xor     ecx, ecx; Expression
0x180020ac2  mov     dword ptr [rax], 16h
0x180020ac8  call    _invalid_parameter
0x180020acd  xor     eax, eax
0x180020acf  jmp     short loc_180020AF4
0x180020ad1  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180020ad5  inc     rdx
0x180020ad8  cmp     byte ptr [rcx+rdx], 0
0x180020adc  jnz     short loc_180020AD5
0x180020ade  inc     rdx
0x180020ae1  xor     r8d, r8d
0x180020ae4  call    _mktemp_s_X
0x180020ae9  xor     ecx, ecx
0x180020aeb  test    eax, eax
0x180020aed  cmovnz  rbx, rcx
0x180020af1  mov     rax, rbx
0x180020af4  add     rsp, 30h
0x180020af8  pop     rbx
0x180020af9  retn
```
