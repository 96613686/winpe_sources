# CKernelFilterDevice::DispatchIrp(_IRP *,_IRP_STATUS)

- ea: `0x140001440`
- end: `0x1400016bb`
- name: `?DispatchIrp@CKernelFilterDevice@@QEAAJPEAU_IRP@@W4_IRP_STATUS@@@Z`
- size: `635`
- prototype: `NTSTATUS __fastcall(_QWORD *, IRP *, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140001240`
- `0x140001300`
- `0x140001440`

## callees

- `0x140001440`
- `0x140003770`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140001545`
- `ntoskrnl!KeInitializeEvent` at `0x140001545`
- `ntoskrnl!IofCompleteRequest` at `0x1400016a2`
- `ntoskrnl!IofCompleteRequest` at `0x1400016a2`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400015e4`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400015e4`
- `ntoskrnl!IofCallDriver` at `0x14000151d`
- `ntoskrnl!IofCallDriver` at `0x1400015a7`
- `ntoskrnl!IofCallDriver` at `0x14000151d`
- `ntoskrnl!IofCallDriver` at `0x1400015a7`
- `ntoskrnl!PoCallDriver` at `0x1400015b5`
- `ntoskrnl!PoCallDriver` at `0x140001689`
- `ntoskrnl!PoCallDriver` at `0x1400015b5`
- `ntoskrnl!PoCallDriver` at `0x140001689`

## pseudocode

```c
NTSTATUS __fastcall CKernelFilterDevice::DispatchIrp(_QWORD *a1, IRP *a2, __int64 a3)
{
  NTSTATUS Status; // eax
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  int v7; // eax
  struct _DEVICE_OBJECT *v8; // rcx
  struct _IO_STACK_LOCATION *v10; // rax
  struct _IO_STACK_LOCATION *v11; // rax
  struct _DEVICE_OBJECT *v12; // rcx
  NTSTATUS v13; // eax
  struct _IO_STACK_LOCATION *v14; // rax
  struct _IO_STACK_LOCATION *v15; // rax
  struct _IO_STACK_LOCATION *v16; // rax
  _KEVENT Event; // [rsp+30h] [rbp-28h] BYREF
  NTSTATUS v18; // [rsp+90h] [rbp+38h] BYREF

  if ( (_DWORD)a3 )
    Status = a2->IoStatus.Status;
  else
    Status = 0;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v18 = Status;
  if ( CurrentStackLocation->MajorFunction )
  {
    switch ( CurrentStackLocation->MajorFunction )
    {
      case 2u:
        v7 = (*(__int64 (__fastcall **)(_QWORD *, IRP *, __int64, NTSTATUS *))(*a1 + 40LL))(a1, a2, a3, &v18);
        break;
      case 3u:
        v7 = (*(__int64 (__fastcall **)(_QWORD *, IRP *, __int64, NTSTATUS *))(*a1 + 48LL))(a1, a2, a3, &v18);
        break;
      case 4u:
        v7 = (*(__int64 (__fastcall **)(_QWORD *, IRP *, __int64, NTSTATUS *))(*a1 + 56LL))(a1, a2, a3, &v18);
        break;
      case 0xEu:
        v7 = (*(__int64 (__fastcall **)(_QWORD *, IRP *, __int64, NTSTATUS *))(*a1 + 64LL))(a1, a2, a3, &v18);
        break;
      case 0x16u:
        v7 = (*(__int64 (__fastcall **)(_QWORD *, IRP *, __int64, NTSTATUS *))(*a1 + 24LL))(a1, a2, a3, &v18);
        break;
      case 0x1Bu:
        v7 = (*(__int64 (__fastcall **)(_QWORD *, IRP *, __int64, NTSTATUS *))(*a1 + 16LL))(a1, a2, a3, &v18);
        break;
      default:
LABEL_34:
        v16 = a2->Tail.Overlay.CurrentStackLocation;
        *(_OWORD *)&v16[-1].MajorFunction = *(_OWORD *)&v16->MajorFunction;
        *(_OWORD *)&v16[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v16->Parameters.NotifyDirectoryEx.CompletionFilter;
        *(_OWORD *)(&v16[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v16->Parameters.SetQuota + 6);
        v16[-1].FileObject = v16->FileObject;
        v16[-1].Control = 0;
LABEL_24:
        v8 = (struct _DEVICE_OBJECT *)a1[7];
        if ( CurrentStackLocation->MajorFunction == 22 )
          return PoCallDriver(v8, a2);
        else
          return IofCallDriver(v8, a2);
    }
  }
  else
  {
    v7 = (*(__int64 (__fastcall **)(_QWORD *, IRP *, __int64, NTSTATUS *))(*a1 + 32LL))(a1, a2, a3, &v18);
  }
  switch ( v7 )
  {
    case 0:
      a2->IoStatus.Status = v18;
      IofCompleteRequest(a2, 0);
      return v18;
    case 1:
      goto LABEL_34;
    case 2:
      return 259;
    case 3:
      v14 = a2->Tail.Overlay.CurrentStackLocation;
      *(_OWORD *)&v14[-1].MajorFunction = *(_OWORD *)&v14->MajorFunction;
      *(_OWORD *)&v14[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v14->Parameters.NotifyDirectoryEx.CompletionFilter;
      *(_OWORD *)(&v14[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v14->Parameters.SetQuota + 6);
      v14[-1].FileObject = v14->FileObject;
      v14[-1].Control = 0;
      v15 = a2->Tail.Overlay.CurrentStackLocation;
      v15[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)CKernelFilterDevice::CallbackClientOnCompletion;
      v15[-1].Context = a1;
      v15[-1].Control = -32;
      goto LABEL_24;
  }
  if ( v7 != 4 )
  {
    if ( v7 == 5 )
      goto LABEL_24;
    return v18;
  }
  memset(&Event, 0, sizeof(Event));
  KeInitializeEvent(&Event, SynchronizationEvent, 0);
  v10 = a2->Tail.Overlay.CurrentStackLocation;
  *(_OWORD *)&v10[-1].MajorFunction = *(_OWORD *)&v10->MajorFunction;
  *(_OWORD *)&v10[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v10->Parameters.NotifyDirectoryEx.CompletionFilter;
  *(_OWORD *)(&v10[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v10->Parameters.SetQuota + 6);
  v10[-1].FileObject = v10->FileObject;
  v10[-1].Control = 0;
  v11 = a2->Tail.Overlay.CurrentStackLocation;
  v11[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)CKernelFilterDevice::DeferIrpCompletion;
  v11[-1].Context = &Event;
  v11[-1].Control = -32;
  v12 = (struct _DEVICE_OBJECT *)a1[7];
  if ( CurrentStackLocation->MajorFunction == 22 )
    v13 = PoCallDriver(v12, a2);
  else
    v13 = IofCallDriver(v12, a2);
  v18 = v13;
  if ( v13 == 259 )
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
  return CKernelFilterDevice::DispatchIrp(a1, a2, 2);
}

```

## disassembly

```asm
0x140001440  push    rbp
0x140001442  push    rbx
0x140001443  push    rsi
0x140001444  push    rdi
0x140001445  mov     rbp, rsp
0x140001448  sub     rsp, 58h
0x14000144c  mov     rbx, rdx
0x14000144f  mov     rdi, rcx
0x140001452  test    r8d, r8d
0x140001455  jz      short loc_14000145C
0x140001457  mov     eax, [rdx+30h]
0x14000145a  jmp     short loc_14000145E
0x14000145c  xor     eax, eax
0x14000145e  mov     rsi, [rdx+0B8h]
0x140001465  mov     [rbp+arg_10], eax
0x140001468  movzx   ecx, byte ptr [rsi]
0x14000146b  test    ecx, ecx
0x14000146d  jz      short loc_1400014C7
0x14000146f  sub     ecx, 2
0x140001472  jz      short loc_1400014BE
0x140001474  sub     ecx, 1
0x140001477  jz      short loc_1400014B5
0x140001479  sub     ecx, 1
0x14000147c  jz      short loc_1400014AC
0x14000147e  sub     ecx, 0Ah
0x140001481  jz      short loc_1400014A3
0x140001483  sub     ecx, 8
0x140001486  jz      short loc_14000149A
0x140001488  cmp     ecx, 5
0x14000148b  jnz     loc_140001658
0x140001491  mov     rax, [rdi]
0x140001494  mov     rax, [rax+10h]
0x140001498  jmp     short loc_1400014CE
0x14000149a  mov     rax, [rdi]
0x14000149d  mov     rax, [rax+18h]
0x1400014a1  jmp     short loc_1400014CE
0x1400014a3  mov     rax, [rdi]
0x1400014a6  mov     rax, [rax+40h]
0x1400014aa  jmp     short loc_1400014CE
0x1400014ac  mov     rax, [rdi]
0x1400014af  mov     rax, [rax+38h]
0x1400014b3  jmp     short loc_1400014CE
0x1400014b5  mov     rax, [rdi]
0x1400014b8  mov     rax, [rax+30h]
0x1400014bc  jmp     short loc_1400014CE
0x1400014be  mov     rax, [rdi]
0x1400014c1  mov     rax, [rax+28h]
0x1400014c5  jmp     short loc_1400014CE
0x1400014c7  mov     rax, [rdi]
0x1400014ca  mov     rax, [rax+20h]
0x1400014ce  lea     r9, [rbp+arg_10]
0x1400014d2  mov     rcx, rdi
0x1400014d5  call    _guard_dispatch_icall
0x1400014da  mov     ecx, eax
0x1400014dc  test    eax, eax
0x1400014de  jz      loc_140001697
0x1400014e4  sub     ecx, 1
0x1400014e7  jz      loc_140001658
0x1400014ed  sub     ecx, 1
0x1400014f0  jz      loc_140001651
0x1400014f6  sub     ecx, 1
0x1400014f9  jz      loc_140001606
0x1400014ff  sub     ecx, 1
0x140001502  jz      short loc_14000152E
0x140001504  cmp     ecx, 1
0x140001507  jnz     loc_1400016AE
0x14000150d  cmp     byte ptr [rsi], 16h
0x140001510  mov     rdx, rbx; Irp
0x140001513  mov     rcx, [rdi+38h]; DeviceObject
0x140001517  jz      loc_140001689
0x14000151d  call    cs:__imp_IofCallDriver
0x140001524  nop     dword ptr [rax+rax+00h]
0x140001529  jmp     loc_1400016B1
0x14000152e  xor     eax, eax
0x140001530  lea     rcx, [rbp+Event]; Event
0x140001534  xorps   xmm0, xmm0
0x140001537  mov     [rbp+Event.Header.WaitListHead.Blink], rax
0x14000153b  xor     r8d, r8d; State
0x14000153e  movups  xmmword ptr [rbp+Event.Header], xmm0
0x140001542  lea     edx, [rax+1]; Type
0x140001545  call    cs:__imp_KeInitializeEvent
0x14000154c  nop     dword ptr [rax+rax+00h]
0x140001551  mov     rax, [rbx+0B8h]
0x140001558  lea     rcx, ?DeferIrpCompletion@CKernelFilterDevice@@SAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAU_KEVENT@@@Z; CKernelFilterDevice::DeferIrpCompletion(_DEVICE_OBJECT *,_IRP *,_KEVENT *)
0x14000155f  mov     rdx, rbx; Irp
0x140001562  movups  xmm0, xmmword ptr [rax]
0x140001565  movups  xmmword ptr [rax-48h], xmm0
0x140001569  movups  xmm1, xmmword ptr [rax+10h]
0x14000156d  movups  xmmword ptr [rax-38h], xmm1
0x140001571  movups  xmm0, xmmword ptr [rax+20h]
0x140001575  movups  xmmword ptr [rax-28h], xmm0
0x140001579  movsd   xmm1, qword ptr [rax+30h]
0x14000157e  movsd   qword ptr [rax-18h], xmm1
0x140001583  mov     byte ptr [rax-45h], 0
0x140001587  mov     rax, [rbx+0B8h]
0x14000158e  mov     [rax-10h], rcx
0x140001592  lea     rcx, [rbp+Event]
0x140001596  mov     [rax-8], rcx
0x14000159a  mov     byte ptr [rax-45h], 0E0h
0x14000159e  cmp     byte ptr [rsi], 16h
0x1400015a1  mov     rcx, [rdi+38h]; DeviceObject
0x1400015a5  jz      short loc_1400015B5
0x1400015a7  call    cs:__imp_IofCallDriver
0x1400015ae  nop     dword ptr [rax+rax+00h]
0x1400015b3  jmp     short loc_1400015C1
0x1400015b5  call    cs:__imp_PoCallDriver
0x1400015bc  nop     dword ptr [rax+rax+00h]
0x1400015c1  mov     ecx, eax
0x1400015c3  mov     [rbp+arg_10], eax
0x1400015c6  mov     eax, 103h
0x1400015cb  cmp     ecx, eax
0x1400015cd  jnz     short loc_1400015F0
0x1400015cf  xor     r9d, r9d; Alertable
0x1400015d2  mov     [rsp+58h+Timeout], 0; Timeout
0x1400015db  xor     r8d, r8d; WaitMode
0x1400015de  lea     rcx, [rbp+Event]; Object
0x1400015e2  xor     edx, edx; WaitReason
0x1400015e4  call    cs:__imp_KeWaitForSingleObject
0x1400015eb  nop     dword ptr [rax+rax+00h]
0x1400015f0  mov     r8d, 2
0x1400015f6  mov     rdx, rbx
0x1400015f9  mov     rcx, rdi
0x1400015fc  call    ?DispatchIrp@CKernelFilterDevice@@QEAAJPEAU_IRP@@W4_IRP_STATUS@@@Z; CKernelFilterDevice::DispatchIrp(_IRP *,_IRP_STATUS)
0x140001601  jmp     loc_1400016B1
0x140001606  mov     rax, [rbx+0B8h]
0x14000160d  lea     rcx, ?CallbackClientOnCompletion@CKernelFilterDevice@@CAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAV1@@Z; CKernelFilterDevice::CallbackClientOnCompletion(_DEVICE_OBJECT *,_IRP *,CKernelFilterDevice *)
0x140001614  movups  xmm0, xmmword ptr [rax]
0x140001617  movups  xmmword ptr [rax-48h], xmm0
0x14000161b  movups  xmm1, xmmword ptr [rax+10h]
0x14000161f  movups  xmmword ptr [rax-38h], xmm1
0x140001623  movups  xmm0, xmmword ptr [rax+20h]
0x140001627  movups  xmmword ptr [rax-28h], xmm0
0x14000162b  movsd   xmm1, qword ptr [rax+30h]
0x140001630  movsd   qword ptr [rax-18h], xmm1
0x140001635  mov     byte ptr [rax-45h], 0
0x140001639  mov     rax, [rbx+0B8h]
0x140001640  mov     [rax-10h], rcx
0x140001644  mov     [rax-8], rdi
0x140001648  mov     byte ptr [rax-45h], 0E0h
0x14000164c  jmp     loc_14000150D
0x140001651  mov     eax, 103h
0x140001656  jmp     short loc_1400016B1
0x140001658  mov     rax, [rbx+0B8h]
0x14000165f  movups  xmm0, xmmword ptr [rax]
0x140001662  movups  xmmword ptr [rax-48h], xmm0
0x140001666  movups  xmm1, xmmword ptr [rax+10h]
0x14000166a  movups  xmmword ptr [rax-38h], xmm1
0x14000166e  movups  xmm0, xmmword ptr [rax+20h]
0x140001672  movups  xmmword ptr [rax-28h], xmm0
0x140001676  movsd   xmm1, qword ptr [rax+30h]
0x14000167b  movsd   qword ptr [rax-18h], xmm1
0x140001680  mov     byte ptr [rax-45h], 0
0x140001684  jmp     loc_14000150D
0x140001689  call    cs:__imp_PoCallDriver
0x140001690  nop     dword ptr [rax+rax+00h]
0x140001695  jmp     short loc_1400016B1
0x140001697  mov     eax, [rbp+arg_10]
0x14000169a  xor     edx, edx; PriorityBoost
0x14000169c  mov     rcx, rbx; Irp
0x14000169f  mov     [rbx+30h], eax
0x1400016a2  call    cs:__imp_IofCompleteRequest
0x1400016a9  nop     dword ptr [rax+rax+00h]
0x1400016ae  mov     eax, [rbp+arg_10]
0x1400016b1  add     rsp, 58h
0x1400016b5  pop     rdi
0x1400016b6  pop     rsi
0x1400016b7  pop     rbx
0x1400016b8  pop     rbp
0x1400016b9  retn
```
