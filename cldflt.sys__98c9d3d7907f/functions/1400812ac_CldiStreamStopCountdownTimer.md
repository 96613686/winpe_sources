# CldiStreamStopCountdownTimer

- ea: `0x1400812ac`
- end: `0x14008136e`
- name: `CldiStreamStopCountdownTimer`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14007cd6c`

## callees

- `0x140003c50`
- `0x1400812ac`

## import_xrefs

- `ntoskrnl!KeCancelTimer` at `0x1400812b9`
- `ntoskrnl!KeCancelTimer` at `0x1400812b9`
- `ntoskrnl!KeRemoveQueueDpc` at `0x1400812d0`
- `ntoskrnl!KeRemoveQueueDpc` at `0x1400812d0`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400812e5`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400812e5`
- `ntoskrnl!KeWaitForSingleObject` at `0x140081309`
- `ntoskrnl!KeWaitForSingleObject` at `0x140081309`
- `ntoskrnl!KeSetEvent` at `0x140081359`
- `ntoskrnl!KeSetEvent` at `0x140081359`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140081333`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140081333`

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
0x1400812ac  push    rbx
0x1400812ae  sub     rsp, 30h
0x1400812b2  lea     rcx, Timer; PKTIMER
0x1400812b9  call    cs:__imp_KeCancelTimer
0x1400812c0  nop     dword ptr [rax+rax+00h]
0x1400812c5  test    al, al
0x1400812c7  jnz     short loc_1400812DE
0x1400812c9  lea     rcx, Dpc; Dpc
0x1400812d0  call    cs:__imp_KeRemoveQueueDpc
0x1400812d7  nop     dword ptr [rax+rax+00h]
0x1400812dc  jmp     short loc_1400812F1
0x1400812de  lea     rcx, RunRef; RunRef
0x1400812e5  call    cs:__imp_ExReleaseRundownProtection
0x1400812ec  nop     dword ptr [rax+rax+00h]
0x1400812f1  xor     r9d, r9d; Alertable
0x1400812f4  mov     [rsp+38h+Timeout], 0; Timeout
0x1400812fd  xor     r8d, r8d; WaitMode
0x140081300  lea     rcx, Event; Object
0x140081307  xor     edx, edx; WaitReason
0x140081309  call    cs:__imp_KeWaitForSingleObject
0x140081310  nop     dword ptr [rax+rax+00h]
0x140081315  mov     ecx, eax
0x140081317  mov     ebx, eax
0x140081319  call    HsmDbgBreakOnStatus
0x14008131e  test    ebx, ebx
0x140081320  js      short loc_14008134D
0x140081322  mov     edx, cs:dword_140028818
0x140081328  test    edx, edx
0x14008132a  jnz     short loc_14008133F
0x14008132c  lea     rcx, RunRef; RunRef
0x140081333  call    cs:__imp_ExWaitForRundownProtectionRelease
0x14008133a  nop     dword ptr [rax+rax+00h]
0x14008133f  mov     edx, cs:dword_140028818
0x140081345  inc     edx
0x140081347  mov     cs:dword_140028818, edx
0x14008134d  xor     r8d, r8d; Wait
0x140081350  lea     rcx, Event; Event
0x140081357  xor     edx, edx; Increment
0x140081359  call    cs:__imp_KeSetEvent
0x140081360  nop     dword ptr [rax+rax+00h]
0x140081365  mov     eax, ebx
0x140081367  add     rsp, 30h
0x14008136b  pop     rbx
0x14008136c  retn
```
