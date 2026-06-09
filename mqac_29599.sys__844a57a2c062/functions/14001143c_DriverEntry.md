# DriverEntry

- ea: `0x14001143c`
- end: `0x14001155c`
- name: `DriverEntry`
- size: `288`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callers

- `0x140030010`

## callees

- `0x140001c34`
- `0x14001143c`
- `0x140011564`
- `0x1400209b8`
- `0x14002f008`
- `0x14002f08c`
- `0x14002f120`
- `0x14002f50c`
- `0x140030078`

## import_xrefs

- `ntoskrnl!EtwRegister` at `0x14001147e`
- `ntoskrnl!EtwRegister` at `0x14001147e`
- `ntoskrnl!EtwUnregister` at `0x140011529`
- `ntoskrnl!EtwUnregister` at `0x140011529`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  NTSTATUS v4; // eax
  NTSTATUS v5; // ebx

  wil_InitializeFeatureStaging();
  WPP_INIT_CONTROL_ARRAY();
  WppLoadTracingSupport();
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm();
  v4 = EtwRegister(&MSMQ_E2E, 0, 0, &g_e2eTraceHandle);
  if ( v4 < 0 )
  {
    if ( g_e2eTraceHandle )
      __int2c();
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->Queue.ListEntry.Blink,
        10,
        &WPP_3695f45fd0c43b36cea54aab790ddc1c_Traceguids,
        (unsigned int)v4);
    }
  }
  DriverObject->MajorFunction[0] = (PDRIVER_DISPATCH)ACCreate;
  DriverObject->MajorFunction[2] = (PDRIVER_DISPATCH)ACClose;
  DriverObject->MajorFunction[18] = (PDRIVER_DISPATCH)ACCleanup;
  DriverObject->MajorFunction[14] = (PDRIVER_DISPATCH)ACDeviceControl;
  DriverObject->DriverUnload = (PDRIVER_UNLOAD)ACUnload;
  v5 = ACInitializeSiloMonitor(DriverObject, RegistryPath);
  if ( v5 >= 0 )
    return 0;
  if ( g_e2eTraceHandle )
  {
    EtwUnregister(g_e2eTraceHandle);
    g_e2eTraceHandle = 0;
  }
  WppCleanupKm();
  wil_UninitializeFeatureStaging();
  return v5;
}

```

## disassembly

```asm
0x14001143c  mov     [rsp+arg_0], rbx
0x140011441  push    rdi
0x140011442  sub     rsp, 20h
0x140011446  mov     rdi, rdx
0x140011449  mov     rbx, rcx
0x14001144c  call    wil_InitializeFeatureStaging
0x140011451  call    WPP_INIT_CONTROL_ARRAY
0x140011456  call    WppLoadTracingSupport
0x14001145b  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x140011466  call    WppInitKm
0x14001146b  lea     r9, ?g_e2eTraceHandle@@3_KA; RegHandle
0x140011472  xor     r8d, r8d; CallbackContext
0x140011475  xor     edx, edx; EnableCallback
0x140011477  lea     rcx, MSMQ_E2E; ProviderId
0x14001147e  call    cs:__imp_EtwRegister
0x140011485  nop     dword ptr [rax+rax+00h]
0x14001148a  mov     r9d, eax
0x14001148d  test    eax, eax
0x14001148f  jns     short loc_1400114CC
0x140011491  cmp     cs:?g_e2eTraceHandle@@3_KA, 0; unsigned __int64 g_e2eTraceHandle
0x140011499  jz      short loc_14001149D
0x14001149b  int     2Ch; Windows NT - assertion failure
0x14001149d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400114a4  lea     rax, WPP_GLOBAL_Control
0x1400114ab  cmp     rcx, rax
0x1400114ae  jz      short loc_1400114CC
0x1400114b0  mov     eax, [rcx+6Ch]
0x1400114b3  test    al, 1
0x1400114b5  jz      short loc_1400114CC
0x1400114b7  mov     rcx, [rcx+58h]
0x1400114bb  lea     r8, WPP_3695f45fd0c43b36cea54aab790ddc1c_Traceguids
0x1400114c2  mov     edx, 0Ah
0x1400114c7  call    WPP_SF_d
0x1400114cc  lea     rax, ACCreate
0x1400114d3  mov     rdx, rdi; struct _UNICODE_STRING *
0x1400114d6  mov     [rbx+70h], rax
0x1400114da  mov     rcx, rbx; struct _DRIVER_OBJECT *
0x1400114dd  lea     rax, ACClose
0x1400114e4  mov     [rbx+80h], rax
0x1400114eb  lea     rax, ACCleanup
0x1400114f2  mov     [rbx+100h], rax
0x1400114f9  lea     rax, ACDeviceControl
0x140011500  mov     [rbx+0E0h], rax
0x140011507  lea     rax, ACUnload
0x14001150e  mov     [rbx+68h], rax
0x140011512  call    ?ACInitializeSiloMonitor@@YAJPEAU_DRIVER_OBJECT@@PEAU_UNICODE_STRING@@@Z; ACInitializeSiloMonitor(_DRIVER_OBJECT *,_UNICODE_STRING *)
0x140011517  mov     ebx, eax
0x140011519  test    eax, eax
0x14001151b  jns     short loc_14001154E
0x14001151d  mov     rcx, cs:?g_e2eTraceHandle@@3_KA; RegHandle
0x140011524  test    rcx, rcx
0x140011527  jz      short loc_140011540
0x140011529  call    cs:__imp_EtwUnregister
0x140011530  nop     dword ptr [rax+rax+00h]
0x140011535  mov     cs:?g_e2eTraceHandle@@3_KA, 0; unsigned __int64 g_e2eTraceHandle
0x140011540  call    WppCleanupKm
0x140011545  call    wil_UninitializeFeatureStaging
0x14001154a  mov     eax, ebx
0x14001154c  jmp     short loc_140011550
0x14001154e  xor     eax, eax
0x140011550  mov     rbx, [rsp+28h+arg_0]
0x140011555  add     rsp, 20h
0x140011559  pop     rdi
0x14001155a  retn
```
