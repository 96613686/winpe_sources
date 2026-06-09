# CKsQueue::~CKsQueue(void)

- ea: `0x18005fe10`
- end: `0x180060109`
- name: `??1CKsQueue@@UEAA@XZ`
- size: `761`
- prototype: `void __fastcall(CKsQueue *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18005fdd8`

## callees

- `0x180005a00`
- `0x180005a40`
- `0x18000aa80`
- `0x18000dddc`
- `0x18000fe40`
- `0x1800160d0`
- `0x180019cb0`
- `0x18005fe10`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18005febe`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005ff4d`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006008c`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005febe`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005ff4d`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006008c`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x18005ff62`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x18005ff62`

## pseudocode

```c
void __fastcall CKsQueue::~CKsQueue(CKsQueue *this)
{
  IKsMdlCache *m_MdlCacheComponent; // rcx
  IKsPipeSection *m_PipeSection; // rcx
  void *m_FlushWorker; // rcx
  _KSPSTREAM_POINTER *m_Leading; // rcx
  _KSPSTREAM_POINTER *m_Trailing; // rcx
  int v7; // edx
  struct _KSGATE *m_StateGate; // rcx
  __int64 v9; // rdx
  INTERLOCKEDLIST_HEAD *p_m_FrameHeadersAvailable; // rdi
  struct _LIST_ENTRY *Flink; // rcx
  struct _LIST_ENTRY *v12; // rax
  IKsPipeSection *v13; // rcx
  IKsProcessingObject *m_ProcessingObject; // rcx

  this->IKsQueue::IKsTransport::IUnknown::__vftable = (CKsQueue_vtbl *)&CKsQueue::`vftable'{for `IKsQueue'};
  this->IKsMdlCache::IUnknown::__vftable = (IKsMdlCache_vtbl *)&CKsQueue::`vftable'{for `IKsMdlCache'};
  this->CBaseUnknown::INonDelegatedUnknown::__vftable = (CBaseUnknown_vtbl *)&CKsQueue::`vftable'{for `INonDelegatedUnknown'};
  this->CBaseUnknown::IIndirectedUnknown::__vftable = (IIndirectedUnknown_vtbl *)&CKsPin::`vftable'{for `IIndirectedUnknown'};
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
      WPP_RECORDER_SF_q(
        WPP_GLOBAL_Control->DeviceExtension,
        5,
        1,
        42,
        (__int64)WPP_13a31f976c1e3a0a846d2ee29290b270_Traceguids,
        (char)this);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      WPP_RECORDER_SF_q(
        WPP_GLOBAL_Control->DeviceExtension,
        5,
        1,
        43,
        (__int64)WPP_13a31f976c1e3a0a846d2ee29290b270_Traceguids,
        (char)this);
  }
  m_MdlCacheComponent = this->m_MdlCacheComponent;
  if ( m_MdlCacheComponent )
  {
    m_MdlCacheComponent->Release(m_MdlCacheComponent);
    this->m_MdlCacheComponent = 0;
  }
  m_PipeSection = this->m_PipeSection;
  if ( m_PipeSection )
    m_PipeSection->UnbindProcessPins(m_PipeSection);
  m_FlushWorker = this->m_FlushWorker;
  if ( m_FlushWorker )
  {
    KsUnregisterWorker(m_FlushWorker);
    this->m_FlushWorker = 0;
  }
  m_Leading = this->m_Leading;
  if ( m_Leading )
  {
    ExFreePoolWithTag(m_Leading, 0);
    this->m_Leading = 0;
  }
  m_Trailing = this->m_Trailing;
  if ( m_Trailing )
  {
    ExFreePoolWithTag(m_Trailing, 0);
    this->m_Trailing = 0;
  }
  KsGateTurnInputOn(this->m_AndGate);
  m_StateGate = this->m_StateGate;
  if ( m_StateGate && !this->m_StateGateIsOr )
    KsGateTurnInputOn(m_StateGate);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v7) = 5;
    WPP_RECORDER_SF_qqd(
      WPP_GLOBAL_Control->DeviceExtension,
      v7,
      this->m_AndGate,
      48,
      (__int64)WPP_13a31f976c1e3a0a846d2ee29290b270_Traceguids,
      (char)this,
      (char)this->m_AndGate,
      this->m_AndGate->Count);
  }
  if ( KsGateCaptureThreshold(this->m_AndGate) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_q(
        WPP_GLOBAL_Control->DeviceExtension,
        4,
        1,
        49,
        (__int64)WPP_13a31f976c1e3a0a846d2ee29290b270_Traceguids,
        (char)this);
    LOBYTE(v9) = this->m_ProcessAsynchronously;
    this->m_ProcessingObject->Process(this->m_ProcessingObject, v9);
  }
  p_m_FrameHeadersAvailable = &this->m_FrameHeadersAvailable;
  while ( 1 )
  {
    Flink = p_m_FrameHeadersAvailable->ListEntry.Flink;
    if ( (INTERLOCKEDLIST_HEAD *)p_m_FrameHeadersAvailable->ListEntry.Flink == p_m_FrameHeadersAvailable )
      break;
    if ( (INTERLOCKEDLIST_HEAD *)Flink->Blink != p_m_FrameHeadersAvailable
      || (v12 = Flink->Flink, Flink->Flink->Blink != Flink) )
    {
      __fastfail(3u);
    }
    p_m_FrameHeadersAvailable->ListEntry.Flink = v12;
    v12->Blink = &p_m_FrameHeadersAvailable->ListEntry;
    ExFreePoolWithTag(Flink, 0);
  }
  ExDeleteNPagedLookasideList(&this->m_ChannelContextLookaside);
  v13 = this->m_PipeSection;
  if ( v13 )
  {
    v13->Release(v13);
    this->m_PipeSection = 0;
  }
  m_ProcessingObject = this->m_ProcessingObject;
  if ( m_ProcessingObject )
  {
    m_ProcessingObject->Release(m_ProcessingObject);
    this->m_ProcessingObject = 0;
  }
  if ( (KsXdvExtLevel & 0x18) != 0 )
    KspQueueVerifierRemoveEntry(&this->m_VerifierQueueEntry);
  this->CBaseUnknown::INonDelegatedUnknown::__vftable = (CBaseUnknown_vtbl *)&CBaseUnknown::`vftable'{for `INonDelegatedUnknown'};
  this->CBaseUnknown::IIndirectedUnknown::__vftable = (IIndirectedUnknown_vtbl *)&CKsPin::`vftable'{for `IIndirectedUnknown'};
}

```

## disassembly

```asm
0x18005fe10  push    rbx
0x18005fe12  push    rbp
0x18005fe13  push    rsi
0x18005fe14  push    rdi
0x18005fe15  sub     rsp, 48h
0x18005fe19  lea     rax, ??_7CKsQueue@@6BIKsQueue@@@; const CKsQueue::`vftable'{for `IKsQueue'}
0x18005fe20  mov     rbx, rcx
0x18005fe23  mov     [rcx], rax
0x18005fe26  lea     rax, ??_7CKsQueue@@6BIKsMdlCache@@@; const CKsQueue::`vftable'{for `IKsMdlCache'}
0x18005fe2d  mov     [rcx+8], rax
0x18005fe31  lea     rax, ??_7CKsQueue@@6BINonDelegatedUnknown@@@; const CKsQueue::`vftable'{for `INonDelegatedUnknown'}
0x18005fe38  mov     [rcx+10h], rax
0x18005fe3c  lea     rax, ??_7CKsPin@@6BIIndirectedUnknown@@@; const CKsPin::`vftable'{for `IIndirectedUnknown'}
0x18005fe43  mov     [rcx+18h], rax
0x18005fe47  lea     rdi, WPP_RECORDER_INITIALIZED
0x18005fe4e  xor     esi, esi
0x18005fe50  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x18005fe57  lea     rbp, WPP_13a31f976c1e3a0a846d2ee29290b270_Traceguids
0x18005fe5e  jnz     loc_18006001A
0x18005fe64  mov     rcx, [rbx+248h]
0x18005fe6b  test    rcx, rcx
0x18005fe6e  jz      short loc_18005FE83
0x18005fe70  mov     rax, [rcx]
0x18005fe73  mov     rax, [rax+10h]
0x18005fe77  call    _guard_dispatch_icall
0x18005fe7c  mov     [rbx+248h], rsi
0x18005fe83  mov     rcx, [rbx+40h]
0x18005fe87  test    rcx, rcx
0x18005fe8a  jz      short loc_18005FE98
0x18005fe8c  mov     rax, [rcx]
0x18005fe8f  mov     rax, [rax+40h]
0x18005fe93  call    _guard_dispatch_icall
0x18005fe98  mov     rcx, [rbx+360h]; Worker
0x18005fe9f  test    rcx, rcx
0x18005fea2  jz      short loc_18005FEB0
0x18005fea4  call    KsUnregisterWorker
0x18005fea9  mov     [rbx+360h], rsi
0x18005feb0  mov     rcx, [rbx+250h]; P
0x18005feb7  test    rcx, rcx
0x18005feba  jz      short loc_18005FED1
0x18005febc  xor     edx, edx; Tag
0x18005febe  call    cs:__imp_ExFreePoolWithTag
0x18005fec5  nop     dword ptr [rax+rax+00h]
0x18005feca  mov     [rbx+250h], rsi
0x18005fed1  mov     rcx, [rbx+258h]; P
0x18005fed8  test    rcx, rcx
0x18005fedb  jnz     loc_18006008A
0x18005fee1  mov     rcx, [rbx+0A8h]; Gate
0x18005fee8  call    KsGateTurnInputOn
0x18005feed  mov     rcx, [rbx+0C0h]; Gate
0x18005fef4  test    rcx, rcx
0x18005fef7  jnz     loc_1800600A4
0x18005fefd  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x18005ff04  jnz     loc_18005FFD6
0x18005ff0a  mov     rcx, [rbx+0A8h]; Gate
0x18005ff11  call    KsGateCaptureThreshold
0x18005ff16  test    al, al
0x18005ff18  jnz     loc_1800600BB
0x18005ff1e  lea     rdi, [rbx+148h]
0x18005ff25  mov     rcx, [rdi]; P
0x18005ff28  cmp     rcx, rdi
0x18005ff2b  jz      short loc_18005FF5B
0x18005ff2d  cmp     [rcx+8], rdi
0x18005ff31  jnz     loc_180060102
0x18005ff37  mov     rax, [rcx]
0x18005ff3a  cmp     [rax+8], rcx
0x18005ff3e  jnz     loc_180060102
0x18005ff44  mov     [rdi], rax
0x18005ff47  xor     edx, edx; Tag
0x18005ff49  mov     [rax+8], rdi
0x18005ff4d  call    cs:__imp_ExFreePoolWithTag
0x18005ff54  nop     dword ptr [rax+rax+00h]
0x18005ff59  jmp     short loc_18005FF25
0x18005ff5b  lea     rcx, [rbx+2C0h]; Lookaside
0x18005ff62  call    cs:__imp_ExDeleteNPagedLookasideList
0x18005ff69  nop     dword ptr [rax+rax+00h]
0x18005ff6e  mov     rcx, [rbx+40h]
0x18005ff72  test    rcx, rcx
0x18005ff75  jz      short loc_18005FF87
0x18005ff77  mov     rax, [rcx]
0x18005ff7a  mov     rax, [rax+10h]
0x18005ff7e  call    _guard_dispatch_icall
0x18005ff83  mov     [rbx+40h], rsi
0x18005ff87  mov     rcx, [rbx+48h]
0x18005ff8b  test    rcx, rcx
0x18005ff8e  jz      short loc_18005FFA0
0x18005ff90  mov     rax, [rcx]
0x18005ff93  mov     rax, [rax+10h]
0x18005ff97  call    _guard_dispatch_icall
0x18005ff9c  mov     [rbx+48h], rsi
0x18005ffa0  mov     eax, cs:KsXdvExtLevel
0x18005ffa6  test    al, 18h
0x18005ffa8  jz      short loc_18005FFB6
0x18005ffaa  lea     rcx, [rbx+370h]; struct _LIST_ENTRY *
0x18005ffb1  call    ?KspQueueVerifierRemoveEntry@@YAXPEAU_LIST_ENTRY@@@Z; KspQueueVerifierRemoveEntry(_LIST_ENTRY *)
0x18005ffb6  lea     rax, ??_7CBaseUnknown@@6BINonDelegatedUnknown@@@; const CBaseUnknown::`vftable'{for `INonDelegatedUnknown'}
0x18005ffbd  mov     [rbx+10h], rax
0x18005ffc1  lea     rax, ??_7CKsPin@@6BIIndirectedUnknown@@@; const CKsPin::`vftable'{for `IIndirectedUnknown'}
0x18005ffc8  mov     [rbx+18h], rax
0x18005ffcc  add     rsp, 48h
0x18005ffd0  pop     rdi
0x18005ffd1  pop     rsi
0x18005ffd2  pop     rbp
0x18005ffd3  pop     rbx
0x18005ffd4  retn
0x18005ffd6  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ffdd  cmp     [rcx+48h], si
0x18005ffe1  jz      loc_18005FF0A
0x18005ffe7  mov     r8, [rbx+0A8h]
0x18005ffee  mov     r9d, 30h ; '0'
0x18005fff4  mov     rcx, [rcx+40h]
0x18005fff8  mov     dl, 5
0x18005fffa  mov     eax, [r8]
0x18005fffd  mov     [rsp+68h+var_30], eax
0x180060001  mov     [rsp+68h+var_38], r8
0x180060006  mov     [rsp+68h+var_40], rbx
0x18006000b  mov     [rsp+68h+var_48], rbp
0x180060010  call    WPP_RECORDER_SF_qqd
0x180060015  jmp     loc_18005FF0A
0x18006001a  mov     rcx, cs:WPP_GLOBAL_Control
0x180060021  cmp     [rcx+48h], si
0x180060025  jnz     short loc_180060069
0x180060027  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x18006002e  jz      loc_18005FE64
0x180060034  mov     rcx, cs:WPP_GLOBAL_Control
0x18006003b  cmp     [rcx+48h], si
0x18006003f  jz      loc_18005FE64
0x180060045  mov     rcx, [rcx+40h]
0x180060049  mov     r9d, 2Bh ; '+'
0x18006004f  mov     [rsp+68h+var_40], rbx
0x180060054  mov     dl, 5
0x180060056  mov     [rsp+68h+var_48], rbp
0x18006005b  lea     r8d, [r9-2Ah]
0x18006005f  call    WPP_RECORDER_SF_q
0x180060064  jmp     loc_18005FE64
0x180060069  mov     rcx, [rcx+40h]
0x18006006d  mov     r9d, 2Ah ; '*'
0x180060073  mov     [rsp+68h+var_40], rbx
0x180060078  mov     dl, 5
0x18006007a  mov     [rsp+68h+var_48], rbp
0x18006007f  lea     r8d, [r9-29h]
0x180060083  call    WPP_RECORDER_SF_q
0x180060088  jmp     short loc_180060027
0x18006008a  xor     edx, edx; Tag
0x18006008c  call    cs:__imp_ExFreePoolWithTag
0x180060093  nop     dword ptr [rax+rax+00h]
0x180060098  mov     [rbx+258h], rsi
0x18006009f  jmp     loc_18005FEE1
0x1800600a4  cmp     [rbx+0C8h], sil
0x1800600ab  jnz     loc_18005FEFD
0x1800600b1  call    KsGateTurnInputOn
0x1800600b6  jmp     loc_18005FEFD
0x1800600bb  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1800600c2  jz      short loc_1800600EA
0x1800600c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800600cb  mov     r9d, 31h ; '1'
0x1800600d1  mov     [rsp+68h+var_40], rbx
0x1800600d6  mov     dl, 4
0x1800600d8  mov     [rsp+68h+var_48], rbp
0x1800600dd  mov     rcx, [rcx+40h]
0x1800600e1  lea     r8d, [r9-30h]
0x1800600e5  call    WPP_RECORDER_SF_q
0x1800600ea  mov     rcx, [rbx+48h]
0x1800600ee  mov     dl, [rbx+79h]
0x1800600f1  mov     rax, [rcx]
0x1800600f4  mov     rax, [rax+28h]
0x1800600f8  call    _guard_dispatch_icall
0x1800600fd  jmp     loc_18005FF1E
0x180060102  mov     ecx, 3
0x180060107  int     29h; Win8: RtlFailFast(ecx)
```
