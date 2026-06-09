# CSession::ExecQuery(IWmiDbHandle *,IWbemQuery *,ulong,ulong,ulong *,void *)

- ea: `0x1800032a0`
- end: `0x180003653`
- name: `?ExecQuery@CSession@@UEAAJPEAUIWmiDbHandle@@PEAUIWbemQuery@@KKPEAKPEAX@Z`
- size: `947`
- prototype: `__int64 __fastcall(CSession *this, struct IWmiDbHandle *, struct IWbemQuery *, unsigned int, unsigned int, unsigned int *, void *)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180001224`
- `0x1800012b8`
- `0x1800013a0`
- `0x180001750`
- `0x1800032a0`
- `0x1800037a0`
- `0x180003fb0`
- `0x180024f30`
- `0x180048010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1800034a1`
- `wbemcomn!GetMemLogObject` at `0x1800034e8`
- `wbemcomn!GetMemLogObject` at `0x18000354b`
- `wbemcomn!GetMemLogObject` at `0x1800035e5`
- `wbemcomn!GetMemLogObject` at `0x1800034a1`
- `wbemcomn!GetMemLogObject` at `0x1800034e8`
- `wbemcomn!GetMemLogObject` at `0x18000354b`
- `wbemcomn!GetMemLogObject` at `0x1800035e5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800034af`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800034f6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180003559`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800035f0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800034af`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800034f6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180003559`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800035f0`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CSession::ExecQuery(
        CSession *this,
        struct IWmiDbHandle *a2,
        struct IWbemQuery *a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int *a6,
        void *a7)
{
  struct IWmiDbHandle *v9; // rdi
  CVarObjHeap *v11; // r10
  char v12; // cl
  char v13; // cl
  int v14; // ebx
  __int64 result; // rax
  int v16; // ebx
  CVarObjHeap *v17; // rcx
  CMemoryLog *v18; // rax
  CMemoryLog *v19; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v21; // rax
  CMemoryLog *v22; // rax
  CMemoryLog *v23; // rax
  unsigned int *v24; // [rsp+28h] [rbp-70h]
  IWbemObjectSink v25; // [rsp+30h] [rbp-68h] BYREF
  int v26; // [rsp+38h] [rbp-60h]
  __int64 v27; // [rsp+40h] [rbp-58h]
  void *v28; // [rsp+48h] [rbp-50h]
  bool v29; // [rsp+50h] [rbp-48h]
  __int16 v30; // [rsp+51h] [rbp-47h]

  try
  {
    v9 = a2;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, a2, a3);
      v11 = WPP_GLOBAL_Control;
    }
    v12 = *((_BYTE *)this + 168);
    v26 = 0;
    v27 = 0;
    v25.lpVtbl = (struct IWbemObjectSinkVtbl *)&UnlockDuringIndicate::`vftable';
    v28 = a7;
    LOBYTE(a2) = v12 == 0;
    v29 = v12 == 0;
    v30 = 0;
    if ( v12 )
    {
      v13 = 0;
LABEL_6:
      if ( g_bShuttingDown )
      {
        MemLogObject = GetMemLogObject();
        CMemoryLog::Write(MemLogObject, -2147217357);
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            57,
            WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
            2147749939LL);
        }
        UnlockDuringIndicate::~UnlockDuringIndicate((UnlockDuringIndicate *)&v25);
        return 2147749939LL;
      }
      else
      {
        v14 = *(_DWORD *)(*((_QWORD *)v9 + 11) + 48LL);
        if ( v14 >= 0 )
        {
          if ( v11 != (CVarObjHeap *)&WPP_GLOBAL_Control
            && (*((_BYTE *)v11 + 28) & 1) != 0
            && *((_BYTE *)v11 + 25) >= 5u )
          {
            WPP_SF_(*((_QWORD *)v11 + 2), 440, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids);
          }
          v16 = CNamespaceHandle::ExecQuerySink(v9, a3, a4, a4, &v25, v24);
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids);
            v17 = WPP_GLOBAL_Control;
          }
          if ( v16 < 0 )
          {
            v21 = GetMemLogObject();
            CMemoryLog::Write(v21, v16);
            v17 = WPP_GLOBAL_Control;
          }
          if ( v17 != (CVarObjHeap *)&WPP_GLOBAL_Control
            && (*((_BYTE *)v17 + 28) & 1) != 0
            && *((_BYTE *)v17 + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)v17 + 2), 58, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, (unsigned int)v16);
          }
          v25.lpVtbl = (struct IWbemObjectSinkVtbl *)&UnlockDuringIndicate::`vftable';
          if ( HIBYTE(v30) && v29 )
          {
            CLock::ReadUnlock((CLock *)&g_readWriteLock);
            HIBYTE(v30) = 0;
          }
          v25.lpVtbl = (struct IWbemObjectSinkVtbl *)&CUnkBase<IWbemObjectSink,&_GUID const IID_IWbemObjectSink>::`vftable';
          if ( v27 )
            (*(void (__fastcall **)(__int64, IWbemObjectSink *))(*(_QWORD *)v27 + 8LL))(v27, &v25);
          return (unsigned int)v16;
        }
        else
        {
          v25.lpVtbl = (struct IWbemObjectSinkVtbl *)&UnlockDuringIndicate::`vftable';
          if ( (_BYTE)a2 && v13 )
          {
            CLock::ReadUnlock((CLock *)&g_readWriteLock);
            HIBYTE(v30) = 0;
          }
          v25.lpVtbl = (struct IWbemObjectSinkVtbl *)&CUnkBase<IWbemObjectSink,&_GUID const IID_IWbemObjectSink>::`vftable';
          return (unsigned int)v14;
        }
      }
    }
    if ( !(unsigned int)CLock::ReadLock((CLock *)&g_readWriteLock, (unsigned int)a2) )
    {
      HIBYTE(v30) = 1;
      v13 = 1;
      LOBYTE(a2) = v29;
      v11 = WPP_GLOBAL_Control;
      goto LABEL_6;
    }
    v18 = GetMemLogObject();
    CMemoryLog::Write(v18, -2147217407);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 544, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749889LL);
    }
    v19 = GetMemLogObject();
    CMemoryLog::Write(v19, -2147217407);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749889LL);
    }
    UnlockDuringIndicate::~UnlockDuringIndicate((UnlockDuringIndicate *)&v25);
    result = 2147749889LL;
  }
  catch ( CX_MemoryException )
  {
    v22 = GetMemLogObject();
    CMemoryLog::Write(v22, -2147217402);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
  catch ( CX_Exception )
  {
    v23 = GetMemLogObject();
    CMemoryLog::Write(v23, -2147217398);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 2147749898LL);
    }
    return 2147749898LL;
  }
  v9 = a2;
}

```

## disassembly

```asm
0x1800032a0  push    rbx
0x1800032a2  push    rsi
0x1800032a3  push    rdi
0x1800032a4  push    r12
0x1800032a6  push    r14
0x1800032a8  push    r15
0x1800032aa  sub     rsp, 68h
0x1800032ae  mov     r14d, r9d
0x1800032b1  mov     rsi, r8
0x1800032b4  mov     rdi, rdx
0x1800032b7  mov     rbx, rcx
0x1800032ba  lea     r12, WPP_GLOBAL_Control
0x1800032c1  mov     r10, cs:WPP_GLOBAL_Control
0x1800032c8  cmp     r10, r12
0x1800032cb  jnz     loc_180003392
0x1800032d1  movzx   ecx, byte ptr [rbx+0A8h]
0x1800032d8  mov     [rsp+98h+var_60], 0
0x1800032e0  xor     r8d, r8d
0x1800032e3  mov     [rsp+98h+var_58], r8
0x1800032e8  lea     r15, ??_7UnlockDuringIndicate@@6B@; const UnlockDuringIndicate::`vftable'
0x1800032ef  mov     [rsp+98h+var_68.lpVtbl], r15
0x1800032f4  mov     rax, [rsp+98h+arg_30]
0x1800032fc  mov     [rsp+98h+var_50], rax
0x180003301  test    cl, cl
0x180003303  setz    dl; unsigned int
0x180003306  mov     [rsp+98h+var_48], dl
0x18000330a  mov     [rsp+98h+var_47], r8w
0x180003310  test    cl, cl
0x180003312  jnz     loc_180003544
0x180003318  lea     rcx, ?g_readWriteLock@@3VCLock@@A; this
0x18000331f  call    ?ReadLock@CLock@@QEAAHK@Z; CLock::ReadLock(ulong)
0x180003324  test    eax, eax
0x180003326  jnz     loc_1800034A1
0x18000332c  mov     byte ptr [rsp+98h+var_47+1], 1
0x180003331  mov     cl, 1
0x180003333  movzx   edx, [rsp+98h+var_48]
0x180003338  mov     r8, [rsp+98h+var_58]
0x18000333d  mov     r10, cs:WPP_GLOBAL_Control
0x180003344  cmp     cs:?g_bShuttingDown@@3_NA, 0; bool g_bShuttingDown
0x18000334b  jnz     loc_18000354B
0x180003351  mov     rax, [rdi+58h]
0x180003355  mov     ebx, [rax+30h]
0x180003358  test    ebx, ebx
0x18000335a  jns     short loc_1800033C5
0x18000335c  mov     [rsp+98h+var_68.lpVtbl], r15
0x180003361  test    dl, dl
0x180003363  jz      short loc_18000336D
0x180003365  test    cl, cl
0x180003367  jnz     loc_180003445
0x18000336d  lea     rax, ??_7?$CUnkBase@UIWbemObjectSink@@$1?IID_IWbemObjectSink@@3U_GUID@@B@@6B@; const CUnkBase<IWbemObjectSink,&_GUID const IID_IWbemObjectSink>::`vftable'
0x180003374  mov     [rsp+98h+var_68.lpVtbl], rax
0x180003379  test    r8, r8
0x18000337c  jnz     loc_1800035A7
0x180003382  mov     eax, ebx
0x180003384  add     rsp, 68h
0x180003388  pop     r15
0x18000338a  pop     r14
0x18000338c  pop     r12
0x18000338e  pop     rdi
0x18000338f  pop     rsi
0x180003390  pop     rbx
0x180003391  retn
0x180003392  test    byte ptr [r10+1Ch], 1
0x180003397  jz      loc_1800032D1
0x18000339d  cmp     byte ptr [r10+19h], 5
0x1800033a2  jb      loc_1800032D1
0x1800033a8  mov     [rsp+98h+var_78], rsi
0x1800033ad  mov     r9, rdi
0x1800033b0  mov     rcx, [r10+10h]
0x1800033b4  call    WPP_SF_qq
0x1800033b9  mov     r10, cs:WPP_GLOBAL_Control
0x1800033c0  jmp     loc_1800032D1
0x1800033c5  cmp     r10, r12
0x1800033c8  jz      short loc_1800033D5
0x1800033ca  test    byte ptr [r10+1Ch], 1
0x1800033cf  jnz     loc_1800035C0
0x1800033d5  lea     rax, [rsp+98h+var_68]
0x1800033da  mov     [rsp+98h+var_78], rax; struct IWbemObjectSink *
0x1800033df  mov     r8d, r14d; unsigned int
0x1800033e2  mov     rdx, rsi; struct IWbemQuery *
0x1800033e5  mov     rcx, rdi; this
0x1800033e8  call    ?ExecQuerySink@CNamespaceHandle@@QEAAJPEAUIWbemQuery@@KKPEAUIWbemObjectSink@@PEAK@Z; CNamespaceHandle::ExecQuerySink(IWbemQuery *,ulong,ulong,IWbemObjectSink *,ulong *)
0x1800033ed  mov     ebx, eax
0x1800033ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800033f6  cmp     rcx, r12
0x1800033f9  jz      short loc_180003401
0x1800033fb  test    byte ptr [rcx+1Ch], 1
0x1800033ff  jnz     short loc_18000347A
0x180003401  test    ebx, ebx
0x180003403  js      loc_1800035E5
0x180003409  cmp     rcx, r12
0x18000340c  jz      short loc_180003418
0x18000340e  test    byte ptr [rcx+1Ch], 1
0x180003412  jnz     loc_180003602
0x180003418  mov     [rsp+98h+var_68.lpVtbl], r15
0x18000341d  cmp     byte ptr [rsp+98h+var_47+1], 0
0x180003422  jnz     short loc_180003460
0x180003424  lea     rax, ??_7?$CUnkBase@UIWbemObjectSink@@$1?IID_IWbemObjectSink@@3U_GUID@@B@@6B@; const CUnkBase<IWbemObjectSink,&_GUID const IID_IWbemObjectSink>::`vftable'
0x18000342b  mov     [rsp+98h+var_68.lpVtbl], rax
0x180003430  mov     rcx, [rsp+98h+var_58]
0x180003435  test    rcx, rcx
0x180003438  jnz     loc_180003629
0x18000343e  mov     eax, ebx
0x180003440  jmp     loc_180003384
0x180003445  lea     rcx, ?g_readWriteLock@@3VCLock@@A; this
0x18000344c  call    ?ReadUnlock@CLock@@QEAAHXZ; CLock::ReadUnlock(void)
0x180003451  mov     byte ptr [rsp+98h+var_47+1], 0
0x180003456  mov     r8, [rsp+98h+var_58]
0x18000345b  jmp     loc_18000336D
0x180003460  cmp     [rsp+98h+var_48], 0
0x180003465  jz      short loc_180003424
0x180003467  lea     rcx, ?g_readWriteLock@@3VCLock@@A; this
0x18000346e  call    ?ReadUnlock@CLock@@QEAAHXZ; CLock::ReadUnlock(void)
0x180003473  mov     byte ptr [rsp+98h+var_47+1], 0
0x180003478  jmp     short loc_180003424
0x18000347a  cmp     byte ptr [rcx+19h], 5
0x18000347e  jb      short loc_180003401
0x180003480  mov     edx, 50h ; 'P'
0x180003485  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18000348c  mov     rcx, [rcx+10h]
0x180003490  call    WPP_SF_
0x180003495  mov     rcx, cs:WPP_GLOBAL_Control
0x18000349c  jmp     loc_180003401
0x1800034a1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800034a7  mov     edx, 80041001h
0x1800034ac  mov     rcx, rax
0x1800034af  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800034b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800034bc  cmp     rcx, r12
0x1800034bf  jz      short loc_1800034E8
0x1800034c1  test    byte ptr [rcx+1Ch], 1
0x1800034c5  jz      short loc_1800034E8
0x1800034c7  cmp     byte ptr [rcx+19h], 2
0x1800034cb  jb      short loc_1800034E8
0x1800034cd  mov     edx, 220h
0x1800034d2  mov     r9d, 80041001h
0x1800034d8  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x1800034df  mov     rcx, [rcx+10h]
0x1800034e3  call    WPP_SF_d
0x1800034e8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800034ee  mov     edx, 80041001h
0x1800034f3  mov     rcx, rax
0x1800034f6  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800034fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180003503  cmp     rcx, r12
0x180003506  jz      short loc_180003530
0x180003508  test    byte ptr [rcx+1Ch], 1
0x18000350c  jz      short loc_180003530
0x18000350e  cmp     byte ptr [rcx+19h], 2
0x180003512  jb      short loc_180003530
0x180003514  mov     edx, 38h ; '8'
0x180003519  mov     r9d, 80041001h
0x18000351f  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180003526  mov     rcx, [rcx+10h]
0x18000352a  call    WPP_SF_d
0x18000352f  nop
0x180003530  lea     rcx, [rsp+98h+var_68]; this
0x180003535  call    ??1UnlockDuringIndicate@@UEAA@XZ; UnlockDuringIndicate::~UnlockDuringIndicate(void)
0x18000353a  mov     eax, 80041001h
0x18000353f  jmp     loc_180003384
0x180003544  xor     cl, cl
0x180003546  jmp     loc_180003344
0x18000354b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180003551  mov     edx, 80041033h
0x180003556  mov     rcx, rax
0x180003559  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000355f  mov     rcx, cs:WPP_GLOBAL_Control
0x180003566  cmp     rcx, r12
0x180003569  jz      short loc_180003593
0x18000356b  test    byte ptr [rcx+1Ch], 1
0x18000356f  jz      short loc_180003593
0x180003571  cmp     byte ptr [rcx+19h], 2
0x180003575  jb      short loc_180003593
0x180003577  mov     edx, 39h ; '9'
0x18000357c  mov     r9d, 80041033h
0x180003582  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x180003589  mov     rcx, [rcx+10h]
0x18000358d  call    WPP_SF_d
0x180003592  nop
0x180003593  lea     rcx, [rsp+98h+var_68]; this
0x180003598  call    ??1UnlockDuringIndicate@@UEAA@XZ; UnlockDuringIndicate::~UnlockDuringIndicate(void)
0x18000359d  mov     eax, 80041033h
0x1800035a2  jmp     loc_180003384
0x1800035a7  mov     rdx, [r8]
0x1800035aa  mov     rax, [rdx+8]
0x1800035ae  lea     rdx, [rsp+98h+var_68]
0x1800035b3  mov     rcx, r8
0x1800035b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035bb  jmp     loc_180003382
0x1800035c0  cmp     byte ptr [r10+19h], 5
0x1800035c5  jb      loc_1800033D5
0x1800035cb  mov     edx, 1B8h
0x1800035d0  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x1800035d7  mov     rcx, [r10+10h]
0x1800035db  call    WPP_SF_
0x1800035e0  jmp     loc_1800033D5
0x1800035e5  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800035eb  mov     edx, ebx
0x1800035ed  mov     rcx, rax
0x1800035f0  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800035f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800035fd  jmp     loc_180003409
0x180003602  cmp     byte ptr [rcx+19h], 2
0x180003606  jb      loc_180003418
0x18000360c  mov     edx, 3Ah ; ':'
0x180003611  mov     r9d, ebx
0x180003614  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18000361b  mov     rcx, [rcx+10h]
0x18000361f  call    WPP_SF_d
0x180003624  jmp     loc_180003418
0x180003629  mov     rax, [rcx]
0x18000362c  lea     rdx, [rsp+98h+var_68]
0x180003631  mov     rax, [rax+8]
0x180003635  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000363a  jmp     loc_18000343E
0x18000363f  mov     eax, 80041006h
0x180003644  jmp     loc_180003384
0x180003649  mov     eax, 8004100Ah
0x18000364e  jmp     loc_180003384
```
