# CVPVBIInterfaceHandler::CVPVBIInterfaceHandler(IUnknown *,ushort *,long *)

- ea: `0x180040714`
- end: `0x1800408c8`
- name: `??0CVPVBIInterfaceHandler@@AEAA@PEAUIUnknown@@PEAGPEAJ@Z`
- size: `436`
- prototype: `CVPVBIInterfaceHandler *__fastcall(CVPVBIInterfaceHandler *__hidden this, struct IUnknown *, unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x180040d20`

## callees

- `0x18000bde0`
- `0x180025860`
- `0x180025a74`
- `0x1800405bc`
- `0x180040714`
- `0x180040dbc`
- `0x180041f30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180040879`
- `KERNEL32!GetLastError` at `0x180040879`
- `KERNEL32!CreateEventW` at `0x18004077d`
- `KERNEL32!CreateEventW` at `0x18004077d`

## pseudocode

```c
CVPVBIInterfaceHandler *__fastcall CVPVBIInterfaceHandler::CVPVBIInterfaceHandler(
        CVPVBIInterfaceHandler *this,
        struct IUnknown *a2,
        unsigned __int16 *a3,
        int *a4)
{
  bool v6; // zf
  HANDLE EventW; // rax
  int Thread; // eax
  char *m_ObjectHandle; // rcx
  signed int v10; // eax
  __int64 v11; // r8
  int v12; // ebp
  _QWORD *v13; // rcx
  USHORT v14; // dx
  signed int LastError; // eax
  GUID InBuffer; // [rsp+40h] [rbp-48h] BYREF
  int v18; // [rsp+50h] [rbp-38h]
  int v19; // [rsp+54h] [rbp-34h]
  unsigned __int16 *NumberOfBytesTransferred; // [rsp+A0h] [rbp+18h] BYREF

  NumberOfBytesTransferred = a3;
  CVPInterfaceHandler::CVPInterfaceHandler(
    this,
    a2,
    a3,
    a4,
    &GUID_ec529b00_1a1f_11d1_bad9_00609744111a,
    &GUID_ec529b01_1a1f_11d1_bad9_00609744111a);
  v6 = this->m_ObjectHandle == 0;
  this->CVPInterfaceHandler::CUnknown::INonDelegatingUnknown::__vftable = (CVPVBIInterfaceHandler_vtbl *)&CVPVBIInterfaceHandler::`vftable'{for `CUnknown'};
  this->CVPInterfaceHandler::IDistributorNotify::IUnknown::__vftable = (IDistributorNotify_vtbl *)&CVPVideoInterfaceHandler::`vftable'{for `IDistributorNotify'};
  this->IVPVBIConfig::IVPBaseConfig::IUnknown::__vftable = (IVPVBIConfig_vtbl *)&CVPVBIInterfaceHandler::`vftable';
  if ( v6 )
    return this;
  EventW = CreateEventW(0, 1, 0, 0);
  this->m_NotifyEventHandle = EventW;
  if ( EventW )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x1Fu, &WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids, EventW);
    Thread = CVPInterfaceHandler::CreateThread(this);
    if ( Thread < 0 )
    {
      *a4 = Thread;
      return this;
    }
    this->m_EventData.EventHandle.Event = this->m_NotifyEventHandle;
    this->m_EventData.NotificationType = 1;
    *(_OWORD *)this->m_EventData.Alignment.Alignment = 0;
    m_ObjectHandle = (char *)this->m_ObjectHandle;
    LODWORD(NumberOfBytesTransferred) = 0;
    InBuffer = GUID_ec529b01_1a1f_11d1_bad9_00609744111a;
    v18 = 0;
    v19 = 1;
    v10 = KsSynchronousDeviceControl(
            m_ObjectHandle,
            0x2F0007u,
            &InBuffer,
            0x18u,
            &this->m_EventData,
            0x20u,
            (LPDWORD)&NumberOfBytesTransferred);
    v12 = v10;
    if ( v10 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        WPP_SF_L(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, v11, (unsigned int)v10);
      *a4 = v12;
      return this;
    }
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return this;
    v14 = 33;
LABEL_17:
    WPP_SF_(v13[2], v14, &WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids);
    return this;
  }
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  *a4 = LastError;
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    v14 = 34;
    goto LABEL_17;
  }
  return this;
}

```

## disassembly

```asm
0x180040714  mov     [rsp+NumberOfBytesTransferred], r8
0x180040719  push    rbx
0x18004071a  push    rbp
0x18004071b  push    rsi
0x18004071c  push    rdi
0x18004071d  sub     rsp, 68h
0x180040721  lea     rax, _GUID_ec529b01_1a1f_11d1_bad9_00609744111a
0x180040728  mov     rsi, r9
0x18004072b  mov     qword ptr [rsp+88h+var_60], rax; struct _GUID *
0x180040730  mov     rbx, rcx
0x180040733  lea     rax, _GUID_ec529b00_1a1f_11d1_bad9_00609744111a
0x18004073a  mov     [rsp+88h+var_68], rax; struct _GUID *
0x18004073f  call    ??0CVPInterfaceHandler@@QEAA@PEAUIUnknown@@PEAGPEAJPEBU_GUID@@3@Z; CVPInterfaceHandler::CVPInterfaceHandler(IUnknown *,ushort *,long *,_GUID const *,_GUID const *)
0x180040744  cmp     qword ptr [rbx+20h], 0
0x180040749  lea     rax, ??_7CVPVBIInterfaceHandler@@6BCUnknown@@@; const CVPVBIInterfaceHandler::`vftable'{for `CUnknown'}
0x180040750  mov     [rbx], rax
0x180040753  lea     rax, ??_7CVPVideoInterfaceHandler@@6BIDistributorNotify@@@; const CVPVideoInterfaceHandler::`vftable'{for `IDistributorNotify'}
0x18004075a  mov     [rbx+18h], rax
0x18004075e  lea     rax, ??_7CVPVBIInterfaceHandler@@6B@; const CVPVBIInterfaceHandler::`vftable'
0x180040765  mov     [rbx+78h], rax
0x180040769  jz      loc_1800408BB
0x18004076f  xor     r9d, r9d; lpName
0x180040772  xor     r8d, r8d; bInitialState
0x180040775  xor     ecx, ecx; lpEventAttributes
0x180040777  lea     ebp, [r9+1]
0x18004077b  mov     edx, ebp; bManualReset
0x18004077d  call    cs:__imp_CreateEventW
0x180040784  nop     dword ptr [rax+rax+00h]
0x180040789  mov     [rbx+58h], rax
0x18004078d  test    rax, rax
0x180040790  jz      loc_180040879
0x180040796  mov     rcx, cs:WPP_GLOBAL_Control
0x18004079d  lea     rdi, WPP_GLOBAL_Control
0x1800407a4  cmp     rcx, rdi
0x1800407a7  jz      short loc_1800407BF
0x1800407a9  mov     rcx, [rcx+10h]
0x1800407ad  lea     edx, [rbp+1Eh]
0x1800407b0  mov     r9, rax
0x1800407b3  lea     r8, WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids
0x1800407ba  call    WPP_SF_q
0x1800407bf  mov     rcx, rbx; this
0x1800407c2  call    ?CreateThread@CVPInterfaceHandler@@QEAAJXZ; CVPInterfaceHandler::CreateThread(void)
0x1800407c7  test    eax, eax
0x1800407c9  js      loc_180040875
0x1800407cf  mov     rax, [rbx+58h]
0x1800407d3  lea     rcx, [rbx+38h]
0x1800407d7  mov     [rbx+40h], rax
0x1800407db  lea     r8, [rsp+88h+InBuffer]; lpInBuffer
0x1800407e0  mov     [rcx], ebp
0x1800407e2  lea     rax, [rsp+88h+NumberOfBytesTransferred]
0x1800407ea  mov     [rsp+88h+lpNumberOfBytesTransferred], rax; lpNumberOfBytesTransferred
0x1800407ef  xorps   xmm0, xmm0
0x1800407f2  movups  xmmword ptr [rbx+48h], xmm0
0x1800407f6  mov     [rsp+88h+var_60], 20h ; ' '; DWORD
0x1800407fe  mov     r9d, 18h; nInBufferSize
0x180040804  movups  xmm1, xmmword ptr cs:_GUID_ec529b01_1a1f_11d1_bad9_00609744111a.Data1
0x18004080b  mov     [rsp+88h+var_68], rcx; LPVOID
0x180040810  mov     edx, 2F0007h; dwIoControlCode
0x180040815  mov     rcx, [rbx+20h]; hFile
0x180040819  mov     dword ptr [rsp+88h+NumberOfBytesTransferred], 0
0x180040824  movdqu  [rsp+88h+InBuffer], xmm1
0x18004082a  mov     [rsp+88h+var_38], 0
0x180040832  mov     [rsp+88h+var_34], ebp
0x180040836  call    KsSynchronousDeviceControl
0x18004083b  mov     ebp, eax
0x18004083d  test    eax, eax
0x18004083f  jns     short loc_180040862
0x180040841  mov     rcx, cs:WPP_GLOBAL_Control
0x180040848  cmp     rcx, rdi
0x18004084b  jz      short loc_18004085E
0x18004084d  mov     rcx, [rcx+10h]
0x180040851  mov     edx, 20h ; ' '
0x180040856  mov     r9d, eax
0x180040859  call    WPP_SF_L
0x18004085e  mov     [rsi], ebp
0x180040860  jmp     short loc_1800408BB
0x180040862  mov     rcx, cs:WPP_GLOBAL_Control
0x180040869  cmp     rcx, rdi
0x18004086c  jz      short loc_1800408BB
0x18004086e  mov     edx, 21h ; '!'
0x180040873  jmp     short loc_1800408AB
0x180040875  mov     [rsi], eax
0x180040877  jmp     short loc_1800408BB
0x180040879  call    cs:__imp_GetLastError
0x180040880  nop     dword ptr [rax+rax+00h]
0x180040885  test    eax, eax
0x180040887  jle     short loc_180040891
0x180040889  movzx   eax, ax
0x18004088c  or      eax, 80070000h
0x180040891  mov     [rsi], eax
0x180040893  mov     rcx, cs:WPP_GLOBAL_Control
0x18004089a  lea     rdi, WPP_GLOBAL_Control
0x1800408a1  cmp     rcx, rdi
0x1800408a4  jz      short loc_1800408BB
0x1800408a6  mov     edx, 22h ; '"'
0x1800408ab  mov     rcx, [rcx+10h]
0x1800408af  lea     r8, WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids
0x1800408b6  call    WPP_SF_
0x1800408bb  mov     rax, rbx
0x1800408be  add     rsp, 68h
0x1800408c2  pop     rdi
0x1800408c3  pop     rsi
0x1800408c4  pop     rbp
0x1800408c5  pop     rbx
0x1800408c6  retn
```
