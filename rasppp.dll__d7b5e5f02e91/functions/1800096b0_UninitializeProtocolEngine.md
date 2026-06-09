# UninitializeProtocolEngine

- ea: `0x1800096b0`
- end: `0x180009797`
- name: `UninitializeProtocolEngine`
- size: `231`
- prototype: `DWORD()`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180003170`
- `0x1800096b0`
- `0x18001246c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800096f6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800096f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009707`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009768`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009707`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009768`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180009751`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180009751`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000977d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000977d`

## string_xrefs

- `0x1800096ca`: `UninitializeProtocolEngine called`
- `0x180009731`: `UninitializeProtocolEngine: Waiting For Worker Thread to exit.`

## pseudocode

```c
DWORD UninitializeProtocolEngine()
{
  HANDLE v0; // rdi
  _QWORD *v1; // rax
  DWORD v3; // eax
  DWORD LastError; // ebx

  v0 = hHandle;
  if ( (byte_18004DF34 & 1) != 0 )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasPppTraceInfo,
      L"UninitializeProtocolEngine called");
  v1 = HeapAlloc(hHeap, 8u, 0x1C10u);
  if ( !v1 )
    return GetLastError();
  v1[1] = ProcessStopPPP;
  InsertWorkItemInQ((__int64)v1);
  if ( (byte_18004DF34 & 1) != 0 )
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
0x1800096b0  mov     [rsp+arg_0], rbx
0x1800096b5  push    rdi
0x1800096b6  sub     rsp, 20h
0x1800096ba  test    cs:byte_18004DF34, 1
0x1800096c1  mov     rdi, cs:hHandle
0x1800096c8  jz      short loc_1800096E4
0x1800096ca  lea     r8, aUninitializepr_1; "UninitializeProtocolEngine called"
0x1800096d1  lea     rdx, RasPppTraceInfo
0x1800096d8  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800096df  call    McTemplateU0z_EventWriteTransfer
0x1800096e4  mov     rcx, cs:hHeap; hHeap
0x1800096eb  mov     edx, 8; dwFlags
0x1800096f0  mov     r8d, 1C10h; dwBytes
0x1800096f6  call    cs:__imp_HeapAlloc
0x1800096fd  nop     dword ptr [rax+rax+00h]
0x180009702  test    rax, rax
0x180009705  jnz     short loc_180009715
0x180009707  call    cs:__imp_GetLastError
0x18000970e  nop     dword ptr [rax+rax+00h]
0x180009713  jmp     short loc_18000978B
0x180009715  lea     rcx, ProcessStopPPP
0x18000971c  mov     [rax+8], rcx
0x180009720  mov     rcx, rax
0x180009723  call    InsertWorkItemInQ
0x180009728  test    cs:byte_18004DF34, 1
0x18000972f  jz      short loc_18000974B
0x180009731  lea     r8, aUninitializepr_0; "UninitializeProtocolEngine: Waiting For"...
0x180009738  lea     rdx, RasPppTraceInfo
0x18000973f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180009746  call    McTemplateU0z_EventWriteTransfer
0x18000974b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000974e  mov     rcx, rdi; hHandle
0x180009751  call    cs:__imp_WaitForSingleObject
0x180009758  nop     dword ptr [rax+rax+00h]
0x18000975d  mov     ebx, eax
0x18000975f  test    eax, eax
0x180009761  jz      short loc_180009778
0x180009763  cmp     eax, 0FFFFFFFFh
0x180009766  jnz     short loc_18000977A
0x180009768  call    cs:__imp_GetLastError
0x18000976f  nop     dword ptr [rax+rax+00h]
0x180009774  mov     ebx, eax
0x180009776  jmp     short loc_18000977A
0x180009778  xor     ebx, ebx
0x18000977a  mov     rcx, rdi; hObject
0x18000977d  call    cs:__imp_CloseHandle
0x180009784  nop     dword ptr [rax+rax+00h]
0x180009789  mov     eax, ebx
0x18000978b  mov     rbx, [rsp+28h+arg_0]
0x180009790  add     rsp, 20h
0x180009794  pop     rdi
0x180009795  retn
```
