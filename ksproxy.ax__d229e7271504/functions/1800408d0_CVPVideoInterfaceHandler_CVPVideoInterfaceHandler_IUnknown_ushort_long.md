# CVPVideoInterfaceHandler::CVPVideoInterfaceHandler(IUnknown *,ushort *,long *)

- ea: `0x1800408d0`
- end: `0x180040a84`
- name: `??0CVPVideoInterfaceHandler@@AEAA@PEAUIUnknown@@PEAGPEAJ@Z`
- size: `436`
- prototype: `CVPVideoInterfaceHandler *__fastcall(CVPVideoInterfaceHandler *__hidden this, struct IUnknown *, unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x180040d70`

## callees

- `0x18000bde0`
- `0x180025860`
- `0x180025a74`
- `0x1800405bc`
- `0x1800408d0`
- `0x180040dbc`
- `0x180041f30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180040a35`
- `KERNEL32!GetLastError` at `0x180040a35`
- `KERNEL32!CreateEventW` at `0x180040939`
- `KERNEL32!CreateEventW` at `0x180040939`

## pseudocode

```c
CVPVideoInterfaceHandler *__fastcall CVPVideoInterfaceHandler::CVPVideoInterfaceHandler(
        CVPVideoInterfaceHandler *this,
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
    &GUID_bc29a660_30e3_11d0_9e69_00c04fd7c15b,
    &GUID_20c5598e_d3c8_11d0_8dfc_00c04fd7c08b);
  v6 = this->m_ObjectHandle == 0;
  this->CVPInterfaceHandler::CUnknown::INonDelegatingUnknown::__vftable = (CVPVideoInterfaceHandler_vtbl *)&CVPVideoInterfaceHandler::`vftable'{for `CUnknown'};
  this->CVPInterfaceHandler::IDistributorNotify::IUnknown::__vftable = (IDistributorNotify_vtbl *)&CVPVideoInterfaceHandler::`vftable'{for `IDistributorNotify'};
  this->IVPConfig::IVPBaseConfig::IUnknown::__vftable = (IVPConfig_vtbl *)&CVPVideoInterfaceHandler::`vftable';
  if ( v6 )
    return this;
  EventW = CreateEventW(0, 1, 0, 0);
  this->m_NotifyEventHandle = EventW;
  if ( EventW )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x12u, &WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids, EventW);
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
    InBuffer = GUID_20c5598e_d3c8_11d0_8dfc_00c04fd7c08b;
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
        WPP_SF_L(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, v11, (unsigned int)v10);
      *a4 = v12;
      return this;
    }
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return this;
    v14 = 20;
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
    v14 = 21;
    goto LABEL_17;
  }
  return this;
}

```

## disassembly

```asm
0x1800408d0  mov     [rsp+NumberOfBytesTransferred], r8
0x1800408d5  push    rbx
0x1800408d6  push    rbp
0x1800408d7  push    rsi
0x1800408d8  push    rdi
0x1800408d9  sub     rsp, 68h
0x1800408dd  lea     rax, _GUID_20c5598e_d3c8_11d0_8dfc_00c04fd7c08b
0x1800408e4  mov     rsi, r9
0x1800408e7  mov     qword ptr [rsp+88h+var_60], rax; struct _GUID *
0x1800408ec  mov     rbx, rcx
0x1800408ef  lea     rax, _GUID_bc29a660_30e3_11d0_9e69_00c04fd7c15b
0x1800408f6  mov     [rsp+88h+var_68], rax; struct _GUID *
0x1800408fb  call    ??0CVPInterfaceHandler@@QEAA@PEAUIUnknown@@PEAGPEAJPEBU_GUID@@3@Z; CVPInterfaceHandler::CVPInterfaceHandler(IUnknown *,ushort *,long *,_GUID const *,_GUID const *)
0x180040900  cmp     qword ptr [rbx+20h], 0
0x180040905  lea     rax, ??_7CVPVideoInterfaceHandler@@6BCUnknown@@@; const CVPVideoInterfaceHandler::`vftable'{for `CUnknown'}
0x18004090c  mov     [rbx], rax
0x18004090f  lea     rax, ??_7CVPVideoInterfaceHandler@@6BIDistributorNotify@@@; const CVPVideoInterfaceHandler::`vftable'{for `IDistributorNotify'}
0x180040916  mov     [rbx+18h], rax
0x18004091a  lea     rax, ??_7CVPVideoInterfaceHandler@@6B@; const CVPVideoInterfaceHandler::`vftable'
0x180040921  mov     [rbx+78h], rax
0x180040925  jz      loc_180040A77
0x18004092b  xor     r9d, r9d; lpName
0x18004092e  xor     r8d, r8d; bInitialState
0x180040931  xor     ecx, ecx; lpEventAttributes
0x180040933  lea     ebp, [r9+1]
0x180040937  mov     edx, ebp; bManualReset
0x180040939  call    cs:__imp_CreateEventW
0x180040940  nop     dword ptr [rax+rax+00h]
0x180040945  mov     [rbx+58h], rax
0x180040949  test    rax, rax
0x18004094c  jz      loc_180040A35
0x180040952  mov     rcx, cs:WPP_GLOBAL_Control
0x180040959  lea     rdi, WPP_GLOBAL_Control
0x180040960  cmp     rcx, rdi
0x180040963  jz      short loc_18004097B
0x180040965  mov     rcx, [rcx+10h]
0x180040969  lea     edx, [rbp+11h]
0x18004096c  mov     r9, rax
0x18004096f  lea     r8, WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids
0x180040976  call    WPP_SF_q
0x18004097b  mov     rcx, rbx; this
0x18004097e  call    ?CreateThread@CVPInterfaceHandler@@QEAAJXZ; CVPInterfaceHandler::CreateThread(void)
0x180040983  test    eax, eax
0x180040985  js      loc_180040A31
0x18004098b  mov     rax, [rbx+58h]
0x18004098f  lea     rcx, [rbx+38h]
0x180040993  mov     [rbx+40h], rax
0x180040997  lea     r8, [rsp+88h+InBuffer]; lpInBuffer
0x18004099c  mov     [rcx], ebp
0x18004099e  lea     rax, [rsp+88h+NumberOfBytesTransferred]
0x1800409a6  mov     [rsp+88h+lpNumberOfBytesTransferred], rax; lpNumberOfBytesTransferred
0x1800409ab  xorps   xmm0, xmm0
0x1800409ae  movups  xmmword ptr [rbx+48h], xmm0
0x1800409b2  mov     [rsp+88h+var_60], 20h ; ' '; DWORD
0x1800409ba  mov     r9d, 18h; nInBufferSize
0x1800409c0  movups  xmm1, xmmword ptr cs:_GUID_20c5598e_d3c8_11d0_8dfc_00c04fd7c08b.Data1
0x1800409c7  mov     [rsp+88h+var_68], rcx; LPVOID
0x1800409cc  mov     edx, 2F0007h; dwIoControlCode
0x1800409d1  mov     rcx, [rbx+20h]; hFile
0x1800409d5  mov     dword ptr [rsp+88h+NumberOfBytesTransferred], 0
0x1800409e0  movdqu  [rsp+88h+InBuffer], xmm1
0x1800409e6  mov     [rsp+88h+var_38], 0
0x1800409ee  mov     [rsp+88h+var_34], ebp
0x1800409f2  call    KsSynchronousDeviceControl
0x1800409f7  mov     ebp, eax
0x1800409f9  test    eax, eax
0x1800409fb  jns     short loc_180040A1E
0x1800409fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180040a04  cmp     rcx, rdi
0x180040a07  jz      short loc_180040A1A
0x180040a09  mov     rcx, [rcx+10h]
0x180040a0d  mov     edx, 13h
0x180040a12  mov     r9d, eax
0x180040a15  call    WPP_SF_L
0x180040a1a  mov     [rsi], ebp
0x180040a1c  jmp     short loc_180040A77
0x180040a1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180040a25  cmp     rcx, rdi
0x180040a28  jz      short loc_180040A77
0x180040a2a  mov     edx, 14h
0x180040a2f  jmp     short loc_180040A67
0x180040a31  mov     [rsi], eax
0x180040a33  jmp     short loc_180040A77
0x180040a35  call    cs:__imp_GetLastError
0x180040a3c  nop     dword ptr [rax+rax+00h]
0x180040a41  test    eax, eax
0x180040a43  jle     short loc_180040A4D
0x180040a45  movzx   eax, ax
0x180040a48  or      eax, 80070000h
0x180040a4d  mov     [rsi], eax
0x180040a4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180040a56  lea     rdi, WPP_GLOBAL_Control
0x180040a5d  cmp     rcx, rdi
0x180040a60  jz      short loc_180040A77
0x180040a62  mov     edx, 15h
0x180040a67  mov     rcx, [rcx+10h]
0x180040a6b  lea     r8, WPP_eeac4563b24f33d64e9e6110b4162be0_Traceguids
0x180040a72  call    WPP_SF_
0x180040a77  mov     rax, rbx
0x180040a7a  add     rsp, 68h
0x180040a7e  pop     rdi
0x180040a7f  pop     rsi
0x180040a80  pop     rbp
0x180040a81  pop     rbx
0x180040a82  retn
```
