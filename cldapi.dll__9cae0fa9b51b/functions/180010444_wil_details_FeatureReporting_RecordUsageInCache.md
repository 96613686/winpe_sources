# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x180010444`
- end: `0x180010717`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `723`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180010840`

## callees

- `0x180010444`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_RecordUsageInCache(
        __int64 a1,
        volatile signed __int32 *a2,
        int a3,
        int a4)
{
  int v7; // r8d
  unsigned __int32 v8; // eax
  BOOL v9; // edx
  unsigned __int32 v10; // ett
  int v11; // ecx
  signed __int32 v12; // edx
  int v13; // ebx
  signed __int32 v14; // r9d
  signed __int32 v15; // eax
  signed __int32 v16; // ecx
  BOOL v17; // r9d
  unsigned int v18; // eax
  int v19; // edx
  int v20; // r8d
  unsigned int v21; // edx
  unsigned int v22; // r8d
  signed __int32 v23; // eax
  signed __int32 v24; // edx
  BOOL v25; // ebp
  unsigned int v26; // eax
  int v27; // r9d
  unsigned int v28; // r8d
  unsigned int v29; // r9d
  signed __int32 v30; // eax

  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  switch ( a3 )
  {
    case 0:
      goto LABEL_49;
    case 1:
      goto LABEL_34;
    case 2:
    case 3:
      goto LABEL_17;
    case 4:
LABEL_49:
      v24 = *a2;
      v25 = a3 == 4;
      while ( 1 )
      {
        *(_DWORD *)(a1 + 4) = 0;
        v26 = v24 | 1;
        if ( (((v24 | 1u) >> 14) & 1) != v25 )
        {
          if ( ((v26 >> 5) & 0x1FF) != 0 )
          {
            *(_DWORD *)(a1 + 4) = (v26 >> 5) & 0x1FF;
            *(_DWORD *)(a1 + 8) = a3 == 0 ? 4 : 0;
            v26 = v24 & 0xFFFFC01E | 1;
          }
          v27 = 0;
          if ( a3 == 4 )
            v27 = 0x4000;
          v26 = v26 & 0xFFFFBFFF | v27;
        }
        v28 = (v26 >> 5) & 0x1FF;
        v29 = v28 + 1;
        if ( v28 + 1 > 0x1FF || v29 < v28 )
        {
          LOWORD(v29) = 1;
          *(_DWORD *)(a1 + 8) = a3;
          *(_DWORD *)(a1 + 4) = v28;
        }
        v30 = _InterlockedCompareExchange(
                a2,
                v26 ^ ((unsigned __int16)v26 ^ (unsigned __int16)(32 * v29)) & 0x3FE0,
                v24);
        if ( v24 == v30 )
          break;
        v24 = v30;
      }
      *(_DWORD *)a1 = (v24 & 1) == 0;
      goto LABEL_62;
    case 5:
LABEL_34:
      v16 = *a2;
      v17 = a3 == 5;
      while ( 1 )
      {
        *(_DWORD *)(a1 + 4) = 0;
        v18 = v16 | 1;
        if ( (((v16 | 1u) >> 22) & 1) != v17 )
        {
          if ( ((v18 >> 15) & 0x7F) != 0 )
          {
            *(_DWORD *)(a1 + 4) = (v18 >> 15) & 0x7F;
            v19 = 5;
            if ( a3 != 1 )
              v19 = 1;
            v18 = v16 & 0xFFC07FFE | 1;
            *(_DWORD *)(a1 + 8) = v19;
          }
          v20 = 0;
          if ( a3 == 5 )
            v20 = 0x400000;
          v18 = v18 & 0xFFBFFFFF | v20;
        }
        v21 = (v18 >> 15) & 0x7F;
        v22 = v21 + 1;
        if ( v21 + 1 > 0x7F || v22 < v21 )
        {
          v22 = 1;
          *(_DWORD *)(a1 + 8) = a3;
          *(_DWORD *)(a1 + 4) = v21;
        }
        v23 = _InterlockedCompareExchange(a2, v18 ^ (v18 ^ (v22 << 15)) & 0x3F8000, v16);
        if ( v16 == v23 )
          break;
        v16 = v23;
      }
      *(_DWORD *)a1 = (v16 & 1) == 0;
LABEL_62:
      *(_DWORD *)(a1 + 16) = 0;
      return a1;
  }
  if ( (unsigned int)(a3 - 6) >= 2 )
  {
    v7 = a3 - 320;
    if ( v7 >= 64 )
      goto LABEL_16;
    v8 = *((_DWORD *)a2 + 1);
    do
    {
      v9 = (v8 & 0x10) != 0 && ((v8 >> 5) & 0x3F) == v7;
      *(_DWORD *)(a1 + 16) = v9;
      v10 = v8;
      v8 = _InterlockedCompareExchange(
             a2 + 1,
             v8 ^ ((unsigned __int16)v8 ^ (unsigned __int16)(32 * v7)) & 0x7E0 | 0x10,
             v8);
    }
    while ( v10 != v8 );
    if ( !*(_DWORD *)(a1 + 16) )
    {
LABEL_16:
      *(_DWORD *)(a1 + 8) = a3;
      *(_DWORD *)(a1 + 4) = 1;
      *(_DWORD *)(a1 + 12) = a4;
    }
    return a1;
  }
LABEL_17:
  v11 = 0;
  switch ( a3 )
  {
    case 2:
      v11 = 2;
      break;
    case 3:
      v11 = 8;
      break;
    case 6:
      v11 = 4;
      break;
    case 7:
      v11 = 16;
      break;
  }
  v12 = *a2;
  v13 = 1;
  while ( 1 )
  {
    v14 = v12 | v11 | 1;
    *(_DWORD *)(a1 + 16) = (v12 | v11) == v12;
    if ( (v12 | v11) == v12 )
      v14 = v12 | v11;
    v15 = _InterlockedCompareExchange(a2, v14, v12);
    if ( v12 == v15 )
      break;
    v12 = v15;
  }
  if ( (v14 & 1) == 0 || (v12 & 1) != 0 )
    v13 = 0;
  *(_DWORD *)a1 = v13;
  return a1;
}

```

## disassembly

```asm
0x180010444  push    rbx
0x180010446  push    rbp
0x180010447  push    rsi
0x180010448  push    rdi
0x180010449  xor     eax, eax
0x18001044b  xorps   xmm0, xmm0
0x18001044e  mov     r10, rcx
0x180010451  mov     edi, r9d
0x180010454  mov     r11d, r8d
0x180010457  mov     rsi, rdx
0x18001045a  movups  xmmword ptr [rcx], xmm0
0x18001045d  mov     [rcx+10h], rax
0x180010461  mov     ecx, r8d
0x180010464  test    r8d, r8d
0x180010467  jz      loc_180010640
0x18001046d  sub     ecx, 1
0x180010470  jz      loc_180010587
0x180010476  sub     ecx, 1
0x180010479  jz      loc_18001050E
0x18001047f  sub     ecx, 1
0x180010482  jz      loc_18001050E
0x180010488  sub     ecx, 1
0x18001048b  jz      loc_180010640
0x180010491  sub     ecx, 1
0x180010494  jz      loc_180010587
0x18001049a  sub     ecx, 1
0x18001049d  jz      short loc_18001050E
0x18001049f  cmp     ecx, 1
0x1800104a2  jz      short loc_18001050E
0x1800104a4  add     r8d, 0FFFFFEC0h
0x1800104ab  lea     ebx, [rax+1]
0x1800104ae  cmp     r8d, 40h ; '@'
0x1800104b2  jge     short loc_1800104FD
0x1800104b4  mov     eax, [rdx+4]
0x1800104b7  lea     ecx, [rbx+0Fh]
0x1800104ba  mov     r9d, r8d
0x1800104bd  shl     r9d, 5
0x1800104c1  test    cl, al
0x1800104c3  jz      short loc_1800104D6
0x1800104c5  mov     edx, eax
0x1800104c7  shr     edx, 5
0x1800104ca  and     edx, 3Fh
0x1800104cd  cmp     edx, r8d
0x1800104d0  jnz     short loc_1800104D6
0x1800104d2  mov     edx, ebx
0x1800104d4  jmp     short loc_1800104D8
0x1800104d6  xor     edx, edx
0x1800104d8  mov     [r10+10h], edx
0x1800104dc  mov     edx, r9d
0x1800104df  xor     edx, eax
0x1800104e1  and     edx, 7E0h
0x1800104e7  xor     edx, eax
0x1800104e9  or      edx, ecx
0x1800104eb  lock cmpxchg [rsi+4], edx
0x1800104f0  jnz     short loc_1800104C1
0x1800104f2  cmp     dword ptr [r10+10h], 0
0x1800104f7  jnz     loc_18001070E
0x1800104fd  mov     [r10+8], r11d
0x180010501  mov     [r10+4], ebx
0x180010505  mov     [r10+0Ch], edi
0x180010509  jmp     loc_18001070E
0x18001050e  xor     ecx, ecx
0x180010510  sub     r11d, 2
0x180010514  jz      short loc_18001053C
0x180010516  sub     r11d, 1
0x18001051a  jz      short loc_180010535
0x18001051c  sub     r11d, 3
0x180010520  jz      short loc_18001052E
0x180010522  cmp     r11d, 1
0x180010526  jnz     short loc_180010541
0x180010528  lea     ecx, [r11+0Fh]
0x18001052c  jmp     short loc_180010541
0x18001052e  mov     ecx, 4
0x180010533  jmp     short loc_180010541
0x180010535  mov     ecx, 8
0x18001053a  jmp     short loc_180010541
0x18001053c  mov     ecx, 2
0x180010541  mov     edx, [rdx]
0x180010543  mov     ebx, 1
0x180010548  xor     eax, eax
0x18001054a  mov     r8d, ecx
0x18001054d  or      r8d, edx
0x180010550  cmp     r8d, edx
0x180010553  mov     r9d, r8d
0x180010556  setz    al
0x180010559  or      r9d, ebx
0x18001055c  cmp     r8d, edx
0x18001055f  mov     [r10+10h], eax
0x180010563  mov     eax, edx
0x180010565  cmovz   r9d, r8d
0x180010569  lock cmpxchg [rsi], r9d
0x18001056e  jz      short loc_180010574
0x180010570  mov     edx, eax
0x180010572  jmp     short loc_180010548
0x180010574  test    bl, r9b
0x180010577  jz      short loc_18001057D
0x180010579  test    bl, dl
0x18001057b  jz      short loc_18001057F
0x18001057d  xor     ebx, ebx
0x18001057f  mov     [r10], ebx
0x180010582  jmp     loc_18001070E
0x180010587  mov     ecx, [rdx]
0x180010589  xor     r9d, r9d
0x18001058c  cmp     r11d, 5
0x180010590  mov     ebx, 1
0x180010595  setz    r9b
0x180010599  mov     eax, ecx
0x18001059b  mov     dword ptr [r10+4], 0
0x1800105a3  or      eax, ebx
0x1800105a5  mov     edx, eax
0x1800105a7  shr     edx, 16h
0x1800105aa  and     edx, ebx
0x1800105ac  cmp     edx, r9d
0x1800105af  jz      short loc_1800105F1
0x1800105b1  mov     r8d, eax
0x1800105b4  shr     r8d, 0Fh
0x1800105b8  and     r8d, 7Fh
0x1800105bc  jbe     short loc_1800105D6
0x1800105be  cmp     r11d, ebx
0x1800105c1  mov     [r10+4], r8d
0x1800105c5  mov     edx, 5
0x1800105ca  cmovnz  edx, ebx
0x1800105cd  and     eax, 0FFC07FFFh
0x1800105d2  mov     [r10+8], edx
0x1800105d6  xor     r8d, r8d
0x1800105d9  mov     edx, 400000h
0x1800105de  cmp     r11d, 5
0x1800105e2  cmovz   r8d, edx
0x1800105e6  mov     edx, eax
0x1800105e8  btr     edx, 16h
0x1800105ec  mov     eax, r8d
0x1800105ef  or      eax, edx
0x1800105f1  mov     edx, eax
0x1800105f3  shr     edx, 0Fh
0x1800105f6  and     edx, 7Fh
0x1800105f9  lea     r8d, [rdx+1]
0x1800105fd  cmp     r8d, 7Fh
0x180010601  ja      short loc_180010608
0x180010603  cmp     r8d, edx
0x180010606  jnb     short loc_180010613
0x180010608  mov     r8d, ebx
0x18001060b  mov     [r10+8], r11d
0x18001060f  mov     [r10+4], edx
0x180010613  shl     r8d, 0Fh
0x180010617  xor     r8d, eax
0x18001061a  and     r8d, 3F8000h
0x180010621  xor     r8d, eax
0x180010624  mov     eax, ecx
0x180010626  lock cmpxchg [rsi], r8d
0x18001062b  jz      short loc_180010634
0x18001062d  mov     ecx, eax
0x18001062f  jmp     loc_180010599
0x180010634  not     ecx
0x180010636  and     ecx, ebx
0x180010638  mov     [r10], ecx
0x18001063b  jmp     loc_180010706
0x180010640  mov     edx, [rdx]
0x180010642  xor     ebp, ebp
0x180010644  lea     ecx, [rbp+4]
0x180010647  cmp     r11d, ecx
0x18001064a  lea     ebx, [rcx-3]
0x18001064d  setz    bpl
0x180010651  mov     eax, edx
0x180010653  mov     dword ptr [r10+4], 0
0x18001065b  or      eax, ebx
0x18001065d  mov     r8d, eax
0x180010660  shr     r8d, 0Eh
0x180010664  and     r8d, ebx
0x180010667  cmp     r8d, ebp
0x18001066a  jz      short loc_1800106B3
0x18001066c  mov     edi, eax
0x18001066e  shr     edi, 5
0x180010671  and     edi, 1FFh
0x180010677  jbe     short loc_180010695
0x180010679  mov     r8d, r11d
0x18001067c  mov     [r10+4], edi
0x180010680  neg     r8d
0x180010683  sbb     r9d, r9d
0x180010686  not     r9d
0x180010689  and     r9d, ecx
0x18001068c  mov     [r10+8], r9d
0x180010690  and     eax, 0FFFFC01Fh
0x180010695  xor     r9d, r9d
0x180010698  mov     r8d, 4000h
0x18001069e  cmp     r11d, ecx
0x1800106a1  cmovz   r9d, r8d
0x1800106a5  mov     r8d, eax
0x1800106a8  btr     r8d, 0Eh
0x1800106ad  mov     eax, r9d
0x1800106b0  or      eax, r8d
0x1800106b3  mov     r8d, eax
0x1800106b6  shr     r8d, 5
0x1800106ba  and     r8d, 1FFh
0x1800106c1  lea     r9d, [r8+1]
0x1800106c5  cmp     r9d, 1FFh
0x1800106cc  ja      short loc_1800106D3
0x1800106ce  cmp     r9d, r8d
0x1800106d1  jnb     short loc_1800106DE
0x1800106d3  mov     r9d, ebx
0x1800106d6  mov     [r10+8], r11d
0x1800106da  mov     [r10+4], r8d
0x1800106de  shl     r9d, 5
0x1800106e2  xor     r9d, eax
0x1800106e5  and     r9d, 3FE0h
0x1800106ec  xor     r9d, eax
0x1800106ef  mov     eax, edx
0x1800106f1  lock cmpxchg [rsi], r9d
0x1800106f6  jz      short loc_1800106FF
0x1800106f8  mov     edx, eax
0x1800106fa  jmp     loc_180010651
0x1800106ff  not     edx
0x180010701  and     edx, ebx
0x180010703  mov     [r10], edx
0x180010706  mov     dword ptr [r10+10h], 0
0x18001070e  mov     rax, r10
0x180010711  pop     rdi
0x180010712  pop     rsi
0x180010713  pop     rbp
0x180010714  pop     rbx
0x180010715  retn
```
