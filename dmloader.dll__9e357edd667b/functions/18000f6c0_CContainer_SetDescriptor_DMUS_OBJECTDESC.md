# CContainer::SetDescriptor(_DMUS_OBJECTDESC *)

- ea: `0x18000f6c0`
- end: `0x18000f848`
- name: `?SetDescriptor@CContainer@@UEAAJPEAU_DMUS_OBJECTDESC@@@Z`
- size: `392`
- prototype: `__int64 __fastcall(CContainer *__hidden this, struct _DMUS_OBJECTDESC *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000f6c0`

## pseudocode

```c
__int64 __fastcall CContainer::SetDescriptor(CContainer *this, struct _DMUS_OBJECTDESC *a2)
{
  unsigned int v4; // ebp
  int v5; // r8d
  __int64 v6; // rsi
  __int64 v7; // r11
  __int64 v8; // rcx
  _WORD *v9; // rbx
  __int64 v10; // r10
  _WORD *v11; // rax
  _WORD *v12; // rcx
  __int64 v13; // rcx
  _WORD *v14; // r10
  _WORD *v15; // rax
  _WORD *v16; // rcx
  int v17; // ecx
  _WORD *v18; // rcx
  __int64 v19; // r10
  _WORD *v20; // rax
  _WORD *v21; // rcx

  if ( !a2 )
    return 2147500035LL;
  if ( *((_BYTE *)this + 864) )
    return 142086678;
  v4 = 0;
  v5 = 0;
  if ( (*((_BYTE *)a2 + 4) & 1) != 0 )
  {
    v5 = 1;
    *(_OWORD *)((char *)this + 56) = *(_OWORD *)((char *)a2 + 8);
  }
  v6 = 2147483646;
  v7 = 64;
  if ( (*((_BYTE *)a2 + 4) & 4) != 0 )
  {
    v8 = 2147483646;
    v9 = (_WORD *)((char *)a2 + 56);
    v10 = 64;
    v11 = (_WORD *)((char *)this + 88);
    do
    {
      if ( !v8 )
        break;
      if ( !*v9 )
        break;
      *v11++ = *v9++;
      --v8;
      --v10;
    }
    while ( v10 );
    v12 = v11 - 1;
    if ( v10 )
      v12 = v11;
    v5 |= 4u;
    *v12 = 0;
  }
  if ( (*((_BYTE *)a2 + 4) & 8) != 0 )
  {
    v13 = 2147483646;
    v14 = (_WORD *)((char *)a2 + 184);
    v15 = (_WORD *)((char *)this + 216);
    do
    {
      if ( !v13 )
        break;
      if ( !*v14 )
        break;
      *v15++ = *v14++;
      --v13;
      --v7;
    }
    while ( v7 );
    v16 = v15 - 1;
    if ( v7 )
      v16 = v15;
    v5 |= 8u;
    *v16 = 0;
  }
  v17 = *((_DWORD *)a2 + 1);
  if ( (v17 & 0x30) != 0 )
  {
    v18 = (_WORD *)((char *)a2 + 312);
    v19 = 260;
    v20 = (_WORD *)((char *)this + 344);
    do
    {
      if ( !v6 )
        break;
      if ( !*v18 )
        break;
      *v20++ = *v18++;
      --v6;
      --v19;
    }
    while ( v19 );
    v21 = v20 - 1;
    if ( v19 )
      v21 = v20;
    *v21 = 0;
    v17 = *((_DWORD *)a2 + 1);
    v5 |= v17 & 0x30;
  }
  if ( (v17 & 0x80u) != 0 )
  {
    v5 |= 0x80u;
    *((_QWORD *)this + 10) = *((_QWORD *)a2 + 6);
  }
  if ( (*((_DWORD *)a2 + 1) & 0x100) != 0 )
  {
    v5 |= 0x100u;
    *((_QWORD *)this + 9) = *((_QWORD *)a2 + 5);
  }
  *((_DWORD *)this + 13) |= v5;
  if ( (~v5 & *((_DWORD *)a2 + 1)) != 0 )
  {
    v4 = 1;
    *((_DWORD *)a2 + 1) = v5;
  }
  return v4;
}

```

## disassembly

```asm
0x18000f6c0  push    rbx
0x18000f6c2  push    rbp
0x18000f6c3  push    rsi
0x18000f6c4  push    rdi
0x18000f6c5  push    r14
0x18000f6c7  xor     r14d, r14d
0x18000f6ca  mov     r9, rcx
0x18000f6cd  test    rdx, rdx
0x18000f6d0  jnz     short loc_18000F6DC
0x18000f6d2  mov     eax, 80004003h
0x18000f6d7  jmp     loc_18000F841
0x18000f6dc  cmp     [rcx+360h], r14b
0x18000f6e3  jz      short loc_18000F6EF
0x18000f6e5  mov     eax, 8781216h
0x18000f6ea  jmp     loc_18000F841
0x18000f6ef  test    byte ptr [rdx+4], 1
0x18000f6f3  mov     ebp, r14d
0x18000f6f6  mov     r8d, r14d
0x18000f6f9  jz      short loc_18000F70A
0x18000f6fb  movups  xmm0, xmmword ptr [rdx+8]
0x18000f6ff  mov     r8d, 1
0x18000f705  movdqu  xmmword ptr [rcx+38h], xmm0
0x18000f70a  test    byte ptr [rdx+4], 4
0x18000f70e  mov     esi, 7FFFFFFEh
0x18000f713  mov     r11d, 40h ; '@'
0x18000f719  jz      short loc_18000F75C
0x18000f71b  mov     ecx, esi
0x18000f71d  lea     rbx, [rdx+38h]
0x18000f721  mov     r10d, r11d
0x18000f724  lea     rax, [r9+58h]
0x18000f728  test    rcx, rcx
0x18000f72b  jz      short loc_18000F749
0x18000f72d  movzx   edi, word ptr [rbx]
0x18000f730  test    di, di
0x18000f733  jz      short loc_18000F749
0x18000f735  mov     [rax], di
0x18000f738  add     rbx, 2
0x18000f73c  add     rax, 2
0x18000f740  dec     rcx
0x18000f743  sub     r10, 1
0x18000f747  jnz     short loc_18000F728
0x18000f749  test    r10, r10
0x18000f74c  lea     rcx, [rax-2]
0x18000f750  cmovnz  rcx, rax
0x18000f754  or      r8d, 4
0x18000f758  mov     [rcx], r14w
0x18000f75c  test    byte ptr [rdx+4], 8
0x18000f760  jz      short loc_18000F7A8
0x18000f762  mov     rcx, rsi
0x18000f765  lea     r10, [rdx+0B8h]
0x18000f76c  lea     rax, [r9+0D8h]
0x18000f773  test    rcx, rcx
0x18000f776  jz      short loc_18000F795
0x18000f778  movzx   ebx, word ptr [r10]
0x18000f77c  test    bx, bx
0x18000f77f  jz      short loc_18000F795
0x18000f781  mov     [rax], bx
0x18000f784  add     r10, 2
0x18000f788  add     rax, 2
0x18000f78c  dec     rcx
0x18000f78f  sub     r11, 1
0x18000f793  jnz     short loc_18000F773
0x18000f795  test    r11, r11
0x18000f798  lea     rcx, [rax-2]
0x18000f79c  cmovnz  rcx, rax
0x18000f7a0  or      r8d, 8
0x18000f7a4  mov     [rcx], r14w
0x18000f7a8  mov     ecx, [rdx+4]
0x18000f7ab  test    cl, 30h
0x18000f7ae  jz      short loc_18000F802
0x18000f7b0  lea     rcx, [rdx+138h]
0x18000f7b7  mov     r10d, 104h
0x18000f7bd  lea     rax, [r9+158h]
0x18000f7c4  test    rsi, rsi
0x18000f7c7  jz      short loc_18000F7E8
0x18000f7c9  movzx   r11d, word ptr [rcx]
0x18000f7cd  test    r11w, r11w
0x18000f7d1  jz      short loc_18000F7E8
0x18000f7d3  mov     [rax], r11w
0x18000f7d7  add     rcx, 2
0x18000f7db  add     rax, 2
0x18000f7df  dec     rsi
0x18000f7e2  sub     r10, 1
0x18000f7e6  jnz     short loc_18000F7C4
0x18000f7e8  lea     rcx, [rax-2]
0x18000f7ec  test    r10, r10
0x18000f7ef  cmovnz  rcx, rax
0x18000f7f3  mov     [rcx], r14w
0x18000f7f7  mov     ecx, [rdx+4]
0x18000f7fa  mov     eax, ecx
0x18000f7fc  and     eax, 30h
0x18000f7ff  or      r8d, eax
0x18000f802  test    cl, cl
0x18000f804  jns     short loc_18000F813
0x18000f806  mov     rax, [rdx+30h]
0x18000f80a  bts     r8d, 7
0x18000f80f  mov     [r9+50h], rax
0x18000f813  mov     ecx, 100h
0x18000f818  test    [rdx+4], ecx
0x18000f81b  jz      short loc_18000F828
0x18000f81d  mov     rax, [rdx+28h]
0x18000f821  or      r8d, ecx
0x18000f824  mov     [r9+48h], rax
0x18000f828  or      [r9+34h], r8d
0x18000f82c  mov     eax, r8d
0x18000f82f  not     eax
0x18000f831  test    [rdx+4], eax
0x18000f834  jz      short loc_18000F83F
0x18000f836  mov     ebp, 1
0x18000f83b  mov     [rdx+4], r8d
0x18000f83f  mov     eax, ebp
0x18000f841  pop     r14
0x18000f843  pop     rdi
0x18000f844  pop     rsi
0x18000f845  pop     rbp
0x18000f846  pop     rbx
0x18000f847  retn
```
