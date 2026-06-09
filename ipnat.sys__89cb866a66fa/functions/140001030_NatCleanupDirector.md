# NatCleanupDirector

- ea: `0x140001030`
- end: `0x140001156`
- name: `NatCleanupDirector`
- size: `294`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140001480`
- `0x140007ca0`
- `0x140024cc0`

## callees

- `0x140001030`
- `0x140001e78`
- `0x14000218c`
- `0x14002c710`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140001090`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140001090`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001110`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001110`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400010ed`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400010ed`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400010d7`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400010d7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000107a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000107a`

## pseudocode

```c
void __fastcall NatCleanupDirector(_QWORD *P)
{
  KIRQL v2; // bp
  _QWORD *i; // r8
  _QWORD **v4; // rbx
  void (__fastcall *v5)(_QWORD); // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_((__int64)WPP_GLOBAL_Control->AttachedDevice, 0xAu, (__int64)WPP_cdce044c4ae83ba031b9a5ec16d7ed01_Traceguids);
  }
  v2 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.Dpc.DeferredRoutine);
  KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)&WPP_MAIN_CB.Dpc.DeferredContext);
  for ( i = (_QWORD *)P[4]; i != P + 4; i = *v4 )
  {
    v4 = (_QWORD **)i[1];
    NatMappingDetachDirector(P, *(i - 1), i - 28, 2);
  }
  KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)&WPP_MAIN_CB.Dpc.DeferredContext);
  KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Dpc.DeferredRoutine, v2);
  v5 = (void (__fastcall *)(_QWORD))P[11];
  if ( v5 )
    v5(P[7]);
  ExFreePoolWithTag(P, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_((__int64)WPP_GLOBAL_Control->AttachedDevice, 0xBu, (__int64)WPP_cdce044c4ae83ba031b9a5ec16d7ed01_Traceguids);
  }
}

```

## disassembly

```asm
0x140001030  push    rbx
0x140001032  push    rbp
0x140001033  push    rsi
0x140001034  push    rdi
0x140001035  push    r14
0x140001037  sub     rsp, 20h
0x14000103b  mov     rdi, rcx
0x14000103e  mov     rcx, cs:WPP_GLOBAL_Control
0x140001045  lea     r14, WPP_GLOBAL_Control
0x14000104c  cmp     rcx, r14
0x14000104f  jz      short loc_140001073
0x140001051  mov     eax, [rcx+2Ch]
0x140001054  test    al, 1
0x140001056  jz      short loc_140001073
0x140001058  cmp     byte ptr [rcx+29h], 6
0x14000105c  jb      short loc_140001073
0x14000105e  mov     rcx, [rcx+18h]
0x140001062  lea     r8, WPP_cdce044c4ae83ba031b9a5ec16d7ed01_Traceguids
0x140001069  mov     edx, 0Ah
0x14000106e  call    WPP_SF_
0x140001073  lea     rcx, WPP_MAIN_CB.Dpc.DeferredRoutine; SpinLock
0x14000107a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001081  nop     dword ptr [rax+rax+00h]
0x140001086  lea     rcx, WPP_MAIN_CB.Dpc.DeferredContext; SpinLock
0x14000108d  mov     bpl, al
0x140001090  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140001097  nop     dword ptr [rax+rax+00h]
0x14000109c  lea     rsi, [rdi+20h]
0x1400010a0  mov     r8, [rsi]
0x1400010a3  jmp     short loc_1400010CB
0x1400010a5  mov     rbx, [r8+8]
0x1400010a9  lea     rdx, [r8-0E0h]
0x1400010b0  mov     r8, rdx
0x1400010b3  mov     r9d, 2
0x1400010b9  mov     rdx, [rdx+0D8h]
0x1400010c0  mov     rcx, rdi
0x1400010c3  call    NatMappingDetachDirector
0x1400010c8  mov     r8, [rbx]
0x1400010cb  cmp     r8, rsi
0x1400010ce  jnz     short loc_1400010A5
0x1400010d0  lea     rcx, WPP_MAIN_CB.Dpc.DeferredContext; SpinLock
0x1400010d7  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400010de  nop     dword ptr [rax+rax+00h]
0x1400010e3  mov     dl, bpl; NewIrql
0x1400010e6  lea     rcx, WPP_MAIN_CB.Dpc.DeferredRoutine; SpinLock
0x1400010ed  call    cs:__imp_KeReleaseSpinLock
0x1400010f4  nop     dword ptr [rax+rax+00h]
0x1400010f9  mov     rax, [rdi+58h]
0x1400010fd  test    rax, rax
0x140001100  jz      short loc_14000110B
0x140001102  mov     rcx, [rdi+38h]
0x140001106  call    _guard_dispatch_icall
0x14000110b  xor     edx, edx; Tag
0x14000110d  mov     rcx, rdi; P
0x140001110  call    cs:__imp_ExFreePoolWithTag
0x140001117  nop     dword ptr [rax+rax+00h]
0x14000111c  mov     rcx, cs:WPP_GLOBAL_Control
0x140001123  cmp     rcx, r14
0x140001126  jz      short loc_14000114A
0x140001128  mov     eax, [rcx+2Ch]
0x14000112b  test    al, 1
0x14000112d  jz      short loc_14000114A
0x14000112f  cmp     byte ptr [rcx+29h], 6
0x140001133  jb      short loc_14000114A
0x140001135  mov     rcx, [rcx+18h]
0x140001139  lea     r8, WPP_cdce044c4ae83ba031b9a5ec16d7ed01_Traceguids
0x140001140  mov     edx, 0Bh
0x140001145  call    WPP_SF_
0x14000114a  add     rsp, 20h
0x14000114e  pop     r14
0x140001150  pop     rdi
0x140001151  pop     rsi
0x140001152  pop     rbp
0x140001153  pop     rbx
0x140001154  retn
```
