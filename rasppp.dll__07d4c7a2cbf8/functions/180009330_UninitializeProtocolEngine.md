# UninitializeProtocolEngine

- ea: `0x180009330`
- end: `0x1800093f8`
- name: `UninitializeProtocolEngine`
- size: `200`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180003110`
- `0x180009330`
- `0x180011e70`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009376`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009376`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009381`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800093d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009381`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800093d6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800093c5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800093c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800093e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800093e5`

## string_xrefs

- `0x18000934a`: `UninitializeProtocolEngine called`
- `0x1800093a5`: `UninitializeProtocolEngine: Waiting For Worker Thread to exit.`

## pseudocode

```c
DWORD UninitializeProtocolEngine()
{
  HANDLE v0; // rdi
  _QWORD *v1; // rax
  DWORD v3; // eax
  DWORD LastError; // ebx

  v0 = hHandle;
  if ( (byte_18004CF34 & 1) != 0 )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasPppTraceInfo,
      L"UninitializeProtocolEngine called");
  v1 = HeapAlloc(hHeap, 8u, 0x1C10u);
  if ( !v1 )
    return GetLastError();
  v1[1] = ProcessStopPPP;
  InsertWorkItemInQ(v1);
  if ( (byte_18004CF34 & 1) != 0 )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasPppTraceInfo,
      L"UninitializeProtocolEngine: Waiting For Worker Thread to exit.");
  v3 = WaitForSingleObject(v0, 0xFFFFFFFF);
  LastError = v3;
  if ( v3 )
  {
    if ( v3 == -1 )
      LastError = GetLastError();
  }
  else
  {
    LastError = 0;
  }
  CloseHandle(v0);
  return LastError;
}

```

## disassembly

```asm
0x180009330  mov     [rsp+arg_0], rbx
0x180009335  push    rdi
0x180009336  sub     rsp, 20h
0x18000933a  test    cs:byte_18004CF34, 1
0x180009341  mov     rdi, cs:hHandle
0x180009348  jz      short loc_180009364
0x18000934a  lea     r8, aUninitializepr_1; "UninitializeProtocolEngine called"
0x180009351  lea     rdx, RasPppTraceInfo
0x180009358  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000935f  call    McTemplateU0z_EventWriteTransfer
0x180009364  mov     rcx, cs:hHeap; hHeap
0x18000936b  mov     edx, 8; dwFlags
0x180009370  mov     r8d, 1C10h; dwBytes
0x180009376  call    cs:__imp_HeapAlloc
0x18000937c  test    rax, rax
0x18000937f  jnz     short loc_180009389
0x180009381  call    cs:__imp_GetLastError
0x180009387  jmp     short loc_1800093ED
0x180009389  lea     rcx, ProcessStopPPP
0x180009390  mov     [rax+8], rcx
0x180009394  mov     rcx, rax
0x180009397  call    InsertWorkItemInQ
0x18000939c  test    cs:byte_18004CF34, 1
0x1800093a3  jz      short loc_1800093BF
0x1800093a5  lea     r8, aUninitializepr_0; "UninitializeProtocolEngine: Waiting For"...
0x1800093ac  lea     rdx, RasPppTraceInfo
0x1800093b3  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800093ba  call    McTemplateU0z_EventWriteTransfer
0x1800093bf  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800093c2  mov     rcx, rdi; hHandle
0x1800093c5  call    cs:__imp_WaitForSingleObject
0x1800093cb  mov     ebx, eax
0x1800093cd  test    eax, eax
0x1800093cf  jz      short loc_1800093E0
0x1800093d1  cmp     eax, 0FFFFFFFFh
0x1800093d4  jnz     short loc_1800093E2
0x1800093d6  call    cs:__imp_GetLastError
0x1800093dc  mov     ebx, eax
0x1800093de  jmp     short loc_1800093E2
0x1800093e0  xor     ebx, ebx
0x1800093e2  mov     rcx, rdi; hObject
0x1800093e5  call    cs:__imp_CloseHandle
0x1800093eb  mov     eax, ebx
0x1800093ed  mov     rbx, [rsp+28h+arg_0]
0x1800093f2  add     rsp, 20h
0x1800093f6  pop     rdi
0x1800093f7  retn
```
