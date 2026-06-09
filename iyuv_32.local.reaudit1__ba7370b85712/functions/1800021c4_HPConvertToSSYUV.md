# HPConvertToSSYUV

- ea: `0x1800021c4`
- end: `0x1800024dd`
- name: `HPConvertToSSYUV`
- size: `793`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001c98`

## callees

- `0x1800021c4`

## pseudocode

```c
__int64 __fastcall HPConvertToSSYUV(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned __int8 v3; // r9
  _QWORD *v5; // r10
  _BYTE *v6; // r15
  int v7; // ebp
  int v8; // ebx
  _BYTE *v9; // r11
  __int64 result; // rax
  unsigned __int16 v11; // cx
  int v12; // edi
  int v13; // r14d
  int v14; // esi
  unsigned __int8 *v15; // r8
  __int64 v16; // rax
  unsigned int v17; // ecx
  int i; // edi
  int v19; // r14d
  unsigned __int8 *v20; // rsi
  unsigned __int8 v21; // dl
  unsigned int v22; // r8d
  unsigned int v23; // edx
  int v24; // edi
  int v25; // r10d
  int v26; // r13d
  unsigned __int8 *v27; // rsi
  __int64 v28; // r8
  unsigned int v29; // ecx
  _BYTE *v30; // r15
  _BYTE *v31; // r12
  __int64 v32; // rsi
  int v33; // r10d
  int v34; // r14d
  int v35; // r11d
  int v36; // edi
  int v37; // r8d
  int v38; // r9d
  int v40; // [rsp+38h] [rbp+8h]
  int v41; // [rsp+40h] [rbp+10h]

  v3 = *(_BYTE *)(a1 + 10);
  v5 = (_QWORD *)a1;
  if ( !v3 )
  {
    v3 = *(_BYTE *)(a2 + 14);
    *(_BYTE *)(a1 + 10) = v3;
  }
  v6 = *(_BYTE **)(a1 + 48);
  v7 = *(unsigned __int16 *)(a1 + 8);
  v8 = *(unsigned __int16 *)(a1 + 6);
  v9 = *(_BYTE **)(a1 + 72);
  result = v3;
  v41 = v7;
  v11 = 4 * ((v3 * (unsigned int)*(unsigned __int16 *)(a1 + 4) + 31) >> 5);
  if ( v3 == 8 )
  {
    v24 = v7 - 1;
    if ( v7 - 1 >= 0 )
    {
      v25 = v11;
      do
      {
        v26 = 0;
        result = 0;
        v27 = (unsigned __int8 *)(a3 + (unsigned int)(v24 * v25));
        if ( (_WORD)v8 )
        {
          do
          {
            v28 = *v27;
            ++v26;
            ++v27;
            v29 = GtoYUV[*(unsigned __int8 *)(a2 + 4 * v28 + 41)]
                + RtoYUV[*(unsigned __int8 *)(a2 + 4 * v28 + 42)]
                + BtoYUV[*(unsigned __int8 *)(a2 + 4 * v28 + 40)];
            *v9 = v29;
            result = v29 >> 8;
            v9[1] = BYTE1(v29);
            v9 += 2;
            *v6++ = BYTE2(v29);
          }
          while ( v26 < v8 );
        }
        --v24;
      }
      while ( v24 >= 0 );
      v5 = (_QWORD *)a1;
    }
  }
  else if ( v3 == 16 )
  {
    for ( i = v7 - 1; i >= 0; --i )
    {
      v19 = 0;
      result = 0;
      v20 = (unsigned __int8 *)(a3 + i * (unsigned int)v11);
      if ( (_WORD)v8 )
      {
        do
        {
          v21 = v20[1];
          ++v19;
          v22 = *v20;
          v20 += 2;
          v23 = RtoYUV[2 * (v21 & 0x7C)]
              + GtoYUV[8 * (((unsigned __int64)v22 >> 5) | (8LL * (v21 & 3)))]
              + BtoYUV[8 * (v22 & 0x1F)];
          *v9 = v23;
          result = v23 >> 8;
          v9[1] = BYTE1(v23);
          v9 += 2;
          *v6++ = BYTE2(v23);
        }
        while ( v19 < v8 );
      }
    }
  }
  else if ( ((v3 - 24) & 0xF7) == 0 )
  {
    v12 = v7 - 1;
    if ( v7 - 1 >= 0 )
    {
      v13 = v11;
      do
      {
        v14 = 0;
        v15 = (unsigned __int8 *)(a3 + (unsigned int)(v12 * v13));
        if ( v8 )
        {
          do
          {
            v16 = *v15;
            ++v14;
            v15 += 3;
            v17 = BtoYUV[v16] + GtoYUV[*(v15 - 2)] + RtoYUV[*(v15 - 1)];
            *v9 = v17;
            result = v17 >> 8;
            v9[1] = BYTE1(v17);
            v9 += 2;
            *v6++ = BYTE2(v17);
          }
          while ( v14 < v8 );
        }
        --v12;
      }
      while ( v12 >= 0 );
    }
  }
  v30 = (_BYTE *)v5[7];
  v31 = (_BYTE *)v5[8];
  v32 = v5[9];
  v33 = 0;
  v40 = 0;
  if ( v7 )
  {
    do
    {
      v34 = 0;
      result = 0;
      if ( (_WORD)v8 )
      {
        v35 = 2 * v8 * (v33 + 1);
        v36 = 2 * v8 * v33;
        v37 = v36 + 1;
        do
        {
          v38 = 2 * v34;
          v34 += 2;
          result = (*(unsigned __int8 *)((unsigned int)(v36 + 3 + v38) + v32)
                  + *(unsigned __int8 *)((unsigned int)(v38 + v35 + 3) + v32)
                  + *(unsigned __int8 *)((unsigned int)(v38 + v35 + 1) + v32)
                  + (unsigned int)*(unsigned __int8 *)((unsigned int)(v37 + v38) + v32)
                  + 2) >> 2;
          v37 = v36 + 1;
          *v31++ = (*(unsigned __int8 *)((unsigned int)(v38 + v35 + 2) + v32)
                  + *(unsigned __int8 *)((unsigned int)(v35 + v38) + v32)
                  + *(unsigned __int8 *)((unsigned int)(v38 + v36 + 2) + v32)
                  + 2
                  + (unsigned int)*(unsigned __int8 *)((unsigned int)(v36 + v38) + v32)) >> 2;
          *v30++ = result;
        }
        while ( v34 < v8 );
        v33 = v40;
        v7 = v41;
      }
      v33 += 2;
      v40 = v33;
    }
    while ( v33 < v7 );
  }
  return result;
}

```

## disassembly

```asm
0x1800021c4  mov     [rsp+arg_10], rbx
0x1800021c9  mov     [rsp+arg_18], rbp
0x1800021ce  mov     [rsp+arg_0], rcx
0x1800021d3  push    rsi
0x1800021d4  push    rdi
0x1800021d5  push    r12
0x1800021d7  push    r13
0x1800021d9  push    r14
0x1800021db  push    r15
0x1800021dd  mov     r9b, [rcx+0Ah]
0x1800021e1  mov     r12, r8
0x1800021e4  mov     r10, rcx
0x1800021e7  test    r9b, r9b
0x1800021ea  jnz     short loc_1800021F4
0x1800021ec  mov     r9b, [rdx+0Eh]
0x1800021f0  mov     [rcx+0Ah], r9b
0x1800021f4  mov     r15, [rcx+30h]
0x1800021f8  movzx   ecx, word ptr [rcx+4]
0x1800021fc  movzx   ebp, word ptr [r10+8]
0x180002201  movzx   ebx, word ptr [r10+6]
0x180002206  mov     r11, [r10+48h]
0x18000220a  movzx   eax, r9b
0x18000220e  imul    ecx, eax
0x180002211  mov     [rsp+30h+arg_8], ebp
0x180002215  add     ecx, 1Fh
0x180002218  shr     ecx, 5
0x18000221b  shl     cx, 2
0x18000221f  cmp     r9b, 8
0x180002223  jz      loc_18000235E
0x180002229  cmp     r9b, 10h
0x18000222d  jz      loc_1800022BE
0x180002233  sub     r9b, 18h
0x180002237  test    r9b, 0F7h
0x18000223b  jnz     loc_1800023DF
0x180002241  lea     edi, [rbp-1]
0x180002244  test    edi, edi
0x180002246  js      loc_1800023DF
0x18000224c  movzx   r14d, cx
0x180002250  lea     r9, cs:180000000h
0x180002257  mov     r8d, r14d
0x18000225a  xor     esi, esi
0x18000225c  imul    r8d, edi
0x180002260  add     r8, r12
0x180002263  test    ebx, ebx
0x180002265  jz      short loc_1800022B4
0x180002267  movzx   eax, byte ptr [r8]
0x18000226b  inc     esi
0x18000226d  lea     r8, [r8+3]
0x180002271  mov     ecx, ds:rva BtoYUV[r9+rax*4]
0x180002279  movzx   eax, byte ptr [r8-2]
0x18000227e  mov     edx, ds:rva GtoYUV[r9+rax*4]
0x180002286  movzx   eax, byte ptr [r8-1]
0x18000228b  add     edx, ecx
0x18000228d  mov     ecx, ds:rva RtoYUV[r9+rax*4]
0x180002295  add     ecx, edx
0x180002297  mov     [r11], cl
0x18000229a  mov     eax, ecx
0x18000229c  shr     eax, 8
0x18000229f  shr     ecx, 10h
0x1800022a2  mov     [r11+1], al
0x1800022a6  add     r11, 2
0x1800022aa  mov     [r15], cl
0x1800022ad  inc     r15
0x1800022b0  cmp     esi, ebx
0x1800022b2  jl      short loc_180002267
0x1800022b4  sub     edi, 1
0x1800022b7  jns     short loc_180002257
0x1800022b9  jmp     loc_1800023DF
0x1800022be  lea     edi, [rbp-1]
0x1800022c1  test    edi, edi
0x1800022c3  js      loc_1800023DF
0x1800022c9  movzx   r13d, cx
0x1800022cd  lea     r9, cs:180000000h
0x1800022d4  mov     esi, r13d
0x1800022d7  xor     r14d, r14d
0x1800022da  imul    esi, edi
0x1800022dd  xor     eax, eax
0x1800022df  add     rsi, r12
0x1800022e2  cmp     ax, bx
0x1800022e5  jnb     short loc_180002350
0x1800022e7  movzx   edx, byte ptr [rsi+1]
0x1800022eb  inc     r14d
0x1800022ee  movzx   r8d, byte ptr [rsi]
0x1800022f2  mov     ecx, edx
0x1800022f4  and     ecx, 3
0x1800022f7  lea     rsi, [rsi+2]
0x1800022fb  shl     rcx, 3
0x1800022ff  and     edx, 7Ch
0x180002302  mov     eax, r8d
0x180002305  and     r8d, 1Fh
0x180002309  shr     rax, 5
0x18000230d  or      rcx, rax
0x180002310  shl     r8, 5
0x180002314  shl     rcx, 5
0x180002318  mov     ecx, [rcx+r9+0B3E0h]
0x180002320  add     ecx, ds:rva RtoYUV[r9+rdx*8]
0x180002328  mov     edx, [r8+r9+0ABE0h]
0x180002330  add     edx, ecx
0x180002332  mov     [r11], dl
0x180002335  mov     eax, edx
0x180002337  shr     eax, 8
0x18000233a  shr     edx, 10h
0x18000233d  mov     [r11+1], al
0x180002341  add     r11, 2
0x180002345  mov     [r15], dl
0x180002348  inc     r15
0x18000234b  cmp     r14d, ebx
0x18000234e  jl      short loc_1800022E7
0x180002350  sub     edi, 1
0x180002353  jns     loc_1800022D4
0x180002359  jmp     loc_1800023DF
0x18000235e  lea     edi, [rbp-1]
0x180002361  test    edi, edi
0x180002363  js      short loc_1800023DF
0x180002365  movzx   r10d, cx
0x180002369  lea     r9, cs:180000000h
0x180002370  mov     esi, r10d
0x180002373  xor     r13d, r13d
0x180002376  imul    esi, edi
0x180002379  xor     eax, eax
0x18000237b  add     rsi, r12
0x18000237e  cmp     ax, bx
0x180002381  jnb     short loc_1800023D5
0x180002383  movzx   r8d, byte ptr [rsi]
0x180002387  inc     r13d
0x18000238a  inc     rsi
0x18000238d  movzx   eax, byte ptr [rdx+r8*4+2Ah]
0x180002393  movzx   ecx, byte ptr [rdx+r8*4+28h]
0x180002399  mov     ecx, ds:rva BtoYUV[r9+rcx*4]
0x1800023a1  add     ecx, ds:rva RtoYUV[r9+rax*4]
0x1800023a9  movzx   eax, byte ptr [rdx+r8*4+29h]
0x1800023af  add     ecx, ds:rva GtoYUV[r9+rax*4]
0x1800023b7  mov     [r11], cl
0x1800023ba  mov     eax, ecx
0x1800023bc  shr     eax, 8
0x1800023bf  shr     ecx, 10h
0x1800023c2  mov     [r11+1], al
0x1800023c6  add     r11, 2
0x1800023ca  mov     [r15], cl
0x1800023cd  inc     r15
0x1800023d0  cmp     r13d, ebx
0x1800023d3  jl      short loc_180002383
0x1800023d5  sub     edi, 1
0x1800023d8  jns     short loc_180002370
0x1800023da  mov     r10, [rsp+30h+arg_0]
0x1800023df  mov     r15, [r10+38h]
0x1800023e3  mov     r12, [r10+40h]
0x1800023e7  mov     rsi, [r10+48h]
0x1800023eb  xor     r10d, r10d
0x1800023ee  mov     dword ptr [rsp+30h+arg_0], r10d
0x1800023f3  test    ebp, ebp
0x1800023f5  jz      loc_1800024C8
0x1800023fb  xor     r14d, r14d
0x1800023fe  xor     eax, eax
0x180002400  cmp     ax, bx
0x180002403  jnb     loc_1800024B6
0x180002409  lea     eax, [r10+1]
0x18000240d  imul    eax, ebx
0x180002410  lea     r11d, [rax+rax]
0x180002414  mov     eax, r10d
0x180002417  imul    eax, ebx
0x18000241a  lea     r13d, [r11+3]
0x18000241e  lea     ebp, [r11+1]
0x180002422  lea     edi, [rax+rax]
0x180002425  lea     r10d, [rdi+3]
0x180002429  lea     r8d, [rdi+1]
0x18000242d  lea     r9d, [r14+r14]
0x180002431  add     r14d, 2
0x180002435  lea     eax, [r9+rbp]
0x180002439  movzx   edx, byte ptr [rax+rsi]
0x18000243d  lea     eax, [r8+r9]
0x180002441  movzx   r8d, byte ptr [rax+rsi]
0x180002446  lea     eax, [r9+r13]
0x18000244a  movzx   eax, byte ptr [rax+rsi]
0x18000244e  add     r8d, edx
0x180002451  add     r8d, eax
0x180002454  lea     eax, [r10+r9]
0x180002458  movzx   eax, byte ptr [rax+rsi]
0x18000245c  add     r8d, eax
0x18000245f  lea     eax, [rdi+2]
0x180002462  add     eax, r9d
0x180002465  movzx   edx, byte ptr [rax+rsi]
0x180002469  lea     eax, [r11+r9]
0x18000246d  movzx   eax, byte ptr [rax+rsi]
0x180002471  add     edx, eax
0x180002473  lea     eax, [r11+2]
0x180002477  add     eax, r9d
0x18000247a  movzx   eax, byte ptr [rax+rsi]
0x18000247e  add     edx, eax
0x180002480  lea     eax, [rdi+r9]
0x180002484  add     edx, 2
0x180002487  movzx   ecx, byte ptr [rax+rsi]
0x18000248b  lea     eax, [r8+2]
0x18000248f  add     ecx, edx
0x180002491  shr     eax, 2
0x180002494  shr     ecx, 2
0x180002497  lea     r8d, [rdi+1]
0x18000249b  mov     [r12], cl
0x18000249f  inc     r12
0x1800024a2  mov     [r15], al
0x1800024a5  inc     r15
0x1800024a8  cmp     r14d, ebx
0x1800024ab  jl      short loc_18000242D
0x1800024ad  mov     r10d, dword ptr [rsp+30h+arg_0]
0x1800024b2  mov     ebp, [rsp+30h+arg_8]
0x1800024b6  add     r10d, 2
0x1800024ba  mov     dword ptr [rsp+30h+arg_0], r10d
0x1800024bf  cmp     r10d, ebp
0x1800024c2  jl      loc_1800023FB
0x1800024c8  mov     rbx, [rsp+30h+arg_10]
0x1800024cd  mov     rbp, [rsp+30h+arg_18]
0x1800024d2  pop     r15
0x1800024d4  pop     r14
0x1800024d6  pop     r13
0x1800024d8  pop     r12
0x1800024da  pop     rdi
0x1800024db  pop     rsi
0x1800024dc  retn
```
