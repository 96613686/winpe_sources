# CNamespaceHandle::ConstructReferenceDir(ushort const *,CFileName &)

- ea: `0x18002435c`
- end: `0x1800246be`
- name: `?ConstructReferenceDir@CNamespaceHandle@@IEAAJPEBGAEAVCFileName@@@Z`
- size: `866`
- prototype: `__int64 __fastcall(CRepository **this, const unsigned __int16 *, struct CFileName *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800329f4`

## callees

- `0x1800012b8`
- `0x1800012f4`
- `0x1800013a0`
- `0x1800014b0`
- `0x180004310`
- `0x18002435c`
- `0x1800246c4`
- `0x18003a3d4`
- `0x180048010`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800243e2`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800243e2`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800244d5`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800245e0`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800245ea`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800245f4`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002464b`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180024655`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002465f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002468f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180024699`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800246a3`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800244d5`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800245e0`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800245ea`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800245f4`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002464b`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180024655`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002465f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002468f`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180024699`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800246a3`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x180024507`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x180024570`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x180024507`
- `wbemcomn!??BWString@@QEAAPEAGXZ` at `0x180024570`
- `wbemcomn!GetMemLogObject` at `0x1800243f0`
- `wbemcomn!GetMemLogObject` at `0x180024489`
- `wbemcomn!GetMemLogObject` at `0x18002453c`
- `wbemcomn!GetMemLogObject` at `0x18002459b`
- `wbemcomn!GetMemLogObject` at `0x1800243f0`
- `wbemcomn!GetMemLogObject` at `0x180024489`
- `wbemcomn!GetMemLogObject` at `0x18002453c`
- `wbemcomn!GetMemLogObject` at `0x18002459b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180024400`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180024494`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180024548`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800245a6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180024400`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180024494`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180024548`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800245a6`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CNamespaceHandle::ConstructReferenceDir(
        CRepository **this,
        const unsigned __int16 *a2,
        struct CFileName *a3)
{
  __int64 v6; // rax
  unsigned __int64 v7; // rax
  unsigned __int64 v8; // r14
  struct CNamespaceHandle *v9; // rax
  struct CNamespaceHandle *v10; // rdi
  CMemoryLog *MemLogObject; // rax
  unsigned int NamespaceHandle; // ebx
  int v14; // esi
  CMemoryLog *v15; // rax
  unsigned __int16 *v16; // r14
  unsigned __int16 *v17; // rsi
  char *v18; // r12
  const unsigned __int16 *v19; // rax
  CMemoryLog *v20; // rax
  __int64 v21; // rax
  CMemoryLog *v22; // rax
  unsigned int v23; // r15d
  unsigned __int16 *v24; // [rsp+40h] [rbp-38h] BYREF
  unsigned __int16 *v25; // [rsp+48h] [rbp-30h] BYREF
  struct CNamespaceHandle *v26[5]; // [rsp+50h] [rbp-28h] BYREF
  bool v27; // [rsp+D8h] [rbp+60h] BYREF

  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 221, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids);
  }
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = v6 + 1;
  if ( v7 <= 2 )
    LODWORD(v7) = 2;
  v8 = (unsigned int)v7;
  v9 = (struct CNamespaceHandle *)CWin32DefaultArena::WbemMemAlloc(saturated_mul((unsigned int)v7, 2u));
  v10 = v9;
  if ( !v9 )
  {
    MemLogObject = GetMemLogObject();
    NamespaceHandle = -2147217402;
    CMemoryLog::Write(MemLogObject, -2147217402);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 222, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749894LL);
    }
    return NamespaceHandle;
  }
  v26[1] = v9;
  v25 = 0;
  v24 = 0;
  v27 = 0;
  v14 = CNamespaceHandle::ComputeKeyFromPath((CNamespaceHandle *)this, a2, (unsigned __int16 *)v9, v8, &v25, &v27, &v24);
  if ( v14 >= 0 )
  {
    v16 = v25;
    v26[2] = (struct CNamespaceHandle *)v25;
    v17 = v24;
    v26[3] = (struct CNamespaceHandle *)v24;
    v26[0] = 0;
    if ( v24
      && (v18 = (char *)(this + 4),
          v19 = (const unsigned __int16 *)WString::operator unsigned short *(this + 4),
          (unsigned int)wbem_wcsicmp(v24, v19)) )
    {
      NamespaceHandle = CRepository::GetNamespaceHandle(this[3], v24, v26);
      if ( (NamespaceHandle & 0x80000000) != 0 )
      {
        v20 = GetMemLogObject();
        CMemoryLog::Write(v20, -1);
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v21 = WString::operator unsigned short *(v18);
          WPP_SF_SS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            224,
            (unsigned int)WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
            (_DWORD)v24,
            v21);
        }
        v22 = GetMemLogObject();
        CMemoryLog::Write(v22, NamespaceHandle);
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            225,
            WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
            NamespaceHandle);
        }
        CWin32DefaultArena::WbemMemFree(v17);
        CWin32DefaultArena::WbemMemFree(v16);
        CWin32DefaultArena::WbemMemFree(v10);
        return NamespaceHandle;
      }
      this = (CRepository **)v26[0];
    }
    else
    {
      (*((void (__fastcall **)(CRepository **))*this + 1))(this);
    }
    v26[0] = (struct CNamespaceHandle *)this;
    if ( v27 )
    {
      v23 = CNamespaceHandle::ConstructReferenceDirFromKey((CNamespaceHandle *)this, 0, v25, a3);
      if ( this )
        (*((void (__fastcall **)(CRepository **))*this + 2))(this);
    }
    else
    {
      v23 = CNamespaceHandle::ConstructReferenceDirFromKey(
              (CNamespaceHandle *)this,
              v25,
              (const unsigned __int16 *)v10,
              a3);
      if ( this )
        (*((void (__fastcall **)(CRepository **))*this + 2))(this);
    }
    CWin32DefaultArena::WbemMemFree(v17);
    CWin32DefaultArena::WbemMemFree(v16);
    CWin32DefaultArena::WbemMemFree(v10);
    return v23;
  }
  else
  {
    v15 = GetMemLogObject();
    CMemoryLog::Write(v15, v14);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        223,
        WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
        (unsigned int)v14);
    }
    CWin32DefaultArena::WbemMemFree(v10);
    return (unsigned int)v14;
  }
}

```

## disassembly

```asm
0x18002435c  push    rbp
0x18002435e  push    rbx
0x18002435f  push    rsi
0x180024360  push    rdi
0x180024361  push    r12
0x180024363  push    r13
0x180024365  push    r14
0x180024367  push    r15
0x180024369  mov     rbp, rsp
0x18002436c  sub     rsp, 78h
0x180024370  mov     r15, r8
0x180024373  mov     rsi, rdx
0x180024376  mov     rbx, rcx
0x180024379  lea     rax, WPP_GLOBAL_Control
0x180024380  mov     rcx, cs:WPP_GLOBAL_Control
0x180024387  cmp     rcx, rax
0x18002438a  jz      short loc_1800243AD
0x18002438c  test    byte ptr [rcx+1Ch], 1
0x180024390  jz      short loc_1800243AD
0x180024392  cmp     byte ptr [rcx+19h], 5
0x180024396  jb      short loc_1800243AD
0x180024398  mov     edx, 0DDh
0x18002439d  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x1800243a4  mov     rcx, [rcx+10h]
0x1800243a8  call    WPP_SF_
0x1800243ad  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800243b1  mov     rax, rcx
0x1800243b4  xor     r13d, r13d
0x1800243b7  inc     rax
0x1800243ba  cmp     [rsi+rax*2], r13w
0x1800243bf  jnz     short loc_1800243B7
0x1800243c1  inc     rax
0x1800243c4  mov     r12d, 2
0x1800243ca  cmp     rax, r12
0x1800243cd  ja      short loc_1800243D2
0x1800243cf  mov     eax, r12d
0x1800243d2  mov     r14d, eax
0x1800243d5  mov     rax, r12
0x1800243d8  mul     r14
0x1800243db  cmovb   rax, rcx
0x1800243df  mov     rcx, rax
0x1800243e2  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800243e8  mov     rdi, rax
0x1800243eb  test    rax, rax
0x1800243ee  jnz     short loc_180024447
0x1800243f0  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800243f6  mov     ebx, 80041006h
0x1800243fb  mov     edx, ebx
0x1800243fd  mov     rcx, rax
0x180024400  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180024406  mov     rcx, cs:WPP_GLOBAL_Control
0x18002440d  lea     r15, WPP_GLOBAL_Control
0x180024414  cmp     rcx, r15
0x180024417  jz      short loc_180024440
0x180024419  test    byte ptr [rcx+1Ch], 1
0x18002441d  jz      short loc_180024440
0x18002441f  cmp     [rcx+19h], r12b
0x180024423  jb      short loc_180024440
0x180024425  mov     edx, 0DEh
0x18002442a  mov     r9d, 80041006h
0x180024430  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180024437  mov     rcx, [rcx+10h]
0x18002443b  call    WPP_SF_d
0x180024440  mov     eax, ebx
0x180024442  jmp     loc_1800246AD
0x180024447  mov     [rbp+var_20], rdi
0x18002444b  mov     [rbp+var_30], r13
0x18002444f  mov     [rbp+var_38], r13
0x180024453  mov     [rbp+arg_18], r13b
0x180024457  lea     rax, [rbp+var_38]
0x18002445b  mov     [rsp+78h+var_48], rax; unsigned __int16 **
0x180024460  lea     rax, [rbp+arg_18]
0x180024464  mov     [rsp+78h+var_50], rax; bool *
0x180024469  lea     rax, [rbp+var_30]
0x18002446d  mov     [rsp+78h+var_58], rax; unsigned __int16 **
0x180024472  mov     r9, r14; unsigned __int64
0x180024475  mov     r8, rdi; unsigned __int16 *
0x180024478  mov     rdx, rsi; unsigned __int16 *
0x18002447b  mov     rcx, rbx; this
0x18002447e  call    ?ComputeKeyFromPath@CNamespaceHandle@@IEAAJPEBGPEAG_KPEAPEAGPEA_N3@Z; CNamespaceHandle::ComputeKeyFromPath(ushort const *,ushort *,unsigned __int64,ushort * *,bool *,ushort * *)
0x180024483  mov     esi, eax
0x180024485  test    eax, eax
0x180024487  jns     short loc_1800244E3
0x180024489  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002448f  mov     edx, esi
0x180024491  mov     rcx, rax
0x180024494  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002449a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800244a1  lea     r15, WPP_GLOBAL_Control
0x1800244a8  cmp     rcx, r15
0x1800244ab  jz      short loc_1800244D2
0x1800244ad  test    byte ptr [rcx+1Ch], 1
0x1800244b1  jz      short loc_1800244D2
0x1800244b3  cmp     [rcx+19h], r12b
0x1800244b7  jb      short loc_1800244D2
0x1800244b9  mov     edx, 0DFh
0x1800244be  mov     r9d, esi
0x1800244c1  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x1800244c8  mov     rcx, [rcx+10h]
0x1800244cc  call    WPP_SF_d
0x1800244d1  nop
0x1800244d2  mov     rcx, rdi
0x1800244d5  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800244db  nop
0x1800244dc  mov     eax, esi
0x1800244de  jmp     loc_1800246AD
0x1800244e3  mov     r14, [rbp+var_30]
0x1800244e7  mov     [rbp+var_18], r14
0x1800244eb  mov     rsi, [rbp+var_38]
0x1800244ef  mov     [rbp+var_10], rsi
0x1800244f3  mov     [rbp+var_28], r13
0x1800244f7  test    rsi, rsi
0x1800244fa  jz      loc_180024606
0x180024500  lea     r12, [rbx+20h]
0x180024504  mov     rcx, r12
0x180024507  call    cs:__imp_??BWString@@QEAAPEAGXZ; WString::operator ushort *(void)
0x18002450d  mov     rdx, rax; unsigned __int16 *
0x180024510  mov     rcx, [rbp+var_38]; unsigned __int16 *
0x180024514  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x180024519  test    eax, eax
0x18002451b  jz      loc_180024606
0x180024521  lea     r8, [rbp+var_28]; struct CNamespaceHandle **
0x180024525  mov     rdx, [rbp+var_38]; unsigned __int16 *
0x180024529  mov     rcx, [rbx+18h]; this
0x18002452d  call    ?GetNamespaceHandle@CRepository@@QEAAJPEBGPEAPEAVCNamespaceHandle@@@Z; CRepository::GetNamespaceHandle(ushort const *,CNamespaceHandle * *)
0x180024532  mov     ebx, eax
0x180024534  test    eax, eax
0x180024536  jns     loc_180024600
0x18002453c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180024542  or      edx, 0FFFFFFFFh
0x180024545  mov     rcx, rax
0x180024548  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002454e  mov     rax, cs:WPP_GLOBAL_Control
0x180024555  lea     r15, WPP_GLOBAL_Control
0x18002455c  cmp     rax, r15
0x18002455f  jz      short loc_18002459B
0x180024561  test    byte ptr [rax+1Ch], 1
0x180024565  jz      short loc_18002459B
0x180024567  cmp     byte ptr [rax+19h], 2
0x18002456b  jb      short loc_18002459B
0x18002456d  mov     rcx, r12
0x180024570  call    cs:__imp_??BWString@@QEAAPEAGXZ; WString::operator ushort *(void)
0x180024576  mov     edx, 0E0h
0x18002457b  mov     [rsp+78h+var_58], rax
0x180024580  mov     r9, [rbp+var_38]
0x180024584  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18002458b  mov     rcx, cs:WPP_GLOBAL_Control
0x180024592  mov     rcx, [rcx+10h]
0x180024596  call    WPP_SF_SS
0x18002459b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800245a1  mov     edx, ebx
0x1800245a3  mov     rcx, rax
0x1800245a6  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800245ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800245b3  cmp     rcx, r15
0x1800245b6  jz      short loc_1800245DD
0x1800245b8  test    byte ptr [rcx+1Ch], 1
0x1800245bc  jz      short loc_1800245DD
0x1800245be  cmp     byte ptr [rcx+19h], 2
0x1800245c2  jb      short loc_1800245DD
0x1800245c4  mov     edx, 0E1h
0x1800245c9  mov     r9d, ebx
0x1800245cc  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x1800245d3  mov     rcx, [rcx+10h]
0x1800245d7  call    WPP_SF_d
0x1800245dc  nop
0x1800245dd  mov     rcx, rsi
0x1800245e0  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800245e6  nop
0x1800245e7  mov     rcx, r14
0x1800245ea  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800245f0  nop
0x1800245f1  mov     rcx, rdi
0x1800245f4  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800245fa  nop
0x1800245fb  jmp     loc_180024440
0x180024600  mov     rbx, [rbp+var_28]
0x180024604  jmp     short loc_180024615
0x180024606  mov     rax, [rbx]
0x180024609  mov     rcx, rbx
0x18002460c  mov     rax, [rax+8]
0x180024610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024615  mov     [rbp+var_28], rbx
0x180024619  mov     r9, r15; struct CFileName *
0x18002461c  mov     rcx, rbx; this
0x18002461f  cmp     [rbp+arg_18], r13b
0x180024623  jz      short loc_180024668
0x180024625  mov     r8, [rbp+var_30]; unsigned __int16 *
0x180024629  xor     edx, edx; unsigned __int16 *
0x18002462b  call    ?ConstructReferenceDirFromKey@CNamespaceHandle@@IEAAJPEBG0AEAVCFileName@@@Z; CNamespaceHandle::ConstructReferenceDirFromKey(ushort const *,ushort const *,CFileName &)
0x180024630  mov     r15d, eax
0x180024633  test    rbx, rbx
0x180024636  jz      short loc_180024648
0x180024638  mov     rdx, [rbx]
0x18002463b  mov     rcx, rbx
0x18002463e  mov     rax, [rdx+10h]
0x180024642  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024647  nop
0x180024648  mov     rcx, rsi
0x18002464b  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180024651  nop
0x180024652  mov     rcx, r14
0x180024655  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18002465b  nop
0x18002465c  mov     rcx, rdi
0x18002465f  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180024665  nop
0x180024666  jmp     short loc_1800246AA
0x180024668  mov     r8, rdi; unsigned __int16 *
0x18002466b  mov     rdx, [rbp+var_30]; unsigned __int16 *
0x18002466f  call    ?ConstructReferenceDirFromKey@CNamespaceHandle@@IEAAJPEBG0AEAVCFileName@@@Z; CNamespaceHandle::ConstructReferenceDirFromKey(ushort const *,ushort const *,CFileName &)
0x180024674  mov     r15d, eax
0x180024677  test    rbx, rbx
0x18002467a  jz      short loc_18002468C
0x18002467c  mov     rcx, [rbx]
0x18002467f  mov     rax, [rcx+10h]
0x180024683  mov     rcx, rbx
0x180024686  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002468b  nop
0x18002468c  mov     rcx, rsi
0x18002468f  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180024695  nop
0x180024696  mov     rcx, r14
0x180024699  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18002469f  nop
0x1800246a0  mov     rcx, rdi
0x1800246a3  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800246a9  nop
0x1800246aa  mov     eax, r15d
0x1800246ad  add     rsp, 78h
0x1800246b1  pop     r15
0x1800246b3  pop     r14
0x1800246b5  pop     r13
0x1800246b7  pop     r12
0x1800246b9  pop     rdi
0x1800246ba  pop     rsi
0x1800246bb  pop     rbx
0x1800246bc  pop     rbp
0x1800246bd  retn
```
