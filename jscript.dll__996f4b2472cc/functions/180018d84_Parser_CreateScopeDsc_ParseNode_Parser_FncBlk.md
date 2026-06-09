# Parser::CreateScopeDsc(ParseNode *,Parser::FncBlk * *)

- ea: `0x180018d84`
- end: `0x1800190bc`
- name: `?CreateScopeDsc@Parser@@AEAAXPEAUParseNode@@PEAPEAUFncBlk@1@@Z`
- size: `824`
- prototype: `void __fastcall(Parser *__hidden this, struct ParseNode *, struct Parser::FncBlk **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800199e0`

## callees

- `0x180018d84`
- `0x18001d9e4`
- `0x1800966aa`

## import_xrefs

- `msvcrt!malloc` at `0x180019023`
- `msvcrt!malloc` at `0x180019072`
- `msvcrt!malloc` at `0x180019023`
- `msvcrt!malloc` at `0x180019072`

## pseudocode

```c
void __fastcall Parser::CreateScopeDsc(Parser *this, struct ParseNode *a2, struct Parser::FncBlk **a3)
{
  int v4; // r14d
  int v5; // ecx
  __int64 v7; // r9
  __int64 v8; // rcx
  int v9; // r14d
  int v10; // esi
  __int64 i; // rax
  __int64 v12; // rcx
  int v13; // r8d
  __int64 v14; // rdx
  int v15; // ecx
  int v16; // ecx
  __int64 v17; // rax
  int v18; // ecx
  int v19; // edi
  int v20; // r15d
  char *v21; // rax
  char *v22; // rbp
  _DWORD *v23; // r9
  __int64 j; // r8
  __int64 v25; // r11
  __int16 v26; // ax
  int v27; // ecx
  _QWORD *v28; // rax
  __int64 k; // r8
  __int64 v30; // r11
  __int16 v31; // ax
  int v32; // ecx
  _QWORD *v33; // rax
  int v34; // ebp
  int v35; // eax
  int v36; // ecx
  int v37; // eax
  _QWORD *v38; // rax
  char **v39; // rdx
  int v40; // [rsp+60h] [rbp+8h]
  __int16 v41; // [rsp+68h] [rbp+10h]

  v4 = 0;
  v5 = *(_DWORD *)a2;
  v40 = *(_DWORD *)a2;
  ++*((_DWORD *)this + 78);
  v7 = *((_QWORD *)a2 + 7);
  if ( v7 )
  {
    do
    {
      v8 = *(_QWORD *)(v7 + 32);
      --v4;
      *(_DWORD *)(v8 + 20) = *((_DWORD *)this + 78);
      *(_QWORD *)(v8 + 24) = v7;
      *(_DWORD *)(v7 + 24) = v4;
      v7 = *(_QWORD *)(v7 + 16);
    }
    while ( v7 );
    v5 = v40;
  }
  v9 = -v4;
  if ( (__int16)v9 != v9 )
    goto LABEL_40;
  v10 = 0;
  if ( v5 != 70 )
  {
    for ( i = *((_QWORD *)a2 + 8); i; i = *(_QWORD *)(i + 16) )
    {
      v12 = *(_QWORD *)(i + 32);
      v13 = *((_DWORD *)this + 78);
      if ( *(_DWORD *)(v12 + 20) == v13 )
        v14 = *(_QWORD *)(v12 + 24);
      else
        v14 = 0;
      if ( v14 )
      {
        *(_DWORD *)(i + 4) |= 0x4000u;
      }
      else
      {
        *(_DWORD *)(v12 + 20) = v13;
        *(_QWORD *)(v12 + 24) = i;
        v15 = *(_DWORD *)(i + 4);
        if ( (v15 & 1) == 0 )
        {
          v16 = ++v10;
          goto LABEL_13;
        }
        *(_DWORD *)(i + 4) = v15 | 0x4000;
      }
      v16 = 0;
LABEL_13:
      *(_DWORD *)(i + 24) = v16;
    }
  }
  v17 = *((_QWORD *)a2 + 9);
  v18 = v10;
  v41 = v10;
  while ( v17 )
  {
    *(_DWORD *)(v17 + 24) = ++v10;
    v17 = *(_QWORD *)(v17 + 16);
  }
  if ( (__int16)v10 != v10 )
LABEL_40:
    Parser::Error(this, 1001);
  v19 = 4 * (v9 + v18) + 80;
  if ( v19 <= 0 )
    goto LABEL_52;
  v20 = *((_DWORD *)this + 4);
  if ( v19 <= *((_DWORD *)this + 5) - v20 )
  {
LABEL_22:
    *((_DWORD *)this + 4) = v20 + ((v19 + 7) & 0xFFFFFFF8);
    v21 = (char *)(*((_QWORD *)this + 1) + v20);
    goto LABEL_23;
  }
  v34 = *((_DWORD *)this + 7);
  if ( v19 < v34 )
  {
    v35 = 4 * (v9 + v18) + 80;
    v36 = *((_DWORD *)this + 6);
    if ( *((_DWORD *)this + 5) > v19 )
      v35 = *((_DWORD *)this + 5);
    v37 = 2 * v35;
    if ( v36 <= v37 )
      v36 = v37;
    if ( v36 > v34 || (v34 = v36, v19 <= v36) )
    {
      if ( v34 + 8 > v34 && v34 + 8 >= v19 )
      {
        v38 = malloc(v34 + 8LL);
        if ( v38 )
        {
          v20 = 0;
          *v38 = *((_QWORD *)this + 1);
          *((_QWORD *)this + 1) = v38;
          *((_DWORD *)this + 5) = v34;
          goto LABEL_22;
        }
      }
    }
LABEL_52:
    *a3 = 0;
LABEL_53:
    Parser::Error(this, 1001);
  }
  if ( 4 * (v9 + v18) + 88 <= 4 * (v9 + v18) + 80 )
    goto LABEL_52;
  v21 = (char *)malloc(v19 + 8LL);
  if ( !v21 )
    goto LABEL_52;
  v39 = (char **)*((_QWORD *)this + 1);
  if ( v20 >= *((_DWORD *)this + 5) )
  {
    *(_QWORD *)v21 = v39;
    *((_QWORD *)this + 1) = v21;
  }
  else
  {
    *(_QWORD *)v21 = *v39;
    *v39 = v21;
  }
LABEL_23:
  v22 = v21 + 8;
  *a3 = (struct Parser::FncBlk *)(v21 + 8);
  if ( v21 == (char *)-8LL )
    goto LABEL_53;
  memset_0(v22, 0, v19);
  *((_DWORD *)v22 + 2) = v19 - 24;
  v23 = v22 + 80;
  *((_WORD *)v22 + 36) = v10 - v41;
  *((_WORD *)v22 + 34) = v9;
  *((_WORD *)v22 + 35) = v41;
  for ( j = *((_QWORD *)a2 + 7); j; j = *(_QWORD *)(j + 16) )
  {
    if ( (*(_DWORD *)(j + 4) & 0x4000) == 0 )
    {
      v25 = *(_QWORD *)(j + 32);
      v26 = *(_WORD *)(v25 + 10);
      if ( (v26 & 0x4000) == 0 )
      {
        v27 = *(_DWORD *)(v25 + 40);
        *(_WORD *)(v25 + 10) = v26 | 0x4000;
        *(_DWORD *)(v25 + 16) = *((_DWORD *)this + 128) + 8;
        v28 = (_QWORD *)*((_QWORD *)this + 66);
        *((_DWORD *)this + 128) = (*((_DWORD *)this + 128) + 13 + 2 * v27) & 0xFFFFFFFC;
        *v28 = v25;
        *((_QWORD *)this + 66) = v25 + 32;
      }
      *v23++ = *(_DWORD *)(v25 + 16);
    }
  }
  if ( v40 == 69 )
  {
    for ( k = *((_QWORD *)a2 + 8); k; k = *(_QWORD *)(k + 16) )
    {
      if ( (*(_DWORD *)(k + 4) & 0x4000) == 0 )
      {
        v30 = *(_QWORD *)(k + 32);
        v31 = *(_WORD *)(v30 + 10);
        if ( (v31 & 0x4000) == 0 )
        {
          v32 = *(_DWORD *)(v30 + 40);
          *(_WORD *)(v30 + 10) = v31 | 0x4000;
          *(_DWORD *)(v30 + 16) = *((_DWORD *)this + 128) + 8;
          v33 = (_QWORD *)*((_QWORD *)this + 66);
          *((_DWORD *)this + 128) = (*((_DWORD *)this + 128) + 13 + 2 * v32) & 0xFFFFFFFC;
          *v33 = v30;
          *((_QWORD *)this + 66) = v30 + 32;
        }
        *v23++ = *(_DWORD *)(v30 + 16);
      }
    }
  }
}

```

## disassembly

```asm
0x180018d84  mov     [rsp+arg_10], r8
0x180018d89  push    rbx
0x180018d8a  push    rbp
0x180018d8b  push    rsi
0x180018d8c  push    rdi
0x180018d8d  push    r13
0x180018d8f  push    r14
0x180018d91  push    r15
0x180018d93  sub     rsp, 20h
0x180018d97  mov     rbx, rcx
0x180018d9a  xor     r14d, r14d
0x180018d9d  mov     ecx, [rdx]
0x180018d9f  mov     r13, rdx
0x180018da2  mov     [rsp+58h+arg_0], ecx
0x180018da6  inc     dword ptr [rbx+138h]
0x180018dac  mov     r9, [rdx+38h]
0x180018db0  test    r9, r9
0x180018db3  jz      short loc_180018DDA
0x180018db5  mov     rcx, [r9+20h]
0x180018db9  dec     r14d
0x180018dbc  mov     eax, [rbx+138h]
0x180018dc2  mov     [rcx+14h], eax
0x180018dc5  mov     [rcx+18h], r9
0x180018dc9  mov     [r9+18h], r14d
0x180018dcd  mov     r9, [r9+10h]
0x180018dd1  test    r9, r9
0x180018dd4  jnz     short loc_180018DB5
0x180018dd6  mov     ecx, [rsp+58h+arg_0]
0x180018dda  neg     r14d
0x180018ddd  movsx   eax, r14w
0x180018de1  cmp     eax, r14d
0x180018de4  jnz     loc_180018FDF
0x180018dea  xor     esi, esi
0x180018dec  mov     r9d, 4000h
0x180018df2  cmp     ecx, 46h ; 'F'
0x180018df5  jz      short loc_180018E4B
0x180018df7  mov     rax, [rdx+40h]
0x180018dfb  test    rax, rax
0x180018dfe  jz      short loc_180018E4B
0x180018e00  mov     rcx, [rax+20h]
0x180018e04  mov     r8d, [rbx+138h]
0x180018e0b  cmp     [rcx+14h], r8d
0x180018e0f  jnz     loc_1800190A7
0x180018e15  mov     rdx, [rcx+18h]
0x180018e19  test    rdx, rdx
0x180018e1c  jnz     short loc_180018E45
0x180018e1e  mov     [rcx+14h], r8d
0x180018e22  mov     [rcx+18h], rax
0x180018e26  mov     ecx, [rax+4]
0x180018e29  test    cl, 1
0x180018e2c  jnz     short loc_180018E3B
0x180018e2e  inc     esi
0x180018e30  mov     ecx, esi
0x180018e32  mov     [rax+18h], ecx
0x180018e35  mov     rax, [rax+10h]
0x180018e39  jmp     short loc_180018DFB
0x180018e3b  or      ecx, r9d
0x180018e3e  mov     [rax+4], ecx
0x180018e41  xor     ecx, ecx
0x180018e43  jmp     short loc_180018E32
0x180018e45  or      [rax+4], r9d
0x180018e49  jmp     short loc_180018E41
0x180018e4b  mov     rax, [r13+48h]
0x180018e4f  mov     ecx, esi
0x180018e51  mov     [rsp+58h+arg_8], ecx
0x180018e55  test    rax, rax
0x180018e58  jnz     loc_1800190AE
0x180018e5e  movsx   eax, si
0x180018e61  cmp     eax, esi
0x180018e63  jnz     loc_180018FDF
0x180018e69  lea     eax, [r14+rcx]
0x180018e6d  lea     edi, ds:50h[rax*4]
0x180018e74  test    edi, edi
0x180018e76  jle     loc_18001904A
0x180018e7c  mov     eax, [rbx+14h]
0x180018e7f  mov     r15d, [rbx+10h]
0x180018e83  sub     eax, r15d
0x180018e86  cmp     edi, eax
0x180018e88  jg      loc_180018FED
0x180018e8e  lea     eax, [rdi+7]
0x180018e91  and     eax, 0FFFFFFF8h
0x180018e94  add     eax, r15d
0x180018e97  mov     [rbx+10h], eax
0x180018e9a  movsxd  rax, r15d
0x180018e9d  add     rax, [rbx+8]
0x180018ea1  lea     rbp, [rax+8]
0x180018ea5  mov     rax, [rsp+58h+arg_10]
0x180018eaa  mov     [rax], rbp
0x180018ead  test    rbp, rbp
0x180018eb0  jz      loc_180019056
0x180018eb6  movsxd  r8, edi; Size
0x180018eb9  xor     edx, edx; Val
0x180018ebb  mov     rcx, rbp; void *
0x180018ebe  call    memset_0
0x180018ec3  lea     eax, [rdi-18h]
0x180018ec6  mov     edi, 4000h
0x180018ecb  mov     [rbp+8], eax
0x180018ece  lea     r9, [rbp+50h]
0x180018ed2  mov     eax, [rsp+58h+arg_8]
0x180018ed6  sub     si, ax
0x180018ed9  mov     [rbp+48h], si
0x180018edd  mov     [rbp+44h], r14w
0x180018ee2  mov     [rbp+46h], ax
0x180018ee6  mov     r8, [r13+38h]
0x180018eea  test    r8, r8
0x180018eed  jz      short loc_180018F57
0x180018eef  test    [r8+4], edi
0x180018ef3  jnz     short loc_180018F51
0x180018ef5  mov     r11, [r8+20h]
0x180018ef9  movzx   eax, word ptr [r11+0Ah]
0x180018efe  test    di, ax
0x180018f01  jnz     short loc_180018F46
0x180018f03  mov     ecx, [r11+28h]
0x180018f07  or      ax, di
0x180018f0a  mov     [r11+0Ah], ax
0x180018f0f  mov     eax, [rbx+200h]
0x180018f15  add     eax, 8
0x180018f18  mov     [r11+10h], eax
0x180018f1c  mov     edx, [rbx+200h]
0x180018f22  mov     rax, [rbx+210h]
0x180018f29  add     edx, 0Dh
0x180018f2c  lea     edx, [rdx+rcx*2]
0x180018f2f  and     edx, 0FFFFFFFCh
0x180018f32  mov     [rbx+200h], edx
0x180018f38  mov     [rax], r11
0x180018f3b  lea     rax, [r11+20h]
0x180018f3f  mov     [rbx+210h], rax
0x180018f46  mov     eax, [r11+10h]
0x180018f4a  mov     [r9], eax
0x180018f4d  add     r9, 4
0x180018f51  mov     r8, [r8+10h]
0x180018f55  jmp     short loc_180018EEA
0x180018f57  cmp     [rsp+58h+arg_0], 45h ; 'E'
0x180018f5c  jnz     short loc_180018FCF
0x180018f5e  mov     r8, [r13+40h]
0x180018f62  test    r8, r8
0x180018f65  jz      short loc_180018FCF
0x180018f67  test    [r8+4], edi
0x180018f6b  jnz     short loc_180018FC9
0x180018f6d  mov     r11, [r8+20h]
0x180018f71  movzx   eax, word ptr [r11+0Ah]
0x180018f76  test    di, ax
0x180018f79  jnz     short loc_180018FBE
0x180018f7b  mov     ecx, [r11+28h]
0x180018f7f  or      ax, di
0x180018f82  mov     [r11+0Ah], ax
0x180018f87  mov     eax, [rbx+200h]
0x180018f8d  add     eax, 8
0x180018f90  mov     [r11+10h], eax
0x180018f94  mov     edx, [rbx+200h]
0x180018f9a  mov     rax, [rbx+210h]
0x180018fa1  add     edx, 0Dh
0x180018fa4  lea     edx, [rdx+rcx*2]
0x180018fa7  and     edx, 0FFFFFFFCh
0x180018faa  mov     [rbx+200h], edx
0x180018fb0  mov     [rax], r11
0x180018fb3  lea     rax, [r11+20h]
0x180018fb7  mov     [rbx+210h], rax
0x180018fbe  mov     eax, [r11+10h]
0x180018fc2  mov     [r9], eax
0x180018fc5  add     r9, 4
0x180018fc9  mov     r8, [r8+10h]
0x180018fcd  jmp     short loc_180018F62
0x180018fcf  add     rsp, 20h
0x180018fd3  pop     r15
0x180018fd5  pop     r14
0x180018fd7  pop     r13
0x180018fd9  pop     rdi
0x180018fda  pop     rsi
0x180018fdb  pop     rbp
0x180018fdc  pop     rbx
0x180018fdd  retn
0x180018fdf  mov     edx, 3E9h; int
0x180018fe4  mov     rcx, rbx; this
0x180018fe7  call    ?Error@Parser@@AEAAXH@Z; Parser::Error(int)
0x180018fed  mov     ebp, [rbx+1Ch]
0x180018ff0  cmp     edi, ebp
0x180018ff2  jge     short loc_180019064
0x180018ff4  cmp     [rbx+14h], edi
0x180018ff7  mov     eax, edi
0x180018ff9  mov     ecx, [rbx+18h]
0x180018ffc  cmovg   eax, [rbx+14h]
0x180019000  add     eax, eax
0x180019002  cmp     ecx, eax
0x180019004  cmovle  ecx, eax
0x180019007  cmp     ecx, ebp
0x180019009  jg      short loc_180019011
0x18001900b  mov     ebp, ecx
0x18001900d  cmp     edi, ecx
0x18001900f  jg      short loc_18001904A
0x180019011  lea     eax, [rbp+8]
0x180019014  cmp     eax, ebp
0x180019016  jl      short loc_18001904A
0x180019018  cmp     eax, edi
0x18001901a  jl      short loc_18001904A
0x18001901c  movsxd  rcx, ebp
0x18001901f  add     rcx, 8; Size
0x180019023  call    cs:__imp_malloc
0x18001902a  nop     dword ptr [rax+rax+00h]
0x18001902f  test    rax, rax
0x180019032  jz      short loc_18001904A
0x180019034  mov     rcx, [rbx+8]
0x180019038  xor     r15d, r15d
0x18001903b  mov     [rax], rcx
0x18001903e  mov     [rbx+8], rax
0x180019042  mov     [rbx+14h], ebp
0x180019045  jmp     loc_180018E8E
0x18001904a  mov     rax, [rsp+58h+arg_10]
0x18001904f  mov     qword ptr [rax], 0
0x180019056  mov     edx, 3E9h; int
0x18001905b  mov     rcx, rbx; this
0x18001905e  call    ?Error@Parser@@AEAAXH@Z; Parser::Error(int)
0x180019064  lea     eax, [rdi+8]
0x180019067  cmp     eax, edi
0x180019069  jl      short loc_18001904A
0x18001906b  movsxd  rcx, edi
0x18001906e  add     rcx, 8; Size
0x180019072  call    cs:__imp_malloc
0x180019079  nop     dword ptr [rax+rax+00h]
0x18001907e  test    rax, rax
0x180019081  jz      short loc_18001904A
0x180019083  mov     rdx, [rbx+8]
0x180019087  cmp     r15d, [rbx+14h]
0x18001908b  jge     short loc_18001909B
0x18001908d  mov     rcx, [rdx]
0x180019090  mov     [rax], rcx
0x180019093  mov     [rdx], rax
0x180019096  jmp     loc_180018EA1
0x18001909b  mov     [rax], rdx
0x18001909e  mov     [rbx+8], rax
0x1800190a2  jmp     loc_180018EA1
0x1800190a7  xor     edx, edx
0x1800190a9  jmp     loc_180018E19
0x1800190ae  inc     esi
0x1800190b0  mov     [rax+18h], esi
0x1800190b3  mov     rax, [rax+10h]
0x1800190b7  jmp     loc_180018E55
```
