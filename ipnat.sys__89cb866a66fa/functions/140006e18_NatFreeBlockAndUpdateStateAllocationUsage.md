# NatFreeBlockAndUpdateStateAllocationUsage

- ea: `0x140006e18`
- end: `0x140006efa`
- name: `NatFreeBlockAndUpdateStateAllocationUsage`
- size: `226`
- prototype: `__int64 __fastcall(PNPAGED_LOOKASIDE_LIST Lookaside, PVOID Entry)`
- caller_count: `9`
- callee_count: `2`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140007ca0`
- `0x140008a54`
- `0x14000d66c`
- `0x140014bac`
- `0x14001526c`
- `0x140016524`
- `0x14001d7ac`
- `0x14001dcb8`
- `0x14001f110`

## callees

- `0x14000218c`
- `0x140006e18`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140006e85`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140006eb4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140006e85`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140006eb4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006ea0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006ea0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006e71`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006e71`

## pseudocode

```c
void __fastcall NatFreeBlockAndUpdateStateAllocationUsage(PNPAGED_LOOKASIDE_LIST Lookaside, PVOID Entry, int a3)
{
  KIRQL v6; // bl

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 65, WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids);
  }
  if ( StateAllocationBoundIsActive )
  {
    v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.Queue.Wcb.DeviceObject);
    ExFreeToNPagedLookasideList(Lookaside, Entry);
    CurrentStateAllocationInBytes -= a3;
    KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Queue.Wcb.DeviceObject, v6);
  }
  else
  {
    ExFreeToNPagedLookasideList(Lookaside, Entry);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 66, WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids);
  }
}

```

## disassembly

```asm
0x140006e18  push    rbx
0x140006e1a  push    rbp
0x140006e1b  push    rsi
0x140006e1c  push    rdi
0x140006e1d  push    r14
0x140006e1f  sub     rsp, 20h
0x140006e23  mov     ebp, r8d
0x140006e26  mov     rdi, rdx
0x140006e29  mov     rsi, rcx
0x140006e2c  mov     rcx, cs:WPP_GLOBAL_Control
0x140006e33  lea     r14, WPP_GLOBAL_Control
0x140006e3a  cmp     rcx, r14
0x140006e3d  jz      short loc_140006E61
0x140006e3f  mov     eax, [rcx+2Ch]
0x140006e42  test    al, 1
0x140006e44  jz      short loc_140006E61
0x140006e46  cmp     byte ptr [rcx+29h], 6
0x140006e4a  jb      short loc_140006E61
0x140006e4c  mov     rcx, [rcx+18h]
0x140006e50  lea     r8, WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids
0x140006e57  mov     edx, 41h ; 'A'
0x140006e5c  call    WPP_SF_
0x140006e61  cmp     cs:StateAllocationBoundIsActive, 0
0x140006e68  jz      short loc_140006EAE
0x140006e6a  lea     rcx, WPP_MAIN_CB.Queue+30h; SpinLock
0x140006e71  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140006e78  nop     dword ptr [rax+rax+00h]
0x140006e7d  mov     rdx, rdi; Entry
0x140006e80  mov     rcx, rsi; Lookaside
0x140006e83  mov     bl, al
0x140006e85  call    cs:__imp_ExFreeToNPagedLookasideList
0x140006e8c  nop     dword ptr [rax+rax+00h]
0x140006e91  sub     cs:CurrentStateAllocationInBytes, ebp
0x140006e97  lea     rcx, WPP_MAIN_CB.Queue+30h; SpinLock
0x140006e9e  mov     dl, bl; NewIrql
0x140006ea0  call    cs:__imp_KeReleaseSpinLock
0x140006ea7  nop     dword ptr [rax+rax+00h]
0x140006eac  jmp     short loc_140006EC0
0x140006eae  mov     rdx, rdi; Entry
0x140006eb1  mov     rcx, rsi; Lookaside
0x140006eb4  call    cs:__imp_ExFreeToNPagedLookasideList
0x140006ebb  nop     dword ptr [rax+rax+00h]
0x140006ec0  mov     rcx, cs:WPP_GLOBAL_Control
0x140006ec7  cmp     rcx, r14
0x140006eca  jz      short loc_140006EEE
0x140006ecc  mov     eax, [rcx+2Ch]
0x140006ecf  test    al, 1
0x140006ed1  jz      short loc_140006EEE
0x140006ed3  cmp     byte ptr [rcx+29h], 6
0x140006ed7  jb      short loc_140006EEE
0x140006ed9  mov     rcx, [rcx+18h]
0x140006edd  lea     r8, WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids
0x140006ee4  mov     edx, 42h ; 'B'
0x140006ee9  call    WPP_SF_
0x140006eee  add     rsp, 20h
0x140006ef2  pop     r14
0x140006ef4  pop     rdi
0x140006ef5  pop     rsi
0x140006ef6  pop     rbp
0x140006ef7  pop     rbx
0x140006ef8  retn
```
