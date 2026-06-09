# CldStreamUninitialize

- ea: `0x1400411d8`
- end: `0x1400412ab`
- name: `CldStreamUninitialize`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140037440`

## callees

- `0x140033c20`
- `0x1400411d8`

## import_xrefs

- `ntoskrnl!KeCancelTimer` at `0x1400411ec`
- `ntoskrnl!KeCancelTimer` at `0x1400411ec`
- `ntoskrnl!KeRemoveQueueDpc` at `0x140041203`
- `ntoskrnl!KeRemoveQueueDpc` at `0x140041203`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140041218`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140041218`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140041232`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140041232`
- `ntoskrnl!ZwClose` at `0x140041299`
- `ntoskrnl!ZwClose` at `0x140041299`
- `ntoskrnl!ObfDereferenceObject` at `0x140041281`
- `ntoskrnl!ObfDereferenceObject` at `0x140041281`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041269`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041269`
- `ntoskrnl!ExDeleteResourceLite` at `0x140041245`
- `ntoskrnl!ExDeleteResourceLite` at `0x140041245`

## pseudocode

```c
void CldStreamUninitialize()
{
  __int64 v0; // rcx

  if ( byte_140028769 )
  {
    if ( KeCancelTimer(&Timer) )
      ExReleaseRundownProtection(&RunRef);
    else
      KeRemoveQueueDpc(&Dpc);
    LOBYTE(v0) = 1;
    CldiStreamStartCountdownTimer(v0);
    ExWaitForRundownProtectionRelease(&RunRef);
    ExDeleteResourceLite(&Resource);
    byte_140028769 = 0;
  }
  if ( P )
    ExFreePoolWithTag(P, 0x6F746C43u);
  if ( Object )
    ObfDereferenceObject(Object);
  if ( Handle )
    ZwClose(Handle);
}

```

## disassembly

```asm
0x1400411d8  sub     rsp, 28h
0x1400411dc  cmp     cs:byte_140028769, 0
0x1400411e3  jz      short loc_140041258
0x1400411e5  lea     rcx, Timer; PKTIMER
0x1400411ec  call    cs:__imp_KeCancelTimer
0x1400411f3  nop     dword ptr [rax+rax+00h]
0x1400411f8  test    al, al
0x1400411fa  jnz     short loc_140041211
0x1400411fc  lea     rcx, Dpc; Dpc
0x140041203  call    cs:__imp_KeRemoveQueueDpc
0x14004120a  nop     dword ptr [rax+rax+00h]
0x14004120f  jmp     short loc_140041224
0x140041211  lea     rcx, RunRef; RunRef
0x140041218  call    cs:__imp_ExReleaseRundownProtection
0x14004121f  nop     dword ptr [rax+rax+00h]
0x140041224  mov     cl, 1
0x140041226  call    CldiStreamStartCountdownTimer
0x14004122b  lea     rcx, RunRef; RunRef
0x140041232  call    cs:__imp_ExWaitForRundownProtectionRelease
0x140041239  nop     dword ptr [rax+rax+00h]
0x14004123e  lea     rcx, Resource; Resource
0x140041245  call    cs:__imp_ExDeleteResourceLite
0x14004124c  nop     dword ptr [rax+rax+00h]
0x140041251  mov     cs:byte_140028769, 0
0x140041258  mov     rcx, cs:P; P
0x14004125f  test    rcx, rcx
0x140041262  jz      short loc_140041275
0x140041264  mov     edx, 6F746C43h; Tag
0x140041269  call    cs:__imp_ExFreePoolWithTag
0x140041270  nop     dword ptr [rax+rax+00h]
0x140041275  mov     rcx, cs:Object; Object
0x14004127c  test    rcx, rcx
0x14004127f  jz      short loc_14004128D
0x140041281  call    cs:__imp_ObfDereferenceObject
0x140041288  nop     dword ptr [rax+rax+00h]
0x14004128d  mov     rcx, cs:Handle; Handle
0x140041294  test    rcx, rcx
0x140041297  jz      short loc_1400412A5
0x140041299  call    cs:__imp_ZwClose
0x1400412a0  nop     dword ptr [rax+rax+00h]
0x1400412a5  add     rsp, 28h
0x1400412a9  retn
```
