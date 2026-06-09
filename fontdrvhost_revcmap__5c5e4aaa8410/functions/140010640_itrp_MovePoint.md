# itrp_MovePoint

- ea: `0x140010640`
- end: `0x1400107b3`
- name: `itrp_MovePoint`
- size: `371`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000ff80`
- `0x140010640`

## pseudocode

```c
__int64 __fastcall itrp_MovePoint(__int16 *a1, _QWORD *a2, int a3, int a4)
{
  __int64 v4; // rdi
  __int64 result; // rax
  __int64 v6; // r11
  __int64 v8; // rsi
  unsigned __int64 v9; // r11
  __int64 v10; // rcx
  unsigned __int64 v11; // rdx
  __int64 v12; // rax
  __int64 v13; // r11
  __int64 v14; // rax
  __int64 v15; // r11
  int *v16; // r14
  int v17; // r12d
  int v18; // eax

  v4 = a1[49];
  result = 0x4000;
  v6 = a1[14];
  v8 = a1[15];
  if ( (_WORD)v4 == 0x4000 )
  {
    if ( (_WORD)v6 )
    {
      *(_DWORD *)(*a2 + 4LL * a3) += (((a4 * v6) >> 13) + 1) >> 1;
      result = a2[9];
      *(_BYTE *)(a3 + result) |= 1u;
    }
    if ( (_WORD)v8 )
    {
      *(_DWORD *)(a2[1] + 4LL * a3) += (((a4 * v8) >> 13) + 1) >> 1;
      result = a2[9];
      *(_BYTE *)(a3 + result) |= 2u;
    }
  }
  else
  {
    if ( (_WORD)v6 )
    {
      if ( (_WORD)v4 == (_WORD)v6 )
      {
        *(_DWORD *)(*a2 + 4LL * a3) += a4;
      }
      else
      {
        v9 = a4 * v6;
        v10 = (int)v4 / 2;
        v11 = v9 >> 63;
        v12 = v10 + v9;
        v13 = v9 - v10;
        if ( (int)v4 < 0 == (_BYTE)v11 )
          v13 = v12;
        if ( (_WORD)v4 )
          v14 = v13 / v4;
        else
          LODWORD(v14) = (v13 < 0) + 0x7FFFFFFF;
        *(_DWORD *)(*a2 + 4LL * a3) += v14;
      }
      result = a2[9];
      v15 = a3;
      *(_BYTE *)(a3 + result) |= 1u;
    }
    else
    {
      v15 = a3;
    }
    if ( (_WORD)v8 )
    {
      v16 = (int *)(a2[1] + 4 * v15);
      v17 = *v16;
      if ( (_WORD)v4 == (_WORD)v8 )
        v18 = v17 + a4;
      else
        v18 = v17 + CompDiv(v4, a4 * v8);
      *v16 = v18;
      result = a2[9];
      *(_BYTE *)(v15 + result) |= 2u;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140010640  push    rbx
0x140010642  push    rbp
0x140010643  push    rsi
0x140010644  push    rdi
0x140010645  push    r12
0x140010647  push    r14
0x140010649  push    r15
0x14001064b  sub     rsp, 20h
0x14001064f  movsx   rdi, word ptr [rcx+62h]
0x140010654  mov     eax, 4000h
0x140010659  movsx   r11, word ptr [rcx+1Ch]
0x14001065e  mov     rbx, rdx
0x140010661  movsx   rsi, word ptr [rcx+1Eh]
0x140010666  movsxd  rbp, r8d
0x140010669  cmp     di, ax
0x14001066c  jz      loc_1400106F2
0x140010672  xor     r10d, r10d
0x140010675  mov     r15d, 2
0x14001067b  test    r11w, r11w
0x14001067f  jz      loc_140010785
0x140010685  cmp     di, r11w
0x140010689  jz      loc_140010793
0x14001068f  movsxd  rax, r9d
0x140010692  mov     r8d, edi
0x140010695  imul    r11, rax
0x140010699  mov     eax, edi
0x14001069b  shr     r8d, 1Fh
0x14001069f  cdq
0x1400106a0  idiv    r15d
0x1400106a3  mov     rdx, r11
0x1400106a6  movsxd  rcx, eax
0x1400106a9  shr     rdx, 3Fh
0x1400106ad  lea     rax, [rcx+r11]
0x1400106b1  sub     r11, rcx
0x1400106b4  cmp     r8b, dl
0x1400106b7  cmovz   r11, rax
0x1400106bb  test    di, di
0x1400106be  jz      loc_14001079F
0x1400106c4  mov     rax, r11
0x1400106c7  cqo
0x1400106c9  idiv    rdi
0x1400106cc  mov     rcx, [rbx]
0x1400106cf  add     [rcx+rbp*4], eax
0x1400106d2  mov     rax, [rbx+48h]
0x1400106d6  mov     r11, rbp
0x1400106d9  or      byte ptr [rbp+rax+0], 1
0x1400106de  test    si, si
0x1400106e1  jnz     short loc_140010751
0x1400106e3  add     rsp, 20h
0x1400106e7  pop     r15
0x1400106e9  pop     r14
0x1400106eb  pop     r12
0x1400106ed  pop     rdi
0x1400106ee  pop     rsi
0x1400106ef  pop     rbp
0x1400106f0  pop     rbx
0x1400106f1  retn
0x1400106f2  movsxd  rdi, r9d
0x1400106f5  lea     rdx, ds:0[rbp*4]
0x1400106fd  test    r11w, r11w
0x140010701  jz      short loc_140010723
0x140010703  mov     rcx, [rbx]
0x140010706  mov     rax, r11
0x140010709  imul    rax, rdi
0x14001070d  sar     rax, 0Dh
0x140010711  inc     rax
0x140010714  sar     rax, 1
0x140010717  add     [rcx+rdx], eax
0x14001071a  mov     rax, [rbx+48h]
0x14001071e  or      byte ptr [rbp+rax+0], 1
0x140010723  test    si, si
0x140010726  jz      short loc_1400106E3
0x140010728  mov     rcx, [rbx+8]
0x14001072c  mov     rax, rsi
0x14001072f  imul    rax, rdi
0x140010733  mov     r15d, 2
0x140010739  sar     rax, 0Dh
0x14001073d  inc     rax
0x140010740  sar     rax, 1
0x140010743  add     [rcx+rdx], eax
0x140010746  mov     rax, [rbx+48h]
0x14001074a  or      [rbp+rax+0], r15b
0x14001074f  jmp     short loc_1400106E3
0x140010751  mov     rax, [rbx+8]
0x140010755  lea     r14, [rax+r11*4]
0x140010759  mov     r12d, [r14]
0x14001075c  cmp     di, si
0x14001075f  jz      short loc_14001078D
0x140010761  movsxd  rax, r9d
0x140010764  mov     rdx, rsi
0x140010767  imul    rdx, rax
0x14001076b  mov     ecx, edi
0x14001076d  call    CompDiv
0x140010772  add     eax, r12d
0x140010775  mov     [r14], eax
0x140010778  mov     rax, [rbx+48h]
0x14001077c  or      [r11+rax], r15b
0x140010780  jmp     loc_1400106E3
0x140010785  mov     r11, rbp
0x140010788  jmp     loc_1400106DE
0x14001078d  lea     eax, [r12+r9]
0x140010791  jmp     short loc_140010775
0x140010793  mov     rax, [rdx]
0x140010796  add     [rax+rbp*4], r9d
0x14001079a  jmp     loc_1400106D2
0x14001079f  test    r11, r11
0x1400107a2  mov     rax, r10
0x1400107a5  sets    al
0x1400107a8  add     rax, 7FFFFFFFh
0x1400107ae  jmp     loc_1400106CC
```
