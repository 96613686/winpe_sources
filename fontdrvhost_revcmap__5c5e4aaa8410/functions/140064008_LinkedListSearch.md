# LinkedListSearch

- ea: `0x140064008`
- end: `0x140064056`
- name: `LinkedListSearch`
- size: `78`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140080fcc`
- `0x140081158`

## callees

- `0x140064008`
- `0x140098010`

## pseudocode

```c
_QWORD *__fastcall LinkedListSearch(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int (__fastcall *a4)(__int64, _QWORD *))
{
  __int64 v4; // rdi
  _QWORD *v6; // rbx
  _QWORD *v8; // rax

  v4 = lruListHead;
  v6 = (_QWORD *)lruListHead;
  while ( v6 )
  {
    if ( !a4(a1, v6) )
      return v6;
    v8 = (_QWORD *)*v6;
    v6 = 0;
    if ( v8 != (_QWORD *)v4 )
      v6 = v8;
  }
  return 0;
}

```

## disassembly

```asm
0x140064008  push    rbx
0x14006400a  push    rbp
0x14006400b  push    rsi
0x14006400c  push    rdi
0x14006400d  sub     rsp, 28h
0x140064011  mov     rdi, cs:lruListHead
0x140064018  mov     rsi, r9
0x14006401b  mov     rbx, rdi
0x14006401e  mov     rbp, rcx
0x140064021  test    rbx, rbx
0x140064024  jz      short loc_14006404B
0x140064026  mov     rdx, rbx
0x140064029  mov     rcx, rbp
0x14006402c  mov     rax, rsi
0x14006402f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140064034  test    eax, eax
0x140064036  jz      short loc_140064046
0x140064038  mov     rax, [rbx]
0x14006403b  xor     ebx, ebx
0x14006403d  cmp     rax, rdi
0x140064040  cmovnz  rbx, rax
0x140064044  jmp     short loc_140064021
0x140064046  mov     rax, rbx
0x140064049  jmp     short loc_14006404D
0x14006404b  xor     eax, eax
0x14006404d  add     rsp, 28h
0x140064051  pop     rdi
0x140064052  pop     rsi
0x140064053  pop     rbp
0x140064054  pop     rbx
0x140064055  retn
```
