# ZtSubscribeClientCertNotif

- ea: `0x18005a41c`
- end: `0x18005a602`
- name: `ZtSubscribeClientCertNotif`
- size: `486`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180055ac4`
- `0x1800564c8`
- `0x180056b70`

## callees

- `0x18005a1c4`
- `0x18005a390`
- `0x18005a41c`
- `0x180086700`
- `0x180086b1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a47a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a4eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a47a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a4eb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005a468`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005a468`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18005a493`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18005a493`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005a5b0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005a5b0`
- `CRYPT32!CertOpenStore` at `0x18005a4bf`
- `CRYPT32!CertOpenStore` at `0x18005a4bf`
- `CRYPT32!CertControlStore` at `0x18005a4e1`
- `CRYPT32!CertControlStore` at `0x18005a4e1`

## pseudocode

```c
__int64 ZtSubscribeClientCertNotif()
{
  DWORD v0; // ebx
  HCERTSTORE v1; // rax
  DWORD LastError; // eax
  unsigned int v3; // edi
  DWORD updated; // eax
  __int64 v5; // rdx
  int v7; // [rsp+60h] [rbp+8h] BYREF

  v0 = 0;
  v7 = 0;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_(1035, 24, WPP_da5f48c7dcef3941ae809be7a10ca70f_Traceguids);
  if ( !g_pZtCertsNotifWait )
  {
    g_hZtCertsNotifEvent = CreateEventW(0, 0, 0, 0);
    if ( g_hZtCertsNotifEvent
      && (g_pZtCertsNotifWait = CreateThreadpoolWait((PTP_WAIT_CALLBACK)ZtCertStoreNotificationsWaitCallback, 0, 0)) != 0
      && (v1 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x28000u, L"my"), (g_hCertStore = v1) != 0) )
    {
      if ( CertControlStore(v1, 0, 2u, &g_hZtCertsNotifEvent) )
      {
        if ( g_fVelocityZtdnsProbing )
        {
          v3 = 0;
          while ( v3 != 1
               || _InterlockedCompareExchange((volatile signed __int32 *)&g_rgZtHelperSettingsState, 0, 0) != _InterlockedCompareExchange(&dword_1800ABAB4, 0, 0) )
          {
            updated = ZtCertUpdateAclIfNeeded(v3, &v7);
            v0 = updated;
            if ( updated )
            {
              if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
                goto LABEL_31;
              v5 = 26;
              goto LABEL_30;
            }
            if ( v3 == 1 && v7 )
              goto LABEL_26;
            if ( ++v3 >= 2 )
              break;
          }
        }
        else
        {
          updated = ZtCertUpdateAclIfNeeded(0, &v7);
          v0 = updated;
          if ( updated )
          {
            if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
            {
              v5 = 27;
LABEL_30:
              WPP_SF_d(1035, v5, WPP_da5f48c7dcef3941ae809be7a10ca70f_Traceguids, updated);
            }
LABEL_31:
            ZtCleanupClientCertNotif();
            goto LABEL_32;
          }
          if ( v7 )
LABEL_26:
            LODWORD(g_ZtEnableWhenReadyState) = 1;
        }
        SetThreadpoolWait(g_pZtCertsNotifWait, g_hZtCertsNotifEvent, 0);
        goto LABEL_32;
      }
      LastError = GetLastError();
      v0 = LastError;
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        WPP_SF_d(1035, 25, WPP_da5f48c7dcef3941ae809be7a10ca70f_Traceguids, LastError);
    }
    else
    {
      v0 = GetLastError();
    }
    if ( !v0 )
      goto LABEL_32;
    goto LABEL_31;
  }
LABEL_32:
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 28, WPP_da5f48c7dcef3941ae809be7a10ca70f_Traceguids, v0);
  return v0;
}

```

## disassembly

```asm
0x18005a41c  push    rbx
0x18005a41e  push    rdi
0x18005a41f  push    r14
0x18005a421  push    r15
0x18005a423  sub     rsp, 38h
0x18005a427  xor     ebx, ebx
0x18005a429  mov     [rsp+58h+arg_0], ebx
0x18005a42d  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18005a434  lea     r15, WPP_da5f48c7dcef3941ae809be7a10ca70f_Traceguids
0x18005a43b  mov     r14d, 40Bh
0x18005a441  jz      short loc_18005A451
0x18005a443  lea     edx, [rbx+18h]
0x18005a446  mov     ecx, r14d
0x18005a449  mov     r8, r15
0x18005a44c  call    WPP_SF_
0x18005a451  cmp     cs:?g_pZtCertsNotifWait@@3PEAU_TP_WAIT@@EA, rbx; _TP_WAIT * g_pZtCertsNotifWait
0x18005a458  jnz     loc_18005A5D9
0x18005a45e  xor     r9d, r9d; lpName
0x18005a461  xor     r8d, r8d; bInitialState
0x18005a464  xor     edx, edx; bManualReset
0x18005a466  xor     ecx, ecx; lpEventAttributes
0x18005a468  call    cs:__imp_CreateEventW
0x18005a46e  mov     cs:?g_hZtCertsNotifEvent@@3PEAXEA, rax; void * g_hZtCertsNotifEvent
0x18005a475  test    rax, rax
0x18005a478  jnz     short loc_18005A487
0x18005a47a  call    cs:__imp_GetLastError
0x18005a480  mov     ebx, eax
0x18005a482  jmp     loc_18005A50F
0x18005a487  xor     r8d, r8d; pcbe
0x18005a48a  lea     rcx, ?ZtCertStoreNotificationsWaitCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18005a491  xor     edx, edx; pv
0x18005a493  call    cs:__imp_CreateThreadpoolWait
0x18005a499  mov     cs:?g_pZtCertsNotifWait@@3PEAU_TP_WAIT@@EA, rax; _TP_WAIT * g_pZtCertsNotifWait
0x18005a4a0  test    rax, rax
0x18005a4a3  jz      short loc_18005A47A
0x18005a4a5  xor     edx, edx; dwEncodingType
0x18005a4a7  lea     rax, aMy; "my"
0x18005a4ae  mov     r9d, 28000h; dwFlags
0x18005a4b4  mov     [rsp+58h+pvPara], rax; pvPara
0x18005a4b9  xor     r8d, r8d; hCryptProv
0x18005a4bc  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x18005a4bf  call    cs:__imp_CertOpenStore
0x18005a4c5  mov     cs:?g_hCertStore@@3PEAXEA, rax; void * g_hCertStore
0x18005a4cc  test    rax, rax
0x18005a4cf  jz      short loc_18005A47A
0x18005a4d1  xor     edx, edx; dwFlags
0x18005a4d3  lea     r9, ?g_hZtCertsNotifEvent@@3PEAXEA; pvCtrlPara
0x18005a4da  mov     rcx, rax; hCertStore
0x18005a4dd  lea     r8d, [rdx+2]; dwCtrlType
0x18005a4e1  call    cs:__imp_CertControlStore
0x18005a4e7  test    eax, eax
0x18005a4e9  jnz     short loc_18005A51C
0x18005a4eb  call    cs:__imp_GetLastError
0x18005a4f1  mov     ebx, eax
0x18005a4f3  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18005a4fa  jz      short loc_18005A50F
0x18005a4fc  mov     edx, 19h
0x18005a501  mov     ecx, r14d
0x18005a504  mov     r9d, eax
0x18005a507  mov     r8, r15
0x18005a50a  call    WPP_SF_d
0x18005a50f  test    ebx, ebx
0x18005a511  jz      loc_18005A5D9
0x18005a517  jmp     loc_18005A5D4
0x18005a51c  cmp     cs:g_fVelocityZtdnsProbing, ebx
0x18005a522  jz      short loc_18005A57D
0x18005a524  xor     edi, edi
0x18005a526  cmp     edi, 1
0x18005a529  jnz     short loc_18005A547
0x18005a52b  xor     ecx, ecx
0x18005a52d  xor     eax, eax
0x18005a52f  lock cmpxchg dword ptr cs:g_rgZtHelperSettingsState, ecx
0x18005a537  mov     edx, eax
0x18005a539  xor     eax, eax
0x18005a53b  lock cmpxchg cs:dword_1800ABAB4, ecx
0x18005a543  cmp     edx, eax
0x18005a545  jz      short loc_18005A59F
0x18005a547  lea     rdx, [rsp+58h+arg_0]
0x18005a54c  mov     ecx, edi
0x18005a54e  call    ZtCertUpdateAclIfNeeded
0x18005a553  mov     ebx, eax
0x18005a555  test    eax, eax
0x18005a557  jnz     short loc_18005A56D
0x18005a559  cmp     edi, 1
0x18005a55c  jnz     short loc_18005A564
0x18005a55e  cmp     [rsp+58h+arg_0], eax
0x18005a562  jnz     short loc_18005A595
0x18005a564  inc     edi
0x18005a566  cmp     edi, 2
0x18005a569  jb      short loc_18005A526
0x18005a56b  jmp     short loc_18005A59F
0x18005a56d  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18005a574  jz      short loc_18005A5D4
0x18005a576  mov     edx, 1Ah
0x18005a57b  jmp     short loc_18005A5C6
0x18005a57d  lea     rdx, [rsp+58h+arg_0]
0x18005a582  xor     ecx, ecx
0x18005a584  call    ZtCertUpdateAclIfNeeded
0x18005a589  mov     ebx, eax
0x18005a58b  test    eax, eax
0x18005a58d  jnz     short loc_18005A5B8
0x18005a58f  cmp     [rsp+58h+arg_0], eax
0x18005a593  jz      short loc_18005A59F
0x18005a595  mov     dword ptr cs:g_ZtEnableWhenReadyState, 1
0x18005a59f  mov     rdx, cs:?g_hZtCertsNotifEvent@@3PEAXEA; h
0x18005a5a6  xor     r8d, r8d; pftTimeout
0x18005a5a9  mov     rcx, cs:?g_pZtCertsNotifWait@@3PEAU_TP_WAIT@@EA; pwa
0x18005a5b0  call    cs:__imp_SetThreadpoolWait
0x18005a5b6  jmp     short loc_18005A5D9
0x18005a5b8  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18005a5bf  jz      short loc_18005A5D4
0x18005a5c1  mov     edx, 1Bh
0x18005a5c6  mov     r9d, eax
0x18005a5c9  mov     r8, r15
0x18005a5cc  mov     ecx, r14d
0x18005a5cf  call    WPP_SF_d
0x18005a5d4  call    ZtCleanupClientCertNotif
0x18005a5d9  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18005a5e0  jz      short loc_18005A5F5
0x18005a5e2  mov     edx, 1Ch
0x18005a5e7  mov     ecx, r14d
0x18005a5ea  mov     r9d, ebx
0x18005a5ed  mov     r8, r15
0x18005a5f0  call    WPP_SF_d
0x18005a5f5  mov     eax, ebx
0x18005a5f7  add     rsp, 38h
0x18005a5fb  pop     r15
0x18005a5fd  pop     r14
0x18005a5ff  pop     rdi
0x18005a600  pop     rbx
0x18005a601  retn
```
