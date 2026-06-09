# PmWrite(_DEVICE_OBJECT *,_IRP *)

- ea: `0x140002730`
- end: `0x14000296f`
- name: `?PmWrite@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `575`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x140002730`
- `0x140002b00`
- `0x140004260`
- `0x140009ca4`
- `0x14000beb4`
- `0x140010f60`

## import_xrefs

- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x140002836`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x140002836`
- `ntoskrnl!IofCallDriver` at `0x1400028c1`
- `ntoskrnl!IofCallDriver` at `0x1400028c1`
- `ntoskrnl!IofCompleteRequest` at `0x14000291a`
- `ntoskrnl!IofCompleteRequest` at `0x14000291a`
- `ntoskrnl!PoEnergyEstimationEnabled` at `0x140002895`
- `ntoskrnl!PoEnergyEstimationEnabled` at `0x140002895`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x140011b0a`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x140011b0a`
- `ntoskrnl!PsUpdateComponentPower` at `0x140011ad7`
- `ntoskrnl!PsUpdateComponentPower` at `0x140011ad7`
- `ntoskrnl!ObReferenceObjectSafe` at `0x140011af0`
- `ntoskrnl!ObReferenceObjectSafe` at `0x140011af0`
- `ntoskrnl!IoGetRequestorProcess` at `0x140011a75`
- `ntoskrnl!IoGetRequestorProcess` at `0x140011a75`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400027b0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011a24`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400027b0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011a24`
- `ntoskrnl!IoGetIoPriorityHint` at `0x140002858`
- `ntoskrnl!IoGetIoPriorityHint` at `0x140002858`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002785`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002785`

## pseudocode

```c
NTSTATUS __fastcall PmWrite(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  KSPIN_LOCK *DeviceExtension; // rbx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  LONGLONG Length; // r12
  bool v7; // bp
  LARGE_INTEGER ByteOffset; // r15
  KIRQL v9; // r8
  KSPIN_LOCK *i; // rax
  struct _IO_STACK_LOCATION *v11; // rbp
  PVOID v12; // r14
  struct _IO_STACK_LOCATION *v13; // rcx
  void *Options; // rax
  int v15; // esi
  struct _PERF_COUNTER_CONTEXT *v16; // r13
  ULONG64 v17; // rax
  union _LARGE_INTEGER v18; // rbx
  unsigned __int8 v19; // r9
  unsigned __int64 v20; // rbx
  __int64 v21; // rax
  void (__fastcall *v23)(struct _IRP *); // rax
  signed __int64 v24; // r9
  struct _DISK_POWER_CONTEXT *v25; // rcx
  unsigned __int64 v26; // r12
  PEPROCESS RequestorProcess; // rax
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // rcx
  PEPROCESS v31; // rsi
  char v32; // al
  PEPROCESS v33; // rbp
  unsigned __int64 QpcTimeStamp; // [rsp+70h] [rbp+8h] BYREF

  DeviceExtension = (KSPIN_LOCK *)a1->DeviceExtension;
  if ( *((_DWORD *)DeviceExtension + 131) )
  {
    CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
    if ( (CurrentStackLocation->Flags & 0x10) != 0 || *((_DWORD *)DeviceExtension + 162) != 1 )
    {
LABEL_7:
      v11 = a2->Tail.Overlay.CurrentStackLocation;
      v12 = a1->DeviceExtension;
      *(_OWORD *)&v11[-1].MajorFunction = *(_OWORD *)&v11->MajorFunction;
      *(_OWORD *)&v11[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v11->Parameters.NotifyDirectoryEx.CompletionFilter;
      *(_OWORD *)(&v11[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v11->Parameters.SetQuota + 6);
      v11[-1].FileObject = v11->FileObject;
      v11[-1].Control = 0;
      v13 = a2->Tail.Overlay.CurrentStackLocation;
      Options = (void *)v11->Parameters.Create.Options;
      v13[-1].CompletionRoutine = PmIoCompletion;
      v13[-1].Context = Options;
      v13[-1].Control = -32;
      v15 = *(_DWORD *)(*((_QWORD *)v12 + 90) + 56LL);
      v16 = (struct _PERF_COUNTER_CONTEXT *)*((_QWORD *)v12 + 90);
      QpcTimeStamp = 0;
      v17 = KeQueryUnbiasedInterruptTimePrecise(&QpcTimeStamp);
      v11->Parameters.WMI.ProviderId = v17;
      v18.QuadPart = v17;
      if ( v15 )
      {
        v11->MinorFunction = 1;
        if ( IoGetIoPriorityHint(a2) <= IoPriorityLow )
        {
          v19 = 0;
        }
        else
        {
          v11->MinorFunction |= 2u;
          v19 = 1;
        }
        v20 = PmPerfCounterIdleUpdate(v16, v18, &v11->Parameters.Create.Options, v19, 0);
        if ( v20 )
        {
          LODWORD(QpcTimeStamp) = 0;
          if ( (unsigned __int8)PoEnergyEstimationEnabled() )
          {
            v25 = (struct _DISK_POWER_CONTEXT *)*((_QWORD *)v12 + 143);
            if ( v25 )
            {
              if ( *((_BYTE *)v12 + 1152) )
              {
                v26 = PmCalculateIdlePower(v25, v20, (unsigned int *)&QpcTimeStamp);
                RequestorProcess = IoGetRequestorProcess(a2);
                v30 = *((_QWORD *)v12 + 143);
                v31 = RequestorProcess;
                v32 = QpcTimeStamp;
                v33 = *(PEPROCESS *)(v30 + 208);
                *(_DWORD *)(v30 + 232) = QpcTimeStamp;
                if ( (Microsoft_Windows_PartitionEnableBits & 2) != 0 )
                  McTemplateK0pxxu_EtwWriteTransfer(v30, v28, v29, v33, v26, v20, v32);
                PsUpdateComponentPower(v33, 1, v26 / 0x2710);
                if ( v31 != v33 )
                {
                  if ( v31 && !(unsigned __int8)ObReferenceObjectSafe(v31) )
                    v31 = 0;
                  if ( v33 )
                    ObDereferenceObjectDeferDelete(v33);
                }
                *(_QWORD *)(*((_QWORD *)v12 + 143) + 208LL) = v31;
              }
            }
          }
        }
      }
      else
      {
        v11->MinorFunction = 0;
      }
      v21 = *((_QWORD *)v12 + 89);
      if ( v21 )
      {
        v23 = *(void (__fastcall **)(struct _IRP *))(v21 + 8);
        if ( v23 )
          v23(a2);
      }
      return IofCallDriver(*((PDEVICE_OBJECT *)v12 + 2), a2);
    }
    else
    {
      Length = CurrentStackLocation->Parameters.Read.Length;
      v7 = 0;
      ByteOffset = CurrentStackLocation->Parameters.Read.ByteOffset;
      v9 = KeAcquireSpinLockRaiseToDpc(DeviceExtension + 14);
      for ( i = (KSPIN_LOCK *)DeviceExtension[112]; i != DeviceExtension + 112; i = (KSPIN_LOCK *)*i )
      {
        v24 = i[4];
        if ( v24 > ByteOffset.QuadPart )
        {
          v7 = Length > v24 - ByteOffset.QuadPart;
          break;
        }
        if ( ByteOffset.QuadPart - v24 < (__int64)i[5] )
        {
          KeReleaseSpinLock(DeviceExtension + 14, v9);
          goto LABEL_22;
        }
      }
      KeReleaseSpinLock(DeviceExtension + 14, v9);
      if ( !v7 )
        goto LABEL_7;
LABEL_22:
      PmRedirectRequest((struct _DEVICE_EXTENSION *)DeviceExtension, a2);
      return 259;
    }
  }
  else
  {
    a2->IoStatus.Status = -1073741662;
    a2->IoStatus.Information = 0;
    IofCompleteRequest(a2, 0);
    return -1073741662;
  }
}

```

## disassembly

```asm
0x140002730  mov     rax, rsp
0x140002733  push    rbx
0x140002734  push    rdi
0x140002735  push    r14
0x140002737  push    r15
0x140002739  sub     rsp, 48h
0x14000273d  mov     rbx, [rcx+40h]
0x140002741  mov     rdi, rdx
0x140002744  mov     r14, rcx
0x140002747  cmp     dword ptr [rbx+20Ch], 0
0x14000274e  jz      loc_140002907
0x140002754  mov     rcx, [rdx+0B8h]
0x14000275b  mov     [rax+10h], rbp
0x14000275f  mov     [rax+18h], rsi
0x140002763  mov     [rax+20h], r12
0x140002767  test    byte ptr [rcx+2], 10h
0x14000276b  jnz     short loc_1400027C5
0x14000276d  cmp     dword ptr [rbx+288h], 1
0x140002774  jnz     short loc_1400027C5
0x140002776  mov     r12d, [rcx+8]
0x14000277a  xor     bpl, bpl
0x14000277d  mov     r15, [rcx+18h]
0x140002781  lea     rcx, [rbx+70h]; SpinLock
0x140002785  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000278c  nop     dword ptr [rax+rax+00h]
0x140002791  lea     rdx, [rbx+380h]
0x140002798  movzx   r8d, al
0x14000279c  mov     rax, [rdx]
0x14000279f  cmp     rax, rdx
0x1400027a2  jnz     loc_14000292D
0x1400027a8  movzx   edx, r8b; NewIrql
0x1400027ac  lea     rcx, [rbx+70h]; SpinLock
0x1400027b0  call    cs:__imp_KeReleaseSpinLock
0x1400027b7  nop     dword ptr [rax+rax+00h]
0x1400027bc  test    bpl, bpl
0x1400027bf  jnz     loc_140002952
0x1400027c5  mov     rbp, [rdi+0B8h]
0x1400027cc  lea     rdx, ?PmIoCompletion@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; PmIoCompletion(_DEVICE_OBJECT *,_IRP *,void *)
0x1400027d3  mov     r14, [r14+40h]
0x1400027d7  xor     r15d, r15d
0x1400027da  mov     [rsp+68h+var_28], r13
0x1400027df  movups  xmm0, xmmword ptr [rbp+0]
0x1400027e3  movups  xmmword ptr [rbp-48h], xmm0
0x1400027e7  movups  xmm1, xmmword ptr [rbp+10h]
0x1400027eb  movups  xmmword ptr [rbp-38h], xmm1
0x1400027ef  movups  xmm0, xmmword ptr [rbp+20h]
0x1400027f3  movups  xmmword ptr [rbp-28h], xmm0
0x1400027f7  movsd   xmm1, qword ptr [rbp+30h]
0x1400027fc  movsd   qword ptr [rbp-18h], xmm1
0x140002801  mov     byte ptr [rbp-45h], 0
0x140002805  mov     rcx, [rdi+0B8h]
0x14000280c  mov     eax, [rbp+10h]
0x14000280f  mov     [rcx-10h], rdx
0x140002813  mov     [rcx-8], rax
0x140002817  mov     byte ptr [rcx-45h], 0E0h
0x14000281b  lea     rcx, [rsp+68h+QpcTimeStamp]; QpcTimeStamp
0x140002820  mov     rax, [r14+2D0h]
0x140002827  mov     esi, [rax+38h]
0x14000282a  mov     r13, [r14+2D0h]
0x140002831  mov     [rsp+68h+QpcTimeStamp], r15
0x140002836  call    cs:__imp_KeQueryUnbiasedInterruptTimePrecise
0x14000283d  nop     dword ptr [rax+rax+00h]
0x140002842  mov     [rbp+8], rax
0x140002846  mov     rbx, rax
0x140002849  test    esi, esi
0x14000284b  jz      loc_140002901
0x140002851  mov     rcx, rdi; Irp
0x140002854  mov     byte ptr [rbp+1], 1
0x140002858  call    cs:__imp_IoGetIoPriorityHint
0x14000285f  nop     dword ptr [rax+rax+00h]
0x140002864  cmp     eax, 1
0x140002867  jle     loc_140002967
0x14000286d  or      byte ptr [rbp+1], 2
0x140002871  mov     r9b, 1; unsigned __int8
0x140002874  lea     r8, [rbp+10h]; unsigned int *
0x140002878  mov     [rsp+68h+var_48], r15b; char
0x14000287d  mov     rdx, rbx; union _LARGE_INTEGER
0x140002880  mov     rcx, r13; struct _PERF_COUNTER_CONTEXT *
0x140002883  call    ?PmPerfCounterIdleUpdate@@YA_KPEAU_PERF_COUNTER_CONTEXT@@T_LARGE_INTEGER@@PEAKEE@Z; PmPerfCounterIdleUpdate(_PERF_COUNTER_CONTEXT *,_LARGE_INTEGER,ulong *,uchar,uchar)
0x140002888  mov     rbx, rax
0x14000288b  test    rax, rax
0x14000288e  jz      short loc_1400028A9
0x140002890  mov     dword ptr [rsp+68h+QpcTimeStamp], r15d
0x140002895  call    cs:__imp_PoEnergyEstimationEnabled
0x14000289c  nop     dword ptr [rax+rax+00h]
0x1400028a1  test    al, al
0x1400028a3  jnz     loc_140011A45
0x1400028a9  mov     rax, [r14+2C8h]
0x1400028b0  mov     r13, [rsp+68h+var_28]
0x1400028b5  test    rax, rax
0x1400028b8  jnz     short loc_1400028EE
0x1400028ba  mov     rcx, [r14+10h]; DeviceObject
0x1400028be  mov     rdx, rdi; Irp
0x1400028c1  call    cs:__imp_IofCallDriver
0x1400028c8  nop     dword ptr [rax+rax+00h]
0x1400028cd  mov     rsi, [rsp+68h+arg_10]
0x1400028d5  mov     rbp, [rsp+68h+arg_8]
0x1400028da  mov     r12, [rsp+68h+arg_18]
0x1400028e2  add     rsp, 48h
0x1400028e6  pop     r15
0x1400028e8  pop     r14
0x1400028ea  pop     rdi
0x1400028eb  pop     rbx
0x1400028ec  retn
0x1400028ee  mov     rax, [rax+8]
0x1400028f2  test    rax, rax
0x1400028f5  jz      short loc_1400028BA
0x1400028f7  mov     rcx, rdi
0x1400028fa  call    _guard_dispatch_icall
0x1400028ff  jmp     short loc_1400028BA
0x140002901  mov     [rbp+1], r15b
0x140002905  jmp     short loc_1400028A9
0x140002907  xor     r15d, r15d
0x14000290a  mov     dword ptr [rdx+30h], 0C00000A2h
0x140002911  mov     [rdx+38h], r15
0x140002915  mov     rcx, rdi; Irp
0x140002918  xor     edx, edx; PriorityBoost
0x14000291a  call    cs:__imp_IofCompleteRequest
0x140002921  nop     dword ptr [rax+rax+00h]
0x140002926  mov     eax, 0C00000A2h
0x14000292b  jmp     short loc_1400028E2
0x14000292d  mov     r9, [rax+20h]
0x140002931  cmp     r9, r15
0x140002934  jg      loc_140011A36
0x14000293a  mov     rcx, r15
0x14000293d  sub     rcx, r9
0x140002940  cmp     rcx, [rax+28h]
0x140002944  jl      loc_140011A1C
0x14000294a  mov     rax, [rax]
0x14000294d  jmp     loc_14000279F
0x140002952  mov     rdx, rdi; struct _IRP *
0x140002955  mov     rcx, rbx; struct _DEVICE_EXTENSION *
0x140002958  call    ?PmRedirectRequest@@YAXPEAU_DEVICE_EXTENSION@@PEAU_IRP@@@Z; PmRedirectRequest(_DEVICE_EXTENSION *,_IRP *)
0x14000295d  mov     eax, 103h
0x140002962  jmp     loc_1400028CD
0x140002967  xor     r9b, r9b
0x14000296a  jmp     loc_140002874
0x140011a1c  movzx   edx, r8b; NewIrql
0x140011a20  lea     rcx, [rbx+70h]; SpinLock
0x140011a24  call    cs:__imp_KeReleaseSpinLock
0x140011a2b  nop     dword ptr [rax+rax+00h]
0x140011a30  nop
0x140011a31  jmp     loc_140002952
0x140011a36  sub     r9, r15
0x140011a39  cmp     r12, r9
0x140011a3c  setnle  bpl
0x140011a40  jmp     loc_1400027A8
0x140011a45  mov     rcx, [r14+478h]; struct _DISK_POWER_CONTEXT *
0x140011a4c  test    rcx, rcx
0x140011a4f  jz      loc_1400028A9
0x140011a55  cmp     [r14+480h], r15b
0x140011a5c  jz      loc_1400028A9
0x140011a62  lea     r8, [rsp+68h+QpcTimeStamp]; unsigned int *
0x140011a67  mov     rdx, rbx; unsigned __int64
0x140011a6a  call    ?PmCalculateIdlePower@@YA_KPEAU_DISK_POWER_CONTEXT@@_KPEAK@Z; PmCalculateIdlePower(_DISK_POWER_CONTEXT *,unsigned __int64,ulong *)
0x140011a6f  mov     rcx, rdi; Irp
0x140011a72  mov     r12, rax
0x140011a75  call    cs:__imp_IoGetRequestorProcess
0x140011a7c  nop     dword ptr [rax+rax+00h]
0x140011a81  mov     rcx, [r14+478h]
0x140011a88  mov     rsi, rax
0x140011a8b  mov     eax, dword ptr [rsp+68h+QpcTimeStamp]
0x140011a8f  mov     rbp, [rcx+0D0h]
0x140011a96  mov     [rcx+0E8h], eax
0x140011a9c  test    cs:Microsoft_Windows_PartitionEnableBits, 2
0x140011aa3  jz      short loc_140011ABB
0x140011aa5  mov     [rsp+68h+var_38], al
0x140011aa9  mov     r9, rbp
0x140011aac  mov     [rsp+68h+var_40], rbx
0x140011ab1  mov     qword ptr [rsp+68h+var_48], r12
0x140011ab6  call    McTemplateK0pxxu_EtwWriteTransfer
0x140011abb  mov     rax, 346DC5D63886594Bh
0x140011ac5  mov     rcx, rbp
0x140011ac8  mul     r12
0x140011acb  shr     rdx, 0Bh
0x140011acf  mov     r8, rdx
0x140011ad2  mov     edx, 1
0x140011ad7  call    cs:__imp_PsUpdateComponentPower
0x140011ade  nop     dword ptr [rax+rax+00h]
0x140011ae3  cmp     rsi, rbp
0x140011ae6  jz      short loc_140011B16
0x140011ae8  test    rsi, rsi
0x140011aeb  jz      short loc_140011B02
0x140011aed  mov     rcx, rsi
0x140011af0  call    cs:__imp_ObReferenceObjectSafe
0x140011af7  nop     dword ptr [rax+rax+00h]
0x140011afc  test    al, al
0x140011afe  cmovz   rsi, r15
0x140011b02  test    rbp, rbp
0x140011b05  jz      short loc_140011B16
0x140011b07  mov     rcx, rbp; Object
0x140011b0a  call    cs:__imp_ObDereferenceObjectDeferDelete
0x140011b11  nop     dword ptr [rax+rax+00h]
0x140011b16  mov     rax, [r14+478h]
0x140011b1d  mov     [rax+0D0h], rsi
0x140011b24  jmp     loc_1400028A9
```
