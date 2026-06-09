# ZtProbeThread(void)

- ea: `0x18005c150`
- end: `0x18005c5c7`
- name: `?ZtProbeThread@@YAJXZ`
- size: `1143`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config`

## callees

- `0x180008b00`
- `0x180046ec0`
- `0x180056a20`
- `0x180058964`
- `0x180058e50`
- `0x18005ad10`
- `0x18005b368`
- `0x18005b564`
- `0x18005b88c`
- `0x18005ba54`
- `0x18005bb78`
- `0x18005bc6c`
- `0x18005bee4`
- `0x18005c150`
- `0x18005c5d0`
- `0x18005c698`
- `0x180066c68`
- `0x1800810a0`
- `0x180086700`
- `0x180086b1c`

## import_xrefs

- `DNSAPI!DnsFreeZtTrustedServers` at `0x18005c271`
- `DNSAPI!DnsFreeZtTrustedServers` at `0x18005c564`
- `DNSAPI!DnsFreeZtTrustedServers` at `0x18005c271`
- `DNSAPI!DnsFreeZtTrustedServers` at `0x18005c564`
- `DNSAPI!DnsZtHelperPromoteConfig` at `0x18005c40d`
- `DNSAPI!DnsZtHelperPromoteConfig` at `0x18005c40d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c2ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c2ba`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18005c293`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18005c293`

## pseudocode

```c
__int64 __fastcall ZtProbeThread(PVOID Parameter)
{
  unsigned int *v1; // rbx
  __int64 v2; // rsi
  unsigned int v3; // edi
  unsigned int v4; // r12d
  unsigned int v5; // r13d
  DWORD v6; // r14d
  __int64 v7; // rcx
  _BYTE *v8; // rax
  DWORD v9; // eax
  int v10; // ecx
  int v11; // r9d
  DWORD LastError; // eax
  int TrustedServersWithSettingsState; // eax
  __int64 v14; // rcx
  __int64 v15; // r8
  int v16; // r14d
  int v17; // r15d
  BOOL v18; // eax
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r8
  unsigned int v22; // r14d
  bool v23; // zf
  int v24; // eax
  unsigned int v25; // ebx
  DWORD v27; // [rsp+30h] [rbp-79h]
  unsigned int v28; // [rsp+34h] [rbp-75h] BYREF
  unsigned int *v29; // [rsp+38h] [rbp-71h] BYREF
  __int64 v30; // [rsp+40h] [rbp-69h] BYREF
  struct _RTL_CRITICAL_SECTION *v31; // [rsp+48h] [rbp-61h] BYREF
  __int64 v32; // [rsp+50h] [rbp-59h]
  __int128 v33; // [rsp+60h] [rbp-49h] BYREF
  int v34; // [rsp+70h] [rbp-39h]
  unsigned int v35; // [rsp+80h] [rbp-29h] BYREF
  _BYTE v36[20]; // [rsp+88h] [rbp-21h] BYREF
  HANDLE Handles[2]; // [rsp+A0h] [rbp-9h] BYREF

  v1 = 0;
  v29 = 0;
  v30 = 0;
  v2 = 0;
  v28 = 0;
  v3 = 0;
  memset(v36, 0, sizeof(v36));
  *(_OWORD *)Handles = 0;
  v32 = 0;
  v31 = &g_csZtProbeThread;
  v35 = 0;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_(1035, 19, WPP_a8da9155b8bb3d04d08e272bf258165a_Traceguids);
  AutoCritSec::Lock((AutoCritSec *)&v31);
  if ( !g_hZtdnsProbeEvent )
  {
    v4 = -2147024809;
    HIDWORD(v29) = 237;
    goto LABEL_70;
  }
  if ( !g_hZtdnsProbeStopEvent )
  {
    v4 = -2147024809;
    HIDWORD(v29) = 238;
    goto LABEL_70;
  }
  Handles[0] = g_hZtdnsProbeEvent;
  v5 = 0;
  Handles[1] = g_hZtdnsProbeStopEvent;
  v4 = 0;
  AutoCritSec::Unlock((AutoCritSec *)&v31);
  v6 = -1;
LABEL_8:
  v27 = v6;
  while ( 1 )
  {
    v7 = 20;
    v8 = v36;
    do
    {
      *v8++ = 0;
      --v7;
    }
    while ( v7 );
    v35 = 0;
    if ( v3 || v2 )
    {
      if ( g_fVelocityZtdnsApiRefactor )
        ZtFreeTrustedServers(v3, v2);
      else
        DnsFreeZtTrustedServers(v3, v2);
      v3 = 0;
      v28 = 0;
      v2 = 0;
      v30 = 0;
    }
    v9 = WaitForMultipleObjects(2u, Handles, 0, v6);
    if ( !v9 )
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        WPP_SF_(1035, 20, WPP_a8da9155b8bb3d04d08e272bf258165a_Traceguids);
      v5 = 0;
      goto LABEL_29;
    }
    if ( v9 == 1 )
      break;
    if ( v9 != 258 )
    {
      v6 = -1;
      if ( v9 != -1 )
      {
        v4 = -2147023537;
        HIDWORD(v29) = 334;
        goto LABEL_68;
      }
      LastError = GetLastError();
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        WPP_SF_d(1035, 23, WPP_a8da9155b8bb3d04d08e272bf258165a_Traceguids, LastError);
      goto LABEL_8;
    }
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_(1035, 22, WPP_a8da9155b8bb3d04d08e272bf258165a_Traceguids);
    v5 = v5 != -1 ? v5 + 1 : 1;
LABEL_29:
    TrustedServersWithSettingsState = ZtGetTrustedServersWithSettingsState(
                                        v10,
                                        (unsigned int)&v28,
                                        (unsigned int)&v30,
                                        v11,
                                        (__int64)v36);
    v2 = v30;
    v3 = v28;
    if ( TrustedServersWithSettingsState )
      goto LABEL_30;
    if ( v30 && v28 )
    {
      if ( v1 && (unsigned int)ZtProbeList::AllServersValidated((ZtProbeList *)v1) )
      {
        v16 = 1;
        if ( (byte_1800ABE01 & 1) != 0 )
          McTemplateK0q_EventWriteTransfer(v14, ZTDNS_EVENT_ZT_CONFIGURATION_VALIDATED, v15, v1[1]);
      }
      else
      {
        v16 = 0;
      }
      v17 = *(_DWORD *)v36;
      v18 = v1 && v1[1] != *(_DWORD *)v36;
      if ( !v16 )
        goto LABEL_46;
      if ( v18 )
      {
        if ( (byte_1800ABE01 & 1) != 0 )
          McTemplateK0q_EventWriteTransfer(v14, ZTDNS_EVENT_ZT_CONFIGURATION_STALE, v15, v1[1]);
LABEL_46:
        if ( v1 )
        {
          if ( v1[1] == v17 )
          {
            ZtProbeList::TraceProbeStatuses((ZtProbeList *)v1);
LABEL_58:
            v6 = ZtThreadCalculateWaitTime(v5);
            if ( (unsigned int)ZtProbeList::SendProbes((ZtProbeList *)v1) )
              v6 = 60000;
            goto LABEL_8;
          }
          ZtProbeList::Shutdown((ZtProbeList *)v1);
          ZtProbeList::Release((ZtProbeList *)v1);
          v29 = 0;
        }
        v34 = *(_DWORD *)&v36[16];
        v33 = *(_OWORD *)v36;
        v24 = ZtThreadBuildProbeList(&v29, &v33, v2, v3);
        v1 = v29;
        if ( v24 < 0 )
        {
LABEL_30:
          v6 = 60000;
          goto LABEL_8;
        }
        v5 = 0;
        goto LABEL_58;
      }
      v22 = DnsZtHelperPromoteConfig(v1 + 1, &v35);
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        WPP_SF_DL(v20, v19, v21, v22, v35);
      ZtEtwConfigurationState(v22, v35, v1[1]);
      v23 = v22 == 0;
      v6 = v27;
      if ( v23 && v35 == 1 && (unsigned int)CheckBeforeShutdownZtProbeThread() )
        goto LABEL_68;
    }
    else
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        WPP_SF_(1035, 24, WPP_a8da9155b8bb3d04d08e272bf258165a_Traceguids);
      if ( (unsigned int)CheckBeforeShutdownZtProbeThread() )
        goto LABEL_68;
    }
  }
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_(1035, 21, WPP_a8da9155b8bb3d04d08e272bf258165a_Traceguids);
LABEL_68:
  if ( v1 )
  {
    ZtProbeList::Shutdown((ZtProbeList *)v1);
    ZtProbeList::Release((ZtProbeList *)v1);
  }
LABEL_70:
  if ( v3 || v2 )
  {
    if ( g_fVelocityZtdnsApiRefactor )
      ZtFreeTrustedServers(v3, v2);
    else
      DnsFreeZtTrustedServers(v3, v2);
  }
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 26, WPP_a8da9155b8bb3d04d08e272bf258165a_Traceguids, v4);
  v25 = WX_WIN32_FROM_HR(v4);
  if ( (_DWORD)v32 )
    AutoCritSec::Unlock((AutoCritSec *)&v31);
  return v25;
}

```

## disassembly

```asm
0x18005c150  push    rbp
0x18005c152  push    rbx
0x18005c153  push    rsi
0x18005c154  push    rdi
0x18005c155  push    r12
0x18005c157  push    r13
0x18005c159  push    r14
0x18005c15b  push    r15
0x18005c15d  lea     rbp, [rsp-1Fh]
0x18005c162  sub     rsp, 0C8h
0x18005c169  mov     rax, cs:__security_cookie
0x18005c170  xor     rax, rsp
0x18005c173  mov     [rbp+57h+var_50], rax
0x18005c177  xor     r15d, r15d
0x18005c17a  lea     rax, ?g_csZtProbeThread@@3VWxCriticalSection@@A; WxCriticalSection g_csZtProbeThread
0x18005c181  mov     ebx, r15d
0x18005c184  mov     dword ptr [rbp+57h+var_C8+4], r15d
0x18005c188  xorps   xmm0, xmm0
0x18005c18b  mov     [rbp-71h], rbx
0x18005c18f  xorps   xmm1, xmm1
0x18005c192  mov     [rbp+57h+var_C0], r15
0x18005c196  mov     esi, r15d
0x18005c199  mov     [rbp+57h+var_CC], r15d
0x18005c19d  mov     edi, r15d
0x18005c1a0  mov     dword ptr [rbp+57h+var_78], r15d
0x18005c1a4  movups  xmmword ptr [rbp+57h+Handles], xmm0
0x18005c1a8  mov     [rbp+57h+var_B0], r15
0x18005c1ac  movups  [rbp+57h+var_78+4], xmm1
0x18005c1b0  mov     [rbp+57h+var_B8], rax
0x18005c1b4  mov     [rbp+57h+var_80], r15d
0x18005c1b8  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18005c1bf  jz      short loc_18005C1D6
0x18005c1c1  lea     edx, [r15+13h]
0x18005c1c5  mov     ecx, 40Bh
0x18005c1ca  lea     r8, WPP_a8da9155b8bb3d04d08e272bf258165a_Traceguids
0x18005c1d1  call    WPP_SF_
0x18005c1d6  lea     rcx, [rbp+57h+var_B8]; this
0x18005c1da  call    ?Lock@AutoCritSec@@QEAAXXZ; AutoCritSec::Lock(void)
0x18005c1df  mov     rcx, cs:?g_hZtdnsProbeEvent@@3PEAXEA; void * g_hZtdnsProbeEvent
0x18005c1e6  test    rcx, rcx
0x18005c1e9  jnz     short loc_18005C1FD
0x18005c1eb  mov     r12d, 80070057h
0x18005c1f1  mov     dword ptr [rbp+57h+var_C8+4], 0EDh
0x18005c1f8  jmp     loc_18005C546
0x18005c1fd  mov     rax, cs:?g_hZtdnsProbeStopEvent@@3PEAXEA; void * g_hZtdnsProbeStopEvent
0x18005c204  test    rax, rax
0x18005c207  jnz     short loc_18005C21B
0x18005c209  mov     r12d, 80070057h
0x18005c20f  mov     dword ptr [rbp+57h+var_C8+4], 0EEh
0x18005c216  jmp     loc_18005C546
0x18005c21b  mov     [rbp+57h+Handles], rcx
0x18005c21f  mov     r13d, r15d
0x18005c222  lea     rcx, [rbp+57h+var_B8]; this
0x18005c226  mov     [rbp+57h+Handles+8], rax
0x18005c22a  mov     r12d, r15d
0x18005c22d  call    ?Unlock@AutoCritSec@@QEAAXXZ; AutoCritSec::Unlock(void)
0x18005c232  or      r14d, 0FFFFFFFFh
0x18005c236  mov     [rbp+57h+var_D0], r14d
0x18005c23a  mov     ecx, 14h
0x18005c23f  lea     rax, [rbp+57h+var_78]
0x18005c243  mov     [rax], r15b
0x18005c246  inc     rax
0x18005c249  sub     rcx, 1
0x18005c24d  jnz     short loc_18005C243
0x18005c24f  mov     [rbp+57h+var_80], r15d
0x18005c253  test    edi, edi
0x18005c255  jnz     short loc_18005C25C
0x18005c257  test    rsi, rsi
0x18005c25a  jz      short loc_18005C285
0x18005c25c  cmp     cs:g_fVelocityZtdnsApiRefactor, r15d
0x18005c263  mov     rdx, rsi
0x18005c266  mov     ecx, edi
0x18005c268  jz      short loc_18005C271
0x18005c26a  call    ZtFreeTrustedServers
0x18005c26f  jmp     short loc_18005C277
0x18005c271  call    cs:__imp_DnsFreeZtTrustedServers
0x18005c277  mov     edi, r15d
0x18005c27a  mov     [rbp+57h+var_CC], r15d
0x18005c27e  mov     rsi, r15
0x18005c281  mov     [rbp+57h+var_C0], r15
0x18005c285  xor     r8d, r8d; bWaitAll
0x18005c288  lea     rdx, [rbp+57h+Handles]; lpHandles
0x18005c28c  mov     r9d, r14d; dwMilliseconds
0x18005c28f  lea     ecx, [r8+2]; nCount
0x18005c293  call    cs:__imp_WaitForMultipleObjects
0x18005c299  test    eax, eax
0x18005c29b  jz      short loc_18005C318
0x18005c29d  cmp     eax, 1
0x18005c2a0  jz      loc_18005C512
0x18005c2a6  cmp     eax, 102h
0x18005c2ab  jz      short loc_18005C2EB
0x18005c2ad  or      r14d, 0FFFFFFFFh
0x18005c2b1  cmp     eax, r14d
0x18005c2b4  jnz     loc_18005C503
0x18005c2ba  call    cs:__imp_GetLastError
0x18005c2c0  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18005c2c7  jz      loc_18005C236
0x18005c2cd  mov     edx, 17h
0x18005c2d2  lea     r8, WPP_a8da9155b8bb3d04d08e272bf258165a_Traceguids
0x18005c2d9  mov     ecx, 40Bh
0x18005c2de  mov     r9d, eax
0x18005c2e1  call    WPP_SF_d
0x18005c2e6  jmp     loc_18005C236
0x18005c2eb  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18005c2f2  jz      short loc_18005C30A
0x18005c2f4  mov     edx, 16h
0x18005c2f9  lea     r8, WPP_a8da9155b8bb3d04d08e272bf258165a_Traceguids
0x18005c300  mov     ecx, 40Bh
0x18005c305  call    WPP_SF_
0x18005c30a  cmp     r13d, 0FFFFFFFFh
0x18005c30e  sbb     eax, eax
0x18005c310  and     r13d, eax
0x18005c313  inc     r13d
0x18005c316  jmp     short loc_18005C33A
0x18005c318  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18005c31f  jz      short loc_18005C337
0x18005c321  mov     edx, 14h
0x18005c326  lea     r8, WPP_a8da9155b8bb3d04d08e272bf258165a_Traceguids
0x18005c32d  mov     ecx, 40Bh
0x18005c332  call    WPP_SF_
0x18005c337  mov     r13d, r15d
0x18005c33a  lea     rax, [rbp+57h+var_78]
0x18005c33e  lea     r8, [rbp+57h+var_C0]
0x18005c342  mov     [rsp+100h+var_E0], rax
0x18005c347  lea     rdx, [rbp+57h+var_CC]
0x18005c34b  call    ZtGetTrustedServersWithSettingsState
0x18005c350  mov     rsi, [rbp+57h+var_C0]
0x18005c354  mov     edi, [rbp+57h+var_CC]
0x18005c357  test    eax, eax
0x18005c359  jz      short loc_18005C366
0x18005c35b  mov     r14d, 0EA60h
0x18005c361  jmp     loc_18005C236
0x18005c366  test    rsi, rsi
0x18005c369  jz      loc_18005C4D5
0x18005c36f  test    edi, edi
0x18005c371  jz      loc_18005C4D5
0x18005c377  test    rbx, rbx
0x18005c37a  jz      short loc_18005C3A9
0x18005c37c  mov     rcx, rbx; this
0x18005c37f  call    ?AllServersValidated@ZtProbeList@@QEAAHXZ; ZtProbeList::AllServersValidated(void)
0x18005c384  test    eax, eax
0x18005c386  jz      short loc_18005C3A9
0x18005c388  mov     r14d, 1
0x18005c38e  test    cs:byte_1800ABE01, r14b
0x18005c395  jz      short loc_18005C3AC
0x18005c397  mov     r9d, [rbx+4]
0x18005c39b  lea     rdx, ZTDNS_EVENT_ZT_CONFIGURATION_VALIDATED
0x18005c3a2  call    McTemplateK0q_EventWriteTransfer
0x18005c3a7  jmp     short loc_18005C3AC
0x18005c3a9  mov     r14d, r15d
0x18005c3ac  mov     r15d, dword ptr [rbp+57h+var_78]
0x18005c3b0  test    rbx, rbx
0x18005c3b3  jz      short loc_18005C3C2
0x18005c3b5  cmp     [rbx+4], r15d
0x18005c3b9  jz      short loc_18005C3C2
0x18005c3bb  mov     eax, 1
0x18005c3c0  jmp     short loc_18005C3C4
0x18005c3c2  xor     eax, eax
0x18005c3c4  test    r14d, r14d
0x18005c3c7  jz      short loc_18005C3E6
0x18005c3c9  test    eax, eax
0x18005c3cb  jz      short loc_18005C405
0x18005c3cd  test    cs:byte_1800ABE01, 1
0x18005c3d4  jz      short loc_18005C3E6
0x18005c3d6  mov     r9d, [rbx+4]
0x18005c3da  lea     rdx, ZTDNS_EVENT_ZT_CONFIGURATION_STALE
0x18005c3e1  call    McTemplateK0q_EventWriteTransfer
0x18005c3e6  test    rbx, rbx
0x18005c3e9  jz      loc_18005C47F
0x18005c3ef  mov     rcx, rbx; this
0x18005c3f2  cmp     [rbx+4], r15d
0x18005c3f6  jnz     short loc_18005C469
0x18005c3f8  call    ?TraceProbeStatuses@ZtProbeList@@QEAAXXZ; ZtProbeList::TraceProbeStatuses(void)
0x18005c3fd  xor     r15d, r15d
0x18005c400  jmp     loc_18005C4B2
0x18005c405  lea     rdx, [rbp+57h+var_80]
0x18005c409  lea     rcx, [rbx+4]
0x18005c40d  call    cs:__imp_DnsZtHelperPromoteConfig
0x18005c413  mov     r14d, eax
0x18005c416  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18005c41d  jz      short loc_18005C42E
0x18005c41f  mov     eax, [rbp+57h+var_80]
0x18005c422  mov     r9d, r14d
0x18005c425  mov     dword ptr [rsp+100h+var_E0], eax
0x18005c429  call    WPP_SF_DL
0x18005c42e  mov     r8d, [rbx+4]
0x18005c432  mov     ecx, r14d
0x18005c435  mov     edx, [rbp+57h+var_80]
0x18005c438  call    ZtEtwConfigurationState
0x18005c43d  xor     r15d, r15d
0x18005c440  test    r14d, r14d
0x18005c443  mov     r14d, [rbp+57h+var_D0]
0x18005c447  jnz     loc_18005C23A
0x18005c44d  cmp     [rbp+57h+var_80], 1
0x18005c451  jnz     loc_18005C23A
0x18005c457  call    CheckBeforeShutdownZtProbeThread
0x18005c45c  test    eax, eax
0x18005c45e  jnz     loc_18005C531
0x18005c464  jmp     loc_18005C23A
0x18005c469  call    ?Shutdown@ZtProbeList@@QEAAXXZ; ZtProbeList::Shutdown(void)
0x18005c46e  mov     rcx, rbx; this
0x18005c471  call    ?Release@ZtProbeList@@QEAAKXZ; ZtProbeList::Release(void)
0x18005c476  xor     r15d, r15d
0x18005c479  mov     [rbp-71h], r15
0x18005c47d  jmp     short loc_18005C482
0x18005c47f  xor     r15d, r15d
0x18005c482  movups  xmm0, [rbp+57h+var_78]
0x18005c486  mov     eax, [rbp+57h+var_68]
0x18005c489  lea     rdx, [rbp+57h+var_A0]
0x18005c48d  mov     r9d, edi
0x18005c490  mov     [rbp+57h+var_90], eax
0x18005c493  mov     r8, rsi
0x18005c496  movaps  [rbp+57h+var_A0], xmm0
0x18005c49a  lea     rcx, [rbp+57h+var_C8]
0x18005c49e  call    ZtThreadBuildProbeList
0x18005c4a3  mov     rbx, [rbp+57h+var_C8]
0x18005c4a7  test    eax, eax
0x18005c4a9  js      loc_18005C35B
0x18005c4af  mov     r13d, r15d
0x18005c4b2  mov     ecx, r13d
0x18005c4b5  call    ZtThreadCalculateWaitTime
0x18005c4ba  mov     rcx, rbx; this
0x18005c4bd  mov     r14d, eax
0x18005c4c0  call    ?SendProbes@ZtProbeList@@QEAAJXZ; ZtProbeList::SendProbes(void)
0x18005c4c5  test    eax, eax
0x18005c4c7  mov     eax, 0EA60h
0x18005c4cc  cmovnz  r14d, eax
0x18005c4d0  jmp     loc_18005C236
0x18005c4d5  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18005c4dc  jz      short loc_18005C4F4
0x18005c4de  mov     edx, 18h
0x18005c4e3  lea     r8, WPP_a8da9155b8bb3d04d08e272bf258165a_Traceguids
0x18005c4ea  mov     ecx, 40Bh
0x18005c4ef  call    WPP_SF_
0x18005c4f4  call    CheckBeforeShutdownZtProbeThread
0x18005c4f9  test    eax, eax
0x18005c4fb  jz      loc_18005C23A
0x18005c501  jmp     short loc_18005C531
0x18005c503  mov     r12d, 8007054Fh
0x18005c509  mov     dword ptr [rbp+57h+var_C8+4], 14Eh
0x18005c510  jmp     short loc_18005C531
0x18005c512  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18005c519  jz      short loc_18005C531
0x18005c51b  mov     edx, 15h
0x18005c520  lea     r8, WPP_a8da9155b8bb3d04d08e272bf258165a_Traceguids
0x18005c527  mov     ecx, 40Bh
0x18005c52c  call    WPP_SF_
0x18005c531  test    rbx, rbx
0x18005c534  jz      short loc_18005C546
0x18005c536  mov     rcx, rbx; this
0x18005c539  call    ?Shutdown@ZtProbeList@@QEAAXXZ; ZtProbeList::Shutdown(void)
0x18005c53e  mov     rcx, rbx; this
0x18005c541  call    ?Release@ZtProbeList@@QEAAKXZ; ZtProbeList::Release(void)
0x18005c546  test    edi, edi
0x18005c548  jnz     short loc_18005C54F
0x18005c54a  test    rsi, rsi
0x18005c54d  jz      short loc_18005C56A
0x18005c54f  cmp     cs:g_fVelocityZtdnsApiRefactor, r15d
0x18005c556  mov     rdx, rsi
0x18005c559  mov     ecx, edi
0x18005c55b  jz      short loc_18005C564
0x18005c55d  call    ZtFreeTrustedServers
0x18005c562  jmp     short loc_18005C56A
0x18005c564  call    cs:__imp_DnsFreeZtTrustedServers
0x18005c56a  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18005c571  jz      short loc_18005C58C
0x18005c573  mov     edx, 1Ah
0x18005c578  lea     r8, WPP_a8da9155b8bb3d04d08e272bf258165a_Traceguids
0x18005c57f  mov     ecx, 40Bh
0x18005c584  mov     r9d, r12d
0x18005c587  call    WPP_SF_d
0x18005c58c  mov     ecx, r12d
0x18005c58f  call    WX_WIN32_FROM_HR
0x18005c594  mov     ebx, eax
0x18005c596  cmp     dword ptr [rbp+57h+var_B0], r15d
0x18005c59a  jz      short loc_18005C5A5
0x18005c59c  lea     rcx, [rbp+57h+var_B8]; this
0x18005c5a0  call    ?Unlock@AutoCritSec@@QEAAXXZ; AutoCritSec::Unlock(void)
0x18005c5a5  mov     eax, ebx
0x18005c5a7  mov     rcx, [rbp+57h+var_50]
0x18005c5ab  xor     rcx, rsp; StackCookie
0x18005c5ae  call    __security_check_cookie
0x18005c5b3  add     rsp, 0C8h
0x18005c5ba  pop     r15
0x18005c5bc  pop     r14
0x18005c5be  pop     r13
0x18005c5c0  pop     r12
0x18005c5c2  pop     rdi
0x18005c5c3  pop     rsi
0x18005c5c4  pop     rbx
0x18005c5c5  pop     rbp
0x18005c5c6  retn
```
