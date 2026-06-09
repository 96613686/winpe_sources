# ZtTrustedCaNotificationWaitCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x18005a7f0`
- end: `0x18005a91a`
- name: `?ZtTrustedCaNotificationWaitCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `298`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x180055780`
- `0x1800559d4`
- `0x18005a608`
- `0x18005a7f0`
- `0x180086700`
- `0x180086b1c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005a825`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005a825`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005a8f1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005a8f1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005a8bc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005a8bc`
- `CRYPT32!CertControlStore` at `0x18005a849`
- `CRYPT32!CertControlStore` at `0x18005a849`

## pseudocode

```c
void __fastcall ZtTrustedCaNotificationWaitCallback(
        PTP_CALLBACK_INSTANCE Instance,
        PVOID Context,
        PTP_WAIT Wait,
        TP_WAIT_RESULT WaitResult)
{
  unsigned int started; // eax
  __int64 v5; // rdx
  __int64 v6; // r9

  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_(1035, 15, WPP_0876438a9faa3d4dd03413ead13a8feb_Traceguids);
  AcquireSRWLockExclusive(&g_rwZtSettingsLock);
  g_fTrustedCaNotificationsSubscribed = 0;
  if ( !CertControlStore(g_hRootStore, 0, 1u, &g_hZtTrustedCaNotifEvent) )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      goto LABEL_19;
    v5 = 16;
    v6 = 87;
    goto LABEL_18;
  }
  if ( !(unsigned int)ZtConfirmTrustedCaInStore() )
  {
    SetThreadpoolWait(g_pZtTrustedCaNotifWait, g_hZtTrustedCaNotifEvent, 0);
    g_fTrustedCaNotificationsSubscribed = 1;
    goto LABEL_19;
  }
  HIDWORD(g_ZtEnableWhenReadyState) = 1;
  if ( g_fVelocityZtdnsProbing )
    started = DnsZtInitiateProbing();
  else
    started = DnsZtStartDriverBasedOnInternalStatus();
  if ( started )
  {
    if ( g_fVelocityZtdnsProbing )
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
        goto LABEL_19;
      v5 = 17;
    }
    else
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
        goto LABEL_19;
      v5 = 18;
    }
    v6 = started;
LABEL_18:
    WPP_SF_d(1035, v5, WPP_0876438a9faa3d4dd03413ead13a8feb_Traceguids, v6);
  }
LABEL_19:
  ReleaseSRWLockExclusive(&g_rwZtSettingsLock);
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_(1035, 19, WPP_0876438a9faa3d4dd03413ead13a8feb_Traceguids);
}

```

## disassembly

```asm
0x18005a7f0  mov     [rsp+arg_0], rbp
0x18005a7f5  push    rsi
0x18005a7f6  sub     rsp, 20h
0x18005a7fa  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18005a801  lea     rbp, WPP_0876438a9faa3d4dd03413ead13a8feb_Traceguids
0x18005a808  mov     esi, 40Bh
0x18005a80d  jz      short loc_18005A81E
0x18005a80f  mov     edx, 0Fh
0x18005a814  mov     ecx, esi
0x18005a816  mov     r8, rbp
0x18005a819  call    WPP_SF_
0x18005a81e  lea     rcx, g_rwZtSettingsLock; SRWLock
0x18005a825  call    cs:__imp_AcquireSRWLockExclusive
0x18005a82b  mov     rcx, cs:?g_hRootStore@@3PEAXEA; hCertStore
0x18005a832  lea     r9, ?g_hZtTrustedCaNotifEvent@@3PEAXEA; pvCtrlPara
0x18005a839  xor     edx, edx; dwFlags
0x18005a83b  mov     cs:?g_fTrustedCaNotificationsSubscribed@@3HA, 0; int g_fTrustedCaNotificationsSubscribed
0x18005a845  lea     r8d, [rdx+1]; dwCtrlType
0x18005a849  call    cs:__imp_CertControlStore
0x18005a84f  test    eax, eax
0x18005a851  jz      short loc_18005A8CE
0x18005a853  call    ?ZtConfirmTrustedCaInStore@@YAHXZ; ZtConfirmTrustedCaInStore(void)
0x18005a858  test    eax, eax
0x18005a85a  jz      short loc_18005A8AB
0x18005a85c  cmp     cs:g_fVelocityZtdnsProbing, 0
0x18005a863  mov     dword ptr cs:g_ZtEnableWhenReadyState+4, 1
0x18005a86d  jz      short loc_18005A876
0x18005a86f  call    DnsZtInitiateProbing
0x18005a874  jmp     short loc_18005A87B
0x18005a876  call    DnsZtStartDriverBasedOnInternalStatus
0x18005a87b  test    eax, eax
0x18005a87d  jz      short loc_18005A8EA
0x18005a87f  cmp     cs:g_fVelocityZtdnsProbing, 0
0x18005a886  jz      short loc_18005A89B
0x18005a888  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18005a88f  jz      short loc_18005A8EA
0x18005a891  mov     edx, 11h
0x18005a896  mov     r9d, eax
0x18005a899  jmp     short loc_18005A8E0
0x18005a89b  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18005a8a2  jz      short loc_18005A8EA
0x18005a8a4  mov     edx, 12h
0x18005a8a9  jmp     short loc_18005A896
0x18005a8ab  mov     rdx, cs:?g_hZtTrustedCaNotifEvent@@3PEAXEA; h
0x18005a8b2  xor     r8d, r8d; pftTimeout
0x18005a8b5  mov     rcx, cs:?g_pZtTrustedCaNotifWait@@3PEAU_TP_WAIT@@EA; pwa
0x18005a8bc  call    cs:__imp_SetThreadpoolWait
0x18005a8c2  mov     cs:?g_fTrustedCaNotificationsSubscribed@@3HA, 1; int g_fTrustedCaNotificationsSubscribed
0x18005a8cc  jmp     short loc_18005A8EA
0x18005a8ce  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18005a8d5  jz      short loc_18005A8EA
0x18005a8d7  mov     edx, 10h
0x18005a8dc  lea     r9d, [rdx+47h]
0x18005a8e0  mov     r8, rbp
0x18005a8e3  mov     ecx, esi
0x18005a8e5  call    WPP_SF_d
0x18005a8ea  lea     rcx, g_rwZtSettingsLock; SRWLock
0x18005a8f1  call    cs:__imp_ReleaseSRWLockExclusive
0x18005a8f7  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18005a8fe  jz      short loc_18005A90F
0x18005a900  mov     edx, 13h
0x18005a905  mov     ecx, esi
0x18005a907  mov     r8, rbp
0x18005a90a  call    WPP_SF_
0x18005a90f  mov     rbp, [rsp+28h+arg_0]
0x18005a914  add     rsp, 20h
0x18005a918  pop     rsi
0x18005a919  retn
```
