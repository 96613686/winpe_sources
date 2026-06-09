# CSession::DeleteObject(IWmiDbHandle *,ulong,_GUID const &,void *)

- ea: `0x180034240`
- end: `0x1800345ba`
- name: `?DeleteObject@CSession@@UEAAJPEAUIWmiDbHandle@@KAEBU_GUID@@PEAX@Z`
- size: `890`
- prototype: `__int64 __fastcall(CSession *this, struct IWmiDbHandle *, __int64, const struct _GUID *)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x18001c038`
- `0x18001d7bc`
- `0x180026248`
- `0x180027580`
- `0x1800276bc`
- `0x180027e8c`
- `0x1800283e8`
- `0x180034240`
- `0x1800356f0`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1800342ce`
- `wbemcomn!GetMemLogObject` at `0x180034349`
- `wbemcomn!GetMemLogObject` at `0x1800343d1`
- `wbemcomn!GetMemLogObject` at `0x180034444`
- `wbemcomn!GetMemLogObject` at `0x18003451b`
- `wbemcomn!GetMemLogObject` at `0x1800342ce`
- `wbemcomn!GetMemLogObject` at `0x180034349`
- `wbemcomn!GetMemLogObject` at `0x1800343d1`
- `wbemcomn!GetMemLogObject` at `0x180034444`
- `wbemcomn!GetMemLogObject` at `0x18003451b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800342de`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180034359`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800343dc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180034454`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003452b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800342de`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180034359`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800343dc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180034454`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003452b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSession::DeleteObject(CSession *this, struct IWmiDbHandle *a2, __int64 a3, const struct _GUID *a4)
{
  bool v6; // dl
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v9; // rax
  int v10; // eax
  unsigned int v11; // ebx
  CMemoryLog *v12; // rax
  CMemoryLog *v13; // rax
  char v14; // cl
  unsigned int v15; // ebx
  CMemoryLog *v16; // rax
  CSession *v17; // [rsp+20h] [rbp-D8h] BYREF
  __int16 v18; // [rsp+29h] [rbp-CFh]
  __int128 *v19; // [rsp+30h] [rbp-C8h] BYREF
  int v20; // [rsp+38h] [rbp-C0h]
  _BYTE v21[184]; // [rsp+40h] [rbp-B8h] BYREF

  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids);
  }
  v19 = &g_readWriteLock;
  v20 = 0;
  v17 = this;
  v18 = 0;
  CEventCollector::CEventCollector((CEventCollector *)v21);
  if ( !*((_BYTE *)this + 168) )
  {
    if ( !CAutoWriteLock::Lock((CAutoWriteLock *)&v19) )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, -2147217407);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749889LL);
      }
      CEventCollector::~CEventCollector((CEventCollector *)v21);
      CAutoTransaction::~CAutoTransaction((CAutoTransaction *)&v17);
      CAutoWriteLock::Unlock((CAutoWriteLock *)&v19);
      return 2147749889LL;
    }
    if ( g_bShuttingDown )
    {
      v9 = GetMemLogObject();
      CMemoryLog::Write(v9, -2147217357);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749939LL);
      }
      CEventCollector::~CEventCollector((CEventCollector *)v21);
      CAutoTransaction::~CAutoTransaction((CAutoTransaction *)&v17);
      CAutoWriteLock::Unlock((CAutoWriteLock *)&v19);
      return 2147749939LL;
    }
    v10 = CAutoTransaction::InternalBeginTransaction((CAutoTransaction *)&v17, v6);
    v11 = v10;
    if ( v10 )
    {
      if ( v10 < 0 )
      {
        v12 = GetMemLogObject();
        CMemoryLog::Write(v12, v11);
      }
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, v11);
      }
      CEventCollector::~CEventCollector((CEventCollector *)v21);
      CAutoTransaction::~CAutoTransaction((CAutoTransaction *)&v17);
      CAutoWriteLock::Unlock((CAutoWriteLock *)&v19);
      return v11;
    }
    goto LABEL_32;
  }
  if ( !g_bShuttingDown )
  {
LABEL_32:
    v14 = *((_BYTE *)this + 168);
    if ( *(int *)(*((_QWORD *)a2 + 11) + 48LL) >= 0 )
    {
      if ( !v14 )
      {
        CAutoTransaction::InternalAbortTransaction((CAutoTransaction *)&v17);
        CEventCollector::DeleteAllEvents((CEventCollector *)v21);
      }
      v16 = GetMemLogObject();
      CMemoryLog::Write(v16, -2147467263);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147500033LL);
      }
      CEventCollector::~CEventCollector((CEventCollector *)v21);
      CAutoTransaction::~CAutoTransaction((CAutoTransaction *)&v17);
      CAutoWriteLock::Unlock((CAutoWriteLock *)&v19);
      return 2147500033LL;
    }
    else
    {
      if ( !v14 )
        CAutoTransaction::InternalAbortTransaction((CAutoTransaction *)&v17);
      v15 = *(_DWORD *)(*((_QWORD *)a2 + 11) + 48LL);
      CEventCollector::~CEventCollector((CEventCollector *)v21);
      CAutoTransaction::~CAutoTransaction((CAutoTransaction *)&v17);
      CAutoWriteLock::Unlock((CAutoWriteLock *)&v19);
      return v15;
    }
  }
  v13 = GetMemLogObject();
  CMemoryLog::Write(v13, -2147217357);
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749939LL);
  }
  CEventCollector::~CEventCollector((CEventCollector *)v21);
  CAutoTransaction::~CAutoTransaction((CAutoTransaction *)&v17);
  CAutoWriteLock::Unlock((CAutoWriteLock *)&v19);
  return 2147749939LL;
}

```

## disassembly

```asm
0x180034240  push    rbx
0x180034242  push    rsi
0x180034243  push    r12
0x180034245  push    r14
0x180034247  sub     rsp, 0D8h
0x18003424e  mov     r14, rdx
0x180034251  mov     rsi, rcx
0x180034254  lea     r12, WPP_GLOBAL_Control
0x18003425b  mov     rcx, cs:WPP_GLOBAL_Control
0x180034262  cmp     rcx, r12
0x180034265  jz      short loc_180034288
0x180034267  test    byte ptr [rcx+1Ch], 1
0x18003426b  jz      short loc_180034288
0x18003426d  cmp     byte ptr [rcx+19h], 5
0x180034271  jb      short loc_180034288
0x180034273  mov     edx, 26h ; '&'
0x180034278  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18003427f  mov     rcx, [rcx+10h]
0x180034283  call    WPP_SF_
0x180034288  lea     rax, ?g_readWriteLock@@3VCLock@@A; CLock g_readWriteLock
0x18003428f  mov     [rsp+0F8h+var_C8], rax
0x180034294  mov     [rsp+0F8h+var_C0], 0
0x18003429c  mov     [rsp+0F8h+var_D8], rsi
0x1800342a1  mov     [rsp+0F8h+var_CF], 0
0x1800342a8  lea     rcx, [rsp+0F8h+var_B8]; this
0x1800342ad  call    ??0CEventCollector@@QEAA@XZ; CEventCollector::CEventCollector(void)
0x1800342b2  nop
0x1800342b3  cmp     byte ptr [rsi+0A8h], 0
0x1800342ba  jnz     loc_18003443B
0x1800342c0  lea     rcx, [rsp+0F8h+var_C8]; this
0x1800342c5  call    ?Lock@CAutoWriteLock@@QEAA_NXZ; CAutoWriteLock::Lock(void)
0x1800342ca  test    al, al
0x1800342cc  jnz     short loc_180034340
0x1800342ce  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800342d4  mov     ebx, 80041001h
0x1800342d9  mov     edx, ebx
0x1800342db  mov     rcx, rax
0x1800342de  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800342e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800342eb  cmp     rcx, r12
0x1800342ee  jz      short loc_180034318
0x1800342f0  test    byte ptr [rcx+1Ch], 1
0x1800342f4  jz      short loc_180034318
0x1800342f6  cmp     byte ptr [rcx+19h], 2
0x1800342fa  jb      short loc_180034318
0x1800342fc  mov     edx, 27h ; '''
0x180034301  mov     r9d, 80041001h
0x180034307  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18003430e  mov     rcx, [rcx+10h]
0x180034312  call    WPP_SF_d
0x180034317  nop
0x180034318  lea     rcx, [rsp+0F8h+var_B8]; this
0x18003431d  call    ??1CEventCollector@@QEAA@XZ; CEventCollector::~CEventCollector(void)
0x180034322  nop
0x180034323  lea     rcx, [rsp+0F8h+var_D8]; this
0x180034328  call    ??1CAutoTransaction@@QEAA@XZ; CAutoTransaction::~CAutoTransaction(void)
0x18003432d  nop
0x18003432e  lea     rcx, [rsp+0F8h+var_C8]; this
0x180034333  call    ?Unlock@CAutoWriteLock@@QEAAXXZ; CAutoWriteLock::Unlock(void)
0x180034338  nop
0x180034339  mov     eax, ebx
0x18003433b  jmp     loc_1800345AC
0x180034340  cmp     cs:?g_bShuttingDown@@3_NA, 0; bool g_bShuttingDown
0x180034347  jz      short loc_1800343BB
0x180034349  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003434f  mov     ebx, 80041033h
0x180034354  mov     edx, ebx
0x180034356  mov     rcx, rax
0x180034359  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003435f  mov     rcx, cs:WPP_GLOBAL_Control
0x180034366  cmp     rcx, r12
0x180034369  jz      short loc_180034393
0x18003436b  test    byte ptr [rcx+1Ch], 1
0x18003436f  jz      short loc_180034393
0x180034371  cmp     byte ptr [rcx+19h], 2
0x180034375  jb      short loc_180034393
0x180034377  mov     edx, 28h ; '('
0x18003437c  mov     r9d, 80041033h
0x180034382  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180034389  mov     rcx, [rcx+10h]
0x18003438d  call    WPP_SF_d
0x180034392  nop
0x180034393  lea     rcx, [rsp+0F8h+var_B8]; this
0x180034398  call    ??1CEventCollector@@QEAA@XZ; CEventCollector::~CEventCollector(void)
0x18003439d  nop
0x18003439e  lea     rcx, [rsp+0F8h+var_D8]; this
0x1800343a3  call    ??1CAutoTransaction@@QEAA@XZ; CAutoTransaction::~CAutoTransaction(void)
0x1800343a8  nop
0x1800343a9  lea     rcx, [rsp+0F8h+var_C8]; this
0x1800343ae  call    ?Unlock@CAutoWriteLock@@QEAAXXZ; CAutoWriteLock::Unlock(void)
0x1800343b3  nop
0x1800343b4  mov     eax, ebx
0x1800343b6  jmp     loc_1800345AC
0x1800343bb  lea     rcx, [rsp+0F8h+var_D8]; this
0x1800343c0  call    ?InternalBeginTransaction@CAutoTransaction@@QEAAK_N@Z; CAutoTransaction::InternalBeginTransaction(bool)
0x1800343c5  mov     ebx, eax
0x1800343c7  test    eax, eax
0x1800343c9  jz      loc_1800344B6
0x1800343cf  jns     short loc_1800343E2
0x1800343d1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800343d7  mov     edx, ebx
0x1800343d9  mov     rcx, rax
0x1800343dc  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800343e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800343e9  cmp     rcx, r12
0x1800343ec  jz      short loc_180034413
0x1800343ee  test    byte ptr [rcx+1Ch], 1
0x1800343f2  jz      short loc_180034413
0x1800343f4  cmp     byte ptr [rcx+19h], 2
0x1800343f8  jb      short loc_180034413
0x1800343fa  mov     edx, 29h ; ')'
0x1800343ff  mov     r9d, ebx
0x180034402  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180034409  mov     rcx, [rcx+10h]
0x18003440d  call    WPP_SF_d
0x180034412  nop
0x180034413  lea     rcx, [rsp+0F8h+var_B8]; this
0x180034418  call    ??1CEventCollector@@QEAA@XZ; CEventCollector::~CEventCollector(void)
0x18003441d  nop
0x18003441e  lea     rcx, [rsp+0F8h+var_D8]; this
0x180034423  call    ??1CAutoTransaction@@QEAA@XZ; CAutoTransaction::~CAutoTransaction(void)
0x180034428  nop
0x180034429  lea     rcx, [rsp+0F8h+var_C8]; this
0x18003442e  call    ?Unlock@CAutoWriteLock@@QEAAXXZ; CAutoWriteLock::Unlock(void)
0x180034433  nop
0x180034434  mov     eax, ebx
0x180034436  jmp     loc_1800345AC
0x18003443b  cmp     cs:?g_bShuttingDown@@3_NA, 0; bool g_bShuttingDown
0x180034442  jz      short loc_1800344B6
0x180034444  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003444a  mov     ebx, 80041033h
0x18003444f  mov     edx, ebx
0x180034451  mov     rcx, rax
0x180034454  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003445a  mov     rcx, cs:WPP_GLOBAL_Control
0x180034461  cmp     rcx, r12
0x180034464  jz      short loc_18003448E
0x180034466  test    byte ptr [rcx+1Ch], 1
0x18003446a  jz      short loc_18003448E
0x18003446c  cmp     byte ptr [rcx+19h], 2
0x180034470  jb      short loc_18003448E
0x180034472  mov     edx, 2Ah ; '*'
0x180034477  mov     r9d, 80041033h
0x18003447d  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180034484  mov     rcx, [rcx+10h]
0x180034488  call    WPP_SF_d
0x18003448d  nop
0x18003448e  lea     rcx, [rsp+0F8h+var_B8]; this
0x180034493  call    ??1CEventCollector@@QEAA@XZ; CEventCollector::~CEventCollector(void)
0x180034498  nop
0x180034499  lea     rcx, [rsp+0F8h+var_D8]; this
0x18003449e  call    ??1CAutoTransaction@@QEAA@XZ; CAutoTransaction::~CAutoTransaction(void)
0x1800344a3  nop
0x1800344a4  lea     rcx, [rsp+0F8h+var_C8]; this
0x1800344a9  call    ?Unlock@CAutoWriteLock@@QEAAXXZ; CAutoWriteLock::Unlock(void)
0x1800344ae  nop
0x1800344af  mov     eax, ebx
0x1800344b1  jmp     loc_1800345AC
0x1800344b6  mov     cl, [rsi+0A8h]
0x1800344bc  mov     rax, [r14+58h]
0x1800344c0  cmp     dword ptr [rax+30h], 0
0x1800344c4  jge     short loc_180034503
0x1800344c6  test    cl, cl
0x1800344c8  jnz     short loc_1800344D4
0x1800344ca  lea     rcx, [rsp+0F8h+var_D8]; this
0x1800344cf  call    ?InternalAbortTransaction@CAutoTransaction@@QEAAKXZ; CAutoTransaction::InternalAbortTransaction(void)
0x1800344d4  mov     rax, [r14+58h]
0x1800344d8  mov     ebx, [rax+30h]
0x1800344db  lea     rcx, [rsp+0F8h+var_B8]; this
0x1800344e0  call    ??1CEventCollector@@QEAA@XZ; CEventCollector::~CEventCollector(void)
0x1800344e5  nop
0x1800344e6  lea     rcx, [rsp+0F8h+var_D8]; this
0x1800344eb  call    ??1CAutoTransaction@@QEAA@XZ; CAutoTransaction::~CAutoTransaction(void)
0x1800344f0  nop
0x1800344f1  lea     rcx, [rsp+0F8h+var_C8]; this
0x1800344f6  call    ?Unlock@CAutoWriteLock@@QEAAXXZ; CAutoWriteLock::Unlock(void)
0x1800344fb  nop
0x1800344fc  mov     eax, ebx
0x1800344fe  jmp     loc_1800345AC
0x180034503  test    cl, cl
0x180034505  jnz     short loc_18003451B
0x180034507  lea     rcx, [rsp+0F8h+var_D8]; this
0x18003450c  call    ?InternalAbortTransaction@CAutoTransaction@@QEAAKXZ; CAutoTransaction::InternalAbortTransaction(void)
0x180034511  lea     rcx, [rsp+0F8h+var_B8]; this
0x180034516  call    ?DeleteAllEvents@CEventCollector@@QEAAXXZ; CEventCollector::DeleteAllEvents(void)
0x18003451b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180034521  mov     ebx, 80004001h
0x180034526  mov     edx, ebx
0x180034528  mov     rcx, rax
0x18003452b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180034531  mov     rcx, cs:WPP_GLOBAL_Control
0x180034538  cmp     rcx, r12
0x18003453b  jz      short loc_180034565
0x18003453d  test    byte ptr [rcx+1Ch], 1
0x180034541  jz      short loc_180034565
0x180034543  cmp     byte ptr [rcx+19h], 2
0x180034547  jb      short loc_180034565
0x180034549  mov     edx, 2Bh ; '+'
0x18003454e  mov     r9d, 80004001h
0x180034554  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18003455b  mov     rcx, [rcx+10h]
0x18003455f  call    WPP_SF_d
0x180034564  nop
0x180034565  lea     rcx, [rsp+0F8h+var_B8]; this
0x18003456a  call    ??1CEventCollector@@QEAA@XZ; CEventCollector::~CEventCollector(void)
0x18003456f  nop
0x180034570  lea     rcx, [rsp+0F8h+var_D8]; this
0x180034575  call    ??1CAutoTransaction@@QEAA@XZ; CAutoTransaction::~CAutoTransaction(void)
0x18003457a  nop
0x18003457b  lea     rcx, [rsp+0F8h+var_C8]; this
0x180034580  call    ?Unlock@CAutoWriteLock@@QEAAXXZ; CAutoWriteLock::Unlock(void)
0x180034585  nop
0x180034586  mov     eax, ebx
0x180034588  jmp     short loc_1800345AC
0x18003458a  lea     rcx, [rsp+0F8h+var_C8]; this
0x18003458f  call    ?Unlock@CAutoWriteLock@@QEAAXXZ; CAutoWriteLock::Unlock(void)
0x180034594  nop
0x180034595  mov     eax, 80041006h
0x18003459a  jmp     short loc_1800345AC
0x18003459c  lea     rcx, [rsp+0F8h+var_C8]; this
0x1800345a1  call    ?Unlock@CAutoWriteLock@@QEAAXXZ; CAutoWriteLock::Unlock(void)
0x1800345a6  nop
0x1800345a7  mov     eax, 8004100Ah
0x1800345ac  add     rsp, 0D8h
0x1800345b3  pop     r14
0x1800345b5  pop     r12
0x1800345b7  pop     rsi
0x1800345b8  pop     rbx
0x1800345b9  retn
```
