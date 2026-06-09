# HidpUnregisterSleepstudyBlockerReasons

- ea: `0x18001a0b8`
- end: `0x18001a1c3`
- name: `HidpUnregisterSleepstudyBlockerReasons`
- size: `267`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002136c`
- `0x18003b444`
- `0x18003f2b4`

## callees

- `0x18001a0b8`
- `0x18001e944`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x18001a1ab`
- `ntoskrnl!KeReleaseSpinLock` at `0x18001a1ab`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18001a0da`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18001a0da`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_UnregisterComponent` at `0x18001a0f5`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_UnregisterComponent` at `0x18001a118`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_UnregisterComponent` at `0x18001a13b`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_UnregisterComponent` at `0x18001a15e`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_UnregisterComponent` at `0x18001a181`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_UnregisterComponent` at `0x18001a0f5`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_UnregisterComponent` at `0x18001a118`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_UnregisterComponent` at `0x18001a13b`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_UnregisterComponent` at `0x18001a15e`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_UnregisterComponent` at `0x18001a181`

## pseudocode

```c
void __fastcall HidpUnregisterSleepstudyBlockerReasons(KSPIN_LOCK *a1)
{
  KIRQL v2; // di

  if ( (unsigned int)Feature_UHSSRI01__private_IsEnabledDeviceUsageNoInline() )
    v2 = KeAcquireSpinLockRaiseToDpc(a1 + 267);
  else
    v2 = 0;
  if ( a1[268] )
  {
    SleepstudyHelper_UnregisterComponent();
    a1[268] = 0;
  }
  if ( a1[269] )
  {
    SleepstudyHelper_UnregisterComponent();
    a1[269] = 0;
  }
  if ( a1[270] )
  {
    SleepstudyHelper_UnregisterComponent();
    a1[270] = 0;
  }
  if ( a1[271] )
  {
    SleepstudyHelper_UnregisterComponent();
    a1[271] = 0;
  }
  if ( a1[272] )
  {
    SleepstudyHelper_UnregisterComponent();
    a1[272] = 0;
  }
  if ( (unsigned int)Feature_UHSSRI01__private_IsEnabledDeviceUsageNoInline() )
    KeReleaseSpinLock(a1 + 267, v2);
}

```

## disassembly

```asm
0x18001a0b8  mov     [rsp+arg_0], rbx
0x18001a0bd  push    rdi
0x18001a0be  sub     rsp, 20h
0x18001a0c2  mov     rbx, rcx
0x18001a0c5  call    Feature_UHSSRI01__private_IsEnabledDeviceUsageNoInline
0x18001a0ca  test    eax, eax
0x18001a0cc  jnz     short loc_18001A0D3
0x18001a0ce  xor     dil, dil
0x18001a0d1  jmp     short loc_18001A0E9
0x18001a0d3  lea     rcx, [rbx+858h]; SpinLock
0x18001a0da  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x18001a0e1  nop     dword ptr [rax+rax+00h]
0x18001a0e6  mov     dil, al
0x18001a0e9  mov     rcx, [rbx+860h]
0x18001a0f0  test    rcx, rcx
0x18001a0f3  jz      short loc_18001A10C
0x18001a0f5  call    cs:__imp_SleepstudyHelper_UnregisterComponent
0x18001a0fc  nop     dword ptr [rax+rax+00h]
0x18001a101  mov     qword ptr [rbx+860h], 0
0x18001a10c  mov     rcx, [rbx+868h]
0x18001a113  test    rcx, rcx
0x18001a116  jz      short loc_18001A12F
0x18001a118  call    cs:__imp_SleepstudyHelper_UnregisterComponent
0x18001a11f  nop     dword ptr [rax+rax+00h]
0x18001a124  mov     qword ptr [rbx+868h], 0
0x18001a12f  mov     rcx, [rbx+870h]
0x18001a136  test    rcx, rcx
0x18001a139  jz      short loc_18001A152
0x18001a13b  call    cs:__imp_SleepstudyHelper_UnregisterComponent
0x18001a142  nop     dword ptr [rax+rax+00h]
0x18001a147  mov     qword ptr [rbx+870h], 0
0x18001a152  mov     rcx, [rbx+878h]
0x18001a159  test    rcx, rcx
0x18001a15c  jz      short loc_18001A175
0x18001a15e  call    cs:__imp_SleepstudyHelper_UnregisterComponent
0x18001a165  nop     dword ptr [rax+rax+00h]
0x18001a16a  mov     qword ptr [rbx+878h], 0
0x18001a175  mov     rcx, [rbx+880h]
0x18001a17c  test    rcx, rcx
0x18001a17f  jz      short loc_18001A198
0x18001a181  call    cs:__imp_SleepstudyHelper_UnregisterComponent
0x18001a188  nop     dword ptr [rax+rax+00h]
0x18001a18d  mov     qword ptr [rbx+880h], 0
0x18001a198  call    Feature_UHSSRI01__private_IsEnabledDeviceUsageNoInline
0x18001a19d  test    eax, eax
0x18001a19f  jz      short loc_18001A1B7
0x18001a1a1  lea     rcx, [rbx+858h]; SpinLock
0x18001a1a8  mov     dl, dil; NewIrql
0x18001a1ab  call    cs:__imp_KeReleaseSpinLock
0x18001a1b2  nop     dword ptr [rax+rax+00h]
0x18001a1b7  mov     rbx, [rsp+28h+arg_0]
0x18001a1bc  add     rsp, 20h
0x18001a1c0  pop     rdi
0x18001a1c1  retn
```
