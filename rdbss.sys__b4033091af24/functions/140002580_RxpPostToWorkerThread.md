# RxpPostToWorkerThread

- ea: `0x140002580`
- end: `0x1400027a0`
- name: `RxpPostToWorkerThread`
- size: `544`
- prototype: `__int64 __usercall@<rax>(PVOID Object@<rcx>, __int64, char)`
- caller_count: `4`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400012d0`
- `0x140001fe0`
- `0x140002120`
- `0x140002170`

## callees

- `0x140002580`
- `0x140017370`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x1400025d3`
- `ntoskrnl!ObfReferenceObject` at `0x1400025d3`
- `ntoskrnl!KfRaiseIrql` at `0x140002626`
- `ntoskrnl!KfRaiseIrql` at `0x140002626`
- `ntoskrnl!KeLowerIrql` at `0x1400026bb`
- `ntoskrnl!KeLowerIrql` at `0x1400026bb`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140002748`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140002748`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140002713`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140002713`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14000259d`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14000259d`
- `ntoskrnl!ExQueueWorkItem` at `0x1400026ab`
- `ntoskrnl!ExQueueWorkItem` at `0x1400026ab`

## pseudocode

```c
__int64 __fastcall RxpPostToWorkerThread(PVOID Object, int a2, __int64 a3, __int64 a4, __int64 a5, char a6)
{
  __int64 v7; // r12
  USHORT CurrentNodeNumber; // ax
  char *v11; // rbx
  USHORT v12; // bp
  __int64 v13; // rdi
  KIRQL v14; // al
  int v15; // r8d
  KIRQL v16; // bp
  __int64 v17; // rcx
  __int64 v18; // rdx
  PDEVICE_OBJECT v19; // rcx
  __int64 v21; // rdx
  char *v22; // rax
  char **v23; // rcx
  PDEVICE_OBJECT v24; // rcx
  __int64 v25; // rdx

  v7 = a2;
  CurrentNodeNumber = KeGetCurrentNodeNumber();
  v11 = (char *)P;
  v12 = CurrentNodeNumber;
  v13 = (v7 + 6LL * (CurrentNodeNumber % (unsigned int)RxGlobalDispatcher)) << 6;
  ObfReferenceObject(Object);
  *(_QWORD *)(a3 + 48) = a5;
  *(_QWORD *)(a3 + 32) = Object;
  *(_QWORD *)(a3 + 16) = RxpProcessWorkItem;
  *(_BYTE *)(a3 + 56) = v7;
  *(_BYTE *)(a3 + 57) = a6;
  *(_WORD *)(a3 + 58) = v12;
  *(_QWORD *)(a3 + 40) = a4;
  *(_QWORD *)(a3 + 24) = a3;
  *(_QWORD *)a3 = 0;
  _InterlockedIncrement64((volatile signed __int64 *)&v11[v13 + 16]);
  v14 = KfRaiseIrql(2u);
  v15 = *(_DWORD *)&v11[v13 + 56];
  v16 = v14;
  _m_prefetchw(&v11[v13 + 32]);
  do
  {
    v17 = *(_QWORD *)&v11[v13 + 32];
    v18 = 0x100000001LL;
    if ( (int)v17 < v15 )
      v18 = 1;
  }
  while ( _InterlockedCompareExchange64((volatile signed __int64 *)&v11[v13 + 32], v17 + v18, *(_QWORD *)&v11[v13 + 32]) != v17 );
  if ( (int)v17 < v15 )
  {
    if ( a6 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        goto LABEL_9;
      }
      v21 = 14;
    }
    else
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        goto LABEL_9;
      }
      v21 = 15;
    }
    WPP_SF_qD(v19->AttachedDevice, v21, WPP_91b9b20a3d1f3beba865abbaf8105594_Traceguids, a3, v7);
LABEL_9:
    ExQueueWorkItem((PWORK_QUEUE_ITEM)a3, *((WORK_QUEUE_TYPE *)RxWorkQueueTypeMap + v7));
    goto LABEL_10;
  }
  if ( a6 )
  {
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      goto LABEL_15;
    }
    v25 = 12;
  }
  else
  {
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      goto LABEL_15;
    }
    v25 = 13;
  }
  WPP_SF_qD(v24->AttachedDevice, v25, WPP_91b9b20a3d1f3beba865abbaf8105594_Traceguids, a3, v7);
LABEL_15:
  _InterlockedIncrement64((volatile signed __int64 *)&v11[v13 + 24]);
  KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)&v11[v13 + 8]);
  v22 = &v11[v13 + 40];
  v23 = (char **)*((_QWORD *)v22 + 1);
  if ( *v23 != v22 )
    __fastfail(3u);
  *(_QWORD *)(a3 + 8) = v23;
  *(_QWORD *)a3 = v22;
  *v23 = (char *)a3;
  *((_QWORD *)v22 + 1) = a3;
  KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)&v11[v13 + 8]);
LABEL_10:
  KeLowerIrql(v16);
  return 0;
}

```

## disassembly

```asm
0x140002580  push    rbx
0x140002582  push    rbp
0x140002583  push    rsi
0x140002584  push    rdi
0x140002585  push    r12
0x140002587  push    r13
0x140002589  push    r14
0x14000258b  push    r15
0x14000258d  sub     rsp, 38h
0x140002591  mov     r14, r9
0x140002594  movsxd  r12, edx
0x140002597  mov     r15, r8
0x14000259a  mov     rsi, rcx
0x14000259d  call    cs:__imp_KeGetCurrentNodeNumber
0x1400025a4  nop     dword ptr [rax+rax+00h]
0x1400025a9  mov     rbx, cs:P
0x1400025b0  xor     edx, edx
0x1400025b2  movzx   ebp, ax
0x1400025b5  mov     rcx, rsi; Object
0x1400025b8  mov     eax, ebp
0x1400025ba  div     cs:RxGlobalDispatcher
0x1400025c0  lea     r11, [rdx+rdx*2]
0x1400025c4  lea     rdi, ds:0[r11*2]
0x1400025cc  add     rdi, r12
0x1400025cf  shl     rdi, 6
0x1400025d3  call    cs:__imp_ObfReferenceObject
0x1400025da  nop     dword ptr [rax+rax+00h]
0x1400025df  mov     rax, [rsp+78h+arg_20]
0x1400025e7  mov     [r15+30h], rax
0x1400025eb  lea     rax, RxpProcessWorkItem
0x1400025f2  mov     [r15+20h], rsi
0x1400025f6  movzx   esi, [rsp+78h+arg_28]
0x1400025fe  mov     [r15+10h], rax
0x140002602  mov     [r15+38h], r12b
0x140002606  mov     [r15+39h], sil
0x14000260a  mov     [r15+3Ah], bp
0x14000260f  mov     [r15+28h], r14
0x140002613  mov     [r15+18h], r15
0x140002617  mov     qword ptr [r15], 0
0x14000261e  lock inc qword ptr [rdi+rbx+10h]
0x140002624  mov     cl, 2; NewIrql
0x140002626  call    cs:__imp_KfRaiseIrql
0x14000262d  nop     dword ptr [rax+rax+00h]
0x140002632  mov     r8d, [rdi+rbx+38h]
0x140002637  movzx   ebp, al
0x14000263a  prefetchw byte ptr [rdi+rbx+20h]
0x14000263f  mov     r9, 100000001h
0x140002649  mov     r10d, 1
0x14000264f  nop
0x140002650  mov     rcx, [rdi+rbx+20h]
0x140002655  mov     rdx, r9
0x140002658  cmp     ecx, r8d
0x14000265b  mov     rax, rcx
0x14000265e  cmovl   rdx, r10
0x140002662  add     rdx, rcx
0x140002665  lock cmpxchg [rdi+rbx+20h], rdx
0x14000266c  cmp     rax, rcx
0x14000266f  jnz     short loc_140002650
0x140002671  cmp     ecx, r8d
0x140002674  jge     loc_140002759
0x14000267a  test    sil, sil
0x14000267d  jnz     short loc_1400026DB
0x14000267f  mov     rcx, cs:WPP_GLOBAL_Control
0x140002686  lea     rax, WPP_GLOBAL_Control
0x14000268d  cmp     rcx, rax
0x140002690  jz      short loc_14000269D
0x140002692  mov     eax, [rcx+2Ch]
0x140002695  test    al, 2
0x140002697  jnz     loc_14000278C
0x14000269d  lea     rdx, RxWorkQueueTypeMap
0x1400026a4  mov     rcx, r15; WorkItem
0x1400026a7  mov     edx, [rdx+r12*4]; QueueType
0x1400026ab  call    cs:__imp_ExQueueWorkItem
0x1400026b2  nop     dword ptr [rax+rax+00h]
0x1400026b7  movzx   ecx, bpl; NewIrql
0x1400026bb  call    cs:__imp_KeLowerIrql
0x1400026c2  nop     dword ptr [rax+rax+00h]
0x1400026c7  xor     eax, eax
0x1400026c9  add     rsp, 38h
0x1400026cd  pop     r15
0x1400026cf  pop     r14
0x1400026d1  pop     r13
0x1400026d3  pop     r12
0x1400026d5  pop     rdi
0x1400026d6  pop     rsi
0x1400026d7  pop     rbp
0x1400026d8  pop     rbx
0x1400026d9  retn
0x1400026db  mov     rcx, cs:WPP_GLOBAL_Control
0x1400026e2  lea     rax, WPP_GLOBAL_Control
0x1400026e9  cmp     rcx, rax
0x1400026ec  jz      short loc_14000269D
0x1400026ee  mov     eax, [rcx+2Ch]
0x1400026f1  test    al, 2
0x1400026f3  jz      short loc_14000269D
0x1400026f5  cmp     byte ptr [rcx+29h], 4
0x1400026f9  jb      short loc_14000269D
0x1400026fb  mov     edx, 0Eh
0x140002700  jmp     loc_140026DDD
0x140002705  lock inc qword ptr [rdi+rbx+18h]
0x14000270b  lea     rsi, [rdi+rbx]
0x14000270f  lea     rcx, [rsi+8]; SpinLock
0x140002713  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14000271a  nop     dword ptr [rax+rax+00h]
0x14000271f  lea     rax, [rbx+28h]
0x140002723  add     rax, rdi
0x140002726  mov     rcx, [rax+8]
0x14000272a  cmp     [rcx], rax
0x14000272d  jz      short loc_140002736
0x14000272f  mov     ecx, 3
0x140002734  int     29h; Win8: RtlFailFast(ecx)
0x140002736  mov     [r15+8], rcx
0x14000273a  mov     [r15], rax
0x14000273d  mov     [rcx], r15
0x140002740  lea     rcx, [rsi+8]; SpinLock
0x140002744  mov     [rax+8], r15
0x140002748  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000274f  nop     dword ptr [rax+rax+00h]
0x140002754  jmp     loc_1400026B7
0x140002759  test    sil, sil
0x14000275c  jz      loc_140026D8E
0x140002762  mov     rcx, cs:WPP_GLOBAL_Control
0x140002769  lea     rax, WPP_GLOBAL_Control
0x140002770  cmp     rcx, rax
0x140002773  jz      short loc_140002705
0x140002775  mov     eax, [rcx+2Ch]
0x140002778  test    al, 2
0x14000277a  jz      short loc_140002705
0x14000277c  cmp     byte ptr [rcx+29h], 4
0x140002780  jb      short loc_140002705
0x140002782  mov     edx, 0Ch
0x140002787  jmp     loc_140026DBF
0x14000278c  cmp     byte ptr [rcx+29h], 4
0x140002790  jb      loc_14000269D
0x140002796  mov     edx, 0Fh
0x14000279b  jmp     loc_140026DDD
0x140026d8e  mov     rcx, cs:WPP_GLOBAL_Control
0x140026d95  lea     rax, WPP_GLOBAL_Control
0x140026d9c  cmp     rcx, rax
0x140026d9f  jz      loc_140002705
0x140026da5  mov     eax, [rcx+2Ch]
0x140026da8  test    al, 2
0x140026daa  jz      loc_140002705
0x140026db0  cmp     byte ptr [rcx+29h], 4
0x140026db4  jb      loc_140002705
0x140026dba  mov     edx, 0Dh
0x140026dbf  mov     rcx, [rcx+18h]
0x140026dc3  lea     r8, WPP_91b9b20a3d1f3beba865abbaf8105594_Traceguids
0x140026dca  mov     r9, r15
0x140026dcd  mov     [rsp+78h+var_58], r12d
0x140026dd2  call    WPP_SF_qD
0x140026dd7  nop
0x140026dd8  jmp     loc_140002705
0x140026ddd  mov     rcx, [rcx+18h]
0x140026de1  lea     r8, WPP_91b9b20a3d1f3beba865abbaf8105594_Traceguids
0x140026de8  mov     r9, r15
0x140026deb  mov     [rsp+78h+var_58], r12d
0x140026df0  call    WPP_SF_qD
0x140026df5  nop
0x140026df6  jmp     loc_14000269D
```
