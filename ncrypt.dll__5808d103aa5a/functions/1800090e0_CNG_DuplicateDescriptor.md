# CNG_DuplicateDescriptor

- ea: `0x1800090e0`
- end: `0x180009624`
- name: `CNG_DuplicateDescriptor`
- size: `1348`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180005a18`
- `0x18000962c`
- `0x180009ecc`
- `0x18001d7b8`

## callees

- `0x180008cfc`
- `0x1800090e0`
- `0x180009cd0`
- `0x18000d02c`
- `0x18000e120`
- `0x18001cf90`
- `0x18001f175`

## string_xrefs

- `0x1800093db`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\descriptor.c`
- `0x180009452`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\descriptor.c`
- `0x18000960a`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\descriptor.c`

## pseudocode

```c
__int64 __fastcall CNG_DuplicateDescriptor(unsigned int *a1, _QWORD *a2, int a3)
{
  __int64 v3; // rdi
  unsigned int *v4; // r15
  unsigned __int64 v5; // r14
  __int64 v6; // r9
  __int64 v7; // r13
  unsigned __int64 v8; // rsi
  __int64 v9; // r12
  __int64 v10; // rcx
  __int64 v11; // r15
  unsigned __int64 v12; // rdx
  unsigned __int64 v13; // r10
  __int64 v14; // rbx
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rax
  __int64 v19; // rdi
  size_t v20; // rbx
  _QWORD *v21; // rax
  int v22; // edx
  _QWORD *v23; // r13
  int v24; // eax
  char *v25; // rdx
  __int64 v26; // rsi
  _WORD *v27; // rdi
  unsigned __int64 i; // r12
  unsigned __int64 v29; // rax
  __int64 v30; // r14
  unsigned __int64 v31; // rbp
  __int64 v32; // r11
  __int64 v33; // rax
  _WORD *v34; // rdx
  __int64 v35; // r8
  _WORD *v36; // rdi
  _WORD *v37; // rdx
  unsigned __int64 v38; // r8
  __int64 v39; // rcx
  _WORD *v40; // r9
  __int64 v41; // r10
  _WORD *v42; // rcx
  int v43; // edx
  __int64 v44; // rax
  unsigned int v45; // ebx
  unsigned __int64 v46; // r8
  __int64 v47; // rcx
  _WORD *v48; // r9
  __int64 v49; // r10
  _WORD *v50; // rcx
  int v51; // edx
  __int64 v52; // rax
  __int64 v54; // rax
  __int64 v55; // rcx
  unsigned int v56; // eax
  __int64 v57; // rcx
  _QWORD *v58; // r11
  __int64 v59; // rax
  __int64 v60; // rax
  __int64 v61; // rcx
  __int64 v62; // rax
  unsigned int *v63; // [rsp+90h] [rbp+8h] BYREF
  _QWORD *v64; // [rsp+98h] [rbp+10h]
  int v65; // [rsp+A0h] [rbp+18h]
  char *v66; // [rsp+A8h] [rbp+20h]

  v65 = a3;
  v64 = a2;
  v63 = a1;
  v3 = 0;
  v4 = a1;
  *a2 = 0;
  v5 = *a1;
  v6 = 32 * v5 + 16;
  if ( *a1 )
  {
    v7 = *((_QWORD *)a1 + 1);
    v8 = 0;
    while ( 1 )
    {
      v9 = 0;
      v10 = 32 * v8;
      v11 = 0;
      v12 = 0;
      v13 = *(unsigned int *)(32 * v8 + v7);
      v3 += v13;
      if ( v13 >= 2 )
        break;
      if ( *(_DWORD *)(32 * v8 + v7) )
      {
        v14 = *(_QWORD *)(v10 + v7 + 8);
LABEL_6:
        v15 = 32 * v12;
        v16 = -1;
        do
          ++v16;
        while ( *(_WORD *)(*(_QWORD *)(v15 + v14) + 2 * v16) );
        v17 = *(_QWORD *)(v15 + v14 + 8);
        v18 = -1;
        do
          ++v18;
        while ( *(_WORD *)(v17 + 2 * v18) );
        v6 += 2 * (v16 + v18) + 4;
      }
LABEL_11:
      ++v8;
      v6 += v11 + v9;
      if ( v8 >= v5 )
      {
        v4 = v63;
        goto LABEL_13;
      }
    }
    v14 = *(_QWORD *)(v10 + v7 + 8);
    do
    {
      v57 = -1;
      v58 = (_QWORD *)(v14 + 32 * v12);
      do
        ++v57;
      while ( *(_WORD *)(*v58 + 2 * v57) );
      v59 = -1;
      do
        ++v59;
      while ( *(_WORD *)(v58[1] + 2 * v59) );
      v60 = v57 + v59;
      v61 = -1;
      v9 += 2 * v60 + 4;
      do
        ++v61;
      while ( *(_WORD *)(v58[4] + 2 * v61) );
      v62 = -1;
      do
        ++v62;
      while ( *(_WORD *)(v58[5] + 2 * v62) );
      v12 += 2LL;
      v11 += 2 * (v61 + v62) + 4;
    }
    while ( v12 < v13 - 1 );
    if ( v12 >= v13 )
      goto LABEL_11;
    goto LABEL_6;
  }
LABEL_13:
  v19 = 32 * v3;
  v20 = v19 + v6;
  v21 = (_QWORD *)SafeAllocaAllocateFromHeap(v19 + v6);
  v23 = v21;
  if ( v21 )
  {
    memset_0(v21, 0, v20);
    v24 = *v4;
    v25 = (char *)(v23 + 2);
    v23[1] = v23 + 2;
    *(_DWORD *)v23 = v24;
    v26 = (__int64)&v23[4 * *v4 + 2];
    v27 = (_WORD *)(v26 + v19);
    for ( i = 0; ; ++i )
    {
      v29 = *v4;
      v66 = v25;
      if ( i >= v29 )
        break;
      v30 = 32 * i;
      v31 = 0;
      *((_DWORD *)v25 + 4) = *(_DWORD *)(*((_QWORD *)v4 + 1) + 32 * i + 16);
      *((_QWORD *)v25 + 3) = *(_QWORD *)(*((_QWORD *)v4 + 1) + 32 * i + 24);
      *(_DWORD *)v25 = *(_DWORD *)(32 * i + *((_QWORD *)v4 + 1));
      *((_QWORD *)v25 + 1) = v26;
      while ( v31 < *(unsigned int *)(*((_QWORD *)v4 + 1) + 32 * i) )
      {
        *(_QWORD *)v26 = v27;
        v32 = 32 * v31;
        v33 = -1;
        v34 = *(_WORD **)(32 * v31 + *(_QWORD *)(*((_QWORD *)v4 + 1) + v30 + 8));
        do
          ++v33;
        while ( v34[v33] );
        if ( v33 )
        {
          v46 = v33 + 1;
          if ( v33 == -1 )
          {
            v51 = -2147024809;
          }
          else
          {
            if ( v46 > 0x7FFFFFFF )
            {
              v51 = -2147024809;
              v45 = -2147024809;
              *v27 = 0;
LABEL_50:
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                WPP_SF_sDsd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v51,
                  (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\descriptor.c",
                  (unsigned int)"Status",
                  v51,
                  (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\descriptor.c",
                  100);
LABEL_53:
              CNG_FreeProtectionDescriptor(v23);
              return v45;
            }
            v47 = 2147483646;
            v48 = v27;
            v49 = 0;
            do
            {
              if ( !v47 )
                break;
              if ( !*v34 )
                break;
              *v48++ = *v34++;
              --v47;
              ++v49;
              --v46;
            }
            while ( v46 );
            v50 = v48 - 1;
            v51 = -2147024774;
            if ( v46 )
            {
              v51 = 0;
              v50 = v48;
            }
            *v50 = 0;
            v52 = v49 - 1;
            if ( v46 )
              v52 = v49;
            v27 += v52;
          }
          v45 = v51;
          if ( v51 < 0 )
            goto LABEL_50;
        }
        v35 = -1;
        *v27 = 0;
        v36 = v27 + 1;
        *(_QWORD *)(v26 + 8) = v36;
        v37 = *(_WORD **)(*(_QWORD *)(*((_QWORD *)v4 + 1) + v30 + 8) + v32 + 8);
        do
          ++v35;
        while ( v37[v35] );
        if ( v35 )
        {
          v38 = v35 + 1;
          if ( v38 )
          {
            if ( v38 > 0x7FFFFFFF )
            {
              v43 = -2147024809;
              v45 = -2147024809;
              *v36 = 0;
LABEL_76:
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                WPP_SF_sDsd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v43,
                  (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\descriptor.c",
                  (unsigned int)"Status",
                  v43,
                  (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\descriptor.c",
                  120);
              goto LABEL_53;
            }
            v39 = 2147483646;
            v40 = v36;
            v41 = 0;
            do
            {
              if ( !v39 )
                break;
              if ( !*v37 )
                break;
              *v40++ = *v37++;
              --v39;
              ++v41;
              --v38;
            }
            while ( v38 );
            v42 = v40 - 1;
            v43 = -2147024774;
            if ( v38 )
            {
              v43 = 0;
              v42 = v40;
            }
            *v42 = 0;
            v44 = v41 - 1;
            if ( v38 )
              v44 = v41;
            v36 += v44;
          }
          else
          {
            v43 = -2147024809;
          }
          v45 = v43;
          if ( v43 < 0 )
            goto LABEL_76;
        }
        *v36 = 0;
        if ( (v65 & 1) != 0 )
        {
          v54 = *((_QWORD *)v4 + 1);
          v63 = 0;
          v55 = *(_QWORD *)(v54 + v30 + 8);
          if ( *(_QWORD *)(v55 + v32 + 16) )
          {
            if ( *(_DWORD *)(v55 + v32 + 24) == 1 )
            {
              v56 = NCryptDuplicateKeyProtectorHandle(*(_QWORD *)(v55 + v32 + 16), &v63, 0);
              v45 = v56;
              if ( v56 )
              {
                DebugTraceError(
                  v56,
                  "Status",
                  "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\descriptor.c",
                  396);
                goto LABEL_53;
              }
              *(_QWORD *)(v26 + 16) = v63;
              *(_DWORD *)(v26 + 24) = 1;
            }
          }
        }
        v27 = v36 + 1;
        v26 += 32;
        ++v31;
      }
      v25 = v66 + 32;
    }
    *v64 = v23;
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v22,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\descriptor.c",
        (unsigned int)"Status",
        14,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\descriptor.c",
        62);
    return 2148073486LL;
  }
}

```

## disassembly

```asm
0x1800090e0  mov     [rsp+arg_10], r8d
0x1800090e5  mov     [rsp+arg_8], rdx
0x1800090ea  mov     [rsp+arg_0], rcx
0x1800090ef  push    rbx
0x1800090f0  push    rbp
0x1800090f1  push    rsi
0x1800090f2  push    rdi
0x1800090f3  push    r12
0x1800090f5  push    r13
0x1800090f7  push    r14
0x1800090f9  push    r15
0x1800090fb  sub     rsp, 48h
0x1800090ff  xor     edi, edi
0x180009101  mov     r15, rcx
0x180009104  mov     [rdx], rdi
0x180009107  mov     r14d, [rcx]
0x18000910a  mov     r9d, r14d
0x18000910d  shl     r9, 5
0x180009111  add     r9, 10h
0x180009115  test    r14, r14
0x180009118  jz      loc_1800091A2
0x18000911e  mov     r13, [rcx+8]
0x180009122  xor     esi, esi
0x180009124  mov     rcx, rsi
0x180009127  xor     r12d, r12d
0x18000912a  shl     rcx, 5
0x18000912e  xor     r15d, r15d
0x180009131  xor     edx, edx
0x180009133  mov     r10d, [rcx+r13]
0x180009137  add     rdi, r10
0x18000913a  cmp     r10, 2
0x18000913e  jnb     loc_1800094E5
0x180009144  test    r10, r10
0x180009147  jz      short loc_18000918B
0x180009149  mov     rbx, [rcx+r13+8]
0x18000914e  shl     rdx, 5
0x180009152  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180009159  mov     rax, [rdx+rbx]
0x18000915d  nop     dword ptr [rax]
0x180009160  inc     rcx
0x180009163  cmp     word ptr [rax+rcx*2], 0
0x180009168  jnz     short loc_180009160
0x18000916a  mov     rdx, [rdx+rbx+8]
0x18000916f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180009176  inc     rax
0x180009179  cmp     word ptr [rdx+rax*2], 0
0x18000917e  jnz     short loc_180009176
0x180009180  add     rax, rcx
0x180009183  lea     r9, [r9+rax*2]
0x180009187  add     r9, 4
0x18000918b  lea     rax, [r15+r12]
0x18000918f  inc     rsi
0x180009192  add     r9, rax
0x180009195  cmp     rsi, r14
0x180009198  jb      short loc_180009124
0x18000919a  mov     r15, [rsp+88h+arg_0]
0x1800091a2  shl     rdi, 5
0x1800091a6  lea     rbx, [rdi+r9]
0x1800091aa  mov     rcx, rbx
0x1800091ad  call    SafeAllocaAllocateFromHeap
0x1800091b2  mov     r13, rax
0x1800091b5  test    rax, rax
0x1800091b8  jz      loc_180009435
0x1800091be  mov     r8, rbx; Size
0x1800091c1  xor     edx, edx; Val
0x1800091c3  mov     rcx, rax; void *
0x1800091c6  call    memset_0
0x1800091cb  mov     eax, [r15]
0x1800091ce  lea     rdx, [r13+10h]
0x1800091d2  mov     [r13+8], rdx
0x1800091d6  mov     [r13+0], eax
0x1800091da  mov     esi, [r15]
0x1800091dd  shl     rsi, 5
0x1800091e1  add     rsi, rdx
0x1800091e4  add     rdi, rsi
0x1800091e7  xor     r12d, r12d
0x1800091ea  mov     eax, [r15]
0x1800091ed  mov     [rsp+88h+arg_18], rdx
0x1800091f5  cmp     r12, rax
0x1800091f8  jnb     loc_180009417
0x1800091fe  mov     rax, [r15+8]
0x180009202  mov     r14, r12
0x180009205  shl     r14, 5
0x180009209  xor     ebp, ebp
0x18000920b  mov     ecx, [rax+r14+10h]
0x180009210  mov     [rdx+10h], ecx
0x180009213  mov     rax, [r15+8]
0x180009217  mov     rcx, [rax+r14+18h]
0x18000921c  mov     [rdx+18h], rcx
0x180009220  mov     rax, [r15+8]
0x180009224  mov     ecx, [r14+rax]
0x180009228  mov     [rdx], ecx
0x18000922a  mov     [rdx+8], rsi
0x18000922e  mov     rax, [r15+8]
0x180009232  mov     ecx, [rax+r14]
0x180009236  cmp     rbp, rcx
0x180009239  jnb     loc_180009403
0x18000923f  mov     [rsi], rdi
0x180009242  mov     r11, rbp
0x180009245  mov     rax, [r15+8]
0x180009249  shl     r11, 5
0x18000924d  mov     rcx, [rax+r14+8]
0x180009252  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180009259  mov     rdx, [r11+rcx]
0x18000925d  nop     dword ptr [rax]
0x180009260  inc     rax
0x180009263  cmp     word ptr [rdx+rax*2], 0
0x180009268  jnz     short loc_180009260
0x18000926a  test    rax, rax
0x18000926d  jnz     loc_18000933E
0x180009273  xor     eax, eax
0x180009275  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18000927c  mov     [rdi], ax
0x18000927f  add     rdi, 2
0x180009283  mov     [rsi+8], rdi
0x180009287  mov     rax, [r15+8]
0x18000928b  mov     rcx, [rax+r14+8]
0x180009290  mov     rdx, [rcx+r11+8]
0x180009295  inc     r8
0x180009298  cmp     word ptr [rdx+r8*2], 0
0x18000929e  jnz     short loc_180009295
0x1800092a0  test    r8, r8
0x1800092a3  jz      short loc_18000931A
0x1800092a5  add     r8, 1
0x1800092a9  jz      loc_1800095BF
0x1800092af  cmp     r8, 7FFFFFFFh
0x1800092b6  ja      loc_1800095F3
0x1800092bc  mov     ecx, 7FFFFFFEh
0x1800092c1  mov     r9, rdi
0x1800092c4  xor     r10d, r10d
0x1800092c7  test    rcx, rcx
0x1800092ca  jz      short loc_1800092EC
0x1800092cc  movzx   eax, word ptr [rdx]
0x1800092cf  test    ax, ax
0x1800092d2  jz      short loc_1800092EC
0x1800092d4  mov     [r9], ax
0x1800092d8  add     rdx, 2
0x1800092dc  add     r9, 2
0x1800092e0  dec     rcx
0x1800092e3  inc     r10
0x1800092e6  sub     r8, 1
0x1800092ea  jnz     short loc_1800092C7
0x1800092ec  xor     eax, eax
0x1800092ee  lea     rcx, [r9-2]
0x1800092f2  test    r8, r8
0x1800092f5  mov     edx, 8007007Ah
0x1800092fa  cmovnz  edx, eax
0x1800092fd  cmovnz  rcx, r9
0x180009301  mov     [rcx], ax
0x180009304  lea     rax, [r10-1]
0x180009308  cmovnz  rax, r10
0x18000930c  lea     rdi, [rdi+rax*2]
0x180009310  mov     ebx, edx
0x180009312  test    edx, edx
0x180009314  js      loc_180009591
0x18000931a  xor     eax, eax
0x18000931c  mov     [rdi], ax
0x18000931f  mov     eax, [rsp+88h+arg_10]
0x180009326  test    al, 1
0x180009328  jnz     loc_180009481
0x18000932e  add     rdi, 2
0x180009332  add     rsi, 20h ; ' '
0x180009336  inc     rbp
0x180009339  jmp     loc_18000922E
0x18000933e  lea     r8, [rax+1]
0x180009342  test    r8, r8
0x180009345  jz      loc_1800095CF
0x18000934b  cmp     r8, 7FFFFFFFh
0x180009352  ja      loc_1800095DF
0x180009358  mov     ecx, 7FFFFFFEh
0x18000935d  mov     r9, rdi
0x180009360  xor     r10d, r10d
0x180009363  test    rcx, rcx
0x180009366  jz      short loc_180009388
0x180009368  movzx   eax, word ptr [rdx]
0x18000936b  test    ax, ax
0x18000936e  jz      short loc_180009388
0x180009370  mov     [r9], ax
0x180009374  add     rdx, 2
0x180009378  add     r9, 2
0x18000937c  dec     rcx
0x18000937f  inc     r10
0x180009382  sub     r8, 1
0x180009386  jnz     short loc_180009363
0x180009388  xor     eax, eax
0x18000938a  lea     rcx, [r9-2]
0x18000938e  test    r8, r8
0x180009391  mov     edx, 8007007Ah
0x180009396  cmovnz  edx, eax
0x180009399  cmovnz  rcx, r9
0x18000939d  mov     [rcx], ax
0x1800093a0  lea     rax, [r10-1]
0x1800093a4  cmovnz  rax, r10
0x1800093a8  lea     rdi, [rdi+rax*2]
0x1800093ac  mov     ebx, edx
0x1800093ae  test    edx, edx
0x1800093b0  jns     loc_180009273
0x1800093b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800093bd  lea     rax, WPP_GLOBAL_Control
0x1800093c4  cmp     rcx, rax
0x1800093c7  jz      short loc_1800093F7
0x1800093c9  test    byte ptr [rcx+1Ch], 1
0x1800093cd  jz      short loc_1800093F7
0x1800093cf  mov     [rsp+88h+var_58], 164h
0x1800093d7  mov     rcx, [rcx+10h]
0x1800093db  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800093e2  mov     [rsp+88h+var_60], r8
0x1800093e7  lea     r9, aStatus; "Status"
0x1800093ee  mov     [rsp+88h+var_68], edx
0x1800093f2  call    WPP_SF_sDsd
0x1800093f7  mov     rcx, r13
0x1800093fa  call    CNG_FreeProtectionDescriptor
0x1800093ff  mov     eax, ebx
0x180009401  jmp     short loc_180009424
0x180009403  mov     rdx, [rsp+88h+arg_18]
0x18000940b  add     rdx, 20h ; ' '
0x18000940f  inc     r12
0x180009412  jmp     loc_1800091EA
0x180009417  mov     rax, [rsp+88h+arg_8]
0x18000941f  mov     [rax], r13
0x180009422  xor     eax, eax
0x180009424  add     rsp, 48h
0x180009428  pop     r15
0x18000942a  pop     r14
0x18000942c  pop     r13
0x18000942e  pop     r12
0x180009430  pop     rdi
0x180009431  pop     rsi
0x180009432  pop     rbp
0x180009433  pop     rbx
0x180009434  retn
0x180009435  mov     rcx, cs:WPP_GLOBAL_Control
0x18000943c  lea     rax, WPP_GLOBAL_Control
0x180009443  cmp     rcx, rax
0x180009446  jz      short loc_18000947A
0x180009448  test    byte ptr [rcx+1Ch], 1
0x18000944c  jz      short loc_18000947A
0x18000944e  mov     rcx, [rcx+10h]
0x180009452  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009459  mov     [rsp+88h+var_58], 13Eh
0x180009461  lea     r9, aStatus; "Status"
0x180009468  mov     [rsp+88h+var_60], r8
0x18000946d  mov     [rsp+88h+var_68], 8009000Eh
0x180009475  call    WPP_SF_sDsd
0x18000947a  mov     eax, 8009000Eh
0x18000947f  jmp     short loc_180009424
0x180009481  mov     rax, [r15+8]
0x180009485  mov     [rsp+88h+arg_0], 0
0x180009491  mov     rcx, [rax+r14+8]
0x180009496  mov     rax, [rcx+r11+10h]
0x18000949b  test    rax, rax
0x18000949e  jz      loc_18000932E
0x1800094a4  cmp     dword ptr [rcx+r11+18h], 1
0x1800094aa  jnz     loc_18000932E
0x1800094b0  xor     r8d, r8d
0x1800094b3  lea     rdx, [rsp+88h+arg_0]
0x1800094bb  mov     rcx, rax
0x1800094be  call    NCryptDuplicateKeyProtectorHandle
0x1800094c3  mov     ebx, eax
0x1800094c5  test    eax, eax
0x1800094c7  jnz     loc_180009604
0x1800094cd  mov     rax, [rsp+88h+arg_0]
0x1800094d5  mov     [rsi+10h], rax
0x1800094d9  mov     dword ptr [rsi+18h], 1
0x1800094e0  jmp     loc_18000932E
0x1800094e5  mov     rbx, [rcx+r13+8]
0x1800094ea  lea     rbp, [r10-1]
0x1800094ee  mov     r11, rdx
0x1800094f1  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800094f8  shl     r11, 5
0x1800094fc  add     r11, rbx
0x1800094ff  mov     rax, [r11]
0x180009502  inc     rcx
0x180009505  cmp     word ptr [rax+rcx*2], 0
0x18000950a  jnz     short loc_180009502
0x18000950c  mov     r8, [r11+8]
0x180009510  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180009517  nop     word ptr [rax+rax+00000000h]
0x180009520  inc     rax
0x180009523  cmp     word ptr [r8+rax*2], 0
0x180009529  jnz     short loc_180009520
0x18000952b  add     rax, rcx
0x18000952e  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180009535  lea     r12, [r12+rax*2]
0x180009539  mov     rax, [r11+20h]
0x18000953d  add     r12, 4
0x180009541  inc     rcx
0x180009544  cmp     word ptr [rax+rcx*2], 0
0x180009549  jnz     short loc_180009541
0x18000954b  mov     r8, [r11+28h]
0x18000954f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180009556  nop     word ptr [rax+rax+00000000h]
0x180009560  inc     rax
0x180009563  cmp     word ptr [r8+rax*2], 0
0x180009569  jnz     short loc_180009560
0x18000956b  add     rax, rcx
0x18000956e  add     rdx, 2
0x180009572  lea     r15, [r15+rax*2]
0x180009576  add     r15, 4
0x18000957a  cmp     rdx, rbp
  ... truncated ...
```
