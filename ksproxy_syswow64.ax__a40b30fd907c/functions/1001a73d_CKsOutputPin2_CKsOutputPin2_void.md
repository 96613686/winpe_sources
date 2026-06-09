# CKsOutputPin2::~CKsOutputPin2(void)

- ea: `0x1001a73d`
- end: `0x1001a896`
- name: `??1CKsOutputPin2@@UAE@XZ`
- size: `345`
- prototype: `void __thiscall(CKsOutputPin *this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1001a710`

## callees

- `0x100147ad`
- `0x10014a8b`
- `0x1001a243`
- `0x1001a73d`
- `0x1001e4c6`
- `0x1002d510`
- `0x1002fe5e`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1001a83c`
- `KERNEL32!CloseHandle` at `0x1001a83c`
- `ole32!CoTaskMemFree` at `0x1001a853`
- `ole32!CoTaskMemFree` at `0x1001a86a`
- `ole32!CoTaskMemFree` at `0x1001a853`
- `ole32!CoTaskMemFree` at `0x1001a86a`

## pseudocode

```c
void __thiscall CKsOutputPin2::~CKsOutputPin2(CKsOutputPin *this)
{
  unsigned int Data1; // ecx
  IQualityControl *m_pQSink; // ecx

  Data1 = this[1].m_mt.majortype.Data1;
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
  if ( Data1 )
  {
    this[1].m_mt.majortype.Data1 = 0;
    (*(void (__thiscall **)(_DWORD, unsigned int))(*(_DWORD *)Data1 + 8))(*(_DWORD *)(*(_DWORD *)Data1 + 8), Data1);
  }
  m_pQSink = this[1].m_pQSink;
  if ( m_pQSink )
  {
    CAsyncItemHandler::`scalar deleting destructor'((CAsyncItemHandler *)m_pQSink, (unsigned int)this[1].m_pQSink);
    this[1].m_pQSink = 0;
  }
  if ( this[1].m_pFilter )
  {
    CloseHandle(this[1].m_pFilter);
    this[1].m_pFilter = 0;
  }
  if ( *(_DWORD *)&this[1].m_mt.formattype.Data2 )
  {
    CoTaskMemFree(*(LPVOID *)&this[1].m_mt.formattype.Data2);
    *(_DWORD *)&this[1].m_mt.formattype.Data2 = 0;
  }
  if ( *(_DWORD *)this[1].m_mt.formattype.Data4 )
  {
    CoTaskMemFree(*(LPVOID *)this[1].m_mt.formattype.Data4);
    *(_DWORD *)this[1].m_mt.formattype.Data4 = 0;
  }
  CKsOutputPin2::DestroyMediaTypeArrays((CKsOutputPin2 *)this);
  McGenEventUnregister_EventUnregister();
  CBaseList::~CBaseList((CBaseList *)&this[1].IQualityControl);
  CKsOutputPin::~CKsOutputPin(this);
}

```

## disassembly

```asm
0x1001a73d  mov     edi, edi
0x1001a73f  push    ebx
0x1001a740  push    edi
0x1001a741  mov     edi, ecx
0x1001a743  xor     ebx, ebx
0x1001a745  mov     ecx, [edi+2FCh]
0x1001a74b  mov     dword ptr [edi], offset ??_7CKsOutputPin2@@6BCUnknown@@@; const CKsOutputPin2::`vftable'{for `CUnknown'}
0x1001a751  mov     dword ptr [edi+0Ch], offset ??_7CKsOutputPin2@@6BIPin@@@; const CKsOutputPin2::`vftable'{for `IPin'}
0x1001a758  mov     dword ptr [edi+10h], offset ??_7CKsOutputPin2@@6BIQualityControl@@@; const CKsOutputPin2::`vftable'{for `IQualityControl'}
0x1001a75f  mov     dword ptr [edi+0A0h], offset ??_7CKsOutputPin2@@6BCBaseStreamControl@@@; const CKsOutputPin2::`vftable'{for `CBaseStreamControl'}
0x1001a769  mov     dword ptr [edi+108h], offset ??_7CKsOutputPin@@6BIMediaSeeking@@@; const CKsOutputPin::`vftable'{for `IMediaSeeking'}
0x1001a773  mov     dword ptr [edi+10Ch], offset ??_7CKsOutputPin2@@6BIKsObject@@@; const CKsOutputPin2::`vftable'{for `IKsObject'}
0x1001a77d  mov     dword ptr [edi+110h], offset ??_7CKsOutputPin2@@6BIKsPinEx@@@; const CKsOutputPin2::`vftable'{for `IKsPinEx'}
0x1001a787  mov     dword ptr [edi+114h], offset ??_7CKsOutputPin@@6BIKsPinPipe@@@; const CKsOutputPin::`vftable'{for `IKsPinPipe'}
0x1001a791  mov     dword ptr [edi+118h], offset ??_7CKsOutputPin@@6BISpecifyPropertyPages@@@; const CKsOutputPin::`vftable'{for `ISpecifyPropertyPages'}
0x1001a79b  mov     dword ptr [edi+11Ch], offset ??_7CKsOutputPin@@6BIStreamBuilder@@@; const CKsOutputPin::`vftable'{for `IStreamBuilder'}
0x1001a7a5  mov     dword ptr [edi+120h], offset ??_7CKsOutputPin2@@6BIKsPropertySet@@@; const CKsOutputPin2::`vftable'{for `IKsPropertySet'}
0x1001a7af  mov     dword ptr [edi+124h], offset ??_7CKsOutputPin2@@6BIKsPinFactory@@@; const CKsOutputPin2::`vftable'{for `IKsPinFactory'}
0x1001a7b9  mov     dword ptr [edi+128h], offset ??_7CKsOutputPin@@6BIAMBufferNegotiation@@@; const CKsOutputPin::`vftable'{for `IAMBufferNegotiation'}
0x1001a7c3  mov     dword ptr [edi+12Ch], offset ??_7CKsOutputPin2@@6BIAMStreamConfig@@@; const CKsOutputPin2::`vftable'{for `IAMStreamConfig'}
0x1001a7cd  mov     dword ptr [edi+130h], offset ??_7CKsOutputPin2@@6BIKsControl@@@; const CKsOutputPin2::`vftable'{for `IKsControl'}
0x1001a7d7  mov     dword ptr [edi+134h], offset ??_7CKsOutputPin2@@6BIKsAggregateControl@@@; const CKsOutputPin2::`vftable'{for `IKsAggregateControl'}
0x1001a7e1  mov     dword ptr [edi+138h], offset ??_7CKsOutputPin2@@6BIMemAllocatorNotifyCallbackTemp@@@; const CKsOutputPin2::`vftable'{for `IMemAllocatorNotifyCallbackTemp'}
0x1001a7eb  mov     dword ptr [edi+13Ch], offset ??_7CKsOutputPin2@@6BIKsPinPrivate@@@; const CKsOutputPin2::`vftable'{for `IKsPinPrivate'}
0x1001a7f5  mov     dword ptr [edi+140h], offset ??_7CKsOutputPin@@6BIKsD3DPin@@@; const CKsOutputPin::`vftable'{for `IKsD3DPin'}
0x1001a7ff  test    ecx, ecx
0x1001a801  jz      short loc_1001A81B
0x1001a803  mov     [edi+2FCh], ebx
0x1001a809  mov     eax, [ecx]
0x1001a80b  push    esi
0x1001a80c  push    ecx
0x1001a80d  mov     esi, [eax+8]
0x1001a810  mov     ecx, esi; this
0x1001a812  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1001a818  call    esi
0x1001a81a  pop     esi
0x1001a81b  mov     ecx, [edi+2F4h]; this
0x1001a821  test    ecx, ecx
0x1001a823  jz      short loc_1001A831
0x1001a825  push    ecx; unsigned int
0x1001a826  call    ??_GCAsyncItemHandler@@QAEPAXI@Z; CAsyncItemHandler::`scalar deleting destructor'(uint)
0x1001a82b  mov     [edi+2F4h], ebx
0x1001a831  mov     eax, [edi+2F0h]
0x1001a837  test    eax, eax
0x1001a839  jz      short loc_1001A848
0x1001a83b  push    eax; hObject
0x1001a83c  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x1001a842  mov     [edi+2F0h], ebx
0x1001a848  mov     eax, [edi+32Ch]
0x1001a84e  test    eax, eax
0x1001a850  jz      short loc_1001A85F
0x1001a852  push    eax; pv
0x1001a853  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x1001a859  mov     [edi+32Ch], ebx
0x1001a85f  mov     eax, [edi+330h]
0x1001a865  test    eax, eax
0x1001a867  jz      short loc_1001A876
0x1001a869  push    eax; pv
0x1001a86a  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x1001a870  mov     [edi+330h], ebx
0x1001a876  mov     ecx, edi; this
0x1001a878  call    ?DestroyMediaTypeArrays@CKsOutputPin2@@QAEXXZ; CKsOutputPin2::DestroyMediaTypeArrays(void)
0x1001a87d  call    _McGenEventUnregister_EventUnregister@4; McGenEventUnregister_EventUnregister(x)
0x1001a882  lea     ecx, [edi+2D8h]; this
0x1001a888  call    ??1CBaseList@@QAE@XZ; CBaseList::~CBaseList(void)
0x1001a88d  mov     ecx, edi; this
0x1001a88f  pop     edi
0x1001a890  pop     ebx
0x1001a891  jmp     ??1CKsOutputPin@@UAE@XZ; CKsOutputPin::~CKsOutputPin(void)
```
