# CKsPin::DispatchClose(_DEVICE_OBJECT *,_IRP *)

- ea: `0x18003ede0`
- end: `0x18003f2f2`
- name: `?DispatchClose@CKsPin@@SAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `1298`
- prototype: `static int(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003ec70`
- `0x18005639c`

## callees

- `0x18000aa80`
- `0x18000b7bc`
- `0x18000c630`
- `0x18000dddc`
- `0x18000fe2c`
- `0x180013a88`
- `0x180015960`
- `0x180019c60`
- `0x18003ede0`
- `0x180041bcc`
- `0x180051a08`
- `0x180065fb0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x18003f0ff`
- `ntoskrnl!ObfDereferenceObject` at `0x18003f11e`
- `ntoskrnl!ObfDereferenceObject` at `0x18003f185`
- `ntoskrnl!ObfDereferenceObject` at `0x18003f2d2`
- `ntoskrnl!ObfDereferenceObject` at `0x18003f0ff`
- `ntoskrnl!ObfDereferenceObject` at `0x18003f11e`
- `ntoskrnl!ObfDereferenceObject` at `0x18003f185`
- `ntoskrnl!ObfDereferenceObject` at `0x18003f2d2`
- `ntoskrnl!KeResetEvent` at `0x18003f144`
- `ntoskrnl!KeResetEvent` at `0x18003f144`
- `ntoskrnl!KeWaitForSingleObject` at `0x18003f172`
- `ntoskrnl!KeWaitForSingleObject` at `0x18003f284`
- `ntoskrnl!KeWaitForSingleObject` at `0x18003f172`
- `ntoskrnl!KeWaitForSingleObject` at `0x18003f284`
- `ntoskrnl!IofCompleteRequest` at `0x18003eea7`
- `ntoskrnl!IofCompleteRequest` at `0x18003f2c3`
- `ntoskrnl!IofCompleteRequest` at `0x18003eea7`
- `ntoskrnl!IofCompleteRequest` at `0x18003f2c3`
- `ntoskrnl!KeInitializeEvent` at `0x18003f219`
- `ntoskrnl!KeInitializeEvent` at `0x18003f219`

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
      (__int64)WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids);
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
          (__int64)WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids,
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
        (__int64)WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids,
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
          (__int64)WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids,
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
        (__int64)WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids,
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
          (__int64)WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids,
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
          (__int64)WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids,
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
          (__int64)WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids,
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
              (__int64)WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids,
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
              (__int64)WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids,
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
0x18003ede0  push    rbx
0x18003ede2  push    rbp
0x18003ede3  push    rsi
0x18003ede4  push    rdi
0x18003ede5  push    r12
0x18003ede7  push    r13
0x18003ede9  push    r14
0x18003edeb  push    r15
0x18003eded  sub     rsp, 68h
0x18003edf1  mov     rdi, rdx
0x18003edf4  xor     r15d, r15d
0x18003edf7  lea     r12, WPP_RECORDER_INITIALIZED
0x18003edfe  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18003ee05  lea     r13, WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids
0x18003ee0c  lea     esi, [r15+1]
0x18003ee10  jz      short loc_18003EE37
0x18003ee12  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ee19  cmp     [rcx+48h], r15w
0x18003ee1e  jz      short loc_18003EE37
0x18003ee20  mov     rcx, [rcx+40h]
0x18003ee24  lea     r9d, [r15+5Ch]
0x18003ee28  mov     r8d, esi
0x18003ee2b  mov     [rsp+0A8h+Timeout], r13
0x18003ee30  mov     dl, 5
0x18003ee32  call    WPP_RECORDER_SF_
0x18003ee37  mov     rdx, [rdi+0B8h]
0x18003ee3e  mov     rax, [rdx+30h]
0x18003ee42  mov     rcx, [rax+18h]
0x18003ee46  mov     rax, [rcx]
0x18003ee49  mov     r14, [rax+70h]
0x18003ee4d  movzx   eax, byte ptr [rdx]
0x18003ee50  lea     rbx, [r14-80h]
0x18003ee54  cmp     al, 12h
0x18003ee56  jnz     short loc_18003EEBA
0x18003ee58  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18003ee5f  jz      short loc_18003EE93
0x18003ee61  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ee68  cmp     [rcx+48h], r15w
0x18003ee6d  jz      short loc_18003EE93
0x18003ee6f  mov     eax, [r14+98h]
0x18003ee76  mov     r9d, 5Dh ; ']'
0x18003ee7c  mov     rcx, [rcx+40h]
0x18003ee80  mov     r8d, esi
0x18003ee83  mov     dword ptr [rsp+0A8h+var_80], eax
0x18003ee87  mov     dl, 5
0x18003ee89  mov     [rsp+0A8h+Timeout], r13
0x18003ee8e  call    WPP_RECORDER_SF_D
0x18003ee93  mov     rdx, rdi; struct _IRP *
0x18003ee96  mov     rcx, rbx; this
0x18003ee99  call    ?StopAndRemoveProcessPin@CKsPin@@AEAAXPEAU_IRP@@@Z; CKsPin::StopAndRemoveProcessPin(_IRP *)
0x18003ee9e  xor     edx, edx; PriorityBoost
0x18003eea0  mov     [rdi+30h], r15d
0x18003eea4  mov     rcx, rdi; Irp
0x18003eea7  call    cs:__imp_IofCompleteRequest
0x18003eeae  nop     dword ptr [rax+rax+00h]
0x18003eeb3  xor     eax, eax
0x18003eeb5  jmp     loc_18003F2E0
0x18003eeba  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18003eec1  jz      short loc_18003EEF9
0x18003eec3  mov     rcx, cs:WPP_GLOBAL_Control
0x18003eeca  cmp     [rcx+48h], r15w
0x18003eecf  jz      short loc_18003EEF9
0x18003eed1  mov     rcx, [rcx+40h]
0x18003eed5  mov     r9d, 5Eh ; '^'
0x18003eedb  mov     dword ptr [rsp+0A8h+var_78], eax
0x18003eedf  mov     r8d, esi
0x18003eee2  mov     eax, [r14+98h]
0x18003eee9  mov     dl, 5
0x18003eeeb  mov     dword ptr [rsp+0A8h+var_80], eax
0x18003eeef  mov     [rsp+0A8h+Timeout], r13
0x18003eef4  call    WPP_RECORDER_SF_DD
0x18003eef9  mov     rcx, [r14+48h]
0x18003eefd  lea     rdx, [rbx+408h]
0x18003ef04  mov     rax, [rcx]
0x18003ef07  mov     rax, [rax+48h]
0x18003ef0b  call    _guard_dispatch_icall
0x18003ef10  mov     rcx, [rbx+450h]; Worker
0x18003ef17  test    rcx, rcx
0x18003ef1a  jz      short loc_18003EF70
0x18003ef1c  call    KsUnregisterWorker
0x18003ef21  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18003ef28  jz      short loc_18003EF69
0x18003ef2a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ef31  cmp     [rcx+48h], r15w
0x18003ef36  jz      short loc_18003EF69
0x18003ef38  mov     eax, [rbx+2CCh]
0x18003ef3e  mov     r9d, 5Fh ; '_'
0x18003ef44  mov     rcx, [rcx+40h]
0x18003ef48  mov     dl, 5
0x18003ef4a  mov     [rsp+0A8h+var_70], eax
0x18003ef4e  mov     rax, [rbx+450h]
0x18003ef55  mov     [rsp+0A8h+var_78], rax
0x18003ef5a  mov     [rsp+0A8h+var_80], rbx
0x18003ef5f  mov     [rsp+0A8h+Timeout], r13
0x18003ef64  call    WPP_RECORDER_SF_qqd
0x18003ef69  mov     [rbx+450h], r15
0x18003ef70  mov     eax, [rbx+3C8h]
0x18003ef76  test    eax, eax
0x18003ef78  jz      short loc_18003EFA9
0x18003ef7a  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18003ef81  jz      short loc_18003EFA9
0x18003ef83  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ef8a  mov     r9d, 60h ; '`'
0x18003ef90  mov     dword ptr [rsp+0A8h+var_78], eax
0x18003ef94  mov     dl, 4
0x18003ef96  mov     [rsp+0A8h+var_80], rbx
0x18003ef9b  mov     [rsp+0A8h+Timeout], r13
0x18003efa0  mov     rcx, [rcx+40h]
0x18003efa4  call    WPP_RECORDER_SF_qd
0x18003efa9  mov     rdx, rdi; struct _IRP *
0x18003efac  mov     [rbx+350h], r15
0x18003efb3  mov     rcx, rbx; this
0x18003efb6  call    ?StopAndRemoveProcessPin@CKsPin@@AEAAXPEAU_IRP@@@Z; CKsPin::StopAndRemoveProcessPin(_IRP *)
0x18003efbb  mov     rcx, [rbx+348h]; Worker
0x18003efc2  test    rcx, rcx
0x18003efc5  jz      short loc_18003F01B
0x18003efc7  call    KsUnregisterWorker
0x18003efcc  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18003efd3  jz      short loc_18003F014
0x18003efd5  mov     rcx, cs:WPP_GLOBAL_Control
0x18003efdc  cmp     [rcx+48h], r15w
0x18003efe1  jz      short loc_18003F014
0x18003efe3  mov     eax, [rbx+2CCh]
0x18003efe9  mov     r9d, 61h ; 'a'
0x18003efef  mov     rcx, [rcx+40h]
0x18003eff3  mov     dl, 5
0x18003eff5  mov     [rsp+0A8h+var_70], eax
0x18003eff9  mov     rax, [rbx+348h]
0x18003f000  mov     [rsp+0A8h+var_78], rax
0x18003f005  mov     [rsp+0A8h+var_80], rbx
0x18003f00a  mov     [rsp+0A8h+Timeout], r13
0x18003f00f  call    WPP_RECORDER_SF_qqd
0x18003f014  mov     [rbx+348h], r15
0x18003f01b  cmp     [rbx+2B8h], r15
0x18003f022  jz      short loc_18003F06C
0x18003f024  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18003f02b  jz      short loc_18003F052
0x18003f02d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f034  mov     r9d, 62h ; 'b'
0x18003f03a  mov     [rsp+0A8h+var_80], rbx
0x18003f03f  mov     r8d, esi
0x18003f042  mov     dl, 4
0x18003f044  mov     [rsp+0A8h+Timeout], r13
0x18003f049  mov     rcx, [rcx+40h]
0x18003f04d  call    WPP_RECORDER_SF_q
0x18003f052  mov     rcx, [rbx+2B8h]
0x18003f059  mov     rax, [rcx]
0x18003f05c  mov     rax, [rax+10h]
0x18003f060  call    _guard_dispatch_icall
0x18003f065  mov     [rbx+2B8h], r15
0x18003f06c  cmp     [rbx+2C0h], r15
0x18003f073  jz      short loc_18003F0BD
0x18003f075  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18003f07c  jz      short loc_18003F0A3
0x18003f07e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f085  mov     r9d, 63h ; 'c'
0x18003f08b  mov     [rsp+0A8h+var_80], rbx
0x18003f090  mov     r8d, esi
0x18003f093  mov     dl, 4
0x18003f095  mov     [rsp+0A8h+Timeout], r13
0x18003f09a  mov     rcx, [rcx+40h]
0x18003f09e  call    WPP_RECORDER_SF_q
0x18003f0a3  mov     rcx, [rbx+2C0h]
0x18003f0aa  mov     rax, [rcx]
0x18003f0ad  mov     rax, [rax+10h]
0x18003f0b1  call    _guard_dispatch_icall
0x18003f0b6  mov     [rbx+2C0h], r15
0x18003f0bd  cmp     [rbx+358h], r15
0x18003f0c4  jz      short loc_18003F112
0x18003f0c6  mov     rcx, [rbx+340h]
0x18003f0cd  test    rcx, rcx
0x18003f0d0  jz      short loc_18003F0F8
0x18003f0d2  mov     rax, [rcx]
0x18003f0d5  mov     rax, [rax+18h]
0x18003f0d9  call    _guard_dispatch_icall
0x18003f0de  mov     rcx, [rbx+340h]
0x18003f0e5  mov     rax, [rcx]
0x18003f0e8  mov     rax, [rax+10h]
0x18003f0ec  call    _guard_dispatch_icall
0x18003f0f1  mov     [rbx+340h], r15
0x18003f0f8  mov     rcx, [rbx+358h]; Object
0x18003f0ff  call    cs:__imp_ObfDereferenceObject
0x18003f106  nop     dword ptr [rax+rax+00h]
0x18003f10b  mov     [rbx+358h], r15
0x18003f112  mov     rcx, [rbx+258h]; Object
0x18003f119  test    rcx, rcx
0x18003f11c  jz      short loc_18003F131
0x18003f11e  call    cs:__imp_ObfDereferenceObject
0x18003f125  nop     dword ptr [rax+rax+00h]
0x18003f12a  mov     [rbx+258h], r15
0x18003f131  cmp     [rbx+378h], r15
0x18003f138  jz      short loc_18003F198
0x18003f13a  lea     rsi, [rbx+3A8h]
0x18003f141  mov     rcx, rsi; Event
0x18003f144  call    cs:__imp_KeResetEvent
0x18003f14b  nop     dword ptr [rax+rax+00h]
0x18003f150  or      eax, 0FFFFFFFFh
0x18003f153  lock xadd [rbx+3A0h], eax
0x18003f15b  sub     eax, 1
0x18003f15e  jle     short loc_18003F17E
0x18003f160  xor     r9d, r9d; Alertable
0x18003f163  mov     [rsp+0A8h+Timeout], r15; Timeout
0x18003f168  xor     r8d, r8d; WaitMode
0x18003f16b  mov     rcx, rsi; Object
0x18003f16e  lea     edx, [r9+5]; WaitReason
0x18003f172  call    cs:__imp_KeWaitForSingleObject
0x18003f179  nop     dword ptr [rax+rax+00h]
0x18003f17e  mov     rcx, [rbx+378h]; Object
0x18003f185  call    cs:__imp_ObfDereferenceObject
0x18003f18c  nop     dword ptr [rax+rax+00h]
0x18003f191  mov     [rbx+378h], r15
0x18003f198  mov     rcx, [rbx+370h]; DefaultClock
0x18003f19f  test    rcx, rcx
0x18003f1a2  jz      short loc_18003F1B0
0x18003f1a4  call    KsFreeDefaultClock
0x18003f1a9  mov     [rbx+370h], r15
0x18003f1b0  mov     rax, [rdi+0B8h]
0x18003f1b7  mov     rdx, r14
0x18003f1ba  mov     rcx, [rax+30h]
0x18003f1be  mov     rbp, [rcx+40h]
0x18003f1c2  mov     rcx, rdi
0x18003f1c5  call    KspClose
0x18003f1ca  mov     esi, eax
0x18003f1cc  cmp     eax, 103h
0x18003f1d1  jz      loc_18003F2DE
0x18003f1d7  mov     rcx, [rbx+2B0h]
0x18003f1de  dec     dword ptr [rcx]
0x18003f1e0  cmp     eax, 0C0000016h
0x18003f1e5  jnz     short loc_18003F1FB
0x18003f1e7  mov     rcx, [rbx]
0x18003f1ea  mov     rax, [rcx+10h]
0x18003f1ee  mov     rcx, rbx
0x18003f1f1  call    _guard_dispatch_icall
0x18003f1f6  jmp     loc_18003F2CF
0x18003f1fb  xor     eax, eax
0x18003f1fd  lea     rcx, [rsp+0A8h+Event]; Event
0x18003f202  xorps   xmm0, xmm0
0x18003f205  mov     [rsp+0A8h+Event.Header.WaitListHead.Blink], rax
0x18003f20a  xor     r8d, r8d; State
0x18003f20d  movups  xmmword ptr [rsp+0A8h+Event.Header], xmm0
0x18003f212  lea     r14d, [rax+1]
0x18003f216  mov     edx, r14d; Type
0x18003f219  call    cs:__imp_KeInitializeEvent
0x18003f220  nop     dword ptr [rax+rax+00h]
0x18003f225  lea     rax, [rsp+0A8h+Event]
0x18003f22a  mov     rcx, rbx
0x18003f22d  mov     [rbx+368h], rax
0x18003f234  mov     rax, [rbx]
0x18003f237  mov     rax, [rax+10h]
0x18003f23b  call    _guard_dispatch_icall
0x18003f240  test    eax, eax
0x18003f242  jz      short loc_18003F2BE
0x18003f244  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18003f24b  jz      short loc_18003F270
0x18003f24d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f254  lea     r9d, [r14+63h]
0x18003f258  mov     [rsp+0A8h+var_80], rbx
0x18003f25d  mov     r8d, r14d
0x18003f260  mov     dl, 4
0x18003f262  mov     [rsp+0A8h+Timeout], r13
0x18003f267  mov     rcx, [rcx+40h]
0x18003f26b  call    WPP_RECORDER_SF_q
0x18003f270  xor     r9d, r9d; Alertable
0x18003f273  mov     [rsp+0A8h+Timeout], r15; Timeout
0x18003f278  xor     r8d, r8d; WaitMode
0x18003f27b  lea     rcx, [rsp+0A8h+Event]; Object
0x18003f280  lea     edx, [r9+5]; WaitReason
0x18003f284  call    cs:__imp_KeWaitForSingleObject
0x18003f28b  nop     dword ptr [rax+rax+00h]
0x18003f290  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18003f297  jz      short loc_18003F2BE
0x18003f299  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f2a0  mov     r9d, 65h ; 'e'
0x18003f2a6  mov     [rsp+0A8h+var_80], rbx
0x18003f2ab  mov     r8d, r14d
0x18003f2ae  mov     dl, 4
0x18003f2b0  mov     [rsp+0A8h+Timeout], r13
0x18003f2b5  mov     rcx, [rcx+40h]
0x18003f2b9  call    WPP_RECORDER_SF_q
0x18003f2be  xor     edx, edx; PriorityBoost
0x18003f2c0  mov     rcx, rdi; Irp
0x18003f2c3  call    cs:__imp_IofCompleteRequest
0x18003f2ca  nop     dword ptr [rax+rax+00h]
0x18003f2cf  mov     rcx, rbp; Object
0x18003f2d2  call    cs:__imp_ObfDereferenceObject
0x18003f2d9  nop     dword ptr [rax+rax+00h]
0x18003f2de  mov     eax, esi
0x18003f2e0  add     rsp, 68h
0x18003f2e4  pop     r15
0x18003f2e6  pop     r14
0x18003f2e8  pop     r13
0x18003f2ea  pop     r12
0x18003f2ec  pop     rdi
0x18003f2ed  pop     rsi
0x18003f2ee  pop     rbp
0x18003f2ef  pop     rbx
0x18003f2f0  retn
```
