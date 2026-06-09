# CKernelFilterDevice::DispatchCreate(_IRP *,_IRP_STATUS,long *)

- ea: `0x14000b400`
- end: `0x14000b563`
- name: `?DispatchCreate@CKernelFilterDevice@@MEAA?AW4_IRP_DISPOSITION@@PEAU_IRP@@W4_IRP_STATUS@@PEAJ@Z`
- size: `355`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT *, IRP *, int, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140001e80`

## callees

- `0x1400018ac`
- `0x1400041f0`
- `0x14000b400`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14000b4a4`
- `ntoskrnl!KeInitializeEvent` at `0x14000b4a4`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000b536`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000b536`
- `ntoskrnl!IofCallDriver` at `0x14000b50d`
- `ntoskrnl!IofCallDriver` at `0x14000b50d`

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
      v11 = CKernelFilterDevice::NotifyNewFile((KSPIN_LOCK *)a1, v9);
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
0x14000b400  push    rbx
0x14000b402  push    rbp
0x14000b403  push    rsi
0x14000b404  push    rdi
0x14000b405  sub     rsp, 58h
0x14000b409  mov     rsi, r9
0x14000b40c  mov     rbp, rdx
0x14000b40f  mov     rdi, rcx
0x14000b412  test    r8d, r8d
0x14000b415  jnz     short loc_14000B420
0x14000b417  lea     eax, [r8+4]
0x14000b41b  jmp     loc_14000B559
0x14000b420  cmp     dword ptr [r9], 0
0x14000b424  jl      loc_14000B557
0x14000b42a  mov     rax, [rcx]
0x14000b42d  mov     rax, [rax]
0x14000b430  call    _guard_dispatch_icall
0x14000b435  test    al, al
0x14000b437  jz      loc_14000B557
0x14000b43d  mov     rax, [rdi]
0x14000b440  mov     rdx, rbp
0x14000b443  mov     rcx, rdi
0x14000b446  mov     rax, [rax+8]
0x14000b44a  call    _guard_dispatch_icall
0x14000b44f  mov     rbx, rax
0x14000b452  test    rax, rax
0x14000b455  jz      short loc_14000B479
0x14000b457  mov     rcx, [rax]
0x14000b45a  mov     rax, [rcx+8]
0x14000b45e  mov     rcx, rbx
0x14000b461  call    _guard_dispatch_icall
0x14000b466  mov     [rsi], eax
0x14000b468  test    eax, eax
0x14000b46a  js      short loc_14000B488
0x14000b46c  mov     rdx, rbx; struct CKernelFilterFile *
0x14000b46f  mov     rcx, rdi; this
0x14000b472  call    ?NotifyNewFile@CKernelFilterDevice@@AEAAJPEAVCKernelFilterFile@@@Z; CKernelFilterDevice::NotifyNewFile(CKernelFilterFile *)
0x14000b477  jmp     short loc_14000B47E
0x14000b479  mov     eax, 0C000009Ah
0x14000b47e  mov     [rsi], eax
0x14000b480  test    eax, eax
0x14000b482  jns     loc_14000B557
0x14000b488  xor     eax, eax
0x14000b48a  lea     rcx, [rsp+78h+Event]; Event
0x14000b48f  xorps   xmm0, xmm0
0x14000b492  mov     [rsp+78h+Event.Header.WaitListHead.Blink], rax
0x14000b497  xor     r8d, r8d; State
0x14000b49a  movups  xmmword ptr [rsp+78h+Event.Header], xmm0
0x14000b49f  lea     esi, [rax+1]
0x14000b4a2  mov     edx, esi; Type
0x14000b4a4  call    cs:__imp_KeInitializeEvent
0x14000b4ab  nop     dword ptr [rax+rax+00h]
0x14000b4b0  mov     rax, [rbp+0B8h]
0x14000b4b7  lea     rcx, ?DeferIrpCompletion@CKernelFilterDevice@@SAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAU_KEVENT@@@Z; CKernelFilterDevice::DeferIrpCompletion(_DEVICE_OBJECT *,_IRP *,_KEVENT *)
0x14000b4be  mov     rdx, rbp; Irp
0x14000b4c1  movups  xmm0, xmmword ptr [rax]
0x14000b4c4  movups  xmmword ptr [rax-48h], xmm0
0x14000b4c8  movups  xmm1, xmmword ptr [rax+10h]
0x14000b4cc  movups  xmmword ptr [rax-38h], xmm1
0x14000b4d0  movups  xmm0, xmmword ptr [rax+20h]
0x14000b4d4  movups  xmmword ptr [rax-28h], xmm0
0x14000b4d8  movsd   xmm1, qword ptr [rax+30h]
0x14000b4dd  movsd   qword ptr [rax-18h], xmm1
0x14000b4e2  mov     byte ptr [rax-45h], 0
0x14000b4e6  mov     rax, [rbp+0B8h]
0x14000b4ed  mov     byte ptr [rax-48h], 2
0x14000b4f1  mov     rax, [rbp+0B8h]
0x14000b4f8  mov     [rax-10h], rcx
0x14000b4fc  lea     rcx, [rsp+78h+Event]
0x14000b501  mov     [rax-8], rcx
0x14000b505  mov     byte ptr [rax-45h], 0E0h
0x14000b509  mov     rcx, [rdi+38h]; DeviceObject
0x14000b50d  call    cs:__imp_IofCallDriver
0x14000b514  nop     dword ptr [rax+rax+00h]
0x14000b519  cmp     eax, 103h
0x14000b51e  jnz     short loc_14000B542
0x14000b520  xor     r9d, r9d; Alertable
0x14000b523  mov     [rsp+78h+Timeout], 0; Timeout
0x14000b52c  xor     r8d, r8d; WaitMode
0x14000b52f  lea     rcx, [rsp+78h+Event]; Object
0x14000b534  xor     edx, edx; WaitReason
0x14000b536  call    cs:__imp_KeWaitForSingleObject
0x14000b53d  nop     dword ptr [rax+rax+00h]
0x14000b542  test    rbx, rbx
0x14000b545  jz      short loc_14000B557
0x14000b547  mov     rax, [rbx]
0x14000b54a  mov     edx, esi
0x14000b54c  mov     rcx, rbx
0x14000b54f  mov     rax, [rax]
0x14000b552  call    _guard_dispatch_icall
0x14000b557  xor     eax, eax
0x14000b559  add     rsp, 58h
0x14000b55d  pop     rdi
0x14000b55e  pop     rsi
0x14000b55f  pop     rbp
0x14000b560  pop     rbx
0x14000b561  retn
```
