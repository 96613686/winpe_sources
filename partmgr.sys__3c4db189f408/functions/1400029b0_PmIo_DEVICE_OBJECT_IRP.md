# PmIo(_DEVICE_OBJECT *,_IRP *)

- ea: `0x1400029b0`
- end: `0x140002af7`
- name: `?PmIo@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `327`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1400029b0`
- `0x140002b00`
- `0x140004260`
- `0x140009ca4`
- `0x140010f60`

## import_xrefs

- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x140002a2f`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x140002a2f`
- `ntoskrnl!IofCallDriver` at `0x140002ab8`
- `ntoskrnl!IofCallDriver` at `0x140002ab8`
- `ntoskrnl!PoEnergyEstimationEnabled` at `0x140002a91`
- `ntoskrnl!PoEnergyEstimationEnabled` at `0x140002a91`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x140011bf5`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x140011bf5`
- `ntoskrnl!PsUpdateComponentPower` at `0x140011bc2`
- `ntoskrnl!PsUpdateComponentPower` at `0x140011bc2`
- `ntoskrnl!ObReferenceObjectSafe` at `0x140011bdb`
- `ntoskrnl!ObReferenceObjectSafe` at `0x140011bdb`
- `ntoskrnl!IoGetRequestorProcess` at `0x140011b5d`
- `ntoskrnl!IoGetRequestorProcess` at `0x140011b5d`
- `ntoskrnl!IoGetIoPriorityHint` at `0x140002a51`
- `ntoskrnl!IoGetIoPriorityHint` at `0x140002a51`

## pseudocode

```c
NTSTATUS __fastcall PmIo(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  PVOID DeviceExtension; // rbp
  struct _IO_STACK_LOCATION *v5; // rcx
  void *Options; // rax
  int v7; // edi
  struct _PERF_COUNTER_CONTEXT *v8; // r12
  ULONG64 v9; // rax
  union _LARGE_INTEGER v10; // rbx
  unsigned __int8 v11; // r9
  unsigned __int64 v12; // rbx
  __int64 v13; // rax
  void (__fastcall *v15)(struct _IRP *); // rax
  struct _DISK_POWER_CONTEXT *v16; // rcx
  unsigned __int64 v17; // r15
  PEPROCESS RequestorProcess; // rax
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rcx
  PEPROCESS v22; // rdi
  char v23; // al
  PEPROCESS v24; // rsi
  unsigned __int64 v25; // [rsp+90h] [rbp+8h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  DeviceExtension = a1->DeviceExtension;
  *(_OWORD *)&CurrentStackLocation[-1].MajorFunction = *(_OWORD *)&CurrentStackLocation->MajorFunction;
  *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation->Parameters.NotifyDirectoryEx.CompletionFilter;
  *(_OWORD *)(&CurrentStackLocation[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&CurrentStackLocation->Parameters.SetQuota
                                                                             + 6);
  CurrentStackLocation[-1].FileObject = CurrentStackLocation->FileObject;
  CurrentStackLocation[-1].Control = 0;
  v5 = a2->Tail.Overlay.CurrentStackLocation;
  Options = (void *)CurrentStackLocation->Parameters.Create.Options;
  v5[-1].CompletionRoutine = PmIoCompletion;
  v5[-1].Context = Options;
  v5[-1].Control = -32;
  v7 = *(_DWORD *)(*((_QWORD *)DeviceExtension + 90) + 56LL);
  v8 = (struct _PERF_COUNTER_CONTEXT *)*((_QWORD *)DeviceExtension + 90);
  v25 = 0;
  v9 = KeQueryUnbiasedInterruptTimePrecise(&v25);
  CurrentStackLocation->Parameters.WMI.ProviderId = v9;
  v10.QuadPart = v9;
  if ( v7 )
  {
    CurrentStackLocation->MinorFunction = 1;
    if ( IoGetIoPriorityHint(a2) <= IoPriorityLow )
    {
      v11 = 0;
    }
    else
    {
      CurrentStackLocation->MinorFunction |= 2u;
      v11 = 1;
    }
    v12 = PmPerfCounterIdleUpdate(v8, v10, &CurrentStackLocation->Parameters.Create.Options, v11, 0);
    if ( v12 )
    {
      LODWORD(v25) = 0;
      if ( (unsigned __int8)PoEnergyEstimationEnabled() )
      {
        v16 = (struct _DISK_POWER_CONTEXT *)*((_QWORD *)DeviceExtension + 143);
        if ( v16 )
        {
          if ( *((_BYTE *)DeviceExtension + 1152) )
          {
            v17 = PmCalculateIdlePower(v16, v12, (unsigned int *)&v25);
            RequestorProcess = IoGetRequestorProcess(a2);
            v21 = *((_QWORD *)DeviceExtension + 143);
            v22 = RequestorProcess;
            v23 = v25;
            v24 = *(PEPROCESS *)(v21 + 208);
            *(_DWORD *)(v21 + 232) = v25;
            if ( (Microsoft_Windows_PartitionEnableBits & 2) != 0 )
              McTemplateK0pxxu_EtwWriteTransfer(v21, v19, v20, v24, v17, v12, v23);
            PsUpdateComponentPower(v24, 1, v17 / 0x2710);
            if ( v22 != v24 )
            {
              if ( v22 && !(unsigned __int8)ObReferenceObjectSafe(v22) )
                v22 = 0;
              if ( v24 )
                ObDereferenceObjectDeferDelete(v24);
            }
            *(_QWORD *)(*((_QWORD *)DeviceExtension + 143) + 208LL) = v22;
          }
        }
      }
    }
  }
  else
  {
    CurrentStackLocation->MinorFunction = 0;
  }
  v13 = *((_QWORD *)DeviceExtension + 89);
  if ( v13 )
  {
    v15 = *(void (__fastcall **)(struct _IRP *))(v13 + 8);
    if ( v15 )
      v15(a2);
  }
  return IofCallDriver(*((PDEVICE_OBJECT *)DeviceExtension + 2), a2);
}

```

## disassembly

```asm
0x1400029b0  mov     r11, rsp
0x1400029b3  push    rbx
0x1400029b4  push    rbp
0x1400029b5  push    rsi
0x1400029b6  push    rdi
0x1400029b7  push    r12
0x1400029b9  push    r13
0x1400029bb  push    r14
0x1400029bd  push    r15
0x1400029bf  sub     rsp, 48h
0x1400029c3  mov     rsi, [rdx+0B8h]
0x1400029ca  mov     r14, rdx
0x1400029cd  mov     rbp, [rcx+40h]
0x1400029d1  xor     r13d, r13d
0x1400029d4  movups  xmm0, xmmword ptr [rsi]
0x1400029d7  movups  xmmword ptr [rsi-48h], xmm0
0x1400029db  movups  xmm1, xmmword ptr [rsi+10h]
0x1400029df  movups  xmmword ptr [rsi-38h], xmm1
0x1400029e3  movups  xmm0, xmmword ptr [rsi+20h]
0x1400029e7  movups  xmmword ptr [rsi-28h], xmm0
0x1400029eb  movsd   xmm1, qword ptr [rsi+30h]
0x1400029f0  movsd   qword ptr [rsi-18h], xmm1
0x1400029f5  mov     byte ptr [rsi-45h], 0
0x1400029f9  mov     rcx, [rdx+0B8h]
0x140002a00  lea     rdx, ?PmIoCompletion@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; PmIoCompletion(_DEVICE_OBJECT *,_IRP *,void *)
0x140002a07  mov     eax, [rsi+10h]
0x140002a0a  mov     [rcx-10h], rdx
0x140002a0e  mov     [rcx-8], rax
0x140002a12  mov     byte ptr [rcx-45h], 0E0h
0x140002a16  lea     rcx, [r11+8]; QpcTimeStamp
0x140002a1a  mov     rax, [rbp+2D0h]
0x140002a21  mov     edi, [rax+38h]
0x140002a24  mov     r12, [rbp+2D0h]
0x140002a2b  mov     [r11+8], r13
0x140002a2f  call    cs:__imp_KeQueryUnbiasedInterruptTimePrecise
0x140002a36  nop     dword ptr [rax+rax+00h]
0x140002a3b  mov     [rsi+8], rax
0x140002a3f  mov     rbx, rax
0x140002a42  test    edi, edi
0x140002a44  jz      loc_140002AE9
0x140002a4a  mov     rcx, r14; Irp
0x140002a4d  mov     byte ptr [rsi+1], 1
0x140002a51  call    cs:__imp_IoGetIoPriorityHint
0x140002a58  nop     dword ptr [rax+rax+00h]
0x140002a5d  cmp     eax, 1
0x140002a60  jle     loc_140002AEF
0x140002a66  or      byte ptr [rsi+1], 2
0x140002a6a  mov     r9b, 1; unsigned __int8
0x140002a6d  lea     r8, [rsi+10h]; unsigned int *
0x140002a71  mov     [rsp+88h+var_68], r13b; char
0x140002a76  mov     rdx, rbx; union _LARGE_INTEGER
0x140002a79  mov     rcx, r12; struct _PERF_COUNTER_CONTEXT *
0x140002a7c  call    ?PmPerfCounterIdleUpdate@@YA_KPEAU_PERF_COUNTER_CONTEXT@@T_LARGE_INTEGER@@PEAKEE@Z; PmPerfCounterIdleUpdate(_PERF_COUNTER_CONTEXT *,_LARGE_INTEGER,ulong *,uchar,uchar)
0x140002a81  mov     rbx, rax
0x140002a84  test    rax, rax
0x140002a87  jz      short loc_140002AA5
0x140002a89  mov     dword ptr [rsp+88h+arg_0], r13d
0x140002a91  call    cs:__imp_PoEnergyEstimationEnabled
0x140002a98  nop     dword ptr [rax+rax+00h]
0x140002a9d  test    al, al
0x140002a9f  jnz     loc_140011B2A
0x140002aa5  mov     rax, [rbp+2C8h]
0x140002aac  test    rax, rax
0x140002aaf  jnz     short loc_140002AD6
0x140002ab1  mov     rcx, [rbp+10h]; DeviceObject
0x140002ab5  mov     rdx, r14; Irp
0x140002ab8  call    cs:__imp_IofCallDriver
0x140002abf  nop     dword ptr [rax+rax+00h]
0x140002ac4  add     rsp, 48h
0x140002ac8  pop     r15
0x140002aca  pop     r14
0x140002acc  pop     r13
0x140002ace  pop     r12
0x140002ad0  pop     rdi
0x140002ad1  pop     rsi
0x140002ad2  pop     rbp
0x140002ad3  pop     rbx
0x140002ad4  retn
0x140002ad6  mov     rax, [rax+8]
0x140002ada  test    rax, rax
0x140002add  jz      short loc_140002AB1
0x140002adf  mov     rcx, r14
0x140002ae2  call    _guard_dispatch_icall
0x140002ae7  jmp     short loc_140002AB1
0x140002ae9  mov     [rsi+1], r13b
0x140002aed  jmp     short loc_140002AA5
0x140002aef  xor     r9b, r9b
0x140002af2  jmp     loc_140002A6D
0x140011b2a  mov     rcx, [rbp+478h]; struct _DISK_POWER_CONTEXT *
0x140011b31  test    rcx, rcx
0x140011b34  jz      loc_140002AA5
0x140011b3a  cmp     [rbp+480h], r13b
0x140011b41  jz      loc_140002AA5
0x140011b47  lea     r8, [rsp+88h+arg_0]; unsigned int *
0x140011b4f  mov     rdx, rbx; unsigned __int64
0x140011b52  call    ?PmCalculateIdlePower@@YA_KPEAU_DISK_POWER_CONTEXT@@_KPEAK@Z; PmCalculateIdlePower(_DISK_POWER_CONTEXT *,unsigned __int64,ulong *)
0x140011b57  mov     rcx, r14; Irp
0x140011b5a  mov     r15, rax
0x140011b5d  call    cs:__imp_IoGetRequestorProcess
0x140011b64  nop     dword ptr [rax+rax+00h]
0x140011b69  mov     rcx, [rbp+478h]
0x140011b70  mov     rdi, rax
0x140011b73  mov     eax, dword ptr [rsp+88h+arg_0]
0x140011b7a  mov     rsi, [rcx+0D0h]
0x140011b81  mov     [rcx+0E8h], eax
0x140011b87  test    cs:Microsoft_Windows_PartitionEnableBits, 2
0x140011b8e  jz      short loc_140011BA6
0x140011b90  mov     [rsp+88h+var_58], al
0x140011b94  mov     r9, rsi
0x140011b97  mov     [rsp+88h+var_60], rbx
0x140011b9c  mov     qword ptr [rsp+88h+var_68], r15
0x140011ba1  call    McTemplateK0pxxu_EtwWriteTransfer
0x140011ba6  mov     rax, 346DC5D63886594Bh
0x140011bb0  mov     rcx, rsi
0x140011bb3  mul     r15
0x140011bb6  shr     rdx, 0Bh
0x140011bba  mov     r8, rdx
0x140011bbd  mov     edx, 1
0x140011bc2  call    cs:__imp_PsUpdateComponentPower
0x140011bc9  nop     dword ptr [rax+rax+00h]
0x140011bce  cmp     rdi, rsi
0x140011bd1  jz      short loc_140011C01
0x140011bd3  test    rdi, rdi
0x140011bd6  jz      short loc_140011BED
0x140011bd8  mov     rcx, rdi
0x140011bdb  call    cs:__imp_ObReferenceObjectSafe
0x140011be2  nop     dword ptr [rax+rax+00h]
0x140011be7  test    al, al
0x140011be9  cmovz   rdi, r13
0x140011bed  test    rsi, rsi
0x140011bf0  jz      short loc_140011C01
0x140011bf2  mov     rcx, rsi; Object
0x140011bf5  call    cs:__imp_ObDereferenceObjectDeferDelete
0x140011bfc  nop     dword ptr [rax+rax+00h]
0x140011c01  mov     rax, [rbp+478h]
0x140011c08  mov     [rax+0D0h], rdi
0x140011c0f  jmp     loc_140002AA5
```
