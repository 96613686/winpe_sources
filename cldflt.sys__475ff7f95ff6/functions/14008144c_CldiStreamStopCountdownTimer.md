# CldiStreamStopCountdownTimer

- ea: `0x14008144c`
- end: `0x14008150e`
- name: `CldiStreamStopCountdownTimer`
- size: `194`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14007ceac`

## callees

- `0x140003c50`
- `0x14008144c`

## import_xrefs

- `ntoskrnl!KeCancelTimer` at `0x140081459`
- `ntoskrnl!KeCancelTimer` at `0x140081459`
- `ntoskrnl!KeRemoveQueueDpc` at `0x140081470`
- `ntoskrnl!KeRemoveQueueDpc` at `0x140081470`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140081485`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140081485`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400814a9`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400814a9`
- `ntoskrnl!KeSetEvent` at `0x1400814f9`
- `ntoskrnl!KeSetEvent` at `0x1400814f9`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400814d3`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400814d3`

## pseudocode

```c
__int64 CldiStreamStopCountdownTimer()
{
  NTSTATUS v0; // ebx

  if ( KeCancelTimer(&Timer) )
    ExReleaseRundownProtection(&RunRef);
  else
    KeRemoveQueueDpc(&Dpc);
  v0 = KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
  HsmDbgBreakOnStatus((unsigned int)v0);
  if ( v0 >= 0 )
  {
    if ( !dword_140028818 )
      ExWaitForRundownProtectionRelease(&RunRef);
    ++dword_140028818;
  }
  KeSetEvent(&Event, 0, 0);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x14008144c  push    rbx
0x14008144e  sub     rsp, 30h
0x140081452  lea     rcx, Timer; PKTIMER
0x140081459  call    cs:__imp_KeCancelTimer
0x140081460  nop     dword ptr [rax+rax+00h]
0x140081465  test    al, al
0x140081467  jnz     short loc_14008147E
0x140081469  lea     rcx, Dpc; Dpc
0x140081470  call    cs:__imp_KeRemoveQueueDpc
0x140081477  nop     dword ptr [rax+rax+00h]
0x14008147c  jmp     short loc_140081491
0x14008147e  lea     rcx, RunRef; RunRef
0x140081485  call    cs:__imp_ExReleaseRundownProtection
0x14008148c  nop     dword ptr [rax+rax+00h]
0x140081491  xor     r9d, r9d; Alertable
0x140081494  mov     [rsp+38h+Timeout], 0; Timeout
0x14008149d  xor     r8d, r8d; WaitMode
0x1400814a0  lea     rcx, Event; Object
0x1400814a7  xor     edx, edx; WaitReason
0x1400814a9  call    cs:__imp_KeWaitForSingleObject
0x1400814b0  nop     dword ptr [rax+rax+00h]
0x1400814b5  mov     ecx, eax
0x1400814b7  mov     ebx, eax
0x1400814b9  call    HsmDbgBreakOnStatus
0x1400814be  test    ebx, ebx
0x1400814c0  js      short loc_1400814ED
0x1400814c2  mov     edx, cs:dword_140028818
0x1400814c8  test    edx, edx
0x1400814ca  jnz     short loc_1400814DF
0x1400814cc  lea     rcx, RunRef; RunRef
0x1400814d3  call    cs:__imp_ExWaitForRundownProtectionRelease
0x1400814da  nop     dword ptr [rax+rax+00h]
0x1400814df  mov     edx, cs:dword_140028818
0x1400814e5  inc     edx
0x1400814e7  mov     cs:dword_140028818, edx
0x1400814ed  xor     r8d, r8d; Wait
0x1400814f0  lea     rcx, Event; Event
0x1400814f7  xor     edx, edx; Increment
0x1400814f9  call    cs:__imp_KeSetEvent
0x140081500  nop     dword ptr [rax+rax+00h]
0x140081505  mov     eax, ebx
0x140081507  add     rsp, 30h
0x14008150b  pop     rbx
0x14008150c  retn
```
