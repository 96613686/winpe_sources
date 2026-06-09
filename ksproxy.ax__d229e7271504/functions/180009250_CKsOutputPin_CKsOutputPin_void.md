# CKsOutputPin::~CKsOutputPin(void)

- ea: `0x180009250`
- end: `0x180009629`
- name: `??1CKsOutputPin@@UEAA@XZ`
- size: `985`
- prototype: `void __fastcall(CKsOutputPin *__hidden this)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800091b0`
- `0x18002cd54`

## callees

- `0x180009250`
- `0x180009630`
- `0x180009654`
- `0x180009704`
- `0x180009734`
- `0x1800097e0`
- `0x18000d430`
- `0x180015e84`
- `0x18001cd00`
- `0x18001e720`
- `0x18001f1c4`
- `0x18002b7e0`
- `0x18003a520`
- `0x18003e22c`
- `0x180045010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800094c0`
- `KERNEL32!CloseHandle` at `0x180009545`
- `KERNEL32!CloseHandle` at `0x18000955d`
- `KERNEL32!CloseHandle` at `0x1800094c0`
- `KERNEL32!CloseHandle` at `0x180009545`
- `KERNEL32!CloseHandle` at `0x18000955d`
- `KERNEL32!DeleteCriticalSection` at `0x180009462`
- `KERNEL32!DeleteCriticalSection` at `0x180009462`

## pseudocode

```c
void __fastcall CKsOutputPin::~CKsOutputPin(CKsOutputPin *this)
{
  CBaseStreamControl *v1; // r15
  IKsControl *v3; // rdi
  IKsD3DPin *v4; // r14
  void *m_PendingIoCompletedEvent; // rcx
  void *m_hFlushCompleteEvent; // rcx
  IKsInterfaceHandler *m_InterfaceHandler; // rcx
  struct _AMMediaType *m_ConfigAmMediaType; // rcx
  unsigned int v9; // edx
  IKsAllocatorEx *m_pKsAllocator; // rcx
  IMemAllocator *m_pAllocator; // rcx
  unsigned int v12; // edi
  __int64 v13; // rsi
  KSALLOCATOR_FRAMING_EX *v14; // rcx
  CAsyncItemHandler *m_pAsyncItemHandler; // rcx
  struct CapabilityUsageHelper *ptr; // rcx
  IUnknown *m_UnkInner; // rcx
  unsigned int i; // eax
  unsigned int v19; // [rsp+60h] [rbp+8h] BYREF

  v1 = &this->CBaseStreamControl;
  this->CBaseOutputPin::CBasePin::CUnknown::INonDelegatingUnknown::__vftable = (CKsOutputPin_vtbl *)&CKsOutputPin::`vftable'{for `CUnknown'};
  v3 = &this->IKsControl;
  this->CBaseOutputPin::CBasePin::IPin::IUnknown::__vftable = (IPin_vtbl *)&CKsOutputPin2::`vftable'{for `IPin'};
  v4 = &this->IKsD3DPin;
  this->CBaseOutputPin::CBasePin::IQualityControl::IUnknown::__vftable = (IQualityControl_vtbl *)&CKsOutputPin2::`vftable'{for `IQualityControl'};
  this->CBaseStreamControl::IAMStreamControl::IUnknown::__vftable = (CBaseStreamControl_vtbl *)&CKsOutputPin2::`vftable'{for `CBaseStreamControl'};
  this->IMediaSeeking::IUnknown::__vftable = (IMediaSeeking_vtbl *)&CKsOutputPin::`vftable'{for `IMediaSeeking'};
  this->IKsObject::IUnknown::__vftable = (IKsObject_vtbl *)&CKsOutputPin2::`vftable'{for `IKsObject'};
  this->IKsPinEx::IKsPin::IUnknown::__vftable = (IKsPinEx_vtbl *)&CKsOutputPin::`vftable'{for `IKsPinEx'};
  this->IKsPinPipe::IUnknown::__vftable = (IKsPinPipe_vtbl *)&CKsOutputPin::`vftable'{for `IKsPinPipe'};
  this->ISpecifyPropertyPages::IUnknown::__vftable = (ISpecifyPropertyPages_vtbl *)&CKsOutputPin::`vftable'{for `ISpecifyPropertyPages'};
  this->IStreamBuilder::IUnknown::__vftable = (IStreamBuilder_vtbl *)&CKsOutputPin::`vftable'{for `IStreamBuilder'};
  this->IKsPropertySet::IUnknown::__vftable = (IKsPropertySet_vtbl *)&CKsOutputPin2::`vftable'{for `IKsPropertySet'};
  this->IKsPinFactory::IUnknown::__vftable = (IKsPinFactory_vtbl *)&CKsOutputPin2::`vftable'{for `IKsPinFactory'};
  this->IAMBufferNegotiation::IUnknown::__vftable = (IAMBufferNegotiation_vtbl *)&CKsOutputPin::`vftable'{for `IAMBufferNegotiation'};
  this->IAMStreamConfig::IUnknown::__vftable = (IAMStreamConfig_vtbl *)&CKsOutputPin::`vftable'{for `IAMStreamConfig'};
  this->IKsControl::IUnknown::__vftable = (IKsControl_vtbl *)&CKsOutputPin2::`vftable'{for `IKsControl'};
  this->IKsAggregateControl::IUnknown::__vftable = (IKsAggregateControl_vtbl *)&CKsOutputPin2::`vftable'{for `IKsAggregateControl'};
  this->IMemAllocatorNotifyCallbackTemp::IUnknown::__vftable = (IMemAllocatorNotifyCallbackTemp_vtbl *)&CKsOutputPin::`vftable'{for `IMemAllocatorNotifyCallbackTemp'};
  this->IKsPinPrivate::IUnknown::__vftable = (IKsPinPrivate_vtbl *)&CKsOutputPin2::`vftable'{for `IKsPinPrivate'};
  this->IKsD3DPin::IUnknown::__vftable = (IKsD3DPin_vtbl *)&CKsOutputPin::`vftable'{for `IKsD3DPin'};
  if ( this->m_PinHandle )
  {
    UnloadVolatileInterfaces(&this->m_MarshalerList);
    if ( this->m_hEOSevent )
    {
      v19 = 0;
      CKsOutputPin::KsEvent((CKsOutputPin *)v3, 0, 0, 0, 0, &v19);
      CAsyncItemHandler::RemoveAsyncItem(this->m_pAsyncItemHandler, this->m_hEOSevent);
      this->m_hEOSevent = 0;
    }
    SetSyncSource(this->m_PinHandle, 0);
    CloseHandle(this->m_PinHandle);
    this->m_PinHandle = 0;
  }
  m_PendingIoCompletedEvent = this->m_PendingIoCompletedEvent;
  if ( m_PendingIoCompletedEvent )
  {
    CloseHandle(m_PendingIoCompletedEvent);
    this->m_PendingIoCompletedEvent = 0;
  }
  m_hFlushCompleteEvent = this->m_hFlushCompleteEvent;
  if ( m_hFlushCompleteEvent )
  {
    CloseHandle(m_hFlushCompleteEvent);
    this->m_hFlushCompleteEvent = 0;
  }
  if ( this->m_DataTypeHandler )
  {
    m_UnkInner = this->m_UnkInner;
    this->m_DataTypeHandler = 0;
    if ( m_UnkInner )
    {
      this->m_UnkInner = 0;
      m_UnkInner->Release(m_UnkInner);
    }
  }
  m_InterfaceHandler = this->m_InterfaceHandler;
  if ( m_InterfaceHandler )
    m_InterfaceHandler->Release(m_InterfaceHandler);
  m_ConfigAmMediaType = this->m_ConfigAmMediaType;
  if ( m_ConfigAmMediaType )
    DeleteMediaType(m_ConfigAmMediaType);
  FreeMarshalers(&this->m_MarshalerList);
  m_pKsAllocator = this->m_pKsAllocator;
  if ( m_pKsAllocator )
  {
    this->m_pKsAllocator = 0;
    m_pKsAllocator->Release(m_pKsAllocator);
  }
  m_pAllocator = this->m_pAllocator;
  if ( m_pAllocator )
  {
    this->m_pAllocator = 0;
    m_pAllocator->Release(m_pAllocator);
  }
  v12 = 0;
  v13 = 0;
  do
  {
    v14 = this->m_AllocatorFramingEx[v13];
    ++v12;
    if ( v14 )
    {
      for ( i = v12; i < 3; ++i )
      {
        if ( v14 == this->m_AllocatorFramingEx[i] )
        {
          this->m_AllocatorFramingEx[i] = 0;
          v14 = this->m_AllocatorFramingEx[v13];
        }
      }
      operator delete(v14, 0x70u);
      this->m_AllocatorFramingEx[v13] = 0;
    }
    ++v13;
  }
  while ( v12 < 3 );
  m_pAsyncItemHandler = this->m_pAsyncItemHandler;
  if ( m_pAsyncItemHandler )
  {
    CAsyncItemHandler::`scalar deleting destructor'(m_pAsyncItemHandler, v9);
    this->m_pAsyncItemHandler = 0;
  }
  CKsOutputPin::CloseDirect3DDeviceManager((CKsOutputPin *)v4);
  ptr = this->m_spCapUsageHelper.ptr_;
  if ( ptr )
  {
    this->m_spCapUsageHelper.ptr_ = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(ptr);
  }
  CBaseList::~CBaseList(&this->m_IoThreadQueue);
  DeleteCriticalSection(&this->m_IoCriticalSection.m_CritSec);
  CBaseList::~CBaseList(&this->m_IoQueue);
  CBaseList::~CBaseList(&this->m_MarshalerList);
  CBaseStreamControl::~CBaseStreamControl(v1);
  CBasePin::~CBasePin(this);
}

```

## disassembly

```asm
0x180009250  mov     [rsp+arg_8], rbx
0x180009255  mov     [rsp+arg_10], rbp
0x18000925a  push    rsi
0x18000925b  push    rdi
0x18000925c  push    r12
0x18000925e  push    r14
0x180009260  push    r15
0x180009262  sub     rsp, 30h
0x180009266  lea     rax, ??_7CKsOutputPin@@6BCUnknown@@@; const CKsOutputPin::`vftable'{for `CUnknown'}
0x18000926d  xor     r12d, r12d
0x180009270  lea     r15, [rcx+0E8h]
0x180009277  mov     [rcx], rax
0x18000927a  lea     rax, ??_7CKsOutputPin2@@6BIPin@@@; const CKsOutputPin2::`vftable'{for `IPin'}
0x180009281  mov     rbx, rcx
0x180009284  lea     rdi, [rcx+1C0h]
0x18000928b  mov     [rcx+18h], rax
0x18000928f  lea     rax, ??_7CKsOutputPin2@@6BIQualityControl@@@; const CKsOutputPin2::`vftable'{for `IQualityControl'}
0x180009296  lea     r14, [rcx+1E0h]
0x18000929d  mov     [rcx+20h], rax
0x1800092a1  lea     rax, ??_7CKsOutputPin2@@6BCBaseStreamControl@@@; const CKsOutputPin2::`vftable'{for `CBaseStreamControl'}
0x1800092a8  mov     [r15], rax
0x1800092ab  lea     rax, ??_7CKsOutputPin@@6BIMediaSeeking@@@; const CKsOutputPin::`vftable'{for `IMediaSeeking'}
0x1800092b2  mov     [rcx+170h], rax
0x1800092b9  lea     rax, ??_7CKsOutputPin2@@6BIKsObject@@@; const CKsOutputPin2::`vftable'{for `IKsObject'}
0x1800092c0  mov     [rcx+178h], rax
0x1800092c7  lea     rax, ??_7CKsOutputPin@@6BIKsPinEx@@@; const CKsOutputPin::`vftable'{for `IKsPinEx'}
0x1800092ce  mov     [rcx+180h], rax
0x1800092d5  lea     rax, ??_7CKsOutputPin@@6BIKsPinPipe@@@; const CKsOutputPin::`vftable'{for `IKsPinPipe'}
0x1800092dc  mov     [rcx+188h], rax
0x1800092e3  lea     rax, ??_7CKsOutputPin@@6BISpecifyPropertyPages@@@; const CKsOutputPin::`vftable'{for `ISpecifyPropertyPages'}
0x1800092ea  mov     [rcx+190h], rax
0x1800092f1  lea     rax, ??_7CKsOutputPin@@6BIStreamBuilder@@@; const CKsOutputPin::`vftable'{for `IStreamBuilder'}
0x1800092f8  mov     [rcx+198h], rax
0x1800092ff  lea     rax, ??_7CKsOutputPin2@@6BIKsPropertySet@@@; const CKsOutputPin2::`vftable'{for `IKsPropertySet'}
0x180009306  mov     [rcx+1A0h], rax
0x18000930d  lea     rax, ??_7CKsOutputPin2@@6BIKsPinFactory@@@; const CKsOutputPin2::`vftable'{for `IKsPinFactory'}
0x180009314  mov     [rcx+1A8h], rax
0x18000931b  lea     rax, ??_7CKsOutputPin@@6BIAMBufferNegotiation@@@; const CKsOutputPin::`vftable'{for `IAMBufferNegotiation'}
0x180009322  mov     [rcx+1B0h], rax
0x180009329  lea     rax, ??_7CKsOutputPin@@6BIAMStreamConfig@@@; const CKsOutputPin::`vftable'{for `IAMStreamConfig'}
0x180009330  mov     [rcx+1B8h], rax
0x180009337  lea     rax, ??_7CKsOutputPin2@@6BIKsControl@@@; const CKsOutputPin2::`vftable'{for `IKsControl'}
0x18000933e  mov     [rdi], rax
0x180009341  lea     rax, ??_7CKsOutputPin2@@6BIKsAggregateControl@@@; const CKsOutputPin2::`vftable'{for `IKsAggregateControl'}
0x180009348  mov     [rcx+1C8h], rax
0x18000934f  lea     rax, ??_7CKsOutputPin@@6BIMemAllocatorNotifyCallbackTemp@@@; const CKsOutputPin::`vftable'{for `IMemAllocatorNotifyCallbackTemp'}
0x180009356  mov     [rcx+1D0h], rax
0x18000935d  lea     rax, ??_7CKsOutputPin2@@6BIKsPinPrivate@@@; const CKsOutputPin2::`vftable'{for `IKsPinPrivate'}
0x180009364  mov     [rcx+1D8h], rax
0x18000936b  lea     rax, ??_7CKsOutputPin@@6BIKsD3DPin@@@; const CKsOutputPin::`vftable'{for `IKsD3DPin'}
0x180009372  mov     [r14], rax
0x180009375  cmp     [rcx+208h], r12
0x18000937c  jnz     loc_1800094D8
0x180009382  mov     rcx, [rbx+298h]; hObject
0x180009389  test    rcx, rcx
0x18000938c  jnz     loc_1800094C0
0x180009392  mov     rcx, [rbx+3C0h]; hObject
0x180009399  test    rcx, rcx
0x18000939c  jnz     loc_18000955D
0x1800093a2  cmp     [rbx+230h], r12
0x1800093a9  jnz     loc_180009575
0x1800093af  mov     rcx, [rbx+240h]
0x1800093b6  test    rcx, rcx
0x1800093b9  jnz     loc_1800095A4
0x1800093bf  mov     rcx, [rbx+350h]; pv
0x1800093c6  test    rcx, rcx
0x1800093c9  jnz     loc_1800095B5
0x1800093cf  lea     rbp, [rbx+2A8h]
0x1800093d6  mov     rcx, rbp
0x1800093d9  call    ?FreeMarshalers@@YAXPEAV?$CGenericList@VCAggregateMarshaler@@@@@Z; FreeMarshalers(CGenericList<CAggregateMarshaler> *)
0x1800093de  mov     rcx, [rbx+368h]
0x1800093e5  test    rcx, rcx
0x1800093e8  jnz     loc_1800094A8
0x1800093ee  mov     rcx, [rbx+0D8h]
0x1800093f5  test    rcx, rcx
0x1800093f8  jnz     loc_1800095BF
0x1800093fe  mov     edi, r12d
0x180009401  mov     rsi, r12
0x180009404  mov     rcx, [rbx+rsi*8+370h]
0x18000940c  inc     edi
0x18000940e  test    rcx, rcx
0x180009411  jnz     loc_1800095D7
0x180009417  inc     rsi
0x18000941a  cmp     edi, 3
0x18000941d  jb      short loc_180009404
0x18000941f  mov     rcx, [rbx+3D8h]; this
0x180009426  test    rcx, rcx
0x180009429  jnz     loc_180009618
0x18000942f  mov     rcx, r14; this
0x180009432  call    ?CloseDirect3DDeviceManager@CKsOutputPin@@UEAAJXZ; CKsOutputPin::CloseDirect3DDeviceManager(void)
0x180009437  mov     rcx, [rbx+410h]
0x18000943e  test    rcx, rcx
0x180009441  jz      short loc_18000944F
0x180009443  mov     [rbx+410h], r12
0x18000944a  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18000944f  lea     rcx, [rbx+320h]; this
0x180009456  call    ??1CBaseList@@QEAA@XZ; CBaseList::~CBaseList(void)
0x18000945b  lea     rcx, [rbx+2F8h]; lpCriticalSection
0x180009462  call    cs:__imp_DeleteCriticalSection
0x180009469  nop     dword ptr [rax+rax+00h]
0x18000946e  lea     rcx, [rbx+2D0h]; this
0x180009475  call    ??1CBaseList@@QEAA@XZ; CBaseList::~CBaseList(void)
0x18000947a  mov     rcx, rbp; this
0x18000947d  call    ??1CBaseList@@QEAA@XZ; CBaseList::~CBaseList(void)
0x180009482  mov     rcx, r15; this
0x180009485  call    ??1CBaseStreamControl@@QEAA@XZ; CBaseStreamControl::~CBaseStreamControl(void)
0x18000948a  mov     rcx, rbx; this
0x18000948d  mov     rbx, [rsp+58h+arg_8]
0x180009492  mov     rbp, [rsp+58h+arg_10]
0x180009497  add     rsp, 30h
0x18000949b  pop     r15
0x18000949d  pop     r14
0x18000949f  pop     r12
0x1800094a1  pop     rdi
0x1800094a2  pop     rsi
0x1800094a3  jmp     ??1CBasePin@@UEAA@XZ; CBasePin::~CBasePin(void)
0x1800094a8  mov     [rbx+368h], r12
0x1800094af  mov     rax, [rcx]
0x1800094b2  mov     rax, [rax+10h]
0x1800094b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094bb  jmp     loc_1800093EE
0x1800094c0  call    cs:__imp_CloseHandle
0x1800094c7  nop     dword ptr [rax+rax+00h]
0x1800094cc  mov     [rbx+298h], r12
0x1800094d3  jmp     loc_180009392
0x1800094d8  add     rcx, 2A8h; this
0x1800094df  mov     edx, 1
0x1800094e4  call    ?UnloadVolatileInterfaces@@YAXPEAV?$CGenericList@VCAggregateMarshaler@@@@H@Z; UnloadVolatileInterfaces(CGenericList<CAggregateMarshaler> *,int)
0x1800094e9  cmp     [rbx+3C8h], r12
0x1800094f0  jz      short loc_180009530
0x1800094f2  lea     rax, [rsp+58h+arg_0]
0x1800094f7  mov     [rsp+58h+arg_0], r12d
0x1800094fc  mov     [rsp+58h+var_30], rax; unsigned int *
0x180009501  xor     r9d, r9d; void *
0x180009504  xor     r8d, r8d; unsigned int
0x180009507  mov     [rsp+58h+var_38], r12d; unsigned int
0x18000950c  xor     edx, edx; struct KSIDENTIFIER *
0x18000950e  mov     rcx, rdi; this
0x180009511  call    ?KsEvent@CKsOutputPin@@UEAAJPEAUKSIDENTIFIER@@KPEAXKPEAK@Z; CKsOutputPin::KsEvent(KSIDENTIFIER *,ulong,void *,ulong,ulong *)
0x180009516  mov     rdx, [rbx+3C8h]; void *
0x18000951d  mov     rcx, [rbx+3D8h]; this
0x180009524  call    ?RemoveAsyncItem@CAsyncItemHandler@@QEAAXPEAX@Z; CAsyncItemHandler::RemoveAsyncItem(void *)
0x180009529  mov     [rbx+3C8h], r12
0x180009530  mov     rcx, [rbx+208h]; void *
0x180009537  xor     edx, edx; void *
0x180009539  call    ?SetSyncSource@@YAJPEAX0@Z; SetSyncSource(void *,void *)
0x18000953e  mov     rcx, [rbx+208h]; hObject
0x180009545  call    cs:__imp_CloseHandle
0x18000954c  nop     dword ptr [rax+rax+00h]
0x180009551  mov     [rbx+208h], r12
0x180009558  jmp     loc_180009382
0x18000955d  call    cs:__imp_CloseHandle
0x180009564  nop     dword ptr [rax+rax+00h]
0x180009569  mov     [rbx+3C0h], r12
0x180009570  jmp     loc_1800093A2
0x180009575  mov     rcx, [rbx+238h]
0x18000957c  mov     [rbx+230h], r12
0x180009583  test    rcx, rcx
0x180009586  jz      loc_1800093AF
0x18000958c  mov     [rbx+238h], r12
0x180009593  mov     rax, [rcx]
0x180009596  mov     rax, [rax+10h]
0x18000959a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000959f  jmp     loc_1800093AF
0x1800095a4  mov     rax, [rcx]
0x1800095a7  mov     rax, [rax+10h]
0x1800095ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095b0  jmp     loc_1800093BF
0x1800095b5  call    ?DeleteMediaType@@YAXPEAU_AMMediaType@@@Z; DeleteMediaType(_AMMediaType *)
0x1800095ba  jmp     loc_1800093CF
0x1800095bf  mov     [rbx+0D8h], r12
0x1800095c6  mov     rax, [rcx]
0x1800095c9  mov     rax, [rax+10h]
0x1800095cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095d2  jmp     loc_1800093FE
0x1800095d7  mov     eax, edi
0x1800095d9  cmp     edi, 3
0x1800095dc  jnb     short loc_180009601
0x1800095de  mov     edx, eax
0x1800095e0  cmp     rcx, [rbx+rdx*8+370h]
0x1800095e8  jnz     short loc_1800095FA
0x1800095ea  mov     [rbx+rdx*8+370h], r12
0x1800095f2  mov     rcx, [rbx+rsi*8+370h]; void *
0x1800095fa  inc     eax
0x1800095fc  cmp     eax, 3
0x1800095ff  jb      short loc_1800095DE
0x180009601  mov     edx, 70h ; 'p'; unsigned __int64
0x180009606  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000960b  mov     [rbx+rsi*8+370h], r12
0x180009613  jmp     loc_180009417
0x180009618  call    ??_GCAsyncItemHandler@@QEAAPEAXI@Z; CAsyncItemHandler::`scalar deleting destructor'(uint)
0x18000961d  mov     [rbx+3D8h], r12
0x180009624  jmp     loc_18000942F
```
