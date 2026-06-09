# _freopen_helper

- ea: `0x18005171c`
- end: `0x180051802`
- name: `_freopen_helper`
- size: `230`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180051810`
- `0x180051850`

## callees

- `0x180007f00`
- `0x18002f050`
- `0x180040540`
- `0x1800405e4`
- `0x18005063c`
- `0x18005171c`
- `0x180059844`

## pseudocode

```c
__int64 __fastcall freopen_helper(__int64 *a1, char *a2, _BYTE *a3, __int64 a4, int a5)
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
    *a1 = openfile(a2, a3, a5, a4);
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
0x18005171c  mov     [rsp+arg_18], r9
0x180051721  push    rbx
0x180051722  push    rsi
0x180051723  push    rdi
0x180051724  push    r14
0x180051726  sub     rsp, 38h
0x18005172a  mov     rbx, r9
0x18005172d  mov     r14, r8
0x180051730  mov     rsi, rdx
0x180051733  mov     rdi, rcx
0x180051736  test    rcx, rcx
0x180051739  jnz     short loc_18005176B
0x18005173b  call    _errno
0x180051740  mov     ebx, 16h
0x180051745  mov     [rax], ebx
0x180051747  mov     [rsp+58h+Reserved], 0; Reserved
0x180051750  xor     r9d, r9d; LineNo
0x180051753  xor     r8d, r8d; FileName
0x180051756  xor     edx, edx; FunctionName
0x180051758  xor     ecx, ecx; Expression
0x18005175a  call    _invalid_parameter
0x18005175f  mov     eax, ebx
0x180051761  add     rsp, 38h
0x180051765  pop     r14
0x180051767  pop     rdi
0x180051768  pop     rsi
0x180051769  pop     rbx
0x18005176a  retn
0x18005176b  mov     qword ptr [rcx], 0
0x180051772  test    rsi, rsi
0x180051775  jz      short loc_18005173B
0x180051777  test    r14, r14
0x18005177a  jz      short loc_18005173B
0x18005177c  test    rbx, rbx
0x18005177f  jz      short loc_18005173B
0x180051781  cmp     byte ptr [rdx], 0
0x180051784  jnz     short loc_180051794
0x180051786  call    _errno
0x18005178b  mov     ebx, 16h
0x180051790  mov     [rax], ebx
0x180051792  jmp     short loc_18005175F
0x180051794  mov     rcx, rbx; Stream
0x180051797  call    _lock_file
0x18005179c  nop
0x18005179d  test    byte ptr [rbx+18h], 83h
0x1800517a1  jz      short loc_1800517AB
0x1800517a3  mov     rcx, rbx; Stream
0x1800517a6  call    _fclose_nolock
0x1800517ab  mov     qword ptr [rbx+10h], 0
0x1800517b3  mov     qword ptr [rbx], 0
0x1800517ba  mov     dword ptr [rbx+18h], 0
0x1800517c1  mov     dword ptr [rbx+8], 0
0x1800517c8  mov     r9, rbx
0x1800517cb  mov     r8d, [rsp+58h+arg_20]
0x1800517d3  mov     rdx, r14
0x1800517d6  mov     rcx, rsi; FileName
0x1800517d9  call    _openfile
0x1800517de  mov     [rdi], rax
0x1800517e1  mov     rcx, rbx; Stream
0x1800517e4  call    _unlock_file
0x1800517e9  cmp     qword ptr [rdi], 0
0x1800517ed  jz      short loc_1800517F6
0x1800517ef  xor     eax, eax
0x1800517f1  jmp     loc_180051761
0x1800517f6  call    _errno
0x1800517fb  mov     eax, [rax]
0x1800517fd  jmp     loc_180051761
0x18007c027  push    rbp
0x18007c029  sub     rsp, 30h
0x18007c02d  mov     rbp, rdx
0x18007c030  mov     rcx, [rbp+78h]; Stream
0x18007c034  add     rsp, 30h
0x18007c038  pop     rbp
0x18007c039  jmp     _unlock_file
```
