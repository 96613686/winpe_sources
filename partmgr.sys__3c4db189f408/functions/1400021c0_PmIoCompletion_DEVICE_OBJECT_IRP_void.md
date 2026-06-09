# PmIoCompletion(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x1400021c0`
- end: `0x140002544`
- name: `?PmIoCompletion@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `900`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *, void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1400021c0`
- `0x1400034a0`
- `0x1400045c0`
- `0x140009ca4`
- `0x14000bc88`
- `0x140010f60`

## import_xrefs

- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x14000221a`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x14000221a`
- `ntoskrnl!IoQueueWorkItem` at `0x140002513`
- `ntoskrnl!IoQueueWorkItem` at `0x140002513`
- `ntoskrnl!PoEnergyEstimationEnabled` at `0x14000234f`
- `ntoskrnl!PoEnergyEstimationEnabled` at `0x14000234f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400024eb`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400024eb`
- `ntoskrnl!IoGetIoPriorityHint` at `0x140002385`
- `ntoskrnl!IoGetIoPriorityHint` at `0x140002385`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400024ae`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400024ae`

## pseudocode

```c
__int64 __fastcall PmIoCompletion(struct _DEVICE_OBJECT *a1, struct _IRP *a2, void *a3)
{
  bool v3; // zf
  unsigned int v4; // r13d
  char *DeviceExtension; // rdi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r14
  UCHAR MinorFunction; // r12
  __int64 v9; // r15
  ULONG64 v10; // rbx
  char v11; // r12
  __int64 v12; // rdx
  __int64 v13; // rdx
  UCHAR MajorFunction; // cl
  unsigned __int64 ProviderId; // r15
  struct _DISK_POWER_CONTEXT *v16; // rcx
  UCHAR v17; // al
  volatile signed __int64 *v18; // r8
  unsigned __int64 v19; // rax
  unsigned __int64 v20; // rdx
  unsigned __int64 v21; // rcx
  void (__fastcall **v22)(_QWORD, _QWORD, struct _IRP *); // rax
  void (__fastcall *v23)(_QWORD, _QWORD, struct _IRP *); // rax
  NTSTATUS Status; // eax
  __int64 v25; // rbx
  __int64 result; // rax
  KIRQL v27; // al
  char *i; // r8
  unsigned __int64 QpcTimeStamp; // [rsp+70h] [rbp+8h] BYREF
  _QWORD *v30; // [rsp+78h] [rbp+10h]

  v3 = a2->PendingReturned == 0;
  v4 = (unsigned int)a3;
  DeviceExtension = (char *)a1->DeviceExtension;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v30 = PmControlObject->DeviceExtension;
  if ( !v3 )
    CurrentStackLocation->Control |= 1u;
  MinorFunction = CurrentStackLocation->MinorFunction;
  v9 = *((_QWORD *)DeviceExtension + 90);
  QpcTimeStamp = 0;
  v10 = KeQueryUnbiasedInterruptTimePrecise(&QpcTimeStamp);
  CurrentStackLocation->Parameters.WMI.ProviderId = v10 - CurrentStackLocation->Parameters.WMI.ProviderId;
  if ( (MinorFunction & 1) != 0 )
  {
    if ( v9 )
    {
      v11 = MinorFunction & 2;
      PmPerfCounterIdleUpdate(
        (struct _PERF_COUNTER_CONTEXT *)v9,
        (union _LARGE_INTEGER)v10,
        &CurrentStackLocation->Parameters.Create.Options,
        v11 != 0,
        1);
      LODWORD(v12) = HIDWORD(KeGetPcr()[1].LockArray);
      if ( (unsigned int)v12 < *(_DWORD *)(v9 + 60) )
      {
        v13 = v9 + 192 * v12;
        MajorFunction = a2->Tail.Overlay.CurrentStackLocation->MajorFunction;
        switch ( MajorFunction )
        {
          case 3u:
            *(_QWORD *)(v13 + 128) += a2->IoStatus.Information;
            ++*(_DWORD *)(v13 + 176);
            *(_QWORD *)(v13 + 144) += CurrentStackLocation->Parameters.Create.SecurityContext;
            break;
          case 4u:
            *(_QWORD *)(v13 + 136) += a2->IoStatus.Information;
            ++*(_DWORD *)(v13 + 180);
            *(_QWORD *)(v13 + 152) += CurrentStackLocation->Parameters.Create.SecurityContext;
            break;
          case 9u:
            ++*(_DWORD *)(v13 + 184);
            *(_QWORD *)(v13 + 160) += CurrentStackLocation->Parameters.Create.SecurityContext;
            break;
        }
        if ( (a2->Flags & 8) != 0 )
          ++*(_DWORD *)(v13 + 188);
        if ( v11 )
          PmPerfCounterStatUpdate(
            (struct _PERF_PRIORITY_COUNTER *)(v13 + 192),
            a2,
            (union _LARGE_INTEGER *)&CurrentStackLocation->Parameters);
      }
    }
  }
  ProviderId = CurrentStackLocation->Parameters.WMI.ProviderId;
  if ( (unsigned __int8)PoEnergyEstimationEnabled() )
  {
    v16 = (struct _DISK_POWER_CONTEXT *)*((_QWORD *)DeviceExtension + 143);
    if ( v16 )
    {
      if ( DeviceExtension[1152] )
        PmUpdateIoPower(v16, a2, v10, ProviderId);
    }
  }
  if ( IoGetIoPriorityHint(a2) > IoPriorityLow )
  {
    v17 = CurrentStackLocation->MajorFunction;
    if ( CurrentStackLocation->MajorFunction == 3 )
    {
      v18 = (volatile signed __int64 *)(DeviceExtension + 792);
    }
    else if ( v17 == 4 )
    {
      v18 = (volatile signed __int64 *)(DeviceExtension + 800);
    }
    else
    {
      v18 = 0;
      if ( v17 == 9 )
        v18 = (volatile signed __int64 *)(DeviceExtension + 808);
    }
    v19 = *v18;
    v20 = CurrentStackLocation->Parameters.WMI.ProviderId;
    if ( v20 > *v18 )
    {
      do
      {
        v21 = v19;
        v19 = _InterlockedCompareExchange64(v18, v20, v19);
        if ( v19 == v21 )
          break;
        v20 = CurrentStackLocation->Parameters.WMI.ProviderId;
      }
      while ( v20 > v19 );
    }
  }
  v22 = (void (__fastcall **)(_QWORD, _QWORD, struct _IRP *))*((_QWORD *)DeviceExtension + 89);
  if ( v22 && *v22 )
  {
    v23 = *v22;
    CurrentStackLocation->Parameters.WMI.ProviderId = (signed __int64)(CurrentStackLocation->Parameters.WMI.ProviderId
                                                                     * v30[54])
                                                    / 10000000;
    v23(v4, *((unsigned int *)DeviceExtension + 42), a2);
  }
  Status = a2->IoStatus.Status;
  switch ( Status )
  {
    case -2147483626:
      PmPropagateVerify((struct _DEVICE_EXTENSION *)DeviceExtension);
      return 0;
    case -1073740703:
      v25 = 5;
      break;
    case -1073740693:
      v25 = 6;
      break;
    case -1073740692:
      v25 = 7;
      break;
    case -1073740642:
      v25 = 8;
      break;
    default:
      return 0;
  }
  result = 0;
  if ( *((_DWORD *)DeviceExtension + 130) )
    return result;
  if ( !_InterlockedCompareExchange((volatile signed __int32 *)DeviceExtension + 221, 1, 0) )
  {
    v27 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)DeviceExtension + 14);
    for ( i = (char *)*((_QWORD *)DeviceExtension + 112); i != DeviceExtension + 896; i = *(char **)i )
      *((_DWORD *)i - 26) |= 0x80u;
    KeReleaseSpinLock((PKSPIN_LOCK)DeviceExtension + 14, v27);
    _InterlockedExchange((volatile __int32 *)DeviceExtension + 131, 0);
    IoQueueWorkItem(*((PIO_WORKITEM *)DeviceExtension + 111), PmOfflineDiskWorkItem, CriticalWorkQueue, (PVOID)v25);
  }
  return 0;
}

```

## disassembly

```asm
0x1400021c0  mov     [rsp+arg_10], rbx
0x1400021c5  push    rbp
0x1400021c6  push    rsi
0x1400021c7  push    rdi
0x1400021c8  push    r12
0x1400021ca  push    r13
0x1400021cc  push    r14
0x1400021ce  push    r15
0x1400021d0  sub     rsp, 30h
0x1400021d4  cmp     byte ptr [rdx+41h], 0
0x1400021d8  mov     r13, r8
0x1400021db  mov     rax, cs:?PmControlObject@@3PEAU_DEVICE_OBJECT@@EA; _DEVICE_OBJECT * PmControlObject
0x1400021e2  mov     rbp, rdx
0x1400021e5  mov     rdi, [rcx+40h]
0x1400021e9  mov     r14, [rdx+0B8h]
0x1400021f0  mov     rax, [rax+40h]
0x1400021f4  mov     [rsp+68h+arg_8], rax
0x1400021f9  jz      short loc_140002200
0x1400021fb  or      byte ptr [r14+3], 1
0x140002200  movzx   r12d, byte ptr [r14+1]
0x140002205  lea     rcx, [rsp+68h+QpcTimeStamp]; QpcTimeStamp
0x14000220a  mov     r15, [rdi+2D0h]
0x140002211  mov     [rsp+68h+QpcTimeStamp], 0
0x14000221a  call    cs:__imp_KeQueryUnbiasedInterruptTimePrecise
0x140002221  nop     dword ptr [rax+rax+00h]
0x140002226  mov     rbx, rax
0x140002229  sub     rax, [r14+8]
0x14000222d  mov     [r14+8], rax
0x140002231  test    r12b, 1
0x140002235  jz      loc_14000234B
0x14000223b  test    r15, r15
0x14000223e  jz      loc_14000234B
0x140002244  and     r12b, 2
0x140002248  mov     [rsp+68h+var_48], 1; char
0x14000224d  lea     r8, [r14+10h]; unsigned int *
0x140002251  mov     rdx, rbx; union _LARGE_INTEGER
0x140002254  setnz   r9b; unsigned __int8
0x140002258  mov     rcx, r15; struct _PERF_COUNTER_CONTEXT *
0x14000225b  call    ?PmPerfCounterIdleUpdate@@YA_KPEAU_PERF_COUNTER_CONTEXT@@T_LARGE_INTEGER@@PEAKEE@Z; PmPerfCounterIdleUpdate(_PERF_COUNTER_CONTEXT *,_LARGE_INTEGER,ulong *,uchar,uchar)
0x140002260  mov     edx, gs:1A4h
0x140002268  cmp     edx, [r15+3Ch]
0x14000226c  jnb     loc_14000234B
0x140002272  mov     rax, [rbp+0B8h]
0x140002279  lea     rdx, [rdx+rdx*2]
0x14000227d  shl     rdx, 6
0x140002281  add     rdx, r15
0x140002284  movzx   ecx, byte ptr [rax]
0x140002287  cmp     cl, 3
0x14000228a  jnz     short loc_1400022C0
0x14000228c  mov     rcx, [rdx+80h]
0x140002293  add     rcx, [rbp+38h]
0x140002297  mov     [rdx+80h], rcx
0x14000229e  mov     eax, [rdx+0B0h]
0x1400022a4  inc     eax
0x1400022a6  mov     [rdx+0B0h], eax
0x1400022ac  mov     rcx, [rdx+90h]
0x1400022b3  add     rcx, [r14+8]
0x1400022b7  mov     [rdx+90h], rcx
0x1400022be  jmp     short loc_14000231E
0x1400022c0  cmp     cl, 4
0x1400022c3  jnz     short loc_1400022F9
0x1400022c5  mov     rcx, [rdx+88h]
0x1400022cc  add     rcx, [rbp+38h]
0x1400022d0  mov     [rdx+88h], rcx
0x1400022d7  mov     eax, [rdx+0B4h]
0x1400022dd  inc     eax
0x1400022df  mov     [rdx+0B4h], eax
0x1400022e5  mov     rcx, [rdx+98h]
0x1400022ec  add     rcx, [r14+8]
0x1400022f0  mov     [rdx+98h], rcx
0x1400022f7  jmp     short loc_14000231E
0x1400022f9  cmp     cl, 9
0x1400022fc  jnz     short loc_14000231E
0x1400022fe  mov     eax, [rdx+0B8h]
0x140002304  inc     eax
0x140002306  mov     [rdx+0B8h], eax
0x14000230c  mov     rcx, [rdx+0A0h]
0x140002313  add     rcx, [r14+8]
0x140002317  mov     [rdx+0A0h], rcx
0x14000231e  mov     eax, [rbp+10h]
0x140002321  test    al, 8
0x140002323  jz      short loc_140002333
0x140002325  mov     eax, [rdx+0BCh]
0x14000232b  inc     eax
0x14000232d  mov     [rdx+0BCh], eax
0x140002333  test    r12b, r12b
0x140002336  jz      short loc_14000234B
0x140002338  lea     rcx, [rdx+0C0h]; struct _PERF_PRIORITY_COUNTER *
0x14000233f  mov     rdx, rbp; struct _IRP *
0x140002342  lea     r8, [r14+8]; union _LARGE_INTEGER *
0x140002346  call    ?PmPerfCounterStatUpdate@@YAXPEAU_PERF_PRIORITY_COUNTER@@PEAU_IRP@@PEAT_LARGE_INTEGER@@@Z; PmPerfCounterStatUpdate(_PERF_PRIORITY_COUNTER *,_IRP *,_LARGE_INTEGER *)
0x14000234b  mov     r15, [r14+8]
0x14000234f  call    cs:__imp_PoEnergyEstimationEnabled
0x140002356  nop     dword ptr [rax+rax+00h]
0x14000235b  test    al, al
0x14000235d  jz      short loc_140002382
0x14000235f  mov     rcx, [rdi+478h]; struct _DISK_POWER_CONTEXT *
0x140002366  test    rcx, rcx
0x140002369  jz      short loc_140002382
0x14000236b  cmp     byte ptr [rdi+480h], 0
0x140002372  jz      short loc_140002382
0x140002374  mov     r9, r15; unsigned __int64
0x140002377  mov     r8, rbx; unsigned __int64
0x14000237a  mov     rdx, rbp; struct _IRP *
0x14000237d  call    ?PmUpdateIoPower@@YAXPEAU_DISK_POWER_CONTEXT@@PEAU_IRP@@_K2@Z; PmUpdateIoPower(_DISK_POWER_CONTEXT *,_IRP *,unsigned __int64,unsigned __int64)
0x140002382  mov     rcx, rbp; Irp
0x140002385  call    cs:__imp_IoGetIoPriorityHint
0x14000238c  nop     dword ptr [rax+rax+00h]
0x140002391  cmp     eax, 1
0x140002394  jle     short loc_1400023E6
0x140002396  movzx   eax, byte ptr [r14]
0x14000239a  cmp     al, 3
0x14000239c  jz      short loc_1400023BB
0x14000239e  cmp     al, 4
0x1400023a0  jz      short loc_1400023B2
0x1400023a2  xor     r8d, r8d
0x1400023a5  cmp     al, 9
0x1400023a7  jnz     short loc_1400023C2
0x1400023a9  lea     r8, [rdi+328h]
0x1400023b0  jmp     short loc_1400023C2
0x1400023b2  lea     r8, [rdi+320h]
0x1400023b9  jmp     short loc_1400023C2
0x1400023bb  lea     r8, [rdi+318h]
0x1400023c2  mov     rax, [r8]
0x1400023c5  mov     rdx, [r14+8]
0x1400023c9  cmp     rdx, rax
0x1400023cc  jbe     short loc_1400023E6
0x1400023ce  xchg    ax, ax
0x1400023d0  mov     rcx, rax
0x1400023d3  lock cmpxchg [r8], rdx
0x1400023d8  cmp     rax, rcx
0x1400023db  jz      short loc_1400023E6
0x1400023dd  mov     rdx, [r14+8]
0x1400023e1  cmp     rdx, rax
0x1400023e4  ja      short loc_1400023D0
0x1400023e6  mov     rax, [rdi+2C8h]
0x1400023ed  test    rax, rax
0x1400023f0  jz      short loc_140002441
0x1400023f2  mov     r9, [rax]
0x1400023f5  test    r9, r9
0x1400023f8  jz      short loc_140002441
0x1400023fa  mov     rcx, [rsp+68h+arg_8]
0x1400023ff  mov     rax, 0D6BF94D5E57A42BDh
0x140002409  mov     r8, rbp
0x14000240c  mov     rcx, [rcx+1B0h]
0x140002413  imul    rcx, [r14+8]
0x140002418  imul    rcx
0x14000241b  mov     rax, r9
0x14000241e  add     rdx, rcx
0x140002421  sar     rdx, 17h
0x140002425  mov     rcx, rdx
0x140002428  shr     rcx, 3Fh
0x14000242c  add     rdx, rcx
0x14000242f  mov     ecx, r13d
0x140002432  mov     [r14+8], rdx
0x140002436  mov     edx, [rdi+0A8h]
0x14000243c  call    _guard_dispatch_icall
0x140002441  mov     eax, [rbp+30h]
0x140002444  cmp     eax, 80000016h
0x140002449  jz      loc_140002521
0x14000244f  cmp     eax, 0C0000461h
0x140002454  jz      short loc_140002484
0x140002456  cmp     eax, 0C000046Bh
0x14000245b  jz      short loc_14000247D
0x14000245d  cmp     eax, 0C000046Ch
0x140002462  jz      short loc_140002476
0x140002464  cmp     eax, 0C000049Eh
0x140002469  jnz     loc_140002529
0x14000246f  mov     ebx, 8
0x140002474  jmp     short loc_140002489
0x140002476  mov     ebx, 7
0x14000247b  jmp     short loc_140002489
0x14000247d  mov     ebx, 6
0x140002482  jmp     short loc_140002489
0x140002484  mov     ebx, 5
0x140002489  xor     eax, eax
0x14000248b  cmp     [rdi+208h], eax
0x140002491  jnz     loc_14000252B
0x140002497  mov     ecx, 1
0x14000249c  lock cmpxchg [rdi+374h], ecx
0x1400024a4  jnz     loc_140002529
0x1400024aa  lea     rcx, [rdi+70h]; SpinLock
0x1400024ae  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400024b5  nop     dword ptr [rax+rax+00h]
0x1400024ba  lea     r10, [rdi+380h]
0x1400024c1  mov     r8, [r10]
0x1400024c4  cmp     r8, r10
0x1400024c7  jz      short loc_1400024E4
0x1400024c9  nop     dword ptr [rax+00000000h]
0x1400024d0  mov     edx, [r8-68h]
0x1400024d4  bts     edx, 7
0x1400024d8  mov     [r8-68h], edx
0x1400024dc  mov     r8, [r8]
0x1400024df  cmp     r8, r10
0x1400024e2  jnz     short loc_1400024D0
0x1400024e4  movzx   edx, al; NewIrql
0x1400024e7  lea     rcx, [rdi+70h]; SpinLock
0x1400024eb  call    cs:__imp_KeReleaseSpinLock
0x1400024f2  nop     dword ptr [rax+rax+00h]
0x1400024f7  xor     eax, eax
0x1400024f9  lea     rdx, ?PmOfflineDiskWorkItem@@YAXPEAU_DEVICE_OBJECT@@PEAX@Z; WorkerRoutine
0x140002500  xchg    eax, [rdi+20Ch]
0x140002506  mov     rcx, [rdi+378h]; IoWorkItem
0x14000250d  mov     r9, rbx; Context
0x140002510  xor     r8d, r8d; QueueType
0x140002513  call    cs:__imp_IoQueueWorkItem
0x14000251a  nop     dword ptr [rax+rax+00h]
0x14000251f  jmp     short loc_140002529
0x140002521  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x140002524  call    ?PmPropagateVerify@@YAXPEAU_DEVICE_EXTENSION@@@Z; PmPropagateVerify(_DEVICE_EXTENSION *)
0x140002529  xor     eax, eax
0x14000252b  mov     rbx, [rsp+68h+arg_10]
0x140002533  add     rsp, 30h
0x140002537  pop     r15
0x140002539  pop     r14
0x14000253b  pop     r13
0x14000253d  pop     r12
0x14000253f  pop     rdi
0x140002540  pop     rsi
0x140002541  pop     rbp
0x140002542  retn
```
