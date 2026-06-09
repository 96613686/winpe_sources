# NatCleanupEditor

- ea: `0x140005300`
- end: `0x140005404`
- name: `NatCleanupEditor`
- size: `260`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x140005a90`
- `0x140007ca0`
- `0x140020970`
- `0x140021150`
- `0x140021cf0`
- `0x140023160`
- `0x140023940`
- `0x1400244e0`

## callees

- `0x14000218c`
- `0x140005300`
- `0x1400064c0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140005360`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140005360`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400053be`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400053be`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400053ad`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400053ad`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140005397`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140005397`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000534a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000534a`

## pseudocode

```c
void __fastcall NatCleanupEditor(_QWORD *P)
{
  KIRQL v2; // bp
  _QWORD *i; // rdx
  _QWORD **v4; // rbx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_((__int64)WPP_GLOBAL_Control->AttachedDevice, 0xAu, (__int64)WPP_37d479de965b38db5e5cf32a4e7b4389_Traceguids);
  }
  v2 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceQueue);
  KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceQueue.DeviceListHead);
  for ( i = (_QWORD *)P[4]; i != P + 4; i = *v4 )
  {
    v4 = (_QWORD **)i[1];
    NatMappingDetachEditor(P, i - 24);
  }
  KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceQueue.DeviceListHead);
  KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceQueue, v2);
  ExFreePoolWithTag(P, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_((__int64)WPP_GLOBAL_Control->AttachedDevice, 0xBu, (__int64)WPP_37d479de965b38db5e5cf32a4e7b4389_Traceguids);
  }
}

```

## disassembly

```asm
0x140005300  push    rbx
0x140005302  push    rbp
0x140005303  push    rsi
0x140005304  push    rdi
0x140005305  push    r14
0x140005307  sub     rsp, 20h
0x14000530b  mov     rsi, rcx
0x14000530e  mov     rcx, cs:WPP_GLOBAL_Control
0x140005315  lea     r14, WPP_GLOBAL_Control
0x14000531c  cmp     rcx, r14
0x14000531f  jz      short loc_140005343
0x140005321  mov     eax, [rcx+2Ch]
0x140005324  test    al, 1
0x140005326  jz      short loc_140005343
0x140005328  cmp     byte ptr [rcx+29h], 6
0x14000532c  jb      short loc_140005343
0x14000532e  mov     rcx, [rcx+18h]
0x140005332  lea     r8, WPP_37d479de965b38db5e5cf32a4e7b4389_Traceguids
0x140005339  mov     edx, 0Ah
0x14000533e  call    WPP_SF_
0x140005343  lea     rcx, WPP_MAIN_CB.DeviceQueue; SpinLock
0x14000534a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140005351  nop     dword ptr [rax+rax+00h]
0x140005356  lea     rcx, WPP_MAIN_CB.DeviceQueue.DeviceListHead; SpinLock
0x14000535d  mov     bpl, al
0x140005360  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140005367  nop     dword ptr [rax+rax+00h]
0x14000536c  lea     rdi, [rsi+20h]
0x140005370  mov     rdx, [rdi]
0x140005373  jmp     short loc_14000538B
0x140005375  mov     rbx, [rdx+8]
0x140005379  mov     rcx, rsi
0x14000537c  add     rdx, 0FFFFFFFFFFFFFF40h
0x140005383  call    NatMappingDetachEditor
0x140005388  mov     rdx, [rbx]
0x14000538b  cmp     rdx, rdi
0x14000538e  jnz     short loc_140005375
0x140005390  lea     rcx, WPP_MAIN_CB.DeviceQueue.DeviceListHead; SpinLock
0x140005397  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000539e  nop     dword ptr [rax+rax+00h]
0x1400053a3  mov     dl, bpl; NewIrql
0x1400053a6  lea     rcx, WPP_MAIN_CB.DeviceQueue; SpinLock
0x1400053ad  call    cs:__imp_KeReleaseSpinLock
0x1400053b4  nop     dword ptr [rax+rax+00h]
0x1400053b9  xor     edx, edx; Tag
0x1400053bb  mov     rcx, rsi; P
0x1400053be  call    cs:__imp_ExFreePoolWithTag
0x1400053c5  nop     dword ptr [rax+rax+00h]
0x1400053ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1400053d1  cmp     rcx, r14
0x1400053d4  jz      short loc_1400053F8
0x1400053d6  mov     eax, [rcx+2Ch]
0x1400053d9  test    al, 1
0x1400053db  jz      short loc_1400053F8
0x1400053dd  cmp     byte ptr [rcx+29h], 6
0x1400053e1  jb      short loc_1400053F8
0x1400053e3  mov     rcx, [rcx+18h]
0x1400053e7  lea     r8, WPP_37d479de965b38db5e5cf32a4e7b4389_Traceguids
0x1400053ee  mov     edx, 0Bh
0x1400053f3  call    WPP_SF_
0x1400053f8  add     rsp, 20h
0x1400053fc  pop     r14
0x1400053fe  pop     rdi
0x1400053ff  pop     rsi
0x140005400  pop     rbp
0x140005401  pop     rbx
0x140005402  retn
```
