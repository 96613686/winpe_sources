# CNamespaceHandle::DeleteClass(ushort const *,CEventCollector &,bool,ulong)

- ea: `0x180025180`
- end: `0x1800253cd`
- name: `?DeleteClass@CNamespaceHandle@@IEAAJPEBGAEAVCEventCollector@@_NK@Z`
- size: `589`
- prototype: `__int64 __fastcall(CNamespaceHandle *this, const unsigned __int16 *, struct CEventCollector *, bool, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001c67c`
- `0x180036248`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x180006000`
- `0x180025180`
- `0x1800253d4`
- `0x180025720`
- `0x180048010`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800251d7`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800251d7`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180025240`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800252ad`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002535e`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800253b5`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180025240`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800252ad`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002535e`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800253b5`
- `wbemcomn!GetMemLogObject` at `0x1800251f4`
- `wbemcomn!GetMemLogObject` at `0x180025261`
- `wbemcomn!GetMemLogObject` at `0x180025312`
- `wbemcomn!GetMemLogObject` at `0x1800251f4`
- `wbemcomn!GetMemLogObject` at `0x180025261`
- `wbemcomn!GetMemLogObject` at `0x180025312`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180025204`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002526c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002531d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180025204`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002526c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002531d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CNamespaceHandle::DeleteClass(
        CNamespaceHandle *this,
        const unsigned __int16 *a2,
        struct CEventCollector *a3,
        bool a4,
        unsigned int a5)
{
  CNamespaceHandle *v9; // rcx
  _WORD *v10; // rbx
  CMemoryLog *v11; // rax
  int ClassDirect; // edi
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v15; // rax
  struct _IWmiObject *v16; // rdi
  unsigned int v17; // esi
  bool v18; // [rsp+50h] [rbp-58h] BYREF
  struct _IWmiObject *v19; // [rsp+58h] [rbp-50h] BYREF
  _QWORD v20[9]; // [rsp+60h] [rbp-48h] BYREF

  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 376, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids);
  }
  v10 = CWin32DefaultArena::WbemMemAlloc(0x2E6u);
  v20[0] = v10;
  if ( v10 )
  {
    *v10 = 0;
    ClassDirect = CNamespaceHandle::ConstructClassDefFileName(v9, a2, (struct CFileName *)v20);
    if ( ClassDirect < 0 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, ClassDirect);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          378,
          WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
          (unsigned int)ClassDirect);
      }
      CWin32DefaultArena::WbemMemFree(v10);
      return (unsigned int)ClassDirect;
    }
    v19 = 0;
    v18 = 0;
    ClassDirect = CNamespaceHandle::GetClassDirect(this, a2, &IID__IWmiObject, (void **)&v19, 0, 0, 0, &v18, a5);
    if ( ClassDirect < 0 )
    {
      v15 = GetMemLogObject();
      CMemoryLog::Write(v15, ClassDirect);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          379,
          WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
          (unsigned int)ClassDirect);
      }
      CWin32DefaultArena::WbemMemFree(v10);
      return (unsigned int)ClassDirect;
    }
    v16 = v19;
    v20[1] = v19;
    v17 = CNamespaceHandle::DeleteClassInternal(this, a2, v19, v10, a3, v18, a4, a5);
    if ( v16 )
      (*(void (__fastcall **)(struct _IWmiObject *))(*(_QWORD *)v16 + 16LL))(v16);
    CWin32DefaultArena::WbemMemFree(v10);
    return v17;
  }
  else
  {
    v11 = GetMemLogObject();
    CMemoryLog::Write(v11, -2147217402);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 377, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749894LL);
    }
    CWin32DefaultArena::WbemMemFree(0);
    return 2147749894LL;
  }
}

```

## disassembly

```asm
0x180025180  push    rbx
0x180025182  push    rbp
0x180025183  push    rsi
0x180025184  push    rdi
0x180025185  push    r12
0x180025187  push    r14
0x180025189  push    r15
0x18002518b  sub     rsp, 70h
0x18002518f  mov     r15b, r9b
0x180025192  mov     r12, r8
0x180025195  mov     rsi, rdx
0x180025198  mov     r14, rcx
0x18002519b  lea     rdi, WPP_GLOBAL_Control
0x1800251a2  mov     bpl, 1
0x1800251a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800251ac  cmp     rcx, rdi
0x1800251af  jz      short loc_1800251D2
0x1800251b1  test    [rcx+1Ch], bpl
0x1800251b5  jz      short loc_1800251D2
0x1800251b7  cmp     byte ptr [rcx+19h], 5
0x1800251bb  jb      short loc_1800251D2
0x1800251bd  mov     edx, 178h
0x1800251c2  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x1800251c9  mov     rcx, [rcx+10h]
0x1800251cd  call    WPP_SF_
0x1800251d2  mov     ecx, 2E6h
0x1800251d7  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800251dd  mov     rbx, rax
0x1800251e0  mov     [rsp+0A8h+var_48], rax
0x1800251e5  test    rax, rax
0x1800251e8  jz      short loc_1800251EF
0x1800251ea  xor     eax, eax
0x1800251ec  mov     [rbx], ax
0x1800251ef  test    rbx, rbx
0x1800251f2  jnz     short loc_18002524E
0x1800251f4  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800251fa  mov     ebx, 80041006h
0x1800251ff  mov     edx, ebx
0x180025201  mov     rcx, rax
0x180025204  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002520a  mov     rcx, cs:WPP_GLOBAL_Control
0x180025211  cmp     rcx, rdi
0x180025214  jz      short loc_18002523E
0x180025216  test    [rcx+1Ch], bpl
0x18002521a  jz      short loc_18002523E
0x18002521c  cmp     byte ptr [rcx+19h], 2
0x180025220  jb      short loc_18002523E
0x180025222  mov     edx, 179h
0x180025227  mov     r9d, 80041006h
0x18002522d  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180025234  mov     rcx, [rcx+10h]
0x180025238  call    WPP_SF_d
0x18002523d  nop
0x18002523e  xor     ecx, ecx
0x180025240  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180025246  nop
0x180025247  mov     eax, ebx
0x180025249  jmp     loc_1800253BE
0x18002524e  lea     r8, [rsp+0A8h+var_48]; struct CFileName *
0x180025253  mov     rdx, rsi; unsigned __int16 *
0x180025256  call    ?ConstructClassDefFileName@CNamespaceHandle@@IEAAJPEBGAEAVCFileName@@@Z; CNamespaceHandle::ConstructClassDefFileName(ushort const *,CFileName &)
0x18002525b  mov     edi, eax
0x18002525d  test    eax, eax
0x18002525f  jns     short loc_1800252BB
0x180025261  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180025267  mov     edx, edi
0x180025269  mov     rcx, rax
0x18002526c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180025272  mov     rcx, cs:WPP_GLOBAL_Control
0x180025279  lea     rax, WPP_GLOBAL_Control
0x180025280  cmp     rcx, rax
0x180025283  jz      short loc_1800252AA
0x180025285  test    [rcx+1Ch], bpl
0x180025289  jz      short loc_1800252AA
0x18002528b  cmp     byte ptr [rcx+19h], 2
0x18002528f  jb      short loc_1800252AA
0x180025291  mov     edx, 17Ah
0x180025296  mov     r9d, edi
0x180025299  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x1800252a0  mov     rcx, [rcx+10h]
0x1800252a4  call    WPP_SF_d
0x1800252a9  nop
0x1800252aa  mov     rcx, rbx
0x1800252ad  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800252b3  nop
0x1800252b4  mov     eax, edi
0x1800252b6  jmp     loc_1800253BE
0x1800252bb  mov     [rsp+0A8h+var_50], 0
0x1800252c4  mov     [rsp+0A8h+var_58], 0
0x1800252c9  mov     ebp, [rsp+0A8h+arg_20]
0x1800252d0  mov     [rsp+0A8h+var_68], ebp; unsigned int
0x1800252d4  lea     rax, [rsp+0A8h+var_58]
0x1800252d9  mov     [rsp+0A8h+var_70], rax; bool *
0x1800252de  mov     [rsp+0A8h+var_78], 0; bool *
0x1800252e7  mov     [rsp+0A8h+var_80], 0; __int64 *
0x1800252f0  mov     byte ptr [rsp+0A8h+var_88], 0; bool
0x1800252f5  lea     r9, [rsp+0A8h+var_50]; void **
0x1800252fa  lea     r8, IID__IWmiObject; struct _GUID *
0x180025301  mov     rdx, rsi; unsigned __int16 *
0x180025304  mov     rcx, r14; this
0x180025307  call    ?GetClassDirect@CNamespaceHandle@@IEAAJPEBGAEBU_GUID@@PEAPEAX_NPEA_JPEA_N5K@Z; CNamespaceHandle::GetClassDirect(ushort const *,_GUID const &,void * *,bool,__int64 *,bool *,bool *,ulong)
0x18002530c  mov     edi, eax
0x18002530e  test    eax, eax
0x180025310  jns     short loc_18002536A
0x180025312  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180025318  mov     edx, edi
0x18002531a  mov     rcx, rax
0x18002531d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180025323  mov     rcx, cs:WPP_GLOBAL_Control
0x18002532a  lea     rax, WPP_GLOBAL_Control
0x180025331  cmp     rcx, rax
0x180025334  jz      short loc_18002535B
0x180025336  test    byte ptr [rcx+1Ch], 1
0x18002533a  jz      short loc_18002535B
0x18002533c  cmp     byte ptr [rcx+19h], 2
0x180025340  jb      short loc_18002535B
0x180025342  mov     edx, 17Bh
0x180025347  mov     r9d, edi
0x18002534a  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180025351  mov     rcx, [rcx+10h]
0x180025355  call    WPP_SF_d
0x18002535a  nop
0x18002535b  mov     rcx, rbx
0x18002535e  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180025364  nop
0x180025365  jmp     loc_1800252B4
0x18002536a  mov     rdi, [rsp+0A8h+var_50]
0x18002536f  mov     [rsp+0A8h+var_40], rdi
0x180025374  mov     al, [rsp+0A8h+var_58]
0x180025378  mov     dword ptr [rsp+0A8h+var_70], ebp; unsigned int
0x18002537c  mov     byte ptr [rsp+0A8h+var_78], r15b; bool
0x180025381  mov     byte ptr [rsp+0A8h+var_80], al; bool
0x180025385  mov     [rsp+0A8h+var_88], r12; struct CEventCollector *
0x18002538a  mov     r9, rbx; unsigned __int16 *
0x18002538d  mov     r8, rdi; struct _IWmiObject *
0x180025390  mov     rdx, rsi; unsigned __int16 *
0x180025393  mov     rcx, r14; this
0x180025396  call    ?DeleteClassInternal@CNamespaceHandle@@IEAAJPEBGPEAU_IWmiObject@@0AEAVCEventCollector@@_N3K@Z; CNamespaceHandle::DeleteClassInternal(ushort const *,_IWmiObject *,ushort const *,CEventCollector &,bool,bool,ulong)
0x18002539b  mov     esi, eax
0x18002539d  test    rdi, rdi
0x1800253a0  jz      short loc_1800253B2
0x1800253a2  mov     rcx, [rdi]
0x1800253a5  mov     rax, [rcx+10h]
0x1800253a9  mov     rcx, rdi
0x1800253ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800253b1  nop
0x1800253b2  mov     rcx, rbx
0x1800253b5  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800253bb  nop
0x1800253bc  mov     eax, esi
0x1800253be  add     rsp, 70h
0x1800253c2  pop     r15
0x1800253c4  pop     r14
0x1800253c6  pop     r12
0x1800253c8  pop     rdi
0x1800253c9  pop     rsi
0x1800253ca  pop     rbp
0x1800253cb  pop     rbx
0x1800253cc  retn
```
