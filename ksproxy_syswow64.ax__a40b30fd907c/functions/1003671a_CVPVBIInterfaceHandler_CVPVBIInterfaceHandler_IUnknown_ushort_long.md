# CVPVBIInterfaceHandler::CVPVBIInterfaceHandler(IUnknown *,ushort *,long *)

- ea: `0x1003671a`
- end: `0x10036878`
- name: `??0CVPVBIInterfaceHandler@@AAE@PAUIUnknown@@PAGPAJ@Z`
- size: `350`
- prototype: `CVPVBIInterfaceHandler *__thiscall(CVPVBIInterfaceHandler *__hidden this, struct IUnknown *, unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x100366e0`

## callees

- `0x100063f1`
- `0x1000665f`
- `0x1001f3b0`
- `0x10035833`
- `0x10035861`
- `0x10035aeb`
- `0x1003671a`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10036838`
- `KERNEL32!GetLastError` at `0x10036838`
- `KERNEL32!CreateEventW` at `0x10036765`
- `KERNEL32!CreateEventW` at `0x10036765`

## pseudocode

```c
CVPVBIInterfaceHandler *__thiscall CVPVBIInterfaceHandler::CVPVBIInterfaceHandler(
        CVPVBIInterfaceHandler *this,
        struct IUnknown *a2,
        unsigned __int16 *a3,
        int *a4)
{
  HANDLE EventW; // eax
  signed int Thread; // eax
  void *m_NotifyEventHandle; // eax
  int v8; // eax
  int v9; // edx
  int v10; // esi
  signed int LastError; // eax
  unsigned int v12; // ecx
  void *m_ObjectHandle; // [esp-1Ch] [ebp-44h]
  DWORD BytesReturned; // [esp+Ch] [ebp-1Ch] BYREF
  _DWORD InBuffer[6]; // [esp+10h] [ebp-18h] BYREF

  CVPInterfaceHandler::CVPInterfaceHandler(
    this,
    a2,
    (unsigned __int16 *)this,
    a4,
    &_GUID_ec529b00_1a1f_11d1_bad9_00609744111a,
    &_GUID_ec529b01_1a1f_11d1_bad9_00609744111a);
  this->CVPInterfaceHandler::CUnknown::INonDelegatingUnknown::__vftable = (CVPVBIInterfaceHandler_vtbl *)&CVPVBIInterfaceHandler::`vftable'{for `CUnknown'};
  this->CVPInterfaceHandler::IDistributorNotify::IUnknown::__vftable = (IDistributorNotify_vtbl *)&CVPVideoInterfaceHandler::`vftable'{for `IDistributorNotify'};
  this->IVPVBIConfig::IVPBaseConfig::IUnknown::__vftable = (IVPVBIConfig_vtbl *)&CVPVBIInterfaceHandler::`vftable';
  if ( this->m_ObjectHandle )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    this->m_NotifyEventHandle = EventW;
    if ( EventW )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        WPP_SF_q(
          0x1Fu,
          &WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids,
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (char)EventW);
      Thread = CVPInterfaceHandler::CreateThread(this);
      if ( Thread < 0 )
      {
        *a4 = Thread;
      }
      else
      {
        m_NotifyEventHandle = this->m_NotifyEventHandle;
        this->m_EventData.EventHandle.Reserved[0] = 0;
        this->m_EventData.EventHandle.Reserved[1] = 0;
        BytesReturned = 0;
        this->m_EventData.EventHandle.Event = m_NotifyEventHandle;
        this->m_EventData.NotificationType = 1;
        InBuffer[0] = _GUID_ec529b01_1a1f_11d1_bad9_00609744111a.Data1;
        InBuffer[1] = *(_DWORD *)&_GUID_ec529b01_1a1f_11d1_bad9_00609744111a.Data2;
        m_ObjectHandle = this->m_ObjectHandle;
        InBuffer[2] = *(_DWORD *)_GUID_ec529b01_1a1f_11d1_bad9_00609744111a.Data4;
        InBuffer[3] = *(_DWORD *)&_GUID_ec529b01_1a1f_11d1_bad9_00609744111a.Data4[4];
        InBuffer[4] = 0;
        InBuffer[5] = 1;
        v8 = KsSynchronousDeviceControl(
               m_ObjectHandle,
               0x2F0007u,
               InBuffer,
               0x18u,
               &this->m_EventData,
               0x10u,
               &BytesReturned);
        v10 = v8;
        if ( v8 >= 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
            WPP_SF_(0x21u, &WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2));
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
            WPP_SF_L(0x20u, v9, *((_QWORD *)WPP_GLOBAL_Control + 2), v8);
          *a4 = v10;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v12 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v12 = LastError;
      *a4 = v12;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        WPP_SF_(0x22u, &WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2));
    }
  }
  return this;
}

```

## disassembly

```asm
0x1003671a  mov     edi, edi
0x1003671c  push    ebp
0x1003671d  mov     ebp, esp
0x1003671f  and     esp, 0FFFFFFF8h
0x10036722  sub     esp, 1Ch
0x10036725  push    ebx
0x10036726  push    esi
0x10036727  mov     esi, [ebp+arg_8]
0x1003672a  mov     ebx, ecx
0x1003672c  push    edi
0x1003672d  push    offset __GUID_ec529b01_1a1f_11d1_bad9_00609744111a; struct _GUID *
0x10036732  push    offset __GUID_ec529b00_1a1f_11d1_bad9_00609744111a; struct _GUID *
0x10036737  push    esi; int *
0x10036738  push    ecx; unsigned __int16 *
0x10036739  push    [ebp+arg_0]; struct IUnknown *
0x1003673c  call    ??0CVPInterfaceHandler@@QAE@PAUIUnknown@@PAGPAJPBU_GUID@@3@Z; CVPInterfaceHandler::CVPInterfaceHandler(IUnknown *,ushort *,long *,_GUID const *,_GUID const *)
0x10036741  xor     edi, edi
0x10036743  mov     dword ptr [ebx], offset ??_7CVPVBIInterfaceHandler@@6BCUnknown@@@; const CVPVBIInterfaceHandler::`vftable'{for `CUnknown'}
0x10036749  mov     dword ptr [ebx+0Ch], offset ??_7CVPVideoInterfaceHandler@@6BIDistributorNotify@@@; const CVPVideoInterfaceHandler::`vftable'{for `IDistributorNotify'}
0x10036750  mov     dword ptr [ebx+3Ch], offset ??_7CVPVBIInterfaceHandler@@6B@; const CVPVBIInterfaceHandler::`vftable'
0x10036757  cmp     [ebx+10h], edi
0x1003675a  jz      loc_1003686D
0x10036760  push    edi; lpName
0x10036761  push    edi; bInitialState
0x10036762  push    1; bManualReset
0x10036764  push    edi; lpEventAttributes
0x10036765  call    ds:__imp__CreateEventW@16; CreateEventW(x,x,x,x)
0x1003676b  mov     [ebx+2Ch], eax
0x1003676e  test    eax, eax
0x10036770  jz      loc_10036838
0x10036776  mov     ecx, _WPP_GLOBAL_Control
0x1003677c  cmp     ecx, offset _WPP_GLOBAL_Control
0x10036782  jz      short loc_10036798
0x10036784  push    eax; char
0x10036785  push    dword ptr [ecx+14h]
0x10036788  mov     edx, offset _WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids; MessageGuid
0x1003678d  push    dword ptr [ecx+10h]; LoggerHandle
0x10036790  push    1Fh
0x10036792  pop     ecx; MessageNumber
0x10036793  call    _WPP_SF_q@20; WPP_SF_q(x,x,x,x,x)
0x10036798  mov     ecx, ebx; this
0x1003679a  call    ?CreateThread@CVPInterfaceHandler@@QAEJXZ; CVPInterfaceHandler::CreateThread(void)
0x1003679f  test    eax, eax
0x100367a1  js      loc_10036834
0x100367a7  mov     eax, [ebx+2Ch]
0x100367aa  lea     ecx, [ebx+1Ch]
0x100367ad  mov     [ebx+24h], edi
0x100367b0  xor     edx, edx
0x100367b2  mov     [ebx+28h], edi
0x100367b5  inc     edx
0x100367b6  mov     [esp+28h+BytesReturned], edi
0x100367ba  mov     esi, offset __GUID_ec529b01_1a1f_11d1_bad9_00609744111a
0x100367bf  mov     [ebx+20h], eax
0x100367c2  lea     edi, [esp+28h+InBuffer]
0x100367c6  mov     [ecx], edx
0x100367c8  lea     eax, [esp+28h+BytesReturned]
0x100367cc  push    eax; lpBytesReturned
0x100367cd  movsd
0x100367ce  lea     eax, [esp+2Ch+InBuffer]
0x100367d2  push    10h; nOutBufferSize
0x100367d4  push    ecx; lpOutBuffer
0x100367d5  push    18h; nInBufferSize
0x100367d7  movsd
0x100367d8  push    eax; lpInBuffer
0x100367d9  push    2F0007h; dwIoControlCode
0x100367de  push    dword ptr [ebx+10h]; hDevice
0x100367e1  movsd
0x100367e2  movsd
0x100367e3  mov     [esp+44h+var_8], 0
0x100367eb  mov     [esp+44h+var_4], edx
0x100367ef  call    _KsSynchronousDeviceControl@28; KsSynchronousDeviceControl(x,x,x,x,x,x,x)
0x100367f4  mov     esi, eax
0x100367f6  test    esi, esi
0x100367f8  jns     short loc_1003681E
0x100367fa  mov     ecx, _WPP_GLOBAL_Control
0x10036800  cmp     ecx, offset _WPP_GLOBAL_Control
0x10036806  jz      short loc_10036817
0x10036808  push    esi; char
0x10036809  push    dword ptr [ecx+14h]
0x1003680c  push    dword ptr [ecx+10h]; LoggerHandle
0x1003680f  push    20h ; ' '
0x10036811  pop     ecx; MessageNumber
0x10036812  call    _WPP_SF_L@20; WPP_SF_L(x,x,x,x,x)
0x10036817  mov     eax, [ebp+arg_8]
0x1003681a  mov     [eax], esi
0x1003681c  jmp     short loc_1003686D
0x1003681e  mov     eax, _WPP_GLOBAL_Control
0x10036823  cmp     eax, offset _WPP_GLOBAL_Control
0x10036828  jz      short loc_1003686D
0x1003682a  push    dword ptr [eax+14h]
0x1003682d  push    dword ptr [eax+10h]
0x10036830  push    21h ; '!'
0x10036832  jmp     short loc_10036862
0x10036834  mov     [esi], eax
0x10036836  jmp     short loc_1003686D
0x10036838  call    ds:__imp__GetLastError@0; GetLastError()
0x1003683e  movzx   ecx, ax
0x10036841  or      ecx, 80070000h
0x10036847  test    eax, eax
0x10036849  cmovle  ecx, eax
0x1003684c  mov     [esi], ecx
0x1003684e  mov     eax, _WPP_GLOBAL_Control
0x10036853  cmp     eax, offset _WPP_GLOBAL_Control
0x10036858  jz      short loc_1003686D
0x1003685a  push    dword ptr [eax+14h]
0x1003685d  push    dword ptr [eax+10h]; LoggerHandle
0x10036860  push    22h ; '"'
0x10036862  mov     edx, offset _WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids; MessageGuid
0x10036867  pop     ecx; MessageNumber
0x10036868  call    _WPP_SF_@16; WPP_SF_(x,x,x,x)
0x1003686d  pop     edi
0x1003686e  pop     esi
0x1003686f  mov     eax, ebx
0x10036871  pop     ebx
0x10036872  mov     esp, ebp
0x10036874  pop     ebp
0x10036875  retn    0Ch
```
