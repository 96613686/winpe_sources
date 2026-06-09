# ZtCleanupClientCertNotif

- ea: `0x18005a390`
- end: `0x18005a413`
- name: `ZtCleanupClientCertNotif`
- size: `131`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180055538`
- `0x18005a41c`

## callees

- `0x18005a390`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a3de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a3de`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18005a3c1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18005a3c1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18005a3b4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18005a3b4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005a3a5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005a3a5`
- `CRYPT32!CertCloseStore` at `0x18005a3fd`
- `CRYPT32!CertCloseStore` at `0x18005a3fd`

## pseudocode

```c
void ZtCleanupClientCertNotif()
{
  if ( g_pZtCertsNotifWait )
  {
    SetThreadpoolWait(g_pZtCertsNotifWait, 0, 0);
    WaitForThreadpoolWaitCallbacks(g_pZtCertsNotifWait, 0);
    CloseThreadpoolWait(g_pZtCertsNotifWait);
    g_pZtCertsNotifWait = 0;
  }
  if ( g_hZtCertsNotifEvent )
  {
    CloseHandle(g_hZtCertsNotifEvent);
    g_hZtCertsNotifEvent = 0;
  }
  if ( g_hCertStore )
  {
    CertCloseStore(g_hCertStore, 0);
    g_hCertStore = 0;
  }
}

```

## disassembly

```asm
0x18005a390  sub     rsp, 28h
0x18005a394  mov     rcx, cs:?g_pZtCertsNotifWait@@3PEAU_TP_WAIT@@EA; pwa
0x18005a39b  test    rcx, rcx
0x18005a39e  jz      short loc_18005A3D2
0x18005a3a0  xor     r8d, r8d; pftTimeout
0x18005a3a3  xor     edx, edx; h
0x18005a3a5  call    cs:__imp_SetThreadpoolWait
0x18005a3ab  mov     rcx, cs:?g_pZtCertsNotifWait@@3PEAU_TP_WAIT@@EA; pwa
0x18005a3b2  xor     edx, edx; fCancelPendingCallbacks
0x18005a3b4  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18005a3ba  mov     rcx, cs:?g_pZtCertsNotifWait@@3PEAU_TP_WAIT@@EA; pwa
0x18005a3c1  call    cs:__imp_CloseThreadpoolWait
0x18005a3c7  mov     cs:?g_pZtCertsNotifWait@@3PEAU_TP_WAIT@@EA, 0; _TP_WAIT * g_pZtCertsNotifWait
0x18005a3d2  mov     rcx, cs:?g_hZtCertsNotifEvent@@3PEAXEA; hObject
0x18005a3d9  test    rcx, rcx
0x18005a3dc  jz      short loc_18005A3EF
0x18005a3de  call    cs:__imp_CloseHandle
0x18005a3e4  mov     cs:?g_hZtCertsNotifEvent@@3PEAXEA, 0; void * g_hZtCertsNotifEvent
0x18005a3ef  mov     rcx, cs:?g_hCertStore@@3PEAXEA; hCertStore
0x18005a3f6  test    rcx, rcx
0x18005a3f9  jz      short loc_18005A40E
0x18005a3fb  xor     edx, edx; dwFlags
0x18005a3fd  call    cs:__imp_CertCloseStore
0x18005a403  mov     cs:?g_hCertStore@@3PEAXEA, 0; void * g_hCertStore
0x18005a40e  add     rsp, 28h
0x18005a412  retn
```
