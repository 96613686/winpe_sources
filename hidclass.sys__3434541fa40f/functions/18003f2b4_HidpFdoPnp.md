# HidpFdoPnp

- ea: `0x18003f2b4`
- end: `0x18003f62d`
- name: `HidpFdoPnp`
- size: `889`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003e58c`

## callees

- `0x18000a020`
- `0x18001025c`
- `0x180010814`
- `0x180013428`
- `0x180013500`
- `0x180016188`
- `0x1800177e4`
- `0x180019694`
- `0x18001a0b8`
- `0x18001a890`
- `0x18001e944`
- `0x18001f980`
- `0x18003b444`
- `0x18003de60`
- `0x18003f2b4`
- `0x180042b00`

## import_xrefs

- `ntoskrnl!KeClearEvent` at `0x18003f3ec`
- `ntoskrnl!KeClearEvent` at `0x18003f4b0`
- `ntoskrnl!KeClearEvent` at `0x18003f3ec`
- `ntoskrnl!KeClearEvent` at `0x18003f4b0`
- `ntoskrnl!IofCompleteRequest` at `0x18003f540`
- `ntoskrnl!IofCompleteRequest` at `0x18003f540`

## string_xrefs

- `0x18003f408`: `Surprise Remove`

## pseudocode

```c
__int64 __fastcall HidpFdoPnp(__int64 a1, IRP *a2)
{
  _IO_STACK_LOCATION *CurrentStackLocation; // r15
  struct _IO_REMOVE_LOCK *v3; // rsi
  IRP *v4; // rdi
  _UNKNOWN **v6; // r9
  char v7; // r14
  unsigned int MinorFunction; // ebp
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  _IO_STACK_LOCATION *v13; // rax
  unsigned int v14; // eax
  int v15; // edx
  int v16; // r8d
  int DeviceRelations; // eax
  unsigned int v18; // ebx
  _IO_STACK_LOCATION *v19; // rax
  __int64 v20; // r8
  unsigned int started; // eax
  int v23; // [rsp+20h] [rbp-88h]

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v3 = (struct _IO_REMOVE_LOCK *)(a1 + 32);
  v4 = a2;
  v6 = &WPP_RECORDER_INITIALIZED;
  v7 = 1;
  MinorFunction = CurrentStackLocation->MinorFunction;
  v9 = CurrentStackLocation->MinorFunction;
  if ( !CurrentStackLocation->MinorFunction
    || (v9 = (unsigned int)(v9 - 1), !(_DWORD)v9)
    || (v9 = (unsigned int)(v9 - 1), !(_DWORD)v9)
    || (v9 = (unsigned int)(v9 - 1), !(_DWORD)v9)
    || (v9 = (unsigned int)(v9 - 1), !(_DWORD)v9)
    || (v9 = (unsigned int)(v9 - 1), !(_DWORD)v9)
    || (v9 = (unsigned int)(v9 - 1), !(_DWORD)v9)
    || (_DWORD)v9 == 17 )
  {
    LOBYTE(a2) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    LOBYTE(v9) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_qqcc(
        WPP_GLOBAL_Control->AttachedDevice,
        (_DWORD)a2,
        v9,
        *(_QWORD *)(a1 + 704),
        4,
        4,
        73,
        (__int64)WPP_09551ba6d0fe3383c1d3f23d6d3d8f25_Traceguids,
        *(_QWORD *)(a1 + 32),
        (char)v4,
        27,
        CurrentStackLocation->MinorFunction);
  }
  switch ( MinorFunction )
  {
    case 0u:
      started = HidpFdoStartDevice(a1, v4, v9, v6);
      goto LABEL_37;
    case 1u:
      goto LABEL_28;
    case 2u:
      v14 = HidpFdoRemoveDevice(v3, (__int64)v4, v9);
      goto LABEL_35;
    case 3u:
      goto LABEL_28;
    case 4u:
      KeClearEvent(&v3[57].Common.RemoveEvent);
      HIDSM_AddHidsmEvent(v3, 2011);
      HidpWaitForSignal(&v3[57].Common.RemoveEvent);
      CancelAllPingPongIrps(v3);
      v19 = v4->Tail.Overlay.CurrentStackLocation;
      *(_OWORD *)&v19[-1].MajorFunction = *(_OWORD *)&v19->MajorFunction;
      *(_OWORD *)&v19[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v19->Parameters.NotifyDirectoryEx.CompletionFilter;
      *(_OWORD *)(&v19[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v19->Parameters.SetQuota + 6);
      v19[-1].FileObject = v19->FileObject;
      v19[-1].Control = 0;
      started = HidpCallDriverSynchronous(*(_QWORD *)&v3->Common.Removed, v4, v20);
LABEL_37:
      v18 = started;
      goto LABEL_38;
    case 5u:
    case 6u:
      v4->IoStatus.Status = 0;
      goto LABEL_28;
  }
  if ( MinorFunction != 7 )
  {
    if ( MinorFunction == 23 )
    {
      KeClearEvent(&v3[57].Common.RemoveEvent);
      HIDSM_AddHidsmEvent(v3, 2015);
      HidpWaitForSignal(&v3[57].Common.RemoveEvent);
      DestroyPingPongs(v3);
      HidpFdoDrainDeviceResetNotifications((__int64)v3);
      HidpFdoDrainDevicePresenceNotifications(v3);
      if ( (unsigned int)Feature_UHSSRI01__private_IsEnabledDeviceUsageNoInline(v11, v10, v12) )
        HidpUnregisterSleepstudyBlockerReasons((KSPIN_LOCK *)&v3->Common.Removed);
    }
    goto LABEL_28;
  }
  if ( !CurrentStackLocation->Parameters.Read.Length )
  {
    DeviceRelations = HidpFdoQueryDeviceRelations(a1, v4, v9, v6);
    v18 = DeviceRelations;
    if ( DeviceRelations >= 0 )
    {
      v4->IoStatus.Status = DeviceRelations;
      goto LABEL_28;
    }
LABEL_38:
    v4->IoStatus.Status = v18;
    IofCompleteRequest(v4, 0);
    goto LABEL_39;
  }
LABEL_28:
  v13 = v4->Tail.Overlay.CurrentStackLocation;
  *(_OWORD *)&v13[-1].MajorFunction = *(_OWORD *)&v13->MajorFunction;
  *(_OWORD *)&v13[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v13->Parameters.NotifyDirectoryEx.CompletionFilter;
  *(_OWORD *)(&v13[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v13->Parameters.SetQuota + 6);
  v13[-1].FileObject = v13->FileObject;
  v13[-1].Control = 0;
  v14 = HidpCallDriver(*(_QWORD *)&v3->Common.Removed, v4);
LABEL_35:
  v18 = v14;
LABEL_39:
  if ( (int)(v18 + 0x80000000) >= 0 && v18 != -1073741637 && (MinorFunction <= 6 || MinorFunction == 23) )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      v7 = 0;
    }
    if ( v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v15) = v7;
      LOBYTE(v16) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qqccd(
        WPP_GLOBAL_Control->AttachedDevice,
        v15,
        v16,
        *(_QWORD *)&v3[21].Common.Removed,
        v23,
        4,
        74,
        (__int64)WPP_09551ba6d0fe3383c1d3f23d6d3d8f25_Traceguids,
        *(_QWORD *)&v3->Common.Removed,
        (char)v4,
        27,
        MinorFunction,
        v18);
    }
  }
  return v18;
}

```

## disassembly

```asm
0x18003f2b4  push    rbx
0x18003f2b6  push    rbp
0x18003f2b7  push    rsi
0x18003f2b8  push    rdi
0x18003f2b9  push    r14
0x18003f2bb  push    r15
0x18003f2bd  sub     rsp, 78h
0x18003f2c1  mov     r15, [rdx+0B8h]
0x18003f2c8  lea     rsi, [rcx+20h]
0x18003f2cc  mov     rdi, rdx
0x18003f2cf  lea     rax, WPP_GLOBAL_Control
0x18003f2d6  mov     rbx, rcx
0x18003f2d9  lea     r9, WPP_RECORDER_INITIALIZED
0x18003f2e0  mov     r14b, 1
0x18003f2e3  lea     r10, WPP_09551ba6d0fe3383c1d3f23d6d3d8f25_Traceguids
0x18003f2ea  movzx   ebp, byte ptr [r15+1]
0x18003f2ef  mov     r8d, ebp
0x18003f2f2  test    ebp, ebp
0x18003f2f4  jz      short loc_18003F320
0x18003f2f6  sub     r8d, 1
0x18003f2fa  jz      short loc_18003F320
0x18003f2fc  sub     r8d, 1
0x18003f300  jz      short loc_18003F320
0x18003f302  sub     r8d, 1
0x18003f306  jz      short loc_18003F320
0x18003f308  sub     r8d, 1
0x18003f30c  jz      short loc_18003F320
0x18003f30e  sub     r8d, 1
0x18003f312  jz      short loc_18003F320
0x18003f314  sub     r8d, 1
0x18003f318  jz      short loc_18003F320
0x18003f31a  cmp     r8d, 11h
0x18003f31e  jnz     short loc_18003F394
0x18003f320  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f327  cmp     rcx, rax
0x18003f32a  jz      short loc_18003F33E
0x18003f32c  mov     eax, [rcx+2Ch]
0x18003f32f  test    al, 8
0x18003f331  jz      short loc_18003F33E
0x18003f333  cmp     byte ptr [rcx+29h], 4
0x18003f337  jb      short loc_18003F33E
0x18003f339  mov     dl, r14b
0x18003f33c  jmp     short loc_18003F340
0x18003f33e  xor     dl, dl
0x18003f340  cmp     cs:WPP_RECORDER_INITIALIZED, r9
0x18003f347  setnz   r8b
0x18003f34b  test    dl, dl
0x18003f34d  jnz     short loc_18003F354
0x18003f34f  test    r8b, r8b
0x18003f352  jz      short loc_18003F394
0x18003f354  mov     rax, [rsi]
0x18003f357  mov     r9, [rsi+2A0h]
0x18003f35e  mov     rcx, [rcx+18h]
0x18003f362  mov     [rsp+0A8h+var_50], bpl
0x18003f367  mov     [rsp+0A8h+var_58], 1Bh
0x18003f36c  mov     [rsp+0A8h+var_60], rdi
0x18003f371  mov     [rsp+0A8h+var_68], rax
0x18003f376  mov     [rsp+0A8h+var_70], r10
0x18003f37b  mov     [rsp+0A8h+var_78], 49h ; 'I'
0x18003f382  mov     [rsp+0A8h+var_80], 4
0x18003f38a  mov     [rsp+0A8h+var_88], 4
0x18003f38f  call    WPP_RECORDER_AND_TRACE_SF_qqcc
0x18003f394  mov     ecx, ebp
0x18003f396  test    ebp, ebp
0x18003f398  jz      loc_18003F52B
0x18003f39e  sub     ecx, 1
0x18003f3a1  jz      loc_18003F440
0x18003f3a7  sub     ecx, 1
0x18003f3aa  jz      loc_18003F51C
0x18003f3b0  sub     ecx, 1
0x18003f3b3  jz      loc_18003F440
0x18003f3b9  sub     ecx, 1
0x18003f3bc  jz      loc_18003F4A6
0x18003f3c2  sub     ecx, 1
0x18003f3c5  jz      loc_18003F49D
0x18003f3cb  sub     ecx, 1
0x18003f3ce  jz      loc_18003F49D
0x18003f3d4  sub     ecx, 1
0x18003f3d7  jz      loc_18003F47C
0x18003f3dd  cmp     ecx, 10h
0x18003f3e0  jnz     short loc_18003F440
0x18003f3e2  lea     rbx, [rsi+728h]
0x18003f3e9  mov     rcx, rbx; Event
0x18003f3ec  call    cs:__imp_KeClearEvent
0x18003f3f3  nop     dword ptr [rax+rax+00h]
0x18003f3f8  mov     edx, 7DFh
0x18003f3fd  mov     rcx, rsi
0x18003f400  call    HIDSM_AddHidsmEvent
0x18003f405  mov     r8, rsi
0x18003f408  lea     rdx, aSurpriseRemove; "Surprise Remove"
0x18003f40f  mov     rcx, rbx; Object
0x18003f412  call    HidpWaitForSignal
0x18003f417  mov     rcx, rsi
0x18003f41a  call    DestroyPingPongs
0x18003f41f  mov     rcx, rsi
0x18003f422  call    HidpFdoDrainDeviceResetNotifications
0x18003f427  mov     rcx, rsi
0x18003f42a  call    HidpFdoDrainDevicePresenceNotifications
0x18003f42f  call    Feature_UHSSRI01__private_IsEnabledDeviceUsageNoInline
0x18003f434  test    eax, eax
0x18003f436  jz      short loc_18003F440
0x18003f438  mov     rcx, rsi
0x18003f43b  call    HidpUnregisterSleepstudyBlockerReasons
0x18003f440  mov     rax, [rdi+0B8h]
0x18003f447  mov     rdx, rdi
0x18003f44a  movups  xmm0, xmmword ptr [rax]
0x18003f44d  movups  xmmword ptr [rax-48h], xmm0
0x18003f451  movups  xmm1, xmmword ptr [rax+10h]
0x18003f455  movups  xmmword ptr [rax-38h], xmm1
0x18003f459  movups  xmm0, xmmword ptr [rax+20h]
0x18003f45d  movups  xmmword ptr [rax-28h], xmm0
0x18003f461  movsd   xmm1, qword ptr [rax+30h]
0x18003f466  movsd   qword ptr [rax-18h], xmm1
0x18003f46b  mov     byte ptr [rax-45h], 0
0x18003f46f  mov     rcx, [rsi]
0x18003f472  call    HidpCallDriver
0x18003f477  jmp     loc_18003F527
0x18003f47c  cmp     dword ptr [r15+8], 0
0x18003f481  jnz     short loc_18003F440
0x18003f483  mov     rdx, rdi
0x18003f486  mov     rcx, rbx
0x18003f489  call    HidpFdoQueryDeviceRelations
0x18003f48e  mov     ebx, eax
0x18003f490  test    eax, eax
0x18003f492  js      loc_18003F538
0x18003f498  mov     [rdi+30h], eax
0x18003f49b  jmp     short loc_18003F440
0x18003f49d  mov     dword ptr [rdi+30h], 0
0x18003f4a4  jmp     short loc_18003F440
0x18003f4a6  lea     rbx, [rsi+728h]
0x18003f4ad  mov     rcx, rbx; Event
0x18003f4b0  call    cs:__imp_KeClearEvent
0x18003f4b7  nop     dword ptr [rax+rax+00h]
0x18003f4bc  mov     edx, 7DBh
0x18003f4c1  mov     rcx, rsi
0x18003f4c4  call    HIDSM_AddHidsmEvent
0x18003f4c9  mov     r8, rsi
0x18003f4cc  lea     rdx, aStopDevice; "Stop Device"
0x18003f4d3  mov     rcx, rbx; Object
0x18003f4d6  call    HidpWaitForSignal
0x18003f4db  mov     rcx, rsi
0x18003f4de  call    CancelAllPingPongIrps
0x18003f4e3  mov     rax, [rdi+0B8h]
0x18003f4ea  mov     rdx, rdi
0x18003f4ed  movups  xmm0, xmmword ptr [rax]
0x18003f4f0  movups  xmmword ptr [rax-48h], xmm0
0x18003f4f4  movups  xmm1, xmmword ptr [rax+10h]
0x18003f4f8  movups  xmmword ptr [rax-38h], xmm1
0x18003f4fc  movups  xmm0, xmmword ptr [rax+20h]
0x18003f500  movups  xmmword ptr [rax-28h], xmm0
0x18003f504  movsd   xmm1, qword ptr [rax+30h]
0x18003f509  movsd   qword ptr [rax-18h], xmm1
0x18003f50e  mov     byte ptr [rax-45h], 0
0x18003f512  mov     rcx, [rsi]
0x18003f515  call    HidpCallDriverSynchronous
0x18003f51a  jmp     short loc_18003F536
0x18003f51c  mov     rdx, rdi
0x18003f51f  mov     rcx, rsi
0x18003f522  call    HidpFdoRemoveDevice
0x18003f527  mov     ebx, eax
0x18003f529  jmp     short loc_18003F54C
0x18003f52b  mov     rdx, rdi
0x18003f52e  mov     rcx, rbx
0x18003f531  call    HidpFdoStartDevice
0x18003f536  mov     ebx, eax
0x18003f538  xor     edx, edx; PriorityBoost
0x18003f53a  mov     [rdi+30h], ebx
0x18003f53d  mov     rcx, rdi; Irp
0x18003f540  call    cs:__imp_IofCompleteRequest
0x18003f547  nop     dword ptr [rax+rax+00h]
0x18003f54c  mov     ecx, 80000000h
0x18003f551  lea     eax, [rbx+rcx]
0x18003f554  test    ecx, eax
0x18003f556  jnz     loc_18003F61D
0x18003f55c  cmp     ebx, 0C00000BBh
0x18003f562  jz      loc_18003F61D
0x18003f568  mov     ecx, ebp
0x18003f56a  test    ebp, ebp
0x18003f56c  jz      short loc_18003F595
0x18003f56e  sub     ecx, 1
0x18003f571  jz      short loc_18003F595
0x18003f573  sub     ecx, 1
0x18003f576  jz      short loc_18003F595
0x18003f578  sub     ecx, 1
0x18003f57b  jz      short loc_18003F595
0x18003f57d  sub     ecx, 1
0x18003f580  jz      short loc_18003F595
0x18003f582  sub     ecx, 1
0x18003f585  jz      short loc_18003F595
0x18003f587  sub     ecx, 1
0x18003f58a  jz      short loc_18003F595
0x18003f58c  cmp     ecx, 11h
0x18003f58f  jnz     loc_18003F61D
0x18003f595  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f59c  lea     rax, WPP_GLOBAL_Control
0x18003f5a3  cmp     rcx, rax
0x18003f5a6  jz      short loc_18003F5B5
0x18003f5a8  mov     eax, [rcx+2Ch]
0x18003f5ab  test    al, 8
0x18003f5ad  jz      short loc_18003F5B5
0x18003f5af  cmp     byte ptr [rcx+29h], 4
0x18003f5b3  jnb     short loc_18003F5B8
0x18003f5b5  xor     r14b, r14b
0x18003f5b8  lea     rax, WPP_RECORDER_INITIALIZED
0x18003f5bf  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18003f5c6  setnz   r8b
0x18003f5ca  test    r14b, r14b
0x18003f5cd  jnz     short loc_18003F5D4
0x18003f5cf  test    r8b, r8b
0x18003f5d2  jz      short loc_18003F61D
0x18003f5d4  mov     rax, [rsi]
0x18003f5d7  mov     dl, r14b
0x18003f5da  mov     r9, [rsi+2A0h]
0x18003f5e1  mov     rcx, [rcx+18h]
0x18003f5e5  mov     [rsp+0A8h+var_48], ebx
0x18003f5e9  mov     [rsp+0A8h+var_50], bpl
0x18003f5ee  mov     [rsp+0A8h+var_58], 1Bh
0x18003f5f3  mov     [rsp+0A8h+var_60], rdi
0x18003f5f8  mov     [rsp+0A8h+var_68], rax
0x18003f5fd  lea     rax, WPP_09551ba6d0fe3383c1d3f23d6d3d8f25_Traceguids
0x18003f604  mov     [rsp+0A8h+var_70], rax
0x18003f609  mov     [rsp+0A8h+var_78], 4Ah ; 'J'
0x18003f610  mov     [rsp+0A8h+var_80], 4
0x18003f618  call    WPP_RECORDER_AND_TRACE_SF_qqccd
0x18003f61d  mov     eax, ebx
0x18003f61f  add     rsp, 78h
0x18003f623  pop     r15
0x18003f625  pop     r14
0x18003f627  pop     rdi
0x18003f628  pop     rsi
0x18003f629  pop     rbp
0x18003f62a  pop     rbx
0x18003f62b  retn
```
