# NsippChangeNotificationCallback

- ea: `0x140005060`
- end: `0x14000528f`
- name: `NsippChangeNotificationCallback`
- size: `559`
- prototype: `void __fastcall(PVOID *Context)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140005060`

## import_xrefs

- `ntoskrnl!IoQueueWorkItem` at `0x14000515a`
- `ntoskrnl!IoQueueWorkItem` at `0x14000515a`
- `ntoskrnl!IofCompleteRequest` at `0x14000527a`
- `ntoskrnl!IofCompleteRequest` at `0x14000527a`
- `ntoskrnl!IoAllocateWorkItem` at `0x140005198`
- `ntoskrnl!IoAllocateWorkItem` at `0x140005198`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14000512d`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140005230`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x14000512d`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140005230`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000511c`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400051d5`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400051e8`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000511c`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400051d5`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400051e8`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000508e`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400050c3`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000508e`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400050c3`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14000507b`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14000507b`

## pseudocode

```c
void __fastcall NsippChangeNotificationCallback(PVOID *Context)
{
  PVOID *v2; // rax
  char v3; // si
  char *v4; // rdx
  PIO_WORKITEM WorkItem; // rax
  KSPIN_LOCK v6; // rdx
  PVOID *v7; // rax
  __int128 *i; // rax
  __int64 v9; // rcx
  __int64 v10; // rax
  __int128 v11; // [rsp+20h] [rbp-18h] BYREF
  KIRQL Irql; // [rsp+40h] [rbp+8h] BYREF

  Irql = 0;
  v11 = 0;
  IoAcquireCancelSpinLock(&Irql);
  KeAcquireSpinLockAtDpcLevel(&NsippNotificationHandleListLock);
  v2 = (PVOID *)NsippNotificationHandleList;
  if ( NsippNotificationHandleList == &NsippNotificationHandleList )
  {
LABEL_6:
    KeReleaseSpinLockFromDpcLevel(&NsippNotificationHandleListLock);
    IoReleaseCancelSpinLock(Irql);
  }
  else
  {
    while ( Context != v2 )
    {
      v2 = (PVOID *)*v2;
      if ( v2 == &NsippNotificationHandleList )
        goto LABEL_6;
    }
    v3 = 0;
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)Context + 11);
    v4 = (char *)Context[12];
    if ( v4 == (char *)(Context + 12) )
    {
      *((_QWORD *)&v11 + 1) = &v11;
      *(_QWORD *)&v11 = &v11;
    }
    else
    {
      *((_QWORD *)&v11 + 1) = Context[13];
      *(_QWORD *)&v11 = v4;
      *((_QWORD *)v4 + 1) = &v11;
      **((_QWORD **)&v11 + 1) = &v11;
      Context[13] = Context + 12;
      Context[12] = Context + 12;
    }
    if ( !*((_DWORD *)Context + 4) )
    {
      WorkItem = IoAllocateWorkItem(NsiProxyDeviceObject);
      if ( WorkItem )
      {
        Context[14] = WorkItem;
        v6 = (KSPIN_LOCK)*Context;
        if ( *((PVOID **)*Context + 1) != Context || (v7 = (PVOID *)Context[1], *v7 != Context) )
LABEL_23:
          __fastfail(3u);
        *v7 = (PVOID)v6;
        v3 = 1;
        *(_QWORD *)(v6 + 8) = v7;
      }
    }
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)Context + 11);
    KeReleaseSpinLockFromDpcLevel(&NsippNotificationHandleListLock);
    for ( i = (__int128 *)v11; i != &v11; i = *(__int128 **)i )
    {
      *((_DWORD *)i - 30) = 0;
      *((_QWORD *)i - 14) = 0;
      _InterlockedExchange64((volatile __int64 *)i - 8, 0);
    }
    IoReleaseCancelSpinLock(Irql);
    while ( 1 )
    {
      v9 = v11;
      if ( (__int128 *)v11 == &v11 )
        break;
      if ( *(__int128 **)(v11 + 8) != &v11 )
        goto LABEL_23;
      v10 = *(_QWORD *)v11;
      if ( *(_QWORD *)(*(_QWORD *)v11 + 8LL) != (_QWORD)v11 )
        goto LABEL_23;
      *(_QWORD *)&v11 = *(_QWORD *)v11;
      *(_QWORD *)(v10 + 8) = &v11;
      IofCompleteRequest((PIRP)(v9 - 168), 0);
    }
    if ( v3 == 1 )
      IoQueueWorkItem((PIO_WORKITEM)Context[14], NsippDeregisterWorker, DelayedWorkQueue, Context);
  }
}

```

## disassembly

```asm
0x140005060  push    rbx
0x140005062  sub     rsp, 30h
0x140005066  mov     rbx, rcx
0x140005069  mov     [rsp+38h+Irql], 0
0x14000506e  xorps   xmm0, xmm0
0x140005071  lea     rcx, [rsp+38h+Irql]; Irql
0x140005076  movups  [rsp+38h+var_18], xmm0
0x14000507b  call    cs:__imp_IoAcquireCancelSpinLock
0x140005082  nop     dword ptr [rax+rax+00h]
0x140005087  lea     rcx, NsippNotificationHandleListLock; SpinLock
0x14000508e  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140005095  nop     dword ptr [rax+rax+00h]
0x14000509a  mov     rax, cs:NsippNotificationHandleList
0x1400050a1  lea     rcx, NsippNotificationHandleList
0x1400050a8  cmp     rax, rcx
0x1400050ab  jz      short loc_140005115
0x1400050ad  cmp     rbx, rax
0x1400050b0  jnz     short loc_14000510D
0x1400050b2  mov     [rsp+38h+arg_8], rsi
0x1400050b7  lea     rcx, [rbx+58h]; SpinLock
0x1400050bb  mov     [rsp+38h+arg_10], rdi
0x1400050c0  xor     sil, sil
0x1400050c3  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400050ca  nop     dword ptr [rax+rax+00h]
0x1400050cf  mov     rdx, [rbx+60h]
0x1400050d3  lea     rcx, [rbx+60h]
0x1400050d7  cmp     rdx, rcx
0x1400050da  jz      loc_140005177
0x1400050e0  mov     rax, [rcx+8]
0x1400050e4  mov     qword ptr [rsp+38h+var_18+8], rax
0x1400050e9  lea     rax, [rsp+38h+var_18]
0x1400050ee  mov     qword ptr [rsp+38h+var_18], rdx
0x1400050f3  mov     [rdx+8], rax
0x1400050f7  lea     rdx, [rsp+38h+var_18]
0x1400050fc  mov     rax, qword ptr [rsp+38h+var_18+8]
0x140005101  mov     [rax], rdx
0x140005104  mov     [rcx+8], rcx
0x140005108  mov     [rcx], rcx
0x14000510b  jmp     short loc_14000518B
0x14000510d  mov     rax, [rax]
0x140005110  cmp     rax, rcx
0x140005113  jnz     short loc_1400050AD
0x140005115  lea     rcx, NsippNotificationHandleListLock; SpinLock
0x14000511c  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140005123  nop     dword ptr [rax+rax+00h]
0x140005128  movzx   ecx, [rsp+38h+Irql]; Irql
0x14000512d  call    cs:__imp_IoReleaseCancelSpinLock
0x140005134  nop     dword ptr [rax+rax+00h]
0x140005139  add     rsp, 30h
0x14000513d  pop     rbx
0x14000513e  retn
0x140005140  cmp     sil, 1
0x140005144  jnz     short loc_140005166
0x140005146  mov     rcx, [rbx+70h]; IoWorkItem
0x14000514a  lea     rdx, NsippDeregisterWorker; WorkerRoutine
0x140005151  mov     r9, rbx; Context
0x140005154  mov     r8d, 1; QueueType
0x14000515a  call    cs:__imp_IoQueueWorkItem
0x140005161  nop     dword ptr [rax+rax+00h]
0x140005166  mov     rsi, [rsp+38h+arg_8]
0x14000516b  mov     rdi, [rsp+38h+arg_10]
0x140005170  add     rsp, 30h
0x140005174  pop     rbx
0x140005175  retn
0x140005177  lea     rax, [rsp+38h+var_18]
0x14000517c  mov     qword ptr [rsp+38h+var_18+8], rax
0x140005181  lea     rax, [rsp+38h+var_18]
0x140005186  mov     qword ptr [rsp+38h+var_18], rax
0x14000518b  cmp     dword ptr [rbx+10h], 0
0x14000518f  jnz     short loc_1400051D1
0x140005191  mov     rcx, cs:NsiProxyDeviceObject; DeviceObject
0x140005198  call    cs:__imp_IoAllocateWorkItem
0x14000519f  nop     dword ptr [rax+rax+00h]
0x1400051a4  test    rax, rax
0x1400051a7  jz      short loc_1400051D1
0x1400051a9  mov     [rbx+70h], rax
0x1400051ad  mov     rdx, [rbx]
0x1400051b0  cmp     [rdx+8], rbx
0x1400051b4  jnz     loc_140005288
0x1400051ba  mov     rax, [rbx+8]
0x1400051be  cmp     [rax], rbx
0x1400051c1  jnz     loc_140005288
0x1400051c7  mov     [rax], rdx
0x1400051ca  mov     sil, 1
0x1400051cd  mov     [rdx+8], rax
0x1400051d1  lea     rcx, [rbx+58h]; SpinLock
0x1400051d5  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400051dc  nop     dword ptr [rax+rax+00h]
0x1400051e1  lea     rcx, NsippNotificationHandleListLock; SpinLock
0x1400051e8  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400051ef  nop     dword ptr [rax+rax+00h]
0x1400051f4  mov     rax, qword ptr [rsp+38h+var_18]
0x1400051f9  lea     rcx, [rsp+38h+var_18]
0x1400051fe  cmp     rax, rcx
0x140005201  jz      short loc_14000522B
0x140005203  xor     edx, edx
0x140005205  nop     word ptr [rax+rax+00000000h]
0x140005210  mov     [rax-78h], edx
0x140005213  mov     rcx, rdx
0x140005216  mov     [rax-70h], rdx
0x14000521a  xchg    rcx, [rax-40h]
0x14000521e  mov     rax, [rax]
0x140005221  lea     rcx, [rsp+38h+var_18]
0x140005226  cmp     rax, rcx
0x140005229  jnz     short loc_140005210
0x14000522b  movzx   ecx, [rsp+38h+Irql]; Irql
0x140005230  call    cs:__imp_IoReleaseCancelSpinLock
0x140005237  nop     dword ptr [rax+rax+00h]
0x14000523c  mov     rcx, qword ptr [rsp+38h+var_18]
0x140005241  lea     rax, [rsp+38h+var_18]
0x140005246  cmp     rcx, rax
0x140005249  jz      loc_140005140
0x14000524f  lea     rax, [rsp+38h+var_18]
0x140005254  cmp     [rcx+8], rax
0x140005258  jnz     short loc_140005288
0x14000525a  mov     rax, [rcx]
0x14000525d  cmp     [rax+8], rcx
0x140005261  jnz     short loc_140005288
0x140005263  lea     rdx, [rsp+38h+var_18]
0x140005268  mov     qword ptr [rsp+38h+var_18], rax
0x14000526d  mov     [rax+8], rdx
0x140005271  add     rcx, 0FFFFFFFFFFFFFF58h; Irp
0x140005278  xor     edx, edx; PriorityBoost
0x14000527a  call    cs:__imp_IofCompleteRequest
0x140005281  nop     dword ptr [rax+rax+00h]
0x140005286  jmp     short loc_14000523C
0x140005288  mov     ecx, 3
0x14000528d  int     29h; Win8: RtlFailFast(ecx)
```
