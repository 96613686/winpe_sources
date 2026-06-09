# UncompressedHash

- ea: `0x1800053ac`
- end: `0x180005689`
- name: `UncompressedHash`
- size: `733`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005250`

## callees

- `0x180005330`
- `0x1800053ac`

## pseudocode

```c
void __fastcall UncompressedHash(int *a1, __int64 a2, unsigned int a3)
{
  int *v3; // r13
  unsigned int v4; // ebp
  __int64 v5; // r15
  int *v6; // r14
  int v7; // edi
  int v8; // r13d
  int v9; // ebx
  int v10; // r12d
  __int64 i; // r14
  __int64 v12; // rax
  int v13; // r13d
  int v14; // r12d
  int v15; // esi
  int v16; // ebx
  __int64 v17; // rax
  int v18; // r13d
  int v19; // r12d
  int v20; // edi
  int v21; // ebx
  __int64 v22; // rax
  int v23; // edi
  __int64 v24; // rax
  int v25; // r12d
  int v26; // edi
  int v27; // ebx
  __int64 v28; // rax
  __int64 v29; // r9
  int v30; // edi
  int v31; // esi
  int v32; // r15d
  int v33; // r12d
  unsigned int j; // r13d
  int v35; // ebx
  __int64 v36; // rax
  int v37; // esi
  __int64 v38; // rax
  int v39; // ebx
  __int64 v40; // rax
  int v41; // ebx
  __int64 v42; // rax
  int v43; // [rsp+20h] [rbp-58h]
  int *v44; // [rsp+28h] [rbp-50h]
  __int64 v46; // [rsp+88h] [rbp+10h]
  unsigned int v47; // [rsp+90h] [rbp+18h]
  int v48; // [rsp+98h] [rbp+20h]

  v47 = a3;
  v46 = a2;
  v3 = a1 + 1;
  v4 = a3;
  v44 = a1 + 1;
  v5 = a2;
  v6 = a1;
  *(_OWORD *)a1 = xmmword_18000B510;
  if ( a3 <= 0x32 )
  {
    v44 = a1 + 1;
  }
  else
  {
    do
    {
      v7 = *v3;
      v8 = v6[2];
      v9 = *v6;
      v10 = v6[3];
      for ( i = 0; i != 48; i += 3 )
      {
        v12 = Mpy32to64(*(unsigned int *)(v5 + 4 * i), *((unsigned int *)qword_18000B520 + i));
        v13 = v12 + v8;
        v14 = HIDWORD(v12) + v10;
        v15 = HIDWORD(v12) - v7 + v9;
        v16 = v12 + HIDWORD(v12) + v9 - 2 * v9;
        v17 = Mpy32to64(*(unsigned int *)(v5 + 4 * i + 4), *((unsigned int *)qword_18000B520 + i + 1));
        v18 = v17 + v13;
        v19 = HIDWORD(v17) + v14;
        v20 = v16 + v17;
        v21 = HIDWORD(v17) + v15 + v16 + 2 * (v16 + v17);
        v22 = Mpy32to64(*(unsigned int *)(v5 + 4 * i + 8), *((unsigned int *)&qword_18000B520[1] + i));
        v23 = v21 + v20;
        v9 = v22 + v21;
        v7 = HIDWORD(v22) + v23;
        v10 = HIDWORD(v22) + v19;
        v8 = v22 + v18;
      }
      v48 = v7;
      v24 = Mpy32to64(*(unsigned int *)(v5 + 192), 3682341274LL);
      v25 = HIDWORD(v24) + v10;
      v43 = v24 + v8;
      v26 = HIDWORD(v24) - v7 + v9;
      v27 = v48 + v24 + v26 - 2 * v9;
      v28 = Mpy32to64(*(unsigned int *)(v5 + 196), 457556239);
      v6 = a1;
      v3 = a1 + 1;
      a1[1] = HIDWORD(v28) + v27 + v26;
      *a1 = v27 + v28;
      a1[3] = HIDWORD(v28) + v25;
      a1[2] = v28 + v43;
      v29 = 0;
      do
      {
        a1[v29] = HIDWORD(qword_18000B520[(int)v29 + 25]) * a1[v29]
                + __ROR4__(LODWORD(qword_18000B520[(int)v29 + 25]) * a1[v29], 16);
        v29 = (unsigned int)(v29 + 1);
      }
      while ( (int)v29 < 4 );
      v4 = v47 - 50;
      v5 += 200;
      v47 = v4;
    }
    while ( v4 > 0x32 );
    v46 = v5;
  }
  v30 = *v3;
  v31 = *v6;
  v32 = v6[3];
  v33 = v6[2];
  if ( v4 )
  {
    for ( j = 0; j < v4; j += 3 )
    {
      v35 = v30;
      v36 = Mpy32to64(*(unsigned int *)(v46 + 4LL * j), *((unsigned int *)qword_18000B520 + j));
      v33 += v36;
      v32 += HIDWORD(v36);
      v30 = HIDWORD(v36) - v30 + v31;
      v37 = v36 - 2 * v31;
      v38 = j + 1;
      v31 = v35 + v37;
      if ( (unsigned int)v38 >= v4 )
        break;
      v39 = v31 + v30;
      v40 = Mpy32to64(*(unsigned int *)(v46 + 4 * v38), *((unsigned int *)qword_18000B520 + v38));
      v33 += v40;
      v30 += HIDWORD(v40) + v31 + v30;
      v32 += HIDWORD(v40);
      v31 = v39 + v40;
      if ( j + 2 >= v4 )
        break;
      v41 = v30 + 2 * v31;
      v42 = Mpy32to64(*(unsigned int *)(v46 + 4LL * (j + 2)), *((unsigned int *)&qword_18000B520[1] + j));
      v30 = HIDWORD(v42) + v41 + v31;
      v32 += HIDWORD(v42);
      v33 += v42;
      v31 = v41 + v42;
    }
    v6 = a1;
    v3 = v44;
  }
  *v3 = v30;
  *v6 = v31;
  v6[3] = v32;
  v6[2] = v33;
}

```

## disassembly

```asm
0x1800053ac  mov     [rsp+arg_10], r8d
0x1800053b1  mov     [rsp+arg_8], rdx
0x1800053b6  mov     [rsp+arg_0], rcx
0x1800053bb  push    rbx
0x1800053bc  push    rbp
0x1800053bd  push    rsi
0x1800053be  push    rdi
0x1800053bf  push    r12
0x1800053c1  push    r13
0x1800053c3  push    r14
0x1800053c5  push    r15
0x1800053c7  sub     rsp, 38h
0x1800053cb  lea     r13, [rcx+4]
0x1800053cf  mov     ebp, r8d
0x1800053d2  mov     [rsp+78h+var_50], r13
0x1800053d7  mov     r15, rdx
0x1800053da  lea     r10, qword_18000B520
0x1800053e1  mov     r14, rcx
0x1800053e4  movups  xmm0, cs:xmmword_18000B510
0x1800053eb  movdqu  xmmword ptr [rcx], xmm0
0x1800053ef  cmp     r8d, 32h ; '2'
0x1800053f3  jbe     loc_180005579
0x1800053f9  mov     edi, [r13+0]
0x1800053fd  lea     rbp, qword_18000B520
0x180005404  mov     r13d, [r14+8]
0x180005408  mov     ebx, [r14]
0x18000540b  mov     r12d, [r14+0Ch]
0x18000540f  xor     r14d, r14d
0x180005412  mov     edx, [rbp+r14*4+0]
0x180005417  mov     ecx, [r15+r14*4]
0x18000541b  call    Mpy32to64
0x180005420  mov     edx, [rbp+r14*4+4]
0x180005425  mov     rcx, rax
0x180005428  shr     rcx, 20h
0x18000542c  add     r13d, eax
0x18000542f  add     r12d, ecx
0x180005432  sub     ecx, edi
0x180005434  lea     esi, [rcx+rbx]
0x180005437  lea     ecx, [rbx+rbx]
0x18000543a  mov     ebx, esi
0x18000543c  sub     ebx, ecx
0x18000543e  mov     ecx, [r15+r14*4+4]
0x180005443  add     ebx, eax
0x180005445  add     ebx, edi
0x180005447  call    Mpy32to64
0x18000544c  mov     edx, [rbp+r14*4+8]
0x180005451  mov     rcx, rax
0x180005454  shr     rcx, 20h
0x180005458  add     r13d, eax
0x18000545b  add     r12d, ecx
0x18000545e  lea     edi, [rbx+rax]
0x180005461  lea     ebx, [rbx+rdi*2]
0x180005464  add     ebx, esi
0x180005466  add     ebx, ecx
0x180005468  mov     ecx, [r15+r14*4+8]
0x18000546d  call    Mpy32to64
0x180005472  add     edi, ebx
0x180005474  mov     rcx, rax
0x180005477  shr     rcx, 20h
0x18000547b  add     ebx, eax
0x18000547d  add     edi, ecx
0x18000547f  add     r12d, ecx
0x180005482  add     r13d, eax
0x180005485  add     r14, 3
0x180005489  cmp     r14, 30h ; '0'
0x18000548d  jnz     short loc_180005412
0x18000548f  mov     ecx, [r15+0C0h]
0x180005496  mov     edx, 0DB7C119Ah
0x18000549b  mov     [rsp+78h+arg_18], edi
0x1800054a2  call    Mpy32to64
0x1800054a7  mov     rcx, rax
0x1800054aa  add     r13d, eax
0x1800054ad  shr     rcx, 20h
0x1800054b1  mov     edx, 1B45C10Fh
0x1800054b6  add     r12d, ecx
0x1800054b9  mov     [rsp+78h+var_58], r13d
0x1800054be  sub     ecx, edi
0x1800054c0  lea     edi, [rcx+rbx]
0x1800054c3  lea     ecx, [rbx+rbx]
0x1800054c6  mov     ebx, edi
0x1800054c8  sub     ebx, ecx
0x1800054ca  mov     ecx, [r15+0C4h]
0x1800054d1  add     ebx, eax
0x1800054d3  add     ebx, [rsp+78h+arg_18]
0x1800054da  call    Mpy32to64
0x1800054df  mov     r14, [rsp+78h+arg_0]
0x1800054e7  lea     ecx, [rbx+rdi]
0x1800054ea  mov     ebp, [rsp+78h+arg_10]
0x1800054f1  lea     r10, qword_18000B520
0x1800054f8  mov     rdx, rax
0x1800054fb  shr     rdx, 20h
0x1800054ff  add     ecx, edx
0x180005501  lea     r13, [r14+4]
0x180005505  mov     [r13+0], ecx
0x180005509  lea     ecx, [rbx+rax]
0x18000550c  mov     [r14], ecx
0x18000550f  lea     ecx, [rdx+r12]
0x180005513  mov     [r14+0Ch], ecx
0x180005517  mov     ecx, [rsp+78h+var_58]
0x18000551b  add     ecx, eax
0x18000551d  mov     [r14+8], ecx
0x180005521  xor     r9d, r9d
0x180005524  mov     edx, [r14+r9*4]
0x180005528  lea     eax, [r9+r9]
0x18000552c  movsxd  rcx, eax
0x18000552f  mov     eax, edx
0x180005531  imul    eax, [r10+rcx*4+0C8h]
0x18000553a  imul    edx, [r10+rcx*4+0CCh]
0x180005543  ror     eax, 10h
0x180005546  add     eax, edx
0x180005548  mov     [r14+r9*4], eax
0x18000554c  inc     r9d
0x18000554f  cmp     r9d, 4
0x180005553  jl      short loc_180005524
0x180005555  add     ebp, 0FFFFFFCEh
0x180005558  add     r15, 0C8h
0x18000555f  mov     [rsp+78h+arg_10], ebp
0x180005566  cmp     ebp, 32h ; '2'
0x180005569  ja      loc_1800053F9
0x18000556f  mov     [rsp+78h+arg_8], r15
0x180005577  jmp     short loc_18000557E
0x180005579  mov     [rsp+78h+var_50], r13
0x18000557e  mov     edi, [r13+0]
0x180005582  mov     esi, [r14]
0x180005585  mov     r15d, [r14+0Ch]
0x180005589  mov     r12d, [r14+8]
0x18000558d  mov     [rsp+78h+arg_10], 0
0x180005598  test    ebp, ebp
0x18000559a  jz      loc_180005668
0x1800055a0  mov     r14, [rsp+78h+arg_8]
0x1800055a8  mov     r13d, [rsp+78h+arg_10]
0x1800055b0  mov     ecx, r13d
0x1800055b3  mov     ebx, edi
0x1800055b5  mov     edx, [r10+rcx*4]
0x1800055b9  mov     ecx, [r14+rcx*4]
0x1800055bd  call    Mpy32to64
0x1800055c2  mov     r8, rax
0x1800055c5  add     r12d, eax
0x1800055c8  shr     r8, 20h
0x1800055cc  mov     ecx, r8d
0x1800055cf  add     r15d, r8d
0x1800055d2  sub     ecx, edi
0x1800055d4  lea     edi, [rcx+rsi]
0x1800055d7  lea     ecx, [rsi+rsi]
0x1800055da  mov     esi, eax
0x1800055dc  sub     esi, ecx
0x1800055de  lea     eax, [r13+1]
0x1800055e2  add     esi, ebx
0x1800055e4  cmp     eax, ebp
0x1800055e6  jnb     short loc_18000565B
0x1800055e8  mov     ecx, [r14+rax*4]
0x1800055ec  lea     rdx, qword_18000B520
0x1800055f3  mov     edx, [rdx+rax*4]
0x1800055f6  lea     ebx, [rsi+rdi]
0x1800055f9  call    Mpy32to64
0x1800055fe  mov     rdx, rax
0x180005601  add     edi, ebx
0x180005603  shr     rdx, 20h
0x180005607  add     r12d, eax
0x18000560a  add     edi, edx
0x18000560c  add     r15d, edx
0x18000560f  lea     esi, [rbx+rax]
0x180005612  lea     eax, [r13+2]
0x180005616  cmp     eax, ebp
0x180005618  jnb     short loc_18000565B
0x18000561a  mov     ecx, eax
0x18000561c  lea     ebx, [rdi+rsi*2]
0x18000561f  lea     rax, qword_18000B520
0x180005626  mov     edx, [rax+rcx*4]
0x180005629  mov     ecx, [r14+rcx*4]
0x18000562d  call    Mpy32to64
0x180005632  lea     edi, [rbx+rsi]
0x180005635  mov     rcx, rax
0x180005638  shr     rcx, 20h
0x18000563c  lea     r10, qword_18000B520
0x180005643  add     edi, ecx
0x180005645  add     r15d, ecx
0x180005648  add     r12d, eax
0x18000564b  lea     esi, [rbx+rax]
0x18000564e  add     r13d, 3
0x180005652  cmp     r13d, ebp
0x180005655  jb      loc_1800055B0
0x18000565b  mov     r14, [rsp+78h+arg_0]
0x180005663  mov     r13, [rsp+78h+var_50]
0x180005668  mov     [r13+0], edi
0x18000566c  mov     [r14], esi
0x18000566f  mov     [r14+0Ch], r15d
0x180005673  mov     [r14+8], r12d
0x180005677  add     rsp, 38h
0x18000567b  pop     r15
0x18000567d  pop     r14
0x18000567f  pop     r13
0x180005681  pop     r12
0x180005683  pop     rdi
0x180005684  pop     rsi
0x180005685  pop     rbp
0x180005686  pop     rbx
0x180005687  retn
```
