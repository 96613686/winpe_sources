# ReportOperationComplete(_WSMAN_PLUGIN_REQUEST *,ulong)

- ea: `0x1800040d0`
- end: `0x180004130`
- name: `?ReportOperationComplete@@YAKPEAU_WSMAN_PLUGIN_REQUEST@@K@Z`
- size: `96`
- prototype: `__int64 __fastcall(WSMAN_PLUGIN_REQUEST *requestDetails, DWORD errorCode)`
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180004750`
- `0x180009b71`
- `0x180009bd7`
- `0x180009c8f`
- `0x180009cf8`

## callees

- `0x180002e80`
- `0x1800040d0`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18000411d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000411d`
- `WsmSvc!WSManPluginOperationComplete` at `0x180004108`
- `WsmSvc!WSManPluginOperationComplete` at `0x180004108`

## pseudocode

```c
__int64 __fastcall ReportOperationComplete(WSMAN_PLUGIN_REQUEST *requestDetails, DWORD errorCode)
{
  DWORD v5; // ebx
  PCWSTR extendedInformation; // [rsp+30h] [rbp+8h] BYREF

  if ( !requestDetails )
    return 0;
  extendedInformation = 0;
  GetFormattedErrorMessage((unsigned __int16 **)&extendedInformation, errorCode);
  v5 = WSManPluginOperationComplete(requestDetails, 0, errorCode, extendedInformation);
  if ( extendedInformation )
    operator delete[]((void *)extendedInformation);
  return v5;
}

```

## disassembly

```asm
0x1800040d0  mov     [rsp+arg_8], rbx
0x1800040d5  push    rsi
0x1800040d6  sub     rsp, 20h
0x1800040da  mov     esi, edx
0x1800040dc  mov     rbx, rcx
0x1800040df  test    rcx, rcx
0x1800040e2  jnz     short loc_1800040E8
0x1800040e4  xor     eax, eax
0x1800040e6  jmp     short loc_180004125
0x1800040e8  lea     rcx, [rsp+28h+extendedInformation]; unsigned __int16 **
0x1800040ed  mov     [rsp+28h+extendedInformation], 0
0x1800040f6  call    ?GetFormattedErrorMessage@@YAKPEAPEAGKZZ; GetFormattedErrorMessage(ushort * *,ulong,...)
0x1800040fb  mov     r9, [rsp+28h+extendedInformation]; extendedInformation
0x180004100  mov     r8d, esi; errorCode
0x180004103  xor     edx, edx; flags
0x180004105  mov     rcx, rbx; requestDetails
0x180004108  call    cs:__imp_WSManPluginOperationComplete
0x18000410e  cmp     [rsp+28h+extendedInformation], 0
0x180004114  mov     ebx, eax
0x180004116  jz      short loc_180004123
0x180004118  mov     rcx, [rsp+28h+extendedInformation]
0x18000411d  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180004123  mov     eax, ebx
0x180004125  mov     rbx, [rsp+28h+arg_8]
0x18000412a  add     rsp, 20h
0x18000412e  pop     rsi
0x18000412f  retn
```
