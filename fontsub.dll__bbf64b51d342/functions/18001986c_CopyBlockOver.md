# CopyBlockOver

- ea: `0x18001986c`
- end: `0x1800198f0`
- name: `CopyBlockOver`
- size: `132`
- prototype: `__int64 __fastcall(int, int, int, int, size_t Size)`
- caller_count: `9`
- callee_count: `4`
- tags: ``

## callers

- `0x180009010`
- `0x180009544`
- `0x180009978`
- `0x18000acf4`
- `0x18000c874`
- `0x180013ee0`
- `0x180014dc0`
- `0x1800154a4`
- `0x180016e9c`

## callees

- `0x18001986c`
- `0x18001a208`
- `0x18001a234`
- `0x18001abee`

## pseudocode

```c
__int64 __fastcall CopyBlockOver(_QWORD *a1, _QWORD *a2, unsigned int a3, unsigned int a4, size_t Size)
{
  __int64 v6; // rbp
  __int64 v8; // r14
  __int64 result; // rax

  v6 = a3;
  v8 = a4;
  if ( a3 + *a1 == a4 + *a2 || !(_DWORD)Size )
    return 0;
  result = CheckInOffset(a2, a4, (unsigned int)Size);
  if ( !(_WORD)result )
  {
    result = CheckOutOffset(a1, (unsigned int)v6);
    if ( !(_WORD)result )
    {
      memmove_0((void *)(v6 + *a1), (const void *)(v8 + *a2), (unsigned int)Size);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001986c  push    rbx
0x18001986e  push    rbp
0x18001986f  push    rsi
0x180019870  push    rdi
0x180019871  push    r12
0x180019873  push    r14
0x180019875  push    r15
0x180019877  sub     rsp, 20h
0x18001987b  mov     r11, [rcx]
0x18001987e  xor     r12d, r12d
0x180019881  mov     r10, [rdx]
0x180019884  mov     rsi, rdx
0x180019887  mov     ebp, r8d
0x18001988a  mov     rdi, rcx
0x18001988d  mov     r14d, r9d
0x180019890  add     r11, rbp
0x180019893  add     r10, r14
0x180019896  cmp     r11, r10
0x180019899  jz      short loc_1800198DE
0x18001989b  mov     eax, dword ptr [rsp+58h+Size]
0x1800198a2  test    eax, eax
0x1800198a4  jz      short loc_1800198DE
0x1800198a6  mov     r8d, eax
0x1800198a9  mov     edx, r9d
0x1800198ac  mov     rcx, rsi
0x1800198af  mov     ebx, eax
0x1800198b1  call    CheckInOffset
0x1800198b6  test    ax, ax
0x1800198b9  jnz     short loc_1800198E1
0x1800198bb  mov     edx, ebp
0x1800198bd  mov     rcx, rdi
0x1800198c0  call    CheckOutOffset
0x1800198c5  test    ax, ax
0x1800198c8  jnz     short loc_1800198E1
0x1800198ca  mov     rdx, [rsi]
0x1800198cd  mov     r8d, ebx; Size
0x1800198d0  mov     rcx, [rdi]
0x1800198d3  add     rdx, r14; Src
0x1800198d6  add     rcx, rbp; void *
0x1800198d9  call    memmove_0
0x1800198de  mov     eax, r12d
0x1800198e1  add     rsp, 20h
0x1800198e5  pop     r15
0x1800198e7  pop     r14
0x1800198e9  pop     r12
0x1800198eb  pop     rdi
0x1800198ec  pop     rsi
0x1800198ed  pop     rbp
0x1800198ee  pop     rbx
0x1800198ef  retn
```
