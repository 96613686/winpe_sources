# itrp_SHP_Common

- ea: `0x140023e80`
- end: `0x14002427a`
- name: `itrp_SHP_Common`
- size: `1018`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140023900`
- `0x1400239e0`

## callees

- `0x140023e80`
- `0x140025240`
- `0x140072578`

## pseudocode

```c
__int64 __fastcall itrp_SHP_Common(__int64 a1, __int64 a2, int a3, char a4, int a5, int a6)
{
  char v6; // r15
  __int64 v7; // rdi
  int v8; // ebx
  __int64 v10; // r10
  __int64 result; // rax
  __int64 v12; // r9
  __int64 v13; // rsi
  __int64 v14; // rbp
  __int64 v15; // r11
  __int64 v16; // r12
  _WORD *v17; // r14
  unsigned __int16 v18; // dx
  unsigned __int16 *v19; // r8
  unsigned __int16 v20; // r15
  unsigned __int16 v21; // cx
  __int16 *v22; // r8
  unsigned __int16 v23; // dx
  int v24; // eax
  __int16 *v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // rax
  __int16 v29; // ax
  int v30; // ecx
  __int64 v31; // rbp
  __int64 v32; // r14
  int v33; // r8d
  int i; // r9d
  __int16 v35; // [rsp+20h] [rbp-48h] BYREF
  int v36; // [rsp+80h] [rbp+18h]

  v36 = a3;
  v6 = a4;
  v7 = *(_QWORD *)(a1 + 16);
  v8 = *(_DWORD *)(a1 + 92) + 1;
  v10 = a1;
  while ( 1 )
  {
    if ( !v8 )
    {
      *(_DWORD *)(v10 + 92) = 0;
      return a2;
    }
    *(_QWORD *)(v10 + 40) -= 4LL;
    v12 = *(_QWORD *)(v10 + 16);
    v13 = *(_QWORD *)(v10 + 56);
    v14 = *(_QWORD *)(v10 + 64);
    v15 = **(int **)(v10 + 40);
    if ( v13 == v12 )
    {
      if ( (int)v15 >= *(unsigned __int16 *)(*(_QWORD *)(v14 + 376) + 16LL) || (int)v15 < 0 )
        goto LABEL_29;
      v16 = 0;
    }
    else
    {
      if ( (int)v15 >= *(_DWORD *)(v14 + 432) || (int)v15 < 0 )
        goto LABEL_29;
      v16 = 4;
    }
    if ( v12 == v13 + 112 )
      break;
LABEL_22:
    if ( *(__int16 *)(v12 + 80) <= 0 )
      goto LABEL_29;
    v26 = *(__int16 *)(v12 + 80);
    v27 = v16 + *(__int16 *)(*(_QWORD *)(v12 + 64) + 2 * v26 - 2);
    if ( (unsigned __int64)(v27 + 0x80000000LL) > 0xFFFFFFFF
      || (v26 = (int)v27 + 1LL, (unsigned __int64)((int)v27 + 2147483649LL) > 0xFFFFFFFF) )
    {
      SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(v26, v27);
      __debugbreak();
    }
    if ( (int)v26 <= (int)v15 )
      goto LABEL_29;
    if ( v7 != v13 && *(_BYTE *)(v14 + 363) == 2 )
    {
      if ( *(_WORD *)(v10 + 204) )
      {
        if ( (*(_BYTE *)(v14 + 448) & 2) != 0 && a3 >= 0 )
        {
          v30 = *(__int16 *)(*(_QWORD *)(v7 + 64) + 2LL * *(__int16 *)(v7 + 80) - 2) + 5;
          if ( a3 < v30 && (int)v15 < v30 && a3 != (_DWORD)v15 )
          {
            v31 = *(_QWORD *)(v7 + 104);
            v32 = 12 * v15;
            if ( IndirectlyDependsOn((struct fnt_ElementType *)v7, v36, v15, 100) )
            {
              *(_WORD *)(v32 + v31 + 6) |= 1u;
            }
            else if ( *(_WORD *)(v32 + v31) == 0xFFFF )
            {
              v33 = v36;
              for ( i = *(__int16 *)(v31 + 12LL * v36); i != -1; i = *(__int16 *)(v31 + 12LL * i) )
              {
                if ( *(_DWORD *)(*(_QWORD *)(v7 + 32) + 4LL * v33) != *(_DWORD *)(*(_QWORD *)(v7 + 32) + 4LL * i) )
                  break;
                v33 = i;
              }
              *(_WORD *)(v32 + v31) = v33;
              *(_WORD *)(v32 + *(_QWORD *)(v7 + 104) + 2) = -1;
            }
          }
        }
      }
    }
    if ( v6 )
    {
      v28 = *(_QWORD *)(v10 + 64);
      if ( (*(_WORD *)(v28 + 450) & 0x10) != 0 )
      {
        if ( (*(_BYTE *)(v28 + 448) & 4) != 0 )
        {
          if ( *(_WORD *)(v10 + 24) != 0x4000
            || *(_WORD *)(v10 + 26)
            || !*(_BYTE *)(v28 + 369)
            && (((*(_WORD *)(v28 + 450) & 1) == 0) & *(_BYTE *)(v15 + *(_QWORD *)(*(_QWORD *)(v10 + 16) + 72LL))) == 0 )
          {
            goto LABEL_61;
          }
LABEL_47:
          v29 = 1;
        }
        else
        {
          if ( *(_WORD *)(v10 + 26) == 0x4000
            && !*(_WORD *)(v10 + 24)
            && (*(_BYTE *)(v28 + 369)
             || (((*(_WORD *)(v28 + 450) & 2) == 0) & (*(_BYTE *)(v15 + *(_QWORD *)(*(_QWORD *)(v10 + 16) + 72LL)) >> 1)) != 0) )
          {
            goto LABEL_47;
          }
LABEL_61:
          v29 = 0;
        }
        if ( !v29 )
          goto LABEL_40;
      }
    }
    if ( *(_WORD *)(v10 + 28) )
    {
      *(_DWORD *)(*(_QWORD *)v7 + 4 * v15) += a5;
      *(_BYTE *)(*(_QWORD *)(v7 + 72) + v15) |= 1u;
    }
    if ( *(_WORD *)(v10 + 30) )
    {
      *(_DWORD *)(*(_QWORD *)(v7 + 8) + 4 * v15) += a6;
      *(_BYTE *)(*(_QWORD *)(v7 + 72) + v15) |= 2u;
    }
LABEL_40:
    a3 = v36;
    --v8;
  }
  v17 = *(_WORD **)(v14 + 376);
  v18 = v17[6];
  v19 = v17 + 4;
  if ( v17[4] >= v18 )
    v18 = v17[4];
  else
    v19 = v17 + 6;
  v20 = 1;
  if ( v18 )
    v20 = *v19;
  v21 = v17[3];
  v22 = v17 + 3;
  v23 = v17[5];
  v35 = 1;
  if ( v21 < v23 )
    v22 = v17 + 5;
  else
    v23 = v21;
  v24 = *(__int16 *)(v12 + 80);
  v25 = &v35;
  if ( v23 )
    v25 = v22;
  if ( v24 >= 1
    && (v24 <= (unsigned int)v20
     || *(_DWORD *)(v12 + 104) + 12 * ((unsigned int)(unsigned __int16)*v25 + 8) - *(_DWORD *)(v12 + 64) >= (unsigned __int64)(2LL * (v24 - 1))) )
  {
    a3 = v36;
    v6 = a4;
    goto LABEL_22;
  }
LABEL_29:
  result = *(_QWORD *)(v10 + 176);
  *(_DWORD *)(v10 + 168) = 4370;
  return result;
}

```

## disassembly

```asm
0x140023e80  mov     [rsp+arg_18], r9b
0x140023e85  mov     [rsp+arg_10], r8d
0x140023e8a  push    rbx
0x140023e8b  push    rbp
0x140023e8c  push    rsi
0x140023e8d  push    rdi
0x140023e8e  push    r13
0x140023e90  push    r14
0x140023e92  push    r15
0x140023e94  sub     rsp, 30h
0x140023e98  mov     ebx, [rcx+5Ch]
0x140023e9b  movzx   r15d, r9b
0x140023e9f  mov     rdi, [rcx+10h]
0x140023ea3  inc     ebx
0x140023ea5  mov     r13, rdx
0x140023ea8  mov     [rsp+68h+arg_0], r12
0x140023ead  mov     r10, rcx
0x140023eb0  mov     r14d, 80000000h
0x140023eb6  test    ebx, ebx
0x140023eb8  jnz     short loc_140023ED5
0x140023eba  mov     [r10+5Ch], ebx
0x140023ebe  mov     rax, r13
0x140023ec1  mov     r12, [rsp+68h+arg_0]
0x140023ec6  add     rsp, 30h
0x140023eca  pop     r15
0x140023ecc  pop     r14
0x140023ece  pop     r13
0x140023ed0  pop     rdi
0x140023ed1  pop     rsi
0x140023ed2  pop     rbp
0x140023ed3  pop     rbx
0x140023ed4  retn
0x140023ed5  add     qword ptr [r10+28h], 0FFFFFFFFFFFFFFFCh
0x140023eda  mov     rax, [r10+28h]
0x140023ede  mov     r9, [r10+10h]
0x140023ee2  mov     rsi, [r10+38h]
0x140023ee6  mov     rbp, [r10+40h]
0x140023eea  movsxd  r11, dword ptr [rax]
0x140023eed  cmp     rsi, r9
0x140023ef0  jz      loc_140023FED
0x140023ef6  cmp     r11d, [rbp+1B0h]
0x140023efd  jge     loc_140024031
0x140023f03  test    r11d, r11d
0x140023f06  js      loc_140024031
0x140023f0c  mov     r12d, 4
0x140023f12  lea     rax, [rsi+70h]
0x140023f16  cmp     r9, rax
0x140023f19  jnz     loc_140023FB5
0x140023f1f  mov     r14, [rbp+178h]
0x140023f26  movzx   edx, word ptr [r14+0Ch]
0x140023f2b  lea     rax, [r14+0Ch]
0x140023f2f  movzx   ecx, word ptr [r14+8]
0x140023f34  lea     r8, [r14+8]
0x140023f38  cmp     cx, dx
0x140023f3b  cmovb   r8, rax
0x140023f3f  cmovnb  dx, cx
0x140023f43  mov     eax, 1
0x140023f48  movzx   r15d, ax
0x140023f4c  cmp     dx, ax
0x140023f4f  jnb     loc_140023FE4
0x140023f55  movzx   ecx, word ptr [r14+6]
0x140023f5a  lea     r8, [r14+6]
0x140023f5e  movzx   edx, word ptr [r14+0Ah]
0x140023f63  cmp     cx, dx
0x140023f66  mov     [rsp+68h+var_48], ax
0x140023f6b  lea     rax, [r14+0Ah]
0x140023f6f  cmovnb  dx, cx
0x140023f73  cmovb   r8, rax
0x140023f77  movsx   eax, word ptr [r9+50h]
0x140023f7c  lea     rcx, [rsp+68h+var_48]
0x140023f81  cmp     dx, 1
0x140023f85  cmovnb  rcx, r8
0x140023f89  cmp     eax, 1
0x140023f8c  jl      loc_140024031
0x140023f92  mov     r8d, eax
0x140023f95  movzx   eax, r15w
0x140023f99  cmp     r8d, eax
0x140023f9c  ja      short loc_14002400A
0x140023f9e  mov     r8d, [rsp+68h+arg_10]
0x140023fa6  mov     r14d, 80000000h
0x140023fac  movzx   r15d, [rsp+68h+arg_18]
0x140023fb5  movsx   rax, word ptr [r9+50h]
0x140023fba  test    ax, ax
0x140023fbd  jle     short loc_140024031
0x140023fbf  mov     rcx, rax
0x140023fc2  mov     rax, [r9+40h]
0x140023fc6  mov     r9d, 0FFFFFFFFh
0x140023fcc  movsx   rdx, word ptr [rax+rcx*2-2]
0x140023fd2  add     rdx, r12
0x140023fd5  lea     rax, [rdx+r14]
0x140023fd9  cmp     rax, r9
0x140023fdc  jbe     short loc_140024048
0x140023fde  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@SAXXZ; SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(void)
0x140023fe3  int     3; Trap to Debugger
0x140023fe4  movzx   r15d, word ptr [r8]
0x140023fe8  jmp     loc_140023F55
0x140023fed  mov     rax, [rbp+178h]
0x140023ff4  movzx   ecx, word ptr [rax+10h]
0x140023ff8  cmp     r11d, ecx
0x140023ffb  jge     short loc_140024031
0x140023ffd  test    r11d, r11d
0x140024000  js      short loc_140024031
0x140024002  xor     r12d, r12d
0x140024005  jmp     loc_140023F12
0x14002400a  movzx   eax, word ptr [rcx]
0x14002400d  add     eax, 8
0x140024010  lea     edx, [rax+rax*2]
0x140024013  shl     edx, 2
0x140024016  lea     eax, [r8-1]
0x14002401a  sub     edx, [r9+40h]
0x14002401e  add     edx, [r9+68h]
0x140024022  movsxd  rcx, eax
0x140024025  add     rcx, rcx
0x140024028  cmp     rdx, rcx
0x14002402b  jnb     loc_140023F9E
0x140024031  mov     rax, [r10+0B0h]
0x140024038  mov     dword ptr [r10+0A8h], 1112h
0x140024043  jmp     loc_140023EC1
0x140024048  movsxd  rcx, edx
0x14002404b  inc     rcx
0x14002404e  lea     rax, [rcx+r14]
0x140024052  cmp     rax, r9
0x140024055  ja      short loc_140023FDE
0x140024057  cmp     ecx, r11d
0x14002405a  jle     short loc_140024031
0x14002405c  cmp     rdi, rsi
0x14002405f  jz      short loc_140024079
0x140024061  cmp     byte ptr [rbp+16Bh], 2
0x140024068  jnz     short loc_140024079
0x14002406a  cmp     word ptr [r10+0CCh], 0
0x140024073  jnz     loc_14002414A
0x140024079  test    r15b, r15b
0x14002407c  jnz     short loc_1400240CC
0x14002407e  cmp     word ptr [r10+1Ch], 0
0x140024084  jz      short loc_14002409D
0x140024086  mov     rax, [rdi]
0x140024089  mov     edx, [rsp+68h+arg_20]
0x140024090  add     [rax+r11*4], edx
0x140024094  mov     rax, [rdi+48h]
0x140024098  or      byte ptr [rax+r11], 1
0x14002409d  cmp     word ptr [r10+1Eh], 0
0x1400240a3  jz      short loc_1400240BD
0x1400240a5  mov     rax, [rdi+8]
0x1400240a9  mov     edx, [rsp+68h+arg_28]
0x1400240b0  add     [rax+r11*4], edx
0x1400240b4  mov     rax, [rdi+48h]
0x1400240b8  or      byte ptr [rax+r11], 2
0x1400240bd  mov     r8d, [rsp+68h+arg_10]
0x1400240c5  dec     ebx
0x1400240c7  jmp     loc_140023EB6
0x1400240cc  mov     rax, [r10+40h]
0x1400240d0  movzx   r8d, word ptr [rax+1C2h]
0x1400240d8  test    r8b, 10h
0x1400240dc  jz      short loc_14002407E
0x1400240de  test    byte ptr [rax+1C0h], 4
0x1400240e5  mov     ecx, 4000h
0x1400240ea  jnz     loc_14002423B
0x1400240f0  cmp     [r10+1Ah], cx
0x1400240f5  jnz     loc_14002420D
0x1400240fb  cmp     word ptr [r10+18h], 0
0x140024101  jnz     loc_14002420D
0x140024107  cmp     byte ptr [rax+171h], 0
0x14002410e  jnz     short loc_140024137
0x140024110  mov     rax, [r10+10h]
0x140024114  mov     rax, [rax+48h]
0x140024118  movzx   edx, byte ptr [r11+rax]
0x14002411d  mov     eax, 1
0x140024122  shr     dl, 1
0x140024124  bt      r8w, ax
0x140024129  setnb   al
0x14002412c  and     dl, al
0x14002412e  test    dl, 1
0x140024131  jz      loc_14002420D
0x140024137  mov     eax, 1
0x14002413c  test    ax, ax
0x14002413f  jz      loc_1400240BD
0x140024145  jmp     loc_14002407E
0x14002414a  test    byte ptr [rbp+1C0h], 2
0x140024151  jz      loc_140024079
0x140024157  test    r8d, r8d
0x14002415a  js      loc_140024079
0x140024160  movsx   rcx, word ptr [rdi+50h]
0x140024165  mov     rax, [rdi+40h]
0x140024169  movsx   ecx, word ptr [rax+rcx*2-2]
0x14002416e  add     ecx, 5
0x140024171  cmp     r8d, ecx
0x140024174  jge     loc_140024079
0x14002417a  test    r11d, r11d
0x14002417d  js      loc_140024079
0x140024183  cmp     r11d, ecx
0x140024186  jge     loc_140024079
0x14002418c  cmp     r8d, r11d
0x14002418f  jz      loc_140024079
0x140024195  movsxd  rsi, [rsp+68h+arg_10]
0x14002419d  lea     rcx, [r11+r11*2]
0x1400241a1  mov     rbp, [rdi+68h]
0x1400241a5  lea     r14, ds:0[rcx*4]
0x1400241ad  mov     rcx, rdi; struct fnt_ElementType *
0x1400241b0  mov     r9d, 64h ; 'd'; int
0x1400241b6  mov     r8d, r11d; int
0x1400241b9  mov     edx, esi; int
0x1400241bb  call    ?IndirectlyDependsOn@@YA_NPEAUfnt_ElementType@@HHH@Z; IndirectlyDependsOn(fnt_ElementType *,int,int,int)
0x1400241c0  test    al, al
0x1400241c2  jnz     short loc_140024229
0x1400241c4  cmp     word ptr [r14+rbp], 0FFFFh
0x1400241ca  jnz     short loc_140024202
0x1400241cc  lea     rcx, [rsi+rsi*2]
0x1400241d0  mov     r8d, esi
0x1400241d3  movsx   r9d, word ptr [rbp+rcx*4+0]
0x1400241d9  cmp     r9d, 0FFFFFFFFh
0x1400241dd  jz      short loc_1400241F1
0x1400241df  mov     rdx, [rdi+20h]
0x1400241e3  movsxd  rsi, r9d
0x1400241e6  movsxd  rcx, r8d
0x1400241e9  mov     eax, [rdx+rsi*4]
0x1400241ec  cmp     [rdx+rcx*4], eax
0x1400241ef  jz      short loc_140024214
0x1400241f1  mov     [r14+rbp], r8w
0x1400241f6  mov     rax, [rdi+68h]
0x1400241fa  mov     word ptr [r14+rax+2], 0FFFFh
0x140024202  mov     r14d, 80000000h
0x140024208  jmp     loc_140024079
0x14002420d  xor     eax, eax
0x14002420f  jmp     loc_14002413C
0x140024214  lea     rax, [rsi+rsi*2]
0x140024218  mov     r8d, r9d
0x14002421b  movsx   r9d, word ptr [rbp+rax*4+0]
0x140024221  cmp     r9d, 0FFFFFFFFh
0x140024225  jnz     short loc_1400241E3
0x140024227  jmp     short loc_1400241F1
0x140024229  or      word ptr [r14+rbp+6], 1
0x140024230  mov     r14d, 80000000h
0x140024236  jmp     loc_140024079
0x14002423b  cmp     [r10+18h], cx
0x140024240  jnz     short loc_14002420D
0x140024242  cmp     word ptr [r10+1Ah], 0
0x140024248  jnz     short loc_14002420D
0x14002424a  cmp     byte ptr [rax+171h], 0
0x140024251  jnz     loc_140024137
0x140024257  mov     rax, [r10+10h]
0x14002425b  mov     rcx, [rax+48h]
0x14002425f  xor     eax, eax
0x140024261  bt      r8w, ax
0x140024266  setnb   al
0x140024269  movzx   ecx, byte ptr [r11+rcx]
0x14002426e  and     cl, al
0x140024270  test    cl, 1
0x140024273  jz      short loc_14002420D
0x140024275  jmp     loc_140024137
```
