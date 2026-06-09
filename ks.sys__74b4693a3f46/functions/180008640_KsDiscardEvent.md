# KsDiscardEvent

- ea: `0x180008640`
- end: `0x18000875a`
- name: `KsDiscardEvent`
- size: `282`
- prototype: `void __stdcall(PKSEVENT_ENTRY EventEntry)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1800082d0`
- `0x180049c20`
- `0x18004b128`
- `0x180051a08`
- `0x180058de0`
- `0x1800608b0`
- `0x180064010`

## callees

- `0x180008640`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1800086a8`
- `ntoskrnl!ObfDereferenceObject` at `0x180008702`
- `ntoskrnl!ObfDereferenceObject` at `0x1800086a8`
- `ntoskrnl!ObfDereferenceObject` at `0x180008702`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18000867d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18000867d`
- `ntoskrnl!KeReleaseSpinLock` at `0x180008693`
- `ntoskrnl!KeReleaseSpinLock` at `0x180008693`
- `ntoskrnl!KeRemoveQueueDpc` at `0x180008656`
- `ntoskrnl!KeRemoveQueueDpc` at `0x180008656`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800086d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800086eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x180008738`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800086d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800086eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x180008738`

## pseudocode

```c
void __stdcall KsDiscardEvent(PKSEVENT_ENTRY EventEntry)
{
  PKSDPC_ITEM DpcItem; // rcx
  KIRQL v3; // al
  PVOID v4; // rcx
  PVOID Object; // rcx
  PKSDPC_ITEM v6; // rax
  _QWORD *v7; // rcx
  __int64 v8; // rdx

  DpcItem = EventEntry->DpcItem;
  if ( !DpcItem )
  {
    Object = EventEntry->Object;
    if ( Object )
      ObfDereferenceObject(Object);
    goto LABEL_11;
  }
  if ( KeRemoveQueueDpc(&DpcItem->Dpc) )
    _InterlockedDecrement((volatile signed __int32 *)&EventEntry->DpcItem->ReferenceCount);
  EventEntry->Flags |= 1u;
  if ( (EventEntry->Flags & 2) == 0 )
  {
    v3 = KeAcquireSpinLockRaiseToDpc(&EventEntry->DpcItem->AccessLock);
    KeReleaseSpinLock(&EventEntry->DpcItem->AccessLock, v3);
  }
  v4 = EventEntry->Object;
  if ( v4 )
    ObfDereferenceObject(v4);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)&EventEntry->DpcItem->ReferenceCount, 0xFFFFFFFF) == 1 )
  {
    if ( (EventEntry->Flags & 4) != 0 )
    {
      while ( 1 )
      {
        v6 = EventEntry->DpcItem + 1;
        v7 = *(_QWORD **)&v6->Dpc.TargetInfoAsUlong;
        if ( *(PKSDPC_ITEM *)&v6->Dpc.TargetInfoAsUlong == v6 )
          break;
        if ( (PKSDPC_ITEM)v7[1] != v6 || (v8 = *v7, *(_QWORD **)(*v7 + 8LL) != v7) )
          __fastfail(3u);
        *(_QWORD *)&v6->Dpc.TargetInfoAsUlong = v8;
        *(_QWORD *)(v8 + 8) = v6;
        ExFreePoolWithTag(v7, 0);
      }
    }
    ExFreePoolWithTag(EventEntry->DpcItem, 0);
LABEL_11:
    ExFreePoolWithTag(&EventEntry[-1].EventItem, 0);
  }
}

```

## disassembly

```asm
0x180008640  push    rbx
0x180008642  sub     rsp, 20h
0x180008646  mov     rbx, rcx
0x180008649  mov     rcx, [rcx+18h]; Dpc
0x18000864d  test    rcx, rcx
0x180008650  jz      loc_1800086F9
0x180008656  call    cs:__imp_KeRemoveQueueDpc
0x18000865d  nop     dword ptr [rax+rax+00h]
0x180008662  test    al, al
0x180008664  jnz     loc_180008746
0x18000866a  or      dword ptr [rbx+50h], 1
0x18000866e  mov     eax, [rbx+50h]
0x180008671  test    al, 2
0x180008673  jnz     short loc_18000869F
0x180008675  mov     rcx, [rbx+18h]
0x180008679  add     rcx, 48h ; 'H'; SpinLock
0x18000867d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x180008684  nop     dword ptr [rax+rax+00h]
0x180008689  mov     rcx, [rbx+18h]
0x18000868d  mov     dl, al; NewIrql
0x18000868f  add     rcx, 48h ; 'H'; SpinLock
0x180008693  call    cs:__imp_KeReleaseSpinLock
0x18000869a  nop     dword ptr [rax+rax+00h]
0x18000869f  mov     rcx, [rbx+10h]; Object
0x1800086a3  test    rcx, rcx
0x1800086a6  jz      short loc_1800086B4
0x1800086a8  call    cs:__imp_ObfDereferenceObject
0x1800086af  nop     dword ptr [rax+rax+00h]
0x1800086b4  mov     rcx, [rbx+18h]
0x1800086b8  or      eax, 0FFFFFFFFh
0x1800086bb  lock xadd [rcx+40h], eax
0x1800086c0  cmp     eax, 1
0x1800086c3  jz      short loc_1800086CC
0x1800086c5  add     rsp, 20h
0x1800086c9  pop     rbx
0x1800086ca  retn
0x1800086cc  mov     eax, [rbx+50h]
0x1800086cf  test    al, 4
0x1800086d1  jnz     short loc_180008710
0x1800086d3  mov     rcx, [rbx+18h]; P
0x1800086d7  xor     edx, edx; Tag
0x1800086d9  call    cs:__imp_ExFreePoolWithTag
0x1800086e0  nop     dword ptr [rax+rax+00h]
0x1800086e5  lea     rcx, [rbx-20h]; P
0x1800086e9  xor     edx, edx; Tag
0x1800086eb  call    cs:__imp_ExFreePoolWithTag
0x1800086f2  nop     dword ptr [rax+rax+00h]
0x1800086f7  jmp     short loc_1800086C5
0x1800086f9  mov     rcx, [rbx+10h]; Object
0x1800086fd  test    rcx, rcx
0x180008700  jz      short loc_1800086E5
0x180008702  call    cs:__imp_ObfDereferenceObject
0x180008709  nop     dword ptr [rax+rax+00h]
0x18000870e  jmp     short loc_1800086E5
0x180008710  mov     rax, [rbx+18h]
0x180008714  add     rax, 50h ; 'P'
0x180008718  mov     rcx, [rax]; P
0x18000871b  cmp     rcx, rax
0x18000871e  jz      short loc_1800086D3
0x180008720  cmp     [rcx+8], rax
0x180008724  jnz     short loc_180008753
0x180008726  mov     rdx, [rcx]
0x180008729  cmp     [rdx+8], rcx
0x18000872d  jnz     short loc_180008753
0x18000872f  mov     [rax], rdx
0x180008732  mov     [rdx+8], rax
0x180008736  xor     edx, edx; Tag
0x180008738  call    cs:__imp_ExFreePoolWithTag
0x18000873f  nop     dword ptr [rax+rax+00h]
0x180008744  jmp     short loc_180008710
0x180008746  mov     rax, [rbx+18h]
0x18000874a  lock dec dword ptr [rax+40h]
0x18000874e  jmp     loc_18000866A
0x180008753  mov     ecx, 3
0x180008758  int     29h; Win8: RtlFailFast(ecx)
```
