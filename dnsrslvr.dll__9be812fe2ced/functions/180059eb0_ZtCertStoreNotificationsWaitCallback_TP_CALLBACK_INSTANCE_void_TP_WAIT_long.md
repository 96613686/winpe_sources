# ZtCertStoreNotificationsWaitCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x180059eb0`
- end: `0x18005a117`
- name: `?ZtCertStoreNotificationsWaitCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `615`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, __int64 WaitResult)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x180055780`
- `0x1800559d4`
- `0x180059eb0`
- `0x18005a120`
- `0x18005a1c4`
- `0x180086700`
- `0x180086b1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059f99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059f99`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180059fc2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180059fc2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005a0d1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005a0d1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005a0ec`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005a0ec`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180059f6c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180059f6c`
- `CRYPT32!CertControlStore` at `0x180059f5d`
- `CRYPT32!CertControlStore` at `0x180059f86`
- `CRYPT32!CertControlStore` at `0x180059f5d`
- `CRYPT32!CertControlStore` at `0x180059f86`

## pseudocode

```c
void __fastcall ZtCertStoreNotificationsWaitCallback(
        PTP_CALLBACK_INSTANCE Instance,
        PVOID Context,
        PTP_WAIT Wait,
        __int64 WaitResult)
{
  int v4; // ebx
  unsigned int v5; // esi
  DWORD v6; // ebp
  BOOL v7; // eax
  DWORD LastError; // eax
  unsigned int i; // esi
  unsigned int updated; // eax
  unsigned int started; // eax
  __int64 v12; // rdx
  unsigned int v13; // eax
  _DWORD v14[14]; // [rsp+20h] [rbp-38h] BYREF

  v14[0] = 0;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_(1035, 15, WPP_da5f48c7dcef3941ae809be7a10ca70f_Traceguids);
  if ( g_fVelocityZtdnsProbing )
  {
    if ( (unsigned int)ZtResyncStore(Instance, Context, Wait, WaitResult) != 87 )
    {
      v4 = 1;
LABEL_17:
      AcquireSRWLockExclusive(&g_rwZtSettingsLock);
      if ( g_fVelocityZtdnsProbing )
      {
        for ( i = 0; i < 2; ++i )
        {
          v14[0] = 0;
          if ( i == 1
            && _InterlockedCompareExchange((volatile signed __int32 *)&g_rgZtHelperSettingsState, 0, 0) == _InterlockedCompareExchange(&dword_1800ABAB4, 0, 0) )
          {
            break;
          }
          updated = ZtCertUpdateAclIfNeeded(i, v14);
          if ( updated && (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
            WPP_SF_d(1035, 19, WPP_da5f48c7dcef3941ae809be7a10ca70f_Traceguids, updated);
          if ( i == 1 )
          {
            if ( v14[0] )
            {
              LODWORD(g_ZtEnableWhenReadyState) = 1;
              started = DnsZtInitiateProbing();
              if ( started )
              {
                if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
                {
                  v12 = 20;
                  goto LABEL_38;
                }
              }
            }
          }
        }
      }
      else
      {
        v13 = ZtCertUpdateAclIfNeeded(0, v14);
        if ( v13 && (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
          WPP_SF_d(1035, 21, WPP_da5f48c7dcef3941ae809be7a10ca70f_Traceguids, v13);
        if ( v14[0] )
        {
          LODWORD(g_ZtEnableWhenReadyState) = 1;
          started = DnsZtStartDriverBasedOnInternalStatus();
          if ( started )
          {
            if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
            {
              v12 = 22;
LABEL_38:
              WPP_SF_d(1035, v12, WPP_da5f48c7dcef3941ae809be7a10ca70f_Traceguids, started);
            }
          }
        }
      }
      ReleaseSRWLockExclusive(&g_rwZtSettingsLock);
      if ( v4 )
        SetThreadpoolWait(g_pZtCertsNotifWait, g_hZtCertsNotifEvent, 0);
      goto LABEL_41;
    }
    if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      return;
    WPP_SF_d(1035, 16, WPP_da5f48c7dcef3941ae809be7a10ca70f_Traceguids, 87);
  }
  else if ( g_hCertStore && g_hZtCertsNotifEvent )
  {
    v5 = 0;
    v6 = 0;
    v7 = CertControlStore(g_hCertStore, 0, 1u, &g_hZtCertsNotifEvent);
    while ( 1 )
    {
      v4 = v7;
      if ( v7 )
        goto LABEL_17;
      if ( v5 >= 3 )
      {
        LastError = GetLastError();
        if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
          WPP_SF_d(1035, 18, WPP_da5f48c7dcef3941ae809be7a10ca70f_Traceguids, LastError);
        goto LABEL_17;
      }
      Sleep(v6);
      v7 = CertControlStore(g_hCertStore, 0, 1u, &g_hZtCertsNotifEvent);
      ++v5;
      v6 += 50;
    }
  }
LABEL_41:
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_(1035, 23, WPP_da5f48c7dcef3941ae809be7a10ca70f_Traceguids);
}

```

## disassembly

```asm
0x180059eb0  push    rbx
0x180059eb2  push    rbp
0x180059eb3  push    rsi
0x180059eb4  push    r12
0x180059eb6  push    r13
0x180059eb8  sub     rsp, 30h
0x180059ebc  mov     [rsp+58h+var_38], 0
0x180059ec4  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180059ecb  lea     r13, WPP_da5f48c7dcef3941ae809be7a10ca70f_Traceguids
0x180059ed2  mov     r12d, 40Bh
0x180059ed8  jz      short loc_180059EEA
0x180059eda  mov     edx, 0Fh
0x180059edf  mov     ecx, r12d
0x180059ee2  mov     r8, r13
0x180059ee5  call    WPP_SF_
0x180059eea  cmp     cs:g_fVelocityZtdnsProbing, 0
0x180059ef1  jz      short loc_180059F2E
0x180059ef3  call    ZtResyncStore
0x180059ef8  mov     r9d, 57h ; 'W'
0x180059efe  cmp     eax, r9d
0x180059f01  jz      short loc_180059F0C
0x180059f03  lea     ebx, [r9-56h]
0x180059f07  jmp     loc_180059FBB
0x180059f0c  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180059f13  jz      loc_18005A10B
0x180059f19  mov     edx, 10h
0x180059f1e  mov     ecx, r12d
0x180059f21  mov     r8, r13
0x180059f24  call    WPP_SF_d
0x180059f29  jmp     loc_18005A0F2
0x180059f2e  mov     rcx, cs:?g_hCertStore@@3PEAXEA; hCertStore
0x180059f35  test    rcx, rcx
0x180059f38  jz      loc_18005A0F2
0x180059f3e  cmp     cs:?g_hZtCertsNotifEvent@@3PEAXEA, 0; void * g_hZtCertsNotifEvent
0x180059f46  jz      loc_18005A0F2
0x180059f4c  xor     esi, esi
0x180059f4e  lea     r9, ?g_hZtCertsNotifEvent@@3PEAXEA; pvCtrlPara
0x180059f55  xor     ebp, ebp
0x180059f57  xor     edx, edx; dwFlags
0x180059f59  lea     r8d, [rsi+1]; dwCtrlType
0x180059f5d  call    cs:__imp_CertControlStore
0x180059f63  jmp     short loc_180059F91
0x180059f65  cmp     esi, 3
0x180059f68  jnb     short loc_180059F99
0x180059f6a  mov     ecx, ebp; dwMilliseconds
0x180059f6c  call    cs:__imp_Sleep
0x180059f72  mov     rcx, cs:?g_hCertStore@@3PEAXEA; hCertStore
0x180059f79  lea     r9, ?g_hZtCertsNotifEvent@@3PEAXEA; pvCtrlPara
0x180059f80  xor     edx, edx; dwFlags
0x180059f82  lea     r8d, [rdx+1]; dwCtrlType
0x180059f86  call    cs:__imp_CertControlStore
0x180059f8c  inc     esi
0x180059f8e  add     ebp, 32h ; '2'
0x180059f91  mov     ebx, eax
0x180059f93  test    eax, eax
0x180059f95  jz      short loc_180059F65
0x180059f97  jmp     short loc_180059FBB
0x180059f99  call    cs:__imp_GetLastError
0x180059f9f  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180059fa6  jz      short loc_180059FBB
0x180059fa8  mov     edx, 12h
0x180059fad  mov     ecx, r12d
0x180059fb0  mov     r9d, eax
0x180059fb3  mov     r8, r13
0x180059fb6  call    WPP_SF_d
0x180059fbb  lea     rcx, g_rwZtSettingsLock; SRWLock
0x180059fc2  call    cs:__imp_AcquireSRWLockExclusive
0x180059fc8  cmp     cs:g_fVelocityZtdnsProbing, 0
0x180059fcf  jz      loc_18005A068
0x180059fd5  xor     esi, esi
0x180059fd7  mov     [rsp+58h+var_38], 0
0x180059fdf  cmp     esi, 1
0x180059fe2  jnz     short loc_18005A004
0x180059fe4  xor     ecx, ecx
0x180059fe6  xor     eax, eax
0x180059fe8  lock cmpxchg dword ptr cs:g_rgZtHelperSettingsState, ecx
0x180059ff0  mov     edx, eax
0x180059ff2  xor     eax, eax
0x180059ff4  lock cmpxchg cs:dword_1800ABAB4, ecx
0x180059ffc  cmp     edx, eax
0x180059ffe  jz      loc_18005A0CA
0x18005a004  lea     rdx, [rsp+58h+var_38]
0x18005a009  mov     ecx, esi
0x18005a00b  call    ZtCertUpdateAclIfNeeded
0x18005a010  test    eax, eax
0x18005a012  jz      short loc_18005A030
0x18005a014  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18005a01b  jz      short loc_18005A030
0x18005a01d  mov     edx, 13h
0x18005a022  mov     ecx, r12d
0x18005a025  mov     r9d, eax
0x18005a028  mov     r8, r13
0x18005a02b  call    WPP_SF_d
0x18005a030  cmp     esi, 1
0x18005a033  jnz     short loc_18005A054
0x18005a035  cmp     [rsp+58h+var_38], 0
0x18005a03a  jz      short loc_18005A054
0x18005a03c  mov     dword ptr cs:g_ZtEnableWhenReadyState, esi
0x18005a042  call    DnsZtInitiateProbing
0x18005a047  test    eax, eax
0x18005a049  jz      short loc_18005A054
0x18005a04b  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18005a052  jnz     short loc_18005A061
0x18005a054  inc     esi
0x18005a056  cmp     esi, 2
0x18005a059  jb      loc_180059FD7
0x18005a05f  jmp     short loc_18005A0CA
0x18005a061  mov     edx, 14h
0x18005a066  jmp     short loc_18005A0BC
0x18005a068  lea     rdx, [rsp+58h+var_38]
0x18005a06d  xor     ecx, ecx
0x18005a06f  call    ZtCertUpdateAclIfNeeded
0x18005a074  test    eax, eax
0x18005a076  jz      short loc_18005A094
0x18005a078  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18005a07f  jz      short loc_18005A094
0x18005a081  mov     edx, 15h
0x18005a086  mov     ecx, r12d
0x18005a089  mov     r9d, eax
0x18005a08c  mov     r8, r13
0x18005a08f  call    WPP_SF_d
0x18005a094  cmp     [rsp+58h+var_38], 0
0x18005a099  jz      short loc_18005A0CA
0x18005a09b  mov     dword ptr cs:g_ZtEnableWhenReadyState, 1
0x18005a0a5  call    DnsZtStartDriverBasedOnInternalStatus
0x18005a0aa  test    eax, eax
0x18005a0ac  jz      short loc_18005A0CA
0x18005a0ae  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18005a0b5  jz      short loc_18005A0CA
0x18005a0b7  mov     edx, 16h
0x18005a0bc  mov     r9d, eax
0x18005a0bf  mov     r8, r13
0x18005a0c2  mov     ecx, r12d
0x18005a0c5  call    WPP_SF_d
0x18005a0ca  lea     rcx, g_rwZtSettingsLock; SRWLock
0x18005a0d1  call    cs:__imp_ReleaseSRWLockExclusive
0x18005a0d7  test    ebx, ebx
0x18005a0d9  jz      short loc_18005A0F2
0x18005a0db  mov     rdx, cs:?g_hZtCertsNotifEvent@@3PEAXEA; h
0x18005a0e2  xor     r8d, r8d; pftTimeout
0x18005a0e5  mov     rcx, cs:?g_pZtCertsNotifWait@@3PEAU_TP_WAIT@@EA; pwa
0x18005a0ec  call    cs:__imp_SetThreadpoolWait
0x18005a0f2  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18005a0f9  jz      short loc_18005A10B
0x18005a0fb  mov     edx, 17h
0x18005a100  mov     ecx, r12d
0x18005a103  mov     r8, r13
0x18005a106  call    WPP_SF_
0x18005a10b  add     rsp, 30h
0x18005a10f  pop     r13
0x18005a111  pop     r12
0x18005a113  pop     rsi
0x18005a114  pop     rbp
0x18005a115  pop     rbx
0x18005a116  retn
```
