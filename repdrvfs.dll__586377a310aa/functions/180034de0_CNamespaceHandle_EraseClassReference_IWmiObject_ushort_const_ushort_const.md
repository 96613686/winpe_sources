# CNamespaceHandle::EraseClassReference(_IWmiObject *,ushort const *,ushort const *)

- ea: `0x180034de0`
- end: `0x180035172`
- name: `?EraseClassReference@CNamespaceHandle@@IEAAJPEAU_IWmiObject@@PEBG1@Z`
- size: `914`
- prototype: `__int64 __fastcall(CNamespaceHandle *__hidden this, struct _IWmiObject *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180035178`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x18001e134`
- `0x180023bf0`
- `0x180027780`
- `0x180032690`
- `0x180034de0`
- `0x180048010`

## import_xrefs

- `msvcrt!wcschr` at `0x180035003`
- `msvcrt!wcschr` at `0x180035003`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180034eeb`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180034eeb`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180034fed`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180035014`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180035084`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003508e`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180035104`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003510e`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180035139`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180035143`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180035152`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003515c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180034fed`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180035014`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180035084`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003508e`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180035104`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003510e`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180035139`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180035143`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180035152`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003515c`
- `wbemcomn!GetMemLogObject` at `0x180034e97`
- `wbemcomn!GetMemLogObject` at `0x180034ef9`
- `wbemcomn!GetMemLogObject` at `0x180034fa1`
- `wbemcomn!GetMemLogObject` at `0x180035033`
- `wbemcomn!GetMemLogObject` at `0x1800350b8`
- `wbemcomn!GetMemLogObject` at `0x180034e97`
- `wbemcomn!GetMemLogObject` at `0x180034ef9`
- `wbemcomn!GetMemLogObject` at `0x180034fa1`
- `wbemcomn!GetMemLogObject` at `0x180035033`
- `wbemcomn!GetMemLogObject` at `0x1800350b8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180034ea5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180034f07`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180034fac`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180035041`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800350c3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180034ea5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180034f07`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180034fac`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180035041`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800350c3`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CNamespaceHandle::EraseClassReference(
        CNamespaceHandle *this,
        struct _IWmiObject *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  CMemoryLog *MemLogObject; // rax
  CVarObjHeap *v9; // rcx
  __int64 v10; // rdx
  unsigned __int16 *v11; // rax
  unsigned __int16 *v12; // rdi
  CMemoryLog *v13; // rax
  unsigned int v15; // ebx
  CMemoryLog *v16; // rax
  wchar_t *v17; // rbx
  const unsigned __int16 *v18; // r9
  unsigned __int16 *v19; // rsi
  CMemoryLog *v20; // rax
  CMemoryLog *v21; // rax
  unsigned int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // r8
  int v25; // [rsp+50h] [rbp-28h] BYREF
  int v26; // [rsp+54h] [rbp-24h] BYREF
  unsigned __int16 *v27[4]; // [rsp+58h] [rbp-20h] BYREF
  unsigned int v28; // [rsp+B8h] [rbp+40h] BYREF

  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 424, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids);
  }
  v28 = 0;
  v25 = 0;
  v26 = 0;
  (*(void (__fastcall **)(struct _IWmiObject *, const unsigned __int16 *, const wchar_t *, _QWORD, _DWORD, int *, int *, unsigned int *, _QWORD))(*(_QWORD *)a2 + 424LL))(
    a2,
    a4,
    L"CIMTYPE",
    0,
    0,
    &v26,
    &v25,
    &v28,
    0);
  if ( !v28 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2147217402);
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147749894LL;
    }
    v10 = 425;
LABEL_15:
    WPP_SF_d(*((_QWORD *)v9 + 2), v10, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749894LL);
    return 2147749894LL;
  }
  v11 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v28, 2u));
  v12 = v11;
  if ( !v11 )
  {
    v13 = GetMemLogObject();
    CMemoryLog::Write(v13, -2147217402);
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147749894LL;
    }
    v10 = 426;
    goto LABEL_15;
  }
  v27[1] = v11;
  v15 = (*(__int64 (__fastcall **)(struct _IWmiObject *, const unsigned __int16 *, const wchar_t *, _QWORD, unsigned int, int *, int *, unsigned int *, unsigned __int16 *))(*(_QWORD *)a2 + 424LL))(
          a2,
          a4,
          L"CIMTYPE",
          0,
          v28,
          &v26,
          &v25,
          &v28,
          v11);
  if ( (v15 & 0x80000000) != 0 )
  {
    v16 = GetMemLogObject();
    CMemoryLog::Write(v16, v15);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 427, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, v15);
    }
    CWin32DefaultArena::WbemMemFree(v12);
    return v15;
  }
  v17 = wcschr(v12, 0x3Au);
  if ( v17 )
  {
    CFileName::CFileName((CFileName *)v27);
    v19 = v27[0];
    if ( !v27[0] )
    {
      v20 = GetMemLogObject();
      CMemoryLog::Write(v20, -2147217402);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          428,
          WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
          2147749894LL);
      }
      CWin32DefaultArena::WbemMemFree(0);
      CWin32DefaultArena::WbemMemFree(v12);
      return 2147749894LL;
    }
    v15 = CNamespaceHandle::ConstructClassReferenceFileName(this, v17 + 1, a3, v18, (struct CFileName *)v27);
    if ( (v15 & 0x80000000) != 0 )
    {
      v21 = GetMemLogObject();
      CMemoryLog::Write(v21, v15);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 429, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, v15);
      }
      CWin32DefaultArena::WbemMemFree(v19);
      CWin32DefaultArena::WbemMemFree(v12);
      return v15;
    }
    v22 = CFileCache::DeleteLink((CFileCache *)byte_180058AF8, v19);
    if ( v22 )
    {
      v15 = A51TranslateErrorCode(v22, v23, v24);
      CWin32DefaultArena::WbemMemFree(v19);
      CWin32DefaultArena::WbemMemFree(v12);
      return v15;
    }
    CWin32DefaultArena::WbemMemFree(v19);
    CWin32DefaultArena::WbemMemFree(v12);
  }
  else
  {
    CWin32DefaultArena::WbemMemFree(v12);
  }
  return 0;
}

```

## disassembly

```asm
0x180034de0  push    rbp
0x180034de2  push    rbx
0x180034de3  push    rsi
0x180034de4  push    rdi
0x180034de5  push    r14
0x180034de7  push    r15
0x180034de9  mov     rbp, rsp
0x180034dec  sub     rsp, 78h
0x180034df0  mov     rsi, r9
0x180034df3  mov     r14, r8
0x180034df6  mov     rbx, rdx
0x180034df9  mov     r15, rcx
0x180034dfc  lea     rdi, WPP_GLOBAL_Control
0x180034e03  mov     rcx, cs:WPP_GLOBAL_Control
0x180034e0a  cmp     rcx, rdi
0x180034e0d  jz      short loc_180034E30
0x180034e0f  test    byte ptr [rcx+1Ch], 1
0x180034e13  jz      short loc_180034E30
0x180034e15  cmp     byte ptr [rcx+19h], 5
0x180034e19  jb      short loc_180034E30
0x180034e1b  mov     edx, 1A8h
0x180034e20  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180034e27  mov     rcx, [rcx+10h]
0x180034e2b  call    WPP_SF_
0x180034e30  mov     [rbp+arg_8], 0
0x180034e37  mov     [rbp+var_28], 0
0x180034e3e  mov     [rbp+var_24], 0
0x180034e45  mov     rax, [rbx]
0x180034e48  mov     [rsp+78h+var_38], 0
0x180034e51  lea     rcx, [rbp+arg_8]
0x180034e55  mov     [rsp+78h+var_40], rcx
0x180034e5a  lea     rcx, [rbp+var_28]
0x180034e5e  mov     [rsp+78h+var_48], rcx
0x180034e63  lea     rcx, [rbp+var_24]
0x180034e67  mov     [rsp+78h+var_50], rcx
0x180034e6c  mov     dword ptr [rsp+78h+var_58], 0
0x180034e74  xor     r9d, r9d
0x180034e77  lea     r8, aCimtype; "CIMTYPE"
0x180034e7e  mov     rdx, rsi
0x180034e81  mov     rcx, rbx
0x180034e84  mov     rax, [rax+1A8h]
0x180034e8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034e90  mov     eax, [rbp+arg_8]
0x180034e93  test    eax, eax
0x180034e95  jnz     short loc_180034ED2
0x180034e97  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180034e9d  mov     edx, 80041006h
0x180034ea2  mov     rcx, rax
0x180034ea5  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180034eab  mov     rcx, cs:WPP_GLOBAL_Control
0x180034eb2  cmp     rcx, rdi
0x180034eb5  jz      loc_180034F47
0x180034ebb  test    byte ptr [rcx+1Ch], 1
0x180034ebf  jz      loc_180034F47
0x180034ec5  cmp     byte ptr [rcx+19h], 2
0x180034ec9  jb      short loc_180034F47
0x180034ecb  mov     edx, 1A9h
0x180034ed0  jmp     short loc_180034F31
0x180034ed2  mov     rcx, rax
0x180034ed5  mov     eax, 2
0x180034eda  mul     rcx
0x180034edd  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180034ee4  cmovb   rax, rcx
0x180034ee8  mov     rcx, rax
0x180034eeb  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180034ef1  mov     rdi, rax
0x180034ef4  test    rax, rax
0x180034ef7  jnz     short loc_180034F51
0x180034ef9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180034eff  mov     edx, 80041006h
0x180034f04  mov     rcx, rax
0x180034f07  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180034f0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180034f14  lea     rax, WPP_GLOBAL_Control
0x180034f1b  cmp     rcx, rax
0x180034f1e  jz      short loc_180034F47
0x180034f20  test    byte ptr [rcx+1Ch], 1
0x180034f24  jz      short loc_180034F47
0x180034f26  cmp     byte ptr [rcx+19h], 2
0x180034f2a  jb      short loc_180034F47
0x180034f2c  mov     edx, 1AAh
0x180034f31  mov     r9d, 80041006h
0x180034f37  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180034f3e  mov     rcx, [rcx+10h]
0x180034f42  call    WPP_SF_d
0x180034f47  mov     eax, 80041006h
0x180034f4c  jmp     loc_180035165
0x180034f51  mov     [rbp+var_18], rdi
0x180034f55  mov     rax, [rbx]
0x180034f58  mov     [rsp+78h+var_38], rdi
0x180034f5d  lea     rcx, [rbp+arg_8]
0x180034f61  mov     [rsp+78h+var_40], rcx
0x180034f66  lea     rcx, [rbp+var_28]
0x180034f6a  mov     [rsp+78h+var_48], rcx
0x180034f6f  lea     rcx, [rbp+var_24]
0x180034f73  mov     [rsp+78h+var_50], rcx
0x180034f78  mov     ecx, [rbp+arg_8]
0x180034f7b  mov     dword ptr [rsp+78h+var_58], ecx
0x180034f7f  xor     r9d, r9d
0x180034f82  lea     r8, aCimtype; "CIMTYPE"
0x180034f89  mov     rdx, rsi
0x180034f8c  mov     rcx, rbx
0x180034f8f  mov     rax, [rax+1A8h]
0x180034f96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034f9b  mov     ebx, eax
0x180034f9d  test    eax, eax
0x180034f9f  jns     short loc_180034FFB
0x180034fa1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180034fa7  mov     edx, ebx
0x180034fa9  mov     rcx, rax
0x180034fac  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180034fb2  mov     rcx, cs:WPP_GLOBAL_Control
0x180034fb9  lea     rax, WPP_GLOBAL_Control
0x180034fc0  cmp     rcx, rax
0x180034fc3  jz      short loc_180034FEA
0x180034fc5  test    byte ptr [rcx+1Ch], 1
0x180034fc9  jz      short loc_180034FEA
0x180034fcb  cmp     byte ptr [rcx+19h], 2
0x180034fcf  jb      short loc_180034FEA
0x180034fd1  mov     edx, 1ABh
0x180034fd6  mov     r9d, ebx
0x180034fd9  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180034fe0  mov     rcx, [rcx+10h]
0x180034fe4  call    WPP_SF_d
0x180034fe9  nop
0x180034fea  mov     rcx, rdi
0x180034fed  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180034ff3  nop
0x180034ff4  mov     eax, ebx
0x180034ff6  jmp     loc_180035165
0x180034ffb  mov     edx, 3Ah ; ':'; Ch
0x180035000  mov     rcx, rdi; Str
0x180035003  call    cs:__imp_wcschr
0x180035009  mov     rbx, rax
0x18003500c  test    rax, rax
0x18003500f  jnz     short loc_180035020
0x180035011  mov     rcx, rdi
0x180035014  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18003501a  nop
0x18003501b  jmp     loc_180035163
0x180035020  lea     rcx, [rbp+var_20]; this
0x180035024  call    ??0CFileName@@QEAA@XZ; CFileName::CFileName(void)
0x180035029  nop
0x18003502a  mov     rsi, [rbp+var_20]
0x18003502e  test    rsi, rsi
0x180035031  jnz     short loc_18003509A
0x180035033  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180035039  mov     edx, 80041006h
0x18003503e  mov     rcx, rax
0x180035041  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180035047  mov     rcx, cs:WPP_GLOBAL_Control
0x18003504e  lea     rax, WPP_GLOBAL_Control
0x180035055  cmp     rcx, rax
0x180035058  jz      short loc_180035082
0x18003505a  test    byte ptr [rcx+1Ch], 1
0x18003505e  jz      short loc_180035082
0x180035060  cmp     byte ptr [rcx+19h], 2
0x180035064  jb      short loc_180035082
0x180035066  mov     edx, 1ACh
0x18003506b  mov     r9d, 80041006h
0x180035071  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180035078  mov     rcx, [rcx+10h]
0x18003507c  call    WPP_SF_d
0x180035081  nop
0x180035082  xor     ecx, ecx
0x180035084  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18003508a  nop
0x18003508b  mov     rcx, rdi
0x18003508e  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180035094  nop
0x180035095  jmp     loc_180034F47
0x18003509a  lea     rdx, [rbx+2]; unsigned __int16 *
0x18003509e  lea     rax, [rbp+var_20]
0x1800350a2  mov     [rsp+78h+var_58], rax; struct CFileName *
0x1800350a7  mov     r8, r14; unsigned __int16 *
0x1800350aa  mov     rcx, r15; this
0x1800350ad  call    ?ConstructClassReferenceFileName@CNamespaceHandle@@IEAAJPEBG00AEAVCFileName@@@Z; CNamespaceHandle::ConstructClassReferenceFileName(ushort const *,ushort const *,ushort const *,CFileName &)
0x1800350b2  mov     ebx, eax
0x1800350b4  test    eax, eax
0x1800350b6  jns     short loc_18003511A
0x1800350b8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800350be  mov     edx, ebx
0x1800350c0  mov     rcx, rax
0x1800350c3  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800350c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800350d0  lea     rax, WPP_GLOBAL_Control
0x1800350d7  cmp     rcx, rax
0x1800350da  jz      short loc_180035101
0x1800350dc  test    byte ptr [rcx+1Ch], 1
0x1800350e0  jz      short loc_180035101
0x1800350e2  cmp     byte ptr [rcx+19h], 2
0x1800350e6  jb      short loc_180035101
0x1800350e8  mov     edx, 1ADh
0x1800350ed  mov     r9d, ebx
0x1800350f0  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x1800350f7  mov     rcx, [rcx+10h]
0x1800350fb  call    WPP_SF_d
0x180035100  nop
0x180035101  mov     rcx, rsi
0x180035104  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18003510a  nop
0x18003510b  mov     rcx, rdi
0x18003510e  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180035114  nop
0x180035115  jmp     loc_180034FF4
0x18003511a  mov     rdx, rsi; unsigned __int16 *
0x18003511d  lea     rcx, byte_180058AF8; this
0x180035124  call    ?DeleteLink@CFileCache@@QEAAJPEBG@Z; CFileCache::DeleteLink(ushort const *)
0x180035129  test    eax, eax
0x18003512b  jz      short loc_18003514F
0x18003512d  mov     ecx, eax; int
0x18003512f  call    ?A51TranslateErrorCode@@YAJJ@Z; A51TranslateErrorCode(long)
0x180035134  mov     ebx, eax
0x180035136  mov     rcx, rsi
0x180035139  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18003513f  nop
0x180035140  mov     rcx, rdi
0x180035143  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180035149  nop
0x18003514a  jmp     loc_180034FF4
0x18003514f  mov     rcx, rsi
0x180035152  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180035158  nop
0x180035159  mov     rcx, rdi
0x18003515c  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180035162  nop
0x180035163  xor     eax, eax
0x180035165  add     rsp, 78h
0x180035169  pop     r15
0x18003516b  pop     r14
0x18003516d  pop     rdi
0x18003516e  pop     rsi
0x18003516f  pop     rbx
0x180035170  pop     rbp
0x180035171  retn
```
