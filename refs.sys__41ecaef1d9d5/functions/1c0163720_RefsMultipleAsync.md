# RefsMultipleAsync

- ea: `0x1c0163720`
- end: `0x1c0163995`
- name: `RefsMultipleAsync`
- size: `629`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1c01639a0`

## callees

- `0x1c000f920`
- `0x1c000f980`
- `0x1c000f9a0`
- `0x1c0093cc0`
- `0x1c00b1354`
- `0x1c00b2638`
- `0x1c00b2fcc`
- `0x1c0163720`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1c016388f`
- `ntoskrnl!IofCompleteRequest` at `0x1c0163917`
- `ntoskrnl!IofCompleteRequest` at `0x1c016388f`
- `ntoskrnl!IofCompleteRequest` at `0x1c0163917`
- `ntoskrnl!IoQueueWorkItemEx` at `0x1c0163805`
- `ntoskrnl!IoQueueWorkItemEx` at `0x1c0163805`
- `ntoskrnl!IoSetIoPriorityHint` at `0x1c016393c`
- `ntoskrnl!IoSetIoPriorityHint` at `0x1c016393c`
- `ntoskrnl!IofCallDriver` at `0x1c016394d`
- `ntoskrnl!IofCallDriver` at `0x1c016394d`

## pseudocode

```c
void __fastcall RefsMultipleAsync(
        __int64 a1,
        struct _DEVICE_OBJECT *a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        __int64 a6)
{
  __int64 v9; // rsi
  __int64 v10; // r8
  __int64 v11; // r8
  unsigned int i; // edi
  __int64 v13; // rax
  IRP *v14; // r15
  struct _IO_WORKITEM *v15; // rcx
  char IsVolumeOnSmr; // al
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  __int64 v18; // rcx
  void *v19; // rdx
  int v20; // ecx
  char v21; // al
  char v22; // [rsp+24h] [rbp-74h]
  __int64 v23; // [rsp+30h] [rbp-68h] BYREF
  __int64 v24; // [rsp+38h] [rbp-60h] BYREF
  LARGE_INTEGER ByteOffset; // [rsp+40h] [rbp-58h]
  _QWORD v26[3]; // [rsp+50h] [rbp-48h] BYREF
  __int64 Length; // [rsp+68h] [rbp-30h]

  v9 = 0;
  v23 = 0;
  v24 = 0;
  v22 = 0;
  v10 = a4;
  if ( *(_QWORD *)(a5 + 8) == a3 )
    v10 = 0;
  RefsPreProcessIo(a1, a3, v10);
  for ( i = 0; i < a4; ++i )
  {
    v13 = 32LL * i;
    v14 = *(IRP **)(v13 + a5 + 8);
    v15 = *(struct _IO_WORKITEM **)(v13 + a5 + 16);
    if ( v15 )
    {
      v19 = *(void **)(32LL * i + a5 + 24);
      if ( *(_QWORD *)(a5 + 8) == a3 )
        RefsDecompressWorker(0, v19, *(PIO_WORKITEM *)(v13 + a5 + 16));
      else
        IoQueueWorkItemEx(v15, RefsDecompressWorker, CriticalWorkQueue, v19);
    }
    else
    {
      IsVolumeOnSmr = MsIsVolumeOnSmr(*(_QWORD *)(*(_QWORD *)(a1 + 64) + 104LL), i, v11);
      CurrentStackLocation = v14->Tail.Overlay.CurrentStackLocation;
      if ( IsVolumeOnSmr && CurrentStackLocation[-1].MajorFunction == 4 )
      {
        ByteOffset = CurrentStackLocation[-1].Parameters.Read.ByteOffset;
        v26[2] = ByteOffset.QuadPart;
        Length = CurrentStackLocation[-1].Parameters.Read.Length;
        v26[0] = ByteOffset.QuadPart;
        v26[1] = Length;
        v20 = MsAcquireContainerWriteHead(a6, v26, &v23, &v24);
        if ( v20 < 0 )
        {
          v14->Tail.Overlay.CurrentStackLocation[-1].DeviceObject = a2;
          --v14->CurrentLocation;
          --v14->Tail.Overlay.CurrentStackLocation;
          v14->IoStatus.Status = v20;
          IofCompleteRequest(v14, 1);
          v9 = v23;
          continue;
        }
        v21 = v22;
        v9 = v23;
        if ( v23 )
          v21 = 1;
        v22 = v21;
        if ( RefsEnableSMRSimulation )
        {
          if ( !(unsigned __int8)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))MsKmDebugSMRWrite)(
                                   *(_QWORD *)(*(_QWORD *)(a1 + 64) + 6144LL),
                                   Length,
                                   (LARGE_INTEGER)ByteOffset.QuadPart) )
          {
            v14->Tail.Overlay.CurrentStackLocation[-1].DeviceObject = a2;
            --v14->CurrentLocation;
            --v14->Tail.Overlay.CurrentStackLocation;
            v14->IoStatus.Status = -1073740684;
            IofCompleteRequest(v14, 1);
            continue;
          }
          v21 = v22;
        }
        if ( v21 )
          IoSetIoPriorityHint(v14, IoPriorityNormal);
      }
      if ( (*(_DWORD *)(a1 + 12) & 1) != 0 )
        IofCallDriver(a2, v14);
      else
        RefsCallStorageDriver(a2, v14, RefsReserveStackStorage, 0);
      if ( v22 )
      {
        MsReleaseContainerWriteHead(v18, v9, v24);
        v22 = 0;
      }
    }
  }
}

```

## disassembly

```asm
0x1c0163720  mov     [rsp+arg_0], rbx
0x1c0163725  mov     [rsp+arg_10], rsi
0x1c016372a  mov     [rsp+DeviceObject], rdx
0x1c016372f  push    rdi
0x1c0163730  push    r12
0x1c0163732  push    r13
0x1c0163734  push    r14
0x1c0163736  push    r15
0x1c0163738  sub     rsp, 70h
0x1c016373c  mov     ebx, r9d
0x1c016373f  mov     r13, r8
0x1c0163742  mov     r14, rcx
0x1c0163745  mov     r12, [rsp+98h+arg_20]
0x1c016374d  xor     esi, esi
0x1c016374f  mov     [rsp+98h+var_68], rsi
0x1c0163754  mov     [rsp+98h+var_60], rsi
0x1c0163759  mov     byte ptr [rsp+98h+var_74], sil
0x1c016375e  mov     r8d, ebx
0x1c0163761  cmp     [r12+8], r13
0x1c0163766  cmovz   r8d, esi
0x1c016376a  mov     rdx, r13
0x1c016376d  call    RefsPreProcessIo
0x1c0163772  mov     edi, esi
0x1c0163774  mov     [rsp+98h+var_70], esi
0x1c0163778  cmp     edi, ebx
0x1c016377a  jnb     loc_1C016397A
0x1c0163780  mov     edx, edi
0x1c0163782  mov     eax, edi
0x1c0163784  shl     rax, 5
0x1c0163788  mov     r15, [rax+r12+8]
0x1c016378d  mov     rcx, [rax+r12+10h]; IoWorkItem
0x1c0163792  test    rcx, rcx
0x1c0163795  jnz     short loc_1C01637E8
0x1c0163797  mov     rcx, [r14+40h]
0x1c016379b  mov     rcx, [rcx+68h]
0x1c016379f  call    MsIsVolumeOnSmr
0x1c01637a4  mov     rcx, [r15+0B8h]
0x1c01637ab  test    al, al
0x1c01637ad  jnz     short loc_1C016381F
0x1c01637af  mov     eax, [r14+0Ch]
0x1c01637b3  mov     rdx, r15; Irp
0x1c01637b6  mov     rcx, [rsp+98h+DeviceObject]; DeviceObject
0x1c01637be  test    al, 1
0x1c01637c0  jnz     loc_1C016394D
0x1c01637c6  xor     r9d, r9d
0x1c01637c9  mov     r8, cs:RefsReserveStackStorage
0x1c01637d0  call    RefsCallStorageDriver
0x1c01637d5  cmp     byte ptr [rsp+98h+var_74], 0
0x1c01637da  jnz     loc_1C016395E
0x1c01637e0  inc     edi
0x1c01637e2  mov     [rsp+98h+var_70], edi
0x1c01637e6  jmp     short loc_1C0163778
0x1c01637e8  shl     rdx, 5
0x1c01637ec  mov     rdx, [rdx+r12+18h]; Context
0x1c01637f1  cmp     [r12+8], r13
0x1c01637f6  jz      short loc_1C0163813
0x1c01637f8  mov     r9, rdx; Context
0x1c01637fb  xor     r8d, r8d; QueueType
0x1c01637fe  lea     rdx, RefsDecompressWorker; WorkerRoutine
0x1c0163805  call    cs:__imp_IoQueueWorkItemEx
0x1c016380c  nop     dword ptr [rax+rax+00h]
0x1c0163811  jmp     short loc_1C01637E0
0x1c0163813  mov     r8, rcx; IoWorkItem
0x1c0163816  xor     ecx, ecx; IoObject
0x1c0163818  call    RefsDecompressWorker
0x1c016381d  jmp     short loc_1C01637E0
0x1c016381f  cmp     byte ptr [rcx-48h], 4
0x1c0163823  jnz     short loc_1C01637AF
0x1c0163825  mov     rax, [rcx-30h]
0x1c0163829  mov     [rsp+98h+var_58], rax
0x1c016382e  mov     [rsp+98h+var_38], rax
0x1c0163833  mov     ecx, [rcx-40h]
0x1c0163836  mov     [rsp+98h+var_30], rcx
0x1c016383b  mov     [rsp+98h+var_48], rax
0x1c0163840  mov     [rsp+98h+var_40], rcx
0x1c0163845  lea     r9, [rsp+98h+var_60]
0x1c016384a  lea     r8, [rsp+98h+var_68]
0x1c016384f  lea     rdx, [rsp+98h+var_48]
0x1c0163854  mov     rcx, [rsp+98h+arg_28]
0x1c016385c  call    MsAcquireContainerWriteHead
0x1c0163861  mov     ecx, eax
0x1c0163863  test    eax, eax
0x1c0163865  jns     short loc_1C01638A5
0x1c0163867  mov     rdx, [r15+0B8h]
0x1c016386e  mov     rax, [rsp+98h+DeviceObject]
0x1c0163876  mov     [rdx-20h], rax
0x1c016387a  dec     byte ptr [r15+43h]
0x1c016387e  add     qword ptr [r15+0B8h], 0FFFFFFFFFFFFFFB8h
0x1c0163886  mov     [r15+30h], ecx
0x1c016388a  mov     dl, 1; PriorityBoost
0x1c016388c  mov     rcx, r15; Irp
0x1c016388f  call    cs:__imp_IofCompleteRequest
0x1c0163896  nop     dword ptr [rax+rax+00h]
0x1c016389b  mov     rsi, [rsp+98h+var_68]
0x1c01638a0  jmp     loc_1C01637E0
0x1c01638a5  mov     eax, [rsp+98h+var_74]
0x1c01638a9  movzx   eax, al
0x1c01638ac  mov     rsi, [rsp+98h+var_68]
0x1c01638b1  test    rsi, rsi
0x1c01638b4  mov     ecx, 1
0x1c01638b9  cmovnz  eax, ecx
0x1c01638bc  mov     [rsp+98h+var_74], eax
0x1c01638c0  mov     [rsp+98h+var_78], al
0x1c01638c4  cmp     cs:RefsEnableSMRSimulation, 0
0x1c01638cb  jz      short loc_1C016392C
0x1c01638cd  mov     rcx, [r14+40h]
0x1c01638d1  mov     r8, [rsp+98h+var_58]
0x1c01638d6  mov     rdx, [rsp+98h+var_30]
0x1c01638db  mov     rcx, [rcx+1800h]
0x1c01638e2  call    MsKmDebugSMRWrite
0x1c01638e7  test    al, al
0x1c01638e9  jnz     short loc_1C0163928
0x1c01638eb  mov     rax, [r15+0B8h]
0x1c01638f2  mov     rcx, [rsp+98h+DeviceObject]
0x1c01638fa  mov     [rax-20h], rcx
0x1c01638fe  dec     byte ptr [r15+43h]
0x1c0163902  add     qword ptr [r15+0B8h], 0FFFFFFFFFFFFFFB8h
0x1c016390a  mov     dword ptr [r15+30h], 0C0000474h
0x1c0163912  mov     dl, 1; PriorityBoost
0x1c0163914  mov     rcx, r15; Irp
0x1c0163917  call    cs:__imp_IofCompleteRequest
0x1c016391e  nop     dword ptr [rax+rax+00h]
0x1c0163923  jmp     loc_1C01637E0
0x1c0163928  mov     eax, [rsp+98h+var_74]
0x1c016392c  test    al, al
0x1c016392e  jz      loc_1C01637AF
0x1c0163934  mov     edx, 2; PriorityHint
0x1c0163939  mov     rcx, r15; Irp
0x1c016393c  call    cs:__imp_IoSetIoPriorityHint
0x1c0163943  nop     dword ptr [rax+rax+00h]
0x1c0163948  jmp     loc_1C01637AF
0x1c016394d  call    cs:__imp_IofCallDriver
0x1c0163954  nop     dword ptr [rax+rax+00h]
0x1c0163959  jmp     loc_1C01637D5
0x1c016395e  mov     r8, [rsp+98h+var_60]
0x1c0163963  mov     rdx, rsi
0x1c0163966  call    MsReleaseContainerWriteHead
0x1c016396b  xor     al, al
0x1c016396d  mov     [rsp+98h+var_74], eax
0x1c0163971  mov     [rsp+98h+var_78], al
0x1c0163975  jmp     loc_1C01637E0
0x1c016397a  lea     r11, [rsp+98h+var_28]
0x1c016397f  mov     rbx, [r11+30h]
0x1c0163983  mov     rsi, [r11+40h]
0x1c0163987  mov     rsp, r11
0x1c016398a  pop     r15
0x1c016398c  pop     r14
0x1c016398e  pop     r13
0x1c0163990  pop     r12
0x1c0163992  pop     rdi
0x1c0163993  retn
0x1c017f370  push    rbp
0x1c017f372  sub     rsp, 20h
0x1c017f376  mov     rbp, rdx
0x1c017f379  add     rsp, 20h
0x1c017f37d  pop     rbp
0x1c017f37e  retn
```
