# PppoeCmDeleteVc

- ea: `0x140005f90`
- end: `0x14000607f`
- name: `PppoeCmDeleteVc`
- size: `239`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x14000110c`
- `0x1400011b4`
- `0x14000547c`
- `0x140005f90`
- `0x140006b80`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140006005`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000603e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006005`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000603e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005fe1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006015`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005fe1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006015`

## pseudocode

```c
__int64 __fastcall PppoeCmDeleteVc(__int64 a1)
{
  __int64 v2; // rdi
  KIRQL v3; // al
  KIRQL v4; // al
  __int64 v5; // rcx
  KIRQL v6; // dl

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_419ea9763cf3388c37536f51169668cc_Traceguids);
  }
  v2 = *(_QWORD *)(a1 + 96);
  v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 56));
  *(_DWORD *)(a1 + 88) &= ~1u;
  *(_BYTE *)(a1 + 64) = v3;
  *(_QWORD *)(a1 + 168) = 0;
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), v3);
  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v2 + 8));
  v5 = *(_QWORD *)(v2 + 96);
  *(_BYTE *)(v2 + 16) = v4;
  RemoveFromHandleTable(v5, *(_QWORD *)(a1 + 112));
  v6 = *(_BYTE *)(v2 + 16);
  --*(_DWORD *)(v2 + 684);
  KeReleaseSpinLock((PKSPIN_LOCK)(v2 + 8), v6);
  DereferenceAdapter(*(_QWORD *)(a1 + 96));
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 24), 0xFFFFFFFF) == 1 )
    (*(void (**)(void))(a1 + 32))();
  return 0;
}

```

## disassembly

```asm
0x140005f90  mov     [rsp+arg_0], rbx
0x140005f95  mov     [rsp+arg_8], rsi
0x140005f9a  push    rdi
0x140005f9b  sub     rsp, 20h
0x140005f9f  mov     rsi, rcx
0x140005fa2  mov     rcx, cs:WPP_GLOBAL_Control
0x140005fa9  lea     rax, WPP_GLOBAL_Control
0x140005fb0  cmp     rcx, rax
0x140005fb3  jz      short loc_140005FD9
0x140005fb5  test    dword ptr [rcx+2Ch], 8000h
0x140005fbc  jz      short loc_140005FD9
0x140005fbe  cmp     byte ptr [rcx+29h], 2
0x140005fc2  jb      short loc_140005FD9
0x140005fc4  mov     rcx, [rcx+18h]
0x140005fc8  lea     r8, WPP_419ea9763cf3388c37536f51169668cc_Traceguids
0x140005fcf  mov     edx, 18h
0x140005fd4  call    WPP_SF_
0x140005fd9  mov     rdi, [rsi+60h]
0x140005fdd  lea     rcx, [rsi+38h]; SpinLock
0x140005fe1  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140005fe8  nop     dword ptr [rax+rax+00h]
0x140005fed  and     dword ptr [rsi+58h], 0FFFFFFFEh
0x140005ff1  lea     rcx, [rsi+38h]; SpinLock
0x140005ff5  mov     dl, al; NewIrql
0x140005ff7  mov     [rsi+40h], al
0x140005ffa  mov     qword ptr [rsi+0A8h], 0
0x140006005  call    cs:__imp_KeReleaseSpinLock
0x14000600c  nop     dword ptr [rax+rax+00h]
0x140006011  lea     rcx, [rdi+8]; SpinLock
0x140006015  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000601c  nop     dword ptr [rax+rax+00h]
0x140006021  mov     rcx, [rdi+60h]
0x140006025  mov     [rdi+10h], al
0x140006028  mov     rdx, [rsi+70h]
0x14000602c  call    RemoveFromHandleTable
0x140006031  mov     dl, [rdi+10h]; NewIrql
0x140006034  lea     rcx, [rdi+8]; SpinLock
0x140006038  dec     dword ptr [rdi+2ACh]
0x14000603e  call    cs:__imp_KeReleaseSpinLock
0x140006045  nop     dword ptr [rax+rax+00h]
0x14000604a  mov     rcx, [rsi+60h]
0x14000604e  call    DereferenceAdapter
0x140006053  lea     rcx, [rsi+18h]
0x140006057  or      eax, 0FFFFFFFFh
0x14000605a  lock xadd [rcx], eax
0x14000605e  cmp     eax, 1
0x140006061  jnz     short loc_14000606C
0x140006063  mov     rax, [rcx+8]
0x140006067  call    _guard_dispatch_icall
0x14000606c  mov     rbx, [rsp+28h+arg_0]
0x140006071  xor     eax, eax
0x140006073  mov     rsi, [rsp+28h+arg_8]
0x140006078  add     rsp, 20h
0x14000607c  pop     rdi
0x14000607d  retn
```
