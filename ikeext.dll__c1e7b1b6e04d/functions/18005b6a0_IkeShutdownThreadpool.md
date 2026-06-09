# IkeShutdownThreadpool

- ea: `0x18005b6a0`
- end: `0x18005b7a0`
- name: `IkeShutdownThreadpool`
- size: `256`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180058100`

## callees

- `0x18005b6a0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18005b702`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18005b72d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18005b758`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18005b783`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18005b702`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18005b72d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18005b758`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18005b783`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18005b6b7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18005b6d0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18005b6e9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18005b6b7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18005b6d0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18005b6e9`

## pseudocode

```c
LPCRITICAL_SECTION IkeShutdownThreadpool()
{
  LPCRITICAL_SECTION result; // rax
  struct _TP_POOL *DebugInfo; // rcx
  struct _TP_POOL *v2; // rcx
  struct _TP_POOL *v3; // rcx
  struct _TP_WAIT *v4; // rcx
  struct _TP_WAIT *v5; // rcx
  struct _TP_WAIT *OwningThread; // rcx
  struct _TP_WAIT *LockSemaphore; // rcx

  result = gIkeExtGlobals;
  DebugInfo = (struct _TP_POOL *)gIkeExtGlobals[76].DebugInfo;
  if ( DebugInfo )
  {
    CloseThreadpool(DebugInfo);
    result = gIkeExtGlobals;
  }
  v2 = (struct _TP_POOL *)result[78].DebugInfo;
  if ( v2 )
  {
    CloseThreadpool(v2);
    result = gIkeExtGlobals;
  }
  v3 = (struct _TP_POOL *)result[80].DebugInfo;
  if ( v3 )
  {
    CloseThreadpool(v3);
    result = gIkeExtGlobals;
  }
  v4 = (struct _TP_WAIT *)result[82].DebugInfo;
  if ( v4 )
  {
    CloseThreadpoolWait(v4);
    gIkeExtGlobals[82].DebugInfo = 0;
    result = gIkeExtGlobals;
  }
  v5 = *(struct _TP_WAIT **)&result[82].LockCount;
  if ( v5 )
  {
    CloseThreadpoolWait(v5);
    *(_QWORD *)&gIkeExtGlobals[82].LockCount = 0;
    result = gIkeExtGlobals;
  }
  OwningThread = (struct _TP_WAIT *)result[82].OwningThread;
  if ( OwningThread )
  {
    CloseThreadpoolWait(OwningThread);
    gIkeExtGlobals[82].OwningThread = 0;
    result = gIkeExtGlobals;
  }
  LockSemaphore = (struct _TP_WAIT *)result[82].LockSemaphore;
  if ( LockSemaphore )
  {
    CloseThreadpoolWait(LockSemaphore);
    result = gIkeExtGlobals;
    gIkeExtGlobals[82].LockSemaphore = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18005b6a0  sub     rsp, 28h
0x18005b6a4  mov     rax, cs:gIkeExtGlobals
0x18005b6ab  mov     rcx, [rax+0BE0h]; ptpp
0x18005b6b2  test    rcx, rcx
0x18005b6b5  jz      short loc_18005B6C4
0x18005b6b7  call    cs:__imp_CloseThreadpool
0x18005b6bd  mov     rax, cs:gIkeExtGlobals
0x18005b6c4  mov     rcx, [rax+0C30h]; ptpp
0x18005b6cb  test    rcx, rcx
0x18005b6ce  jz      short loc_18005B6DD
0x18005b6d0  call    cs:__imp_CloseThreadpool
0x18005b6d6  mov     rax, cs:gIkeExtGlobals
0x18005b6dd  mov     rcx, [rax+0C80h]; ptpp
0x18005b6e4  test    rcx, rcx
0x18005b6e7  jz      short loc_18005B6F6
0x18005b6e9  call    cs:__imp_CloseThreadpool
0x18005b6ef  mov     rax, cs:gIkeExtGlobals
0x18005b6f6  mov     rcx, [rax+0CD0h]; pwa
0x18005b6fd  test    rcx, rcx
0x18005b700  jz      short loc_18005B721
0x18005b702  call    cs:__imp_CloseThreadpoolWait
0x18005b708  mov     rax, cs:gIkeExtGlobals
0x18005b70f  mov     qword ptr [rax+0CD0h], 0
0x18005b71a  mov     rax, cs:gIkeExtGlobals
0x18005b721  mov     rcx, [rax+0CD8h]; pwa
0x18005b728  test    rcx, rcx
0x18005b72b  jz      short loc_18005B74C
0x18005b72d  call    cs:__imp_CloseThreadpoolWait
0x18005b733  mov     rax, cs:gIkeExtGlobals
0x18005b73a  mov     qword ptr [rax+0CD8h], 0
0x18005b745  mov     rax, cs:gIkeExtGlobals
0x18005b74c  mov     rcx, [rax+0CE0h]; pwa
0x18005b753  test    rcx, rcx
0x18005b756  jz      short loc_18005B777
0x18005b758  call    cs:__imp_CloseThreadpoolWait
0x18005b75e  mov     rax, cs:gIkeExtGlobals
0x18005b765  mov     qword ptr [rax+0CE0h], 0
0x18005b770  mov     rax, cs:gIkeExtGlobals
0x18005b777  mov     rcx, [rax+0CE8h]; pwa
0x18005b77e  test    rcx, rcx
0x18005b781  jz      short loc_18005B79B
0x18005b783  call    cs:__imp_CloseThreadpoolWait
0x18005b789  mov     rax, cs:gIkeExtGlobals
0x18005b790  mov     qword ptr [rax+0CE8h], 0
0x18005b79b  add     rsp, 28h
0x18005b79f  retn
```
