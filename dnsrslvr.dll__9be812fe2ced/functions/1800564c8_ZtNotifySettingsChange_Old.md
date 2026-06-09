# ZtNotifySettingsChange_Old

- ea: `0x1800564c8`
- end: `0x1800569d0`
- name: `ZtNotifySettingsChange_Old`
- size: `1288`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180056b70`

## callees

- `0x180033ef8`
- `0x180046ec0`
- `0x1800557e4`
- `0x180055ff4`
- `0x180056200`
- `0x1800564c8`
- `0x1800569d8`
- `0x18005a1c4`
- `0x18005a41c`
- `0x1800674f0`
- `0x1800675e4`
- `0x180067a10`
- `0x180068754`
- `0x180068c74`
- `0x18007dfa4`
- `0x180086b1c`

## import_xrefs

- `DNSAPI!DnsFreeZtTrustedCa` at `0x18005694c`
- `DNSAPI!DnsFreeZtTrustedCa` at `0x18005694c`
- `DNSAPI!DnsFreeZtTrustedServers` at `0x18005693a`
- `DNSAPI!DnsFreeZtTrustedServers` at `0x18005693a`
- `DNSAPI!DnsZtHelperPromoteConfig` at `0x180056805`
- `DNSAPI!DnsZtHelperPromoteConfig` at `0x180056805`
- `DNSAPI!DnsFreeZtClientCertConfig` at `0x18005695a`
- `DNSAPI!DnsFreeZtClientCertConfig` at `0x18005695a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800569a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800569a1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800565b8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800565b8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800567f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800568e2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800567f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800568e2`
- `CRYPT32!CertFreeCertificateContext` at `0x18005696d`
- `CRYPT32!CertFreeCertificateContext` at `0x18005696d`

## pseudocode

```c
__int64 __fastcall ZtNotifySettingsChange_Old(int a1, __int64 a2, __int64 a3)
{
  __int64 v3; // r14
  HKEY v4; // rbx
  char v7; // al
  unsigned int v8; // edi
  unsigned int v9; // eax
  int v10; // eax
  __int64 v11; // rcx
  unsigned int updated; // eax
  unsigned int v13; // eax
  __int64 v14; // rax
  unsigned int v15; // eax
  __int64 v16; // rax
  __int64 v17; // rdx
  __int128 *v18; // rax
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  char v21; // si
  int v22; // eax
  __int64 v24; // [rsp+38h] [rbp-C8h]
  int v25; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v26; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v27; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v28; // [rsp+70h] [rbp-90h] BYREF
  __int128 v29; // [rsp+80h] [rbp-80h]
  __int128 v30; // [rsp+90h] [rbp-70h]
  __int64 v31; // [rsp+A0h] [rbp-60h]
  __int64 v32; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v33; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v34; // [rsp+C0h] [rbp-40h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+C8h] [rbp-38h] BYREF
  DnsZtRuleMap *v36; // [rsp+D0h] [rbp-30h] BYREF
  unsigned int v37; // [rsp+D8h] [rbp-28h] BYREF
  int v38; // [rsp+DCh] [rbp-24h] BYREF
  __int64 v39; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v40; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v41; // [rsp+F8h] [rbp-8h]
  __int128 v42; // [rsp+108h] [rbp+8h]
  __int64 v43; // [rsp+118h] [rbp+18h]

  v3 = a1;
  v37 = 0;
  v32 = 0;
  v4 = 0;
  v43 = 0;
  v26 = 0;
  v36 = 0;
  v33 = 0;
  v34 = 0;
  pCertContext = 0;
  v40 = 0;
  v27 = 0;
  v41 = 0;
  v39 = 0;
  v42 = 0;
  v38 = 0;
  v25 = 0;
  v7 = BYTE1(xmmword_1800AB5A0);
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
  {
    WPP_SF_dqq(a1, 15, (unsigned int)WPP_9eb49e7daef039ee6a83bac14e1bfbb9_Traceguids, a1, a2, a3);
    v7 = BYTE1(xmmword_1800AB5A0);
  }
  if ( !a2 || !a3 )
  {
    v8 = 87;
    goto LABEL_50;
  }
  v8 = 0;
  if ( *(_QWORD *)(a2 + 8) )
  {
    if ( (unsigned int)v3 > 1 )
    {
      v8 = 87;
      if ( (v7 & 8) != 0 )
        WPP_SF_d(1035, 16, WPP_9eb49e7daef039ee6a83bac14e1bfbb9_Traceguids, 87);
    }
    else
    {
      v9 = ZtRegOpenFilters(&v26);
      v8 = v9;
      if ( !v9 )
      {
        AcquireSRWLockExclusive(&g_rwZtSettingsLock);
        v10 = ZtSynchronizeSettingsState(a3, (char *)&g_rgZtHelperSettingsState + 20 * v3);
        v4 = v26;
        if ( !v10 )
        {
LABEL_44:
          ReleaseSRWLockExclusive(&g_rwZtSettingsLock);
          goto LABEL_50;
        }
        updated = ZtUpdateSettingsSaveBackup(
                    v11,
                    v3,
                    a2,
                    (__int64)&v37,
                    (__int64)&v32,
                    &v36,
                    (__int64)&v33,
                    (__int64)&v34,
                    (__int64)&pCertContext,
                    &v27);
        v8 = updated;
        if ( updated )
        {
          if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
          {
            v17 = 18;
LABEL_33:
            WPP_SF_d(1035, v17, WPP_9eb49e7daef039ee6a83bac14e1bfbb9_Traceguids, updated);
          }
        }
        else
        {
          ZtResetEnableWhenReadyState(a2);
          if ( !(_DWORD)v3 )
          {
            if ( (*(_BYTE *)(a2 + 8) & 8) != 0 && *(_QWORD *)(a2 + 56) )
            {
              v13 = ZtCertUpdateAclIfNeeded(0, &v25);
              v8 = v13;
              if ( v13 && v13 != 1168 )
              {
                if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
                  WPP_SF_d(1035, 19, WPP_9eb49e7daef039ee6a83bac14e1bfbb9_Traceguids, v13);
                v8 = 0;
              }
              if ( v25 )
                LODWORD(g_ZtEnableWhenReadyState) = 1;
            }
            v14 = *(_QWORD *)(a2 + 16);
            if ( v14 )
            {
              if ( (unsigned int)(*(_DWORD *)(v14 + 16) - 1) <= 1 )
              {
                v15 = ZtSubscribeClientCertNotif();
                v8 = v15;
                if ( v15 )
                {
                  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
                    WPP_SF_d(1035, 20, WPP_9eb49e7daef039ee6a83bac14e1bfbb9_Traceguids, v15);
                  v16 = *(_QWORD *)(a2 + 8);
LABEL_28:
                  if ( (v16 & 0x19) != 0 )
                  {
                    v8 = DnsZtProcessReadyToBeEnabled(0, *(_QWORD *)(a2 + 16), &v38);
                    if ( v8 )
                      goto LABEL_41;
                  }
                  updated = ZtApplySettings(0, *(_QWORD *)(a2 + 16), *(_QWORD *)(a2 + 8), (__int64)v4, v38, &v40);
                  v8 = updated;
                  if ( updated )
                  {
                    if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
                      goto LABEL_41;
                    v17 = 21;
                    goto LABEL_33;
                  }
                  goto LABEL_37;
                }
              }
            }
          }
          v16 = *(_QWORD *)(a2 + 8);
          if ( !(_DWORD)v3 )
            goto LABEL_28;
          if ( (v16 & 1) == 0 )
          {
LABEL_37:
            ReleaseSRWLockExclusive(&g_rwZtSettingsLock);
            if ( (_DWORD)v3 == 1 )
              v8 = DnsZtHelperPromoteConfig(a3, 0);
            goto LABEL_50;
          }
          v8 = ZtComputeConfigChange(&g_rgZtConfig[7 * v3], *(_QWORD *)(a2 + 16), &v39);
          if ( !v8 )
          {
            v18 = *(__int128 **)(a2 + 16);
            v19 = v18[1];
            v28 = *v18;
            v20 = v18[2];
            v29 = v19;
            *(_QWORD *)&v19 = *((_QWORD *)v18 + 6);
            v30 = v20;
            v31 = v19;
            ZtUpdateConfig(&v28, &g_rgfZtConfigInitialized[v3], &g_rgZtConfig[7 * v3], &v40);
            goto LABEL_37;
          }
        }
LABEL_41:
        v21 = v27;
        ZtRestoreBackupSettings(
          v3,
          (__int64)&v37,
          (__int64)&v32,
          (__int64)&v36,
          (__int64)&v33,
          (__int64)&v34,
          (__int64)&pCertContext,
          v24,
          v27);
        if ( (_DWORD)v3 )
        {
          v28 = v40;
          v29 = v41;
          v30 = v42;
          v31 = v43;
          ZtUpdateConfig(&v28, &g_rgfZtConfigInitialized[v3], &g_rgZtConfig[7 * v3], 0);
        }
        else
        {
          v22 = IsZtdnsStatusEnabled(&v40);
          ZtApplySettings(0, (__int64)&v40, v21, (__int64)v4, v22, 0);
        }
        goto LABEL_44;
      }
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        WPP_SF_d(1035, 17, WPP_9eb49e7daef039ee6a83bac14e1bfbb9_Traceguids, v9);
      v4 = v26;
    }
  }
LABEL_50:
  DnsFreeZtTrustedServers(v37, v32);
  v32 = 0;
  v37 = 0;
  DnsFreeZtTrustedCa(v33);
  v33 = 0;
  DnsFreeZtClientCertConfig(v34);
  v34 = 0;
  if ( pCertContext )
  {
    CertFreeCertificateContext(pCertContext);
    pCertContext = 0;
  }
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 22, WPP_9eb49e7daef039ee6a83bac14e1bfbb9_Traceguids, v8);
  if ( v4 )
    RegCloseKey(v4);
  return v8;
}

```

## disassembly

```asm
0x1800564c8  mov     [rsp-8+arg_18], rbx
0x1800564cd  push    rbp
0x1800564ce  push    rsi
0x1800564cf  push    rdi
0x1800564d0  push    r12
0x1800564d2  push    r13
0x1800564d4  push    r14
0x1800564d6  push    r15
0x1800564d8  lea     rbp, [rsp-30h]
0x1800564dd  sub     rsp, 130h
0x1800564e4  mov     rax, cs:__security_cookie
0x1800564eb  xor     rax, rsp
0x1800564ee  mov     [rbp+60h+var_40], rax
0x1800564f2  xor     r15d, r15d
0x1800564f5  movsxd  r14, ecx
0x1800564f8  xorps   xmm0, xmm0
0x1800564fb  mov     [rbp+60h+var_88], r15d
0x1800564ff  xor     eax, eax
0x180056501  mov     [rbp+60h+var_B0], r15
0x180056505  mov     ebx, r15d
0x180056508  mov     [rbp+60h+var_48], rax
0x18005650c  mov     [rsp+160h+var_108], rbx
0x180056511  mov     r12, r8
0x180056514  mov     rsi, rdx
0x180056517  mov     [rbp+60h+var_90], r15
0x18005651b  mov     [rbp+60h+var_A8], r15
0x18005651f  mov     [rbp+60h+var_A0], r15
0x180056523  mov     [rbp+60h+pCertContext], r15
0x180056527  movups  [rbp+60h+var_78], xmm0
0x18005652b  mov     [rsp+160h+var_100], r15
0x180056530  movups  [rbp+60h+var_68], xmm0
0x180056534  mov     [rbp+60h+var_80], r15
0x180056538  movups  [rbp+60h+var_58], xmm0
0x18005653c  mov     [rbp+60h+var_84], r15d
0x180056540  mov     [rsp+160h+var_110], r15d
0x180056545  mov     al, byte ptr cs:xmmword_1800AB5A0+1
0x18005654b  test    al, 8
0x18005654d  jz      short loc_180056572
0x18005654f  mov     [rsp+160h+var_138], r8
0x180056554  lea     edx, [r15+0Fh]
0x180056558  lea     r8, WPP_9eb49e7daef039ee6a83bac14e1bfbb9_Traceguids
0x18005655f  mov     [rsp+160h+var_140], rsi
0x180056564  mov     r9d, r14d
0x180056567  call    WPP_SF_dqq
0x18005656c  mov     al, byte ptr cs:xmmword_1800AB5A0+1
0x180056572  test    rsi, rsi
0x180056575  jnz     short loc_180056581
0x180056577  mov     edi, 57h ; 'W'
0x18005657c  jmp     loc_180056933
0x180056581  test    r12, r12
0x180056584  jz      short loc_180056577
0x180056586  mov     edi, r15d
0x180056589  cmp     [rsi+8], r15
0x18005658d  jz      loc_180056933
0x180056593  cmp     r14d, 1
0x180056597  ja      loc_180056913
0x18005659d  lea     rcx, [rsp+160h+var_108]
0x1800565a2  call    ZtRegOpenFilters
0x1800565a7  mov     edi, eax
0x1800565a9  test    eax, eax
0x1800565ab  jnz     loc_1800568EA
0x1800565b1  lea     rcx, g_rwZtSettingsLock; SRWLock
0x1800565b8  call    cs:__imp_AcquireSRWLockExclusive
0x1800565be  lea     rax, __ImageBase
0x1800565c5  mov     r13, r14
0x1800565c8  lea     rdx, rva g_rgZtHelperSettingsState[rax]
0x1800565cf  lea     rcx, ds:0[r14*4]
0x1800565d7  add     rcx, r14
0x1800565da  lea     rdx, [rdx+rcx*4]
0x1800565de  mov     rcx, r12
0x1800565e1  call    ZtSynchronizeSettingsState
0x1800565e6  mov     rbx, [rsp+160h+var_108]
0x1800565eb  test    eax, eax
0x1800565ed  jz      loc_1800568DB
0x1800565f3  lea     rax, [rsp+160h+var_100]
0x1800565f8  mov     r8, rsi
0x1800565fb  mov     [rsp+160h+var_118], rax
0x180056600  lea     r9, [rbp+60h+var_88]
0x180056604  lea     rax, [rbp+60h+pCertContext]
0x180056608  mov     edx, r14d
0x18005660b  mov     [rsp+160h+var_120], rax
0x180056610  lea     rax, [rbp+60h+var_A0]
0x180056614  mov     [rsp+160h+var_128], rax
0x180056619  lea     rax, [rbp+60h+var_A8]
0x18005661d  mov     [rsp+160h+var_130], rax
0x180056622  lea     rax, [rbp+60h+var_90]
0x180056626  mov     [rsp+160h+var_138], rax
0x18005662b  lea     rax, [rbp+60h+var_B0]
0x18005662f  mov     [rsp+160h+var_140], rax
0x180056634  call    ?ZtUpdateSettingsSaveBackup@@YAJ_KW4_ZTDNS_SETTINGS_TYPE@@PEAU_DNS_ZT_SETTINGS@@PEAKPEAPEAU_DNS_ZT_TRUSTED_SERVER@@PEAPEAVDnsZtRuleMap@@PEAPEAU_DNS_ZT_TRUSTED_CA@@PEAPEAU_DNS_ZT_CLIENT_CERT_CONFIG@@PEAPEBU_CERT_CONTEXT@@PEA_K@Z; ZtUpdateSettingsSaveBackup(unsigned __int64,_ZTDNS_SETTINGS_TYPE,_DNS_ZT_SETTINGS *,ulong *,_DNS_ZT_TRUSTED_SERVER * *,DnsZtRuleMap * *,_DNS_ZT_TRUSTED_CA * *,_DNS_ZT_CLIENT_CERT_CONFIG * *,_CERT_CONTEXT const * *,unsigned __int64 *)
0x180056639  mov     edi, eax
0x18005663b  test    eax, eax
0x18005663d  jnz     loc_180056812
0x180056643  mov     rcx, rsi
0x180056646  call    ZtResetEnableWhenReadyState
0x18005664b  test    r14d, r14d
0x18005664e  jnz     loc_1800566F4
0x180056654  test    byte ptr [rsi+8], 8
0x180056658  jz      short loc_1800566AE
0x18005665a  cmp     [rsi+38h], r15
0x18005665e  jz      short loc_1800566AE
0x180056660  lea     rdx, [rsp+160h+var_110]
0x180056665  xor     ecx, ecx
0x180056667  call    ZtCertUpdateAclIfNeeded
0x18005666c  mov     edi, eax
0x18005666e  test    eax, eax
0x180056670  jz      short loc_18005669D
0x180056672  cmp     eax, 490h
0x180056677  jz      short loc_18005669D
0x180056679  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180056680  jz      short loc_18005669A
0x180056682  lea     edx, [r14+13h]
0x180056686  mov     ecx, 40Bh
0x18005668b  mov     r9d, eax
0x18005668e  lea     r8, WPP_9eb49e7daef039ee6a83bac14e1bfbb9_Traceguids
0x180056695  call    WPP_SF_d
0x18005669a  mov     edi, r15d
0x18005669d  cmp     [rsp+160h+var_110], r15d
0x1800566a2  jz      short loc_1800566AE
0x1800566a4  mov     dword ptr cs:g_ZtEnableWhenReadyState, 1
0x1800566ae  mov     rax, [rsi+10h]
0x1800566b2  test    rax, rax
0x1800566b5  jz      short loc_1800566F4
0x1800566b7  mov     eax, [rax+10h]
0x1800566ba  dec     eax
0x1800566bc  cmp     eax, 1
0x1800566bf  ja      short loc_1800566F4
0x1800566c1  call    ZtSubscribeClientCertNotif
0x1800566c6  mov     edi, eax
0x1800566c8  test    eax, eax
0x1800566ca  jz      short loc_1800566F4
0x1800566cc  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800566d3  jz      short loc_1800566EE
0x1800566d5  mov     edx, 14h
0x1800566da  lea     r8, WPP_9eb49e7daef039ee6a83bac14e1bfbb9_Traceguids
0x1800566e1  mov     ecx, 40Bh
0x1800566e6  mov     r9d, eax
0x1800566e9  call    WPP_SF_d
0x1800566ee  mov     rax, [rsi+8]
0x1800566f2  jmp     short loc_1800566FD
0x1800566f4  mov     rax, [rsi+8]
0x1800566f8  test    r14d, r14d
0x1800566fb  jnz     short loc_180056771
0x1800566fd  test    al, 19h
0x1800566ff  jz      short loc_18005671A
0x180056701  mov     rdx, [rsi+10h]
0x180056705  lea     r8, [rbp+60h+var_84]
0x180056709  xor     ecx, ecx
0x18005670b  call    DnsZtProcessReadyToBeEnabled
0x180056710  mov     edi, eax
0x180056712  test    eax, eax
0x180056714  jnz     loc_180056828
0x18005671a  mov     eax, [rbp+60h+var_84]
0x18005671d  lea     rcx, [rbp+60h+var_78]
0x180056721  mov     r8, [rsi+8]
0x180056725  mov     r9, rbx
0x180056728  mov     rdx, [rsi+10h]
0x18005672c  mov     [rsp+160h+var_138], rcx
0x180056731  xor     ecx, ecx
0x180056733  mov     dword ptr [rsp+160h+var_140], eax
0x180056737  call    ?ZtApplySettings@@YAJW4_ZTDNS_SETTINGS_TYPE@@PEAU_DNS_ZT_CONFIG@@_KPEAUHKEY__@@H1@Z; ZtApplySettings(_ZTDNS_SETTINGS_TYPE,_DNS_ZT_CONFIG *,unsigned __int64,HKEY__ *,int,_DNS_ZT_CONFIG *)
0x18005673c  mov     edi, eax
0x18005673e  test    eax, eax
0x180056740  jz      loc_1800567E9
0x180056746  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18005674d  jz      loc_180056828
0x180056753  mov     edx, 15h
0x180056758  mov     ecx, 40Bh
0x18005675d  lea     r8, WPP_9eb49e7daef039ee6a83bac14e1bfbb9_Traceguids
0x180056764  mov     r9d, eax
0x180056767  call    WPP_SF_d
0x18005676c  jmp     loc_180056828
0x180056771  test    al, 1
0x180056773  jz      short loc_1800567E9
0x180056775  mov     rdx, [rsi+10h]
0x180056779  lea     rcx, g_rgZtConfig
0x180056780  imul    r15, r13, 38h ; '8'
0x180056784  lea     r8, [rbp+60h+var_80]
0x180056788  add     r15, rcx
0x18005678b  mov     rcx, r15
0x18005678e  call    ZtComputeConfigChange
0x180056793  mov     edi, eax
0x180056795  test    eax, eax
0x180056797  jnz     loc_180056825
0x18005679d  mov     rax, [rsi+10h]
0x1800567a1  lea     rcx, __ImageBase
0x1800567a8  lea     rdx, rva g_rgfZtConfigInitialized[rcx]
0x1800567af  mov     r8, r15
0x1800567b2  lea     rdx, [rdx+r14*4]
0x1800567b6  lea     r9, [rbp+60h+var_78]
0x1800567ba  movups  xmm0, xmmword ptr [rax]
0x1800567bd  lea     rcx, [rsp+160h+var_F0]
0x1800567c2  movups  xmm1, xmmword ptr [rax+10h]
0x1800567c6  movaps  [rsp+160h+var_F0], xmm0
0x1800567cb  movups  xmm0, xmmword ptr [rax+20h]
0x1800567cf  movaps  [rbp+60h+var_E0], xmm1
0x1800567d3  movsd   xmm1, qword ptr [rax+30h]
0x1800567d8  movaps  [rbp+60h+var_D0], xmm0
0x1800567dc  movsd   [rbp+60h+var_C0], xmm1
0x1800567e1  call    ZtUpdateConfig
0x1800567e6  xor     r15d, r15d
0x1800567e9  lea     rcx, g_rwZtSettingsLock; SRWLock
0x1800567f0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800567f6  cmp     r14d, 1
0x1800567fa  jnz     loc_180056933
0x180056800  xor     edx, edx
0x180056802  mov     rcx, r12
0x180056805  call    cs:__imp_DnsZtHelperPromoteConfig
0x18005680b  mov     edi, eax
0x18005680d  jmp     loc_180056933
0x180056812  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180056819  jz      short loc_180056828
0x18005681b  mov     edx, 12h
0x180056820  jmp     loc_180056758
0x180056825  xor     r15d, r15d
0x180056828  mov     rsi, [rsp+160h+var_100]
0x18005682d  lea     rax, [rbp+60h+pCertContext]
0x180056831  mov     [rsp+160h+var_120], rsi
0x180056836  lea     r9, [rbp+60h+var_90]
0x18005683a  mov     [rsp+160h+var_130], rax
0x18005683f  lea     r8, [rbp+60h+var_B0]
0x180056843  lea     rax, [rbp+60h+var_A0]
0x180056847  mov     ecx, r14d
0x18005684a  mov     [rsp+160h+var_138], rax
0x18005684f  lea     rdx, [rbp+60h+var_88]
0x180056853  lea     rax, [rbp+60h+var_A8]
0x180056857  mov     [rsp+160h+var_140], rax
0x18005685c  call    ?ZtRestoreBackupSettings@@YAXW4_ZTDNS_SETTINGS_TYPE@@PEAKPEAPEAU_DNS_ZT_TRUSTED_SERVER@@PEAPEAVDnsZtRuleMap@@PEAPEAU_DNS_ZT_TRUSTED_CA@@PEAPEAU_DNS_ZT_CLIENT_CERT_CONFIG@@PEAPEBU_CERT_CONTEXT@@K_K@Z; ZtRestoreBackupSettings(_ZTDNS_SETTINGS_TYPE,ulong *,_DNS_ZT_TRUSTED_SERVER * *,DnsZtRuleMap * *,_DNS_ZT_TRUSTED_CA * *,_DNS_ZT_CLIENT_CERT_CONFIG * *,_CERT_CONTEXT const * *,ulong,unsigned __int64)
0x180056861  test    r14d, r14d
0x180056864  jnz     short loc_18005688B
0x180056866  lea     rcx, [rbp+60h+var_78]
0x18005686a  call    IsZtdnsStatusEnabled
0x18005686f  mov     [rsp+160h+var_138], r15
0x180056874  lea     rdx, [rbp+60h+var_78]
0x180056878  mov     r9, rbx
0x18005687b  mov     dword ptr [rsp+160h+var_140], eax
0x18005687f  mov     r8, rsi
0x180056882  xor     ecx, ecx
0x180056884  call    ?ZtApplySettings@@YAJW4_ZTDNS_SETTINGS_TYPE@@PEAU_DNS_ZT_CONFIG@@_KPEAUHKEY__@@H1@Z; ZtApplySettings(_ZTDNS_SETTINGS_TYPE,_DNS_ZT_CONFIG *,unsigned __int64,HKEY__ *,int,_DNS_ZT_CONFIG *)
0x180056889  jmp     short loc_1800568DB
0x18005688b  movups  xmm0, [rbp+60h+var_78]
0x18005688f  lea     rcx, g_rgZtConfig
0x180056896  xor     r9d, r9d
0x180056899  movups  xmm1, [rbp+60h+var_68]
0x18005689d  imul    r8, r14, 38h ; '8'
0x1800568a1  movaps  [rsp+160h+var_F0], xmm0
0x1800568a6  movups  xmm0, [rbp+60h+var_58]
0x1800568aa  movaps  [rbp+60h+var_E0], xmm1
0x1800568ae  movsd   xmm1, [rbp+60h+var_48]
0x1800568b3  add     r8, rcx
0x1800568b6  movaps  [rbp+60h+var_D0], xmm0
0x1800568ba  lea     rcx, __ImageBase
0x1800568c1  movsd   [rbp+60h+var_C0], xmm1
0x1800568c6  lea     rdx, rva g_rgfZtConfigInitialized[rcx]
0x1800568cd  lea     rdx, [rdx+r14*4]
0x1800568d1  lea     rcx, [rsp+160h+var_F0]
0x1800568d6  call    ZtUpdateConfig
0x1800568db  lea     rcx, g_rwZtSettingsLock; SRWLock
0x1800568e2  call    cs:__imp_ReleaseSRWLockExclusive
0x1800568e8  jmp     short loc_180056933
0x1800568ea  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800568f1  jz      short loc_18005690C
0x1800568f3  mov     edx, 11h
0x1800568f8  lea     r8, WPP_9eb49e7daef039ee6a83bac14e1bfbb9_Traceguids
0x1800568ff  mov     ecx, 40Bh
0x180056904  mov     r9d, eax
0x180056907  call    WPP_SF_d
0x18005690c  mov     rbx, [rsp+160h+var_108]
0x180056911  jmp     short loc_180056933
0x180056913  mov     edi, 57h ; 'W'
0x180056918  test    al, 8
0x18005691a  jz      short loc_180056933
0x18005691c  lea     edx, [rdi-47h]
0x18005691f  mov     ecx, 40Bh
0x180056924  mov     r9d, edi
0x180056927  lea     r8, WPP_9eb49e7daef039ee6a83bac14e1bfbb9_Traceguids
0x18005692e  call    WPP_SF_d
0x180056933  mov     rdx, [rbp+60h+var_B0]
0x180056937  mov     ecx, [rbp+60h+var_88]
0x18005693a  call    cs:__imp_DnsFreeZtTrustedServers
0x180056940  mov     rcx, [rbp+60h+var_A8]
0x180056944  mov     [rbp+60h+var_B0], r15
0x180056948  mov     [rbp+60h+var_88], r15d
0x18005694c  call    cs:__imp_DnsFreeZtTrustedCa
0x180056952  mov     rcx, [rbp+60h+var_A0]
0x180056956  mov     [rbp+60h+var_A8], r15
0x18005695a  call    cs:__imp_DnsFreeZtClientCertConfig
0x180056960  mov     rcx, [rbp+60h+pCertContext]; pCertContext
0x180056964  mov     [rbp+60h+var_A0], r15
0x180056968  test    rcx, rcx
0x18005696b  jz      short loc_180056977
0x18005696d  call    cs:__imp_CertFreeCertificateContext
0x180056973  mov     [rbp+60h+pCertContext], r15
0x180056977  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18005697e  jz      short loc_180056999
0x180056980  mov     edx, 16h
0x180056985  lea     r8, WPP_9eb49e7daef039ee6a83bac14e1bfbb9_Traceguids
0x18005698c  mov     ecx, 40Bh
0x180056991  mov     r9d, edi
0x180056994  call    WPP_SF_d
  ... truncated ...
```
