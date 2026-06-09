# CKsInputPin::~CKsInputPin(void)

- ea: `0x1001110d`
- end: `0x1001132f`
- name: `??1CKsInputPin@@UAE@XZ`
- size: `546`
- prototype: `void __thiscall(CKsInputPin *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x100110e0`

## callees

- `0x1000de58`
- `0x1001110d`
- `0x10020b2b`
- `0x10021391`
- `0x100213de`
- `0x1002191f`
- `0x1002d510`
- `0x1002fe5e`
- `0x10032267`
- `0x1003af9d`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x100111ff`
- `KERNEL32!CloseHandle` at `0x10011218`
- `KERNEL32!CloseHandle` at `0x100111ff`
- `KERNEL32!CloseHandle` at `0x10011218`
- `KERNEL32!DeleteCriticalSection` at `0x1001131f`
- `KERNEL32!DeleteCriticalSection` at `0x1001131f`

## pseudocode

```c
void __thiscall CKsInputPin::~CKsInputPin(CKsInputPin *this)
{
  IKsPinEx *v2; // esi
  IUnknown *m_UnkInner; // ecx
  IKsInterfaceHandler *m_InterfaceHandler; // ecx
  IKsAllocatorEx *m_pKsAllocator; // ecx
  IMemAllocator *m_pAllocator; // ecx
  unsigned int v7; // esi
  CKsInputPin_vtbl **v8; // ebx
  KSALLOCATOR_FRAMING_EX *v9; // eax
  unsigned int v10; // ecx
  KSALLOCATOR_FRAMING_EX *v11; // edx
  CKsProxy *v12; // [esp+0h] [ebp-Ch]
  void *v13; // [esp+0h] [ebp-Ch]
  struct CKsProxy *v14; // [esp+4h] [ebp-8h]
  void *v15; // [esp+4h] [ebp-8h]

  v2 = &this->IKsPinEx;
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
    UnloadVolatileInterfaces(&this->m_MarshalerList, 1);
    if ( this->m_QualitySupport )
    {
      this->m_QualitySupport = 0;
      EstablishQualitySupport(0, v12, v14);
      (*(void (__thiscall **)(_DWORD, _DWORD, IKsPinEx *))(**(_DWORD **)this->m_pFilter[3].m_clsid.Data4 + 16))(
        *(_DWORD *)(**(_DWORD **)this->m_pFilter[3].m_clsid.Data4 + 16),
        *(_DWORD *)this->m_pFilter[3].m_clsid.Data4,
        v2);
    }
    CKsProxy::TerminateEndOfStreamNotification(v12, v14);
    SetSyncSource(v13, v15);
    CloseHandle(this->m_PinHandle);
    this->m_PinHandle = 0;
  }
  if ( this->m_PendingIoCompletedEvent )
  {
    CloseHandle(this->m_PendingIoCompletedEvent);
    this->m_PendingIoCompletedEvent = 0;
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
  v7 = 0;
  do
  {
    v8 = &this->CBaseInputPin::CBasePin::CUnknown::INonDelegatingUnknown::__vftable + v7++;
    v9 = (KSALLOCATOR_FRAMING_EX *)v8[102];
    if ( v9 )
    {
      v10 = v7;
      if ( v7 < 3 )
      {
        v11 = (KSALLOCATOR_FRAMING_EX *)v8[102];
        do
        {
          v9 = v11;
          if ( v11 == this->m_AllocatorFramingEx[v10] )
          {
            this->m_AllocatorFramingEx[v10] = 0;
            v9 = (KSALLOCATOR_FRAMING_EX *)v8[102];
          }
          ++v10;
          v11 = v9;
        }
        while ( v10 < 3 );
      }
      operator delete(v9, 0x70u);
      v8[102] = 0;
    }
  }
  while ( v7 < 3 );
  CBaseList::~CBaseList(&this->m_MarshalerList);
  DeleteCriticalSection(&this->m_IoCriticalSection.m_CritSec);
  CBaseInputPin::~CBaseInputPin(this);
}

```

## disassembly

```asm
0x1001110d  mov     edi, edi
0x1001110f  push    ebx
0x10011110  push    esi; void *
0x10011111  push    edi; void *
0x10011112  mov     edi, ecx
0x10011114  xor     ebx, ebx
0x10011116  lea     esi, [edi+0DCh]
0x1001111c  mov     dword ptr [edi], offset ??_7CKsInputPin@@6BCUnknown@@@; const CKsInputPin::`vftable'{for `CUnknown'}
0x10011122  mov     dword ptr [edi+0Ch], offset ??_7CKsInputPin@@6BIPin@@@; const CKsInputPin::`vftable'{for `IPin'}
0x10011129  mov     dword ptr [edi+10h], offset ??_7CKsInputPin@@6BIQualityControl@@@; const CKsInputPin::`vftable'{for `IQualityControl'}
0x10011130  mov     dword ptr [edi+98h], offset ??_7CKsInputPin@@6BCBaseInputPin@@@; const CKsInputPin::`vftable'{for `CBaseInputPin'}
0x1001113a  mov     dword ptr [edi+0D8h], offset ??_7CKsInputPin@@6BIKsObject@@@; const CKsInputPin::`vftable'{for `IKsObject'}
0x10011144  mov     dword ptr [esi], offset ??_7CKsInputPin@@6BIKsPinEx@@@; const CKsInputPin::`vftable'{for `IKsPinEx'}
0x1001114a  mov     dword ptr [edi+0E0h], offset ??_7CKsInputPin@@6BIKsPinPipe@@@; const CKsInputPin::`vftable'{for `IKsPinPipe'}
0x10011154  mov     dword ptr [edi+0E4h], offset ??_7CKsInputPin@@6BISpecifyPropertyPages@@@; const CKsInputPin::`vftable'{for `ISpecifyPropertyPages'}
0x1001115e  mov     dword ptr [edi+0E8h], offset ??_7CKsInputPin@@6BIStreamBuilder@@@; const CKsInputPin::`vftable'{for `IStreamBuilder'}
0x10011168  mov     dword ptr [edi+0ECh], offset ??_7CKsInputPin@@6BIKsPropertySet@@@; const CKsInputPin::`vftable'{for `IKsPropertySet'}
0x10011172  mov     dword ptr [edi+0F0h], offset ??_7CKsInputPin@@6BIKsPinFactory@@@; const CKsInputPin::`vftable'{for `IKsPinFactory'}
0x1001117c  mov     dword ptr [edi+0F4h], offset ??_7CKsInputPin@@6BIKsControl@@@; const CKsInputPin::`vftable'{for `IKsControl'}
0x10011186  mov     dword ptr [edi+0F8h], offset ??_7CKsInputPin@@6BIKsAggregateControl@@@; const CKsInputPin::`vftable'{for `IKsAggregateControl'}
0x10011190  cmp     [edi+0FCh], ebx
0x10011196  jz      short loc_1001120D
0x10011198  xor     edx, edx
0x1001119a  lea     ecx, [edi+170h]
0x100111a0  inc     edx
0x100111a1  call    ?UnloadVolatileInterfaces@@YGXPAV?$CGenericList@VCAggregateMarshaler@@@@H@Z; UnloadVolatileInterfaces(CGenericList<CAggregateMarshaler> *,int)
0x100111a6  xor     eax, eax
0x100111a8  cmp     [edi+188h], eax
0x100111ae  jz      short loc_100111DE
0x100111b0  mov     edx, [edi+0FCh]
0x100111b6  xor     ecx, ecx
0x100111b8  push    eax; struct IKsPin *
0x100111b9  mov     [edi+188h], eax
0x100111bf  call    ?EstablishQualitySupport@@YGHPAUIKsPin@@PAXPAVCKsProxy@@@Z; EstablishQualitySupport(IKsPin *,void *,CKsProxy *)
0x100111c4  mov     eax, [edi+28h]
0x100111c7  push    esi
0x100111c8  mov     eax, [eax+120h]
0x100111ce  push    eax
0x100111cf  mov     ecx, [eax]
0x100111d1  mov     esi, [ecx+10h]
0x100111d4  mov     ecx, esi; this
0x100111d6  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x100111dc  call    esi
0x100111de  mov     edx, [edi+0FCh]
0x100111e4  mov     ecx, [edi+28h]
0x100111e7  call    ?TerminateEndOfStreamNotification@CKsProxy@@QAGXPAX@Z; CKsProxy::TerminateEndOfStreamNotification(void *)
0x100111ec  mov     ecx, [edi+0FCh]
0x100111f2  xor     edx, edx
0x100111f4  call    ?SetSyncSource@@YGJPAX0@Z; SetSyncSource(void *,void *)
0x100111f9  push    dword ptr [edi+0FCh]; hObject
0x100111ff  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x10011205  xor     ebx, ebx
0x10011207  mov     [edi+0FCh], ebx
0x1001120d  mov     eax, [edi+154h]
0x10011213  test    eax, eax
0x10011215  jz      short loc_10011224
0x10011217  push    eax; hObject
0x10011218  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x1001121e  mov     [edi+154h], ebx
0x10011224  cmp     [edi+100h], ebx
0x1001122a  jz      short loc_10011252
0x1001122c  mov     ecx, [edi+104h]
0x10011232  mov     [edi+100h], ebx
0x10011238  test    ecx, ecx
0x1001123a  jz      short loc_10011252
0x1001123c  mov     [edi+104h], ebx
0x10011242  mov     eax, [ecx]
0x10011244  push    ecx
0x10011245  mov     esi, [eax+8]
0x10011248  mov     ecx, esi; this
0x1001124a  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10011250  call    esi
0x10011252  mov     ecx, [edi+108h]
0x10011258  test    ecx, ecx
0x1001125a  jz      short loc_1001126C
0x1001125c  mov     eax, [ecx]
0x1001125e  push    ecx
0x1001125f  mov     esi, [eax+8]
0x10011262  mov     ecx, esi; this
0x10011264  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1001126a  call    esi
0x1001126c  lea     ecx, [edi+170h]
0x10011272  call    ?FreeMarshalers@@YGXPAV?$CGenericList@VCAggregateMarshaler@@@@@Z; FreeMarshalers(CGenericList<CAggregateMarshaler> *)
0x10011277  mov     ecx, [edi+194h]
0x1001127d  test    ecx, ecx
0x1001127f  jz      short loc_10011297
0x10011281  mov     [edi+194h], ebx
0x10011287  mov     eax, [ecx]
0x10011289  push    ecx
0x1001128a  mov     esi, [eax+8]
0x1001128d  mov     ecx, esi; this
0x1001128f  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10011295  call    esi
0x10011297  mov     ecx, [edi+9Ch]
0x1001129d  test    ecx, ecx
0x1001129f  jz      short loc_100112B7
0x100112a1  mov     [edi+9Ch], ebx
0x100112a7  mov     eax, [ecx]
0x100112a9  push    ecx
0x100112aa  mov     esi, [eax+8]
0x100112ad  mov     ecx, esi; this
0x100112af  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x100112b5  call    esi
0x100112b7  mov     esi, ebx
0x100112b9  lea     ebx, [edi+esi*4]
0x100112bc  inc     esi
0x100112bd  mov     eax, [ebx+198h]
0x100112c3  test    eax, eax
0x100112c5  jz      short loc_10011308
0x100112c7  mov     ecx, esi
0x100112c9  cmp     ecx, 3
0x100112cc  jnb     short loc_100112F4
0x100112ce  mov     edx, eax
0x100112d0  mov     eax, edx
0x100112d2  cmp     edx, [edi+ecx*4+198h]
0x100112d9  jnz     short loc_100112EC
0x100112db  mov     dword ptr [edi+ecx*4+198h], 0
0x100112e6  mov     eax, [ebx+198h]
0x100112ec  inc     ecx
0x100112ed  mov     edx, eax
0x100112ef  cmp     ecx, 3
0x100112f2  jb      short loc_100112D0
0x100112f4  push    70h ; 'p'; unsigned int
0x100112f6  push    eax; Block
0x100112f7  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x100112fc  pop     ecx
0x100112fd  pop     ecx
0x100112fe  mov     dword ptr [ebx+198h], 0
0x10011308  cmp     esi, 3
0x1001130b  jb      short loc_100112B9
0x1001130d  lea     ecx, [edi+170h]; this
0x10011313  call    ??1CBaseList@@QAE@XZ; CBaseList::~CBaseList(void)
0x10011318  lea     eax, [edi+158h]
0x1001131e  push    eax; lpCriticalSection
0x1001131f  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x10011325  mov     ecx, edi; this
0x10011327  pop     edi
0x10011328  pop     esi
0x10011329  pop     ebx
0x1001132a  jmp     ??1CBaseInputPin@@UAE@XZ; CBaseInputPin::~CBaseInputPin(void)
```
