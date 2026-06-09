# Lz_NextToken

- ea: `0x180016288`
- end: `0x1800169bc`
- name: `Lz_NextToken`
- size: `1844`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180015c9c`

## callees

- `0x180015e74`
- `0x180015ecc`
- `0x180015fb0`
- `0x180016288`
- `0x1800169c4`
- `0x180016ad8`

## pseudocode

```c
__int64 __fastcall Lz_NextToken(__int64 a1)
{
  int v1; // edx
  _DWORD *v2; // r14
  int v3; // r8d
  unsigned int v5; // esi
  unsigned int v6; // ecx
  __int64 v7; // rax
  int v8; // edi
  _DWORD *v9; // rcx
  __int64 result; // rax
  int v11; // edi
  int v12; // edi
  int v13; // edi
  int v14; // edi
  int v15; // edi
  int v16; // edi
  unsigned int v17; // ecx
  __int64 v18; // rax
  __int64 v19; // r14
  _DWORD *v20; // rcx
  int v21; // eax
  __int16 v22; // ax
  int v23; // edx
  int v24; // edi
  int v25; // r8d
  int v26; // ecx
  unsigned int v27; // ecx
  __int64 v28; // rax
  __int64 v29; // r15
  _DWORD *v30; // rcx
  int v31; // eax
  int v32; // eax
  int v33; // ecx
  int v34; // edx
  int v35; // r8d
  int v36; // ecx
  int v37; // edi
  unsigned int v38; // ecx
  __int64 v39; // rax
  __int64 v40; // r14
  _DWORD *v41; // rcx
  int v42; // eax
  __int64 v43; // rcx
  int v44; // edx
  int v45; // r8d
  int v46; // ecx
  int v47; // edi
  unsigned int v48; // ecx
  __int64 v49; // rax
  _DWORD *v50; // rcx
  int v51; // eax
  int v52; // edi
  unsigned int v53; // ecx
  __int64 v54; // rax
  int v55; // r14d
  _DWORD *v56; // rcx
  int v57; // eax
  __int64 v58; // rdx
  int v59; // edi
  unsigned int v60; // ecx
  __int64 v61; // rax
  int v62; // r14d
  _DWORD *v63; // rcx
  int v64; // eax
  int v65; // edi
  unsigned int v66; // ecx
  __int64 v67; // rax
  int v68; // r14d
  _DWORD *v69; // rcx
  int v70; // eax
  int v71; // edi
  unsigned int v72; // ecx
  __int64 v73; // rax
  unsigned int v74; // r14d
  _DWORD *v75; // rcx
  int v76; // eax
  __int16 v77; // [rsp+50h] [rbp+30h] BYREF
  __int16 v78; // [rsp+52h] [rbp+32h]
  __int16 v79; // [rsp+54h] [rbp+34h]
  __int64 v80; // [rsp+58h] [rbp+38h]

  v1 = *(unsigned __int16 *)(a1 + 332);
  v2 = (_DWORD *)(a1 + 416);
  v3 = *(unsigned __int16 *)(a1 + 416);
  WORD2(v80) = 0;
  LODWORD(v80) = 0;
  v5 = 0;
  v6 = (__int16)((v3 * ((unsigned int)*(unsigned __int16 *)(a1 + 336) - v1 + 1) - 1)
               / ((unsigned int)*(unsigned __int16 *)(a1 + 334) - v1 + 1));
  if ( *(_DWORD *)(a1 + 424) > v6 )
  {
    do
      v7 = (int)v5++;
    while ( *(_DWORD *)(a1 + 8 * v7 + 432) > v6 );
  }
  v79 = v3;
  v8 = *(_DWORD *)(a1 + 8LL * (int)v5 + 420);
  v77 = *(_WORD *)(a1 + 8LL * (int)v5 + 424);
  v78 = *(_WORD *)(a1 + 8LL * (int)v5 + 416);
  Arith_Remove_Symbol(a1, &v77);
  v9 = v2;
  do
  {
    *v9 += 8;
    result = v5--;
    v9 += 2;
  }
  while ( (_DWORD)result );
  if ( *v2 > 0xED8u )
    result = Lz_Bump(a1 + 408);
  if ( v8 )
  {
    v11 = v8 - 1;
    if ( v11 )
    {
      v12 = v11 - 1;
      if ( v12 )
      {
        v13 = v12 - 1;
        if ( v13 )
        {
          v14 = v13 - 1;
          if ( v14 )
          {
            v15 = v14 - 1;
            if ( v15 )
            {
              if ( v15 != 1 )
                return result;
              v16 = 0;
              v17 = (__int16)((*(unsigned __int16 *)(a1 + 3056)
                             * (*(unsigned __int16 *)(a1 + 336) - (unsigned int)*(unsigned __int16 *)(a1 + 332) + 1)
                             - 1)
                            / (*(unsigned __int16 *)(a1 + 334) - (unsigned int)*(unsigned __int16 *)(a1 + 332) + 1));
              if ( *(_DWORD *)(a1 + 3064) > v17 )
              {
                do
                  v18 = v16++;
                while ( *(_DWORD *)(a1 + 8 * v18 + 3072) > v17 );
              }
              v79 = *(_WORD *)(a1 + 3056);
              v19 = *(int *)(a1 + 8LL * v16 + 3060);
              v77 = *(_WORD *)(a1 + 8LL * v16 + 3064);
              v78 = *(_WORD *)(a1 + 8LL * v16 + 3056);
              Arith_Remove_Symbol(a1, &v77);
              v20 = (_DWORD *)(a1 + 3056);
              do
              {
                *v20 += 8;
                v21 = v16--;
                v20 += 2;
              }
              while ( v21 );
              if ( *(_DWORD *)(a1 + 3056) > 0xED8u )
                Lz_Bump(a1 + 3048);
              v22 = Arith_Decode_Bits(a1, (unsigned int)MatchCodeExtra[v19]);
              v23 = *(unsigned __int16 *)(a1 + 332);
              v24 = 0;
              v25 = *(unsigned __int16 *)(a1 + 3584);
              v26 = *(unsigned __int16 *)(a1 + 334) - v23;
              LOWORD(v80) = *(_WORD *)(a1 + 4 * v19 + 56) + v22 + 5;
              v27 = (__int16)((v25 * ((unsigned int)*(unsigned __int16 *)(a1 + 336) - v23 + 1) - 1) / (v26 + 1));
              if ( *(_DWORD *)(a1 + 3592) > v27 )
              {
                do
                  v28 = v24++;
                while ( *(_DWORD *)(a1 + 8 * v28 + 3600) > v27 );
              }
              v79 = v25;
              v29 = *(int *)(a1 + 8LL * v24 + 3588);
              v77 = *(_WORD *)(a1 + 8LL * v24 + 3592);
              v78 = *(_WORD *)(a1 + 8LL * v24 + 3584);
              Arith_Remove_Symbol(a1, &v77);
              v30 = (_DWORD *)(a1 + 3584);
              do
              {
                *v30 += 8;
                v31 = v24--;
                v30 += 2;
              }
              while ( v31 );
              if ( *(_DWORD *)(a1 + 3584) > 0xED8u )
                Lz_Bump(a1 + 3576);
              v32 = Arith_Decode_Bits(a1, (unsigned int)WindowCodeExtra[v29]);
              v33 = *(_DWORD *)(a1 + 4 * v29 + 164);
              goto LABEL_41;
            }
            v34 = *(unsigned __int16 *)(a1 + 332);
            v35 = *(unsigned __int16 *)(a1 + 4640);
            v36 = *(unsigned __int16 *)(a1 + 334);
            v37 = 0;
            LOWORD(v80) = 4;
            v38 = (__int16)((v35 * ((unsigned int)*(unsigned __int16 *)(a1 + 336) - v34 + 1) - 1) / (v36 - v34 + 1));
            if ( *(_DWORD *)(a1 + 4648) > v38 )
            {
              do
                v39 = v37++;
              while ( *(_DWORD *)(a1 + 8 * v39 + 4656) > v38 );
            }
            v79 = v35;
            v40 = *(int *)(a1 + 8LL * v37 + 4644);
            v77 = *(_WORD *)(a1 + 8LL * v37 + 4648);
            v78 = *(_WORD *)(a1 + 8LL * v37 + 4640);
            Arith_Remove_Symbol(a1, &v77);
            v41 = (_DWORD *)(a1 + 4640);
            do
            {
              *v41 += 8;
              v42 = v37--;
              v41 += 2;
            }
            while ( v42 );
            if ( *(_DWORD *)(a1 + 4640) <= 0xED8u )
            {
LABEL_40:
              v32 = Arith_Decode_Bits(a1, (unsigned int)WindowCodeExtra[v40]);
              v33 = *(_DWORD *)(a1 + 4 * v40 + 164);
LABEL_41:
              HIDWORD(v80) = v33 + 1 + v32;
              return DComp_Token_Match(a1, v80);
            }
            v43 = a1 + 4632;
          }
          else
          {
            v44 = *(unsigned __int16 *)(a1 + 332);
            v45 = *(unsigned __int16 *)(a1 + 4112);
            v46 = *(unsigned __int16 *)(a1 + 334);
            v47 = 0;
            LOWORD(v80) = 3;
            v48 = (__int16)((v45 * ((unsigned int)*(unsigned __int16 *)(a1 + 336) - v44 + 1) - 1) / (v46 - v44 + 1));
            if ( *(_DWORD *)(a1 + 4120) > v48 )
            {
              do
                v49 = v47++;
              while ( *(_DWORD *)(a1 + 8 * v49 + 4128) > v48 );
            }
            v79 = v45;
            v40 = *(int *)(a1 + 8LL * v47 + 4116);
            v77 = *(_WORD *)(a1 + 8LL * v47 + 4120);
            v78 = *(_WORD *)(a1 + 8LL * v47 + 4112);
            Arith_Remove_Symbol(a1, &v77);
            v50 = (_DWORD *)(a1 + 4112);
            do
            {
              *v50 += 8;
              v51 = v47--;
              v50 += 2;
            }
            while ( v51 );
            if ( *(_DWORD *)(a1 + 4112) <= 0xED8u )
              goto LABEL_40;
            v43 = a1 + 4104;
          }
          Lz_Bump(v43);
          goto LABEL_40;
        }
        v52 = 0;
        v53 = (__int16)((*(unsigned __int16 *)(a1 + 2528)
                       * (*(unsigned __int16 *)(a1 + 336) - (unsigned int)*(unsigned __int16 *)(a1 + 332) + 1)
                       - 1)
                      / (*(unsigned __int16 *)(a1 + 334) - (unsigned int)*(unsigned __int16 *)(a1 + 332) + 1));
        if ( *(_DWORD *)(a1 + 2536) > v53 )
        {
          do
            v54 = v52++;
          while ( *(_DWORD *)(a1 + 8 * v54 + 2544) > v53 );
        }
        v79 = *(_WORD *)(a1 + 2528);
        v55 = *(_DWORD *)(a1 + 8LL * v52 + 2532);
        v77 = *(_WORD *)(a1 + 8LL * v52 + 2536);
        v78 = *(_WORD *)(a1 + 8LL * v52 + 2528);
        Arith_Remove_Symbol(a1, &v77);
        v56 = (_DWORD *)(a1 + 2528);
        do
        {
          *v56 += 8;
          v57 = v52--;
          v56 += 2;
        }
        while ( v57 );
        if ( *(_DWORD *)(a1 + 2528) > 0xED8u )
          Lz_Bump(a1 + 2520);
        v58 = (unsigned int)(v55 + 192);
      }
      else
      {
        v59 = 0;
        v60 = (__int16)((*(unsigned __int16 *)(a1 + 2000)
                       * (*(unsigned __int16 *)(a1 + 336) - (unsigned int)*(unsigned __int16 *)(a1 + 332) + 1)
                       - 1)
                      / (*(unsigned __int16 *)(a1 + 334) - (unsigned int)*(unsigned __int16 *)(a1 + 332) + 1));
        if ( *(_DWORD *)(a1 + 2008) > v60 )
        {
          do
            v61 = v59++;
          while ( *(_DWORD *)(a1 + 8 * v61 + 2016) > v60 );
        }
        v79 = *(_WORD *)(a1 + 2000);
        v62 = *(_DWORD *)(a1 + 8LL * v59 + 2004);
        v77 = *(_WORD *)(a1 + 8LL * v59 + 2008);
        v78 = *(_WORD *)(a1 + 8LL * v59 + 2000);
        Arith_Remove_Symbol(a1, &v77);
        v63 = (_DWORD *)(a1 + 2000);
        do
        {
          *v63 += 8;
          v64 = v59--;
          v63 += 2;
        }
        while ( v64 );
        if ( *(_DWORD *)(a1 + 2000) > 0xED8u )
          Lz_Bump(a1 + 1992);
        v58 = (unsigned int)(v62 + 128);
      }
    }
    else
    {
      v65 = 0;
      v66 = (__int16)((*(unsigned __int16 *)(a1 + 1472)
                     * (*(unsigned __int16 *)(a1 + 336) - (unsigned int)*(unsigned __int16 *)(a1 + 332) + 1)
                     - 1)
                    / (*(unsigned __int16 *)(a1 + 334) - (unsigned int)*(unsigned __int16 *)(a1 + 332) + 1));
      if ( *(_DWORD *)(a1 + 1480) > v66 )
      {
        do
          v67 = v65++;
        while ( *(_DWORD *)(a1 + 8 * v67 + 1488) > v66 );
      }
      v79 = *(_WORD *)(a1 + 1472);
      v68 = *(_DWORD *)(a1 + 8LL * v65 + 1476);
      v77 = *(_WORD *)(a1 + 8LL * v65 + 1480);
      v78 = *(_WORD *)(a1 + 8LL * v65 + 1472);
      Arith_Remove_Symbol(a1, &v77);
      v69 = (_DWORD *)(a1 + 1472);
      do
      {
        *v69 += 8;
        v70 = v65--;
        v69 += 2;
      }
      while ( v70 );
      if ( *(_DWORD *)(a1 + 1472) > 0xED8u )
        Lz_Bump(a1 + 1464);
      v58 = (unsigned int)(v68 + 64);
    }
  }
  else
  {
    v71 = 0;
    v72 = (__int16)((*(unsigned __int16 *)(a1 + 944)
                   * (*(unsigned __int16 *)(a1 + 336) - (unsigned int)*(unsigned __int16 *)(a1 + 332) + 1)
                   - 1)
                  / (*(unsigned __int16 *)(a1 + 334) - (unsigned int)*(unsigned __int16 *)(a1 + 332) + 1));
    if ( *(_DWORD *)(a1 + 952) > v72 )
    {
      do
        v73 = v71++;
      while ( *(_DWORD *)(a1 + 8 * v73 + 960) > v72 );
    }
    v79 = *(_WORD *)(a1 + 944);
    v74 = *(_DWORD *)(a1 + 8LL * v71 + 948);
    v77 = *(_WORD *)(a1 + 8LL * v71 + 952);
    v78 = *(_WORD *)(a1 + 8LL * v71 + 944);
    Arith_Remove_Symbol(a1, &v77);
    v75 = (_DWORD *)(a1 + 944);
    do
    {
      *v75 += 8;
      v76 = v71--;
      v75 += 2;
    }
    while ( v76 );
    if ( *(_DWORD *)(a1 + 944) > 0xED8u )
      Lz_Bump(a1 + 936);
    v58 = v74;
  }
  return DComp_Token_Literal(a1, v58);
}

```

## disassembly

```asm
0x180016288  mov     [rsp-28h+arg_10], rbx
0x18001628d  mov     [rsp-28h+arg_18], rsi
0x180016292  push    rbp
0x180016293  push    rdi
0x180016294  push    r12
0x180016296  push    r14
0x180016298  push    r15
0x18001629a  mov     rbp, rsp
0x18001629d  sub     rsp, 20h
0x1800162a1  movzx   edx, word ptr [rcx+14Ch]
0x1800162a8  lea     r14, [rcx+1A0h]
0x1800162af  movzx   r8d, word ptr [r14]
0x1800162b3  xor     eax, eax
0x1800162b5  mov     dword ptr [rbp+arg_8+2], eax
0x1800162b8  mov     rbx, rcx
0x1800162bb  mov     [rbp+38h], eax
0x1800162be  mov     r12d, 1
0x1800162c4  movzx   eax, word ptr [rcx+150h]
0x1800162cb  xor     esi, esi
0x1800162cd  movzx   ecx, word ptr [rcx+14Eh]
0x1800162d4  sub     eax, edx
0x1800162d6  sub     ecx, edx
0x1800162d8  add     eax, r12d
0x1800162db  imul    eax, r8d
0x1800162df  add     ecx, r12d
0x1800162e2  xor     edx, edx
0x1800162e4  sub     eax, r12d
0x1800162e7  div     ecx
0x1800162e9  movsx   ecx, ax
0x1800162ec  cmp     [rbx+1A8h], ecx
0x1800162f2  jbe     short loc_180016303
0x1800162f4  movsxd  rax, esi
0x1800162f7  add     esi, r12d
0x1800162fa  cmp     [rbx+rax*8+1B0h], ecx
0x180016301  ja      short loc_1800162F4
0x180016303  movsxd  rcx, esi
0x180016306  lea     rdx, [rbp+arg_0]
0x18001630a  mov     [rbp+arg_4], r8w
0x18001630f  movzx   eax, word ptr [rbx+rcx*8+1A8h]
0x180016317  mov     edi, [rbx+rcx*8+1A4h]
0x18001631e  mov     [rbp+arg_0], ax
0x180016322  movzx   eax, word ptr [rbx+rcx*8+1A0h]
0x18001632a  mov     rcx, rbx
0x18001632d  mov     [rbp+arg_2], ax
0x180016331  call    Arith_Remove_Symbol
0x180016336  mov     rcx, r14
0x180016339  add     dword ptr [rcx], 8
0x18001633c  mov     eax, esi
0x18001633e  sub     esi, r12d
0x180016341  lea     rcx, [rcx+8]
0x180016345  test    eax, eax
0x180016347  jnz     short loc_180016339
0x180016349  mov     r15d, 0ED8h
0x18001634f  cmp     [r14], r15d
0x180016352  jbe     short loc_180016360
0x180016354  lea     rcx, [rbx+198h]
0x18001635b  call    Lz_Bump
0x180016360  test    edi, edi
0x180016362  jz      loc_1800168F1
0x180016368  sub     edi, r12d
0x18001636b  jz      loc_18001683F
0x180016371  sub     edi, r12d
0x180016374  jz      loc_18001678A
0x18001637a  sub     edi, r12d
0x18001637d  jz      loc_1800166D5
0x180016383  sub     edi, r12d
0x180016386  jz      loc_1800165EC
0x18001638c  sub     edi, r12d
0x18001638f  jz      loc_180016536
0x180016395  cmp     edi, r12d
0x180016398  jnz     loc_1800169A5
0x18001639e  movzx   edx, word ptr [rbx+14Ch]
0x1800163a5  lea     rsi, [rbx+0BF0h]
0x1800163ac  movzx   eax, word ptr [rbx+150h]
0x1800163b3  xor     edi, edi
0x1800163b5  movzx   r8d, word ptr [rsi]
0x1800163b9  sub     eax, edx
0x1800163bb  movzx   ecx, word ptr [rbx+14Eh]
0x1800163c2  add     eax, r12d
0x1800163c5  sub     ecx, edx
0x1800163c7  imul    eax, r8d
0x1800163cb  add     ecx, r12d
0x1800163ce  xor     edx, edx
0x1800163d0  sub     eax, r12d
0x1800163d3  div     ecx
0x1800163d5  movsx   ecx, ax
0x1800163d8  cmp     [rbx+0BF8h], ecx
0x1800163de  jbe     short loc_1800163EF
0x1800163e0  movsxd  rax, edi
0x1800163e3  add     edi, r12d
0x1800163e6  cmp     [rbx+rax*8+0C00h], ecx
0x1800163ed  ja      short loc_1800163E0
0x1800163ef  movsxd  rcx, edi
0x1800163f2  lea     rdx, [rbp+arg_0]
0x1800163f6  mov     [rbp+arg_4], r8w
0x1800163fb  movzx   eax, word ptr [rbx+rcx*8+0BF8h]
0x180016403  movsxd  r14, dword ptr [rbx+rcx*8+0BF4h]
0x18001640b  mov     [rbp+arg_0], ax
0x18001640f  movzx   eax, word ptr [rbx+rcx*8+0BF0h]
0x180016417  mov     rcx, rbx
0x18001641a  mov     [rbp+arg_2], ax
0x18001641e  call    Arith_Remove_Symbol
0x180016423  mov     rcx, rsi
0x180016426  add     dword ptr [rcx], 8
0x180016429  mov     eax, edi
0x18001642b  sub     edi, r12d
0x18001642e  lea     rcx, [rcx+8]
0x180016432  test    eax, eax
0x180016434  jnz     short loc_180016426
0x180016436  cmp     [rsi], r15d
0x180016439  jbe     short loc_180016447
0x18001643b  lea     rcx, [rbx+0BE8h]
0x180016442  call    Lz_Bump
0x180016447  lea     rsi, __ImageBase
0x18001644e  mov     rcx, rbx
0x180016451  mov     edx, ds:rva MatchCodeExtra[rsi+r14*4]
0x180016459  call    Arith_Decode_Bits
0x18001645e  movzx   edx, word ptr [rbx+14Ch]
0x180016465  add     ax, 5
0x180016469  add     ax, [rbx+r14*4+38h]
0x18001646f  xor     edi, edi
0x180016471  movzx   ecx, word ptr [rbx+14Eh]
0x180016478  lea     r14, [rbx+0E00h]
0x18001647f  movzx   r8d, word ptr [r14]
0x180016483  sub     ecx, edx
0x180016485  mov     word ptr [rbp+arg_8], ax
0x180016489  add     ecx, r12d
0x18001648c  movzx   eax, word ptr [rbx+150h]
0x180016493  sub     eax, edx
0x180016495  xor     edx, edx
0x180016497  add     eax, r12d
0x18001649a  imul    eax, r8d
0x18001649e  sub     eax, r12d
0x1800164a1  div     ecx
0x1800164a3  movsx   ecx, ax
0x1800164a6  cmp     [rbx+0E08h], ecx
0x1800164ac  jbe     short loc_1800164BD
0x1800164ae  movsxd  rax, edi
0x1800164b1  add     edi, r12d
0x1800164b4  cmp     [rbx+rax*8+0E10h], ecx
0x1800164bb  ja      short loc_1800164AE
0x1800164bd  movsxd  rcx, edi
0x1800164c0  lea     rdx, [rbp+arg_0]
0x1800164c4  mov     [rbp+arg_4], r8w
0x1800164c9  movzx   eax, word ptr [rbx+rcx*8+0E08h]
0x1800164d1  movsxd  r15, dword ptr [rbx+rcx*8+0E04h]
0x1800164d9  mov     [rbp+arg_0], ax
0x1800164dd  movzx   eax, word ptr [rbx+rcx*8+0E00h]
0x1800164e5  mov     rcx, rbx
0x1800164e8  mov     [rbp+arg_2], ax
0x1800164ec  call    Arith_Remove_Symbol
0x1800164f1  mov     rcx, r14
0x1800164f4  add     dword ptr [rcx], 8
0x1800164f7  mov     eax, edi
0x1800164f9  sub     edi, r12d
0x1800164fc  lea     rcx, [rcx+8]
0x180016500  test    eax, eax
0x180016502  jnz     short loc_1800164F4
0x180016504  cmp     dword ptr [r14], 0ED8h
0x18001650b  jbe     short loc_180016519
0x18001650d  lea     rcx, [rbx+0DF8h]
0x180016514  call    Lz_Bump
0x180016519  mov     edx, ds:rva WindowCodeExtra[rsi+r15*4]
0x180016521  mov     rcx, rbx
0x180016524  call    Arith_Decode_Bits
0x180016529  mov     ecx, [rbx+r15*4+0A4h]
0x180016531  jmp     loc_1800166BD
0x180016536  movzx   edx, word ptr [rbx+14Ch]
0x18001653d  lea     rsi, [rbx+1220h]
0x180016544  movzx   r8d, word ptr [rsi]
0x180016548  mov     eax, 4
0x18001654d  movzx   ecx, word ptr [rbx+14Eh]
0x180016554  xor     edi, edi
0x180016556  mov     word ptr [rbp+arg_8], ax
0x18001655a  sub     ecx, edx
0x18001655c  movzx   eax, word ptr [rbx+150h]
0x180016563  add     ecx, r12d
0x180016566  sub     eax, edx
0x180016568  xor     edx, edx
0x18001656a  add     eax, r12d
0x18001656d  imul    eax, r8d
0x180016571  sub     eax, r12d
0x180016574  div     ecx
0x180016576  movsx   ecx, ax
0x180016579  cmp     [rbx+1228h], ecx
0x18001657f  jbe     short loc_180016590
0x180016581  movsxd  rax, edi
0x180016584  add     edi, r12d
0x180016587  cmp     [rbx+rax*8+1230h], ecx
0x18001658e  ja      short loc_180016581
0x180016590  movsxd  rcx, edi
0x180016593  lea     rdx, [rbp+arg_0]
0x180016597  mov     [rbp+arg_4], r8w
0x18001659c  movzx   eax, word ptr [rbx+rcx*8+1228h]
0x1800165a4  movsxd  r14, dword ptr [rbx+rcx*8+1224h]
0x1800165ac  mov     [rbp+arg_0], ax
0x1800165b0  movzx   eax, word ptr [rbx+rcx*8+1220h]
0x1800165b8  mov     rcx, rbx
0x1800165bb  mov     [rbp+arg_2], ax
0x1800165bf  call    Arith_Remove_Symbol
0x1800165c4  mov     rcx, rsi
0x1800165c7  add     dword ptr [rcx], 8
0x1800165ca  mov     eax, edi
0x1800165cc  sub     edi, r12d
0x1800165cf  lea     rcx, [rcx+8]
0x1800165d3  test    eax, eax
0x1800165d5  jnz     short loc_1800165C7
0x1800165d7  cmp     [rsi], r15d
0x1800165da  jbe     loc_18001669E
0x1800165e0  lea     rcx, [rbx+1218h]
0x1800165e7  jmp     loc_180016699
0x1800165ec  movzx   edx, word ptr [rbx+14Ch]
0x1800165f3  lea     rsi, [rbx+1010h]
0x1800165fa  movzx   r8d, word ptr [rsi]
0x1800165fe  mov     eax, 3
0x180016603  movzx   ecx, word ptr [rbx+14Eh]
0x18001660a  xor     edi, edi
0x18001660c  mov     word ptr [rbp+arg_8], ax
0x180016610  sub     ecx, edx
0x180016612  movzx   eax, word ptr [rbx+150h]
0x180016619  add     ecx, r12d
0x18001661c  sub     eax, edx
0x18001661e  xor     edx, edx
0x180016620  add     eax, r12d
0x180016623  imul    eax, r8d
0x180016627  sub     eax, r12d
0x18001662a  div     ecx
0x18001662c  movsx   ecx, ax
0x18001662f  cmp     [rbx+1018h], ecx
0x180016635  jbe     short loc_180016646
0x180016637  movsxd  rax, edi
0x18001663a  add     edi, r12d
0x18001663d  cmp     [rbx+rax*8+1020h], ecx
0x180016644  ja      short loc_180016637
0x180016646  movsxd  rcx, edi
0x180016649  lea     rdx, [rbp+arg_0]
0x18001664d  mov     [rbp+arg_4], r8w
0x180016652  movzx   eax, word ptr [rbx+rcx*8+1018h]
0x18001665a  movsxd  r14, dword ptr [rbx+rcx*8+1014h]
0x180016662  mov     [rbp+arg_0], ax
0x180016666  movzx   eax, word ptr [rbx+rcx*8+1010h]
0x18001666e  mov     rcx, rbx
0x180016671  mov     [rbp+arg_2], ax
0x180016675  call    Arith_Remove_Symbol
0x18001667a  mov     rcx, rsi
0x18001667d  add     dword ptr [rcx], 8
0x180016680  mov     eax, edi
0x180016682  sub     edi, r12d
0x180016685  lea     rcx, [rcx+8]
0x180016689  test    eax, eax
0x18001668b  jnz     short loc_18001667D
0x18001668d  cmp     [rsi], r15d
0x180016690  jbe     short loc_18001669E
0x180016692  lea     rcx, [rbx+1008h]
0x180016699  call    Lz_Bump
0x18001669e  lea     rsi, __ImageBase
0x1800166a5  mov     rcx, rbx
0x1800166a8  mov     edx, ds:rva WindowCodeExtra[rsi+r14*4]
0x1800166b0  call    Arith_Decode_Bits
0x1800166b5  mov     ecx, [rbx+r14*4+0A4h]
0x1800166bd  inc     ecx
0x1800166bf  add     eax, ecx
0x1800166c1  mov     rcx, rbx
0x1800166c4  mov     dword ptr [rbp+arg_8+4], eax
0x1800166c7  mov     rdx, [rbp+arg_8]
0x1800166cb  call    DComp_Token_Match
0x1800166d0  jmp     loc_1800169A5
0x1800166d5  movzx   edx, word ptr [rbx+14Ch]
0x1800166dc  lea     rsi, [rbx+9E0h]
0x1800166e3  movzx   eax, word ptr [rbx+150h]
0x1800166ea  xor     edi, edi
0x1800166ec  movzx   r8d, word ptr [rsi]
0x1800166f0  sub     eax, edx
0x1800166f2  movzx   ecx, word ptr [rbx+14Eh]
0x1800166f9  add     eax, r12d
0x1800166fc  sub     ecx, edx
0x1800166fe  imul    eax, r8d
0x180016702  add     ecx, r12d
0x180016705  xor     edx, edx
0x180016707  sub     eax, r12d
0x18001670a  div     ecx
0x18001670c  movsx   ecx, ax
0x18001670f  cmp     [rbx+9E8h], ecx
0x180016715  jbe     short loc_180016726
0x180016717  movsxd  rax, edi
0x18001671a  add     edi, r12d
0x18001671d  cmp     [rbx+rax*8+9F0h], ecx
0x180016724  ja      short loc_180016717
0x180016726  movsxd  rcx, edi
0x180016729  lea     rdx, [rbp+arg_0]
0x18001672d  mov     [rbp+arg_4], r8w
0x180016732  movzx   eax, word ptr [rbx+rcx*8+9E8h]
0x18001673a  mov     r14d, [rbx+rcx*8+9E4h]
0x180016742  mov     [rbp+arg_0], ax
0x180016746  movzx   eax, word ptr [rbx+rcx*8+9E0h]
0x18001674e  mov     rcx, rbx
0x180016751  mov     [rbp+arg_2], ax
0x180016755  call    Arith_Remove_Symbol
0x18001675a  mov     rcx, rsi
0x18001675d  add     dword ptr [rcx], 8
  ... truncated ...
```
