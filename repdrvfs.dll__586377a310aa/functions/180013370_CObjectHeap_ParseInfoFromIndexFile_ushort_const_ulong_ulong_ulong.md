# CObjectHeap::ParseInfoFromIndexFile(ushort const *,ulong *,ulong *,ulong *)

- ea: `0x180013370`
- end: `0x18001354f`
- name: `?ParseInfoFromIndexFile@CObjectHeap@@IEAAJPEBGPEAK11@Z`
- size: `479`
- prototype: `int(CObjectHeap *__hidden this, const unsigned __int16 *, unsigned int *, unsigned int *, unsigned int *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180013048`
- `0x1800203a0`
- `0x180030a90`

## callees

- `0x1800012b8`
- `0x180013370`

## import_xrefs

- `msvcrt!wcschr` at `0x180013388`
- `msvcrt!wcschr` at `0x180013388`
- `wbemcomn!GetMemLogObject` at `0x1800133f8`
- `wbemcomn!GetMemLogObject` at `0x1800134d3`
- `wbemcomn!GetMemLogObject` at `0x1800133f8`
- `wbemcomn!GetMemLogObject` at `0x1800134d3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180013406`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800134e1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180013406`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800134e1`

## pseudocode

```c
__int64 __fastcall CObjectHeap::ParseInfoFromIndexFile(
        CObjectHeap *this,
        const unsigned __int16 *a2,
        unsigned int *a3,
        unsigned int *a4,
        unsigned int *a5)
{
  wchar_t *v7; // rax
  unsigned __int16 *v8; // rax
  unsigned __int16 v9; // cx
  int v10; // edx
  unsigned __int16 *v11; // rax
  unsigned __int16 v12; // cx
  int v13; // edx
  CMemoryLog *v14; // rax
  CVarObjHeap *v15; // rcx
  unsigned __int16 *v17; // rax
  unsigned __int16 v18; // cx
  int v19; // edx
  CMemoryLog *MemLogObject; // rax
  __int64 v21; // rdx

  v7 = wcschr(a2, 0x2Eu);
  if ( !v7 )
    return 87;
  v8 = v7 + 1;
  *a3 = 0;
  v9 = *v8;
  if ( *v8 )
  {
    v10 = 0;
    do
    {
      if ( v9 == 46 )
        break;
      ++v8;
      v10 = v9 + 2 * (5 * v10 - 24);
      *a3 = v10;
      v9 = *v8;
    }
    while ( *v8 );
  }
  if ( *v8 != 46 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, 87);
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 87;
    }
    v21 = 19;
    goto LABEL_29;
  }
  v11 = v8 + 1;
  *a4 = 0;
  v12 = *v11;
  if ( *v11 )
  {
    v13 = 0;
    do
    {
      if ( v12 == 46 )
        break;
      ++v11;
      v13 = v12 + 2 * (5 * v13 - 24);
      *a4 = v13;
      v12 = *v11;
    }
    while ( *v11 );
  }
  if ( *v11 != 46 )
  {
    v14 = GetMemLogObject();
    CMemoryLog::Write(v14, 87);
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 87;
    }
    v21 = 20;
LABEL_29:
    WPP_SF_d(*((_QWORD *)v15 + 2), v21, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids, 87);
    return 87;
  }
  v17 = v11 + 1;
  *a5 = 0;
  v18 = *v17;
  if ( *v17 )
  {
    v19 = 0;
    do
    {
      if ( v18 == 46 )
        break;
      ++v17;
      v19 = v18 + 2 * (5 * v19 - 24);
      *a5 = v19;
      v18 = *v17;
    }
    while ( *v17 );
  }
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x180013370  mov     [rsp+arg_0], rbx
0x180013375  push    rdi
0x180013376  sub     rsp, 20h
0x18001337a  mov     rcx, rdx; Str
0x18001337d  mov     rbx, r9
0x180013380  mov     edx, 2Eh ; '.'; Ch
0x180013385  mov     rdi, r8
0x180013388  call    cs:__imp_wcschr
0x18001338e  test    rax, rax
0x180013391  jz      loc_180013423
0x180013397  add     rax, 2
0x18001339b  xor     r9d, r9d
0x18001339e  mov     [rdi], r9d
0x1800133a1  movzx   ecx, word ptr [rax]
0x1800133a4  test    cx, cx
0x1800133a7  jz      short loc_1800133B6
0x1800133a9  mov     edx, r9d
0x1800133ac  cmp     cx, 2Eh ; '.'
0x1800133b0  jnz     loc_180013493
0x1800133b6  cmp     word ptr [rax], 2Eh ; '.'
0x1800133ba  jnz     loc_1800134D3
0x1800133c0  add     rax, 2
0x1800133c4  mov     [rbx], r9d
0x1800133c7  movzx   ecx, word ptr [rax]
0x1800133ca  test    cx, cx
0x1800133cd  jz      short loc_1800133F2
0x1800133cf  mov     edx, r9d
0x1800133d2  cmp     cx, 2Eh ; '.'
0x1800133d6  jz      short loc_1800133F2
0x1800133d8  movzx   ecx, cx
0x1800133db  lea     edx, [rdx+rdx*4]
0x1800133de  add     rax, 2
0x1800133e2  lea     edx, [rdx-18h]
0x1800133e5  lea     edx, [rcx+rdx*2]
0x1800133e8  mov     [rbx], edx
0x1800133ea  movzx   ecx, word ptr [rax]
0x1800133ed  test    cx, cx
0x1800133f0  jnz     short loc_1800133D2
0x1800133f2  cmp     word ptr [rax], 2Eh ; '.'
0x1800133f6  jz      short loc_180013433
0x1800133f8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800133fe  mov     rcx, rax
0x180013401  mov     edx, 57h ; 'W'
0x180013406  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001340c  mov     rcx, cs:WPP_GLOBAL_Control
0x180013413  lea     rax, WPP_GLOBAL_Control
0x18001341a  cmp     rcx, rax
0x18001341d  jnz     loc_180013539
0x180013423  mov     eax, 57h ; 'W'
0x180013428  mov     rbx, [rsp+28h+arg_0]
0x18001342d  add     rsp, 20h
0x180013431  pop     rdi
0x180013432  retn
0x180013433  mov     r8, [rsp+28h+arg_20]
0x180013438  add     rax, 2
0x18001343c  mov     [r8], r9d
0x18001343f  movzx   ecx, word ptr [rax]
0x180013442  test    cx, cx
0x180013445  jnz     short loc_18001346D
0x180013447  mov     rcx, cs:WPP_GLOBAL_Control
0x18001344e  lea     rax, WPP_GLOBAL_Control
0x180013455  cmp     rcx, rax
0x180013458  jz      short loc_180013460
0x18001345a  test    byte ptr [rcx+1Ch], 1
0x18001345e  jnz     short loc_1800134B6
0x180013460  mov     rbx, [rsp+28h+arg_0]
0x180013465  xor     eax, eax
0x180013467  add     rsp, 20h
0x18001346b  pop     rdi
0x18001346c  retn
0x18001346d  mov     edx, r9d
0x180013470  cmp     cx, 2Eh ; '.'
0x180013474  jz      short loc_180013447
0x180013476  movzx   ecx, cx
0x180013479  lea     edx, [rdx+rdx*4]
0x18001347c  add     rax, 2
0x180013480  lea     edx, [rdx-18h]
0x180013483  lea     edx, [rcx+rdx*2]
0x180013486  mov     [r8], edx
0x180013489  movzx   ecx, word ptr [rax]
0x18001348c  test    cx, cx
0x18001348f  jnz     short loc_180013470
0x180013491  jmp     short loc_180013447
0x180013493  movzx   ecx, cx
0x180013496  lea     edx, [rdx+rdx*4]
0x180013499  add     rax, 2
0x18001349d  lea     edx, [rdx-18h]
0x1800134a0  lea     edx, [rcx+rdx*2]
0x1800134a3  mov     [rdi], edx
0x1800134a5  movzx   ecx, word ptr [rax]
0x1800134a8  test    cx, cx
0x1800134ab  jz      loc_1800133B6
0x1800134b1  jmp     loc_1800133AC
0x1800134b6  cmp     byte ptr [rcx+19h], 2
0x1800134ba  jb      short loc_180013460
0x1800134bc  mov     rcx, [rcx+10h]
0x1800134c0  lea     r8, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids
0x1800134c7  mov     edx, 15h
0x1800134cc  call    WPP_SF_d
0x1800134d1  jmp     short loc_180013460
0x1800134d3  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800134d9  mov     rcx, rax
0x1800134dc  mov     edx, 57h ; 'W'
0x1800134e1  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800134e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800134ee  lea     rax, WPP_GLOBAL_Control
0x1800134f5  cmp     rcx, rax
0x1800134f8  jz      loc_180013423
0x1800134fe  test    byte ptr [rcx+1Ch], 1
0x180013502  jz      loc_180013423
0x180013508  cmp     byte ptr [rcx+19h], 2
0x18001350c  jb      loc_180013423
0x180013512  mov     edx, 13h
0x180013517  jmp     short loc_18001351E
0x180013519  mov     edx, 14h
0x18001351e  mov     rcx, [rcx+10h]
0x180013522  lea     r8, WPP_046e956a0ea4315e17b1ebb118145f1a_Traceguids
0x180013529  mov     r9d, 57h ; 'W'
0x18001352f  call    WPP_SF_d
0x180013534  jmp     loc_180013423
0x180013539  test    byte ptr [rcx+1Ch], 1
0x18001353d  jz      loc_180013423
0x180013543  cmp     byte ptr [rcx+19h], 2
0x180013547  jb      loc_180013423
0x18001354d  jmp     short loc_180013519
```
