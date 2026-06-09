# CNamespaceHandle::GetReferrerFromFile(ushort const *,ushort *,ulong,ushort * *,ushort * *,ushort * *)

- ea: `0x18000954c`
- end: `0x180009911`
- name: `?GetReferrerFromFile@CNamespaceHandle@@IEAAJPEBGPEAGKPEAPEAG22@Z`
- size: `965`
- prototype: `__int64 __fastcall(CNamespaceHandle *this, const unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180008730`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x18000954c`
- `0x18000b650`
- `0x18000bf70`
- `0x18001e134`
- `0x180026124`
- `0x18002b7b6`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180009689`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180009735`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800097d2`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180009689`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180009735`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800097d2`
- `wbemcomn!GetMemLogObject` at `0x180009627`
- `wbemcomn!GetMemLogObject` at `0x18000969b`
- `wbemcomn!GetMemLogObject` at `0x18000974a`
- `wbemcomn!GetMemLogObject` at `0x1800097e7`
- `wbemcomn!GetMemLogObject` at `0x18000989e`
- `wbemcomn!GetMemLogObject` at `0x180009627`
- `wbemcomn!GetMemLogObject` at `0x18000969b`
- `wbemcomn!GetMemLogObject` at `0x18000974a`
- `wbemcomn!GetMemLogObject` at `0x1800097e7`
- `wbemcomn!GetMemLogObject` at `0x18000989e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180009635`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800096a9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180009758`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800097f5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800098ae`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180009635`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800096a9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180009758`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800097f5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800098ae`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CNamespaceHandle::GetReferrerFromFile(
        CNamespaceHandle *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned int a4,
        unsigned __int16 **a5,
        unsigned __int16 **a6,
        unsigned __int16 **a7)
{
  unsigned int v9; // eax
  unsigned __int8 *v11; // rdi
  struct MemoryPage *v12; // rsi
  CMemoryLog *MemLogObject; // rax
  CVarObjHeap *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r14
  unsigned __int16 *v17; // rax
  void **v18; // r9
  CMemoryLog *v19; // rax
  size_t v20; // r14
  __int64 v21; // r13
  unsigned __int16 *v22; // rcx
  void **v23; // r9
  CMemoryLog *v24; // rax
  unsigned __int8 *v25; // r15
  __int64 v26; // r14
  __int64 v27; // r13
  unsigned __int16 *v28; // rcx
  void **v29; // r9
  CMemoryLog *v30; // rax
  unsigned __int8 *v31; // r15
  __int64 v32; // r14
  __int64 v33; // r8
  CMemoryLog *v34; // rax
  unsigned __int8 *v35; // [rsp+30h] [rbp-30h] BYREF
  struct MemoryPage *v36; // [rsp+38h] [rbp-28h] BYREF
  char v37[8]; // [rsp+40h] [rbp-20h] BYREF
  void (__fastcall *v38)(struct MemoryPage *, unsigned __int8 *); // [rsp+48h] [rbp-18h]
  struct MemoryPage *v39; // [rsp+50h] [rbp-10h]
  unsigned __int8 *v40; // [rsp+58h] [rbp-8h]
  CNamespaceHandle *v41; // [rsp+A0h] [rbp+40h] BYREF
  unsigned int v42; // [rsp+B8h] [rbp+58h]

  v42 = a4;
  v41 = this;
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 506, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids);
  }
  v35 = 0;
  v36 = 0;
  LODWORD(v41) = 0;
  if ( !dword_180058AFC || g_bShuttingDown )
  {
    v9 = 1255;
    return A51TranslateErrorCode(v9, (__int64)a2, (__int64)a3);
  }
  v9 = CObjectHeap::ReadObject((CObjectHeap *)&qword_180058EF8, a2, (unsigned int *)&v41, &v35, &v36);
  if ( v9 )
    return A51TranslateErrorCode(v9, (__int64)a2, (__int64)a3);
  v11 = v35;
  v12 = v36;
  v37[0] = 0;
  v38 = CleanupReadObjectMemory;
  v39 = v36;
  v40 = v35;
  if ( !(_DWORD)v41 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2147217402);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_33;
    }
    v15 = 507;
LABEL_32:
    WPP_SF_d(*((_QWORD *)v14 + 2), v15, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749894LL);
LABEL_33:
    ScopeGuardImpl2<void (*)(MemoryPage *,unsigned char *),MemoryPage *,unsigned char *>::~ScopeGuardImpl2<void (*)(MemoryPage *,unsigned char *),MemoryPage *,unsigned char *>(v37);
    return 2147749894LL;
  }
  v16 = *(unsigned int *)v35;
  v17 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul((unsigned int)(v16 + 1), 2u));
  v18 = (void **)a5;
  *a5 = v17;
  if ( !v17 )
  {
    v19 = GetMemLogObject();
    CMemoryLog::Write(v19, -2147217402);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 508, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749894LL);
    }
    CleanupReadObjectMemory(v12, v11);
    return 2147749894LL;
  }
  v20 = 2 * v16;
  v17[v20 / 2] = 0;
  memcpy_0(*v18, v11 + 4, v20);
  v21 = *(unsigned int *)&v11[v20 + 4];
  v22 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul((unsigned int)(v21 + 1), 2u));
  v23 = (void **)a6;
  *a6 = v22;
  if ( !v22 )
  {
    v24 = GetMemLogObject();
    CMemoryLog::Write(v24, -2147217402);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_33;
    }
    v15 = 509;
    goto LABEL_32;
  }
  v25 = &v11[v20 + 8];
  v26 = 2 * v21;
  v22[v21] = 0;
  memcpy_0(*v23, v25, 2 * v21);
  v27 = *(unsigned int *)&v25[2 * v21];
  v28 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul((unsigned int)(v27 + 1), 2u));
  v29 = (void **)a7;
  *a7 = v28;
  if ( !v28 )
  {
    v30 = GetMemLogObject();
    CMemoryLog::Write(v30, -2147217402);
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_33;
    }
    v15 = 510;
    goto LABEL_32;
  }
  v31 = &v25[v26];
  v32 = 2 * v27;
  v28[v27] = 0;
  memcpy_0(*v29, v31 + 4, 2 * v27);
  if ( *(_DWORD *)&v31[2 * v27 + 4] >= v42 )
  {
    v34 = GetMemLogObject();
    CMemoryLog::Write(v34, -2147217407);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 511, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749889LL);
    }
    ScopeGuardImpl2<void (*)(MemoryPage *,unsigned char *),MemoryPage *,unsigned char *>::~ScopeGuardImpl2<void (*)(MemoryPage *,unsigned char *),MemoryPage *,unsigned char *>(v37);
    return 2147749889LL;
  }
  else
  {
    v33 = *(unsigned int *)&v31[v32 + 4];
    a3[v33] = 0;
    memcpy_0(a3, &v31[v32 + 8], v33 * 2);
    CleanupReadObjectMemory(v12, v11);
    return 0;
  }
}

```

## disassembly

```asm
0x18000954c  mov     [rsp-38h+arg_8], rbx
0x180009551  mov     [rsp-38h+arg_18], r9d
0x180009556  mov     [rsp-38h+arg_0], rcx
0x18000955b  push    rbp
0x18000955c  push    rsi
0x18000955d  push    rdi
0x18000955e  push    r12
0x180009560  push    r13
0x180009562  push    r14
0x180009564  push    r15
0x180009566  mov     rbp, rsp
0x180009569  sub     rsp, 60h
0x18000956d  mov     r12, r8
0x180009570  mov     rbx, rdx
0x180009573  lea     r14, WPP_GLOBAL_Control
0x18000957a  mov     r15b, 1
0x18000957d  mov     rcx, cs:WPP_GLOBAL_Control
0x180009584  cmp     rcx, r14
0x180009587  jz      short loc_1800095AA
0x180009589  test    [rcx+1Ch], r15b
0x18000958d  jz      short loc_1800095AA
0x18000958f  cmp     byte ptr [rcx+19h], 5
0x180009593  jb      short loc_1800095AA
0x180009595  mov     edx, 1FAh
0x18000959a  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x1800095a1  mov     rcx, [rcx+10h]
0x1800095a5  call    WPP_SF_
0x1800095aa  xor     r13d, r13d
0x1800095ad  mov     [rbp+var_30], r13
0x1800095b1  mov     [rbp+var_28], r13
0x1800095b5  mov     dword ptr [rbp+arg_0], r13d
0x1800095b9  cmp     cs:dword_180058AFC, r13d
0x1800095c0  jnz     short loc_1800095C9
0x1800095c2  mov     eax, 4E7h
0x1800095c7  jmp     short loc_1800095F6
0x1800095c9  cmp     cs:?g_bShuttingDown@@3_NA, r13b; bool g_bShuttingDown
0x1800095d0  jnz     short loc_1800095C2
0x1800095d2  lea     rax, [rbp+var_28]
0x1800095d6  mov     [rsp+60h+var_40], rax; struct MemoryPage **
0x1800095db  lea     r9, [rbp+var_30]; unsigned __int8 **
0x1800095df  lea     r8, [rbp+arg_0]; unsigned int *
0x1800095e3  mov     rdx, rbx; unsigned __int16 *
0x1800095e6  lea     rcx, qword_180058EF8; this
0x1800095ed  call    ?ReadObject@CObjectHeap@@QEAAJPEBGPEAKPEAPEAEPEAPEAVMemoryPage@@@Z; CObjectHeap::ReadObject(ushort const *,ulong *,uchar * *,MemoryPage * *)
0x1800095f2  test    eax, eax
0x1800095f4  jz      short loc_180009602
0x1800095f6  mov     ecx, eax; int
0x1800095f8  call    ?A51TranslateErrorCode@@YAJJ@Z; A51TranslateErrorCode(long)
0x1800095fd  jmp     loc_1800098F9
0x180009602  mov     rdi, [rbp+var_30]
0x180009606  mov     rsi, [rbp+var_28]
0x18000960a  mov     [rbp+var_20], r13b
0x18000960e  lea     rax, ?CleanupReadObjectMemory@@YAXPEAVMemoryPage@@PEAE@Z; CleanupReadObjectMemory(MemoryPage *,uchar *)
0x180009615  mov     [rbp+var_18], rax
0x180009619  mov     [rbp+var_10], rsi
0x18000961d  mov     [rbp+var_8], rdi
0x180009621  cmp     dword ptr [rbp+arg_0], r13d
0x180009625  jnz     short loc_18000966D
0x180009627  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000962d  mov     edx, 80041006h
0x180009632  mov     rcx, rax
0x180009635  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000963b  mov     rcx, cs:WPP_GLOBAL_Control
0x180009642  cmp     rcx, r14
0x180009645  jz      loc_180009835
0x18000964b  test    [rcx+1Ch], r15b
0x18000964f  jz      loc_180009835
0x180009655  mov     ebx, 2
0x18000965a  cmp     [rcx+19h], bl
0x18000965d  jb      loc_180009835
0x180009663  mov     edx, 1FBh
0x180009668  jmp     loc_18000981E
0x18000966d  mov     r14d, [rdi]
0x180009670  lea     ecx, [r14+1]
0x180009674  mov     ebx, 2
0x180009679  mov     eax, ebx
0x18000967b  mul     rcx
0x18000967e  lea     rcx, [rbx-3]
0x180009682  cmovb   rax, rcx
0x180009686  mov     rcx, rax
0x180009689  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000968f  mov     r9, [rbp+arg_20]
0x180009693  mov     [r9], rax
0x180009696  test    rax, rax
0x180009699  jnz     short loc_1800096FF
0x18000969b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800096a1  mov     edx, 80041006h
0x1800096a6  mov     rcx, rax
0x1800096a9  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800096af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800096b6  lea     rax, WPP_GLOBAL_Control
0x1800096bd  cmp     rcx, rax
0x1800096c0  jz      short loc_1800096E9
0x1800096c2  test    [rcx+1Ch], r15b
0x1800096c6  jz      short loc_1800096E9
0x1800096c8  cmp     [rcx+19h], bl
0x1800096cb  jb      short loc_1800096E9
0x1800096cd  mov     edx, 1FCh
0x1800096d2  mov     r9d, 80041006h
0x1800096d8  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x1800096df  mov     rcx, [rcx+10h]
0x1800096e3  call    WPP_SF_d
0x1800096e8  nop
0x1800096e9  mov     rdx, rdi; unsigned __int8 *
0x1800096ec  mov     rcx, rsi; struct MemoryPage *
0x1800096ef  call    ?CleanupReadObjectMemory@@YAXPEAVMemoryPage@@PEAE@Z; CleanupReadObjectMemory(MemoryPage *,uchar *)
0x1800096f4  nop
0x1800096f5  mov     eax, 80041006h
0x1800096fa  jmp     loc_1800098F9
0x1800096ff  lea     r15, [rdi+4]
0x180009703  add     r14, r14
0x180009706  mov     [r14+rax], r13w
0x18000970b  mov     r8, r14; Size
0x18000970e  mov     rdx, r15; Src
0x180009711  mov     rcx, [r9]; void *
0x180009714  call    memcpy_0
0x180009719  mov     r13d, [r14+r15]
0x18000971d  lea     ecx, [r13+1]
0x180009721  mov     rax, rbx
0x180009724  mul     rcx
0x180009727  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000972e  cmovb   rax, rcx
0x180009732  mov     rcx, rax
0x180009735  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18000973b  mov     rcx, rax
0x18000973e  mov     r9, [rbp+arg_28]
0x180009742  mov     [r9], rax
0x180009745  test    rax, rax
0x180009748  jnz     short loc_180009792
0x18000974a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180009750  mov     edx, 80041006h
0x180009755  mov     rcx, rax
0x180009758  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000975e  mov     rcx, cs:WPP_GLOBAL_Control
0x180009765  lea     rax, WPP_GLOBAL_Control
0x18000976c  cmp     rcx, rax
0x18000976f  jz      loc_180009835
0x180009775  test    byte ptr [rcx+1Ch], 1
0x180009779  jz      loc_180009835
0x18000977f  cmp     [rcx+19h], bl
0x180009782  jb      loc_180009835
0x180009788  mov     edx, 1FDh
0x18000978d  jmp     loc_18000981E
0x180009792  add     r15, 4
0x180009796  add     r15, r14
0x180009799  lea     r14, ds:0[r13*2]
0x1800097a1  xor     eax, eax
0x1800097a3  mov     [r14+rcx], ax
0x1800097a8  mov     r8, r14; Size
0x1800097ab  mov     rdx, r15; Src
0x1800097ae  mov     rcx, [r9]; void *
0x1800097b1  call    memcpy_0
0x1800097b6  mov     r13d, [r14+r15]
0x1800097ba  lea     ecx, [r13+1]
0x1800097be  mov     rax, rbx
0x1800097c1  mul     rcx
0x1800097c4  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800097cb  cmovb   rax, rcx
0x1800097cf  mov     rcx, rax
0x1800097d2  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800097d8  mov     rcx, rax
0x1800097db  mov     r9, [rbp+arg_30]
0x1800097df  mov     [r9], rax
0x1800097e2  test    rax, rax
0x1800097e5  jnz     short loc_180009843
0x1800097e7  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800097ed  mov     edx, 80041006h
0x1800097f2  mov     rcx, rax
0x1800097f5  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800097fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180009802  lea     rax, WPP_GLOBAL_Control
0x180009809  cmp     rcx, rax
0x18000980c  jz      short loc_180009835
0x18000980e  test    byte ptr [rcx+1Ch], 1
0x180009812  jz      short loc_180009835
0x180009814  cmp     [rcx+19h], bl
0x180009817  jb      short loc_180009835
0x180009819  mov     edx, 1FEh
0x18000981e  mov     r9d, 80041006h
0x180009824  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18000982b  mov     rcx, [rcx+10h]
0x18000982f  call    WPP_SF_d
0x180009834  nop
0x180009835  lea     rcx, [rbp+var_20]
0x180009839  call    ??1?$ScopeGuardImpl2@P6AXPEAVMemoryPage@@PEAE@ZPEAV1@PEAE@@QEAA@XZ; ScopeGuardImpl2<void (*)(MemoryPage *,uchar *),MemoryPage *,uchar *>::~ScopeGuardImpl2<void (*)(MemoryPage *,uchar *),MemoryPage *,uchar *>(void)
0x18000983e  jmp     loc_1800096F5
0x180009843  add     r15, r14
0x180009846  lea     r14, ds:0[r13*2]
0x18000984e  xor     eax, eax
0x180009850  mov     [r14+rcx], ax
0x180009855  mov     r8, r14; Size
0x180009858  lea     rdx, [r15+4]; Src
0x18000985c  mov     rcx, [r9]; void *
0x18000985f  call    memcpy_0
0x180009864  mov     eax, [rbp+arg_18]
0x180009867  cmp     [r14+r15+4], eax
0x18000986c  jnb     short loc_18000989E
0x18000986e  mov     eax, [r14+r15+4]
0x180009873  lea     r8, [rax+rax]; Size
0x180009877  xor     eax, eax
0x180009879  mov     [r8+r12], ax
0x18000987e  lea     rdx, [r15+8]
0x180009882  add     rdx, r14; Src
0x180009885  mov     rcx, r12; void *
0x180009888  call    memcpy_0
0x18000988d  nop
0x18000988e  mov     rdx, rdi; unsigned __int8 *
0x180009891  mov     rcx, rsi; struct MemoryPage *
0x180009894  call    ?CleanupReadObjectMemory@@YAXPEAVMemoryPage@@PEAE@Z; CleanupReadObjectMemory(MemoryPage *,uchar *)
0x180009899  nop
0x18000989a  xor     eax, eax
0x18000989c  jmp     short loc_1800098F9
0x18000989e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800098a4  mov     edi, 80041001h
0x1800098a9  mov     edx, edi
0x1800098ab  mov     rcx, rax
0x1800098ae  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800098b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800098bb  lea     rax, WPP_GLOBAL_Control
0x1800098c2  cmp     rcx, rax
0x1800098c5  jz      short loc_1800098EE
0x1800098c7  test    byte ptr [rcx+1Ch], 1
0x1800098cb  jz      short loc_1800098EE
0x1800098cd  cmp     [rcx+19h], bl
0x1800098d0  jb      short loc_1800098EE
0x1800098d2  mov     edx, 1FFh
0x1800098d7  mov     r9d, 80041001h
0x1800098dd  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x1800098e4  mov     rcx, [rcx+10h]
0x1800098e8  call    WPP_SF_d
0x1800098ed  nop
0x1800098ee  lea     rcx, [rbp+var_20]
0x1800098f2  call    ??1?$ScopeGuardImpl2@P6AXPEAVMemoryPage@@PEAE@ZPEAV1@PEAE@@QEAA@XZ; ScopeGuardImpl2<void (*)(MemoryPage *,uchar *),MemoryPage *,uchar *>::~ScopeGuardImpl2<void (*)(MemoryPage *,uchar *),MemoryPage *,uchar *>(void)
0x1800098f7  mov     eax, edi
0x1800098f9  mov     rbx, [rsp+60h+arg_8]
0x180009901  add     rsp, 60h
0x180009905  pop     r15
0x180009907  pop     r14
0x180009909  pop     r13
0x18000990b  pop     r12
0x18000990d  pop     rdi
0x18000990e  pop     rsi
0x18000990f  pop     rbp
0x180009910  retn
```
