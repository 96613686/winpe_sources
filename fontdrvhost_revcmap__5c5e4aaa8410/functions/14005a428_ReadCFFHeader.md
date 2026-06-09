# ReadCFFHeader

- ea: `0x14005a428`
- end: `0x14005a4ae`
- name: `ReadCFFHeader`
- size: `134`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140059d9c`

## callees

- `0x14005a428`
- `0x140075de0`
- `0x140098010`

## pseudocode

```c
__int64 __fastcall ReadCFFHeader(__int64 a1, __int64 a2, _BYTE *a3)
{
  char v5; // cl
  char v6; // al
  _BYTE v7[128]; // [rsp+30h] [rbp-98h] BYREF

  if ( (*(__int64 (__fastcall **)(_QWORD, _BYTE *, __int64))(a1 + 8))(*(_QWORD *)a1, v7, 4) != 1 )
    return 0xFFFFFFFFLL;
  v5 = v7[0];
  a3[1] = v7[1];
  a3[2] = v7[2];
  v6 = v7[3];
  *a3 = v5;
  a3[3] = v6;
  return v5 != 1 ? 0xFFFFFFFC : 0;
}

```

## disassembly

```asm
0x14005a428  push    rbx
0x14005a42a  sub     rsp, 0C0h
0x14005a431  mov     rax, cs:__security_cookie
0x14005a438  xor     rax, rsp
0x14005a43b  mov     [rsp+0C8h+var_18], rax
0x14005a443  mov     rax, [rcx+8]
0x14005a447  mov     r9d, 1
0x14005a44d  mov     rcx, [rcx]
0x14005a450  mov     rbx, r8
0x14005a453  mov     [rsp+0C8h+var_A8], rdx
0x14005a458  lea     rdx, [rsp+0C8h+var_98]
0x14005a45d  lea     r8d, [r9+3]
0x14005a461  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a466  cmp     rax, 1
0x14005a46a  jz      short loc_14005A471
0x14005a46c  or      eax, 0FFFFFFFFh
0x14005a46f  jmp     short loc_14005A495
0x14005a471  mov     al, [rsp+0C8h+var_97]
0x14005a475  mov     cl, [rsp+0C8h+var_98]
0x14005a479  mov     [rbx+1], al
0x14005a47c  mov     al, [rsp+0C8h+var_96]
0x14005a480  mov     [rbx+2], al
0x14005a483  mov     al, [rsp+0C8h+var_95]
0x14005a487  mov     [rbx], cl
0x14005a489  dec     cl
0x14005a48b  neg     cl
0x14005a48d  mov     [rbx+3], al
0x14005a490  sbb     eax, eax
0x14005a492  and     eax, 0FFFFFFFCh
0x14005a495  mov     rcx, [rsp+0C8h+var_18]
0x14005a49d  xor     rcx, rsp; StackCookie
0x14005a4a0  call    __security_check_cookie
0x14005a4a5  add     rsp, 0C0h
0x14005a4ac  pop     rbx
0x14005a4ad  retn
```
