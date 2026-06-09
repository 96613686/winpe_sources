# PiiFilterEmbeddedPathsExecute

- ea: `0x1800180f8`
- end: `0x1800186cd`
- name: `PiiFilterEmbeddedPathsExecute`
- size: `1493`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800174a4`
- `0x1800186d4`

## callees

- `0x18000267c`
- `0x18000f2dc`
- `0x180013f04`
- `0x180015de8`
- `0x1800180f8`

## import_xrefs

- `msvcrt!wcschr` at `0x180018657`
- `msvcrt!wcschr` at `0x180018657`
- `msvcrt!iswspace` at `0x1800185b3`
- `msvcrt!iswspace` at `0x180018618`
- `msvcrt!iswspace` at `0x1800185b3`
- `msvcrt!iswspace` at `0x180018618`
- `ntdll!RtlFreeHeap` at `0x180018693`
- `ntdll!RtlFreeHeap` at `0x1800186b0`
- `ntdll!RtlFreeHeap` at `0x180018693`
- `ntdll!RtlFreeHeap` at `0x1800186b0`
- `ntdll!RtlAllocateHeap` at `0x180018138`
- `ntdll!RtlAllocateHeap` at `0x180018167`
- `ntdll!RtlAllocateHeap` at `0x180018138`
- `ntdll!RtlAllocateHeap` at `0x180018167`

## pseudocode

```c
__int64 __fastcall PiiFilterEmbeddedPathsExecute(
        unsigned __int16 *a1,
        unsigned __int64 a2,
        unsigned __int64 *a3,
        unsigned __int16 *a4)
{
  SIZE_T v4; // rsi
  unsigned __int64 v7; // rbx
  signed int v9; // edi
  wchar_t *Heap; // rbp
  __int64 v11; // r12
  unsigned __int64 v12; // rdx
  __int64 v13; // rax
  unsigned __int16 *v14; // r8
  unsigned __int16 *v15; // rcx
  unsigned __int64 v16; // r8
  unsigned __int64 v17; // rdx
  unsigned __int64 v18; // rdi
  _QWORD *v19; // r8
  wchar_t **v20; // rax
  wchar_t *v21; // rsi
  __int64 *v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rax
  unsigned __int64 v25; // rdi
  wchar_t **v26; // rax
  __int64 *v27; // rax
  __int64 v28; // r13
  unsigned __int64 v29; // rdx
  __int64 v30; // rax
  unsigned __int16 *v31; // rcx
  wchar_t *v32; // r8
  wchar_t *v33; // rcx
  wchar_t *v34; // r8
  __int64 v35; // rax
  unsigned __int64 v36; // rdx
  wchar_t *v37; // rcx
  __int64 v38; // rsi
  wchar_t *v39; // rax
  __int64 v40; // rcx
  __int64 v41; // rax
  unsigned __int16 *v42; // r9
  __int64 v43; // rax
  unsigned __int64 v44; // rdx
  wchar_t *v45; // r8
  wchar_t *v46; // rcx
  unsigned __int16 *v47; // rax
  wchar_t *v48; // rdx
  wchar_t *v49; // rcx
  wchar_t *i; // rax
  const wchar_t *v51; // rcx
  wchar_t v52; // dx
  unsigned __int16 *v53; // rdi
  const wchar_t *j; // rcx
  wint_t *v55; // rdi
  wint_t *v56; // rbx
  int v57; // esi
  unsigned __int16 v58; // ax
  BOOL v59; // eax
  char *v60; // rdi
  unsigned __int64 v61; // rcx
  wchar_t *v62; // rax
  unsigned __int64 v64; // [rsp+20h] [rbp-48h]
  int v65; // [rsp+78h] [rbp+10h] BYREF
  wchar_t *SubStr; // [rsp+80h] [rbp+18h]

  v4 = 2 * a2;
  v7 = a2;
  v64 = 2 * a2;
  SubStr = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * a2);
  if ( !SubStr )
    return (unsigned int)-1073741801;
  Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v4);
  if ( !Heap )
  {
    v9 = -1073741801;
    goto LABEL_116;
  }
  if ( v7 )
  {
    if ( v7 > 0x7FFFFFFF )
    {
      v9 = -1073741811;
      *a1 = 0;
      goto LABEL_116;
    }
    v11 = 2147483646;
    v12 = v7;
    v13 = 2147483646;
    v14 = a1;
    do
    {
      if ( !v13 )
        break;
      if ( !*a4 )
        break;
      *v14++ = *a4++;
      --v13;
      --v12;
    }
    while ( v12 );
    v15 = v14 - 1;
    v9 = v12 == 0 ? 0x80000005 : 0;
    if ( v12 )
      v15 = v14;
    *v15 = 0;
    if ( !v12 )
      goto LABEL_116;
    v16 = a3[8];
    v17 = a3[2];
    if ( !(v17 + v16) )
    {
LABEL_70:
      v47 = a1;
      v48 = Heap;
      do
      {
        if ( !v11 )
          break;
        if ( !*v47 )
          break;
        *v48++ = *v47++;
        --v11;
        --v7;
      }
      while ( v7 );
      v49 = v48 - 1;
      v9 = v7 == 0 ? 0x80000005 : 0;
      if ( v7 )
        v49 = v48;
      *v49 = 0;
      if ( v7 )
      {
        AslStringUpper(Heap, v48, v16, 1);
        for ( i = wcsstr_0(Heap, L"\\USERS\\"); i; i = wcsstr_0(v51, L"\\USERS\\") )
        {
          v51 = i + 7;
          v52 = i[7];
          if ( v52 )
          {
            v53 = &a1[v51 - Heap];
            do
            {
              if ( v52 == 92 )
                break;
              if ( v53 >= (unsigned __int16 *)((char *)a1 + v4) )
                break;
              ++v51;
              *v53++ = 120;
              v52 = *v51;
            }
            while ( *v51 );
          }
        }
        for ( j = a1; ; j = v56 )
        {
          v62 = wcschr(j, 0x40u);
          if ( !v62 || !*v62 )
            break;
          v55 = v62 - 1;
          v65 = 0;
          v56 = v62 + 1;
          v57 = 0;
          v58 = v62[1];
          if ( v58 )
          {
            do
            {
              if ( (unsigned int)PiipIsInvalidEmailCharacter(v58, 0, &v65) )
                break;
              if ( *v56 == 46 )
                v57 = 1;
              v58 = *++v56;
            }
            while ( *v56 );
          }
          v59 = iswspace(*v56) || !*v56 || *v56 == 62;
          if ( v57 && v59 )
          {
            --v56;
            v65 = 0;
            while ( v55 >= a1 )
            {
              if ( (unsigned int)PiipIsInvalidEmailCharacter(*v55, 1, &v65) )
              {
                if ( *v55 != 60 && !iswspace(*v55) )
                  goto LABEL_112;
                break;
              }
              --v55;
            }
            if ( !v65 )
            {
              v60 = (char *)(v55 + 1);
              v61 = (unsigned __int64)((char *)v56 - v60 + 2) >> 1;
              if ( v60 > (char *)v56 )
                v61 = 0;
              if ( v61 )
              {
                while ( v61 )
                {
                  *(_WORD *)v60 = 35;
                  v60 += 2;
                  --v61;
                }
              }
            }
          }
LABEL_112:
          ;
        }
        v9 = 0;
      }
      goto LABEL_116;
    }
    v18 = 0;
    v65 = 0;
    while ( v18 < v17 )
    {
      v19 = a3 + 5;
      if ( !is_mul_ok(a3[1], v18) || (v20 = (wchar_t **)(*v19 + a3[1] * v18), (unsigned __int64)v20 < *v19) )
        v20 = 0;
      v21 = *v20;
      if ( !is_mul_ok(a3[1], v18) || (v22 = (__int64 *)(*v19 + a3[1] * v18), (unsigned __int64)v22 < *v19) )
        v22 = 0;
      v23 = *v22;
      v24 = -1;
      do
        ++v24;
      while ( *(_WORD *)(v23 + 2 * v24) );
LABEL_39:
      v28 = v23 + 2 * v24;
      v29 = v7;
      v30 = 2147483646;
      v31 = a1;
      v32 = Heap;
      do
      {
        if ( !v30 )
          break;
        if ( !*v31 )
          break;
        *v32++ = *v31++;
        --v30;
        --v29;
      }
      while ( v29 );
      v33 = v32 - 1;
      if ( v29 )
        v33 = v32;
      *v33 = 0;
      v9 = v29 == 0 ? 0x80000005 : 0;
      if ( !v29 )
        goto LABEL_116;
      AslStringUpper(Heap, v29, v32, 1);
      v34 = SubStr;
      v35 = 2147483646;
      v36 = v7;
      do
      {
        if ( !v35 )
          break;
        if ( !*v21 )
          break;
        *v34++ = *v21++;
        --v35;
        --v36;
      }
      while ( v36 );
      v37 = v34 - 1;
      if ( v36 )
        v37 = v34;
      *v37 = 0;
      v9 = v36 == 0 ? 0x80000005 : 0;
      if ( !v36 )
        goto LABEL_116;
      v38 = -1;
      do
        ++v38;
      while ( SubStr[v38] );
      if ( v38 && (AslStringUpper(SubStr, v36, v34, 1), (v39 = wcsstr_0(Heap, SubStr)) != 0) )
      {
        v40 = v39 - Heap;
        v41 = v38 + v40;
        a1[v40] = 0;
        v4 = v64;
        v42 = &a1[v41];
        if ( v42 >= &a1[v64 / 2] )
          goto LABEL_116;
        v43 = 2147483646;
        v44 = v7;
        v45 = Heap;
        do
        {
          if ( !v43 )
            break;
          if ( !*v42 )
            break;
          *v45++ = *v42++;
          --v43;
          --v44;
        }
        while ( v44 );
        v46 = v45 - 1;
        if ( v44 )
          v46 = v45;
        *v46 = 0;
        v9 = v44 == 0 ? 0x80000005 : 0;
        if ( !v44 )
          goto LABEL_116;
        v9 = RtlStringCchCatW(a1, v7, (const unsigned __int16 *)(v28 + 2));
        if ( v9 < 0 )
          goto LABEL_116;
        v9 = RtlStringCchCatW(a1, v7, Heap);
        if ( v9 < 0 )
          goto LABEL_116;
        v18 = (unsigned int)v65;
      }
      else
      {
        v4 = v64;
        v18 = (unsigned int)++v65;
      }
      v16 = a3[8];
      v17 = a3[2];
      if ( (unsigned int)v18 >= v17 + v16 )
        goto LABEL_70;
    }
    v25 = v18 - v17;
    if ( v25 >= v16 )
    {
      v21 = (wchar_t *)MEMORY[0];
    }
    else
    {
      if ( is_mul_ok(a3[7], v25) && (v26 = (wchar_t **)(a3[11] + a3[7] * v25), (unsigned __int64)v26 >= a3[11]) )
        v21 = *v26;
      else
        v21 = (wchar_t *)MEMORY[0];
      if ( is_mul_ok(a3[7], v25) )
      {
        v27 = (__int64 *)(a3[11] + a3[7] * v25);
        if ( (unsigned __int64)v27 >= a3[11] )
          goto LABEL_37;
      }
    }
    v27 = 0;
LABEL_37:
    v23 = *v27;
    v24 = -1;
    do
      ++v24;
    while ( *(_WORD *)(v23 + 2 * v24) );
    goto LABEL_39;
  }
  v9 = -1073741811;
LABEL_116:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, SubStr);
  if ( Heap )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800180f8  mov     [rsp+arg_0], rbx
0x1800180fd  push    rbp
0x1800180fe  push    rsi
0x1800180ff  push    rdi
0x180018100  push    r12
0x180018102  push    r13
0x180018104  push    r14
0x180018106  push    r15
0x180018108  sub     rsp, 30h
0x18001810c  lea     rsi, [rdx+rdx]
0x180018110  mov     r14, rcx
0x180018113  mov     rcx, gs:60h
0x18001811c  mov     r15, r8
0x18001811f  mov     rbx, rdx
0x180018122  mov     [rsp+68h+var_48], rsi
0x180018127  mov     ebp, 8
0x18001812c  mov     r8, rsi; Size
0x18001812f  mov     edx, ebp; Flags
0x180018131  mov     rdi, r9
0x180018134  mov     rcx, [rcx+30h]; HeapHandle
0x180018138  call    cs:__imp_RtlAllocateHeap
0x18001813e  mov     [rsp+68h+SubStr], rax
0x180018146  test    rax, rax
0x180018149  jnz     short loc_180018155
0x18001814b  mov     edi, 0C0000017h
0x180018150  jmp     loc_1800186B6
0x180018155  mov     rcx, gs:60h
0x18001815e  mov     r8, rsi; Size
0x180018161  mov     edx, ebp; Flags
0x180018163  mov     rcx, [rcx+30h]; HeapHandle
0x180018167  call    cs:__imp_RtlAllocateHeap
0x18001816d  xor     r10d, r10d
0x180018170  mov     rbp, rax
0x180018173  test    rax, rax
0x180018176  jnz     short loc_180018182
0x180018178  mov     edi, 0C0000017h
0x18001817d  jmp     loc_18001867C
0x180018182  test    rbx, rbx
0x180018185  jz      loc_18001866E
0x18001818b  cmp     rbx, 7FFFFFFFh
0x180018192  jbe     short loc_18001819E
0x180018194  mov     edi, 0C000000Dh
0x180018199  jmp     loc_180018678
0x18001819e  mov     r12d, 7FFFFFFEh
0x1800181a4  mov     rdx, rbx
0x1800181a7  mov     eax, r12d
0x1800181aa  mov     r8, r14
0x1800181ad  mov     r9d, 1
0x1800181b3  test    rax, rax
0x1800181b6  jz      short loc_1800181D4
0x1800181b8  movzx   ecx, word ptr [rdi]
0x1800181bb  test    cx, cx
0x1800181be  jz      short loc_1800181D4
0x1800181c0  mov     [r8], cx
0x1800181c4  add     rdi, 2
0x1800181c8  add     r8, 2
0x1800181cc  sub     rax, r9
0x1800181cf  sub     rdx, r9
0x1800181d2  jnz     short loc_1800181B3
0x1800181d4  mov     rax, rdx
0x1800181d7  lea     rcx, [r8-2]
0x1800181db  neg     rax
0x1800181de  sbb     edi, edi
0x1800181e0  not     edi
0x1800181e2  and     edi, 80000005h
0x1800181e8  test    rdx, rdx
0x1800181eb  cmovnz  rcx, r8
0x1800181ef  mov     [rcx], r10w
0x1800181f3  jz      loc_18001867C
0x1800181f9  mov     r8, [r15+40h]
0x1800181fd  mov     rdx, [r15+10h]
0x180018201  lea     rax, [rdx+r8]
0x180018205  test    rax, rax
0x180018208  jz      loc_1800184A0
0x18001820e  mov     edi, r10d
0x180018211  mov     [rsp+68h+arg_8], edi
0x180018215  cmp     rdi, rdx
0x180018218  jnb     short loc_180018262
0x18001821a  mov     rax, rdi
0x18001821d  lea     r8, [r15+28h]
0x180018221  mul     qword ptr [r15+8]
0x180018225  test    rdx, rdx
0x180018228  jnz     short loc_180018232
0x18001822a  add     rax, [r8]
0x18001822d  cmp     rax, [r8]
0x180018230  jnb     short loc_180018235
0x180018232  mov     rax, r10
0x180018235  mov     rsi, [rax]
0x180018238  mov     rax, rdi
0x18001823b  mul     qword ptr [r15+8]
0x18001823f  test    rdx, rdx
0x180018242  jnz     short loc_18001824C
0x180018244  add     rax, [r8]
0x180018247  cmp     rax, [r8]
0x18001824a  jnb     short loc_18001824F
0x18001824c  mov     rax, r10
0x18001824f  mov     rcx, [rax]
0x180018252  or      rax, 0FFFFFFFFFFFFFFFFh
0x180018256  inc     rax
0x180018259  cmp     [rcx+rax*2], r10w
0x18001825e  jnz     short loc_180018256
0x180018260  jmp     short loc_1800182C1
0x180018262  sub     rdi, rdx
0x180018265  cmp     rdi, r8
0x180018268  jnb     short loc_1800182A5
0x18001826a  mov     rax, rdi
0x18001826d  mul     qword ptr [r15+38h]
0x180018271  test    rdx, rdx
0x180018274  jnz     short loc_180018285
0x180018276  add     rax, [r15+58h]
0x18001827a  cmp     rax, [r15+58h]
0x18001827e  jb      short loc_180018285
0x180018280  mov     rsi, [rax]
0x180018283  jmp     short loc_18001828D
0x180018285  mov     rsi, ds:0
0x18001828d  mov     rax, rdi
0x180018290  mul     qword ptr [r15+38h]
0x180018294  test    rdx, rdx
0x180018297  jnz     short loc_1800182AD
0x180018299  add     rax, [r15+58h]
0x18001829d  cmp     rax, [r15+58h]
0x1800182a1  jnb     short loc_1800182B0
0x1800182a3  jmp     short loc_1800182AD
0x1800182a5  mov     rsi, ds:0
0x1800182ad  mov     rax, r10
0x1800182b0  mov     rcx, [rax]
0x1800182b3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800182b7  inc     rax
0x1800182ba  cmp     [rcx+rax*2], r10w
0x1800182bf  jnz     short loc_1800182B7
0x1800182c1  lea     r13, [rcx+rax*2]
0x1800182c5  mov     rdx, rbx
0x1800182c8  mov     rax, r12
0x1800182cb  mov     rcx, r14
0x1800182ce  mov     r8, rbp
0x1800182d1  test    rax, rax
0x1800182d4  jz      short loc_1800182F2
0x1800182d6  movzx   edi, word ptr [rcx]
0x1800182d9  test    di, di
0x1800182dc  jz      short loc_1800182F2
0x1800182de  mov     [r8], di
0x1800182e2  add     rcx, 2
0x1800182e6  add     r8, 2
0x1800182ea  sub     rax, r9
0x1800182ed  sub     rdx, r9
0x1800182f0  jnz     short loc_1800182D1
0x1800182f2  mov     rax, rdx
0x1800182f5  lea     rcx, [r8-2]
0x1800182f9  neg     rax
0x1800182fc  sbb     edi, edi
0x1800182fe  test    rdx, rdx
0x180018301  not     edi
0x180018303  cmovnz  rcx, r8
0x180018307  mov     [rcx], r10w
0x18001830b  and     edi, 80000005h
0x180018311  js      loc_18001867C
0x180018317  mov     rcx, rbp
0x18001831a  call    AslStringUpper
0x18001831f  mov     r8, [rsp+68h+SubStr]
0x180018327  xor     r10d, r10d
0x18001832a  mov     rax, r12
0x18001832d  mov     rdx, rbx
0x180018330  lea     r9d, [r10+1]
0x180018334  test    rax, rax
0x180018337  jz      short loc_180018355
0x180018339  movzx   ecx, word ptr [rsi]
0x18001833c  test    cx, cx
0x18001833f  jz      short loc_180018355
0x180018341  mov     [r8], cx
0x180018345  add     rsi, 2
0x180018349  add     r8, 2
0x18001834d  sub     rax, r9
0x180018350  sub     rdx, r9
0x180018353  jnz     short loc_180018334
0x180018355  mov     rax, rdx
0x180018358  lea     rcx, [r8-2]
0x18001835c  neg     rax
0x18001835f  sbb     edi, edi
0x180018361  test    rdx, rdx
0x180018364  not     edi
0x180018366  cmovnz  rcx, r8
0x18001836a  mov     [rcx], r10w
0x18001836e  and     edi, 80000005h
0x180018374  js      loc_18001867C
0x18001837a  mov     rax, [rsp+68h+SubStr]
0x180018382  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180018386  inc     rsi
0x180018389  cmp     [rax+rsi*2], r10w
0x18001838e  jnz     short loc_180018386
0x180018390  test    rsi, rsi
0x180018393  jnz     short loc_1800183AA
0x180018395  mov     edi, [rsp+68h+arg_8]
0x180018399  mov     rsi, [rsp+68h+var_48]
0x18001839e  add     edi, r9d
0x1800183a1  mov     [rsp+68h+arg_8], edi
0x1800183a5  jmp     loc_180018489
0x1800183aa  mov     rcx, rax
0x1800183ad  call    AslStringUpper
0x1800183b2  mov     rdx, [rsp+68h+SubStr]; SubStr
0x1800183ba  mov     rcx, rbp; Str
0x1800183bd  call    wcsstr_0
0x1800183c2  xor     r10d, r10d
0x1800183c5  mov     rcx, rax
0x1800183c8  test    rax, rax
0x1800183cb  jnz     short loc_1800183D3
0x1800183cd  lea     r9d, [rax+1]
0x1800183d1  jmp     short loc_180018395
0x1800183d3  sub     rcx, rbp
0x1800183d6  sar     rcx, 1
0x1800183d9  lea     rax, [rsi+rcx]
0x1800183dd  mov     [r14+rcx*2], r10w
0x1800183e2  mov     rsi, [rsp+68h+var_48]
0x1800183e7  lea     r9, [r14+rax*2]
0x1800183eb  lea     rax, [rsi+r14]
0x1800183ef  cmp     r9, rax
0x1800183f2  jnb     loc_18001867C
0x1800183f8  mov     rax, r12
0x1800183fb  mov     rdx, rbx
0x1800183fe  mov     r8, rbp
0x180018401  test    rax, rax
0x180018404  jz      short loc_180018428
0x180018406  movzx   ecx, word ptr [r9]
0x18001840a  test    cx, cx
0x18001840d  jz      short loc_180018428
0x18001840f  mov     [r8], cx
0x180018413  add     r9, 2
0x180018417  mov     ecx, 1
0x18001841c  add     r8, 2
0x180018420  sub     rax, rcx
0x180018423  sub     rdx, rcx
0x180018426  jnz     short loc_180018401
0x180018428  mov     rax, rdx
0x18001842b  lea     rcx, [r8-2]
0x18001842f  neg     rax
0x180018432  sbb     edi, edi
0x180018434  test    rdx, rdx
0x180018437  not     edi
0x180018439  cmovnz  rcx, r8
0x18001843d  mov     [rcx], r10w
0x180018441  and     edi, 80000005h
0x180018447  js      loc_18001867C
0x18001844d  lea     r8, [r13+2]; unsigned __int16 *
0x180018451  mov     rdx, rbx; unsigned __int64
0x180018454  mov     rcx, r14; unsigned __int16 *
0x180018457  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001845c  mov     edi, eax
0x18001845e  test    eax, eax
0x180018460  js      loc_18001867C
0x180018466  mov     r8, rbp; unsigned __int16 *
0x180018469  mov     rdx, rbx; unsigned __int64
0x18001846c  mov     rcx, r14; unsigned __int16 *
0x18001846f  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180018474  xor     r10d, r10d
0x180018477  mov     edi, eax
0x180018479  test    eax, eax
0x18001847b  js      loc_18001867C
0x180018481  mov     edi, [rsp+68h+arg_8]
0x180018485  lea     r9d, [r10+1]
0x180018489  mov     r8, [r15+40h]
0x18001848d  mov     rdx, [r15+10h]
0x180018491  mov     eax, edi
0x180018493  lea     rcx, [rdx+r8]
0x180018497  cmp     rax, rcx
0x18001849a  jb      loc_180018215
0x1800184a0  mov     rax, r14
0x1800184a3  mov     rdx, rbp
0x1800184a6  test    r12, r12
0x1800184a9  jz      short loc_1800184C6
0x1800184ab  movzx   ecx, word ptr [rax]
0x1800184ae  test    cx, cx
0x1800184b1  jz      short loc_1800184C6
0x1800184b3  mov     [rdx], cx
0x1800184b6  add     rax, 2
0x1800184ba  add     rdx, 2
0x1800184be  sub     r12, r9
0x1800184c1  sub     rbx, r9
0x1800184c4  jnz     short loc_1800184A6
0x1800184c6  mov     rax, rbx
0x1800184c9  lea     rcx, [rdx-2]
0x1800184cd  neg     rax
0x1800184d0  sbb     edi, edi
0x1800184d2  not     edi
0x1800184d4  and     edi, 80000005h
0x1800184da  test    rbx, rbx
0x1800184dd  cmovnz  rcx, rdx
0x1800184e1  mov     [rcx], r10w
0x1800184e5  jz      loc_18001867C
0x1800184eb  mov     rcx, rbp
0x1800184ee  call    AslStringUpper
0x1800184f3  lea     rdx, aUsers; "\\USERS\\"
0x1800184fa  mov     rcx, rbp; Str
0x1800184fd  call    wcsstr_0
0x180018502  xor     r13d, r13d
0x180018505  jmp     short loc_180018550
0x180018507  lea     rcx, [rax+0Eh]
0x18001850b  movzx   edx, word ptr [rcx]
0x18001850e  test    dx, dx
0x180018511  jz      short loc_180018544
0x180018513  mov     rax, rcx
0x180018516  sub     rax, rbp
  ... truncated ...
```
