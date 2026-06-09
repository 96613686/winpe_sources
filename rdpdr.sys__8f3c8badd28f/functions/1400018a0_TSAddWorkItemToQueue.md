# TSAddWorkItemToQueue

- ea: `0x1400018a0`
- end: `0x140001bd6`
- name: `TSAddWorkItemToQueue`
- size: `822`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14001b608`
- `0x140023cf0`
- `0x140024830`
- `0x140025000`
- `0x14002a9c0`

## callees

- `0x1400018a0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400018dc`
- `ntoskrnl!ExAllocatePool2` at `0x140001af1`
- `ntoskrnl!ExAllocatePool2` at `0x1400018dc`
- `ntoskrnl!ExAllocatePool2` at `0x140001af1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001934`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001b23`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001b7b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001934`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001b23`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001b7b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001906`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001ab1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001b38`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001906`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001ab1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001b38`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001923`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000199a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001a04`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001ac9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001b94`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001923`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000199a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001a04`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001ac9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001b94`
- `ntoskrnl!PsCreateSystemThread` at `0x140001a97`
- `ntoskrnl!PsCreateSystemThread` at `0x140001a97`
- `ntoskrnl!KeSetEvent` at `0x14000197e`
- `ntoskrnl!KeSetEvent` at `0x14000197e`
- `ntoskrnl!IoQueueWorkItem` at `0x140001bbe`
- `ntoskrnl!IoQueueWorkItem` at `0x140001bbe`
- `ntoskrnl!KeGetCurrentIrql` at `0x140001a1b`
- `ntoskrnl!KeGetCurrentIrql` at `0x140001a1b`
- `ntoskrnl!IoAllocateWorkItem` at `0x140001b09`
- `ntoskrnl!IoAllocateWorkItem` at `0x140001b09`

## pseudocode

```c
__int64 __fastcall TSAddWorkItemToQueue(__int64 a1, __int64 a2, __int64 a3)
{
  _QWORD *StartContext; // rbx
  __int64 Pool2; // rax
  _QWORD *v8; // rdi
  KIRQL v9; // al
  KIRQL v10; // bp
  _QWORD *v11; // rax
  unsigned int v12; // eax
  __int64 i; // r14
  unsigned int v14; // ebp
  KIRQL v15; // al
  WORK_QUEUE_TYPE v16; // ebp
  _QWORD *v17; // r14
  struct _IO_WORKITEM *WorkItem; // rax
  KIRQL v19; // al
  KIRQL v20; // r14
  _QWORD *j; // rcx
  __int64 v22; // rcx
  _QWORD *v23; // rax
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-48h] BYREF

  StartContext = *(_QWORD **)&WPP_MAIN_CB.AlignmentRequirement;
  if ( !*(_QWORD *)&WPP_MAIN_CB.AlignmentRequirement )
    return 3221225485LL;
  Pool2 = ExAllocatePool2(64, 32, 544297812);
  v8 = (_QWORD *)Pool2;
  if ( !Pool2 )
    return 3221225495LL;
  *(_QWORD *)(Pool2 + 24) = a2;
  *(_QWORD *)(Pool2 + 16) = a3;
  v9 = KeAcquireSpinLockRaiseToDpc(StartContext + 14);
  v10 = v9;
  if ( (*((_DWORD *)StartContext + 4) & 0x80u) != 0 )
  {
    KeReleaseSpinLock(StartContext + 14, v9);
    ExFreePoolWithTag(v8, 0);
    return 3221225506LL;
  }
  v11 = (_QWORD *)StartContext[1];
  if ( (_QWORD *)*v11 != StartContext )
    goto LABEL_38;
  *v8 = StartContext;
  v8[1] = v11;
  *v11 = v8;
  StartContext[1] = v8;
  KeSetEvent((PRKEVENT)(StartContext + 16), 0, 0);
  v12 = *((_DWORD *)StartContext + 6);
  if ( v12 >= *((_DWORD *)StartContext + 5) )
  {
    KeReleaseSpinLock(StartContext + 14, v10);
    return 0;
  }
  i = 0;
  *((_DWORD *)StartContext + 6) = v12 + 1;
  if ( (StartContext[2] & 1) != 0 )
  {
    for ( i = 0; (unsigned int)i < 0xA; i = (unsigned int)(i + 1) )
    {
      if ( !StartContext[i + 4] )
      {
        StartContext[i + 4] = -1;
        break;
      }
    }
  }
  KeReleaseSpinLock(StartContext + 14, v10);
  if ( (StartContext[2] & 1) == 0 || KeGetCurrentIrql() )
  {
    v16 = (StartContext[2] & 2) == 0;
    v17 = (_QWORD *)ExAllocatePool2(64, 16, 544297812);
    if ( v17 )
    {
      WorkItem = IoAllocateWorkItem((PDEVICE_OBJECT)StartContext[15]);
      if ( WorkItem )
      {
        *v17 = StartContext;
        v17[1] = WorkItem;
        IoQueueWorkItem(WorkItem, TSQueueCallback, v16, v17);
        return 0;
      }
      ExFreePoolWithTag(v17, 0);
    }
    v14 = -1073741670;
  }
  else
  {
    *(&ObjectAttributes.Length + 1) = 0;
    *(&ObjectAttributes.Attributes + 1) = 0;
    if ( (_DWORD)i == 10 )
    {
      v14 = -1073741527;
    }
    else
    {
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 576;
      ObjectAttributes.ObjectName = 0;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v14 = PsCreateSystemThread(
              (PHANDLE)&StartContext[i + 4],
              0x1FFFFFu,
              &ObjectAttributes,
              0,
              0,
              TSQueueWorker,
              StartContext);
      if ( !v14 )
        return 0;
      v15 = KeAcquireSpinLockRaiseToDpc(StartContext + 14);
      StartContext[i + 4] = 0;
      KeReleaseSpinLock(StartContext + 14, v15);
    }
  }
  v19 = KeAcquireSpinLockRaiseToDpc(StartContext + 14);
  --*((_DWORD *)StartContext + 6);
  v20 = v19;
  for ( j = (_QWORD *)*StartContext; j != StartContext; j = (_QWORD *)*j )
  {
    if ( j == v8 )
    {
      v22 = *v8;
      if ( *(_QWORD **)(*v8 + 8LL) == v8 )
      {
        v23 = (_QWORD *)v8[1];
        if ( (_QWORD *)*v23 == v8 )
        {
          *v23 = v22;
          *(_QWORD *)(v22 + 8) = v23;
          ExFreePoolWithTag(v8, 0);
          goto LABEL_36;
        }
      }
LABEL_38:
      __fastfail(3u);
    }
  }
  v14 = 0;
LABEL_36:
  KeReleaseSpinLock(StartContext + 14, v20);
  return v14;
}

```

## disassembly

```asm
0x1400018a0  push    rbx
0x1400018a2  push    rbp
0x1400018a3  push    rsi
0x1400018a4  sub     rsp, 70h
0x1400018a8  mov     rbx, qword ptr cs:WPP_MAIN_CB.AlignmentRequirement
0x1400018af  mov     rsi, r8
0x1400018b2  mov     rbp, rdx
0x1400018b5  test    rbx, rbx
0x1400018b8  jnz     short loc_1400018C4
0x1400018ba  mov     eax, 0C000000Dh
0x1400018bf  jmp     loc_1400019C0
0x1400018c4  mov     edx, 20h ; ' '
0x1400018c9  mov     [rsp+88h+arg_0], rdi
0x1400018d1  mov     ecx, 40h ; '@'
0x1400018d6  mov     r8d, 20715354h
0x1400018dc  call    cs:__imp_ExAllocatePool2
0x1400018e3  nop     dword ptr [rax+rax+00h]
0x1400018e8  mov     rdi, rax
0x1400018eb  test    rax, rax
0x1400018ee  jnz     short loc_1400018FA
0x1400018f0  mov     eax, 0C0000017h
0x1400018f5  jmp     loc_1400019B8
0x1400018fa  lea     rcx, [rbx+70h]; SpinLock
0x1400018fe  mov     [rax+18h], rbp
0x140001902  mov     [rax+10h], rsi
0x140001906  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000190d  nop     dword ptr [rax+rax+00h]
0x140001912  mov     ecx, [rbx+10h]
0x140001915  movzx   ebp, al
0x140001918  test    cl, cl
0x14000191a  jns     short loc_140001947
0x14000191c  movzx   edx, al; NewIrql
0x14000191f  lea     rcx, [rbx+70h]; SpinLock
0x140001923  call    cs:__imp_KeReleaseSpinLock
0x14000192a  nop     dword ptr [rax+rax+00h]
0x14000192f  xor     edx, edx; Tag
0x140001931  mov     rcx, rdi; P
0x140001934  call    cs:__imp_ExFreePoolWithTag
0x14000193b  nop     dword ptr [rax+rax+00h]
0x140001940  mov     eax, 0C0000022h
0x140001945  jmp     short loc_1400019B8
0x140001947  mov     rax, [rbx+8]
0x14000194b  mov     [rsp+88h+arg_8], r14
0x140001953  mov     [rsp+88h+arg_10], r15
0x14000195b  cmp     [rax], rbx
0x14000195e  jnz     loc_140001BCF
0x140001964  mov     [rdi], rbx
0x140001967  lea     rcx, [rbx+80h]; Event
0x14000196e  mov     [rdi+8], rax
0x140001972  xor     r8d, r8d; Wait
0x140001975  mov     [rax], rdi
0x140001978  xor     edx, edx; Increment
0x14000197a  mov     [rbx+8], rdi
0x14000197e  call    cs:__imp_KeSetEvent
0x140001985  nop     dword ptr [rax+rax+00h]
0x14000198a  mov     eax, [rbx+18h]
0x14000198d  cmp     eax, [rbx+14h]
0x140001990  jb      short loc_1400019C9
0x140001992  movzx   edx, bpl; NewIrql
0x140001996  lea     rcx, [rbx+70h]; SpinLock
0x14000199a  call    cs:__imp_KeReleaseSpinLock
0x1400019a1  nop     dword ptr [rax+rax+00h]
0x1400019a6  xor     eax, eax
0x1400019a8  mov     r14, [rsp+88h+arg_8]
0x1400019b0  mov     r15, [rsp+88h+arg_10]
0x1400019b8  mov     rdi, [rsp+88h+arg_0]
0x1400019c0  add     rsp, 70h
0x1400019c4  pop     rsi
0x1400019c5  pop     rbp
0x1400019c6  pop     rbx
0x1400019c7  retn
0x1400019c9  xor     r15d, r15d
0x1400019cc  inc     eax
0x1400019ce  mov     r14d, r15d
0x1400019d1  mov     [rbx+18h], eax
0x1400019d4  mov     eax, [rbx+10h]
0x1400019d7  test    al, 1
0x1400019d9  jz      short loc_1400019FC
0x1400019db  mov     r14d, r15d
0x1400019de  cmp     r14d, 0Ah
0x1400019e2  jnb     short loc_1400019FC
0x1400019e4  cmp     [rbx+r14*8+20h], r15
0x1400019e9  lea     rcx, [rbx+r14*8]
0x1400019ed  jz      short loc_1400019F4
0x1400019ef  inc     r14d
0x1400019f2  jmp     short loc_1400019DE
0x1400019f4  mov     qword ptr [rcx+20h], 0FFFFFFFFFFFFFFFFh
0x1400019fc  movzx   edx, bpl; NewIrql
0x140001a00  lea     rcx, [rbx+70h]; SpinLock
0x140001a04  call    cs:__imp_KeReleaseSpinLock
0x140001a0b  nop     dword ptr [rax+rax+00h]
0x140001a10  mov     eax, [rbx+10h]
0x140001a13  test    al, 1
0x140001a15  jz      loc_140001AD7
0x140001a1b  call    cs:__imp_KeGetCurrentIrql
0x140001a22  nop     dword ptr [rax+rax+00h]
0x140001a27  test    al, al
0x140001a29  jnz     loc_140001AD7
0x140001a2f  mov     dword ptr [rsp+88h+ObjectAttributes+4], r15d
0x140001a34  mov     dword ptr [rsp+88h+ObjectAttributes+1Ch], r15d
0x140001a39  cmp     r14d, 0Ah
0x140001a3d  jnz     short loc_140001A49
0x140001a3f  mov     ebp, 0C0000129h
0x140001a44  jmp     loc_140001B34
0x140001a49  lea     rax, TSQueueWorker
0x140001a50  mov     [rsp+88h+StartContext], rbx; StartContext
0x140001a55  xorps   xmm0, xmm0
0x140001a58  mov     [rsp+88h+StartRoutine], rax; StartRoutine
0x140001a5d  lea     rcx, [rbx+20h]
0x140001a61  mov     [rsp+88h+ClientId], r15; ClientId
0x140001a66  lea     rcx, [rcx+r14*8]; ThreadHandle
0x140001a6a  mov     [rsp+88h+ObjectAttributes.Length], 30h ; '0'
0x140001a72  xor     r9d, r9d; ProcessHandle
0x140001a75  mov     [rsp+88h+ObjectAttributes.RootDirectory], r15
0x140001a7a  lea     r8, [rsp+88h+ObjectAttributes]; ObjectAttributes
0x140001a7f  mov     [rsp+88h+ObjectAttributes.Attributes], 240h
0x140001a87  mov     edx, 1FFFFFh; DesiredAccess
0x140001a8c  mov     [rsp+88h+ObjectAttributes.ObjectName], r15
0x140001a91  movdqu  xmmword ptr [rsp+88h+ObjectAttributes.SecurityDescriptor], xmm0
0x140001a97  call    cs:__imp_PsCreateSystemThread
0x140001a9e  nop     dword ptr [rax+rax+00h]
0x140001aa3  mov     ebp, eax
0x140001aa5  test    eax, eax
0x140001aa7  jz      loc_1400019A6
0x140001aad  lea     rcx, [rbx+70h]; SpinLock
0x140001ab1  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001ab8  nop     dword ptr [rax+rax+00h]
0x140001abd  lea     rcx, [rbx+70h]; SpinLock
0x140001ac1  mov     [rbx+r14*8+20h], r15
0x140001ac6  movzx   edx, al; NewIrql
0x140001ac9  call    cs:__imp_KeReleaseSpinLock
0x140001ad0  nop     dword ptr [rax+rax+00h]
0x140001ad5  jmp     short loc_140001B34
0x140001ad7  mov     ebp, [rbx+10h]
0x140001ada  mov     edx, 10h
0x140001adf  shr     ebp, 1
0x140001ae1  mov     ecx, 40h ; '@'
0x140001ae6  not     ebp
0x140001ae8  mov     r8d, 20715354h
0x140001aee  and     ebp, 1
0x140001af1  call    cs:__imp_ExAllocatePool2
0x140001af8  nop     dword ptr [rax+rax+00h]
0x140001afd  mov     r14, rax
0x140001b00  test    rax, rax
0x140001b03  jz      short loc_140001B2F
0x140001b05  mov     rcx, [rbx+78h]; DeviceObject
0x140001b09  call    cs:__imp_IoAllocateWorkItem
0x140001b10  nop     dword ptr [rax+rax+00h]
0x140001b15  test    rax, rax
0x140001b18  jnz     loc_140001BA7
0x140001b1e  xor     edx, edx; Tag
0x140001b20  mov     rcx, r14; P
0x140001b23  call    cs:__imp_ExFreePoolWithTag
0x140001b2a  nop     dword ptr [rax+rax+00h]
0x140001b2f  mov     ebp, 0C000009Ah
0x140001b34  lea     rcx, [rbx+70h]; SpinLock
0x140001b38  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001b3f  nop     dword ptr [rax+rax+00h]
0x140001b44  dec     dword ptr [rbx+18h]
0x140001b47  movzx   r14d, al
0x140001b4b  mov     rcx, [rbx]
0x140001b4e  cmp     rcx, rbx
0x140001b51  jz      short loc_140001B89
0x140001b53  cmp     rcx, rdi
0x140001b56  jz      short loc_140001B5D
0x140001b58  mov     rcx, [rcx]
0x140001b5b  jmp     short loc_140001B4E
0x140001b5d  mov     rcx, [rdi]
0x140001b60  cmp     [rcx+8], rdi
0x140001b64  jnz     short loc_140001BCF
0x140001b66  mov     rax, [rdi+8]
0x140001b6a  cmp     [rax], rdi
0x140001b6d  jnz     short loc_140001BCF
0x140001b6f  mov     [rax], rcx
0x140001b72  xor     edx, edx; Tag
0x140001b74  mov     [rcx+8], rax
0x140001b78  mov     rcx, rdi; P
0x140001b7b  call    cs:__imp_ExFreePoolWithTag
0x140001b82  nop     dword ptr [rax+rax+00h]
0x140001b87  jmp     short loc_140001B8C
0x140001b89  mov     ebp, r15d
0x140001b8c  movzx   edx, r14b; NewIrql
0x140001b90  lea     rcx, [rbx+70h]; SpinLock
0x140001b94  call    cs:__imp_KeReleaseSpinLock
0x140001b9b  nop     dword ptr [rax+rax+00h]
0x140001ba0  mov     eax, ebp
0x140001ba2  jmp     loc_1400019A8
0x140001ba7  mov     r9, r14; Context
0x140001baa  mov     [r14], rbx
0x140001bad  mov     r8d, ebp; QueueType
0x140001bb0  mov     [r14+8], rax
0x140001bb4  lea     rdx, TSQueueCallback; WorkerRoutine
0x140001bbb  mov     rcx, rax; IoWorkItem
0x140001bbe  call    cs:__imp_IoQueueWorkItem
0x140001bc5  nop     dword ptr [rax+rax+00h]
0x140001bca  jmp     loc_1400019A6
0x140001bcf  mov     ecx, 3
0x140001bd4  int     29h; Win8: RtlFailFast(ecx)
```
