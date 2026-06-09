# ShutdownCallFrame

- ea: `0x1800101a8`
- end: `0x18001022d`
- name: `ShutdownCallFrame`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180010990`

## callees

- `0x1800101a8`

## import_xrefs

- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x1800101c4`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x1800101ed`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180010216`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x1800101c4`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x1800101ed`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180010216`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800101b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800101da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010203`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800101b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800101da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010203`

## pseudocode

```c
PSLIST_ENTRY ShutdownCallFrame()
{
  PSLIST_ENTRY v0; // rax
  PSLIST_ENTRY v1; // rax
  PSLIST_ENTRY result; // rax

  while ( 1 )
  {
    v0 = InterlockedPopEntrySList(&DedicatedAllocator<CallFrame>::g_listHead);
    if ( !v0 )
      break;
    CoTaskMemFree(v0);
  }
  while ( 1 )
  {
    v1 = InterlockedPopEntrySList(&DedicatedAllocator<DISPATCH_CLIENT_FRAME>::g_listHead);
    if ( !v1 )
      break;
    CoTaskMemFree(v1);
  }
  while ( 1 )
  {
    result = InterlockedPopEntrySList(&DedicatedAllocator<DISPATCH_SERVER_FRAME>::g_listHead);
    if ( !result )
      break;
    CoTaskMemFree(result);
  }
  return result;
}

```

## disassembly

```asm
0x1800101a8  sub     rsp, 28h
0x1800101ac  jmp     short loc_1800101BD
0x1800101ae  mov     rcx, rax; pv
0x1800101b1  call    cs:__imp_CoTaskMemFree
0x1800101b8  nop     dword ptr [rax+rax+00h]
0x1800101bd  lea     rcx, ?g_listHead@?$DedicatedAllocator@VCallFrame@@@@0T_SLIST_HEADER@@A; ListHead
0x1800101c4  call    cs:__imp_InterlockedPopEntrySList
0x1800101cb  nop     dword ptr [rax+rax+00h]
0x1800101d0  test    rax, rax
0x1800101d3  jnz     short loc_1800101AE
0x1800101d5  jmp     short loc_1800101E6
0x1800101d7  mov     rcx, rax; pv
0x1800101da  call    cs:__imp_CoTaskMemFree
0x1800101e1  nop     dword ptr [rax+rax+00h]
0x1800101e6  lea     rcx, ?g_listHead@?$DedicatedAllocator@UDISPATCH_CLIENT_FRAME@@@@0T_SLIST_HEADER@@A; ListHead
0x1800101ed  call    cs:__imp_InterlockedPopEntrySList
0x1800101f4  nop     dword ptr [rax+rax+00h]
0x1800101f9  test    rax, rax
0x1800101fc  jnz     short loc_1800101D7
0x1800101fe  jmp     short loc_18001020F
0x180010200  mov     rcx, rax; pv
0x180010203  call    cs:__imp_CoTaskMemFree
0x18001020a  nop     dword ptr [rax+rax+00h]
0x18001020f  lea     rcx, ?g_listHead@?$DedicatedAllocator@UDISPATCH_SERVER_FRAME@@@@0T_SLIST_HEADER@@A; ListHead
0x180010216  call    cs:__imp_InterlockedPopEntrySList
0x18001021d  nop     dword ptr [rax+rax+00h]
0x180010222  test    rax, rax
0x180010225  jnz     short loc_180010200
0x180010227  add     rsp, 28h
0x18001022b  retn
```
