# ZtCleanupTrustedCaNotif

- ea: `0x18005aad0`
- end: `0x18005ab53`
- name: `ZtCleanupTrustedCaNotif`
- size: `131`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180055538`
- `0x18005a920`

## callees

- `0x18005aad0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005ab1e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005ab1e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18005ab01`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18005ab01`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18005aaf4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18005aaf4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005aae5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005aae5`
- `CRYPT32!CertCloseStore` at `0x18005ab3d`
- `CRYPT32!CertCloseStore` at `0x18005ab3d`

## pseudocode

```c
void ZtCleanupTrustedCaNotif()
{
  if ( g_pZtTrustedCaNotifWait )
  {
    SetThreadpoolWait(g_pZtTrustedCaNotifWait, 0, 0);
    WaitForThreadpoolWaitCallbacks(g_pZtTrustedCaNotifWait, 0);
    CloseThreadpoolWait(g_pZtTrustedCaNotifWait);
    g_pZtTrustedCaNotifWait = 0;
  }
  if ( g_hZtTrustedCaNotifEvent )
  {
    CloseHandle(g_hZtTrustedCaNotifEvent);
    g_hZtTrustedCaNotifEvent = 0;
  }
  if ( g_hRootStore )
  {
    CertCloseStore(g_hRootStore, 0);
    g_hRootStore = 0;
  }
}

```

## disassembly

```asm
0x18005aad0  sub     rsp, 28h
0x18005aad4  mov     rcx, cs:?g_pZtTrustedCaNotifWait@@3PEAU_TP_WAIT@@EA; pwa
0x18005aadb  test    rcx, rcx
0x18005aade  jz      short loc_18005AB12
0x18005aae0  xor     r8d, r8d; pftTimeout
0x18005aae3  xor     edx, edx; h
0x18005aae5  call    cs:__imp_SetThreadpoolWait
0x18005aaeb  mov     rcx, cs:?g_pZtTrustedCaNotifWait@@3PEAU_TP_WAIT@@EA; pwa
0x18005aaf2  xor     edx, edx; fCancelPendingCallbacks
0x18005aaf4  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18005aafa  mov     rcx, cs:?g_pZtTrustedCaNotifWait@@3PEAU_TP_WAIT@@EA; pwa
0x18005ab01  call    cs:__imp_CloseThreadpoolWait
0x18005ab07  mov     cs:?g_pZtTrustedCaNotifWait@@3PEAU_TP_WAIT@@EA, 0; _TP_WAIT * g_pZtTrustedCaNotifWait
0x18005ab12  mov     rcx, cs:?g_hZtTrustedCaNotifEvent@@3PEAXEA; hObject
0x18005ab19  test    rcx, rcx
0x18005ab1c  jz      short loc_18005AB2F
0x18005ab1e  call    cs:__imp_CloseHandle
0x18005ab24  mov     cs:?g_hZtTrustedCaNotifEvent@@3PEAXEA, 0; void * g_hZtTrustedCaNotifEvent
0x18005ab2f  mov     rcx, cs:?g_hRootStore@@3PEAXEA; hCertStore
0x18005ab36  test    rcx, rcx
0x18005ab39  jz      short loc_18005AB4E
0x18005ab3b  xor     edx, edx; dwFlags
0x18005ab3d  call    cs:__imp_CertCloseStore
0x18005ab43  mov     cs:?g_hRootStore@@3PEAXEA, 0; void * g_hRootStore
0x18005ab4e  add     rsp, 28h
0x18005ab52  retn
```
