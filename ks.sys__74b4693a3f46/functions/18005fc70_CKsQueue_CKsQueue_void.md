# CKsQueue::~CKsQueue(void)

- ea: `0x18005fc70`
- end: `0x18005ff69`
- name: `??1CKsQueue@@UEAA@XZ`
- size: `761`
- prototype: `void __fastcall(CKsQueue *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18005fc38`

## callees

- `0x180005a00`
- `0x180005a40`
- `0x18000aa80`
- `0x18000dddc`
- `0x18000fe2c`
- `0x180016080`
- `0x180019c60`
- `0x18005fc70`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18005fd1e`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005fdad`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005feec`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005fd1e`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005fdad`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005feec`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x18005fdc2`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x18005fdc2`

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
        (__int64)WPP_c705d9135b58358f87ecf40b472c5dce_Traceguids,
        (char)this);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      WPP_RECORDER_SF_q(
        WPP_GLOBAL_Control->DeviceExtension,
        5,
        1,
        43,
        (__int64)WPP_c705d9135b58358f87ecf40b472c5dce_Traceguids,
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
      (__int64)WPP_c705d9135b58358f87ecf40b472c5dce_Traceguids,
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
        (__int64)WPP_c705d9135b58358f87ecf40b472c5dce_Traceguids,
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
0x18005fc70  push    rbx
0x18005fc72  push    rbp
0x18005fc73  push    rsi
0x18005fc74  push    rdi
0x18005fc75  sub     rsp, 48h
0x18005fc79  lea     rax, ??_7CKsQueue@@6BIKsQueue@@@; const CKsQueue::`vftable'{for `IKsQueue'}
0x18005fc80  mov     rbx, rcx
0x18005fc83  mov     [rcx], rax
0x18005fc86  lea     rax, ??_7CKsQueue@@6BIKsMdlCache@@@; const CKsQueue::`vftable'{for `IKsMdlCache'}
0x18005fc8d  mov     [rcx+8], rax
0x18005fc91  lea     rax, ??_7CKsQueue@@6BINonDelegatedUnknown@@@; const CKsQueue::`vftable'{for `INonDelegatedUnknown'}
0x18005fc98  mov     [rcx+10h], rax
0x18005fc9c  lea     rax, ??_7CKsPin@@6BIIndirectedUnknown@@@; const CKsPin::`vftable'{for `IIndirectedUnknown'}
0x18005fca3  mov     [rcx+18h], rax
0x18005fca7  lea     rdi, WPP_RECORDER_INITIALIZED
0x18005fcae  xor     esi, esi
0x18005fcb0  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x18005fcb7  lea     rbp, WPP_c705d9135b58358f87ecf40b472c5dce_Traceguids
0x18005fcbe  jnz     loc_18005FE7A
0x18005fcc4  mov     rcx, [rbx+248h]
0x18005fccb  test    rcx, rcx
0x18005fcce  jz      short loc_18005FCE3
0x18005fcd0  mov     rax, [rcx]
0x18005fcd3  mov     rax, [rax+10h]
0x18005fcd7  call    _guard_dispatch_icall
0x18005fcdc  mov     [rbx+248h], rsi
0x18005fce3  mov     rcx, [rbx+40h]
0x18005fce7  test    rcx, rcx
0x18005fcea  jz      short loc_18005FCF8
0x18005fcec  mov     rax, [rcx]
0x18005fcef  mov     rax, [rax+40h]
0x18005fcf3  call    _guard_dispatch_icall
0x18005fcf8  mov     rcx, [rbx+360h]; Worker
0x18005fcff  test    rcx, rcx
0x18005fd02  jz      short loc_18005FD10
0x18005fd04  call    KsUnregisterWorker
0x18005fd09  mov     [rbx+360h], rsi
0x18005fd10  mov     rcx, [rbx+250h]; P
0x18005fd17  test    rcx, rcx
0x18005fd1a  jz      short loc_18005FD31
0x18005fd1c  xor     edx, edx; Tag
0x18005fd1e  call    cs:__imp_ExFreePoolWithTag
0x18005fd25  nop     dword ptr [rax+rax+00h]
0x18005fd2a  mov     [rbx+250h], rsi
0x18005fd31  mov     rcx, [rbx+258h]; P
0x18005fd38  test    rcx, rcx
0x18005fd3b  jnz     loc_18005FEEA
0x18005fd41  mov     rcx, [rbx+0A8h]; Gate
0x18005fd48  call    KsGateTurnInputOn
0x18005fd4d  mov     rcx, [rbx+0C0h]; Gate
0x18005fd54  test    rcx, rcx
0x18005fd57  jnz     loc_18005FF04
0x18005fd5d  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x18005fd64  jnz     loc_18005FE36
0x18005fd6a  mov     rcx, [rbx+0A8h]; Gate
0x18005fd71  call    KsGateCaptureThreshold
0x18005fd76  test    al, al
0x18005fd78  jnz     loc_18005FF1B
0x18005fd7e  lea     rdi, [rbx+148h]
0x18005fd85  mov     rcx, [rdi]; P
0x18005fd88  cmp     rcx, rdi
0x18005fd8b  jz      short loc_18005FDBB
0x18005fd8d  cmp     [rcx+8], rdi
0x18005fd91  jnz     loc_18005FF62
0x18005fd97  mov     rax, [rcx]
0x18005fd9a  cmp     [rax+8], rcx
0x18005fd9e  jnz     loc_18005FF62
0x18005fda4  mov     [rdi], rax
0x18005fda7  xor     edx, edx; Tag
0x18005fda9  mov     [rax+8], rdi
0x18005fdad  call    cs:__imp_ExFreePoolWithTag
0x18005fdb4  nop     dword ptr [rax+rax+00h]
0x18005fdb9  jmp     short loc_18005FD85
0x18005fdbb  lea     rcx, [rbx+2C0h]; Lookaside
0x18005fdc2  call    cs:__imp_ExDeleteNPagedLookasideList
0x18005fdc9  nop     dword ptr [rax+rax+00h]
0x18005fdce  mov     rcx, [rbx+40h]
0x18005fdd2  test    rcx, rcx
0x18005fdd5  jz      short loc_18005FDE7
0x18005fdd7  mov     rax, [rcx]
0x18005fdda  mov     rax, [rax+10h]
0x18005fdde  call    _guard_dispatch_icall
0x18005fde3  mov     [rbx+40h], rsi
0x18005fde7  mov     rcx, [rbx+48h]
0x18005fdeb  test    rcx, rcx
0x18005fdee  jz      short loc_18005FE00
0x18005fdf0  mov     rax, [rcx]
0x18005fdf3  mov     rax, [rax+10h]
0x18005fdf7  call    _guard_dispatch_icall
0x18005fdfc  mov     [rbx+48h], rsi
0x18005fe00  mov     eax, cs:KsXdvExtLevel
0x18005fe06  test    al, 18h
0x18005fe08  jz      short loc_18005FE16
0x18005fe0a  lea     rcx, [rbx+370h]; struct _LIST_ENTRY *
0x18005fe11  call    ?KspQueueVerifierRemoveEntry@@YAXPEAU_LIST_ENTRY@@@Z; KspQueueVerifierRemoveEntry(_LIST_ENTRY *)
0x18005fe16  lea     rax, ??_7CBaseUnknown@@6BINonDelegatedUnknown@@@; const CBaseUnknown::`vftable'{for `INonDelegatedUnknown'}
0x18005fe1d  mov     [rbx+10h], rax
0x18005fe21  lea     rax, ??_7CKsPin@@6BIIndirectedUnknown@@@; const CKsPin::`vftable'{for `IIndirectedUnknown'}
0x18005fe28  mov     [rbx+18h], rax
0x18005fe2c  add     rsp, 48h
0x18005fe30  pop     rdi
0x18005fe31  pop     rsi
0x18005fe32  pop     rbp
0x18005fe33  pop     rbx
0x18005fe34  retn
0x18005fe36  mov     rcx, cs:WPP_GLOBAL_Control
0x18005fe3d  cmp     [rcx+48h], si
0x18005fe41  jz      loc_18005FD6A
0x18005fe47  mov     r8, [rbx+0A8h]
0x18005fe4e  mov     r9d, 30h ; '0'
0x18005fe54  mov     rcx, [rcx+40h]
0x18005fe58  mov     dl, 5
0x18005fe5a  mov     eax, [r8]
0x18005fe5d  mov     [rsp+68h+var_30], eax
0x18005fe61  mov     [rsp+68h+var_38], r8
0x18005fe66  mov     [rsp+68h+var_40], rbx
0x18005fe6b  mov     [rsp+68h+var_48], rbp
0x18005fe70  call    WPP_RECORDER_SF_qqd
0x18005fe75  jmp     loc_18005FD6A
0x18005fe7a  mov     rcx, cs:WPP_GLOBAL_Control
0x18005fe81  cmp     [rcx+48h], si
0x18005fe85  jnz     short loc_18005FEC9
0x18005fe87  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x18005fe8e  jz      loc_18005FCC4
0x18005fe94  mov     rcx, cs:WPP_GLOBAL_Control
0x18005fe9b  cmp     [rcx+48h], si
0x18005fe9f  jz      loc_18005FCC4
0x18005fea5  mov     rcx, [rcx+40h]
0x18005fea9  mov     r9d, 2Bh ; '+'
0x18005feaf  mov     [rsp+68h+var_40], rbx
0x18005feb4  mov     dl, 5
0x18005feb6  mov     [rsp+68h+var_48], rbp
0x18005febb  lea     r8d, [r9-2Ah]
0x18005febf  call    WPP_RECORDER_SF_q
0x18005fec4  jmp     loc_18005FCC4
0x18005fec9  mov     rcx, [rcx+40h]
0x18005fecd  mov     r9d, 2Ah ; '*'
0x18005fed3  mov     [rsp+68h+var_40], rbx
0x18005fed8  mov     dl, 5
0x18005feda  mov     [rsp+68h+var_48], rbp
0x18005fedf  lea     r8d, [r9-29h]
0x18005fee3  call    WPP_RECORDER_SF_q
0x18005fee8  jmp     short loc_18005FE87
0x18005feea  xor     edx, edx; Tag
0x18005feec  call    cs:__imp_ExFreePoolWithTag
0x18005fef3  nop     dword ptr [rax+rax+00h]
0x18005fef8  mov     [rbx+258h], rsi
0x18005feff  jmp     loc_18005FD41
0x18005ff04  cmp     [rbx+0C8h], sil
0x18005ff0b  jnz     loc_18005FD5D
0x18005ff11  call    KsGateTurnInputOn
0x18005ff16  jmp     loc_18005FD5D
0x18005ff1b  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x18005ff22  jz      short loc_18005FF4A
0x18005ff24  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ff2b  mov     r9d, 31h ; '1'
0x18005ff31  mov     [rsp+68h+var_40], rbx
0x18005ff36  mov     dl, 4
0x18005ff38  mov     [rsp+68h+var_48], rbp
0x18005ff3d  mov     rcx, [rcx+40h]
0x18005ff41  lea     r8d, [r9-30h]
0x18005ff45  call    WPP_RECORDER_SF_q
0x18005ff4a  mov     rcx, [rbx+48h]
0x18005ff4e  mov     dl, [rbx+79h]
0x18005ff51  mov     rax, [rcx]
0x18005ff54  mov     rax, [rax+28h]
0x18005ff58  call    _guard_dispatch_icall
0x18005ff5d  jmp     loc_18005FD7E
0x18005ff62  mov     ecx, 3
0x18005ff67  int     29h; Win8: RtlFailFast(ecx)
```
