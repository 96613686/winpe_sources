# CKsInputPin::CKsInputPin(ushort *,int,_GUID,CKsProxy *,long *,ushort *)

- ea: `0x10010e48`
- end: `0x100110da`
- name: `??0CKsInputPin@@QAE@PAGHU_GUID@@PAVCKsProxy@@PAJ0@Z`
- size: `658`
- prototype: `CKsInputPin *__thiscall(CKsInputPin *this, unsigned __int16 *, unsigned int, struct _GUID, struct CKsProxy *, int *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x10009f60`

## callees

- `0x10006937`
- `0x10009f00`
- `0x10010e48`
- `0x10012330`
- `0x100125f0`
- `0x10020ce6`
- `0x1003035c`
- `0x10031648`
- `0x1003aba0`
- `0x1003b5e4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x100110b1`
- `KERNEL32!GetLastError` at `0x100110b1`
- `KERNEL32!CreateEventW` at `0x10010fda`
- `KERNEL32!CreateEventW` at `0x10010fda`
- `KERNEL32!InitializeCriticalSection` at `0x10010f71`
- `KERNEL32!InitializeCriticalSection` at `0x10010f71`

## pseudocode

```c
CKsInputPin *__thiscall CKsInputPin::CKsInputPin(
        CKsInputPin *this,
        unsigned __int16 *a2,
        unsigned int a3,
        struct _GUID a4,
        struct CKsProxy *a5,
        int *a6,
        unsigned __int16 *a7)
{
  HANDLE EventW; // eax
  KSPIN_COMMUNICATION m_OriginalCommunication; // eax
  int MediaType; // eax
  IKsPinEx *v11; // eax
  signed int LastError; // eax
  unsigned int v13; // ecx
  unsigned int v15; // [esp+0h] [ebp-ECh]
  struct _AMMediaType *v16; // [esp+0h] [ebp-ECh]
  enum KSPIN_COMMUNICATION *v17; // [esp+4h] [ebp-E8h]
  struct CMediaType v18; // [esp+18h] [ebp-D4h] BYREF
  WCHAR SubKey[66]; // [esp+60h] [ebp-8Ch] BYREF

  CBasePin::CBasePin(
    this,
    a4.Data1 != 0 ? (const unsigned __int16 *)(a4.Data1 + 148) : 0,
    (struct CBaseFilter *)a4.Data1,
    a4.Data1 != 0 ? (struct CCritSec *)(a4.Data1 + 148) : 0,
    (int *)this,
    *(const unsigned __int16 **)a4.Data4,
    PINDIR_INPUT);
  this->m_pAllocator = 0;
  *(_WORD *)&this->m_bReadOnly = 0;
  memset(&this->m_SampleProps, 0, sizeof(this->m_SampleProps));
  this->m_PinFactoryId = a3;
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
  this->m_PinHandle = 0;
  this->m_DataTypeHandler = 0;
  this->m_UnkInner = 0;
  this->m_InterfaceHandler = 0;
  this->m_PropagatingAcquire = 0;
  this->m_MarshalData = 1;
  this->m_PendingIoCount = 0;
  this->m_PendingIoCompletedEvent = 0;
  InitializeCriticalSection(&this->m_IoCriticalSection.m_CritSec);
  this->m_RelativeRefCount = 1;
  this->m_QualitySupport = 0;
  this->m_MarshalerList.m_pFirst = 0;
  this->m_MarshalerList.m_pLast = 0;
  this->m_MarshalerList.m_Count = 0;
  this->m_MarshalerList.m_Cache.m_iCacheSize = 10;
  this->m_MarshalerList.m_Cache.m_iUsed = 0;
  this->m_MarshalerList.m_Cache.m_pHead = 0;
  this->m_DeliveryError = 0;
  this->m_pKsAllocator = 0;
  this->m_fPipeAllocator = 0;
  this->m_PinBusCacheInit = 0;
  this->m_FramingProp[0] = FramingProp_Uninitialized;
  this->m_FramingProp[1] = FramingProp_Uninitialized;
  this->m_FramingProp[2] = FramingProp_Uninitialized;
  this->m_AllocatorFramingEx[0] = 0;
  this->m_AllocatorFramingEx[1] = 0;
  this->m_AllocatorFramingEx[2] = 0;
  if ( (int)**(_DWORD **)&a4.Data2 >= 0 )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    this->m_PendingIoCompletedEvent = EventW;
    if ( EventW )
    {
      **(_DWORD **)&a4.Data2 = CKsProxy::GetPinFactoryCommunication(
                                 this->m_PinFactoryId,
                                 a4.Data1,
                                 (CKsProxy *)&this->m_OriginalCommunication,
                                 v15,
                                 v17);
      m_OriginalCommunication = this->m_OriginalCommunication;
      this->m_CurrentCommunication = m_OriginalCommunication;
      if ( m_OriginalCommunication == KSPIN_COMMUNICATION_NONE )
      {
        memset(&v18, 0, sizeof(v18));
        v18.lSampleSize = 1;
        v18.bFixedSizeSamples = 1;
        MediaType = CKsInputPin::GetMediaType(this, 0, &v18);
        **(_DWORD **)&a4.Data2 = MediaType;
        if ( MediaType >= 0 )
          CKsInputPin::SetMediaType(this, &v18);
        FreeMediaType(v16);
      }
      StringCchPrintfW(SubKey, 0x40u, L"PinFactory\\%u\\Interfaces", a3);
      v11 = &this->IKsPinEx;
      if ( !this )
        v11 = 0;
      AggregateMarshalers(*(HKEY *)(a4.Data1 + 296), SubKey, (int)&this->m_MarshalerList, (int)v11);
    }
    else
    {
      LastError = GetLastError();
      v13 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v13 = LastError;
      **(_DWORD **)&a4.Data2 = v13;
    }
  }
  return this;
}

```

## disassembly

```asm
0x10010e48  mov     edi, edi
0x10010e4a  push    ebp
0x10010e4b  mov     ebp, esp
0x10010e4d  sub     esp, 0E0h
0x10010e53  mov     eax, ___security_cookie
0x10010e58  xor     eax, ebp
0x10010e5a  mov     [ebp+var_8], eax
0x10010e5d  mov     edx, [ebp+arg_8.Data1]
0x10010e60  mov     eax, dword ptr [ebp+arg_8.Data4]
0x10010e63  push    ebx
0x10010e64  push    esi; enum KSPIN_COMMUNICATION *
0x10010e65  mov     esi, dword ptr [ebp+arg_8.Data2]
0x10010e68  mov     ebx, ecx
0x10010e6a  push    edi; struct _AMMediaType *
0x10010e6b  push    0; enum _PinDirection
0x10010e6d  push    eax; unsigned __int16 *
0x10010e6e  push    ecx; int *
0x10010e6f  mov     ecx, edx
0x10010e71  mov     [ebp+var_D8], edx
0x10010e77  neg     ecx
0x10010e79  mov     [ebp+var_DC], esi
0x10010e7f  lea     eax, [edx+94h]
0x10010e85  sbb     ecx, ecx
0x10010e87  and     ecx, eax
0x10010e89  push    ecx; struct CCritSec *
0x10010e8a  push    edx; struct CBaseFilter *
0x10010e8b  push    ecx; unsigned __int16 *
0x10010e8c  mov     ecx, ebx; this
0x10010e8e  call    ??0CBasePin@@QAE@PBGPAVCBaseFilter@@PAVCCritSec@@PAJ0W4_PinDirection@@@Z; CBasePin::CBasePin(ushort const *,CBaseFilter *,CCritSec *,long *,ushort const *,_PinDirection)
0x10010e93  xor     eax, eax
0x10010e95  push    30h ; '0'; Size
0x10010e97  push    eax; Val
0x10010e98  mov     [ebx+9Ch], eax
0x10010e9e  mov     [ebx+0A0h], ax
0x10010ea5  lea     eax, [ebx+0A8h]
0x10010eab  push    eax; void *
0x10010eac  call    _memset
0x10010eb1  mov     eax, [ebp+arg_4]
0x10010eb4  xor     ecx, ecx
0x10010eb6  add     esp, 0Ch
0x10010eb9  mov     [ebx+10Ch], eax
0x10010ebf  xor     edi, edi
0x10010ec1  mov     dword ptr [ebx], offset ??_7CKsInputPin@@6BCUnknown@@@; const CKsInputPin::`vftable'{for `CUnknown'}
0x10010ec7  lea     eax, [ebx+158h]
0x10010ecd  mov     dword ptr [ebx+0Ch], offset ??_7CKsInputPin@@6BIPin@@@; const CKsInputPin::`vftable'{for `IPin'}
0x10010ed4  inc     edi
0x10010ed5  mov     dword ptr [ebx+10h], offset ??_7CKsInputPin@@6BIQualityControl@@@; const CKsInputPin::`vftable'{for `IQualityControl'}
0x10010edc  push    eax; lpCriticalSection
0x10010edd  mov     dword ptr [ebx+98h], offset ??_7CKsInputPin@@6BCBaseInputPin@@@; const CKsInputPin::`vftable'{for `CBaseInputPin'}
0x10010ee7  mov     dword ptr [ebx+0D8h], offset ??_7CKsInputPin@@6BIKsObject@@@; const CKsInputPin::`vftable'{for `IKsObject'}
0x10010ef1  mov     dword ptr [ebx+0DCh], offset ??_7CKsInputPin@@6BIKsPinEx@@@; const CKsInputPin::`vftable'{for `IKsPinEx'}
0x10010efb  mov     dword ptr [ebx+0E0h], offset ??_7CKsInputPin@@6BIKsPinPipe@@@; const CKsInputPin::`vftable'{for `IKsPinPipe'}
0x10010f05  mov     dword ptr [ebx+0E4h], offset ??_7CKsInputPin@@6BISpecifyPropertyPages@@@; const CKsInputPin::`vftable'{for `ISpecifyPropertyPages'}
0x10010f0f  mov     dword ptr [ebx+0E8h], offset ??_7CKsInputPin@@6BIStreamBuilder@@@; const CKsInputPin::`vftable'{for `IStreamBuilder'}
0x10010f19  mov     dword ptr [ebx+0ECh], offset ??_7CKsInputPin@@6BIKsPropertySet@@@; const CKsInputPin::`vftable'{for `IKsPropertySet'}
0x10010f23  mov     dword ptr [ebx+0F0h], offset ??_7CKsInputPin@@6BIKsPinFactory@@@; const CKsInputPin::`vftable'{for `IKsPinFactory'}
0x10010f2d  mov     dword ptr [ebx+0F4h], offset ??_7CKsInputPin@@6BIKsControl@@@; const CKsInputPin::`vftable'{for `IKsControl'}
0x10010f37  mov     dword ptr [ebx+0F8h], offset ??_7CKsInputPin@@6BIKsAggregateControl@@@; const CKsInputPin::`vftable'{for `IKsAggregateControl'}
0x10010f41  mov     [ebx+0FCh], ecx
0x10010f47  mov     [ebx+100h], ecx
0x10010f4d  mov     [ebx+104h], ecx
0x10010f53  mov     [ebx+108h], ecx
0x10010f59  mov     [ebx+148h], ecx
0x10010f5f  mov     [ebx+14Ch], edi
0x10010f65  mov     [ebx+150h], ecx
0x10010f6b  mov     [ebx+154h], ecx
0x10010f71  call    ds:__imp__InitializeCriticalSection@4; InitializeCriticalSection(x)
0x10010f77  xor     ecx, ecx
0x10010f79  mov     [ebx+1C8h], edi
0x10010f7f  lea     eax, [ebx+170h]
0x10010f85  mov     [ebx+188h], ecx
0x10010f8b  mov     [eax], ecx
0x10010f8d  lea     edi, [ebx+1A4h]
0x10010f93  mov     [eax+4], ecx
0x10010f96  mov     [eax+8], ecx
0x10010f99  mov     dword ptr [eax+0Ch], 0Ah
0x10010fa0  mov     [eax+10h], ecx
0x10010fa3  mov     [eax+14h], ecx
0x10010fa6  xor     eax, eax
0x10010fa8  mov     [ebx+18Ch], ecx
0x10010fae  mov     [ebx+194h], ecx
0x10010fb4  mov     [ebx+1B0h], ecx
0x10010fba  mov     [ebx+1C4h], ecx
0x10010fc0  stosd
0x10010fc1  stosd
0x10010fc2  stosd
0x10010fc3  xor     eax, eax
0x10010fc5  lea     edi, [ebx+198h]
0x10010fcb  stosd
0x10010fcc  stosd
0x10010fcd  stosd
0x10010fce  cmp     [esi], ecx
0x10010fd0  jl      loc_100110C7
0x10010fd6  push    ecx; lpName
0x10010fd7  push    ecx; bInitialState
0x10010fd8  push    ecx; bManualReset
0x10010fd9  push    ecx; lpEventAttributes
0x10010fda  call    ds:__imp__CreateEventW@16; CreateEventW(x,x,x,x)
0x10010fe0  mov     [ebx+154h], eax
0x10010fe6  test    eax, eax
0x10010fe8  jz      loc_100110B1
0x10010fee  mov     edx, [ebx+10Ch]
0x10010ff4  lea     esi, [ebx+110h]
0x10010ffa  mov     ecx, [ebp+var_D8]
0x10011000  push    esi; this
0x10011001  call    ?GetPinFactoryCommunication@CKsProxy@@QAGJKPAW4KSPIN_COMMUNICATION@@@Z; CKsProxy::GetPinFactoryCommunication(ulong,KSPIN_COMMUNICATION *)
0x10011006  mov     edi, [ebp+var_DC]
0x1001100c  mov     [edi], eax
0x1001100e  mov     eax, [esi]
0x10011010  mov     [ebx+114h], eax
0x10011016  test    eax, eax
0x10011018  jnz     short loc_1001106A
0x1001101a  push    48h ; 'H'; Size
0x1001101c  push    eax; Val
0x1001101d  lea     eax, [ebp+var_D4]
0x10011023  push    eax; void *
0x10011024  call    _memset
0x10011029  xor     eax, eax
0x1001102b  add     esp, 0Ch
0x1001102e  inc     eax
0x1001102f  mov     ecx, ebx; this
0x10011031  mov     [ebp+var_D4.lSampleSize], eax
0x10011037  mov     [ebp+var_D4.bFixedSizeSamples], eax
0x1001103d  lea     eax, [ebp+var_D4]
0x10011043  push    eax; struct CMediaType *
0x10011044  push    0; int
0x10011046  call    ?GetMediaType@CKsInputPin@@UAEJHPAVCMediaType@@@Z; CKsInputPin::GetMediaType(int,CMediaType *)
0x1001104b  mov     [edi], eax
0x1001104d  test    eax, eax
0x1001104f  js      short loc_1001105F
0x10011051  lea     eax, [ebp+var_D4]
0x10011057  mov     ecx, ebx; this
0x10011059  push    eax; struct CMediaType *
0x1001105a  call    ?SetMediaType@CKsInputPin@@UAEJPBVCMediaType@@@Z; CKsInputPin::SetMediaType(CMediaType const *)
0x1001105f  lea     ecx, [ebp+var_D4]
0x10011065  call    ?FreeMediaType@@YGXAAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x1001106a  push    [ebp+arg_4]
0x1001106d  lea     eax, [ebp+SubKey]
0x10011073  push    offset aPinfactoryUInt; "PinFactory\\%u\\Interfaces"
0x10011078  push    40h ; '@'; unsigned int
0x1001107a  push    eax; unsigned __int16 *
0x1001107b  call    ?StringCchPrintfW@@YAJPAGIPBGZZ; StringCchPrintfW(ushort *,uint,ushort const *,...)
0x10011080  add     esp, 10h
0x10011083  lea     eax, [ebx+0DCh]
0x10011089  xor     ecx, ecx
0x1001108b  lea     edx, [ebp+SubKey]; lpSubKey
0x10011091  test    ebx, ebx
0x10011093  cmovz   eax, ecx
0x10011096  push    eax; int
0x10011097  lea     eax, [ebx+170h]
0x1001109d  push    eax; int
0x1001109e  mov     eax, [ebp+var_D8]
0x100110a4  mov     ecx, [eax+128h]; hKey
0x100110aa  call    ?AggregateMarshalers@@YGJPAUHKEY__@@PBGPAV?$CGenericList@VCAggregateMarshaler@@@@PAUIUnknown@@@Z; AggregateMarshalers(HKEY__ *,ushort const *,CGenericList<CAggregateMarshaler> *,IUnknown *)
0x100110af  jmp     short loc_100110C7
0x100110b1  call    ds:__imp__GetLastError@0; GetLastError()
0x100110b7  movzx   ecx, ax
0x100110ba  or      ecx, 80070000h
0x100110c0  test    eax, eax
0x100110c2  cmovle  ecx, eax
0x100110c5  mov     [esi], ecx
0x100110c7  mov     ecx, [ebp+var_8]
0x100110ca  mov     eax, ebx
0x100110cc  pop     edi
0x100110cd  pop     esi
0x100110ce  xor     ecx, ebp; StackCookie
0x100110d0  pop     ebx
0x100110d1  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100110d6  leave
0x100110d7  retn    24h ; '$'
```
