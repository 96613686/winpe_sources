# CKsOutputPin::ProcessCompleteConnect(IPin *)

- ea: `0x100150a0`
- end: `0x1001568d`
- name: `?ProcessCompleteConnect@CKsOutputPin@@UAGJPAUIPin@@@Z`
- size: `1517`
- prototype: `int(CKsOutputPin *__hidden this, struct IPin *)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x100063f1`
- `0x100064e5`
- `0x1000665f`
- `0x10010c0e`
- `0x100150a0`
- `0x1001fd03`
- `0x1001fe62`
- `0x1001feac`
- `0x10020525`
- `0x10020593`
- `0x10021163`
- `0x100218b2`
- `0x1002bd71`
- `0x1002d510`
- `0x1003a6fd`
- `0x1003af9d`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10015537`
- `KERNEL32!GetLastError` at `0x10015587`
- `KERNEL32!GetLastError` at `0x100155b0`
- `KERNEL32!GetLastError` at `0x10015537`
- `KERNEL32!GetLastError` at `0x10015587`
- `KERNEL32!GetLastError` at `0x100155b0`
- `KERNEL32!CreateEventW` at `0x10015408`
- `KERNEL32!CreateEventW` at `0x10015408`
- `KERNEL32!CloseHandle` at `0x100154e4`
- `KERNEL32!CloseHandle` at `0x1001555c`
- `KERNEL32!CloseHandle` at `0x10015608`
- `KERNEL32!CloseHandle` at `0x100154e4`
- `KERNEL32!CloseHandle` at `0x1001555c`
- `KERNEL32!CloseHandle` at `0x10015608`
- `ole32!CoCreateInstance` at `0x1001531e`
- `ole32!CoCreateInstance` at `0x1001531e`

## pseudocode

```c
int __stdcall CKsOutputPin::ProcessCompleteConnect(CKsOutputPin *this, struct IPin *a2)
{
  KSPIN_COMMUNICATION *p_m_CurrentCommunication; // esi
  IKsPinEx *v3; // eax
  int CompatibleInterface; // edi
  int result; // eax
  int *v6; // eax
  void **p_m_PinHandle; // esi
  int PinHandle; // eax
  int Instance; // edi
  CBaseFilter *m_pFilter; // edx
  IKsInterfaceHandler **p_m_InterfaceHandler; // esi
  void *v12; // eax
  IKsControl_vtbl *v13; // eax
  _DWORD *v14; // esi
  HANDLE EventW; // eax
  IKsControl_vtbl *v16; // eax
  char LastError; // al
  char v18; // al
  signed int v19; // eax
  IKsInterfaceHandler *m_InterfaceHandler; // ecx
  IUnknown *m_UnkInner; // ecx
  KSPIN_COMMUNICATION m_OriginalCommunication; // eax
  void *v23; // [esp+28h] [ebp-58h]
  void *v24; // [esp+28h] [ebp-58h]
  int v25; // [esp+2Ch] [ebp-54h]
  struct CBasePin *v26; // [esp+30h] [ebp-50h]
  struct IKsPin *v27; // [esp+30h] [ebp-50h]
  void *v28; // [esp+30h] [ebp-50h]
  struct IKsPin *v29; // [esp+34h] [ebp-4Ch]
  struct KSIDENTIFIER *v30; // [esp+34h] [ebp-4Ch]
  int v31; // [esp+3Ch] [ebp-44h]
  _DWORD **v32; // [esp+40h] [ebp-40h] BYREF
  void *v33; // [esp+44h] [ebp-3Ch]
  void *Block; // [esp+48h] [ebp-38h]
  int v35; // [esp+4Ch] [ebp-34h] BYREF
  struct IKsPin v36[6]; // [esp+50h] [ebp-30h] BYREF
  struct IKsPin v37[6]; // [esp+68h] [ebp-18h] BYREF

  v31 = 0;
  if ( this->m_PinHandle )
  {
    Block = &this->IKsPinEx;
    goto LABEL_25;
  }
  if ( ((int (__thiscall *)(HRESULT (__stdcall *)(IUnknown *, const _GUID *, void **), struct IPin *, GUID *, _DWORD ***))a2->QueryInterface)(
         a2->QueryInterface,
         a2,
         &_GUID_b61178d1_a2d9_11cf_9e53_00aa00a216a1,
         &v32) >= 0 )
  {
    p_m_CurrentCommunication = &this->m_CurrentCommunication;
    if ( this->m_OriginalCommunication == KSPIN_COMMUNICATION_BOTH )
      *p_m_CurrentCommunication = ChooseCommunicationMethod(v26, v29);
    v3 = &this->IKsPinEx;
    Block = &this->IKsPinEx;
    if ( !this )
      v3 = 0;
    v33 = v3;
    CompatibleInterface = FindCompatibleInterface(v37, (struct IKsPin *)v26, (struct KSIDENTIFIER *)v29);
    if ( CompatibleInterface >= 0 )
    {
      CompatibleInterface = FindCompatibleMedium(v36, v27, v30);
      if ( CompatibleInterface >= 0 )
      {
        if ( CompatibleInterface == 1 )
        {
          v31 = 0;
          this->m_MarshalData = 1;
        }
        else
        {
          if ( *p_m_CurrentCommunication == KSPIN_COMMUNICATION_SOURCE )
          {
            CompatibleInterface = ((int (__thiscall *)(_DWORD, _DWORD **, GUID *, int *))**v32)(
                                    **v32,
                                    v32,
                                    &_GUID_423c13a2_2070_11d0_9ef7_00aa00a216a1,
                                    &v35);
            if ( CompatibleInterface >= 0 )
            {
              CompatibleInterface = ((int (__thiscall *)(_DWORD, _DWORD **, struct IKsPin *, struct IKsPin *))(*v32)[5])(
                                      (*v32)[5],
                                      v32,
                                      v37,
                                      v36);
              v31 = (*(int (__thiscall **)(_DWORD, int))(*(_DWORD *)v35 + 12))(*(_DWORD *)(*(_DWORD *)v35 + 12), v35);
              (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v35 + 8))(*(_DWORD *)(*(_DWORD *)v35 + 8), v35);
            }
          }
          else
          {
            v31 = 0;
          }
          this->m_MarshalData = 0;
        }
      }
    }
    ((void (__thiscall *)(_DWORD, _DWORD **))(*v32)[2])((*v32)[2], v32);
    if ( CompatibleInterface < 0 )
      return CompatibleInterface;
    goto LABEL_22;
  }
  this->m_CurrentCommunication = KSPIN_COMMUNICATION_SINK;
  v6 = (int *)&this->IKsPinEx;
  Block = &this->IKsPinEx;
  if ( !this )
    v6 = 0;
  v33 = v6;
  result = FindCompatiblePinFactoryIdentifier(
             0,
             v6,
             (struct IKsPin *)5,
             v37,
             (unsigned int)v26,
             (struct KSIDENTIFIER *)v29);
  if ( result >= 0 )
  {
    v31 = 0;
    v36[0] = (struct IKsPin)_GUID_4747b320_62ce_11cf_a5d6_28db04c10000.Data1;
    v36[1] = *(struct IKsPin *)&_GUID_4747b320_62ce_11cf_a5d6_28db04c10000.Data2;
    v36[2] = *(struct IKsPin *)_GUID_4747b320_62ce_11cf_a5d6_28db04c10000.Data4;
    v36[3] = *(struct IKsPin *)&_GUID_4747b320_62ce_11cf_a5d6_28db04c10000.Data4[4];
    v36[4].__vftable = 0;
    v36[5].__vftable = 0;
LABEL_22:
    p_m_PinHandle = &this->m_PinHandle;
    PinHandle = CreatePinHandle(
                  (struct KSIDENTIFIER *)v31,
                  (struct KSIDENTIFIER *)&this->m_mt,
                  this->m_pFilter,
                  (struct CMediaType *)this->m_PinFactoryId,
                  (struct CKsProxy *)0x80000000,
                  (unsigned int)&this->m_PinHandle,
                  (unsigned int)v27,
                  (void **)v30);
    LOBYTE(Instance) = PinHandle;
    v31 = PinHandle;
    if ( PinHandle < 0 )
    {
LABEL_56:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        WPP_SF_SSd(*((_QWORD *)WPP_GLOBAL_Control + 2), (int)this->m_pFilter->m_pName, (int)this->m_pName, Instance);
      if ( *p_m_PinHandle )
      {
        CloseHandle(*p_m_PinHandle);
        *p_m_PinHandle = 0;
        this->m_QualitySupport = 0;
      }
      m_InterfaceHandler = this->m_InterfaceHandler;
      if ( m_InterfaceHandler )
      {
        this->m_InterfaceHandler = 0;
        ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IKsInterfaceHandler *))m_InterfaceHandler->Release)(
          m_InterfaceHandler->Release,
          m_InterfaceHandler);
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
      m_OriginalCommunication = this->m_OriginalCommunication;
      this->m_MarshalData = 1;
      this->m_CurrentCommunication = m_OriginalCommunication;
      return v31;
    }
    m_pFilter = this->m_pFilter;
    qmemcpy(&this->m_CurrentInterface, v37, sizeof(this->m_CurrentInterface));
    v25 = (int)v33;
    qmemcpy(&this->m_CurrentMedium, v36, sizeof(this->m_CurrentMedium));
    AggregateSets((DWORD)this->m_PinHandle, (HKEY)m_pFilter[3].m_pLock, &this->m_MarshalerList.m_pFirst, v25);
    this->m_QualitySupport = VerifyQualitySupport(v28);
LABEL_25:
    p_m_InterfaceHandler = &this->m_InterfaceHandler;
    if ( !this->m_InterfaceHandler && this->m_CurrentCommunication != KSPIN_COMMUNICATION_BRIDGE )
    {
      Instance = CoCreateInstance(
                   &this->m_CurrentInterface.Set,
                   0,
                   0x401u,
                   &_GUID_d3abc7e0_9a61_11d0_a40d_00a0c9223196,
                   (LPVOID *)&this->m_InterfaceHandler);
      v31 = Instance;
      if ( *p_m_InterfaceHandler )
      {
        v12 = Block;
        if ( !this )
          v12 = 0;
        ((void (__thiscall *)(HRESULT (__stdcall *)(IKsInterfaceHandler *, IKsPin *), IKsInterfaceHandler *, void *))(*p_m_InterfaceHandler)->KsSetPin)(
          (*p_m_InterfaceHandler)->KsSetPin,
          *p_m_InterfaceHandler,
          v12);
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), (int)this->m_pFilter->m_pName, (int)this->m_pName);
      }
      if ( Instance < 0 )
        goto LABEL_55;
    }
    if ( !this->m_hEOSevent )
    {
      v37[0] = (struct IKsPin)_GUID_7f4bcbe0_9ea5_11cf_a5d6_28db04c10000.Data1;
      v37[1] = *(struct IKsPin *)&_GUID_7f4bcbe0_9ea5_11cf_a5d6_28db04c10000.Data2;
      v37[2] = *(struct IKsPin *)_GUID_7f4bcbe0_9ea5_11cf_a5d6_28db04c10000.Data4;
      v37[3] = *(struct IKsPin *)&_GUID_7f4bcbe0_9ea5_11cf_a5d6_28db04c10000.Data4[4];
      v37[4].__vftable = (IKsPin_vtbl *)4;
      v13 = this->IKsControl::IUnknown::__vftable;
      v37[5].__vftable = (IKsPin_vtbl *)512;
      if ( ((int (__thiscall *)(HRESULT (__stdcall *)(IKsControl *, KSIDENTIFIER *, unsigned int, void *, unsigned int, unsigned int *), IKsControl *, struct IKsPin *, int, _DWORD, _DWORD, int *))v13->KsEvent)(
             v13->KsEvent,
             &this->IKsControl,
             v37,
             24,
             0,
             0,
             &v35) >= 0 )
      {
        v14 = operator new(0x18u);
        Block = v14;
        if ( !v14 )
        {
          LOBYTE(Instance) = 14;
          v31 = -2147024882;
          goto LABEL_55;
        }
        v37[5].__vftable = (IKsPin_vtbl *)1;
        v36[0].__vftable = (IKsPin_vtbl *)1;
        EventW = CreateEventW(0, 0, 0, 0);
        this->m_hEOSevent = EventW;
        if ( EventW )
        {
          *((_BYTE *)v14 + 8) = 1;
          v14[1] = 0;
          *v14 = 0;
          v14[3] = this->m_hEOSevent;
          v14[4] = CKsOutputPin::EOSEventHandler;
          v14[5] = this;
          v36[1] = (struct IKsPin)this->m_hEOSevent;
          v16 = this->IKsControl::IUnknown::__vftable;
          v36[2].__vftable = 0;
          v36[3].__vftable = 0;
          Instance = ((int (__thiscall *)(HRESULT (__stdcall *)(IKsControl *, KSIDENTIFIER *, unsigned int, void *, unsigned int, unsigned int *), IKsControl *, struct IKsPin *, int, struct IKsPin *, int, int *))v16->KsEvent)(
                       v16->KsEvent,
                       &this->IKsControl,
                       v37,
                       24,
                       v36,
                       16,
                       &v35);
          v31 = Instance;
          if ( Instance < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
            {
              LastError = GetLastError();
              WPP_SF_q(
                0x11u,
                &WPP_673e2124b19330a2d80119fad92a0606_Traceguids,
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                LastError);
            }
            CloseHandle(this->m_hEOSevent);
            v24 = Block;
            this->m_hEOSevent = 0;
            operator delete(v24, 0x18u);
            goto LABEL_55;
          }
          if ( (this->m_pAsyncItemHandler
             || (Instance = this->InitializeAsyncThread(this), v31 = Instance, Instance >= 0))
            && this->m_pAsyncItemHandler )
          {
            CAsyncItemHandler::QueueAsyncItem((CAsyncItemHandler *)v26, (struct _ASYNC_ITEM *)v29);
          }
          else
          {
            ((void (__thiscall *)(HRESULT (__stdcall *)(IKsControl *, KSIDENTIFIER *, unsigned int, void *, unsigned int, unsigned int *), IKsControl *, _DWORD, _DWORD, struct IKsPin *, int, int *))this->KsEvent)(
              this->KsEvent,
              &this->IKsControl,
              0,
              0,
              v36,
              16,
              &v35);
            CloseHandle(this->m_hEOSevent);
            v23 = Block;
            this->m_hEOSevent = 0;
            operator delete(v23, 0x18u);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
              WPP_SF_(0x10u, &WPP_673e2124b19330a2d80119fad92a0606_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2));
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
          {
            v18 = GetLastError();
            WPP_SF_q(0x12u, &WPP_673e2124b19330a2d80119fad92a0606_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2), v18);
          }
          operator delete(v14, 0x18u);
          v19 = GetLastError();
          Instance = (unsigned __int16)v19 | 0x80070000;
          if ( v19 <= 0 )
            Instance = v19;
          v31 = Instance;
        }
        if ( Instance < 0 )
        {
LABEL_55:
          p_m_PinHandle = &this->m_PinHandle;
          goto LABEL_56;
        }
      }
    }
    return v31;
  }
  return result;
}

```

## disassembly

```asm
0x100150a0  mov     edi, edi
0x100150a2  push    ebp
0x100150a3  mov     ebp, esp
0x100150a5  and     esp, 0FFFFFFF8h
0x100150a8  sub     esp, 44h
0x100150ab  push    ebx
0x100150ac  mov     ebx, [ebp+this]
0x100150af  push    esi; struct _ASYNC_ITEM *
0x100150b0  push    edi; this
0x100150b1  mov     [esp+50h+var_44], 0
0x100150b9  cmp     dword ptr [ebx+164h], 0
0x100150c0  jnz     loc_100152EA
0x100150c6  mov     ecx, [ebp+arg_4]
0x100150c9  mov     eax, [ecx]
0x100150cb  mov     esi, [eax]
0x100150cd  lea     eax, [esp+50h+var_40]
0x100150d1  push    eax
0x100150d2  push    offset __GUID_b61178d1_a2d9_11cf_9e53_00aa00a216a1
0x100150d7  push    ecx
0x100150d8  mov     ecx, esi; this
0x100150da  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x100150e0  call    esi
0x100150e2  test    eax, eax
0x100150e4  js      loc_10015212
0x100150ea  cmp     dword ptr [ebx+188h], 3
0x100150f1  lea     esi, [ebx+18Ch]
0x100150f7  jnz     short loc_10015106
0x100150f9  mov     edx, [esp+50h+var_40]
0x100150fd  mov     ecx, ebx
0x100150ff  call    ?ChooseCommunicationMethod@@YG?AW4KSPIN_COMMUNICATION@@PAVCBasePin@@PAUIKsPin@@@Z; ChooseCommunicationMethod(CBasePin *,IKsPin *)
0x10015104  mov     [esi], eax
0x10015106  mov     edx, [esp+50h+var_40]
0x1001510a  lea     eax, [ebx+110h]
0x10015110  xor     ecx, ecx
0x10015112  mov     [esp+50h+Block], eax
0x10015116  test    ebx, ebx
0x10015118  cmovz   eax, ecx
0x1001511b  lea     ecx, [esp+50h+var_18]
0x1001511f  push    ecx; struct IKsPin *
0x10015120  mov     ecx, eax
0x10015122  mov     [esp+54h+var_3C], eax
0x10015126  call    ?FindCompatibleInterface@@YGJPAUIKsPin@@0PAUKSIDENTIFIER@@@Z; FindCompatibleInterface(IKsPin *,IKsPin *,KSIDENTIFIER *)
0x1001512b  mov     edi, eax
0x1001512d  test    edi, edi
0x1001512f  js      loc_100151F3
0x10015135  mov     edx, [esp+50h+var_40]
0x10015139  lea     eax, [esp+50h+var_30]
0x1001513d  mov     ecx, [esp+50h+var_3C]
0x10015141  push    eax; struct IKsPin *
0x10015142  call    ?FindCompatibleMedium@@YGJPAUIKsPin@@0PAUKSIDENTIFIER@@@Z; FindCompatibleMedium(IKsPin *,IKsPin *,KSIDENTIFIER *)
0x10015147  mov     edi, eax
0x10015149  test    edi, edi
0x1001514b  js      loc_100151F3
0x10015151  xor     eax, eax
0x10015153  inc     eax
0x10015154  cmp     edi, eax
0x10015156  jnz     short loc_1001516B
0x10015158  mov     [esp+50h+var_44], 0
0x10015160  mov     [ebx+1C0h], eax
0x10015166  jmp     loc_100151F3
0x1001516b  cmp     dword ptr [esi], 2
0x1001516e  jnz     short loc_100151E1
0x10015170  mov     ecx, [esp+50h+var_40]
0x10015174  mov     eax, [ecx]
0x10015176  mov     esi, [eax]
0x10015178  lea     eax, [esp+50h+var_34]
0x1001517c  push    eax
0x1001517d  push    offset __GUID_423c13a2_2070_11d0_9ef7_00aa00a216a1
0x10015182  push    ecx
0x10015183  mov     ecx, esi; this
0x10015185  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1001518b  call    esi
0x1001518d  mov     edi, eax
0x1001518f  test    edi, edi
0x10015191  js      short loc_100151E9
0x10015193  mov     ecx, [esp+50h+var_40]
0x10015197  mov     eax, [ecx]
0x10015199  mov     esi, [eax+14h]
0x1001519c  lea     eax, [esp+50h+var_30]
0x100151a0  push    eax
0x100151a1  lea     eax, [esp+54h+var_18]
0x100151a5  push    eax
0x100151a6  push    ecx
0x100151a7  mov     ecx, esi; this
0x100151a9  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x100151af  call    esi
0x100151b1  mov     edi, eax
0x100151b3  mov     eax, [esp+50h+var_34]
0x100151b7  push    eax
0x100151b8  mov     ecx, [eax]
0x100151ba  mov     esi, [ecx+0Ch]
0x100151bd  mov     ecx, esi; this
0x100151bf  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x100151c5  call    esi
0x100151c7  mov     ecx, [esp+50h+var_34]
0x100151cb  push    ecx
0x100151cc  mov     [esp+54h+var_44], eax
0x100151d0  mov     edx, [ecx]
0x100151d2  mov     esi, [edx+8]
0x100151d5  mov     ecx, esi; this
0x100151d7  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x100151dd  call    esi
0x100151df  jmp     short loc_100151E9
0x100151e1  mov     [esp+50h+var_44], 0
0x100151e9  mov     dword ptr [ebx+1C0h], 0
0x100151f3  mov     eax, [esp+50h+var_40]
0x100151f7  push    eax
0x100151f8  mov     ecx, [eax]
0x100151fa  mov     esi, [ecx+8]
0x100151fd  mov     ecx, esi; this
0x100151ff  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10015205  call    esi
0x10015207  test    edi, edi
0x10015209  jns     short loc_10015264
0x1001520b  mov     eax, edi
0x1001520d  jmp     loc_10015684
0x10015212  xor     ecx, ecx
0x10015214  mov     dword ptr [ebx+18Ch], 1
0x1001521e  lea     eax, [ebx+110h]
0x10015224  test    ebx, ebx
0x10015226  mov     [esp+50h+Block], eax
0x1001522a  cmovz   eax, ecx
0x1001522d  lea     ecx, [esp+50h+var_18]
0x10015231  push    ecx; struct IKsPin *
0x10015232  push    5; struct IKsPin *
0x10015234  xor     edx, edx
0x10015236  mov     [esp+58h+var_3C], eax
0x1001523a  mov     ecx, eax
0x1001523c  call    ?FindCompatiblePinFactoryIdentifier@@YGJPAUIKsPin@@0KPAUKSIDENTIFIER@@@Z; FindCompatiblePinFactoryIdentifier(IKsPin *,IKsPin *,ulong,KSIDENTIFIER *)
0x10015241  test    eax, eax
0x10015243  js      loc_10015684
0x10015249  mov     esi, offset __GUID_4747b320_62ce_11cf_a5d6_28db04c10000
0x1001524e  lea     edi, [esp+50h+var_30]
0x10015252  xor     eax, eax
0x10015254  mov     [esp+50h+var_44], eax
0x10015258  movsd
0x10015259  movsd
0x1001525a  movsd
0x1001525b  movsd
0x1001525c  mov     [esp+50h+var_20], eax
0x10015260  mov     [esp+50h+var_1C], eax
0x10015264  lea     esi, [ebx+164h]
0x1001526a  push    esi; unsigned int
0x1001526b  push    80000000h; struct CKsProxy *
0x10015270  push    dword ptr [ebx+184h]; struct CMediaType *
0x10015276  lea     eax, [ebx+34h]
0x10015279  push    dword ptr [ebx+28h]; void *
0x1001527c  lea     edx, [esp+60h+var_30]
0x10015280  push    eax; struct KSIDENTIFIER *
0x10015281  push    [esp+64h+var_44]; struct KSIDENTIFIER *
0x10015285  lea     ecx, [esp+68h+var_18]
0x10015289  call    ?CreatePinHandle@@YGJAAUKSIDENTIFIER@@0PAXPAVCMediaType@@PAVCKsProxy@@KKPAPAX@Z; CreatePinHandle(KSIDENTIFIER &,KSIDENTIFIER &,void *,CMediaType *,CKsProxy *,ulong,ulong,void * *)
0x1001528e  mov     edi, eax
0x10015290  mov     [esp+50h+var_44], edi
0x10015294  test    edi, edi
0x10015296  js      loc_100155D6
0x1001529c  mov     edx, [ebx+28h]
0x1001529f  lea     edi, [ebx+190h]
0x100152a5  push    6
0x100152a7  pop     ecx
0x100152a8  push    6
0x100152aa  lea     esi, [esp+54h+var_18]
0x100152ae  rep movsd
0x100152b0  pop     ecx
0x100152b1  push    [esp+50h+var_3C]
0x100152b5  lea     edi, [ebx+1A8h]
0x100152bb  lea     esi, [esp+54h+var_30]
0x100152bf  rep movsd
0x100152c1  mov     edx, [edx+128h]
0x100152c7  lea     eax, [ebx+1D4h]
0x100152cd  lea     esi, [ebx+164h]
0x100152d3  mov     ecx, [esi]
0x100152d5  push    eax
0x100152d6  call    ?AggregateSets@@YGJPAXPAUHKEY__@@PAV?$CGenericList@VCAggregateMarshaler@@@@PAUIUnknown@@@Z; AggregateSets(void *,HKEY__ *,CGenericList<CAggregateMarshaler> *,IUnknown *)
0x100152db  mov     ecx, [esi]
0x100152dd  call    ?VerifyQualitySupport@@YGHPAX@Z; VerifyQualitySupport(void *)
0x100152e2  mov     [ebx+234h], eax
0x100152e8  jmp     short loc_100152F4
0x100152ea  lea     eax, [ebx+110h]
0x100152f0  mov     [esp+50h+Block], eax
0x100152f4  lea     esi, [ebx+180h]
0x100152fa  cmp     dword ptr [esi], 0
0x100152fd  lea     eax, [ebx+18Ch]
0x10015303  lea     ecx, [ebx+190h]
0x10015309  jnz     short loc_1001537F
0x1001530b  cmp     dword ptr [eax], 4
0x1001530e  jz      short loc_1001537F
0x10015310  push    esi; ppv
0x10015311  push    offset __GUID_d3abc7e0_9a61_11d0_a40d_00a0c9223196; riid
0x10015316  push    401h; dwClsContext
0x1001531b  push    0; pUnkOuter
0x1001531d  push    ecx; rclsid
0x1001531e  call    ds:__imp__CoCreateInstance@20; CoCreateInstance(x,x,x,x,x)
0x10015324  mov     ecx, [esi]
0x10015326  mov     edi, eax
0x10015328  mov     [esp+50h+var_44], edi
0x1001532c  test    ecx, ecx
0x1001532e  jz      short loc_1001534D
0x10015330  mov     eax, [esp+50h+Block]
0x10015334  xor     edx, edx
0x10015336  mov     esi, [ecx]
0x10015338  test    ebx, ebx
0x1001533a  cmovz   eax, edx
0x1001533d  push    eax
0x1001533e  push    ecx
0x1001533f  mov     ecx, [esi+0Ch]; this
0x10015342  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10015348  call    dword ptr [esi+0Ch]
0x1001534b  jmp     short loc_10015377
0x1001534d  mov     ecx, _WPP_GLOBAL_Control
0x10015353  cmp     ecx, offset _WPP_GLOBAL_Control
0x10015359  jz      short loc_10015377
0x1001535b  push    dword ptr [ebx+14h]; int
0x1001535e  mov     eax, [ebx+28h]
0x10015361  mov     edx, offset _WPP_673e2124b19330a2d80119fad92a0606_Traceguids
0x10015366  push    dword ptr [eax+3Ch]; int
0x10015369  push    dword ptr [ecx+14h]
0x1001536c  push    dword ptr [ecx+10h]; LoggerHandle
0x1001536f  push    0Fh
0x10015371  pop     ecx
0x10015372  call    _WPP_SF_SS@24; WPP_SF_SS(x,x,x,x,x,x)
0x10015377  test    edi, edi
0x10015379  js      loc_100155D0
0x1001537f  cmp     dword ptr [ebx+290h], 0
0x10015386  jnz     loc_10015680
0x1001538c  mov     esi, offset __GUID_7f4bcbe0_9ea5_11cf_a5d6_28db04c10000
0x10015391  lea     edi, [esp+50h+var_18]
0x10015395  movsd
0x10015396  movsd
0x10015397  movsd
0x10015398  movsd
0x10015399  lea     edi, [ebx+130h]
0x1001539f  mov     [esp+50h+var_8], 4
0x100153a7  mov     eax, [edi]
0x100153a9  mov     [esp+50h+var_4], 200h
0x100153b1  mov     esi, [eax+14h]
0x100153b4  lea     eax, [esp+50h+var_34]
0x100153b8  push    eax
0x100153b9  push    0
0x100153bb  push    0
0x100153bd  push    18h
0x100153bf  lea     eax, [esp+60h+var_18]
0x100153c3  mov     ecx, esi; this
0x100153c5  push    eax
0x100153c6  push    edi
0x100153c7  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x100153cd  call    esi
0x100153cf  test    eax, eax
0x100153d1  js      loc_10015680
0x100153d7  push    18h; Size
0x100153d9  call    ??2@YAPAXI@Z; operator new(uint)
0x100153de  mov     esi, eax
0x100153e0  mov     [esp+54h+Block], esi
0x100153e4  pop     ecx
0x100153e5  test    esi, esi
0x100153e7  jnz     short loc_100153F7
0x100153e9  mov     edi, 8007000Eh
0x100153ee  mov     [esp+50h+var_44], edi
0x100153f2  jmp     loc_100155D0
0x100153f7  xor     eax, eax
0x100153f9  inc     eax
0x100153fa  mov     [esp+50h+var_4], eax
0x100153fe  mov     [esp+50h+var_30.__vftable], eax
0x10015402  xor     eax, eax
0x10015404  push    eax; lpName
0x10015405  push    eax; bInitialState
0x10015406  push    eax; bManualReset
0x10015407  push    eax; lpEventAttributes
0x10015408  call    ds:__imp__CreateEventW@16; CreateEventW(x,x,x,x)
0x1001540e  mov     [ebx+290h], eax
0x10015414  test    eax, eax
0x10015416  jz      loc_1001557B
0x1001541c  xor     ecx, ecx
0x1001541e  mov     byte ptr [esi+8], 1
0x10015422  mov     [esi+4], ecx
0x10015425  mov     [esi], ecx
0x10015427  mov     eax, [ebx+290h]
0x1001542d  mov     [esi+0Ch], eax
0x10015430  mov     dword ptr [esi+10h], offset ?EOSEventHandler@CKsOutputPin@@SGXW4ASYNC_ITEM_STATUS@@PAU_ASYNC_ITEM@@@Z; CKsOutputPin::EOSEventHandler(ASYNC_ITEM_STATUS,_ASYNC_ITEM *)
0x10015437  mov     [esi+14h], ebx
0x1001543a  mov     eax, [ebx+290h]
0x10015440  mov     [esp+50h+var_2C], eax
0x10015444  mov     eax, [edi]
0x10015446  mov     [esp+50h+var_28], ecx
0x1001544a  mov     dword ptr [esp+50h+var_24], ecx
0x1001544e  mov     esi, [eax+14h]
0x10015451  lea     eax, [esp+50h+var_34]
0x10015455  push    eax
0x10015456  push    10h
0x10015458  lea     eax, [esp+58h+var_30]
0x1001545c  mov     ecx, esi; this
0x1001545e  push    eax
0x1001545f  push    18h
0x10015461  lea     eax, [esp+60h+var_18]
0x10015465  push    eax
0x10015466  push    edi
0x10015467  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1001546d  call    esi
0x1001546f  mov     edi, eax
0x10015471  mov     [esp+50h+var_44], edi
  ... truncated ...
```
