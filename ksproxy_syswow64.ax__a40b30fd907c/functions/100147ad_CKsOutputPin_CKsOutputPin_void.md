# CKsOutputPin::~CKsOutputPin(void)

- ea: `0x100147ad`
- end: `0x10014a85`
- name: `??1CKsOutputPin@@UAE@XZ`
- size: `728`
- prototype: `void __thiscall(CKsOutputPin *__hidden this)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x10014780`
- `0x1001a73d`

## callees

- `0x100147ad`
- `0x10014a8b`
- `0x10018890`
- `0x10019830`
- `0x1001f3b0`
- `0x10020b2b`
- `0x10021391`
- `0x100213de`
- `0x1002bf4c`
- `0x1002d510`
- `0x1002f86e`
- `0x1002fe5e`
- `0x100302a7`
- `0x10031712`
- `0x1003af9d`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x100148ce`
- `KERNEL32!CloseHandle` at `0x100148e5`
- `KERNEL32!CloseHandle` at `0x100148fc`
- `KERNEL32!CloseHandle` at `0x100148ce`
- `KERNEL32!CloseHandle` at `0x100148e5`
- `KERNEL32!CloseHandle` at `0x100148fc`
- `KERNEL32!DeleteCriticalSection` at `0x10014a52`
- `KERNEL32!DeleteCriticalSection` at `0x10014a52`

## pseudocode

```c
void __thiscall CKsOutputPin::~CKsOutputPin(CKsOutputPin *this)
{
  IUnknown *m_UnkInner; // ecx
  IKsInterfaceHandler *m_InterfaceHandler; // ecx
  IKsAllocatorEx *m_pKsAllocator; // ecx
  IMemAllocator *m_pAllocator; // ecx
  unsigned int v6; // esi
  CKsOutputPin_vtbl **v7; // ebx
  KSALLOCATOR_FRAMING_EX *v8; // eax
  unsigned int v9; // ecx
  KSALLOCATOR_FRAMING_EX *v10; // edx
  CAsyncItemHandler *m_pAsyncItemHandler; // ecx
  struct CapabilityUsageHelper *ptr; // [esp-4h] [ebp-14h]
  CAsyncItemHandler *v13; // [esp+0h] [ebp-10h]
  void *v14; // [esp+4h] [ebp-Ch]
  DWORD BytesReturned; // [esp+Ch] [ebp-4h] BYREF

  this->CBaseOutputPin::CBasePin::CUnknown::INonDelegatingUnknown::__vftable = (CKsOutputPin_vtbl *)&CKsOutputPin::`vftable'{for `CUnknown'};
  this->CBaseOutputPin::CBasePin::IPin::IUnknown::__vftable = (IPin_vtbl *)&CKsOutputPin2::`vftable'{for `IPin'};
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
    UnloadVolatileInterfaces(&this->m_MarshalerList, 1);
    if ( this->m_hEOSevent )
    {
      KsSynchronousDeviceControl(this->m_PinHandle, 0x2F000Bu, 0, 0, 0, 0, &BytesReturned);
      CAsyncItemHandler::RemoveAsyncItem(v13, v14);
      this->m_hEOSevent = 0;
    }
    SetSyncSource(v13, v14);
    CloseHandle(this->m_PinHandle);
    this->m_PinHandle = 0;
  }
  if ( this->m_PendingIoCompletedEvent )
  {
    CloseHandle(this->m_PendingIoCompletedEvent);
    this->m_PendingIoCompletedEvent = 0;
  }
  if ( this->m_hFlushCompleteEvent )
  {
    CloseHandle(this->m_hFlushCompleteEvent);
    this->m_hFlushCompleteEvent = 0;
  }
  if ( this->m_DataTypeHandler )
  {
    m_UnkInner = this->m_UnkInner;
    this->m_DataTypeHandler = 0;
    if ( m_UnkInner )
    {
      this->m_UnkInner = 0;
      ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IUnknown *))m_UnkInner->Release)(
        m_UnkInner->Release,
        m_UnkInner);
    }
  }
  m_InterfaceHandler = this->m_InterfaceHandler;
  if ( m_InterfaceHandler )
    ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IKsInterfaceHandler *))m_InterfaceHandler->Release)(
      m_InterfaceHandler->Release,
      this->m_InterfaceHandler);
  if ( this->m_ConfigAmMediaType )
    DeleteMediaType((struct _AMMediaType *)v13);
  FreeMarshalers(&this->m_MarshalerList);
  m_pKsAllocator = this->m_pKsAllocator;
  if ( m_pKsAllocator )
  {
    this->m_pKsAllocator = 0;
    ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IKsAllocatorEx *))m_pKsAllocator->Release)(
      m_pKsAllocator->Release,
      m_pKsAllocator);
  }
  m_pAllocator = this->m_pAllocator;
  if ( m_pAllocator )
  {
    this->m_pAllocator = 0;
    ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IMemAllocator *))m_pAllocator->Release)(
      m_pAllocator->Release,
      m_pAllocator);
  }
  v6 = 0;
  do
  {
    v7 = &this->CBaseOutputPin::CBasePin::CUnknown::INonDelegatingUnknown::__vftable + v6++;
    v8 = (KSALLOCATOR_FRAMING_EX *)v7[148];
    if ( v8 )
    {
      v9 = v6;
      if ( v6 < 3 )
      {
        v10 = (KSALLOCATOR_FRAMING_EX *)v7[148];
        do
        {
          v8 = v10;
          if ( v10 == this->m_AllocatorFramingEx[v9] )
          {
            this->m_AllocatorFramingEx[v9] = 0;
            v8 = (KSALLOCATOR_FRAMING_EX *)v7[148];
          }
          ++v9;
          v10 = v8;
        }
        while ( v9 < 3 );
      }
      operator delete(v8, 0x70u);
      v7[148] = 0;
    }
  }
  while ( v6 < 3 );
  m_pAsyncItemHandler = this->m_pAsyncItemHandler;
  if ( m_pAsyncItemHandler )
  {
    CAsyncItemHandler::`scalar deleting destructor'(m_pAsyncItemHandler, (unsigned int)this->m_pAsyncItemHandler);
    this->m_pAsyncItemHandler = 0;
  }
  CKsOutputPin::CloseDirect3DDeviceManager((CKsOutputPin *)&this->IKsD3DPin);
  if ( this->m_spCapUsageHelper.ptr_ )
  {
    ptr = this->m_spCapUsageHelper.ptr_;
    this->m_spCapUsageHelper.ptr_ = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(ptr);
  }
  CBaseList::~CBaseList(&this->m_IoThreadQueue);
  DeleteCriticalSection(&this->m_IoCriticalSection.m_CritSec);
  CBaseList::~CBaseList(&this->m_IoQueue);
  CBaseList::~CBaseList(&this->m_MarshalerList);
  CBaseStreamControl::~CBaseStreamControl(&this->CBaseStreamControl);
  CBasePin::~CBasePin(this);
}

```

## disassembly

```asm
0x100147ad  mov     edi, edi
0x100147af  push    ebp
0x100147b0  mov     ebp, esp
0x100147b2  push    ecx
0x100147b3  push    ebx
0x100147b4  push    esi; void *
0x100147b5  push    edi; struct _AMMediaType *
0x100147b6  mov     edi, ecx
0x100147b8  xor     ebx, ebx
0x100147ba  mov     dword ptr [edi], offset ??_7CKsOutputPin@@6BCUnknown@@@; const CKsOutputPin::`vftable'{for `CUnknown'}
0x100147c0  mov     dword ptr [edi+0Ch], offset ??_7CKsOutputPin2@@6BIPin@@@; const CKsOutputPin2::`vftable'{for `IPin'}
0x100147c7  mov     dword ptr [edi+10h], offset ??_7CKsOutputPin2@@6BIQualityControl@@@; const CKsOutputPin2::`vftable'{for `IQualityControl'}
0x100147ce  mov     dword ptr [edi+0A0h], offset ??_7CKsOutputPin2@@6BCBaseStreamControl@@@; const CKsOutputPin2::`vftable'{for `CBaseStreamControl'}
0x100147d8  mov     dword ptr [edi+108h], offset ??_7CKsOutputPin@@6BIMediaSeeking@@@; const CKsOutputPin::`vftable'{for `IMediaSeeking'}
0x100147e2  mov     dword ptr [edi+10Ch], offset ??_7CKsOutputPin2@@6BIKsObject@@@; const CKsOutputPin2::`vftable'{for `IKsObject'}
0x100147ec  mov     dword ptr [edi+110h], offset ??_7CKsOutputPin@@6BIKsPinEx@@@; const CKsOutputPin::`vftable'{for `IKsPinEx'}
0x100147f6  mov     dword ptr [edi+114h], offset ??_7CKsOutputPin@@6BIKsPinPipe@@@; const CKsOutputPin::`vftable'{for `IKsPinPipe'}
0x10014800  mov     dword ptr [edi+118h], offset ??_7CKsOutputPin@@6BISpecifyPropertyPages@@@; const CKsOutputPin::`vftable'{for `ISpecifyPropertyPages'}
0x1001480a  mov     dword ptr [edi+11Ch], offset ??_7CKsOutputPin@@6BIStreamBuilder@@@; const CKsOutputPin::`vftable'{for `IStreamBuilder'}
0x10014814  mov     dword ptr [edi+120h], offset ??_7CKsOutputPin2@@6BIKsPropertySet@@@; const CKsOutputPin2::`vftable'{for `IKsPropertySet'}
0x1001481e  mov     dword ptr [edi+124h], offset ??_7CKsOutputPin2@@6BIKsPinFactory@@@; const CKsOutputPin2::`vftable'{for `IKsPinFactory'}
0x10014828  mov     dword ptr [edi+128h], offset ??_7CKsOutputPin@@6BIAMBufferNegotiation@@@; const CKsOutputPin::`vftable'{for `IAMBufferNegotiation'}
0x10014832  mov     dword ptr [edi+12Ch], offset ??_7CKsOutputPin@@6BIAMStreamConfig@@@; const CKsOutputPin::`vftable'{for `IAMStreamConfig'}
0x1001483c  mov     dword ptr [edi+130h], offset ??_7CKsOutputPin2@@6BIKsControl@@@; const CKsOutputPin2::`vftable'{for `IKsControl'}
0x10014846  mov     dword ptr [edi+134h], offset ??_7CKsOutputPin2@@6BIKsAggregateControl@@@; const CKsOutputPin2::`vftable'{for `IKsAggregateControl'}
0x10014850  mov     dword ptr [edi+138h], offset ??_7CKsOutputPin@@6BIMemAllocatorNotifyCallbackTemp@@@; const CKsOutputPin::`vftable'{for `IMemAllocatorNotifyCallbackTemp'}
0x1001485a  mov     dword ptr [edi+13Ch], offset ??_7CKsOutputPin2@@6BIKsPinPrivate@@@; const CKsOutputPin2::`vftable'{for `IKsPinPrivate'}
0x10014864  mov     dword ptr [edi+140h], offset ??_7CKsOutputPin@@6BIKsD3DPin@@@; const CKsOutputPin::`vftable'{for `IKsD3DPin'}
0x1001486e  cmp     [edi+164h], ebx
0x10014874  jz      short loc_100148DA
0x10014876  xor     edx, edx
0x10014878  lea     ecx, [edi+1D4h]
0x1001487e  inc     edx
0x1001487f  call    ?UnloadVolatileInterfaces@@YGXPAV?$CGenericList@VCAggregateMarshaler@@@@H@Z; UnloadVolatileInterfaces(CGenericList<CAggregateMarshaler> *,int)
0x10014884  cmp     [edi+290h], ebx
0x1001488a  jz      short loc_100148BB
0x1001488c  lea     eax, [ebp+BytesReturned]
0x1001488f  push    eax; lpBytesReturned
0x10014890  push    ebx; nOutBufferSize
0x10014891  push    ebx; lpOutBuffer
0x10014892  push    ebx; nInBufferSize
0x10014893  push    ebx; lpInBuffer
0x10014894  push    2F000Bh; dwIoControlCode
0x10014899  push    dword ptr [edi+164h]; hDevice
0x1001489f  call    _KsSynchronousDeviceControl@28; KsSynchronousDeviceControl(x,x,x,x,x,x,x)
0x100148a4  mov     edx, [edi+290h]
0x100148aa  mov     ecx, [edi+298h]
0x100148b0  call    ?RemoveAsyncItem@CAsyncItemHandler@@QAGXPAX@Z; CAsyncItemHandler::RemoveAsyncItem(void *)
0x100148b5  mov     [edi+290h], ebx
0x100148bb  mov     ecx, [edi+164h]
0x100148c1  xor     edx, edx
0x100148c3  call    ?SetSyncSource@@YGJPAX0@Z; SetSyncSource(void *,void *)
0x100148c8  push    dword ptr [edi+164h]; hObject
0x100148ce  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x100148d4  mov     [edi+164h], ebx
0x100148da  mov     eax, [edi+1CCh]
0x100148e0  test    eax, eax
0x100148e2  jz      short loc_100148F1
0x100148e4  push    eax; hObject
0x100148e5  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x100148eb  mov     [edi+1CCh], ebx
0x100148f1  mov     eax, [edi+28Ch]
0x100148f7  test    eax, eax
0x100148f9  jz      short loc_10014908
0x100148fb  push    eax; hObject
0x100148fc  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x10014902  mov     [edi+28Ch], ebx
0x10014908  cmp     [edi+178h], ebx
0x1001490e  jz      short loc_10014936
0x10014910  mov     ecx, [edi+17Ch]
0x10014916  mov     [edi+178h], ebx
0x1001491c  test    ecx, ecx
0x1001491e  jz      short loc_10014936
0x10014920  mov     [edi+17Ch], ebx
0x10014926  mov     eax, [ecx]
0x10014928  push    ecx
0x10014929  mov     esi, [eax+8]
0x1001492c  mov     ecx, esi; this
0x1001492e  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10014934  call    esi
0x10014936  mov     ecx, [edi+180h]
0x1001493c  test    ecx, ecx
0x1001493e  jz      short loc_10014950
0x10014940  mov     eax, [ecx]
0x10014942  push    ecx
0x10014943  mov     esi, [eax+8]
0x10014946  mov     ecx, esi; this
0x10014948  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1001494e  call    esi
0x10014950  mov     ecx, [edi+23Ch]
0x10014956  test    ecx, ecx
0x10014958  jz      short loc_1001495F
0x1001495a  call    ?DeleteMediaType@@YGXPAU_AMMediaType@@@Z; DeleteMediaType(_AMMediaType *)
0x1001495f  lea     ecx, [edi+1D4h]
0x10014965  call    ?FreeMarshalers@@YGXPAV?$CGenericList@VCAggregateMarshaler@@@@@Z; FreeMarshalers(CGenericList<CAggregateMarshaler> *)
0x1001496a  mov     ecx, [edi+24Ch]
0x10014970  test    ecx, ecx
0x10014972  jz      short loc_1001498A
0x10014974  mov     [edi+24Ch], ebx
0x1001497a  mov     eax, [ecx]
0x1001497c  push    ecx
0x1001497d  mov     esi, [eax+8]
0x10014980  mov     ecx, esi; this
0x10014982  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10014988  call    esi
0x1001498a  mov     ecx, [edi+98h]
0x10014990  test    ecx, ecx
0x10014992  jz      short loc_100149AA
0x10014994  mov     [edi+98h], ebx
0x1001499a  mov     eax, [ecx]
0x1001499c  push    ecx
0x1001499d  mov     esi, [eax+8]
0x100149a0  mov     ecx, esi; this
0x100149a2  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x100149a8  call    esi
0x100149aa  mov     esi, ebx
0x100149ac  lea     ebx, [edi+esi*4]
0x100149af  inc     esi
0x100149b0  mov     eax, [ebx+250h]
0x100149b6  test    eax, eax
0x100149b8  jz      short loc_100149FB
0x100149ba  mov     ecx, esi
0x100149bc  cmp     ecx, 3
0x100149bf  jnb     short loc_100149E7
0x100149c1  mov     edx, eax
0x100149c3  mov     eax, edx
0x100149c5  cmp     edx, [edi+ecx*4+250h]
0x100149cc  jnz     short loc_100149DF
0x100149ce  mov     dword ptr [edi+ecx*4+250h], 0
0x100149d9  mov     eax, [ebx+250h]
0x100149df  inc     ecx
0x100149e0  mov     edx, eax
0x100149e2  cmp     ecx, 3
0x100149e5  jb      short loc_100149C3
0x100149e7  push    70h ; 'p'; unsigned int
0x100149e9  push    eax; Block
0x100149ea  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x100149ef  pop     ecx
0x100149f0  pop     ecx
0x100149f1  mov     dword ptr [ebx+250h], 0
0x100149fb  cmp     esi, 3
0x100149fe  jb      short loc_100149AC
0x10014a00  mov     ecx, [edi+298h]; this
0x10014a06  test    ecx, ecx
0x10014a08  jz      short loc_10014A1A
0x10014a0a  push    ecx; unsigned int
0x10014a0b  call    ??_GCAsyncItemHandler@@QAEPAXI@Z; CAsyncItemHandler::`scalar deleting destructor'(uint)
0x10014a10  mov     dword ptr [edi+298h], 0
0x10014a1a  lea     eax, [edi+140h]
0x10014a20  push    eax; this
0x10014a21  call    ?CloseDirect3DDeviceManager@CKsOutputPin@@UAGJXZ; CKsOutputPin::CloseDirect3DDeviceManager(void)
0x10014a26  mov     eax, [edi+2BCh]
0x10014a2c  test    eax, eax
0x10014a2e  jz      short loc_10014A40
0x10014a30  push    eax
0x10014a31  mov     dword ptr [edi+2BCh], 0
0x10014a3b  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UAGKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x10014a40  lea     ecx, [edi+21Ch]; this
0x10014a46  call    ??1CBaseList@@QAE@XZ; CBaseList::~CBaseList(void)
0x10014a4b  lea     eax, [edi+204h]
0x10014a51  push    eax; lpCriticalSection
0x10014a52  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x10014a58  lea     ecx, [edi+1ECh]; this
0x10014a5e  call    ??1CBaseList@@QAE@XZ; CBaseList::~CBaseList(void)
0x10014a63  lea     ecx, [edi+1D4h]; this
0x10014a69  call    ??1CBaseList@@QAE@XZ; CBaseList::~CBaseList(void)
0x10014a6e  lea     ecx, [edi+0A0h]; this
0x10014a74  call    ??1CBaseStreamControl@@QAE@XZ; CBaseStreamControl::~CBaseStreamControl(void)
0x10014a79  mov     ecx, edi; this
0x10014a7b  call    ??1CBasePin@@UAE@XZ; CBasePin::~CBasePin(void)
0x10014a80  pop     edi
0x10014a81  pop     esi
0x10014a82  pop     ebx
0x10014a83  leave
0x10014a84  retn
```
