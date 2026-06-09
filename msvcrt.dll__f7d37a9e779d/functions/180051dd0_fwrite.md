# fwrite

- ea: `0x180051dd0`
- end: `0x180051e4e`
- name: `fwrite`
- size: `126`
- prototype: `size_t __cdecl(const void *Buffer, size_t ElementSize, size_t ElementCount, FILE *Stream)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180007f00`
- `0x18002f050`
- `0x180040540`
- `0x1800405e4`
- `0x180051c28`
- `0x180051dd0`

## pseudocode

```c
size_t __cdecl fwrite(const void *Buffer, size_t ElementSize, size_t ElementCount, FILE *Stream)
{
  size_t v9; // rdi

  if ( !ElementSize || !ElementCount )
    return 0;
  if ( !Stream )
  {
    *errno() = 22;
    invalid_parameter(0, 0, 0, 0, 0);
  }
  lock_file(Stream);
  v9 = fwrite_nolock(Buffer, ElementSize, ElementCount, Stream);
  unlock_file(Stream);
  return v9;
}

```

## disassembly

```asm
0x180051dd0  mov     [rsp+arg_18], r9
0x180051dd5  push    rbx
0x180051dd6  push    rsi
0x180051dd7  push    rdi
0x180051dd8  push    r14
0x180051dda  sub     rsp, 38h
0x180051dde  mov     rbx, r9
0x180051de1  mov     rdi, r8
0x180051de4  mov     rsi, rdx
0x180051de7  mov     r14, rcx
0x180051dea  test    rdx, rdx
0x180051ded  jz      short loc_180051E18
0x180051def  test    r8, r8
0x180051df2  jz      short loc_180051E18
0x180051df4  test    rbx, rbx
0x180051df7  jnz     short loc_180051E24
0x180051df9  call    _errno
0x180051dfe  mov     dword ptr [rax], 16h
0x180051e04  mov     [rsp+58h+Reserved], rbx; Reserved
0x180051e09  xor     r9d, r9d; LineNo
0x180051e0c  xor     r8d, r8d; FileName
0x180051e0f  xor     edx, edx; FunctionName
0x180051e11  xor     ecx, ecx; Expression
0x180051e13  call    _invalid_parameter
0x180051e18  xor     eax, eax
0x180051e1a  add     rsp, 38h
0x180051e1e  pop     r14
0x180051e20  pop     rdi
0x180051e21  pop     rsi
0x180051e22  pop     rbx
0x180051e23  retn
0x180051e24  mov     rcx, rbx; Stream
0x180051e27  call    _lock_file
0x180051e2c  nop
0x180051e2d  mov     r9, rbx; Stream
0x180051e30  mov     r8, rdi; ElementCount
0x180051e33  mov     rdx, rsi; ElementSize
0x180051e36  mov     rcx, r14; Buffer
0x180051e39  call    _fwrite_nolock
0x180051e3e  mov     rdi, rax
0x180051e41  mov     rcx, rbx; Stream
0x180051e44  call    _unlock_file
0x180051e49  mov     rax, rdi
0x180051e4c  jmp     short loc_180051E1A
0x18007c027  push    rbp
0x18007c029  sub     rsp, 30h
0x18007c02d  mov     rbp, rdx
0x18007c030  mov     rcx, [rbp+78h]; Stream
0x18007c034  add     rsp, 30h
0x18007c038  pop     rbp
0x18007c039  jmp     _unlock_file
```
