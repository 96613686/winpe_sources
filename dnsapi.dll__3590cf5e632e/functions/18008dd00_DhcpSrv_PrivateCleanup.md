# DhcpSrv_PrivateCleanup

- ea: `0x18008dd00`
- end: `0x18008ddca`
- name: `DhcpSrv_PrivateCleanup`
- size: `202`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18008e5c0`
- `0x18008e810`

## callees

- `0x1800898c8`
- `0x18008db84`
- `0x18008dd00`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008dd6e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008dd91`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008dd6e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008dd91`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008dd4c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18008dd4c`

## pseudocode

```c
void DhcpSrv_PrivateCleanup()
{
  if ( g_fDhcpSrvQueueCsCreated )
  {
    if ( g_pDhcpSrvQueue )
    {
      DhcpSrv_FreeQueue(g_pDhcpSrvQueue);
      g_pDhcpSrvQueue = 0;
    }
    if ( g_pDhcpSrvTimedOutQueue )
    {
      DhcpSrv_FreeQueue(g_pDhcpSrvTimedOutQueue);
      g_pDhcpSrvTimedOutQueue = 0;
    }
    DeleteCriticalSection(&g_DhcpSrvQueueCS);
    g_fDhcpSrvQueueCsCreated = 0;
  }
  if ( g_DhcpSrvSem )
  {
    CloseHandle(g_DhcpSrvSem);
    g_DhcpSrvSem = 0;
  }
  if ( g_DhcpSrvQuitEvent )
  {
    CloseHandle(g_DhcpSrvQuitEvent);
    g_DhcpSrvQuitEvent = 0;
  }
  if ( g_pIdentityCreds )
  {
    Dns_FreeAuthIdentityCredentials(g_pIdentityCreds);
    g_pIdentityCreds = 0;
  }
}

```

## disassembly

```asm
0x18008dd00  sub     rsp, 28h
0x18008dd04  cmp     cs:g_fDhcpSrvQueueCsCreated, 0
0x18008dd0b  jz      short loc_18008DD62
0x18008dd0d  mov     rcx, cs:g_pDhcpSrvQueue; lpMem
0x18008dd14  test    rcx, rcx
0x18008dd17  jz      short loc_18008DD29
0x18008dd19  call    DhcpSrv_FreeQueue
0x18008dd1e  mov     cs:g_pDhcpSrvQueue, 0
0x18008dd29  mov     rcx, cs:g_pDhcpSrvTimedOutQueue; lpMem
0x18008dd30  test    rcx, rcx
0x18008dd33  jz      short loc_18008DD45
0x18008dd35  call    DhcpSrv_FreeQueue
0x18008dd3a  mov     cs:g_pDhcpSrvTimedOutQueue, 0
0x18008dd45  lea     rcx, g_DhcpSrvQueueCS; lpCriticalSection
0x18008dd4c  call    cs:__imp_DeleteCriticalSection
0x18008dd53  nop     dword ptr [rax+rax+00h]
0x18008dd58  mov     cs:g_fDhcpSrvQueueCsCreated, 0
0x18008dd62  mov     rcx, cs:g_DhcpSrvSem; hObject
0x18008dd69  test    rcx, rcx
0x18008dd6c  jz      short loc_18008DD85
0x18008dd6e  call    cs:__imp_CloseHandle
0x18008dd75  nop     dword ptr [rax+rax+00h]
0x18008dd7a  mov     cs:g_DhcpSrvSem, 0
0x18008dd85  mov     rcx, cs:g_DhcpSrvQuitEvent; hObject
0x18008dd8c  test    rcx, rcx
0x18008dd8f  jz      short loc_18008DDA8
0x18008dd91  call    cs:__imp_CloseHandle
0x18008dd98  nop     dword ptr [rax+rax+00h]
0x18008dd9d  mov     cs:g_DhcpSrvQuitEvent, 0
0x18008dda8  mov     rcx, cs:g_pIdentityCreds; lpMem
0x18008ddaf  test    rcx, rcx
0x18008ddb2  jz      short loc_18008DDC4
0x18008ddb4  call    Dns_FreeAuthIdentityCredentials
0x18008ddb9  mov     cs:g_pIdentityCreds, 0
0x18008ddc4  add     rsp, 28h
0x18008ddc8  retn
```
