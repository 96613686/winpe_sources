# WfpMidlObjectInit

- ea: `0x180003370`
- end: `0x18000343f`
- name: `WfpMidlObjectInit`
- size: `207`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180003170`

## callees

- `0x180003370`
- `0x1800034e0`
- `0x1800036a4`
- `0x180007e38`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800033de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800033de`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180003389`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180003389`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x1800033c4`
- `RPCRT4!MesEncodeDynBufferHandleCreate` at `0x1800033c4`

## string_xrefs

- `0x180003429`: `MesEncodeFixedBufferHandleCreate`
- `0x180003401`: `WfpCriticalSectionCreate`

## pseudocode

```c
__int64 WfpMidlObjectInit()
{
  __int64 v0; // rbx
  unsigned int v1; // eax
  __int64 v2; // rcx
  DWORD LastError; // eax
  __int64 v5; // rcx
  __int64 v6; // rax

  dword_18007C648 = 0;
  if ( InitializeCriticalSectionAndSpinCount(&gWfpMidlObject, 0) )
  {
    dword_18007C648 = 1;
    v0 = 0;
  }
  else
  {
    LastError = GetLastError();
    v6 = WfpReportSysErrorAsWinError(v5, "InitializeCriticalSectionAndSpinCount", LastError);
    v0 = v6;
    if ( v6 )
    {
      WfpReportError(v6, "WfpCriticalSectionCreate");
LABEL_7:
      WfpMidlObjectShutdown();
      WfpReportError(v0, "WfpMidlObjectInit");
      return v0;
    }
  }
  dword_18007C650 = 1;
  v1 = MesEncodeDynBufferHandleCreate(&pBuffer, &pEncodedSize, &Handle);
  if ( v1 )
  {
    v0 = WfpReportSysErrorAsWinError(v2, "MesEncodeFixedBufferHandleCreate", v1);
    if ( v0 )
      goto LABEL_7;
  }
  return v0;
}

```

## disassembly

```asm
0x180003370  push    rbx
0x180003372  sub     rsp, 20h
0x180003376  xor     edx, edx; dwSpinCount
0x180003378  mov     cs:dword_18007C648, 0
0x180003382  lea     rcx, gWfpMidlObject; lpCriticalSection
0x180003389  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180003390  nop     dword ptr [rax+rax+00h]
0x180003395  test    eax, eax
0x180003397  jz      short loc_1800033DE
0x180003399  mov     cs:dword_18007C648, 1
0x1800033a3  xor     ebx, ebx
0x1800033a5  lea     r8, Handle; pHandle
0x1800033ac  mov     cs:dword_18007C650, 1
0x1800033b6  lea     rdx, pEncodedSize; pEncodedSize
0x1800033bd  lea     rcx, pBuffer; pBuffer
0x1800033c4  call    cs:__imp_MesEncodeDynBufferHandleCreate
0x1800033cb  nop     dword ptr [rax+rax+00h]
0x1800033d0  test    eax, eax
0x1800033d2  jnz     short loc_180003426
0x1800033d4  mov     rax, rbx
0x1800033d7  add     rsp, 20h
0x1800033db  pop     rbx
0x1800033dc  retn
0x1800033de  call    cs:__imp_GetLastError
0x1800033e5  nop     dword ptr [rax+rax+00h]
0x1800033ea  mov     r8d, eax
0x1800033ed  lea     rdx, aInitializecrit; "InitializeCriticalSectionAndSpinCount"
0x1800033f4  call    WfpReportSysErrorAsWinError
0x1800033f9  mov     rbx, rax
0x1800033fc  test    rax, rax
0x1800033ff  jz      short loc_1800033A5
0x180003401  lea     rdx, aWfpcriticalsec; "WfpCriticalSectionCreate"
0x180003408  mov     rcx, rax
0x18000340b  call    WfpReportError
0x180003410  call    WfpMidlObjectShutdown
0x180003415  lea     rdx, aWfpmidlobjecti; "WfpMidlObjectInit"
0x18000341c  mov     rcx, rbx
0x18000341f  call    WfpReportError
0x180003424  jmp     short loc_1800033D4
0x180003426  mov     r8d, eax
0x180003429  lea     rdx, aMesencodefixed; "MesEncodeFixedBufferHandleCreate"
0x180003430  call    WfpReportSysErrorAsWinError
0x180003435  mov     rbx, rax
0x180003438  test    rax, rax
0x18000343b  jz      short loc_1800033D4
0x18000343d  jmp     short loc_180003410
```
