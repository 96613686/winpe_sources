# GCFixOnePath

- ea: `0x14006039c`
- end: `0x140060728`
- name: `GCFixOnePath`
- size: `908`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x14006b3cc`
- `0x14006b7ac`

## callees

- `0x14003d74c`
- `0x14003d880`
- `0x14006039c`
- `0x140060730`
- `0x1400607fc`

## pseudocode

```c
__int64 __fastcall GCFixOnePath(__int64 a1)
{
  __int64 v1; // rbx
  __int64 v2; // rcx
  __int64 v3; // rsi
  int v4; // edi
  int v5; // r14d
  __int64 v6; // rbp
  __int64 v7; // r12
  __int64 v8; // rax
  __int64 v9; // r8
  __int64 v10; // rcx
  __int64 v11; // rax
  int v12; // r14d
  int v13; // eax
  int v14; // r8d
  __int64 i; // rdx
  __int64 v16; // rcx
  int v17; // r13d
  unsigned int v18; // r13d
  int v19; // r8d
  __int64 j; // r9
  __int64 v21; // rcx
  __int64 k; // r9
  __int64 v23; // rcx
  int v24; // edx
  int v25; // r8d
  int v26; // r10d
  unsigned int v27; // r10d
  int v28; // r9d
  int v29; // r11d
  __int64 m; // rdx
  __int64 v31; // r9
  int v32; // eax
  unsigned int v33; // eax
  __int64 v34; // rax
  int v35; // r15d
  int v36; // r14d
  int v37; // r11d
  int v38; // esi
  int v39; // edi
  int v40; // edi
  unsigned int v41; // r13d
  int v42; // r9d
  unsigned int v43; // r10d
  unsigned int v44; // eax
  int v45; // ecx
  int v46; // edx
  int v47; // r11d
  int v48; // eax
  __int64 v49; // rax
  _DWORD *v50; // rdx
  int v51; // r8d
  int v52; // edx
  int v53; // ecx

  v1 = a1;
  if ( !a1 )
    return 0;
  v2 = *(_QWORD *)(a1 + 64);
  if ( !v2 )
    return 0;
  v3 = pPathListBuffer;
  v4 = 0;
  v5 = 0;
  v6 = v1;
  v7 = v1;
  do
  {
    if ( v4 >= 500 || v6 != v1 && (*(_BYTE *)(v6 + 72) & 2) != 0 )
      break;
    v5 += *(__int16 *)(v6 + 10);
    v8 = v4++;
    *(_QWORD *)(v3 + 8 * v8) = v2;
    v6 = *(_QWORD *)(*(_QWORD *)(v6 + 64) + 24LL);
    v7 = v6;
    v2 = *(_QWORD *)(v6 + 64);
  }
  while ( v2 );
  if ( v4 > 2 )
  {
    v9 = 0;
    do
    {
      v10 = *(_QWORD *)(*(_QWORD *)(v3 + 8 * v9) + 16LL);
      *(_DWORD *)(v10 + 72) &= ~0x10u;
      v11 = *(_QWORD *)(v3 + 8 * v9);
      v9 = (unsigned int)(v9 + 1);
      *(_DWORD *)(*(_QWORD *)(v11 + 24) + 72LL) &= ~0x10u;
    }
    while ( (int)v9 < v4 );
  }
  v12 = *(__int16 *)(v6 + 10) + v5;
  v13 = fixdiv(
          (unsigned int)(12 * (*(_DWORD *)(v1 + 24) - *(_DWORD *)(v1 + 20))),
          (unsigned int)(*(_DWORD *)(v1 + 16) - *(_DWORD *)(v1 + 12)));
  if ( v13 >= 39322 )
    v13 = 39322;
  ClumpCounters(v3, (unsigned int)v4, (unsigned int)v13);
  SortGroupsByFrac(v3, (unsigned int)v4);
  v14 = 0;
  for ( i = 0; (int)i < v4; v14 += *(__int16 *)(v16 + 42) )
  {
    v16 = *(_QWORD *)(v3 + 8 * i);
    i = (unsigned int)(i + 1);
  }
  if ( (*(_BYTE *)(v1 + 72) & 2) != 0 )
    v17 = *(_DWORD *)(v1 + 40);
  else
    v17 = *(_DWORD *)(v1 + 24);
  v18 = v17 - *(_DWORD *)(((*(_DWORD *)(v6 + 72) & 2) != 0 ? 0x10 : 0) + v6 + 20);
  v19 = v12 + v14 - ((int)(v18 + 0x8000) >> 16);
  while ( 1 )
  {
    v19 += v4;
    if ( v19 >= 0 )
      break;
    for ( j = 0; (int)j < v4; *(_DWORD *)(v21 + 40) += 0x10000 )
    {
      v21 = *(_QWORD *)(v3 + 8 * j);
      j = (unsigned int)(j + 1);
    }
  }
  while ( v19 > v4 )
  {
    for ( k = 0; (int)k < v4; *(_DWORD *)(v23 + 40) -= 0x10000 )
    {
      v23 = *(_QWORD *)(v3 + 8 * k);
      k = (unsigned int)(k + 1);
    }
    v19 -= v4;
  }
  v24 = (int)(fixmul(v18) + 0x8000) >> 16;
  if ( v24 > 0 && v25 > 0 )
  {
    _mm_lfence();
    v27 = *(unsigned __int8 *)(*(_QWORD *)(v3 + 8LL * v25 - 8) + 44LL);
    if ( v27 != v25 - 1 )
    {
      v28 = 0;
      if ( *(unsigned __int8 *)(*(_QWORD *)v3 + 44LL) < v27 )
      {
        do
          ++v28;
        while ( *(unsigned __int8 *)(*(_QWORD *)(v3 + 8LL * v28) + 44LL) < v27 );
      }
      if ( v25 - v28 > v24 )
      {
        if ( (int)(v27 - v25 + 1) <= v24 )
          v25 = v27 + 1;
      }
      else
      {
        v25 = v28;
      }
    }
    v26 = 2;
  }
  v29 = 0;
  for ( m = 0; (int)m < v4; v29 += *(__int16 *)(v34 + 42) )
  {
    v31 = *(_QWORD *)(v3 + 8 * m);
    v32 = *(_DWORD *)(v31 + 40);
    if ( v32 == 0xFFFF )
    {
      ++v25;
      v33 = 0x10000;
    }
    else
    {
      v33 = v32 & 0xFFFF0000;
      if ( (int)m >= v25 )
        v33 += 0x10000;
    }
    *(_DWORD *)(v31 + 40) = v33;
    v34 = *(_QWORD *)(v3 + 8 * m);
    m = (unsigned int)(m + 1);
  }
  v35 = *(_DWORD *)(v1 + 72);
  if ( ((unsigned __int8)v35 & (unsigned __int8)v26) == 0 )
  {
    v36 = v12 << 16;
    v37 = v29 << 16;
    v38 = *(_DWORD *)(v1 + 36) - *(_DWORD *)(v1 + 40);
    if ( v38 < 0 )
      v38 = *(_DWORD *)(v1 + 40) - *(_DWORD *)(v1 + 36);
    v39 = v37 + v36;
    if ( ((unsigned __int8)v26 & *(_BYTE *)(v6 + 72)) != 0 )
    {
      v40 = *(_DWORD *)(v7 + 36) + v39;
    }
    else
    {
      v41 = v18 - v37 - v36;
      v42 = *(_DWORD *)(v6 + 20) + *(_DWORD *)(v6 + 24);
      v43 = ((int)(v38 + *(_DWORD *)(v1 + 24) + *(_DWORD *)(v1 + 20) - v41) / v26 + 0x8000) & 0xFFFF0000;
      v44 = ((int)(v42 + *(_DWORD *)(v7 + 36) + v41 - *(_DWORD *)(v6 + 40)) / 2 + 0x8000) & 0xFFFF0000;
      v40 = v44 + v39;
      v45 = v42
          + *(_DWORD *)(v7 + 36)
          + v38
          + *(_DWORD *)(v1 + 24)
          + *(_DWORD *)(v1 + 20)
          - *(_DWORD *)(v6 + 40)
          - 2 * (v40 + v44);
      v46 = -v45;
      if ( v45 > 0 )
        v46 = v42
            + *(_DWORD *)(v7 + 36)
            + v38
            + *(_DWORD *)(v1 + 24)
            + *(_DWORD *)(v1 + 20)
            - *(_DWORD *)(v6 + 40)
            - 2 * (v40 + v44);
      v47 = v42
          + *(_DWORD *)(v7 + 36)
          + v38
          + *(_DWORD *)(v1 + 24)
          + *(_DWORD *)(v1 + 20)
          + 2 * (v36 + v37 - 2 * v43)
          - *(_DWORD *)(v6 + 40);
      v48 = -v47;
      if ( v47 > 0 )
        v48 = v47;
      if ( v48 < v46 )
        v40 = v43;
      v26 = 2;
    }
    *(_DWORD *)(v1 + 40) = v40;
    *(_DWORD *)(v1 + 72) = v26 | v35;
    *(_DWORD *)(v1 + 36) = v40 - v38;
    *(_WORD *)(v1 + 76) = 0;
  }
  do
  {
    v49 = *(_QWORD *)(v1 + 64);
    v50 = (_DWORD *)(v1 + 36);
    v1 = *(_QWORD *)(v49 + 24);
    v51 = *(_DWORD *)(v1 + 72);
    if ( ((unsigned __int8)v51 & (unsigned __int8)v26) != 0 )
      break;
    v52 = *v50 - *(_DWORD *)(v49 + 40);
    v53 = *(_DWORD *)(v1 + 40) - *(_DWORD *)(v1 + 36);
    *(_DWORD *)(v1 + 40) = v52;
    *(_DWORD *)(v1 + 36) = v52 - v53;
    *(_DWORD *)(v1 + 72) = v26 | v51;
    *(_WORD *)(v1 + 76) = 0;
  }
  while ( *(_QWORD *)(v1 + 64) );
  return 1;
}

```

## disassembly

```asm
0x14006039c  push    rbx
0x14006039e  push    rbp
0x14006039f  push    rsi
0x1400603a0  push    rdi
0x1400603a1  push    r12
0x1400603a3  push    r13
0x1400603a5  push    r14
0x1400603a7  push    r15
0x1400603a9  sub     rsp, 28h
0x1400603ad  mov     r15d, r8d
0x1400603b0  mov     rbx, rcx
0x1400603b3  test    rcx, rcx
0x1400603b6  jz      loc_140060715
0x1400603bc  mov     rcx, [rcx+40h]
0x1400603c0  test    rcx, rcx
0x1400603c3  jz      loc_140060715
0x1400603c9  mov     rsi, cs:pPathListBuffer
0x1400603d0  xor     edi, edi
0x1400603d2  xor     r14d, r14d
0x1400603d5  mov     rbp, rbx
0x1400603d8  mov     r12, rbx
0x1400603db  lea     r13d, [rdi+2]
0x1400603df  cmp     edi, 1F4h
0x1400603e5  jge     short loc_140060416
0x1400603e7  cmp     rbp, rbx
0x1400603ea  jz      short loc_1400603F2
0x1400603ec  test    [rbp+48h], r13b
0x1400603f0  jnz     short loc_140060416
0x1400603f2  movsx   eax, word ptr [rbp+0Ah]
0x1400603f6  add     r14d, eax
0x1400603f9  movsxd  rax, edi
0x1400603fc  inc     edi
0x1400603fe  mov     [rsi+rax*8], rcx
0x140060402  mov     rax, [rbp+40h]
0x140060406  mov     rbp, [rax+18h]
0x14006040a  mov     r12, rbp
0x14006040d  mov     rcx, [rbp+40h]
0x140060411  test    rcx, rcx
0x140060414  jnz     short loc_1400603DF
0x140060416  cmp     edi, r13d
0x140060419  jle     short loc_140060444
0x14006041b  xor     r8d, r8d
0x14006041e  mov     r9d, 0FFFFFFEFh
0x140060424  mov     rax, [rsi+r8*8]
0x140060428  mov     rcx, [rax+10h]
0x14006042c  and     [rcx+48h], r9d
0x140060430  mov     rax, [rsi+r8*8]
0x140060434  inc     r8d
0x140060437  mov     rcx, [rax+18h]
0x14006043b  and     [rcx+48h], r9d
0x14006043f  cmp     r8d, edi
0x140060442  jl      short loc_140060424
0x140060444  movsx   eax, word ptr [rbp+0Ah]
0x140060448  mov     edx, [rbx+10h]
0x14006044b  add     r14d, eax
0x14006044e  mov     eax, [rbx+18h]
0x140060451  sub     eax, [rbx+14h]
0x140060454  sub     edx, [rbx+0Ch]
0x140060457  lea     ecx, [rax+rax*2]
0x14006045a  shl     ecx, 2
0x14006045d  call    fixdiv
0x140060462  mov     ecx, 999Ah
0x140060467  mov     edx, edi
0x140060469  cmp     eax, ecx
0x14006046b  cmovge  eax, ecx
0x14006046e  mov     rcx, rsi
0x140060471  mov     r8d, eax
0x140060474  call    ClumpCounters
0x140060479  mov     edx, edi
0x14006047b  mov     rcx, rsi
0x14006047e  call    SortGroupsByFrac
0x140060483  xor     r8d, r8d
0x140060486  xor     edx, edx
0x140060488  test    edi, edi
0x14006048a  jle     short loc_14006049D
0x14006048c  mov     rcx, [rsi+rdx*8]
0x140060490  inc     edx
0x140060492  movsx   eax, word ptr [rcx+2Ah]
0x140060496  add     r8d, eax
0x140060499  cmp     edx, edi
0x14006049b  jl      short loc_14006048C
0x14006049d  mov     eax, [rbp+48h]
0x1400604a0  mov     ecx, r15d
0x1400604a3  sar     ecx, 1
0x1400604a5  mov     edx, r15d
0x1400604a8  sub     edx, ecx
0x1400604aa  mov     r10d, r13d
0x1400604ad  and     eax, r13d
0x1400604b0  cmovz   edx, r15d
0x1400604b4  neg     eax
0x1400604b6  sbb     rax, rax
0x1400604b9  and     eax, 10h
0x1400604bc  test    [rbx+48h], r10b
0x1400604c0  jz      short loc_1400604CA
0x1400604c2  mov     r13d, [rbx+28h]
0x1400604c6  sub     edx, ecx
0x1400604c8  jmp     short loc_1400604CE
0x1400604ca  mov     r13d, [rbx+18h]
0x1400604ce  sub     r13d, [rax+rbp+14h]
0x1400604d3  lea     eax, [r13+8000h]
0x1400604da  sar     eax, 10h
0x1400604dd  sub     r8d, eax
0x1400604e0  add     r8d, r14d
0x1400604e3  jmp     short loc_1400604FF
0x1400604e5  xor     r9d, r9d
0x1400604e8  test    edi, edi
0x1400604ea  jle     short loc_1400604FF
0x1400604ec  mov     rcx, [rsi+r9*8]
0x1400604f0  inc     r9d
0x1400604f3  add     dword ptr [rcx+28h], 10000h
0x1400604fa  cmp     r9d, edi
0x1400604fd  jl      short loc_1400604EC
0x1400604ff  add     r8d, edi
0x140060502  js      short loc_1400604E5
0x140060504  mov     r15d, 0FFFF0000h
0x14006050a  jmp     short loc_140060526
0x14006050c  xor     r9d, r9d
0x14006050f  test    edi, edi
0x140060511  jle     short loc_140060523
0x140060513  mov     rcx, [rsi+r9*8]
0x140060517  inc     r9d
0x14006051a  add     [rcx+28h], r15d
0x14006051e  cmp     r9d, edi
0x140060521  jl      short loc_140060513
0x140060523  sub     r8d, edi
0x140060526  cmp     r8d, edi
0x140060529  jg      short loc_14006050C
0x14006052b  mov     ecx, r13d
0x14006052e  call    fixmul
0x140060533  lea     edx, [rax+8000h]
0x140060539  sar     edx, 10h
0x14006053c  test    edx, edx
0x14006053e  jle     short loc_1400605A5
0x140060540  test    r8d, r8d
0x140060543  jle     short loc_1400605A5
0x140060545  lfence
0x140060548  movsxd  rax, r8d
0x14006054b  mov     rcx, [rsi+rax*8-8]
0x140060550  lea     eax, [r8-1]
0x140060554  movzx   r10d, byte ptr [rcx+2Ch]
0x140060559  cmp     r10d, eax
0x14006055c  jz      short loc_14006059F
0x14006055e  mov     rax, [rsi]
0x140060561  xor     r9d, r9d
0x140060564  movzx   ecx, byte ptr [rax+2Ch]
0x140060568  cmp     ecx, r10d
0x14006056b  jnb     short loc_140060580
0x14006056d  inc     r9d
0x140060570  movsxd  rax, r9d
0x140060573  mov     rcx, [rsi+rax*8]
0x140060577  movzx   eax, byte ptr [rcx+2Ch]
0x14006057b  cmp     eax, r10d
0x14006057e  jb      short loc_14006056D
0x140060580  mov     eax, r8d
0x140060583  sub     eax, r9d
0x140060586  cmp     eax, edx
0x140060588  jg      short loc_14006058F
0x14006058a  mov     r8d, r9d
0x14006058d  jmp     short loc_14006059F
0x14006058f  mov     eax, r10d
0x140060592  sub     eax, r8d
0x140060595  inc     eax
0x140060597  cmp     eax, edx
0x140060599  jg      short loc_14006059F
0x14006059b  lea     r8d, [r10+1]
0x14006059f  mov     r10d, 2
0x1400605a5  xor     r11d, r11d
0x1400605a8  xor     edx, edx
0x1400605aa  test    edi, edi
0x1400605ac  jle     short loc_1400605E9
0x1400605ae  mov     r9, [rsi+rdx*8]
0x1400605b2  mov     eax, [r9+28h]
0x1400605b6  cmp     eax, 0FFFFh
0x1400605bb  jnz     short loc_1400605C7
0x1400605bd  inc     r8d
0x1400605c0  mov     eax, 10000h
0x1400605c5  jmp     short loc_1400605D4
0x1400605c7  and     eax, r15d
0x1400605ca  cmp     edx, r8d
0x1400605cd  jl      short loc_1400605D4
0x1400605cf  add     eax, 10000h
0x1400605d4  mov     [r9+28h], eax
0x1400605d8  mov     rax, [rsi+rdx*8]
0x1400605dc  inc     edx
0x1400605de  movsx   ecx, word ptr [rax+2Ah]
0x1400605e2  add     r11d, ecx
0x1400605e5  cmp     edx, edi
0x1400605e7  jl      short loc_1400605AE
0x1400605e9  mov     r15d, [rbx+48h]
0x1400605ed  test    r10b, r15b
0x1400605f0  jnz     loc_1400606D3
0x1400605f6  mov     eax, [rbx+28h]
0x1400605f9  sub     eax, [rbx+24h]
0x1400605fc  shl     r14d, 10h
0x140060600  mov     esi, eax
0x140060602  shl     r11d, 10h
0x140060606  neg     esi
0x140060608  cmovs   esi, eax
0x14006060b  lea     edi, [r11+r14]
0x14006060f  test    [rbp+48h], r10b
0x140060613  jz      short loc_14006061F
0x140060615  add     edi, [r12+24h]
0x14006061a  jmp     loc_1400606BE
0x14006061f  mov     r8d, [rbx+14h]
0x140060623  sub     r13d, r11d
0x140060626  add     r8d, [rbx+18h]
0x14006062a  sub     r13d, r14d
0x14006062d  mov     r9d, [rbp+18h]
0x140060631  mov     eax, r8d
0x140060634  add     r9d, [rbp+14h]
0x140060638  sub     eax, r13d
0x14006063b  sub     r13d, [rbp+28h]
0x14006063f  add     eax, esi
0x140060641  add     r13d, [r12+24h]
0x140060646  cdq
0x140060647  idiv    r10d
0x14006064a  mov     ecx, 0FFFF0000h
0x14006064f  lea     r10d, [rax+8000h]
0x140060656  and     r10d, ecx
0x140060659  lea     eax, [r9+r13]
0x14006065d  cdq
0x14006065e  mov     r13d, 2
0x140060664  idiv    r13d
0x140060667  add     eax, 8000h
0x14006066c  and     eax, ecx
0x14006066e  mov     ecx, r8d
0x140060671  sub     ecx, [rbp+28h]
0x140060674  add     edi, eax
0x140060676  add     eax, edi
0x140060678  add     eax, eax
0x14006067a  sub     ecx, eax
0x14006067c  lea     eax, [r10+r10]
0x140060680  add     ecx, esi
0x140060682  add     ecx, [r12+24h]
0x140060687  add     ecx, r9d
0x14006068a  mov     edx, ecx
0x14006068c  neg     edx
0x14006068e  cmovs   edx, ecx
0x140060691  sub     r11d, eax
0x140060694  add     r11d, r14d
0x140060697  add     r11d, r11d
0x14006069a  sub     r11d, [rbp+28h]
0x14006069e  add     r11d, r8d
0x1400606a1  add     r11d, esi
0x1400606a4  add     r11d, [r12+24h]
0x1400606a9  add     r11d, r9d
0x1400606ac  mov     eax, r11d
0x1400606af  neg     eax
0x1400606b1  cmovs   eax, r11d
0x1400606b5  cmp     eax, edx
0x1400606b7  cmovl   edi, r10d
0x1400606bb  mov     r10d, r13d
0x1400606be  or      r15d, r10d
0x1400606c1  mov     [rbx+28h], edi
0x1400606c4  sub     edi, esi
0x1400606c6  mov     [rbx+48h], r15d
0x1400606ca  xor     eax, eax
0x1400606cc  mov     [rbx+24h], edi
0x1400606cf  mov     [rbx+4Ch], ax
0x1400606d3  mov     rax, [rbx+40h]
0x1400606d7  lea     rdx, [rbx+24h]
0x1400606db  mov     rbx, [rax+18h]
0x1400606df  mov     r8d, [rbx+48h]
0x1400606e3  test    r10b, r8b
0x1400606e6  jnz     short loc_14006070E
0x1400606e8  mov     edx, [rdx]
0x1400606ea  or      r8d, r10d
0x1400606ed  sub     edx, [rax+28h]
0x1400606f0  mov     ecx, [rbx+28h]
0x1400606f3  sub     ecx, [rbx+24h]
0x1400606f6  mov     [rbx+28h], edx
0x1400606f9  sub     edx, ecx
0x1400606fb  xor     ecx, ecx
0x1400606fd  mov     [rbx+24h], edx
0x140060700  mov     [rbx+48h], r8d
0x140060704  mov     [rbx+4Ch], cx
0x140060708  cmp     [rbx+40h], rcx
0x14006070c  jnz     short loc_1400606D3
0x14006070e  mov     eax, 1
0x140060713  jmp     short loc_140060717
0x140060715  xor     eax, eax
0x140060717  add     rsp, 28h
0x14006071b  pop     r15
0x14006071d  pop     r14
0x14006071f  pop     r13
0x140060721  pop     r12
0x140060723  pop     rdi
0x140060724  pop     rsi
0x140060725  pop     rbp
0x140060726  pop     rbx
0x140060727  retn
```
