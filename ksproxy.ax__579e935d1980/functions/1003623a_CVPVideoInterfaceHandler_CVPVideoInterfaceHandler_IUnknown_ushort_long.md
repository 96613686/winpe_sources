# CVPVideoInterfaceHandler::CVPVideoInterfaceHandler(IUnknown *,ushort *,long *)

- ea: `0x1003623a`
- end: `0x10036398`
- name: `??0CVPVideoInterfaceHandler@@AAE@PAUIUnknown@@PAGPAJ@Z`
- size: `350`
- prototype: `CVPVideoInterfaceHandler *__thiscall(CVPVideoInterfaceHandler *__hidden this, struct IUnknown *, unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x10036200`

## callees

- `0x100063f1`
- `0x1000665f`
- `0x1001f3b0`
- `0x10035833`
- `0x10035861`
- `0x10035aeb`
- `0x1003623a`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10036358`
- `KERNEL32!GetLastError` at `0x10036358`
- `KERNEL32!CreateEventW` at `0x10036285`
- `KERNEL32!CreateEventW` at `0x10036285`

## pseudocode

```c
CVPVideoInterfaceHandler *__thiscall CVPVideoInterfaceHandler::CVPVideoInterfaceHandler(
        CVPVideoInterfaceHandler *this,
        struct IUnknown *a2,
        unsigned __int16 *a3,
        int *a4)
{
  HANDLE EventW; // eax
  signed int Thread; // eax
  void *m_NotifyEventHandle; // eax
  int v8; // eax
  int v9; // esi
  signed int LastError; // eax
  unsigned int v11; // ecx
  void *m_ObjectHandle; // [esp-1Ch] [ebp-44h]
  DWORD BytesReturned; // [esp+Ch] [ebp-1Ch] BYREF
  _DWORD InBuffer[6]; // [esp+10h] [ebp-18h] BYREF

  CVPInterfaceHandler::CVPInterfaceHandler(
    this,
    a2,
    (unsigned __int16 *)this,
    a4,
    &_GUID_bc29a660_30e3_11d0_9e69_00c04fd7c15b,
    &_GUID_20c5598e_d3c8_11d0_8dfc_00c04fd7c08b);
  this->CVPInterfaceHandler::CUnknown::INonDelegatingUnknown::__vftable = (CVPVideoInterfaceHandler_vtbl *)&CVPVideoInterfaceHandler::`vftable'{for `CUnknown'};
  this->CVPInterfaceHandler::IDistributorNotify::IUnknown::__vftable = (IDistributorNotify_vtbl *)&CVPVideoInterfaceHandler::`vftable'{for `IDistributorNotify'};
  this->IVPConfig::IVPBaseConfig::IUnknown::__vftable = (IVPConfig_vtbl *)&CVPVideoInterfaceHandler::`vftable';
  if ( this->m_ObjectHandle )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    this->m_NotifyEventHandle = EventW;
    if ( EventW )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        WPP_SF_q(
          0x12u,
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
        InBuffer[0] = _GUID_20c5598e_d3c8_11d0_8dfc_00c04fd7c08b.Data1;
        InBuffer[1] = *(_DWORD *)&_GUID_20c5598e_d3c8_11d0_8dfc_00c04fd7c08b.Data2;
        m_ObjectHandle = this->m_ObjectHandle;
        InBuffer[2] = *(_DWORD *)_GUID_20c5598e_d3c8_11d0_8dfc_00c04fd7c08b.Data4;
        InBuffer[3] = *(_DWORD *)&_GUID_20c5598e_d3c8_11d0_8dfc_00c04fd7c08b.Data4[4];
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
        v9 = v8;
        if ( v8 >= 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
            WPP_SF_(0x14u, &WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2));
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
            WPP_SF_L(0x13u, *((_QWORD *)WPP_GLOBAL_Control + 2), v8);
          *a4 = v9;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v11 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v11 = LastError;
      *a4 = v11;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        WPP_SF_(0x15u, &WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2));
    }
  }
  return this;
}

```

## disassembly

```asm
0x1003623a  mov     edi, edi
0x1003623c  push    ebp
0x1003623d  mov     ebp, esp
0x1003623f  and     esp, 0FFFFFFF8h
0x10036242  sub     esp, 1Ch
0x10036245  push    ebx
0x10036246  push    esi
0x10036247  mov     esi, [ebp+arg_8]
0x1003624a  mov     ebx, ecx
0x1003624c  push    edi
0x1003624d  push    offset __GUID_20c5598e_d3c8_11d0_8dfc_00c04fd7c08b; struct _GUID *
0x10036252  push    offset __GUID_bc29a660_30e3_11d0_9e69_00c04fd7c15b; struct _GUID *
0x10036257  push    esi; int *
0x10036258  push    ecx; unsigned __int16 *
0x10036259  push    [ebp+arg_0]; struct IUnknown *
0x1003625c  call    ??0CVPInterfaceHandler@@QAE@PAUIUnknown@@PAGPAJPBU_GUID@@3@Z; CVPInterfaceHandler::CVPInterfaceHandler(IUnknown *,ushort *,long *,_GUID const *,_GUID const *)
0x10036261  xor     edi, edi
0x10036263  mov     dword ptr [ebx], offset ??_7CVPVideoInterfaceHandler@@6BCUnknown@@@; const CVPVideoInterfaceHandler::`vftable'{for `CUnknown'}
0x10036269  mov     dword ptr [ebx+0Ch], offset ??_7CVPVideoInterfaceHandler@@6BIDistributorNotify@@@; const CVPVideoInterfaceHandler::`vftable'{for `IDistributorNotify'}
0x10036270  mov     dword ptr [ebx+3Ch], offset ??_7CVPVideoInterfaceHandler@@6B@; const CVPVideoInterfaceHandler::`vftable'
0x10036277  cmp     [ebx+10h], edi
0x1003627a  jz      loc_1003638D
0x10036280  push    edi; lpName
0x10036281  push    edi; bInitialState
0x10036282  push    1; bManualReset
0x10036284  push    edi; lpEventAttributes
0x10036285  call    ds:__imp__CreateEventW@16; CreateEventW(x,x,x,x)
0x1003628b  mov     [ebx+2Ch], eax
0x1003628e  test    eax, eax
0x10036290  jz      loc_10036358
0x10036296  mov     ecx, _WPP_GLOBAL_Control
0x1003629c  cmp     ecx, offset _WPP_GLOBAL_Control
0x100362a2  jz      short loc_100362B8
0x100362a4  push    eax; char
0x100362a5  push    dword ptr [ecx+14h]
0x100362a8  mov     edx, offset _WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids; MessageGuid
0x100362ad  push    dword ptr [ecx+10h]; LoggerHandle
0x100362b0  push    12h
0x100362b2  pop     ecx; MessageNumber
0x100362b3  call    _WPP_SF_q@20; WPP_SF_q(x,x,x,x,x)
0x100362b8  mov     ecx, ebx; this
0x100362ba  call    ?CreateThread@CVPInterfaceHandler@@QAEJXZ; CVPInterfaceHandler::CreateThread(void)
0x100362bf  test    eax, eax
0x100362c1  js      loc_10036354
0x100362c7  mov     eax, [ebx+2Ch]
0x100362ca  lea     ecx, [ebx+1Ch]
0x100362cd  mov     [ebx+24h], edi
0x100362d0  xor     edx, edx
0x100362d2  mov     [ebx+28h], edi
0x100362d5  inc     edx
0x100362d6  mov     [esp+28h+BytesReturned], edi
0x100362da  mov     esi, offset __GUID_20c5598e_d3c8_11d0_8dfc_00c04fd7c08b
0x100362df  mov     [ebx+20h], eax
0x100362e2  lea     edi, [esp+28h+InBuffer]
0x100362e6  mov     [ecx], edx
0x100362e8  lea     eax, [esp+28h+BytesReturned]
0x100362ec  push    eax; lpBytesReturned
0x100362ed  movsd
0x100362ee  lea     eax, [esp+2Ch+InBuffer]
0x100362f2  push    10h; nOutBufferSize
0x100362f4  push    ecx; lpOutBuffer
0x100362f5  push    18h; nInBufferSize
0x100362f7  movsd
0x100362f8  push    eax; lpInBuffer
0x100362f9  push    2F0007h; dwIoControlCode
0x100362fe  push    dword ptr [ebx+10h]; hDevice
0x10036301  movsd
0x10036302  movsd
0x10036303  mov     [esp+44h+var_8], 0
0x1003630b  mov     [esp+44h+var_4], edx
0x1003630f  call    _KsSynchronousDeviceControl@28; KsSynchronousDeviceControl(x,x,x,x,x,x,x)
0x10036314  mov     esi, eax
0x10036316  test    esi, esi
0x10036318  jns     short loc_1003633E
0x1003631a  mov     ecx, _WPP_GLOBAL_Control
0x10036320  cmp     ecx, offset _WPP_GLOBAL_Control
0x10036326  jz      short loc_10036337
0x10036328  push    esi; char
0x10036329  push    dword ptr [ecx+14h]
0x1003632c  push    dword ptr [ecx+10h]; LoggerHandle
0x1003632f  push    13h
0x10036331  pop     ecx; MessageNumber
0x10036332  call    _WPP_SF_L@20; WPP_SF_L(x,x,x,x,x)
0x10036337  mov     eax, [ebp+arg_8]
0x1003633a  mov     [eax], esi
0x1003633c  jmp     short loc_1003638D
0x1003633e  mov     eax, _WPP_GLOBAL_Control
0x10036343  cmp     eax, offset _WPP_GLOBAL_Control
0x10036348  jz      short loc_1003638D
0x1003634a  push    dword ptr [eax+14h]
0x1003634d  push    dword ptr [eax+10h]
0x10036350  push    14h
0x10036352  jmp     short loc_10036382
0x10036354  mov     [esi], eax
0x10036356  jmp     short loc_1003638D
0x10036358  call    ds:__imp__GetLastError@0; GetLastError()
0x1003635e  movzx   ecx, ax
0x10036361  or      ecx, 80070000h
0x10036367  test    eax, eax
0x10036369  cmovle  ecx, eax
0x1003636c  mov     [esi], ecx
0x1003636e  mov     eax, _WPP_GLOBAL_Control
0x10036373  cmp     eax, offset _WPP_GLOBAL_Control
0x10036378  jz      short loc_1003638D
0x1003637a  push    dword ptr [eax+14h]
0x1003637d  push    dword ptr [eax+10h]; LoggerHandle
0x10036380  push    15h
0x10036382  mov     edx, offset _WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids; MessageGuid
0x10036387  pop     ecx; MessageNumber
0x10036388  call    _WPP_SF_@16; WPP_SF_(x,x,x,x)
0x1003638d  pop     edi
0x1003638e  pop     esi
0x1003638f  mov     eax, ebx
0x10036391  pop     ebx
0x10036392  mov     esp, ebp
0x10036394  pop     ebp
0x10036395  retn    0Ch
```
