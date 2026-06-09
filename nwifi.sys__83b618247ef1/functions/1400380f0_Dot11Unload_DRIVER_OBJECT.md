# Dot11Unload(_DRIVER_OBJECT *)

- ea: `0x1400380f0`
- end: `0x14003819a`
- name: `?Dot11Unload@@YAXPEAU_DRIVER_OBJECT@@@Z`
- size: `170`
- prototype: `void __fastcall(struct _DRIVER_OBJECT *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140036420`

## callees

- `0x14000d22c`
- `0x1400380f0`
- `0x1400383d4`
- `0x1400b9064`
- `0x1400b9838`
- `0x1400b9d3c`
- `0x1400ba204`

## import_xrefs

- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140038113`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140038126`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140038139`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14003814c`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140038113`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140038126`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140038139`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14003814c`

## pseudocode

```c
void __fastcall Dot11Unload(struct _DRIVER_OBJECT *a1)
{
  Dot11DeInitCrypto(a1);
  Dot11DeInitTimerModule();
  Dot11DeInitRegistry();
  if ( dword_1400B0200 )
  {
    ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&WPP_MAIN_CB.DeviceQueue);
    ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead);
    ExDeleteNPagedLookasideList(&Lookaside);
    ExDeleteNPagedLookasideList(&stru_1400B0180);
    dword_1400B0200 = 0;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_efa9d851e01938244e0b3a4ce074e193_Traceguids);
  McGenEventUnregister_EtwUnregister();
  WppCleanupKm();
}

```

## disassembly

```asm
0x1400380f0  sub     rsp, 28h
0x1400380f4  call    Dot11DeInitCrypto
0x1400380f9  call    Dot11DeInitTimerModule
0x1400380fe  call    Dot11DeInitRegistry
0x140038103  cmp     cs:dword_1400B0200, 0
0x14003810a  jz      short loc_140038162
0x14003810c  lea     rcx, WPP_MAIN_CB.DeviceQueue; Lookaside
0x140038113  call    cs:__imp_ExDeleteNPagedLookasideList
0x14003811a  nop     dword ptr [rax+rax+00h]
0x14003811f  lea     rcx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead; Lookaside
0x140038126  call    cs:__imp_ExDeleteNPagedLookasideList
0x14003812d  nop     dword ptr [rax+rax+00h]
0x140038132  lea     rcx, Lookaside; Lookaside
0x140038139  call    cs:__imp_ExDeleteNPagedLookasideList
0x140038140  nop     dword ptr [rax+rax+00h]
0x140038145  lea     rcx, stru_1400B0180; Lookaside
0x14003814c  call    cs:__imp_ExDeleteNPagedLookasideList
0x140038153  nop     dword ptr [rax+rax+00h]
0x140038158  mov     cs:dword_1400B0200, 0
0x140038162  mov     rcx, cs:WPP_GLOBAL_Control
0x140038169  lea     rax, WPP_GLOBAL_Control
0x140038170  cmp     rcx, rax
0x140038173  jz      short loc_14003818A
0x140038175  mov     rcx, [rcx+18h]
0x140038179  lea     r8, WPP_efa9d851e01938244e0b3a4ce074e193_Traceguids
0x140038180  mov     edx, 0Ch
0x140038185  call    WPP_SF_
0x14003818a  call    McGenEventUnregister_EtwUnregister
0x14003818f  call    WppCleanupKm
0x140038194  add     rsp, 28h
0x140038198  retn
```
