# NatAllocateBlockWithLimitCheck

- ea: `0x140006a08`
- end: `0x140006b02`
- name: `NatAllocateBlockWithLimitCheck`
- size: `250`
- prototype: `__int64 __fastcall(PNPAGED_LOOKASIDE_LIST Lookaside)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140008a54`
- `0x14000d8b0`
- `0x140014bac`
- `0x14001d05c`

## callees

- `0x14000218c`
- `0x140006a08`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140006a85`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140006ab9`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140006a85`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140006ab9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006aa8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006aa8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006a61`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006a61`

## pseudocode

```c
void __fastcall NatAllocateBlockWithLimitCheck(PNPAGED_LOOKASIDE_LIST Lookaside, PVOID *a2, int a3)
{
  KIRQL v6; // bp
  PVOID v7; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 63, WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids);
  }
  if ( StateAllocationBoundIsActive )
  {
    v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.Queue.Wcb.DeviceObject);
    if ( a3 + CurrentStateAllocationInBytes >= (unsigned int)MaxStateAllocationInBytes )
    {
      v7 = 0;
    }
    else
    {
      v7 = ExAllocateFromNPagedLookasideList(Lookaside);
      CurrentStateAllocationInBytes += a3;
    }
    *a2 = v7;
    KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Queue.Wcb.DeviceObject, v6);
  }
  else
  {
    *a2 = ExAllocateFromNPagedLookasideList(Lookaside);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 64, WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids);
  }
}

```

## disassembly

```asm
0x140006a08  push    rbx
0x140006a0a  push    rbp
0x140006a0b  push    rsi
0x140006a0c  push    rdi
0x140006a0d  push    r14
0x140006a0f  sub     rsp, 20h
0x140006a13  mov     esi, r8d
0x140006a16  mov     rbx, rdx
0x140006a19  mov     rdi, rcx
0x140006a1c  mov     rcx, cs:WPP_GLOBAL_Control
0x140006a23  lea     r14, WPP_GLOBAL_Control
0x140006a2a  cmp     rcx, r14
0x140006a2d  jz      short loc_140006A51
0x140006a2f  mov     eax, [rcx+2Ch]
0x140006a32  test    al, 1
0x140006a34  jz      short loc_140006A51
0x140006a36  cmp     byte ptr [rcx+29h], 6
0x140006a3a  jb      short loc_140006A51
0x140006a3c  mov     rcx, [rcx+18h]
0x140006a40  lea     r8, WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids
0x140006a47  mov     edx, 3Fh ; '?'
0x140006a4c  call    WPP_SF_
0x140006a51  cmp     cs:StateAllocationBoundIsActive, 0
0x140006a58  jz      short loc_140006AB6
0x140006a5a  lea     rcx, WPP_MAIN_CB.Queue+30h; SpinLock
0x140006a61  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140006a68  nop     dword ptr [rax+rax+00h]
0x140006a6d  mov     edx, cs:CurrentStateAllocationInBytes
0x140006a73  mov     bpl, al
0x140006a76  mov     ecx, cs:MaxStateAllocationInBytes
0x140006a7c  add     edx, esi
0x140006a7e  cmp     edx, ecx
0x140006a80  jnb     short loc_140006A99
0x140006a82  mov     rcx, rdi; Lookaside
0x140006a85  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140006a8c  nop     dword ptr [rax+rax+00h]
0x140006a91  add     cs:CurrentStateAllocationInBytes, esi
0x140006a97  jmp     short loc_140006A9B
0x140006a99  xor     eax, eax
0x140006a9b  mov     dl, bpl; NewIrql
0x140006a9e  mov     [rbx], rax
0x140006aa1  lea     rcx, WPP_MAIN_CB.Queue+30h; SpinLock
0x140006aa8  call    cs:__imp_KeReleaseSpinLock
0x140006aaf  nop     dword ptr [rax+rax+00h]
0x140006ab4  jmp     short loc_140006AC8
0x140006ab6  mov     rcx, rdi; Lookaside
0x140006ab9  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140006ac0  nop     dword ptr [rax+rax+00h]
0x140006ac5  mov     [rbx], rax
0x140006ac8  mov     rcx, cs:WPP_GLOBAL_Control
0x140006acf  cmp     rcx, r14
0x140006ad2  jz      short loc_140006AF6
0x140006ad4  mov     eax, [rcx+2Ch]
0x140006ad7  test    al, 1
0x140006ad9  jz      short loc_140006AF6
0x140006adb  cmp     byte ptr [rcx+29h], 6
0x140006adf  jb      short loc_140006AF6
0x140006ae1  mov     rcx, [rcx+18h]
0x140006ae5  lea     r8, WPP_3dced903be7c36e6d4794e339c1e51b4_Traceguids
0x140006aec  mov     edx, 40h ; '@'
0x140006af1  call    WPP_SF_
0x140006af6  add     rsp, 20h
0x140006afa  pop     r14
0x140006afc  pop     rdi
0x140006afd  pop     rsi
0x140006afe  pop     rbp
0x140006aff  pop     rbx
0x140006b00  retn
```
