# Dot11Unload(_DRIVER_OBJECT *)

- ea: `0x140038310`
- end: `0x1400383ba`
- name: `?Dot11Unload@@YAXPEAU_DRIVER_OBJECT@@@Z`
- size: `170`
- prototype: `void __fastcall(struct _DRIVER_OBJECT *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140036640`

## callees

- `0x14000d21c`
- `0x140038310`
- `0x1400385f4`
- `0x1400bc064`
- `0x1400bc7e8`
- `0x1400bccec`
- `0x1400bd1b4`

## import_xrefs

- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140038333`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140038346`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140038359`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14003836c`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140038333`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140038346`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140038359`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14003836c`

## pseudocode

```c
void __fastcall Dot11Unload(struct _DRIVER_OBJECT *a1)
{
  Dot11DeInitCrypto(a1);
  Dot11DeInitTimerModule();
  Dot11DeInitRegistry();
  if ( dword_1400B3240 )
  {
    ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&WPP_MAIN_CB.DeviceQueue);
    ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead);
    ExDeleteNPagedLookasideList(&Lookaside);
    ExDeleteNPagedLookasideList(&stru_1400B31C0);
    dword_1400B3240 = 0;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_efa9d851e01938244e0b3a4ce074e193_Traceguids);
  McGenEventUnregister_EtwUnregister();
  WppCleanupKm();
}

```

## disassembly

```asm
0x140038310  sub     rsp, 28h
0x140038314  call    Dot11DeInitCrypto
0x140038319  call    Dot11DeInitTimerModule
0x14003831e  call    Dot11DeInitRegistry
0x140038323  cmp     cs:dword_1400B3240, 0
0x14003832a  jz      short loc_140038382
0x14003832c  lea     rcx, WPP_MAIN_CB.DeviceQueue; Lookaside
0x140038333  call    cs:__imp_ExDeleteNPagedLookasideList
0x14003833a  nop     dword ptr [rax+rax+00h]
0x14003833f  lea     rcx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead; Lookaside
0x140038346  call    cs:__imp_ExDeleteNPagedLookasideList
0x14003834d  nop     dword ptr [rax+rax+00h]
0x140038352  lea     rcx, Lookaside; Lookaside
0x140038359  call    cs:__imp_ExDeleteNPagedLookasideList
0x140038360  nop     dword ptr [rax+rax+00h]
0x140038365  lea     rcx, stru_1400B31C0; Lookaside
0x14003836c  call    cs:__imp_ExDeleteNPagedLookasideList
0x140038373  nop     dword ptr [rax+rax+00h]
0x140038378  mov     cs:dword_1400B3240, 0
0x140038382  mov     rcx, cs:WPP_GLOBAL_Control
0x140038389  lea     rax, WPP_GLOBAL_Control
0x140038390  cmp     rcx, rax
0x140038393  jz      short loc_1400383AA
0x140038395  mov     rcx, [rcx+18h]
0x140038399  lea     r8, WPP_efa9d851e01938244e0b3a4ce074e193_Traceguids
0x1400383a0  mov     edx, 0Ch
0x1400383a5  call    WPP_SF_
0x1400383aa  call    McGenEventUnregister_EtwUnregister
0x1400383af  call    WppCleanupKm
0x1400383b4  add     rsp, 28h
0x1400383b8  retn
```
