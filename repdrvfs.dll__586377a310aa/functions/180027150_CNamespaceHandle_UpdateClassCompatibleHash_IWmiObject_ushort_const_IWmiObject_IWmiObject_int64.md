# CNamespaceHandle::UpdateClassCompatibleHash(_IWmiObject *,ushort const *,_IWmiObject *,_IWmiObject *,__int64)

- ea: `0x180027150`
- end: `0x1800274a8`
- name: `?UpdateClassCompatibleHash@CNamespaceHandle@@IEAAJPEAU_IWmiObject@@PEBG00_J@Z`
- size: `856`
- prototype: `__int64 __fastcall(const unsigned __int16 **this, struct _IWmiObject *, const unsigned __int16 *, struct _IWmiObject *, struct _IWmiObject *, __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180027000`
- `0x180035908`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x180013880`
- `0x180013f90`
- `0x180027150`
- `0x180031e48`
- `0x180035178`
- `0x180036780`
- `0x180048010`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800271a6`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800271c1`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800271a6`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800271c1`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800272b0`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800272ba`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800273b8`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800273c2`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180027426`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180027430`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180027486`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180027490`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800272b0`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800272ba`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800273b8`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800273c2`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180027426`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180027430`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180027486`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180027490`
- `wbemcomn!GetMemLogObject` at `0x180027264`
- `wbemcomn!GetMemLogObject` at `0x18002736c`
- `wbemcomn!GetMemLogObject` at `0x1800273ce`
- `wbemcomn!GetMemLogObject` at `0x180027439`
- `wbemcomn!GetMemLogObject` at `0x180027264`
- `wbemcomn!GetMemLogObject` at `0x18002736c`
- `wbemcomn!GetMemLogObject` at `0x1800273ce`
- `wbemcomn!GetMemLogObject` at `0x180027439`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002726f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180027377`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800273d9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180027449`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002726f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180027377`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800273d9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180027449`
- `OLEAUT32!__imp_VariantInit` at `0x1800272eb`
- `OLEAUT32!__imp_VariantInit` at `0x1800272eb`
- `OLEAUT32!__imp_VariantClear` at `0x180027352`
- `OLEAUT32!__imp_VariantClear` at `0x18002741c`
- `OLEAUT32!__imp_VariantClear` at `0x180027352`
- `OLEAUT32!__imp_VariantClear` at `0x18002741c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CNamespaceHandle::UpdateClassCompatibleHash(
        const unsigned __int16 **this,
        struct _IWmiObject *a2,
        const unsigned __int16 *a3,
        struct _IWmiObject *a4,
        struct _IWmiObject *a5,
        __int64 a6)
{
  unsigned __int16 *v10; // rbx
  unsigned __int16 *v11; // rdi
  int v12; // esi
  CMemoryLog *v13; // rax
  const unsigned __int16 *v14; // rdx
  CMemoryLog *v15; // rax
  CMemoryLog *v16; // rax
  CMemoryLog *MemLogObject; // rax
  VARIANTARG pvarg; // [rsp+58h] [rbp-50h] BYREF

  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 256, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids);
  }
  v10 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(0x2E6u);
  if ( v10 )
    *v10 = 0;
  v11 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(0x2E6u);
  if ( v11 )
    *v11 = 0;
  if ( !v10 || !v11 )
  {
    MemLogObject = GetMemLogObject();
    v12 = -2147217402;
    CMemoryLog::Write(MemLogObject, -2147217402);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 257, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749894LL);
    }
    goto LABEL_37;
  }
  StringCchCopyW(v10, 0x173u, L"CD_");
  StringCchCatW(v10, 0x173u, a3);
  StringCchCopyW(v11, 0x173u, this[7]);
  StringCchCatW(v11, 0x173u, L"\\");
  StringCchCatW(v11, 0x173u, v10);
  v12 = CNamespaceHandle::ClassToFile((CNamespaceHandle *)this, a2, a4, v11, a6);
  if ( v12 < 0 )
  {
    v13 = GetMemLogObject();
    CMemoryLog::Write(v13, v12);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        258,
        WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
        (unsigned int)v12);
    }
LABEL_37:
    CWin32DefaultArena::WbemMemFree(v11);
    CWin32DefaultArena::WbemMemFree(v10);
    return (unsigned int)v12;
  }
  if ( !a5 )
    goto LABEL_21;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v12 = (*(__int64 (__fastcall **)(struct _IWmiObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)a4 + 32LL))(
          a4,
          L"__CLASS",
          0,
          &pvarg,
          0,
          0);
  if ( v12 >= 0 )
  {
    v12 = CNamespaceHandle::EraseClassRelationships((CNamespaceHandle *)this, v14, a5, v10);
    if ( v12 >= 0 )
    {
      VariantClear(&pvarg);
LABEL_21:
      v12 = CNamespaceHandle::WriteClassRelationships((CNamespaceHandle *)this, a4, v10);
      if ( v12 < 0 )
      {
        v15 = GetMemLogObject();
        CMemoryLog::Write(v15, v12);
      }
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          260,
          WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
          (unsigned int)v12);
      }
      CWin32DefaultArena::WbemMemFree(v11);
      CWin32DefaultArena::WbemMemFree(v10);
      return (unsigned int)v12;
    }
  }
  v16 = GetMemLogObject();
  CMemoryLog::Write(v16, v12);
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      259,
      WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
      (unsigned int)v12);
  }
  VariantClear(&pvarg);
  CWin32DefaultArena::WbemMemFree(v11);
  CWin32DefaultArena::WbemMemFree(v10);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180027150  push    rbx
0x180027152  push    rbp
0x180027153  push    rsi
0x180027154  push    rdi
0x180027155  push    r12
0x180027157  push    r14
0x180027159  push    r15
0x18002715b  sub     rsp, 70h
0x18002715f  mov     r14, r9
0x180027162  mov     rsi, r8
0x180027165  mov     rbp, rdx
0x180027168  mov     r15, rcx
0x18002716b  lea     r12, WPP_GLOBAL_Control
0x180027172  mov     rcx, cs:WPP_GLOBAL_Control
0x180027179  cmp     rcx, r12
0x18002717c  jz      short loc_18002719F
0x18002717e  test    byte ptr [rcx+1Ch], 1
0x180027182  jz      short loc_18002719F
0x180027184  cmp     byte ptr [rcx+19h], 5
0x180027188  jb      short loc_18002719F
0x18002718a  mov     edx, 100h
0x18002718f  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180027196  mov     rcx, [rcx+10h]
0x18002719a  call    WPP_SF_
0x18002719f  mov     edi, 2E6h
0x1800271a4  mov     ecx, edi
0x1800271a6  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800271ac  mov     rbx, rax
0x1800271af  mov     [rsp+0A8h+var_68], rax
0x1800271b4  test    rax, rax
0x1800271b7  jz      short loc_1800271BE
0x1800271b9  xor     eax, eax
0x1800271bb  mov     [rbx], ax
0x1800271be  mov     rcx, rdi
0x1800271c1  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800271c7  mov     rdi, rax
0x1800271ca  mov     [rsp+0A8h+var_60], rax
0x1800271cf  test    rax, rax
0x1800271d2  jz      short loc_1800271D9
0x1800271d4  xor     eax, eax
0x1800271d6  mov     [rdi], ax
0x1800271d9  test    rbx, rbx
0x1800271dc  jz      loc_180027439
0x1800271e2  test    rdi, rdi
0x1800271e5  jz      loc_180027439
0x1800271eb  lea     r8, aCd_0; "CD_"
0x1800271f2  mov     r12d, 173h
0x1800271f8  mov     edx, r12d; unsigned __int64
0x1800271fb  mov     rcx, rbx; unsigned __int16 *
0x1800271fe  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180027203  mov     r8, rsi; unsigned __int16 *
0x180027206  mov     edx, r12d; unsigned __int64
0x180027209  mov     rcx, rbx; unsigned __int16 *
0x18002720c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180027211  mov     r8, [r15+38h]; unsigned __int16 *
0x180027215  mov     edx, r12d; unsigned __int64
0x180027218  mov     rcx, rdi; unsigned __int16 *
0x18002721b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180027220  lea     r8, asc_18004B0E0; "\\"
0x180027227  mov     edx, r12d; unsigned __int64
0x18002722a  mov     rcx, rdi; unsigned __int16 *
0x18002722d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180027232  mov     r8, rbx; unsigned __int16 *
0x180027235  mov     edx, r12d; unsigned __int64
0x180027238  mov     rcx, rdi; unsigned __int16 *
0x18002723b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180027240  mov     rax, [rsp+0A8h+arg_28]
0x180027248  mov     [rsp+0A8h+var_88], rax; __int64
0x18002724d  mov     r9, rdi; unsigned __int16 *
0x180027250  mov     r8, r14; struct _IWmiObject *
0x180027253  mov     rdx, rbp; struct _IWmiObject *
0x180027256  mov     rcx, r15; this
0x180027259  call    ?ClassToFile@CNamespaceHandle@@IEAAJPEAU_IWmiObject@@0PEBG_J@Z; CNamespaceHandle::ClassToFile(_IWmiObject *,_IWmiObject *,ushort const *,__int64)
0x18002725e  mov     esi, eax
0x180027260  test    eax, eax
0x180027262  jns     short loc_1800272C6
0x180027264  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002726a  mov     edx, esi
0x18002726c  mov     rcx, rax
0x18002726f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180027275  mov     rcx, cs:WPP_GLOBAL_Control
0x18002727c  lea     rax, WPP_GLOBAL_Control
0x180027283  cmp     rcx, rax
0x180027286  jz      short loc_1800272AD
0x180027288  test    byte ptr [rcx+1Ch], 1
0x18002728c  jz      short loc_1800272AD
0x18002728e  cmp     byte ptr [rcx+19h], 2
0x180027292  jb      short loc_1800272AD
0x180027294  lea     edx, [r12-71h]
0x180027299  mov     r9d, esi
0x18002729c  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x1800272a3  mov     rcx, [rcx+10h]
0x1800272a7  call    WPP_SF_d
0x1800272ac  nop
0x1800272ad  mov     rcx, rdi
0x1800272b0  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800272b6  nop
0x1800272b7  mov     rcx, rbx
0x1800272ba  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800272c0  nop
0x1800272c1  jmp     loc_180027497
0x1800272c6  mov     rbp, [rsp+0A8h+arg_20]
0x1800272ce  test    rbp, rbp
0x1800272d1  jz      loc_180027358
0x1800272d7  xorps   xmm0, xmm0
0x1800272da  xor     eax, eax
0x1800272dc  movups  xmmword ptr [rsp+0A8h+pvarg], xmm0
0x1800272e1  mov     qword ptr [rsp+0A8h+pvarg+10h], rax
0x1800272e6  lea     rcx, [rsp+0A8h+pvarg]; pvarg
0x1800272eb  call    cs:__imp_VariantInit
0x1800272f1  mov     rax, [r14]
0x1800272f4  mov     [rsp+0A8h+var_80], 0
0x1800272fd  mov     [rsp+0A8h+var_88], 0
0x180027306  lea     r9, [rsp+0A8h+pvarg]
0x18002730b  xor     r8d, r8d
0x18002730e  lea     rdx, aClass; "__CLASS"
0x180027315  mov     rcx, r14
0x180027318  mov     rax, [rax+20h]
0x18002731c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027321  mov     esi, eax
0x180027323  lea     rax, [rsp+0A8h+pvarg]
0x180027328  mov     [rsp+0A8h+var_58], rax
0x18002732d  test    esi, esi
0x18002732f  js      loc_1800273CE
0x180027335  mov     r9, rbx; unsigned __int16 *
0x180027338  mov     r8, rbp; struct _IWmiObject *
0x18002733b  mov     rcx, r15; this
0x18002733e  call    ?EraseClassRelationships@CNamespaceHandle@@IEAAJPEBGPEAU_IWmiObject@@0@Z; CNamespaceHandle::EraseClassRelationships(ushort const *,_IWmiObject *,ushort const *)
0x180027343  mov     esi, eax
0x180027345  test    eax, eax
0x180027347  js      loc_1800273CE
0x18002734d  lea     rcx, [rsp+0A8h+pvarg]; pvarg
0x180027352  call    cs:__imp_VariantClear
0x180027358  mov     r8, rbx; unsigned __int16 *
0x18002735b  mov     rdx, r14; struct _IWmiObject *
0x18002735e  mov     rcx, r15; this
0x180027361  call    ?WriteClassRelationships@CNamespaceHandle@@IEAAJPEAU_IWmiObject@@PEBG@Z; CNamespaceHandle::WriteClassRelationships(_IWmiObject *,ushort const *)
0x180027366  mov     esi, eax
0x180027368  test    eax, eax
0x18002736a  jns     short loc_18002737D
0x18002736c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180027372  mov     edx, esi
0x180027374  mov     rcx, rax
0x180027377  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002737d  mov     rcx, cs:WPP_GLOBAL_Control
0x180027384  lea     rax, WPP_GLOBAL_Control
0x18002738b  cmp     rcx, rax
0x18002738e  jz      short loc_1800273B5
0x180027390  test    byte ptr [rcx+1Ch], 1
0x180027394  jz      short loc_1800273B5
0x180027396  cmp     byte ptr [rcx+19h], 2
0x18002739a  jb      short loc_1800273B5
0x18002739c  mov     edx, 104h
0x1800273a1  mov     r9d, esi
0x1800273a4  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x1800273ab  mov     rcx, [rcx+10h]
0x1800273af  call    WPP_SF_d
0x1800273b4  nop
0x1800273b5  mov     rcx, rdi
0x1800273b8  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800273be  nop
0x1800273bf  mov     rcx, rbx
0x1800273c2  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800273c8  nop
0x1800273c9  jmp     loc_180027497
0x1800273ce  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800273d4  mov     edx, esi
0x1800273d6  mov     rcx, rax
0x1800273d9  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800273df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800273e6  lea     rax, WPP_GLOBAL_Control
0x1800273ed  cmp     rcx, rax
0x1800273f0  jz      short loc_180027417
0x1800273f2  test    byte ptr [rcx+1Ch], 1
0x1800273f6  jz      short loc_180027417
0x1800273f8  cmp     byte ptr [rcx+19h], 2
0x1800273fc  jb      short loc_180027417
0x1800273fe  mov     edx, 103h
0x180027403  mov     r9d, esi
0x180027406  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18002740d  mov     rcx, [rcx+10h]
0x180027411  call    WPP_SF_d
0x180027416  nop
0x180027417  lea     rcx, [rsp+0A8h+pvarg]; pvarg
0x18002741c  call    cs:__imp_VariantClear
0x180027422  nop
0x180027423  mov     rcx, rdi
0x180027426  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18002742c  nop
0x18002742d  mov     rcx, rbx
0x180027430  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180027436  nop
0x180027437  jmp     short loc_180027497
0x180027439  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002743f  mov     esi, 80041006h
0x180027444  mov     edx, esi
0x180027446  mov     rcx, rax
0x180027449  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002744f  mov     rcx, cs:WPP_GLOBAL_Control
0x180027456  cmp     rcx, r12
0x180027459  jz      short loc_180027483
0x18002745b  test    byte ptr [rcx+1Ch], 1
0x18002745f  jz      short loc_180027483
0x180027461  cmp     byte ptr [rcx+19h], 2
0x180027465  jb      short loc_180027483
0x180027467  mov     edx, 101h
0x18002746c  mov     r9d, 80041006h
0x180027472  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180027479  mov     rcx, [rcx+10h]
0x18002747d  call    WPP_SF_d
0x180027482  nop
0x180027483  mov     rcx, rdi
0x180027486  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18002748c  nop
0x18002748d  mov     rcx, rbx
0x180027490  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180027496  nop
0x180027497  mov     eax, esi
0x180027499  add     rsp, 70h
0x18002749d  pop     r15
0x18002749f  pop     r14
0x1800274a1  pop     r12
0x1800274a3  pop     rdi
0x1800274a4  pop     rsi
0x1800274a5  pop     rbp
0x1800274a6  pop     rbx
0x1800274a7  retn
```
