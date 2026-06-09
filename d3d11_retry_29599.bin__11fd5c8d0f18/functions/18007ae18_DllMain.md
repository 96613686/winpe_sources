# DllMain

- ea: `0x18007ae18`
- end: `0x18007ae79`
- name: `DllMain`
- size: `97`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800a9b94`

## callees

- `0x18007ae18`
- `0x18007ae80`
- `0x18007b210`
- `0x18007b32c`
- `0x18007b398`
- `0x18007b3cc`
- `0x18007b410`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18007ae32`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18007ae32`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  void *v3; // r9
  CTelemetryHelper *v6; // rcx
  DWORD v7; // r8d

  if ( !fdwReason )
  {
    TraceLoggingUnregister_EtwEventUnregister(qword_18022B790, fdwReason, lpvReserved);
    McGenEventUnregister_EtwEventUnregister();
    goto LABEL_6;
  }
  if ( fdwReason != 1 )
  {
LABEL_6:
    v7 = fdwReason;
    return CModule::DllMain((CModule *)hinstDLL, hinstDLL, v7, v3);
  }
  DisableThreadLibraryCalls(hinstDLL);
  McGenEventRegister_EtwEventRegister();
  CTelemetryHelper::Register((CTelemetryHelper *)&g_Telemetry);
  CTelemetryHelper::LogDllAttachEvent(v6);
  v7 = fdwReason;
  return CModule::DllMain((CModule *)hinstDLL, hinstDLL, v7, v3);
}

```

## disassembly

```asm
0x18007ae18  mov     [rsp+arg_0], rbx
0x18007ae1d  push    rdi
0x18007ae1e  sub     rsp, 20h
0x18007ae22  mov     edi, edx
0x18007ae24  mov     rbx, rcx
0x18007ae27  mov     eax, edx
0x18007ae29  test    edx, edx
0x18007ae2b  jz      short loc_18007AE63
0x18007ae2d  cmp     eax, 1
0x18007ae30  jnz     short loc_18007AE74
0x18007ae32  call    cs:__imp_DisableThreadLibraryCalls
0x18007ae38  call    McGenEventRegister_EtwEventRegister
0x18007ae3d  lea     rcx, ?g_Telemetry@@3VCD3D11TelemetryHelper@@A; this
0x18007ae44  call    ?Register@CTelemetryHelper@@UEAAJXZ; CTelemetryHelper::Register(void)
0x18007ae49  call    ?LogDllAttachEvent@CTelemetryHelper@@QEAAXXZ; CTelemetryHelper::LogDllAttachEvent(void)
0x18007ae4e  mov     r8d, edi; unsigned int
0x18007ae51  mov     rdx, rbx; HINSTANCE
0x18007ae54  mov     rbx, [rsp+28h+arg_0]
0x18007ae59  add     rsp, 20h
0x18007ae5d  pop     rdi
0x18007ae5e  jmp     ?DllMain@CModule@@QEAAHPEAUHINSTANCE__@@KPEAX@Z; CModule::DllMain(HINSTANCE__ *,ulong,void *)
0x18007ae63  mov     rcx, cs:qword_18022B790
0x18007ae6a  call    TraceLoggingUnregister_EtwEventUnregister
0x18007ae6f  call    McGenEventUnregister_EtwEventUnregister
0x18007ae74  mov     r8d, edi
0x18007ae77  jmp     short loc_18007AE51
```
