# CRefresherCache::FindRefresherRecord(CRefresherId *,int,IUnknown *,CRefresherRecord * *)

- ea: `0x180084fdc`
- end: `0x1800852c9`
- name: `?FindRefresherRecord@CRefresherCache@@QEAAJPEAVCRefresherId@@HPEAUIUnknown@@PEAPEAVCRefresherRecord@@@Z`
- size: `749`
- prototype: `__int64 __usercall@<rax>(CRefresherCache *__hidden this@<rcx>, struct CRefresherId *@<rdx>, int@<r8d>, struct IUnknown *@<r9>, struct CRefresherRecord **)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800548a0`
- `0x1800558a4`
- `0x1800852d0`

## callees

- `0x180037120`
- `0x1800700c8`
- `0x18007212c`
- `0x180084fb4`
- `0x180084fdc`
- `0x18008a72c`
- `0x18009e010`

## import_xrefs

- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180085094`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x1800850bc`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x1800850d9`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180085094`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x1800850bc`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x1800850d9`
- `wbemcomn!GetMemLogObject` at `0x18008500e`
- `wbemcomn!GetMemLogObject` at `0x18008516a`
- `wbemcomn!GetMemLogObject` at `0x180085233`
- `wbemcomn!GetMemLogObject` at `0x18008500e`
- `wbemcomn!GetMemLogObject` at `0x18008516a`
- `wbemcomn!GetMemLogObject` at `0x180085233`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180085085`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x1800851ec`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180085085`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x1800851ec`
- `wbemcomn!?Add@CFlexArray@@QEAAHPEAX@Z` at `0x1800851df`
- `wbemcomn!?Add@CFlexArray@@QEAAHPEAX@Z` at `0x1800851df`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x1800850f7`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x1800851c9`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180085229`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180085294`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x1800852a6`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x1800850f7`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x1800851c9`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180085229`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180085294`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x1800852a6`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x180085072`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x180085072`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008501e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180085178`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180085241`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18008501e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180085178`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180085241`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180085109`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180085109`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall CRefresherCache::FindRefresherRecord(
        CRefresherCache *this,
        struct CRefresherId *a2,
        int a3,
        struct IUnknown *a4,
        struct CRefresherRecord **a5)
{
  struct CRefresherRecord **v8; // r14
  CMemoryLog *v9; // rax
  int v11; // edi
  unsigned int v12; // ebx
  char *v13; // rax
  __int64 v14; // rcx
  void *v15; // rax
  struct CRefresherRecord **v16; // rax
  struct CRefresherRecord **v17; // rdi
  struct CRefresherRecord **v18; // rdi
  CMemoryLog *v19; // rax
  CMemoryLog *MemLogObject; // rax
  _BYTE v21[56]; // [rsp+20h] [rbp-38h] BYREF

  v8 = a5;
  if ( a5 )
  {
    CInCritSec::CInCritSec((CInCritSec *)v21, (struct _RTL_CRITICAL_SECTION *)((char *)this + 232));
    v11 = 0;
    v12 = 1;
    while ( v11 < CFlexArray::Size((CRefresherCache *)((char *)this + 40)) )
    {
      v13 = (char *)CFlexArray::GetAt((CRefresherCache *)((char *)this + 40), v11);
      v14 = *(_QWORD *)(v13 + 36) - *(_QWORD *)((char *)a2 + 12);
      if ( !v14 )
        v14 = *(_QWORD *)(v13 + 44) - *(_QWORD *)((char *)a2 + 20);
      if ( !v14 )
      {
        v15 = CFlexArray::GetAt((CRefresherCache *)((char *)this + 40), v11);
        (*(void (__fastcall **)(void *))(*(_QWORD *)v15 + 8LL))(v15);
        *v8 = (struct CRefresherRecord *)CFlexArray::GetAt((CRefresherCache *)((char *)this + 40), v11);
        v12 = 0;
LABEL_16:
        CInCritSec::~CInCritSec((CInCritSec *)v21);
        return v12;
      }
      ++v11;
    }
    if ( !a3 )
    {
      *v8 = 0;
      goto LABEL_16;
    }
    v16 = (struct CRefresherRecord **)CWin32DefaultArena::WbemMemAlloc(0x110u);
    v17 = v16;
    a5 = v16;
    if ( v16 )
    {
      CRefresherRecord::CRefresherRecord((CRefresherRecord *)v16, a2, this, a4);
      *v17 = (struct CRefresherRecord *)&CRemoteRecord::`vftable'{for `IWbemRemoteRefresher'};
      v17[1] = (struct CRefresherRecord *)&CRemoteRecord::`vftable'{for `IWbemRefresher'};
    }
    else
    {
      v17 = 0;
    }
    std::unique_ptr<CClassInfo>::unique_ptr<CClassInfo>(&a5, (__int64)v17);
    v18 = a5;
    if ( a5 )
    {
      if ( !CFlexArray::Add((CRefresherCache *)((char *)this + 40), a5)
        && CFlexArray::Size((CRefresherCache *)((char *)this + 40)) - 1 >= 0 )
      {
        (*((void (__fastcall **)(struct CRefresherRecord **))*v18 + 1))(v18);
        *v8 = (struct CRefresherRecord *)std::unique_ptr<CUniversalRefresher::CRemote::CEnumRequest>::release(&a5);
        std::unique_ptr<CRefresherRecord>::~unique_ptr<CRefresherRecord>((__int64 *)&a5);
        CInCritSec::~CInCritSec((CInCritSec *)v21);
        return 0;
      }
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, -2147217402);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_583a410948f0357245c15279aca1a26e_Traceguids, 2147749894LL);
      }
    }
    else
    {
      v19 = GetMemLogObject();
      CMemoryLog::Write(v19, -2147217402);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_583a410948f0357245c15279aca1a26e_Traceguids, 2147749894LL);
      }
    }
    std::unique_ptr<CRefresherRecord>::~unique_ptr<CRefresherRecord>((__int64 *)&a5);
    CInCritSec::~CInCritSec((CInCritSec *)v21);
    return 2147749894LL;
  }
  v9 = GetMemLogObject();
  CMemoryLog::Write(v9, -2147217400);
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_583a410948f0357245c15279aca1a26e_Traceguids, 2147749896LL);
  }
  return 2147749896LL;
}

```

## disassembly

```asm
0x180084fdc  mov     [rsp+arg_0], rbx
0x180084fe1  mov     [rsp+arg_8], rsi
0x180084fe6  mov     [rsp+arg_18], r9
0x180084feb  push    rdi
0x180084fec  push    r12
0x180084fee  push    r13
0x180084ff0  push    r14
0x180084ff2  push    r15
0x180084ff4  sub     rsp, 30h
0x180084ff8  mov     r13d, r8d
0x180084ffb  mov     r12, rdx
0x180084ffe  mov     r15, rcx
0x180085001  mov     r14, [rsp+58h+arg_20]
0x180085009  test    r14, r14
0x18008500c  jnz     short loc_180085066
0x18008500e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180085014  mov     edi, 80041008h
0x180085019  mov     edx, edi
0x18008501b  mov     rcx, rax
0x18008501e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180085024  lea     rax, WPP_GLOBAL_Control
0x18008502b  mov     rcx, cs:WPP_GLOBAL_Control
0x180085032  cmp     rcx, rax
0x180085035  jz      short loc_18008505F
0x180085037  lea     ebx, [r14+1]
0x18008503b  test    [rcx+1Ch], bl
0x18008503e  jz      short loc_18008505F
0x180085040  cmp     byte ptr [rcx+19h], 2
0x180085044  jb      short loc_18008505F
0x180085046  lea     edx, [rbx+18h]
0x180085049  mov     r9d, 80041008h
0x18008504f  lea     r8, WPP_583a410948f0357245c15279aca1a26e_Traceguids
0x180085056  mov     rcx, [rcx+10h]
0x18008505a  call    WPP_SF_d
0x18008505f  mov     eax, edi
0x180085061  jmp     loc_1800852B1
0x180085066  lea     rdx, [rcx+0E8h]
0x18008506d  lea     rcx, [rsp+58h+var_38]
0x180085072  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x180085078  nop
0x180085079  xor     edi, edi
0x18008507b  lea     rsi, [r15+28h]
0x18008507f  lea     ebx, [rdi+1]
0x180085082  mov     rcx, rsi
0x180085085  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x18008508b  cmp     edi, eax
0x18008508d  jge     short loc_1800850E6
0x18008508f  mov     edx, edi
0x180085091  mov     rcx, rsi
0x180085094  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x18008509a  mov     rcx, [rax+24h]
0x18008509e  sub     rcx, [r12+0Ch]
0x1800850a3  jnz     short loc_1800850AE
0x1800850a5  mov     rcx, [rax+2Ch]
0x1800850a9  sub     rcx, [r12+14h]
0x1800850ae  test    rcx, rcx
0x1800850b1  jz      short loc_1800850B7
0x1800850b3  add     edi, ebx
0x1800850b5  jmp     short loc_180085082
0x1800850b7  mov     edx, edi
0x1800850b9  mov     rcx, rsi
0x1800850bc  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x1800850c2  mov     r8, rax
0x1800850c5  mov     rcx, [rax]
0x1800850c8  mov     rax, [rcx+8]
0x1800850cc  mov     rcx, r8
0x1800850cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800850d4  mov     edx, edi
0x1800850d6  mov     rcx, rsi
0x1800850d9  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x1800850df  mov     [r14], rax
0x1800850e2  xor     ebx, ebx
0x1800850e4  jmp     short loc_1800850F2
0x1800850e6  test    r13d, r13d
0x1800850e9  jnz     short loc_180085104
0x1800850eb  mov     qword ptr [r14], 0
0x1800850f2  lea     rcx, [rsp+58h+var_38]
0x1800850f7  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x1800850fd  mov     eax, ebx
0x1800850ff  jmp     loc_1800852B1
0x180085104  mov     ecx, 110h
0x180085109  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18008510f  mov     rdi, rax
0x180085112  mov     [rsp+58h+arg_20], rax
0x18008511a  test    rax, rax
0x18008511d  jz      short loc_18008514A
0x18008511f  mov     r9, [rsp+58h+arg_18]; struct IUnknown *
0x180085124  mov     r8, r15; struct CRefresherCache *
0x180085127  mov     rdx, r12; struct _WBEM_REFRESHER_ID *
0x18008512a  mov     rcx, rax; this
0x18008512d  call    ??0CRefresherRecord@@QEAA@AEBU_WBEM_REFRESHER_ID@@PEAVCRefresherCache@@PEAUIUnknown@@@Z; CRefresherRecord::CRefresherRecord(_WBEM_REFRESHER_ID const &,CRefresherCache *,IUnknown *)
0x180085132  nop
0x180085133  lea     rax, ??_7CRemoteRecord@@6BIWbemRemoteRefresher@@@; const CRemoteRecord::`vftable'{for `IWbemRemoteRefresher'}
0x18008513a  mov     [rdi], rax
0x18008513d  lea     rax, ??_7CRemoteRecord@@6BIWbemRefresher@@@; const CRemoteRecord::`vftable'{for `IWbemRefresher'}
0x180085144  mov     [rdi+8], rax
0x180085148  jmp     short loc_18008514C
0x18008514a  xor     edi, edi
0x18008514c  mov     rdx, rdi
0x18008514f  lea     rcx, [rsp+58h+arg_20]
0x180085157  call    ??0?$unique_ptr@UCClassInfo@@U?$default_delete@UCClassInfo@@@std@@@std@@QEAA@PEAUCClassInfo@@@Z; std::unique_ptr<CClassInfo>::unique_ptr<CClassInfo>(CClassInfo *)
0x18008515c  nop
0x18008515d  mov     rdi, [rsp+58h+arg_20]
0x180085165  test    rdi, rdi
0x180085168  jnz     short loc_1800851D9
0x18008516a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180085170  mov     edx, 80041006h
0x180085175  mov     rcx, rax
0x180085178  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18008517e  lea     rax, WPP_GLOBAL_Control
0x180085185  mov     rcx, cs:WPP_GLOBAL_Control
0x18008518c  cmp     rcx, rax
0x18008518f  jz      short loc_1800851B6
0x180085191  test    [rcx+1Ch], bl
0x180085194  jz      short loc_1800851B6
0x180085196  cmp     byte ptr [rcx+19h], 2
0x18008519a  jb      short loc_1800851B6
0x18008519c  lea     edx, [rdi+1Ah]
0x18008519f  mov     r9d, 80041006h
0x1800851a5  lea     r8, WPP_583a410948f0357245c15279aca1a26e_Traceguids
0x1800851ac  mov     rcx, [rcx+10h]
0x1800851b0  call    WPP_SF_d
0x1800851b5  nop
0x1800851b6  lea     rcx, [rsp+58h+arg_20]
0x1800851be  call    ??1?$unique_ptr@VCRefresherRecord@@U?$default_delete@VCRefresherRecord@@@std@@@std@@QEAA@XZ; std::unique_ptr<CRefresherRecord>::~unique_ptr<CRefresherRecord>(void)
0x1800851c3  nop
0x1800851c4  lea     rcx, [rsp+58h+var_38]
0x1800851c9  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x1800851cf  mov     eax, 80041006h
0x1800851d4  jmp     loc_1800852B1
0x1800851d9  mov     rdx, rdi
0x1800851dc  mov     rcx, rsi
0x1800851df  call    cs:__imp_?Add@CFlexArray@@QEAAHPEAX@Z; CFlexArray::Add(void *)
0x1800851e5  test    eax, eax
0x1800851e7  jnz     short loc_180085233
0x1800851e9  mov     rcx, rsi
0x1800851ec  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x1800851f2  cmp     eax, 1
0x1800851f5  js      short loc_180085233
0x1800851f7  mov     rax, [rdi]
0x1800851fa  mov     rcx, rdi
0x1800851fd  mov     rax, [rax+8]
0x180085201  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085206  lea     rcx, [rsp+58h+arg_20]
0x18008520e  call    ?release@?$unique_ptr@VCEnumRequest@CRemote@CUniversalRefresher@@U?$default_delete@VCEnumRequest@CRemote@CUniversalRefresher@@@std@@@std@@QEAAPEAVCEnumRequest@CRemote@CUniversalRefresher@@XZ; std::unique_ptr<CUniversalRefresher::CRemote::CEnumRequest>::release(void)
0x180085213  mov     [r14], rax
0x180085216  lea     rcx, [rsp+58h+arg_20]
0x18008521e  call    ??1?$unique_ptr@VCRefresherRecord@@U?$default_delete@VCRefresherRecord@@@std@@@std@@QEAA@XZ; std::unique_ptr<CRefresherRecord>::~unique_ptr<CRefresherRecord>(void)
0x180085223  nop
0x180085224  lea     rcx, [rsp+58h+var_38]
0x180085229  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x18008522f  xor     eax, eax
0x180085231  jmp     short loc_1800852B1
0x180085233  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180085239  mov     edx, 80041006h
0x18008523e  mov     rcx, rax
0x180085241  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180085247  lea     rax, WPP_GLOBAL_Control
0x18008524e  mov     rcx, cs:WPP_GLOBAL_Control
0x180085255  cmp     rcx, rax
0x180085258  jz      short loc_180085281
0x18008525a  test    [rcx+1Ch], bl
0x18008525d  jz      short loc_180085281
0x18008525f  cmp     byte ptr [rcx+19h], 2
0x180085263  jb      short loc_180085281
0x180085265  mov     edx, 1Bh
0x18008526a  mov     r9d, 80041006h
0x180085270  lea     r8, WPP_583a410948f0357245c15279aca1a26e_Traceguids
0x180085277  mov     rcx, [rcx+10h]
0x18008527b  call    WPP_SF_d
0x180085280  nop
0x180085281  lea     rcx, [rsp+58h+arg_20]
0x180085289  call    ??1?$unique_ptr@VCRefresherRecord@@U?$default_delete@VCRefresherRecord@@@std@@@std@@QEAA@XZ; std::unique_ptr<CRefresherRecord>::~unique_ptr<CRefresherRecord>(void)
0x18008528e  nop
0x18008528f  lea     rcx, [rsp+58h+var_38]
0x180085294  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x18008529a  mov     eax, 80041006h
0x18008529f  jmp     short loc_1800852B1
0x1800852a1  lea     rcx, [rsp+58h+var_38]
0x1800852a6  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x1800852ac  mov     eax, 80041006h
0x1800852b1  mov     rbx, [rsp+58h+arg_0]
0x1800852b6  mov     rsi, [rsp+58h+arg_8]
0x1800852bb  add     rsp, 30h
0x1800852bf  pop     r15
0x1800852c1  pop     r14
0x1800852c3  pop     r13
0x1800852c5  pop     r12
0x1800852c7  pop     rdi
0x1800852c8  retn
```
