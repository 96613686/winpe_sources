# CldStreamUninitialize

- ea: `0x1400411e8`
- end: `0x1400412bb`
- name: `CldStreamUninitialize`
- size: `211`
- prototype: `void()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140037460`

## callees

- `0x140033c20`
- `0x1400411e8`

## import_xrefs

- `ntoskrnl!KeCancelTimer` at `0x1400411fc`
- `ntoskrnl!KeCancelTimer` at `0x1400411fc`
- `ntoskrnl!KeRemoveQueueDpc` at `0x140041213`
- `ntoskrnl!KeRemoveQueueDpc` at `0x140041213`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140041228`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140041228`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140041242`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140041242`
- `ntoskrnl!ZwClose` at `0x1400412a9`
- `ntoskrnl!ZwClose` at `0x1400412a9`
- `ntoskrnl!ObfDereferenceObject` at `0x140041291`
- `ntoskrnl!ObfDereferenceObject` at `0x140041291`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041279`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041279`
- `ntoskrnl!ExDeleteResourceLite` at `0x140041255`
- `ntoskrnl!ExDeleteResourceLite` at `0x140041255`

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
0x1400411e8  sub     rsp, 28h
0x1400411ec  cmp     cs:byte_140028769, 0
0x1400411f3  jz      short loc_140041268
0x1400411f5  lea     rcx, Timer; PKTIMER
0x1400411fc  call    cs:__imp_KeCancelTimer
0x140041203  nop     dword ptr [rax+rax+00h]
0x140041208  test    al, al
0x14004120a  jnz     short loc_140041221
0x14004120c  lea     rcx, Dpc; Dpc
0x140041213  call    cs:__imp_KeRemoveQueueDpc
0x14004121a  nop     dword ptr [rax+rax+00h]
0x14004121f  jmp     short loc_140041234
0x140041221  lea     rcx, RunRef; RunRef
0x140041228  call    cs:__imp_ExReleaseRundownProtection
0x14004122f  nop     dword ptr [rax+rax+00h]
0x140041234  mov     cl, 1
0x140041236  call    CldiStreamStartCountdownTimer
0x14004123b  lea     rcx, RunRef; RunRef
0x140041242  call    cs:__imp_ExWaitForRundownProtectionRelease
0x140041249  nop     dword ptr [rax+rax+00h]
0x14004124e  lea     rcx, Resource; Resource
0x140041255  call    cs:__imp_ExDeleteResourceLite
0x14004125c  nop     dword ptr [rax+rax+00h]
0x140041261  mov     cs:byte_140028769, 0
0x140041268  mov     rcx, cs:P; P
0x14004126f  test    rcx, rcx
0x140041272  jz      short loc_140041285
0x140041274  mov     edx, 6F746C43h; Tag
0x140041279  call    cs:__imp_ExFreePoolWithTag
0x140041280  nop     dword ptr [rax+rax+00h]
0x140041285  mov     rcx, cs:Object; Object
0x14004128c  test    rcx, rcx
0x14004128f  jz      short loc_14004129D
0x140041291  call    cs:__imp_ObfDereferenceObject
0x140041298  nop     dword ptr [rax+rax+00h]
0x14004129d  mov     rcx, cs:Handle; Handle
0x1400412a4  test    rcx, rcx
0x1400412a7  jz      short loc_1400412B5
0x1400412a9  call    cs:__imp_ZwClose
0x1400412b0  nop     dword ptr [rax+rax+00h]
0x1400412b5  add     rsp, 28h
0x1400412b9  retn
```
