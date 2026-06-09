# ShutdownCallFrame

- ea: `0x180012c98`
- end: `0x180012cf8`
- name: `ShutdownCallFrame`
- size: `96`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18001341c`

## callees

- `0x180012c98`

## import_xrefs

- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180012cae`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180012ccb`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180012ce8`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180012cae`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180012ccb`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180012ce8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012ca1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012cbe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012cdb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012ca1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012cbe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012cdb`

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
0x180012c98  sub     rsp, 28h
0x180012c9c  jmp     short loc_180012CA7
0x180012c9e  mov     rcx, rax; pv
0x180012ca1  call    cs:__imp_CoTaskMemFree
0x180012ca7  lea     rcx, ?g_listHead@?$DedicatedAllocator@VCallFrame@@@@0T_SLIST_HEADER@@A; ListHead
0x180012cae  call    cs:__imp_InterlockedPopEntrySList
0x180012cb4  test    rax, rax
0x180012cb7  jnz     short loc_180012C9E
0x180012cb9  jmp     short loc_180012CC4
0x180012cbb  mov     rcx, rax; pv
0x180012cbe  call    cs:__imp_CoTaskMemFree
0x180012cc4  lea     rcx, ?g_listHead@?$DedicatedAllocator@UDISPATCH_CLIENT_FRAME@@@@0T_SLIST_HEADER@@A; ListHead
0x180012ccb  call    cs:__imp_InterlockedPopEntrySList
0x180012cd1  test    rax, rax
0x180012cd4  jnz     short loc_180012CBB
0x180012cd6  jmp     short loc_180012CE1
0x180012cd8  mov     rcx, rax; pv
0x180012cdb  call    cs:__imp_CoTaskMemFree
0x180012ce1  lea     rcx, ?g_listHead@?$DedicatedAllocator@UDISPATCH_SERVER_FRAME@@@@0T_SLIST_HEADER@@A; ListHead
0x180012ce8  call    cs:__imp_InterlockedPopEntrySList
0x180012cee  test    rax, rax
0x180012cf1  jnz     short loc_180012CD8
0x180012cf3  add     rsp, 28h
0x180012cf7  retn
```
