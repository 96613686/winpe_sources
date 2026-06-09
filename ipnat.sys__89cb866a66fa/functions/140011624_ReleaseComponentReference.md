# ReleaseComponentReference

- ea: `0x140011624`
- end: `0x140011695`
- name: `ReleaseComponentReference`
- size: `113`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140007ca0`
- `0x140010df4`
- `0x140011264`
- `0x140011510`
- `0x140019cec`
- `0x14001a0f0`

## callees

- `0x140011624`
- `0x14002c710`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140011675`
- `ntoskrnl!KeSetEvent` at `0x140011675`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001164d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001165d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001164d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001165d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001162f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001162f`

## pseudocode

```c
char ReleaseComponentReference()
{
  KIRQL v0; // al

  v0 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceExtension);
  if ( --WPP_MAIN_CB.DeviceType )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceExtension, v0);
    return 0;
  }
  else
  {
    KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceExtension, v0);
    KeSetEvent((PRKEVENT)&WPP_MAIN_CB.Queue, 0, 0);
    ((void (*)(void))WPP_MAIN_CB.Queue.Wcb.DeviceRoutine)();
    return 1;
  }
}

```

## disassembly

```asm
0x140011624  sub     rsp, 28h
0x140011628  lea     rcx, WPP_MAIN_CB.DeviceExtension; SpinLock
0x14001162f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140011636  nop     dword ptr [rax+rax+00h]
0x14001163b  add     cs:WPP_MAIN_CB.DeviceType, 0FFFFFFFFh
0x140011642  lea     rcx, WPP_MAIN_CB.DeviceExtension; SpinLock
0x140011649  mov     dl, al; NewIrql
0x14001164b  jz      short loc_14001165D
0x14001164d  call    cs:__imp_KeReleaseSpinLock
0x140011654  nop     dword ptr [rax+rax+00h]
0x140011659  xor     al, al
0x14001165b  jmp     short loc_14001168F
0x14001165d  call    cs:__imp_KeReleaseSpinLock
0x140011664  nop     dword ptr [rax+rax+00h]
0x140011669  xor     r8d, r8d; Wait
0x14001166c  lea     rcx, WPP_MAIN_CB.Queue; Event
0x140011673  xor     edx, edx; Increment
0x140011675  call    cs:__imp_KeSetEvent
0x14001167c  nop     dword ptr [rax+rax+00h]
0x140011681  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+18h
0x140011688  call    _guard_dispatch_icall
0x14001168d  mov     al, 1
0x14001168f  add     rsp, 28h
0x140011693  retn
```
