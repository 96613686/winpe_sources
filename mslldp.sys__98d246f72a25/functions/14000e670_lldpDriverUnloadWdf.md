# lldpDriverUnloadWdf

- ea: `0x14000e670`
- end: `0x14000e6d9`
- name: `lldpDriverUnloadWdf`
- size: `105`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140013350`

## callees

- `0x140005a24`
- `0x140006670`
- `0x14000e670`
- `0x14000e6e0`
- `0x14000ee64`
- `0x14000f8f4`
- `0x140010aa8`

## import_xrefs

- `NDIS!NdisDeregisterProtocolDriver` at `0x14000e694`
- `NDIS!NdisDeregisterProtocolDriver` at `0x14000e694`

## pseudocode

```c
__int64 __fastcall lldpDriverUnloadWdf(__int64 a1)
{
  lldpMarkDriverUnloading();
  lldpNmrDeregisterProvider();
  lldpDereferencePacketPool();
  if ( WPP_MAIN_CB.Queue.ListEntry.Flink )
  {
    NdisDeregisterProtocolDriver(WPP_MAIN_CB.Queue.ListEntry.Flink);
    WPP_MAIN_CB.Queue.ListEntry.Flink = 0;
  }
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 944))(WdfDriverGlobals, a1);
  lldpUnloadDriverCore();
  return wil_UninitializeFeatureStaging();
}

```

## disassembly

```asm
0x14000e670  push    rbx
0x14000e672  sub     rsp, 20h
0x14000e676  mov     rbx, rcx
0x14000e679  call    lldpMarkDriverUnloading
0x14000e67e  call    lldpNmrDeregisterProvider
0x14000e683  call    lldpDereferencePacketPool
0x14000e688  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue; NdisProtocolHandle
0x14000e68f  test    rcx, rcx
0x14000e692  jz      short loc_14000E6AB
0x14000e694  call    cs:__imp_NdisDeregisterProtocolDriver
0x14000e69b  nop     dword ptr [rax+rax+00h]
0x14000e6a0  mov     qword ptr cs:WPP_MAIN_CB.Queue, 0
0x14000e6ab  mov     rax, cs:WdfFunctions_01015
0x14000e6b2  mov     rdx, rbx
0x14000e6b5  mov     rcx, cs:WdfDriverGlobals
0x14000e6bc  mov     rax, [rax+3B0h]
0x14000e6c3  call    _guard_dispatch_icall
0x14000e6c8  call    lldpUnloadDriverCore
0x14000e6cd  call    wil_UninitializeFeatureStaging
0x14000e6d2  add     rsp, 20h
0x14000e6d6  pop     rbx
0x14000e6d7  retn
```
