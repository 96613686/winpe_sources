# AhgGenomeCompute

- ea: `0x18000b1f0`
- end: `0x18000b708`
- name: `AhgGenomeCompute`
- size: `1304`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a60c`

## callees

- `0x18000b1f0`
- `0x18000e240`

## import_xrefs

- `KERNEL32!SystemTimeToFileTime` at `0x18000b278`
- `KERNEL32!SystemTimeToFileTime` at `0x18000b4f9`
- `KERNEL32!SystemTimeToFileTime` at `0x18000b278`
- `KERNEL32!SystemTimeToFileTime` at `0x18000b4f9`

## string_xrefs

- `0x18000b2cf`: `AhgGenomeCompute`
- `0x18000b553`: `AhgGenomeCompute`
- `0x18000b614`: `AhgGenomeCompute`

## pseudocode

```c
__int64 __fastcall AhgGenomeCompute(_DWORD *a1, int *a2, __int64 a3)
{
  int v4; // r14d
  unsigned __int64 v5; // rbx
  unsigned int v6; // edi
  __int64 v7; // rsi
  unsigned int v8; // r8d
  int v9; // ecx
  int v10; // eax
  unsigned int v11; // esi
  unsigned int v12; // edi
  int v13; // ecx
  bool v14; // zf
  bool v15; // cc
  int v16; // ecx
  bool v17; // zf
  bool v18; // cc
  int v19; // r12d
  __int64 v20; // rbx
  unsigned int v21; // r13d
  __int64 v22; // r12
  int v23; // r9d
  int v24; // r8d
  unsigned int i; // edx
  int v26; // eax
  unsigned int v27; // ebx
  int v28; // edx
  bool v29; // zf
  bool v30; // cc
  unsigned int j; // r8d
  __int64 v32; // rax
  int v34; // [rsp+20h] [rbp-38h]
  struct _FILETIME FileTime; // [rsp+28h] [rbp-30h] BYREF
  struct _FILETIME v36; // [rsp+30h] [rbp-28h]
  struct _FILETIME v37; // [rsp+38h] [rbp-20h]
  unsigned __int64 v38; // [rsp+40h] [rbp-18h]
  int v41; // [rsp+B0h] [rbp+58h]
  int v42; // [rsp+B0h] [rbp+58h]
  int v43; // [rsp+B8h] [rbp+60h]

  v34 = 4;
  FileTime = 0;
  v41 = 0;
  v4 = 0;
  v43 = 0;
  if ( (*(_BYTE *)(a3 + 636) & 1) != 0 )
  {
    v5 = *(_QWORD *)(a3 + 640);
    v6 = 0;
    v36 = (struct _FILETIME)v5;
    v43 = 1;
    while ( 1 )
    {
      v7 = v6;
      if ( !SystemTimeToFileTime((const SYSTEMTIME *)(0x180000000LL + 24LL * dword_18001EA50[v6] + 125560), &FileTime) )
        break;
      v36 = FileTime;
      v37 = (struct _FILETIME)v5;
      if ( v5 >= *(_QWORD *)&FileTime )
      {
        ++v6;
        v34 = dword_18001EA50[v7];
        if ( v6 < 6 )
          continue;
      }
      goto LABEL_8;
    }
    AslLogCallPrintf(2, "AhgGenomeCompute", 247, "Failed to convert system time to file time");
    v43 = 0;
  }
LABEL_8:
  if ( (*(_BYTE *)(a3 + 732) & 1) != 0 )
  {
    v8 = *(_DWORD *)(a3 + 736);
    v9 = 0;
    while ( v8 < dword_18001EA24[3 * v9] || v8 >= dword_18001EA28[3 * v9] )
    {
      if ( (unsigned int)++v9 >= 4 )
        goto LABEL_15;
    }
    v10 = dword_18001EA74[6 * dword_18001EA20[3 * v9]];
    LOWORD(v41) = HIWORD(v10);
    HIWORD(v41) = v10;
LABEL_15:
    v4 = 128;
  }
  if ( (*(_BYTE *)(a3 + 780) & 1) != 0 )
  {
    v11 = *(_DWORD *)(a3 + 784);
    v12 = HIWORD(v11);
    v4 |= 0x100u;
LABEL_99:
    v27 = 0;
    goto LABEL_100;
  }
  LOWORD(v11) = HIWORD(v41);
  LOWORD(v12) = v41;
  if ( (*(_BYTE *)(a3 + 764) & 1) != 0 )
  {
    if ( (_WORD)v41 == 5 )
    {
      if ( HIWORD(v41) != 1 && HIWORD(v41) )
        goto LABEL_26;
    }
    else if ( (unsigned __int16)v41 >= 5u )
    {
      goto LABEL_26;
    }
    LOWORD(v12) = 5;
    LOWORD(v11) = 1;
LABEL_26:
    v4 |= 0x1000u;
    goto LABEL_99;
  }
  if ( (*(_BYTE *)(a3 + 700) & 1) != 0 )
  {
    v13 = *(_DWORD *)(a3 + 704);
    v14 = HIWORD(v13) == (unsigned __int16)v41;
    v15 = HIWORD(v13) <= (unsigned __int16)v41;
    if ( HIWORD(v13) == (_WORD)v41 )
    {
      if ( (_WORD)v13 == HIWORD(v41) )
      {
LABEL_34:
        LOWORD(v12) = HIWORD(v13);
        LOWORD(v11) = v13;
LABEL_35:
        v4 |= 0x20u;
        goto LABEL_36;
      }
      v14 = HIWORD(v13) == (unsigned __int16)v41;
      v15 = HIWORD(v13) <= (unsigned __int16)v41;
    }
    if ( v15 && (!v14 || (unsigned __int16)v13 <= HIWORD(v41)) )
      goto LABEL_35;
    goto LABEL_34;
  }
LABEL_36:
  if ( (*(_BYTE *)(a3 + 716) & 1) == 0 )
    goto LABEL_45;
  v16 = *(_DWORD *)(a3 + 720);
  v17 = HIWORD(v16) == (unsigned __int16)v12;
  v18 = HIWORD(v16) <= (unsigned __int16)v12;
  if ( HIWORD(v16) != (_WORD)v12 )
  {
LABEL_40:
    if ( v18 && (!v17 || (unsigned __int16)v16 <= (unsigned __int16)v11) )
      goto LABEL_44;
    goto LABEL_43;
  }
  if ( (_WORD)v16 != (_WORD)v11 )
  {
    v17 = HIWORD(v16) == (unsigned __int16)v12;
    v18 = HIWORD(v16) <= (unsigned __int16)v12;
    goto LABEL_40;
  }
LABEL_43:
  LOWORD(v12) = HIWORD(v16);
  LOWORD(v11) = v16;
LABEL_44:
  v4 |= 0x40u;
LABEL_45:
  if ( (*(_BYTE *)(a3 + 796) & 1) != 0 )
  {
    if ( (_WORD)v12 == 6 )
    {
      if ( !(_WORD)v11 )
        goto LABEL_50;
    }
    else if ( (unsigned __int16)v12 < 6u )
    {
LABEL_50:
      LOWORD(v12) = 6;
      LOWORD(v11) = 0;
    }
    v4 |= 0x200u;
  }
  if ( (*(_BYTE *)(a3 + 652) & 1) != 0 && *(_WORD *)(a3 + 656) == 0x8664 )
  {
    if ( (_WORD)v12 == 6 )
    {
      if ( !(_WORD)v11 )
        goto LABEL_58;
    }
    else if ( (unsigned __int16)v12 < 6u )
    {
LABEL_58:
      LOWORD(v12) = 6;
      LOWORD(v11) = 0;
    }
    v4 |= 2u;
  }
  if ( (*(_BYTE *)(a3 + 668) & 1) != 0 && *(_DWORD *)(a3 + 672) == 1 )
  {
    if ( (_WORD)v12 == 6 )
    {
      if ( !(_WORD)v11 )
        goto LABEL_66;
    }
    else if ( (unsigned __int16)v12 < 6u )
    {
LABEL_66:
      LOWORD(v12) = 6;
      LOWORD(v11) = 0;
    }
    v4 |= 4u;
  }
  v19 = 4;
  if ( (*(_BYTE *)(a3 + 636) & 1) != 0 )
  {
    v20 = *(_QWORD *)(a3 + 640);
    v21 = 0;
    v36 = (struct _FILETIME)v20;
    while ( SystemTimeToFileTime((const SYSTEMTIME *)(0x180000000LL + 24LL * dword_18001EA50[v21] + 125560), &FileTime) )
    {
      v37 = FileTime;
      v38 = __PAIR64__(v36.dwHighDateTime, v20);
      if ( __PAIR64__(v36.dwHighDateTime, v20) >= *(_QWORD *)&FileTime )
      {
        v22 = v21++;
        v19 = dword_18001EA50[v22];
        if ( v21 < 6 )
          continue;
      }
      goto LABEL_75;
    }
    AslLogCallPrintf(2, "AhgGenomeCompute", 369, "Failed to convert system time to file time");
LABEL_75:
    v23 = 1;
    v4 |= 1u;
  }
  else
  {
    v23 = 0;
  }
  v24 = 4;
  if ( (*(_BYTE *)(a3 + 684) & 1) != 0 )
  {
    for ( i = 0; i < 6; ++i )
    {
      if ( *(_DWORD *)(a3 + 688) <= (unsigned int)(unsigned __int16)word_18001EA78[12 * dword_18001EA50[i]] )
        break;
      v24 = dword_18001EA50[i];
    }
    v4 |= 0x10u;
    v26 = 1;
  }
  else
  {
    v26 = 0;
  }
  if ( v23 == 1 )
  {
    if ( v26 == 1 && v19 >= v24 )
      v19 = v24;
  }
  else
  {
    v19 = 4;
    if ( v26 == 1 )
      v19 = v24;
  }
  if ( v4 )
  {
    v28 = dword_18001EA74[6 * v19];
    v29 = HIWORD(v28) == (unsigned __int16)v12;
    v30 = HIWORD(v28) <= (unsigned __int16)v12;
    if ( HIWORD(v28) == (_WORD)v12 )
    {
      if ( (_WORD)v28 == (_WORD)v11 )
      {
LABEL_98:
        LOWORD(v12) = HIWORD(v28);
        LOWORD(v11) = v28;
        goto LABEL_99;
      }
      v29 = HIWORD(v28) == (unsigned __int16)v12;
      v30 = HIWORD(v28) <= (unsigned __int16)v12;
    }
    if ( v30 && (!v29 || (unsigned __int16)v28 <= (unsigned __int16)v11) )
      goto LABEL_99;
    goto LABEL_98;
  }
  v27 = 1006;
  AslLogCallPrintf(1, "AhgGenomeCompute", 416, "Bad timestamp");
LABEL_100:
  if ( v43 == 1 && LOWORD(dword_18001EA74[6 * v34]) == (_WORD)v11 && HIWORD(dword_18001EA74[6 * v34]) == (_WORD)v12 )
    v4 |= 0x2000u;
  for ( j = 1; j < 6; ++j )
  {
    if ( (unsigned __int16)v11 + ((unsigned __int16)v12 << 16) < (unsigned int)dword_18001EA74[6 * dword_18001EA50[j]] )
      break;
  }
  v32 = dword_18001EA50[j - 1];
  *a2 = v4;
  HIWORD(v42) = dword_18001EA74[6 * v32];
  LOWORD(v42) = HIWORD(dword_18001EA74[6 * v32]);
  *a1 = v42;
  return v27;
}

```

## disassembly

```asm
0x18000b1f0  mov     [rsp-40h+arg_8], rdx
0x18000b1f5  mov     [rsp-40h+arg_0], rcx
0x18000b1fa  push    rbp
0x18000b1fb  push    rbx
0x18000b1fc  push    rsi
0x18000b1fd  push    rdi
0x18000b1fe  push    r12
0x18000b200  push    r13
0x18000b202  push    r14
0x18000b204  push    r15
0x18000b206  mov     rbp, rsp
0x18000b209  sub     rsp, 58h
0x18000b20d  xor     r11d, r11d
0x18000b210  mov     [rbp+var_38], 4
0x18000b217  mov     r15, r8
0x18000b21a  mov     qword ptr [rbp+FileTime.dwLowDateTime], r11
0x18000b21e  mov     [rbp+arg_10], r11d
0x18000b222  lea     r9, cs:180000000h
0x18000b229  mov     r14d, r11d
0x18000b22c  mov     [rbp+arg_18], r11d
0x18000b230  lea     r10d, [r11+1]
0x18000b234  lea     ebx, [r11+6]
0x18000b238  test    [r8+27Ch], r10b
0x18000b23f  jz      loc_18000B2F7
0x18000b245  mov     rbx, [r8+280h]
0x18000b24c  mov     edi, r11d
0x18000b24f  mov     [rbp+var_28], rbx
0x18000b253  mov     r12d, dword ptr [rbp+var_28+4]
0x18000b257  mov     [rbp+arg_18], r10d
0x18000b25b  mov     esi, edi
0x18000b25d  lea     rdx, [rbp+FileTime]; lpFileTime
0x18000b261  movsxd  rax, ds:rva dword_18001EA50[r9+rsi*4]
0x18000b269  lea     rcx, [rax+rax*2]
0x18000b26d  lea     rcx, ds:1EA78h[rcx*8]
0x18000b275  add     rcx, r9; lpSystemTime
0x18000b278  call    cs:__imp_SystemTimeToFileTime
0x18000b27e  xor     r11d, r11d
0x18000b281  test    eax, eax
0x18000b283  jz      short loc_18000B2C2
0x18000b285  mov     eax, [rbp+FileTime.dwLowDateTime]
0x18000b288  lea     r9, cs:180000000h
0x18000b28f  mov     ecx, [rbp+FileTime.dwHighDateTime]
0x18000b292  lea     r10d, [r11+1]
0x18000b296  mov     dword ptr [rbp+var_28], eax
0x18000b299  mov     dword ptr [rbp+var_28+4], ecx
0x18000b29c  mov     rax, [rbp+var_28]
0x18000b2a0  mov     dword ptr [rbp+var_20], ebx
0x18000b2a3  mov     dword ptr [rbp+var_20+4], r12d
0x18000b2a7  cmp     [rbp+var_20], rax
0x18000b2ab  jb      short loc_18000B2F2
0x18000b2ad  mov     eax, ds:rva dword_18001EA50[r9+rsi*4]
0x18000b2b5  add     edi, r10d
0x18000b2b8  mov     [rbp+var_38], eax
0x18000b2bb  cmp     edi, 6
0x18000b2be  jb      short loc_18000B25B
0x18000b2c0  jmp     short loc_18000B2F2
0x18000b2c2  lea     r9, aFailedToConver_1; "Failed to convert system time to file t"...
0x18000b2c9  mov     r8d, 0F7h
0x18000b2cf  lea     rdx, aAhggenomecompu; "AhgGenomeCompute"
0x18000b2d6  mov     ecx, 2
0x18000b2db  call    AslLogCallPrintf
0x18000b2e0  xor     r11d, r11d
0x18000b2e3  lea     r9, cs:180000000h
0x18000b2ea  mov     [rbp+arg_18], r11d
0x18000b2ee  lea     r10d, [r11+1]
0x18000b2f2  mov     ebx, 6
0x18000b2f7  test    [r15+2DCh], r10b
0x18000b2fe  jz      short loc_18000B372
0x18000b300  mov     r8d, [r15+2E0h]
0x18000b307  mov     ecx, r11d
0x18000b30a  mov     eax, ecx
0x18000b30c  lea     rdx, [rax+rax*2]
0x18000b310  cmp     r8d, ds:rva dword_18001EA24[r9+rdx*4]
0x18000b318  jb      short loc_18000B324
0x18000b31a  cmp     r8d, ds:rva dword_18001EA28[r9+rdx*4]
0x18000b322  jb      short loc_18000B32E
0x18000b324  add     ecx, r10d
0x18000b327  cmp     ecx, 4
0x18000b32a  jb      short loc_18000B30A
0x18000b32c  jmp     short loc_18000B36C
0x18000b32e  movsxd  rax, ds:rva dword_18001EA20[r9+rdx*4]
0x18000b336  lea     rcx, [rax+rax*2]
0x18000b33a  mov     eax, ds:rva dword_18001EA74[r9+rcx*8]
0x18000b342  mov     ecx, eax
0x18000b344  shr     ecx, 10h
0x18000b347  mov     word ptr [rbp+arg_10+2], ax
0x18000b34b  mov     word ptr [rbp+arg_10], cx
0x18000b34f  test    cx, cx
0x18000b352  jnz     short loc_18000B366
0x18000b354  test    ax, ax
0x18000b357  jz      short loc_18000B366
0x18000b359  test    cx, cx
0x18000b35c  jnz     short loc_18000B366
0x18000b35e  test    ax, ax
0x18000b361  mov     eax, r11d
0x18000b364  jz      short loc_18000B369
0x18000b366  mov     eax, [rbp+arg_10]
0x18000b369  mov     [rbp+arg_10], eax
0x18000b36c  mov     r14d, 80h
0x18000b372  test    [r15+30Ch], r10b
0x18000b379  jz      short loc_18000B398
0x18000b37b  mov     esi, [r15+310h]
0x18000b382  mov     edi, esi
0x18000b384  shr     edi, 10h
0x18000b387  bts     r14d, 8
0x18000b38c  lea     r15, cs:180000000h
0x18000b393  jmp     loc_18000B65E
0x18000b398  movzx   esi, word ptr [rbp+arg_10+2]
0x18000b39c  movzx   edi, word ptr [rbp+arg_10]
0x18000b3a0  test    [r15+2FCh], r10b
0x18000b3a7  jz      short loc_18000B3D1
0x18000b3a9  mov     eax, 5
0x18000b3ae  cmp     ax, di
0x18000b3b1  jnz     short loc_18000B3BB
0x18000b3b3  cmp     r10w, si
0x18000b3b7  jnz     short loc_18000B3C3
0x18000b3b9  jmp     short loc_18000B3C5
0x18000b3bb  ja      short loc_18000B3C5
0x18000b3bd  jnz     short loc_18000B3CA
0x18000b3bf  cmp     r10w, si
0x18000b3c3  jbe     short loc_18000B3CA
0x18000b3c5  mov     edi, eax
0x18000b3c7  mov     esi, r10d
0x18000b3ca  bts     r14d, 0Ch
0x18000b3cf  jmp     short loc_18000B38C
0x18000b3d1  test    [r15+2BCh], r10b
0x18000b3d8  jz      short loc_18000B406
0x18000b3da  mov     ecx, [r15+2C0h]
0x18000b3e1  mov     eax, ecx
0x18000b3e3  shr     eax, 10h
0x18000b3e6  cmp     ax, di
0x18000b3e9  jnz     short loc_18000B3F3
0x18000b3eb  cmp     cx, si
0x18000b3ee  jz      short loc_18000B3FC
0x18000b3f0  cmp     ax, di
0x18000b3f3  ja      short loc_18000B3FC
0x18000b3f5  jnz     short loc_18000B402
0x18000b3f7  cmp     cx, si
0x18000b3fa  jbe     short loc_18000B402
0x18000b3fc  movzx   edi, ax
0x18000b3ff  movzx   esi, cx
0x18000b402  or      r14d, 20h
0x18000b406  test    [r15+2CCh], r10b
0x18000b40d  jz      short loc_18000B43B
0x18000b40f  mov     ecx, [r15+2D0h]
0x18000b416  mov     eax, ecx
0x18000b418  shr     eax, 10h
0x18000b41b  cmp     ax, di
0x18000b41e  jnz     short loc_18000B428
0x18000b420  cmp     cx, si
0x18000b423  jz      short loc_18000B431
0x18000b425  cmp     ax, di
0x18000b428  ja      short loc_18000B431
0x18000b42a  jnz     short loc_18000B437
0x18000b42c  cmp     cx, si
0x18000b42f  jbe     short loc_18000B437
0x18000b431  movzx   edi, ax
0x18000b434  movzx   esi, cx
0x18000b437  or      r14d, 40h
0x18000b43b  test    [r15+31Ch], r10b
0x18000b442  jz      short loc_18000B45E
0x18000b444  cmp     bx, di
0x18000b447  jnz     short loc_18000B451
0x18000b449  cmp     r11w, si
0x18000b44d  jnz     short loc_18000B459
0x18000b44f  jmp     short loc_18000B453
0x18000b451  jbe     short loc_18000B459
0x18000b453  movzx   edi, bx
0x18000b456  mov     esi, r11d
0x18000b459  bts     r14d, 9
0x18000b45e  test    [r15+28Ch], r10b
0x18000b465  jz      short loc_18000B48F
0x18000b467  mov     eax, 8664h
0x18000b46c  cmp     [r15+290h], ax
0x18000b474  jnz     short loc_18000B48F
0x18000b476  cmp     bx, di
0x18000b479  jnz     short loc_18000B483
0x18000b47b  cmp     r11w, si
0x18000b47f  jnz     short loc_18000B48B
0x18000b481  jmp     short loc_18000B485
0x18000b483  jbe     short loc_18000B48B
0x18000b485  movzx   edi, bx
0x18000b488  mov     esi, r11d
0x18000b48b  or      r14d, 2
0x18000b48f  test    [r15+29Ch], r10b
0x18000b496  jz      short loc_18000B4BA
0x18000b498  cmp     [r15+2A0h], r10d
0x18000b49f  jnz     short loc_18000B4BA
0x18000b4a1  cmp     bx, di
0x18000b4a4  jnz     short loc_18000B4AE
0x18000b4a6  cmp     r11w, si
0x18000b4aa  jnz     short loc_18000B4B6
0x18000b4ac  jmp     short loc_18000B4B0
0x18000b4ae  jbe     short loc_18000B4B6
0x18000b4b0  movzx   edi, bx
0x18000b4b3  mov     esi, r11d
0x18000b4b6  or      r14d, 4
0x18000b4ba  mov     r12d, 4
0x18000b4c0  test    [r15+27Ch], r10b
0x18000b4c7  jz      loc_18000B575
0x18000b4cd  mov     rbx, [r15+280h]
0x18000b4d4  mov     r13d, r11d
0x18000b4d7  mov     [rbp+var_28], rbx
0x18000b4db  mov     eax, r13d
0x18000b4de  lea     rdx, [rbp+FileTime]; lpFileTime
0x18000b4e2  movsxd  rax, ds:rva dword_18001EA50[r9+rax*4]
0x18000b4ea  lea     rcx, [rax+rax*2]
0x18000b4ee  lea     rcx, ds:1EA78h[rcx*8]
0x18000b4f6  add     rcx, r9; lpSystemTime
0x18000b4f9  call    cs:__imp_SystemTimeToFileTime
0x18000b4ff  xor     r11d, r11d
0x18000b502  test    eax, eax
0x18000b504  jz      short loc_18000B546
0x18000b506  mov     eax, dword ptr [rbp+var_28+4]
0x18000b509  lea     r10d, [r11+1]
0x18000b50d  mov     ecx, [rbp+FileTime.dwHighDateTime]
0x18000b510  mov     dword ptr [rbp+var_18+4], eax
0x18000b513  mov     eax, [rbp+FileTime.dwLowDateTime]
0x18000b516  mov     dword ptr [rbp+var_20], eax
0x18000b519  mov     dword ptr [rbp+var_20+4], ecx
0x18000b51c  mov     rax, [rbp+var_20]
0x18000b520  mov     dword ptr [rbp+var_18], ebx
0x18000b523  cmp     [rbp+var_18], rax
0x18000b527  jb      short loc_18000B56D
0x18000b529  mov     r12d, r13d
0x18000b52c  lea     r9, cs:180000000h
0x18000b533  add     r13d, r10d
0x18000b536  mov     r12d, ds:rva dword_18001EA50[r9+r12*4]
0x18000b53e  cmp     r13d, 6
0x18000b542  jb      short loc_18000B4DB
0x18000b544  jmp     short loc_18000B56D
0x18000b546  lea     r9, aFailedToConver_1; "Failed to convert system time to file t"...
0x18000b54d  mov     r8d, 171h
0x18000b553  lea     rdx, aAhggenomecompu; "AhgGenomeCompute"
0x18000b55a  mov     ecx, 2
0x18000b55f  call    AslLogCallPrintf
0x18000b564  mov     r10d, 1
0x18000b56a  xor     r11d, r11d
0x18000b56d  mov     r9d, r10d
0x18000b570  or      r14d, r10d
0x18000b573  jmp     short loc_18000B578
0x18000b575  mov     r9d, r11d
0x18000b578  mov     ebx, 4
0x18000b57d  mov     r8d, ebx
0x18000b580  test    [r15+2ACh], r10b
0x18000b587  jz      short loc_18000B5DB
0x18000b589  mov     edx, r11d
0x18000b58c  mov     r11d, [r15+2B0h]
0x18000b593  lea     r15, cs:180000000h
0x18000b59a  mov     eax, edx
0x18000b59c  movsxd  r10, ds:rva dword_18001EA50[r15+rax*4]
0x18000b5a4  lea     rcx, [r10+r10*2]
0x18000b5a8  movzx   eax, ds:rva word_18001EA78[r15+rcx*8]
0x18000b5b1  cmp     r11d, eax
0x18000b5b4  jbe     short loc_18000B5C9
0x18000b5b6  mov     r8d, r10d
0x18000b5b9  mov     r10d, 1
0x18000b5bf  add     edx, r10d
0x18000b5c2  cmp     edx, 6
0x18000b5c5  jb      short loc_18000B59A
0x18000b5c7  jmp     short loc_18000B5CF
0x18000b5c9  mov     r10d, 1
0x18000b5cf  or      r14d, 10h
0x18000b5d3  mov     eax, r10d
0x18000b5d6  xor     r11d, r11d
0x18000b5d9  jmp     short loc_18000B5E5
0x18000b5db  mov     eax, r11d
0x18000b5de  lea     r15, cs:180000000h
0x18000b5e5  cmp     r9d, r10d
0x18000b5e8  jnz     short loc_18000B5F8
0x18000b5ea  cmp     eax, r10d
0x18000b5ed  jnz     short loc_18000B602
0x18000b5ef  cmp     r12d, r8d
0x18000b5f2  cmovge  r12d, r8d
0x18000b5f6  jmp     short loc_18000B602
0x18000b5f8  cmp     eax, r10d
0x18000b5fb  mov     r12d, ebx
0x18000b5fe  cmovz   r12d, r8d
0x18000b602  test    r14d, r14d
0x18000b605  jnz     short loc_18000B62E
0x18000b607  lea     r9, aBadTimestamp; "Bad timestamp"
0x18000b60e  mov     r8d, 1A0h
0x18000b614  lea     rdx, aAhggenomecompu; "AhgGenomeCompute"
0x18000b61b  mov     ecx, r10d
0x18000b61e  mov     ebx, 3EEh
0x18000b623  call    AslLogCallPrintf
0x18000b628  lea     r10d, [r14+1]
0x18000b62c  jmp     short loc_18000B661
0x18000b62e  movsxd  rax, r12d
0x18000b631  lea     rcx, [rax+rax*2]
0x18000b635  mov     edx, ds:rva dword_18001EA74[r15+rcx*8]
0x18000b63d  mov     eax, edx
0x18000b63f  shr     eax, 10h
0x18000b642  cmp     ax, di
0x18000b645  jnz     short loc_18000B64F
0x18000b647  cmp     dx, si
0x18000b64a  jz      short loc_18000B658
0x18000b64c  cmp     ax, di
0x18000b64f  ja      short loc_18000B658
0x18000b651  jnz     short loc_18000B65E
  ... truncated ...
```
