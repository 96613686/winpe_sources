# CKsFilter::DispatchClose(_DEVICE_OBJECT *,_IRP *)

- ea: `0x180051800`
- end: `0x180051b9f`
- name: `?DispatchClose@CKsFilter@@SAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `927`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000aa80`
- `0x18000b7bc`
- `0x18000c630`
- `0x18000da50`
- `0x18000dddc`
- `0x180019cb0`
- `0x1800332f4`
- `0x180051800`
- `0x180051ba8`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x180051b59`
- `ntoskrnl!KeWaitForSingleObject` at `0x180051b59`
- `ntoskrnl!IofCompleteRequest` at `0x1800519fa`
- `ntoskrnl!IofCompleteRequest` at `0x180051a65`
- `ntoskrnl!IofCompleteRequest` at `0x1800519fa`
- `ntoskrnl!IofCompleteRequest` at `0x180051a65`
- `ntoskrnl!KeInitializeEvent` at `0x1800519c6`
- `ntoskrnl!KeInitializeEvent` at `0x1800519c6`

## pseudocode

```c
__int64 __fastcall CKsFilter::DispatchClose(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  struct _IRP *v2; // rdi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  int MajorFunction; // edx
  __int64 v6; // rbx
  __int64 v7; // r14
  __int64 Notification; // rax
  void *v9; // rcx
  int v10; // edx
  int v11; // r8d
  unsigned int v12; // esi
  __int64 v13; // rbx
  __int64 v14; // rcx
  int v15; // edx
  int v17; // edx
  struct _KEVENT Event; // [rsp+40h] [rbp-48h] BYREF

  v2 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      31,
      (__int64)WPP_001f1e784e56319d01cbbdcd1f1acdab_Traceguids);
  }
  CurrentStackLocation = v2->Tail.Overlay.CurrentStackLocation;
  MajorFunction = CurrentStackLocation->MajorFunction;
  if ( (_BYTE)MajorFunction == 18 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(MajorFunction) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        MajorFunction,
        1,
        32,
        (__int64)WPP_001f1e784e56319d01cbbdcd1f1acdab_Traceguids);
    }
    v2->IoStatus.Status = 0;
    IofCompleteRequest(v2, 0);
    return 0;
  }
  else
  {
    v6 = *(_QWORD *)(*(_QWORD *)CurrentStackLocation->FileObject->FsContext + 112LL);
    v7 = v6 - 88;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(MajorFunction) = 5;
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        MajorFunction,
        1,
        33,
        (__int64)WPP_001f1e784e56319d01cbbdcd1f1acdab_Traceguids,
        CurrentStackLocation->MajorFunction);
    }
    if ( v2->IoStatus.Status != -1073741802 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v6 + 72) + 40LL))(*(_QWORD *)(v6 + 72));
    (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v6 + 72) + 72LL))(*(_QWORD *)(v6 + 72), v7 + 616);
    if ( v2->IoStatus.Status != -1073741802 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v6 + 72) + 48LL))(*(_QWORD *)(v6 + 72));
    Notification = KspGetNotification();
    if ( Notification && *(_BYTE *)(v7 + 768) )
      (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD, __int64))(*(_QWORD *)Notification + 24LL))(
        Notification,
        v7 + 264,
        *(unsigned __int8 *)(v6 + 208),
        *(unsigned int *)(v6 + 224),
        v7 + 216);
    v9 = *(void **)(v7 + 552);
    if ( v9 )
    {
      KsUnregisterWorker(v9);
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LOBYTE(v10) = 5;
        WPP_RECORDER_SF_qq(
          WPP_GLOBAL_Control->DeviceExtension,
          v10,
          v11,
          34,
          (char)WPP_001f1e784e56319d01cbbdcd1f1acdab_Traceguids,
          v6 - 88);
      }
      *(_QWORD *)(v7 + 552) = 0;
    }
    v12 = KspClose(v2, v6);
    if ( v12 != 259 )
    {
      v13 = *(_QWORD *)(*(_QWORD *)(v6 + 40) + 56LL);
      v14 = *(_QWORD *)(*(_QWORD *)a1->DeviceExtension + 128LL);
      if ( v14 )
        (*(void (__fastcall **)(_QWORD))(v14 + 40))(*(_QWORD *)(v14 + 8));
      if ( v12 == -1073741802 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      }
      else
      {
        memset(&Event, 0, sizeof(Event));
        KeInitializeEvent(&Event, SynchronizationEvent, 0);
        *(_QWORD *)(v7 + 720) = &Event;
        if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7) )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v15) = 4;
            WPP_RECORDER_SF_q(
              WPP_GLOBAL_Control->DeviceExtension,
              v15,
              1,
              35,
              (__int64)WPP_001f1e784e56319d01cbbdcd1f1acdab_Traceguids,
              v7);
          }
          KeWaitForSingleObject(&Event, Suspended, 0, 0, 0);
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v17) = 4;
            WPP_RECORDER_SF_q(
              WPP_GLOBAL_Control->DeviceExtension,
              v17,
              1,
              36,
              (__int64)WPP_001f1e784e56319d01cbbdcd1f1acdab_Traceguids,
              v7);
          }
        }
        IofCompleteRequest(v2, 0);
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    return v12;
  }
}

```

## disassembly

```asm
0x180051800  push    rdi
0x180051802  push    r12
0x180051804  push    r13
0x180051806  push    r15
0x180051808  sub     rsp, 68h
0x18005180c  mov     rdi, rdx
0x18005180f  mov     r15, rcx
0x180051812  lea     r12, WPP_RECORDER_INITIALIZED
0x180051819  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180051820  lea     r13, WPP_001f1e784e56319d01cbbdcd1f1acdab_Traceguids
0x180051827  jz      short loc_18005183B
0x180051829  mov     rcx, cs:WPP_GLOBAL_Control
0x180051830  cmp     word ptr [rcx+48h], 0
0x180051835  jnz     loc_180051A75
0x18005183b  mov     rax, [rdi+0B8h]
0x180051842  mov     [rsp+88h+arg_8], rbp
0x18005184a  movzx   edx, byte ptr [rax]
0x18005184d  cmp     dl, 12h
0x180051850  jz      loc_180051A52
0x180051856  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18005185d  mov     rax, [rax+30h]
0x180051861  mov     [rsp+88h+arg_0], rbx
0x180051869  mov     [rsp+88h+arg_10], rsi
0x180051871  mov     [rsp+88h+var_28], r14
0x180051876  mov     rcx, [rax+18h]
0x18005187a  mov     rbx, [rcx]
0x18005187d  mov     rbx, [rbx+70h]
0x180051881  lea     r14, [rbx-58h]
0x180051885  jz      short loc_180051899
0x180051887  mov     rcx, cs:WPP_GLOBAL_Control
0x18005188e  cmp     word ptr [rcx+48h], 0
0x180051893  jnz     loc_180051AC2
0x180051899  cmp     dword ptr [rdi+30h], 0C0000016h
0x1800518a0  jz      short loc_1800518B2
0x1800518a2  mov     rcx, [rbx+48h]
0x1800518a6  mov     rax, [rcx]
0x1800518a9  mov     rax, [rax+28h]
0x1800518ad  call    _guard_dispatch_icall
0x1800518b2  mov     rcx, [rbx+48h]
0x1800518b6  lea     rdx, [r14+268h]
0x1800518bd  mov     rax, [rcx]
0x1800518c0  mov     rax, [rax+48h]
0x1800518c4  call    _guard_dispatch_icall
0x1800518c9  cmp     dword ptr [rdi+30h], 0C0000016h
0x1800518d0  jz      short loc_1800518E2
0x1800518d2  mov     rcx, [rbx+48h]
0x1800518d6  mov     rax, [rcx]
0x1800518d9  mov     rax, [rax+30h]
0x1800518dd  call    _guard_dispatch_icall
0x1800518e2  call    KspGetNotification
0x1800518e7  mov     r10, rax
0x1800518ea  test    rax, rax
0x1800518ed  jz      short loc_18005192A
0x1800518ef  cmp     byte ptr [r14+300h], 0
0x1800518f7  jz      short loc_18005192A
0x1800518f9  mov     rcx, [rax]
0x1800518fc  lea     r8, [r14+0D8h]
0x180051903  mov     r9d, [rbx+0E0h]
0x18005190a  lea     rdx, [r14+108h]
0x180051911  mov     [rsp+88h+Timeout], r8
0x180051916  movzx   r8d, byte ptr [rbx+0D0h]
0x18005191e  mov     rax, [rcx+18h]
0x180051922  mov     rcx, r10
0x180051925  call    _guard_dispatch_icall
0x18005192a  mov     rcx, [r14+228h]; Worker
0x180051931  xor     ebp, ebp
0x180051933  test    rcx, rcx
0x180051936  jz      short loc_18005195E
0x180051938  call    KsUnregisterWorker
0x18005193d  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180051944  jz      short loc_180051957
0x180051946  mov     rcx, cs:WPP_GLOBAL_Control
0x18005194d  cmp     [rcx+48h], bp
0x180051951  jnz     loc_180051AE7
0x180051957  mov     [r14+228h], rbp
0x18005195e  mov     rdx, rbx
0x180051961  mov     rcx, rdi
0x180051964  call    KspClose
0x180051969  mov     esi, eax
0x18005196b  cmp     eax, 103h
0x180051970  jz      loc_180051A15
0x180051976  mov     rcx, [rbx+28h]
0x18005197a  mov     rbx, [rcx+38h]
0x18005197e  mov     rcx, [r15+40h]
0x180051982  mov     rdx, [rcx]
0x180051985  mov     rcx, [rdx+80h]
0x18005198c  test    rcx, rcx
0x18005198f  jz      short loc_18005199E
0x180051991  mov     rax, [rcx+28h]
0x180051995  mov     rcx, [rcx+8]
0x180051999  call    _guard_dispatch_icall
0x18005199e  cmp     esi, 0C0000016h
0x1800519a4  jz      loc_180051A41
0x1800519aa  xorps   xmm0, xmm0
0x1800519ad  lea     rcx, [rsp+88h+Event]; Event
0x1800519b2  xor     eax, eax
0x1800519b4  xor     r8d, r8d; State
0x1800519b7  mov     edx, 1; Type
0x1800519bc  mov     [rsp+88h+Event.Header.WaitListHead.Blink], rax
0x1800519c1  movups  xmmword ptr [rsp+88h+Event.Header], xmm0
0x1800519c6  call    cs:__imp_KeInitializeEvent
0x1800519cd  nop     dword ptr [rax+rax+00h]
0x1800519d2  lea     rax, [rsp+88h+Event]
0x1800519d7  mov     rcx, r14
0x1800519da  mov     [r14+2D0h], rax
0x1800519e1  mov     rax, [r14]
0x1800519e4  mov     rax, [rax+10h]
0x1800519e8  call    _guard_dispatch_icall
0x1800519ed  test    eax, eax
0x1800519ef  jnz     loc_180051B13
0x1800519f5  xor     edx, edx; PriorityBoost
0x1800519f7  mov     rcx, rdi; Irp
0x1800519fa  call    cs:__imp_IofCompleteRequest
0x180051a01  nop     dword ptr [rax+rax+00h]
0x180051a06  mov     rax, [rbx]
0x180051a09  mov     rcx, rbx
0x180051a0c  mov     rax, [rax+10h]
0x180051a10  call    _guard_dispatch_icall
0x180051a15  mov     r14, [rsp+88h+var_28]
0x180051a1a  mov     eax, esi
0x180051a1c  mov     rsi, [rsp+88h+arg_10]
0x180051a24  mov     rbx, [rsp+88h+arg_0]
0x180051a2c  mov     rbp, [rsp+88h+arg_8]
0x180051a34  add     rsp, 68h
0x180051a38  pop     r15
0x180051a3a  pop     r13
0x180051a3c  pop     r12
0x180051a3e  pop     rdi
0x180051a3f  retn
0x180051a41  mov     rax, [r14]
0x180051a44  mov     rcx, r14
0x180051a47  mov     rax, [rax+10h]
0x180051a4b  call    _guard_dispatch_icall
0x180051a50  jmp     short loc_180051A06
0x180051a52  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180051a59  jnz     short loc_180051A96
0x180051a5b  xor     ebp, ebp
0x180051a5d  xor     edx, edx; PriorityBoost
0x180051a5f  mov     rcx, rdi; Irp
0x180051a62  mov     [rdi+30h], ebp
0x180051a65  call    cs:__imp_IofCompleteRequest
0x180051a6c  nop     dword ptr [rax+rax+00h]
0x180051a71  xor     eax, eax
0x180051a73  jmp     short loc_180051A2C
0x180051a75  mov     rcx, [rcx+40h]
0x180051a79  mov     r9d, 1Fh
0x180051a7f  mov     r8d, 1
0x180051a85  mov     [rsp+88h+Timeout], r13
0x180051a8a  mov     dl, 5
0x180051a8c  call    WPP_RECORDER_SF_
0x180051a91  jmp     loc_18005183B
0x180051a96  mov     rcx, cs:WPP_GLOBAL_Control
0x180051a9d  cmp     word ptr [rcx+48h], 0
0x180051aa2  jz      short loc_180051A5B
0x180051aa4  mov     rcx, [rcx+40h]
0x180051aa8  mov     r9d, 20h ; ' '
0x180051aae  mov     r8d, 1
0x180051ab4  mov     [rsp+88h+Timeout], r13
0x180051ab9  mov     dl, 5
0x180051abb  call    WPP_RECORDER_SF_
0x180051ac0  jmp     short loc_180051A5B
0x180051ac2  mov     rcx, [rcx+40h]
0x180051ac6  mov     r9d, 21h ; '!'
0x180051acc  mov     dword ptr [rsp+88h+var_60], edx
0x180051ad0  mov     r8d, 1
0x180051ad6  mov     dl, 5
0x180051ad8  mov     [rsp+88h+Timeout], r13
0x180051add  call    WPP_RECORDER_SF_D
0x180051ae2  jmp     loc_180051899
0x180051ae7  mov     rax, [r14+228h]
0x180051aee  mov     r9d, 22h ; '"'
0x180051af4  mov     rcx, [rcx+40h]
0x180051af8  mov     dl, 5
0x180051afa  mov     [rsp+88h+var_58], rax
0x180051aff  mov     [rsp+88h+var_60], r14
0x180051b04  mov     [rsp+88h+Timeout], r13
0x180051b09  call    WPP_RECORDER_SF_qq
0x180051b0e  jmp     loc_180051957
0x180051b13  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180051b1a  jz      short loc_180051B44
0x180051b1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180051b23  mov     r9d, 23h ; '#'
0x180051b29  mov     [rsp+88h+var_60], r14
0x180051b2e  mov     r8d, 1
0x180051b34  mov     dl, 4
0x180051b36  mov     [rsp+88h+Timeout], r13
0x180051b3b  mov     rcx, [rcx+40h]
0x180051b3f  call    WPP_RECORDER_SF_q
0x180051b44  xor     r9d, r9d; Alertable
0x180051b47  mov     [rsp+88h+Timeout], rbp; Timeout
0x180051b4c  xor     r8d, r8d; WaitMode
0x180051b4f  lea     rcx, [rsp+88h+Event]; Object
0x180051b54  mov     edx, 5; WaitReason
0x180051b59  call    cs:__imp_KeWaitForSingleObject
0x180051b60  nop     dword ptr [rax+rax+00h]
0x180051b65  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180051b6c  jz      loc_1800519F5
0x180051b72  mov     rcx, cs:WPP_GLOBAL_Control
0x180051b79  mov     r9d, 24h ; '$'
0x180051b7f  mov     [rsp+88h+var_60], r14
0x180051b84  mov     r8d, 1
0x180051b8a  mov     dl, 4
0x180051b8c  mov     [rsp+88h+Timeout], r13
0x180051b91  mov     rcx, [rcx+40h]
0x180051b95  call    WPP_RECORDER_SF_q
0x180051b9a  jmp     loc_1800519F5
```
