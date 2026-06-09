# RefsMultipleAsync(_IRP_CONTEXT *,REFS_IO_CONTEXT *,_DEVICE_OBJECT *,_IRP *,ulong,IO_RUN *,CmsTransactionContext *)

- ea: `0x140334528`
- end: `0x1403348ed`
- name: `?RefsMultipleAsync@@YAXPEAU_IRP_CONTEXT@@PEAUREFS_IO_CONTEXT@@PEAU_DEVICE_OBJECT@@PEAU_IRP@@KPEAUIO_RUN@@PEAVCmsTransactionContext@@@Z`
- size: `965`
- prototype: `void(struct _IRP_CONTEXT *, struct REFS_IO_CONTEXT *, struct _DEVICE_OBJECT *, struct _IRP *, unsigned int, struct IO_RUN *, struct CmsTransactionContext *)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14033e290`

## callees

- `0x140088c00`
- `0x1400961f0`
- `0x140099d90`
- `0x1400aa590`
- `0x1400d2024`
- `0x1400dde9c`
- `0x140118aac`
- `0x140334528`
- `0x14033a19c`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1403346a2`
- `ntoskrnl!IofCompleteRequest` at `0x14033471b`
- `ntoskrnl!IofCompleteRequest` at `0x1403346a2`
- `ntoskrnl!IofCompleteRequest` at `0x14033471b`
- `ntoskrnl!IoInitializeWorkItem` at `0x1403347bd`
- `ntoskrnl!IoInitializeWorkItem` at `0x1403347bd`
- `ntoskrnl!IoUninitializeWorkItem` at `0x140334825`
- `ntoskrnl!IoUninitializeWorkItem` at `0x140334825`
- `ntoskrnl!IoFreeWorkItem` at `0x14033484d`
- `ntoskrnl!IoFreeWorkItem` at `0x14033484d`
- `ntoskrnl!IofCallDriver` at `0x14033488e`
- `ntoskrnl!IofCallDriver` at `0x14033488e`
- `ntoskrnl!IoQueueWorkItemEx` at `0x1403345fd`
- `ntoskrnl!IoQueueWorkItemEx` at `0x1403345fd`
- `ntoskrnl!IoSetIoPriorityHint` at `0x140334739`
- `ntoskrnl!IoSetIoPriorityHint` at `0x140334739`
- `ntoskrnl!IoAllocateWorkItem` at `0x1403347cb`
- `ntoskrnl!IoAllocateWorkItem` at `0x1403347cb`
- `ntoskrnl!IoTryQueueWorkItem` at `0x140334802`
- `ntoskrnl!IoTryQueueWorkItem` at `0x140334802`

## pseudocode

```c
void __fastcall RefsMultipleAsync(
        struct _IRP_CONTEXT *a1,
        struct REFS_IO_CONTEXT *a2,
        struct _DEVICE_OBJECT *a3,
        struct _IRP *a4,
        unsigned int a5,
        struct _IRP **a6,
        struct CmsTransactionContext *a7)
{
  struct _DEVICE_OBJECT *v8; // r15
  struct REFS_IO_CONTEXT *v9; // rdi
  __int64 v11; // r13
  char v12; // r14
  unsigned int v13; // r9d
  struct _IRP **v14; // rsi
  __int64 v15; // rax
  unsigned int v16; // r12d
  __int64 v17; // rbx
  struct _IO_WORKITEM *v18; // rcx
  IRP *v19; // rbx
  unsigned int v20; // edx
  struct REFS_IO_CONTEXT *v21; // rcx
  CCHAR v22; // r11
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  LARGE_INTEGER ByteOffset; // rdi
  __int64 Length; // rsi
  __int32 v26; // eax
  unsigned int WorkItemIndexFromIoContext; // eax
  struct _LIST_ENTRY *v28; // rsi
  bool v29; // r15
  struct _DEVICE_OBJECT *v30; // rcx
  struct _IO_WORKITEM *WorkItem; // rdi
  char v32; // al
  __int64 v33; // [rsp+20h] [rbp-88h]
  __int64 v34; // [rsp+28h] [rbp-80h] BYREF
  __int64 v35; // [rsp+30h] [rbp-78h]
  __int64 v36; // [rsp+38h] [rbp-70h] BYREF
  __int64 v37; // [rsp+40h] [rbp-68h]
  _QWORD v38[11]; // [rsp+50h] [rbp-58h] BYREF

  v8 = a3;
  v9 = a2;
  v11 = 0;
  v34 = 0;
  v36 = 0;
  v12 = 0;
  v13 = a5;
  v14 = a6;
  if ( a6[1] == a4 )
    v13 = 0;
  RefsPreProcessIo(a1, a2, a4, v13);
  v15 = *((_QWORD *)a1 + 8);
  v35 = v15;
  v37 = *((_QWORD *)a1 + 1) & 0x100000000LL;
  v16 = 0;
  HIDWORD(v33) = 0;
  while ( v16 < a5 )
  {
    v17 = 4LL * v16;
    v18 = (struct _IO_WORKITEM *)v14[v17 + 2];
    if ( v18 )
    {
      if ( v14[1] == a4 || (*((_BYTE *)a1 + 8) & 1) != 0 )
        RefsDecompressWorker(0, v14[v17 + 3], (PIO_WORKITEM)v14[v17 + 2]);
      else
        IoQueueWorkItemEx(v18, RefsDecompressWorker, CriticalWorkQueue, v14[v17 + 3]);
    }
    else
    {
      v19 = v14[v17 + 1];
      if ( (unsigned __int8)MsIsVolumeOnSmr(*(_QWORD *)(v15 + 112)) )
      {
        CurrentStackLocation = v19->Tail.Overlay.CurrentStackLocation;
        if ( CurrentStackLocation[-1].MajorFunction == 4 )
        {
          ByteOffset = CurrentStackLocation[-1].Parameters.Read.ByteOffset;
          v38[2] = ByteOffset.QuadPart;
          Length = CurrentStackLocation[-1].Parameters.Read.Length;
          v38[3] = Length;
          v38[0] = ByteOffset.QuadPart;
          v38[1] = Length;
          v26 = MsAcquireContainerWriteHead(a7, v38, &v34, &v36, v33);
          if ( v26 < 0 )
          {
            v19->Tail.Overlay.CurrentStackLocation[-1].DeviceObject = v8;
            --v19->CurrentLocation;
            --v19->Tail.Overlay.CurrentStackLocation;
            _InterlockedExchange((volatile __int32 *)&v19->IoStatus.0, v26);
            IofCompleteRequest(v19, 1);
            v11 = v34;
            goto LABEL_41;
          }
          v11 = v34;
          v22 = 1;
          if ( v34 )
            v12 = 1;
          BYTE2(v33) = v12;
          if ( RefsEnableSMRSimulation
            && !(unsigned __int8)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))MsDebugSMRWrite)(
                                   *(_QWORD *)(v35 + 10712),
                                   Length,
                                   (LARGE_INTEGER)ByteOffset.QuadPart) )
          {
            v19->Tail.Overlay.CurrentStackLocation[-1].DeviceObject = v8;
            --v19->CurrentLocation;
            --v19->Tail.Overlay.CurrentStackLocation;
            _InterlockedExchange((volatile __int32 *)&v19->IoStatus.0, -1073740684);
            IofCompleteRequest(v19, v22);
            goto LABEL_41;
          }
          if ( v12 )
          {
            IoSetIoPriorityHint(v19, IoPriorityNormal);
            v22 = 1;
          }
          v20 = a5;
          v9 = a2;
        }
      }
      LOBYTE(v21) = v22;
      BYTE1(v33) = v22;
      if ( !RefsDisableAssociatedIrpAsyncPosting && !v12 && (v16 < v20 - 1 || *((_DWORD *)v9 + 21)) )
      {
        WorkItemIndexFromIoContext = GetWorkItemIndexFromIoContext(v9);
        v28 = (struct _LIST_ENTRY *)WorkItemIndexFromIoContext;
        v29 = 0;
        LOBYTE(v33) = 0;
        v30 = *(struct _DEVICE_OBJECT **)(v35 + 192);
        if ( WorkItemIndexFromIoContext >= 4 )
        {
          WorkItem = IoAllocateWorkItem(v30);
        }
        else
        {
          WorkItem = (struct REFS_IO_CONTEXT *)((char *)v9 + 112 * WorkItemIndexFromIoContext + 160);
          IoInitializeWorkItem(v30, WorkItem);
        }
        v19->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = (struct _LIST_ENTRY *)a1;
        v19->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Blink = v28;
        if ( WorkItem )
        {
          v32 = IoTryQueueWorkItem(WorkItem, RefsAsyncIoWorker, 0, v19, v33);
          v29 = v32 != 0;
          LOBYTE(v33) = v32 != 0;
          if ( !v32 )
          {
            if ( (unsigned int)v28 >= 4 )
            {
              IoFreeWorkItem(WorkItem);
            }
            else
            {
              IoUninitializeWorkItem(WorkItem);
              v21 = a2;
              _InterlockedAnd((volatile signed __int32 *)a2 + 152, ~(1 << (char)v28));
            }
          }
        }
        LOBYTE(v21) = !v29;
        BYTE1(v33) = !v29;
        v8 = a3;
      }
      if ( (_BYTE)v21 )
      {
        if ( v37 )
          IofCallDriver(v8, v19);
        else
          RefsCallStorageDriver(v8, v19, RefsReserveStackStorage, 0);
      }
      if ( v12 )
      {
        MsReleaseContainerWriteHead(v21, v11, v36);
        v12 = 0;
        BYTE2(v33) = 0;
      }
    }
LABEL_41:
    HIDWORD(v33) = ++v16;
    v9 = a2;
    v14 = a6;
    v15 = v35;
  }
}

```

## disassembly

```asm
0x140334528  mov     rax, rsp
0x14033452b  mov     [rax+20h], r9
0x14033452f  mov     [rax+18h], r8
0x140334533  mov     [rax+10h], rdx
0x140334537  mov     [rax+8], rcx
0x14033453b  push    rbx
0x14033453c  push    rsi
0x14033453d  push    rdi
0x14033453e  push    r12
0x140334540  push    r13
0x140334542  push    r14
0x140334544  push    r15
0x140334546  sub     rsp, 70h
0x14033454a  mov     r10, r9
0x14033454d  mov     r15, r8
0x140334550  mov     rdi, rdx
0x140334553  mov     rbx, rcx
0x140334556  xor     r13d, r13d
0x140334559  mov     [rax-80h], r13
0x14033455d  mov     [rax-70h], r13
0x140334561  xor     r14b, r14b
0x140334564  mov     r9d, [rsp+0A8h+arg_20]
0x14033456c  xor     eax, eax
0x14033456e  mov     rsi, [rsp+0A8h+arg_28]
0x140334576  cmp     [rsi+8], r10
0x14033457a  cmovz   r9d, eax; unsigned int
0x14033457e  mov     r8, r10; struct _IRP *
0x140334581  call    ?RefsPreProcessIo@@YAXPEAU_IRP_CONTEXT@@PEAUREFS_IO_CONTEXT@@PEAU_IRP@@K@Z; RefsPreProcessIo(_IRP_CONTEXT *,REFS_IO_CONTEXT *,_IRP *,ulong)
0x140334586  mov     rax, [rbx+40h]
0x14033458a  mov     [rsp+0A8h+var_78], rax
0x14033458f  mov     rcx, [rbx+8]
0x140334593  mov     rdx, 100000000h
0x14033459d  and     rcx, rdx
0x1403345a0  mov     [rsp+0A8h+var_68], rcx
0x1403345a5  xor     r12d, r12d
0x1403345a8  mov     [rsp+0A8h+var_84], r12d
0x1403345ad  lea     r11d, [r13+1]
0x1403345b1  mov     edx, [rsp+0A8h+arg_20]
0x1403345b8  cmp     r12d, edx
0x1403345bb  jnb     loc_1403348DC
0x1403345c1  mov     ebx, r12d
0x1403345c4  shl     rbx, 5
0x1403345c8  mov     rcx, [rbx+rsi+10h]; IoWorkItem
0x1403345cd  test    rcx, rcx
0x1403345d0  jz      short loc_140334622
0x1403345d2  mov     rax, [rsp+0A8h+arg_18]
0x1403345da  cmp     [rsi+8], rax
0x1403345de  jz      short loc_14033460E
0x1403345e0  mov     rax, [rsp+0A8h+arg_0]
0x1403345e8  test    [rax+8], r11b
0x1403345ec  jnz     short loc_14033460E
0x1403345ee  mov     r9, [rbx+rsi+18h]; Context
0x1403345f3  xor     r8d, r8d; QueueType
0x1403345f6  lea     rdx, ?RefsDecompressWorker@@YAXPEAX0PEAU_IO_WORKITEM@@@Z; WorkerRoutine
0x1403345fd  call    cs:__imp_IoQueueWorkItemEx
0x140334604  nop     dword ptr [rax+rax+00h]
0x140334609  jmp     loc_1403348B4
0x14033460e  mov     r8, rcx; IoWorkItem
0x140334611  mov     rdx, [rbx+rsi+18h]; Context
0x140334616  xor     ecx, ecx; IoObject
0x140334618  call    ?RefsDecompressWorker@@YAXPEAX0PEAU_IO_WORKITEM@@@Z; RefsDecompressWorker(void *,void *,_IO_WORKITEM *)
0x14033461d  jmp     loc_1403348B4
0x140334622  mov     rbx, [rbx+rsi+8]
0x140334627  mov     rcx, [rax+70h]
0x14033462b  call    MsIsVolumeOnSmr
0x140334630  test    al, al
0x140334632  jz      loc_14033475A
0x140334638  mov     rax, [rbx+0B8h]
0x14033463f  cmp     byte ptr [rax-48h], 4
0x140334643  jnz     loc_14033475A
0x140334649  mov     rdi, [rax-30h]
0x14033464d  mov     [rsp+0A8h+var_48], rdi
0x140334652  mov     esi, [rax-40h]
0x140334655  mov     [rsp+0A8h+var_40], rsi
0x14033465a  mov     [rsp+0A8h+var_58], rdi
0x14033465f  mov     [rsp+0A8h+var_50], rsi
0x140334664  lea     r9, [rsp+0A8h+var_70]
0x140334669  lea     r8, [rsp+0A8h+var_80]
0x14033466e  lea     rdx, [rsp+0A8h+var_58]
0x140334673  mov     rcx, [rsp+0A8h+arg_30]
0x14033467b  call    MsAcquireContainerWriteHead
0x140334680  test    eax, eax
0x140334682  jns     short loc_1403346B8
0x140334684  mov     rdx, [rbx+0B8h]
0x14033468b  mov     [rdx-20h], r15
0x14033468f  dec     byte ptr [rbx+43h]
0x140334692  add     qword ptr [rbx+0B8h], 0FFFFFFFFFFFFFFB8h
0x14033469a  xchg    eax, [rbx+30h]
0x14033469d  mov     dl, 1; PriorityBoost
0x14033469f  mov     rcx, rbx; Irp
0x1403346a2  call    cs:__imp_IofCompleteRequest
0x1403346a9  nop     dword ptr [rax+rax+00h]
0x1403346ae  mov     r13, [rsp+0A8h+var_80]
0x1403346b3  jmp     loc_1403348B4
0x1403346b8  movzx   r14d, r14b
0x1403346bc  mov     r13, [rsp+0A8h+var_80]
0x1403346c1  test    r13, r13
0x1403346c4  mov     r11d, 1
0x1403346ca  cmovnz  r14d, r11d
0x1403346ce  mov     [rsp+0A8h+var_86], r14b
0x1403346d3  cmp     cs:?RefsEnableSMRSimulation@@3EA, 0; uchar RefsEnableSMRSimulation
0x1403346da  jz      short loc_14033472C
0x1403346dc  mov     r8, rdi
0x1403346df  mov     rdx, rsi
0x1403346e2  mov     rcx, [rsp+0A8h+var_78]
0x1403346e7  mov     rcx, [rcx+29D8h]
0x1403346ee  call    MsDebugSMRWrite
0x1403346f3  test    al, al
0x1403346f5  jnz     short loc_14033472C
0x1403346f7  mov     rax, [rbx+0B8h]
0x1403346fe  mov     [rax-20h], r15
0x140334702  dec     byte ptr [rbx+43h]
0x140334705  add     qword ptr [rbx+0B8h], 0FFFFFFFFFFFFFFB8h
0x14033470d  mov     eax, 0C0000474h
0x140334712  xchg    eax, [rbx+30h]
0x140334715  mov     dl, r11b; PriorityBoost
0x140334718  mov     rcx, rbx; Irp
0x14033471b  call    cs:__imp_IofCompleteRequest
0x140334722  nop     dword ptr [rax+rax+00h]
0x140334727  jmp     loc_1403348B4
0x14033472c  test    r14b, r14b
0x14033472f  jz      short loc_14033474B
0x140334731  mov     edx, 2; PriorityHint
0x140334736  mov     rcx, rbx; Irp
0x140334739  call    cs:__imp_IoSetIoPriorityHint
0x140334740  nop     dword ptr [rax+rax+00h]
0x140334745  mov     r11d, 1
0x14033474b  mov     edx, [rsp+0A8h+arg_20]
0x140334752  mov     rdi, [rsp+0A8h+arg_8]
0x14033475a  mov     cl, r11b
0x14033475d  mov     [rsp+0A8h+var_87], cl
0x140334761  cmp     cs:?RefsDisableAssociatedIrpAsyncPosting@@3EA, 0; uchar RefsDisableAssociatedIrpAsyncPosting
0x140334768  jnz     loc_14033486B
0x14033476e  test    r14b, r14b
0x140334771  jnz     loc_14033486B
0x140334777  lea     eax, [rdx-1]
0x14033477a  cmp     r12d, eax
0x14033477d  jb      short loc_140334789
0x14033477f  cmp     dword ptr [rdi+54h], 0
0x140334783  jz      loc_14033486B
0x140334789  mov     rcx, rdi; struct REFS_IO_CONTEXT *
0x14033478c  call    ?GetWorkItemIndexFromIoContext@@YAKPEAUREFS_IO_CONTEXT@@@Z; GetWorkItemIndexFromIoContext(REFS_IO_CONTEXT *)
0x140334791  mov     esi, eax
0x140334793  xor     r15b, r15b
0x140334796  mov     [rsp+0A8h+var_88], r15b
0x14033479b  mov     rax, [rsp+0A8h+var_78]
0x1403347a0  mov     rcx, [rax+0C0h]; DeviceObject
0x1403347a7  cmp     esi, 4
0x1403347aa  jnb     short loc_1403347CB
0x1403347ac  imul    r8d, esi, 70h ; 'p'
0x1403347b0  add     r8, 0A0h
0x1403347b7  add     rdi, r8
0x1403347ba  mov     rdx, rdi; IoWorkItem
0x1403347bd  call    cs:__imp_IoInitializeWorkItem
0x1403347c4  nop     dword ptr [rax+rax+00h]
0x1403347c9  jmp     short loc_1403347DA
0x1403347cb  call    cs:__imp_IoAllocateWorkItem
0x1403347d2  nop     dword ptr [rax+rax+00h]
0x1403347d7  mov     rdi, rax
0x1403347da  mov     rax, [rsp+0A8h+arg_0]
0x1403347e2  mov     [rbx+78h], rax
0x1403347e6  mov     [rbx+80h], rsi
0x1403347ed  test    rdi, rdi
0x1403347f0  jz      short loc_140334859
0x1403347f2  mov     r9, rbx
0x1403347f5  xor     r8d, r8d
0x1403347f8  lea     rdx, ?RefsAsyncIoWorker@@YAXPEAX0PEAU_IO_WORKITEM@@@Z; RefsAsyncIoWorker(void *,void *,_IO_WORKITEM *)
0x1403347ff  mov     rcx, rdi
0x140334802  call    cs:__imp_IoTryQueueWorkItem
0x140334809  nop     dword ptr [rax+rax+00h]
0x14033480e  test    al, al
0x140334810  setnz   r15b
0x140334814  mov     [rsp+0A8h+var_88], r15b
0x140334819  test    al, al
0x14033481b  jnz     short loc_140334859
0x14033481d  mov     rcx, rdi; IoWorkItem
0x140334820  cmp     esi, 4
0x140334823  jnb     short loc_14033484D
0x140334825  call    cs:__imp_IoUninitializeWorkItem
0x14033482c  nop     dword ptr [rax+rax+00h]
0x140334831  mov     ecx, esi
0x140334833  mov     eax, 1
0x140334838  shl     eax, cl
0x14033483a  not     eax
0x14033483c  mov     rcx, [rsp+0A8h+arg_8]
0x140334844  lock and [rcx+260h], eax
0x14033484b  jmp     short loc_140334859
0x14033484d  call    cs:__imp_IoFreeWorkItem
0x140334854  nop     dword ptr [rax+rax+00h]
0x140334859  test    r15b, r15b
0x14033485c  setz    cl
0x14033485f  mov     [rsp+0A8h+var_87], cl
0x140334863  mov     r15, [rsp+0A8h+arg_10]
0x14033486b  test    cl, cl
0x14033486d  jz      short loc_14033489A
0x14033486f  mov     rdx, rbx; Irp
0x140334872  mov     rcx, r15; DeviceObject
0x140334875  cmp     [rsp+0A8h+var_68], 0
0x14033487b  jnz     short loc_14033488E
0x14033487d  xor     r9d, r9d; int *
0x140334880  mov     r8, cs:?RefsReserveStackStorage@@3PEAXEA; Context
0x140334887  call    ?RefsCallStorageDriver@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAXPEAJ@Z; RefsCallStorageDriver(_DEVICE_OBJECT *,_IRP *,void *,long *)
0x14033488c  jmp     short loc_14033489A
0x14033488e  call    cs:__imp_IofCallDriver
0x140334895  nop     dword ptr [rax+rax+00h]
0x14033489a  test    r14b, r14b
0x14033489d  jz      short loc_1403348B4
0x14033489f  mov     r8, [rsp+0A8h+var_70]
0x1403348a4  mov     rdx, r13
0x1403348a7  call    MsReleaseContainerWriteHead
0x1403348ac  xor     r14b, r14b
0x1403348af  mov     [rsp+0A8h+var_86], r14b
0x1403348b4  mov     r11d, 1
0x1403348ba  add     r12d, r11d
0x1403348bd  mov     [rsp+0A8h+var_84], r12d
0x1403348c2  mov     rdi, [rsp+0A8h+arg_8]
0x1403348ca  mov     rsi, [rsp+0A8h+arg_28]
0x1403348d2  mov     rax, [rsp+0A8h+var_78]
0x1403348d7  jmp     loc_1403345B1
0x1403348dc  add     rsp, 70h
0x1403348e0  pop     r15
0x1403348e2  pop     r14
0x1403348e4  pop     r13
0x1403348e6  pop     r12
0x1403348e8  pop     rdi
0x1403348e9  pop     rsi
0x1403348ea  pop     rbx
0x1403348eb  retn
0x14034485d  push    rbp
0x14034485f  sub     rsp, 20h
0x140344863  mov     rbp, rdx
0x140344866  add     rsp, 20h
0x14034486a  pop     rbp
0x14034486b  retn
```
