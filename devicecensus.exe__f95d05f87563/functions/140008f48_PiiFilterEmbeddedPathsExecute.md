# PiiFilterEmbeddedPathsExecute

- ea: `0x140008f48`
- end: `0x1400094fb`
- name: `PiiFilterEmbeddedPathsExecute`
- size: `1459`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int64 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140006460`

## callees

- `0x140004998`
- `0x140008ed0`
- `0x140008f48`
- `0x140009bbc`

## import_xrefs

- `msvcrt!wcsstr` at `0x1400091f5`
- `msvcrt!wcsstr` at `0x140009336`
- `msvcrt!wcsstr` at `0x140009388`
- `msvcrt!wcsstr` at `0x1400091f5`
- `msvcrt!wcsstr` at `0x140009336`
- `msvcrt!wcsstr` at `0x140009388`
- `msvcrt!wcschr` at `0x140009495`
- `msvcrt!wcschr` at `0x140009495`
- `msvcrt!iswspace` at `0x1400093f1`
- `msvcrt!iswspace` at `0x140009456`
- `msvcrt!iswspace` at `0x1400093f1`
- `msvcrt!iswspace` at `0x140009456`
- `ntdll!RtlFreeHeap` at `0x1400094c1`
- `ntdll!RtlFreeHeap` at `0x1400094de`
- `ntdll!RtlFreeHeap` at `0x1400094c1`
- `ntdll!RtlFreeHeap` at `0x1400094de`
- `ntdll!RtlAllocateHeap` at `0x140008f86`
- `ntdll!RtlAllocateHeap` at `0x140008fb5`
- `ntdll!RtlAllocateHeap` at `0x140008f86`
- `ntdll!RtlAllocateHeap` at `0x140008fb5`

## pseudocode

```c
__int64 __fastcall PiiFilterEmbeddedPathsExecute(
        unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        unsigned __int16 *a4)
{
  signed int v7; // edi
  wchar_t *Heap; // rbp
  __int64 v9; // r12
  __int64 v10; // rsi
  __int64 v11; // rax
  __int64 v12; // rdx
  unsigned __int16 *v13; // r8
  unsigned __int16 *v14; // rcx
  _QWORD *v15; // r8
  unsigned __int64 v16; // rdx
  unsigned __int64 v17; // rdi
  wchar_t **v18; // rax
  wchar_t *v19; // rbx
  __int64 *v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rax
  unsigned __int64 v23; // rdi
  wchar_t **v24; // rax
  __int64 *v25; // rax
  __int64 v26; // r13
  unsigned __int16 *v27; // rdi
  __int64 v28; // rcx
  wchar_t *v29; // rax
  __int64 v30; // rdx
  wchar_t *v31; // rcx
  __int64 v32; // r8
  wchar_t *v33; // rax
  __int64 v34; // rcx
  __int64 v35; // rdx
  wchar_t *v36; // rcx
  __int64 v37; // rbx
  wchar_t *v38; // rax
  __int64 v39; // rcx
  unsigned __int16 *v40; // r8
  __int64 v41; // rcx
  __int64 v42; // rdx
  wchar_t *v43; // rax
  wchar_t *v44; // rcx
  unsigned __int16 *v45; // rax
  wchar_t *v46; // rdx
  wchar_t *v47; // rcx
  wchar_t *i; // rax
  const wchar_t *v49; // rcx
  wchar_t v50; // dx
  unsigned __int16 *v51; // rdi
  const wchar_t *j; // rcx
  wint_t *v53; // rdi
  wint_t *v54; // rbx
  int v55; // esi
  unsigned __int16 v56; // ax
  BOOL v57; // eax
  char *v58; // rdi
  unsigned __int64 v59; // rcx
  wchar_t *v60; // rax
  __int64 v62; // [rsp+78h] [rbp+10h] BYREF
  wchar_t *SubStr; // [rsp+80h] [rbp+18h]

  v62 = a2;
  SubStr = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x800u);
  if ( !SubStr )
    return (unsigned int)-1073741801;
  Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x800u);
  if ( Heap )
  {
    v9 = 2147483646;
    v10 = 1024;
    v11 = 2147483646;
    v12 = 1024;
    v13 = a1;
    do
    {
      if ( !v11 )
        break;
      if ( !*a4 )
        break;
      *v13++ = *a4++;
      --v11;
      --v12;
    }
    while ( v12 );
    v14 = v13 - 1;
    v7 = v12 == 0 ? 0x80000005 : 0;
    if ( v12 )
      v14 = v13;
    *v14 = 0;
    if ( !v12 )
      goto LABEL_112;
    v15 = (_QWORD *)a3[8];
    v16 = a3[2];
    if ( !(_QWORD *)((char *)v15 + v16) )
    {
LABEL_67:
      v45 = a1;
      v46 = Heap;
      do
      {
        if ( !v9 )
          break;
        if ( !*v45 )
          break;
        *v46++ = *v45++;
        --v9;
        --v10;
      }
      while ( v10 );
      v47 = v46 - 1;
      v7 = v10 == 0 ? 0x80000005 : 0;
      if ( v10 )
        v47 = v46;
      *v47 = 0;
      if ( v10 )
      {
        AslStringUpper(Heap, v46, v15, 0);
        for ( i = wcsstr(Heap, L"\\USERS\\"); i; i = wcsstr(v49, L"\\USERS\\") )
        {
          v49 = i + 7;
          v50 = i[7];
          if ( v50 )
          {
            v51 = &a1[v49 - Heap];
            do
            {
              if ( v50 == 92 )
                break;
              if ( v51 >= a1 + 1024 )
                break;
              ++v49;
              *v51++ = 120;
              v50 = *v49;
            }
            while ( *v49 );
          }
        }
        for ( j = a1; ; j = v54 )
        {
          v60 = wcschr(j, 0x40u);
          if ( !v60 || !*v60 )
            break;
          v53 = v60 - 1;
          LODWORD(v62) = 0;
          v54 = v60 + 1;
          v55 = 0;
          v56 = v60[1];
          if ( v56 )
          {
            do
            {
              if ( (unsigned int)PiipIsInvalidEmailCharacter(v56, 0, (int *)&v62) )
                break;
              if ( *v54 == 46 )
                v55 = 1;
              v56 = *++v54;
            }
            while ( *v54 );
          }
          v57 = iswspace(*v54) || !*v54 || *v54 == 62;
          if ( v55 && v57 )
          {
            --v54;
            LODWORD(v62) = 0;
            while ( v53 >= a1 )
            {
              if ( (unsigned int)PiipIsInvalidEmailCharacter(*v53, 1, (int *)&v62) )
              {
                if ( *v53 != 60 && !iswspace(*v53) )
                  goto LABEL_109;
                break;
              }
              --v53;
            }
            if ( !(_DWORD)v62 )
            {
              v58 = (char *)(v53 + 1);
              v59 = (unsigned __int64)((char *)v54 - v58 + 2) >> 1;
              if ( v58 > (char *)v54 )
                v59 = 0;
              if ( v59 )
              {
                while ( v59 )
                {
                  *(_WORD *)v58 = 35;
                  v58 += 2;
                  --v59;
                }
              }
            }
          }
LABEL_109:
          ;
        }
        v7 = 0;
      }
      goto LABEL_112;
    }
    v17 = 0;
    LODWORD(v62) = 0;
    while ( v17 < v16 )
    {
      v15 = a3 + 5;
      if ( !is_mul_ok(a3[1], v17) || (v18 = (wchar_t **)(*v15 + a3[1] * v17), (unsigned __int64)v18 < *v15) )
        v18 = 0;
      v19 = *v18;
      if ( !is_mul_ok(a3[1], v17) || (v20 = (__int64 *)(*v15 + a3[1] * v17), (unsigned __int64)v20 < *v15) )
        v20 = 0;
      v21 = *v20;
      v22 = -1;
      do
        ++v22;
      while ( *(_WORD *)(v21 + 2 * v22) );
LABEL_36:
      v26 = v21 + 2 * v22;
      v27 = a1;
      v28 = 2147483646;
      v29 = Heap;
      v30 = 1024;
      do
      {
        if ( !v28 )
          break;
        v15 = (_QWORD *)*v27;
        if ( !(_WORD)v15 )
          break;
        *v29 = (unsigned __int16)v15;
        ++v27;
        ++v29;
        --v28;
        --v30;
      }
      while ( v30 );
      v31 = v29 - 1;
      if ( v30 )
        v31 = v29;
      *v31 = 0;
      v7 = v30 == 0 ? 0x80000005 : 0;
      if ( !v30 )
        goto LABEL_112;
      AslStringUpper(Heap, v30, v15, 0);
      v33 = SubStr;
      v34 = 2147483646;
      v35 = 1024;
      do
      {
        if ( !v34 )
          break;
        if ( !*v19 )
          break;
        *v33++ = *v19++;
        --v34;
        --v35;
      }
      while ( v35 );
      v36 = v33 - 1;
      if ( v35 )
        v36 = v33;
      *v36 = 0;
      v7 = v35 == 0 ? 0x80000005 : 0;
      if ( !v35 )
        goto LABEL_112;
      v37 = -1;
      do
        ++v37;
      while ( SubStr[v37] );
      if ( v37 && (AslStringUpper(SubStr, v35, v32, 0), (v38 = wcsstr(Heap, SubStr)) != 0) )
      {
        v39 = v38 - Heap;
        a1[v39] = 0;
        v40 = &a1[v37 + v39];
        if ( v40 >= a1 + 1024 )
          goto LABEL_112;
        v41 = 2147483646;
        v42 = 1024;
        v43 = Heap;
        do
        {
          if ( !v41 )
            break;
          if ( !*v40 )
            break;
          *v43++ = *v40++;
          --v41;
          --v42;
        }
        while ( v42 );
        v44 = v43 - 1;
        if ( v42 )
          v44 = v43;
        *v44 = 0;
        v7 = v42 == 0 ? 0x80000005 : 0;
        if ( !v42 )
          goto LABEL_112;
        v7 = RtlStringCchCatW(a1, 1024, (unsigned __int16 *)(v26 + 2));
        if ( v7 < 0 )
          goto LABEL_112;
        v7 = RtlStringCchCatW(a1, 1024, Heap);
        if ( v7 < 0 )
          goto LABEL_112;
        v17 = (unsigned int)v62;
      }
      else
      {
        v17 = (unsigned int)(v62 + 1);
        LODWORD(v62) = v62 + 1;
      }
      v15 = (_QWORD *)a3[8];
      v16 = a3[2];
      if ( (unsigned int)v17 >= (unsigned __int64)v15 + v16 )
        goto LABEL_67;
    }
    v23 = v17 - v16;
    if ( v23 >= (unsigned __int64)v15 )
    {
      v19 = (wchar_t *)MEMORY[0];
    }
    else
    {
      if ( is_mul_ok(a3[7], v23) && (v24 = (wchar_t **)(a3[11] + a3[7] * v23), (unsigned __int64)v24 >= a3[11]) )
        v19 = *v24;
      else
        v19 = (wchar_t *)MEMORY[0];
      if ( is_mul_ok(a3[7], v23) )
      {
        v25 = (__int64 *)(a3[11] + a3[7] * v23);
        if ( (unsigned __int64)v25 >= a3[11] )
          goto LABEL_34;
      }
    }
    v25 = 0;
LABEL_34:
    v21 = *v25;
    v22 = -1;
    do
      ++v22;
    while ( *(_WORD *)(v21 + 2 * v22) );
    goto LABEL_36;
  }
  v7 = -1073741801;
LABEL_112:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, SubStr);
  if ( Heap )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140008f48  mov     [rsp+arg_0], rbx
0x140008f4d  mov     [rsp+arg_8], rdx
0x140008f52  push    rbp
0x140008f53  push    rsi
0x140008f54  push    rdi
0x140008f55  push    r12
0x140008f57  push    r13
0x140008f59  push    r14
0x140008f5b  push    r15
0x140008f5d  sub     rsp, 30h
0x140008f61  mov     r15, rcx
0x140008f64  mov     r14, r8
0x140008f67  mov     rcx, gs:60h
0x140008f70  mov     ebx, 800h
0x140008f75  mov     esi, 8
0x140008f7a  mov     r8d, ebx; Size
0x140008f7d  mov     edx, esi; Flags
0x140008f7f  mov     rdi, r9
0x140008f82  mov     rcx, [rcx+30h]; HeapHandle
0x140008f86  call    cs:__imp_RtlAllocateHeap
0x140008f8c  mov     [rsp+68h+SubStr], rax
0x140008f94  test    rax, rax
0x140008f97  jnz     short loc_140008FA3
0x140008f99  mov     edi, 0C0000017h
0x140008f9e  jmp     loc_1400094E4
0x140008fa3  mov     rcx, gs:60h
0x140008fac  mov     r8, rbx; Size
0x140008faf  mov     edx, esi; Flags
0x140008fb1  mov     rcx, [rcx+30h]; HeapHandle
0x140008fb5  call    cs:__imp_RtlAllocateHeap
0x140008fbb  xor     r9d, r9d
0x140008fbe  mov     rbp, rax
0x140008fc1  test    rax, rax
0x140008fc4  jnz     short loc_140008FD0
0x140008fc6  mov     edi, 0C0000017h
0x140008fcb  jmp     loc_1400094AA
0x140008fd0  mov     r12d, 7FFFFFFEh
0x140008fd6  mov     esi, 400h
0x140008fdb  mov     eax, r12d
0x140008fde  mov     edx, esi
0x140008fe0  mov     r8, r15
0x140008fe3  mov     r10d, 1
0x140008fe9  test    rax, rax
0x140008fec  jz      short loc_14000900A
0x140008fee  movzx   ecx, word ptr [rdi]
0x140008ff1  test    cx, cx
0x140008ff4  jz      short loc_14000900A
0x140008ff6  mov     [r8], cx
0x140008ffa  add     rdi, 2
0x140008ffe  add     r8, 2
0x140009002  sub     rax, r10
0x140009005  sub     rdx, r10
0x140009008  jnz     short loc_140008FE9
0x14000900a  mov     rax, rdx
0x14000900d  lea     rcx, [r8-2]
0x140009011  neg     rax
0x140009014  sbb     edi, edi
0x140009016  not     edi
0x140009018  and     edi, 80000005h
0x14000901e  test    rdx, rdx
0x140009021  cmovnz  rcx, r8
0x140009025  mov     [rcx], r9w
0x140009029  jz      loc_1400094AA
0x14000902f  mov     r8, [r14+40h]
0x140009033  mov     rdx, [r14+10h]
0x140009037  lea     rax, [rdx+r8]
0x14000903b  test    rax, rax
0x14000903e  jz      loc_1400092D9
0x140009044  mov     edi, r9d
0x140009047  mov     dword ptr [rsp+68h+arg_8], edi
0x14000904b  cmp     rdi, rdx
0x14000904e  jnb     short loc_140009098
0x140009050  mov     rax, rdi
0x140009053  lea     r8, [r14+28h]
0x140009057  mul     qword ptr [r14+8]
0x14000905b  test    rdx, rdx
0x14000905e  jnz     short loc_140009068
0x140009060  add     rax, [r8]
0x140009063  cmp     rax, [r8]
0x140009066  jnb     short loc_14000906B
0x140009068  mov     rax, r9
0x14000906b  mov     rbx, [rax]
0x14000906e  mov     rax, rdi
0x140009071  mul     qword ptr [r14+8]
0x140009075  test    rdx, rdx
0x140009078  jnz     short loc_140009082
0x14000907a  add     rax, [r8]
0x14000907d  cmp     rax, [r8]
0x140009080  jnb     short loc_140009085
0x140009082  mov     rax, r9
0x140009085  mov     rcx, [rax]
0x140009088  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000908c  inc     rax
0x14000908f  cmp     [rcx+rax*2], r9w
0x140009094  jnz     short loc_14000908C
0x140009096  jmp     short loc_1400090F7
0x140009098  sub     rdi, rdx
0x14000909b  cmp     rdi, r8
0x14000909e  jnb     short loc_1400090DB
0x1400090a0  mov     rax, rdi
0x1400090a3  mul     qword ptr [r14+38h]
0x1400090a7  test    rdx, rdx
0x1400090aa  jnz     short loc_1400090BB
0x1400090ac  add     rax, [r14+58h]
0x1400090b0  cmp     rax, [r14+58h]
0x1400090b4  jb      short loc_1400090BB
0x1400090b6  mov     rbx, [rax]
0x1400090b9  jmp     short loc_1400090C3
0x1400090bb  mov     rbx, ds:0
0x1400090c3  mov     rax, rdi
0x1400090c6  mul     qword ptr [r14+38h]
0x1400090ca  test    rdx, rdx
0x1400090cd  jnz     short loc_1400090E3
0x1400090cf  add     rax, [r14+58h]
0x1400090d3  cmp     rax, [r14+58h]
0x1400090d7  jnb     short loc_1400090E6
0x1400090d9  jmp     short loc_1400090E3
0x1400090db  mov     rbx, ds:0
0x1400090e3  mov     rax, r9
0x1400090e6  mov     rcx, [rax]
0x1400090e9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400090ed  inc     rax
0x1400090f0  cmp     [rcx+rax*2], r9w
0x1400090f5  jnz     short loc_1400090ED
0x1400090f7  lea     r13, [rcx+rax*2]
0x1400090fb  mov     rdi, r15
0x1400090fe  mov     rcx, r12
0x140009101  mov     rax, rbp
0x140009104  mov     rdx, rsi
0x140009107  test    rcx, rcx
0x14000910a  jz      short loc_14000912A
0x14000910c  movzx   r8d, word ptr [rdi]
0x140009110  test    r8w, r8w
0x140009114  jz      short loc_14000912A
0x140009116  mov     [rax], r8w
0x14000911a  add     rdi, 2
0x14000911e  add     rax, 2
0x140009122  sub     rcx, r10
0x140009125  sub     rdx, r10
0x140009128  jnz     short loc_140009107
0x14000912a  test    rdx, rdx
0x14000912d  lea     rcx, [rax-2]
0x140009131  cmovnz  rcx, rax
0x140009135  mov     rax, rdx
0x140009138  neg     rax
0x14000913b  sbb     edi, edi
0x14000913d  not     edi
0x14000913f  mov     [rcx], r9w
0x140009143  and     edi, 80000005h
0x140009149  test    rdx, rdx
0x14000914c  jz      loc_1400094AA
0x140009152  mov     rcx, rbp
0x140009155  call    AslStringUpper
0x14000915a  mov     rax, [rsp+68h+SubStr]
0x140009162  xor     r9d, r9d
0x140009165  mov     rcx, r12
0x140009168  mov     rdx, rsi
0x14000916b  lea     r10d, [r9+1]
0x14000916f  test    rcx, rcx
0x140009172  jz      short loc_14000918F
0x140009174  movzx   edi, word ptr [rbx]
0x140009177  test    di, di
0x14000917a  jz      short loc_14000918F
0x14000917c  mov     [rax], di
0x14000917f  add     rbx, 2
0x140009183  add     rax, 2
0x140009187  sub     rcx, r10
0x14000918a  sub     rdx, r10
0x14000918d  jnz     short loc_14000916F
0x14000918f  test    rdx, rdx
0x140009192  lea     rcx, [rax-2]
0x140009196  cmovnz  rcx, rax
0x14000919a  mov     rax, rdx
0x14000919d  neg     rax
0x1400091a0  sbb     edi, edi
0x1400091a2  not     edi
0x1400091a4  mov     [rcx], r9w
0x1400091a8  and     edi, 80000005h
0x1400091ae  test    rdx, rdx
0x1400091b1  jz      loc_1400094AA
0x1400091b7  mov     rax, [rsp+68h+SubStr]
0x1400091bf  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400091c3  inc     rbx
0x1400091c6  cmp     [rax+rbx*2], r9w
0x1400091cb  jnz     short loc_1400091C3
0x1400091cd  test    rbx, rbx
0x1400091d0  jnz     short loc_1400091E2
0x1400091d2  mov     edi, dword ptr [rsp+68h+arg_8]
0x1400091d6  add     edi, r10d
0x1400091d9  mov     dword ptr [rsp+68h+arg_8], edi
0x1400091dd  jmp     loc_1400092C2
0x1400091e2  mov     rcx, rax
0x1400091e5  call    AslStringUpper
0x1400091ea  mov     rdx, [rsp+68h+SubStr]; SubStr
0x1400091f2  mov     rcx, rbp; Str
0x1400091f5  call    cs:__imp_wcsstr
0x1400091fb  xor     r9d, r9d
0x1400091fe  mov     rcx, rax
0x140009201  test    rax, rax
0x140009204  jnz     short loc_14000920C
0x140009206  lea     r10d, [rax+1]
0x14000920a  jmp     short loc_1400091D2
0x14000920c  sub     rcx, rbp
0x14000920f  sar     rcx, 1
0x140009212  lea     rax, [rbx+rcx]
0x140009216  mov     [r15+rcx*2], r9w
0x14000921b  lea     r8, [r15+rax*2]
0x14000921f  lea     rax, [r15+800h]
0x140009226  cmp     r8, rax
0x140009229  jnb     loc_1400094AA
0x14000922f  mov     rcx, r12
0x140009232  mov     rdx, rsi
0x140009235  mov     rax, rbp
0x140009238  test    rcx, rcx
0x14000923b  jz      short loc_14000925E
0x14000923d  movzx   edi, word ptr [r8]
0x140009241  test    di, di
0x140009244  jz      short loc_14000925E
0x140009246  mov     [rax], di
0x140009249  add     r8, 2
0x14000924d  mov     edi, 1
0x140009252  add     rax, 2
0x140009256  sub     rcx, rdi
0x140009259  sub     rdx, rdi
0x14000925c  jnz     short loc_140009238
0x14000925e  test    rdx, rdx
0x140009261  lea     rcx, [rax-2]
0x140009265  cmovnz  rcx, rax
0x140009269  mov     rax, rdx
0x14000926c  neg     rax
0x14000926f  sbb     edi, edi
0x140009271  not     edi
0x140009273  mov     [rcx], r9w
0x140009277  and     edi, 80000005h
0x14000927d  test    rdx, rdx
0x140009280  jz      loc_1400094AA
0x140009286  lea     r8, [r13+2]; unsigned __int16 *
0x14000928a  mov     rdx, rsi; unsigned __int64
0x14000928d  mov     rcx, r15; unsigned __int16 *
0x140009290  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140009295  mov     edi, eax
0x140009297  test    eax, eax
0x140009299  js      loc_1400094AA
0x14000929f  mov     r8, rbp; unsigned __int16 *
0x1400092a2  mov     rdx, rsi; unsigned __int64
0x1400092a5  mov     rcx, r15; unsigned __int16 *
0x1400092a8  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400092ad  xor     r9d, r9d
0x1400092b0  mov     edi, eax
0x1400092b2  test    eax, eax
0x1400092b4  js      loc_1400094AA
0x1400092ba  mov     edi, dword ptr [rsp+68h+arg_8]
0x1400092be  lea     r10d, [r9+1]
0x1400092c2  mov     r8, [r14+40h]
0x1400092c6  mov     rdx, [r14+10h]
0x1400092ca  mov     eax, edi
0x1400092cc  lea     rcx, [rdx+r8]
0x1400092d0  cmp     rax, rcx
0x1400092d3  jb      loc_14000904B
0x1400092d9  mov     rax, r15
0x1400092dc  mov     rdx, rbp
0x1400092df  test    r12, r12
0x1400092e2  jz      short loc_1400092FF
0x1400092e4  movzx   ecx, word ptr [rax]
0x1400092e7  test    cx, cx
0x1400092ea  jz      short loc_1400092FF
0x1400092ec  mov     [rdx], cx
0x1400092ef  add     rax, 2
0x1400092f3  add     rdx, 2
0x1400092f7  sub     r12, r10
0x1400092fa  sub     rsi, r10
0x1400092fd  jnz     short loc_1400092DF
0x1400092ff  mov     rax, rsi
0x140009302  lea     rcx, [rdx-2]
0x140009306  neg     rax
0x140009309  sbb     edi, edi
0x14000930b  not     edi
0x14000930d  and     edi, 80000005h
0x140009313  test    rsi, rsi
0x140009316  cmovnz  rcx, rdx
0x14000931a  mov     [rcx], r9w
0x14000931e  jz      loc_1400094AA
0x140009324  mov     rcx, rbp
0x140009327  call    AslStringUpper
0x14000932c  lea     rdx, aUsers; "\\USERS\\"
0x140009333  mov     rcx, rbp; Str
0x140009336  call    cs:__imp_wcsstr
0x14000933c  xor     r13d, r13d
0x14000933f  jmp     short loc_14000938E
0x140009341  lea     rcx, [rax+0Eh]
0x140009345  movzx   edx, word ptr [rcx]
0x140009348  test    dx, dx
0x14000934b  jz      short loc_140009381
0x14000934d  mov     rax, rcx
0x140009350  sub     rax, rbp
0x140009353  sar     rax, 1
0x140009356  lea     rdi, [r15+rax*2]
0x14000935a  cmp     dx, 5Ch ; '\'
0x14000935e  jz      short loc_140009381
0x140009360  lea     rax, [r15+800h]
  ... truncated ...
```
