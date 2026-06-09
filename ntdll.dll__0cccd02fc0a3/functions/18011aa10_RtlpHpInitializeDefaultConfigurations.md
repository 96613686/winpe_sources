# RtlpHpInitializeDefaultConfigurations

- ea: `0x18011aa10`
- end: `0x18011b6d9`
- name: `RtlpHpInitializeDefaultConfigurations`
- size: `3273`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800743c0`

## callees

- `0x1800e5d88`
- `0x18011aa10`

## pseudocode

```c
char RtlpHpInitializeDefaultConfigurations()
{
  struct _PEB *v0; // rax
  _DWORD *pShimData; // rdx
  __int64 v2; // r8
  char v3; // r9
  char *v4; // rdx
  __int64 v5; // rbx
  char v6; // si
  int v7; // eax
  bool v8; // al
  bool v9; // r10
  int v10; // eax
  char v11; // al
  char v12; // r10
  char v13; // al
  char v14; // r10
  char v15; // al
  char v16; // r10
  char v17; // al
  char v18; // r10
  int v19; // eax
  char v20; // al
  char v21; // r10
  int v22; // eax
  char v23; // al
  char v24; // r10
  int v25; // eax
  char v26; // r10
  int v27; // eax
  int v28; // eax
  unsigned int v29; // eax
  unsigned __int8 v31; // [rsp+20h] [rbp-69h]

  RtlpHpInitializeHeapPgSampling();
  v0 = NtCurrentPeb();
  pShimData = v0->pShimData;
  if ( !pShimData )
    return (char)v0;
  if ( pShimData[130] >= 0x11C0u )
  {
    if ( pShimData[1136] )
    {
      v2 = (unsigned int)pShimData[1137];
      if ( (_DWORD)v2 )
      {
        v3 = 26;
        v31 = 0;
        v4 = (char *)pShimData + v2;
        LOBYTE(v0) = (unsigned __int8)v4[2] >> 4;
        if ( (_BYTE)v0 == 1 )
        {
          LOBYTE(v0) = 56;
          if ( !v4[3] )
          {
            if ( v4[8] != 21 || *(_WORD *)v4 != 56 || v4[4] != -85 )
              goto LABEL_84;
            if ( !v4[3] )
              goto LABEL_12;
          }
          if ( v4[8] != 21 )
          {
LABEL_12:
            v5 = *((unsigned __int16 *)v4 + 3) - 48LL;
            v6 = 0x80;
            if ( (unsigned __int8)v4[8] < 9u || (v7 = 1, (v4[v5 + 49] & 1) == 0) )
              v7 = 0;
            if ( v7 )
              v31 = v4[40] & 0xF;
            v8 = (unsigned __int8)v4[8] >= 9u && (v4[v5 + 49] & 1) != 0;
            v9 = v8;
            if ( (unsigned __int8)v4[8] < 0xAu || (v10 = 1, (v4[v5 + 49] & 2) == 0) )
              v10 = 0;
            if ( v10 )
              v31 = v31 & 0xF | (16 * ((unsigned __int8)v4[40] >> 4));
            if ( (unsigned __int8)v4[8] >= 0xAu && (v4[v5 + 49] & 2) != 0 )
              v11 = 2;
            else
              v11 = 0;
            v12 = v11 | v9 & 0xFD;
            if ( (unsigned __int8)v4[8] >= 0xBu && (v4[v5 + 49] & 4) != 0 )
              v13 = 4;
            else
              v13 = 0;
            v14 = v13 | v12 & 0xFB;
            if ( (unsigned __int8)v4[8] >= 0xCu && (v4[v5 + 49] & 8) != 0 )
              v15 = 8;
            else
              v15 = 0;
            v16 = v15 | v14 & 0xF7;
            if ( (unsigned __int8)v4[8] >= 0xDu && (v4[v5 + 49] & 0x10) != 0 )
              v17 = 16;
            else
              v17 = 0;
            v18 = v17 | v16 & 0xEF;
            if ( (unsigned __int8)v4[8] < 0xEu || (v19 = 1, (v4[v5 + 49] & 0x20) == 0) )
              v19 = 0;
            if ( v19 )
              v3 = v4[42] & 3 | 0x18;
            if ( (unsigned __int8)v4[8] >= 0xEu && (v4[v5 + 49] & 0x20) != 0 )
              v20 = 32;
            else
              v20 = 0;
            v21 = v20 | v18 & 0xDF;
            if ( (unsigned __int8)v4[8] < 0xFu || (v22 = 1, (v4[v5 + 49] & 0x40) == 0) )
              v22 = 0;
            if ( v22 )
              v3 = v3 & 0xFB | (4 * ((v4[42] & 4) != 0));
            if ( (unsigned __int8)v4[8] >= 0xFu && (v4[v5 + 49] & 0x40) != 0 )
              v23 = 64;
            else
              v23 = 0;
            v24 = v23 | v21 & 0xBF;
            if ( (unsigned __int8)v4[8] < 0x10u || (v25 = 1, v4[v5 + 49] >= 0) )
              v25 = 0;
            if ( v25 )
              v3 = v3 & 0xF7 | (8 * ((v4[42] & 8) != 0));
            if ( (unsigned __int8)v4[8] < 0x10u || v4[v5 + 49] >= 0 )
              v6 = 0;
            v26 = v6 | v24 & 0x7F;
            if ( (unsigned __int8)v4[8] < 0x11u || (v27 = 1, (v4[v5 + 50] & 1) == 0) )
              v27 = 0;
            if ( v27 )
              v3 = v3 & 0xEF | (16 * ((v4[42] & 0x10) != 0));
            if ( (unsigned __int8)v4[8] < 0x12u || (v28 = 1, (v4[v5 + 50] & 2) == 0) )
              v28 = 0;
            if ( v28 )
              v3 = v3 & 0xDF | (32 * ((v4[42] & 0x20) != 0));
            if ( (unsigned __int8)v4[8] < 0x13u || (LODWORD(v0) = 1, (v4[v5 + 50] & 4) == 0) )
              LODWORD(v0) = 0;
            if ( (_DWORD)v0 )
              LOBYTE(v0) = v3 & 0xBF | (((v4[42] & 0x40) != 0) << 6);
            goto LABEL_85;
          }
        }
LABEL_84:
        v26 = 0;
LABEL_85:
        if ( (v26 & 2) == 0 )
          return (char)v0;
        v29 = v31;
        goto LABEL_89;
      }
    }
  }
  if ( (*((_BYTE *)pShimData + 4529) & 2) == 0 )
    return (char)v0;
  v29 = *((unsigned __int8 *)pShimData + 4520);
LABEL_89:
  LODWORD(v0) = v29 >> 4;
  if ( ((unsigned __int8)v0 & 4) != 0 )
    RtlpHpHeapFeatures |= 0x20u;
  return (char)v0;
}

```

## disassembly

```asm
0x18011aa10  push    rbp
0x18011aa12  push    rbx
0x18011aa13  push    rsi
0x18011aa14  push    rdi
0x18011aa15  push    r12
0x18011aa17  push    r13
0x18011aa19  push    r14
0x18011aa1b  push    r15
0x18011aa1d  lea     rbp, [rsp-1Fh]
0x18011aa22  sub     rsp, 0A8h
0x18011aa29  call    RtlpHpInitializeHeapPgSampling
0x18011aa2e  xorps   xmm0, xmm0
0x18011aa31  xor     eax, eax
0x18011aa33  movups  [rbp+57h+var_80], xmm0
0x18011aa37  mov     [rbp+57h+var_50], rax
0x18011aa3b  movups  [rbp+57h+var_70], xmm0
0x18011aa3f  movups  [rbp+57h+var_60], xmm0
0x18011aa43  mov     rax, gs:60h
0x18011aa4c  mov     rdx, [rax+2D8h]
0x18011aa53  test    rdx, rdx
0x18011aa56  jz      loc_18011B6C4
0x18011aa5c  cmp     dword ptr [rdx+208h], 11C0h
0x18011aa66  jb      loc_18011B6A3
0x18011aa6c  cmp     dword ptr [rdx+11C0h], 0
0x18011aa73  jz      loc_18011B6A3
0x18011aa79  mov     r8d, [rdx+11C4h]
0x18011aa80  test    r8d, r8d
0x18011aa83  jz      loc_18011B6A3
0x18011aa89  mov     cl, byte ptr [rbp+57h+var_60+0Bh]
0x18011aa8c  mov     r9b, 0E3h
0x18011aa8f  mov     r13b, byte ptr [rbp+57h+var_60+7]
0x18011aa93  mov     dil, 81h
0x18011aa96  mov     r11b, byte ptr [rbp+57h+var_60+9]
0x18011aa9a  and     r13b, r9b
0x18011aa9d  movups  [rbp+57h+var_98], xmm0
0x18011aaa1  and     byte ptr [rbp+57h+var_98+0Bh], 0FEh
0x18011aaa5  and     r11b, dil
0x18011aaa8  movups  [rbp+57h+var_B8], xmm0
0x18011aaac  xor     esi, esi
0x18011aaae  mov     dword ptr [rbp+57h+var_B8], 110038h
0x18011aab5  and     cl, 0FEh
0x18011aab8  mov     byte ptr [rbp+57h+var_B8+4], 0ABh
0x18011aabc  and     cl, 0FEh
0x18011aabf  mov     byte ptr [rbp+57h+var_B8+8], 15h
0x18011aac3  or      r13b, 3
0x18011aac7  mov     byte ptr [rbp+57h+var_60+0Bh], cl
0x18011aaca  or      r11b, 1
0x18011aace  mov     dword ptr [rbp+57h+var_98], 0FFFF0000h
0x18011aad5  mov     eax, 30h ; '0'
0x18011aada  mov     byte ptr [rbp+57h+var_98+8], sil
0x18011aade  mov     word ptr [rbp+57h+var_B8+6], ax
0x18011aae2  and     r13b, r9b
0x18011aae5  xor     eax, eax
0x18011aae7  mov     byte ptr [rbp+57h+var_98+0Ah], 1Ah
0x18011aaeb  mov     dword ptr [rbp+57h+var_B8+9], eax
0x18011aaee  and     r11b, dil
0x18011aaf1  mov     word ptr [rbp+57h+var_B8+0Dh], ax
0x18011aaf5  xor     r14d, r14d
0x18011aaf8  mov     byte ptr [rbp+57h+var_B8+0Fh], al
0x18011aafb  or      r13b, 3
0x18011aaff  mov     word ptr [rbp+57h+var_98+4], ax
0x18011ab03  or      r11b, 1
0x18011ab07  mov     byte ptr [rbp+57h+var_98+6], al
0x18011ab0a  mov     cl, 11h
0x18011ab0c  mov     al, byte ptr [rbp+57h+var_98+7]
0x18011ab0f  xor     r15d, r15d
0x18011ab12  and     al, r9b
0x18011ab15  shr     cl, 4
0x18011ab18  or      al, 3
0x18011ab1a  mov     dword ptr [rbp+57h+var_80], 110038h
0x18011ab21  mov     [rbp+57h+var_BE], al
0x18011ab24  xor     r12d, r12d
0x18011ab27  mov     byte ptr [rbp+57h+var_98+7], al
0x18011ab2a  xor     r10b, r10b
0x18011ab2d  mov     al, byte ptr [rbp+57h+var_98+9]
0x18011ab30  mov     r9b, 1Ah
0x18011ab33  and     al, dil
0x18011ab36  mov     byte ptr [rbp+57h+var_80+4], 0ABh
0x18011ab3a  or      al, 1
0x18011ab3c  mov     dword ptr [rbp+57h+var_60], 0FFFF0000h
0x18011ab43  mov     [rbp+57h+var_BF], al
0x18011ab46  mov     dil, 2
0x18011ab49  mov     byte ptr [rbp+57h+var_98+9], al
0x18011ab4c  xor     eax, eax
0x18011ab4e  mov     [rbp+57h+var_88], rax
0x18011ab52  lea     eax, [rsi+30h]
0x18011ab55  mov     word ptr [rbp+57h+var_80+6], ax
0x18011ab59  mov     al, 15h
0x18011ab5b  mov     byte ptr [rbp+57h+var_80+8], al
0x18011ab5e  xor     eax, eax
0x18011ab60  mov     dword ptr [rbp+57h+var_80+9], eax
0x18011ab63  mov     word ptr [rbp+57h+var_80+0Dh], ax
0x18011ab67  mov     byte ptr [rbp+57h+var_80+0Fh], al
0x18011ab6a  mov     qword ptr [rbp+57h+var_70], rax
0x18011ab6e  mov     qword ptr [rbp+57h+var_70+8], rax
0x18011ab72  mov     word ptr [rbp+57h+var_60+4], ax
0x18011ab76  mov     byte ptr [rbp+57h+var_60+6], al
0x18011ab79  mov     [rbp+57h+var_C0], al
0x18011ab7c  mov     byte ptr [rbp+57h+var_60+8], al
0x18011ab7f  mov     [rbp+57h+var_50], rax
0x18011ab83  mov     al, 11h
0x18011ab85  movups  [rbp+57h+var_A8], xmm0
0x18011ab89  shr     al, 4
0x18011ab8c  cmp     al, cl
0x18011ab8e  mov     qword ptr [rbp+57h+var_A8], rsi
0x18011ab92  mov     qword ptr [rbp+57h+var_A8+8], r14
0x18011ab96  mov     byte ptr [rbp+57h+var_60+7], r13b
0x18011ab9a  mov     byte ptr [rbp+57h+var_60+9], r11b
0x18011ab9e  mov     byte ptr [rbp+57h+var_60+0Ah], r9b
0x18011aba2  jnz     loc_18011B694
0x18011aba8  add     rdx, r8
0x18011abab  mov     al, [rdx+2]
0x18011abae  shr     al, 4
0x18011abb1  cmp     al, cl
0x18011abb3  jnz     loc_18011B694
0x18011abb9  lea     eax, [rsi+38h]
0x18011abbc  mov     cl, 15h
0x18011abbe  mov     r8b, 0ABh
0x18011abc1  cmp     [rdx+3], r10b
0x18011abc5  jnz     short loc_18011ABE9
0x18011abc7  cmp     [rdx+8], cl
0x18011abca  jnz     loc_18011B694
0x18011abd0  cmp     [rdx], ax
0x18011abd3  jnz     loc_18011B694
0x18011abd9  cmp     [rdx+4], r8b
0x18011abdd  jnz     loc_18011B694
0x18011abe3  cmp     [rdx+3], r10b
0x18011abe7  jz      short loc_18011ABF2
0x18011abe9  cmp     [rdx+8], cl
0x18011abec  jz      loc_18011B694
0x18011abf2  movzx   ebx, word ptr [rdx+6]
0x18011abf6  mov     r8d, 30h ; '0'
0x18011abfc  movzx   eax, r8w
0x18011ac00  mov     r10d, 1
0x18011ac06  movzx   r8d, r8w
0x18011ac0a  sub     rbx, rax
0x18011ac0d  sub     r8, rax
0x18011ac10  test    byte ptr [rbp+r8+57h+var_88], r10b
0x18011ac15  jz      short loc_18011AC1C
0x18011ac17  mov     ecx, r10d
0x18011ac1a  jmp     short loc_18011AC1E
0x18011ac1c  xor     ecx, ecx
0x18011ac1e  cmp     [rdx+8], r10b
0x18011ac22  jb      short loc_18011AC30
0x18011ac24  test    [rbx+rdx+30h], r10b
0x18011ac29  jz      short loc_18011AC30
0x18011ac2b  mov     eax, r10d
0x18011ac2e  jmp     short loc_18011AC32
0x18011ac30  xor     eax, eax
0x18011ac32  cmp     ecx, eax
0x18011ac34  jz      short loc_18011AC4B
0x18011ac36  test    byte ptr [rbp+r8+57h+var_88], r10b
0x18011ac3b  jz      short loc_18011AC46
0x18011ac3d  mov     qword ptr [rbp+57h+var_70], rsi
0x18011ac41  mov     sil, 15h
0x18011ac44  jmp     short loc_18011AC5D
0x18011ac46  mov     sil, 15h
0x18011ac49  jmp     short loc_18011AC55
0x18011ac4b  mov     sil, 15h
0x18011ac4e  test    byte ptr [rbp+r8+57h+var_88], r10b
0x18011ac53  jz      short loc_18011AC5D
0x18011ac55  mov     rax, [rdx+10h]
0x18011ac59  mov     qword ptr [rbp+57h+var_70], rax
0x18011ac5d  cmp     sil, r10b
0x18011ac60  jb      short loc_18011AC69
0x18011ac62  test    byte ptr [rbp+r8+57h+var_88], r10b
0x18011ac67  jnz     short loc_18011AC76
0x18011ac69  cmp     [rdx+8], r10b
0x18011ac6d  jb      short loc_18011AC7B
0x18011ac6f  test    [rbx+rdx+30h], r10b
0x18011ac74  jz      short loc_18011AC7B
0x18011ac76  mov     al, r10b
0x18011ac79  jmp     short loc_18011AC7D
0x18011ac7b  xor     al, al
0x18011ac7d  mov     cl, byte ptr [rbp+57h+var_50]
0x18011ac80  and     cl, 0FEh
0x18011ac83  or      cl, al
0x18011ac85  mov     byte ptr [rbp+57h+var_50], cl
0x18011ac88  cmp     sil, dil
0x18011ac8b  jb      short loc_18011AC94
0x18011ac8d  test    byte ptr [rbp+r8+57h+var_88], dil
0x18011ac92  jnz     short loc_18011AC97
0x18011ac94  xor     r10d, r10d
0x18011ac97  cmp     [rdx+8], dil
0x18011ac9b  jb      short loc_18011ACAB
0x18011ac9d  test    [rbx+rdx+30h], dil
0x18011aca2  jz      short loc_18011ACAB
0x18011aca4  mov     eax, 1
0x18011aca9  jmp     short loc_18011ACAD
0x18011acab  xor     eax, eax
0x18011acad  cmp     r10d, eax
0x18011acb0  jz      short loc_18011ACC4
0x18011acb2  cmp     sil, dil
0x18011acb5  jb      short loc_18011ACD0
0x18011acb7  test    byte ptr [rbp+r8+57h+var_88], dil
0x18011acbc  jz      short loc_18011ACD0
0x18011acbe  mov     dword ptr [rbp+57h+var_70+8], r14d
0x18011acc2  jmp     short loc_18011ACD6
0x18011acc4  cmp     sil, dil
0x18011acc7  jb      short loc_18011ACE2
0x18011acc9  test    byte ptr [rbp+r8+57h+var_88], dil
0x18011acce  jz      short loc_18011ACD6
0x18011acd0  mov     eax, [rdx+18h]
0x18011acd3  mov     dword ptr [rbp+57h+var_70+8], eax
0x18011acd6  cmp     sil, dil
0x18011acd9  jb      short loc_18011ACE2
0x18011acdb  test    byte ptr [rbp+r8+57h+var_88], dil
0x18011ace0  jnz     short loc_18011ACEF
0x18011ace2  cmp     [rdx+8], dil
0x18011ace6  jb      short loc_18011ACF4
0x18011ace8  test    [rbx+rdx+30h], dil
0x18011aced  jz      short loc_18011ACF4
0x18011acef  mov     al, dil
0x18011acf2  jmp     short loc_18011ACF6
0x18011acf4  xor     al, al
0x18011acf6  and     cl, 0FDh
0x18011acf9  or      cl, al
0x18011acfb  mov     byte ptr [rbp+57h+var_50], cl
0x18011acfe  cmp     sil, 3
0x18011ad02  jb      short loc_18011AD17
0x18011ad04  test    byte ptr [rbp+r8+57h+var_88], 4
0x18011ad0a  jz      short loc_18011AD17
0x18011ad0c  mov     r14d, 1
0x18011ad12  mov     r10d, r14d
0x18011ad15  jmp     short loc_18011AD1E
0x18011ad17  xor     r10d, r10d
0x18011ad1a  lea     r14d, [r10+1]
0x18011ad1e  cmp     byte ptr [rdx+8], 3
0x18011ad22  jb      short loc_18011AD30
0x18011ad24  test    byte ptr [rbx+rdx+30h], 4
0x18011ad29  jz      short loc_18011AD30
0x18011ad2b  mov     eax, r14d
0x18011ad2e  jmp     short loc_18011AD32
0x18011ad30  xor     eax, eax
0x18011ad32  cmp     r10d, eax
0x18011ad35  jz      short loc_18011AD55
0x18011ad37  cmp     sil, 3
0x18011ad3b  mov     sil, 4
0x18011ad3e  jb      short loc_18011AD50
0x18011ad40  test    byte ptr [rbp+r8+57h+var_88], sil
0x18011ad45  jz      short loc_18011AD50
0x18011ad47  mov     dword ptr [rbp+57h+var_70+0Ch], r15d
0x18011ad4b  mov     r15b, 15h
0x18011ad4e  jmp     short loc_18011AD68
0x18011ad50  mov     r15b, 15h
0x18011ad53  jmp     short loc_18011AD62
0x18011ad55  mov     sil, 4
0x18011ad58  mov     r15b, 15h
0x18011ad5b  test    byte ptr [rbp+r8+57h+var_88], sil
0x18011ad60  jz      short loc_18011AD68
0x18011ad62  mov     eax, [rdx+1Ch]
0x18011ad65  mov     dword ptr [rbp+57h+var_70+0Ch], eax
0x18011ad68  cmp     r15b, 3
0x18011ad6c  jb      short loc_18011AD75
0x18011ad6e  test    byte ptr [rbp+r8+57h+var_88], sil
0x18011ad73  jnz     short loc_18011AD82
0x18011ad75  cmp     byte ptr [rdx+8], 3
0x18011ad79  jb      short loc_18011AD87
0x18011ad7b  test    [rbx+rdx+30h], sil
0x18011ad80  jz      short loc_18011AD87
0x18011ad82  mov     al, sil
0x18011ad85  jmp     short loc_18011AD89
0x18011ad87  xor     al, al
0x18011ad89  and     cl, 0FBh
0x18011ad8c  or      cl, al
0x18011ad8e  mov     byte ptr [rbp+57h+var_50], cl
0x18011ad91  cmp     r15b, sil
0x18011ad94  jb      short loc_18011ADA3
0x18011ad96  test    byte ptr [rbp+r8+57h+var_88], 8
0x18011ad9c  jz      short loc_18011ADA3
0x18011ad9e  mov     r10d, r14d
0x18011ada1  jmp     short loc_18011ADA6
0x18011ada3  xor     r10d, r10d
0x18011ada6  cmp     [rdx+8], sil
0x18011adaa  jb      short loc_18011ADB8
0x18011adac  test    byte ptr [rbx+rdx+30h], 8
0x18011adb1  jz      short loc_18011ADB8
0x18011adb3  mov     eax, r14d
0x18011adb6  jmp     short loc_18011ADBA
0x18011adb8  xor     eax, eax
0x18011adba  cmp     r10d, eax
0x18011adbd  jz      short loc_18011ADD3
0x18011adbf  cmp     r15b, sil
0x18011adc2  jb      short loc_18011ADE0
0x18011adc4  test    byte ptr [rbp+r8+57h+var_88], 8
0x18011adca  jz      short loc_18011ADE0
0x18011adcc  mov     word ptr [rbp+57h+var_60], r12w
0x18011add1  jmp     short loc_18011ADE8
0x18011add3  cmp     r15b, sil
0x18011add6  jb      short loc_18011ADF5
0x18011add8  test    byte ptr [rbp+r8+57h+var_88], 8
0x18011adde  jz      short loc_18011ADE8
0x18011ade0  movzx   eax, word ptr [rdx+20h]
0x18011ade4  mov     word ptr [rbp+57h+var_60], ax
0x18011ade8  cmp     r15b, sil
0x18011adeb  jb      short loc_18011ADF5
0x18011aded  test    byte ptr [rbp+r8+57h+var_88], 8
0x18011adf3  jnz     short loc_18011AE02
0x18011adf5  cmp     [rdx+8], sil
0x18011adf9  jb      short loc_18011AE06
  ... truncated ...
```
