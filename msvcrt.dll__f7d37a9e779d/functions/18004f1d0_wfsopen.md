# _wfsopen

- ea: `0x18004f1d0`
- end: `0x18004f2b3`
- name: `_wfsopen`
- size: `227`
- prototype: `FILE *__cdecl(const wchar_t *FileName, const wchar_t *Mode, int ShFlag)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18004f140`
- `0x18004f160`

## callees

- `0x180007f00`
- `0x18002f050`
- `0x18002f2b0`
- `0x1800405e4`
- `0x18004f1d0`
- `0x180057034`
- `0x18005da6c`

## pseudocode

```c
FILE *__cdecl wfsopen(const wchar_t *FileName, const wchar_t *Mode, int ShFlag)
{
  __int64 v7; // rax
  FILE *v8; // rbx
  FILE *v9; // rdi
  __int64 v10; // [rsp+0h] [rbp-58h] BYREF
  __int64 *v11; // [rsp+30h] [rbp-28h]

  v11 = &v10;
  if ( !FileName )
  {
    *errno() = 22;
    return 0;
  }
  if ( !Mode || !*Mode )
  {
    *errno() = 22;
    invalid_parameter(0, 0, 0, 0, 0);
  }
  v7 = getstream();
  v8 = (FILE *)v7;
  if ( !v7 )
  {
    *errno() = 24;
    return 0;
  }
  if ( *FileName )
  {
    v9 = (FILE *)wopenfile((wchar_t *)FileName, Mode, ShFlag, v7);
    unlock_file(v8);
    return v9;
  }
  else
  {
    *errno() = 22;
    local_unwind(v11, &loc_18004F288);
    return 0;
  }
}

```

## disassembly

```asm
0x18004f1d0  mov     [rsp+arg_8], rbx
0x18004f1d5  mov     [rsp+arg_10], rsi
0x18004f1da  push    rdi
0x18004f1db  push    r14
0x18004f1dd  push    r15
0x18004f1df  sub     rsp, 40h
0x18004f1e3  mov     [rsp+58h+var_28], rsp
0x18004f1e8  mov     r14d, r8d
0x18004f1eb  mov     rdi, rdx
0x18004f1ee  mov     rsi, rcx
0x18004f1f1  xor     r15d, r15d
0x18004f1f4  test    rcx, rcx
0x18004f1f7  jnz     short loc_18004F21A
0x18004f1f9  call    _errno
0x18004f1fe  mov     dword ptr [rax], 16h
0x18004f204  xor     eax, eax
0x18004f206  mov     rbx, [rsp+58h+arg_8]
0x18004f20b  mov     rsi, [rsp+58h+arg_10]
0x18004f210  add     rsp, 40h
0x18004f214  pop     r15
0x18004f216  pop     r14
0x18004f218  pop     rdi
0x18004f219  retn
0x18004f21a  test    rdi, rdi
0x18004f21d  jnz     short loc_18004F240
0x18004f21f  call    _errno
0x18004f224  mov     dword ptr [rax], 16h
0x18004f22a  mov     [rsp+58h+Reserved], r15; Reserved
0x18004f22f  xor     r9d, r9d; LineNo
0x18004f232  xor     r8d, r8d; FileName
0x18004f235  xor     edx, edx; FunctionName
0x18004f237  xor     ecx, ecx; Expression
0x18004f239  call    _invalid_parameter
0x18004f23e  jmp     short loc_18004F204
0x18004f240  cmp     [rdx], r15w
0x18004f244  jz      short loc_18004F21F
0x18004f246  call    _getstream
0x18004f24b  mov     rbx, rax
0x18004f24e  mov     [rsp+58h+arg_0], rax
0x18004f253  test    rax, rax
0x18004f256  jnz     short loc_18004F265
0x18004f258  call    _errno
0x18004f25d  mov     dword ptr [rax], 18h
0x18004f263  jmp     short loc_18004F204
0x18004f265  cmp     [rsi], r15w
0x18004f269  jnz     short loc_18004F28F
0x18004f26b  call    _errno
0x18004f270  mov     dword ptr [rax], 16h
0x18004f276  lea     rdx, loc_18004F288
0x18004f27d  mov     rcx, [rsp+58h+var_28]
0x18004f282  call    _local_unwind
0x18004f287  nop
0x18004f288  xor     eax, eax
0x18004f28a  jmp     loc_18004F206
0x18004f28f  mov     r9, rbx
0x18004f292  mov     r8d, r14d
0x18004f295  mov     rdx, rdi
0x18004f298  mov     rcx, rsi; FileName
0x18004f29b  call    _wopenfile
0x18004f2a0  mov     rdi, rax
0x18004f2a3  mov     rcx, rbx; Stream
0x18004f2a6  call    _unlock_file
0x18004f2ab  mov     rax, rdi
0x18004f2ae  jmp     loc_18004F206
0x18007bf1a  push    rbp
0x18007bf1c  sub     rsp, 30h
0x18007bf20  mov     rbp, rdx
0x18007bf23  mov     rcx, [rbp+60h]; Stream
0x18007bf27  call    _unlock_file
0x18007bf2c  nop
0x18007bf2d  add     rsp, 30h
0x18007bf31  pop     rbp
0x18007bf32  retn
```
