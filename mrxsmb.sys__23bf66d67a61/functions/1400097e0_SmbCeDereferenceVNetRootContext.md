# SmbCeDereferenceVNetRootContext

- ea: `0x1400097e0`
- end: `0x1400099c5`
- name: `SmbCeDereferenceVNetRootContext`
- size: `485`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter2)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x1400093a0`
- `0x140017e60`
- `0x140022950`
- `0x140023cc0`
- `0x140028450`
- `0x14002f7a8`
- `0x1400302f0`

## callees

- `0x1400097e0`
- `0x140037fa4`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x140009992`
- `ntoskrnl!KeBugCheckEx` at `0x1400099b8`
- `ntoskrnl!KeBugCheckEx` at `0x140009992`
- `ntoskrnl!KeBugCheckEx` at `0x1400099b8`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x1400098c1`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x1400098c1`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140009834`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140009834`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140009843`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140009843`
- `rdbss!RxPostToWorkerThread` at `0x14000991e`
- `rdbss!RxPostToWorkerThread` at `0x14000991e`

## pseudocode

```c
int __fastcall SmbCeDereferenceVNetRootContext(ULONG_PTR BugCheckParameter2)
{
  __int64 v1; // rdi
  signed __int32 v3; // esi
  PDEVICE_OBJECT *v4; // rax
  KIRQL v5; // bp
  __int64 v6; // r8
  _QWORD *v7; // rdx
  __int64 v8; // r8
  _QWORD *v9; // rdx
  signed __int32 v10; // ecx
  char v11; // cc
  signed __int32 v12; // ecx
  signed __int32 v13; // eax
  signed __int32 v14; // eax

  v1 = *(_QWORD *)(BugCheckParameter2 + 24);
  v3 = _InterlockedDecrement((volatile signed __int32 *)(BugCheckParameter2 + 8));
  v4 = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    LODWORD(v4) = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( ((unsigned __int8)v4 & 0x40) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      LODWORD(v4) = WPP_SF_qDD(
                      WPP_GLOBAL_Control->AttachedDevice,
                      34,
                      WPP_c2a8e7a4add33c98a1c08e02d1cd8763_Traceguids,
                      BugCheckParameter2,
                      v3 + 1,
                      v3);
  }
  if ( !v3 )
  {
    v5 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)(v1 + 1920));
    *(_DWORD *)(v1 + 2352) = (unsigned int)PsGetCurrentThreadId();
    *(_DWORD *)(BugCheckParameter2 + 12) = 10;
    v6 = *(_QWORD *)(BugCheckParameter2 + 384);
    if ( *(_QWORD *)(v6 + 8) != BugCheckParameter2 + 384
      || (v7 = *(_QWORD **)(BugCheckParameter2 + 392), *v7 != BugCheckParameter2 + 384)
      || (*v7 = v6,
          *(_QWORD *)(v6 + 8) = v7,
          v8 = *(_QWORD *)(BugCheckParameter2 + 400),
          *(_QWORD *)(v8 + 8) != BugCheckParameter2 + 400)
      || (v9 = *(_QWORD **)(BugCheckParameter2 + 408), *v9 != BugCheckParameter2 + 400) )
    {
      __fastfail(3u);
    }
    *v9 = v8;
    *(_QWORD *)(v8 + 8) = v9;
    *(_DWORD *)(v1 + 2352) = -1;
    ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v1 + 1920), v5);
    *(_QWORD *)(BugCheckParameter2 + 208) = BugCheckParameter2 + 200;
    *(_QWORD *)(BugCheckParameter2 + 200) = BugCheckParameter2 + 200;
    _InterlockedIncrement((volatile signed __int32 *)(v1 + 2668));
    v10 = _InterlockedExchangeAdd((volatile signed __int32 *)(v1 + 2648), 1u);
    v11 = (v10 + 1 < 0) ^ __OFADD__(1, v10) | (v10 == -1);
    v12 = v10 + 1;
    if ( v11 )
      KeBugCheckEx(0x27u, 0xA0001u, BugCheckParameter2, v12, 4u);
    v13 = _InterlockedExchangeAdd((volatile signed __int32 *)(v1 + 2664), 1u);
    v11 = (v13 + 1 < 0) ^ __OFADD__(1, v13) | (v13 == -1);
    v14 = v13 + 1;
    if ( v11 )
      KeBugCheckEx(0x27u, 0xA0001u, BugCheckParameter2, v14, 8u);
    LODWORD(v4) = RxPostToWorkerThread(
                    (PRDBSS_DEVICE_OBJECT)v1,
                    NormalWorkQueue,
                    (PRX_WORK_QUEUE_ITEM)(BugCheckParameter2 + 200),
                    SmbCepTearDownVNetRootContext,
                    (PVOID)BugCheckParameter2);
  }
  return (int)v4;
}

```

## disassembly

```asm
0x1400097e0  mov     [rsp+arg_8], rbx
0x1400097e5  mov     [rsp+arg_10], rsi
0x1400097ea  push    rdi
0x1400097eb  sub     rsp, 30h
0x1400097ef  mov     rdi, [rcx+18h]
0x1400097f3  mov     rbx, rcx
0x1400097f6  mov     esi, 0FFFFFFFFh
0x1400097fb  lock xadd [rcx+8], esi
0x140009800  dec     esi
0x140009802  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140009809  lea     rax, WPP_GLOBAL_Control
0x140009810  cmp     rcx, rax
0x140009813  jz      short loc_140009820
0x140009815  mov     eax, [rcx+2Ch]
0x140009818  test    al, 40h
0x14000981a  jnz     loc_140009947
0x140009820  test    esi, esi
0x140009822  jnz     loc_14000992F
0x140009828  lea     rcx, [rdi+780h]; SpinLock
0x14000982f  mov     [rsp+38h+arg_0], rbp
0x140009834  call    cs:__imp_ExAcquireSpinLockExclusive
0x14000983b  nop     dword ptr [rax+rax+00h]
0x140009840  movzx   ebp, al
0x140009843  call    cs:__imp_PsGetCurrentThreadId
0x14000984a  nop     dword ptr [rax+rax+00h]
0x14000984f  mov     [rdi+930h], eax
0x140009855  lea     rcx, [rbx+180h]
0x14000985c  mov     dword ptr [rbx+0Ch], 0Ah
0x140009863  mov     r8, [rcx]
0x140009866  cmp     [r8+8], rcx
0x14000986a  jnz     loc_140009940
0x140009870  mov     rdx, [rcx+8]
0x140009874  cmp     [rdx], rcx
0x140009877  jnz     loc_140009940
0x14000987d  mov     [rdx], r8
0x140009880  lea     rax, [rbx+190h]
0x140009887  mov     [r8+8], rdx
0x14000988b  mov     r8, [rax]
0x14000988e  cmp     [r8+8], rax
0x140009892  jnz     loc_140009940
0x140009898  mov     rdx, [rax+8]
0x14000989c  cmp     [rdx], rax
0x14000989f  jnz     loc_140009940
0x1400098a5  mov     [rdx], r8
0x1400098a8  lea     rcx, [rdi+780h]; SpinLock
0x1400098af  mov     [r8+8], rdx
0x1400098b3  movzx   edx, bpl; OldIrql
0x1400098b7  mov     dword ptr [rdi+930h], 0FFFFFFFFh
0x1400098c1  call    cs:__imp_ExReleaseSpinLockExclusive
0x1400098c8  nop     dword ptr [rax+rax+00h]
0x1400098cd  lea     r8, [rbx+0C8h]; pWorkQueueItem
0x1400098d4  mov     [r8+8], r8
0x1400098d8  mov     [r8], r8
0x1400098db  lock inc dword ptr [rdi+0A6Ch]
0x1400098e2  mov     eax, 1
0x1400098e7  mov     ecx, eax
0x1400098e9  lock xadd [rdi+0A58h], ecx
0x1400098f1  add     ecx, eax
0x1400098f3  jle     loc_140009979
0x1400098f9  lock xadd [rdi+0A68h], eax
0x140009901  add     eax, 1
0x140009904  jle     loc_14000999F
0x14000990a  lea     r9, SmbCepTearDownVNetRootContext; Routine
0x140009911  mov     [rsp+38h+pContext], rbx; pContext
0x140009916  mov     edx, 3; WorkQueueType
0x14000991b  mov     rcx, rdi; pMRxDeviceObject
0x14000991e  call    cs:__imp_RxPostToWorkerThread
0x140009925  nop     dword ptr [rax+rax+00h]
0x14000992a  mov     rbp, [rsp+38h+arg_0]
0x14000992f  mov     rbx, [rsp+38h+arg_8]
0x140009934  mov     rsi, [rsp+38h+arg_10]
0x140009939  add     rsp, 30h
0x14000993d  pop     rdi
0x14000993e  retn
0x140009940  mov     ecx, 3
0x140009945  int     29h; Win8: RtlFailFast(ecx)
0x140009947  cmp     byte ptr [rcx+29h], 4
0x14000994b  jb      loc_140009820
0x140009951  mov     rcx, [rcx+18h]
0x140009955  lea     eax, [rsi+1]
0x140009958  mov     edx, 22h ; '"'
0x14000995d  mov     [rsp+38h+var_10], esi
0x140009961  mov     r9, rbx
0x140009964  mov     dword ptr [rsp+38h+pContext], eax
0x140009968  lea     r8, WPP_c2a8e7a4add33c98a1c08e02d1cd8763_Traceguids
0x14000996f  call    WPP_SF_qDD
0x140009974  jmp     loc_140009820
0x140009979  movsxd  r9, ecx; BugCheckParameter3
0x14000997c  mov     r8, rbx; BugCheckParameter2
0x14000997f  mov     ecx, 27h ; '''; BugCheckCode
0x140009984  mov     [rsp+38h+pContext], 4; BugCheckParameter4
0x14000998d  mov     edx, 0A0001h; BugCheckParameter1
0x140009992  call    cs:__imp_KeBugCheckEx
0x14000999f  movsxd  r9, eax; BugCheckParameter3
0x1400099a2  mov     r8, rbx; BugCheckParameter2
0x1400099a5  mov     edx, 0A0001h; BugCheckParameter1
0x1400099aa  mov     [rsp+38h+pContext], 8; BugCheckParameter4
0x1400099b3  mov     ecx, 27h ; '''; BugCheckCode
0x1400099b8  call    cs:__imp_KeBugCheckEx
```
