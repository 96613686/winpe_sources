# CKsPin::SetDeviceState(KSSTATE,KSSTATE,IKsTransport * *)

- ea: `0x180041840`
- end: `0x180041b1f`
- name: `?SetDeviceState@CKsPin@@UEAAJW4KSSTATE@@0PEAPEAUIKsTransport@@@Z`
- size: `735`
- prototype: `__int64 __fastcall(CKsPin *__hidden this, enum KSSTATE, enum KSSTATE, struct IKsTransport **)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, installer_update`

## callees

- `0x18000c630`
- `0x18000cf4c`
- `0x18000dddc`
- `0x180014778`
- `0x180019c60`
- `0x1800332f4`
- `0x180041840`
- `0x1800607e0`
- `0x180061390`

## import_xrefs

- `ntoskrnl!PsGetProcessId` at `0x180041ad1`
- `ntoskrnl!PsGetProcessId` at `0x180041ad1`
- `ntoskrnl!KeWaitForSingleObject` at `0x180041a97`
- `ntoskrnl!KeWaitForSingleObject` at `0x180041a97`

## pseudocode

```c
__int64 __fastcall CKsPin::SetDeviceState(CKsPin *this, __int64 a2, enum KSSTATE a3, struct IKsTransport **a4)
{
  enum KSSTATE v6; // ebp
  CKsPin *v7; // rsi
  __int64 Notification; // rax
  int v9; // eax
  unsigned int v10; // ebx
  int v12; // ebx
  __int64 v13; // rax
  _KSPPROCESSPIN *InPlaceCounterpart; // rdx
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // r15
  _KSFILTER_EXT *Parent; // rbx
  void (__fastcall *v19)(__int64, _KSCAMERA_FRAMESERVER_UNIQUEID *, __int64, _QWORD, enum KSSTATE, enum KSSTATE, _KSFILTER *); // rdi
  unsigned int ProcessId; // eax
  __int64 v21; // r8
  __int64 v22; // [rsp+28h] [rbp-60h]

  v6 = (int)a2;
  v7 = this;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    this = (CKsPin *)WPP_GLOBAL_Control;
    if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(a2) = 5;
      WPP_RECORDER_SF_q(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        1,
        69,
        (__int64)WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids,
        (char)v7);
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      this = (CKsPin *)WPP_GLOBAL_Control;
      if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LOBYTE(a2) = 5;
        WPP_RECORDER_SF_qdd(
          WPP_GLOBAL_Control->DeviceExtension,
          a2,
          1,
          70,
          (__int64)WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids,
          (char)v7,
          a3,
          v6);
      }
    }
  }
  if ( v7->m_State == v6 )
  {
    v12 = 0;
    if ( v6 == KSSTATE_STOP
      && a3 == KSSTATE_ACQUIRE
      && !v7->m_ConnectionFileObject
      && _InterlockedExchangeAdd((volatile signed __int32 *)&v7->m_ActiveFrameCountPlusOne, 0xFFFFFFFF) != 1 )
    {
      KeWaitForSingleObject(&v7->m_StopEvent, Suspended, 0, 0, 0);
    }
    *a4 = 0;
    goto LABEL_43;
  }
  if ( v7->m_fIsVideoCameraDevice
    && (a3 == KSSTATE_STOP && v6 || a3 != KSSTATE_RUN && v6 == KSSTATE_PAUSE || v6 == KSSTATE_RUN) )
  {
    Notification = KspGetNotification(this, a2);
    if ( Notification )
    {
      LOBYTE(a2) = v7->m_fIsVideoCameraDevice;
      v9 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)Notification + 32LL))(Notification, a2, 0);
      v10 = v9;
      if ( v9 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
          {
            LODWORD(v22) = v9;
            WPP_RECORDER_SF_D(
              WPP_GLOBAL_Control->DeviceExtension,
              0,
              2,
              71,
              (__int64)WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids,
              v22);
          }
        }
        return v10;
      }
    }
  }
  v12 = 1;
  if ( v6 == KSSTATE_ACQUIRE && a3 == KSSTATE_STOP )
    v7->m_ActiveFrameCountPlusOne = 1;
  v13 = 696;
  v7->m_State = v6;
  this = (CKsPin *)704;
  if ( v6 <= a3 )
    v13 = 704;
  *a4 = *(struct IKsTransport **)((char *)&v7->IKsPin::IKsTransport::IUnknown::__vftable + v13);
  if ( v6 == KSSTATE_STOP )
    CKsPin::CancelIrpsOutstanding(v7);
  if ( !v7->m_ConnectionFileObject && !v7->m_ConnectedPinInterface )
  {
    if ( a3 )
    {
      if ( v6 )
        goto LABEL_43;
    }
    else
    {
      InPlaceCounterpart = v7->m_Process.InPlaceCounterpart;
      if ( InPlaceCounterpart )
        KsSetTargetDeviceObject(v7->m_Header, (PDEVICE_OBJECT)InPlaceCounterpart->Pin[4].ConnectionMedium.Alignment);
      if ( v6 )
        goto LABEL_36;
    }
    KsSetTargetDeviceObject(v7->m_Header, 0);
LABEL_36:
    v7->m_Header->TargetState = a3 == KSSTATE_STOP;
    v15 = (__int64)v7->m_Ext.Device->GetStruct(v7->m_Ext.Device);
    KsRecalculateStackDepth(**(KSDEVICE_HEADER **)(*(_QWORD *)(v15 + 24) + 64LL), 0);
  }
LABEL_43:
  v16 = KspGetNotification(this, a2);
  v17 = v16;
  if ( v16 && a3 != v6 && v12 )
  {
    Parent = v7->m_Ext.Parent;
    v19 = *(void (__fastcall **)(__int64, _KSCAMERA_FRAMESERVER_UNIQUEID *, __int64, _QWORD, enum KSSTATE, enum KSSTATE, _KSFILTER *))(*(_QWORD *)v16 + 16LL);
    ProcessId = (unsigned int)PsGetProcessId(Parent->OwningProcess);
    LOBYTE(v21) = v7->m_Ext.IsOwnedByFrameServer;
    v19(v17, &v7->m_Ext.UniqueDeviceId, v21, ProcessId, a3, v6, &Parent->Public);
  }
  return 0;
}

```

## disassembly

```asm
0x180041840  push    rbx
0x180041842  push    rbp
0x180041843  push    rsi
0x180041844  push    rdi
0x180041845  push    r12
0x180041847  push    r13
0x180041849  push    r14
0x18004184b  push    r15
0x18004184d  sub     rsp, 48h
0x180041851  mov     rdi, r9
0x180041854  mov     r14d, r8d
0x180041857  mov     ebp, edx
0x180041859  mov     rsi, rcx
0x18004185c  xor     r12d, r12d
0x18004185f  lea     r13, WPP_RECORDER_INITIALIZED
0x180041866  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18004186d  lea     rax, WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids
0x180041874  lea     r15d, [r12+1]
0x180041879  jz      short loc_1800418EB
0x18004187b  mov     rcx, cs:WPP_GLOBAL_Control
0x180041882  cmp     [rcx+48h], r12w
0x180041887  jz      short loc_1800418AD
0x180041889  mov     rcx, [rcx+40h]
0x18004188d  lea     r9d, [r12+45h]
0x180041892  mov     [rsp+88h+var_60], rsi
0x180041897  mov     r8d, r15d
0x18004189a  mov     dl, 5
0x18004189c  mov     [rsp+88h+Timeout], rax
0x1800418a1  call    WPP_RECORDER_SF_q
0x1800418a6  lea     rax, WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids
0x1800418ad  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1800418b4  jz      short loc_1800418EB
0x1800418b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800418bd  cmp     [rcx+48h], r12w
0x1800418c2  jz      short loc_1800418EB
0x1800418c4  mov     rcx, [rcx+40h]
0x1800418c8  mov     r9d, 46h ; 'F'
0x1800418ce  mov     [rsp+88h+var_50], ebp
0x1800418d2  mov     r8d, r15d
0x1800418d5  mov     dword ptr [rsp+88h+var_58], r14d
0x1800418da  mov     dl, 5
0x1800418dc  mov     [rsp+88h+var_60], rsi
0x1800418e1  mov     [rsp+88h+Timeout], rax
0x1800418e6  call    WPP_RECORDER_SF_qdd
0x1800418eb  cmp     [rsi+2CCh], ebp
0x1800418f1  jz      loc_180041A5D
0x1800418f7  cmp     [rsi+530h], r12b
0x1800418fe  jz      loc_18004198B
0x180041904  test    r14d, r14d
0x180041907  jnz     short loc_18004190D
0x180041909  test    ebp, ebp
0x18004190b  jnz     short loc_18004191D
0x18004190d  cmp     r14d, 3
0x180041911  jz      short loc_180041918
0x180041913  cmp     ebp, 2
0x180041916  jz      short loc_18004191D
0x180041918  cmp     ebp, 3
0x18004191b  jnz     short loc_18004198B
0x18004191d  call    KspGetNotification
0x180041922  mov     r9, rax
0x180041925  test    rax, rax
0x180041928  jz      short loc_18004198B
0x18004192a  mov     rcx, [rax]
0x18004192d  xor     r8d, r8d
0x180041930  mov     dl, [rsi+530h]
0x180041936  mov     rax, [rcx+20h]
0x18004193a  mov     rcx, r9
0x18004193d  call    _guard_dispatch_icall
0x180041942  mov     ebx, eax
0x180041944  test    eax, eax
0x180041946  jns     short loc_18004198B
0x180041948  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18004194f  jz      short loc_180041984
0x180041951  mov     rcx, cs:WPP_GLOBAL_Control
0x180041958  cmp     [rcx+48h], r12w
0x18004195d  jz      short loc_180041984
0x18004195f  mov     rcx, [rcx+40h]
0x180041963  mov     r9d, 47h ; 'G'
0x180041969  mov     dword ptr [rsp+88h+var_60], eax
0x18004196d  xor     edx, edx
0x18004196f  lea     rax, WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids
0x180041976  mov     [rsp+88h+Timeout], rax
0x18004197b  lea     r8d, [r9-45h]
0x18004197f  call    WPP_RECORDER_SF_D
0x180041984  mov     eax, ebx
0x180041986  jmp     loc_180041B0D
0x18004198b  mov     ebx, r15d
0x18004198e  cmp     ebp, r15d
0x180041991  jnz     short loc_18004199F
0x180041993  test    r14d, r14d
0x180041996  jnz     short loc_18004199F
0x180041998  mov     [rsi+3D8h], r15d
0x18004199f  mov     eax, 2B8h
0x1800419a4  mov     [rsi+2CCh], ebp
0x1800419aa  cmp     ebp, r14d
0x1800419ad  lea     ecx, [rax+8]
0x1800419b0  cmovle  eax, ecx
0x1800419b3  mov     rax, [rax+rsi]
0x1800419b7  mov     [rdi], rax
0x1800419ba  test    ebp, ebp
0x1800419bc  jnz     short loc_1800419C6
0x1800419be  mov     rcx, rsi; this
0x1800419c1  call    ?CancelIrpsOutstanding@CKsPin@@AEAAXXZ; CKsPin::CancelIrpsOutstanding(void)
0x1800419c6  cmp     [rsi+358h], r12
0x1800419cd  jnz     loc_180041AA6
0x1800419d3  cmp     [rsi+340h], r12
0x1800419da  jnz     loc_180041AA6
0x1800419e0  test    r14d, r14d
0x1800419e3  jz      short loc_1800419EF
0x1800419e5  test    ebp, ebp
0x1800419e7  jnz     loc_180041AA6
0x1800419ed  jmp     short loc_180041A15
0x1800419ef  mov     rdx, [rsi+210h]
0x1800419f6  test    rdx, rdx
0x1800419f9  jz      short loc_180041A11
0x1800419fb  mov     rdx, [rdx]
0x1800419fe  mov     rcx, [rsi+3C0h]; Header
0x180041a05  mov     rdx, [rdx+260h]; TargetDevice
0x180041a0c  call    KsSetTargetDeviceObject
0x180041a11  test    ebp, ebp
0x180041a13  jnz     short loc_180041A23
0x180041a15  mov     rcx, [rsi+3C0h]; Header
0x180041a1c  xor     edx, edx; TargetDevice
0x180041a1e  call    KsSetTargetDeviceObject
0x180041a23  mov     rax, [rsi+3C0h]
0x180041a2a  mov     ecx, r12d
0x180041a2d  test    r14d, r14d
0x180041a30  setz    cl
0x180041a33  mov     [rax+68h], ecx
0x180041a36  mov     rcx, [rsi+0C8h]
0x180041a3d  mov     rax, [rcx]
0x180041a40  mov     rax, [rax+18h]
0x180041a44  call    _guard_dispatch_icall
0x180041a49  xor     edx, edx; ReuseStackLocation
0x180041a4b  mov     rcx, [rax+18h]
0x180041a4f  mov     rcx, [rcx+40h]
0x180041a53  mov     rcx, [rcx]; Header
0x180041a56  call    KsRecalculateStackDepth
0x180041a5b  jmp     short loc_180041AA6
0x180041a5d  mov     ebx, r12d
0x180041a60  test    ebp, ebp
0x180041a62  jnz     short loc_180041AA3
0x180041a64  cmp     r14d, r15d
0x180041a67  jnz     short loc_180041AA3
0x180041a69  cmp     [rsi+358h], r12
0x180041a70  jnz     short loc_180041AA3
0x180041a72  or      eax, 0FFFFFFFFh
0x180041a75  lock xadd [rsi+3D8h], eax
0x180041a7d  cmp     eax, r15d
0x180041a80  jz      short loc_180041AA3
0x180041a82  lea     rcx, [rsi+3E0h]; Object
0x180041a89  mov     [rsp+88h+Timeout], r12; Timeout
0x180041a8e  xor     r9d, r9d; Alertable
0x180041a91  lea     edx, [rbp+5]; WaitReason
0x180041a94  xor     r8d, r8d; WaitMode
0x180041a97  call    cs:__imp_KeWaitForSingleObject
0x180041a9e  nop     dword ptr [rax+rax+00h]
0x180041aa3  mov     [rdi], r12
0x180041aa6  call    KspGetNotification
0x180041aab  mov     r15, rax
0x180041aae  test    rax, rax
0x180041ab1  jz      short loc_180041B0B
0x180041ab3  cmp     r14d, ebp
0x180041ab6  jz      short loc_180041B0B
0x180041ab8  test    ebx, ebx
0x180041aba  jz      short loc_180041B0B
0x180041abc  mov     rcx, [rax]
0x180041abf  mov     rbx, [rsi+0A8h]
0x180041ac6  mov     rdi, [rcx+10h]
0x180041aca  mov     rcx, [rbx+0A8h]; Process
0x180041ad1  call    cs:__imp_PsGetProcessId
0x180041ad8  nop     dword ptr [rax+rax+00h]
0x180041add  mov     r8b, [rsi+1C8h]
0x180041ae4  lea     rdx, [rsi+1A8h]
0x180041aeb  sub     rbx, 0FFFFFFFFFFFFFF80h
0x180041aef  mov     r9d, eax
0x180041af2  mov     [rsp+88h+var_58], rbx
0x180041af7  mov     rax, rdi
0x180041afa  mov     dword ptr [rsp+88h+var_60], ebp
0x180041afe  mov     rcx, r15
0x180041b01  mov     dword ptr [rsp+88h+Timeout], r14d
0x180041b06  call    _guard_dispatch_icall
0x180041b0b  xor     eax, eax
0x180041b0d  add     rsp, 48h
0x180041b11  pop     r15
0x180041b13  pop     r14
0x180041b15  pop     r13
0x180041b17  pop     r12
0x180041b19  pop     rdi
0x180041b1a  pop     rsi
0x180041b1b  pop     rbp
0x180041b1c  pop     rbx
0x180041b1d  retn
```
