# RtlpCopyEffectiveAce

- ea: `0x18003aad0`
- end: `0x18003b1df`
- name: `RtlpCopyEffectiveAce`
- size: `1807`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, __int64, __int64, __int64, __int64, __int64, int, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18003a620`
- `0x18003b1f0`

## callees

- `0x180039cd0`
- `0x18003aad0`
- `0x180162810`
- `0x180164280`

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
0x18003aad0  push    rbp
0x18003aad2  push    rbx
0x18003aad3  push    rsi
0x18003aad4  push    rdi
0x18003aad5  push    r12
0x18003aad7  push    r13
0x18003aad9  push    r15
0x18003aadb  lea     rbp, [rsp-7]
0x18003aae0  sub     rsp, 0E0h
0x18003aae7  mov     rax, cs:__security_cookie
0x18003aaee  xor     rax, rsp
0x18003aaf1  mov     [rbp+37h+var_38], rax
0x18003aaf5  mov     r11, [rbp+37h+arg_30]
0x18003aaf9  mov     rax, r9
0x18003aafc  mov     r9, [rbp+37h+arg_68]
0x18003ab03  movzx   esi, dl
0x18003ab06  mov     rbx, [rbp+37h+arg_78]
0x18003ab0d  movzx   r10d, r8b
0x18003ab11  mov     r8, [rbp+37h+arg_58]
0x18003ab18  mov     rdi, rcx
0x18003ab1b  mov     rcx, [rbp+37h+arg_20]
0x18003ab1f  mov     r12, [rbp+37h+arg_50]
0x18003ab26  mov     r13, [rbp+37h+arg_60]
0x18003ab2d  mov     [rsp+110h+var_F0], dl
0x18003ab31  mov     rdx, [rbp+37h+arg_28]
0x18003ab35  test    rdx, rdx
0x18003ab38  mov     [rbp+37h+var_90], r8
0x18003ab3c  mov     r8, [rbp+37h+arg_70]
0x18003ab43  cmovz   rdx, rax
0x18003ab47  mov     [rbp+37h+var_A0], rax
0x18003ab4b  test    r11, r11
0x18003ab4e  mov     [rbp+37h+var_A8], rcx
0x18003ab52  mov     [rsp+110h+var_E8], r8
0x18003ab57  cmovz   r11, rcx
0x18003ab5b  mov     [rsp+110h+var_D8], rbx
0x18003ab60  mov     [rsp+110h+var_B8], r11
0x18003ab65  mov     [rbp+37h+var_88], 101h
0x18003ab6c  mov     [rbp+37h+var_84], 3000000h
0x18003ab74  mov     [rbp+37h+var_B0], rdx
0x18003ab78  mov     byte ptr [r8], 0
0x18003ab7c  test    r9, r9
0x18003ab7f  jz      short loc_18003AB85
0x18003ab81  mov     byte ptr [r9], 0
0x18003ab85  mov     byte ptr [rbx], 0
0x18003ab88  movzx   ecx, byte ptr [rdi]
0x18003ab8b  movzx   r15d, word ptr [rdi+2]
0x18003ab90  mov     [rsp+110h+arg_8], r14
0x18003ab98  cmp     cl, 0Bh
0x18003ab9b  jnb     loc_18003AE66
0x18003aba1  xor     eax, eax
0x18003aba3  xor     r14b, r14b
0x18003aba6  mov     [rsp+110h+var_D0], rax
0x18003abab  mov     [rbp+37h+Src], rax
0x18003abaf  mov     [rsp+110h+var_C0], eax
0x18003abb3  cmp     cl, 3
0x18003abb6  ja      loc_18003AE9D
0x18003abbc  lea     rsi, [rdi+8]
0x18003abc0  mov     dword ptr [rsp+110h+Size], 8
0x18003abc8  mov     [rsp+110h+var_C8], rdi
0x18003abcd  mov     r9, rdi
0x18003abd0  test    r15d, r15d
0x18003abd3  jz      loc_18003AD12
0x18003abd9  mov     edx, [rdi+4]
0x18003abdc  mov     ebx, edx
0x18003abde  mov     rcx, [rbp+37h+arg_38]
0x18003abe2  test    edx, edx
0x18003abe4  jns     short loc_18003ABE8
0x18003abe6  or      ebx, [rcx]
0x18003abe8  bt      ebx, 1Eh
0x18003abec  jnb     short loc_18003ABF1
0x18003abee  or      ebx, [rcx+4]
0x18003abf1  bt      ebx, 1Dh
0x18003abf5  jnb     short loc_18003ABFA
0x18003abf7  or      ebx, [rcx+8]
0x18003abfa  bt      ebx, 1Ch
0x18003abfe  jnb     short loc_18003AC03
0x18003ac00  or      ebx, [rcx+0Ch]
0x18003ac03  movzx   eax, byte ptr [rdi]
0x18003ac06  cmp     al, 0Ah
0x18003ac08  ja      loc_18003AE24
0x18003ac0e  mov     r10d, 673h
0x18003ac14  bt      r10d, eax
0x18003ac18  jnb     loc_18003AE24
0x18003ac1e  and     ebx, [rcx+0Ch]
0x18003ac21  and     ebx, 0FFFFFFFh
0x18003ac27  cmp     ebx, edx
0x18003ac29  jz      short loc_18003AC2F
0x18003ac2b  mov     byte ptr [r8], 1
0x18003ac2f  and     ebx, 11FFFFFh
0x18003ac35  jz      loc_18003AE0C
0x18003ac3b  cmp     byte ptr [rsi], 1
0x18003ac3e  jnz     short loc_18003AC68
0x18003ac40  cmp     byte ptr [rsi+2], 0
0x18003ac44  jnz     short loc_18003AC68
0x18003ac46  cmp     byte ptr [rsi+3], 0
0x18003ac4a  jnz     short loc_18003AC68
0x18003ac4c  cmp     byte ptr [rsi+4], 0
0x18003ac50  jnz     short loc_18003AC68
0x18003ac52  cmp     byte ptr [rsi+5], 0
0x18003ac56  jnz     short loc_18003AC68
0x18003ac58  cmp     byte ptr [rsi+6], 0
0x18003ac5c  jnz     short loc_18003AC68
0x18003ac5e  cmp     byte ptr [rsi+7], 3
0x18003ac62  jz      loc_18003AD84
0x18003ac68  mov     rax, [rsp+110h+var_E8]
0x18003ac6d  test    r14b, r14b
0x18003ac70  jnz     loc_18003B155
0x18003ac76  mov     r14, [r12]
0x18003ac7a  test    r14, r14
0x18003ac7d  jz      loc_18003ADC6
0x18003ac83  movzx   ecx, word ptr [r13+2]
0x18003ac88  sub     rcx, r14
0x18003ac8b  mov     eax, r15d
0x18003ac8e  add     rcx, r13
0x18003ac91  cmp     rax, rcx
0x18003ac94  jg      loc_18003ADC6
0x18003ac9a  mov     edi, dword ptr [rsp+110h+Size]
0x18003ac9e  mov     rdx, r9; Src
0x18003aca1  mov     r8d, edi; Size
0x18003aca4  mov     rcx, r14; void *
0x18003aca7  call    memmove
0x18003acac  add     rdi, r14
0x18003acaf  mov     r14, [rsp+110h+var_D0]
0x18003acb4  test    r14, r14
0x18003acb7  jnz     loc_18003B1B5
0x18003acbd  movzx   r8d, byte ptr [rsi+1]
0x18003acc2  mov     rdx, rsi; Src
0x18003acc5  mov     rcx, rdi; void *
0x18003acc8  lea     r8, ds:8[r8*4]; Size
0x18003acd0  call    memmove
0x18003acd5  movzx   esi, byte ptr [rsi+1]
0x18003acd9  mov     rdx, [rbp+37h+Src]; Src
0x18003acdd  add     rsi, 2
0x18003ace1  lea     rsi, [rdi+rsi*4]
0x18003ace5  test    rdx, rdx
0x18003ace8  jnz     loc_18003ADE9
0x18003acee  sub     esi, [r12]
0x18003acf2  cmp     r15d, esi
0x18003acf5  jb      loc_18003AD80
0x18003acfb  mov     rax, [r12]
0x18003acff  mov     r15d, esi
0x18003ad02  mov     [rax+2], si
0x18003ad06  mov     rax, [r12]
0x18003ad0a  mov     [rax+4], ebx
0x18003ad0d  mov     rbx, [rsp+110h+var_D8]
0x18003ad12  movzx   esi, [rsp+110h+var_F0]
0x18003ad17  cmp     byte ptr [rbx], 0
0x18003ad1a  jnz     short loc_18003AD3B
0x18003ad1c  test    r15d, r15d
0x18003ad1f  jz      short loc_18003AD3B
0x18003ad21  mov     rax, [r12]
0x18003ad25  and     byte ptr [rax+1], 0E0h
0x18003ad29  test    sil, sil
0x18003ad2c  jz      short loc_18003AD36
0x18003ad2e  mov     rax, [r12]
0x18003ad32  or      byte ptr [rax+1], 10h
0x18003ad36  inc     word ptr [r13+4]
0x18003ad3b  cmp     r15d, 0FFFFh
0x18003ad42  ja      short loc_18003AD80
0x18003ad44  cmp     byte ptr [rbx], 0
0x18003ad47  jnz     short loc_18003AD50
0x18003ad49  mov     eax, r15d
0x18003ad4c  add     [r12], rax
0x18003ad50  mov     rax, [rbp+37h+var_90]
0x18003ad54  mov     [rax], r15d
0x18003ad57  mov     al, 1
0x18003ad59  mov     r14, [rsp+110h+arg_8]
0x18003ad61  mov     rcx, [rbp+37h+var_38]
0x18003ad65  xor     rcx, rsp; StackCookie
0x18003ad68  call    __security_check_cookie
0x18003ad6d  add     rsp, 0E0h
0x18003ad74  pop     r15
0x18003ad76  pop     r13
0x18003ad78  pop     r12
0x18003ad7a  pop     rdi
0x18003ad7b  pop     rsi
0x18003ad7c  pop     rbx
0x18003ad7d  pop     rbp
0x18003ad7e  retn
0x18003ad80  xor     al, al
0x18003ad82  jmp     short loc_18003AD59
0x18003ad84  movzx   eax, byte ptr [rsi+1]
0x18003ad88  cmp     al, 1
0x18003ad8a  jnz     loc_18003AC68
0x18003ad90  xor     r8d, r8d
0x18003ad93  lea     edx, [rax-1]
0x18003ad96  cmp     r8d, edx
0x18003ad99  jl      short loc_18003ADD3
0x18003ad9b  mov     eax, [rsi+8]
0x18003ad9e  test    eax, eax
0x18003ada0  jnz     loc_18003AE41
0x18003ada6  mov     rax, [rbp+37h+var_A0]
0x18003adaa  mov     rsi, rax
0x18003adad  movzx   eax, byte ptr [rax+1]
0x18003adb1  lea     r15d, [r15+rax*4]
0x18003adb5  mov     rax, [rsp+110h+var_E8]
0x18003adba  add     r15d, 0FFFFFFFCh
0x18003adbe  mov     byte ptr [rax], 1
0x18003adc1  jmp     loc_18003AC6D
0x18003adc6  mov     rbx, [rsp+110h+var_D8]
0x18003adcb  mov     byte ptr [rbx], 1
0x18003adce  jmp     loc_18003AD3B
0x18003add3  movsxd  rcx, r8d
0x18003add6  mov     eax, dword ptr [rbp+rcx*4+37h+var_84+4]
0x18003adda  cmp     [rsi+rcx*4+8], eax
0x18003adde  jnz     loc_18003AC68
0x18003ade4  inc     r8d
0x18003ade7  jmp     short loc_18003AD96
0x18003ade9  movsxd  rax, [rsp+110h+var_C0]
0x18003adee  test    eax, eax
0x18003adf0  jle     loc_18003ACEE
0x18003adf6  mov     r8, rax; Size
0x18003adf9  mov     rcx, rsi; void *
0x18003adfc  mov     rdi, rax
0x18003adff  call    memmove
0x18003ae04  add     rsi, rdi
0x18003ae07  jmp     loc_18003ACEE
0x18003ae0c  lea     rdx, [rbp+37h+var_88]
0x18003ae10  mov     rcx, rsi
0x18003ae13  call    RtlEqualPrefixSid
0x18003ae18  test    al, al
0x18003ae1a  jnz     short loc_18003AE37
0x18003ae1c  xor     r15d, r15d
0x18003ae1f  jmp     loc_18003AD0D
0x18003ae24  mov     eax, [rcx+0Ch]
0x18003ae27  and     eax, 0EFFFFFFh
0x18003ae2c  bts     eax, 18h
0x18003ae30  and     ebx, eax
0x18003ae32  jmp     loc_18003AC27
0x18003ae37  mov     r9, [rsp+110h+var_C8]
0x18003ae3c  jmp     loc_18003AC3B
0x18003ae41  sub     eax, 1
0x18003ae44  jz      loc_18003B143
0x18003ae4a  sub     eax, 1
0x18003ae4d  jz      loc_18003B13A
0x18003ae53  cmp     eax, 1
0x18003ae56  jnz     loc_18003AC68
0x18003ae5c  mov     rax, [rsp+110h+var_B8]
0x18003ae61  jmp     loc_18003ADAA
0x18003ae66  lea     eax, [rcx-0Dh]
0x18003ae69  cmp     al, 1
0x18003ae6b  jbe     loc_18003ABA1
0x18003ae71  mov     rcx, [r12]; void *
0x18003ae75  mov     r8, r15; Size
0x18003ae78  movzx   eax, word ptr [r13+2]
0x18003ae7d  sub     rax, rcx
0x18003ae80  add     rax, r13
0x18003ae83  cmp     r15, rax
0x18003ae86  jg      short loc_18003AE95
0x18003ae88  mov     rdx, rdi; Src
0x18003ae8b  call    memmove
0x18003ae90  jmp     loc_18003AD17
0x18003ae95  mov     byte ptr [rbx], 1
0x18003ae98  jmp     loc_18003AD3B
0x18003ae9d  lea     eax, [rcx-9]
0x18003aea0  cmp     al, 1
0x18003aea2  ja      short loc_18003AECD
0x18003aea4  movzx   eax, byte ptr [rdi+9]
0x18003aea8  lea     rsi, [rdi+8]
0x18003aeac  lea     eax, ds:8[rax*4]
0x18003aeb3  mov     ecx, eax
0x18003aeb5  add     rcx, rsi
0x18003aeb8  mov     [rbp+37h+Src], rcx
0x18003aebc  mov     ecx, r15d
0x18003aebf  sub     ecx, eax
0x18003aec1  sub     ecx, 8
0x18003aec4  mov     [rsp+110h+var_C0], ecx
0x18003aec8  jmp     loc_18003ABC0
0x18003aecd  cmp     cl, 0Dh
0x18003aed0  jnb     short loc_18003AF34
0x18003aed2  cmp     cl, 4
0x18003aed5  jz      short loc_18003AF3E
0x18003aed7  mov     r8d, [rdi+8]
0x18003aedb  lea     rsi, [rdi+0Ch]
0x18003aedf  mov     r11d, r8d
0x18003aee2  and     r8d, 2
0x18003aee6  and     r11d, 1
0x18003aeea  mov     eax, r8d
0x18003aeed  neg     eax
0x18003aeef  mov     ecx, r11d
0x18003aef2  sbb     rdx, rdx
0x18003aef5  shl     rcx, 4
0x18003aef9  and     edx, 10h
0x18003aefc  xor     eax, eax
0x18003aefe  add     rsi, rdx
0x18003af01  add     rsi, rcx
0x18003af04  mov     ebx, esi
0x18003af06  sub     ebx, edi
0x18003af08  mov     dword ptr [rsp+110h+Size], ebx
0x18003af0c  test    r8d, r8d
0x18003af0f  jnz     loc_18003B047
0x18003af15  mov     ecx, eax
0x18003af17  test    r9, r9
0x18003af1a  jz      short loc_18003AF25
0x18003af1c  test    rcx, rcx
0x18003af1f  jnz     loc_18003B05E
0x18003af25  mov     rbx, [rsp+110h+var_D8]
0x18003af2a  mov     r8, [rsp+110h+var_E8]
0x18003af2f  jmp     loc_18003ABC8
0x18003af34  cmp     cl, 0Eh
  ... truncated ...
```
