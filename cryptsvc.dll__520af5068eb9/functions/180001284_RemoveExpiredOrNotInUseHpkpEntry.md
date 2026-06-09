# _RemoveExpiredOrNotInUseHpkpEntry

- ea: `0x180001284`
- end: `0x18000159b`
- name: `_RemoveExpiredOrNotInUseHpkpEntry`
- size: `791`
- prototype: `__int64 __fastcall(_QWORD *Base, unsigned int *, void *, unsigned int *, FILETIME *lpFileTime2)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001868`

## callees

- `0x180001284`
- `0x18000ec04`
- `0x18000ec28`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000131c`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180001339`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180001384`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000131c`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180001339`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180001384`

## pseudocode

```c
__int64 __fastcall RemoveExpiredOrNotInUseHpkpEntry(
        _QWORD *Base,
        unsigned int *a2,
        void *a3,
        unsigned int *a4,
        FILETIME *lpFileTime2)
{
  __int64 v5; // rsi
  unsigned int v6; // edi
  __int64 v7; // rbp
  _QWORD *v8; // r12
  void *v9; // rbx
  int v10; // edx
  __int64 v11; // r15
  __int64 i; // r14
  __int64 v13; // rax
  const FILETIME *v14; // rcx
  FILETIME *v15; // rbx
  unsigned int v16; // r13d
  unsigned int v17; // r15d
  size_t v18; // r13
  __int64 v19; // rbx
  int v20; // eax
  __int64 v21; // r12
  __int64 v22; // rbp
  __int64 v23; // r14
  void *v24; // rax
  unsigned int v25; // ecx
  unsigned int v26; // r13d
  __int64 v27; // rdx
  __int64 v28; // rax
  int v30; // [rsp+30h] [rbp-88h]
  unsigned int v31; // [rsp+30h] [rbp-88h]
  unsigned int v32; // [rsp+34h] [rbp-84h]
  unsigned int v33; // [rsp+34h] [rbp-84h]
  unsigned int v34; // [rsp+38h] [rbp-80h]
  _DWORD NumOfElements[3]; // [rsp+3Ch] [rbp-7Ch] BYREF
  __int64 v36; // [rsp+48h] [rbp-70h]
  size_t v37; // [rsp+50h] [rbp-68h]
  _QWORD Key[12]; // [rsp+58h] [rbp-60h] BYREF

  v5 = 0;
  v6 = 0;
  v32 = *a2;
  v7 = 0;
  v34 = 0;
  v8 = Base;
  NumOfElements[0] = *a4;
  v9 = a3;
  if ( !*a2 )
    goto LABEL_21;
  do
  {
    v10 = 1;
    v11 = v8[v7] + 16LL;
    v30 = 1;
    for ( i = 0; i != 3; ++i )
    {
      v13 = 48 * i;
      v14 = (const FILETIME *)(v11 + 48 * i + 8);
      if ( v14->dwLowDateTime || v14->dwHighDateTime )
      {
        v15 = (FILETIME *)(v13 + v11);
        if ( *(_DWORD *)(v13 + v11 + 20) > (unsigned int)dword_180020344 )
        {
          v15[2].dwHighDateTime = dword_180020344;
          v6 = 1;
        }
        if ( CompareFileTime(v14, lpFileTime2) > 0 )
        {
          v15[1] = *lpFileTime2;
          v6 = 1;
          if ( CompareFileTime(v15, lpFileTime2) > 0 )
            *v15 = *lpFileTime2;
LABEL_10:
          v10 = 0;
          v30 = 0;
          continue;
        }
        *(_QWORD *)&NumOfElements[1] = *(_QWORD *)&v15[1] + 10000000LL * v15[2].dwHighDateTime;
        if ( CompareFileTime(lpFileTime2, (const FILETIME *)&NumOfElements[1]) <= 0 )
          goto LABEL_10;
        v10 = v30;
        v6 = 1;
        v15[1] = 0;
      }
    }
    if ( v10 )
    {
      v6 = 1;
    }
    else
    {
      v8[v5] = v8[v7];
      v5 = (unsigned int)(v5 + 1);
    }
    v7 = (unsigned int)(v7 + 1);
  }
  while ( (unsigned int)v7 < v32 );
  if ( dword_18002034C < (unsigned int)v5 )
  {
    qsort(v8, (unsigned int)v5, 8u, (_CoreCrtNonSecureSearchSortCompareFunction)CompareDomainEntryLastAdd);
    LODWORD(v5) = dword_18002034C;
    v6 = 1;
  }
  v9 = a3;
LABEL_21:
  qsort(v8, (unsigned int)v5, 8u, (_CoreCrtNonSecureSearchSortCompareFunction)CompareDomainEntrySubjectIdentifier);
  v37 = NumOfElements[0];
  qsort(v9, NumOfElements[0], 8u, SortCompareHeaderEntry);
  v31 = 0;
  v16 = 0;
  v33 = 0;
  v17 = 0;
  if ( (_DWORD)v5 )
  {
    do
    {
      v18 = v37;
      v19 = 0;
      v36 = v8[v17];
      v20 = 1;
      v21 = v36;
      NumOfElements[1] = 1;
      do
      {
        v22 = 48 * v19;
        v23 = v21 + 48 * v19;
        if ( *(_DWORD *)(v23 + 24) || *(_DWORD *)(v23 + 28) )
        {
          Key[0] = 16;
          Key[1] = v22 + v21 + 48;
          v24 = bsearch(Key, a3, v18, 8u, SearchCompareHeaderEntry);
          if ( v24 )
          {
            *(_DWORD *)(*(_QWORD *)v24 + 8LL) = 1;
            v20 = 0;
            NumOfElements[1] = 0;
          }
          else
          {
            v6 = 1;
            *(_DWORD *)(v21 + v22 + 24) = 0;
            v20 = NumOfElements[1];
            *(_DWORD *)(v23 + 28) = 0;
          }
        }
        ++v19;
      }
      while ( v19 != 3 );
      v8 = Base;
      v16 = v31;
      if ( v20 )
      {
        v6 = 1;
      }
      else
      {
        Base[v31] = Base[v33];
        v16 = ++v31;
      }
      v17 = v33 + 1;
      v33 = v17;
    }
    while ( v17 < (unsigned int)v5 );
    v9 = a3;
  }
  v25 = 0;
  if ( NumOfElements[0] )
  {
    v26 = 0;
    do
    {
      v27 = *((_QWORD *)v9 + v25);
      if ( *(_DWORD *)(v27 + 8) )
      {
        v28 = v26++;
        *((_QWORD *)v9 + v28) = v27;
      }
      else
      {
        v6 = 1;
      }
      ++v25;
    }
    while ( v25 < NumOfElements[0] );
    v34 = v26;
    v16 = v31;
  }
  *a2 = v16;
  *a4 = v34;
  return v6;
}

```

## disassembly

```asm
0x180001284  mov     rax, rsp
0x180001287  mov     [rax+20h], r9
0x18000128b  mov     [rax+18h], r8
0x18000128f  mov     [rax+10h], rdx
0x180001293  mov     [rax+8], rcx
0x180001297  push    rbx
0x180001298  push    rbp
0x180001299  push    rsi
0x18000129a  push    rdi
0x18000129b  push    r12
0x18000129d  push    r13
0x18000129f  push    r14
0x1800012a1  push    r15
0x1800012a3  sub     rsp, 78h
0x1800012a7  mov     eax, [rdx]
0x1800012a9  xor     esi, esi
0x1800012ab  xor     edi, edi
0x1800012ad  mov     [rsp+0B8h+var_84], eax
0x1800012b1  xor     ebp, ebp
0x1800012b3  mov     [rsp+0B8h+var_80], esi
0x1800012b7  mov     r12, rcx
0x1800012ba  mov     ecx, [r9]
0x1800012bd  mov     dword ptr [rsp+0B8h+NumOfElements], ecx
0x1800012c1  mov     rbx, r8
0x1800012c4  test    eax, eax
0x1800012c6  jz      loc_1800013E4
0x1800012cc  mov     r13, [rsp+0B8h+lpFileTime2]
0x1800012d4  mov     r15, [r12+rbp*8]
0x1800012d8  mov     edx, 1
0x1800012dd  add     r15, 10h
0x1800012e1  mov     [rsp+0B8h+var_88], edx
0x1800012e5  xor     r14d, r14d
0x1800012e8  lea     rax, [r14+r14*2]
0x1800012ec  shl     rax, 4
0x1800012f0  lea     rcx, [rax+8]
0x1800012f4  add     rcx, r15; lpFileTime1
0x1800012f7  cmp     dword ptr [rcx], 0
0x1800012fa  jnz     short loc_180001302
0x1800012fc  cmp     dword ptr [rcx+4], 0
0x180001300  jz      short loc_180001350
0x180001302  lea     rbx, [rax+r15]
0x180001306  mov     eax, cs:dword_180020344
0x18000130c  cmp     [rbx+14h], eax
0x18000130f  jbe     short loc_180001319
0x180001311  mov     [rbx+14h], eax
0x180001314  mov     edi, 1
0x180001319  mov     rdx, r13; lpFileTime2
0x18000131c  call    cs:__imp_CompareFileTime
0x180001322  test    eax, eax
0x180001324  jle     short loc_180001369
0x180001326  mov     rax, [r13+0]
0x18000132a  mov     rdx, r13; lpFileTime2
0x18000132d  mov     rcx, rbx; lpFileTime1
0x180001330  mov     [rbx+8], rax
0x180001334  mov     edi, 1
0x180001339  call    cs:__imp_CompareFileTime
0x18000133f  test    eax, eax
0x180001341  jle     short loc_18000134A
0x180001343  mov     rax, [r13+0]
0x180001347  mov     [rbx], rax
0x18000134a  xor     edx, edx
0x18000134c  mov     [rsp+0B8h+var_88], edx
0x180001350  inc     r14
0x180001353  cmp     r14, 3
0x180001357  jnz     short loc_1800012E8
0x180001359  test    edx, edx
0x18000135b  jnz     short loc_1800013A1
0x18000135d  mov     rax, [r12+rbp*8]
0x180001361  mov     [r12+rsi*8], rax
0x180001365  inc     esi
0x180001367  jmp     short loc_1800013A6
0x180001369  mov     eax, [rbx+14h]
0x18000136c  lea     rdx, [rsp+0B8h+NumOfElements+4]; lpFileTime2
0x180001371  imul    rcx, rax, 989680h
0x180001378  add     rcx, [rbx+8]
0x18000137c  mov     qword ptr [rsp+0B8h+NumOfElements+4], rcx
0x180001381  mov     rcx, r13; lpFileTime1
0x180001384  call    cs:__imp_CompareFileTime
0x18000138a  test    eax, eax
0x18000138c  jle     short loc_18000134A
0x18000138e  mov     edx, [rsp+0B8h+var_88]
0x180001392  mov     edi, 1
0x180001397  mov     qword ptr [rbx+8], 0
0x18000139f  jmp     short loc_180001350
0x1800013a1  mov     edi, 1
0x1800013a6  inc     ebp
0x1800013a8  cmp     ebp, [rsp+0B8h+var_84]
0x1800013ac  jb      loc_1800012D4
0x1800013b2  cmp     cs:dword_18002034C, esi
0x1800013b8  jnb     short loc_1800013DC
0x1800013ba  mov     edx, esi; NumOfElements
0x1800013bc  lea     r9, _CompareDomainEntryLastAdd; CompareFunction
0x1800013c3  mov     r8d, 8; SizeOfElements
0x1800013c9  mov     rcx, r12; Base
0x1800013cc  call    qsort
0x1800013d1  mov     esi, cs:dword_18002034C
0x1800013d7  mov     edi, 1
0x1800013dc  mov     rbx, [rsp+0B8h+Base]
0x1800013e4  mov     edx, esi; NumOfElements
0x1800013e6  lea     r9, _CompareDomainEntrySubjectIdentifier; CompareFunction
0x1800013ed  mov     r8d, 8; SizeOfElements
0x1800013f3  mov     rcx, r12; Base
0x1800013f6  call    qsort
0x1800013fb  mov     eax, dword ptr [rsp+0B8h+NumOfElements]
0x1800013ff  lea     r9, _SortCompareHeaderEntry; CompareFunction
0x180001406  mov     edx, eax; NumOfElements
0x180001408  mov     [rsp+0B8h+var_68], rax
0x18000140d  mov     r8d, 8; SizeOfElements
0x180001413  mov     rcx, rbx; Base
0x180001416  call    qsort
0x18000141b  xor     r9d, r9d
0x18000141e  mov     [rsp+0B8h+var_88], r9d
0x180001423  mov     r13d, r9d
0x180001426  mov     [rsp+0B8h+var_84], r9d
0x18000142b  mov     r15d, r9d
0x18000142e  test    esi, esi
0x180001430  jz      loc_18000152F
0x180001436  mov     r13, [rsp+0B8h+var_68]
0x18000143b  mov     rbx, r9
0x18000143e  mov     eax, r15d
0x180001441  mov     r15, [rsp+0B8h+Base]
0x180001449  mov     rax, [r12+rax*8]
0x18000144d  mov     [rsp+0B8h+var_70], rax
0x180001452  mov     eax, 1
0x180001457  mov     r12, [rsp+0B8h+var_70]
0x18000145c  mov     dword ptr [rsp+0B8h+NumOfElements+4], eax
0x180001460  lea     rbp, [rbx+rbx*2]
0x180001464  shl     rbp, 4
0x180001468  lea     r14, [r12+rbp]
0x18000146c  cmp     [r12+rbp+18h], r9d
0x180001471  jnz     short loc_180001479
0x180001473  cmp     [r14+1Ch], r9d
0x180001477  jz      short loc_1800014DC
0x180001479  lea     rax, [r12+30h]
0x18000147e  mov     [rsp+0B8h+Key], 10h
0x180001487  add     rax, rbp
0x18000148a  lea     rcx, [rsp+0B8h+Key]; Key
0x18000148f  mov     [rsp+0B8h+var_58], rax
0x180001494  mov     r9d, 8; SizeOfElements
0x18000149a  lea     rax, _SearchCompareHeaderEntry
0x1800014a1  mov     r8, r13; NumOfElements
0x1800014a4  mov     rdx, r15; Base
0x1800014a7  mov     [rsp+0B8h+CompareFunction], rax; CompareFunction
0x1800014ac  call    bsearch
0x1800014b1  xor     r9d, r9d
0x1800014b4  test    rax, rax
0x1800014b7  jnz     short loc_1800014CB
0x1800014b9  lea     edi, [rax+1]
0x1800014bc  mov     [r12+rbp+18h], r9d
0x1800014c1  mov     eax, dword ptr [rsp+0B8h+NumOfElements+4]
0x1800014c5  mov     [r14+1Ch], r9d
0x1800014c9  jmp     short loc_1800014DC
0x1800014cb  mov     rax, [rax]
0x1800014ce  mov     dword ptr [rax+8], 1
0x1800014d5  mov     eax, r9d
0x1800014d8  mov     dword ptr [rsp+0B8h+NumOfElements+4], eax
0x1800014dc  inc     rbx
0x1800014df  cmp     rbx, 3
0x1800014e3  jnz     loc_180001460
0x1800014e9  mov     r15d, [rsp+0B8h+var_84]
0x1800014ee  mov     r12, [rsp+0B8h+arg_0]
0x1800014f6  mov     r13d, [rsp+0B8h+var_88]
0x1800014fb  test    eax, eax
0x1800014fd  jnz     short loc_180001511
0x1800014ff  mov     rax, [r12+r15*8]
0x180001503  mov     [r12+r13*8], rax
0x180001507  inc     r13d
0x18000150a  mov     [rsp+0B8h+var_88], r13d
0x18000150f  jmp     short loc_180001516
0x180001511  mov     edi, 1
0x180001516  inc     r15d
0x180001519  mov     [rsp+0B8h+var_84], r15d
0x18000151e  cmp     r15d, esi
0x180001521  jb      loc_180001436
0x180001527  mov     rbx, [rsp+0B8h+Base]
0x18000152f  mov     r8d, dword ptr [rsp+0B8h+NumOfElements]
0x180001534  mov     ecx, r9d
0x180001537  test    r8d, r8d
0x18000153a  jz      short loc_18000156F
0x18000153c  mov     r13d, [rsp+0B8h+var_80]
0x180001541  mov     eax, ecx
0x180001543  mov     rdx, [rbx+rax*8]
0x180001547  cmp     [rdx+8], r9d
0x18000154b  jz      short loc_180001559
0x18000154d  mov     eax, r13d
0x180001550  inc     r13d
0x180001553  mov     [rbx+rax*8], rdx
0x180001557  jmp     short loc_18000155E
0x180001559  mov     edi, 1
0x18000155e  inc     ecx
0x180001560  cmp     ecx, r8d
0x180001563  jb      short loc_180001541
0x180001565  mov     [rsp+0B8h+var_80], r13d
0x18000156a  mov     r13d, [rsp+0B8h+var_88]
0x18000156f  mov     rax, [rsp+0B8h+arg_8]
0x180001577  mov     rcx, [rsp+0B8h+arg_18]
0x18000157f  mov     [rax], r13d
0x180001582  mov     eax, [rsp+0B8h+var_80]
0x180001586  mov     [rcx], eax
0x180001588  mov     eax, edi
0x18000158a  add     rsp, 78h
0x18000158e  pop     r15
0x180001590  pop     r14
0x180001592  pop     r13
0x180001594  pop     r12
0x180001596  pop     rdi
0x180001597  pop     rsi
0x180001598  pop     rbp
0x180001599  pop     rbx
0x18000159a  retn
```
