# RtlpCopyEffectiveAce

- ea: `0x1800af7d0`
- end: `0x1800afedf`
- name: `RtlpCopyEffectiveAce`
- size: `1807`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, __int64, __int64, __int64, __int64, __int64, int, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1800af320`
- `0x1800afef0`

## callees

- `0x1800ae9d0`
- `0x1800af7d0`
- `0x180162000`
- `0x180163a80`

## pseudocode

```c
char __fastcall RtlpCopyEffectiveAce(
        unsigned __int8 *Src,
        char a2,
        char a3,
        unsigned __int8 *a4,
        unsigned __int8 *a5,
        __int64 a6,
        __int64 a7,
        _DWORD *a8,
        __int64 a9,
        unsigned int a10,
        void **a11,
        _DWORD *a12,
        __int64 a13,
        _BYTE *a14,
        _BYTE *a15,
        _BYTE *a16)
{
  __int64 v16; // r11
  char v17; // si
  _BYTE *v18; // rbx
  __int64 v21; // rdx
  _BYTE *v22; // r8
  unsigned __int8 v23; // cl
  __int64 v24; // r15
  char v25; // r14
  unsigned __int8 *v26; // rsi
  unsigned __int8 *v27; // r9
  int v28; // edx
  int v29; // ebx
  unsigned int v30; // eax
  int v31; // r10d
  int v32; // ebx
  int v33; // ebx
  _BYTE *v34; // rax
  char *v35; // r14
  char *v36; // rdi
  char *v37; // rsi
  unsigned int v38; // esi
  int v40; // eax
  int j; // r8d
  int v42; // eax
  __int64 v43; // rax
  int v44; // r15d
  int v45; // eax
  int v46; // eax
  __int64 v47; // rcx
  __int64 v48; // rdx
  unsigned int v49; // ebx
  char *v50; // rcx
  int v51; // r14d
  int v52; // ecx
  int v53; // ecx
  int v54; // ecx
  int v55; // eax
  int v56; // eax
  int v57; // eax
  unsigned int i; // edx
  _QWORD *v59; // r8
  __int64 v60; // rax
  unsigned int v61; // eax
  unsigned int Size; // [rsp+30h] [rbp-A9h]
  unsigned __int8 *v64; // [rsp+40h] [rbp-99h]
  unsigned __int8 *v65; // [rsp+48h] [rbp-91h]
  int v66; // [rsp+50h] [rbp-89h]
  unsigned __int8 *v67; // [rsp+58h] [rbp-81h]
  unsigned __int8 *v68; // [rsp+60h] [rbp-79h]
  unsigned __int8 *Srca; // [rsp+78h] [rbp-61h]
  int v71; // [rsp+88h] [rbp-51h] BYREF
  _QWORD v72[5]; // [rsp+8Ch] [rbp-4Dh]
  char v73[8]; // [rsp+B8h] [rbp-21h] BYREF
  int v74; // [rsp+C0h] [rbp-19h]

  v16 = a7;
  v17 = a2;
  v18 = a16;
  v21 = a6;
  v22 = a15;
  if ( !a6 )
    v21 = (__int64)a4;
  if ( !a7 )
    v16 = (__int64)a5;
  v67 = (unsigned __int8 *)v16;
  v71 = 257;
  v72[0] = 50331648;
  v68 = (unsigned __int8 *)v21;
  *a15 = 0;
  if ( a14 )
    *a14 = 0;
  *a16 = 0;
  v23 = *Src;
  v24 = *((unsigned __int16 *)Src + 1);
  if ( *Src < 0xBu || (unsigned __int8)(v23 - 13) <= 1u )
  {
    v25 = 0;
    v64 = 0;
    Srca = 0;
    v66 = 0;
    if ( v23 <= 3u )
    {
      v26 = Src + 8;
LABEL_10:
      Size = 8;
      goto LABEL_11;
    }
    if ( (unsigned __int8)(v23 - 9) <= 1u )
    {
LABEL_79:
      v26 = Src + 8;
      Srca = &Src[4 * Src[9] + 16];
      v66 = v24 - (4 * Src[9] + 8) - 8;
      goto LABEL_10;
    }
    if ( v23 >= 0xDu )
    {
      if ( v23 <= 0xEu )
        goto LABEL_79;
LABEL_82:
      v47 = 16LL * (*((_DWORD *)Src + 2) & 1);
      v48 = (*((_DWORD *)Src + 2) & 2) != 0 ? 0x10 : 0;
      v26 = &Src[v48 + 12 + v47];
      v49 = v47 + v48 + 12;
      Size = v49;
      if ( (*((_DWORD *)Src + 2) & 2) != 0 )
      {
        if ( (*((_DWORD *)Src + 2) & 1) != 0 )
          v50 = (char *)(Src + 28);
        else
          v50 = (char *)(Src + 12);
      }
      else
      {
        v50 = 0;
      }
      if ( a14 && v50 )
      {
        if ( a9 )
        {
          for ( i = 0; i < a10; ++i )
          {
            v59 = *(_QWORD **)(a9 + 8LL * i);
            v60 = *(_QWORD *)v50 - *v59;
            if ( *(_QWORD *)v50 == *v59 )
              v60 = *((_QWORD *)v50 + 1) - v59[1];
            if ( !v60 )
            {
              *a14 = 1;
              if ( a3 )
              {
                v25 = 1;
                goto LABEL_86;
              }
              *a15 = 1;
              if ( (Src[8] & 1) != 0 )
              {
                LODWORD(v24) = v24 - 16;
                Size = v49 - 16;
                memmove(v73, Src, v49 - 16);
                v74 &= ~2u;
                v27 = (unsigned __int8 *)v73;
                v18 = a16;
                v22 = a15;
                v65 = (unsigned __int8 *)v73;
              }
              else
              {
                LODWORD(v24) = v24 - 20;
                Size = v49 - 20;
                memmove(v73, Src, v49 - 20);
                v18 = a16;
                v27 = (unsigned __int8 *)v73;
                v22 = a15;
                v65 = (unsigned __int8 *)v73;
                v73[0] = *((_BYTE *)RtlBaseAceType + *Src);
              }
              goto LABEL_12;
            }
          }
        }
        LODWORD(v24) = 0;
        goto LABEL_52;
      }
LABEL_86:
      v18 = a16;
      v22 = a15;
LABEL_11:
      v65 = Src;
      v27 = Src;
LABEL_12:
      if ( !(_DWORD)v24 )
        goto LABEL_44;
      v28 = *((_DWORD *)Src + 1);
      v29 = v28;
      if ( v28 < 0 )
        v29 = *a8 | v28;
      if ( (v29 & 0x40000000) != 0 )
        v29 |= a8[1];
      if ( (v29 & 0x20000000) != 0 )
        v29 |= a8[2];
      if ( (v29 & 0x10000000) != 0 )
        v29 |= a8[3];
      v30 = *Src;
      if ( (unsigned __int8)v30 <= 0xAu && (v31 = 1651, _bittest(&v31, v30)) )
        v32 = a8[3] & v29 & 0xFFFFFFF;
      else
        v32 = (a8[3] & 0xEFFFFFF | 0x1000000) & v29;
      if ( v32 != v28 )
        *v22 = 1;
      v33 = v32 & 0x11FFFFF;
      if ( !v33 )
      {
        if ( !(unsigned __int8)RtlEqualPrefixSid(v26, &v71, v22) )
        {
          LODWORD(v24) = 0;
LABEL_43:
          v18 = a16;
LABEL_44:
          v17 = a2;
          goto LABEL_45;
        }
        v27 = v65;
      }
      if ( *v26 == 1 && !v26[2] && !v26[3] && !v26[4] && !v26[5] && !v26[6] && v26[7] == 3 )
      {
        v40 = v26[1];
        if ( (_BYTE)v40 == 1 )
        {
          for ( j = 0; j < v40 - 1; ++j )
          {
            if ( *(_DWORD *)&v26[4 * j + 8] != *((_DWORD *)v72 + j + 1) )
              goto LABEL_34;
          }
          v42 = *((_DWORD *)v26 + 2);
          if ( !v42 )
          {
            v43 = (__int64)a4;
LABEL_60:
            v26 = (unsigned __int8 *)v43;
            v44 = v24 + 4 * *(unsigned __int8 *)(v43 + 1);
            v34 = a15;
            LODWORD(v24) = v44 - 4;
            *a15 = 1;
LABEL_35:
            if ( v25 && *v34 )
            {
              v61 = Size;
              if ( (Src[8] & 1) != 0 )
              {
                LODWORD(v24) = v24 - 16;
                Size -= 16;
                memmove(v73, Src, v61 - 16);
                v74 &= ~2u;
              }
              else
              {
                LODWORD(v24) = v24 - 20;
                Size -= 20;
                memmove(v73, Src, v61 - 20);
                v73[0] = *((_BYTE *)RtlBaseAceType + *Src);
              }
              v27 = (unsigned __int8 *)v73;
            }
            v35 = (char *)*a11;
            if ( !*a11 || (unsigned int)v24 > a13 + *(unsigned __int16 *)(a13 + 2) - (_QWORD)v35 )
            {
              v18 = a16;
              *a16 = 1;
              goto LABEL_50;
            }
            memmove(*a11, v27, Size);
            v36 = &v35[Size];
            if ( v64 )
            {
              memmove(v36, v64, 4LL * v64[1] + 8);
              v36 += 4 * v64[1] + 8;
            }
            memmove(v36, v26, 4LL * v26[1] + 8);
            v37 = &v36[4 * v26[1] + 8];
            if ( Srca && v66 > 0 )
            {
              memmove(v37, Srca, v66);
              LODWORD(v37) = v66 + (_DWORD)v37;
            }
            v38 = (_DWORD)v37 - *(_DWORD *)a11;
            if ( (unsigned int)v24 < v38 )
              return 0;
            LODWORD(v24) = v38;
            *((_WORD *)*a11 + 1) = v38;
            *((_DWORD *)*a11 + 1) = v33;
            goto LABEL_43;
          }
          v45 = v42 - 1;
          if ( v45 )
          {
            v46 = v45 - 1;
            if ( !v46 )
            {
              v43 = (__int64)v68;
              goto LABEL_60;
            }
            if ( v46 == 1 )
            {
              v43 = (__int64)v67;
              goto LABEL_60;
            }
          }
          else
          {
            v43 = (__int64)a5;
            if ( a5 )
              goto LABEL_60;
          }
        }
      }
LABEL_34:
      v34 = a15;
      goto LABEL_35;
    }
    if ( v23 != 4 )
      goto LABEL_82;
    v64 = Src + 12;
    v51 = 4 * Src[13];
    v26 = &Src[v51 + 8 + 12];
    if ( !(unsigned __int8)RtlEqualPrefixSid(Src + 12, &v71, a15) )
    {
      v22 = a15;
      Size = v51 + 20;
      v64 = 0;
      goto LABEL_103;
    }
    Size = 12;
    v52 = *((_DWORD *)Src + 5);
    if ( v52 )
    {
      v53 = v52 - 1;
      if ( v53 )
      {
        v54 = v53 - 1;
        if ( !v54 )
        {
          v22 = a15;
          v64 = v68;
          v56 = v68[1];
          *a15 = 1;
          LODWORD(v24) = v24 + 4 * v56 - 4;
          goto LABEL_103;
        }
        if ( v54 == 1 )
        {
          v64 = v67;
          v55 = v67[1];
LABEL_96:
          v22 = a15;
          LODWORD(v24) = v24 + 4 * v55 - 4;
          *a15 = 1;
LABEL_103:
          v18 = a16;
          v25 = 0;
          goto LABEL_11;
        }
      }
      else if ( a5 )
      {
        v22 = a15;
        v64 = a5;
        v57 = a5[1];
        *a15 = 1;
        LODWORD(v24) = v24 + 4 * v57 - 4;
        goto LABEL_103;
      }
      v22 = a15;
      if ( !*a15 )
      {
        v64 = 0;
        Size = v51 + 20;
      }
      goto LABEL_103;
    }
    v64 = a4;
    v55 = a4[1];
    goto LABEL_96;
  }
  if ( v24 > a13 + *(unsigned __int16 *)(a13 + 2) - (_QWORD)*a11 )
  {
    *a16 = 1;
    goto LABEL_50;
  }
  memmove(*a11, Src, *((unsigned __int16 *)Src + 1));
LABEL_45:
  if ( !*v18 && (_DWORD)v24 )
  {
    *((_BYTE *)*a11 + 1) &= 0xE0u;
    if ( v17 )
      *((_BYTE *)*a11 + 1) |= 0x10u;
    ++*(_WORD *)(a13 + 4);
  }
LABEL_50:
  if ( (unsigned int)v24 <= 0xFFFF )
  {
    if ( *v18 )
    {
LABEL_53:
      *a12 = v24;
      return 1;
    }
LABEL_52:
    *a11 = (char *)*a11 + (unsigned int)v24;
    goto LABEL_53;
  }
  return 0;
}

```

## disassembly

```asm
0x1800af7d0  push    rbp
0x1800af7d2  push    rbx
0x1800af7d3  push    rsi
0x1800af7d4  push    rdi
0x1800af7d5  push    r12
0x1800af7d7  push    r13
0x1800af7d9  push    r15
0x1800af7db  lea     rbp, [rsp-7]
0x1800af7e0  sub     rsp, 0E0h
0x1800af7e7  mov     rax, cs:__security_cookie
0x1800af7ee  xor     rax, rsp
0x1800af7f1  mov     [rbp+37h+var_38], rax
0x1800af7f5  mov     r11, [rbp+37h+arg_30]
0x1800af7f9  mov     rax, r9
0x1800af7fc  mov     r9, [rbp+37h+arg_68]
0x1800af803  movzx   esi, dl
0x1800af806  mov     rbx, [rbp+37h+arg_78]
0x1800af80d  movzx   r10d, r8b
0x1800af811  mov     r8, [rbp+37h+arg_58]
0x1800af818  mov     rdi, rcx
0x1800af81b  mov     rcx, [rbp+37h+arg_20]
0x1800af81f  mov     r12, [rbp+37h+arg_50]
0x1800af826  mov     r13, [rbp+37h+arg_60]
0x1800af82d  mov     [rsp+110h+var_F0], dl
0x1800af831  mov     rdx, [rbp+37h+arg_28]
0x1800af835  test    rdx, rdx
0x1800af838  mov     [rbp+37h+var_90], r8
0x1800af83c  mov     r8, [rbp+37h+arg_70]
0x1800af843  cmovz   rdx, rax
0x1800af847  mov     [rbp+37h+var_A0], rax
0x1800af84b  test    r11, r11
0x1800af84e  mov     [rbp+37h+var_A8], rcx
0x1800af852  mov     [rsp+110h+var_E8], r8
0x1800af857  cmovz   r11, rcx
0x1800af85b  mov     [rsp+110h+var_D8], rbx
0x1800af860  mov     [rsp+110h+var_B8], r11
0x1800af865  mov     [rbp+37h+var_88], 101h
0x1800af86c  mov     [rbp+37h+var_84], 3000000h
0x1800af874  mov     [rbp+37h+var_B0], rdx
0x1800af878  mov     byte ptr [r8], 0
0x1800af87c  test    r9, r9
0x1800af87f  jz      short loc_1800AF885
0x1800af881  mov     byte ptr [r9], 0
0x1800af885  mov     byte ptr [rbx], 0
0x1800af888  movzx   ecx, byte ptr [rdi]
0x1800af88b  movzx   r15d, word ptr [rdi+2]
0x1800af890  mov     [rsp+110h+arg_8], r14
0x1800af898  cmp     cl, 0Bh
0x1800af89b  jnb     loc_1800AFB66
0x1800af8a1  xor     eax, eax
0x1800af8a3  xor     r14b, r14b
0x1800af8a6  mov     [rsp+110h+var_D0], rax
0x1800af8ab  mov     [rbp+37h+Src], rax
0x1800af8af  mov     [rsp+110h+var_C0], eax
0x1800af8b3  cmp     cl, 3
0x1800af8b6  ja      loc_1800AFB9D
0x1800af8bc  lea     rsi, [rdi+8]
0x1800af8c0  mov     dword ptr [rsp+110h+Size], 8
0x1800af8c8  mov     [rsp+110h+var_C8], rdi
0x1800af8cd  mov     r9, rdi
0x1800af8d0  test    r15d, r15d
0x1800af8d3  jz      loc_1800AFA12
0x1800af8d9  mov     edx, [rdi+4]
0x1800af8dc  mov     ebx, edx
0x1800af8de  mov     rcx, [rbp+37h+arg_38]
0x1800af8e2  test    edx, edx
0x1800af8e4  jns     short loc_1800AF8E8
0x1800af8e6  or      ebx, [rcx]
0x1800af8e8  bt      ebx, 1Eh
0x1800af8ec  jnb     short loc_1800AF8F1
0x1800af8ee  or      ebx, [rcx+4]
0x1800af8f1  bt      ebx, 1Dh
0x1800af8f5  jnb     short loc_1800AF8FA
0x1800af8f7  or      ebx, [rcx+8]
0x1800af8fa  bt      ebx, 1Ch
0x1800af8fe  jnb     short loc_1800AF903
0x1800af900  or      ebx, [rcx+0Ch]
0x1800af903  movzx   eax, byte ptr [rdi]
0x1800af906  cmp     al, 0Ah
0x1800af908  ja      loc_1800AFB24
0x1800af90e  mov     r10d, 673h
0x1800af914  bt      r10d, eax
0x1800af918  jnb     loc_1800AFB24
0x1800af91e  and     ebx, [rcx+0Ch]
0x1800af921  and     ebx, 0FFFFFFFh
0x1800af927  cmp     ebx, edx
0x1800af929  jz      short loc_1800AF92F
0x1800af92b  mov     byte ptr [r8], 1
0x1800af92f  and     ebx, 11FFFFFh
0x1800af935  jz      loc_1800AFB0C
0x1800af93b  cmp     byte ptr [rsi], 1
0x1800af93e  jnz     short loc_1800AF968
0x1800af940  cmp     byte ptr [rsi+2], 0
0x1800af944  jnz     short loc_1800AF968
0x1800af946  cmp     byte ptr [rsi+3], 0
0x1800af94a  jnz     short loc_1800AF968
0x1800af94c  cmp     byte ptr [rsi+4], 0
0x1800af950  jnz     short loc_1800AF968
0x1800af952  cmp     byte ptr [rsi+5], 0
0x1800af956  jnz     short loc_1800AF968
0x1800af958  cmp     byte ptr [rsi+6], 0
0x1800af95c  jnz     short loc_1800AF968
0x1800af95e  cmp     byte ptr [rsi+7], 3
0x1800af962  jz      loc_1800AFA84
0x1800af968  mov     rax, [rsp+110h+var_E8]
0x1800af96d  test    r14b, r14b
0x1800af970  jnz     loc_1800AFE55
0x1800af976  mov     r14, [r12]
0x1800af97a  test    r14, r14
0x1800af97d  jz      loc_1800AFAC6
0x1800af983  movzx   ecx, word ptr [r13+2]
0x1800af988  sub     rcx, r14
0x1800af98b  mov     eax, r15d
0x1800af98e  add     rcx, r13
0x1800af991  cmp     rax, rcx
0x1800af994  jg      loc_1800AFAC6
0x1800af99a  mov     edi, dword ptr [rsp+110h+Size]
0x1800af99e  mov     rdx, r9; Src
0x1800af9a1  mov     r8d, edi; Size
0x1800af9a4  mov     rcx, r14; void *
0x1800af9a7  call    memmove
0x1800af9ac  add     rdi, r14
0x1800af9af  mov     r14, [rsp+110h+var_D0]
0x1800af9b4  test    r14, r14
0x1800af9b7  jnz     loc_1800AFEB5
0x1800af9bd  movzx   r8d, byte ptr [rsi+1]
0x1800af9c2  mov     rdx, rsi; Src
0x1800af9c5  mov     rcx, rdi; void *
0x1800af9c8  lea     r8, ds:8[r8*4]; Size
0x1800af9d0  call    memmove
0x1800af9d5  movzx   esi, byte ptr [rsi+1]
0x1800af9d9  mov     rdx, [rbp+37h+Src]; Src
0x1800af9dd  add     rsi, 2
0x1800af9e1  lea     rsi, [rdi+rsi*4]
0x1800af9e5  test    rdx, rdx
0x1800af9e8  jnz     loc_1800AFAE9
0x1800af9ee  sub     esi, [r12]
0x1800af9f2  cmp     r15d, esi
0x1800af9f5  jb      loc_1800AFA80
0x1800af9fb  mov     rax, [r12]
0x1800af9ff  mov     r15d, esi
0x1800afa02  mov     [rax+2], si
0x1800afa06  mov     rax, [r12]
0x1800afa0a  mov     [rax+4], ebx
0x1800afa0d  mov     rbx, [rsp+110h+var_D8]
0x1800afa12  movzx   esi, [rsp+110h+var_F0]
0x1800afa17  cmp     byte ptr [rbx], 0
0x1800afa1a  jnz     short loc_1800AFA3B
0x1800afa1c  test    r15d, r15d
0x1800afa1f  jz      short loc_1800AFA3B
0x1800afa21  mov     rax, [r12]
0x1800afa25  and     byte ptr [rax+1], 0E0h
0x1800afa29  test    sil, sil
0x1800afa2c  jz      short loc_1800AFA36
0x1800afa2e  mov     rax, [r12]
0x1800afa32  or      byte ptr [rax+1], 10h
0x1800afa36  inc     word ptr [r13+4]
0x1800afa3b  cmp     r15d, 0FFFFh
0x1800afa42  ja      short loc_1800AFA80
0x1800afa44  cmp     byte ptr [rbx], 0
0x1800afa47  jnz     short loc_1800AFA50
0x1800afa49  mov     eax, r15d
0x1800afa4c  add     [r12], rax
0x1800afa50  mov     rax, [rbp+37h+var_90]
0x1800afa54  mov     [rax], r15d
0x1800afa57  mov     al, 1
0x1800afa59  mov     r14, [rsp+110h+arg_8]
0x1800afa61  mov     rcx, [rbp+37h+var_38]
0x1800afa65  xor     rcx, rsp; StackCookie
0x1800afa68  call    __security_check_cookie
0x1800afa6d  add     rsp, 0E0h
0x1800afa74  pop     r15
0x1800afa76  pop     r13
0x1800afa78  pop     r12
0x1800afa7a  pop     rdi
0x1800afa7b  pop     rsi
0x1800afa7c  pop     rbx
0x1800afa7d  pop     rbp
0x1800afa7e  retn
0x1800afa80  xor     al, al
0x1800afa82  jmp     short loc_1800AFA59
0x1800afa84  movzx   eax, byte ptr [rsi+1]
0x1800afa88  cmp     al, 1
0x1800afa8a  jnz     loc_1800AF968
0x1800afa90  xor     r8d, r8d
0x1800afa93  lea     edx, [rax-1]
0x1800afa96  cmp     r8d, edx
0x1800afa99  jl      short loc_1800AFAD3
0x1800afa9b  mov     eax, [rsi+8]
0x1800afa9e  test    eax, eax
0x1800afaa0  jnz     loc_1800AFB41
0x1800afaa6  mov     rax, [rbp+37h+var_A0]
0x1800afaaa  mov     rsi, rax
0x1800afaad  movzx   eax, byte ptr [rax+1]
0x1800afab1  lea     r15d, [r15+rax*4]
0x1800afab5  mov     rax, [rsp+110h+var_E8]
0x1800afaba  add     r15d, 0FFFFFFFCh
0x1800afabe  mov     byte ptr [rax], 1
0x1800afac1  jmp     loc_1800AF96D
0x1800afac6  mov     rbx, [rsp+110h+var_D8]
0x1800afacb  mov     byte ptr [rbx], 1
0x1800aface  jmp     loc_1800AFA3B
0x1800afad3  movsxd  rcx, r8d
0x1800afad6  mov     eax, dword ptr [rbp+rcx*4+37h+var_84+4]
0x1800afada  cmp     [rsi+rcx*4+8], eax
0x1800afade  jnz     loc_1800AF968
0x1800afae4  inc     r8d
0x1800afae7  jmp     short loc_1800AFA96
0x1800afae9  movsxd  rax, [rsp+110h+var_C0]
0x1800afaee  test    eax, eax
0x1800afaf0  jle     loc_1800AF9EE
0x1800afaf6  mov     r8, rax; Size
0x1800afaf9  mov     rcx, rsi; void *
0x1800afafc  mov     rdi, rax
0x1800afaff  call    memmove
0x1800afb04  add     rsi, rdi
0x1800afb07  jmp     loc_1800AF9EE
0x1800afb0c  lea     rdx, [rbp+37h+var_88]
0x1800afb10  mov     rcx, rsi
0x1800afb13  call    RtlEqualPrefixSid
0x1800afb18  test    al, al
0x1800afb1a  jnz     short loc_1800AFB37
0x1800afb1c  xor     r15d, r15d
0x1800afb1f  jmp     loc_1800AFA0D
0x1800afb24  mov     eax, [rcx+0Ch]
0x1800afb27  and     eax, 0EFFFFFFh
0x1800afb2c  bts     eax, 18h
0x1800afb30  and     ebx, eax
0x1800afb32  jmp     loc_1800AF927
0x1800afb37  mov     r9, [rsp+110h+var_C8]
0x1800afb3c  jmp     loc_1800AF93B
0x1800afb41  sub     eax, 1
0x1800afb44  jz      loc_1800AFE43
0x1800afb4a  sub     eax, 1
0x1800afb4d  jz      loc_1800AFE3A
0x1800afb53  cmp     eax, 1
0x1800afb56  jnz     loc_1800AF968
0x1800afb5c  mov     rax, [rsp+110h+var_B8]
0x1800afb61  jmp     loc_1800AFAAA
0x1800afb66  lea     eax, [rcx-0Dh]
0x1800afb69  cmp     al, 1
0x1800afb6b  jbe     loc_1800AF8A1
0x1800afb71  mov     rcx, [r12]; void *
0x1800afb75  mov     r8, r15; Size
0x1800afb78  movzx   eax, word ptr [r13+2]
0x1800afb7d  sub     rax, rcx
0x1800afb80  add     rax, r13
0x1800afb83  cmp     r15, rax
0x1800afb86  jg      short loc_1800AFB95
0x1800afb88  mov     rdx, rdi; Src
0x1800afb8b  call    memmove
0x1800afb90  jmp     loc_1800AFA17
0x1800afb95  mov     byte ptr [rbx], 1
0x1800afb98  jmp     loc_1800AFA3B
0x1800afb9d  lea     eax, [rcx-9]
0x1800afba0  cmp     al, 1
0x1800afba2  ja      short loc_1800AFBCD
0x1800afba4  movzx   eax, byte ptr [rdi+9]
0x1800afba8  lea     rsi, [rdi+8]
0x1800afbac  lea     eax, ds:8[rax*4]
0x1800afbb3  mov     ecx, eax
0x1800afbb5  add     rcx, rsi
0x1800afbb8  mov     [rbp+37h+Src], rcx
0x1800afbbc  mov     ecx, r15d
0x1800afbbf  sub     ecx, eax
0x1800afbc1  sub     ecx, 8
0x1800afbc4  mov     [rsp+110h+var_C0], ecx
0x1800afbc8  jmp     loc_1800AF8C0
0x1800afbcd  cmp     cl, 0Dh
0x1800afbd0  jnb     short loc_1800AFC34
0x1800afbd2  cmp     cl, 4
0x1800afbd5  jz      short loc_1800AFC3E
0x1800afbd7  mov     r8d, [rdi+8]
0x1800afbdb  lea     rsi, [rdi+0Ch]
0x1800afbdf  mov     r11d, r8d
0x1800afbe2  and     r8d, 2
0x1800afbe6  and     r11d, 1
0x1800afbea  mov     eax, r8d
0x1800afbed  neg     eax
0x1800afbef  mov     ecx, r11d
0x1800afbf2  sbb     rdx, rdx
0x1800afbf5  shl     rcx, 4
0x1800afbf9  and     edx, 10h
0x1800afbfc  xor     eax, eax
0x1800afbfe  add     rsi, rdx
0x1800afc01  add     rsi, rcx
0x1800afc04  mov     ebx, esi
0x1800afc06  sub     ebx, edi
0x1800afc08  mov     dword ptr [rsp+110h+Size], ebx
0x1800afc0c  test    r8d, r8d
0x1800afc0f  jnz     loc_1800AFD47
0x1800afc15  mov     ecx, eax
0x1800afc17  test    r9, r9
0x1800afc1a  jz      short loc_1800AFC25
0x1800afc1c  test    rcx, rcx
0x1800afc1f  jnz     loc_1800AFD5E
0x1800afc25  mov     rbx, [rsp+110h+var_D8]
0x1800afc2a  mov     r8, [rsp+110h+var_E8]
0x1800afc2f  jmp     loc_1800AF8C8
0x1800afc34  cmp     cl, 0Eh
  ... truncated ...
```
