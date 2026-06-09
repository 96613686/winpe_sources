# CBtrIndex::IndexEnumerationBegin(ushort const *,void * *)

- ea: `0x18000c500`
- end: `0x18000ca2d`
- name: `?IndexEnumerationBegin@CBtrIndex@@QEAAJPEBGPEAPEAX@Z`
- size: `1325`
- prototype: `__int64 __fastcall(CBtrIndex *__hidden this, const unsigned __int16 *, void **)`
- caller_count: `5`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180008730`
- `0x180009b80`
- `0x18000bef0`
- `0x18001dba8`
- `0x180024154`

## callees

- `0x1800012b8`
- `0x18000c500`
- `0x18000d1f4`
- `0x18000d220`
- `0x18000dc00`
- `0x18000def0`
- `0x18000df50`
- `0x180010fa0`
- `0x180023480`
- `0x180023b3c`
- `0x180024f8c`
- `0x1800443eb`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000c55e`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000c5a5`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000c846`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000c55e`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000c5a5`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000c846`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000c768`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000c787`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000c804`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000c768`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000c787`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000c804`
- `wbemcomn!??0CFlexArray@@QEAA@HH@Z` at `0x18000c71c`
- `wbemcomn!??0CFlexArray@@QEAA@HH@Z` at `0x18000c71c`
- `wbemcomn!GetMemLogObject` at `0x18000c5b9`
- `wbemcomn!GetMemLogObject` at `0x18000c7d9`
- `wbemcomn!GetMemLogObject` at `0x18000c89f`
- `wbemcomn!GetMemLogObject` at `0x18000c906`
- `wbemcomn!GetMemLogObject` at `0x18000c9d3`
- `wbemcomn!GetMemLogObject` at `0x18000c5b9`
- `wbemcomn!GetMemLogObject` at `0x18000c7d9`
- `wbemcomn!GetMemLogObject` at `0x18000c89f`
- `wbemcomn!GetMemLogObject` at `0x18000c906`
- `wbemcomn!GetMemLogObject` at `0x18000c9d3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000c5c7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000c7e4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000c8ad`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000c914`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000c9de`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000c5c7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000c7e4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000c8ad`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000c914`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000c9de`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000c61c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000c61c`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CBtrIndex::IndexEnumerationBegin(CBtrIndex *this, char *a2, void **a3)
{
  int v6; // r12d
  __int64 v7; // rdi
  __int64 v8; // rbx
  char *v9; // rax
  char *v10; // r14
  char *j; // rcx
  char v12; // al
  char *v13; // rax
  CMemoryLog *v14; // rax
  CVarObjHeap *v15; // rcx
  __int64 v16; // rdx
  __int64 v18; // rax
  const unsigned __int16 *v19; // r9
  __int64 v20; // r8
  const unsigned __int16 *v21; // rdx
  _QWORD *i; // rcx
  unsigned int *v23; // r8
  unsigned int v24; // eax
  unsigned int v25; // ebx
  unsigned int v26; // edx
  char *v27; // r13
  CMemoryLog *v28; // rax
  char *v29; // rax
  char *v30; // rsi
  unsigned int v31; // eax
  unsigned int v32; // ebx
  char *v33; // rax
  char *v34; // r15
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v36; // rax
  CMemoryLog *v37; // rax
  int v38; // [rsp+20h] [rbp-F8h]
  char *Str2; // [rsp+28h] [rbp-F0h] BYREF
  void **v40; // [rsp+30h] [rbp-E8h]
  void *v41[3]; // [rsp+38h] [rbp-E0h] BYREF
  _OWORD v42[8]; // [rsp+50h] [rbp-C8h] BYREF
  __int64 v43; // [rsp+D0h] [rbp-48h] BYREF

  v40 = a3;
  v6 = 0;
  v38 = 0;
  if ( g_dwSecTlsIndex == -1 || !TlsGetValue(g_dwSecTlsIndex) )
  {
    v7 = -1;
  }
  else
  {
    v42[0] = *(_OWORD *)L"CI_41C53E6DB1ACF2453CEFD41398198E613F10DFF47709ECAB1D7F037756AC8CE7";
    v42[1] = *(_OWORD *)L"E6DB1ACF2453CEFD41398198E613F10DFF47709ECAB1D7F037756AC8CE7";
    v42[2] = *(_OWORD *)L"2453CEFD41398198E613F10DFF47709ECAB1D7F037756AC8CE7";
    v42[3] = *(_OWORD *)L"41398198E613F10DFF47709ECAB1D7F037756AC8CE7";
    v42[4] = *(_OWORD *)L"E613F10DFF47709ECAB1D7F037756AC8CE7";
    v42[5] = *(_OWORD *)L"FF47709ECAB1D7F037756AC8CE7";
    v42[6] = *(_OWORD *)L"CAB1D7F037756AC8CE7";
    v42[7] = *(_OWORD *)L"37756AC8CE7";
    v43 = *(_QWORD *)L"CE7";
    v7 = -1;
    v18 = -1;
    do
      ++v18;
    while ( *(_WORD *)&a2[2 * v18] );
    v19 = (const unsigned __int16 *)a2;
    v20 = (unsigned int)v18;
LABEL_23:
    if ( v20 >= 67 )
    {
      v21 = v19;
      for ( i = v42; i != (__int64 *)((char *)&v43 + 6); i = (_QWORD *)((char *)i + 2) )
      {
        if ( *v21 != *(_WORD *)i )
        {
          ++v19;
          --v20;
          goto LABEL_23;
        }
        ++v21;
      }
      if ( v19 != (const unsigned __int16 *)&a2[2 * (unsigned int)v18] )
        v38 = 1;
    }
  }
  if ( a3 )
    *a3 = (void *)-1LL;
  v8 = -1;
  do
    ++v8;
  while ( *(_WORD *)&a2[2 * v8] );
  v9 = (char *)CWin32DefaultArena::WbemMemAlloc(v8 + 1);
  v10 = v9;
  if ( !v9 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, 8);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_4468c7411f373aed0078c9b7f9420cb4_Traceguids, 8);
    }
    return 8;
  }
  v41[0] = v9;
  v41[1] = 0;
  for ( j = v9; *(_WORD *)a2; *j++ = v12 )
  {
    if ( !v8 )
      break;
    --v8;
    v12 = *a2;
    a2 += 2;
  }
  *j = 0;
  v13 = (char *)CWin32DefaultArena::WbemMemAlloc(0x2B18u);
  Str2 = v13;
  if ( !v13 || (v29 = (char *)CBTreeIterator::CBTreeIterator((CBTreeIterator *)v13), v30 = v29, (Str2 = v29) == 0) )
  {
    v14 = GetMemLogObject();
    CMemoryLog::Write(v14, 8);
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_17;
    }
    v16 = 25;
LABEL_16:
    WPP_SF_d(*((_QWORD *)v15 + 2), v16, WPP_4468c7411f373aed0078c9b7f9420cb4_Traceguids, 8);
LABEL_17:
    CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>(v41);
    return 8;
  }
  try
  {
    v31 = CBTreeIterator::Init((CBTreeIterator *)v29, (CBtrIndex *)((char *)this + 8), v10);
  }
  catch ( CX_MemoryException )
  {
    v32 = 14;
    v30 = Str2;
    goto LABEL_71;
  }
  v32 = v31;
  if ( v31 )
  {
LABEL_71:
    CBTreeIterator::Release((CBTreeIterator *)v30);
    v37 = GetMemLogObject();
    CMemoryLog::Write(v37, v32);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_4468c7411f373aed0078c9b7f9420cb4_Traceguids, v32);
    }
    CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>(v41);
    return v32;
  }
  v33 = (char *)CWin32DefaultArena::WbemMemAlloc(0x60u);
  v34 = v33;
  Str2 = v33;
  if ( v33 )
  {
    CFlexArray::CFlexArray((CFlexArray *)v33, 8, 100);
    *((_QWORD *)v34 + 11) = 0;
  }
  else
  {
    v34 = 0;
  }
  if ( !v34 )
  {
    CBTreeIterator::Release((CBTreeIterator *)v30);
    v36 = GetMemLogObject();
    CMemoryLog::Write(v36, 8);
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_17;
    }
    v16 = 27;
    goto LABEL_16;
  }
  Str2 = 0;
  do
    ++v7;
  while ( v10[v7] );
  while ( 1 )
  {
    v24 = CBTreeIterator::Next((CBTreeIterator *)v30, &Str2, v23);
    v25 = v24;
    if ( v24 == 259 )
      break;
    if ( v24 )
      goto LABEL_35;
    v27 = Str2;
    if ( strncmp_0(v10, Str2, (unsigned int)v7) || v38 )
    {
      _BtrMemFree(v27);
      *((_DWORD *)v34 + 22) = 1;
      goto LABEL_35;
    }
    if ( !(unsigned int)CIteratorBatch::Add((CIteratorBatch *)v34, v27) )
    {
      v25 = 14;
      goto LABEL_35;
    }
    ++v6;
  }
  v25 = 0;
LABEL_35:
  CBTreeIterator::~CBTreeIterator((CBTreeIterator *)v30);
  CWin32DefaultArena::WbemMemFree(v30);
  if ( v25 )
  {
    CIteratorBatch::`scalar deleting destructor'((CIteratorBatch *)v34, v26);
    if ( v25 == 2 )
    {
LABEL_37:
      CWin32DefaultArena::WbemMemFree(v10);
      return 2;
    }
    v28 = GetMemLogObject();
    CMemoryLog::Write(v28, v25);
  }
  else
  {
    if ( !v6 )
    {
      CIteratorBatch::`scalar deleting destructor'((CIteratorBatch *)v34, v26);
      goto LABEL_37;
    }
    if ( v40 )
      *v40 = v34;
    else
      CIteratorBatch::`scalar deleting destructor'((CIteratorBatch *)v34, v26);
  }
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_4468c7411f373aed0078c9b7f9420cb4_Traceguids, v25);
  }
  CWin32DefaultArena::WbemMemFree(v10);
  return v25;
}

```

## disassembly

```asm
0x18000c500  push    rbx
0x18000c502  push    rsi
0x18000c503  push    rdi
0x18000c504  push    r12
0x18000c506  push    r13
0x18000c508  push    r14
0x18000c50a  push    r15
0x18000c50c  sub     rsp, 0E0h
0x18000c513  mov     r13, r8
0x18000c516  mov     [rsp+118h+var_E8], r8
0x18000c51b  mov     rsi, rdx
0x18000c51e  mov     r15, rcx
0x18000c521  xor     r12d, r12d
0x18000c524  mov     [rsp+118h+var_F8], r12d
0x18000c529  mov     ecx, cs:?g_dwSecTlsIndex@@3KA; dwTlsIndex
0x18000c52f  cmp     ecx, 0FFFFFFFFh
0x18000c532  jnz     loc_18000C61C
0x18000c538  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18000c53f  test    r13, r13
0x18000c542  jz      short loc_18000C548
0x18000c544  mov     [r13+0], rdi
0x18000c548  mov     rbx, rdi
0x18000c54b  nop     dword ptr [rax+rax+00h]
0x18000c550  inc     rbx
0x18000c553  cmp     [rsi+rbx*2], r12w
0x18000c558  jnz     short loc_18000C550
0x18000c55a  lea     rcx, [rbx+1]
0x18000c55e  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000c564  mov     r14, rax
0x18000c567  test    rax, rax
0x18000c56a  jz      loc_18000C89F
0x18000c570  mov     [rsp+118h+var_E0], rax
0x18000c575  mov     [rsp+118h+var_D8], r12
0x18000c57a  mov     rcx, rax
0x18000c57d  cmp     word ptr [rsi], 0
0x18000c581  jz      short loc_18000C59D
0x18000c583  test    rbx, rbx
0x18000c586  jz      short loc_18000C59D
0x18000c588  dec     rbx
0x18000c58b  movzx   eax, byte ptr [rsi]
0x18000c58e  add     rsi, 2
0x18000c592  mov     [rcx], al
0x18000c594  inc     rcx
0x18000c597  cmp     word ptr [rsi], 0
0x18000c59b  jnz     short loc_18000C583
0x18000c59d  mov     byte ptr [rcx], 0
0x18000c5a0  mov     ecx, 2B18h
0x18000c5a5  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000c5ab  mov     [rsp+118h+Str2], rax
0x18000c5b0  test    rax, rax
0x18000c5b3  jnz     loc_18000C80F
0x18000c5b9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000c5bf  mov     edx, 8
0x18000c5c4  mov     rcx, rax
0x18000c5c7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000c5cd  lea     rax, WPP_GLOBAL_Control
0x18000c5d4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c5db  cmp     rcx, rax
0x18000c5de  jz      short loc_18000C608
0x18000c5e0  test    byte ptr [rcx+1Ch], 1
0x18000c5e4  jz      short loc_18000C608
0x18000c5e6  cmp     byte ptr [rcx+19h], 2
0x18000c5ea  jb      short loc_18000C608
0x18000c5ec  mov     edx, 19h
0x18000c5f1  mov     r9d, 8
0x18000c5f7  lea     r8, WPP_4468c7411f373aed0078c9b7f9420cb4_Traceguids
0x18000c5fe  mov     rcx, [rcx+10h]
0x18000c602  call    WPP_SF_d
0x18000c607  nop
0x18000c608  lea     rcx, [rsp+118h+var_E0]
0x18000c60d  call    ??1?$CVectorDeleteMe@G@@QEAA@XZ; CVectorDeleteMe<ushort>::~CVectorDeleteMe<ushort>(void)
0x18000c612  mov     eax, 8
0x18000c617  jmp     loc_18000C793
0x18000c61c  call    cs:__imp_TlsGetValue
0x18000c622  test    rax, rax
0x18000c625  jz      loc_18000C538
0x18000c62b  movaps  xmm0, xmmword ptr cs:aCi41c53e6db1ac; "CI_41C53E6DB1ACF2453CEFD41398198E613F10"...
0x18000c632  movaps  [rsp+118h+var_C8], xmm0
0x18000c637  movaps  xmm1, xmmword ptr cs:aCi41c53e6db1ac+10h; "E6DB1ACF2453CEFD41398198E613F10DFF47709"...
0x18000c63e  movaps  [rsp+118h+var_B8], xmm1
0x18000c643  movaps  xmm0, xmmword ptr cs:aCi41c53e6db1ac+20h; "2453CEFD41398198E613F10DFF47709ECAB1D7F"...
0x18000c64a  movaps  [rsp+118h+var_A8], xmm0
0x18000c64f  movaps  xmm1, xmmword ptr cs:aCi41c53e6db1ac+30h; "41398198E613F10DFF47709ECAB1D7F037756AC"...
0x18000c656  movaps  [rsp+118h+var_98], xmm1
0x18000c65e  movaps  xmm0, xmmword ptr cs:aCi41c53e6db1ac+40h; "E613F10DFF47709ECAB1D7F037756AC8CE7"
0x18000c665  movaps  [rsp+118h+var_88], xmm0
0x18000c66d  movaps  xmm1, xmmword ptr cs:aCi41c53e6db1ac+50h; "FF47709ECAB1D7F037756AC8CE7"
0x18000c674  movaps  [rsp+118h+var_78], xmm1
0x18000c67c  movaps  xmm0, xmmword ptr cs:aCi41c53e6db1ac+60h; "CAB1D7F037756AC8CE7"
0x18000c683  movaps  [rsp+118h+var_68], xmm0
0x18000c68b  movaps  xmm1, xmmword ptr cs:aCi41c53e6db1ac+70h; "37756AC8CE7"
0x18000c692  movaps  [rsp+118h+var_58], xmm1
0x18000c69a  movsd   xmm0, qword ptr cs:aCi41c53e6db1ac+80h; "CE7"
0x18000c6a2  movsd   [rsp+118h+var_48], xmm0
0x18000c6ab  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18000c6b2  mov     rax, rdi
0x18000c6b5  inc     rax
0x18000c6b8  cmp     [rsi+rax*2], r12w
0x18000c6bd  jnz     short loc_18000C6B5
0x18000c6bf  mov     r10d, eax
0x18000c6c2  mov     r9, rsi
0x18000c6c5  mov     r8d, eax
0x18000c6c8  nop     dword ptr [rax+rax+00000000h]
0x18000c6d0  cmp     r8, 43h ; 'C'
0x18000c6d4  jl      loc_18000C53F
0x18000c6da  mov     rdx, r9
0x18000c6dd  lea     rcx, [rsp+118h+var_C8]
0x18000c6e2  lea     rax, [rsp+118h+var_48+6]
0x18000c6ea  cmp     rcx, rax
0x18000c6ed  jz      loc_18000C885
0x18000c6f3  movzx   eax, word ptr [rcx]
0x18000c6f6  cmp     [rdx], ax
0x18000c6f9  jz      short loc_18000C704
0x18000c6fb  add     r9, 2
0x18000c6ff  dec     r8
0x18000c702  jmp     short loc_18000C6D0
0x18000c704  add     rdx, 2
0x18000c708  add     rcx, 2
0x18000c70c  jmp     short loc_18000C6E2
0x18000c70e  mov     edx, 8
0x18000c713  mov     r8d, 64h ; 'd'
0x18000c719  mov     rcx, r15
0x18000c71c  call    cs:__imp_??0CFlexArray@@QEAA@HH@Z; CFlexArray::CFlexArray(int,int)
0x18000c722  mov     [r15+58h], r12
0x18000c726  test    r15, r15
0x18000c729  jz      loc_18000C8FE
0x18000c72f  mov     [rsp+118h+Str2], r12
0x18000c734  inc     rdi
0x18000c737  cmp     byte ptr [r14+rdi], 0
0x18000c73c  jnz     short loc_18000C734
0x18000c73e  lea     rdx, [rsp+118h+Str2]; char **
0x18000c743  mov     rcx, rsi; this
0x18000c746  call    ?Next@CBTreeIterator@@QEAAKPEAPEADPEAK@Z; CBTreeIterator::Next(char * *,ulong *)
0x18000c74b  mov     ebx, eax
0x18000c74d  cmp     eax, 103h
0x18000c752  jz      loc_18000C970
0x18000c758  test    eax, eax
0x18000c75a  jz      short loc_18000C7A6
0x18000c75c  mov     rcx, rsi; this
0x18000c75f  call    ??1CBTreeIterator@@AEAA@XZ; CBTreeIterator::~CBTreeIterator(void)
0x18000c764  nop
0x18000c765  mov     rcx, rsi
0x18000c768  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000c76e  nop
0x18000c76f  test    ebx, ebx
0x18000c771  jz      loc_18000C865
0x18000c777  mov     rcx, r15; this
0x18000c77a  call    ??_GCIteratorBatch@@QEAAPEAXI@Z; CIteratorBatch::`scalar deleting destructor'(uint)
0x18000c77f  cmp     ebx, 2
0x18000c782  jnz     short loc_18000C7D9
0x18000c784  mov     rcx, r14
0x18000c787  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000c78d  nop
0x18000c78e  mov     eax, 2
0x18000c793  add     rsp, 0E0h
0x18000c79a  pop     r15
0x18000c79c  pop     r14
0x18000c79e  pop     r13
0x18000c7a0  pop     r12
0x18000c7a2  pop     rdi
0x18000c7a3  pop     rsi
0x18000c7a4  pop     rbx
0x18000c7a5  retn
0x18000c7a6  mov     r8d, edi; MaxCount
0x18000c7a9  mov     r13, [rsp+118h+Str2]
0x18000c7ae  mov     rdx, r13; Str2
0x18000c7b1  mov     rcx, r14; Str1
0x18000c7b4  call    strncmp_0
0x18000c7b9  test    eax, eax
0x18000c7bb  jnz     short loc_18000C7C7
0x18000c7bd  cmp     [rsp+118h+var_F8], eax
0x18000c7c1  jz      loc_18000C94F
0x18000c7c7  mov     rcx, r13; void *
0x18000c7ca  call    ?_BtrMemFree@@YAHPEAX@Z; _BtrMemFree(void *)
0x18000c7cf  mov     dword ptr [r15+58h], 1
0x18000c7d7  jmp     short loc_18000C75C
0x18000c7d9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000c7df  mov     edx, ebx
0x18000c7e1  mov     rcx, rax
0x18000c7e4  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000c7ea  lea     rax, WPP_GLOBAL_Control
0x18000c7f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c7f8  cmp     rcx, rax
0x18000c7fb  jnz     loc_18000C991
0x18000c801  mov     rcx, r14
0x18000c804  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000c80a  nop
0x18000c80b  mov     eax, ebx
0x18000c80d  jmp     short loc_18000C793
0x18000c80f  mov     rcx, rax; this
0x18000c812  call    ??0CBTreeIterator@@QEAA@XZ; CBTreeIterator::CBTreeIterator(void)
0x18000c817  mov     rsi, rax
0x18000c81a  mov     [rsp+118h+Str2], rax
0x18000c81f  test    rax, rax
0x18000c822  jz      loc_18000C5B9
0x18000c828  lea     rdx, [r15+8]; struct CBTree *
0x18000c82c  mov     r8, r14; char *
0x18000c82f  mov     rcx, rax; this
0x18000c832  call    ?Init@CBTreeIterator@@QEAAKPEAVCBTree@@PEAD@Z; CBTreeIterator::Init(CBTree *,char *)
0x18000c837  mov     ebx, eax
0x18000c839  test    eax, eax
0x18000c83b  jnz     loc_18000C9CB
0x18000c841  mov     ecx, 60h ; '`'
0x18000c846  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000c84c  mov     r15, rax
0x18000c84f  mov     [rsp+118h+Str2], rax
0x18000c854  test    rax, rax
0x18000c857  jnz     loc_18000C70E
0x18000c85d  mov     r15, r12
0x18000c860  jmp     loc_18000C726
0x18000c865  test    r12d, r12d
0x18000c868  jz      loc_18000C977
0x18000c86e  mov     r13, [rsp+118h+var_E8]
0x18000c873  test    r13, r13
0x18000c876  jz      loc_18000C984
0x18000c87c  mov     [r13+0], r15
0x18000c880  jmp     loc_18000C7EA
0x18000c885  lea     rax, [rsi+r10*2]
0x18000c889  cmp     r9, rax
0x18000c88c  jz      loc_18000C53F
0x18000c892  mov     [rsp+118h+var_F8], 1
0x18000c89a  jmp     loc_18000C53F
0x18000c89f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000c8a5  mov     edx, 8
0x18000c8aa  mov     rcx, rax
0x18000c8ad  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000c8b3  lea     rax, WPP_GLOBAL_Control
0x18000c8ba  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c8c1  cmp     rcx, rax
0x18000c8c4  jz      loc_18000C612
0x18000c8ca  test    byte ptr [rcx+1Ch], 1
0x18000c8ce  jz      loc_18000C612
0x18000c8d4  cmp     byte ptr [rcx+19h], 2
0x18000c8d8  jb      loc_18000C612
0x18000c8de  mov     edx, 18h
0x18000c8e3  mov     r9d, 8
0x18000c8e9  lea     r8, WPP_4468c7411f373aed0078c9b7f9420cb4_Traceguids
0x18000c8f0  mov     rcx, [rcx+10h]
0x18000c8f4  call    WPP_SF_d
0x18000c8f9  jmp     loc_18000C612
0x18000c8fe  mov     rcx, rsi; this
0x18000c901  call    ?Release@CBTreeIterator@@QEAAKXZ; CBTreeIterator::Release(void)
0x18000c906  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000c90c  mov     edx, 8
0x18000c911  mov     rcx, rax
0x18000c914  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000c91a  lea     rax, WPP_GLOBAL_Control
0x18000c921  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c928  cmp     rcx, rax
0x18000c92b  jz      loc_18000C608
0x18000c931  test    byte ptr [rcx+1Ch], 1
0x18000c935  jz      loc_18000C608
0x18000c93b  cmp     byte ptr [rcx+19h], 2
0x18000c93f  jb      loc_18000C608
0x18000c945  mov     edx, 1Bh
0x18000c94a  jmp     loc_18000C5F1
0x18000c94f  mov     rdx, r13; char *
0x18000c952  mov     rcx, r15; this
0x18000c955  call    ?Add@CIteratorBatch@@QEAAHPEAD@Z; CIteratorBatch::Add(char *)
0x18000c95a  test    eax, eax
0x18000c95c  jz      short loc_18000C966
0x18000c95e  inc     r12d
0x18000c961  jmp     loc_18000C73E
0x18000c966  mov     ebx, 0Eh
0x18000c96b  jmp     loc_18000C75C
0x18000c970  xor     ebx, ebx
0x18000c972  jmp     loc_18000C75C
0x18000c977  mov     rcx, r15; this
0x18000c97a  call    ??_GCIteratorBatch@@QEAAPEAXI@Z; CIteratorBatch::`scalar deleting destructor'(uint)
0x18000c97f  jmp     loc_18000C784
0x18000c984  mov     rcx, r15; this
0x18000c987  call    ??_GCIteratorBatch@@QEAAPEAXI@Z; CIteratorBatch::`scalar deleting destructor'(uint)
0x18000c98c  jmp     loc_18000C7EA
0x18000c991  test    byte ptr [rcx+1Ch], 1
0x18000c995  jz      loc_18000C801
0x18000c99b  cmp     byte ptr [rcx+19h], 2
0x18000c99f  jb      loc_18000C801
0x18000c9a5  mov     edx, 1Ch
0x18000c9aa  mov     r9d, ebx
0x18000c9ad  lea     r8, WPP_4468c7411f373aed0078c9b7f9420cb4_Traceguids
0x18000c9b4  mov     rcx, [rcx+10h]
0x18000c9b8  call    WPP_SF_d
0x18000c9bd  jmp     loc_18000C801
0x18000c9c2  mov     ebx, [rsp+118h+var_F8]
0x18000c9c6  mov     rsi, [rsp+118h+Str2]
0x18000c9cb  mov     rcx, rsi; this
0x18000c9ce  call    ?Release@CBTreeIterator@@QEAAKXZ; CBTreeIterator::Release(void)
0x18000c9d3  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000c9d9  mov     edx, ebx
0x18000c9db  mov     rcx, rax
0x18000c9de  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000c9e4  lea     rax, WPP_GLOBAL_Control
0x18000c9eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c9f2  cmp     rcx, rax
0x18000c9f5  jz      short loc_18000CA1C
0x18000c9f7  test    byte ptr [rcx+1Ch], 1
0x18000c9fb  jz      short loc_18000CA1C
0x18000c9fd  cmp     byte ptr [rcx+19h], 2
0x18000ca01  jb      short loc_18000CA1C
0x18000ca03  mov     edx, 1Ah
  ... truncated ...
```
