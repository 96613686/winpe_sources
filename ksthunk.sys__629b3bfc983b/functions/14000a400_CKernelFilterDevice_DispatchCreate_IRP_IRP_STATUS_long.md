# CKernelFilterDevice::DispatchCreate(_IRP *,_IRP_STATUS,long *)

- ea: `0x14000a400`
- end: `0x14000a563`
- name: `?DispatchCreate@CKernelFilterDevice@@MEAA?AW4_IRP_DISPOSITION@@PEAU_IRP@@W4_IRP_STATUS@@PEAJ@Z`
- size: `355`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140001e00`

## callees

- `0x1400018ac`
- `0x140003770`
- `0x14000a400`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14000a4a4`
- `ntoskrnl!KeInitializeEvent` at `0x14000a4a4`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000a536`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000a536`
- `ntoskrnl!IofCallDriver` at `0x14000a50d`
- `ntoskrnl!IofCallDriver` at `0x14000a50d`

## pseudocode

```c
__int64 __fastcall CKernelFilterDevice::DispatchCreate(PDEVICE_OBJECT *a1, IRP *a2, int a3, int *a4)
{
  __int64 v8; // rax
  struct CKernelFilterFile *v9; // rbx
  int v10; // eax
  int v11; // eax
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v13; // rax
  struct _KEVENT Event; // [rsp+30h] [rbp-48h] BYREF

  if ( !a3 )
    return 4;
  if ( *a4 >= 0 && (*(unsigned __int8 (__fastcall **)(PDEVICE_OBJECT *))&(*a1)->Type)(a1) )
  {
    v8 = ((__int64 (__fastcall *)(PDEVICE_OBJECT *, IRP *))(*a1)->DriverObject)(a1, a2);
    v9 = (struct CKernelFilterFile *)v8;
    if ( v8 )
    {
      v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
      *a4 = v10;
      if ( v10 < 0 )
      {
LABEL_10:
        memset(&Event, 0, sizeof(Event));
        KeInitializeEvent(&Event, SynchronizationEvent, 0);
        CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
        *(_OWORD *)&CurrentStackLocation[-1].MajorFunction = *(_OWORD *)&CurrentStackLocation->MajorFunction;
        *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation->Parameters.NotifyDirectoryEx.CompletionFilter;
        *(_OWORD *)(&CurrentStackLocation[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&CurrentStackLocation->Parameters.SetQuota
                                                                                   + 6);
        CurrentStackLocation[-1].FileObject = CurrentStackLocation->FileObject;
        CurrentStackLocation[-1].Control = 0;
        a2->Tail.Overlay.CurrentStackLocation[-1].MajorFunction = 2;
        v13 = a2->Tail.Overlay.CurrentStackLocation;
        v13[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)CKernelFilterDevice::DeferIrpCompletion;
        v13[-1].Context = &Event;
        v13[-1].Control = -32;
        if ( IofCallDriver(a1[7], a2) == 259 )
          KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
        if ( v9 )
          (**(void (__fastcall ***)(struct CKernelFilterFile *, __int64))v9)(v9, 1);
        return 0;
      }
      v11 = CKernelFilterDevice::NotifyNewFile((CKernelFilterDevice *)a1, v9);
    }
    else
    {
      v11 = -1073741670;
    }
    *a4 = v11;
    if ( v11 < 0 )
      goto LABEL_10;
  }
  return 0;
}

```

## disassembly

```asm
0x14000a400  push    rbx
0x14000a402  push    rbp
0x14000a403  push    rsi
0x14000a404  push    rdi
0x14000a405  sub     rsp, 58h
0x14000a409  mov     rsi, r9
0x14000a40c  mov     rbp, rdx
0x14000a40f  mov     rdi, rcx
0x14000a412  test    r8d, r8d
0x14000a415  jnz     short loc_14000A420
0x14000a417  lea     eax, [r8+4]
0x14000a41b  jmp     loc_14000A559
0x14000a420  cmp     dword ptr [r9], 0
0x14000a424  jl      loc_14000A557
0x14000a42a  mov     rax, [rcx]
0x14000a42d  mov     rax, [rax]
0x14000a430  call    _guard_dispatch_icall
0x14000a435  test    al, al
0x14000a437  jz      loc_14000A557
0x14000a43d  mov     rax, [rdi]
0x14000a440  mov     rdx, rbp
0x14000a443  mov     rcx, rdi
0x14000a446  mov     rax, [rax+8]
0x14000a44a  call    _guard_dispatch_icall
0x14000a44f  mov     rbx, rax
0x14000a452  test    rax, rax
0x14000a455  jz      short loc_14000A479
0x14000a457  mov     rcx, [rax]
0x14000a45a  mov     rax, [rcx+8]
0x14000a45e  mov     rcx, rbx
0x14000a461  call    _guard_dispatch_icall
0x14000a466  mov     [rsi], eax
0x14000a468  test    eax, eax
0x14000a46a  js      short loc_14000A488
0x14000a46c  mov     rdx, rbx; struct CKernelFilterFile *
0x14000a46f  mov     rcx, rdi; this
0x14000a472  call    ?NotifyNewFile@CKernelFilterDevice@@AEAAJPEAVCKernelFilterFile@@@Z; CKernelFilterDevice::NotifyNewFile(CKernelFilterFile *)
0x14000a477  jmp     short loc_14000A47E
0x14000a479  mov     eax, 0C000009Ah
0x14000a47e  mov     [rsi], eax
0x14000a480  test    eax, eax
0x14000a482  jns     loc_14000A557
0x14000a488  xor     eax, eax
0x14000a48a  lea     rcx, [rsp+78h+Event]; Event
0x14000a48f  xorps   xmm0, xmm0
0x14000a492  mov     [rsp+78h+Event.Header.WaitListHead.Blink], rax
0x14000a497  xor     r8d, r8d; State
0x14000a49a  movups  xmmword ptr [rsp+78h+Event.Header], xmm0
0x14000a49f  lea     esi, [rax+1]
0x14000a4a2  mov     edx, esi; Type
0x14000a4a4  call    cs:__imp_KeInitializeEvent
0x14000a4ab  nop     dword ptr [rax+rax+00h]
0x14000a4b0  mov     rax, [rbp+0B8h]
0x14000a4b7  lea     rcx, ?DeferIrpCompletion@CKernelFilterDevice@@SAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAU_KEVENT@@@Z; CKernelFilterDevice::DeferIrpCompletion(_DEVICE_OBJECT *,_IRP *,_KEVENT *)
0x14000a4be  mov     rdx, rbp; Irp
0x14000a4c1  movups  xmm0, xmmword ptr [rax]
0x14000a4c4  movups  xmmword ptr [rax-48h], xmm0
0x14000a4c8  movups  xmm1, xmmword ptr [rax+10h]
0x14000a4cc  movups  xmmword ptr [rax-38h], xmm1
0x14000a4d0  movups  xmm0, xmmword ptr [rax+20h]
0x14000a4d4  movups  xmmword ptr [rax-28h], xmm0
0x14000a4d8  movsd   xmm1, qword ptr [rax+30h]
0x14000a4dd  movsd   qword ptr [rax-18h], xmm1
0x14000a4e2  mov     byte ptr [rax-45h], 0
0x14000a4e6  mov     rax, [rbp+0B8h]
0x14000a4ed  mov     byte ptr [rax-48h], 2
0x14000a4f1  mov     rax, [rbp+0B8h]
0x14000a4f8  mov     [rax-10h], rcx
0x14000a4fc  lea     rcx, [rsp+78h+Event]
0x14000a501  mov     [rax-8], rcx
0x14000a505  mov     byte ptr [rax-45h], 0E0h
0x14000a509  mov     rcx, [rdi+38h]; DeviceObject
0x14000a50d  call    cs:__imp_IofCallDriver
0x14000a514  nop     dword ptr [rax+rax+00h]
0x14000a519  cmp     eax, 103h
0x14000a51e  jnz     short loc_14000A542
0x14000a520  xor     r9d, r9d; Alertable
0x14000a523  mov     [rsp+78h+Timeout], 0; Timeout
0x14000a52c  xor     r8d, r8d; WaitMode
0x14000a52f  lea     rcx, [rsp+78h+Event]; Object
0x14000a534  xor     edx, edx; WaitReason
0x14000a536  call    cs:__imp_KeWaitForSingleObject
0x14000a53d  nop     dword ptr [rax+rax+00h]
0x14000a542  test    rbx, rbx
0x14000a545  jz      short loc_14000A557
0x14000a547  mov     rax, [rbx]
0x14000a54a  mov     edx, esi
0x14000a54c  mov     rcx, rbx
0x14000a54f  mov     rax, [rax]
0x14000a552  call    _guard_dispatch_icall
0x14000a557  xor     eax, eax
0x14000a559  add     rsp, 58h
0x14000a55d  pop     rdi
0x14000a55e  pop     rsi
0x14000a55f  pop     rbp
0x14000a560  pop     rbx
0x14000a561  retn
```
