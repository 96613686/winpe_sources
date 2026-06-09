# NcaConfigMgrPolUpdateShutdown

- ea: `0x180006b10`
- end: `0x180006c1f`
- name: `NcaConfigMgrPolUpdateShutdown`
- size: `271`
- prototype: `ULONG()`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180006940`

## callees

- `0x180004f04`
- `0x180006544`
- `0x180006b10`
- `0x18000b3a8`
- `0x18000b9f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180006b67`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180006b67`

## string_xrefs

- `0x180006b4d`: `ConfigMgrPolUpdate`
- `0x180006bde`: `ConfigMgrPolUpdate`

## pseudocode

```c
ULONG NcaConfigMgrPolUpdateShutdown()
{
  PVOID v0; // rcx
  ULONG result; // eax
  LPVOID v2; // rcx

  v0 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids);
  if ( (Microsoft_Windows_NcasvcEnableBits & 1) != 0 )
    McTemplateU0z_EventWriteTransfer((__int64)v0, (const EVENT_DESCRIPTOR *)ModuleShutdownStart, L"ConfigMgrPolUpdate");
  result = SetEvent(gNcaMain);
  v2 = gNcaConfigMgr;
  if ( gNcaConfigMgr )
  {
    result = NcaGPTriggerUnregisterWait(gNcaConfigMgr);
    gNcaConfigMgr = 0;
  }
  if ( qword_180028BB8 )
  {
    result = NcaSrcLnkdTriggerUnregisterWait(&stru_180028F20, qword_180028BB8);
    qword_180028BB8 = 0;
  }
  if ( qword_180028BC0 )
  {
    result = NcaSrcLnkdTriggerUnregisterWait(&stru_180029900, qword_180028BC0);
    qword_180028BB8 = 0;
  }
  if ( (Microsoft_Windows_NcasvcEnableBits & 1) != 0 )
    result = McTemplateU0z_EventWriteTransfer(
               (__int64)v2,
               (const EVENT_DESCRIPTOR *)ModuleShutdownEnd,
               L"ConfigMgrPolUpdate");
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    return WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids);
  return result;
}

```

## disassembly

```asm
0x180006b10  push    rdi
0x180006b12  sub     rsp, 20h
0x180006b16  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b1d  lea     rdi, WPP_GLOBAL_Control
0x180006b24  cmp     rcx, rdi
0x180006b27  jz      short loc_180006B44
0x180006b29  test    byte ptr [rcx+1Ch], 8
0x180006b2d  jz      short loc_180006B44
0x180006b2f  mov     rcx, [rcx+10h]
0x180006b33  lea     r8, WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids
0x180006b3a  mov     edx, 15h
0x180006b3f  call    WPP_SF_
0x180006b44  test    cs:Microsoft_Windows_NcasvcEnableBits, 1
0x180006b4b  jz      short loc_180006B60
0x180006b4d  lea     r8, aConfigmgrpolup; "ConfigMgrPolUpdate"
0x180006b54  lea     rdx, ModuleShutdownStart
0x180006b5b  call    McTemplateU0z_EventWriteTransfer
0x180006b60  mov     rcx, cs:?gNcaMain@@3UNCA_MAIN_COMPONENT_@@A; hEvent
0x180006b67  call    cs:__imp_SetEvent
0x180006b6e  nop     dword ptr [rax+rax+00h]
0x180006b73  mov     rcx, cs:?gNcaConfigMgr@@3UNCA_CONFIG_MGR_COMPONENT_@@A; lpMem
0x180006b7a  test    rcx, rcx
0x180006b7d  jz      short loc_180006B8F
0x180006b7f  call    NcaGPTriggerUnregisterWait
0x180006b84  mov     cs:?gNcaConfigMgr@@3UNCA_CONFIG_MGR_COMPONENT_@@A, 0; NCA_CONFIG_MGR_COMPONENT_ gNcaConfigMgr
0x180006b8f  mov     rdx, cs:qword_180028BB8; struct _LIST_ENTRY *
0x180006b96  test    rdx, rdx
0x180006b99  jz      short loc_180006BB2
0x180006b9b  lea     rcx, stru_180028F20; lpCriticalSection
0x180006ba2  call    NcaSrcLnkdTriggerUnregisterWait
0x180006ba7  mov     cs:qword_180028BB8, 0
0x180006bb2  mov     rdx, cs:qword_180028BC0; struct _LIST_ENTRY *
0x180006bb9  test    rdx, rdx
0x180006bbc  jz      short loc_180006BD5
0x180006bbe  lea     rcx, stru_180029900; lpCriticalSection
0x180006bc5  call    NcaSrcLnkdTriggerUnregisterWait
0x180006bca  mov     cs:qword_180028BB8, 0
0x180006bd5  test    cs:Microsoft_Windows_NcasvcEnableBits, 1
0x180006bdc  jz      short loc_180006BF1
0x180006bde  lea     r8, aConfigmgrpolup; "ConfigMgrPolUpdate"
0x180006be5  lea     rdx, ModuleShutdownEnd
0x180006bec  call    McTemplateU0z_EventWriteTransfer
0x180006bf1  mov     rcx, cs:WPP_GLOBAL_Control
0x180006bf8  cmp     rcx, rdi
0x180006bfb  jz      short loc_180006C18
0x180006bfd  test    byte ptr [rcx+1Ch], 8
0x180006c01  jz      short loc_180006C18
0x180006c03  mov     rcx, [rcx+10h]
0x180006c07  lea     r8, WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids
0x180006c0e  mov     edx, 16h
0x180006c13  call    WPP_SF_
0x180006c18  add     rsp, 20h
0x180006c1c  pop     rdi
0x180006c1d  retn
```
