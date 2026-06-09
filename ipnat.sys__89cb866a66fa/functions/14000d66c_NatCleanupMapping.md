# NatCleanupMapping

- ea: `0x14000d66c`
- end: `0x14000d8aa`
- name: `NatCleanupMapping`
- size: `574`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `9`
- callee_count: `6`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140007ca0`
- `0x14000d8b0`
- `0x14000e378`
- `0x14000e988`
- `0x140022320`
- `0x140024cc0`
- `0x14002597c`
- `0x14002665c`
- `0x1400275d0`

## callees

- `0x140001e78`
- `0x14000218c`
- `0x1400064c0`
- `0x140006e18`
- `0x14000ce94`
- `0x14000d66c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000d6da`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000d72f`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000d74c`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000d794`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000d7b1`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000d6da`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000d72f`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000d74c`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000d794`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000d7b1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d7f0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d7f0`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000d709`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000d71c`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000d76e`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000d781`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000d7da`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000d709`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000d71c`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000d76e`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000d781`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000d7da`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d6ba`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d6ba`

## pseudocode

```c
void __fastcall NatCleanupMapping(_QWORD *Entry)
{
  KIRQL v2; // di
  __int64 v3; // rcx
  __int64 v4; // rcx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_((__int64)WPP_GLOBAL_Control->AttachedDevice, 0xAu, (__int64)WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids);
  }
  v2 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.Dpc.DeferredRoutine);
  if ( Entry[26] )
  {
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)&WPP_MAIN_CB.Dpc.DeferredContext);
    NatMappingDetachDirector(Entry[26], Entry[27], Entry, 1);
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)&WPP_MAIN_CB.Dpc.DeferredContext);
  }
  KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)&WPP_MAIN_CB.Dpc.DeferredRoutine);
  KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceQueue);
  if ( Entry[22] )
  {
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceQueue.DeviceListHead);
    NatMappingDetachEditor(Entry[22], Entry);
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceQueue.DeviceListHead);
  }
  KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceQueue);
  KeAcquireSpinLockAtDpcLevel(&InterfaceLock);
  if ( Entry[18] )
  {
    KeAcquireSpinLockAtDpcLevel(&InterfaceMappingLock);
    NatMappingDetachInterface(Entry[18], Entry[19], Entry);
    KeReleaseSpinLockFromDpcLevel(&InterfaceMappingLock);
  }
  KeReleaseSpinLock(&InterfaceLock, v2);
  v3 = 3LL * (Entry[8] & 0x3FF);
  LODWORD(MappingCache[v3]) = 0;
  MappingCache[v3 + 1] = 0;
  MappingCache[v3 + 2] = 0;
  v4 = 3LL * (Entry[9] & 0x3FF);
  LODWORD(qword_1400382A0[v4]) = 0;
  qword_1400382A0[v4 + 1] = 0;
  qword_1400382A0[v4 + 2] = 0;
  NatFreeBlockAndUpdateStateAllocationUsage(&MappingLookasideList, Entry, 368);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_((__int64)WPP_GLOBAL_Control->AttachedDevice, 0xBu, (__int64)WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids);
  }
}

```

## disassembly

```asm
0x14000d66c  mov     [rsp+arg_0], rbx
0x14000d671  mov     [rsp+arg_8], rbp
0x14000d676  push    rdi
0x14000d677  sub     rsp, 20h
0x14000d67b  mov     rbx, rcx
0x14000d67e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d685  lea     rbp, WPP_GLOBAL_Control
0x14000d68c  cmp     rcx, rbp
0x14000d68f  jz      short loc_14000D6B3
0x14000d691  mov     eax, [rcx+2Ch]
0x14000d694  test    al, 1
0x14000d696  jz      short loc_14000D6B3
0x14000d698  cmp     byte ptr [rcx+29h], 6
0x14000d69c  jb      short loc_14000D6B3
0x14000d69e  mov     rcx, [rcx+18h]
0x14000d6a2  lea     r8, WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids
0x14000d6a9  mov     edx, 0Ah
0x14000d6ae  call    WPP_SF_
0x14000d6b3  lea     rcx, WPP_MAIN_CB.Dpc.DeferredRoutine; SpinLock
0x14000d6ba  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000d6c1  nop     dword ptr [rax+rax+00h]
0x14000d6c6  cmp     qword ptr [rbx+0D0h], 0
0x14000d6ce  mov     dil, al
0x14000d6d1  jz      short loc_14000D715
0x14000d6d3  lea     rcx, WPP_MAIN_CB.Dpc.DeferredContext; SpinLock
0x14000d6da  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14000d6e1  nop     dword ptr [rax+rax+00h]
0x14000d6e6  mov     rdx, [rbx+0D8h]
0x14000d6ed  mov     r9d, 1
0x14000d6f3  mov     rcx, [rbx+0D0h]
0x14000d6fa  mov     r8, rbx
0x14000d6fd  call    NatMappingDetachDirector
0x14000d702  lea     rcx, WPP_MAIN_CB.Dpc.DeferredContext; SpinLock
0x14000d709  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000d710  nop     dword ptr [rax+rax+00h]
0x14000d715  lea     rcx, WPP_MAIN_CB.Dpc.DeferredRoutine; SpinLock
0x14000d71c  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000d723  nop     dword ptr [rax+rax+00h]
0x14000d728  lea     rcx, WPP_MAIN_CB.DeviceQueue; SpinLock
0x14000d72f  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14000d736  nop     dword ptr [rax+rax+00h]
0x14000d73b  cmp     qword ptr [rbx+0B0h], 0
0x14000d743  jz      short loc_14000D77A
0x14000d745  lea     rcx, WPP_MAIN_CB.DeviceQueue.DeviceListHead; SpinLock
0x14000d74c  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14000d753  nop     dword ptr [rax+rax+00h]
0x14000d758  mov     rcx, [rbx+0B0h]
0x14000d75f  mov     rdx, rbx
0x14000d762  call    NatMappingDetachEditor
0x14000d767  lea     rcx, WPP_MAIN_CB.DeviceQueue.DeviceListHead; SpinLock
0x14000d76e  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000d775  nop     dword ptr [rax+rax+00h]
0x14000d77a  lea     rcx, WPP_MAIN_CB.DeviceQueue; SpinLock
0x14000d781  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000d788  nop     dword ptr [rax+rax+00h]
0x14000d78d  lea     rcx, InterfaceLock; SpinLock
0x14000d794  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14000d79b  nop     dword ptr [rax+rax+00h]
0x14000d7a0  cmp     qword ptr [rbx+90h], 0
0x14000d7a8  jz      short loc_14000D7E6
0x14000d7aa  lea     rcx, InterfaceMappingLock; SpinLock
0x14000d7b1  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14000d7b8  nop     dword ptr [rax+rax+00h]
0x14000d7bd  mov     rdx, [rbx+98h]
0x14000d7c4  mov     r8, rbx
0x14000d7c7  mov     rcx, [rbx+90h]
0x14000d7ce  call    NatMappingDetachInterface
0x14000d7d3  lea     rcx, InterfaceMappingLock; SpinLock
0x14000d7da  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000d7e1  nop     dword ptr [rax+rax+00h]
0x14000d7e6  mov     dl, dil; NewIrql
0x14000d7e9  lea     rcx, InterfaceLock; SpinLock
0x14000d7f0  call    cs:__imp_KeReleaseSpinLock
0x14000d7f7  nop     dword ptr [rax+rax+00h]
0x14000d7fc  mov     eax, [rbx+40h]
0x14000d7ff  mov     r8d, 3FFh
0x14000d805  mov     rdx, cs:off_14002F070
0x14000d80c  and     eax, r8d
0x14000d80f  lea     rcx, [rax+rax*2]
0x14000d813  mov     dword ptr [rdx+rcx*8], 0
0x14000d81a  mov     qword ptr [rdx+rcx*8+8], 0
0x14000d823  mov     qword ptr [rdx+rcx*8+10h], 0
0x14000d82c  mov     eax, [rbx+48h]
0x14000d82f  mov     rdx, cs:off_14002F088
0x14000d836  and     eax, r8d
0x14000d839  mov     r8d, 170h
0x14000d83f  lea     rcx, [rax+rax*2]
0x14000d843  mov     dword ptr [rdx+rcx*8], 0
0x14000d84a  mov     qword ptr [rdx+rcx*8+8], 0
0x14000d853  mov     qword ptr [rdx+rcx*8+10h], 0
0x14000d85c  mov     rdx, rbx; Entry
0x14000d85f  lea     rcx, MappingLookasideList; Lookaside
0x14000d866  call    NatFreeBlockAndUpdateStateAllocationUsage
0x14000d86b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d872  cmp     rcx, rbp
0x14000d875  jz      short loc_14000D899
0x14000d877  mov     eax, [rcx+2Ch]
0x14000d87a  test    al, 1
0x14000d87c  jz      short loc_14000D899
0x14000d87e  cmp     byte ptr [rcx+29h], 6
0x14000d882  jb      short loc_14000D899
0x14000d884  mov     rcx, [rcx+18h]
0x14000d888  lea     r8, WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids
0x14000d88f  mov     edx, 0Bh
0x14000d894  call    WPP_SF_
0x14000d899  mov     rbx, [rsp+28h+arg_0]
0x14000d89e  mov     rbp, [rsp+28h+arg_8]
0x14000d8a3  add     rsp, 20h
0x14000d8a7  pop     rdi
0x14000d8a8  retn
```
