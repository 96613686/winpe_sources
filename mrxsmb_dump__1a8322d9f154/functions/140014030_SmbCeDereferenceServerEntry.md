# SmbCeDereferenceServerEntry

- ea: `0x140014030`
- end: `0x1400141f1`
- name: `SmbCeDereferenceServerEntry`
- size: `449`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter2)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x140003480`
- `0x140005540`
- `0x140014030`
- `0x140014370`
- `0x140014650`
- `0x140028830`
- `0x140037fa4`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1400141e0`
- `ntoskrnl!KeSetEvent` at `0x1400141e0`
- `ntoskrnl!KeBugCheckEx` at `0x1400141b6`
- `ntoskrnl!KeBugCheckEx` at `0x1400141b6`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140014114`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140014114`
- `rdbss!RxPostToWorkerThread` at `0x140014153`
- `rdbss!RxPostToWorkerThread` at `0x140014153`

## pseudocode

```c
int __fastcall SmbCeDereferenceServerEntry(ULONG_PTR BugCheckParameter2)
{
  int v2; // ebx
  PDEVICE_OBJECT *v3; // rax
  __int64 v4; // rsi
  KIRQL v5; // bl
  __int64 v6; // r8
  _QWORD *v7; // rdx
  __int64 v8; // rcx

  v2 = _InterlockedDecrement((volatile signed __int32 *)(BugCheckParameter2 + 8));
  v3 = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    LODWORD(v3) = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( ((unsigned __int8)v3 & 0x40) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      LODWORD(v3) = WPP_SF_qDD(
                      WPP_GLOBAL_Control->AttachedDevice,
                      26,
                      WPP_948a51171ac53989b14c3e6a960354da_Traceguids,
                      BugCheckParameter2,
                      v2 + 1,
                      v2);
  }
  if ( v2 <= 0 )
  {
    if ( v2 < 0 )
      KeBugCheckEx(0x27u, 0x65534FD7u, BugCheckParameter2, v2, 0);
    v4 = *(_QWORD *)(BugCheckParameter2 + 24);
    v5 = SmbCeAcquireSpinLock(v4);
    *(_DWORD *)(BugCheckParameter2 + 12) = 10;
    SmbCeUpperDisconnectAllBindingObjectsLite(BugCheckParameter2, 3221225996LL);
    v6 = *(_QWORD *)(BugCheckParameter2 + 32);
    if ( *(_QWORD *)(v6 + 8) != BugCheckParameter2 + 32
      || (v7 = *(_QWORD **)(BugCheckParameter2 + 40), *v7 != BugCheckParameter2 + 32) )
    {
      __fastfail(3u);
    }
    v8 = *(_QWORD *)(BugCheckParameter2 + 24);
    *v7 = v6;
    *(_QWORD *)(v6 + 8) = v7;
    if ( *(_QWORD *)(v8 + 1904) == v8 + 1904 )
      MRxSmbCancelRecurrentService((PKSPIN_LOCK)(v8 + 1344));
    if ( !SmbCeGetFirstServerEntry(v4) )
      KeSetEvent((PRKEVENT)(v4 + 1320), 0, 0);
    *(_DWORD *)(v4 + 2352) = -1;
    ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v4 + 1920), v5);
    *(_QWORD *)(BugCheckParameter2 + 336) = BugCheckParameter2 + 328;
    *(_QWORD *)(BugCheckParameter2 + 328) = BugCheckParameter2 + 328;
    SmbCeIncrementTeardownOpCounter(v4, BugCheckParameter2, 0);
    LODWORD(v3) = RxPostToWorkerThread(
                    (PRDBSS_DEVICE_OBJECT)v4,
                    NormalWorkQueue,
                    (PRX_WORK_QUEUE_ITEM)(BugCheckParameter2 + 328),
                    (PRX_WORKERTHREAD_ROUTINE)SmbCeTearDownServerEntry,
                    (PVOID)BugCheckParameter2);
  }
  return (int)v3;
}

```

## disassembly

```asm
0x140014030  mov     [rsp+arg_8], rbx
0x140014035  mov     [rsp+arg_10], rsi
0x14001403a  push    rdi
0x14001403b  sub     rsp, 30h
0x14001403f  mov     rdi, rcx
0x140014042  or      ebx, 0FFFFFFFFh
0x140014045  lock xadd [rcx+8], ebx
0x14001404a  dec     ebx
0x14001404c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140014053  lea     rax, WPP_GLOBAL_Control
0x14001405a  cmp     rcx, rax
0x14001405d  jz      short loc_14001406A
0x14001405f  mov     eax, [rcx+2Ch]
0x140014062  test    al, 40h
0x140014064  jnz     loc_14001416B
0x14001406a  test    ebx, ebx
0x14001406c  jle     short loc_14001407F
0x14001406e  mov     rbx, [rsp+38h+arg_8]
0x140014073  mov     rsi, [rsp+38h+arg_10]
0x140014078  add     rsp, 30h
0x14001407c  pop     rdi
0x14001407d  retn
0x14001407f  js      loc_14001419D
0x140014085  mov     rsi, [rdi+18h]
0x140014089  mov     rcx, rsi
0x14001408c  call    SmbCeAcquireSpinLock
0x140014091  mov     dword ptr [rsp+38h+arg_0], 0C000020Ch
0x140014099  mov     rcx, rdi
0x14001409c  mov     dword ptr [rsp+38h+arg_0+4], 0
0x1400140a4  mov     bl, al
0x1400140a6  mov     rdx, [rsp+38h+arg_0]
0x1400140ab  mov     dword ptr [rdi+0Ch], 0Ah
0x1400140b2  call    SmbCeUpperDisconnectAllBindingObjectsLite
0x1400140b7  lea     rcx, [rdi+20h]
0x1400140bb  mov     r8, [rcx]
0x1400140be  cmp     [r8+8], rcx
0x1400140c2  jnz     loc_140014164
0x1400140c8  mov     rdx, [rcx+8]
0x1400140cc  cmp     [rdx], rcx
0x1400140cf  jnz     loc_140014164
0x1400140d5  mov     rcx, [rdi+18h]
0x1400140d9  mov     [rdx], r8
0x1400140dc  mov     [r8+8], rdx
0x1400140e0  lea     rax, [rcx+770h]
0x1400140e7  cmp     [rax], rax
0x1400140ea  jz      loc_1400141C3
0x1400140f0  mov     rcx, rsi
0x1400140f3  call    SmbCeGetFirstServerEntry
0x1400140f8  test    rax, rax
0x1400140fb  jz      loc_1400141D4
0x140014101  lea     rcx, [rsi+780h]; SpinLock
0x140014108  mov     dword ptr [rsi+930h], 0FFFFFFFFh
0x140014112  mov     dl, bl; OldIrql
0x140014114  call    cs:__imp_ExReleaseSpinLockExclusive
0x14001411b  nop     dword ptr [rax+rax+00h]
0x140014120  lea     rbx, [rdi+148h]
0x140014127  xor     r8d, r8d
0x14001412a  mov     rdx, rdi
0x14001412d  mov     [rbx+8], rbx
0x140014131  mov     rcx, rsi
0x140014134  mov     [rbx], rbx
0x140014137  call    SmbCeIncrementTeardownOpCounter
0x14001413c  lea     r9, SmbCeTearDownServerEntry; Routine
0x140014143  mov     [rsp+38h+pContext], rdi; pContext
0x140014148  mov     r8, rbx; pWorkQueueItem
0x14001414b  mov     edx, 3; WorkQueueType
0x140014150  mov     rcx, rsi; pMRxDeviceObject
0x140014153  call    cs:__imp_RxPostToWorkerThread
0x14001415a  nop     dword ptr [rax+rax+00h]
0x14001415f  jmp     loc_14001406E
0x140014164  mov     ecx, 3
0x140014169  int     29h; Win8: RtlFailFast(ecx)
0x14001416b  cmp     byte ptr [rcx+29h], 4
0x14001416f  jb      loc_14001406A
0x140014175  mov     rcx, [rcx+18h]
0x140014179  lea     eax, [rbx+1]
0x14001417c  mov     edx, 1Ah
0x140014181  mov     [rsp+38h+var_10], ebx
0x140014185  mov     r9, rdi
0x140014188  mov     dword ptr [rsp+38h+pContext], eax
0x14001418c  lea     r8, WPP_948a51171ac53989b14c3e6a960354da_Traceguids
0x140014193  call    WPP_SF_qDD
0x140014198  jmp     loc_14001406A
0x14001419d  movsxd  r9, ebx; BugCheckParameter3
0x1400141a0  mov     r8, rdi; BugCheckParameter2
0x1400141a3  mov     edx, 65534FD7h; BugCheckParameter1
0x1400141a8  mov     [rsp+38h+pContext], 0; BugCheckParameter4
0x1400141b1  mov     ecx, 27h ; '''; BugCheckCode
0x1400141b6  call    cs:__imp_KeBugCheckEx
0x1400141c3  add     rcx, 540h; SpinLock
0x1400141ca  call    MRxSmbCancelRecurrentService
0x1400141cf  jmp     loc_1400140F0
0x1400141d4  lea     rcx, [rsi+528h]; Event
0x1400141db  xor     r8d, r8d; Wait
0x1400141de  xor     edx, edx; Increment
0x1400141e0  call    cs:__imp_KeSetEvent
0x1400141e7  nop     dword ptr [rax+rax+00h]
0x1400141ec  jmp     loc_140014101
```
