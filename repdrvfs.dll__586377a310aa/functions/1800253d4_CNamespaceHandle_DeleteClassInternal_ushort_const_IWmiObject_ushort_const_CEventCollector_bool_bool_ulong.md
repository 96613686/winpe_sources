# CNamespaceHandle::DeleteClassInternal(ushort const *,_IWmiObject *,ushort const *,CEventCollector &,bool,bool,ulong)

- ea: `0x1800253d4`
- end: `0x180025719`
- name: `?DeleteClassInternal@CNamespaceHandle@@IEAAJPEBGPEAU_IWmiObject@@0AEAVCEventCollector@@_N3K@Z`
- size: `837`
- prototype: `__int64 __fastcall(CNamespaceHandle *__hidden this, const unsigned __int16 *, struct _IWmiObject *, const unsigned __int16 *, struct CEventCollector *, bool, bool, unsigned int)`
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180025180`
- `0x180032f08`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x180014024`
- `0x18001e134`
- `0x180020f2c`
- `0x180023270`
- `0x1800253d4`
- `0x180030a90`
- `0x1800332dc`
- `0x180033a0c`
- `0x180035178`
- `0x18003e1f0`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18002542d`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18002542d`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180025496`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180025536`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800255af`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002562d`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180025658`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800256bb`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800256ff`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180025496`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180025536`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800255af`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002562d`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180025658`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800256bb`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800256ff`
- `wbemcomn!GetMemLogObject` at `0x18002544a`
- `wbemcomn!GetMemLogObject` at `0x1800254ea`
- `wbemcomn!GetMemLogObject` at `0x180025563`
- `wbemcomn!GetMemLogObject` at `0x1800255e1`
- `wbemcomn!GetMemLogObject` at `0x18002544a`
- `wbemcomn!GetMemLogObject` at `0x1800254ea`
- `wbemcomn!GetMemLogObject` at `0x180025563`
- `wbemcomn!GetMemLogObject` at `0x1800255e1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002545a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800254f5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002556e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800255ec`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002545a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800254f5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002556e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800255ec`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CNamespaceHandle::DeleteClassInternal(
        CNamespaceHandle *this,
        const unsigned __int16 *a2,
        struct _IWmiObject *a3,
        const unsigned __int16 *a4,
        struct CEventCollector *a5,
        bool a6,
        bool a7,
        unsigned int a8)
{
  unsigned __int16 *v12; // rbx
  CMemoryLog *v13; // rax
  int v15; // edi
  CMemoryLog *MemLogObject; // rax
  char v17; // r12
  const unsigned __int16 *v18; // rdx
  CMemoryLog *v19; // rax
  CMemoryLog *v20; // rax
  unsigned int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // rax
  unsigned int v25; // ecx
  unsigned int v26; // eax

  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 380, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids);
  }
  v12 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(0x2E6u);
  if ( v12 )
  {
    *v12 = 0;
    Cat2Str(v12, *((unsigned __int16 **)this + 7), a4, 0x173u);
    v15 = CNamespaceHandle::DeleteDerivedClasses(this, a2, a5, a7, a8);
    if ( v15 < 0 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v15);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          382,
          WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
          (unsigned int)v15);
      }
LABEL_17:
      CWin32DefaultArena::WbemMemFree(v12);
      return (unsigned int)v15;
    }
    v17 = *((_BYTE *)a5 + 96);
    *((_BYTE *)a5 + 96) = 1;
    v15 = CNamespaceHandle::DeleteClassInstances(this, a2, a3, a5);
    if ( v15 < 0 )
    {
      v19 = GetMemLogObject();
      CMemoryLog::Write(v19, v15);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          383,
          WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
          (unsigned int)v15);
      }
      goto LABEL_17;
    }
    *((_BYTE *)a5 + 96) = v17;
    if ( !a6 )
    {
      v15 = CNamespaceHandle::EraseClassRelationships(this, v18, a3, a4);
      if ( v15 < 0 )
      {
        v20 = GetMemLogObject();
        CMemoryLog::Write(v20, v15);
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            384,
            WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
            (unsigned int)v15);
        }
        goto LABEL_17;
      }
      v21 = CFileCache::DeleteObject((CFileCache *)byte_180058AF8, v12);
      if ( v21 )
      {
        v15 = A51TranslateErrorCode(v21, v22, v23);
        CWin32DefaultArena::WbemMemFree(v12);
        return (unsigned int)v15;
      }
      v24 = -1;
      do
        ++v24;
      while ( v12[v24] );
      v12[v24 - 66] = 82;
      if ( !dword_180058AFC || g_bShuttingDown )
      {
        v25 = 1255;
LABEL_42:
        v15 = A51TranslateErrorCode(v25, v22, v23);
        CWin32DefaultArena::WbemMemFree(v12);
        return (unsigned int)v15;
      }
      v26 = CObjectHeap::DeleteNode((CObjectHeap *)&qword_180058EF8, v12);
      v25 = 0;
      if ( v26 != 2 )
        v25 = v26;
      if ( v25 )
        goto LABEL_42;
    }
    CHierarchyCache::InvalidateClass(*((CHierarchyCache **)this + 11), a2);
    if ( !a7 )
      CNamespaceHandle::FireEvent(this, a5, 0xBu, a2, a3, 0);
    CWin32DefaultArena::WbemMemFree(v12);
    return 0;
  }
  else
  {
    v13 = GetMemLogObject();
    CMemoryLog::Write(v13, -2147217402);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 381, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749894LL);
    }
    CWin32DefaultArena::WbemMemFree(0);
    return 2147749894LL;
  }
}

```

## disassembly

```asm
0x1800253d4  push    rbx
0x1800253d6  push    rbp
0x1800253d7  push    rsi
0x1800253d8  push    rdi
0x1800253d9  push    r12
0x1800253db  push    r13
0x1800253dd  push    r14
0x1800253df  push    r15
0x1800253e1  sub     rsp, 48h
0x1800253e5  mov     r13, r9
0x1800253e8  mov     r15, r8
0x1800253eb  mov     r14, rdx
0x1800253ee  mov     rsi, rcx
0x1800253f1  lea     rdi, WPP_GLOBAL_Control
0x1800253f8  mov     r12b, 1
0x1800253fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180025402  cmp     rcx, rdi
0x180025405  jz      short loc_180025428
0x180025407  test    [rcx+1Ch], r12b
0x18002540b  jz      short loc_180025428
0x18002540d  cmp     byte ptr [rcx+19h], 5
0x180025411  jb      short loc_180025428
0x180025413  mov     edx, 17Ch
0x180025418  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18002541f  mov     rcx, [rcx+10h]
0x180025423  call    WPP_SF_
0x180025428  mov     ecx, 2E6h
0x18002542d  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180025433  mov     rbx, rax
0x180025436  mov     [rsp+88h+var_58], rax
0x18002543b  test    rax, rax
0x18002543e  jz      short loc_180025445
0x180025440  xor     eax, eax
0x180025442  mov     [rbx], ax
0x180025445  test    rbx, rbx
0x180025448  jnz     short loc_1800254A4
0x18002544a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180025450  mov     ebx, 80041006h
0x180025455  mov     edx, ebx
0x180025457  mov     rcx, rax
0x18002545a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180025460  mov     rcx, cs:WPP_GLOBAL_Control
0x180025467  cmp     rcx, rdi
0x18002546a  jz      short loc_180025494
0x18002546c  test    [rcx+1Ch], r12b
0x180025470  jz      short loc_180025494
0x180025472  cmp     byte ptr [rcx+19h], 2
0x180025476  jb      short loc_180025494
0x180025478  mov     edx, 17Dh
0x18002547d  mov     r9d, 80041006h
0x180025483  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18002548a  mov     rcx, [rcx+10h]
0x18002548e  call    WPP_SF_d
0x180025493  nop
0x180025494  xor     ecx, ecx
0x180025496  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18002549c  nop
0x18002549d  mov     eax, ebx
0x18002549f  jmp     loc_180025708
0x1800254a4  mov     r9d, 173h; unsigned int
0x1800254aa  mov     r8, r13; unsigned __int16 *
0x1800254ad  mov     rdx, [rsi+38h]; unsigned __int16 *
0x1800254b1  mov     rcx, rbx; unsigned __int16 *
0x1800254b4  call    ?Cat2Str@@YAXPEAG0PEBGK@Z; Cat2Str(ushort *,ushort *,ushort const *,ulong)
0x1800254b9  mov     r9d, [rsp+88h+arg_38]
0x1800254c1  mov     dword ptr [rsp+88h+var_68], r9d; unsigned int
0x1800254c6  mov     r9b, [rsp+88h+arg_30]; bool
0x1800254ce  mov     rbp, [rsp+88h+arg_20]
0x1800254d6  mov     r8, rbp; struct CEventCollector *
0x1800254d9  mov     rdx, r14; unsigned __int16 *
0x1800254dc  mov     rcx, rsi; this
0x1800254df  call    ?DeleteDerivedClasses@CNamespaceHandle@@IEAAJPEBGAEAVCEventCollector@@_NK@Z; CNamespaceHandle::DeleteDerivedClasses(ushort const *,CEventCollector &,bool,ulong)
0x1800254e4  mov     edi, eax
0x1800254e6  test    eax, eax
0x1800254e8  jns     short loc_180025544
0x1800254ea  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800254f0  mov     edx, edi
0x1800254f2  mov     rcx, rax
0x1800254f5  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800254fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180025502  lea     rax, WPP_GLOBAL_Control
0x180025509  cmp     rcx, rax
0x18002550c  jz      short loc_180025533
0x18002550e  test    [rcx+1Ch], r12b
0x180025512  jz      short loc_180025533
0x180025514  cmp     byte ptr [rcx+19h], 2
0x180025518  jb      short loc_180025533
0x18002551a  mov     edx, 17Eh
0x18002551f  mov     r9d, edi
0x180025522  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180025529  mov     rcx, [rcx+10h]
0x18002552d  call    WPP_SF_d
0x180025532  nop
0x180025533  mov     rcx, rbx
0x180025536  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18002553c  nop
0x18002553d  mov     eax, edi
0x18002553f  jmp     loc_180025708
0x180025544  mov     r12b, [rbp+60h]
0x180025548  mov     byte ptr [rbp+60h], 1
0x18002554c  mov     r9, rbp; struct CEventCollector *
0x18002554f  mov     r8, r15; struct _IWmiObject *
0x180025552  mov     rdx, r14; unsigned __int16 *
0x180025555  mov     rcx, rsi; this
0x180025558  call    ?DeleteClassInstances@CNamespaceHandle@@IEAAJPEBGPEAU_IWmiObject@@AEAVCEventCollector@@@Z; CNamespaceHandle::DeleteClassInstances(ushort const *,_IWmiObject *,CEventCollector &)
0x18002555d  mov     edi, eax
0x18002555f  test    eax, eax
0x180025561  jns     short loc_1800255B8
0x180025563  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180025569  mov     edx, edi
0x18002556b  mov     rcx, rax
0x18002556e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180025574  mov     rcx, cs:WPP_GLOBAL_Control
0x18002557b  lea     rax, WPP_GLOBAL_Control
0x180025582  cmp     rcx, rax
0x180025585  jz      short loc_1800255AC
0x180025587  test    byte ptr [rcx+1Ch], 1
0x18002558b  jz      short loc_1800255AC
0x18002558d  cmp     byte ptr [rcx+19h], 2
0x180025591  jb      short loc_1800255AC
0x180025593  mov     edx, 17Fh
0x180025598  mov     r9d, edi
0x18002559b  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x1800255a2  mov     rcx, [rcx+10h]
0x1800255a6  call    WPP_SF_d
0x1800255ab  nop
0x1800255ac  mov     rcx, rbx
0x1800255af  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800255b5  nop
0x1800255b6  jmp     short loc_18002553D
0x1800255b8  mov     [rbp+60h], r12b
0x1800255bc  xor     r12d, r12d
0x1800255bf  cmp     [rsp+88h+arg_28], r12b
0x1800255c7  jnz     loc_1800256C7
0x1800255cd  mov     r9, r13; unsigned __int16 *
0x1800255d0  mov     r8, r15; struct _IWmiObject *
0x1800255d3  mov     rcx, rsi; this
0x1800255d6  call    ?EraseClassRelationships@CNamespaceHandle@@IEAAJPEBGPEAU_IWmiObject@@0@Z; CNamespaceHandle::EraseClassRelationships(ushort const *,_IWmiObject *,ushort const *)
0x1800255db  mov     edi, eax
0x1800255dd  test    eax, eax
0x1800255df  jns     short loc_180025639
0x1800255e1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800255e7  mov     edx, edi
0x1800255e9  mov     rcx, rax
0x1800255ec  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800255f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800255f9  lea     rax, WPP_GLOBAL_Control
0x180025600  cmp     rcx, rax
0x180025603  jz      short loc_18002562A
0x180025605  test    byte ptr [rcx+1Ch], 1
0x180025609  jz      short loc_18002562A
0x18002560b  cmp     byte ptr [rcx+19h], 2
0x18002560f  jb      short loc_18002562A
0x180025611  mov     edx, 180h
0x180025616  mov     r9d, edi
0x180025619  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180025620  mov     rcx, [rcx+10h]
0x180025624  call    WPP_SF_d
0x180025629  nop
0x18002562a  mov     rcx, rbx
0x18002562d  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180025633  nop
0x180025634  jmp     loc_18002553D
0x180025639  mov     rdx, rbx; unsigned __int16 *
0x18002563c  lea     rcx, byte_180058AF8; this
0x180025643  call    ?DeleteObject@CFileCache@@QEAAJPEBG@Z; CFileCache::DeleteObject(ushort const *)
0x180025648  test    eax, eax
0x18002564a  jz      short loc_180025664
0x18002564c  mov     ecx, eax; int
0x18002564e  call    ?A51TranslateErrorCode@@YAJJ@Z; A51TranslateErrorCode(long)
0x180025653  mov     edi, eax
0x180025655  mov     rcx, rbx
0x180025658  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18002565e  nop
0x18002565f  jmp     loc_18002553D
0x180025664  or      rax, 0FFFFFFFFFFFFFFFFh
0x180025668  inc     rax
0x18002566b  cmp     [rbx+rax*2], r12w
0x180025670  jnz     short loc_180025668
0x180025672  mov     word ptr [rbx+rax*2-84h], 52h ; 'R'
0x18002567c  cmp     cs:dword_180058AFC, r12d
0x180025683  jnz     short loc_18002568C
0x180025685  mov     ecx, 4E7h
0x18002568a  jmp     short loc_1800256B1
0x18002568c  cmp     cs:?g_bShuttingDown@@3_NA, r12b; bool g_bShuttingDown
0x180025693  jnz     short loc_180025685
0x180025695  mov     rdx, rbx; unsigned __int16 *
0x180025698  lea     rcx, qword_180058EF8; this
0x18002569f  call    ?DeleteNode@CObjectHeap@@QEAAJPEBG@Z; CObjectHeap::DeleteNode(ushort const *)
0x1800256a4  mov     ecx, r12d
0x1800256a7  cmp     eax, 2
0x1800256aa  cmovnz  ecx, eax; int
0x1800256ad  test    ecx, ecx
0x1800256af  jz      short loc_1800256C7
0x1800256b1  call    ?A51TranslateErrorCode@@YAJJ@Z; A51TranslateErrorCode(long)
0x1800256b6  mov     edi, eax
0x1800256b8  mov     rcx, rbx
0x1800256bb  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800256c1  nop
0x1800256c2  jmp     loc_18002553D
0x1800256c7  mov     rdx, r14; unsigned __int16 *
0x1800256ca  mov     rcx, [rsi+58h]; this
0x1800256ce  call    ?InvalidateClass@CHierarchyCache@@QEAAJPEBG@Z; CHierarchyCache::InvalidateClass(ushort const *)
0x1800256d3  cmp     [rsp+88h+arg_30], r12b
0x1800256db  jnz     short loc_1800256FC
0x1800256dd  mov     [rsp+88h+var_60], r12; struct _IWmiObject *
0x1800256e2  mov     [rsp+88h+var_68], r15; struct _IWmiObject *
0x1800256e7  mov     r9, r14; unsigned __int16 *
0x1800256ea  mov     r8d, 0Bh; unsigned int
0x1800256f0  mov     rdx, rbp; struct CEventCollector *
0x1800256f3  mov     rcx, rsi; this
0x1800256f6  call    ?FireEvent@CNamespaceHandle@@IEAAJAEAVCEventCollector@@KPEBGPEAU_IWmiObject@@2@Z; CNamespaceHandle::FireEvent(CEventCollector &,ulong,ushort const *,_IWmiObject *,_IWmiObject *)
0x1800256fb  nop
0x1800256fc  mov     rcx, rbx
0x1800256ff  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180025705  nop
0x180025706  xor     eax, eax
0x180025708  add     rsp, 48h
0x18002570c  pop     r15
0x18002570e  pop     r14
0x180025710  pop     r13
0x180025712  pop     r12
0x180025714  pop     rdi
0x180025715  pop     rsi
0x180025716  pop     rbp
0x180025717  pop     rbx
0x180025718  retn
```
