# SmbCeDereferenceServerEntryEx

- ea: `0x140014400`
- end: `0x14001464a`
- name: `SmbCeDereferenceServerEntryEx`
- size: `586`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter2)`
- caller_count: `21`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1400017f0`
- `0x140006ec0`
- `0x1400093a0`
- `0x140012840`
- `0x14001f0e0`
- `0x140021840`
- `0x140022950`
- `0x140024330`
- `0x1400283b0`
- `0x14002ed80`
- `0x140031500`
- `0x140031940`
- `0x14003864c`
- `0x14003fbb0`
- `0x140045660`
- `0x1400463a8`
- `0x14004b4cc`
- `0x14004b798`
- `0x14007f65c`
- `0x14007f8e4`
- `0x140092abc`

## callees

- `0x140003480`
- `0x140005540`
- `0x140014400`
- `0x140014650`
- `0x140028830`
- `0x140037fa4`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1400145f1`
- `ntoskrnl!KeSetEvent` at `0x1400145f1`
- `ntoskrnl!KeBugCheckEx` at `0x1400145b7`
- `ntoskrnl!KeBugCheckEx` at `0x140014617`
- `ntoskrnl!KeBugCheckEx` at `0x14001463d`
- `ntoskrnl!KeBugCheckEx` at `0x1400145b7`
- `ntoskrnl!KeBugCheckEx` at `0x140014617`
- `ntoskrnl!KeBugCheckEx` at `0x14001463d`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x1400144ee`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x1400144ee`
- `rdbss!RxPostToWorkerThread` at `0x14001454b`
- `rdbss!RxPostToWorkerThread` at `0x14001454b`

## pseudocode

```c
int __fastcall SmbCeDereferenceServerEntryEx(ULONG_PTR BugCheckParameter2, char a2)
{
  int v4; // ebx
  PDEVICE_OBJECT *v5; // rax
  __int64 v6; // rbx
  KIRQL v7; // bp
  __int64 v8; // rdx
  _QWORD *v9; // rax
  __int64 v10; // rcx
  signed __int32 v11; // ecx
  char v12; // cc
  signed __int32 v13; // ecx
  signed __int32 v14; // eax
  signed __int32 v15; // eax

  v4 = _InterlockedDecrement((volatile signed __int32 *)(BugCheckParameter2 + 8));
  v5 = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    LODWORD(v5) = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( ((unsigned __int8)v5 & 0x40) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      LODWORD(v5) = WPP_SF_qDD(
                      WPP_GLOBAL_Control->AttachedDevice,
                      26,
                      WPP_948a51171ac53989b14c3e6a960354da_Traceguids,
                      BugCheckParameter2,
                      v4 + 1,
                      v4);
  }
  if ( v4 <= 0 )
  {
    if ( v4 < 0 )
      KeBugCheckEx(0x27u, 0x65534FD7u, BugCheckParameter2, v4, 0);
    v6 = *(_QWORD *)(BugCheckParameter2 + 24);
    v7 = 0;
    if ( !a2 )
      v7 = SmbCeAcquireSpinLock(v6);
    *(_DWORD *)(BugCheckParameter2 + 12) = 10;
    SmbCeUpperDisconnectAllBindingObjectsLite(BugCheckParameter2, 3221225996LL);
    v8 = *(_QWORD *)(BugCheckParameter2 + 32);
    if ( *(_QWORD *)(v8 + 8) != BugCheckParameter2 + 32
      || (v9 = *(_QWORD **)(BugCheckParameter2 + 40), *v9 != BugCheckParameter2 + 32) )
    {
      __fastfail(3u);
    }
    v10 = *(_QWORD *)(BugCheckParameter2 + 24);
    *v9 = v8;
    *(_QWORD *)(v8 + 8) = v9;
    if ( *(_QWORD *)(v10 + 1904) == v10 + 1904 )
      MRxSmbCancelRecurrentService((PKSPIN_LOCK)(v10 + 1344));
    if ( !SmbCeGetFirstServerEntry(v6) )
      KeSetEvent((PRKEVENT)(v6 + 1320), 0, 0);
    if ( !a2 )
    {
      *(_DWORD *)(v6 + 2352) = -1;
      ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v6 + 1920), v7);
    }
    *(_QWORD *)(BugCheckParameter2 + 336) = BugCheckParameter2 + 328;
    *(_QWORD *)(BugCheckParameter2 + 328) = BugCheckParameter2 + 328;
    _InterlockedIncrement((volatile signed __int32 *)(v6 + 2668));
    v11 = _InterlockedExchangeAdd((volatile signed __int32 *)(v6 + 2632), 1u);
    v12 = (v11 + 1 < 0) ^ __OFADD__(1, v11) | (v11 == -1);
    v13 = v11 + 1;
    if ( v12 )
      KeBugCheckEx(0x27u, 0xA0001u, BugCheckParameter2, v13, 0);
    v14 = _InterlockedExchangeAdd((volatile signed __int32 *)(v6 + 2664), 1u);
    v12 = (v14 + 1 < 0) ^ __OFADD__(1, v14) | (v14 == -1);
    v15 = v14 + 1;
    if ( v12 )
      KeBugCheckEx(0x27u, 0xA0001u, BugCheckParameter2, v15, 8u);
    LODWORD(v5) = RxPostToWorkerThread(
                    (PRDBSS_DEVICE_OBJECT)v6,
                    NormalWorkQueue,
                    (PRX_WORK_QUEUE_ITEM)(BugCheckParameter2 + 328),
                    SmbCeTearDownServerEntry,
                    (PVOID)BugCheckParameter2);
  }
  return (int)v5;
}

```

## disassembly

```asm
0x140014400  push    rbx
0x140014402  push    rsi
0x140014403  push    rdi
0x140014404  sub     rsp, 30h
0x140014408  movzx   esi, dl
0x14001440b  mov     rdi, rcx
0x14001440e  mov     ebx, 0FFFFFFFFh
0x140014413  lock xadd [rcx+8], ebx
0x140014418  dec     ebx
0x14001441a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140014421  lea     rax, WPP_GLOBAL_Control
0x140014428  cmp     rcx, rax
0x14001442b  jz      short loc_140014438
0x14001442d  mov     eax, [rcx+2Ch]
0x140014430  test    al, 40h
0x140014432  jnz     loc_14001456D
0x140014438  test    ebx, ebx
0x14001443a  jle     short loc_140014445
0x14001443c  add     rsp, 30h
0x140014440  pop     rdi
0x140014441  pop     rsi
0x140014442  pop     rbx
0x140014443  retn
0x140014445  mov     [rsp+48h+arg_10], r14
0x14001444a  js      loc_14001459F
0x140014450  mov     rbx, [rdi+18h]
0x140014454  mov     [rsp+48h+arg_8], rbp
0x140014459  xor     bpl, bpl
0x14001445c  test    sil, sil
0x14001445f  jz      loc_1400145C4
0x140014465  xor     r14d, r14d
0x140014468  mov     dword ptr [rsp+48h+arg_0], 0C000020Ch
0x140014470  mov     dword ptr [rsp+48h+arg_0+4], r14d
0x140014475  mov     rcx, rdi
0x140014478  mov     rdx, [rsp+48h+arg_0]
0x14001447d  mov     dword ptr [rdi+0Ch], 0Ah
0x140014484  call    SmbCeUpperDisconnectAllBindingObjectsLite
0x140014489  mov     rdx, [rdi+20h]
0x14001448d  lea     rcx, [rdi+20h]
0x140014491  cmp     [rdx+8], rcx
0x140014495  jnz     loc_140014566
0x14001449b  mov     rax, [rcx+8]
0x14001449f  cmp     [rax], rcx
0x1400144a2  jnz     loc_140014566
0x1400144a8  mov     rcx, [rdi+18h]
0x1400144ac  mov     [rax], rdx
0x1400144af  mov     [rdx+8], rax
0x1400144b3  lea     rax, [rcx+770h]
0x1400144ba  cmp     [rax], rax
0x1400144bd  jz      loc_1400145D4
0x1400144c3  mov     rcx, rbx
0x1400144c6  call    SmbCeGetFirstServerEntry
0x1400144cb  test    rax, rax
0x1400144ce  jz      loc_1400145E5
0x1400144d4  test    sil, sil
0x1400144d7  jnz     short loc_1400144FA
0x1400144d9  lea     rcx, [rbx+780h]; SpinLock
0x1400144e0  mov     dword ptr [rbx+930h], 0FFFFFFFFh
0x1400144ea  movzx   edx, bpl; OldIrql
0x1400144ee  call    cs:__imp_ExReleaseSpinLockExclusive
0x1400144f5  nop     dword ptr [rax+rax+00h]
0x1400144fa  lea     r8, [rdi+148h]; pWorkQueueItem
0x140014501  mov     [r8+8], r8
0x140014505  mov     [r8], r8
0x140014508  lock inc dword ptr [rbx+0A6Ch]
0x14001450f  mov     eax, 1
0x140014514  mov     ecx, eax
0x140014516  lock xadd [rbx+0A48h], ecx
0x14001451e  add     ecx, eax
0x140014520  jle     loc_140014602
0x140014526  lock xadd [rbx+0A68h], eax
0x14001452e  add     eax, 1
0x140014531  jle     loc_140014624
0x140014537  lea     r9, SmbCeTearDownServerEntry; Routine
0x14001453e  mov     [rsp+48h+pContext], rdi; pContext
0x140014543  mov     edx, 3; WorkQueueType
0x140014548  mov     rcx, rbx; pMRxDeviceObject
0x14001454b  call    cs:__imp_RxPostToWorkerThread
0x140014552  nop     dword ptr [rax+rax+00h]
0x140014557  mov     rbp, [rsp+48h+arg_8]
0x14001455c  mov     r14, [rsp+48h+arg_10]
0x140014561  jmp     loc_14001443C
0x140014566  mov     ecx, 3
0x14001456b  int     29h; Win8: RtlFailFast(ecx)
0x14001456d  cmp     byte ptr [rcx+29h], 4
0x140014571  jb      loc_140014438
0x140014577  mov     rcx, [rcx+18h]
0x14001457b  lea     eax, [rbx+1]
0x14001457e  mov     edx, 1Ah
0x140014583  mov     [rsp+48h+var_20], ebx
0x140014587  mov     r9, rdi
0x14001458a  mov     dword ptr [rsp+48h+pContext], eax
0x14001458e  lea     r8, WPP_948a51171ac53989b14c3e6a960354da_Traceguids
0x140014595  call    WPP_SF_qDD
0x14001459a  jmp     loc_140014438
0x14001459f  xor     r14d, r14d
0x1400145a2  movsxd  r9, ebx; BugCheckParameter3
0x1400145a5  mov     r8, rdi; BugCheckParameter2
0x1400145a8  mov     [rsp+48h+pContext], r14; BugCheckParameter4
0x1400145ad  mov     edx, 65534FD7h; BugCheckParameter1
0x1400145b2  mov     ecx, 27h ; '''; BugCheckCode
0x1400145b7  call    cs:__imp_KeBugCheckEx
0x1400145c4  mov     rcx, rbx
0x1400145c7  call    SmbCeAcquireSpinLock
0x1400145cc  movzx   ebp, al
0x1400145cf  jmp     loc_140014465
0x1400145d4  add     rcx, 540h; SpinLock
0x1400145db  call    MRxSmbCancelRecurrentService
0x1400145e0  jmp     loc_1400144C3
0x1400145e5  lea     rcx, [rbx+528h]; Event
0x1400145ec  xor     r8d, r8d; Wait
0x1400145ef  xor     edx, edx; Increment
0x1400145f1  call    cs:__imp_KeSetEvent
0x1400145f8  nop     dword ptr [rax+rax+00h]
0x1400145fd  jmp     loc_1400144D4
0x140014602  movsxd  r9, ecx; BugCheckParameter3
0x140014605  mov     r8, rdi; BugCheckParameter2
0x140014608  mov     ecx, 27h ; '''; BugCheckCode
0x14001460d  mov     [rsp+48h+pContext], r14; BugCheckParameter4
0x140014612  mov     edx, 0A0001h; BugCheckParameter1
0x140014617  call    cs:__imp_KeBugCheckEx
0x140014624  movsxd  r9, eax; BugCheckParameter3
0x140014627  mov     r8, rdi; BugCheckParameter2
0x14001462a  mov     edx, 0A0001h; BugCheckParameter1
0x14001462f  mov     [rsp+48h+pContext], 8; BugCheckParameter4
0x140014638  mov     ecx, 27h ; '''; BugCheckCode
0x14001463d  call    cs:__imp_KeBugCheckEx
```
