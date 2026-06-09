# DecompressCBlockToRGBTRIPLE

- ea: `0x180005184`
- end: `0x1800054e1`
- name: `DecompressCBlockToRGBTRIPLE`
- size: `861`
- prototype: `__int16 *__fastcall(__int64, __int16 *, unsigned int *, int, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800059d0`

## callees

- `0x180005184`

## pseudocode

```c
__int16 *__fastcall DecompressCBlockToRGBTRIPLE(__int64 a1, __int16 *a2, unsigned int *a3, int a4, int *a5)
{
  __int64 v5; // rdi
  unsigned int *v6; // rbx
  __int64 v7; // r11
  unsigned int v8; // eax
  unsigned __int16 v9; // si
  int v10; // r9d
  __int16 *v11; // r8
  int v13; // ebx
  char v14; // dl
  char v15; // r10
  char v16; // r9
  __int64 k; // rax
  __int64 v18; // rcx
  unsigned __int16 v19; // r8
  __int16 v20; // bp
  __int64 v21; // r14
  unsigned int v22; // r8d
  unsigned __int16 v23; // r10
  __int16 v24; // ax
  __int16 v25; // si
  char v26; // r10
  unsigned __int16 v27; // cx
  __int64 *v28; // rdx
  __int64 v29; // r12
  __int16 v30; // di
  __int16 v31; // r14
  char v32; // cl
  __int64 i; // r8
  unsigned __int16 v34; // ax
  char v35; // r13
  char v36; // al
  char v37; // bp
  __int64 v38; // r13
  bool v39; // zf
  __int16 v40; // r14
  __int16 v41; // r15
  char v42; // r8
  unsigned __int16 v43; // cx
  __int16 v44; // r13
  __int64 v45; // rdx
  char v46; // cl
  __int64 j; // rax
  __int64 v48; // rdi
  char v49; // r12
  char v50; // r9
  char v51; // r10
  int v52; // [rsp+4h] [rbp-64h]
  int v53; // [rsp+8h] [rbp-60h]
  int v54; // [rsp+Ch] [rbp-5Ch]
  int v55; // [rsp+Ch] [rbp-5Ch]
  __int64 *v56; // [rsp+10h] [rbp-58h]
  __int64 v57; // [rsp+18h] [rbp-50h]
  __int64 v58; // [rsp+20h] [rbp-48h]
  __int64 v59; // [rsp+28h] [rbp-40h]
  __int64 v60; // [rsp+70h] [rbp+8h]
  __int16 *v61; // [rsp+78h] [rbp+10h]
  __int16 *v62; // [rsp+78h] [rbp+10h]
  char v64; // [rsp+90h] [rbp+28h]
  __int16 v65; // [rsp+90h] [rbp+28h]

  v61 = a2;
  v60 = a1;
  v5 = a4;
  v6 = a3;
  v7 = a1;
  if ( *a5 > 0 )
  {
    --*a5;
    return a2;
  }
  v8 = *a3;
  if ( *a3 <= 1 )
  {
    v9 = 0;
    goto LABEL_16;
  }
  v10 = (unsigned __int16)*a2;
  v11 = a2 + 1;
  v8 -= 2;
  *v6 = v8;
  if ( (v10 & 0x8000u) == 0 )
  {
    if ( v8 > 1 )
    {
      if ( *v11 < 0 )
      {
        v58 = v5;
        v56 = qword_18000B0A0;
        ++a2;
        v54 = 2;
        v59 = 2 * (int)v5;
        v62 = v11;
        do
        {
          v21 = v7;
          v57 = v7;
          v53 = 2;
          do
          {
            v22 = *v6;
            if ( *v6 > 1 )
            {
              v23 = *a2++;
              v22 -= 2;
              v62 = a2;
              *v6 = v22;
            }
            else
            {
              v23 = 0;
            }
            v24 = v23 >> 7;
            v25 = v23 >> 2;
            v26 = 8 * v23;
            v64 = v24;
            if ( v22 > 1 )
            {
              v27 = *a2;
              *v6 = v22 - 2;
              v62 = a2 + 1;
            }
            else
            {
              v27 = 0;
            }
            v28 = v56;
            v29 = v21;
            v30 = v27 >> 7;
            v31 = v27 >> 2;
            v32 = 8 * v27;
            v52 = 2;
            do
            {
              for ( i = 0; i != 2; ++i )
              {
                v34 = *(_WORD *)v28;
                v28 = (__int64 *)((char *)v28 + 2);
                if ( (v34 & (unsigned __int16)v10) != 0 )
                {
                  v35 = v26;
                  v36 = v64;
                  v37 = v25;
                }
                else
                {
                  v35 = v32;
                  v36 = v30;
                  v37 = v31;
                }
                *(_BYTE *)(i + v29 + 2 * i) = v35;
                v38 = v29 + 2 * i;
                *(_BYTE *)(i + v38 + 1) = v37 & 0xF8;
                *(_BYTE *)(i + v38 + 2) = v36 & 0xF8;
              }
              v29 += v58;
              v39 = v52-- == 1;
              v56 = v28;
            }
            while ( !v39 );
            a2 = v62;
            v21 = v57 + 6;
            v39 = v53-- == 1;
            v6 = a3;
            v57 += 6;
          }
          while ( !v39 );
          v7 = v59 + v60;
          v39 = v54-- == 1;
          v60 += v59;
        }
        while ( !v39 );
        return a2;
      }
      a2 += 2;
      v8 -= 2;
      v19 = *v11;
      v20 = 1;
      v61 = a2;
      v9 = v10;
      *v6 = v8;
      goto LABEL_37;
    }
    ++a2;
    v9 = v10;
    v61 = v11;
LABEL_16:
    v19 = 0;
    v20 = 1;
LABEL_37:
    v40 = v19 >> 7;
    v41 = v19 >> 2;
    v42 = 8 * v19;
    if ( v8 > 1 )
    {
      v43 = *a2;
      v61 = a2 + 1;
      *v6 = v8 - 2;
    }
    else
    {
      v43 = 0;
    }
    v55 = 4;
    v44 = v43 >> 7;
    v45 = v5;
    v65 = v43 >> 2;
    v46 = 8 * v43;
    do
    {
      for ( j = 0; j != 4; ++j )
      {
        v48 = v7 + 2 * j;
        if ( (v9 & (unsigned __int16)v20) != 0 )
        {
          v49 = v42;
          v50 = v40;
          v51 = v41;
        }
        else
        {
          v49 = v46;
          v50 = v44;
          v51 = v65;
        }
        *(_BYTE *)(j + v48) = v49;
        *(_BYTE *)(j + v48 + 1) = v51 & 0xF8;
        *(_BYTE *)(j + v48 + 2) = v50 & 0xF8;
        v20 *= 2;
      }
      v7 += v45;
      --v55;
    }
    while ( v55 );
    return v61;
  }
  if ( (v10 & 0xFFFFFC00) == 0x8400 )
  {
    *a5 = (v10 & 0x3FF) - 1;
  }
  else
  {
    v13 = 4;
    v14 = ((unsigned __int16)v10 >> 7) & 0xF8;
    v15 = ((unsigned __int16)v10 >> 2) & 0xF8;
    v16 = 8 * v10;
    do
    {
      for ( k = 0; k != 4; ++k )
      {
        v18 = v7 + 2 * k;
        *(_BYTE *)(k + v18) = v16;
        *(_BYTE *)(k + v18 + 1) = v15;
        *(_BYTE *)(k + v18 + 2) = v14;
      }
      v7 += v5;
      --v13;
    }
    while ( v13 );
  }
  return v11;
}

```

## disassembly

```asm
0x180005184  mov     rax, rsp
0x180005187  mov     [rax+20h], rbx
0x18000518b  mov     [rax+18h], r8
0x18000518f  mov     [rax+10h], rdx
0x180005193  mov     [rax+8], rcx
0x180005197  push    rbp
0x180005198  push    rsi
0x180005199  push    rdi
0x18000519a  push    r12
0x18000519c  push    r13
0x18000519e  push    r14
0x1800051a0  push    r15
0x1800051a2  sub     rsp, 30h
0x1800051a6  mov     r10, [rsp+68h+arg_20]
0x1800051ae  xor     r12d, r12d
0x1800051b1  movsxd  rdi, r9d
0x1800051b4  mov     rbx, r8
0x1800051b7  mov     r11, rcx
0x1800051ba  mov     eax, [r10]
0x1800051bd  test    eax, eax
0x1800051bf  jle     short loc_1800051CB
0x1800051c1  dec     eax
0x1800051c3  mov     [r10], eax
0x1800051c6  jmp     loc_1800054C6
0x1800051cb  mov     eax, [r8]
0x1800051ce  mov     r13d, 1
0x1800051d4  cmp     eax, r13d
0x1800051d7  ja      short loc_1800051E1
0x1800051d9  mov     esi, r12d
0x1800051dc  jmp     loc_180005273
0x1800051e1  movzx   r9d, word ptr [rdx]
0x1800051e5  lea     r8, [rdx+2]
0x1800051e9  add     eax, 0FFFFFFFEh
0x1800051ec  mov     [rbx], eax
0x1800051ee  test    r9w, r9w
0x1800051f2  jns     short loc_180005262
0x1800051f4  mov     eax, r9d
0x1800051f7  mov     ecx, r9d
0x1800051fa  and     eax, 0FFFFFC00h
0x1800051ff  cmp     eax, 8400h
0x180005204  jnz     short loc_18000521A
0x180005206  and     ecx, 3FFh
0x18000520c  sub     ecx, r13d
0x18000520f  mov     [r10], ecx
0x180005212  mov     rax, r8
0x180005215  jmp     loc_1800054C9
0x18000521a  movzx   edx, r9w
0x18000521e  movzx   r10d, r9w
0x180005222  shr     dx, 7
0x180005226  mov     ebx, 4
0x18000522b  shr     r10w, 2
0x180005230  and     dl, 0F8h
0x180005233  and     r10b, 0F8h
0x180005237  shl     r9b, 3
0x18000523b  mov     rax, r12
0x18000523e  lea     rcx, [r11+rax*2]
0x180005242  mov     [rax+rcx], r9b
0x180005246  mov     [rax+rcx+1], r10b
0x18000524b  mov     [rax+rcx+2], dl
0x18000524f  add     rax, r13
0x180005252  cmp     rax, 4
0x180005256  jnz     short loc_18000523E
0x180005258  add     r11, rdi
0x18000525b  sub     ebx, r13d
0x18000525e  jnz     short loc_18000523B
0x180005260  jmp     short loc_180005212
0x180005262  cmp     eax, r13d
0x180005265  ja      short loc_18000527F
0x180005267  mov     rdx, r8
0x18000526a  movzx   esi, r9w
0x18000526e  mov     [rsp+68h+arg_8], rdx
0x180005273  mov     r8d, r12d
0x180005276  movzx   ebp, r13w
0x18000527a  jmp     loc_18000540F
0x18000527f  cmp     [r8], r12w
0x180005283  jge     loc_1800053F6
0x180005289  lea     rax, qword_18000B0A0
0x180005290  mov     [rsp+68h+var_48], rdi
0x180005295  mov     [rsp+68h+var_58], rax
0x18000529a  mov     rdx, r8
0x18000529d  lea     eax, [rdi+rdi]
0x1800052a0  mov     [rsp+68h+var_5C], 2
0x1800052a8  cdqe
0x1800052aa  mov     [rsp+68h+var_40], rax
0x1800052af  mov     [rsp+68h+arg_8], rdx
0x1800052b4  mov     r14, r11
0x1800052b7  mov     [rsp+68h+var_50], r11
0x1800052bc  mov     [rsp+68h+var_60], 2
0x1800052c4  mov     r8d, [rbx]
0x1800052c7  cmp     r8d, r13d
0x1800052ca  ja      short loc_1800052D1
0x1800052cc  mov     r10d, r12d
0x1800052cf  jmp     short loc_1800052E5
0x1800052d1  movzx   r10d, word ptr [rdx]
0x1800052d5  add     rdx, 2
0x1800052d9  add     r8d, 0FFFFFFFEh
0x1800052dd  mov     [rsp+68h+arg_8], rdx
0x1800052e2  mov     [rbx], r8d
0x1800052e5  movzx   eax, r10w
0x1800052e9  movzx   esi, r10w
0x1800052ed  shr     ax, 7
0x1800052f1  shr     si, 2
0x1800052f5  shl     r10b, 3
0x1800052f9  mov     word ptr [rsp+68h+arg_20], ax
0x180005301  cmp     r8d, r13d
0x180005304  ja      short loc_18000530B
0x180005306  mov     ecx, r12d
0x180005309  jmp     short loc_18000531D
0x18000530b  movzx   ecx, word ptr [rdx]
0x18000530e  lea     eax, [r8-2]
0x180005312  add     rdx, 2
0x180005316  mov     [rbx], eax
0x180005318  mov     [rsp+68h+arg_8], rdx
0x18000531d  movzx   ebx, word ptr [rsp+68h+arg_20]
0x180005325  movzx   edi, cx
0x180005328  mov     rdx, [rsp+68h+var_58]
0x18000532d  movzx   eax, cx
0x180005330  shr     ax, 2
0x180005334  mov     r12, r14
0x180005337  shr     di, 7
0x18000533b  movzx   r14d, ax
0x18000533f  shl     cl, 3
0x180005342  mov     [rsp+68h+var_64], 2
0x18000534a  xor     r15d, r15d
0x18000534d  mov     r8d, r15d
0x180005350  movzx   eax, word ptr [rdx]
0x180005353  add     rdx, 2
0x180005357  test    r9w, ax
0x18000535b  jz      short loc_180005368
0x18000535d  mov     r13b, r10b
0x180005360  movzx   eax, bx
0x180005363  movzx   ebp, si
0x180005366  jmp     short loc_180005372
0x180005368  mov     r13b, cl
0x18000536b  movzx   eax, di
0x18000536e  movzx   ebp, r14w
0x180005372  lea     r11, [r12+r8*2]
0x180005376  and     bpl, 0F8h
0x18000537a  mov     [r8+r11], r13b
0x18000537e  and     al, 0F8h
0x180005380  lea     r13, [r12+r8*2]
0x180005384  mov     [r8+r13+1], bpl
0x180005389  mov     [r8+r13+2], al
0x18000538e  mov     r13d, 1
0x180005394  add     r8, r13
0x180005397  cmp     r8, 2
0x18000539b  jnz     short loc_180005350
0x18000539d  add     r12, [rsp+68h+var_48]
0x1800053a2  sub     [rsp+68h+var_64], r13d
0x1800053a7  mov     [rsp+68h+var_58], rdx
0x1800053ac  jnz     short loc_18000534A
0x1800053ae  mov     r14, [rsp+68h+var_50]
0x1800053b3  xor     r12d, r12d
0x1800053b6  mov     rdx, [rsp+68h+arg_8]
0x1800053bb  add     r14, 6
0x1800053bf  sub     [rsp+68h+var_60], r13d
0x1800053c4  mov     rbx, [rsp+68h+arg_10]
0x1800053cc  mov     [rsp+68h+var_50], r14
0x1800053d1  jnz     loc_1800052C4
0x1800053d7  mov     r11, [rsp+68h+arg_0]
0x1800053dc  add     r11, [rsp+68h+var_40]
0x1800053e1  sub     [rsp+68h+var_5C], r13d
0x1800053e6  mov     [rsp+68h+arg_0], r11
0x1800053eb  jnz     loc_1800052B4
0x1800053f1  jmp     loc_1800054C6
0x1800053f6  lea     rdx, [r8+2]
0x1800053fa  add     eax, 0FFFFFFFEh
0x1800053fd  movzx   r8d, word ptr [r8]
0x180005401  mov     ebp, r13d
0x180005404  mov     [rsp+68h+arg_8], rdx
0x180005409  movzx   esi, r9w
0x18000540d  mov     [rbx], eax
0x18000540f  movzx   r14d, r8w
0x180005413  movzx   r15d, r8w
0x180005417  shr     r14w, 7
0x18000541c  shr     r15w, 2
0x180005421  shl     r8b, 3
0x180005425  cmp     eax, r13d
0x180005428  ja      short loc_18000542F
0x18000542a  mov     ecx, r12d
0x18000542d  jmp     short loc_180005440
0x18000542f  movzx   ecx, word ptr [rdx]
0x180005432  add     rdx, 2
0x180005436  add     eax, 0FFFFFFFEh
0x180005439  mov     [rsp+68h+arg_8], rdx
0x18000543e  mov     [rbx], eax
0x180005440  movzx   r13d, cx
0x180005444  mov     [rsp+68h+var_5C], 4
0x18000544c  movzx   eax, cx
0x18000544f  shr     r13w, 7
0x180005454  shr     ax, 2
0x180005458  mov     rdx, rdi
0x18000545b  mov     word ptr [rsp+68h+arg_20], ax
0x180005463  shl     cl, 3
0x180005466  movzx   ebx, word ptr [rsp+68h+arg_20]
0x18000546e  mov     rax, r12
0x180005471  lea     rdi, [r11+rax*2]
0x180005475  test    bp, si
0x180005478  jz      short loc_180005487
0x18000547a  mov     r12b, r8b
0x18000547d  movzx   r9d, r14w
0x180005481  movzx   r10d, r15w
0x180005485  jmp     short loc_180005492
0x180005487  mov     r12b, cl
0x18000548a  movzx   r9d, r13w
0x18000548e  movzx   r10d, bx
0x180005492  mov     [rax+rdi], r12b
0x180005496  and     r10b, 0F8h
0x18000549a  and     r9b, 0F8h
0x18000549e  mov     [rax+rdi+1], r10b
0x1800054a3  mov     [rax+rdi+2], r9b
0x1800054a8  add     bp, bp
0x1800054ab  inc     rax
0x1800054ae  cmp     rax, 4
0x1800054b2  jnz     short loc_180005471
0x1800054b4  add     r11, rdx
0x1800054b7  xor     r12d, r12d
0x1800054ba  sub     [rsp+68h+var_5C], 1
0x1800054bf  jnz     short loc_180005466
0x1800054c1  mov     rdx, [rsp+68h+arg_8]
0x1800054c6  mov     rax, rdx
0x1800054c9  mov     rbx, [rsp+68h+arg_18]
0x1800054d1  add     rsp, 30h
0x1800054d5  pop     r15
0x1800054d7  pop     r14
0x1800054d9  pop     r13
0x1800054db  pop     r12
0x1800054dd  pop     rdi
0x1800054de  pop     rsi
0x1800054df  pop     rbp
0x1800054e0  retn
```
