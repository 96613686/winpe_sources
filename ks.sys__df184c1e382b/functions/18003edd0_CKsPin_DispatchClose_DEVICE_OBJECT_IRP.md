# CKsPin::DispatchClose(_DEVICE_OBJECT *,_IRP *)

- ea: `0x18003edd0`
- end: `0x18003f2e2`
- name: `?DispatchClose@CKsPin@@SAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `1298`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003ec60`
- `0x18005653c`

## callees

- `0x18000aa80`
- `0x18000b7bc`
- `0x18000c630`
- `0x18000dddc`
- `0x18000fe40`
- `0x180013a88`
- `0x1800159b0`
- `0x180019cb0`
- `0x18003edd0`
- `0x180041bcc`
- `0x180051ba8`
- `0x180066920`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x18003f0ef`
- `ntoskrnl!ObfDereferenceObject` at `0x18003f10e`
- `ntoskrnl!ObfDereferenceObject` at `0x18003f175`
- `ntoskrnl!ObfDereferenceObject` at `0x18003f2c2`
- `ntoskrnl!ObfDereferenceObject` at `0x18003f0ef`
- `ntoskrnl!ObfDereferenceObject` at `0x18003f10e`
- `ntoskrnl!ObfDereferenceObject` at `0x18003f175`
- `ntoskrnl!ObfDereferenceObject` at `0x18003f2c2`
- `ntoskrnl!KeResetEvent` at `0x18003f134`
- `ntoskrnl!KeResetEvent` at `0x18003f134`
- `ntoskrnl!KeWaitForSingleObject` at `0x18003f162`
- `ntoskrnl!KeWaitForSingleObject` at `0x18003f274`
- `ntoskrnl!KeWaitForSingleObject` at `0x18003f162`
- `ntoskrnl!KeWaitForSingleObject` at `0x18003f274`
- `ntoskrnl!IofCompleteRequest` at `0x18003ee97`
- `ntoskrnl!IofCompleteRequest` at `0x18003f2b3`
- `ntoskrnl!IofCompleteRequest` at `0x18003ee97`
- `ntoskrnl!IofCompleteRequest` at `0x18003f2b3`
- `ntoskrnl!KeInitializeEvent` at `0x18003f209`
- `ntoskrnl!KeInitializeEvent` at `0x18003f209`

## pseudocode

```c
__int64 __fastcall CKsPin::DispatchClose(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  struct _IRP *v2; // rdi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdx
  __int64 v4; // r14
  char MajorFunction; // al
  __int64 v6; // rbx
  int v8; // edx
  int v9; // r8d
  void *v10; // rcx
  int v11; // edx
  void *v12; // rcx
  int v13; // r8d
  __int64 v14; // rcx
  void *v15; // rcx
  void *v16; // rcx
  struct _FILE_OBJECT *RelatedFileObject; // rbp
  unsigned int v18; // eax
  unsigned int v19; // esi
  int v20; // edx
  int v21; // edx
  struct _KEVENT Event; // [rsp+40h] [rbp-68h] BYREF

  v2 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      92,
      (__int64)WPP_9505c27395793143ec5446714e36088f_Traceguids);
  }
  CurrentStackLocation = v2->Tail.Overlay.CurrentStackLocation;
  v4 = *(_QWORD *)(*(_QWORD *)CurrentStackLocation->FileObject->FsContext + 112LL);
  MajorFunction = CurrentStackLocation->MajorFunction;
  v6 = v4 - 128;
  if ( CurrentStackLocation->MajorFunction == 18 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LOBYTE(CurrentStackLocation) = 5;
        WPP_RECORDER_SF_D(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)CurrentStackLocation,
          1,
          93,
          (__int64)WPP_9505c27395793143ec5446714e36088f_Traceguids,
          *(_DWORD *)(v4 + 152));
      }
    }
    CKsPin::StopAndRemoveProcessPin((CKsPin *)(v4 - 128), v2);
    v2->IoStatus.Status = 0;
    IofCompleteRequest(v2, 0);
    return 0;
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(CurrentStackLocation) = 5;
      WPP_RECORDER_SF_DD(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)CurrentStackLocation,
        1,
        94,
        (__int64)WPP_9505c27395793143ec5446714e36088f_Traceguids,
        *(_DWORD *)(v4 + 152),
        MajorFunction);
    }
    (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v4 + 72) + 72LL))(*(_QWORD *)(v4 + 72), v6 + 1032);
    v10 = *(void **)(v6 + 1104);
    if ( v10 )
    {
      KsUnregisterWorker(v10);
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LOBYTE(v8) = 5;
        WPP_RECORDER_SF_qqd(
          WPP_GLOBAL_Control->DeviceExtension,
          v8,
          v9,
          95,
          (__int64)WPP_9505c27395793143ec5446714e36088f_Traceguids,
          v4 + 0x80,
          *(_QWORD *)(v6 + 1104),
          *(_DWORD *)(v6 + 716));
      }
      *(_QWORD *)(v6 + 1104) = 0;
    }
    if ( *(_DWORD *)(v6 + 968) && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = 4;
      WPP_RECORDER_SF_qd(
        WPP_GLOBAL_Control->DeviceExtension,
        v8,
        v9,
        96,
        (__int64)WPP_9505c27395793143ec5446714e36088f_Traceguids,
        v4 + 0x80,
        *(_DWORD *)(v6 + 968));
    }
    *(_QWORD *)(v6 + 848) = 0;
    CKsPin::StopAndRemoveProcessPin((CKsPin *)(v4 - 128), v2);
    v12 = *(void **)(v6 + 840);
    if ( v12 )
    {
      KsUnregisterWorker(v12);
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LOBYTE(v11) = 5;
        WPP_RECORDER_SF_qqd(
          WPP_GLOBAL_Control->DeviceExtension,
          v11,
          v13,
          97,
          (__int64)WPP_9505c27395793143ec5446714e36088f_Traceguids,
          v4 + 0x80,
          *(_QWORD *)(v6 + 840),
          *(_DWORD *)(v6 + 716));
      }
      *(_QWORD *)(v6 + 840) = 0;
    }
    if ( *(_QWORD *)(v6 + 696) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v11) = 4;
        WPP_RECORDER_SF_q(
          WPP_GLOBAL_Control->DeviceExtension,
          v11,
          1,
          98,
          (__int64)WPP_9505c27395793143ec5446714e36088f_Traceguids,
          v4 + 0x80);
      }
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v6 + 696) + 16LL))(*(_QWORD *)(v6 + 696));
      *(_QWORD *)(v6 + 696) = 0;
    }
    if ( *(_QWORD *)(v6 + 704) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v11) = 4;
        WPP_RECORDER_SF_q(
          WPP_GLOBAL_Control->DeviceExtension,
          v11,
          1,
          99,
          (__int64)WPP_9505c27395793143ec5446714e36088f_Traceguids,
          v4 + 0x80);
      }
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v6 + 704) + 16LL))(*(_QWORD *)(v6 + 704));
      *(_QWORD *)(v6 + 704) = 0;
    }
    if ( *(_QWORD *)(v6 + 856) )
    {
      v14 = *(_QWORD *)(v6 + 832);
      if ( v14 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 24LL))(v14);
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v6 + 832) + 16LL))(*(_QWORD *)(v6 + 832));
        *(_QWORD *)(v6 + 832) = 0;
      }
      ObfDereferenceObject(*(PVOID *)(v6 + 856));
      *(_QWORD *)(v6 + 856) = 0;
    }
    v15 = *(void **)(v6 + 600);
    if ( v15 )
    {
      ObfDereferenceObject(v15);
      *(_QWORD *)(v6 + 600) = 0;
    }
    if ( *(_QWORD *)(v6 + 888) )
    {
      KeResetEvent((PRKEVENT)(v6 + 936));
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v6 + 928), 0xFFFFFFFF) > 1 )
        KeWaitForSingleObject((PVOID)(v6 + 936), Suspended, 0, 0, 0);
      ObfDereferenceObject(*(PVOID *)(v6 + 888));
      *(_QWORD *)(v6 + 888) = 0;
    }
    v16 = *(void **)(v6 + 880);
    if ( v16 )
    {
      KsFreeDefaultClock(v16);
      *(_QWORD *)(v6 + 880) = 0;
    }
    RelatedFileObject = v2->Tail.Overlay.CurrentStackLocation->FileObject->RelatedFileObject;
    v18 = KspClose(v2, v4);
    v19 = v18;
    if ( v18 != 259 )
    {
      --**(_DWORD **)(v6 + 688);
      if ( v18 == -1073741802 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v4 - 128);
      }
      else
      {
        memset(&Event, 0, sizeof(Event));
        KeInitializeEvent(&Event, SynchronizationEvent, 0);
        *(_QWORD *)(v6 + 872) = &Event;
        if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6) )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v20) = 4;
            WPP_RECORDER_SF_q(
              WPP_GLOBAL_Control->DeviceExtension,
              v20,
              1,
              100,
              (__int64)WPP_9505c27395793143ec5446714e36088f_Traceguids,
              v4 + 0x80);
          }
          KeWaitForSingleObject(&Event, Suspended, 0, 0, 0);
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v21) = 4;
            WPP_RECORDER_SF_q(
              WPP_GLOBAL_Control->DeviceExtension,
              v21,
              1,
              101,
              (__int64)WPP_9505c27395793143ec5446714e36088f_Traceguids,
              v4 + 0x80);
          }
        }
        IofCompleteRequest(v2, 0);
      }
      ObfDereferenceObject(RelatedFileObject);
    }
    return v19;
  }
}

```

## disassembly

```asm
0x18003edd0  push    rbx
0x18003edd2  push    rbp
0x18003edd3  push    rsi
0x18003edd4  push    rdi
0x18003edd5  push    r12
0x18003edd7  push    r13
0x18003edd9  push    r14
0x18003eddb  push    r15
0x18003eddd  sub     rsp, 68h
0x18003ede1  mov     rdi, rdx
0x18003ede4  xor     r15d, r15d
0x18003ede7  lea     r12, WPP_RECORDER_INITIALIZED
0x18003edee  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18003edf5  lea     r13, WPP_9505c27395793143ec5446714e36088f_Traceguids
0x18003edfc  lea     esi, [r15+1]
0x18003ee00  jz      short loc_18003EE27
0x18003ee02  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ee09  cmp     [rcx+48h], r15w
0x18003ee0e  jz      short loc_18003EE27
0x18003ee10  mov     rcx, [rcx+40h]
0x18003ee14  lea     r9d, [r15+5Ch]
0x18003ee18  mov     r8d, esi
0x18003ee1b  mov     [rsp+0A8h+Timeout], r13
0x18003ee20  mov     dl, 5
0x18003ee22  call    WPP_RECORDER_SF_
0x18003ee27  mov     rdx, [rdi+0B8h]
0x18003ee2e  mov     rax, [rdx+30h]
0x18003ee32  mov     rcx, [rax+18h]
0x18003ee36  mov     rax, [rcx]
0x18003ee39  mov     r14, [rax+70h]
0x18003ee3d  movzx   eax, byte ptr [rdx]
0x18003ee40  lea     rbx, [r14-80h]
0x18003ee44  cmp     al, 12h
0x18003ee46  jnz     short loc_18003EEAA
0x18003ee48  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18003ee4f  jz      short loc_18003EE83
0x18003ee51  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ee58  cmp     [rcx+48h], r15w
0x18003ee5d  jz      short loc_18003EE83
0x18003ee5f  mov     eax, [r14+98h]
0x18003ee66  mov     r9d, 5Dh ; ']'
0x18003ee6c  mov     rcx, [rcx+40h]
0x18003ee70  mov     r8d, esi
0x18003ee73  mov     dword ptr [rsp+0A8h+var_80], eax
0x18003ee77  mov     dl, 5
0x18003ee79  mov     [rsp+0A8h+Timeout], r13
0x18003ee7e  call    WPP_RECORDER_SF_D
0x18003ee83  mov     rdx, rdi; struct _IRP *
0x18003ee86  mov     rcx, rbx; this
0x18003ee89  call    ?StopAndRemoveProcessPin@CKsPin@@AEAAXPEAU_IRP@@@Z; CKsPin::StopAndRemoveProcessPin(_IRP *)
0x18003ee8e  xor     edx, edx; PriorityBoost
0x18003ee90  mov     [rdi+30h], r15d
0x18003ee94  mov     rcx, rdi; Irp
0x18003ee97  call    cs:__imp_IofCompleteRequest
0x18003ee9e  nop     dword ptr [rax+rax+00h]
0x18003eea3  xor     eax, eax
0x18003eea5  jmp     loc_18003F2D0
0x18003eeaa  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18003eeb1  jz      short loc_18003EEE9
0x18003eeb3  mov     rcx, cs:WPP_GLOBAL_Control
0x18003eeba  cmp     [rcx+48h], r15w
0x18003eebf  jz      short loc_18003EEE9
0x18003eec1  mov     rcx, [rcx+40h]
0x18003eec5  mov     r9d, 5Eh ; '^'
0x18003eecb  mov     dword ptr [rsp+0A8h+var_78], eax
0x18003eecf  mov     r8d, esi
0x18003eed2  mov     eax, [r14+98h]
0x18003eed9  mov     dl, 5
0x18003eedb  mov     dword ptr [rsp+0A8h+var_80], eax
0x18003eedf  mov     [rsp+0A8h+Timeout], r13
0x18003eee4  call    WPP_RECORDER_SF_DD
0x18003eee9  mov     rcx, [r14+48h]
0x18003eeed  lea     rdx, [rbx+408h]
0x18003eef4  mov     rax, [rcx]
0x18003eef7  mov     rax, [rax+48h]
0x18003eefb  call    _guard_dispatch_icall
0x18003ef00  mov     rcx, [rbx+450h]; Worker
0x18003ef07  test    rcx, rcx
0x18003ef0a  jz      short loc_18003EF60
0x18003ef0c  call    KsUnregisterWorker
0x18003ef11  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18003ef18  jz      short loc_18003EF59
0x18003ef1a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ef21  cmp     [rcx+48h], r15w
0x18003ef26  jz      short loc_18003EF59
0x18003ef28  mov     eax, [rbx+2CCh]
0x18003ef2e  mov     r9d, 5Fh ; '_'
0x18003ef34  mov     rcx, [rcx+40h]
0x18003ef38  mov     dl, 5
0x18003ef3a  mov     [rsp+0A8h+var_70], eax
0x18003ef3e  mov     rax, [rbx+450h]
0x18003ef45  mov     [rsp+0A8h+var_78], rax
0x18003ef4a  mov     [rsp+0A8h+var_80], rbx
0x18003ef4f  mov     [rsp+0A8h+Timeout], r13
0x18003ef54  call    WPP_RECORDER_SF_qqd
0x18003ef59  mov     [rbx+450h], r15
0x18003ef60  mov     eax, [rbx+3C8h]
0x18003ef66  test    eax, eax
0x18003ef68  jz      short loc_18003EF99
0x18003ef6a  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18003ef71  jz      short loc_18003EF99
0x18003ef73  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ef7a  mov     r9d, 60h ; '`'
0x18003ef80  mov     dword ptr [rsp+0A8h+var_78], eax
0x18003ef84  mov     dl, 4
0x18003ef86  mov     [rsp+0A8h+var_80], rbx
0x18003ef8b  mov     [rsp+0A8h+Timeout], r13
0x18003ef90  mov     rcx, [rcx+40h]
0x18003ef94  call    WPP_RECORDER_SF_qd
0x18003ef99  mov     rdx, rdi; struct _IRP *
0x18003ef9c  mov     [rbx+350h], r15
0x18003efa3  mov     rcx, rbx; this
0x18003efa6  call    ?StopAndRemoveProcessPin@CKsPin@@AEAAXPEAU_IRP@@@Z; CKsPin::StopAndRemoveProcessPin(_IRP *)
0x18003efab  mov     rcx, [rbx+348h]; Worker
0x18003efb2  test    rcx, rcx
0x18003efb5  jz      short loc_18003F00B
0x18003efb7  call    KsUnregisterWorker
0x18003efbc  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18003efc3  jz      short loc_18003F004
0x18003efc5  mov     rcx, cs:WPP_GLOBAL_Control
0x18003efcc  cmp     [rcx+48h], r15w
0x18003efd1  jz      short loc_18003F004
0x18003efd3  mov     eax, [rbx+2CCh]
0x18003efd9  mov     r9d, 61h ; 'a'
0x18003efdf  mov     rcx, [rcx+40h]
0x18003efe3  mov     dl, 5
0x18003efe5  mov     [rsp+0A8h+var_70], eax
0x18003efe9  mov     rax, [rbx+348h]
0x18003eff0  mov     [rsp+0A8h+var_78], rax
0x18003eff5  mov     [rsp+0A8h+var_80], rbx
0x18003effa  mov     [rsp+0A8h+Timeout], r13
0x18003efff  call    WPP_RECORDER_SF_qqd
0x18003f004  mov     [rbx+348h], r15
0x18003f00b  cmp     [rbx+2B8h], r15
0x18003f012  jz      short loc_18003F05C
0x18003f014  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18003f01b  jz      short loc_18003F042
0x18003f01d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f024  mov     r9d, 62h ; 'b'
0x18003f02a  mov     [rsp+0A8h+var_80], rbx
0x18003f02f  mov     r8d, esi
0x18003f032  mov     dl, 4
0x18003f034  mov     [rsp+0A8h+Timeout], r13
0x18003f039  mov     rcx, [rcx+40h]
0x18003f03d  call    WPP_RECORDER_SF_q
0x18003f042  mov     rcx, [rbx+2B8h]
0x18003f049  mov     rax, [rcx]
0x18003f04c  mov     rax, [rax+10h]
0x18003f050  call    _guard_dispatch_icall
0x18003f055  mov     [rbx+2B8h], r15
0x18003f05c  cmp     [rbx+2C0h], r15
0x18003f063  jz      short loc_18003F0AD
0x18003f065  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18003f06c  jz      short loc_18003F093
0x18003f06e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f075  mov     r9d, 63h ; 'c'
0x18003f07b  mov     [rsp+0A8h+var_80], rbx
0x18003f080  mov     r8d, esi
0x18003f083  mov     dl, 4
0x18003f085  mov     [rsp+0A8h+Timeout], r13
0x18003f08a  mov     rcx, [rcx+40h]
0x18003f08e  call    WPP_RECORDER_SF_q
0x18003f093  mov     rcx, [rbx+2C0h]
0x18003f09a  mov     rax, [rcx]
0x18003f09d  mov     rax, [rax+10h]
0x18003f0a1  call    _guard_dispatch_icall
0x18003f0a6  mov     [rbx+2C0h], r15
0x18003f0ad  cmp     [rbx+358h], r15
0x18003f0b4  jz      short loc_18003F102
0x18003f0b6  mov     rcx, [rbx+340h]
0x18003f0bd  test    rcx, rcx
0x18003f0c0  jz      short loc_18003F0E8
0x18003f0c2  mov     rax, [rcx]
0x18003f0c5  mov     rax, [rax+18h]
0x18003f0c9  call    _guard_dispatch_icall
0x18003f0ce  mov     rcx, [rbx+340h]
0x18003f0d5  mov     rax, [rcx]
0x18003f0d8  mov     rax, [rax+10h]
0x18003f0dc  call    _guard_dispatch_icall
0x18003f0e1  mov     [rbx+340h], r15
0x18003f0e8  mov     rcx, [rbx+358h]; Object
0x18003f0ef  call    cs:__imp_ObfDereferenceObject
0x18003f0f6  nop     dword ptr [rax+rax+00h]
0x18003f0fb  mov     [rbx+358h], r15
0x18003f102  mov     rcx, [rbx+258h]; Object
0x18003f109  test    rcx, rcx
0x18003f10c  jz      short loc_18003F121
0x18003f10e  call    cs:__imp_ObfDereferenceObject
0x18003f115  nop     dword ptr [rax+rax+00h]
0x18003f11a  mov     [rbx+258h], r15
0x18003f121  cmp     [rbx+378h], r15
0x18003f128  jz      short loc_18003F188
0x18003f12a  lea     rsi, [rbx+3A8h]
0x18003f131  mov     rcx, rsi; Event
0x18003f134  call    cs:__imp_KeResetEvent
0x18003f13b  nop     dword ptr [rax+rax+00h]
0x18003f140  or      eax, 0FFFFFFFFh
0x18003f143  lock xadd [rbx+3A0h], eax
0x18003f14b  sub     eax, 1
0x18003f14e  jle     short loc_18003F16E
0x18003f150  xor     r9d, r9d; Alertable
0x18003f153  mov     [rsp+0A8h+Timeout], r15; Timeout
0x18003f158  xor     r8d, r8d; WaitMode
0x18003f15b  mov     rcx, rsi; Object
0x18003f15e  lea     edx, [r9+5]; WaitReason
0x18003f162  call    cs:__imp_KeWaitForSingleObject
0x18003f169  nop     dword ptr [rax+rax+00h]
0x18003f16e  mov     rcx, [rbx+378h]; Object
0x18003f175  call    cs:__imp_ObfDereferenceObject
0x18003f17c  nop     dword ptr [rax+rax+00h]
0x18003f181  mov     [rbx+378h], r15
0x18003f188  mov     rcx, [rbx+370h]; DefaultClock
0x18003f18f  test    rcx, rcx
0x18003f192  jz      short loc_18003F1A0
0x18003f194  call    KsFreeDefaultClock
0x18003f199  mov     [rbx+370h], r15
0x18003f1a0  mov     rax, [rdi+0B8h]
0x18003f1a7  mov     rdx, r14
0x18003f1aa  mov     rcx, [rax+30h]
0x18003f1ae  mov     rbp, [rcx+40h]
0x18003f1b2  mov     rcx, rdi
0x18003f1b5  call    KspClose
0x18003f1ba  mov     esi, eax
0x18003f1bc  cmp     eax, 103h
0x18003f1c1  jz      loc_18003F2CE
0x18003f1c7  mov     rcx, [rbx+2B0h]
0x18003f1ce  dec     dword ptr [rcx]
0x18003f1d0  cmp     eax, 0C0000016h
0x18003f1d5  jnz     short loc_18003F1EB
0x18003f1d7  mov     rcx, [rbx]
0x18003f1da  mov     rax, [rcx+10h]
0x18003f1de  mov     rcx, rbx
0x18003f1e1  call    _guard_dispatch_icall
0x18003f1e6  jmp     loc_18003F2BF
0x18003f1eb  xor     eax, eax
0x18003f1ed  lea     rcx, [rsp+0A8h+Event]; Event
0x18003f1f2  xorps   xmm0, xmm0
0x18003f1f5  mov     [rsp+0A8h+Event.Header.WaitListHead.Blink], rax
0x18003f1fa  xor     r8d, r8d; State
0x18003f1fd  movups  xmmword ptr [rsp+0A8h+Event.Header], xmm0
0x18003f202  lea     r14d, [rax+1]
0x18003f206  mov     edx, r14d; Type
0x18003f209  call    cs:__imp_KeInitializeEvent
0x18003f210  nop     dword ptr [rax+rax+00h]
0x18003f215  lea     rax, [rsp+0A8h+Event]
0x18003f21a  mov     rcx, rbx
0x18003f21d  mov     [rbx+368h], rax
0x18003f224  mov     rax, [rbx]
0x18003f227  mov     rax, [rax+10h]
0x18003f22b  call    _guard_dispatch_icall
0x18003f230  test    eax, eax
0x18003f232  jz      short loc_18003F2AE
0x18003f234  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18003f23b  jz      short loc_18003F260
0x18003f23d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f244  lea     r9d, [r14+63h]
0x18003f248  mov     [rsp+0A8h+var_80], rbx
0x18003f24d  mov     r8d, r14d
0x18003f250  mov     dl, 4
0x18003f252  mov     [rsp+0A8h+Timeout], r13
0x18003f257  mov     rcx, [rcx+40h]
0x18003f25b  call    WPP_RECORDER_SF_q
0x18003f260  xor     r9d, r9d; Alertable
0x18003f263  mov     [rsp+0A8h+Timeout], r15; Timeout
0x18003f268  xor     r8d, r8d; WaitMode
0x18003f26b  lea     rcx, [rsp+0A8h+Event]; Object
0x18003f270  lea     edx, [r9+5]; WaitReason
0x18003f274  call    cs:__imp_KeWaitForSingleObject
0x18003f27b  nop     dword ptr [rax+rax+00h]
0x18003f280  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18003f287  jz      short loc_18003F2AE
0x18003f289  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f290  mov     r9d, 65h ; 'e'
0x18003f296  mov     [rsp+0A8h+var_80], rbx
0x18003f29b  mov     r8d, r14d
0x18003f29e  mov     dl, 4
0x18003f2a0  mov     [rsp+0A8h+Timeout], r13
0x18003f2a5  mov     rcx, [rcx+40h]
0x18003f2a9  call    WPP_RECORDER_SF_q
0x18003f2ae  xor     edx, edx; PriorityBoost
0x18003f2b0  mov     rcx, rdi; Irp
0x18003f2b3  call    cs:__imp_IofCompleteRequest
0x18003f2ba  nop     dword ptr [rax+rax+00h]
0x18003f2bf  mov     rcx, rbp; Object
0x18003f2c2  call    cs:__imp_ObfDereferenceObject
0x18003f2c9  nop     dword ptr [rax+rax+00h]
0x18003f2ce  mov     eax, esi
0x18003f2d0  add     rsp, 68h
0x18003f2d4  pop     r15
0x18003f2d6  pop     r14
0x18003f2d8  pop     r13
0x18003f2da  pop     r12
0x18003f2dc  pop     rdi
0x18003f2dd  pop     rsi
0x18003f2de  pop     rbp
0x18003f2df  pop     rbx
0x18003f2e0  retn
```
