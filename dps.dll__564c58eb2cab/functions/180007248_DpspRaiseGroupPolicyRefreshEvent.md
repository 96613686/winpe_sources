# DpspRaiseGroupPolicyRefreshEvent

- ea: `0x180007248`
- end: `0x1800072c4`
- name: `DpspRaiseGroupPolicyRefreshEvent`
- size: `124`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180016200`

## callees

- `0x180007248`
- `0x180009090`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x18000725e`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x18000725e`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18000727c`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18000727c`

## pseudocode

```c
__int64 DpspRaiseGroupPolicyRefreshEvent()
{
  signed int Args; // ebx
  signed int v1; // eax

  Args = 0;
  if ( EventEnabled(g_hETW, &WDI_DPS_EVENT_GROUPPOLICY_REFRESH) )
  {
    v1 = EventWrite(g_hETW, &WDI_DPS_EVENT_GROUPPOLICY_REFRESH, 0, 0);
    Args = v1;
    if ( v1 > 0 )
      Args = (unsigned __int16)v1 | 0x80070000;
    if ( Args < 0 )
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsevents.cpp",
        (int)L"DpspRaiseGroupPolicyRefreshEvent",
        78,
        (int)L"Error = %d",
        Args);
  }
  return (unsigned int)Args;
}

```

## disassembly

```asm
0x180007248  push    rbx
0x18000724a  sub     rsp, 30h
0x18000724e  mov     rcx, cs:g_hETW; RegHandle
0x180007255  lea     rdx, WDI_DPS_EVENT_GROUPPOLICY_REFRESH; EventDescriptor
0x18000725c  xor     ebx, ebx
0x18000725e  call    cs:__imp_EventEnabled
0x180007264  test    al, al
0x180007266  jz      short loc_1800072BC
0x180007268  mov     rcx, cs:g_hETW; RegHandle
0x18000726f  lea     rdx, WDI_DPS_EVENT_GROUPPOLICY_REFRESH; EventDescriptor
0x180007276  xor     r9d, r9d; UserData
0x180007279  xor     r8d, r8d; UserDataCount
0x18000727c  call    cs:__imp_EventWrite
0x180007282  mov     ebx, eax
0x180007284  test    eax, eax
0x180007286  jle     short loc_180007291
0x180007288  movzx   ebx, ax
0x18000728b  or      ebx, 80070000h
0x180007291  test    ebx, ebx
0x180007293  jns     short loc_1800072BC
0x180007295  movzx   ecx, bx
0x180007298  lea     r9, aErrorD; "Error = %d"
0x18000729f  mov     dword ptr [rsp+38h+Args], ecx; Args
0x1800072a3  lea     rdx, aDpspraisegroup; "DpspRaiseGroupPolicyRefreshEvent"
0x1800072aa  lea     rcx, aClientcoreBase_6; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800072b1  mov     r8d, 4Eh ; 'N'; int
0x1800072b7  call    WdipTraceError
0x1800072bc  mov     eax, ebx
0x1800072be  add     rsp, 30h
0x1800072c2  pop     rbx
0x1800072c3  retn
```
