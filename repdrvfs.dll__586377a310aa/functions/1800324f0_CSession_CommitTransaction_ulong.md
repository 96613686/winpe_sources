# CSession::CommitTransaction(ulong)

- ea: `0x1800324f0`
- end: `0x180032687`
- name: `?CommitTransaction@CSession@@UEAAJK@Z`
- size: `407`
- prototype: `__int64 __fastcall(CSession *this)`
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x180003fb0`
- `0x18001b578`
- `0x18001d5f0`
- `0x18001e270`
- `0x1800240ac`
- `0x1800257e8`
- `0x180027580`
- `0x1800276bc`
- `0x180027e8c`
- `0x1800324f0`
- `0x180048010`

## import_xrefs

- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180032570`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180032636`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180032570`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x180032636`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180032581`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180032581`
- `wbemcomn!?RemoveAt@CFlexArray@@QEAAHH@Z` at `0x18003258f`
- `wbemcomn!?RemoveAt@CFlexArray@@QEAAHH@Z` at `0x18003258f`

## pseudocode

```c
__int64 __fastcall CSession::CommitTransaction(CSession *this)
{
  CFlexArray *v2; // rbx
  void *v3; // rdi
  void *v4; // rsi
  struct _IWmiCoreServices *v5; // rbx
  __int64; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v8; // rax
  _BYTE v9[184]; // [rsp+20h] [rbp-B8h] BYREF
  struct _IWmiCoreServices *v10; // [rsp+E0h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids);
  }
  if ( *((_BYTE *)this + 168) )
  {
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      CFileCache::CommitTransaction((CFileCache *)byte_180058AF8);
      *((_BYTE *)this + 168) = 0;
      CEventCollector::CEventCollector((CEventCollector *)v9);
      v2 = (CSession *)((char *)this + 24);
      v9[96] = *((_BYTE *)v2 + 96);
      while ( CFlexArray::Size(v2) )
      {
        v3 = 0;
        v4 = CFlexArray::GetAt(v2, 0);
        if ( !CFlexArray::RemoveAt(v2, 0) )
          v3 = v4;
        CPointerArray<CRepEvent,CUniqueManager<CRepEvent>,CFlexArray>::Add(v9, v3);
      }
      CLock::WriteUnlock((CLock *)&g_readWriteLock);
      v10 = 0;
      if ( (int)CGlobals::GetCoreSvcs((CGlobals *)&g_Glob, &v10) >= 0 )
      {
        v5 = v10;
        CEventCollector::SendEvents((CEventCollector *)v9, v10);
        CEventCollector::DeleteAllEvents((CEventCollector *)v9);
        if ( v5 )
          (*(void (__fastcall **)(struct _IWmiCoreServices *))(*(_QWORD *)v5 + 16LL))(v5);
      }
      CEventCollector::~CEventCollector((CEventCollector *)v9);
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &CX_MemoryException `RTTI Type Descriptor', 0) )
      {
        CLock::WriteUnlock((CLock *)&g_readWriteLock);
        MemLogObject = GetMemLogObject();
        CMemoryLog::Write(MemLogObject, -2147217402);
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            71,
            WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
            2147749894LL);
        }
         = 2147749894LL;
        __eh34_try_continuation(0, &CX_MemoryException `RTTI Type Descriptor', &loc_180032624);
        return ;
      }
      if ( __eh34_catch_type(0, &CX_Exception `RTTI Type Descriptor', 0) )
      {
        CLock::WriteUnlock((CLock *)&g_readWriteLock);
        v8 = GetMemLogObject();
        CMemoryLog::Write(v8, -2147217398);
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            72,
            WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids,
            2147749898LL);
        }
         = 2147749898LL;
        __eh34_try_continuation(0, &CX_Exception `RTTI Type Descriptor', &loc_18003262B);
        return ;
      }
    }
  }
  else
  {
    CFlexArray::Size((CSession *)((char *)this + 24));
    CLock::ReadUnlock((CLock *)&g_readWriteLock);
  }
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x1800324f0  push    rbx
0x1800324f2  push    rsi
0x1800324f3  push    rdi
0x1800324f4  push    r15
0x1800324f6  sub     rsp, 0B8h
0x1800324fd  mov     rbx, rcx
0x180032500  lea     r15, WPP_GLOBAL_Control
0x180032507  mov     rcx, cs:WPP_GLOBAL_Control
0x18003250e  cmp     rcx, r15
0x180032511  jz      short loc_180032534
0x180032513  test    byte ptr [rcx+1Ch], 1
0x180032517  jz      short loc_180032534
0x180032519  cmp     byte ptr [rcx+19h], 5
0x18003251d  jb      short loc_180032534
0x18003251f  mov     edx, 46h ; 'F'
0x180032524  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18003252b  mov     rcx, [rcx+10h]
0x18003252f  call    WPP_SF_
0x180032534  cmp     byte ptr [rbx+0A8h], 0
0x18003253b  jz      loc_180032632
0x180032541  lea     rcx, byte_180058AF8; this
0x180032548  call    ?CommitTransaction@CFileCache@@QEAAJXZ; CFileCache::CommitTransaction(void)
0x18003254d  mov     byte ptr [rbx+0A8h], 0
0x180032554  lea     rcx, [rsp+0D8h+var_B8]; this
0x180032559  call    ??0CEventCollector@@QEAA@XZ; CEventCollector::CEventCollector(void)
0x18003255e  nop
0x18003255f  add     rbx, 18h
0x180032563  mov     al, [rbx+60h]
0x180032566  mov     [rsp+0D8h+var_58], al
0x18003256d  mov     rcx, rbx
0x180032570  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x180032576  test    eax, eax
0x180032578  jz      short loc_1800325AA
0x18003257a  xor     edi, edi
0x18003257c  xor     edx, edx
0x18003257e  mov     rcx, rbx
0x180032581  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x180032587  mov     rsi, rax
0x18003258a  xor     edx, edx
0x18003258c  mov     rcx, rbx
0x18003258f  call    cs:__imp_?RemoveAt@CFlexArray@@QEAAHH@Z; CFlexArray::RemoveAt(int)
0x180032595  test    eax, eax
0x180032597  cmovz   rdi, rsi
0x18003259b  mov     rdx, rdi
0x18003259e  lea     rcx, [rsp+0D8h+var_B8]
0x1800325a3  call    ?Add@?$CPointerArray@VCRepEvent@@V?$CUniqueManager@VCRepEvent@@@@VCFlexArray@@@@QEAAHPEAVCRepEvent@@@Z; CPointerArray<CRepEvent,CUniqueManager<CRepEvent>,CFlexArray>::Add(CRepEvent *)
0x1800325a8  jmp     short loc_18003256D
0x1800325aa  lea     rcx, ?g_readWriteLock@@3VCLock@@A; this
0x1800325b1  call    ?WriteUnlock@CLock@@QEAAHXZ; CLock::WriteUnlock(void)
0x1800325b6  mov     [rsp+0D8h+arg_0], 0
0x1800325c2  lea     rdx, [rsp+0D8h+arg_0]; struct _IWmiCoreServices **
0x1800325ca  lea     rcx, ?g_Glob@@3VCGlobals@@A; this
0x1800325d1  call    ?GetCoreSvcs@CGlobals@@QEAAJPEAPEAU_IWmiCoreServices@@@Z; CGlobals::GetCoreSvcs(_IWmiCoreServices * *)
0x1800325d6  test    eax, eax
0x1800325d8  js      short loc_180032617
0x1800325da  mov     rbx, [rsp+0D8h+arg_0]
0x1800325e2  mov     [rsp+0D8h+arg_0], rbx
0x1800325ea  mov     rdx, rbx; struct _IWmiCoreServices *
0x1800325ed  lea     rcx, [rsp+0D8h+var_B8]; this
0x1800325f2  call    ?SendEvents@CEventCollector@@QEAAJPEAU_IWmiCoreServices@@@Z; CEventCollector::SendEvents(_IWmiCoreServices *)
0x1800325f7  lea     rcx, [rsp+0D8h+var_B8]; this
0x1800325fc  call    ?DeleteAllEvents@CEventCollector@@QEAAXXZ; CEventCollector::DeleteAllEvents(void)
0x180032601  nop
0x180032602  test    rbx, rbx
0x180032605  jz      short loc_180032617
0x180032607  mov     rax, [rbx]
0x18003260a  mov     rcx, rbx
0x18003260d  mov     rax, [rax+10h]
0x180032611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032616  nop
0x180032617  lea     rcx, [rsp+0D8h+var_B8]; this
0x18003261c  call    ??1CEventCollector@@QEAA@XZ; CEventCollector::~CEventCollector(void)
0x180032621  nop
0x180032622  jmp     short loc_180032648
0x180032624  mov     eax, 80041006h
0x180032629  jmp     short loc_180032630
0x18003262b  mov     eax, 8004100Ah
0x180032630  jmp     short loc_18003267A
0x180032632  lea     rcx, [rbx+18h]
0x180032636  call    cs:__imp_?Size@CFlexArray@@QEBAHXZ; CFlexArray::Size(void)
0x18003263c  lea     rcx, ?g_readWriteLock@@3VCLock@@A; this
0x180032643  call    ?ReadUnlock@CLock@@QEAAHXZ; CLock::ReadUnlock(void)
0x180032648  mov     rcx, cs:WPP_GLOBAL_Control
0x18003264f  cmp     rcx, r15
0x180032652  jz      short loc_180032678
0x180032654  test    byte ptr [rcx+1Ch], 1
0x180032658  jz      short loc_180032678
0x18003265a  cmp     byte ptr [rcx+19h], 2
0x18003265e  jb      short loc_180032678
0x180032660  mov     edx, 49h ; 'I'
0x180032665  xor     r9d, r9d
0x180032668  lea     r8, WPP_2cf5eb29da313cb256d577853629d7e2_Traceguids
0x18003266f  mov     rcx, [rcx+10h]
0x180032673  call    WPP_SF_d
0x180032678  xor     eax, eax
0x18003267a  add     rsp, 0B8h
0x180032681  pop     r15
0x180032683  pop     rdi
0x180032684  pop     rsi
0x180032685  pop     rbx
0x180032686  retn
```
