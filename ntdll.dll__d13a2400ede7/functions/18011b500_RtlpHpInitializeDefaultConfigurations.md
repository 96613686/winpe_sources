# RtlpHpInitializeDefaultConfigurations

- ea: `0x18011b500`
- end: `0x18011c1c9`
- name: `RtlpHpInitializeDefaultConfigurations`
- size: `3273`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800d5620`

## callees

- `0x1800e6108`
- `0x18011b500`

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
0x18011b500  push    rbp
0x18011b502  push    rbx
0x18011b503  push    rsi
0x18011b504  push    rdi
0x18011b505  push    r12
0x18011b507  push    r13
0x18011b509  push    r14
0x18011b50b  push    r15
0x18011b50d  lea     rbp, [rsp-1Fh]
0x18011b512  sub     rsp, 0A8h
0x18011b519  call    RtlpHpInitializeHeapPgSampling
0x18011b51e  xorps   xmm0, xmm0
0x18011b521  xor     eax, eax
0x18011b523  movups  [rbp+57h+var_80], xmm0
0x18011b527  mov     [rbp+57h+var_50], rax
0x18011b52b  movups  [rbp+57h+var_70], xmm0
0x18011b52f  movups  [rbp+57h+var_60], xmm0
0x18011b533  mov     rax, gs:60h
0x18011b53c  mov     rdx, [rax+2D8h]
0x18011b543  test    rdx, rdx
0x18011b546  jz      loc_18011C1B4
0x18011b54c  cmp     dword ptr [rdx+208h], 11C0h
0x18011b556  jb      loc_18011C193
0x18011b55c  cmp     dword ptr [rdx+11C0h], 0
0x18011b563  jz      loc_18011C193
0x18011b569  mov     r8d, [rdx+11C4h]
0x18011b570  test    r8d, r8d
0x18011b573  jz      loc_18011C193
0x18011b579  mov     cl, byte ptr [rbp+57h+var_60+0Bh]
0x18011b57c  mov     r9b, 0E3h
0x18011b57f  mov     r13b, byte ptr [rbp+57h+var_60+7]
0x18011b583  mov     dil, 81h
0x18011b586  mov     r11b, byte ptr [rbp+57h+var_60+9]
0x18011b58a  and     r13b, r9b
0x18011b58d  movups  [rbp+57h+var_98], xmm0
0x18011b591  and     byte ptr [rbp+57h+var_98+0Bh], 0FEh
0x18011b595  and     r11b, dil
0x18011b598  movups  [rbp+57h+var_B8], xmm0
0x18011b59c  xor     esi, esi
0x18011b59e  mov     dword ptr [rbp+57h+var_B8], 110038h
0x18011b5a5  and     cl, 0FEh
0x18011b5a8  mov     byte ptr [rbp+57h+var_B8+4], 0ABh
0x18011b5ac  and     cl, 0FEh
0x18011b5af  mov     byte ptr [rbp+57h+var_B8+8], 15h
0x18011b5b3  or      r13b, 3
0x18011b5b7  mov     byte ptr [rbp+57h+var_60+0Bh], cl
0x18011b5ba  or      r11b, 1
0x18011b5be  mov     dword ptr [rbp+57h+var_98], 0FFFF0000h
0x18011b5c5  mov     eax, 30h ; '0'
0x18011b5ca  mov     byte ptr [rbp+57h+var_98+8], sil
0x18011b5ce  mov     word ptr [rbp+57h+var_B8+6], ax
0x18011b5d2  and     r13b, r9b
0x18011b5d5  xor     eax, eax
0x18011b5d7  mov     byte ptr [rbp+57h+var_98+0Ah], 1Ah
0x18011b5db  mov     dword ptr [rbp+57h+var_B8+9], eax
0x18011b5de  and     r11b, dil
0x18011b5e1  mov     word ptr [rbp+57h+var_B8+0Dh], ax
0x18011b5e5  xor     r14d, r14d
0x18011b5e8  mov     byte ptr [rbp+57h+var_B8+0Fh], al
0x18011b5eb  or      r13b, 3
0x18011b5ef  mov     word ptr [rbp+57h+var_98+4], ax
0x18011b5f3  or      r11b, 1
0x18011b5f7  mov     byte ptr [rbp+57h+var_98+6], al
0x18011b5fa  mov     cl, 11h
0x18011b5fc  mov     al, byte ptr [rbp+57h+var_98+7]
0x18011b5ff  xor     r15d, r15d
0x18011b602  and     al, r9b
0x18011b605  shr     cl, 4
0x18011b608  or      al, 3
0x18011b60a  mov     dword ptr [rbp+57h+var_80], 110038h
0x18011b611  mov     [rbp+57h+var_BE], al
0x18011b614  xor     r12d, r12d
0x18011b617  mov     byte ptr [rbp+57h+var_98+7], al
0x18011b61a  xor     r10b, r10b
0x18011b61d  mov     al, byte ptr [rbp+57h+var_98+9]
0x18011b620  mov     r9b, 1Ah
0x18011b623  and     al, dil
0x18011b626  mov     byte ptr [rbp+57h+var_80+4], 0ABh
0x18011b62a  or      al, 1
0x18011b62c  mov     dword ptr [rbp+57h+var_60], 0FFFF0000h
0x18011b633  mov     [rbp+57h+var_BF], al
0x18011b636  mov     dil, 2
0x18011b639  mov     byte ptr [rbp+57h+var_98+9], al
0x18011b63c  xor     eax, eax
0x18011b63e  mov     [rbp+57h+var_88], rax
0x18011b642  lea     eax, [rsi+30h]
0x18011b645  mov     word ptr [rbp+57h+var_80+6], ax
0x18011b649  mov     al, 15h
0x18011b64b  mov     byte ptr [rbp+57h+var_80+8], al
0x18011b64e  xor     eax, eax
0x18011b650  mov     dword ptr [rbp+57h+var_80+9], eax
0x18011b653  mov     word ptr [rbp+57h+var_80+0Dh], ax
0x18011b657  mov     byte ptr [rbp+57h+var_80+0Fh], al
0x18011b65a  mov     qword ptr [rbp+57h+var_70], rax
0x18011b65e  mov     qword ptr [rbp+57h+var_70+8], rax
0x18011b662  mov     word ptr [rbp+57h+var_60+4], ax
0x18011b666  mov     byte ptr [rbp+57h+var_60+6], al
0x18011b669  mov     [rbp+57h+var_C0], al
0x18011b66c  mov     byte ptr [rbp+57h+var_60+8], al
0x18011b66f  mov     [rbp+57h+var_50], rax
0x18011b673  mov     al, 11h
0x18011b675  movups  [rbp+57h+var_A8], xmm0
0x18011b679  shr     al, 4
0x18011b67c  cmp     al, cl
0x18011b67e  mov     qword ptr [rbp+57h+var_A8], rsi
0x18011b682  mov     qword ptr [rbp+57h+var_A8+8], r14
0x18011b686  mov     byte ptr [rbp+57h+var_60+7], r13b
0x18011b68a  mov     byte ptr [rbp+57h+var_60+9], r11b
0x18011b68e  mov     byte ptr [rbp+57h+var_60+0Ah], r9b
0x18011b692  jnz     loc_18011C184
0x18011b698  add     rdx, r8
0x18011b69b  mov     al, [rdx+2]
0x18011b69e  shr     al, 4
0x18011b6a1  cmp     al, cl
0x18011b6a3  jnz     loc_18011C184
0x18011b6a9  lea     eax, [rsi+38h]
0x18011b6ac  mov     cl, 15h
0x18011b6ae  mov     r8b, 0ABh
0x18011b6b1  cmp     [rdx+3], r10b
0x18011b6b5  jnz     short loc_18011B6D9
0x18011b6b7  cmp     [rdx+8], cl
0x18011b6ba  jnz     loc_18011C184
0x18011b6c0  cmp     [rdx], ax
0x18011b6c3  jnz     loc_18011C184
0x18011b6c9  cmp     [rdx+4], r8b
0x18011b6cd  jnz     loc_18011C184
0x18011b6d3  cmp     [rdx+3], r10b
0x18011b6d7  jz      short loc_18011B6E2
0x18011b6d9  cmp     [rdx+8], cl
0x18011b6dc  jz      loc_18011C184
0x18011b6e2  movzx   ebx, word ptr [rdx+6]
0x18011b6e6  mov     r8d, 30h ; '0'
0x18011b6ec  movzx   eax, r8w
0x18011b6f0  mov     r10d, 1
0x18011b6f6  movzx   r8d, r8w
0x18011b6fa  sub     rbx, rax
0x18011b6fd  sub     r8, rax
0x18011b700  test    byte ptr [rbp+r8+57h+var_88], r10b
0x18011b705  jz      short loc_18011B70C
0x18011b707  mov     ecx, r10d
0x18011b70a  jmp     short loc_18011B70E
0x18011b70c  xor     ecx, ecx
0x18011b70e  cmp     [rdx+8], r10b
0x18011b712  jb      short loc_18011B720
0x18011b714  test    [rbx+rdx+30h], r10b
0x18011b719  jz      short loc_18011B720
0x18011b71b  mov     eax, r10d
0x18011b71e  jmp     short loc_18011B722
0x18011b720  xor     eax, eax
0x18011b722  cmp     ecx, eax
0x18011b724  jz      short loc_18011B73B
0x18011b726  test    byte ptr [rbp+r8+57h+var_88], r10b
0x18011b72b  jz      short loc_18011B736
0x18011b72d  mov     qword ptr [rbp+57h+var_70], rsi
0x18011b731  mov     sil, 15h
0x18011b734  jmp     short loc_18011B74D
0x18011b736  mov     sil, 15h
0x18011b739  jmp     short loc_18011B745
0x18011b73b  mov     sil, 15h
0x18011b73e  test    byte ptr [rbp+r8+57h+var_88], r10b
0x18011b743  jz      short loc_18011B74D
0x18011b745  mov     rax, [rdx+10h]
0x18011b749  mov     qword ptr [rbp+57h+var_70], rax
0x18011b74d  cmp     sil, r10b
0x18011b750  jb      short loc_18011B759
0x18011b752  test    byte ptr [rbp+r8+57h+var_88], r10b
0x18011b757  jnz     short loc_18011B766
0x18011b759  cmp     [rdx+8], r10b
0x18011b75d  jb      short loc_18011B76B
0x18011b75f  test    [rbx+rdx+30h], r10b
0x18011b764  jz      short loc_18011B76B
0x18011b766  mov     al, r10b
0x18011b769  jmp     short loc_18011B76D
0x18011b76b  xor     al, al
0x18011b76d  mov     cl, byte ptr [rbp+57h+var_50]
0x18011b770  and     cl, 0FEh
0x18011b773  or      cl, al
0x18011b775  mov     byte ptr [rbp+57h+var_50], cl
0x18011b778  cmp     sil, dil
0x18011b77b  jb      short loc_18011B784
0x18011b77d  test    byte ptr [rbp+r8+57h+var_88], dil
0x18011b782  jnz     short loc_18011B787
0x18011b784  xor     r10d, r10d
0x18011b787  cmp     [rdx+8], dil
0x18011b78b  jb      short loc_18011B79B
0x18011b78d  test    [rbx+rdx+30h], dil
0x18011b792  jz      short loc_18011B79B
0x18011b794  mov     eax, 1
0x18011b799  jmp     short loc_18011B79D
0x18011b79b  xor     eax, eax
0x18011b79d  cmp     r10d, eax
0x18011b7a0  jz      short loc_18011B7B4
0x18011b7a2  cmp     sil, dil
0x18011b7a5  jb      short loc_18011B7C0
0x18011b7a7  test    byte ptr [rbp+r8+57h+var_88], dil
0x18011b7ac  jz      short loc_18011B7C0
0x18011b7ae  mov     dword ptr [rbp+57h+var_70+8], r14d
0x18011b7b2  jmp     short loc_18011B7C6
0x18011b7b4  cmp     sil, dil
0x18011b7b7  jb      short loc_18011B7D2
0x18011b7b9  test    byte ptr [rbp+r8+57h+var_88], dil
0x18011b7be  jz      short loc_18011B7C6
0x18011b7c0  mov     eax, [rdx+18h]
0x18011b7c3  mov     dword ptr [rbp+57h+var_70+8], eax
0x18011b7c6  cmp     sil, dil
0x18011b7c9  jb      short loc_18011B7D2
0x18011b7cb  test    byte ptr [rbp+r8+57h+var_88], dil
0x18011b7d0  jnz     short loc_18011B7DF
0x18011b7d2  cmp     [rdx+8], dil
0x18011b7d6  jb      short loc_18011B7E4
0x18011b7d8  test    [rbx+rdx+30h], dil
0x18011b7dd  jz      short loc_18011B7E4
0x18011b7df  mov     al, dil
0x18011b7e2  jmp     short loc_18011B7E6
0x18011b7e4  xor     al, al
0x18011b7e6  and     cl, 0FDh
0x18011b7e9  or      cl, al
0x18011b7eb  mov     byte ptr [rbp+57h+var_50], cl
0x18011b7ee  cmp     sil, 3
0x18011b7f2  jb      short loc_18011B807
0x18011b7f4  test    byte ptr [rbp+r8+57h+var_88], 4
0x18011b7fa  jz      short loc_18011B807
0x18011b7fc  mov     r14d, 1
0x18011b802  mov     r10d, r14d
0x18011b805  jmp     short loc_18011B80E
0x18011b807  xor     r10d, r10d
0x18011b80a  lea     r14d, [r10+1]
0x18011b80e  cmp     byte ptr [rdx+8], 3
0x18011b812  jb      short loc_18011B820
0x18011b814  test    byte ptr [rbx+rdx+30h], 4
0x18011b819  jz      short loc_18011B820
0x18011b81b  mov     eax, r14d
0x18011b81e  jmp     short loc_18011B822
0x18011b820  xor     eax, eax
0x18011b822  cmp     r10d, eax
0x18011b825  jz      short loc_18011B845
0x18011b827  cmp     sil, 3
0x18011b82b  mov     sil, 4
0x18011b82e  jb      short loc_18011B840
0x18011b830  test    byte ptr [rbp+r8+57h+var_88], sil
0x18011b835  jz      short loc_18011B840
0x18011b837  mov     dword ptr [rbp+57h+var_70+0Ch], r15d
0x18011b83b  mov     r15b, 15h
0x18011b83e  jmp     short loc_18011B858
0x18011b840  mov     r15b, 15h
0x18011b843  jmp     short loc_18011B852
0x18011b845  mov     sil, 4
0x18011b848  mov     r15b, 15h
0x18011b84b  test    byte ptr [rbp+r8+57h+var_88], sil
0x18011b850  jz      short loc_18011B858
0x18011b852  mov     eax, [rdx+1Ch]
0x18011b855  mov     dword ptr [rbp+57h+var_70+0Ch], eax
0x18011b858  cmp     r15b, 3
0x18011b85c  jb      short loc_18011B865
0x18011b85e  test    byte ptr [rbp+r8+57h+var_88], sil
0x18011b863  jnz     short loc_18011B872
0x18011b865  cmp     byte ptr [rdx+8], 3
0x18011b869  jb      short loc_18011B877
0x18011b86b  test    [rbx+rdx+30h], sil
0x18011b870  jz      short loc_18011B877
0x18011b872  mov     al, sil
0x18011b875  jmp     short loc_18011B879
0x18011b877  xor     al, al
0x18011b879  and     cl, 0FBh
0x18011b87c  or      cl, al
0x18011b87e  mov     byte ptr [rbp+57h+var_50], cl
0x18011b881  cmp     r15b, sil
0x18011b884  jb      short loc_18011B893
0x18011b886  test    byte ptr [rbp+r8+57h+var_88], 8
0x18011b88c  jz      short loc_18011B893
0x18011b88e  mov     r10d, r14d
0x18011b891  jmp     short loc_18011B896
0x18011b893  xor     r10d, r10d
0x18011b896  cmp     [rdx+8], sil
0x18011b89a  jb      short loc_18011B8A8
0x18011b89c  test    byte ptr [rbx+rdx+30h], 8
0x18011b8a1  jz      short loc_18011B8A8
0x18011b8a3  mov     eax, r14d
0x18011b8a6  jmp     short loc_18011B8AA
0x18011b8a8  xor     eax, eax
0x18011b8aa  cmp     r10d, eax
0x18011b8ad  jz      short loc_18011B8C3
0x18011b8af  cmp     r15b, sil
0x18011b8b2  jb      short loc_18011B8D0
0x18011b8b4  test    byte ptr [rbp+r8+57h+var_88], 8
0x18011b8ba  jz      short loc_18011B8D0
0x18011b8bc  mov     word ptr [rbp+57h+var_60], r12w
0x18011b8c1  jmp     short loc_18011B8D8
0x18011b8c3  cmp     r15b, sil
0x18011b8c6  jb      short loc_18011B8E5
0x18011b8c8  test    byte ptr [rbp+r8+57h+var_88], 8
0x18011b8ce  jz      short loc_18011B8D8
0x18011b8d0  movzx   eax, word ptr [rdx+20h]
0x18011b8d4  mov     word ptr [rbp+57h+var_60], ax
0x18011b8d8  cmp     r15b, sil
0x18011b8db  jb      short loc_18011B8E5
0x18011b8dd  test    byte ptr [rbp+r8+57h+var_88], 8
0x18011b8e3  jnz     short loc_18011B8F2
0x18011b8e5  cmp     [rdx+8], sil
0x18011b8e9  jb      short loc_18011B8F6
  ... truncated ...
```
