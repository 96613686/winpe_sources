# ZeroLongWordAlign

- ea: `0x18001a060`
- end: `0x18001a0b9`
- name: `ZeroLongWordAlign`
- size: `89`
- prototype: ``
- caller_count: `17`
- callee_count: `2`
- tags: ``

## callers

- `0x1800087e8`
- `0x180009978`
- `0x18000acf4`
- `0x18000b040`
- `0x18000c350`
- `0x18000c874`
- `0x18000d45c`
- `0x18000fd08`
- `0x1800109fc`
- `0x180013364`
- `0x180013c38`
- `0x180013ee0`
- `0x180014dc0`
- `0x1800154a4`
- `0x180016e9c`
- `0x1800198f8`
- `0x180019f90`

## callees

- `0x18001a060`
- `0x18001a76c`

## pseudocode

```c
__int64 __fastcall ZeroLongWordAlign(_QWORD *a1, unsigned int a2, unsigned int *a3)
{
  unsigned int v4; // ebx
  __int64 result; // rax
  unsigned int v7; // ebx
  unsigned __int16 i; // di

  v4 = (a2 + 3) & 0xFFFFFFFC;
  *a3 = v4;
  if ( v4 < a2 )
    return 1002;
  v7 = v4 - a2;
  for ( i = 0; i < v7; ++i )
  {
    result = WriteByte(a1, 0, i + a2);
    if ( (_WORD)result )
      return result;
  }
  return 0;
}

```

## disassembly

```asm
0x18001a060  push    rbx
0x18001a062  push    rbp
0x18001a063  push    rsi
0x18001a064  push    rdi
0x18001a065  push    r14
0x18001a067  sub     rsp, 20h
0x18001a06b  lea     ebx, [rdx+3]
0x18001a06e  mov     esi, edx
0x18001a070  and     ebx, 0FFFFFFFCh
0x18001a073  mov     rbp, rcx
0x18001a076  mov     [r8], ebx
0x18001a079  cmp     ebx, edx
0x18001a07b  jnb     short loc_18001A084
0x18001a07d  mov     eax, 3EAh
0x18001a082  jmp     short loc_18001A0AE
0x18001a084  sub     ebx, esi
0x18001a086  xor     r14d, r14d
0x18001a089  mov     edi, r14d
0x18001a08c  movzx   eax, di
0x18001a08f  cmp     eax, ebx
0x18001a091  jnb     short loc_18001A0AB
0x18001a093  lea     r8d, [rax+rsi]
0x18001a097  xor     edx, edx
0x18001a099  mov     rcx, rbp
0x18001a09c  call    WriteByte
0x18001a0a1  test    ax, ax
0x18001a0a4  jnz     short loc_18001A0AE
0x18001a0a6  inc     di
0x18001a0a9  jmp     short loc_18001A08C
0x18001a0ab  mov     eax, r14d
0x18001a0ae  add     rsp, 20h
0x18001a0b2  pop     r14
0x18001a0b4  pop     rdi
0x18001a0b5  pop     rsi
0x18001a0b6  pop     rbp
0x18001a0b7  pop     rbx
0x18001a0b8  retn
```
