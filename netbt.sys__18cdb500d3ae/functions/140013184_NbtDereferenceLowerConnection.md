# NbtDereferenceLowerConnection

- ea: `0x140013184`
- end: `0x1400133b9`
- name: `NbtDereferenceLowerConnection`
- size: `565`
- prototype: ``
- caller_count: `24`
- callee_count: `2`
- tags: ``

## callers

- `0x14000efd4`
- `0x1400103e8`
- `0x140010680`
- `0x140010988`
- `0x140010c90`
- `0x140011e50`
- `0x140011f50`
- `0x14001206c`
- `0x14001212c`
- `0x140012a10`
- `0x1400133c0`
- `0x140014610`
- `0x140014a40`
- `0x140021610`
- `0x140022ed0`
- `0x140023cb4`
- `0x1400269a8`
- `0x1400281b0`
- `0x14002af10`
- `0x14002d608`
- `0x14002ef50`
- `0x14002efd0`
- `0x14002fbc0`
- `0x14002fee0`

## callees

- `0x140013184`
- `0x1400439bc`

## import_xrefs

- `ntoskrnl!ExQueueWorkItem` at `0x1400132f5`
- `ntoskrnl!ExQueueWorkItem` at `0x1400132f5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400131aa`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001327b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400131aa`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001327b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400131cb`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001320d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400131cb`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001320d`
- `ntoskrnl!ExAllocatePool2` at `0x14001331e`
- `ntoskrnl!ExAllocatePool2` at `0x14001331e`

## pseudocode

```c
void __fastcall NbtDereferenceLowerConnection(__int64 a1, __int64 a2, __int64 a3, char a4, __int64 a5)
{
  KIRQL v6; // al
  KIRQL v7; // dl
  KSPIN_LOCK *v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rbx
  KIRQL v11; // al
  __int64 *v12; // rcx
  KIRQL v13; // di
  __int64 Pool2; // rax

  if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
    WPP_SF_qddds(
      a1,
      83,
      (unsigned int)WPP_8017b60c53a232e581eda6237e04704c_Traceguids,
      a1,
      *(_DWORD *)(a1 + 20),
      *(_DWORD *)(a1 + 20) - 1,
      a4,
      a5);
  v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 104));
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 20), 0xFFFFFFFF) != 1 )
  {
    v7 = v6;
    v8 = (KSPIN_LOCK *)(a1 + 104);
LABEL_5:
    KeReleaseSpinLock(v8, v7);
    return;
  }
  _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 40) + 900LL));
  v9 = *(_QWORD *)(a1 + 24);
  *(_DWORD *)(a1 + 20) = 1000;
  if ( v9 && ((*(_DWORD *)(v9 + 16) - 829321027) & 0xFEFFFFFF) == 0 )
  {
    *(_DWORD *)(v9 + 48) = 9;
    *(_QWORD *)(v9 + 24) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    *(_BYTE *)(v9 + 267) = 9;
    *(_BYTE *)(a1 + 124) = 9;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 104), v6);
  v10 = a1 + 128;
  if ( a1 != -128 && !*(_DWORD *)(a1 + 192) )
  {
    *(_DWORD *)(a1 + 188) = 0;
LABEL_11:
    *(_DWORD *)(v10 + 64) = 1;
    *(_QWORD *)(v10 + 48) = &DelayedWipeOutLowerconn;
    *(_QWORD *)(v10 + 16) = 0;
    *(_QWORD *)(v10 + 24) = a1;
    *(_QWORD *)(v10 + 32) = 0;
    *(_QWORD *)(v10 + 40) = 0;
    *(_BYTE *)(v10 + 68) = 32;
    *(_QWORD *)(v10 + 8) = v10;
    *(_QWORD *)v10 = v10;
    v11 = KeAcquireSpinLockRaiseToDpc(&qword_1400396D8);
    v12 = (__int64 *)qword_1400396E8;
    v13 = v11;
    if ( *(PVOID **)qword_1400396E8 != &P )
      __fastfail(3u);
    *(_QWORD *)v10 = &P;
    *(_QWORD *)(v10 + 8) = v12;
    *v12 = v10;
    qword_1400396E8 = v10;
    _InterlockedAdd(&dword_1400396F0, 1u);
    if ( !byte_140039752 && !_InterlockedExchange(&dword_1400396F4, 1) )
    {
      WorkItem.List.Flink = 0;
      WorkItem.WorkerRoutine = (PWORKER_THREAD_ROUTINE)NTExecuteWorker;
      WorkItem.Parameter = &WorkItem;
      ExQueueWorkItem(&WorkItem, CriticalWorkQueue);
    }
    v7 = v13;
    v8 = &qword_1400396D8;
    goto LABEL_5;
  }
  Pool2 = ExAllocatePool2(64, 72, 842162766);
  v10 = Pool2;
  if ( Pool2 )
  {
    *(_DWORD *)(Pool2 + 60) = 1;
    goto LABEL_11;
  }
}

```

## disassembly

```asm
0x140013184  mov     [rsp+arg_0], rbx
0x140013189  mov     [rsp+arg_8], rsi
0x14001318e  push    rdi
0x14001318f  sub     rsp, 40h
0x140013193  mov     rdi, rcx
0x140013196  test    byte ptr cs:xmmword_140038420+9, 40h
0x14001319d  jnz     loc_140013345
0x1400131a3  lea     rbx, [rdi+68h]
0x1400131a7  mov     rcx, rbx; SpinLock
0x1400131aa  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400131b1  nop     dword ptr [rax+rax+00h]
0x1400131b6  mov     r8b, al
0x1400131b9  or      edx, 0FFFFFFFFh
0x1400131bc  lock xadd [rdi+14h], edx
0x1400131c1  cmp     edx, 1
0x1400131c4  jz      short loc_1400131E8
0x1400131c6  mov     dl, al; NewIrql
0x1400131c8  mov     rcx, rbx; SpinLock
0x1400131cb  call    cs:__imp_KeReleaseSpinLock
0x1400131d2  nop     dword ptr [rax+rax+00h]
0x1400131d7  mov     rbx, [rsp+48h+arg_0]
0x1400131dc  mov     rsi, [rsp+48h+arg_8]
0x1400131e1  add     rsp, 40h
0x1400131e5  pop     rdi
0x1400131e6  retn
0x1400131e8  mov     rax, [rdi+28h]
0x1400131ec  lock dec dword ptr [rax+384h]
0x1400131f3  mov     rcx, [rdi+18h]
0x1400131f7  mov     dword ptr [rdi+14h], 3E8h
0x1400131fe  test    rcx, rcx
0x140013201  jnz     loc_14001337F
0x140013207  mov     dl, r8b; NewIrql
0x14001320a  mov     rcx, rbx; SpinLock
0x14001320d  call    cs:__imp_KeReleaseSpinLock
0x140013214  nop     dword ptr [rax+rax+00h]
0x140013219  lea     rbx, [rdi+80h]
0x140013220  mov     esi, 1
0x140013225  test    rbx, rbx
0x140013228  jz      loc_140013310
0x14001322e  cmp     dword ptr [rbx+40h], 0
0x140013232  jnz     loc_140013310
0x140013238  mov     dword ptr [rbx+3Ch], 0
0x14001323f  mov     [rbx+40h], esi
0x140013242  lea     rax, DelayedWipeOutLowerconn
0x140013249  mov     [rbx+30h], rax
0x14001324d  lea     rcx, qword_1400396D8; SpinLock
0x140013254  mov     qword ptr [rbx+10h], 0
0x14001325c  mov     [rbx+18h], rdi
0x140013260  mov     qword ptr [rbx+20h], 0
0x140013268  mov     qword ptr [rbx+28h], 0
0x140013270  mov     byte ptr [rbx+44h], 20h ; ' '
0x140013274  mov     [rbx+8], rbx
0x140013278  mov     [rbx], rbx
0x14001327b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140013282  nop     dword ptr [rax+rax+00h]
0x140013287  mov     rcx, cs:qword_1400396E8
0x14001328e  mov     dil, al
0x140013291  lea     rax, P
0x140013298  cmp     [rcx], rax
0x14001329b  jnz     loc_14001333E
0x1400132a1  mov     [rbx], rax
0x1400132a4  mov     [rbx+8], rcx
0x1400132a8  mov     [rcx], rbx
0x1400132ab  mov     cs:qword_1400396E8, rbx
0x1400132b2  lock add cs:dword_1400396F0, esi
0x1400132b9  cmp     cs:byte_140039752, 0
0x1400132c0  jnz     short loc_140013301
0x1400132c2  xchg    esi, cs:dword_1400396F4
0x1400132c8  test    esi, esi
0x1400132ca  jnz     short loc_140013301
0x1400132cc  lea     rax, NTExecuteWorker
0x1400132d3  mov     cs:WorkItem.List.Flink, 0
0x1400132de  lea     rcx, WorkItem; WorkItem
0x1400132e5  mov     cs:WorkItem.WorkerRoutine, rax
0x1400132ec  xor     edx, edx; QueueType
0x1400132ee  mov     cs:WorkItem.Parameter, rcx
0x1400132f5  call    cs:__imp_ExQueueWorkItem
0x1400132fc  nop     dword ptr [rax+rax+00h]
0x140013301  mov     dl, dil
0x140013304  lea     rcx, qword_1400396D8
0x14001330b  jmp     loc_1400131CB
0x140013310  mov     edx, 48h ; 'H'
0x140013315  mov     r8d, 3232624Eh
0x14001331b  lea     ecx, [rdx-8]
0x14001331e  call    cs:__imp_ExAllocatePool2
0x140013325  nop     dword ptr [rax+rax+00h]
0x14001332a  mov     rbx, rax
0x14001332d  test    rax, rax
0x140013330  jz      loc_1400131D7
0x140013336  mov     [rax+3Ch], esi
0x140013339  jmp     loc_14001323F
0x14001333e  mov     ecx, 3
0x140013343  int     29h; Win8: RtlFailFast(ecx)
0x140013345  mov     r10d, [rcx+14h]
0x140013349  mov     edx, 53h ; 'S'
0x14001334e  mov     rax, [rsp+48h+arg_20]
0x140013353  mov     [rsp+48h+var_10], rax
0x140013358  mov     [rsp+48h+var_18], r9d
0x14001335d  mov     r9, rdi
0x140013360  lea     r8d, [r10-1]
0x140013364  mov     [rsp+48h+var_20], r8d
0x140013369  lea     r8, WPP_8017b60c53a232e581eda6237e04704c_Traceguids
0x140013370  mov     [rsp+48h+var_28], r10d
0x140013375  call    WPP_SF_qddds
0x14001337a  jmp     loc_1400131A3
0x14001337f  mov     eax, [rcx+10h]
0x140013382  sub     eax, 316E6F43h
0x140013387  test    eax, 0FEFFFFFFh
0x14001338c  jnz     loc_140013207
0x140013392  mov     dword ptr [rcx+30h], 9
0x140013399  mov     qword ptr [rcx+18h], 0
0x1400133a1  mov     qword ptr [rdi+18h], 0
0x1400133a9  mov     byte ptr [rcx+10Bh], 9
0x1400133b0  mov     byte ptr [rdi+7Ch], 9
0x1400133b4  jmp     loc_140013207
```
