# CBtrIndex::FindFirst(ushort const *,_WIN32_FIND_DATAW *,void * *)

- ea: `0x18000cb50`
- end: `0x18000d1eb`
- name: `?FindFirst@CBtrIndex@@QEAAJPEBGPEAU_WIN32_FIND_DATAW@@PEAPEAX@Z`
- size: `1691`
- prototype: `__int64 __fastcall(CBtrIndex *__hidden this, const unsigned __int16 *, struct _WIN32_FIND_DATAW *, void **)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18000bf70`
- `0x18000ca40`

## callees

- `0x1800012b8`
- `0x18000cb50`
- `0x18000d1f4`
- `0x18000d220`
- `0x18000dc00`
- `0x18000def0`
- `0x18000df50`
- `0x180010fa0`
- `0x180023b3c`
- `0x180024f8c`
- `0x1800443eb`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000cbbd`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000cc0c`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000cc57`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000cbbd`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000cc0c`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000cc57`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000ccd8`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000cdc0`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000cea6`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000ccd8`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000cdc0`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000cea6`
- `wbemcomn!?Unlock@?$CLockableFlexArray@VCStaticCritSec@@@@QEAAXXZ` at `0x18000ce59`
- `wbemcomn!?Unlock@?$CLockableFlexArray@VCStaticCritSec@@@@QEAAXXZ` at `0x18000ce59`
- `wbemcomn!?Lock@?$CLockableFlexArray@VCStaticCritSec@@@@QEAAXXZ` at `0x18000ce3a`
- `wbemcomn!?Lock@?$CLockableFlexArray@VCStaticCritSec@@@@QEAAXXZ` at `0x18000ce3a`
- `wbemcomn!?GetArenaHeap@CWin32DefaultArena@@SAPEAXXZ` at `0x18000cdeb`
- `wbemcomn!?GetArenaHeap@CWin32DefaultArena@@SAPEAXXZ` at `0x18000cdeb`
- `wbemcomn!?Add@CFlexArray@@QEAAHPEAX@Z` at `0x18000ce4a`
- `wbemcomn!?Add@CFlexArray@@QEAAHPEAX@Z` at `0x18000ce6d`
- `wbemcomn!?Add@CFlexArray@@QEAAHPEAX@Z` at `0x18000ce4a`
- `wbemcomn!?Add@CFlexArray@@QEAAHPEAX@Z` at `0x18000ce6d`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18000cd02`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18000ce29`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18000cd02`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18000ce29`
- `wbemcomn!??0CFlexArray@@QEAA@HH@Z` at `0x18000cc7c`
- `wbemcomn!??0CFlexArray@@QEAA@HH@Z` at `0x18000cc7c`
- `wbemcomn!??ACFlexArray@@QEAAAEAPEAXH@Z` at `0x18000cd15`
- `wbemcomn!??ACFlexArray@@QEAAAEAPEAXH@Z` at `0x18000cd15`
- `wbemcomn!?RemoveAt@CFlexArray@@QEAAHH@Z` at `0x18000cd23`
- `wbemcomn!?RemoveAt@CFlexArray@@QEAAHH@Z` at `0x18000cd23`
- `wbemcomn!GetMemLogObject` at `0x18000cfb7`
- `wbemcomn!GetMemLogObject` at `0x18000d01e`
- `wbemcomn!GetMemLogObject` at `0x18000d078`
- `wbemcomn!GetMemLogObject` at `0x18000d0e0`
- `wbemcomn!GetMemLogObject` at `0x18000d12e`
- `wbemcomn!GetMemLogObject` at `0x18000d188`
- `wbemcomn!GetMemLogObject` at `0x18000cfb7`
- `wbemcomn!GetMemLogObject` at `0x18000d01e`
- `wbemcomn!GetMemLogObject` at `0x18000d078`
- `wbemcomn!GetMemLogObject` at `0x18000d0e0`
- `wbemcomn!GetMemLogObject` at `0x18000d12e`
- `wbemcomn!GetMemLogObject` at `0x18000d188`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000cfc5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000d02c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000d088`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000d0eb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000d139`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000d196`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000cfc5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000d02c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000d088`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000d0eb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000d139`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000d196`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cdf9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cdf9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000cee2`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000cee2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall CBtrIndex::FindFirst(
        CBtrIndex *this,
        const unsigned __int16 *a2,
        struct _WIN32_FIND_DATAW *a3,
        void **a4)
{
  __int64 v7; // rbx
  WCHAR *cFileName; // r13
  __int64 v9; // rcx
  char *v10; // rax
  char *v11; // r14
  char *v12; // rcx
  __int16 i; // dx
  char *v14; // rax
  char *v15; // rax
  char *v16; // r12
  unsigned int v17; // eax
  unsigned int v18; // edi
  char *v19; // rax
  unsigned int *v20; // r8
  char *v21; // r15
  __int64 v22; // rdi
  unsigned int v23; // eax
  unsigned int v24; // esi
  unsigned int v25; // edx
  struct _WIN32_FIND_DATAW *v26; // rsi
  _BYTE *v27; // rdi
  _BYTE *j; // rcx
  WCHAR v29; // ax
  void *ArenaHeap; // rax
  char *v32; // r13
  int v33; // edi
  char *v34; // rax
  const wchar_t *v35; // rcx
  __int64 v36; // rdx
  char *v37; // rdx
  __int64 v38; // rax
  const unsigned __int16 *v39; // r8
  char *v40; // rcx
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v42; // rax
  CVarObjHeap *v43; // rcx
  __int64 v44; // rdx
  CMemoryLog *v45; // rax
  CMemoryLog *v46; // rax
  CMemoryLog *v47; // rax
  CMemoryLog *v48; // rax
  __int64 v49; // [rsp+0h] [rbp-198h] BYREF
  int v50; // [rsp+20h] [rbp-178h]
  char *Str2; // [rsp+28h] [rbp-170h] BYREF
  WCHAR *v52; // [rsp+30h] [rbp-168h]
  struct _WIN32_FIND_DATAW *v53; // [rsp+38h] [rbp-160h]
  void *v54[2]; // [rsp+40h] [rbp-158h] BYREF
  char v55; // [rsp+50h] [rbp-148h] BYREF
  char v56; // [rsp+15Ah] [rbp-3Eh] BYREF

  v53 = a3;
  v50 = 0;
  if ( g_dwSecTlsIndex == -1 || !TlsGetValue(g_dwSecTlsIndex) )
  {
    v7 = -1;
  }
  else
  {
    v34 = &v55;
    v35 = L"KI_41C53E6DB1ACF2453CEFD41398198E613F10DFF47709ECAB1D7F037756AC8CE7\\I_EEC4121F2A07B61ABA16414812AA9AFC39AB0A1"
           "36360A5ACE2240DC19B0464EB";
    v36 = 2;
    do
    {
      *(_OWORD *)v34 = *(_OWORD *)v35;
      *((_OWORD *)v34 + 1) = *((_OWORD *)v35 + 1);
      *((_OWORD *)v34 + 2) = *((_OWORD *)v35 + 2);
      *((_OWORD *)v34 + 3) = *((_OWORD *)v35 + 3);
      *((_OWORD *)v34 + 4) = *((_OWORD *)v35 + 4);
      *((_OWORD *)v34 + 5) = *((_OWORD *)v35 + 5);
      *((_OWORD *)v34 + 6) = *((_OWORD *)v35 + 6);
      *((_OWORD *)v34 + 7) = *((_OWORD *)v35 + 7);
      v34 += 128;
      v35 += 64;
      --v36;
    }
    while ( v36 );
    *(_OWORD *)(v34 - 2) = *(_OWORD *)(v35 - 1);
    v37 = &v56;
    v7 = -1;
    v38 = -1;
    do
      ++v38;
    while ( a2[v38] );
    v39 = &a2[(unsigned int)(v38 - 1)];
    v40 = (char *)&v49 + 78;
    do
    {
      if ( *(_WORD *)v37 != *v39 )
        break;
      v37 -= 2;
      --v39;
    }
    while ( v40 != v37 );
    if ( v40 == v37 )
      v50 = 1;
  }
  cFileName = a3->cFileName;
  v52 = a3->cFileName;
  a3->cFileName[0] = 0;
  a3->dwFileAttributes = 128;
  v9 = -1;
  do
    ++v9;
  while ( a2[v9] );
  v10 = (char *)CWin32DefaultArena::WbemMemAlloc(v9 + 1);
  v11 = v10;
  if ( !v10 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, 8);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_4468c7411f373aed0078c9b7f9420cb4_Traceguids, 8);
    }
    return 8;
  }
  v54[0] = v10;
  v54[1] = 0;
  v12 = v10;
  for ( i = *a2; *a2; LOBYTE(i) = *a2 )
  {
    ++a2;
    *v12++ = i;
  }
  *v12 = 0;
  v14 = (char *)CWin32DefaultArena::WbemMemAlloc(0x2B18u);
  Str2 = v14;
  if ( !v14 || (v15 = (char *)CBTreeIterator::CBTreeIterator((CBTreeIterator *)v14), v16 = v15, (Str2 = v15) == 0) )
  {
    v48 = GetMemLogObject();
    CMemoryLog::Write(v48, 8);
    v43 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_92;
    }
    v44 = 18;
LABEL_91:
    WPP_SF_d(*((_QWORD *)v43 + 2), v44, WPP_4468c7411f373aed0078c9b7f9420cb4_Traceguids, 8);
LABEL_92:
    CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>(v54);
    return 8;
  }
  try
  {
    v17 = CBTreeIterator::Init((CBTreeIterator *)v15, (CBtrIndex *)((char *)this + 8), v11);
  }
  catch ( CX_MemoryException )
  {
    v50 = 14;
    v18 = 14;
    v16 = Str2;
    goto LABEL_82;
  }
  v18 = v17;
  if ( !v17 )
  {
    v19 = (char *)CWin32DefaultArena::WbemMemAlloc(0x60u);
    v21 = v19;
    Str2 = v19;
    if ( v19 )
    {
      CFlexArray::CFlexArray((CFlexArray *)v19, 8, 100);
      *((_QWORD *)v21 + 11) = 0;
    }
    else
    {
      v21 = 0;
    }
    if ( v21 )
    {
      Str2 = 0;
      v22 = -1;
      do
        ++v22;
      while ( v11[v22] );
      v23 = CBTreeIterator::Next((CBTreeIterator *)v16, &Str2, v20);
      v24 = v23;
      if ( v23 == 259 )
      {
        v24 = 0;
      }
      else if ( !v23 )
      {
        v32 = Str2;
        if ( strncmp_0(v11, Str2, (unsigned int)v22) || v50 )
        {
          _BtrMemFree(v32);
          *((_DWORD *)v21 + 22) = 1;
          cFileName = v52;
        }
        else
        {
          if ( !CFlexArray::Size((CFlexArray *)v21)
            && (CLockableFlexArray<CStaticCritSec>::Lock(qword_180059B40),
                v33 = CFlexArray::Add((CFlexArray *)qword_180059B40, v21),
                CLockableFlexArray<CStaticCritSec>::Unlock(qword_180059B40),
                v33)
            || CFlexArray::Add((CFlexArray *)v21, v32) )
          {
            v24 = 14;
          }
          cFileName = v52;
        }
      }
      CBTreeIterator::~CBTreeIterator((CBTreeIterator *)v16);
      CWin32DefaultArena::WbemMemFree(v16);
      if ( !v24 )
      {
        v26 = v53;
        if ( !v53 || v21 == (char *)-1LL )
        {
          v45 = GetMemLogObject();
          v24 = 87;
          CMemoryLog::Write(v45, 87);
          if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_4468c7411f373aed0078c9b7f9420cb4_Traceguids, 87);
          }
        }
        else if ( CFlexArray::Size((CFlexArray *)v21) )
        {
          v27 = *(_BYTE **)CFlexArray::operator[](v21, 0);
          CFlexArray::RemoveAt((CFlexArray *)v21, 0);
          do
            ++v7;
          while ( v27[v7] );
          for ( j = &v27[v7 - 1]; *(j - 1) != 92; --j )
          {
            if ( j <= v27 )
              break;
          }
          v25 = 0;
          if ( *j )
          {
            while ( v25 < 0x104 )
            {
              v29 = (char)*j++;
              *cFileName++ = v29;
              ++v25;
              if ( !*j )
              {
                if ( v25 >= 0x104 )
                  break;
                goto LABEL_32;
              }
            }
          }
          else
          {
LABEL_32:
            *cFileName = 0;
          }
          v26->dwFileAttributes = 128;
          if ( v27 )
          {
            _InterlockedDecrement(&g_lAllocs);
            ArenaHeap = (void *)((__int64 (*)(void))CWin32DefaultArena::GetArenaHeap)();
            HeapFree(ArenaHeap, 0, v27);
          }
          v24 = 0;
        }
        else
        {
          v24 = 18;
        }
      }
      if ( v24 == 18 )
      {
        v24 = 2;
      }
      else if ( !v24 )
      {
        CIteratorBatch::`scalar deleting destructor'((CIteratorBatch *)v21, v25);
LABEL_48:
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_4468c7411f373aed0078c9b7f9420cb4_Traceguids, v24);
        }
        CWin32DefaultArena::WbemMemFree(v11);
        return v24;
      }
      CIteratorBatch::`scalar deleting destructor'((CIteratorBatch *)v21, v25);
      if ( v24 == 2 )
      {
        CWin32DefaultArena::WbemMemFree(v11);
        return 2;
      }
      v46 = GetMemLogObject();
      CMemoryLog::Write(v46, v24);
      goto LABEL_48;
    }
    CBTreeIterator::Release((CBTreeIterator *)v16);
    v42 = GetMemLogObject();
    CMemoryLog::Write(v42, 8);
    v43 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_92;
    }
    v44 = 20;
    goto LABEL_91;
  }
LABEL_82:
  CBTreeIterator::Release((CBTreeIterator *)v16);
  v47 = GetMemLogObject();
  CMemoryLog::Write(v47, v18);
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_4468c7411f373aed0078c9b7f9420cb4_Traceguids, v18);
  }
  CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>(v54);
  return v18;
}

```

## disassembly

```asm
0x18000cb50  push    rbx
0x18000cb52  push    rsi
0x18000cb53  push    rdi
0x18000cb54  push    r12
0x18000cb56  push    r13
0x18000cb58  push    r14
0x18000cb5a  push    r15
0x18000cb5c  sub     rsp, 160h
0x18000cb63  mov     r14, r8
0x18000cb66  mov     [rsp+198h+var_160], r8
0x18000cb6b  mov     rdi, rdx
0x18000cb6e  mov     rsi, rcx
0x18000cb71  xor     r15d, r15d
0x18000cb74  mov     [rsp+198h+var_178], r15d
0x18000cb79  mov     ecx, cs:?g_dwSecTlsIndex@@3KA; dwTlsIndex
0x18000cb7f  cmp     ecx, 0FFFFFFFFh
0x18000cb82  jnz     loc_18000CEE2
0x18000cb88  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000cb8f  lea     r13, [r14+2Ch]
0x18000cb93  mov     [rsp+198h+var_168], r13
0x18000cb98  mov     [r13+0], r15w
0x18000cb9d  mov     dword ptr [r14], 80h
0x18000cba4  mov     rcx, rbx
0x18000cba7  nop     word ptr [rax+rax+00000000h]
0x18000cbb0  inc     rcx
0x18000cbb3  cmp     [rdi+rcx*2], r15w
0x18000cbb8  jnz     short loc_18000CBB0
0x18000cbba  inc     rcx
0x18000cbbd  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000cbc3  mov     r14, rax
0x18000cbc6  test    rax, rax
0x18000cbc9  jz      loc_18000CFB7
0x18000cbcf  mov     [rsp+198h+var_158], rax
0x18000cbd4  mov     [rsp+198h+var_150], r15
0x18000cbd9  mov     rcx, rax
0x18000cbdc  movzx   edx, word ptr [rdi]
0x18000cbdf  test    dx, dx
0x18000cbe2  jz      short loc_18000CC04
0x18000cbe4  nop     dword ptr [rax+00h]
0x18000cbe8  nop     dword ptr [rax+rax+00000000h]
0x18000cbf0  lea     rdi, [rdi+2]
0x18000cbf4  mov     [rcx], dl
0x18000cbf6  inc     rcx
0x18000cbf9  movzx   eax, word ptr [rdi]
0x18000cbfc  movzx   edx, al
0x18000cbff  test    ax, ax
0x18000cc02  jnz     short loc_18000CBF0
0x18000cc04  mov     byte ptr [rcx], 0
0x18000cc07  mov     ecx, 2B18h
0x18000cc0c  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000cc12  mov     [rsp+198h+Str2], rax
0x18000cc17  test    rax, rax
0x18000cc1a  jz      loc_18000D188
0x18000cc20  mov     rcx, rax; this
0x18000cc23  call    ??0CBTreeIterator@@QEAA@XZ; CBTreeIterator::CBTreeIterator(void)
0x18000cc28  mov     r12, rax
0x18000cc2b  mov     [rsp+198h+Str2], rax
0x18000cc30  test    rax, rax
0x18000cc33  jz      loc_18000D188
0x18000cc39  lea     rdx, [rsi+8]; struct CBTree *
0x18000cc3d  mov     r8, r14; char *
0x18000cc40  mov     rcx, rax; this
0x18000cc43  call    ?Init@CBTreeIterator@@QEAAKPEAVCBTree@@PEAD@Z; CBTreeIterator::Init(CBTree *,char *)
0x18000cc48  mov     edi, eax
0x18000cc4a  test    eax, eax
0x18000cc4c  jnz     loc_18000D126
0x18000cc52  mov     ecx, 60h ; '`'
0x18000cc57  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000cc5d  mov     r15, rax
0x18000cc60  mov     [rsp+198h+Str2], rax
0x18000cc65  test    rax, rax
0x18000cc68  jz      loc_18000CDDC
0x18000cc6e  mov     edx, 8
0x18000cc73  mov     r8d, 64h ; 'd'
0x18000cc79  mov     rcx, rax
0x18000cc7c  call    cs:__imp_??0CFlexArray@@QEAA@HH@Z; CFlexArray::CFlexArray(int,int)
0x18000cc82  xor     eax, eax
0x18000cc84  mov     [r15+58h], rax
0x18000cc88  test    r15, r15
0x18000cc8b  jz      loc_18000D016
0x18000cc91  mov     [rsp+198h+Str2], rax
0x18000cc96  mov     rdi, rbx
0x18000cc99  nop     dword ptr [rax+00000000h]
0x18000cca0  inc     rdi
0x18000cca3  cmp     byte ptr [r14+rdi], 0
0x18000cca8  jnz     short loc_18000CCA0
0x18000ccaa  lea     rdx, [rsp+198h+Str2]; char **
0x18000ccaf  mov     rcx, r12; this
0x18000ccb2  call    ?Next@CBTreeIterator@@QEAAKPEAPEADPEAK@Z; CBTreeIterator::Next(char * *,ulong *)
0x18000ccb7  mov     esi, eax
0x18000ccb9  cmp     eax, 103h
0x18000ccbe  jz      loc_18000D071
0x18000ccc4  test    eax, eax
0x18000ccc6  jz      loc_18000CE01
0x18000cccc  mov     rcx, r12; this
0x18000cccf  call    ??1CBTreeIterator@@AEAA@XZ; CBTreeIterator::~CBTreeIterator(void)
0x18000ccd4  nop
0x18000ccd5  mov     rcx, r12
0x18000ccd8  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000ccde  nop
0x18000ccdf  test    esi, esi
0x18000cce1  jnz     loc_18000CD94
0x18000cce7  mov     rsi, [rsp+198h+var_160]
0x18000ccec  test    rsi, rsi
0x18000ccef  jz      loc_18000D078
0x18000ccf5  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x18000ccf9  jz      loc_18000D078
0x18000ccff  mov     rcx, r15
0x18000cd02  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x18000cd08  test    eax, eax
0x18000cd0a  jz      loc_18000CEBE
0x18000cd10  xor     edx, edx
0x18000cd12  mov     rcx, r15
0x18000cd15  call    cs:__imp_??ACFlexArray@@QEAAAEAPEAXH@Z; CFlexArray::operator[](int)
0x18000cd1b  mov     rdi, [rax]
0x18000cd1e  xor     edx, edx
0x18000cd20  mov     rcx, r15
0x18000cd23  call    cs:__imp_?RemoveAt@CFlexArray@@QEAAHH@Z; CFlexArray::RemoveAt(int)
0x18000cd29  nop     dword ptr [rax+00000000h]
0x18000cd30  inc     rbx
0x18000cd33  cmp     byte ptr [rdi+rbx], 0
0x18000cd37  jnz     short loc_18000CD30
0x18000cd39  lea     rcx, [rdi-1]
0x18000cd3d  add     rcx, rbx
0x18000cd40  cmp     byte ptr [rcx-1], 5Ch ; '\'
0x18000cd44  jz      short loc_18000CD54
0x18000cd46  cmp     rcx, rdi
0x18000cd49  jbe     short loc_18000CD54
0x18000cd4b  dec     rcx
0x18000cd4e  cmp     byte ptr [rcx-1], 5Ch ; '\'
0x18000cd52  jnz     short loc_18000CD46
0x18000cd54  xor     edx, edx
0x18000cd56  cmp     [rcx], dl
0x18000cd58  jz      short loc_18000CD80
0x18000cd5a  cmp     edx, 104h
0x18000cd60  jnb     short loc_18000CD87
0x18000cd62  movsx   eax, byte ptr [rcx]
0x18000cd65  inc     rcx
0x18000cd68  mov     [r13+0], ax
0x18000cd6d  add     r13, 2
0x18000cd71  inc     edx; unsigned int
0x18000cd73  cmp     byte ptr [rcx], 0
0x18000cd76  jnz     short loc_18000CD5A
0x18000cd78  cmp     edx, 104h
0x18000cd7e  jnb     short loc_18000CD87
0x18000cd80  xor     eax, eax
0x18000cd82  mov     [r13+0], ax
0x18000cd87  mov     dword ptr [rsi], 80h
0x18000cd8d  test    rdi, rdi
0x18000cd90  jnz     short loc_18000CDE4
0x18000cd92  xor     esi, esi
0x18000cd94  lea     rbx, WPP_GLOBAL_Control
0x18000cd9b  cmp     esi, 12h
0x18000cd9e  jz      loc_18000D0D6
0x18000cda4  test    esi, esi
0x18000cda6  jz      loc_18000CEB4
0x18000cdac  mov     rcx, r15; this
0x18000cdaf  call    ??_GCIteratorBatch@@QEAAPEAXI@Z; CIteratorBatch::`scalar deleting destructor'(uint)
0x18000cdb4  cmp     esi, 2
0x18000cdb7  jnz     loc_18000CE85
0x18000cdbd  mov     rcx, r14
0x18000cdc0  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000cdc6  nop
0x18000cdc7  mov     eax, esi
0x18000cdc9  add     rsp, 160h
0x18000cdd0  pop     r15
0x18000cdd2  pop     r14
0x18000cdd4  pop     r13
0x18000cdd6  pop     r12
0x18000cdd8  pop     rdi
0x18000cdd9  pop     rsi
0x18000cdda  pop     rbx
0x18000cddb  retn
0x18000cddc  mov     r15, rax
0x18000cddf  jmp     loc_18000CC88
0x18000cde4  lock dec cs:?g_lAllocs@@3JA; long g_lAllocs
0x18000cdeb  call    cs:__imp_?GetArenaHeap@CWin32DefaultArena@@SAPEAXXZ; CWin32DefaultArena::GetArenaHeap(void)
0x18000cdf1  mov     rcx, rax; hHeap
0x18000cdf4  mov     r8, rdi; lpMem
0x18000cdf7  xor     edx, edx; dwFlags
0x18000cdf9  call    cs:__imp_HeapFree
0x18000cdff  jmp     short loc_18000CD92
0x18000ce01  mov     r8d, edi; MaxCount
0x18000ce04  mov     r13, [rsp+198h+Str2]
0x18000ce09  mov     rdx, r13; Str2
0x18000ce0c  mov     rcx, r14; Str1
0x18000ce0f  call    strncmp_0
0x18000ce14  test    eax, eax
0x18000ce16  jnz     loc_18000CEC8
0x18000ce1c  cmp     [rsp+198h+var_178], eax
0x18000ce20  jnz     loc_18000CEC8
0x18000ce26  mov     rcx, r15
0x18000ce29  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x18000ce2f  test    eax, eax
0x18000ce31  jnz     short loc_18000CE67
0x18000ce33  lea     rcx, qword_180059B40
0x18000ce3a  call    cs:__imp_?Lock@?$CLockableFlexArray@VCStaticCritSec@@@@QEAAXXZ; CLockableFlexArray<CStaticCritSec>::Lock(void)
0x18000ce40  mov     rdx, r15
0x18000ce43  lea     rcx, qword_180059B40
0x18000ce4a  call    cs:__imp_?Add@CFlexArray@@QEAAHPEAX@Z; CFlexArray::Add(void *)
0x18000ce50  mov     edi, eax
0x18000ce52  lea     rcx, qword_180059B40
0x18000ce59  call    cs:__imp_?Unlock@?$CLockableFlexArray@VCStaticCritSec@@@@QEAAXXZ; CLockableFlexArray<CStaticCritSec>::Unlock(void)
0x18000ce5f  test    edi, edi
0x18000ce61  jnz     loc_18000D067
0x18000ce67  mov     rdx, r13
0x18000ce6a  mov     rcx, r15
0x18000ce6d  call    cs:__imp_?Add@CFlexArray@@QEAAHPEAX@Z; CFlexArray::Add(void *)
0x18000ce73  test    eax, eax
0x18000ce75  jnz     loc_18000D067
0x18000ce7b  mov     r13, [rsp+198h+var_168]
0x18000ce80  jmp     loc_18000CCCC
0x18000ce85  test    esi, esi
0x18000ce87  jnz     loc_18000D0E0
0x18000ce8d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ce94  cmp     rcx, rbx
0x18000ce97  jz      short loc_18000CEA3
0x18000ce99  test    byte ptr [rcx+1Ch], 1
0x18000ce9d  jnz     loc_18000D0F6
0x18000cea3  mov     rcx, r14
0x18000cea6  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18000ceac  nop
0x18000cead  mov     eax, esi
0x18000ceaf  jmp     loc_18000CDC9
0x18000ceb4  mov     rcx, r15; this
0x18000ceb7  call    ??_GCIteratorBatch@@QEAAPEAXI@Z; CIteratorBatch::`scalar deleting destructor'(uint)
0x18000cebc  jmp     short loc_18000CE8D
0x18000cebe  mov     esi, 12h
0x18000cec3  jmp     loc_18000CD94
0x18000cec8  mov     rcx, r13; void *
0x18000cecb  call    ?_BtrMemFree@@YAHPEAX@Z; _BtrMemFree(void *)
0x18000ced0  mov     dword ptr [r15+58h], 1
0x18000ced8  mov     r13, [rsp+198h+var_168]
0x18000cedd  jmp     loc_18000CCCC
0x18000cee2  call    cs:__imp_TlsGetValue
0x18000cee8  test    rax, rax
0x18000ceeb  jz      loc_18000CB88
0x18000cef1  lea     rax, [rsp+198h+var_148]
0x18000cef6  lea     rcx, aKi41c53e6db1ac; "KI_41C53E6DB1ACF2453CEFD41398198E613F10"...
0x18000cefd  mov     edx, 2
0x18000cf02  movups  xmm0, xmmword ptr [rcx]
0x18000cf05  movups  xmmword ptr [rax], xmm0
0x18000cf08  movups  xmm1, xmmword ptr [rcx+10h]
0x18000cf0c  movups  xmmword ptr [rax+10h], xmm1
0x18000cf10  movups  xmm0, xmmword ptr [rcx+20h]
0x18000cf14  movups  xmmword ptr [rax+20h], xmm0
0x18000cf18  movups  xmm1, xmmword ptr [rcx+30h]
0x18000cf1c  movups  xmmword ptr [rax+30h], xmm1
0x18000cf20  movups  xmm0, xmmword ptr [rcx+40h]
0x18000cf24  movups  xmmword ptr [rax+40h], xmm0
0x18000cf28  movups  xmm1, xmmword ptr [rcx+50h]
0x18000cf2c  movups  xmmword ptr [rax+50h], xmm1
0x18000cf30  movups  xmm0, xmmword ptr [rcx+60h]
0x18000cf34  movups  xmmword ptr [rax+60h], xmm0
0x18000cf38  movups  xmm1, xmmword ptr [rcx+70h]
0x18000cf3c  movups  xmmword ptr [rax+70h], xmm1
0x18000cf40  lea     rax, [rax+80h]
0x18000cf47  lea     rcx, [rcx+80h]
0x18000cf4e  sub     rdx, 1
0x18000cf52  jnz     short loc_18000CF02
0x18000cf54  movups  xmm0, xmmword ptr [rcx-2]
0x18000cf58  movups  xmmword ptr [rax-2], xmm0
0x18000cf5c  lea     rdx, [rsp+198h+var_3E]
0x18000cf64  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000cf6b  mov     rax, rbx
0x18000cf6e  xchg    ax, ax
0x18000cf70  inc     rax
0x18000cf73  cmp     [rdi+rax*2], r15w
0x18000cf78  jnz     short loc_18000CF70
0x18000cf7a  dec     eax
0x18000cf7c  lea     r8, [rdi+rax*2]
0x18000cf80  lea     rcx, [rsp+198h+var_148]
0x18000cf85  add     rcx, 0FFFFFFFFFFFFFFFEh
0x18000cf89  movzx   eax, word ptr [r8]
0x18000cf8d  cmp     [rdx], ax
0x18000cf90  jz      short loc_18000CFA8
0x18000cf92  cmp     rcx, rdx
0x18000cf95  jnz     loc_18000CB8F
0x18000cf9b  mov     [rsp+198h+var_178], 1
0x18000cfa3  jmp     loc_18000CB8F
0x18000cfa8  sub     rdx, 2
0x18000cfac  sub     r8, 2
0x18000cfb0  cmp     rcx, rdx
0x18000cfb3  jz      short loc_18000CF92
0x18000cfb5  jmp     short loc_18000CF89
0x18000cfb7  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000cfbd  mov     edx, 8
0x18000cfc2  mov     rcx, rax
0x18000cfc5  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000cfcb  lea     rbx, WPP_GLOBAL_Control
0x18000cfd2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cfd9  cmp     rcx, rbx
0x18000cfdc  jz      loc_18000D1E1
0x18000cfe2  test    byte ptr [rcx+1Ch], 1
0x18000cfe6  jz      loc_18000D1E1
0x18000cfec  cmp     byte ptr [rcx+19h], 2
0x18000cff0  jb      loc_18000D1E1
0x18000cff6  mov     edx, 11h
0x18000cffb  mov     r9d, 8
0x18000d001  lea     r8, WPP_4468c7411f373aed0078c9b7f9420cb4_Traceguids
  ... truncated ...
```
