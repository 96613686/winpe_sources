# acmdStreamSize

- ea: `0x18000330c`
- end: `0x180003580`
- name: `acmdStreamSize`
- size: `628`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1800036c0`

## callees

- `0x18000330c`

## pseudocode

```c
__int64 __fastcall acmdStreamSize(__int64 a1, _DWORD *a2)
{
  __int64 v2; // r9
  __int64 v4; // rdi
  unsigned int v6; // r8d
  int v7; // r11d
  unsigned int v8; // eax
  unsigned int v9; // ecx
  unsigned int v10; // r8d
  unsigned int v11; // r10d
  unsigned int v12; // r11d
  unsigned int v13; // esi
  unsigned int v14; // r11d
  unsigned int v15; // ecx
  unsigned int v16; // edi
  int v17; // eax
  unsigned int v18; // r10d
  unsigned int v19; // ecx
  unsigned int v20; // r10d
  int v21; // ecx
  unsigned int v22; // edx
  unsigned int v23; // r9d
  unsigned int v24; // r8d
  int v25; // edx
  int v26; // r10d
  unsigned int v27; // ecx
  int v28; // r10d

  v2 = *(_QWORD *)(a1 + 12);
  if ( *(_DWORD *)(v2 + 4) )
  {
    v4 = *(_QWORD *)(a1 + 4);
    if ( (a2[1] & 0xF) == 0 )
    {
      a2[3] = 0;
      v14 = 1152;
      if ( *(_WORD *)v4 == 85 )
      {
        if ( *(_DWORD *)(v4 + 4) <= 0x5DC0u )
          v14 = 576;
        v15 = *(_DWORD *)(v4 + 8) * v14 / *(_DWORD *)(v4 + 4);
        if ( !v15 )
          return 512;
        v16 = *(_DWORD *)(v4 + 4) / *(_DWORD *)(v2 + 4);
        if ( !v16 )
          return 512;
        v17 = a2[2] / v15 + 1;
        if ( !(a2[2] % v15) )
          v17 = a2[2] / v15;
        v18 = v14 * v17 / v16 * (*(unsigned __int16 *)(v2 + 14) >> 3 << (*(unsigned __int16 *)(v2 + 2) >> 1));
        if ( !v18 )
          return 512;
      }
      else
      {
        v19 = 1;
        v20 = a2[2] / (*(unsigned __int16 *)(v4 + 14) >> 3 << (*(unsigned __int16 *)(v4 + 2) >> 1));
        if ( *(_DWORD *)(v2 + 4) <= 0x5DC0u )
          v14 = 576;
        if ( v14 * (*(_DWORD *)(v4 + 4) / *(_DWORD *)(v2 + 4)) > 1 )
          v19 = v14 * (*(_DWORD *)(v4 + 4) / *(_DWORD *)(v2 + 4));
        v21 = v20 / v19;
        v22 = *(_DWORD *)(v2 + 8) * v14 % *(_DWORD *)(v2 + 4);
        v23 = *(_DWORD *)(v2 + 8) * v14 / *(_DWORD *)(v2 + 4);
        v24 = v22;
        v25 = v20 % v14;
        v26 = v21 + 1;
        if ( !v25 )
          v26 = v21;
        v27 = v23 + 1;
        if ( !v24 )
          v27 = v23;
        v28 = v27 * v26;
        if ( !v28 )
          return 512;
        v18 = v28 + 3000;
      }
      a2[3] = v18;
      return 0;
    }
    if ( (a2[1] & 0xF) != 1 )
      return 8;
    a2[2] = 0;
    if ( *(_WORD *)v2 == 85 )
    {
      v6 = a2[3];
      if ( v6 <= 0xBB8 )
        return 512;
      v7 = 1152;
      if ( *(_DWORD *)(v2 + 4) <= 0x5DC0u )
        v7 = 576;
      v8 = (unsigned int)(*(_DWORD *)(v2 + 8) * v7) / *(_DWORD *)(v2 + 4);
      if ( !v8 )
        return 512;
      v9 = v8 + 1;
      if ( !((unsigned int)(*(_DWORD *)(v2 + 8) * v7) % *(_DWORD *)(v2 + 4)) )
        v9 = (unsigned int)(*(_DWORD *)(v2 + 8) * v7) / *(_DWORD *)(v2 + 4);
      v10 = v7
          * *(_DWORD *)(v4 + 4)
          / *(_DWORD *)(v2 + 4)
          * (*(unsigned __int16 *)(v4 + 14) >> 3 << (*(unsigned __int16 *)(v4 + 2) >> 1))
          * ((v6 - 3000)
           / v9);
    }
    else
    {
      v11 = *(_DWORD *)(v4 + 4);
      v12 = 1152;
      v13 = v11 / *(_DWORD *)(v2 + 4);
      if ( v11 <= 0x5DC0 )
        v12 = 576;
      if ( !v13 || !v11 )
        return 512;
      v10 = *(_DWORD *)(v4 + 8)
          * v12
          / v11
          * (a2[3]
           / (*(unsigned __int16 *)(v2 + 14) >> 3 << (*(unsigned __int16 *)(v2 + 2) >> 1))
           / (v12
            / v13));
    }
    if ( v10 )
    {
      a2[2] = v10;
      return 0;
    }
  }
  return 512;
}

```

## disassembly

```asm
0x18000330c  push    rbx
0x18000330e  push    rsi
0x18000330f  push    rdi
0x180003310  mov     r9, [rcx+0Ch]
0x180003314  mov     rbx, rdx
0x180003317  cmp     dword ptr [r9+4], 0
0x18000331c  jz      loc_1800034DB
0x180003322  mov     eax, [rdx+4]
0x180003325  mov     rdi, [rcx+4]
0x180003329  and     eax, 0Fh
0x18000332c  jz      loc_180003459
0x180003332  cmp     eax, 1
0x180003335  jz      short loc_180003341
0x180003337  mov     eax, 8
0x18000333c  jmp     loc_1800034E0
0x180003341  mov     eax, 55h ; 'U'
0x180003346  mov     dword ptr [rdx+8], 0
0x18000334d  cmp     ax, [r9]
0x180003351  jnz     short loc_1800033CD
0x180003353  mov     r8d, [rdx+0Ch]
0x180003357  cmp     r8d, 0BB8h
0x18000335e  jbe     loc_1800034DB
0x180003364  cmp     dword ptr [r9+4], 5DC0h
0x18000336c  mov     eax, 240h
0x180003371  mov     r11d, 480h
0x180003377  cmovbe  r11d, eax
0x18000337b  xor     edx, edx
0x18000337d  mov     eax, r11d
0x180003380  imul    eax, [r9+8]
0x180003385  div     dword ptr [r9+4]
0x180003389  test    eax, eax
0x18000338b  jz      loc_1800034DB
0x180003391  test    edx, edx
0x180003393  lea     ecx, [rax+1]
0x180003396  cmovz   ecx, eax
0x180003399  xor     edx, edx
0x18000339b  lea     eax, [r8-0BB8h]
0x1800033a2  div     ecx
0x1800033a4  movzx   edx, word ptr [rdi+0Eh]
0x1800033a8  movzx   ecx, word ptr [rdi+2]
0x1800033ac  mov     r8d, eax
0x1800033af  mov     eax, [rdi+4]
0x1800033b2  shr     edx, 3
0x1800033b5  shr     ecx, 1
0x1800033b7  shl     edx, cl
0x1800033b9  imul    r8d, edx
0x1800033bd  xor     edx, edx
0x1800033bf  div     dword ptr [r9+4]
0x1800033c3  imul    r8d, eax
0x1800033c7  imul    r8d, r11d
0x1800033cb  jmp     short loc_180003445
0x1800033cd  mov     r10d, [rdi+4]
0x1800033d1  xor     edx, edx
0x1800033d3  mov     eax, r10d
0x1800033d6  mov     r11d, 480h
0x1800033dc  div     dword ptr [r9+4]
0x1800033e0  cmp     r10d, 5DC0h
0x1800033e7  mov     esi, eax
0x1800033e9  mov     eax, 240h
0x1800033ee  cmovbe  r11d, eax
0x1800033f2  test    esi, esi
0x1800033f4  jz      loc_1800034DB
0x1800033fa  test    r10d, r10d
0x1800033fd  jz      loc_1800034DB
0x180003403  movzx   r8d, word ptr [r9+0Eh]
0x180003408  xor     edx, edx
0x18000340a  movzx   ecx, word ptr [r9+2]
0x18000340f  mov     eax, [rbx+0Ch]
0x180003412  shr     r8d, 3
0x180003416  shr     ecx, 1
0x180003418  shl     r8d, cl
0x18000341b  div     r8d
0x18000341e  xor     edx, edx
0x180003420  mov     r8d, eax
0x180003423  mov     eax, r11d
0x180003426  imul    r11d, [rdi+8]
0x18000342b  div     esi
0x18000342d  xor     edx, edx
0x18000342f  mov     ecx, eax
0x180003431  mov     eax, r8d
0x180003434  div     ecx
0x180003436  xor     edx, edx
0x180003438  mov     r8d, eax
0x18000343b  mov     eax, r11d
0x18000343e  div     r10d
0x180003441  imul    r8d, eax
0x180003445  test    r8d, r8d
0x180003448  jz      loc_1800034DB
0x18000344e  mov     [rbx+8], r8d
0x180003452  xor     eax, eax
0x180003454  jmp     loc_1800034E0
0x180003459  mov     eax, 55h ; 'U'
0x18000345e  mov     dword ptr [rdx+0Ch], 0
0x180003465  mov     r11d, 480h
0x18000346b  cmp     ax, [rdi]
0x18000346e  jnz     short loc_1800034E4
0x180003470  cmp     dword ptr [rdi+4], 5DC0h
0x180003477  mov     eax, 240h
0x18000347c  cmovbe  r11d, eax
0x180003480  xor     edx, edx
0x180003482  mov     eax, r11d
0x180003485  imul    eax, [rdi+8]
0x180003489  div     dword ptr [rdi+4]
0x18000348c  mov     ecx, eax
0x18000348e  test    eax, eax
0x180003490  jz      short loc_1800034DB
0x180003492  mov     eax, [rdi+4]
0x180003495  xor     edx, edx
0x180003497  div     dword ptr [r9+4]
0x18000349b  mov     edi, eax
0x18000349d  test    eax, eax
0x18000349f  jz      short loc_1800034DB
0x1800034a1  mov     eax, [rbx+8]
0x1800034a4  xor     edx, edx
0x1800034a6  movzx   r10d, word ptr [r9+0Eh]
0x1800034ab  div     ecx
0x1800034ad  movzx   ecx, word ptr [r9+2]
0x1800034b2  shr     r10d, 3
0x1800034b6  mov     r8d, eax
0x1800034b9  inc     eax
0x1800034bb  shr     ecx, 1
0x1800034bd  shl     r10d, cl
0x1800034c0  test    edx, edx
0x1800034c2  cmovz   eax, r8d
0x1800034c6  xor     edx, edx
0x1800034c8  imul    eax, r11d
0x1800034cc  div     edi
0x1800034ce  imul    r10d, eax
0x1800034d2  test    r10d, r10d
0x1800034d5  jnz     loc_180003577
0x1800034db  mov     eax, 200h
0x1800034e0  pop     rdi
0x1800034e1  pop     rsi
0x1800034e2  pop     rbx
0x1800034e3  retn
0x1800034e4  movzx   r8d, word ptr [rdi+0Eh]
0x1800034e9  xor     edx, edx
0x1800034eb  movzx   ecx, word ptr [rdi+2]
0x1800034ef  mov     eax, [rbx+8]
0x1800034f2  shr     ecx, 1
0x1800034f4  shr     r8d, 3
0x1800034f8  shl     r8d, cl
0x1800034fb  mov     ecx, 1
0x180003500  div     r8d
0x180003503  cmp     dword ptr [r9+4], 5DC0h
0x18000350b  mov     r10d, eax
0x18000350e  mov     eax, 240h
0x180003513  cmovbe  r11d, eax
0x180003517  mov     eax, [rdi+4]
0x18000351a  xor     edx, edx
0x18000351c  div     dword ptr [r9+4]
0x180003520  imul    eax, r11d
0x180003524  cmp     eax, ecx
0x180003526  cmova   ecx, eax
0x180003529  xor     edx, edx
0x18000352b  mov     eax, r10d
0x18000352e  div     ecx
0x180003530  xor     edx, edx
0x180003532  mov     ecx, eax
0x180003534  mov     eax, r11d
0x180003537  imul    eax, [r9+8]
0x18000353c  div     dword ptr [r9+4]
0x180003540  mov     r9d, eax
0x180003543  mov     r8d, edx
0x180003546  xor     edx, edx
0x180003548  mov     eax, r10d
0x18000354b  div     r11d
0x18000354e  lea     r10d, [rcx+1]
0x180003552  test    edx, edx
0x180003554  cmovz   r10d, ecx
0x180003558  test    r8d, r8d
0x18000355b  lea     ecx, [r9+1]
0x18000355f  cmovz   ecx, r9d
0x180003563  imul    r10d, ecx
0x180003567  test    r10d, r10d
0x18000356a  jz      loc_1800034DB
0x180003570  add     r10d, 0BB8h
0x180003577  mov     [rbx+0Ch], r10d
0x18000357b  jmp     loc_180003452
```
