# CSession::PutObject(IWmiDbHandle *,_GUID const &,void *,ulong,ulong,IWmiDbHandle * *)

- ea: `0x18001cc50`
- end: `0x18001d22d`
- name: `?PutObject@CSession@@UEAAJPEAUIWmiDbHandle@@AEBU_GUID@@PEAXKKPEAPEAU2@@Z`
- size: `1501`
- prototype: `__int64 __fastcall(CSession *__hidden this, struct IWmiDbHandle *, const struct _GUID *, void *, unsigned int, unsigned int, struct IWmiDbHandle **)`
- caller_count: `0`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x18001b578`
- `0x18001c038`
- `0x18001cc50`
- `0x18001d234`
- `0x18001d258`
- `0x18001d334`
- `0x18001d5f0`
- `0x18001d7bc`
- `0x18001e1f0`
- `0x18001e270`
- `0x180027e8c`
- `0x1800283e8`
- `0x1800356f0`
- `0x180048010`

## import_xrefs

- `wbemcomn!??0CCritSec@@QEAA@XZ` at `0x18001ccc9`
- `wbemcomn!??0CCritSec@@QEAA@XZ` at `0x18001ccc9`
- `wbemcomn!??1CCritSec@@QEAA@XZ` at `0x18001ce61`
- `wbemcomn!??1CCritSec@@QEAA@XZ` at `0x18001cecf`
- `wbemcomn!??1CCritSec@@QEAA@XZ` at `0x18001ce61`
- `wbemcomn!??1CCritSec@@QEAA@XZ` at `0x18001cecf`
- `wbemcomn!??0CFlexArray@@QEAA@HH@Z` at `0x18001ccb2`
- `wbemcomn!??0CFlexArray@@QEAA@HH@Z` at `0x18001ccb2`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18001ce19`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18001ce19`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18001ce3b`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18001ce3b`
- `wbemcomn!GetMemLogObject` at `0x18001ce99`
- `wbemcomn!GetMemLogObject` at `0x18001cfd7`
- `wbemcomn!GetMemLogObject` at `0x18001d086`
- `wbemcomn!GetMemLogObject` at `0x18001d0f7`
- `wbemcomn!GetMemLogObject` at `0x18001d1de`
- `wbemcomn!GetMemLogObject` at `0x18001ce99`
- `wbemcomn!GetMemLogObject` at `0x18001cfd7`
- `wbemcomn!GetMemLogObject` at `0x18001d086`
- `wbemcomn!GetMemLogObject` at `0x18001d0f7`
- `wbemcomn!GetMemLogObject` at `0x18001d1de`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001ceaa`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001cfe7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001d091`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001d107`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001d1e9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001ceaa`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001cfe7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001d091`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001d107`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001d1e9`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CSession::PutObject(
        CSession *this,
        struct IWmiDbHandle *a2,
        const struct _GUID *a3,
        void *a4,
        unsigned int a5,
        unsigned int a6,
        struct IWmiDbHandle **a7)
{
  int v10; // edi
  const struct _GUID *v11; // rdx
  int v12; // eax
  bool v13; // dl
  int v14; // eax
  unsigned int v15; // ebx
  struct CEventCollector *v16; // rcx
  int v17; // eax
  int v18; // ebx
  struct _IWmiCoreServices *v19; // rbx
  CMemoryLog *v21; // rax
  CMemoryLog *v22; // rax
  CMemoryLog *v23; // rax
  CMemoryLog *v24; // rax
  unsigned int v25; // ebx
  CMemoryLog *MemLogObject; // rax
  unsigned int v27; // [rsp+20h] [rbp-108h]
  CSession *v28; // [rsp+40h] [rbp-E8h] BYREF
  char v29; // [rsp+48h] [rbp-E0h]
  __int16 v30; // [rsp+49h] [rbp-DFh]
  __int128 *v31; // [rsp+50h] [rbp-D8h] BYREF
  int v32; // [rsp+58h] [rbp-D0h]
  _BYTE v33[96]; // [rsp+60h] [rbp-C8h] BYREF
  char v34; // [rsp+C0h] [rbp-68h]
  struct _RTL_CRITICAL_SECTION v35[2]; // [rsp+C8h] [rbp-60h] BYREF
  struct _IWmiCoreServices *v36; // [rsp+130h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids);
  }
  v31 = &g_readWriteLock;
  v10 = 0;
  v32 = 0;
  v28 = this;
  v30 = 256;
  CFlexArray::CFlexArray((CFlexArray *)v33, 8, 100);
  v34 = 0;
  CCritSec::CCritSec((CCritSec *)v35);
  if ( *((_BYTE *)this + 168) )
  {
    if ( !g_bShuttingDown )
    {
      v16 = (CSession *)((char *)this + 24);
LABEL_7:
      if ( *(int *)(*((_QWORD *)a2 + 11) + 48LL) < 0 )
      {
        if ( !*((_BYTE *)this + 168) )
          CAutoTransaction::InternalAbortTransaction((CAutoTransaction *)&v28);
        v25 = *(_DWORD *)(*((_QWORD *)a2 + 11) + 48LL);
        CEventCollector::~CEventCollector((CEventCollector *)v33);
        CAutoTransaction::~CAutoTransaction((CAutoTransaction *)&v28);
        CAutoWriteLock::Unlock((CAutoWriteLock *)&v31);
        return v25;
      }
      else
      {
        v17 = CNamespaceHandle::PutObject(a2, v11, a4, a5, v27, a7, v16);
        v18 = v17;
        if ( !*((_BYTE *)this + 168) )
        {
          if ( v17 < 0 )
          {
            CAutoTransaction::InternalAbortTransaction((CAutoTransaction *)&v28);
          }
          else
          {
            LOBYTE(v30) = 0;
            if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids);
            }
            if ( v29 )
              CFileCache::CommitTransaction((CFileCache *)byte_180058AF8);
            byte_180058AF0 = 0;
            if ( v10 )
            {
              CLock::WriteUnlock((CLock *)&g_readWriteLock);
              v10 = 0;
              v32 = 0;
            }
            if ( g_Glob && qword_180058A78 )
            {
              (*(void (__fastcall **)(struct _IWmiCoreServices *))(*(_QWORD *)qword_180058A78 + 8LL))(qword_180058A78);
              v19 = qword_180058A78;
              v36 = qword_180058A78;
              CEventCollector::SendEvents((CEventCollector *)v33, qword_180058A78);
              if ( v19 )
                (*(void (__fastcall **)(struct _IWmiCoreServices *))(*(_QWORD *)v19 + 16LL))(v19);
              v18 = 0;
            }
            else
            {
              v18 = -2147217388;
            }
          }
          CInCritSec::CInCritSec((CInCritSec *)&v36, v35);
          v34 = 0;
          CPointerArray<CRepEvent,CUniqueManager<CRepEvent>,CFlexArray>::RemoveAll(v33);
          CInCritSec::~CInCritSec((CInCritSec *)&v36);
        }
        if ( v18 < 0 )
        {
          MemLogObject = GetMemLogObject();
          CMemoryLog::Write(MemLogObject, v18);
        }
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            35,
            WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
            (unsigned int)v18);
        }
        CCritSec::~CCritSec((CCritSec *)v35);
        CPointerArray<CRepEvent,CUniqueManager<CRepEvent>,CFlexArray>::~CPointerArray<CRepEvent,CUniqueManager<CRepEvent>,CFlexArray>(v33);
        if ( (_BYTE)v30 )
          CAutoTransaction::InternalAbortTransaction((CAutoTransaction *)&v28);
        if ( v10 )
        {
          CLock::WriteUnlock((CLock *)&g_readWriteLock);
          v32 = 0;
        }
        return (unsigned int)v18;
      }
    }
    v24 = GetMemLogObject();
    CMemoryLog::Write(v24, -2147217357);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749939LL);
    }
    CEventCollector::~CEventCollector((CEventCollector *)v33);
    CAutoTransaction::~CAutoTransaction((CAutoTransaction *)&v28);
    CAutoWriteLock::Unlock((CAutoWriteLock *)&v31);
    return 2147749939LL;
  }
  else
  {
    v12 = CLock::WriteLock((CLock *)&g_readWriteLock, (unsigned int)v11);
    LOBYTE(v10) = v12 == 0;
    v32 = v10;
    if ( v12 )
    {
      v22 = GetMemLogObject();
      CMemoryLog::Write(v22, -2147217407);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749889LL);
      }
      CEventCollector::~CEventCollector((CEventCollector *)v33);
      CAutoTransaction::~CAutoTransaction((CAutoTransaction *)&v28);
      CAutoWriteLock::Unlock((CAutoWriteLock *)&v31);
      return 2147749889LL;
    }
    else if ( g_bShuttingDown )
    {
      v21 = GetMemLogObject();
      CMemoryLog::Write(v21, -2147217357);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749939LL);
      }
      CCritSec::~CCritSec((CCritSec *)v35);
      CPointerArray<CRepEvent,CUniqueManager<CRepEvent>,CFlexArray>::~CPointerArray<CRepEvent,CUniqueManager<CRepEvent>,CFlexArray>(v33);
      if ( v10 )
      {
        CLock::WriteUnlock((CLock *)&g_readWriteLock);
        v32 = 0;
      }
      return 2147749939LL;
    }
    else
    {
      v14 = CAutoTransaction::InternalBeginTransaction((CAutoTransaction *)&v28, v13);
      v15 = v14;
      if ( !v14 )
      {
        v16 = (struct CEventCollector *)v33;
        byte_180058AF0 = 0;
        goto LABEL_7;
      }
      if ( v14 < 0 )
      {
        v23 = GetMemLogObject();
        CMemoryLog::Write(v23, v15);
      }
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, v15);
      }
      CEventCollector::~CEventCollector((CEventCollector *)v33);
      CAutoTransaction::~CAutoTransaction((CAutoTransaction *)&v28);
      CAutoWriteLock::Unlock((CAutoWriteLock *)&v31);
      return v15;
    }
  }
}

```

## disassembly

```asm
0x18001cc50  push    rbx
0x18001cc52  push    rdi
0x18001cc53  push    r12
0x18001cc55  push    r13
0x18001cc57  push    r14
0x18001cc59  push    r15
0x18001cc5b  sub     rsp, 0F8h
0x18001cc62  mov     r12, r9
0x18001cc65  mov     r15, rdx
0x18001cc68  mov     r14, rcx
0x18001cc6b  lea     rax, WPP_GLOBAL_Control
0x18001cc72  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cc79  cmp     rcx, rax
0x18001cc7c  jnz     loc_18001CFA9
0x18001cc82  lea     rbx, ?g_readWriteLock@@3VCLock@@A; CLock g_readWriteLock
0x18001cc89  mov     [rsp+128h+var_D8], rbx
0x18001cc8e  xor     r13d, r13d
0x18001cc91  mov     edi, r13d
0x18001cc94  mov     [rsp+128h+var_D0], r13d
0x18001cc99  mov     [rsp+128h+var_E8], r14
0x18001cc9e  mov     [rsp+128h+var_DF], 100h
0x18001cca5  lea     edx, [r13+8]
0x18001cca9  lea     r8d, [r13+64h]
0x18001ccad  lea     rcx, [rsp+128h+var_C8]
0x18001ccb2  call    cs:__imp_??0CFlexArray@@QEAA@HH@Z; CFlexArray::CFlexArray(int,int)
0x18001ccb8  nop
0x18001ccb9  mov     [rsp+128h+var_68], r13b
0x18001ccc1  lea     rcx, [rsp+128h+var_60]
0x18001ccc9  call    cs:__imp_??0CCritSec@@QEAA@XZ; CCritSec::CCritSec(void)
0x18001cccf  nop
0x18001ccd0  cmp     [r14+0A8h], r13b
0x18001ccd7  jnz     loc_18001CEE8
0x18001ccdd  mov     rcx, rbx; this
0x18001cce0  call    ?WriteLock@CLock@@QEAAHK@Z; CLock::WriteLock(ulong)
0x18001cce5  test    eax, eax
0x18001cce7  setz    dil
0x18001cceb  mov     [rsp+128h+var_D0], edi
0x18001ccef  test    dil, dil
0x18001ccf2  jz      loc_18001CFD7
0x18001ccf8  cmp     cs:?g_bShuttingDown@@3_NA, r13b; bool g_bShuttingDown
0x18001ccff  jnz     loc_18001CE99
0x18001cd05  lea     rcx, [rsp+128h+var_E8]; this
0x18001cd0a  call    ?InternalBeginTransaction@CAutoTransaction@@QEAAK_N@Z; CAutoTransaction::InternalBeginTransaction(bool)
0x18001cd0f  mov     ebx, eax
0x18001cd11  test    eax, eax
0x18001cd13  jnz     loc_18001D084
0x18001cd19  lea     rcx, [rsp+128h+var_C8]
0x18001cd1e  mov     cs:byte_180058AF0, r13b
0x18001cd25  mov     rax, [r15+58h]
0x18001cd29  cmp     [rax+30h], r13d
0x18001cd2d  jl      loc_18001D170
0x18001cd33  mov     [rsp+128h+var_F8], rcx; struct CEventCollector *
0x18001cd38  mov     rax, [rsp+128h+arg_30]
0x18001cd40  mov     [rsp+128h+var_100], rax; struct IWmiDbHandle **
0x18001cd45  mov     r9d, [rsp+128h+arg_20]; unsigned int
0x18001cd4d  mov     r8, r12; void *
0x18001cd50  mov     rcx, r15; this
0x18001cd53  call    ?PutObject@CNamespaceHandle@@QEAAJAEBU_GUID@@PEAXKKPEAPEAUIWmiDbHandle@@AEAVCEventCollector@@@Z; CNamespaceHandle::PutObject(_GUID const &,void *,ulong,ulong,IWmiDbHandle * *,CEventCollector &)
0x18001cd58  mov     ebx, eax
0x18001cd5a  cmp     [r14+0A8h], r13b
0x18001cd61  jnz     loc_18001D1D2
0x18001cd67  test    eax, eax
0x18001cd69  js      loc_18001D1B2
0x18001cd6f  mov     byte ptr [rsp+128h+var_DF], r13b
0x18001cd74  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cd7b  lea     r14, WPP_GLOBAL_Control
0x18001cd82  cmp     rcx, r14
0x18001cd85  jz      short loc_18001CD91
0x18001cd87  test    byte ptr [rcx+1Ch], 1
0x18001cd8b  jnz     loc_18001CF85
0x18001cd91  cmp     [rsp+128h+var_E0], r13b
0x18001cd96  jnz     loc_18001CF45
0x18001cd9c  mov     cs:byte_180058AF0, r13b
0x18001cda3  test    edi, edi
0x18001cda5  jnz     loc_18001CF6C
0x18001cdab  cmp     cs:?g_Glob@@3VCGlobals@@A, r13d; CGlobals g_Glob
0x18001cdb2  jz      loc_18001D1C8
0x18001cdb8  mov     rcx, cs:qword_180058A78
0x18001cdbf  test    rcx, rcx
0x18001cdc2  jz      loc_18001D1C8
0x18001cdc8  mov     rax, [rcx]
0x18001cdcb  mov     rax, [rax+8]
0x18001cdcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cdd4  mov     rbx, cs:qword_180058A78
0x18001cddb  mov     [rsp+128h+arg_0], rbx
0x18001cde3  mov     rdx, rbx; struct _IWmiCoreServices *
0x18001cde6  lea     rcx, [rsp+128h+var_C8]; this
0x18001cdeb  call    ?SendEvents@CEventCollector@@QEAAJPEAU_IWmiCoreServices@@@Z; CEventCollector::SendEvents(_IWmiCoreServices *)
0x18001cdf0  nop
0x18001cdf1  test    rbx, rbx
0x18001cdf4  jz      short loc_18001CE06
0x18001cdf6  mov     rax, [rbx]
0x18001cdf9  mov     rcx, rbx
0x18001cdfc  mov     rax, [rax+10h]
0x18001ce00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce05  nop
0x18001ce06  mov     ebx, r13d
0x18001ce09  lea     rdx, [rsp+128h+var_60]
0x18001ce11  lea     rcx, [rsp+128h+arg_0]
0x18001ce19  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x18001ce1f  nop
0x18001ce20  mov     [rsp+128h+var_68], r13b
0x18001ce28  lea     rcx, [rsp+128h+var_C8]
0x18001ce2d  call    ?RemoveAll@?$CPointerArray@VCRepEvent@@V?$CUniqueManager@VCRepEvent@@@@VCFlexArray@@@@QEAAXXZ; CPointerArray<CRepEvent,CUniqueManager<CRepEvent>,CFlexArray>::RemoveAll(void)
0x18001ce32  nop
0x18001ce33  lea     rcx, [rsp+128h+arg_0]
0x18001ce3b  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x18001ce41  test    ebx, ebx
0x18001ce43  js      loc_18001D1DE
0x18001ce49  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ce50  cmp     rcx, r14
0x18001ce53  jnz     loc_18001CEFE
0x18001ce59  lea     rcx, [rsp+128h+var_60]
0x18001ce61  call    cs:__imp_??1CCritSec@@QEAA@XZ; CCritSec::~CCritSec(void)
0x18001ce67  lea     rcx, [rsp+128h+var_C8]
0x18001ce6c  call    ??1?$CPointerArray@VCRepEvent@@V?$CUniqueManager@VCRepEvent@@@@VCFlexArray@@@@QEAA@XZ; CPointerArray<CRepEvent,CUniqueManager<CRepEvent>,CFlexArray>::~CPointerArray<CRepEvent,CUniqueManager<CRepEvent>,CFlexArray>(void)
0x18001ce71  nop
0x18001ce72  cmp     byte ptr [rsp+128h+var_DF], r13b
0x18001ce77  jnz     loc_18001D1F4
0x18001ce7d  test    edi, edi
0x18001ce7f  jnz     loc_18001CF2F
0x18001ce85  mov     eax, ebx
0x18001ce87  add     rsp, 0F8h
0x18001ce8e  pop     r15
0x18001ce90  pop     r14
0x18001ce92  pop     r13
0x18001ce94  pop     r12
0x18001ce96  pop     rdi
0x18001ce97  pop     rbx
0x18001ce98  retn
0x18001ce99  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001ce9f  nop
0x18001cea0  mov     ebx, 80041033h
0x18001cea5  mov     edx, ebx
0x18001cea7  mov     rcx, rax
0x18001ceaa  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001ceb0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ceb7  lea     r14, WPP_GLOBAL_Control
0x18001cebe  cmp     rcx, r14
0x18001cec1  jnz     loc_18001D050
0x18001cec7  lea     rcx, [rsp+128h+var_60]
0x18001cecf  call    cs:__imp_??1CCritSec@@QEAA@XZ; CCritSec::~CCritSec(void)
0x18001ced5  lea     rcx, [rsp+128h+var_C8]
0x18001ceda  call    ??1?$CPointerArray@VCRepEvent@@V?$CUniqueManager@VCRepEvent@@@@VCFlexArray@@@@QEAA@XZ; CPointerArray<CRepEvent,CUniqueManager<CRepEvent>,CFlexArray>::~CPointerArray<CRepEvent,CUniqueManager<CRepEvent>,CFlexArray>(void)
0x18001cedf  nop
0x18001cee0  test    edi, edi
0x18001cee2  jnz     short loc_18001CF56
0x18001cee4  mov     eax, ebx
0x18001cee6  jmp     short loc_18001CE87
0x18001cee8  cmp     cs:?g_bShuttingDown@@3_NA, r13b; bool g_bShuttingDown
0x18001ceef  jnz     loc_18001D0F7
0x18001cef5  lea     rcx, [r14+18h]
0x18001cef9  jmp     loc_18001CD25
0x18001cefe  test    byte ptr [rcx+1Ch], 1
0x18001cf02  jz      loc_18001CE59
0x18001cf08  cmp     byte ptr [rcx+19h], 2
0x18001cf0c  jb      loc_18001CE59
0x18001cf12  mov     edx, 23h ; '#'
0x18001cf17  mov     r9d, ebx
0x18001cf1a  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18001cf21  mov     rcx, [rcx+10h]
0x18001cf25  call    WPP_SF_d
0x18001cf2a  jmp     loc_18001CE59
0x18001cf2f  lea     rcx, ?g_readWriteLock@@3VCLock@@A; this
0x18001cf36  call    ?WriteUnlock@CLock@@QEAAHXZ; CLock::WriteUnlock(void)
0x18001cf3b  mov     [rsp+128h+var_D0], r13d
0x18001cf40  jmp     loc_18001CE85
0x18001cf45  lea     rcx, byte_180058AF8; this
0x18001cf4c  call    ?CommitTransaction@CFileCache@@QEAAJXZ; CFileCache::CommitTransaction(void)
0x18001cf51  jmp     loc_18001CD9C
0x18001cf56  lea     rcx, ?g_readWriteLock@@3VCLock@@A; this
0x18001cf5d  call    ?WriteUnlock@CLock@@QEAAHXZ; CLock::WriteUnlock(void)
0x18001cf62  mov     [rsp+128h+var_D0], r13d
0x18001cf67  jmp     loc_18001CEE4
0x18001cf6c  lea     rcx, ?g_readWriteLock@@3VCLock@@A; this
0x18001cf73  call    ?WriteUnlock@CLock@@QEAAHXZ; CLock::WriteUnlock(void)
0x18001cf78  mov     edi, r13d
0x18001cf7b  mov     [rsp+128h+var_D0], r13d
0x18001cf80  jmp     loc_18001CDAB
0x18001cf85  cmp     byte ptr [rcx+19h], 5
0x18001cf89  jb      loc_18001CD91
0x18001cf8f  mov     edx, 50h ; 'P'
0x18001cf94  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18001cf9b  mov     rcx, [rcx+10h]
0x18001cf9f  call    WPP_SF_
0x18001cfa4  jmp     loc_18001CD91
0x18001cfa9  test    byte ptr [rcx+1Ch], 1
0x18001cfad  jz      loc_18001CC82
0x18001cfb3  cmp     byte ptr [rcx+19h], 5
0x18001cfb7  jb      loc_18001CC82
0x18001cfbd  mov     edx, 1Eh
0x18001cfc2  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18001cfc9  mov     rcx, [rcx+10h]
0x18001cfcd  call    WPP_SF_
0x18001cfd2  jmp     loc_18001CC82
0x18001cfd7  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001cfdd  mov     ebx, 80041001h
0x18001cfe2  mov     edx, ebx
0x18001cfe4  mov     rcx, rax
0x18001cfe7  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001cfed  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cff4  lea     r14, WPP_GLOBAL_Control
0x18001cffb  cmp     rcx, r14
0x18001cffe  jz      short loc_18001D028
0x18001d000  test    byte ptr [rcx+1Ch], 1
0x18001d004  jz      short loc_18001D028
0x18001d006  cmp     byte ptr [rcx+19h], 2
0x18001d00a  jb      short loc_18001D028
0x18001d00c  mov     edx, 1Fh
0x18001d011  mov     r9d, 80041001h
0x18001d017  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18001d01e  mov     rcx, [rcx+10h]
0x18001d022  call    WPP_SF_d
0x18001d027  nop
0x18001d028  lea     rcx, [rsp+128h+var_C8]; this
0x18001d02d  call    ??1CEventCollector@@QEAA@XZ; CEventCollector::~CEventCollector(void)
0x18001d032  nop
0x18001d033  lea     rcx, [rsp+128h+var_E8]; this
0x18001d038  call    ??1CAutoTransaction@@QEAA@XZ; CAutoTransaction::~CAutoTransaction(void)
0x18001d03d  nop
0x18001d03e  lea     rcx, [rsp+128h+var_D8]; this
0x18001d043  call    ?Unlock@CAutoWriteLock@@QEAAXXZ; CAutoWriteLock::Unlock(void)
0x18001d048  nop
0x18001d049  mov     eax, ebx
0x18001d04b  jmp     loc_18001CE87
0x18001d050  test    byte ptr [rcx+1Ch], 1
0x18001d054  jz      loc_18001CEC7
0x18001d05a  cmp     byte ptr [rcx+19h], 2
0x18001d05e  jb      loc_18001CEC7
0x18001d064  mov     edx, 20h ; ' '
0x18001d069  mov     r9d, 80041033h
0x18001d06f  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18001d076  mov     rcx, [rcx+10h]
0x18001d07a  call    WPP_SF_d
0x18001d07f  jmp     loc_18001CEC7
0x18001d084  jns     short loc_18001D097
0x18001d086  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001d08c  mov     edx, ebx
0x18001d08e  mov     rcx, rax
0x18001d091  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001d097  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d09e  lea     r14, WPP_GLOBAL_Control
0x18001d0a5  cmp     rcx, r14
0x18001d0a8  jz      short loc_18001D0CF
0x18001d0aa  test    byte ptr [rcx+1Ch], 1
0x18001d0ae  jz      short loc_18001D0CF
0x18001d0b0  cmp     byte ptr [rcx+19h], 2
0x18001d0b4  jb      short loc_18001D0CF
0x18001d0b6  mov     edx, 21h ; '!'
0x18001d0bb  mov     r9d, ebx
0x18001d0be  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18001d0c5  mov     rcx, [rcx+10h]
0x18001d0c9  call    WPP_SF_d
0x18001d0ce  nop
0x18001d0cf  lea     rcx, [rsp+128h+var_C8]; this
0x18001d0d4  call    ??1CEventCollector@@QEAA@XZ; CEventCollector::~CEventCollector(void)
0x18001d0d9  nop
0x18001d0da  lea     rcx, [rsp+128h+var_E8]; this
0x18001d0df  call    ??1CAutoTransaction@@QEAA@XZ; CAutoTransaction::~CAutoTransaction(void)
0x18001d0e4  nop
0x18001d0e5  lea     rcx, [rsp+128h+var_D8]; this
0x18001d0ea  call    ?Unlock@CAutoWriteLock@@QEAAXXZ; CAutoWriteLock::Unlock(void)
0x18001d0ef  nop
0x18001d0f0  mov     eax, ebx
0x18001d0f2  jmp     loc_18001CE87
0x18001d0f7  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001d0fd  mov     ebx, 80041033h
0x18001d102  mov     edx, ebx
0x18001d104  mov     rcx, rax
0x18001d107  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001d10d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d114  lea     r14, WPP_GLOBAL_Control
0x18001d11b  cmp     rcx, r14
0x18001d11e  jz      short loc_18001D148
0x18001d120  test    byte ptr [rcx+1Ch], 1
0x18001d124  jz      short loc_18001D148
0x18001d126  cmp     byte ptr [rcx+19h], 2
0x18001d12a  jb      short loc_18001D148
0x18001d12c  mov     edx, 22h ; '"'
0x18001d131  mov     r9d, 80041033h
0x18001d137  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18001d13e  mov     rcx, [rcx+10h]
0x18001d142  call    WPP_SF_d
0x18001d147  nop
0x18001d148  lea     rcx, [rsp+128h+var_C8]; this
0x18001d14d  call    ??1CEventCollector@@QEAA@XZ; CEventCollector::~CEventCollector(void)
0x18001d152  nop
0x18001d153  lea     rcx, [rsp+128h+var_E8]; this
0x18001d158  call    ??1CAutoTransaction@@QEAA@XZ; CAutoTransaction::~CAutoTransaction(void)
0x18001d15d  nop
0x18001d15e  lea     rcx, [rsp+128h+var_D8]; this
0x18001d163  call    ?Unlock@CAutoWriteLock@@QEAAXXZ; CAutoWriteLock::Unlock(void)
0x18001d168  nop
0x18001d169  mov     eax, ebx
0x18001d16b  jmp     loc_18001CE87
0x18001d170  cmp     [r14+0A8h], r13b
0x18001d177  jnz     short loc_18001D183
0x18001d179  lea     rcx, [rsp+128h+var_E8]; this
0x18001d17e  call    ?InternalAbortTransaction@CAutoTransaction@@QEAAKXZ; CAutoTransaction::InternalAbortTransaction(void)
0x18001d183  mov     rax, [r15+58h]
  ... truncated ...
```
