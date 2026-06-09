# DoDerefMiniportAdapterBlockWork

- ea: `0x1400026f0`
- end: `0x1400027c3`
- name: `DoDerefMiniportAdapterBlockWork`
- size: `211`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400026f0`
- `0x140003e08`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140002763`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002763`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002740`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002740`
- `NDIS!NdisMPauseComplete` at `0x140002776`
- `NDIS!NdisMPauseComplete` at `0x140002776`

## pseudocode

```c
void __fastcall DoDerefMiniportAdapterBlockWork(__int64 a1)
{
  KIRQL v2; // al

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_03516810ed2635a74cea1971954143d2_Traceguids);
  }
  v2 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 - 184));
  *(_DWORD *)(a1 + 16) = 1;
  *(_BYTE *)(a1 - 176) = v2;
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 - 184), v2);
  NdisMPauseComplete(*(NDIS_HANDLE *)(a1 - 192));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_03516810ed2635a74cea1971954143d2_Traceguids);
  }
}

```

## disassembly

```asm
0x1400026f0  mov     [rsp+arg_0], rbx
0x1400026f5  mov     [rsp+arg_8], rsi
0x1400026fa  push    rdi
0x1400026fb  sub     rsp, 20h
0x1400026ff  mov     rbx, rcx
0x140002702  mov     rcx, cs:WPP_GLOBAL_Control
0x140002709  lea     rsi, WPP_GLOBAL_Control
0x140002710  cmp     rcx, rsi
0x140002713  jz      short loc_140002739
0x140002715  test    dword ptr [rcx+2Ch], 800h
0x14000271c  jz      short loc_140002739
0x14000271e  cmp     byte ptr [rcx+29h], 2
0x140002722  jb      short loc_140002739
0x140002724  mov     rcx, [rcx+18h]
0x140002728  lea     r8, WPP_03516810ed2635a74cea1971954143d2_Traceguids
0x14000272f  mov     edx, 0Ah
0x140002734  call    WPP_SF_
0x140002739  lea     rcx, [rbx-0B8h]; SpinLock
0x140002740  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002747  nop     dword ptr [rax+rax+00h]
0x14000274c  lea     rcx, [rbx-0B8h]; SpinLock
0x140002753  mov     dword ptr [rbx+10h], 1
0x14000275a  movzx   edx, al; NewIrql
0x14000275d  mov     [rbx-0B0h], al
0x140002763  call    cs:__imp_KeReleaseSpinLock
0x14000276a  nop     dword ptr [rax+rax+00h]
0x14000276f  mov     rcx, [rbx-0C0h]; MiniportAdapterHandle
0x140002776  call    cs:__imp_NdisMPauseComplete
0x14000277d  nop     dword ptr [rax+rax+00h]
0x140002782  mov     rcx, cs:WPP_GLOBAL_Control
0x140002789  cmp     rcx, rsi
0x14000278c  jz      short loc_1400027B2
0x14000278e  test    dword ptr [rcx+2Ch], 800h
0x140002795  jz      short loc_1400027B2
0x140002797  cmp     byte ptr [rcx+29h], 2
0x14000279b  jb      short loc_1400027B2
0x14000279d  mov     rcx, [rcx+18h]
0x1400027a1  lea     r8, WPP_03516810ed2635a74cea1971954143d2_Traceguids
0x1400027a8  mov     edx, 0Bh
0x1400027ad  call    WPP_SF_
0x1400027b2  mov     rbx, [rsp+28h+arg_0]
0x1400027b7  mov     rsi, [rsp+28h+arg_8]
0x1400027bc  add     rsp, 20h
0x1400027c0  pop     rdi
0x1400027c1  retn
```
