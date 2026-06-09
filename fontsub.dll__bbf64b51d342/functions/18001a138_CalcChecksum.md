# CalcChecksum

- ea: `0x18001a138`
- end: `0x18001a1ff`
- name: `CalcChecksum`
- size: `199`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180009978`
- `0x18000c874`
- `0x18000d45c`
- `0x180019c00`
- `0x180019ec0`
- `0x180019f90`

## callees

- `0x18001a138`
- `0x18001a208`

## pseudocode

```c
__int64 __fastcall CalcChecksum(_QWORD *a1, __int64 a2, unsigned int a3, _DWORD *a4)
{
  unsigned int v5; // ebx
  __int64 result; // rax
  unsigned int v8; // edx
  int v9; // r10d
  unsigned int v10; // r9d
  int v11; // ebp
  __int64 v12; // rdx
  unsigned int v13; // r10d
  int v14; // r8d
  unsigned int i; // ecx
  __int64 v16; // rax

  *a4 = 0;
  v5 = a2;
  result = CheckInOffset(a1, a2, a3);
  if ( !(_WORD)result )
  {
    v10 = v8 + (v9 & 0xFFFFFFFC);
    if ( v8 < v10 )
    {
      v11 = 0;
      do
      {
        v12 = v5;
        v5 += 4;
        v11 += *(unsigned __int8 *)(v12 + *a1 + 3)
             | ((*(unsigned __int8 *)(v12 + *a1 + 2)
               | (((*(unsigned __int8 *)(v12 + *a1) << 8) | *(unsigned __int8 *)(v12 + *a1 + 1)) << 8)) << 8);
        *a4 = v11;
      }
      while ( v5 < v10 );
    }
    v13 = v9 & 3;
    if ( v13 )
    {
      v14 = 0;
      for ( i = 0; i < v13; ++i )
      {
        v16 = i;
        v14 = *(unsigned __int8 *)(v16 + *a1 + v5) + (v14 << 8);
      }
      *a4 += v14 << (8 * (4 - i));
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001a138  push    rbx
0x18001a13a  push    rbp
0x18001a13b  push    rsi
0x18001a13c  push    rdi
0x18001a13d  push    r14
0x18001a13f  sub     rsp, 20h
0x18001a143  mov     r10d, r8d
0x18001a146  xor     r14d, r14d
0x18001a149  mov     r8d, r8d
0x18001a14c  mov     rdi, r9
0x18001a14f  mov     [r9], r14d
0x18001a152  mov     ebx, edx
0x18001a154  mov     rsi, rcx
0x18001a157  call    CheckInOffset
0x18001a15c  test    ax, ax
0x18001a15f  jnz     loc_18001A1F4
0x18001a165  mov     r9d, r10d
0x18001a168  lea     r11d, [r14+4]
0x18001a16c  and     r9d, 0FFFFFFFCh
0x18001a170  add     r9d, edx
0x18001a173  cmp     edx, r9d
0x18001a176  jnb     short loc_18001A1B5
0x18001a178  mov     ebp, r14d
0x18001a17b  mov     rcx, [rsi]
0x18001a17e  mov     edx, ebx
0x18001a180  add     ebx, r11d
0x18001a183  movzx   eax, byte ptr [rdx+rcx]
0x18001a187  movzx   r8d, byte ptr [rdx+rcx+1]
0x18001a18d  shl     eax, 8
0x18001a190  or      r8d, eax
0x18001a193  movzx   eax, byte ptr [rdx+rcx+2]
0x18001a198  shl     r8d, 8
0x18001a19c  or      r8d, eax
0x18001a19f  movzx   eax, byte ptr [rdx+rcx+3]
0x18001a1a4  shl     r8d, 8
0x18001a1a8  or      r8d, eax
0x18001a1ab  add     ebp, r8d
0x18001a1ae  mov     [rdi], ebp
0x18001a1b0  cmp     ebx, r9d
0x18001a1b3  jb      short loc_18001A17B
0x18001a1b5  and     r10d, 3
0x18001a1b9  jz      short loc_18001A1F1
0x18001a1bb  mov     r8d, r14d
0x18001a1be  mov     ecx, r14d
0x18001a1c1  test    r10d, r10d
0x18001a1c4  jz      short loc_18001A1E1
0x18001a1c6  mov     r9d, ebx
0x18001a1c9  add     r9, [rsi]
0x18001a1cc  mov     eax, ecx
0x18001a1ce  inc     ecx
0x18001a1d0  shl     r8d, 8
0x18001a1d4  movzx   edx, byte ptr [rax+r9]
0x18001a1d9  add     r8d, edx
0x18001a1dc  cmp     ecx, r10d
0x18001a1df  jb      short loc_18001A1CC
0x18001a1e1  sub     r11d, ecx
0x18001a1e4  shl     r11d, 3
0x18001a1e8  mov     cl, r11b
0x18001a1eb  shl     r8d, cl
0x18001a1ee  add     [rdi], r8d
0x18001a1f1  mov     eax, r14d
0x18001a1f4  add     rsp, 20h
0x18001a1f8  pop     r14
0x18001a1fa  pop     rdi
0x18001a1fb  pop     rsi
0x18001a1fc  pop     rbp
0x18001a1fd  pop     rbx
0x18001a1fe  retn
```
