# CMpegHeader::FromInt(ulong)

- ea: `0x18000f600`
- end: `0x18000f860`
- name: `?FromInt@CMpegHeader@@QEAAHK@Z`
- size: `608`
- prototype: `__int64 __fastcall(CMpegHeader *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800058e0`
- `0x180005a40`

## callees

- `0x18000f600`

## pseudocode

```c
__int64 __fastcall CMpegHeader::FromInt(CMpegHeader *this, unsigned int a2)
{
  unsigned int v3; // r14d
  int v4; // ecx
  int v5; // r9d
  int v6; // esi
  __int64 v7; // r15
  int v8; // r12d
  int v9; // r13d
  int v10; // ebx
  unsigned int v11; // ebp
  unsigned int v12; // edi
  __int64 v13; // r8
  int v14; // r15d
  int v15; // r14d
  int v16; // r9d
  float v17; // xmm1_4
  int v18; // esi
  int v19; // ebx
  __int64 result; // rax

  *((_DWORD *)this + 2) = a2 >> 21;
  *((_DWORD *)this + 6) = (a2 & 0x10000) == 0;
  *((_DWORD *)this + 10) = (a2 >> 8) & 1;
  *((_DWORD *)this + 12) = (a2 >> 4) & 3;
  *((_DWORD *)this + 13) = (a2 >> 3) & 1;
  v3 = (a2 >> 17) & 3;
  v4 = (a2 >> 20) & 1;
  v5 = (a2 >> 19) & 1;
  *((_DWORD *)this + 3) = v4;
  v6 = (unsigned __int16)a2 >> 12;
  *((_DWORD *)this + 4) = v5;
  v7 = (a2 >> 10) & 3;
  *((_DWORD *)this + 7) = v6;
  v8 = (a2 >> 9) & 1;
  *((_DWORD *)this + 8) = v7;
  v9 = (unsigned __int8)a2 >> 6;
  *((_DWORD *)this + 9) = v8;
  *((_DWORD *)this + 11) = v9;
  *((_DWORD *)this + 14) = (a2 >> 2) & 1;
  *((_DWORD *)this + 15) = a2 & 3;
  *((_DWORD *)this + 5) = 4 - v3;
  if ( a2 >> 21 == 2047
    && v3 == 1
    && v6 != 15
    && (unsigned __int16)a2 >> 12
    && (_DWORD)v7 != 3
    && (v4 || v3 == 1 && !v5) )
  {
    v10 = 0;
    v11 = 1;
    *((_DWORD *)this + 16) = 1;
    if ( v5 )
      v12 = 0;
    else
      v12 = 2 - (v4 != 0);
    v13 = 3LL - v3;
    v14 = dword_180014BF0[4 * v12 + v7];
    v15 = 1000 * dword_180014A50[15 * v13 + 15 * (v12 != 0 ? 3 : 0) + ((unsigned __int16)a2 >> 12)];
    v16 = dword_180014BE0[v13];
    LODWORD(v13) = dword_180014BB8[2 * v12 + v12 + v13];
    v17 = (float)((float)(int)v13 * 1000.0) / (float)v14;
    v18 = v16 * (v8 + (int)v13 * (v15 / v16) / v14);
    LOBYTE(v10) = v9 != 3;
    v19 = v10 + 1;
  }
  else
  {
    v19 = 0;
    v17 = 0.0;
    *((_QWORD *)this + 1) = 0;
    v11 = 0;
    *((_QWORD *)this + 2) = 0;
    v18 = 0;
    *((_QWORD *)this + 3) = 0;
    v15 = 0;
    *((_QWORD *)this + 4) = 0;
    v14 = 0;
    *((_QWORD *)this + 5) = 0;
    v12 = 0;
    *((_QWORD *)this + 6) = 0;
    *((_QWORD *)this + 7) = 0;
    *((_DWORD *)this + 16) = 0;
  }
  *((_DWORD *)this + 17) = v12;
  *((_DWORD *)this + 18) = v19;
  *((_DWORD *)this + 19) = v14;
  *((_DWORD *)this + 20) = v15;
  *((_DWORD *)this + 21) = v18;
  result = v11;
  *((float *)this + 22) = v17;
  return result;
}

```

## disassembly

```asm
0x18000f600  mov     [rsp+arg_8], rbx
0x18000f605  push    rbp
0x18000f606  push    rsi
0x18000f607  push    rdi
0x18000f608  push    r12
0x18000f60a  push    r13
0x18000f60c  push    r14
0x18000f60e  push    r15
0x18000f610  mov     r11, rcx
0x18000f613  mov     eax, edx
0x18000f615  shr     eax, 10h
0x18000f618  mov     r8d, edx
0x18000f61b  not     eax
0x18000f61d  shr     r8d, 15h
0x18000f621  and     eax, 1
0x18000f624  mov     [rcx+8], r8d
0x18000f628  mov     [r11+18h], eax
0x18000f62c  mov     r14d, edx
0x18000f62f  mov     eax, edx
0x18000f631  shr     r14d, 11h
0x18000f635  shr     eax, 8
0x18000f638  mov     ecx, edx
0x18000f63a  and     eax, 1
0x18000f63d  shr     ecx, 14h
0x18000f640  mov     [r11+28h], eax
0x18000f644  mov     r9d, edx
0x18000f647  mov     eax, edx
0x18000f649  shr     r9d, 13h
0x18000f64d  shr     eax, 4
0x18000f650  mov     esi, edx
0x18000f652  and     eax, 3
0x18000f655  shr     esi, 0Ch
0x18000f658  mov     [r11+30h], eax
0x18000f65c  mov     r15d, edx
0x18000f65f  mov     eax, edx
0x18000f661  shr     r15d, 0Ah
0x18000f665  shr     eax, 3
0x18000f668  mov     r12d, edx
0x18000f66b  and     eax, 1
0x18000f66e  shr     r12d, 9
0x18000f672  mov     [r11+34h], eax
0x18000f676  mov     r13d, edx
0x18000f679  mov     eax, edx
0x18000f67b  shr     r13d, 6
0x18000f67f  shr     eax, 2
0x18000f682  and     r14d, 3
0x18000f686  and     eax, 1
0x18000f689  and     ecx, 1
0x18000f68c  and     r9d, 1
0x18000f690  mov     [r11+0Ch], ecx
0x18000f694  and     esi, 0Fh
0x18000f697  mov     [r11+10h], r9d
0x18000f69b  and     r15d, 3
0x18000f69f  mov     [r11+1Ch], esi
0x18000f6a3  and     r12d, 1
0x18000f6a7  mov     [r11+20h], r15d
0x18000f6ab  and     r13d, 3
0x18000f6af  mov     [r11+24h], r12d
0x18000f6b3  and     edx, 3
0x18000f6b6  mov     [r11+2Ch], r13d
0x18000f6ba  mov     r10d, 4
0x18000f6c0  mov     [r11+38h], eax
0x18000f6c4  sub     r10d, r14d
0x18000f6c7  mov     [r11+3Ch], edx
0x18000f6cb  mov     [r11+14h], r10d
0x18000f6cf  cmp     r8d, 7FFh
0x18000f6d6  jnz     loc_18000F7D2
0x18000f6dc  cmp     r10d, 3
0x18000f6e0  jnz     loc_18000F7D2
0x18000f6e6  cmp     esi, 0Fh
0x18000f6e9  jz      loc_18000F7D2
0x18000f6ef  test    esi, esi
0x18000f6f1  jz      loc_18000F7D2
0x18000f6f7  cmp     r15d, r10d
0x18000f6fa  jz      loc_18000F7D2
0x18000f700  test    ecx, ecx
0x18000f702  jnz     short loc_18000F717
0x18000f704  cmp     r14d, 1
0x18000f708  jnz     loc_18000F7D2
0x18000f70e  test    r9d, r9d
0x18000f711  jnz     loc_18000F7D2
0x18000f717  xor     ebx, ebx
0x18000f719  mov     ebp, 1
0x18000f71e  mov     [r11+40h], ebp
0x18000f722  test    r9d, r9d
0x18000f725  jz      short loc_18000F72B
0x18000f727  mov     edi, ebx
0x18000f729  jmp     short loc_18000F732
0x18000f72b  neg     ecx
0x18000f72d  sbb     edi, edi
0x18000f72f  add     edi, 2
0x18000f732  mov     eax, r14d
0x18000f735  lea     r9, __ImageBase
0x18000f73c  mov     r10d, edi
0x18000f73f  mov     r8d, 3
0x18000f745  sub     r8, rax
0x18000f748  mov     eax, edi
0x18000f74a  neg     eax
0x18000f74c  mov     eax, esi
0x18000f74e  lea     rcx, [r15+r10*4]
0x18000f752  mov     r15d, ds:rva dword_180014BF0[r9+rcx*4]
0x18000f75a  sbb     rcx, rcx
0x18000f75d  and     ecx, 3
0x18000f760  add     rcx, r8
0x18000f763  imul    rdx, rcx, 0Fh
0x18000f767  movd    xmm0, r15d
0x18000f76c  cvtdq2ps xmm0, xmm0
0x18000f76f  lea     rcx, [r8+r10*2]
0x18000f773  add     rdx, rax
0x18000f776  add     rcx, r10
0x18000f779  imul    r14d, ds:rva dword_180014A50[r9+rdx*4], 3E8h
0x18000f785  mov     r9d, ds:rva dword_180014BE0[r9+r8*4]
0x18000f78d  lea     r8, __ImageBase
0x18000f794  mov     r8d, ds:rva dword_180014BB8[r8+rcx*4]
0x18000f79c  mov     eax, r14d
0x18000f79f  cdq
0x18000f7a0  movd    xmm1, r8d
0x18000f7a5  idiv    r9d
0x18000f7a8  cvtdq2ps xmm1, xmm1
0x18000f7ab  imul    eax, r8d
0x18000f7af  mulss   xmm1, cs:__real@447a0000
0x18000f7b7  cdq
0x18000f7b8  idiv    r15d
0x18000f7bb  divss   xmm1, xmm0
0x18000f7bf  lea     esi, [r12+rax]
0x18000f7c3  imul    esi, r9d
0x18000f7c7  cmp     r13d, 3
0x18000f7cb  setnz   bl
0x18000f7ce  inc     ebx
0x18000f7d0  jmp     short loc_18000F803
0x18000f7d2  xor     ebx, ebx
0x18000f7d4  xorps   xmm1, xmm1
0x18000f7d7  mov     [r11+8], rbx
0x18000f7db  mov     ebp, ebx
0x18000f7dd  mov     [r11+10h], rbx
0x18000f7e1  mov     esi, ebx
0x18000f7e3  mov     [r11+18h], rbx
0x18000f7e7  mov     r14d, ebx
0x18000f7ea  mov     [r11+20h], rbx
0x18000f7ee  mov     r15d, ebx
0x18000f7f1  mov     [r11+28h], rbx
0x18000f7f5  mov     edi, ebx
0x18000f7f7  mov     [r11+30h], rbx
0x18000f7fb  mov     [r11+38h], rbx
0x18000f7ff  mov     [r11+40h], ebx
0x18000f803  mov     eax, 54h ; 'T'
0x18000f808  mov     [rsp+38h+arg_0], r11
0x18000f80d  mov     r10d, 44h ; 'D'
0x18000f813  mov     [rsp+38h+arg_10], r11
0x18000f818  mov     r9d, 48h ; 'H'
0x18000f81e  mov     [rsp+38h+arg_18], r11
0x18000f823  mov     r8d, 4Ch ; 'L'
0x18000f829  mov     edx, 50h ; 'P'
0x18000f82e  mov     ecx, 58h ; 'X'
0x18000f833  mov     [r10+r11], edi
0x18000f837  mov     [r9+r11], ebx
0x18000f83b  mov     [r8+r11], r15d
0x18000f83f  mov     [rdx+r11], r14d
0x18000f843  mov     [rax+r11], esi
0x18000f847  mov     eax, ebp
0x18000f849  movss   dword ptr [rcx+r11], xmm1
0x18000f84f  mov     rbx, [rsp+38h+arg_8]
0x18000f854  pop     r15
0x18000f856  pop     r14
0x18000f858  pop     r13
0x18000f85a  pop     r12
0x18000f85c  pop     rdi
0x18000f85d  pop     rsi
0x18000f85e  pop     rbp
0x18000f85f  retn
```
