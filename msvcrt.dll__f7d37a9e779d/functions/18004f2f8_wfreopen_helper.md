# _wfreopen_helper

- ea: `0x18004f2f8`
- end: `0x18004f3dc`
- name: `_wfreopen_helper`
- size: `228`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18004f2c0`
- `0x18004f3f0`

## callees

- `0x180007f00`
- `0x18002f050`
- `0x180040540`
- `0x1800405e4`
- `0x18004f2f8`
- `0x18005063c`
- `0x18005da6c`

## pseudocode

```c
__int64 __fastcall wfreopen_helper(__int64 *a1, wchar_t *a2, _WORD *a3, __int64 a4, int a5)
{
  if ( !a1 || (*a1 = 0, !a2) || !a3 || !a4 )
  {
    *errno() = 22;
    invalid_parameter(0, 0, 0, 0, 0);
  }
  if ( *a2 )
  {
    lock_file((FILE *)a4);
    if ( (*(_BYTE *)(a4 + 24) & 0x83) != 0 )
      fclose_nolock((FILE *)a4);
    *(_QWORD *)(a4 + 16) = 0;
    *(_QWORD *)a4 = 0;
    *(_DWORD *)(a4 + 24) = 0;
    *(_DWORD *)(a4 + 8) = 0;
    *a1 = wopenfile(a2, a3, a5, a4);
    unlock_file((FILE *)a4);
    if ( *a1 )
      return 0;
    else
      return (unsigned int)*errno();
  }
  else
  {
    *errno() = 22;
    return 22;
  }
}

```

## disassembly

```asm
0x18004f2f8  mov     [rsp+arg_0], rbx
0x18004f2fd  mov     [rsp+arg_8], rsi
0x18004f302  mov     [rsp+arg_18], r9
0x18004f307  push    rdi
0x18004f308  push    r14
0x18004f30a  push    r15
0x18004f30c  sub     rsp, 30h
0x18004f310  mov     rbx, r9
0x18004f313  mov     r14, r8
0x18004f316  mov     rsi, rdx
0x18004f319  mov     rdi, rcx
0x18004f31c  xor     r15d, r15d
0x18004f31f  test    rcx, rcx
0x18004f322  jnz     short loc_18004F35A
0x18004f324  call    _errno
0x18004f329  mov     ebx, 16h
0x18004f32e  mov     [rax], ebx
0x18004f330  mov     [rsp+48h+Reserved], r15; Reserved
0x18004f335  xor     r9d, r9d; LineNo
0x18004f338  xor     r8d, r8d; FileName
0x18004f33b  xor     edx, edx; FunctionName
0x18004f33d  xor     ecx, ecx; Expression
0x18004f33f  call    _invalid_parameter
0x18004f344  mov     eax, ebx
0x18004f346  mov     rbx, [rsp+48h+arg_0]
0x18004f34b  mov     rsi, [rsp+48h+arg_8]
0x18004f350  add     rsp, 30h
0x18004f354  pop     r15
0x18004f356  pop     r14
0x18004f358  pop     rdi
0x18004f359  retn
0x18004f35a  mov     [rcx], r15
0x18004f35d  test    rsi, rsi
0x18004f360  jz      short loc_18004F324
0x18004f362  test    r14, r14
0x18004f365  jz      short loc_18004F324
0x18004f367  test    rbx, rbx
0x18004f36a  jz      short loc_18004F324
0x18004f36c  cmp     [rdx], r15w
0x18004f370  jnz     short loc_18004F380
0x18004f372  call    _errno
0x18004f377  mov     ebx, 16h
0x18004f37c  mov     [rax], ebx
0x18004f37e  jmp     short loc_18004F344
0x18004f380  mov     rcx, rbx; Stream
0x18004f383  call    _lock_file
0x18004f388  nop
0x18004f389  test    byte ptr [rbx+18h], 83h
0x18004f38d  jz      short loc_18004F397
0x18004f38f  mov     rcx, rbx; Stream
0x18004f392  call    _fclose_nolock
0x18004f397  mov     [rbx+10h], r15
0x18004f39b  mov     [rbx], r15
0x18004f39e  mov     [rbx+18h], r15d
0x18004f3a2  mov     [rbx+8], r15d
0x18004f3a6  mov     r9, rbx
0x18004f3a9  mov     r8d, [rsp+48h+arg_20]
0x18004f3ae  mov     rdx, r14
0x18004f3b1  mov     rcx, rsi; FileName
0x18004f3b4  call    _wopenfile
0x18004f3b9  mov     [rdi], rax
0x18004f3bc  mov     rcx, rbx; Stream
0x18004f3bf  call    _unlock_file
0x18004f3c4  cmp     [rdi], r15
0x18004f3c7  jz      short loc_18004F3D0
0x18004f3c9  xor     eax, eax
0x18004f3cb  jmp     loc_18004F346
0x18004f3d0  call    _errno
0x18004f3d5  mov     eax, [rax]
0x18004f3d7  jmp     loc_18004F346
0x18007bf3a  push    rbp
0x18007bf3c  sub     rsp, 30h
0x18007bf40  mov     rbp, rdx
0x18007bf43  mov     rcx, [rbp+68h]; Stream
0x18007bf47  add     rsp, 30h
0x18007bf4b  pop     rbp
0x18007bf4c  jmp     _unlock_file
```
