# CSession::DeleteObjectByPath(IWmiDbHandle *,ushort const *,ulong)

- ea: `0x18001c070`
- end: `0x18001c674`
- name: `?DeleteObjectByPath@CSession@@UEAAJPEAUIWmiDbHandle@@PEBGK@Z`
- size: `1540`
- prototype: `__int64 __fastcall(CSession *__hidden this, struct IWmiDbHandle *, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800012b8`
- `0x1800013c8`
- `0x18001b5c0`
- `0x18001c038`
- `0x18001c070`
- `0x18001c67c`
- `0x18001d234`
- `0x18001d5f0`
- `0x18001d7bc`
- `0x18001e1f0`
- `0x18001e270`
- `0x180026248`
- `0x180027e8c`
- `0x1800283e8`
- `0x1800356f0`
- `0x180048010`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001c394`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001c394`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001c5f1`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001c5f1`
- `wbemcomn!??0CCritSec@@QEAA@XZ` at `0x18001c110`
- `wbemcomn!??0CCritSec@@QEAA@XZ` at `0x18001c110`
- `wbemcomn!??1CCritSec@@QEAA@XZ` at `0x18001c600`
- `wbemcomn!??1CCritSec@@QEAA@XZ` at `0x18001c600`
- `wbemcomn!??0CFlexArray@@QEAA@HH@Z` at `0x18001c0fa`
- `wbemcomn!??0CFlexArray@@QEAA@HH@Z` at `0x18001c0fa`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18001c4dc`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18001c4dc`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18001c4fe`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18001c4fe`
- `wbemcomn!GetMemLogObject` at `0x18001c131`
- `wbemcomn!GetMemLogObject` at `0x18001c1ab`
- `wbemcomn!GetMemLogObject` at `0x18001c22f`
- `wbemcomn!GetMemLogObject` at `0x18001c2af`
- `wbemcomn!GetMemLogObject` at `0x18001c3bc`
- `wbemcomn!GetMemLogObject` at `0x18001c5a5`
- `wbemcomn!GetMemLogObject` at `0x18001c131`
- `wbemcomn!GetMemLogObject` at `0x18001c1ab`
- `wbemcomn!GetMemLogObject` at `0x18001c22f`
- `wbemcomn!GetMemLogObject` at `0x18001c2af`
- `wbemcomn!GetMemLogObject` at `0x18001c3bc`
- `wbemcomn!GetMemLogObject` at `0x18001c5a5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001c141`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001c1bb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001c23a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001c2bf`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001c3ca`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001c5b0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001c141`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001c1bb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001c23a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001c2bf`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001c3ca`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001c5b0`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CSession::DeleteObjectByPath(
        CSession *this,
        struct IWmiDbHandle *a2,
        const unsigned __int16 *a3,
        unsigned int a4)
{
  const unsigned __int16 *v4; // r15
  int v7; // r14d
  bool v8; // dl
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v11; // rax
  int v12; // eax
  unsigned int v13; // ebx
  CMemoryLog *v14; // rax
  struct CEventCollector *v15; // r13
  CMemoryLog *v16; // rax
  unsigned int v17; // ebx
  __int64 v18; // rax
  unsigned __int64 v19; // rbx
  unsigned __int16 *v20; // rax
  unsigned __int16 *v21; // r12
  CMemoryLog *v22; // rax
  __int64 v23; // rcx
  unsigned __int16 v24; // dx
  unsigned __int16 *v25; // rcx
  int v26; // eax
  CSession *v27; // rcx
  int v28; // ebx
  CLock *v29; // rsi
  struct _IWmiCoreServices *v30; // rbx
  CMemoryLog *v31; // rax
  CLock *v32; // [rsp+20h] [rbp-E8h] BYREF
  int v33; // [rsp+28h] [rbp-E0h]
  CSession *v34; // [rsp+30h] [rbp-D8h] BYREF
  bool v35; // [rsp+38h] [rbp-D0h]
  __int16 v36; // [rsp+39h] [rbp-CFh]
  unsigned __int16 *v37; // [rsp+40h] [rbp-C8h]
  _BYTE v38[96]; // [rsp+50h] [rbp-B8h] BYREF
  char v39; // [rsp+B0h] [rbp-58h]
  struct _RTL_CRITICAL_SECTION v40[2]; // [rsp+B8h] [rbp-50h] BYREF
  struct _IWmiCoreServices *v41; // [rsp+110h] [rbp+8h] BYREF
  CNamespaceHandle *v42; // [rsp+118h] [rbp+10h]
  unsigned int v43; // [rsp+128h] [rbp+20h]

  v43 = a4;
  v42 = a2;
  v4 = a3;
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, a3);
  }
  v32 = (CLock *)&g_readWriteLock;
  v7 = 0;
  v33 = 0;
  v34 = this;
  v36 = 0;
  CFlexArray::CFlexArray((CFlexArray *)v38, 8, 100);
  v39 = 0;
  CCritSec::CCritSec((CCritSec *)v40);
  if ( !*((_BYTE *)this + 168) )
  {
    if ( !CAutoWriteLock::Lock((CAutoWriteLock *)&v32) )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, -2147217407);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749889LL);
      }
      CEventCollector::~CEventCollector((CEventCollector *)v38);
      CAutoTransaction::~CAutoTransaction((CAutoTransaction *)&v34);
      CAutoWriteLock::Unlock((CAutoWriteLock *)&v32);
      return 2147749889LL;
    }
    if ( g_bShuttingDown )
    {
      v11 = GetMemLogObject();
      CMemoryLog::Write(v11, -2147217357);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749939LL);
      }
      CEventCollector::~CEventCollector((CEventCollector *)v38);
      CAutoTransaction::~CAutoTransaction((CAutoTransaction *)&v34);
      CAutoWriteLock::Unlock((CAutoWriteLock *)&v32);
      return 2147749939LL;
    }
    v12 = CAutoTransaction::InternalBeginTransaction((CAutoTransaction *)&v34, v8);
    v13 = v12;
    if ( v12 )
    {
      if ( v12 < 0 )
      {
        v14 = GetMemLogObject();
        CMemoryLog::Write(v14, v13);
      }
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, v13);
      }
      CEventCollector::~CEventCollector((CEventCollector *)v38);
      CAutoTransaction::~CAutoTransaction((CAutoTransaction *)&v34);
      CAutoWriteLock::Unlock((CAutoWriteLock *)&v32);
      return v13;
    }
    v15 = (struct CEventCollector *)v38;
    v7 = v33;
LABEL_32:
    if ( *(int *)(*((_QWORD *)a2 + 11) + 48LL) < 0 )
    {
      if ( !*((_BYTE *)this + 168) )
        CAutoTransaction::InternalAbortTransaction((CAutoTransaction *)&v34);
      v17 = *(_DWORD *)(*((_QWORD *)a2 + 11) + 48LL);
      CEventCollector::~CEventCollector((CEventCollector *)v38);
      CAutoTransaction::~CAutoTransaction((CAutoTransaction *)&v34);
      CAutoWriteLock::Unlock((CAutoWriteLock *)&v32);
      return v17;
    }
    v18 = -1;
    do
      ++v18;
    while ( v4[v18] );
    v19 = (unsigned int)(v18 + 1);
    v20 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v19, 2u));
    v21 = v20;
    if ( !v20 )
    {
      if ( !*((_BYTE *)this + 168) )
        CAutoTransaction::InternalAbortTransaction((CAutoTransaction *)&v34);
      v22 = GetMemLogObject();
      CMemoryLog::Write(v22, -2147217402);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749894LL);
      }
      CEventCollector::~CEventCollector((CEventCollector *)v38);
      CAutoTransaction::~CAutoTransaction((CAutoTransaction *)&v34);
      CAutoWriteLock::Unlock((CAutoWriteLock *)&v32);
      return 2147749894LL;
    }
    if ( v19 )
    {
      if ( v19 <= 0x7FFFFFFF )
      {
        v23 = 2147483646;
        do
        {
          if ( !v23 )
            break;
          v24 = *v4;
          if ( !*v4 )
            break;
          ++v4;
          *v20++ = v24;
          --v23;
          --v19;
        }
        while ( v19 );
        v25 = v20 - 1;
        if ( v19 )
          v25 = v20;
        *v25 = 0;
      }
      else
      {
        *v20 = 0;
      }
    }
    v37 = v21;
    v26 = CNamespaceHandle::DeleteObjectByPath(v42, v43, v21, v15);
    v28 = v26;
    if ( *((_BYTE *)this + 168) )
    {
      v29 = v32;
      goto LABEL_71;
    }
    if ( v26 >= 0 )
    {
      LOBYTE(v36) = 0;
      v28 = CSession::InternalCommitTransaction(v27, v35);
      if ( !v28 )
      {
        v29 = v32;
        if ( v7 )
        {
          CLock::WriteUnlock(v32);
          v7 = 0;
          v33 = 0;
        }
        if ( g_Glob && qword_180058A78 )
        {
          (*(void (__fastcall **)(struct _IWmiCoreServices *))(*(_QWORD *)qword_180058A78 + 8LL))(qword_180058A78);
          v30 = qword_180058A78;
          v41 = qword_180058A78;
          CEventCollector::SendEvents((CEventCollector *)v38, qword_180058A78);
          if ( v30 )
            (*(void (__fastcall **)(struct _IWmiCoreServices *))(*(_QWORD *)v30 + 16LL))(v30);
          v28 = 0;
        }
        else
        {
          v28 = -2147217388;
        }
        goto LABEL_60;
      }
    }
    else
    {
      CAutoTransaction::InternalAbortTransaction((CAutoTransaction *)&v34);
    }
    v29 = v32;
LABEL_60:
    CInCritSec::CInCritSec((CInCritSec *)&v41, v40);
    v39 = 0;
    CPointerArray<CRepEvent,CUniqueManager<CRepEvent>,CFlexArray>::RemoveAll(v38);
    CInCritSec::~CInCritSec((CInCritSec *)&v41);
LABEL_71:
    if ( v28 < 0 )
    {
      v31 = GetMemLogObject();
      CMemoryLog::Write(v31, v28);
    }
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        52,
        WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
        (unsigned int)v28);
    }
    CWin32DefaultArena::WbemMemFree(v21);
    CCritSec::~CCritSec((CCritSec *)v40);
    CPointerArray<CRepEvent,CUniqueManager<CRepEvent>,CFlexArray>::~CPointerArray<CRepEvent,CUniqueManager<CRepEvent>,CFlexArray>(v38);
    if ( (_BYTE)v36 )
      CAutoTransaction::InternalAbortTransaction((CAutoTransaction *)&v34);
    if ( v7 )
    {
      CLock::WriteUnlock(v29);
      v33 = 0;
    }
    return (unsigned int)v28;
  }
  if ( !g_bShuttingDown )
  {
    v15 = (CSession *)((char *)this + 24);
    goto LABEL_32;
  }
  v16 = GetMemLogObject();
  CMemoryLog::Write(v16, -2147217357);
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749939LL);
  }
  CEventCollector::~CEventCollector((CEventCollector *)v38);
  CAutoTransaction::~CAutoTransaction((CAutoTransaction *)&v34);
  CAutoWriteLock::Unlock((CAutoWriteLock *)&v32);
  return 2147749939LL;
}

```

## disassembly

```asm
0x18001c070  mov     [rsp+arg_10], rbx
0x18001c075  mov     [rsp+arg_18], r9d
0x18001c07a  mov     [rsp+arg_8], rdx
0x18001c07f  push    rsi
0x18001c080  push    r12
0x18001c082  push    r13
0x18001c084  push    r14
0x18001c086  push    r15
0x18001c088  sub     rsp, 0E0h
0x18001c08f  mov     r15, r8
0x18001c092  mov     r12, rdx
0x18001c095  mov     rsi, rcx
0x18001c098  lea     r13, WPP_GLOBAL_Control
0x18001c09f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c0a6  cmp     rcx, r13
0x18001c0a9  jz      short loc_18001C0CF
0x18001c0ab  test    byte ptr [rcx+1Ch], 1
0x18001c0af  jz      short loc_18001C0CF
0x18001c0b1  cmp     byte ptr [rcx+19h], 5
0x18001c0b5  jb      short loc_18001C0CF
0x18001c0b7  mov     edx, 2Eh ; '.'
0x18001c0bc  mov     r9, r8
0x18001c0bf  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18001c0c6  mov     rcx, [rcx+10h]
0x18001c0ca  call    WPP_SF_S
0x18001c0cf  lea     rax, ?g_readWriteLock@@3VCLock@@A; CLock g_readWriteLock
0x18001c0d6  mov     [rsp+108h+var_E8], rax
0x18001c0db  xor     ebx, ebx
0x18001c0dd  mov     r14d, ebx
0x18001c0e0  mov     [rsp+108h+var_E0], ebx
0x18001c0e4  mov     [rsp+108h+var_D8], rsi
0x18001c0e9  mov     [rsp+108h+var_CF], bx
0x18001c0ee  lea     edx, [rbx+8]
0x18001c0f1  lea     r8d, [rbx+64h]
0x18001c0f5  lea     rcx, [rsp+108h+var_B8]
0x18001c0fa  call    cs:__imp_??0CFlexArray@@QEAA@HH@Z; CFlexArray::CFlexArray(int,int)
0x18001c100  nop
0x18001c101  mov     [rsp+108h+var_58], bl
0x18001c108  lea     rcx, [rsp+108h+var_50]
0x18001c110  call    cs:__imp_??0CCritSec@@QEAA@XZ; CCritSec::CCritSec(void)
0x18001c116  nop
0x18001c117  cmp     [rsi+0A8h], bl
0x18001c11d  jnz     loc_18001C2A7
0x18001c123  lea     rcx, [rsp+108h+var_E8]; this
0x18001c128  call    ?Lock@CAutoWriteLock@@QEAA_NXZ; CAutoWriteLock::Lock(void)
0x18001c12d  test    al, al
0x18001c12f  jnz     short loc_18001C1A3
0x18001c131  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001c137  mov     ebx, 80041001h
0x18001c13c  mov     edx, ebx
0x18001c13e  mov     rcx, rax
0x18001c141  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001c147  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c14e  cmp     rcx, r13
0x18001c151  jz      short loc_18001C17B
0x18001c153  test    byte ptr [rcx+1Ch], 1
0x18001c157  jz      short loc_18001C17B
0x18001c159  cmp     byte ptr [rcx+19h], 2
0x18001c15d  jb      short loc_18001C17B
0x18001c15f  mov     edx, 2Fh ; '/'
0x18001c164  mov     r9d, 80041001h
0x18001c16a  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18001c171  mov     rcx, [rcx+10h]
0x18001c175  call    WPP_SF_d
0x18001c17a  nop
0x18001c17b  lea     rcx, [rsp+108h+var_B8]; this
0x18001c180  call    ??1CEventCollector@@QEAA@XZ; CEventCollector::~CEventCollector(void)
0x18001c185  nop
0x18001c186  lea     rcx, [rsp+108h+var_D8]; this
0x18001c18b  call    ??1CAutoTransaction@@QEAA@XZ; CAutoTransaction::~CAutoTransaction(void)
0x18001c190  nop
0x18001c191  lea     rcx, [rsp+108h+var_E8]; this
0x18001c196  call    ?Unlock@CAutoWriteLock@@QEAAXXZ; CAutoWriteLock::Unlock(void)
0x18001c19b  nop
0x18001c19c  mov     eax, ebx
0x18001c19e  jmp     loc_18001C65B
0x18001c1a3  cmp     cs:?g_bShuttingDown@@3_NA, bl; bool g_bShuttingDown
0x18001c1a9  jz      short loc_18001C21D
0x18001c1ab  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001c1b1  mov     ebx, 80041033h
0x18001c1b6  mov     edx, ebx
0x18001c1b8  mov     rcx, rax
0x18001c1bb  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001c1c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c1c8  cmp     rcx, r13
0x18001c1cb  jz      short loc_18001C1F5
0x18001c1cd  test    byte ptr [rcx+1Ch], 1
0x18001c1d1  jz      short loc_18001C1F5
0x18001c1d3  cmp     byte ptr [rcx+19h], 2
0x18001c1d7  jb      short loc_18001C1F5
0x18001c1d9  mov     edx, 30h ; '0'
0x18001c1de  mov     r9d, 80041033h
0x18001c1e4  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18001c1eb  mov     rcx, [rcx+10h]
0x18001c1ef  call    WPP_SF_d
0x18001c1f4  nop
0x18001c1f5  lea     rcx, [rsp+108h+var_B8]; this
0x18001c1fa  call    ??1CEventCollector@@QEAA@XZ; CEventCollector::~CEventCollector(void)
0x18001c1ff  nop
0x18001c200  lea     rcx, [rsp+108h+var_D8]; this
0x18001c205  call    ??1CAutoTransaction@@QEAA@XZ; CAutoTransaction::~CAutoTransaction(void)
0x18001c20a  nop
0x18001c20b  lea     rcx, [rsp+108h+var_E8]; this
0x18001c210  call    ?Unlock@CAutoWriteLock@@QEAAXXZ; CAutoWriteLock::Unlock(void)
0x18001c215  nop
0x18001c216  mov     eax, ebx
0x18001c218  jmp     loc_18001C65B
0x18001c21d  lea     rcx, [rsp+108h+var_D8]; this
0x18001c222  call    ?InternalBeginTransaction@CAutoTransaction@@QEAAK_N@Z; CAutoTransaction::InternalBeginTransaction(bool)
0x18001c227  mov     ebx, eax
0x18001c229  test    eax, eax
0x18001c22b  jz      short loc_18001C299
0x18001c22d  jns     short loc_18001C240
0x18001c22f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001c235  mov     edx, ebx
0x18001c237  mov     rcx, rax
0x18001c23a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001c240  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c247  cmp     rcx, r13
0x18001c24a  jz      short loc_18001C271
0x18001c24c  test    byte ptr [rcx+1Ch], 1
0x18001c250  jz      short loc_18001C271
0x18001c252  cmp     byte ptr [rcx+19h], 2
0x18001c256  jb      short loc_18001C271
0x18001c258  mov     edx, 31h ; '1'
0x18001c25d  mov     r9d, ebx
0x18001c260  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18001c267  mov     rcx, [rcx+10h]
0x18001c26b  call    WPP_SF_d
0x18001c270  nop
0x18001c271  lea     rcx, [rsp+108h+var_B8]; this
0x18001c276  call    ??1CEventCollector@@QEAA@XZ; CEventCollector::~CEventCollector(void)
0x18001c27b  nop
0x18001c27c  lea     rcx, [rsp+108h+var_D8]; this
0x18001c281  call    ??1CAutoTransaction@@QEAA@XZ; CAutoTransaction::~CAutoTransaction(void)
0x18001c286  nop
0x18001c287  lea     rcx, [rsp+108h+var_E8]; this
0x18001c28c  call    ?Unlock@CAutoWriteLock@@QEAAXXZ; CAutoWriteLock::Unlock(void)
0x18001c291  nop
0x18001c292  mov     eax, ebx
0x18001c294  jmp     loc_18001C65B
0x18001c299  lea     r13, [rsp+108h+var_B8]
0x18001c29e  mov     r14d, [rsp+108h+var_E0]
0x18001c2a3  xor     ebx, ebx
0x18001c2a5  jmp     short loc_18001C325
0x18001c2a7  cmp     cs:?g_bShuttingDown@@3_NA, bl; bool g_bShuttingDown
0x18001c2ad  jz      short loc_18001C321
0x18001c2af  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001c2b5  mov     ebx, 80041033h
0x18001c2ba  mov     edx, ebx
0x18001c2bc  mov     rcx, rax
0x18001c2bf  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001c2c5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c2cc  cmp     rcx, r13
0x18001c2cf  jz      short loc_18001C2F9
0x18001c2d1  test    byte ptr [rcx+1Ch], 1
0x18001c2d5  jz      short loc_18001C2F9
0x18001c2d7  cmp     byte ptr [rcx+19h], 2
0x18001c2db  jb      short loc_18001C2F9
0x18001c2dd  mov     edx, 32h ; '2'
0x18001c2e2  mov     r9d, 80041033h
0x18001c2e8  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18001c2ef  mov     rcx, [rcx+10h]
0x18001c2f3  call    WPP_SF_d
0x18001c2f8  nop
0x18001c2f9  lea     rcx, [rsp+108h+var_B8]; this
0x18001c2fe  call    ??1CEventCollector@@QEAA@XZ; CEventCollector::~CEventCollector(void)
0x18001c303  nop
0x18001c304  lea     rcx, [rsp+108h+var_D8]; this
0x18001c309  call    ??1CAutoTransaction@@QEAA@XZ; CAutoTransaction::~CAutoTransaction(void)
0x18001c30e  nop
0x18001c30f  lea     rcx, [rsp+108h+var_E8]; this
0x18001c314  call    ?Unlock@CAutoWriteLock@@QEAAXXZ; CAutoWriteLock::Unlock(void)
0x18001c319  nop
0x18001c31a  mov     eax, ebx
0x18001c31c  jmp     loc_18001C65B
0x18001c321  lea     r13, [rsi+18h]
0x18001c325  mov     rax, [r12+58h]
0x18001c32a  cmp     [rax+30h], ebx
0x18001c32d  jge     short loc_18001C371
0x18001c32f  cmp     [rsi+0A8h], bl
0x18001c335  jnz     short loc_18001C341
0x18001c337  lea     rcx, [rsp+108h+var_D8]; this
0x18001c33c  call    ?InternalAbortTransaction@CAutoTransaction@@QEAAKXZ; CAutoTransaction::InternalAbortTransaction(void)
0x18001c341  mov     rax, [r12+58h]
0x18001c346  mov     ebx, [rax+30h]
0x18001c349  lea     rcx, [rsp+108h+var_B8]; this
0x18001c34e  call    ??1CEventCollector@@QEAA@XZ; CEventCollector::~CEventCollector(void)
0x18001c353  nop
0x18001c354  lea     rcx, [rsp+108h+var_D8]; this
0x18001c359  call    ??1CAutoTransaction@@QEAA@XZ; CAutoTransaction::~CAutoTransaction(void)
0x18001c35e  nop
0x18001c35f  lea     rcx, [rsp+108h+var_E8]; this
0x18001c364  call    ?Unlock@CAutoWriteLock@@QEAAXXZ; CAutoWriteLock::Unlock(void)
0x18001c369  nop
0x18001c36a  mov     eax, ebx
0x18001c36c  jmp     loc_18001C65B
0x18001c371  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001c375  mov     rax, rcx
0x18001c378  inc     rax
0x18001c37b  cmp     [r15+rax*2], bx
0x18001c380  jnz     short loc_18001C378
0x18001c382  lea     ebx, [rax+1]
0x18001c385  mov     eax, 2
0x18001c38a  mul     rbx
0x18001c38d  cmovb   rax, rcx
0x18001c391  mov     rcx, rax
0x18001c394  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18001c39a  mov     r12, rax
0x18001c39d  xor     r8d, r8d
0x18001c3a0  test    rax, rax
0x18001c3a3  jnz     loc_18001C436
0x18001c3a9  cmp     [rsi+0A8h], r8b
0x18001c3b0  jnz     short loc_18001C3BC
0x18001c3b2  lea     rcx, [rsp+108h+var_D8]; this
0x18001c3b7  call    ?InternalAbortTransaction@CAutoTransaction@@QEAAKXZ; CAutoTransaction::InternalAbortTransaction(void)
0x18001c3bc  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001c3c2  mov     edx, 80041006h
0x18001c3c7  mov     rcx, rax
0x18001c3ca  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001c3d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c3d7  lea     rax, WPP_GLOBAL_Control
0x18001c3de  cmp     rcx, rax
0x18001c3e1  jz      short loc_18001C40B
0x18001c3e3  test    byte ptr [rcx+1Ch], 1
0x18001c3e7  jz      short loc_18001C40B
0x18001c3e9  cmp     byte ptr [rcx+19h], 2
0x18001c3ed  jb      short loc_18001C40B
0x18001c3ef  mov     edx, 33h ; '3'
0x18001c3f4  mov     r9d, 80041006h
0x18001c3fa  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18001c401  mov     rcx, [rcx+10h]
0x18001c405  call    WPP_SF_d
0x18001c40a  nop
0x18001c40b  lea     rcx, [rsp+108h+var_B8]; this
0x18001c410  call    ??1CEventCollector@@QEAA@XZ; CEventCollector::~CEventCollector(void)
0x18001c415  nop
0x18001c416  lea     rcx, [rsp+108h+var_D8]; this
0x18001c41b  call    ??1CAutoTransaction@@QEAA@XZ; CAutoTransaction::~CAutoTransaction(void)
0x18001c420  nop
0x18001c421  lea     rcx, [rsp+108h+var_E8]; this
0x18001c426  call    ?Unlock@CAutoWriteLock@@QEAAXXZ; CAutoWriteLock::Unlock(void)
0x18001c42b  nop
0x18001c42c  mov     eax, 80041006h
0x18001c431  jmp     loc_18001C65B
0x18001c436  test    rbx, rbx
0x18001c439  jz      short loc_18001C488
0x18001c43b  cmp     rbx, 7FFFFFFFh
0x18001c442  jbe     short loc_18001C44D
0x18001c444  xor     r15d, r15d
0x18001c447  mov     [rax], r15w
0x18001c44b  jmp     short loc_18001C48B
0x18001c44d  mov     ecx, 7FFFFFFEh
0x18001c452  test    rcx, rcx
0x18001c455  jz      short loc_18001C474
0x18001c457  movzx   edx, word ptr [r15]
0x18001c45b  test    dx, dx
0x18001c45e  jz      short loc_18001C474
0x18001c460  add     r15, 2
0x18001c464  mov     [rax], dx
0x18001c467  add     rax, 2
0x18001c46b  dec     rcx
0x18001c46e  sub     rbx, 1
0x18001c472  jnz     short loc_18001C452
0x18001c474  lea     rcx, [rax-2]
0x18001c478  xor     r15d, r15d
0x18001c47b  test    rbx, rbx
0x18001c47e  cmovnz  rcx, rax
0x18001c482  mov     [rcx], r15w
0x18001c486  jmp     short loc_18001C48B
0x18001c488  xor     r15d, r15d
0x18001c48b  mov     [rsp+108h+var_C8], r12
0x18001c490  mov     r9, r13; struct CEventCollector *
0x18001c493  mov     r8, r12; unsigned __int16 *
0x18001c496  mov     edx, [rsp+108h+arg_18]; unsigned int
0x18001c49d  mov     rcx, [rsp+108h+arg_8]; this
0x18001c4a5  call    ?DeleteObjectByPath@CNamespaceHandle@@QEAAJKPEBGAEAVCEventCollector@@@Z; CNamespaceHandle::DeleteObjectByPath(ulong,ushort const *,CEventCollector &)
0x18001c4aa  mov     ebx, eax
0x18001c4ac  cmp     [rsi+0A8h], r15b
0x18001c4b3  jnz     loc_18001C59C
0x18001c4b9  test    eax, eax
0x18001c4bb  jns     short loc_18001C509
0x18001c4bd  lea     rcx, [rsp+108h+var_D8]; this
0x18001c4c2  call    ?InternalAbortTransaction@CAutoTransaction@@QEAAKXZ; CAutoTransaction::InternalAbortTransaction(void)
0x18001c4c7  mov     rsi, [rsp+108h+var_E8]
0x18001c4cc  lea     rdx, [rsp+108h+var_50]
0x18001c4d4  lea     rcx, [rsp+108h+arg_0]
0x18001c4dc  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x18001c4e2  nop
0x18001c4e3  mov     [rsp+108h+var_58], r15b
0x18001c4eb  lea     rcx, [rsp+108h+var_B8]
0x18001c4f0  call    ?RemoveAll@?$CPointerArray@VCRepEvent@@V?$CUniqueManager@VCRepEvent@@@@VCFlexArray@@@@QEAAXXZ; CPointerArray<CRepEvent,CUniqueManager<CRepEvent>,CFlexArray>::RemoveAll(void)
0x18001c4f5  nop
0x18001c4f6  lea     rcx, [rsp+108h+arg_0]
0x18001c4fe  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x18001c504  jmp     loc_18001C5A1
0x18001c509  mov     byte ptr [rsp+108h+var_CF], r15b
0x18001c50e  mov     dl, [rsp+108h+var_D0]; bool
0x18001c512  call    ?InternalCommitTransaction@CSession@@IEAAJ_N@Z; CSession::InternalCommitTransaction(bool)
0x18001c517  mov     ebx, eax
  ... truncated ...
```
