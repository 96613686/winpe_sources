# WriteBytes

- ea: `0x18001a7b8`
- end: `0x18001a7ff`
- name: `WriteBytes`
- size: `71`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18000f364`
- `0x1800109fc`
- `0x180013364`
- `0x18001a808`

## callees

- `0x18001a234`
- `0x18001a7b8`
- `0x18001abe2`

## pseudocode

```c
__int64 __fastcall WriteBytes(_QWORD *a1, const void *a2, unsigned int a3, size_t a4)
{
  __int64 result; // rax

  result = CheckOutOffset(a1, a3);
  if ( !(_WORD)result )
  {
    memcpy_0((void *)(*a1 + a3), a2, a4);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001a7b8  push    rbx
0x18001a7ba  push    rbp
0x18001a7bb  push    rsi
0x18001a7bc  push    rdi
0x18001a7bd  push    r14
0x18001a7bf  sub     rsp, 20h
0x18001a7c3  mov     edi, r8d
0x18001a7c6  mov     rbp, rdx
0x18001a7c9  mov     edx, edi
0x18001a7cb  mov     r8, r9
0x18001a7ce  mov     rbx, r9
0x18001a7d1  mov     rsi, rcx
0x18001a7d4  call    CheckOutOffset
0x18001a7d9  xor     r14d, r14d
0x18001a7dc  test    ax, ax
0x18001a7df  jnz     short loc_18001A7F4
0x18001a7e1  mov     ecx, edi
0x18001a7e3  mov     r8, rbx; Size
0x18001a7e6  add     rcx, [rsi]; void *
0x18001a7e9  mov     rdx, rbp; Src
0x18001a7ec  call    memcpy_0
0x18001a7f1  mov     eax, r14d
0x18001a7f4  add     rsp, 20h
0x18001a7f8  pop     r14
0x18001a7fa  pop     rdi
0x18001a7fb  pop     rsi
0x18001a7fc  pop     rbp
0x18001a7fd  pop     rbx
0x18001a7fe  retn
```
