# ZtNotifySettingsChange

- ea: `0x180056b70`
- end: `0x180057128`
- name: `ZtNotifySettingsChange`
- size: `1464`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180050040`

## callees

- `0x180033ef8`
- `0x180046ec0`
- `0x1800556b0`
- `0x1800558e0`
- `0x180055ff4`
- `0x1800561bc`
- `0x180056200`
- `0x1800564c8`
- `0x1800569d8`
- `0x180056b70`
- `0x180058f88`
- `0x18005a1c4`
- `0x18005a41c`
- `0x18005c70c`
- `0x180066b8c`
- `0x180066c2c`
- `0x180066c68`
- `0x1800674f0`
- `0x1800675e4`
- `0x180067a10`
- `0x180068754`
- `0x180068c74`
- `0x18007dfa4`
- `0x180086b1c`

## import_xrefs

- `DNSAPI!DnsFreeZtTrustedCa` at `0x180057092`
- `DNSAPI!DnsFreeZtTrustedCa` at `0x180057092`
- `DNSAPI!DnsFreeZtTrustedServers` at `0x180057080`
- `DNSAPI!DnsFreeZtTrustedServers` at `0x180057080`
- `DNSAPI!DnsZtHelperPromoteConfig` at `0x180056f22`
- `DNSAPI!DnsZtHelperPromoteConfig` at `0x180056f22`
- `DNSAPI!DnsFreeZtClientCertConfig` at `0x1800570a0`
- `DNSAPI!DnsFreeZtClientCertConfig` at `0x1800570a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800570f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800570f9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180056c81`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180056c81`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180056eec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180056ffa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180056eec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180056ffa`
- `CRYPT32!CertFreeCertificateContext` at `0x1800570c5`
- `CRYPT32!CertFreeCertificateContext` at `0x1800570c5`

## pseudocode

```c
__int64 __fastcall ZtNotifySettingsChange(int a1, _QWORD *a2, __int64 a3)
{
  __int64 v3; // r14
  HKEY v4; // rbx
  char v7; // al
  unsigned int v9; // edi
  unsigned int v10; // eax
  int v11; // eax
  __int64 v12; // rcx
  unsigned int updated; // eax
  unsigned int v14; // eax
  __int64 v15; // rax
  unsigned int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int128 *v19; // rax
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  unsigned int started; // eax
  char v23; // si
  int v24; // eax
  __int64 v25; // [rsp+38h] [rbp-C8h]
  int v26; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v27; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v28; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v29; // [rsp+70h] [rbp-90h] BYREF
  __int128 v30; // [rsp+80h] [rbp-80h]
  __int128 v31; // [rsp+90h] [rbp-70h]
  __int64 v32; // [rsp+A0h] [rbp-60h]
  __int64 v33; // [rsp+B0h] [rbp-50h] BYREF
  void *v34; // [rsp+B8h] [rbp-48h] BYREF
  void *v35; // [rsp+C0h] [rbp-40h] BYREF
  DnsZtRuleMap *v36; // [rsp+C8h] [rbp-38h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+D0h] [rbp-30h] BYREF
  unsigned int v38; // [rsp+D8h] [rbp-28h] BYREF
  int v39; // [rsp+DCh] [rbp-24h] BYREF
  int v40; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v41; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v42; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v43; // [rsp+100h] [rbp+0h]
  __int128 v44; // [rsp+110h] [rbp+10h]
  __int64 v45; // [rsp+120h] [rbp+20h]

  v3 = a1;
  v38 = 0;
  v33 = 0;
  v4 = 0;
  v45 = 0;
  v27 = 0;
  v36 = 0;
  v34 = 0;
  v35 = 0;
  pCertContext = 0;
  v42 = 0;
  v40 = 0;
  v43 = 0;
  v39 = 0;
  v44 = 0;
  v28 = 0;
  v41 = 0;
  v26 = 0;
  v7 = BYTE1(xmmword_1800AB5A0);
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
  {
    WPP_SF_dqq(a1, 23, (unsigned int)WPP_9eb49e7daef039ee6a83bac14e1bfbb9_Traceguids, a1, (__int64)a2, a3);
    v7 = BYTE1(xmmword_1800AB5A0);
  }
  if ( !g_fVelocityZtdnsProbing )
    return ZtNotifySettingsChange_Old((unsigned int)v3, a2, a3);
  if ( !a2 || !a3 )
  {
    v9 = 87;
    goto LABEL_57;
  }
  v9 = 0;
  if ( !a2[1] )
    goto LABEL_57;
  if ( (unsigned int)v3 > 1 )
  {
    v9 = 87;
    if ( (v7 & 8) != 0 )
      WPP_SF_d(1035, 24, WPP_9eb49e7daef039ee6a83bac14e1bfbb9_Traceguids, 87);
    goto LABEL_57;
  }
  v10 = ZtRegOpenFilters(&v27);
  v9 = v10;
  if ( v10 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_d(1035, 25, WPP_9eb49e7daef039ee6a83bac14e1bfbb9_Traceguids, v10);
    v4 = v27;
    goto LABEL_57;
  }
  AcquireSRWLockExclusive(&g_rwZtSettingsLock);
  v11 = ZtSynchronizeSettingsState(a3, (char *)&g_rgZtHelperSettingsState + 20 * v3);
  v4 = v27;
  if ( !v11 )
    goto LABEL_51;
  updated = ZtUpdateSettingsSaveBackup(
              v12,
              v3,
              (__int64)a2,
              (__int64)&v38,
              (__int64)&v33,
              &v36,
              (__int64)&v34,
              (__int64)&v35,
              (__int64)&pCertContext,
              &v28);
  v9 = updated;
  if ( updated )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    {
      v18 = 26;
LABEL_32:
      WPP_SF_d(1035, v18, WPP_9eb49e7daef039ee6a83bac14e1bfbb9_Traceguids, updated);
      goto LABEL_48;
    }
    goto LABEL_48;
  }
  if ( (_DWORD)v3 == 1 )
    ZtResetEnableWhenReadyState(a2);
  if ( a2[7] )
  {
    v14 = ZtCertUpdateAclIfNeeded((unsigned int)v3, &v26);
    if ( v14 && v14 != 1168 && (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_d(1035, 27, WPP_9eb49e7daef039ee6a83bac14e1bfbb9_Traceguids, v14);
    if ( v26 && (_DWORD)v3 == 1 )
      LODWORD(g_ZtEnableWhenReadyState) = 1;
  }
  v15 = a2[2];
  if ( v15 )
  {
    if ( (unsigned int)(*(_DWORD *)(v15 + 16) - 1) <= 1 )
    {
      v16 = ZtSubscribeClientCertNotif();
      if ( v16 )
      {
        if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
          WPP_SF_d(1035, 28, WPP_9eb49e7daef039ee6a83bac14e1bfbb9_Traceguids, v16);
      }
    }
  }
  v17 = a2[2];
  if ( (_DWORD)v3 )
  {
    v9 = DnsZtProcessReadyToProbe(v17, &v39);
    if ( !v9 )
    {
      if ( (a2[1] & 1) == 0 )
        goto LABEL_37;
      v9 = ZtComputeConfigChange(&g_rgZtConfig[7 * v3], a2[2], &v41);
      if ( !v9 )
      {
        v19 = (__int128 *)a2[2];
        v20 = v19[1];
        v29 = *v19;
        v21 = v19[2];
        v30 = v20;
        *(_QWORD *)&v20 = *((_QWORD *)v19 + 6);
        v31 = v21;
        v32 = v20;
        ZtUpdateConfig(&v29, &g_rgfZtConfigInitialized[v3], &g_rgZtConfig[7 * v3], &v42);
LABEL_37:
        if ( LODWORD(g_rgZtConfig[7 * v3 + 2]) == 2 )
          ZtEtwStartValidation(qword_1800ABAD8, dword_1800ABACC, qword_1800ABB08, qword_1800ABAE8, dword_1800ABAB4);
        v9 = DnsUpdateZtStatus();
        if ( v9 )
          goto LABEL_48;
        goto LABEL_40;
      }
    }
LABEL_48:
    v23 = v28;
    ZtRestoreBackupSettings(
      v3,
      (__int64)&v38,
      (__int64)&v33,
      (__int64)&v36,
      (__int64)&v34,
      (__int64)&v35,
      (__int64)&pCertContext,
      v25,
      v28);
    if ( (_DWORD)v3 )
    {
      v29 = v42;
      v30 = v43;
      v31 = v44;
      v32 = v45;
      ZtUpdateConfig(&v29, &g_rgfZtConfigInitialized[v3], &g_rgZtConfig[7 * v3], 0);
    }
    else
    {
      v24 = IsZtdnsStatusEnabled(&v42);
      ZtApplySettings(0, (__int64)&v42, v23, (__int64)v4, v24, 0);
    }
LABEL_51:
    ReleaseSRWLockExclusive(&g_rwZtSettingsLock);
    goto LABEL_57;
  }
  updated = ZtApplySettings(0, v17, a2[1], (__int64)v4, *(_DWORD *)(v17 + 16) != 0, &v42);
  v9 = updated;
  if ( updated )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      goto LABEL_48;
    v18 = 29;
    goto LABEL_32;
  }
LABEL_40:
  ReleaseSRWLockExclusive(&g_rwZtSettingsLock);
  if ( (_DWORD)v3 == 1 )
  {
    if ( v39 == 2 )
    {
      started = AlertOrStartZtProbeThread(1u);
    }
    else
    {
      if ( v39 != 3 )
        goto LABEL_57;
      started = DnsZtHelperPromoteConfig(a3, &v40);
    }
    v9 = started;
  }
LABEL_57:
  if ( g_fVelocityZtdnsApiRefactor )
  {
    ZtFreeTrustedServers(v38, v33);
    v33 = 0;
    v38 = 0;
    ZtFreeTrustedCa(v34);
    v34 = 0;
    ZtFreeClientCertConfig(v35);
  }
  else
  {
    DnsFreeZtTrustedServers(v38, v33);
    v33 = 0;
    v38 = 0;
    DnsFreeZtTrustedCa(v34);
    v34 = 0;
    DnsFreeZtClientCertConfig(v35);
  }
  v35 = 0;
  if ( v36 )
  {
    DnsZtRuleMap::Release(v36);
    v36 = 0;
  }
  if ( pCertContext )
  {
    CertFreeCertificateContext(pCertContext);
    pCertContext = 0;
  }
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 30, WPP_9eb49e7daef039ee6a83bac14e1bfbb9_Traceguids, v9);
  if ( v4 )
    RegCloseKey(v4);
  return v9;
}

```

## disassembly

```asm
0x180056b70  mov     [rsp-8+arg_18], rbx
0x180056b75  push    rbp
0x180056b76  push    rsi
0x180056b77  push    rdi
0x180056b78  push    r12
0x180056b7a  push    r13
0x180056b7c  push    r14
0x180056b7e  push    r15
0x180056b80  lea     rbp, [rsp-30h]
0x180056b85  sub     rsp, 130h
0x180056b8c  mov     rax, cs:__security_cookie
0x180056b93  xor     rax, rsp
0x180056b96  mov     [rbp+60h+var_38], rax
0x180056b9a  xor     r12d, r12d
0x180056b9d  movsxd  r14, ecx
0x180056ba0  xorps   xmm0, xmm0
0x180056ba3  mov     [rbp+60h+var_88], r12d
0x180056ba7  xor     eax, eax
0x180056ba9  mov     [rbp+60h+var_B0], r12
0x180056bad  mov     ebx, r12d
0x180056bb0  mov     [rbp+60h+var_40], rax
0x180056bb4  mov     [rsp+160h+var_108], rbx
0x180056bb9  mov     r15, r8
0x180056bbc  mov     rsi, rdx
0x180056bbf  mov     [rbp+60h+var_98], r12
0x180056bc3  mov     [rbp+60h+var_A8], r12
0x180056bc7  mov     [rbp+60h+var_A0], r12
0x180056bcb  mov     [rbp+60h+pCertContext], r12
0x180056bcf  movups  [rbp+60h+var_70], xmm0
0x180056bd3  mov     [rbp+60h+var_80], r12d
0x180056bd7  movups  [rbp+60h+var_60], xmm0
0x180056bdb  mov     [rbp+60h+var_84], r12d
0x180056bdf  movups  [rbp+60h+var_50], xmm0
0x180056be3  mov     [rsp+160h+var_100], r12
0x180056be8  mov     [rbp+60h+var_78], r12
0x180056bec  mov     [rsp+160h+var_110], r12d
0x180056bf1  mov     al, byte ptr cs:xmmword_1800AB5A0+1
0x180056bf7  test    al, 8
0x180056bf9  jz      short loc_180056C1F
0x180056bfb  mov     [rsp+160h+var_138], r8
0x180056c00  lea     edx, [r12+17h]
0x180056c05  lea     r8, WPP_9eb49e7daef039ee6a83bac14e1bfbb9_Traceguids
0x180056c0c  mov     [rsp+160h+var_140], rsi
0x180056c11  mov     r9d, r14d
0x180056c14  call    WPP_SF_dqq
0x180056c19  mov     al, byte ptr cs:xmmword_1800AB5A0+1
0x180056c1f  cmp     cs:g_fVelocityZtdnsProbing, r12d
0x180056c26  jnz     short loc_180056C3B
0x180056c28  mov     r8, r15
0x180056c2b  mov     rdx, rsi
0x180056c2e  mov     ecx, r14d
0x180056c31  call    ZtNotifySettingsChange_Old
0x180056c36  jmp     loc_180057101
0x180056c3b  test    rsi, rsi
0x180056c3e  jnz     short loc_180056C4A
0x180056c40  mov     edi, 57h ; 'W'
0x180056c45  jmp     loc_18005704B
0x180056c4a  test    r15, r15
0x180056c4d  jz      short loc_180056C40
0x180056c4f  mov     edi, r12d
0x180056c52  cmp     [rsi+8], r12
0x180056c56  jz      loc_18005704B
0x180056c5c  cmp     r14d, 1
0x180056c60  ja      loc_18005702B
0x180056c66  lea     rcx, [rsp+160h+var_108]
0x180056c6b  call    ZtRegOpenFilters
0x180056c70  mov     edi, eax
0x180056c72  test    eax, eax
0x180056c74  jnz     loc_180057002
0x180056c7a  lea     rcx, g_rwZtSettingsLock; SRWLock
0x180056c81  call    cs:__imp_AcquireSRWLockExclusive
0x180056c87  lea     rax, __ImageBase
0x180056c8e  mov     r13, r14
0x180056c91  lea     rdx, rva g_rgZtHelperSettingsState[rax]
0x180056c98  lea     rcx, ds:0[r14*4]
0x180056ca0  add     rcx, r14
0x180056ca3  lea     rdx, [rdx+rcx*4]
0x180056ca7  mov     rcx, r15
0x180056caa  call    ZtSynchronizeSettingsState
0x180056caf  mov     rbx, [rsp+160h+var_108]
0x180056cb4  test    eax, eax
0x180056cb6  jz      loc_180056FF3
0x180056cbc  lea     rax, [rsp+160h+var_100]
0x180056cc1  mov     r8, rsi
0x180056cc4  mov     [rsp+160h+var_118], rax
0x180056cc9  lea     r9, [rbp+60h+var_88]
0x180056ccd  lea     rax, [rbp+60h+pCertContext]
0x180056cd1  mov     edx, r14d
0x180056cd4  mov     [rsp+160h+var_120], rax
0x180056cd9  lea     rax, [rbp+60h+var_A0]
0x180056cdd  mov     [rsp+160h+var_128], rax
0x180056ce2  lea     rax, [rbp+60h+var_A8]
0x180056ce6  mov     [rsp+160h+var_130], rax
0x180056ceb  lea     rax, [rbp+60h+var_98]
0x180056cef  mov     [rsp+160h+var_138], rax
0x180056cf4  lea     rax, [rbp+60h+var_B0]
0x180056cf8  mov     [rsp+160h+var_140], rax
0x180056cfd  call    ?ZtUpdateSettingsSaveBackup@@YAJ_KW4_ZTDNS_SETTINGS_TYPE@@PEAU_DNS_ZT_SETTINGS@@PEAKPEAPEAU_DNS_ZT_TRUSTED_SERVER@@PEAPEAVDnsZtRuleMap@@PEAPEAU_DNS_ZT_TRUSTED_CA@@PEAPEAU_DNS_ZT_CLIENT_CERT_CONFIG@@PEAPEBU_CERT_CONTEXT@@PEA_K@Z; ZtUpdateSettingsSaveBackup(unsigned __int64,_ZTDNS_SETTINGS_TYPE,_DNS_ZT_SETTINGS *,ulong *,_DNS_ZT_TRUSTED_SERVER * *,DnsZtRuleMap * *,_DNS_ZT_TRUSTED_CA * *,_DNS_ZT_CLIENT_CERT_CONFIG * *,_CERT_CONTEXT const * *,unsigned __int64 *)
0x180056d02  mov     edi, eax
0x180056d04  test    eax, eax
0x180056d06  jnz     loc_180056F2A
0x180056d0c  lea     edi, [rax+1]
0x180056d0f  cmp     r14d, edi
0x180056d12  jnz     short loc_180056D1C
0x180056d14  mov     rcx, rsi
0x180056d17  call    ZtResetEnableWhenReadyState
0x180056d1c  cmp     [rsi+38h], r12
0x180056d20  jz      short loc_180056D6E
0x180056d22  lea     rdx, [rsp+160h+var_110]
0x180056d27  mov     ecx, r14d
0x180056d2a  call    ZtCertUpdateAclIfNeeded
0x180056d2f  test    eax, eax
0x180056d31  jz      short loc_180056D5C
0x180056d33  cmp     eax, 490h
0x180056d38  jz      short loc_180056D5C
0x180056d3a  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180056d41  jz      short loc_180056D5C
0x180056d43  mov     edx, 1Bh
0x180056d48  lea     r8, WPP_9eb49e7daef039ee6a83bac14e1bfbb9_Traceguids
0x180056d4f  mov     ecx, 40Bh
0x180056d54  mov     r9d, eax
0x180056d57  call    WPP_SF_d
0x180056d5c  cmp     [rsp+160h+var_110], r12d
0x180056d61  jz      short loc_180056D6E
0x180056d63  cmp     r14d, edi
0x180056d66  jnz     short loc_180056D6E
0x180056d68  mov     dword ptr cs:g_ZtEnableWhenReadyState, edi
0x180056d6e  mov     rax, [rsi+10h]
0x180056d72  test    rax, rax
0x180056d75  jz      short loc_180056DAB
0x180056d77  mov     eax, [rax+10h]
0x180056d7a  sub     eax, edi
0x180056d7c  cmp     eax, edi
0x180056d7e  ja      short loc_180056DAB
0x180056d80  call    ZtSubscribeClientCertNotif
0x180056d85  test    eax, eax
0x180056d87  jz      short loc_180056DAB
0x180056d89  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180056d90  jz      short loc_180056DAB
0x180056d92  mov     edx, 1Ch
0x180056d97  lea     r8, WPP_9eb49e7daef039ee6a83bac14e1bfbb9_Traceguids
0x180056d9e  mov     ecx, 40Bh
0x180056da3  mov     r9d, eax
0x180056da6  call    WPP_SF_d
0x180056dab  mov     rcx, [rsi+10h]
0x180056daf  test    r14d, r14d
0x180056db2  jnz     short loc_180056E10
0x180056db4  cmp     [rcx+10h], r12d
0x180056db8  lea     rdx, [rbp+60h+var_70]
0x180056dbc  mov     r8, [rsi+8]
0x180056dc0  mov     eax, r12d
0x180056dc3  mov     [rsp+160h+var_138], rdx
0x180056dc8  setnz   al
0x180056dcb  mov     rdx, rcx
0x180056dce  mov     dword ptr [rsp+160h+var_140], eax
0x180056dd2  xor     ecx, ecx
0x180056dd4  mov     r9, rbx
0x180056dd7  call    ?ZtApplySettings@@YAJW4_ZTDNS_SETTINGS_TYPE@@PEAU_DNS_ZT_CONFIG@@_KPEAUHKEY__@@H1@Z; ZtApplySettings(_ZTDNS_SETTINGS_TYPE,_DNS_ZT_CONFIG *,unsigned __int64,HKEY__ *,int,_DNS_ZT_CONFIG *)
0x180056ddc  mov     edi, eax
0x180056dde  test    eax, eax
0x180056de0  jz      loc_180056EE5
0x180056de6  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180056ded  jz      loc_180056F40
0x180056df3  lea     edx, [r14+1Dh]
0x180056df7  mov     ecx, 40Bh
0x180056dfc  lea     r8, WPP_9eb49e7daef039ee6a83bac14e1bfbb9_Traceguids
0x180056e03  mov     r9d, eax
0x180056e06  call    WPP_SF_d
0x180056e0b  jmp     loc_180056F40
0x180056e10  lea     rdx, [rbp+60h+var_84]
0x180056e14  call    DnsZtProcessReadyToProbe
0x180056e19  mov     edi, eax
0x180056e1b  test    eax, eax
0x180056e1d  jnz     loc_180056F40
0x180056e23  test    byte ptr [rsi+8], 1
0x180056e27  jz      short loc_180056E9D
0x180056e29  mov     rdx, [rsi+10h]
0x180056e2d  lea     rcx, g_rgZtConfig
0x180056e34  imul    r12, r13, 38h ; '8'
0x180056e38  lea     r8, [rbp+60h+var_78]
0x180056e3c  add     r12, rcx
0x180056e3f  mov     rcx, r12
0x180056e42  call    ZtComputeConfigChange
0x180056e47  mov     edi, eax
0x180056e49  test    eax, eax
0x180056e4b  jnz     loc_180056F3D
0x180056e51  mov     rax, [rsi+10h]
0x180056e55  lea     r9, [rbp+60h+var_70]
0x180056e59  mov     r8, r12
0x180056e5c  lea     rcx, [rsp+160h+var_F0]
0x180056e61  movups  xmm0, xmmword ptr [rax]
0x180056e64  movups  xmm1, xmmword ptr [rax+10h]
0x180056e68  movaps  [rsp+160h+var_F0], xmm0
0x180056e6d  movups  xmm0, xmmword ptr [rax+20h]
0x180056e71  movaps  [rbp+60h+var_E0], xmm1
0x180056e75  movsd   xmm1, qword ptr [rax+30h]
0x180056e7a  lea     rax, __ImageBase
0x180056e81  lea     rdx, rva g_rgfZtConfigInitialized[rax]
0x180056e88  movaps  [rbp+60h+var_D0], xmm0
0x180056e8c  lea     rdx, [rdx+r14*4]
0x180056e90  movsd   [rbp+60h+var_C0], xmm1
0x180056e95  call    ZtUpdateConfig
0x180056e9a  xor     r12d, r12d
0x180056e9d  imul    rax, r13, 38h ; '8'
0x180056ea1  lea     r13, g_rgZtConfig
0x180056ea8  cmp     dword ptr [rax+r13+10h], 2
0x180056eae  jnz     short loc_180056EDA
0x180056eb0  mov     eax, cs:dword_1800ABAB4
0x180056eb6  mov     r9, cs:qword_1800ABAE8
0x180056ebd  mov     r8, cs:qword_1800ABB08
0x180056ec4  mov     edx, cs:dword_1800ABACC
0x180056eca  mov     rcx, cs:qword_1800ABAD8
0x180056ed1  mov     dword ptr [rsp+160h+var_140], eax
0x180056ed5  call    ZtEtwStartValidation
0x180056eda  call    DnsUpdateZtStatus
0x180056edf  mov     edi, eax
0x180056ee1  test    eax, eax
0x180056ee3  jnz     short loc_180056F47
0x180056ee5  lea     rcx, g_rwZtSettingsLock; SRWLock
0x180056eec  call    cs:__imp_ReleaseSRWLockExclusive
0x180056ef2  cmp     r14d, 1
0x180056ef6  jnz     loc_18005704B
0x180056efc  cmp     [rbp+60h+var_84], 2
0x180056f00  jnz     short loc_180056F11
0x180056f02  mov     ecx, r14d
0x180056f05  call    AlertOrStartZtProbeThread
0x180056f0a  mov     edi, eax
0x180056f0c  jmp     loc_18005704B
0x180056f11  cmp     [rbp+60h+var_84], 3
0x180056f15  jnz     loc_18005704B
0x180056f1b  lea     rdx, [rbp+60h+var_80]
0x180056f1f  mov     rcx, r15
0x180056f22  call    cs:__imp_DnsZtHelperPromoteConfig
0x180056f28  jmp     short loc_180056F0A
0x180056f2a  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180056f31  jz      short loc_180056F40
0x180056f33  mov     edx, 1Ah
0x180056f38  jmp     loc_180056DF7
0x180056f3d  xor     r12d, r12d
0x180056f40  lea     r13, g_rgZtConfig
0x180056f47  mov     rsi, [rsp+160h+var_100]
0x180056f4c  lea     rax, [rbp+60h+pCertContext]
0x180056f50  mov     [rsp+160h+var_120], rsi
0x180056f55  lea     r9, [rbp+60h+var_98]
0x180056f59  mov     [rsp+160h+var_130], rax
0x180056f5e  lea     r8, [rbp+60h+var_B0]
0x180056f62  lea     rax, [rbp+60h+var_A0]
0x180056f66  mov     ecx, r14d
0x180056f69  mov     [rsp+160h+var_138], rax
0x180056f6e  lea     rdx, [rbp+60h+var_88]
0x180056f72  lea     rax, [rbp+60h+var_A8]
0x180056f76  mov     [rsp+160h+var_140], rax
0x180056f7b  call    ?ZtRestoreBackupSettings@@YAXW4_ZTDNS_SETTINGS_TYPE@@PEAKPEAPEAU_DNS_ZT_TRUSTED_SERVER@@PEAPEAVDnsZtRuleMap@@PEAPEAU_DNS_ZT_TRUSTED_CA@@PEAPEAU_DNS_ZT_CLIENT_CERT_CONFIG@@PEAPEBU_CERT_CONTEXT@@K_K@Z; ZtRestoreBackupSettings(_ZTDNS_SETTINGS_TYPE,ulong *,_DNS_ZT_TRUSTED_SERVER * *,DnsZtRuleMap * *,_DNS_ZT_TRUSTED_CA * *,_DNS_ZT_CLIENT_CERT_CONFIG * *,_CERT_CONTEXT const * *,ulong,unsigned __int64)
0x180056f80  test    r14d, r14d
0x180056f83  jnz     short loc_180056FAA
0x180056f85  lea     rcx, [rbp+60h+var_70]
0x180056f89  call    IsZtdnsStatusEnabled
0x180056f8e  mov     [rsp+160h+var_138], r12
0x180056f93  lea     rdx, [rbp+60h+var_70]
0x180056f97  mov     r9, rbx
0x180056f9a  mov     dword ptr [rsp+160h+var_140], eax
0x180056f9e  mov     r8, rsi
0x180056fa1  xor     ecx, ecx
0x180056fa3  call    ?ZtApplySettings@@YAJW4_ZTDNS_SETTINGS_TYPE@@PEAU_DNS_ZT_CONFIG@@_KPEAUHKEY__@@H1@Z; ZtApplySettings(_ZTDNS_SETTINGS_TYPE,_DNS_ZT_CONFIG *,unsigned __int64,HKEY__ *,int,_DNS_ZT_CONFIG *)
0x180056fa8  jmp     short loc_180056FF3
0x180056faa  movups  xmm0, [rbp+60h+var_70]
0x180056fae  lea     rcx, __ImageBase
0x180056fb5  xor     r9d, r9d
0x180056fb8  movups  xmm1, [rbp+60h+var_60]
0x180056fbc  lea     rdx, rva g_rgfZtConfigInitialized[rcx]
0x180056fc3  movaps  [rsp+160h+var_F0], xmm0
0x180056fc8  lea     rdx, [rdx+r14*4]
0x180056fcc  movups  xmm0, [rbp+60h+var_50]
0x180056fd0  lea     rcx, [rsp+160h+var_F0]
0x180056fd5  imul    r8, r14, 38h ; '8'
0x180056fd9  movaps  [rbp+60h+var_E0], xmm1
0x180056fdd  movsd   xmm1, [rbp+60h+var_40]
0x180056fe2  movaps  [rbp+60h+var_D0], xmm0
0x180056fe6  movsd   [rbp+60h+var_C0], xmm1
0x180056feb  add     r8, r13
0x180056fee  call    ZtUpdateConfig
0x180056ff3  lea     rcx, g_rwZtSettingsLock; SRWLock
0x180056ffa  call    cs:__imp_ReleaseSRWLockExclusive
0x180057000  jmp     short loc_18005704B
0x180057002  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180057009  jz      short loc_180057024
0x18005700b  mov     edx, 19h
0x180057010  lea     r8, WPP_9eb49e7daef039ee6a83bac14e1bfbb9_Traceguids
0x180057017  mov     ecx, 40Bh
0x18005701c  mov     r9d, eax
0x18005701f  call    WPP_SF_d
0x180057024  mov     rbx, [rsp+160h+var_108]
0x180057029  jmp     short loc_18005704B
0x18005702b  mov     edi, 57h ; 'W'
0x180057030  test    al, 8
0x180057032  jz      short loc_18005704B
0x180057034  lea     edx, [rdi-3Fh]
0x180057037  mov     ecx, 40Bh
0x18005703c  mov     r9d, edi
0x18005703f  lea     r8, WPP_9eb49e7daef039ee6a83bac14e1bfbb9_Traceguids
  ... truncated ...
```
