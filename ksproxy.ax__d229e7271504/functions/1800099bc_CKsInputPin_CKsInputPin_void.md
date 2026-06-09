# CKsInputPin::~CKsInputPin(void)

- ea: `0x1800099bc`
- end: `0x180009c45`
- name: `??1CKsInputPin@@UEAA@XZ`
- size: `649`
- prototype: `void __fastcall(CKsInputPin *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180009980`

## callees

- `0x180009630`
- `0x180009654`
- `0x1800099bc`
- `0x180009d04`
- `0x18000d430`
- `0x180015e84`
- `0x18001f1c4`
- `0x180024eb8`
- `0x180036b7c`
- `0x180045010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180009af9`
- `KERNEL32!CloseHandle` at `0x180009b18`
- `KERNEL32!CloseHandle` at `0x180009af9`
- `KERNEL32!CloseHandle` at `0x180009b18`
- `KERNEL32!DeleteCriticalSection` at `0x180009c27`
- `KERNEL32!DeleteCriticalSection` at `0x180009c27`

## pseudocode

```c
void __fastcall CKsInputPin::~CKsInputPin(CKsInputPin *this)
{
  IKsPinEx *v1; // rsi
  void *m_PinHandle; // rdx
  void *m_PendingIoCompletedEvent; // rcx
  IUnknown *m_UnkInner; // rcx
  IKsInterfaceHandler *m_InterfaceHandler; // rcx
  IKsAllocatorEx *m_pKsAllocator; // rcx
  IMemAllocator *m_pAllocator; // rcx
  unsigned int v9; // edi
  __int64 v10; // rsi
  KSALLOCATOR_FRAMING_EX *v11; // rcx
  unsigned int i; // eax

  v1 = &this->IKsPinEx;
  this->CBaseInputPin::CBasePin::CUnknown::INonDelegatingUnknown::__vftable = (CKsInputPin_vtbl *)&CKsInputPin::`vftable'{for `CUnknown'};
  this->CBaseInputPin::CBasePin::IPin::IUnknown::__vftable = (IPin_vtbl *)&CKsInputPin::`vftable'{for `IPin'};
  this->CBaseInputPin::CBasePin::IQualityControl::IUnknown::__vftable = (IQualityControl_vtbl *)&CKsInputPin::`vftable'{for `IQualityControl'};
  this->CBaseInputPin::IMemInputPin::IUnknown::__vftable = (IMemInputPin_vtbl *)&CKsInputPin::`vftable'{for `CBaseInputPin'};
  this->IKsObject::IUnknown::__vftable = (IKsObject_vtbl *)&CKsInputPin::`vftable'{for `IKsObject'};
  this->IKsPinEx::IKsPin::IUnknown::__vftable = (IKsPinEx_vtbl *)&CKsInputPin::`vftable'{for `IKsPinEx'};
  this->IKsPinPipe::IUnknown::__vftable = (IKsPinPipe_vtbl *)&CKsInputPin::`vftable'{for `IKsPinPipe'};
  this->ISpecifyPropertyPages::IUnknown::__vftable = (ISpecifyPropertyPages_vtbl *)&CKsInputPin::`vftable'{for `ISpecifyPropertyPages'};
  this->IStreamBuilder::IUnknown::__vftable = (IStreamBuilder_vtbl *)&CKsInputPin::`vftable'{for `IStreamBuilder'};
  this->IKsPropertySet::IUnknown::__vftable = (IKsPropertySet_vtbl *)&CKsInputPin::`vftable'{for `IKsPropertySet'};
  this->IKsPinFactory::IUnknown::__vftable = (IKsPinFactory_vtbl *)&CKsInputPin::`vftable'{for `IKsPinFactory'};
  this->IKsControl::IUnknown::__vftable = (IKsControl_vtbl *)&CKsInputPin::`vftable'{for `IKsControl'};
  this->IKsAggregateControl::IUnknown::__vftable = (IKsAggregateControl_vtbl *)&CKsInputPin::`vftable'{for `IKsAggregateControl'};
  if ( this->m_PinHandle )
  {
    UnloadVolatileInterfaces(&this->m_MarshalerList);
    if ( this->m_QualitySupport )
    {
      m_PinHandle = this->m_PinHandle;
      this->m_QualitySupport = 0;
      EstablishQualitySupport(0, m_PinHandle, 0);
      ((void (__fastcall *)(IUnknown *const, IKsPinEx *))this->m_pFilter[4].m_pUnknown->CUnknown::__vftable[1].AddRef)(
        this->m_pFilter[4].m_pUnknown,
        v1);
    }
    CKsProxy::TerminateEndOfStreamNotification((CKsProxy *)this->m_pFilter, this->m_PinHandle);
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
  FreeMarshalers((__int64)&this->m_MarshalerList);
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
  v9 = 0;
  v10 = 0;
  do
  {
    v11 = this->m_AllocatorFramingEx[v10];
    ++v9;
    if ( v11 )
    {
      for ( i = v9; i < 3; ++i )
      {
        if ( v11 == this->m_AllocatorFramingEx[i] )
        {
          this->m_AllocatorFramingEx[i] = 0;
          v11 = this->m_AllocatorFramingEx[v10];
        }
      }
      operator delete(v11, 0x70u);
      this->m_AllocatorFramingEx[v10] = 0;
    }
    ++v10;
  }
  while ( v9 < 3 );
  CBaseList::~CBaseList(&this->m_MarshalerList);
  DeleteCriticalSection(&this->m_IoCriticalSection.m_CritSec);
  CBaseInputPin::~CBaseInputPin(this);
}

```

## disassembly

```asm
0x1800099bc  push    rbx
0x1800099be  push    rbp
0x1800099bf  push    rsi
0x1800099c0  push    rdi
0x1800099c1  push    r14
0x1800099c3  sub     rsp, 20h
0x1800099c7  lea     rax, ??_7CKsInputPin@@6BCUnknown@@@; const CKsInputPin::`vftable'{for `CUnknown'}
0x1800099ce  xor     r14d, r14d
0x1800099d1  lea     rsi, [rcx+138h]
0x1800099d8  mov     [rcx], rax
0x1800099db  lea     rax, ??_7CKsInputPin@@6BIPin@@@; const CKsInputPin::`vftable'{for `IPin'}
0x1800099e2  mov     rbx, rcx
0x1800099e5  mov     [rcx+18h], rax
0x1800099e9  lea     rax, ??_7CKsInputPin@@6BIQualityControl@@@; const CKsInputPin::`vftable'{for `IQualityControl'}
0x1800099f0  mov     [rcx+20h], rax
0x1800099f4  lea     rax, ??_7CKsInputPin@@6BCBaseInputPin@@@; const CKsInputPin::`vftable'{for `CBaseInputPin'}
0x1800099fb  mov     [rcx+0D8h], rax
0x180009a02  lea     rax, ??_7CKsInputPin@@6BIKsObject@@@; const CKsInputPin::`vftable'{for `IKsObject'}
0x180009a09  mov     [rcx+130h], rax
0x180009a10  lea     rax, ??_7CKsInputPin@@6BIKsPinEx@@@; const CKsInputPin::`vftable'{for `IKsPinEx'}
0x180009a17  mov     [rsi], rax
0x180009a1a  lea     rax, ??_7CKsInputPin@@6BIKsPinPipe@@@; const CKsInputPin::`vftable'{for `IKsPinPipe'}
0x180009a21  mov     [rcx+140h], rax
0x180009a28  lea     rax, ??_7CKsInputPin@@6BISpecifyPropertyPages@@@; const CKsInputPin::`vftable'{for `ISpecifyPropertyPages'}
0x180009a2f  mov     [rcx+148h], rax
0x180009a36  lea     rax, ??_7CKsInputPin@@6BIStreamBuilder@@@; const CKsInputPin::`vftable'{for `IStreamBuilder'}
0x180009a3d  mov     [rcx+150h], rax
0x180009a44  lea     rax, ??_7CKsInputPin@@6BIKsPropertySet@@@; const CKsInputPin::`vftable'{for `IKsPropertySet'}
0x180009a4b  mov     [rcx+158h], rax
0x180009a52  lea     rax, ??_7CKsInputPin@@6BIKsPinFactory@@@; const CKsInputPin::`vftable'{for `IKsPinFactory'}
0x180009a59  mov     [rcx+160h], rax
0x180009a60  lea     rax, ??_7CKsInputPin@@6BIKsControl@@@; const CKsInputPin::`vftable'{for `IKsControl'}
0x180009a67  mov     [rcx+168h], rax
0x180009a6e  lea     rax, ??_7CKsInputPin@@6BIKsAggregateControl@@@; const CKsInputPin::`vftable'{for `IKsAggregateControl'}
0x180009a75  mov     [rcx+170h], rax
0x180009a7c  cmp     [rcx+178h], r14
0x180009a83  jz      loc_180009B0C
0x180009a89  add     rcx, 218h; this
0x180009a90  lea     edx, [r14+1]
0x180009a94  call    ?UnloadVolatileInterfaces@@YAXPEAV?$CGenericList@VCAggregateMarshaler@@@@H@Z; UnloadVolatileInterfaces(CGenericList<CAggregateMarshaler> *,int)
0x180009a99  cmp     [rbx+240h], r14d
0x180009aa0  jz      short loc_180009AD4
0x180009aa2  mov     rdx, [rbx+178h]; void *
0x180009aa9  xor     r8d, r8d; struct CKsProxy *
0x180009aac  xor     ecx, ecx; struct IKsPin *
0x180009aae  mov     [rbx+240h], r14d
0x180009ab5  call    ?EstablishQualitySupport@@YAHPEAUIKsPin@@PEAXPEAVCKsProxy@@@Z; EstablishQualitySupport(IKsPin *,void *,CKsProxy *)
0x180009aba  mov     rax, [rbx+50h]
0x180009abe  mov     rdx, rsi
0x180009ac1  mov     rcx, [rax+1E8h]
0x180009ac8  mov     rax, [rcx]
0x180009acb  mov     rax, [rax+20h]
0x180009acf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ad4  mov     rdx, [rbx+178h]; void *
0x180009adb  mov     rcx, [rbx+50h]; this
0x180009adf  call    ?TerminateEndOfStreamNotification@CKsProxy@@QEAAXPEAX@Z; CKsProxy::TerminateEndOfStreamNotification(void *)
0x180009ae4  mov     rcx, [rbx+178h]; void *
0x180009aeb  xor     edx, edx; void *
0x180009aed  call    ?SetSyncSource@@YAJPEAX0@Z; SetSyncSource(void *,void *)
0x180009af2  mov     rcx, [rbx+178h]; hObject
0x180009af9  call    cs:__imp_CloseHandle
0x180009b00  nop     dword ptr [rax+rax+00h]
0x180009b05  mov     [rbx+178h], r14
0x180009b0c  mov     rcx, [rbx+1E8h]; hObject
0x180009b13  test    rcx, rcx
0x180009b16  jz      short loc_180009B2B
0x180009b18  call    cs:__imp_CloseHandle
0x180009b1f  nop     dword ptr [rax+rax+00h]
0x180009b24  mov     [rbx+1E8h], r14
0x180009b2b  cmp     [rbx+180h], r14
0x180009b32  jz      short loc_180009B5A
0x180009b34  mov     rcx, [rbx+188h]
0x180009b3b  mov     [rbx+180h], r14
0x180009b42  test    rcx, rcx
0x180009b45  jz      short loc_180009B5A
0x180009b47  mov     [rbx+188h], r14
0x180009b4e  mov     rax, [rcx]
0x180009b51  mov     rax, [rax+10h]
0x180009b55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b5a  mov     rcx, [rbx+190h]
0x180009b61  test    rcx, rcx
0x180009b64  jz      short loc_180009B72
0x180009b66  mov     rax, [rcx]
0x180009b69  mov     rax, [rax+10h]
0x180009b6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b72  lea     rbp, [rbx+218h]
0x180009b79  mov     rcx, rbp
0x180009b7c  call    ?FreeMarshalers@@YAXPEAV?$CGenericList@VCAggregateMarshaler@@@@@Z; FreeMarshalers(CGenericList<CAggregateMarshaler> *)
0x180009b81  mov     rcx, [rbx+250h]
0x180009b88  test    rcx, rcx
0x180009b8b  jz      short loc_180009BA0
0x180009b8d  mov     [rbx+250h], r14
0x180009b94  mov     rax, [rcx]
0x180009b97  mov     rax, [rax+10h]
0x180009b9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ba0  mov     rcx, [rbx+0E0h]
0x180009ba7  test    rcx, rcx
0x180009baa  jz      short loc_180009BBF
0x180009bac  mov     [rbx+0E0h], r14
0x180009bb3  mov     rax, [rcx]
0x180009bb6  mov     rax, [rax+10h]
0x180009bba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bbf  mov     edi, r14d
0x180009bc2  mov     rsi, r14
0x180009bc5  mov     rcx, [rbx+rsi*8+258h]
0x180009bcd  inc     edi
0x180009bcf  test    rcx, rcx
0x180009bd2  jz      short loc_180009C10
0x180009bd4  mov     eax, edi
0x180009bd6  cmp     edi, 3
0x180009bd9  jnb     short loc_180009BFE
0x180009bdb  mov     edx, eax
0x180009bdd  cmp     rcx, [rbx+rdx*8+258h]
0x180009be5  jnz     short loc_180009BF7
0x180009be7  mov     [rbx+rdx*8+258h], r14
0x180009bef  mov     rcx, [rbx+rsi*8+258h]; void *
0x180009bf7  inc     eax
0x180009bf9  cmp     eax, 3
0x180009bfc  jb      short loc_180009BDB
0x180009bfe  mov     edx, 70h ; 'p'; unsigned __int64
0x180009c03  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009c08  mov     [rbx+rsi*8+258h], r14
0x180009c10  inc     rsi
0x180009c13  cmp     edi, 3
0x180009c16  jb      short loc_180009BC5
0x180009c18  mov     rcx, rbp; this
0x180009c1b  call    ??1CBaseList@@QEAA@XZ; CBaseList::~CBaseList(void)
0x180009c20  lea     rcx, [rbx+1F0h]; lpCriticalSection
0x180009c27  call    cs:__imp_DeleteCriticalSection
0x180009c2e  nop     dword ptr [rax+rax+00h]
0x180009c33  mov     rcx, rbx; this
0x180009c36  add     rsp, 20h
0x180009c3a  pop     r14
0x180009c3c  pop     rdi
0x180009c3d  pop     rsi
0x180009c3e  pop     rbp
0x180009c3f  pop     rbx
0x180009c40  jmp     ??1CBaseInputPin@@UEAA@XZ; CBaseInputPin::~CBaseInputPin(void)
```
