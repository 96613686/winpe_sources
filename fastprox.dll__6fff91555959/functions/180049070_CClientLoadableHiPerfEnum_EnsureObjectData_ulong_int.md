# CClientLoadableHiPerfEnum::EnsureObjectData(ulong,int)

- ea: `0x180049070`
- end: `0x180049397`
- name: `?EnsureObjectData@CClientLoadableHiPerfEnum@@IEAAJKH@Z`
- size: `807`
- prototype: `__int64 __fastcall(CClientLoadableHiPerfEnum *__hidden this, unsigned int, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180048614`
- `0x180071574`

## callees

- `0x180037120`
- `0x180049070`
- `0x1800496d0`
- `0x1800700c8`
- `0x180070868`
- `0x18007212c`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18004915b`
- `wbemcomn!GetMemLogObject` at `0x18004924a`
- `wbemcomn!GetMemLogObject` at `0x180049296`
- `wbemcomn!GetMemLogObject` at `0x18004915b`
- `wbemcomn!GetMemLogObject` at `0x18004924a`
- `wbemcomn!GetMemLogObject` at `0x180049296`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x1800490a2`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x1800490ad`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x1800490c2`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x1800490d4`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18004911a`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180049130`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x1800492fe`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180049315`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18004933e`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180049357`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x1800490a2`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x1800490ad`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x1800490c2`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x1800490d4`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18004911a`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180049130`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x1800492fe`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180049315`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18004933e`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180049357`
- `wbemcomn!?Add@CFlexArray@@QEAAHPEAX@Z` at `0x180049148`
- `wbemcomn!?Add@CFlexArray@@QEAAHPEAX@Z` at `0x180049226`
- `wbemcomn!?Add@CFlexArray@@QEAAHPEAX@Z` at `0x18004932d`
- `wbemcomn!?Add@CFlexArray@@QEAAHPEAX@Z` at `0x180049148`
- `wbemcomn!?Add@CFlexArray@@QEAAHPEAX@Z` at `0x180049226`
- `wbemcomn!?Add@CFlexArray@@QEAAHPEAX@Z` at `0x18004932d`
- `wbemcomn!?RemoveAt@CFlexArray@@QEAAHH@Z` at `0x18004934a`
- `wbemcomn!?RemoveAt@CFlexArray@@QEAAHH@Z` at `0x180049363`
- `wbemcomn!?RemoveAt@CFlexArray@@QEAAHH@Z` at `0x18004934a`
- `wbemcomn!?RemoveAt@CFlexArray@@QEAAHH@Z` at `0x180049363`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180049166`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004925a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800492a6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180049166`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004925a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800492a6`
- `wbemcomn!??ACFlexArray@@QEAAAEAPEAXH@Z` at `0x18004913c`
- `wbemcomn!??ACFlexArray@@QEAAAEAPEAXH@Z` at `0x180049321`
- `wbemcomn!??ACFlexArray@@QEAAAEAPEAXH@Z` at `0x18004913c`
- `wbemcomn!??ACFlexArray@@QEAAAEAPEAXH@Z` at `0x180049321`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800491da`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800491da`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CClientLoadableHiPerfEnum::EnsureObjectData(
        CClientLoadableHiPerfEnum *this,
        unsigned int a2,
        int a3)
{
  int v5; // edi
  CFlexArray *v6; // rsi
  CFlexArray *v7; // r12
  int v8; // ebx
  unsigned int v9; // edx
  unsigned int v11; // r15d
  unsigned int j; // ebx
  int v13; // eax
  void **v14; // rax
  CMemoryLog *MemLogObject; // rax
  struct IWbemObjectAccess *v16; // rax
  unsigned int v17; // edx
  unsigned int k; // ebx
  CMemoryLog *v19; // rax
  unsigned int v20; // edx
  CWbemRefreshingSvc *v21; // rcx
  unsigned int v22; // r15d
  CMemoryLog *v23; // rax
  __int64 v24; // rdx
  unsigned int v25; // r14d
  unsigned int i; // ebx
  int v27; // eax
  void **v28; // rax
  int v29; // eax
  int v30; // eax
  struct IWbemObjectAccess *v31[2]; // [rsp+20h] [rbp-10h] BYREF
  CUniversalRefresher::CNestedRefresher *v32; // [rsp+70h] [rbp+40h] BYREF
  int v33; // [rsp+80h] [rbp+50h]
  __int64 v34; // [rsp+88h] [rbp+58h] BYREF

  v33 = a3;
  v5 = 0;
  v6 = (CClientLoadableHiPerfEnum *)((char *)this + 24);
  v7 = (CClientLoadableHiPerfEnum *)((char *)this + 136);
  v8 = CFlexArray::Size((CClientLoadableHiPerfEnum *)((char *)this + 136));
  v9 = CFlexArray::Size(v6) + v8;
  if ( a2 <= v9 )
  {
LABEL_2:
    if ( a2 > CFlexArray::Size(v6) )
    {
      v25 = a2 - CFlexArray::Size(v6);
      for ( i = 0; i < v25; ++i )
      {
        v27 = CFlexArray::Size(v7);
        v28 = (void **)CFlexArray::operator[](v7, (unsigned int)(v27 - 1));
        if ( CFlexArray::Add(v6, *v28) )
        {
LABEL_10:
          v5 = -2147217402;
          goto LABEL_11;
        }
        v29 = CFlexArray::Size(v7);
        CFlexArray::RemoveAt(v7, v29 - 1);
      }
    }
    else if ( a2 < CFlexArray::Size(v6) )
    {
      v11 = CFlexArray::Size(v6) - a2;
      for ( j = 0; j < v11; ++j )
      {
        v13 = CFlexArray::Size(v6);
        v14 = (void **)CFlexArray::operator[](v6, (unsigned int)(v13 - 1));
        if ( CFlexArray::Add(v7, *v14) )
          goto LABEL_10;
        v30 = CFlexArray::Size(v6);
        CFlexArray::RemoveAt(v6, v30 - 1);
      }
    }
LABEL_4:
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        WPP_130b2b029f413412596981c5d88fbd87_Traceguids,
        (unsigned int)v5);
    }
    return (unsigned int)v5;
  }
  v22 = a2 - v9;
  v34 = 0;
  v31[0] = 0;
  for ( k = 0; ; ++k )
  {
    if ( v5 < 0 )
    {
LABEL_11:
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v5);
      goto LABEL_4;
    }
    if ( k >= v22 )
      goto LABEL_2;
    if ( v33 )
    {
      v5 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 30) + 96LL))(
             *((_QWORD *)this + 30),
             &v34);
      if ( v5 < 0 )
        continue;
      v5 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IWbemObjectAccess **))v34)(
             v34,
             &IID_IWbemObjectAccess,
             v31);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
      if ( v5 < 0 )
        continue;
    }
    v16 = (struct IWbemObjectAccess *)CWin32DefaultArena::WbemMemAlloc(0x10u);
    v31[1] = v16;
    if ( v16 )
      v16 = (struct IWbemObjectAccess *)CHiPerfEnumData::CHiPerfEnumData((CHiPerfEnumData *)v16, 0, v31[0]);
    std::unique_ptr<CClassInfo>::unique_ptr<CClassInfo>(&v32, (__int64)v16);
    if ( v31[0] )
      ((void (__fastcall *)(struct IWbemObjectAccess *))v31[0]->lpVtbl->Release)(v31[0]);
    if ( !v32 )
      break;
    if ( CFlexArray::Add(v6, v32) )
    {
      v23 = GetMemLogObject();
      v5 = -2147217402;
      CMemoryLog::Write(v23, -2147217402);
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v24 = 14;
LABEL_35:
        WPP_SF_d(*((_QWORD *)v21 + 2), v24, WPP_130b2b029f413412596981c5d88fbd87_Traceguids, 2147749894LL);
        goto LABEL_26;
      }
      goto LABEL_26;
    }
    std::unique_ptr<CUniversalRefresher::CRemote::CEnumRequest>::release(&v32);
    std::unique_ptr<CUniversalRefresher::CNestedRefresher>::~unique_ptr<CUniversalRefresher::CNestedRefresher>(
      &v32,
      v17);
  }
  v19 = GetMemLogObject();
  v5 = -2147217402;
  CMemoryLog::Write(v19, -2147217402);
  v21 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v24 = 13;
    goto LABEL_35;
  }
LABEL_26:
  std::unique_ptr<CUniversalRefresher::CNestedRefresher>::~unique_ptr<CUniversalRefresher::CNestedRefresher>(&v32, v20);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180049070  mov     [rsp-38h+arg_8], rbx
0x180049075  mov     [rsp-38h+arg_10], r8d
0x18004907a  push    rbp
0x18004907b  push    rsi
0x18004907c  push    rdi
0x18004907d  push    r12
0x18004907f  push    r13
0x180049081  push    r14
0x180049083  push    r15
0x180049085  mov     rbp, rsp
0x180049088  sub     rsp, 30h
0x18004908c  mov     r14d, edx
0x18004908f  mov     r13, rcx
0x180049092  xor     edi, edi
0x180049094  lea     rsi, [rcx+18h]
0x180049098  lea     r12, [rcx+88h]
0x18004909f  mov     rcx, r12
0x1800490a2  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x1800490a8  mov     ebx, eax
0x1800490aa  mov     rcx, rsi
0x1800490ad  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x1800490b3  lea     edx, [rax+rbx]
0x1800490b6  cmp     r14d, edx
0x1800490b9  ja      loc_180049281
0x1800490bf  mov     rcx, rsi
0x1800490c2  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x1800490c8  mov     rcx, rsi
0x1800490cb  cmp     r14d, eax
0x1800490ce  ja      loc_1800492FE
0x1800490d4  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x1800490da  cmp     r14d, eax
0x1800490dd  jb      short loc_180049117
0x1800490df  test    edi, edi
0x1800490e1  js      short loc_18004915B
0x1800490e3  lea     rax, WPP_GLOBAL_Control
0x1800490ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800490f1  cmp     rcx, rax
0x1800490f4  jz      short loc_180049100
0x1800490f6  test    byte ptr [rcx+1Ch], 1
0x1800490fa  jnz     loc_180049370
0x180049100  mov     eax, edi
0x180049102  mov     rbx, [rsp+30h+arg_8]
0x180049107  add     rsp, 30h
0x18004910b  pop     r15
0x18004910d  pop     r14
0x18004910f  pop     r13
0x180049111  pop     r12
0x180049113  pop     rdi
0x180049114  pop     rsi
0x180049115  pop     rbp
0x180049116  retn
0x180049117  mov     rcx, rsi
0x18004911a  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x180049120  mov     r15d, eax
0x180049123  sub     r15d, r14d
0x180049126  xor     ebx, ebx
0x180049128  cmp     ebx, r15d
0x18004912b  jnb     short loc_1800490DF
0x18004912d  mov     rcx, rsi
0x180049130  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x180049136  lea     edx, [rax-1]
0x180049139  mov     rcx, rsi
0x18004913c  call    cs:__imp_??ACFlexArray@@QEAAAEAPEAXH@Z; CFlexArray::operator[](int)
0x180049142  mov     rdx, [rax]
0x180049145  mov     rcx, r12
0x180049148  call    cs:__imp_?Add@CFlexArray@@QEAAHPEAX@Z; CFlexArray::Add(void *)
0x18004914e  test    eax, eax
0x180049150  jz      loc_180049354
0x180049156  mov     edi, 80041006h
0x18004915b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180049161  mov     edx, edi
0x180049163  mov     rcx, rax
0x180049166  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004916c  jmp     loc_1800490E3
0x180049171  test    edi, edi
0x180049173  js      short loc_18004915B
0x180049175  cmp     ebx, r15d
0x180049178  jnb     loc_1800490BF
0x18004917e  cmp     [rbp+arg_10], 0
0x180049182  jz      short loc_1800491D5
0x180049184  mov     rcx, [r13+0F0h]
0x18004918b  mov     rax, [rcx]
0x18004918e  lea     rdx, [rbp+arg_18]
0x180049192  mov     rax, [rax+60h]
0x180049196  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004919b  mov     edi, eax
0x18004919d  test    eax, eax
0x18004919f  js      loc_180049243
0x1800491a5  mov     rcx, [rbp+arg_18]
0x1800491a9  mov     rax, [rcx]
0x1800491ac  lea     r8, [rbp+var_10]
0x1800491b0  lea     rdx, IID_IWbemObjectAccess
0x1800491b7  mov     rax, [rax]
0x1800491ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800491bf  mov     edi, eax
0x1800491c1  mov     rcx, [rbp+arg_18]
0x1800491c5  mov     rax, [rcx]
0x1800491c8  mov     rax, [rax+10h]
0x1800491cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800491d1  test    edi, edi
0x1800491d3  js      short loc_180049243
0x1800491d5  mov     ecx, 10h
0x1800491da  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800491e0  mov     [rbp+var_8], rax
0x1800491e4  test    rax, rax
0x1800491e7  jz      short loc_1800491F8
0x1800491e9  mov     r8, [rbp+var_10]; struct IWbemObjectAccess *
0x1800491ed  xor     edx, edx; int
0x1800491ef  mov     rcx, rax; this
0x1800491f2  call    ??0CHiPerfEnumData@@QEAA@JPEAUIWbemObjectAccess@@@Z; CHiPerfEnumData::CHiPerfEnumData(long,IWbemObjectAccess *)
0x1800491f7  nop
0x1800491f8  mov     rdx, rax
0x1800491fb  lea     rcx, [rbp+arg_0]
0x1800491ff  call    ??0?$unique_ptr@UCClassInfo@@U?$default_delete@UCClassInfo@@@std@@@std@@QEAA@PEAUCClassInfo@@@Z; std::unique_ptr<CClassInfo>::unique_ptr<CClassInfo>(CClassInfo *)
0x180049204  nop
0x180049205  mov     rcx, [rbp+var_10]
0x180049209  test    rcx, rcx
0x18004920c  jz      short loc_18004921A
0x18004920e  mov     rax, [rcx]
0x180049211  mov     rax, [rax+10h]
0x180049215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004921a  mov     rdx, [rbp+arg_0]
0x18004921e  test    rdx, rdx
0x180049221  jz      short loc_18004924A
0x180049223  mov     rcx, rsi
0x180049226  call    cs:__imp_?Add@CFlexArray@@QEAAHPEAX@Z; CFlexArray::Add(void *)
0x18004922c  test    eax, eax
0x18004922e  jnz     short loc_180049296
0x180049230  lea     rcx, [rbp+arg_0]
0x180049234  call    ?release@?$unique_ptr@VCEnumRequest@CRemote@CUniversalRefresher@@U?$default_delete@VCEnumRequest@CRemote@CUniversalRefresher@@@std@@@std@@QEAAPEAVCEnumRequest@CRemote@CUniversalRefresher@@XZ; std::unique_ptr<CUniversalRefresher::CRemote::CEnumRequest>::release(void)
0x180049239  nop
0x18004923a  lea     rcx, [rbp+arg_0]
0x18004923e  call    ??1?$unique_ptr@VCNestedRefresher@CUniversalRefresher@@U?$default_delete@VCNestedRefresher@CUniversalRefresher@@@std@@@std@@QEAA@XZ; std::unique_ptr<CUniversalRefresher::CNestedRefresher>::~unique_ptr<CUniversalRefresher::CNestedRefresher>(void)
0x180049243  inc     ebx
0x180049245  jmp     loc_180049171
0x18004924a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180049250  mov     edi, 80041006h
0x180049255  mov     edx, edi
0x180049257  mov     rcx, rax
0x18004925a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180049260  lea     rax, WPP_GLOBAL_Control
0x180049267  mov     rcx, cs:WPP_GLOBAL_Control
0x18004926e  cmp     rcx, rax
0x180049271  jnz     short loc_1800492D2
0x180049273  lea     rcx, [rbp+arg_0]
0x180049277  call    ??1?$unique_ptr@VCNestedRefresher@CUniversalRefresher@@U?$default_delete@VCNestedRefresher@CUniversalRefresher@@@std@@@std@@QEAA@XZ; std::unique_ptr<CUniversalRefresher::CNestedRefresher>::~unique_ptr<CUniversalRefresher::CNestedRefresher>(void)
0x18004927c  jmp     loc_180049100
0x180049281  mov     r15d, r14d
0x180049284  sub     r15d, edx
0x180049287  mov     [rbp+arg_18], rdi
0x18004928b  mov     [rbp+var_10], rdi
0x18004928f  xor     ebx, ebx
0x180049291  jmp     loc_180049171
0x180049296  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004929c  mov     edi, 80041006h
0x1800492a1  mov     edx, edi
0x1800492a3  mov     rcx, rax
0x1800492a6  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800492ac  lea     rax, WPP_GLOBAL_Control
0x1800492b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800492ba  cmp     rcx, rax
0x1800492bd  jz      short loc_180049273
0x1800492bf  test    byte ptr [rcx+1Ch], 1
0x1800492c3  jz      short loc_180049273
0x1800492c5  cmp     byte ptr [rcx+19h], 2
0x1800492c9  jb      short loc_180049273
0x1800492cb  mov     edx, 0Eh
0x1800492d0  jmp     short loc_1800492E3
0x1800492d2  test    byte ptr [rcx+1Ch], 1
0x1800492d6  jz      short loc_180049273
0x1800492d8  cmp     byte ptr [rcx+19h], 2
0x1800492dc  jb      short loc_180049273
0x1800492de  mov     edx, 0Dh
0x1800492e3  mov     r9d, 80041006h
0x1800492e9  lea     r8, WPP_130b2b029f413412596981c5d88fbd87_Traceguids
0x1800492f0  mov     rcx, [rcx+10h]
0x1800492f4  call    WPP_SF_d
0x1800492f9  jmp     loc_180049273
0x1800492fe  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x180049304  sub     r14d, eax
0x180049307  xor     ebx, ebx
0x180049309  cmp     ebx, r14d
0x18004930c  jnb     loc_1800490DF
0x180049312  mov     rcx, r12
0x180049315  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x18004931b  lea     edx, [rax-1]
0x18004931e  mov     rcx, r12
0x180049321  call    cs:__imp_??ACFlexArray@@QEAAAEAPEAXH@Z; CFlexArray::operator[](int)
0x180049327  mov     rdx, [rax]
0x18004932a  mov     rcx, rsi
0x18004932d  call    cs:__imp_?Add@CFlexArray@@QEAAHPEAX@Z; CFlexArray::Add(void *)
0x180049333  test    eax, eax
0x180049335  jnz     loc_180049156
0x18004933b  mov     rcx, r12
0x18004933e  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x180049344  lea     edx, [rax-1]
0x180049347  mov     rcx, r12
0x18004934a  call    cs:__imp_?RemoveAt@CFlexArray@@QEAAHH@Z; CFlexArray::RemoveAt(int)
0x180049350  inc     ebx
0x180049352  jmp     short loc_180049309
0x180049354  mov     rcx, rsi
0x180049357  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x18004935d  lea     edx, [rax-1]
0x180049360  mov     rcx, rsi
0x180049363  call    cs:__imp_?RemoveAt@CFlexArray@@QEAAHH@Z; CFlexArray::RemoveAt(int)
0x180049369  inc     ebx
0x18004936b  jmp     loc_180049128
0x180049370  cmp     byte ptr [rcx+19h], 2
0x180049374  jb      loc_180049100
0x18004937a  mov     edx, 0Fh
0x18004937f  mov     r9d, edi
0x180049382  lea     r8, WPP_130b2b029f413412596981c5d88fbd87_Traceguids
0x180049389  mov     rcx, [rcx+10h]
0x18004938d  call    WPP_SF_d
0x180049392  jmp     loc_180049100
```
