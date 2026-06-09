# EfsGetLocalFileName

- ea: `0x180008544`
- end: `0x180008a15`
- name: `EfsGetLocalFileName`
- size: `1233`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int16 **, _WORD *)`
- caller_count: `8`
- callee_count: `5`
- tags: ``

## callers

- `0x180007320`
- `0x180007460`
- `0x180007590`
- `0x180007750`
- `0x180007890`
- `0x180007a30`
- `0x180007b10`
- `0x180007c20`

## callees

- `0x180005c94`
- `0x180005d58`
- `0x1800064f4`
- `0x180008544`
- `0x18001200e`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008607`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000868b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008723`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000890d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008927`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800089bb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800089d4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008607`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000868b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008723`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000890d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008927`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800089bb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800089d4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000861a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000869e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008731`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008935`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000861a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000869e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008731`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008935`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000891b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800089c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800089e2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000891b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800089c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800089e2`
- `srvcli!NetShareGetInfo` at `0x1800087ff`
- `srvcli!NetShareGetInfo` at `0x1800087ff`
- `netutils!NetApiBufferFree` at `0x1800089f5`
- `netutils!NetApiBufferFree` at `0x1800089f5`

## pseudocode

```c
__int64 __fastcall EfsGetLocalFileName(unsigned __int16 *a1, __int64 a2, unsigned __int16 **a3, _WORD *a4)
{
  __int64 v7; // rdx
  unsigned __int16 *v8; // rax
  unsigned __int64 v9; // rbx
  __int64 v10; // rcx
  HANDLE v11; // rax
  unsigned __int16 *v12; // rax
  unsigned int v13; // ebx
  unsigned __int16 *v14; // r11
  int v15; // r15d
  int v16; // r12d
  unsigned __int64 v17; // r14
  SIZE_T v18; // rdi
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v20; // rax
  unsigned __int16 *v21; // rdi
  HANDLE v22; // rax
  unsigned __int16 *v23; // rax
  unsigned __int16 *v24; // r14
  __int64 v25; // rcx
  WCHAR *v26; // r11
  WCHAR *v27; // r10
  unsigned __int16 *v28; // r12
  DWORD Info; // eax
  int v30; // ecx
  __int64 v31; // r9
  __int64 v32; // rdx
  _WORD *v33; // rax
  __int64 v34; // r8
  __int64 v35; // rcx
  unsigned __int16 *v36; // rax
  unsigned __int64 v37; // rax
  unsigned __int64 v38; // rcx
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rcx
  unsigned int v42; // ecx
  unsigned __int64 v43; // rsi
  HANDLE v44; // rax
  HANDLE v45; // rax
  unsigned __int16 *v46; // rax
  HANDLE v47; // rax
  HANDLE v48; // rax
  unsigned int v50; // [rsp+80h] [rbp+8h]
  unsigned int v51; // [rsp+88h] [rbp+10h]
  LPBYTE bufptr; // [rsp+98h] [rbp+20h] BYREF

  bufptr = 0;
  *a4 = 0;
  if ( !a1 )
    return 5;
  v7 = 0x7FFFFFFF;
  v8 = a1;
  do
  {
    if ( !*v8 )
      break;
    ++v8;
    --v7;
  }
  while ( v7 );
  v9 = (0x7FFFFFFF - v7) & -(__int64)(v7 != 0);
  if ( !v7 )
    return 5;
  if ( v9 > 0xFFFFFFFF )
    return 5;
  v10 = (unsigned int)(v9 + 10);
  if ( (unsigned int)v10 < (unsigned int)v9 || 2 * (unsigned __int64)(unsigned int)v10 > 0xFFFFFFFF )
    return 5;
  v50 = v9 + 1;
  if ( (unsigned int)(v9 + 1) <= 0x104 )
    v10 = 261;
  v51 = v10;
  if ( *a1 != 1 )
  {
    v15 = 0;
    v16 = 1;
    if ( (unsigned int)v9 > 4 && *a1 == 92 && a1[1] == 92 )
    {
      if ( (a1[2] == 63 || a1[2] == 46) && a1[3] == 92 )
        v16 = 0;
      else
        v15 = 1;
    }
    v17 = (unsigned int)v10;
    v18 = 2 * v10;
    ProcessHeap = GetProcessHeap();
    v20 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, v18);
    v21 = v20;
    if ( !v20 )
      goto LABEL_13;
    memset_0(v20, 0, 2 * v17);
    if ( !v15 )
    {
      if ( v16 && (unsigned int)v9 >= 0x104 )
      {
        StringCchCopyW(v21, (unsigned int)v17, L"\\\\?\\");
        StringCchCatW(v21, (unsigned int)v17, a1);
      }
      else
      {
        StringCchCopyW(v21, v17, a1);
      }
      v13 = 0;
      *a3 = v21;
      goto LABEL_75;
    }
    v22 = GetProcessHeap();
    v23 = (unsigned __int16 *)HeapAlloc(v22, 8u, 2LL * v50);
    v24 = v23;
    if ( !v23 )
    {
      v13 = 8;
LABEL_74:
      v48 = GetProcessHeap();
      HeapFree(v48, 0, v21);
      goto LABEL_75;
    }
    if ( (int)StringCchCopyW(v23, v50, a1) < 0 )
      goto LABEL_33;
    LODWORD(v25) = 0;
    if ( *v24 == 92 )
    {
      do
        v25 = (unsigned int)(v25 + 1);
      while ( v24[v25] == 92 );
    }
    v26 = &v24[(unsigned int)v25];
    if ( *v26 )
    {
      do
      {
        if ( v24[(unsigned int)v25] == 92 )
          break;
        v25 = (unsigned int)(v25 + 1);
      }
      while ( v24[v25] );
    }
    if ( v24[(unsigned int)v25] == 92 )
    {
      v24[(unsigned int)v25] = 0;
      LODWORD(v25) = v25 + 1;
    }
    v27 = &v24[(unsigned int)v25];
    if ( *v27 )
    {
      do
      {
        if ( v24[(unsigned int)v25] == 92 )
          break;
        v25 = (unsigned int)(v25 + 1);
      }
      while ( v24[v25] );
    }
    v28 = &a1[(unsigned int)v25];
    if ( !*v28 )
      goto LABEL_45;
    v24[(unsigned int)v25] = 0;
    Info = NetShareGetInfo(v26, v27, 2u, &bufptr);
    v13 = Info;
    if ( Info )
    {
      fnEfsLogTrace1(v30, (unsigned int)EFS_API_ERROR, Info, 21, 54);
LABEL_45:
      v13 = 53;
      goto LABEL_73;
    }
    v31 = *((_QWORD *)bufptr + 5);
    if ( !v31 )
      goto LABEL_72;
    v32 = 0x7FFFFFFF;
    v33 = (_WORD *)*((_QWORD *)bufptr + 5);
    do
    {
      if ( !*v33 )
        break;
      ++v33;
      --v32;
    }
    while ( v32 );
    v34 = (0x7FFFFFFF - v32) & -(__int64)(v32 != 0);
    if ( !v32 )
      goto LABEL_72;
    v35 = 0x7FFFFFFF;
    v36 = v28;
    do
    {
      if ( !*v36 )
        break;
      ++v36;
      --v35;
    }
    while ( v35 );
    if ( !v35
      || (v37 = ((0x7FFFFFFF - v35) & -(__int64)(v35 != 0)) + 1, v38 = v37 + v34, v37 + v34 < v37)
      || v38 > 0xFFFFFFFF
      || (v39 = (unsigned int)(v38 + 5), (unsigned int)v39 < (unsigned int)v38)
      || (unsigned __int64)(2 * v39) > 0xFFFFFFFF )
    {
LABEL_72:
      v13 = 5;
LABEL_73:
      v47 = GetProcessHeap();
      HeapFree(v47, 0, v24);
      if ( !v21 )
        goto LABEL_75;
      goto LABEL_74;
    }
    v40 = -1;
    v41 = -1;
    do
      ++v41;
    while ( v28[v41] );
    do
      ++v40;
    while ( *(_WORD *)(v31 + 2 * v40) );
    v42 = v40 + v41 + 1;
    if ( v42 < 0x104 || (v43 = v42 + 5, (unsigned int)v43 <= v51) )
    {
      v43 = v51;
      if ( v42 < 0x104 )
      {
        StringCchCopyW(v21, v51, *((const unsigned __int16 **)bufptr + 5));
        goto LABEL_71;
      }
    }
    else
    {
      v44 = GetProcessHeap();
      HeapFree(v44, 0, v21);
      v45 = GetProcessHeap();
      v46 = (unsigned __int16 *)HeapAlloc(v45, 8u, 2LL * (unsigned int)v43);
      v21 = v46;
      if ( !v46 )
      {
LABEL_33:
        v13 = 8;
        goto LABEL_73;
      }
      memset_0(v46, 0, 2LL * (unsigned int)v43);
    }
    StringCchCopyW(v21, v43, L"\\\\?\\");
    StringCchCatW(v21, v43, *((const unsigned __int16 **)bufptr + 5));
LABEL_71:
    StringCchCatW(v21, v43, v28);
    *a3 = v21;
    v21 = 0;
    goto LABEL_73;
  }
  v11 = GetProcessHeap();
  v12 = (unsigned __int16 *)HeapAlloc(v11, 8u, 2LL * (unsigned int)v9);
  if ( !v12 )
  {
LABEL_13:
    v13 = 8;
    goto LABEL_75;
  }
  *a4 = 1;
  StringCchCopyW(v12, (unsigned int)v9, a1 + 1);
  v13 = 0;
  *a3 = v14;
LABEL_75:
  if ( bufptr )
    NetApiBufferFree(bufptr);
  return v13;
}

```

## disassembly

```asm
0x180008544  mov     rax, rsp
0x180008547  mov     [rax+18h], r8
0x18000854b  mov     [rax+10h], edx
0x18000854e  push    rbx
0x18000854f  push    rbp
0x180008550  push    rsi
0x180008551  push    rdi
0x180008552  push    r12
0x180008554  push    r13
0x180008556  push    r14
0x180008558  push    r15
0x18000855a  sub     rsp, 38h
0x18000855e  xor     r12d, r12d
0x180008561  mov     r14, r9
0x180008564  mov     [rax+20h], r12
0x180008568  mov     r15, r8
0x18000856b  mov     [r9], r12w
0x18000856f  mov     rsi, rcx
0x180008572  test    rcx, rcx
0x180008575  jz      loc_1800089FD
0x18000857b  mov     r13d, 7FFFFFFFh
0x180008581  lea     r8d, [r12+1]
0x180008586  mov     edx, r13d
0x180008589  mov     rax, rcx
0x18000858c  cmp     [rax], r12w
0x180008590  jz      short loc_18000859B
0x180008592  add     rax, 2
0x180008596  sub     rdx, r8
0x180008599  jnz     short loc_18000858C
0x18000859b  mov     rcx, r13
0x18000859e  mov     rax, rdx
0x1800085a1  sub     rcx, rdx
0x1800085a4  neg     rax
0x1800085a7  sbb     rbx, rbx
0x1800085aa  and     rbx, rcx
0x1800085ad  test    rdx, rdx
0x1800085b0  jz      loc_1800089FD
0x1800085b6  mov     edx, 0FFFFFFFFh
0x1800085bb  cmp     rbx, rdx
0x1800085be  ja      loc_1800089FD
0x1800085c4  lea     ecx, [rbx+0Ah]
0x1800085c7  cmp     ecx, ebx
0x1800085c9  jb      loc_1800089FD
0x1800085cf  mov     eax, ecx
0x1800085d1  add     rax, rax
0x1800085d4  cmp     rax, rdx
0x1800085d7  ja      loc_1800089FD
0x1800085dd  lea     eax, [rbx+1]
0x1800085e0  mov     edx, 105h
0x1800085e5  cmp     eax, 104h
0x1800085ea  mov     dword ptr [rsp+78h+arg_0], eax
0x1800085f1  cmovbe  ecx, edx
0x1800085f4  mov     dword ptr [rsp+78h+arg_8], ecx
0x1800085fb  cmp     r8w, [rsi]
0x1800085ff  jnz     short loc_18000864F
0x180008601  mov     edi, ebx
0x180008603  lea     rbx, [rdi+rdi]
0x180008607  call    cs:__imp_GetProcessHeap
0x18000860d  mov     ebp, 8
0x180008612  mov     r8, rbx; dwBytes
0x180008615  mov     rcx, rax; hHeap
0x180008618  mov     edx, ebp; dwFlags
0x18000861a  call    cs:__imp_HeapAlloc
0x180008620  mov     r11, rax
0x180008623  test    rax, rax
0x180008626  jnz     short loc_18000862F
0x180008628  mov     ebx, ebp
0x18000862a  jmp     loc_1800089E8
0x18000862f  lea     r8, [rsi+2]; unsigned __int16 *
0x180008633  mov     word ptr [r14], 1
0x180008639  mov     rdx, rdi; unsigned __int64
0x18000863c  mov     rcx, r11; unsigned __int16 *
0x18000863f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180008644  mov     ebx, r12d
0x180008647  mov     [r15], r11
0x18000864a  jmp     loc_1800089E8
0x18000864f  mov     r15d, r12d
0x180008652  mov     r12d, r8d
0x180008655  cmp     ebx, 4
0x180008658  jbe     short loc_180008684
0x18000865a  cmp     word ptr [rsi], 5Ch ; '\'
0x18000865e  jnz     short loc_180008684
0x180008660  cmp     word ptr [rsi+2], 5Ch ; '\'
0x180008665  jnz     short loc_180008684
0x180008667  cmp     word ptr [rsi+4], 3Fh ; '?'
0x18000866c  jz      short loc_18000867A
0x18000866e  cmp     word ptr [rsi+4], 2Eh ; '.'
0x180008673  jz      short loc_18000867A
0x180008675  mov     r15d, r8d
0x180008678  jmp     short loc_180008684
0x18000867a  cmp     word ptr [rsi+6], 5Ch ; '\'
0x18000867f  jnz     short loc_180008675
0x180008681  xor     r12d, r12d
0x180008684  mov     r14d, ecx
0x180008687  lea     rdi, [rcx+rcx]
0x18000868b  call    cs:__imp_GetProcessHeap
0x180008691  mov     ebp, 8
0x180008696  mov     r8, rdi; dwBytes
0x180008699  mov     rcx, rax; hHeap
0x18000869c  mov     edx, ebp; dwFlags
0x18000869e  call    cs:__imp_HeapAlloc
0x1800086a4  mov     rdi, rax
0x1800086a7  test    rax, rax
0x1800086aa  jz      loc_180008628
0x1800086b0  lea     r8, [r14+r14]; Size
0x1800086b4  xor     edx, edx; Val
0x1800086b6  mov     rcx, rax; void *
0x1800086b9  call    memset_0
0x1800086be  test    r15d, r15d
0x1800086c1  jnz     short loc_180008717
0x1800086c3  xor     r15d, r15d
0x1800086c6  test    r12d, r12d
0x1800086c9  jz      short loc_1800086F6
0x1800086cb  mov     edx, 104h
0x1800086d0  cmp     ebx, edx
0x1800086d2  jb      short loc_1800086F6
0x1800086d4  lea     r8, asc_1800186E0; "\\\\?\\"
0x1800086db  mov     edx, r14d; unsigned __int64
0x1800086de  mov     rcx, rdi; unsigned __int16 *
0x1800086e1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800086e6  mov     r8, rsi; unsigned __int16 *
0x1800086e9  mov     edx, r14d; unsigned __int64
0x1800086ec  mov     rcx, rdi; unsigned __int16 *
0x1800086ef  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800086f4  jmp     short loc_180008704
0x1800086f6  mov     r8, rsi; unsigned __int16 *
0x1800086f9  mov     rdx, r14; unsigned __int64
0x1800086fc  mov     rcx, rdi; unsigned __int16 *
0x1800086ff  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180008704  mov     rax, [rsp+78h+arg_10]
0x18000870c  mov     ebx, r15d
0x18000870f  mov     [rax], rdi
0x180008712  jmp     loc_1800089E8
0x180008717  mov     r15d, dword ptr [rsp+78h+arg_0]
0x18000871f  lea     rbx, [r15+r15]
0x180008723  call    cs:__imp_GetProcessHeap
0x180008729  mov     r8, rbx; dwBytes
0x18000872c  mov     edx, ebp; dwFlags
0x18000872e  mov     rcx, rax; hHeap
0x180008731  call    cs:__imp_HeapAlloc
0x180008737  mov     r14, rax
0x18000873a  test    rax, rax
0x18000873d  jnz     short loc_180008746
0x18000873f  mov     ebx, ebp
0x180008741  jmp     loc_1800089D4
0x180008746  mov     r8, rsi; unsigned __int16 *
0x180008749  mov     rdx, r15; unsigned __int64
0x18000874c  mov     rcx, r14; unsigned __int16 *
0x18000874f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180008754  xor     r15d, r15d
0x180008757  test    eax, eax
0x180008759  jns     short loc_180008762
0x18000875b  mov     ebx, ebp
0x18000875d  jmp     loc_1800089BB
0x180008762  mov     r9w, 5Ch ; '\'
0x180008767  mov     ecx, r15d
0x18000876a  mov     r8d, 1
0x180008770  cmp     [r14], r9w
0x180008774  jnz     short loc_180008780
0x180008776  add     ecx, r8d
0x180008779  cmp     [r14+rcx*2], r9w
0x18000877e  jz      short loc_180008776
0x180008780  mov     eax, ecx
0x180008782  lea     r11, [r14+rax*2]
0x180008786  cmp     [r11], r15w
0x18000878a  jz      short loc_18000879F
0x18000878c  mov     eax, ecx
0x18000878e  cmp     [r14+rax*2], r9w
0x180008793  jz      short loc_18000879F
0x180008795  add     ecx, r8d
0x180008798  cmp     [r14+rcx*2], r15w
0x18000879d  jnz     short loc_18000878C
0x18000879f  mov     edx, ecx
0x1800087a1  cmp     [r14+rdx*2], r9w
0x1800087a6  jnz     short loc_1800087B0
0x1800087a8  mov     [r14+rdx*2], r15w
0x1800087ad  add     ecx, r8d
0x1800087b0  mov     eax, ecx
0x1800087b2  lea     r10, [r14+rax*2]
0x1800087b6  cmp     [r10], r15w
0x1800087ba  jz      short loc_1800087CF
0x1800087bc  mov     eax, ecx
0x1800087be  cmp     [r14+rax*2], r9w
0x1800087c3  jz      short loc_1800087CF
0x1800087c5  add     ecx, r8d
0x1800087c8  cmp     [r14+rcx*2], r15w
0x1800087cd  jnz     short loc_1800087BC
0x1800087cf  mov     edx, ecx
0x1800087d1  lea     r12, [rsi+rdx*2]
0x1800087d5  cmp     [r12], r15w
0x1800087da  jnz     short loc_1800087E6
0x1800087dc  mov     ebx, 35h ; '5'
0x1800087e1  jmp     loc_1800089BB
0x1800087e6  mov     [r14+rdx*2], r15w
0x1800087eb  lea     r9, [rsp+78h+bufptr]; bufptr
0x1800087f3  mov     rdx, r10; netname
0x1800087f6  mov     r8d, 2; level
0x1800087fc  mov     rcx, r11; servername
0x1800087ff  call    cs:__imp_NetShareGetInfo
0x180008805  mov     ebx, eax
0x180008807  test    eax, eax
0x180008809  jz      short loc_18000882A
0x18000880b  mov     r9d, 15h
0x180008811  mov     [rsp+78h+var_58], 136h
0x180008819  mov     r8d, eax
0x18000881c  lea     rdx, EFS_API_ERROR
0x180008823  call    fnEfsLogTrace1
0x180008828  jmp     short loc_1800087DC
0x18000882a  mov     r10, [rsp+78h+bufptr]
0x180008832  mov     r9, [r10+28h]
0x180008836  test    r9, r9
0x180008839  jz      loc_1800089B6
0x18000883f  mov     rdx, r13
0x180008842  mov     rax, r9
0x180008845  mov     r11d, 1
0x18000884b  cmp     [rax], r15w
0x18000884f  jz      short loc_18000885A
0x180008851  add     rax, 2
0x180008855  sub     rdx, r11
0x180008858  jnz     short loc_18000884B
0x18000885a  mov     rcx, r13
0x18000885d  mov     rax, rdx
0x180008860  sub     rcx, rdx
0x180008863  neg     rax
0x180008866  sbb     r8, r8
0x180008869  and     r8, rcx
0x18000886c  test    rdx, rdx
0x18000886f  jz      loc_1800089B6
0x180008875  mov     rcx, r13
0x180008878  mov     rax, r12
0x18000887b  cmp     [rax], r15w
0x18000887f  jz      short loc_18000888A
0x180008881  add     rax, 2
0x180008885  sub     rcx, r11
0x180008888  jnz     short loc_18000887B
0x18000888a  sub     r13, rcx
0x18000888d  mov     rax, rcx
0x180008890  neg     rax
0x180008893  sbb     rax, rax
0x180008896  and     rax, r13
0x180008899  test    rcx, rcx
0x18000889c  jz      loc_1800089B6
0x1800088a2  inc     rax
0x1800088a5  lea     rcx, [rax+r8]
0x1800088a9  cmp     rcx, rax
0x1800088ac  jb      loc_1800089B6
0x1800088b2  mov     edx, 0FFFFFFFFh
0x1800088b7  cmp     rcx, rdx
0x1800088ba  ja      loc_1800089B6
0x1800088c0  lea     eax, [rcx+5]
0x1800088c3  cmp     eax, ecx
0x1800088c5  jb      loc_1800089B6
0x1800088cb  add     rax, rax
0x1800088ce  cmp     rax, rdx
0x1800088d1  ja      loc_1800089B6
0x1800088d7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800088db  mov     rcx, rax
0x1800088de  inc     rcx
0x1800088e1  cmp     [r12+rcx*2], r15w
0x1800088e6  jnz     short loc_1800088DE
0x1800088e8  inc     rax
0x1800088eb  cmp     [r9+rax*2], r15w
0x1800088f0  jnz     short loc_1800088E8
0x1800088f2  inc     ecx
0x1800088f4  mov     edx, 104h
0x1800088f9  add     ecx, eax
0x1800088fb  mov     eax, dword ptr [rsp+78h+arg_8]
0x180008902  cmp     ecx, edx
0x180008904  jb      short loc_180008959
0x180008906  lea     esi, [rcx+5]
0x180008909  cmp     esi, eax
0x18000890b  jbe     short loc_180008959
0x18000890d  call    cs:__imp_GetProcessHeap
0x180008913  mov     r8, rdi; lpMem
0x180008916  xor     edx, edx; dwFlags
0x180008918  mov     rcx, rax; hHeap
0x18000891b  call    cs:__imp_HeapFree
0x180008921  mov     r15d, esi
0x180008924  add     r15, r15
0x180008927  call    cs:__imp_GetProcessHeap
0x18000892d  mov     r8, r15; dwBytes
0x180008930  mov     edx, ebp; dwFlags
0x180008932  mov     rcx, rax; hHeap
0x180008935  call    cs:__imp_HeapAlloc
0x18000893b  mov     rdi, rax
0x18000893e  test    rax, rax
0x180008941  jz      loc_18000875B
0x180008947  mov     r8, r15; Size
0x18000894a  xor     edx, edx; Val
0x18000894c  mov     rcx, rax; void *
0x18000894f  call    memset_0
0x180008954  xor     r15d, r15d
0x180008957  jmp     short loc_18000895F
0x180008959  mov     esi, eax
0x18000895b  cmp     ecx, edx
0x18000895d  jb      short loc_18000898A
0x18000895f  lea     r8, asc_1800186E0; "\\\\?\\"
0x180008966  mov     rdx, rsi; unsigned __int64
0x180008969  mov     rcx, rdi; unsigned __int16 *
0x18000896c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
  ... truncated ...
```
