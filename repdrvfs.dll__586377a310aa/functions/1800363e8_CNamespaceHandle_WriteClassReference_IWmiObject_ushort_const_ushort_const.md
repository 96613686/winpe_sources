# CNamespaceHandle::WriteClassReference(_IWmiObject *,ushort const *,ushort const *)

- ea: `0x1800363e8`
- end: `0x18003677a`
- name: `?WriteClassReference@CNamespaceHandle@@IEAAJPEAU_IWmiObject@@PEBG1@Z`
- size: `914`
- prototype: `__int64 __fastcall(CNamespaceHandle *__hidden this, struct _IWmiObject *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180036780`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x18001e134`
- `0x180023bf0`
- `0x180032690`
- `0x1800363e8`
- `0x180036dd8`
- `0x180048010`

## import_xrefs

- `msvcrt!wcschr` at `0x18003660b`
- `msvcrt!wcschr` at `0x18003660b`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800364f3`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800364f3`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800365f5`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003661c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003668c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180036696`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003670c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180036716`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180036741`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003674b`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003675a`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180036764`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800365f5`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003661c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003668c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180036696`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003670c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180036716`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180036741`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003674b`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003675a`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180036764`
- `wbemcomn!GetMemLogObject` at `0x18003649f`
- `wbemcomn!GetMemLogObject` at `0x180036501`
- `wbemcomn!GetMemLogObject` at `0x1800365a9`
- `wbemcomn!GetMemLogObject` at `0x18003663b`
- `wbemcomn!GetMemLogObject` at `0x1800366c0`
- `wbemcomn!GetMemLogObject` at `0x18003649f`
- `wbemcomn!GetMemLogObject` at `0x180036501`
- `wbemcomn!GetMemLogObject` at `0x1800365a9`
- `wbemcomn!GetMemLogObject` at `0x18003663b`
- `wbemcomn!GetMemLogObject` at `0x1800366c0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800364ad`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003650f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800365b4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036649`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800366cb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800364ad`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003650f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800365b4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180036649`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800366cb`

## pseudocode

```c
__int64 __fastcall CNamespaceHandle::WriteClassReference(
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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 295, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids);
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
    v10 = 296;
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
    v10 = 297;
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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 298, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, v15);
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
          299,
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
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 300, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, v15);
      }
      CWin32DefaultArena::WbemMemFree(v19);
      CWin32DefaultArena::WbemMemFree(v12);
      return v15;
    }
    v22 = CFileCache::WriteLink((CFileCache *)byte_180058AF8, v19);
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
0x1800363e8  push    rbp
0x1800363ea  push    rbx
0x1800363eb  push    rsi
0x1800363ec  push    rdi
0x1800363ed  push    r14
0x1800363ef  push    r15
0x1800363f1  mov     rbp, rsp
0x1800363f4  sub     rsp, 78h
0x1800363f8  mov     rsi, r9
0x1800363fb  mov     r14, r8
0x1800363fe  mov     rbx, rdx
0x180036401  mov     r15, rcx
0x180036404  lea     rdi, WPP_GLOBAL_Control
0x18003640b  mov     rcx, cs:WPP_GLOBAL_Control
0x180036412  cmp     rcx, rdi
0x180036415  jz      short loc_180036438
0x180036417  test    byte ptr [rcx+1Ch], 1
0x18003641b  jz      short loc_180036438
0x18003641d  cmp     byte ptr [rcx+19h], 5
0x180036421  jb      short loc_180036438
0x180036423  mov     edx, 127h
0x180036428  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18003642f  mov     rcx, [rcx+10h]
0x180036433  call    WPP_SF_
0x180036438  mov     [rbp+arg_8], 0
0x18003643f  mov     [rbp+var_28], 0
0x180036446  mov     [rbp+var_24], 0
0x18003644d  mov     rax, [rbx]
0x180036450  mov     [rsp+78h+var_38], 0
0x180036459  lea     rcx, [rbp+arg_8]
0x18003645d  mov     [rsp+78h+var_40], rcx
0x180036462  lea     rcx, [rbp+var_28]
0x180036466  mov     [rsp+78h+var_48], rcx
0x18003646b  lea     rcx, [rbp+var_24]
0x18003646f  mov     [rsp+78h+var_50], rcx
0x180036474  mov     dword ptr [rsp+78h+var_58], 0
0x18003647c  xor     r9d, r9d
0x18003647f  lea     r8, aCimtype; "CIMTYPE"
0x180036486  mov     rdx, rsi
0x180036489  mov     rcx, rbx
0x18003648c  mov     rax, [rax+1A8h]
0x180036493  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036498  mov     eax, [rbp+arg_8]
0x18003649b  test    eax, eax
0x18003649d  jnz     short loc_1800364DA
0x18003649f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800364a5  mov     edx, 80041006h
0x1800364aa  mov     rcx, rax
0x1800364ad  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800364b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800364ba  cmp     rcx, rdi
0x1800364bd  jz      loc_18003654F
0x1800364c3  test    byte ptr [rcx+1Ch], 1
0x1800364c7  jz      loc_18003654F
0x1800364cd  cmp     byte ptr [rcx+19h], 2
0x1800364d1  jb      short loc_18003654F
0x1800364d3  mov     edx, 128h
0x1800364d8  jmp     short loc_180036539
0x1800364da  mov     rcx, rax
0x1800364dd  mov     eax, 2
0x1800364e2  mul     rcx
0x1800364e5  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800364ec  cmovb   rax, rcx
0x1800364f0  mov     rcx, rax
0x1800364f3  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800364f9  mov     rdi, rax
0x1800364fc  test    rax, rax
0x1800364ff  jnz     short loc_180036559
0x180036501  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180036507  mov     edx, 80041006h
0x18003650c  mov     rcx, rax
0x18003650f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180036515  mov     rcx, cs:WPP_GLOBAL_Control
0x18003651c  lea     rax, WPP_GLOBAL_Control
0x180036523  cmp     rcx, rax
0x180036526  jz      short loc_18003654F
0x180036528  test    byte ptr [rcx+1Ch], 1
0x18003652c  jz      short loc_18003654F
0x18003652e  cmp     byte ptr [rcx+19h], 2
0x180036532  jb      short loc_18003654F
0x180036534  mov     edx, 129h
0x180036539  mov     r9d, 80041006h
0x18003653f  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180036546  mov     rcx, [rcx+10h]
0x18003654a  call    WPP_SF_d
0x18003654f  mov     eax, 80041006h
0x180036554  jmp     loc_18003676D
0x180036559  mov     [rbp+var_18], rdi
0x18003655d  mov     rax, [rbx]
0x180036560  mov     [rsp+78h+var_38], rdi
0x180036565  lea     rcx, [rbp+arg_8]
0x180036569  mov     [rsp+78h+var_40], rcx
0x18003656e  lea     rcx, [rbp+var_28]
0x180036572  mov     [rsp+78h+var_48], rcx
0x180036577  lea     rcx, [rbp+var_24]
0x18003657b  mov     [rsp+78h+var_50], rcx
0x180036580  mov     ecx, [rbp+arg_8]
0x180036583  mov     dword ptr [rsp+78h+var_58], ecx
0x180036587  xor     r9d, r9d
0x18003658a  lea     r8, aCimtype; "CIMTYPE"
0x180036591  mov     rdx, rsi
0x180036594  mov     rcx, rbx
0x180036597  mov     rax, [rax+1A8h]
0x18003659e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800365a3  mov     ebx, eax
0x1800365a5  test    eax, eax
0x1800365a7  jns     short loc_180036603
0x1800365a9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800365af  mov     edx, ebx
0x1800365b1  mov     rcx, rax
0x1800365b4  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800365ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800365c1  lea     rax, WPP_GLOBAL_Control
0x1800365c8  cmp     rcx, rax
0x1800365cb  jz      short loc_1800365F2
0x1800365cd  test    byte ptr [rcx+1Ch], 1
0x1800365d1  jz      short loc_1800365F2
0x1800365d3  cmp     byte ptr [rcx+19h], 2
0x1800365d7  jb      short loc_1800365F2
0x1800365d9  mov     edx, 12Ah
0x1800365de  mov     r9d, ebx
0x1800365e1  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x1800365e8  mov     rcx, [rcx+10h]
0x1800365ec  call    WPP_SF_d
0x1800365f1  nop
0x1800365f2  mov     rcx, rdi
0x1800365f5  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800365fb  nop
0x1800365fc  mov     eax, ebx
0x1800365fe  jmp     loc_18003676D
0x180036603  mov     edx, 3Ah ; ':'; Ch
0x180036608  mov     rcx, rdi; Str
0x18003660b  call    cs:__imp_wcschr
0x180036611  mov     rbx, rax
0x180036614  test    rax, rax
0x180036617  jnz     short loc_180036628
0x180036619  mov     rcx, rdi
0x18003661c  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180036622  nop
0x180036623  jmp     loc_18003676B
0x180036628  lea     rcx, [rbp+var_20]; this
0x18003662c  call    ??0CFileName@@QEAA@XZ; CFileName::CFileName(void)
0x180036631  nop
0x180036632  mov     rsi, [rbp+var_20]
0x180036636  test    rsi, rsi
0x180036639  jnz     short loc_1800366A2
0x18003663b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180036641  mov     edx, 80041006h
0x180036646  mov     rcx, rax
0x180036649  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003664f  mov     rcx, cs:WPP_GLOBAL_Control
0x180036656  lea     rax, WPP_GLOBAL_Control
0x18003665d  cmp     rcx, rax
0x180036660  jz      short loc_18003668A
0x180036662  test    byte ptr [rcx+1Ch], 1
0x180036666  jz      short loc_18003668A
0x180036668  cmp     byte ptr [rcx+19h], 2
0x18003666c  jb      short loc_18003668A
0x18003666e  mov     edx, 12Bh
0x180036673  mov     r9d, 80041006h
0x180036679  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180036680  mov     rcx, [rcx+10h]
0x180036684  call    WPP_SF_d
0x180036689  nop
0x18003668a  xor     ecx, ecx
0x18003668c  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180036692  nop
0x180036693  mov     rcx, rdi
0x180036696  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18003669c  nop
0x18003669d  jmp     loc_18003654F
0x1800366a2  lea     rdx, [rbx+2]; unsigned __int16 *
0x1800366a6  lea     rax, [rbp+var_20]
0x1800366aa  mov     [rsp+78h+var_58], rax; struct CFileName *
0x1800366af  mov     r8, r14; unsigned __int16 *
0x1800366b2  mov     rcx, r15; this
0x1800366b5  call    ?ConstructClassReferenceFileName@CNamespaceHandle@@IEAAJPEBG00AEAVCFileName@@@Z; CNamespaceHandle::ConstructClassReferenceFileName(ushort const *,ushort const *,ushort const *,CFileName &)
0x1800366ba  mov     ebx, eax
0x1800366bc  test    eax, eax
0x1800366be  jns     short loc_180036722
0x1800366c0  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800366c6  mov     edx, ebx
0x1800366c8  mov     rcx, rax
0x1800366cb  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800366d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800366d8  lea     rax, WPP_GLOBAL_Control
0x1800366df  cmp     rcx, rax
0x1800366e2  jz      short loc_180036709
0x1800366e4  test    byte ptr [rcx+1Ch], 1
0x1800366e8  jz      short loc_180036709
0x1800366ea  cmp     byte ptr [rcx+19h], 2
0x1800366ee  jb      short loc_180036709
0x1800366f0  mov     edx, 12Ch
0x1800366f5  mov     r9d, ebx
0x1800366f8  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x1800366ff  mov     rcx, [rcx+10h]
0x180036703  call    WPP_SF_d
0x180036708  nop
0x180036709  mov     rcx, rsi
0x18003670c  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180036712  nop
0x180036713  mov     rcx, rdi
0x180036716  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18003671c  nop
0x18003671d  jmp     loc_1800365FC
0x180036722  mov     rdx, rsi; unsigned __int16 *
0x180036725  lea     rcx, byte_180058AF8; this
0x18003672c  call    ?WriteLink@CFileCache@@QEAAJPEBG@Z; CFileCache::WriteLink(ushort const *)
0x180036731  test    eax, eax
0x180036733  jz      short loc_180036757
0x180036735  mov     ecx, eax; int
0x180036737  call    ?A51TranslateErrorCode@@YAJJ@Z; A51TranslateErrorCode(long)
0x18003673c  mov     ebx, eax
0x18003673e  mov     rcx, rsi
0x180036741  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180036747  nop
0x180036748  mov     rcx, rdi
0x18003674b  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180036751  nop
0x180036752  jmp     loc_1800365FC
0x180036757  mov     rcx, rsi
0x18003675a  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180036760  nop
0x180036761  mov     rcx, rdi
0x180036764  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18003676a  nop
0x18003676b  xor     eax, eax
0x18003676d  add     rsp, 78h
0x180036771  pop     r15
0x180036773  pop     r14
0x180036775  pop     rdi
0x180036776  pop     rsi
0x180036777  pop     rbx
0x180036778  pop     rbp
0x180036779  retn
```
