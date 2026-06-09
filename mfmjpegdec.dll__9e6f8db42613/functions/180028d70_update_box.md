# update_box

- ea: `0x180028d70`
- end: `0x1800290ea`
- name: `update_box`
- size: `890`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180027e00`
- `0x180028990`

## callees

- `0x180028d70`

## pseudocode

```c
__int64 __fastcall update_box(__int64 a1, int *a2)
{
  int v3; // r15d
  int v5; // esi
  int v6; // edi
  __int64 v7; // r14
  __int64 result; // rax
  int v9; // r10d
  __int64 v10; // r11
  int v11; // ebx
  int v12; // r8d
  int v13; // edx
  _WORD *v14; // rcx
  int v15; // ebx
  int v16; // r8d
  int v17; // edx
  _WORD *v18; // rcx
  int v19; // ebx
  int v20; // r8d
  int v21; // edx
  _WORD *v22; // rcx
  int v23; // ebx
  int v24; // r8d
  int v25; // edx
  _WORD *v26; // rcx
  int v27; // ebx
  int v28; // r8d
  int v29; // edx
  _WORD *v30; // rcx
  unsigned int v31; // ebx
  int v32; // r8d
  int v33; // edx
  _WORD *v34; // rcx
  __int64 v35; // rdx
  int v36; // r9d
  int v37; // r8d
  int v38; // r8d
  int v39; // ebx
  int v40; // r9d
  _WORD *i; // rdx
  bool v42; // zf
  int v43; // ecx

  v3 = *a2;
  v5 = a2[1];
  v6 = a2[2];
  v7 = *(_QWORD *)(*(_QWORD *)(a1 + 592) + 56LL);
  result = (unsigned int)a2[5];
  v9 = a2[3];
  v10 = a2[4];
  if ( v5 > *a2 )
  {
    v11 = *a2;
    while ( v6 > v9 )
    {
LABEL_9:
      if ( ++v11 > v5 )
        goto LABEL_12;
    }
    v12 = v6;
    while ( 1 )
    {
      v13 = v10;
      v14 = (_WORD *)(*(_QWORD *)(v7 + 8LL * v11) + 2 * v10 + ((__int64)v12 << 6));
      if ( (int)v10 <= (int)result )
        break;
LABEL_8:
      if ( ++v12 > v9 )
        goto LABEL_9;
    }
    while ( !*v14 )
    {
      ++v14;
      if ( ++v13 > (int)result )
        goto LABEL_8;
    }
    v3 = v11;
    *a2 = v11;
    if ( v5 > v11 )
    {
LABEL_12:
      v15 = v5;
      while ( v6 > v9 )
      {
LABEL_19:
        if ( --v15 < v3 )
          goto LABEL_22;
      }
      v16 = v6;
      while ( 1 )
      {
        v17 = v10;
        v18 = (_WORD *)(*(_QWORD *)(v7 + 8LL * v15) + 2 * v10 + ((__int64)v16 << 6));
        if ( (int)v10 <= (int)result )
          break;
LABEL_18:
        if ( ++v16 > v9 )
          goto LABEL_19;
      }
      while ( !*v18 )
      {
        ++v18;
        if ( ++v17 > (int)result )
          goto LABEL_18;
      }
      v5 = v15;
      a2[1] = v15;
    }
  }
LABEL_22:
  if ( v9 > v6 )
  {
    v19 = v6;
    while ( 1 )
    {
      v20 = v3;
      if ( v3 <= v5 )
        break;
LABEL_29:
      if ( ++v19 > v9 )
        goto LABEL_32;
    }
    while ( 1 )
    {
      v21 = v10;
      v22 = (_WORD *)(2 * (v10 + 32LL * v19) + *(_QWORD *)(v7 + 8LL * v20));
      if ( (int)v10 <= (int)result )
        break;
LABEL_28:
      if ( ++v20 > v5 )
        goto LABEL_29;
    }
    while ( !*v22 )
    {
      ++v22;
      if ( ++v21 > (int)result )
        goto LABEL_28;
    }
    v6 = v19;
    a2[2] = v19;
    if ( v9 > v19 )
    {
LABEL_32:
      v23 = v9;
      while ( 1 )
      {
        v24 = v3;
        if ( v3 <= v5 )
          break;
LABEL_38:
        if ( --v23 < v6 )
          goto LABEL_41;
      }
      while ( 1 )
      {
        v25 = v10;
        v26 = (_WORD *)(2 * (v10 + 32LL * v23) + *(_QWORD *)(v7 + 8LL * v24));
        if ( (int)v10 <= (int)result )
          break;
LABEL_37:
        if ( ++v24 > v5 )
          goto LABEL_38;
      }
      while ( !*v26 )
      {
        ++v26;
        if ( ++v25 > (int)result )
          goto LABEL_37;
      }
      v9 = v23;
      a2[3] = v23;
    }
  }
LABEL_41:
  if ( (int)result > (int)v10 )
  {
    v27 = v10;
    while ( 1 )
    {
      v28 = v3;
      if ( v3 <= v5 )
        break;
LABEL_48:
      if ( ++v27 > (int)result )
        goto LABEL_51;
    }
    while ( 1 )
    {
      v29 = v6;
      v30 = (_WORD *)(2 * (v27 + 32LL * v6) + *(_QWORD *)(v7 + 8LL * v28));
      if ( v6 <= v9 )
        break;
LABEL_47:
      if ( ++v28 > v5 )
        goto LABEL_48;
    }
    while ( !*v30 )
    {
      ++v29;
      v30 += 32;
      if ( v29 > v9 )
        goto LABEL_47;
    }
    LODWORD(v10) = v27;
    a2[4] = v27;
    if ( (int)result > v27 )
    {
LABEL_51:
      v31 = result;
      while ( 1 )
      {
        v32 = v3;
        if ( v3 <= v5 )
          break;
LABEL_57:
        if ( (int)--v31 < (int)v10 )
          goto LABEL_60;
      }
      while ( 1 )
      {
        v33 = v6;
        v34 = (_WORD *)(2 * ((int)v31 + 32LL * v6) + *(_QWORD *)(v7 + 8LL * v32));
        if ( v6 <= v9 )
          break;
LABEL_56:
        if ( ++v32 > v5 )
          goto LABEL_57;
      }
      while ( !*v34 )
      {
        ++v33;
        v34 += 32;
        if ( v33 > v9 )
          goto LABEL_56;
      }
      result = v31;
      a2[5] = v31;
    }
  }
LABEL_60:
  v35 = 4LL * *(int *)(a1 + 64);
  v36 = dword_180077978[*(int *)((char *)&dword_180077840 + v35)] * (v5 - v3);
  v37 = dword_180077978[*(int *)((char *)&dword_180077890 + v35)] * (v9 - v6);
  LODWORD(v35) = 8 * dword_180077978[*(int *)((char *)&dword_1800778E0 + v35)] * (result - v10);
  LODWORD(v35) = 4 * v37 * 4 * v37 + v35 * v35;
  v38 = 0;
  for ( a2[6] = 8 * v36 * 8 * v36 + v35; v3 <= v5; ++v3 )
  {
    if ( v6 <= v9 )
    {
      v39 = v6;
      do
      {
        v40 = v10;
        for ( i = (_WORD *)(*(_QWORD *)(v7 + 8LL * v3) + 2LL * (int)v10 + ((__int64)v39 << 6));
              v40 <= (int)result;
              v38 = v43 )
        {
          v42 = *i == 0;
          v43 = v38 + 1;
          ++i;
          if ( v42 )
            v43 = v38;
          ++v40;
        }
        ++v39;
      }
      while ( v39 <= v9 );
    }
  }
  a2[7] = v38;
  return result;
}

```

## disassembly

```asm
0x180028d70  push    rbx
0x180028d72  push    rbp
0x180028d73  push    rsi
0x180028d74  push    rdi
0x180028d75  push    r12
0x180028d77  push    r14
0x180028d79  push    r15
0x180028d7b  mov     rax, [rcx+250h]
0x180028d82  mov     r12, rdx
0x180028d85  mov     r15d, [rdx]
0x180028d88  mov     rbp, rcx
0x180028d8b  mov     esi, [rdx+4]
0x180028d8e  mov     edi, [rdx+8]
0x180028d91  mov     r14, [rax+38h]
0x180028d95  mov     eax, [rdx+14h]
0x180028d98  mov     r10d, [rdx+0Ch]
0x180028d9c  movsxd  r11, dword ptr [rdx+10h]
0x180028da0  cmp     esi, r15d
0x180028da3  jle     loc_180028E6A
0x180028da9  mov     ebx, r15d
0x180028dac  nop     dword ptr [rax+00h]
0x180028db0  cmp     edi, r10d
0x180028db3  jg      short loc_180028DFA
0x180028db5  movsxd  rcx, ebx
0x180028db8  mov     r8d, edi
0x180028dbb  mov     rcx, [r14+rcx*8]
0x180028dbf  lea     r9, [rcx+r11*2]
0x180028dc3  nop     dword ptr [rax+00h]
0x180028dc7  nop     word ptr [rax+rax+00000000h]
0x180028dd0  movsxd  rcx, r8d
0x180028dd3  mov     edx, r11d
0x180028dd6  shl     rcx, 6
0x180028dda  add     rcx, r9
0x180028ddd  cmp     r11d, eax
0x180028de0  jg      short loc_180028DF2
0x180028de2  cmp     word ptr [rcx], 0
0x180028de6  jnz     short loc_180028E02
0x180028de8  add     rcx, 2
0x180028dec  inc     edx
0x180028dee  cmp     edx, eax
0x180028df0  jle     short loc_180028DE2
0x180028df2  inc     r8d
0x180028df5  cmp     r8d, r10d
0x180028df8  jle     short loc_180028DD0
0x180028dfa  inc     ebx
0x180028dfc  cmp     ebx, esi
0x180028dfe  jle     short loc_180028DB0
0x180028e00  jmp     short loc_180028E0D
0x180028e02  mov     r15d, ebx
0x180028e05  mov     [r12], ebx
0x180028e09  cmp     esi, ebx
0x180028e0b  jle     short loc_180028E6A
0x180028e0d  mov     ebx, esi
0x180028e0f  nop
0x180028e10  cmp     edi, r10d
0x180028e13  jg      short loc_180028E5A
0x180028e15  movsxd  rcx, ebx
0x180028e18  mov     r8d, edi
0x180028e1b  mov     rcx, [r14+rcx*8]
0x180028e1f  lea     r9, [rcx+r11*2]
0x180028e23  nop     dword ptr [rax+00h]
0x180028e27  nop     word ptr [rax+rax+00000000h]
0x180028e30  movsxd  rcx, r8d
0x180028e33  mov     edx, r11d
0x180028e36  shl     rcx, 6
0x180028e3a  add     rcx, r9
0x180028e3d  cmp     r11d, eax
0x180028e40  jg      short loc_180028E52
0x180028e42  cmp     word ptr [rcx], 0
0x180028e46  jnz     short loc_180028E63
0x180028e48  add     rcx, 2
0x180028e4c  inc     edx
0x180028e4e  cmp     edx, eax
0x180028e50  jle     short loc_180028E42
0x180028e52  inc     r8d
0x180028e55  cmp     r8d, r10d
0x180028e58  jle     short loc_180028E30
0x180028e5a  dec     ebx
0x180028e5c  cmp     ebx, r15d
0x180028e5f  jge     short loc_180028E10
0x180028e61  jmp     short loc_180028E6A
0x180028e63  mov     esi, ebx
0x180028e65  mov     [r12+4], ebx
0x180028e6a  cmp     r10d, edi
0x180028e6d  jle     loc_180028F2A
0x180028e73  mov     ebx, edi
0x180028e75  mov     r8d, r15d
0x180028e78  cmp     r15d, esi
0x180028e7b  jg      short loc_180028EBA
0x180028e7d  movsxd  r9, ebx
0x180028e80  shl     r9, 5
0x180028e84  add     r9, r11
0x180028e87  add     r9, r9
0x180028e8a  nop     word ptr [rax+rax+00h]
0x180028e90  movsxd  rcx, r8d
0x180028e93  mov     edx, r11d
0x180028e96  mov     rcx, [r14+rcx*8]
0x180028e9a  add     rcx, r9
0x180028e9d  cmp     r11d, eax
0x180028ea0  jg      short loc_180028EB2
0x180028ea2  cmp     word ptr [rcx], 0
0x180028ea6  jnz     short loc_180028EC3
0x180028ea8  add     rcx, 2
0x180028eac  inc     edx
0x180028eae  cmp     edx, eax
0x180028eb0  jle     short loc_180028EA2
0x180028eb2  inc     r8d
0x180028eb5  cmp     r8d, esi
0x180028eb8  jle     short loc_180028E90
0x180028eba  inc     ebx
0x180028ebc  cmp     ebx, r10d
0x180028ebf  jle     short loc_180028E75
0x180028ec1  jmp     short loc_180028ECF
0x180028ec3  mov     edi, ebx
0x180028ec5  mov     [r12+8], ebx
0x180028eca  cmp     r10d, ebx
0x180028ecd  jle     short loc_180028F2A
0x180028ecf  mov     ebx, r10d
0x180028ed2  mov     r8d, r15d
0x180028ed5  cmp     r15d, esi
0x180028ed8  jg      short loc_180028F1A
0x180028eda  movsxd  r9, ebx
0x180028edd  shl     r9, 5
0x180028ee1  add     r9, r11
0x180028ee4  add     r9, r9
0x180028ee7  nop     word ptr [rax+rax+00000000h]
0x180028ef0  movsxd  rcx, r8d
0x180028ef3  mov     edx, r11d
0x180028ef6  mov     rcx, [r14+rcx*8]
0x180028efa  add     rcx, r9
0x180028efd  cmp     r11d, eax
0x180028f00  jg      short loc_180028F12
0x180028f02  cmp     word ptr [rcx], 0
0x180028f06  jnz     short loc_180028F22
0x180028f08  add     rcx, 2
0x180028f0c  inc     edx
0x180028f0e  cmp     edx, eax
0x180028f10  jle     short loc_180028F02
0x180028f12  inc     r8d
0x180028f15  cmp     r8d, esi
0x180028f18  jle     short loc_180028EF0
0x180028f1a  dec     ebx
0x180028f1c  cmp     ebx, edi
0x180028f1e  jge     short loc_180028ED2
0x180028f20  jmp     short loc_180028F2A
0x180028f22  mov     r10d, ebx
0x180028f25  mov     [r12+0Ch], ebx
0x180028f2a  cmp     eax, r11d
0x180028f2d  jle     loc_180028FEA
0x180028f33  mov     ebx, r11d
0x180028f36  mov     r8d, r15d
0x180028f39  cmp     r15d, esi
0x180028f3c  jg      short loc_180028F7A
0x180028f3e  movsxd  r9, edi
0x180028f41  shl     r9, 5
0x180028f45  movsxd  rcx, ebx
0x180028f48  add     r9, rcx
0x180028f4b  add     r9, r9
0x180028f4e  xchg    ax, ax
0x180028f50  movsxd  rcx, r8d
0x180028f53  mov     edx, edi
0x180028f55  mov     rcx, [r14+rcx*8]
0x180028f59  add     rcx, r9
0x180028f5c  cmp     edi, r10d
0x180028f5f  jg      short loc_180028F72
0x180028f61  cmp     word ptr [rcx], 0
0x180028f65  jnz     short loc_180028F82
0x180028f67  inc     edx
0x180028f69  add     rcx, 40h ; '@'
0x180028f6d  cmp     edx, r10d
0x180028f70  jle     short loc_180028F61
0x180028f72  inc     r8d
0x180028f75  cmp     r8d, esi
0x180028f78  jle     short loc_180028F50
0x180028f7a  inc     ebx
0x180028f7c  cmp     ebx, eax
0x180028f7e  jle     short loc_180028F36
0x180028f80  jmp     short loc_180028F8E
0x180028f82  mov     r11d, ebx
0x180028f85  mov     [r12+10h], ebx
0x180028f8a  cmp     eax, ebx
0x180028f8c  jle     short loc_180028FEA
0x180028f8e  mov     ebx, eax
0x180028f90  mov     r8d, r15d
0x180028f93  cmp     r15d, esi
0x180028f96  jg      short loc_180028FDA
0x180028f98  movsxd  r9, edi
0x180028f9b  shl     r9, 5
0x180028f9f  movsxd  rcx, ebx
0x180028fa2  add     r9, rcx
0x180028fa5  add     r9, r9
0x180028fa8  nop     dword ptr [rax+rax+00000000h]
0x180028fb0  movsxd  rcx, r8d
0x180028fb3  mov     edx, edi
0x180028fb5  mov     rcx, [r14+rcx*8]
0x180028fb9  add     rcx, r9
0x180028fbc  cmp     edi, r10d
0x180028fbf  jg      short loc_180028FD2
0x180028fc1  cmp     word ptr [rcx], 0
0x180028fc5  jnz     short loc_180028FE3
0x180028fc7  inc     edx
0x180028fc9  add     rcx, 40h ; '@'
0x180028fcd  cmp     edx, r10d
0x180028fd0  jle     short loc_180028FC1
0x180028fd2  inc     r8d
0x180028fd5  cmp     r8d, esi
0x180028fd8  jle     short loc_180028FB0
0x180028fda  dec     ebx
0x180028fdc  cmp     ebx, r11d
0x180028fdf  jge     short loc_180028F90
0x180028fe1  jmp     short loc_180028FEA
0x180028fe3  mov     eax, ebx
0x180028fe5  mov     [r12+14h], ebx
0x180028fea  movsxd  rcx, dword ptr [rbp+40h]
0x180028fee  lea     rbx, __ImageBase
0x180028ff5  mov     r9d, esi
0x180028ff8  mov     r8d, r10d
0x180028ffb  sub     r8d, edi
0x180028ffe  sub     r9d, r15d
0x180029001  lea     rdx, ds:0[rcx*4]
0x180029009  movsxd  rcx, dword ptr [rdx+rbx+77840h]
0x180029011  imul    r9d, ds:rva dword_180077978[rbx+rcx*4]
0x18002901a  movsxd  rcx, dword ptr [rdx+rbx+77890h]
0x180029022  imul    r8d, ds:rva dword_180077978[rbx+rcx*4]
0x18002902b  movsxd  rcx, dword ptr [rdx+rbx+778E0h]
0x180029033  mov     edx, eax
0x180029035  sub     edx, r11d
0x180029038  shl     r9d, 3
0x18002903c  imul    r9d, r9d
0x180029040  imul    edx, ds:rva dword_180077978[rbx+rcx*4]
0x180029048  shl     r8d, 2
0x18002904c  imul    r8d, r8d
0x180029050  shl     edx, 3
0x180029053  imul    edx, edx
0x180029056  add     edx, r8d
0x180029059  xor     r8d, r8d
0x18002905c  add     edx, r9d
0x18002905f  mov     [r12+18h], edx
0x180029064  cmp     r15d, esi
0x180029067  jg      short loc_1800290DA
0x180029069  nop     dword ptr [rax+00000000h]
0x180029070  cmp     edi, r10d
0x180029073  jg      short loc_1800290D2
0x180029075  movsxd  rcx, r15d
0x180029078  mov     ebx, edi
0x18002907a  movsxd  rdx, r11d
0x18002907d  mov     rcx, [r14+rcx*8]
0x180029081  lea     rbp, [rcx+rdx*2]
0x180029085  nop     word ptr [rax+rax+00000000h]
0x180029090  movsxd  rdx, ebx
0x180029093  mov     r9d, r11d
0x180029096  shl     rdx, 6
0x18002909a  add     rdx, rbp
0x18002909d  cmp     r11d, eax
0x1800290a0  jg      short loc_1800290CB
0x1800290a2  nop     dword ptr [rax+00h]
0x1800290a6  nop     word ptr [rax+rax+00000000h]
0x1800290b0  cmp     word ptr [rdx], 0
0x1800290b4  lea     ecx, [r8+1]
0x1800290b8  lea     rdx, [rdx+2]
0x1800290bc  cmovz   ecx, r8d
0x1800290c0  inc     r9d
0x1800290c3  mov     r8d, ecx
0x1800290c6  cmp     r9d, eax
0x1800290c9  jle     short loc_1800290B0
0x1800290cb  inc     ebx
0x1800290cd  cmp     ebx, r10d
0x1800290d0  jle     short loc_180029090
0x1800290d2  inc     r15d
0x1800290d5  cmp     r15d, esi
0x1800290d8  jle     short loc_180029070
0x1800290da  mov     [r12+1Ch], r8d
0x1800290df  pop     r15
0x1800290e1  pop     r14
0x1800290e3  pop     r12
0x1800290e5  pop     rdi
0x1800290e6  pop     rsi
0x1800290e7  pop     rbp
0x1800290e8  pop     rbx
0x1800290e9  retn
```
