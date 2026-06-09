# NcaConfigMgrShutdown

- ea: `0x180006c60`
- end: `0x180006d64`
- name: `NcaConfigMgrShutdown`
- size: `260`
- prototype: `ULONG()`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800067e0`

## callees

- `0x180004f04`
- `0x180005d04`
- `0x180006544`
- `0x180006c60`
- `0x18001cc3e`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180006cbb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180006cbb`

## string_xrefs

- `0x180006ca1`: `ConfigMgr`
- `0x180006d1e`: `ConfigMgr`

## pseudocode

```c
ULONG NcaConfigMgrShutdown()
{
  PVOID v0; // rcx
  PVOID *v1; // rbx
  ULONG result; // eax
  __int64 v3; // rcx

  v0 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids);
  if ( (Microsoft_Windows_NcasvcEnableBits & 1) != 0 )
    McTemplateU0z_EventWriteTransfer((__int64)v0, (const EVENT_DESCRIPTOR *)ModuleShutdownStart, L"ConfigMgr");
  SetEvent(gNcaMain);
  NcaConfigMgrPolicyEmpty((struct NCA_POLICY_ *)&xmmword_180028BC8);
  v1 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_99360b57fc053e6d111dc188653e9d6e_Traceguids);
    v1 = (PVOID *)WPP_GLOBAL_Control;
  }
  result = (unsigned int)memset_0(&gNcaConfigMgr, 0, 0x90u);
  if ( (Microsoft_Windows_NcasvcEnableBits & 1) != 0 )
  {
    result = McTemplateU0z_EventWriteTransfer(v3, (const EVENT_DESCRIPTOR *)ModuleShutdownEnd, L"ConfigMgr");
    v1 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v1 != &WPP_GLOBAL_Control && (*((_BYTE *)v1 + 28) & 8) != 0 )
    return WPP_SF_(v1[2], 20, WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids);
  return result;
}

```

## disassembly

```asm
0x180006c60  mov     [rsp+arg_0], rbx
0x180006c65  push    rsi
0x180006c66  sub     rsp, 20h
0x180006c6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180006c71  lea     rsi, WPP_GLOBAL_Control
0x180006c78  cmp     rcx, rsi
0x180006c7b  jz      short loc_180006C98
0x180006c7d  test    byte ptr [rcx+1Ch], 8
0x180006c81  jz      short loc_180006C98
0x180006c83  mov     rcx, [rcx+10h]
0x180006c87  lea     r8, WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids
0x180006c8e  mov     edx, 13h
0x180006c93  call    WPP_SF_
0x180006c98  test    cs:Microsoft_Windows_NcasvcEnableBits, 1
0x180006c9f  jz      short loc_180006CB4
0x180006ca1  lea     r8, aConfigmgr; "ConfigMgr"
0x180006ca8  lea     rdx, ModuleShutdownStart
0x180006caf  call    McTemplateU0z_EventWriteTransfer
0x180006cb4  mov     rcx, cs:?gNcaMain@@3UNCA_MAIN_COMPONENT_@@A; hEvent
0x180006cbb  call    cs:__imp_SetEvent
0x180006cc2  nop     dword ptr [rax+rax+00h]
0x180006cc7  lea     rcx, xmmword_180028BC8; struct NCA_POLICY_ *
0x180006cce  call    ?NcaConfigMgrPolicyEmpty@@YAXPEAUNCA_POLICY_@@@Z; NcaConfigMgrPolicyEmpty(NCA_POLICY_ *)
0x180006cd3  mov     rbx, cs:WPP_GLOBAL_Control
0x180006cda  cmp     rbx, rsi
0x180006cdd  jz      short loc_180006D01
0x180006cdf  test    byte ptr [rbx+1Ch], 8
0x180006ce3  jz      short loc_180006D01
0x180006ce5  mov     rcx, [rbx+10h]
0x180006ce9  lea     r8, WPP_99360b57fc053e6d111dc188653e9d6e_Traceguids
0x180006cf0  mov     edx, 26h ; '&'
0x180006cf5  call    WPP_SF_
0x180006cfa  mov     rbx, cs:WPP_GLOBAL_Control
0x180006d01  xor     edx, edx; Val
0x180006d03  lea     rcx, ?gNcaConfigMgr@@3UNCA_CONFIG_MGR_COMPONENT_@@A; void *
0x180006d0a  mov     r8d, 90h; Size
0x180006d10  call    memset_0
0x180006d15  test    cs:Microsoft_Windows_NcasvcEnableBits, 1
0x180006d1c  jz      short loc_180006D38
0x180006d1e  lea     r8, aConfigmgr; "ConfigMgr"
0x180006d25  lea     rdx, ModuleShutdownEnd
0x180006d2c  call    McTemplateU0z_EventWriteTransfer
0x180006d31  mov     rbx, cs:WPP_GLOBAL_Control
0x180006d38  cmp     rbx, rsi
0x180006d3b  jz      short loc_180006D58
0x180006d3d  test    byte ptr [rbx+1Ch], 8
0x180006d41  jz      short loc_180006D58
0x180006d43  mov     rcx, [rbx+10h]
0x180006d47  lea     r8, WPP_20ecdd7472aa32d31d1847316c3804e5_Traceguids
0x180006d4e  mov     edx, 14h
0x180006d53  call    WPP_SF_
0x180006d58  mov     rbx, [rsp+28h+arg_0]
0x180006d5d  add     rsp, 20h
0x180006d61  pop     rsi
0x180006d62  retn
```
