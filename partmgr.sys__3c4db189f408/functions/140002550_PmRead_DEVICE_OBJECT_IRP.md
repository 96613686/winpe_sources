# PmRead(_DEVICE_OBJECT *,_IRP *)

- ea: `0x140002550`
- end: `0x140002722`
- name: `?PmRead@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `466`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x140002550`
- `0x140002b00`
- `0x140004260`
- `0x140009ca4`
- `0x14000a2b4`
- `0x14000beb4`
- `0x140010f60`

## import_xrefs

- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x1400025fe`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x1400025fe`
- `ntoskrnl!IofCallDriver` at `0x1400026a3`
- `ntoskrnl!IofCallDriver` at `0x1400026a3`
- `ntoskrnl!PoEnergyEstimationEnabled` at `0x14000265d`
- `ntoskrnl!PoEnergyEstimationEnabled` at `0x14000265d`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x1400119fd`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x1400119fd`
- `ntoskrnl!PsUpdateComponentPower` at `0x1400119ca`
- `ntoskrnl!PsUpdateComponentPower` at `0x1400119ca`
- `ntoskrnl!ObReferenceObjectSafe` at `0x1400119e3`
- `ntoskrnl!ObReferenceObjectSafe` at `0x1400119e3`
- `ntoskrnl!IoGetRequestorProcess` at `0x140011968`
- `ntoskrnl!IoGetRequestorProcess` at `0x140011968`
- `ntoskrnl!IoGetIoPriorityHint` at `0x140002620`
- `ntoskrnl!IoGetIoPriorityHint` at `0x140002620`

## pseudocode

```c
NTSTATUS __fastcall PmRead(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  struct _DEVICE_EXTENSION *DeviceExtension; // rbx
  PVOID v5; // rbp
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdi
  struct _IO_STACK_LOCATION *v7; // rcx
  void *Options; // rax
  int v9; // esi
  struct _PERF_COUNTER_CONTEXT *v10; // r12
  ULONG64 v11; // rax
  union _LARGE_INTEGER v12; // rbx
  unsigned __int8 v13; // r9
  unsigned __int64 v14; // rbx
  __int64 v15; // rax
  void (__fastcall *v17)(struct _IRP *); // rax
  struct _IO_STACK_LOCATION *v18; // rdx
  struct _DISK_POWER_CONTEXT *v19; // rcx
  unsigned __int64 v20; // r15
  PEPROCESS RequestorProcess; // rax
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // rcx
  PEPROCESS v25; // rdi
  char v26; // al
  PEPROCESS v27; // rsi
  unsigned __int64 QpcTimeStamp; // [rsp+70h] [rbp+8h] BYREF

  DeviceExtension = (struct _DEVICE_EXTENSION *)a1->DeviceExtension;
  if ( *(_DWORD *)(*((_QWORD *)DeviceExtension + 29) + 28LL) == 18
    && (v18 = a2->Tail.Overlay.CurrentStackLocation, (v18->Flags & 0x10) == 0)
    && *((_DWORD *)DeviceExtension + 162) == 1
    && PmIsOverlap(
         (struct _DEVICE_EXTENSION *)a1->DeviceExtension,
         v18->Parameters.Read.ByteOffset.QuadPart,
         v18->Parameters.Read.Length) )
  {
    PmRedirectRequest(DeviceExtension, a2);
    return 259;
  }
  else
  {
    v5 = a1->DeviceExtension;
    CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
    *(_OWORD *)&CurrentStackLocation[-1].MajorFunction = *(_OWORD *)&CurrentStackLocation->MajorFunction;
    *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation->Parameters.NotifyDirectoryEx.CompletionFilter;
    *(_OWORD *)(&CurrentStackLocation[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&CurrentStackLocation->Parameters.SetQuota
                                                                               + 6);
    CurrentStackLocation[-1].FileObject = CurrentStackLocation->FileObject;
    CurrentStackLocation[-1].Control = 0;
    v7 = a2->Tail.Overlay.CurrentStackLocation;
    Options = (void *)CurrentStackLocation->Parameters.Create.Options;
    v7[-1].CompletionRoutine = PmIoCompletion;
    v7[-1].Context = Options;
    v7[-1].Control = -32;
    v9 = *(_DWORD *)(*((_QWORD *)v5 + 90) + 56LL);
    v10 = (struct _PERF_COUNTER_CONTEXT *)*((_QWORD *)v5 + 90);
    QpcTimeStamp = 0;
    v11 = KeQueryUnbiasedInterruptTimePrecise(&QpcTimeStamp);
    CurrentStackLocation->Parameters.WMI.ProviderId = v11;
    v12.QuadPart = v11;
    if ( v9 )
    {
      CurrentStackLocation->MinorFunction = 1;
      if ( IoGetIoPriorityHint(a2) <= IoPriorityLow )
      {
        v13 = 0;
      }
      else
      {
        CurrentStackLocation->MinorFunction |= 2u;
        v13 = 1;
      }
      v14 = PmPerfCounterIdleUpdate(v10, v12, &CurrentStackLocation->Parameters.Create.Options, v13, 0);
      if ( v14 )
      {
        LODWORD(QpcTimeStamp) = 0;
        if ( (unsigned __int8)PoEnergyEstimationEnabled() )
        {
          v19 = (struct _DISK_POWER_CONTEXT *)*((_QWORD *)v5 + 143);
          if ( v19 )
          {
            if ( *((_BYTE *)v5 + 1152) )
            {
              v20 = PmCalculateIdlePower(v19, v14, (unsigned int *)&QpcTimeStamp);
              RequestorProcess = IoGetRequestorProcess(a2);
              v24 = *((_QWORD *)v5 + 143);
              v25 = RequestorProcess;
              v26 = QpcTimeStamp;
              v27 = *(PEPROCESS *)(v24 + 208);
              *(_DWORD *)(v24 + 232) = QpcTimeStamp;
              if ( (Microsoft_Windows_PartitionEnableBits & 2) != 0 )
                McTemplateK0pxxu_EtwWriteTransfer(v24, v22, v23, v27, v20, v14, v26);
              PsUpdateComponentPower(v27, 1, v20 / 0x2710);
              if ( v25 != v27 )
              {
                if ( v25 && !(unsigned __int8)ObReferenceObjectSafe(v25) )
                  v25 = 0;
                if ( v27 )
                  ObDereferenceObjectDeferDelete(v27);
              }
              *(_QWORD *)(*((_QWORD *)v5 + 143) + 208LL) = v25;
            }
          }
        }
      }
    }
    else
    {
      CurrentStackLocation->MinorFunction = 0;
    }
    v15 = *((_QWORD *)v5 + 89);
    if ( v15 )
    {
      v17 = *(void (__fastcall **)(struct _IRP *))(v15 + 8);
      if ( v17 )
        v17(a2);
    }
    return IofCallDriver(*((PDEVICE_OBJECT *)v5 + 2), a2);
  }
}

```

## disassembly

```asm
0x140002550  push    rbx
0x140002552  push    rbp
0x140002553  push    r14
0x140002555  sub     rsp, 50h
0x140002559  mov     rbx, [rcx+40h]
0x14000255d  mov     r14, rdx
0x140002560  mov     rbp, rcx
0x140002563  mov     rax, [rbx+0E8h]
0x14000256a  cmp     dword ptr [rax+1Ch], 12h
0x14000256e  jz      loc_1400026D2
0x140002574  mov     rbp, [rbp+40h]
0x140002578  lea     rdx, ?PmIoCompletion@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; PmIoCompletion(_DEVICE_OBJECT *,_IRP *,void *)
0x14000257f  mov     [rsp+68h+arg_8], rsi
0x140002584  mov     [rsp+68h+arg_10], rdi
0x14000258c  mov     rdi, [r14+0B8h]
0x140002593  mov     [rsp+68h+arg_18], r12
0x14000259b  mov     [rsp+68h+var_20], r13
0x1400025a0  xor     r13d, r13d
0x1400025a3  mov     [rsp+68h+var_28], r15
0x1400025a8  movups  xmm0, xmmword ptr [rdi]
0x1400025ab  movups  xmmword ptr [rdi-48h], xmm0
0x1400025af  movups  xmm1, xmmword ptr [rdi+10h]
0x1400025b3  movups  xmmword ptr [rdi-38h], xmm1
0x1400025b7  movups  xmm0, xmmword ptr [rdi+20h]
0x1400025bb  movups  xmmword ptr [rdi-28h], xmm0
0x1400025bf  movsd   xmm1, qword ptr [rdi+30h]
0x1400025c4  movsd   qword ptr [rdi-18h], xmm1
0x1400025c9  mov     byte ptr [rdi-45h], 0
0x1400025cd  mov     rcx, [r14+0B8h]
0x1400025d4  mov     eax, [rdi+10h]
0x1400025d7  mov     [rcx-10h], rdx
0x1400025db  mov     [rcx-8], rax
0x1400025df  mov     byte ptr [rcx-45h], 0E0h
0x1400025e3  lea     rcx, [rsp+68h+QpcTimeStamp]; QpcTimeStamp
0x1400025e8  mov     rax, [rbp+2D0h]
0x1400025ef  mov     esi, [rax+38h]
0x1400025f2  mov     r12, [rbp+2D0h]
0x1400025f9  mov     [rsp+68h+QpcTimeStamp], r13
0x1400025fe  call    cs:__imp_KeQueryUnbiasedInterruptTimePrecise
0x140002605  nop     dword ptr [rax+rax+00h]
0x14000260a  mov     [rdi+8], rax
0x14000260e  mov     rbx, rax
0x140002611  test    esi, esi
0x140002613  jz      loc_1400026CC
0x140002619  mov     rcx, r14; Irp
0x14000261c  mov     byte ptr [rdi+1], 1
0x140002620  call    cs:__imp_IoGetIoPriorityHint
0x140002627  nop     dword ptr [rax+rax+00h]
0x14000262c  cmp     eax, 1
0x14000262f  jle     loc_14000271A
0x140002635  or      byte ptr [rdi+1], 2
0x140002639  mov     r9b, 1; unsigned __int8
0x14000263c  lea     r8, [rdi+10h]; unsigned int *
0x140002640  mov     [rsp+68h+var_48], r13b; char
0x140002645  mov     rdx, rbx; union _LARGE_INTEGER
0x140002648  mov     rcx, r12; struct _PERF_COUNTER_CONTEXT *
0x14000264b  call    ?PmPerfCounterIdleUpdate@@YA_KPEAU_PERF_COUNTER_CONTEXT@@T_LARGE_INTEGER@@PEAKEE@Z; PmPerfCounterIdleUpdate(_PERF_COUNTER_CONTEXT *,_LARGE_INTEGER,ulong *,uchar,uchar)
0x140002650  mov     rbx, rax
0x140002653  test    rax, rax
0x140002656  jz      short loc_140002671
0x140002658  mov     dword ptr [rsp+68h+QpcTimeStamp], r13d
0x14000265d  call    cs:__imp_PoEnergyEstimationEnabled
0x140002664  nop     dword ptr [rax+rax+00h]
0x140002669  test    al, al
0x14000266b  jnz     loc_140011938
0x140002671  mov     rax, [rbp+2C8h]
0x140002678  mov     r15, [rsp+68h+var_28]
0x14000267d  mov     r13, [rsp+68h+var_20]
0x140002682  mov     r12, [rsp+68h+arg_18]
0x14000268a  mov     rdi, [rsp+68h+arg_10]
0x140002692  mov     rsi, [rsp+68h+arg_8]
0x140002697  test    rax, rax
0x14000269a  jnz     short loc_1400026B9
0x14000269c  mov     rcx, [rbp+10h]; DeviceObject
0x1400026a0  mov     rdx, r14; Irp
0x1400026a3  call    cs:__imp_IofCallDriver
0x1400026aa  nop     dword ptr [rax+rax+00h]
0x1400026af  add     rsp, 50h
0x1400026b3  pop     r14
0x1400026b5  pop     rbp
0x1400026b6  pop     rbx
0x1400026b7  retn
0x1400026b9  mov     rax, [rax+8]
0x1400026bd  test    rax, rax
0x1400026c0  jz      short loc_14000269C
0x1400026c2  mov     rcx, r14
0x1400026c5  call    _guard_dispatch_icall
0x1400026ca  jmp     short loc_14000269C
0x1400026cc  mov     [rdi+1], r13b
0x1400026d0  jmp     short loc_140002671
0x1400026d2  mov     rdx, [rdx+0B8h]
0x1400026d9  test    byte ptr [rdx+2], 10h
0x1400026dd  jnz     loc_140002574
0x1400026e3  cmp     dword ptr [rbx+288h], 1
0x1400026ea  jnz     loc_140002574
0x1400026f0  mov     r8d, [rdx+8]; unsigned __int64
0x1400026f4  mov     rcx, rbx; struct _DEVICE_EXTENSION *
0x1400026f7  mov     rdx, [rdx+18h]; __int64
0x1400026fb  call    ?PmIsOverlap@@YAEPEAU_DEVICE_EXTENSION@@_J_K@Z; PmIsOverlap(_DEVICE_EXTENSION *,__int64,unsigned __int64)
0x140002700  test    al, al
0x140002702  jz      loc_140002574
0x140002708  mov     rdx, r14; struct _IRP *
0x14000270b  mov     rcx, rbx; struct _DEVICE_EXTENSION *
0x14000270e  call    ?PmRedirectRequest@@YAXPEAU_DEVICE_EXTENSION@@PEAU_IRP@@@Z; PmRedirectRequest(_DEVICE_EXTENSION *,_IRP *)
0x140002713  mov     eax, 103h
0x140002718  jmp     short loc_1400026AF
0x14000271a  xor     r9b, r9b
0x14000271d  jmp     loc_14000263C
0x140011938  mov     rcx, [rbp+478h]; struct _DISK_POWER_CONTEXT *
0x14001193f  test    rcx, rcx
0x140011942  jz      loc_140002671
0x140011948  cmp     [rbp+480h], r13b
0x14001194f  jz      loc_140002671
0x140011955  lea     r8, [rsp+68h+QpcTimeStamp]; unsigned int *
0x14001195a  mov     rdx, rbx; unsigned __int64
0x14001195d  call    ?PmCalculateIdlePower@@YA_KPEAU_DISK_POWER_CONTEXT@@_KPEAK@Z; PmCalculateIdlePower(_DISK_POWER_CONTEXT *,unsigned __int64,ulong *)
0x140011962  mov     rcx, r14; Irp
0x140011965  mov     r15, rax
0x140011968  call    cs:__imp_IoGetRequestorProcess
0x14001196f  nop     dword ptr [rax+rax+00h]
0x140011974  mov     rcx, [rbp+478h]
0x14001197b  mov     rdi, rax
0x14001197e  mov     eax, dword ptr [rsp+68h+QpcTimeStamp]
0x140011982  mov     rsi, [rcx+0D0h]
0x140011989  mov     [rcx+0E8h], eax
0x14001198f  test    cs:Microsoft_Windows_PartitionEnableBits, 2
0x140011996  jz      short loc_1400119AE
0x140011998  mov     [rsp+68h+var_38], al
0x14001199c  mov     r9, rsi
0x14001199f  mov     [rsp+68h+var_40], rbx
0x1400119a4  mov     qword ptr [rsp+68h+var_48], r15
0x1400119a9  call    McTemplateK0pxxu_EtwWriteTransfer
0x1400119ae  mov     rax, 346DC5D63886594Bh
0x1400119b8  mov     rcx, rsi
0x1400119bb  mul     r15
0x1400119be  shr     rdx, 0Bh
0x1400119c2  mov     r8, rdx
0x1400119c5  mov     edx, 1
0x1400119ca  call    cs:__imp_PsUpdateComponentPower
0x1400119d1  nop     dword ptr [rax+rax+00h]
0x1400119d6  cmp     rdi, rsi
0x1400119d9  jz      short loc_140011A09
0x1400119db  test    rdi, rdi
0x1400119de  jz      short loc_1400119F5
0x1400119e0  mov     rcx, rdi
0x1400119e3  call    cs:__imp_ObReferenceObjectSafe
0x1400119ea  nop     dword ptr [rax+rax+00h]
0x1400119ef  test    al, al
0x1400119f1  cmovz   rdi, r13
0x1400119f5  test    rsi, rsi
0x1400119f8  jz      short loc_140011A09
0x1400119fa  mov     rcx, rsi; Object
0x1400119fd  call    cs:__imp_ObDereferenceObjectDeferDelete
0x140011a04  nop     dword ptr [rax+rax+00h]
0x140011a09  mov     rax, [rbp+478h]
0x140011a10  mov     [rax+0D0h], rdi
0x140011a17  jmp     loc_140002671
```
