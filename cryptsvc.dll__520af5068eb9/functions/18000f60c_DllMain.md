# DllMain

- ea: `0x18000f60c`
- end: `0x18000f65b`
- name: `DllMain`
- size: `79`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000e164`

## callees

- `0x180001008`
- `0x18000c0c8`
- `0x18000f60c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000f622`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000f622`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x18000f63a`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x18000f63a`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  HPOWERNOTIFY v4; // rcx

  if ( fdwReason == 1 )
  {
    SafeAllocaInitialize(hinstDLL, fdwReason, lpvReserved);
    DisableThreadLibraryCalls(hinstDLL);
  }
  else if ( !fdwReason )
  {
    v4 = RegistrationHandle;
    if ( RegistrationHandle )
    {
      PowerSettingUnregisterNotification(RegistrationHandle);
      RegistrationHandle = 0;
    }
    TraceLoggingUnregister_EventUnregister(v4, *(_QWORD *)&fdwReason, lpvReserved);
  }
  return 1;
}

```

## disassembly

```asm
0x18000f60c  push    rbx
0x18000f60e  sub     rsp, 20h
0x18000f612  mov     rbx, rcx
0x18000f615  cmp     edx, 1
0x18000f618  jnz     short loc_18000F62A
0x18000f61a  call    SafeAllocaInitialize
0x18000f61f  mov     rcx, rbx; hLibModule
0x18000f622  call    cs:__imp_DisableThreadLibraryCalls
0x18000f628  jmp     short loc_18000F650
0x18000f62a  test    edx, edx
0x18000f62c  jnz     short loc_18000F650
0x18000f62e  mov     rcx, cs:RegistrationHandle; RegistrationHandle
0x18000f635  test    rcx, rcx
0x18000f638  jz      short loc_18000F64B
0x18000f63a  call    cs:__imp_PowerSettingUnregisterNotification
0x18000f640  mov     cs:RegistrationHandle, 0
0x18000f64b  call    TraceLoggingUnregister_EventUnregister
0x18000f650  mov     eax, 1
0x18000f655  add     rsp, 20h
0x18000f659  pop     rbx
0x18000f65a  retn
```
