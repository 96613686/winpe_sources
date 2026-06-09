# ZtCheckForTrustedCa

- ea: `0x18005a920`
- end: `0x18005aaca`
- name: `ZtCheckForTrustedCa`
- size: `426`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180054e04`

## callees

- `0x18005a608`
- `0x18005a920`
- `0x18005aad0`
- `0x180086700`
- `0x180086b1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a9dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a9dd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005a9ad`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005a9ad`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18005a9cb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18005a9cb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005aa5d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005aa5d`
- `CRYPT32!CertOpenStore` at `0x18005a973`
- `CRYPT32!CertOpenStore` at `0x18005a973`
- `CRYPT32!CertControlStore` at `0x18005aa03`
- `CRYPT32!CertControlStore` at `0x18005aa42`
- `CRYPT32!CertControlStore` at `0x18005aa03`
- `CRYPT32!CertControlStore` at `0x18005aa42`

## pseudocode

```c
__int64 ZtCheckForTrustedCa()
{
  unsigned int v0; // edi
  DWORD LastError; // ebx
  __int64 v2; // rdx

  v0 = 0;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_(1035, 20, WPP_0876438a9faa3d4dd03413ead13a8feb_Traceguids);
  if ( !g_hRootStore )
  {
    g_hRootStore = CertOpenStore((LPCSTR)0xA, 0, 0, 0x28000u, L"root");
    if ( !g_hRootStore )
      goto LABEL_9;
LABEL_5:
    LastError = 0;
    v0 = ZtConfirmTrustedCaInStore();
    if ( v0 )
      goto LABEL_22;
    if ( !g_pZtTrustedCaNotifWait )
    {
      g_hZtTrustedCaNotifEvent = CreateEventW(0, 0, 0, 0);
      if ( !g_hZtTrustedCaNotifEvent
        || (g_pZtTrustedCaNotifWait = CreateThreadpoolWait((PTP_WAIT_CALLBACK)ZtTrustedCaNotificationWaitCallback, 0, 0)) == 0 )
      {
LABEL_9:
        LastError = GetLastError();
        if ( !LastError )
          goto LABEL_22;
        goto LABEL_21;
      }
    }
    if ( g_fTrustedCaNotificationsSubscribed )
      goto LABEL_22;
    if ( CertControlStore(g_hRootStore, 0, 2u, &g_hZtTrustedCaNotifEvent) )
    {
      SetThreadpoolWait(g_pZtTrustedCaNotifWait, g_hZtTrustedCaNotifEvent, 0);
      g_fTrustedCaNotificationsSubscribed = 1;
      goto LABEL_22;
    }
    LastError = 87;
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    {
      v2 = 22;
      goto LABEL_20;
    }
    goto LABEL_21;
  }
  if ( g_fTrustedCaNotificationsSubscribed || CertControlStore(g_hRootStore, 0, 1u, 0) )
    goto LABEL_5;
  LastError = 87;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
  {
    v2 = 21;
LABEL_20:
    WPP_SF_d(1035, v2, WPP_0876438a9faa3d4dd03413ead13a8feb_Traceguids, 87);
  }
LABEL_21:
  ZtCleanupTrustedCaNotif();
LABEL_22:
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 23, WPP_0876438a9faa3d4dd03413ead13a8feb_Traceguids, LastError);
  return v0;
}

```

## disassembly

```asm
0x18005a920  mov     [rsp+arg_0], rbx
0x18005a925  push    rdi
0x18005a926  sub     rsp, 30h
0x18005a92a  xor     edi, edi
0x18005a92c  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18005a933  jz      short loc_18005A949
0x18005a935  lea     edx, [rdi+14h]
0x18005a938  mov     ecx, 40Bh
0x18005a93d  lea     r8, WPP_0876438a9faa3d4dd03413ead13a8feb_Traceguids
0x18005a944  call    WPP_SF_
0x18005a949  mov     rcx, cs:?g_hRootStore@@3PEAXEA; hCertStore
0x18005a950  test    rcx, rcx
0x18005a953  jnz     loc_18005A9F2
0x18005a959  xor     edx, edx; dwEncodingType
0x18005a95b  lea     rax, aRoot; "root"
0x18005a962  mov     r9d, 28000h; dwFlags
0x18005a968  mov     [rsp+38h+pvPara], rax; pvPara
0x18005a96d  xor     r8d, r8d; hCryptProv
0x18005a970  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x18005a973  call    cs:__imp_CertOpenStore
0x18005a979  mov     cs:?g_hRootStore@@3PEAXEA, rax; void * g_hRootStore
0x18005a980  test    rax, rax
0x18005a983  jz      short loc_18005A9DD
0x18005a985  call    ?ZtConfirmTrustedCaInStore@@YAHXZ; ZtConfirmTrustedCaInStore(void)
0x18005a98a  xor     ebx, ebx
0x18005a98c  mov     edi, eax
0x18005a98e  test    eax, eax
0x18005a990  jnz     loc_18005AA9B
0x18005a996  cmp     cs:?g_pZtTrustedCaNotifWait@@3PEAU_TP_WAIT@@EA, rbx; _TP_WAIT * g_pZtTrustedCaNotifWait
0x18005a99d  jnz     loc_18005AA26
0x18005a9a3  xor     r9d, r9d; lpName
0x18005a9a6  xor     r8d, r8d; bInitialState
0x18005a9a9  xor     edx, edx; bManualReset
0x18005a9ab  xor     ecx, ecx; lpEventAttributes
0x18005a9ad  call    cs:__imp_CreateEventW
0x18005a9b3  mov     cs:?g_hZtTrustedCaNotifEvent@@3PEAXEA, rax; void * g_hZtTrustedCaNotifEvent
0x18005a9ba  test    rax, rax
0x18005a9bd  jz      short loc_18005A9DD
0x18005a9bf  xor     r8d, r8d; pcbe
0x18005a9c2  lea     rcx, ?ZtTrustedCaNotificationWaitCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18005a9c9  xor     edx, edx; pv
0x18005a9cb  call    cs:__imp_CreateThreadpoolWait
0x18005a9d1  mov     cs:?g_pZtTrustedCaNotifWait@@3PEAU_TP_WAIT@@EA, rax; _TP_WAIT * g_pZtTrustedCaNotifWait
0x18005a9d8  test    rax, rax
0x18005a9db  jnz     short loc_18005AA26
0x18005a9dd  call    cs:__imp_GetLastError
0x18005a9e3  mov     ebx, eax
0x18005a9e5  test    eax, eax
0x18005a9e7  jz      loc_18005AA9B
0x18005a9ed  jmp     loc_18005AA96
0x18005a9f2  cmp     cs:?g_fTrustedCaNotificationsSubscribed@@3HA, edi; int g_fTrustedCaNotificationsSubscribed
0x18005a9f8  jnz     short loc_18005A985
0x18005a9fa  xor     r9d, r9d; pvCtrlPara
0x18005a9fd  xor     edx, edx; dwFlags
0x18005a9ff  lea     r8d, [r9+1]; dwCtrlType
0x18005aa03  call    cs:__imp_CertControlStore
0x18005aa09  test    eax, eax
0x18005aa0b  jnz     loc_18005A985
0x18005aa11  lea     r9d, [rax+57h]
0x18005aa15  mov     ebx, r9d
0x18005aa18  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18005aa1f  jz      short loc_18005AA96
0x18005aa21  lea     edx, [rax+15h]
0x18005aa24  jmp     short loc_18005AA85
0x18005aa26  cmp     cs:?g_fTrustedCaNotificationsSubscribed@@3HA, ebx; int g_fTrustedCaNotificationsSubscribed
0x18005aa2c  jnz     short loc_18005AA9B
0x18005aa2e  mov     rcx, cs:?g_hRootStore@@3PEAXEA; hCertStore
0x18005aa35  lea     r9, ?g_hZtTrustedCaNotifEvent@@3PEAXEA; pvCtrlPara
0x18005aa3c  xor     edx, edx; dwFlags
0x18005aa3e  lea     r8d, [rdx+2]; dwCtrlType
0x18005aa42  call    cs:__imp_CertControlStore
0x18005aa48  test    eax, eax
0x18005aa4a  jz      short loc_18005AA6F
0x18005aa4c  mov     rdx, cs:?g_hZtTrustedCaNotifEvent@@3PEAXEA; h
0x18005aa53  xor     r8d, r8d; pftTimeout
0x18005aa56  mov     rcx, cs:?g_pZtTrustedCaNotifWait@@3PEAU_TP_WAIT@@EA; pwa
0x18005aa5d  call    cs:__imp_SetThreadpoolWait
0x18005aa63  mov     cs:?g_fTrustedCaNotificationsSubscribed@@3HA, 1; int g_fTrustedCaNotificationsSubscribed
0x18005aa6d  jmp     short loc_18005AA9B
0x18005aa6f  mov     r9d, 57h ; 'W'
0x18005aa75  mov     ebx, r9d
0x18005aa78  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18005aa7f  jz      short loc_18005AA96
0x18005aa81  lea     edx, [r9-41h]
0x18005aa85  lea     r8, WPP_0876438a9faa3d4dd03413ead13a8feb_Traceguids
0x18005aa8c  mov     ecx, 40Bh
0x18005aa91  call    WPP_SF_d
0x18005aa96  call    ZtCleanupTrustedCaNotif
0x18005aa9b  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18005aaa2  jz      short loc_18005AABD
0x18005aaa4  mov     edx, 17h
0x18005aaa9  lea     r8, WPP_0876438a9faa3d4dd03413ead13a8feb_Traceguids
0x18005aab0  mov     ecx, 40Bh
0x18005aab5  mov     r9d, ebx
0x18005aab8  call    WPP_SF_d
0x18005aabd  mov     rbx, [rsp+38h+arg_0]
0x18005aac2  mov     eax, edi
0x18005aac4  add     rsp, 30h
0x18005aac8  pop     rdi
0x18005aac9  retn
```
