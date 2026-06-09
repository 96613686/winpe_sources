# PppoeCmDeactivateVcComplete

- ea: `0x140018230`
- end: `0x1400182cf`
- name: `PppoeCmDeactivateVcComplete`
- size: `159`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140002e0c`

## callees

- `0x14000113c`
- `0x140002e0c`
- `0x140006b80`
- `0x140018230`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1400182ad`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400182ad`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018294`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018294`

## pseudocode

```c
void __fastcall PppoeCmDeactivateVcComplete(unsigned int a1, __int64 a2, __int64 a3)
{
  __int64 v4; // r9
  KIRQL v5; // al

  v4 = a1;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_419ea9763cf3388c37536f51169668cc_Traceguids, a1);
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a2 + 24), 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(__int64, __int64, __int64, __int64))(a2 + 32))(a2 + 24, a2, a3, v4);
  v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 56));
  *(_DWORD *)(a2 + 88) &= ~4u;
  *(_BYTE *)(a2 + 64) = v5;
  KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 56), v5);
  TpCmCallCleanup(a2, 0);
}

```

## disassembly

```asm
0x140018230  mov     [rsp+arg_0], rbx
0x140018235  push    rdi
0x140018236  sub     rsp, 20h
0x14001823a  mov     rdi, rdx
0x14001823d  mov     r9d, ecx
0x140018240  mov     rcx, cs:WPP_GLOBAL_Control
0x140018247  lea     rax, WPP_GLOBAL_Control
0x14001824e  cmp     rcx, rax
0x140018251  jz      short loc_140018277
0x140018253  test    dword ptr [rcx+2Ch], 8000h
0x14001825a  jz      short loc_140018277
0x14001825c  cmp     byte ptr [rcx+29h], 2
0x140018260  jb      short loc_140018277
0x140018262  mov     rcx, [rcx+18h]
0x140018266  lea     r8, WPP_419ea9763cf3388c37536f51169668cc_Traceguids
0x14001826d  mov     edx, 2Eh ; '.'
0x140018272  call    WPP_SF_d
0x140018277  lea     rcx, [rdi+18h]
0x14001827b  or      eax, 0FFFFFFFFh
0x14001827e  lock xadd [rcx], eax
0x140018282  cmp     eax, 1
0x140018285  jnz     short loc_140018290
0x140018287  mov     rax, [rcx+8]
0x14001828b  call    _guard_dispatch_icall
0x140018290  lea     rcx, [rdi+38h]; SpinLock
0x140018294  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001829b  nop     dword ptr [rax+rax+00h]
0x1400182a0  and     dword ptr [rdi+58h], 0FFFFFFFBh
0x1400182a4  lea     rcx, [rdi+38h]; SpinLock
0x1400182a8  mov     dl, al; NewIrql
0x1400182aa  mov     [rdi+40h], al
0x1400182ad  call    cs:__imp_KeReleaseSpinLock
0x1400182b4  nop     dword ptr [rax+rax+00h]
0x1400182b9  xor     edx, edx
0x1400182bb  mov     rcx, rdi
0x1400182be  call    TpCmCallCleanup
0x1400182c3  mov     rbx, [rsp+28h+arg_0]
0x1400182c8  add     rsp, 20h
0x1400182cc  pop     rdi
0x1400182cd  retn
```
