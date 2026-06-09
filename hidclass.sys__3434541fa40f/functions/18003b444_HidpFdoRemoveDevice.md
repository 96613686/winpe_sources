# HidpFdoRemoveDevice

- ea: `0x18003b444`
- end: `0x18003b695`
- name: `HidpFdoRemoveDevice`
- size: `593`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18003f2b4`

## callees

- `0x18000a020`
- `0x18000c5c0`
- `0x18000ddc8`
- `0x18001025c`
- `0x180010814`
- `0x180013428`
- `0x180016188`
- `0x180017d98`
- `0x18001a0b8`
- `0x18001a890`
- `0x18001c8a0`
- `0x18001e8ec`
- `0x18003b444`
- `0x18003f8bc`
- `0x180040c74`

## import_xrefs

- `ntoskrnl!MmBadPointer` at `0x18003b5d1`
- `ntoskrnl!MmBadPointer` at `0x18003b5e9`
- `ntoskrnl!MmBadPointer` at `0x18003b625`
- `ntoskrnl!KeClearEvent` at `0x18003b562`
- `ntoskrnl!KeClearEvent` at `0x18003b562`
- `ntoskrnl!IoFreeIrp` at `0x18003b5dd`
- `ntoskrnl!IoFreeIrp` at `0x18003b5dd`
- `ntoskrnl!IoReleaseRemoveLockAndWaitEx` at `0x18003b5b1`
- `ntoskrnl!IoReleaseRemoveLockAndWaitEx` at `0x18003b5b1`
- `ntoskrnl!IoDetachDevice` at `0x18003b637`
- `ntoskrnl!IoDetachDevice` at `0x18003b637`
- `ntoskrnl!PoUnregisterPowerSettingCallback` at `0x18003b49e`
- `ntoskrnl!PoUnregisterPowerSettingCallback` at `0x18003b49e`
- `ntoskrnl!ExUnsubscribeWnfStateChange` at `0x18003b541`
- `ntoskrnl!ExUnsubscribeWnfStateChange` at `0x18003b541`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x18003b47a`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x18003b47a`

## string_xrefs

- `0x18003b57e`: `Remove Device`
- `0x18003b672`: `FDO OpenCount > 0 after IRP_MN_REMOVE_DEVICE`

## pseudocode

```c
__int64 __fastcall HidpFdoRemoveDevice(struct _IO_REMOVE_LOCK *a1, __int64 a2, __int64 a3)
{
  void *v5; // rcx
  char v6; // al
  int v7; // edx
  int v8; // r8d
  IRP *Flink; // rcx
  unsigned int v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // r8
  unsigned int updated; // eax
  __int64 v14; // rcx

  Feature_HPPICNS__private_IsEnabledDeviceUsageNoInline(a1, a2, a3);
  IoAcquireRemoveLockEx(a1 + 20, (PVOID)a2, File, 1u, 0x20u);
  HidpUnregisterSleepstudyBlockerReasons((KSPIN_LOCK *)&a1->Common.Removed);
  v5 = *(void **)&a1[19].Common.RemoveEvent.Header.Lock;
  if ( v5 )
  {
    v6 = PoUnregisterPowerSettingCallback(v5);
    *(_QWORD *)&a1[19].Common.RemoveEvent.Header.Lock = 0;
    LOBYTE(v7) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    if ( (_BYTE)v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qL(
        WPP_GLOBAL_Control->AttachedDevice,
        v7,
        v8,
        *(_QWORD *)&a1[21].Common.Removed,
        4,
        2,
        37,
        (__int64)WPP_7228c8f8fc8f39095d4c835c051ae1a4_Traceguids,
        *(_QWORD *)&a1->Common.Removed,
        v6);
    }
  }
  if ( a1[19].Common.RemoveEvent.Header.WaitListHead.Blink )
  {
    ExUnsubscribeWnfStateChange();
    a1[19].Common.RemoveEvent.Header.WaitListHead.Blink = 0;
  }
  KeClearEvent(&a1[57].Common.RemoveEvent);
  HIDSM_AddHidsmEvent(a1, 2003);
  HidpWaitForSignal(&a1[57].Common.RemoveEvent);
  DestroyPingPongs(a1);
  HidpFdoDrainDeviceResetNotifications(a1);
  HidpFdoDrainDevicePresenceNotifications(a1);
  IoReleaseRemoveLockAndWaitEx(a1 + 20, (PVOID)a2, 0x20u);
  HidpFdoUnRegisterWithPoFx(a1);
  Flink = (IRP *)a1[13].Common.RemoveEvent.Header.WaitListHead.Flink;
  if ( Flink && Flink != MmBadPointer )
  {
    IoFreeIrp(Flink);
    a1[13].Common.RemoveEvent.Header.WaitListHead.Flink = (_LIST_ENTRY *)MmBadPointer;
  }
  ++*(_BYTE *)(a2 + 67);
  *(_QWORD *)(a2 + 184) += 72LL;
  *(_DWORD *)(a2 + 48) = 0;
  v10 = HidpCallDriver(*(_QWORD *)&a1->Common.Removed, a2);
  DerefDriverExt(**(_QWORD **)&a1->Common.RemoveEvent.Header.Lock, v11, v12);
  *(_QWORD *)&a1->Common.RemoveEvent.Header.Lock = MmBadPointer;
  IoDetachDevice(*(PDEVICE_OBJECT *)&a1[-1].Common.RemoveEvent.Header.Lock);
  updated = HidpFdoUpdateOpenCounts((_DWORD)a1, 0, 0, 0, 0, 0);
  if ( updated )
    MicrosoftTelemetryAssertTriggeredArgsMsgKM(
      v14,
      updated,
      HIWORD(a1[3].Common.RemoveEvent.Header.SignalState) | (LOWORD(a1[3].Common.RemoveEvent.Header.SignalState) << 16),
      "FDO OpenCount > 0 after IRP_MN_REMOVE_DEVICE");
  else
    HidpCleanUpFdo((__int64)a1);
  return v10;
}

```

## disassembly

```asm
0x18003b444  push    rbx
0x18003b446  push    rbp
0x18003b447  push    rsi
0x18003b448  push    rdi
0x18003b449  sub     rsp, 58h
0x18003b44d  mov     rsi, rdx
0x18003b450  mov     rdi, rcx
0x18003b453  call    Feature_HPPICNS__private_IsEnabledDeviceUsageNoInline
0x18003b458  lea     rbp, [rdi+280h]
0x18003b45f  mov     [rsp+78h+RemlockSize], 20h ; ' '; RemlockSize
0x18003b467  mov     rcx, rbp; RemoveLock
0x18003b46a  lea     r8, File; File
0x18003b471  mov     r9d, 1; Line
0x18003b477  mov     rdx, rsi; Tag
0x18003b47a  call    cs:__imp_IoAcquireRemoveLockEx
0x18003b481  nop     dword ptr [rax+rax+00h]
0x18003b486  mov     rcx, rdi
0x18003b489  call    HidpUnregisterSleepstudyBlockerReasons
0x18003b48e  mov     rcx, [rdi+268h]; Handle
0x18003b495  test    rcx, rcx
0x18003b498  jz      loc_18003B535
0x18003b49e  call    cs:__imp_PoUnregisterPowerSettingCallback
0x18003b4a5  nop     dword ptr [rax+rax+00h]
0x18003b4aa  mov     qword ptr [rdi+268h], 0
0x18003b4b5  mov     r10, cs:WPP_GLOBAL_Control
0x18003b4bc  lea     rcx, WPP_GLOBAL_Control
0x18003b4c3  cmp     r10, rcx
0x18003b4c6  jz      short loc_18003B4DC
0x18003b4c8  mov     ecx, [r10+2Ch]
0x18003b4cc  test    cl, 2
0x18003b4cf  jz      short loc_18003B4DC
0x18003b4d1  cmp     byte ptr [r10+29h], 4
0x18003b4d6  jb      short loc_18003B4DC
0x18003b4d8  mov     dl, 1
0x18003b4da  jmp     short loc_18003B4DE
0x18003b4dc  xor     dl, dl
0x18003b4de  lea     rcx, WPP_RECORDER_INITIALIZED
0x18003b4e5  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x18003b4ec  setnz   r8b
0x18003b4f0  test    dl, dl
0x18003b4f2  jnz     short loc_18003B4F9
0x18003b4f4  test    r8b, r8b
0x18003b4f7  jz      short loc_18003B535
0x18003b4f9  mov     r9, [rdi+2A0h]
0x18003b500  mov     rcx, [r10+18h]
0x18003b504  mov     [rsp+78h+var_30], eax
0x18003b508  mov     rax, [rdi]
0x18003b50b  mov     [rsp+78h+var_38], rax
0x18003b510  lea     rax, WPP_7228c8f8fc8f39095d4c835c051ae1a4_Traceguids
0x18003b517  mov     [rsp+78h+var_40], rax
0x18003b51c  mov     [rsp+78h+var_48], 25h ; '%'
0x18003b523  mov     [rsp+78h+var_50], 2
0x18003b52b  mov     byte ptr [rsp+78h+RemlockSize], 4
0x18003b530  call    WPP_RECORDER_AND_TRACE_SF_qL
0x18003b535  mov     rcx, [rdi+278h]
0x18003b53c  test    rcx, rcx
0x18003b53f  jz      short loc_18003B558
0x18003b541  call    cs:__imp_ExUnsubscribeWnfStateChange
0x18003b548  nop     dword ptr [rax+rax+00h]
0x18003b54d  mov     qword ptr [rdi+278h], 0
0x18003b558  lea     rbx, [rdi+728h]
0x18003b55f  mov     rcx, rbx; Event
0x18003b562  call    cs:__imp_KeClearEvent
0x18003b569  nop     dword ptr [rax+rax+00h]
0x18003b56e  mov     edx, 7D3h
0x18003b573  mov     rcx, rdi
0x18003b576  call    HIDSM_AddHidsmEvent
0x18003b57b  mov     r8, rdi
0x18003b57e  lea     rdx, aRemoveDevice; "Remove Device"
0x18003b585  mov     rcx, rbx; Object
0x18003b588  call    HidpWaitForSignal
0x18003b58d  mov     rcx, rdi
0x18003b590  call    DestroyPingPongs
0x18003b595  mov     rcx, rdi
0x18003b598  call    HidpFdoDrainDeviceResetNotifications
0x18003b59d  mov     rcx, rdi
0x18003b5a0  call    HidpFdoDrainDevicePresenceNotifications
0x18003b5a5  mov     r8d, 20h ; ' '; RemlockSize
0x18003b5ab  mov     rdx, rsi; Tag
0x18003b5ae  mov     rcx, rbp; RemoveLock
0x18003b5b1  call    cs:__imp_IoReleaseRemoveLockAndWaitEx
0x18003b5b8  nop     dword ptr [rax+rax+00h]
0x18003b5bd  mov     rcx, rdi
0x18003b5c0  call    HidpFdoUnRegisterWithPoFx
0x18003b5c5  mov     rcx, [rdi+1B0h]; Irp
0x18003b5cc  test    rcx, rcx
0x18003b5cf  jz      short loc_18003B5FA
0x18003b5d1  mov     rax, cs:MmBadPointer
0x18003b5d8  cmp     rcx, [rax]
0x18003b5db  jz      short loc_18003B5FA
0x18003b5dd  call    cs:__imp_IoFreeIrp
0x18003b5e4  nop     dword ptr [rax+rax+00h]
0x18003b5e9  mov     rax, cs:MmBadPointer
0x18003b5f0  mov     rcx, [rax]
0x18003b5f3  mov     [rdi+1B0h], rcx
0x18003b5fa  inc     byte ptr [rsi+43h]
0x18003b5fd  mov     rdx, rsi
0x18003b600  add     qword ptr [rsi+0B8h], 48h ; 'H'
0x18003b608  mov     dword ptr [rsi+30h], 0
0x18003b60f  mov     rcx, [rdi]
0x18003b612  call    HidpCallDriver
0x18003b617  mov     rcx, [rdi+8]
0x18003b61b  mov     ebx, eax
0x18003b61d  mov     rcx, [rcx]
0x18003b620  call    DerefDriverExt
0x18003b625  mov     rcx, cs:MmBadPointer
0x18003b62c  mov     rdx, [rcx]
0x18003b62f  mov     [rdi+8], rdx
0x18003b633  mov     rcx, [rdi-18h]; TargetDevice
0x18003b637  call    cs:__imp_IoDetachDevice
0x18003b63e  nop     dword ptr [rax+rax+00h]
0x18003b643  xor     r9d, r9d
0x18003b646  mov     byte ptr [rsp+78h+var_50], 0
0x18003b64b  xor     r8d, r8d
0x18003b64e  mov     byte ptr [rsp+78h+RemlockSize], 0
0x18003b653  xor     edx, edx
0x18003b655  mov     rcx, rdi
0x18003b658  call    HidpFdoUpdateOpenCounts
0x18003b65d  mov     edx, eax
0x18003b65f  test    eax, eax
0x18003b661  jnz     short loc_18003B66D
0x18003b663  mov     rcx, rdi
0x18003b666  call    HidpCleanUpFdo
0x18003b66b  jmp     short loc_18003B689
0x18003b66d  movzx   r8d, word ptr [rdi+6Ch]; __annotation("Debug", "TelemetryAssert", "FALSE", "FDO OpenCount > 0 after IRP_MN_REMOVE_DEVICE")
0x18003b672  lea     r9, aFdoOpencount0A; "FDO OpenCount > 0 after IRP_MN_REMOVE_D"...
0x18003b679  movzx   eax, word ptr [rdi+6Eh]
0x18003b67d  shl     r8d, 10h
0x18003b681  or      r8d, eax
0x18003b684  call    MicrosoftTelemetryAssertTriggeredArgsMsgKM
0x18003b689  mov     eax, ebx
0x18003b68b  add     rsp, 58h
0x18003b68f  pop     rdi
0x18003b690  pop     rsi
0x18003b691  pop     rbp
0x18003b692  pop     rbx
0x18003b693  retn
```
