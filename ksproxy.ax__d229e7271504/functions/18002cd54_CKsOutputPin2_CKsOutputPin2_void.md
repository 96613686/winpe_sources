# CKsOutputPin2::~CKsOutputPin2(void)

- ea: `0x18002cd54`
- end: `0x18002cf2b`
- name: `??1CKsOutputPin2@@UEAA@XZ`
- size: `471`
- prototype: `void __fastcall(CKsOutputPin *this, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18002cf40`

## callees

- `0x180009250`
- `0x180009630`
- `0x18001e720`
- `0x18002cd54`
- `0x18002f2b8`
- `0x180031cc8`
- `0x180045010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18002cea8`
- `KERNEL32!CloseHandle` at `0x18002cea8`
- `ole32!CoTaskMemFree` at `0x18002cecb`
- `ole32!CoTaskMemFree` at `0x18002ceee`
- `ole32!CoTaskMemFree` at `0x18002cecb`
- `ole32!CoTaskMemFree` at `0x18002ceee`

## pseudocode

```c
void __fastcall CKsOutputPin2::~CKsOutputPin2(CKsOutputPin *this, unsigned __int64 a2)
{
  CBaseFilter *m_pFilter; // rcx
  CCritSec *m_pLock; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx

  this->CBaseOutputPin::CBasePin::CUnknown::INonDelegatingUnknown::__vftable = (CKsOutputPin_vtbl *)&CKsOutputPin2::`vftable'{for `CUnknown'};
  this->CBaseOutputPin::CBasePin::IPin::IUnknown::__vftable = (IPin_vtbl *)&CKsOutputPin2::`vftable'{for `IPin'};
  this->CBaseOutputPin::CBasePin::IQualityControl::IUnknown::__vftable = (IQualityControl_vtbl *)&CKsOutputPin2::`vftable'{for `IQualityControl'};
  this->CBaseStreamControl::IAMStreamControl::IUnknown::__vftable = (CBaseStreamControl_vtbl *)&CKsOutputPin2::`vftable'{for `CBaseStreamControl'};
  this->IMediaSeeking::IUnknown::__vftable = (IMediaSeeking_vtbl *)&CKsOutputPin::`vftable'{for `IMediaSeeking'};
  this->IKsObject::IUnknown::__vftable = (IKsObject_vtbl *)&CKsOutputPin2::`vftable'{for `IKsObject'};
  this->IKsPinEx::IKsPin::IUnknown::__vftable = (IKsPinEx_vtbl *)&CKsOutputPin2::`vftable'{for `IKsPinEx'};
  this->IKsPinPipe::IUnknown::__vftable = (IKsPinPipe_vtbl *)&CKsOutputPin::`vftable'{for `IKsPinPipe'};
  this->ISpecifyPropertyPages::IUnknown::__vftable = (ISpecifyPropertyPages_vtbl *)&CKsOutputPin::`vftable'{for `ISpecifyPropertyPages'};
  this->IStreamBuilder::IUnknown::__vftable = (IStreamBuilder_vtbl *)&CKsOutputPin::`vftable'{for `IStreamBuilder'};
  this->IKsPropertySet::IUnknown::__vftable = (IKsPropertySet_vtbl *)&CKsOutputPin2::`vftable'{for `IKsPropertySet'};
  this->IKsPinFactory::IUnknown::__vftable = (IKsPinFactory_vtbl *)&CKsOutputPin2::`vftable'{for `IKsPinFactory'};
  this->IAMBufferNegotiation::IUnknown::__vftable = (IAMBufferNegotiation_vtbl *)&CKsOutputPin::`vftable'{for `IAMBufferNegotiation'};
  this->IAMStreamConfig::IUnknown::__vftable = (IAMStreamConfig_vtbl *)&CKsOutputPin2::`vftable'{for `IAMStreamConfig'};
  this->IKsControl::IUnknown::__vftable = (IKsControl_vtbl *)&CKsOutputPin2::`vftable'{for `IKsControl'};
  this->IKsAggregateControl::IUnknown::__vftable = (IKsAggregateControl_vtbl *)&CKsOutputPin2::`vftable'{for `IKsAggregateControl'};
  this->IMemAllocatorNotifyCallbackTemp::IUnknown::__vftable = (IMemAllocatorNotifyCallbackTemp_vtbl *)&CKsOutputPin2::`vftable'{for `IMemAllocatorNotifyCallbackTemp'};
  this->IKsPinPrivate::IUnknown::__vftable = (IKsPinPrivate_vtbl *)&CKsOutputPin2::`vftable'{for `IKsPinPrivate'};
  this->IKsD3DPin::IUnknown::__vftable = (IKsD3DPin_vtbl *)&CKsOutputPin::`vftable'{for `IKsD3DPin'};
  m_pFilter = this[1].m_pFilter;
  if ( m_pFilter )
  {
    this[1].m_pFilter = 0;
    m_pFilter->NonDelegatingRelease(m_pFilter);
  }
  m_pLock = this[1].m_pLock;
  if ( m_pLock )
  {
    CAsyncItemHandler::`scalar deleting destructor'((CAsyncItemHandler *)m_pLock);
    this[1].m_pLock = 0;
  }
  v5 = *(void **)&this[1].m_dir;
  if ( v5 )
  {
    CloseHandle(v5);
    *(_QWORD *)&this[1].m_dir = 0;
  }
  v6 = *(void **)&this[1].m_mt.formattype.Data2;
  if ( v6 )
  {
    CoTaskMemFree(v6);
    *(_QWORD *)&this[1].m_mt.formattype.Data2 = 0;
  }
  v7 = *(void **)&this[1].m_mt.formattype.Data4[4];
  if ( v7 )
  {
    CoTaskMemFree(v7);
    *(_QWORD *)&this[1].m_mt.formattype.Data4[4] = 0;
  }
  CKsOutputPin2::DestroyMediaTypeArrays((CKsOutputPin2 *)this, a2);
  McGenEventUnregister_EventUnregister();
  CBaseList::~CBaseList((CBaseList *)&this[1].m_cRef);
  CKsOutputPin::~CKsOutputPin(this);
}

```

## disassembly

```asm
0x18002cd54  push    rbx
0x18002cd56  sub     rsp, 20h
0x18002cd5a  lea     rax, ??_7CKsOutputPin2@@6BCUnknown@@@; const CKsOutputPin2::`vftable'{for `CUnknown'}
0x18002cd61  mov     rbx, rcx
0x18002cd64  mov     [rcx], rax
0x18002cd67  lea     rax, ??_7CKsOutputPin2@@6BIPin@@@; const CKsOutputPin2::`vftable'{for `IPin'}
0x18002cd6e  mov     [rcx+18h], rax
0x18002cd72  lea     rax, ??_7CKsOutputPin2@@6BIQualityControl@@@; const CKsOutputPin2::`vftable'{for `IQualityControl'}
0x18002cd79  mov     [rcx+20h], rax
0x18002cd7d  lea     rax, ??_7CKsOutputPin2@@6BCBaseStreamControl@@@; const CKsOutputPin2::`vftable'{for `CBaseStreamControl'}
0x18002cd84  mov     [rcx+0E8h], rax
0x18002cd8b  lea     rax, ??_7CKsOutputPin@@6BIMediaSeeking@@@; const CKsOutputPin::`vftable'{for `IMediaSeeking'}
0x18002cd92  mov     [rcx+170h], rax
0x18002cd99  lea     rax, ??_7CKsOutputPin2@@6BIKsObject@@@; const CKsOutputPin2::`vftable'{for `IKsObject'}
0x18002cda0  mov     [rcx+178h], rax
0x18002cda7  lea     rax, ??_7CKsOutputPin2@@6BIKsPinEx@@@; const CKsOutputPin2::`vftable'{for `IKsPinEx'}
0x18002cdae  mov     [rcx+180h], rax
0x18002cdb5  lea     rax, ??_7CKsOutputPin@@6BIKsPinPipe@@@; const CKsOutputPin::`vftable'{for `IKsPinPipe'}
0x18002cdbc  mov     [rcx+188h], rax
0x18002cdc3  lea     rax, ??_7CKsOutputPin@@6BISpecifyPropertyPages@@@; const CKsOutputPin::`vftable'{for `ISpecifyPropertyPages'}
0x18002cdca  mov     [rcx+190h], rax
0x18002cdd1  lea     rax, ??_7CKsOutputPin@@6BIStreamBuilder@@@; const CKsOutputPin::`vftable'{for `IStreamBuilder'}
0x18002cdd8  mov     [rcx+198h], rax
0x18002cddf  lea     rax, ??_7CKsOutputPin2@@6BIKsPropertySet@@@; const CKsOutputPin2::`vftable'{for `IKsPropertySet'}
0x18002cde6  mov     [rcx+1A0h], rax
0x18002cded  lea     rax, ??_7CKsOutputPin2@@6BIKsPinFactory@@@; const CKsOutputPin2::`vftable'{for `IKsPinFactory'}
0x18002cdf4  mov     [rcx+1A8h], rax
0x18002cdfb  lea     rax, ??_7CKsOutputPin@@6BIAMBufferNegotiation@@@; const CKsOutputPin::`vftable'{for `IAMBufferNegotiation'}
0x18002ce02  mov     [rcx+1B0h], rax
0x18002ce09  lea     rax, ??_7CKsOutputPin2@@6BIAMStreamConfig@@@; const CKsOutputPin2::`vftable'{for `IAMStreamConfig'}
0x18002ce10  mov     [rcx+1B8h], rax
0x18002ce17  lea     rax, ??_7CKsOutputPin2@@6BIKsControl@@@; const CKsOutputPin2::`vftable'{for `IKsControl'}
0x18002ce1e  mov     [rcx+1C0h], rax
0x18002ce25  lea     rax, ??_7CKsOutputPin2@@6BIKsAggregateControl@@@; const CKsOutputPin2::`vftable'{for `IKsAggregateControl'}
0x18002ce2c  mov     [rcx+1C8h], rax
0x18002ce33  lea     rax, ??_7CKsOutputPin2@@6BIMemAllocatorNotifyCallbackTemp@@@; const CKsOutputPin2::`vftable'{for `IMemAllocatorNotifyCallbackTemp'}
0x18002ce3a  mov     [rcx+1D0h], rax
0x18002ce41  lea     rax, ??_7CKsOutputPin2@@6BIKsPinPrivate@@@; const CKsOutputPin2::`vftable'{for `IKsPinPrivate'}
0x18002ce48  mov     [rcx+1D8h], rax
0x18002ce4f  lea     rax, ??_7CKsOutputPin@@6BIKsD3DPin@@@; const CKsOutputPin::`vftable'{for `IKsD3DPin'}
0x18002ce56  mov     [rcx+1E0h], rax
0x18002ce5d  mov     rcx, [rcx+470h]
0x18002ce64  test    rcx, rcx
0x18002ce67  jz      short loc_18002CE80
0x18002ce69  mov     qword ptr [rbx+470h], 0
0x18002ce74  mov     rax, [rcx]
0x18002ce77  mov     rax, [rax+10h]
0x18002ce7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ce80  mov     rcx, [rbx+460h]; this
0x18002ce87  test    rcx, rcx
0x18002ce8a  jz      short loc_18002CE9C
0x18002ce8c  call    ??_GCAsyncItemHandler@@QEAAPEAXI@Z; CAsyncItemHandler::`scalar deleting destructor'(uint)
0x18002ce91  mov     qword ptr [rbx+460h], 0
0x18002ce9c  mov     rcx, [rbx+458h]; hObject
0x18002cea3  test    rcx, rcx
0x18002cea6  jz      short loc_18002CEBF
0x18002cea8  call    cs:__imp_CloseHandle
0x18002ceaf  nop     dword ptr [rax+rax+00h]
0x18002ceb4  mov     qword ptr [rbx+458h], 0
0x18002cebf  mov     rcx, [rbx+4B8h]; pv
0x18002cec6  test    rcx, rcx
0x18002cec9  jz      short loc_18002CEE2
0x18002cecb  call    cs:__imp_CoTaskMemFree
0x18002ced2  nop     dword ptr [rax+rax+00h]
0x18002ced7  mov     qword ptr [rbx+4B8h], 0
0x18002cee2  mov     rcx, [rbx+4C0h]; pv
0x18002cee9  test    rcx, rcx
0x18002ceec  jz      short loc_18002CF05
0x18002ceee  call    cs:__imp_CoTaskMemFree
0x18002cef5  nop     dword ptr [rax+rax+00h]
0x18002cefa  mov     qword ptr [rbx+4C0h], 0
0x18002cf05  mov     rcx, rbx; this
0x18002cf08  call    ?DestroyMediaTypeArrays@CKsOutputPin2@@QEAAXXZ; CKsOutputPin2::DestroyMediaTypeArrays(void)
0x18002cf0d  call    McGenEventUnregister_EventUnregister
0x18002cf12  lea     rcx, [rbx+430h]; this
0x18002cf19  call    ??1CBaseList@@QEAA@XZ; CBaseList::~CBaseList(void)
0x18002cf1e  mov     rcx, rbx; this
0x18002cf21  add     rsp, 20h
0x18002cf25  pop     rbx
0x18002cf26  jmp     ??1CKsOutputPin@@UEAA@XZ; CKsOutputPin::~CKsOutputPin(void)
```
