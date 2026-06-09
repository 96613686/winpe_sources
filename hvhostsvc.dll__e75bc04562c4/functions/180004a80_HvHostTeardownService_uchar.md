# HvHostTeardownService(uchar)

- ea: `0x180004a80`
- end: `0x180004af4`
- name: `?HvHostTeardownService@@YAXE@Z`
- size: `116`
- prototype: `void __fastcall(HvStatsPanel *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180004a60`
- `0x180006340`

## callees

- `0x180004a80`
- `0x1800079ac`
- `0x180008818`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004add`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004add`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180004ac0`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180004ac0`

## pseudocode

```c
void __fastcall HvHostTeardownService(HvStatsPanel *a1)
{
  char v1; // bl
  HvSysConfigTimer *v2; // rcx

  v1 = (char)a1;
  if ( g_IsCpuManager || g_IsVmManager )
  {
    HvStatsPanel::Teardown(a1);
    if ( g_IsCpuManager )
      HvSysConfigTimer::Teardown(v2);
  }
  if ( g_SvcHostStopWaitHandle != (HANDLE)-1LL )
  {
    if ( !v1 )
      UnregisterWaitEx(g_SvcHostStopWaitHandle, 0);
    g_SvcHostStopWaitHandle = (HANDLE)-1LL;
  }
  if ( g_ServiceStopEvent )
  {
    CloseHandle(g_ServiceStopEvent);
    g_ServiceStopEvent = 0;
  }
}

```

## disassembly

```asm
0x180004a80  push    rbx
0x180004a82  sub     rsp, 20h
0x180004a86  cmp     cs:?g_IsCpuManager@@3EA, 0; uchar g_IsCpuManager
0x180004a8d  mov     bl, cl
0x180004a8f  jnz     short loc_180004A9A
0x180004a91  cmp     cs:?g_IsVmManager@@3EA, 0; uchar g_IsVmManager
0x180004a98  jz      short loc_180004AAD
0x180004a9a  call    ?Teardown@HvStatsPanel@@QEAAXXZ; HvStatsPanel::Teardown(void)
0x180004a9f  cmp     cs:?g_IsCpuManager@@3EA, 0; uchar g_IsCpuManager
0x180004aa6  jz      short loc_180004AAD
0x180004aa8  call    ?Teardown@HvSysConfigTimer@@QEAAXXZ; HvSysConfigTimer::Teardown(void)
0x180004aad  mov     rcx, cs:?g_SvcHostStopWaitHandle@@3PEAXEA; WaitHandle
0x180004ab4  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180004ab8  jz      short loc_180004AD1
0x180004aba  test    bl, bl
0x180004abc  jnz     short loc_180004AC6
0x180004abe  xor     edx, edx; CompletionEvent
0x180004ac0  call    cs:__imp_UnregisterWaitEx
0x180004ac6  mov     cs:?g_SvcHostStopWaitHandle@@3PEAXEA, 0FFFFFFFFFFFFFFFFh; void * g_SvcHostStopWaitHandle
0x180004ad1  mov     rcx, cs:?g_ServiceStopEvent@@3PEAXEA; hObject
0x180004ad8  test    rcx, rcx
0x180004adb  jz      short loc_180004AEE
0x180004add  call    cs:__imp_CloseHandle
0x180004ae3  mov     cs:?g_ServiceStopEvent@@3PEAXEA, 0; void * g_ServiceStopEvent
0x180004aee  add     rsp, 20h
0x180004af2  pop     rbx
0x180004af3  retn
```
