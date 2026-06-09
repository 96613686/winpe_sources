# CKsInputPin::CKsInputPin(ushort *,int,_GUID,CKsProxy *,long *,ushort *)

- ea: `0x18000d88c`
- end: `0x18000db9f`
- name: `??0CKsInputPin@@QEAA@PEAGHU_GUID@@PEAVCKsProxy@@PEAJ0@Z`
- size: `787`
- prototype: `CKsInputPin *__fastcall(CKsInputPin *this, unsigned __int16 *, unsigned int, struct _GUID *, struct CKsProxy *, int *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b6fc`

## callees

- `0x18000909c`
- `0x180009c4c`
- `0x18000cab4`
- `0x18000d88c`
- `0x18000dba8`
- `0x18000dd00`
- `0x18001f620`
- `0x18001ffb0`
- `0x1800273d0`
- `0x180028e20`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000db56`
- `KERNEL32!GetLastError` at `0x18000db56`
- `KERNEL32!CreateEventW` at `0x18000da8b`
- `KERNEL32!CreateEventW` at `0x18000da8b`
- `KERNEL32!InitializeCriticalSection` at `0x18000da12`
- `KERNEL32!InitializeCriticalSection` at `0x18000da12`

## pseudocode

```c
CKsInputPin *__fastcall CKsInputPin::CKsInputPin(
        CKsInputPin *this,
        unsigned __int16 *a2,
        unsigned int a3,
        struct _GUID *a4,
        struct CKsProxy *a5,
        int *a6,
        unsigned __int16 *a7)
{
  HANDLE EventW; // rax
  KSPIN_COMMUNICATION m_OriginalCommunication; // eax
  int MediaType; // eax
  signed int LastError; // eax
  int *v14; // [rsp+20h] [rbp-148h]
  struct _AMMediaType v15; // [rsp+40h] [rbp-128h] BYREF
  unsigned __int16 v16[64]; // [rsp+A0h] [rbp-C8h] BYREF

  CBasePin::CBasePin(
    this,
    a7,
    a5,
    (struct CCritSec *)((unsigned __int64)&a5->CCritSec & -(__int64)(a5 != 0)),
    v14,
    a7,
    PINDIR_INPUT);
  this->m_pAllocator = 0;
  *(_WORD *)&this->m_bReadOnly = 0;
  memset_0(&this->m_SampleProps, 0, sizeof(this->m_SampleProps));
  this->m_PinHandle = 0;
  this->CBaseInputPin::CBasePin::CUnknown::INonDelegatingUnknown::__vftable = (CKsInputPin_vtbl *)&CKsInputPin::`vftable'{for `CUnknown'};
  this->m_DataTypeHandler = 0;
  this->CBaseInputPin::CBasePin::IPin::IUnknown::__vftable = (IPin_vtbl *)&CKsInputPin::`vftable'{for `IPin'};
  this->m_UnkInner = 0;
  this->CBaseInputPin::CBasePin::IQualityControl::IUnknown::__vftable = (IQualityControl_vtbl *)&CKsInputPin::`vftable'{for `IQualityControl'};
  this->m_InterfaceHandler = 0;
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
  this->m_PinFactoryId = a3;
  this->m_PropagatingAcquire = 0;
  *(_QWORD *)&this->m_MarshalData = 1;
  this->m_PendingIoCompletedEvent = 0;
  InitializeCriticalSection(&this->m_IoCriticalSection.m_CritSec);
  this->m_MarshalerList.m_pFirst = 0;
  this->m_MarshalerList.m_pLast = 0;
  this->m_MarshalerList.m_Count = 0;
  *(_QWORD *)&this->m_MarshalerList.m_Cache.m_iCacheSize = 10;
  this->m_MarshalerList.m_Cache.m_pHead = 0;
  *(_QWORD *)&this->m_QualitySupport = 0;
  this->m_pKsAllocator = 0;
  *(_QWORD *)&this->m_FramingProp[2] = 0;
  this->m_PinBusCacheInit = 0;
  this->m_RelativeRefCount = 1;
  *(_QWORD *)this->m_FramingProp = 0;
  *(_OWORD *)this->m_AllocatorFramingEx = 0;
  this->m_AllocatorFramingEx[2] = 0;
  if ( *a6 >= 0 )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    this->m_PendingIoCompletedEvent = EventW;
    if ( EventW )
    {
      *a6 = CKsProxy::GetPinFactoryCommunication(a5, this->m_PinFactoryId, &this->m_OriginalCommunication);
      m_OriginalCommunication = this->m_OriginalCommunication;
      this->m_CurrentCommunication = m_OriginalCommunication;
      if ( m_OriginalCommunication == KSPIN_COMMUNICATION_NONE )
      {
        memset_0((void *)&v15, 0, sizeof(v15));
        v15.lSampleSize = 1;
        v15.bFixedSizeSamples = 1;
        MediaType = CKsInputPin::GetMediaType(this, 0, (struct CMediaType *)&v15);
        *a6 = MediaType;
        if ( MediaType >= 0 )
          CKsInputPin::SetMediaType(this, (const struct CMediaType *)&v15);
        FreeMediaType(&v15);
      }
      StringCchPrintfW(v16, 0x40u, L"PinFactory\\%u\\Interfaces", a3);
      AggregateMarshalers(
        a5->m_DeviceRegKey,
        v16,
        &this->m_MarshalerList,
        (unsigned __int64)&this->IKsPinEx & -(__int64)(this != 0));
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      *a6 = LastError;
    }
  }
  return this;
}

```

## disassembly

```asm
0x18000d88c  mov     [rsp+arg_8], rbx
0x18000d891  push    rbp
0x18000d892  push    rsi
0x18000d893  push    rdi
0x18000d894  push    r12
0x18000d896  push    r13
0x18000d898  push    r14
0x18000d89a  push    r15
0x18000d89c  sub     rsp, 130h
0x18000d8a3  mov     rax, cs:__security_cookie
0x18000d8aa  xor     rax, rsp
0x18000d8ad  mov     [rsp+168h+var_48], rax
0x18000d8b5  mov     rbp, [rsp+168h+arg_20]
0x18000d8bd  mov     rdi, rcx
0x18000d8c0  mov     rdx, [rsp+168h+arg_30]; unsigned __int16 *
0x18000d8c8  mov     r15d, r8d
0x18000d8cb  mov     rsi, [rsp+168h+arg_28]
0x18000d8d3  mov     rax, rbp
0x18000d8d6  neg     rax
0x18000d8d9  mov     r8, rbp; struct CBaseFilter *
0x18000d8dc  lea     rcx, [rbp+0F8h]
0x18000d8e3  sbb     r9, r9
0x18000d8e6  xor     r13d, r13d
0x18000d8e9  and     r9, rcx; struct CCritSec *
0x18000d8ec  mov     [rsp+168h+var_138], r13d; enum _PinDirection
0x18000d8f1  mov     rcx, rdi; this
0x18000d8f4  mov     [rsp+168h+var_140], rdx; unsigned __int16 *
0x18000d8f9  call    ??0CBasePin@@QEAA@PEBGPEAVCBaseFilter@@PEAVCCritSec@@PEAJ0W4_PinDirection@@@Z; CBasePin::CBasePin(ushort const *,CBaseFilter *,CCritSec *,long *,ushort const *,_PinDirection)
0x18000d8fe  lea     rcx, [rdi+0F0h]; void *
0x18000d905  mov     [rdi+0E0h], r13
0x18000d90c  xor     edx, edx; Val
0x18000d90e  mov     [rdi+0E8h], r13w
0x18000d916  lea     r8d, [r13+40h]; Size
0x18000d91a  call    memset_0
0x18000d91f  lea     rax, ??_7CKsInputPin@@6BCUnknown@@@; const CKsInputPin::`vftable'{for `CUnknown'}
0x18000d926  mov     [rdi+178h], r13
0x18000d92d  mov     [rdi], rax
0x18000d930  lea     r12, [rdi+138h]
0x18000d937  lea     rax, ??_7CKsInputPin@@6BIPin@@@; const CKsInputPin::`vftable'{for `IPin'}
0x18000d93e  mov     [rdi+180h], r13
0x18000d945  mov     [rdi+18h], rax
0x18000d949  lea     ebx, [r13+1]
0x18000d94d  lea     rax, ??_7CKsInputPin@@6BIQualityControl@@@; const CKsInputPin::`vftable'{for `IQualityControl'}
0x18000d954  mov     [rdi+188h], r13
0x18000d95b  mov     [rdi+20h], rax
0x18000d95f  lea     rcx, [rdi+1F0h]; lpCriticalSection
0x18000d966  lea     rax, ??_7CKsInputPin@@6BCBaseInputPin@@@; const CKsInputPin::`vftable'{for `CBaseInputPin'}
0x18000d96d  mov     [rdi+190h], r13
0x18000d974  mov     [rdi+0D8h], rax
0x18000d97b  lea     rax, ??_7CKsInputPin@@6BIKsObject@@@; const CKsInputPin::`vftable'{for `IKsObject'}
0x18000d982  mov     [rdi+130h], rax
0x18000d989  lea     rax, ??_7CKsInputPin@@6BIKsPinEx@@@; const CKsInputPin::`vftable'{for `IKsPinEx'}
0x18000d990  mov     [r12], rax
0x18000d994  lea     rax, ??_7CKsInputPin@@6BIKsPinPipe@@@; const CKsInputPin::`vftable'{for `IKsPinPipe'}
0x18000d99b  mov     [rdi+140h], rax
0x18000d9a2  lea     rax, ??_7CKsInputPin@@6BISpecifyPropertyPages@@@; const CKsInputPin::`vftable'{for `ISpecifyPropertyPages'}
0x18000d9a9  mov     [rdi+148h], rax
0x18000d9b0  lea     rax, ??_7CKsInputPin@@6BIStreamBuilder@@@; const CKsInputPin::`vftable'{for `IStreamBuilder'}
0x18000d9b7  mov     [rdi+150h], rax
0x18000d9be  lea     rax, ??_7CKsInputPin@@6BIKsPropertySet@@@; const CKsInputPin::`vftable'{for `IKsPropertySet'}
0x18000d9c5  mov     [rdi+158h], rax
0x18000d9cc  lea     rax, ??_7CKsInputPin@@6BIKsPinFactory@@@; const CKsInputPin::`vftable'{for `IKsPinFactory'}
0x18000d9d3  mov     [rdi+160h], rax
0x18000d9da  lea     rax, ??_7CKsInputPin@@6BIKsControl@@@; const CKsInputPin::`vftable'{for `IKsControl'}
0x18000d9e1  mov     [rdi+168h], rax
0x18000d9e8  lea     rax, ??_7CKsInputPin@@6BIKsAggregateControl@@@; const CKsInputPin::`vftable'{for `IKsAggregateControl'}
0x18000d9ef  mov     [rdi+170h], rax
0x18000d9f6  mov     [rdi+198h], r15d
0x18000d9fd  mov     [rdi+1D8h], r13d
0x18000da04  mov     [rdi+1DCh], rbx
0x18000da0b  mov     [rdi+1E8h], r13
0x18000da12  call    cs:__imp_InitializeCriticalSection
0x18000da19  nop     dword ptr [rax+rax+00h]
0x18000da1e  lea     r14, [rdi+218h]
0x18000da25  xor     eax, eax
0x18000da27  mov     [r14], r13
0x18000da2a  xorps   xmm0, xmm0
0x18000da2d  mov     [r14+8], r13
0x18000da31  mov     [r14+10h], r13d
0x18000da35  mov     qword ptr [r14+18h], 0Ah
0x18000da3d  mov     [r14+20h], r13
0x18000da41  mov     [rdi+240h], r13
0x18000da48  mov     [rdi+250h], r13
0x18000da4f  mov     [rdi+278h], r13
0x18000da56  mov     [rdi+290h], r13d
0x18000da5d  mov     [rdi+294h], ebx
0x18000da63  mov     [rdi+270h], rax
0x18000da6a  movups  xmmword ptr [rdi+258h], xmm0
0x18000da71  mov     [rdi+268h], rax
0x18000da78  cmp     [rsi], r13d
0x18000da7b  jl      loc_18000DB70
0x18000da81  xor     r9d, r9d; lpName
0x18000da84  xor     r8d, r8d; bInitialState
0x18000da87  xor     edx, edx; bManualReset
0x18000da89  xor     ecx, ecx; lpEventAttributes
0x18000da8b  call    cs:__imp_CreateEventW
0x18000da92  nop     dword ptr [rax+rax+00h]
0x18000da97  mov     [rdi+1E8h], rax
0x18000da9e  test    rax, rax
0x18000daa1  jz      loc_18000DB56
0x18000daa7  mov     edx, [rdi+198h]; unsigned int
0x18000daad  lea     rbx, [rdi+19Ch]
0x18000dab4  mov     r8, rbx; enum KSPIN_COMMUNICATION *
0x18000dab7  mov     rcx, rbp; this
0x18000daba  call    ?GetPinFactoryCommunication@CKsProxy@@QEAAJKPEAW4KSPIN_COMMUNICATION@@@Z; CKsProxy::GetPinFactoryCommunication(ulong,KSPIN_COMMUNICATION *)
0x18000dabf  mov     [rsi], eax
0x18000dac1  mov     eax, [rbx]
0x18000dac3  mov     [rdi+1A0h], eax
0x18000dac9  test    eax, eax
0x18000dacb  jnz     short loc_18000DB15
0x18000dacd  xor     edx, edx; Val
0x18000dacf  lea     r8d, [r13+58h]; Size
0x18000dad3  lea     rcx, [rsp+168h+var_128]; void *
0x18000dad8  call    memset_0
0x18000dadd  lea     eax, [r13+1]
0x18000dae1  xor     edx, edx; int
0x18000dae3  lea     r8, [rsp+168h+var_128]; struct CMediaType *
0x18000dae8  mov     [rsp+168h+var_128.lSampleSize], eax
0x18000daec  mov     rcx, rdi; this
0x18000daef  mov     [rsp+168h+var_128.bFixedSizeSamples], eax
0x18000daf3  call    ?GetMediaType@CKsInputPin@@UEAAJHPEAVCMediaType@@@Z; CKsInputPin::GetMediaType(int,CMediaType *)
0x18000daf8  mov     [rsi], eax
0x18000dafa  test    eax, eax
0x18000dafc  js      short loc_18000DB0B
0x18000dafe  lea     rdx, [rsp+168h+var_128]; struct CMediaType *
0x18000db03  mov     rcx, rdi; this
0x18000db06  call    ?SetMediaType@CKsInputPin@@UEAAJPEBVCMediaType@@@Z; CKsInputPin::SetMediaType(CMediaType const *)
0x18000db0b  lea     rcx, [rsp+168h+var_128]; struct _AMMediaType *
0x18000db10  call    ?FreeMediaType@@YAXAEAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x18000db15  mov     r9d, r15d
0x18000db18  lea     r8, aPinfactoryUInt; "PinFactory\\%u\\Interfaces"
0x18000db1f  mov     edx, 40h ; '@'; unsigned __int64
0x18000db24  lea     rcx, [rsp+168h+var_C8]; unsigned __int16 *
0x18000db2c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000db31  mov     rcx, [rbp+1F8h]
0x18000db38  lea     rdx, [rsp+168h+var_C8]
0x18000db40  mov     rax, rdi
0x18000db43  mov     r8, r14
0x18000db46  neg     rax
0x18000db49  sbb     r9, r9
0x18000db4c  and     r9, r12
0x18000db4f  call    ?AggregateMarshalers@@YAJPEAUHKEY__@@PEBGPEAV?$CGenericList@VCAggregateMarshaler@@@@PEAUIUnknown@@@Z; AggregateMarshalers(HKEY__ *,ushort const *,CGenericList<CAggregateMarshaler> *,IUnknown *)
0x18000db54  jmp     short loc_18000DB70
0x18000db56  call    cs:__imp_GetLastError
0x18000db5d  nop     dword ptr [rax+rax+00h]
0x18000db62  test    eax, eax
0x18000db64  jle     short loc_18000DB6E
0x18000db66  movzx   eax, ax
0x18000db69  or      eax, 80070000h
0x18000db6e  mov     [rsi], eax
0x18000db70  mov     rax, rdi
0x18000db73  mov     rcx, [rsp+168h+var_48]
0x18000db7b  xor     rcx, rsp; StackCookie
0x18000db7e  call    __security_check_cookie
0x18000db83  mov     rbx, [rsp+168h+arg_8]
0x18000db8b  add     rsp, 130h
0x18000db92  pop     r15
0x18000db94  pop     r14
0x18000db96  pop     r13
0x18000db98  pop     r12
0x18000db9a  pop     rdi
0x18000db9b  pop     rsi
0x18000db9c  pop     rbp
0x18000db9d  retn
```
