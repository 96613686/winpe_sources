# PcpCleanup

- ea: `0x14001e238`
- end: `0x14001e2d3`
- name: `PcpCleanup`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14001deb0`

## callees

- `0x14001e238`
- `0x14001e808`

## import_xrefs

- `NDIS!NdisFreeMemoryWithTag` at `0x14001e29f`
- `NDIS!NdisFreeMemoryWithTag` at `0x14001e29f`
- `NETIO!HfDestroyFactory` at `0x14001e2bc`
- `NETIO!HfDestroyFactory` at `0x14001e2bc`
- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x14001e24f`
- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x14001e269`
- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x14001e24f`
- `fwpkclnt!FwpiCalloutUnregisterAndDeleteByKey0` at `0x14001e269`
- `fwpkclnt!FwpmEngineClose0` at `0x14001e27c`
- `fwpkclnt!FwpmEngineClose0` at `0x14001e27c`

## pseudocode

```c
__int64 __fastcall PcpCleanup(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // r8
  __int64 v5; // r9

  if ( PcgWfpEngineHandle )
  {
    FwpiCalloutUnregisterAndDeleteByKey0(PcgWfpEngineHandle, &PcgWfpCalloutGuid, a3, a4);
    FwpiCalloutUnregisterAndDeleteByKey0(PcgWfpEngineHandle, &PcgWfpV6CalloutGuid, v4, v5);
    FwpmEngineClose0(PcgWfpEngineHandle);
    PcgWfpEngineHandle = 0;
  }
  NdisFreeMemoryWithTag(PcgRegistryPath.Buffer, 0x65676350u);
  if ( *(_QWORD *)&WPP_MAIN_CB.AlignmentRequirement )
    HfDestroyFactory(&WPP_MAIN_CB.AlignmentRequirement);
  return WppCleanupKm();
}

```

## disassembly

```asm
0x14001e238  sub     rsp, 28h
0x14001e23c  mov     rcx, cs:PcgWfpEngineHandle
0x14001e243  test    rcx, rcx
0x14001e246  jz      short loc_14001E293
0x14001e248  lea     rdx, PcgWfpCalloutGuid
0x14001e24f  call    cs:__imp_FwpiCalloutUnregisterAndDeleteByKey0
0x14001e256  nop     dword ptr [rax+rax+00h]
0x14001e25b  mov     rcx, cs:PcgWfpEngineHandle
0x14001e262  lea     rdx, PcgWfpV6CalloutGuid
0x14001e269  call    cs:__imp_FwpiCalloutUnregisterAndDeleteByKey0
0x14001e270  nop     dword ptr [rax+rax+00h]
0x14001e275  mov     rcx, cs:PcgWfpEngineHandle; engineHandle
0x14001e27c  call    cs:__imp_FwpmEngineClose0
0x14001e283  nop     dword ptr [rax+rax+00h]
0x14001e288  mov     cs:PcgWfpEngineHandle, 0
0x14001e293  mov     rcx, cs:PcgRegistryPath.Buffer; VirtualAddress
0x14001e29a  mov     edx, 65676350h; Tag
0x14001e29f  call    cs:__imp_NdisFreeMemoryWithTag
0x14001e2a6  nop     dword ptr [rax+rax+00h]
0x14001e2ab  cmp     qword ptr cs:WPP_MAIN_CB.AlignmentRequirement, 0
0x14001e2b3  jz      short loc_14001E2C8
0x14001e2b5  lea     rcx, WPP_MAIN_CB.AlignmentRequirement
0x14001e2bc  call    cs:__imp_HfDestroyFactory
0x14001e2c3  nop     dword ptr [rax+rax+00h]
0x14001e2c8  call    WppCleanupKm
0x14001e2cd  add     rsp, 28h
0x14001e2d1  retn
```
