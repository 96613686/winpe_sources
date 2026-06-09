# LogonRequestHandler(ushort const *,_DOMAIN_INFO *,uchar,void *,ulong,ulong,ushort const *,ulong,ushort const *,ushort const *,ulong,ulong,sockaddr *,uchar * const,ulong *)

- ea: `0x18006da7c`
- end: `0x18006df87`
- name: `?LogonRequestHandler@@YAEPEBGPEAU_DOMAIN_INFO@@EPEAXKK0K00KKPEAUsockaddr@@QEAEPEAK@Z`
- size: `1291`
- prototype: `bool __fastcall(unsigned __int16 *, struct _DOMAIN_INFO *, char, void *, unsigned int, unsigned int, const unsigned __int16 *SourceString, unsigned int, unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int, struct sockaddr *, unsigned __int8 *const, unsigned int *)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18006ef9c`
- `0x18007070c`

## callees

- `0x18000bd98`
- `0x18000e270`
- `0x180024adc`
- `0x1800354d8`
- `0x18003f684`
- `0x18006cd94`
- `0x18006d0a0`
- `0x18006da7c`
- `0x180073314`
- `0x18007d9b8`
- `0x1800840f8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18006ded6`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18006ded6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18006dc15`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18006dc15`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18006dbfa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18006dbfa`
- `ntdll!RtlEqualSid` at `0x18006daf9`
- `ntdll!RtlEqualSid` at `0x18006daf9`

## string_xrefs

- `0x18006db95`: `Netlogon Service Paused`
- `0x18006dbda`: `SysVol not ready`
- `0x18006dc3e`: `Sites and subnets cache is still building`

## pseudocode

```c
bool __fastcall LogonRequestHandler(
        unsigned __int16 *a1,
        struct _DOMAIN_INFO *a2,
        char a3,
        void *a4,
        unsigned int a5,
        unsigned int a6,
        const unsigned __int16 *SourceString,
        unsigned int a8,
        unsigned __int16 *a9,
        unsigned __int16 *a10,
        unsigned int a11,
        unsigned int a12,
        struct sockaddr *a13,
        unsigned __int8 *const a14,
        unsigned int *a15)
{
  unsigned __int8 *v15; // rbx
  unsigned __int16 v18; // r14
  char IsEnabled; // al
  DWORD dwCurrentState; // ecx
  const char *v21; // rax
  BOOL v22; // ebx
  bool v23; // zf
  unsigned int v24; // edi
  int IncomingPassword; // eax
  unsigned int v26; // eax
  int v27; // eax
  unsigned int *v28; // rcx
  char *v29; // rax
  unsigned int v30; // r11d
  const char *v31; // r9
  int v33; // [rsp+74h] [rbp-5Dh] BYREF
  unsigned __int8 *v34; // [rsp+78h] [rbp-59h]
  struct sockaddr *v35; // [rsp+80h] [rbp-51h] BYREF
  unsigned int *v36; // [rsp+88h] [rbp-49h]
  unsigned __int16 *v37; // [rsp+90h] [rbp-41h]
  unsigned __int16 *v38; // [rsp+98h] [rbp-39h]
  unsigned __int16 *v39[4]; // [rsp+A0h] [rbp-31h] BYREF

  v15 = a14;
  v38 = a10;
  v35 = a13;
  v36 = a15;
  v37 = a1;
  v34 = a14;
  v33 = 0;
  if ( a4 && !RtlEqualSid(*((PSID *)a2 + 23), a4) )
  {
    v39[1] = (unsigned __int16 *)((char *)a2 + 216);
    v39[2] = (unsigned __int16 *)((char *)a2 + 72);
    v39[0] = a9;
    v39[3] = 0;
    NlpWriteEventlogEx(0x1589u, 1u, 0, 0xFFFFFFFF, v39, 3u, 0, 0);
    return 0;
  }
  v18 = 0;
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::GetImpl'::`2'::impl);
  dwCurrentState = NlGlobalServiceStatus.dwCurrentState;
  if ( IsEnabled )
  {
    if ( NlGlobalServiceStatus.dwCurrentState == 7 && ((a6 & 0x10000000) == 0 || *((_DWORD *)a2 + 147) != 1) )
    {
LABEL_8:
      v21 = "Netlogon Service Paused";
LABEL_29:
      v24 = a5;
      if ( a5 == 2 )
      {
        v18 = 20;
      }
      else if ( a8 >= 3 && dwCurrentState == 7 )
      {
        v18 = 15;
      }
      NlPrintDomRoutine(0x10u, a2, L"Returning paused to '%ws' since: %hs\n", a9, v21);
      goto LABEL_57;
    }
    if ( NlGlobalDsPaused )
    {
LABEL_10:
      v21 = "DS paused";
      goto LABEL_29;
    }
    if ( NlGlobalPartialDisable && (a6 & 0x40000000) == 0 )
    {
LABEL_13:
      v21 = "Waiting for RPCSS";
      goto LABEL_29;
    }
    if ( !dword_1800F124C )
    {
LABEL_15:
      v21 = "SysVol not ready";
      goto LABEL_29;
    }
    if ( dword_1800F12B4 )
    {
      AcquireSRWLockShared(&gNlSiteCacheLock);
      v22 = gpNlSitesAndSubnetsCache != 0;
      ReleaseSRWLockShared(&gNlSiteCacheLock);
      v23 = !v22;
      v15 = v34;
      if ( v23 && (a6 & 0x40000000) == 0 )
      {
        dwCurrentState = NlGlobalServiceStatus.dwCurrentState;
        v21 = "Sites and subnets cache is still building";
        goto LABEL_29;
      }
      goto LABEL_35;
    }
LABEL_28:
    v21 = "DCLocatorReplyEnabled set to FALSE";
    goto LABEL_29;
  }
  if ( NlGlobalServiceStatus.dwCurrentState == 7 && ((a6 & 0x10000000) == 0 || *((_DWORD *)a2 + 147) != 1) )
    goto LABEL_8;
  if ( NlGlobalDsPaused )
    goto LABEL_10;
  if ( NlGlobalPartialDisable && (a6 & 0x40000000) == 0 )
    goto LABEL_13;
  if ( !dword_1800F124C )
    goto LABEL_15;
  if ( !dword_1800F12B4 )
    goto LABEL_28;
LABEL_35:
  if ( SourceString && *SourceString )
  {
    v24 = a5;
    if ( dword_1800F1278 )
    {
      NlPrintDomRoutine(0x10u, a2, L"LogonRequestHandler: Avoiding user '%ws' lookup for '%ws'\n", SourceString, a9);
    }
    else
    {
      if ( a11 == 1024 || a11 == 64 )
      {
        if ( NlGlobalCDC )
          IncomingPassword = -1073741724;
        else
          IncomingPassword = NlGetIncomingPassword(a2, SourceString, 0, a11, a5 == 2, 0, 0, 0, 0, 0, 0, &v33, 0);
      }
      else
      {
        IncomingPassword = NlSamVerifyUserAccountEnabled(a2, SourceString, a11, a5 == 2);
      }
      if ( IncomingPassword < 0 )
      {
        if ( IncomingPassword != -1073741724 )
          goto LABEL_57;
        if ( a5 == 2 )
        {
          v18 = 21;
          goto LABEL_57;
        }
        goto LABEL_55;
      }
    }
    if ( a5 != 2 )
    {
      if ( a5 == 1 )
        v18 = 6;
      else
        v18 = 16;
      goto LABEL_57;
    }
LABEL_50:
    v18 = 19;
    goto LABEL_57;
  }
  v24 = a5;
  if ( a5 == 2 )
    goto LABEL_50;
LABEL_55:
  if ( v24 == 1 )
    v18 = 16;
LABEL_57:
  if ( v18 == 6 || v18 == 15 || v18 == 16 )
  {
    *(_WORD *)v15 = v18;
    strcpy_s((char *)v15 + 2, 0x12u, "\\\\");
    v35 = (struct sockaddr *)(v15 + 4);
    NetpLogonPutOemString((char *)a2 + 312, 16, &v35);
    v27 = (int)v35;
    v28 = v36;
    v35->sa_family = -1;
    *v28 = v27 + 2 - (_DWORD)v34;
    v29 = NlMailslotOpcode(v18);
    v31 = "Sam";
    if ( v24 != 2 )
      v31 = "Uas";
    NlPrintDomRoutine(
      v30,
      a2,
      L"%hs logon mailslot message for %ws from \\\\%ws. Response '%hs' on %ws\n",
      v31,
      SourceString,
      a9,
      v29,
      v37);
    return 1;
  }
  if ( v18 != 19 && (unsigned int)v18 - 20 > 1 )
    return 0;
  if ( (a6 & 0xC) != 0 )
    v26 = BuildSamLogonResponseEx(a2, a3, v18, SourceString, v33, v37, a9, v38, v35, a6, a12, v15, v36);
  else
    v26 = BuildSamLogonResponse(a2, a3, v18, SourceString, v37, a9, (a6 >> 1) & 1, a12, v15, v36);
  return !v26;
}

```

## disassembly

```asm
0x18006da7c  push    rbp
0x18006da7e  push    rbx
0x18006da7f  push    rsi
0x18006da80  push    rdi
0x18006da81  push    r12
0x18006da83  push    r13
0x18006da85  push    r14
0x18006da87  push    r15
0x18006da89  lea     rbp, [rsp-7]
0x18006da8e  sub     rsp, 0D8h
0x18006da95  mov     rax, cs:__security_cookie
0x18006da9c  xor     rax, rsp
0x18006da9f  mov     [rbp+3Fh+var_50], rax
0x18006daa3  mov     rax, [rbp+3Fh+arg_48]
0x18006daaa  xor     edi, edi
0x18006daac  mov     rbx, [rbp+3Fh+arg_68]
0x18006dab3  mov     r15, rdx
0x18006dab6  mov     r12, [rbp+3Fh+SourceString]
0x18006daba  mov     r13, [rbp+3Fh+arg_40]
0x18006dac1  mov     [rbp+3Fh+var_78], rax
0x18006dac5  mov     rax, [rbp+3Fh+arg_60]
0x18006dacc  mov     [rbp+3Fh+var_90], rax
0x18006dad0  mov     rax, [rbp+3Fh+arg_70]
0x18006dad7  mov     [rbp+3Fh+var_88], rax
0x18006dadb  mov     [rbp+3Fh+var_A0], r8b
0x18006dadf  mov     [rbp+3Fh+var_80], rcx
0x18006dae3  mov     [rbp+3Fh+var_98], rbx
0x18006dae7  mov     [rbp+3Fh+var_9C], edi
0x18006daea  test    r9, r9
0x18006daed  jz      short loc_18006DB53
0x18006daef  mov     rcx, [r15+0B8h]; Sid1
0x18006daf6  mov     rdx, r9; Sid2
0x18006daf9  call    cs:__imp_RtlEqualSid
0x18006daff  test    al, al
0x18006db01  jnz     short loc_18006DB53
0x18006db03  mov     dword ptr [rsp+110h+var_D8], edi; unsigned int
0x18006db07  lea     rax, [r15+0D8h]
0x18006db0e  mov     [rbp+3Fh+var_68], rax
0x18006db12  lea     edx, [rdi+1]; unsigned int
0x18006db15  lea     rax, [r15+48h]
0x18006db19  mov     [rsp+110h+var_E0], rdi; unsigned __int8 *
0x18006db1e  mov     [rbp+3Fh+var_60], rax
0x18006db22  or      r9d, 0FFFFFFFFh; unsigned int
0x18006db26  lea     rax, [rbp+3Fh+var_70]
0x18006db2a  mov     dword ptr [rsp+110h+var_E8], 3; unsigned int
0x18006db32  xor     r8d, r8d; unsigned int
0x18006db35  mov     [rsp+110h+var_F0], rax; unsigned __int16 **
0x18006db3a  mov     ecx, 1589h; unsigned int
0x18006db3f  mov     [rbp+3Fh+var_70], r13
0x18006db43  mov     [rbp+3Fh+var_58], rdi
0x18006db47  call    ?NlpWriteEventlogEx@@YAXKKKKPEAPEAGKPEAEK@Z; NlpWriteEventlogEx(ulong,ulong,ulong,ulong,ushort * *,ulong,uchar *,ulong)
0x18006db4c  xor     al, al
0x18006db4e  jmp     loc_18006DF67
0x18006db53  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements> `wil::Feature<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::GetImpl(void)'::`2'::impl
0x18006db5a  mov     [rbp+3Fh+var_9F], dil
0x18006db5e  mov     r14d, edi
0x18006db61  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::__private_IsEnabled(void)
0x18006db66  mov     esi, [rbp+3Fh+arg_28]
0x18006db69  xor     r8d, r8d
0x18006db6c  mov     ecx, cs:?NlGlobalServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState; _SERVICE_STATUS NlGlobalServiceStatus ...
0x18006db72  mov     r10d, 10h
0x18006db78  test    al, al
0x18006db7a  jz      loc_18006DC47
0x18006db80  cmp     ecx, 7
0x18006db83  jnz     short loc_18006DBA1
0x18006db85  bt      esi, 1Ch
0x18006db89  jnb     short loc_18006DB95
0x18006db8b  cmp     dword ptr [r15+24Ch], 1
0x18006db93  jz      short loc_18006DBA1
0x18006db95  lea     rax, aNetlogonServic; "Netlogon Service Paused"
0x18006db9c  jmp     loc_18006DCA1
0x18006dba1  cmp     cs:?NlGlobalDsPaused@@3HA, r8d; int NlGlobalDsPaused
0x18006dba8  jz      short loc_18006DBB6
0x18006dbaa  lea     rax, aDsPaused; "DS paused"
0x18006dbb1  jmp     loc_18006DCA1
0x18006dbb6  cmp     cs:?NlGlobalPartialDisable@@3HA, r8d; int NlGlobalPartialDisable
0x18006dbbd  jz      short loc_18006DBD1
0x18006dbbf  bt      esi, 1Eh
0x18006dbc3  jb      short loc_18006DBD1
0x18006dbc5  lea     rax, aWaitingForRpcs; "Waiting for RPCSS"
0x18006dbcc  jmp     loc_18006DCA1
0x18006dbd1  cmp     cs:dword_1800F124C, r8d
0x18006dbd8  jnz     short loc_18006DBE6
0x18006dbda  lea     rax, aSysvolNotReady; "SysVol not ready"
0x18006dbe1  jmp     loc_18006DCA1
0x18006dbe6  cmp     cs:dword_1800F12B4, r8d
0x18006dbed  jz      loc_18006DC9A
0x18006dbf3  lea     rcx, ?gNlSiteCacheLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18006dbfa  call    cs:__imp_AcquireSRWLockShared
0x18006dc00  xor     ecx, ecx
0x18006dc02  cmp     cs:?gpNlSitesAndSubnetsCache@@3PEAVCNlSitesAndSubnetsCache@@EA, rcx; CNlSitesAndSubnetsCache * gpNlSitesAndSubnetsCache
0x18006dc09  mov     ebx, ecx
0x18006dc0b  lea     rcx, ?gNlSiteCacheLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x18006dc12  setnz   bl
0x18006dc15  call    cs:__imp_ReleaseSRWLockShared
0x18006dc1b  xor     r8d, r8d
0x18006dc1e  test    ebx, ebx
0x18006dc20  mov     rbx, [rbp+3Fh+var_98]
0x18006dc24  lea     r10d, [r8+10h]
0x18006dc28  jnz     loc_18006DCE0
0x18006dc2e  bt      esi, 1Eh
0x18006dc32  jb      loc_18006DCE0
0x18006dc38  mov     ecx, cs:?NlGlobalServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState; _SERVICE_STATUS NlGlobalServiceStatus ...
0x18006dc3e  lea     rax, aSitesAndSubnet; "Sites and subnets cache is still buildi"...
0x18006dc45  jmp     short loc_18006DCA1
0x18006dc47  cmp     ecx, 7
0x18006dc4a  jnz     short loc_18006DC64
0x18006dc4c  bt      esi, 1Ch
0x18006dc50  jnb     loc_18006DB95
0x18006dc56  cmp     dword ptr [r15+24Ch], 1
0x18006dc5e  jnz     loc_18006DB95
0x18006dc64  cmp     cs:?NlGlobalDsPaused@@3HA, r8d; int NlGlobalDsPaused
0x18006dc6b  jnz     loc_18006DBAA
0x18006dc71  cmp     cs:?NlGlobalPartialDisable@@3HA, r8d; int NlGlobalPartialDisable
0x18006dc78  jz      short loc_18006DC84
0x18006dc7a  bt      esi, 1Eh
0x18006dc7e  jnb     loc_18006DBC5
0x18006dc84  cmp     cs:dword_1800F124C, r8d
0x18006dc8b  jz      loc_18006DBDA
0x18006dc91  cmp     cs:dword_1800F12B4, r8d
0x18006dc98  jnz     short loc_18006DCE0
0x18006dc9a  lea     rax, aDclocatorreply_0; "DCLocatorReplyEnabled set to FALSE"
0x18006dca1  mov     edi, [rbp+3Fh+arg_20]
0x18006dca4  cmp     edi, 2
0x18006dca7  jnz     short loc_18006DCAF
0x18006dca9  lea     r14d, [rdi+12h]
0x18006dcad  jmp     short loc_18006DCC1
0x18006dcaf  cmp     [rbp+3Fh+arg_38], 3
0x18006dcb6  jb      short loc_18006DCC1
0x18006dcb8  cmp     ecx, 7
0x18006dcbb  jnz     short loc_18006DCC1
0x18006dcbd  lea     r14d, [rcx+8]
0x18006dcc1  mov     r9, r13
0x18006dcc4  mov     [rsp+110h+var_F0], rax
0x18006dcc9  lea     r8, aReturningPause; "Returning paused to '%ws' since: %hs\n"
0x18006dcd0  mov     rdx, r15; struct _DOMAIN_INFO *
0x18006dcd3  mov     ecx, r10d; unsigned int
0x18006dcd6  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18006dcdb  jmp     loc_18006DDF1
0x18006dce0  test    r12, r12
0x18006dce3  jz      loc_18006DDE0
0x18006dce9  cmp     [r12], r8w
0x18006dcee  jz      loc_18006DDE0
0x18006dcf4  cmp     cs:dword_1800F1278, r8d
0x18006dcfb  mov     edi, [rbp+3Fh+arg_20]
0x18006dcfe  jnz     loc_18006DDA1
0x18006dd04  mov     ecx, [rbp+3Fh+arg_50]
0x18006dd0a  cmp     ecx, 400h
0x18006dd10  jz      short loc_18006DD31
0x18006dd12  cmp     ecx, 40h ; '@'
0x18006dd15  jz      short loc_18006DD31
0x18006dd17  mov     r9d, r8d
0x18006dd1a  cmp     edi, 2
0x18006dd1d  mov     r8d, ecx; unsigned int
0x18006dd20  mov     rdx, r12; SourceString
0x18006dd23  setz    r9b; int
0x18006dd27  mov     rcx, r15; struct _DOMAIN_INFO *
0x18006dd2a  call    ?NlSamVerifyUserAccountEnabled@@YAJPEAU_DOMAIN_INFO@@PEBGKH@Z; NlSamVerifyUserAccountEnabled(_DOMAIN_INFO *,ushort const *,ulong,int)
0x18006dd2f  jmp     short loc_18006DD8B
0x18006dd31  cmp     cs:?NlGlobalCDC@@3HA, r8d; int NlGlobalCDC
0x18006dd38  jnz     short loc_18006DD86
0x18006dd3a  mov     [rsp+110h+var_B0], r8
0x18006dd3f  lea     rdx, [rbp+3Fh+var_9C]
0x18006dd43  mov     [rsp+110h+var_B8], rdx
0x18006dd48  mov     eax, r8d
0x18006dd4b  mov     qword ptr [rsp+110h+var_C0], r8
0x18006dd50  cmp     edi, 2
0x18006dd53  mov     [rsp+110h+var_C8], r8
0x18006dd58  mov     r9d, ecx
0x18006dd5b  mov     [rsp+110h+var_D0], r8
0x18006dd60  setz    al
0x18006dd63  mov     [rsp+110h+var_D8], r8
0x18006dd68  mov     rdx, r12
0x18006dd6b  mov     [rsp+110h+var_E0], r8
0x18006dd70  mov     rcx, r15
0x18006dd73  mov     [rsp+110h+var_E8], r8
0x18006dd78  xor     r8d, r8d
0x18006dd7b  mov     dword ptr [rsp+110h+var_F0], eax
0x18006dd7f  call    ?NlGetIncomingPassword@@YAJPEAU_DOMAIN_INFO@@PEBGW4_NETLOGON_SECURE_CHANNEL_TYPE@@KHPEAU_LM_OWF_PASSWORD@@3PEAK44PEAPEAXPEAH4@Z; NlGetIncomingPassword(_DOMAIN_INFO *,ushort const *,_NETLOGON_SECURE_CHANNEL_TYPE,ulong,int,_LM_OWF_PASSWORD *,_LM_OWF_PASSWORD *,ulong *,ulong *,ulong *,void * *,int *,ulong *)
0x18006dd84  jmp     short loc_18006DD8B
0x18006dd86  mov     eax, 0C0000064h
0x18006dd8b  test    eax, eax
0x18006dd8d  jns     short loc_18006DDBB
0x18006dd8f  cmp     eax, 0C0000064h
0x18006dd94  jnz     short loc_18006DDF1
0x18006dd96  cmp     edi, 2
0x18006dd99  jnz     short loc_18006DDE8
0x18006dd9b  lea     r14d, [rdi+13h]
0x18006dd9f  jmp     short loc_18006DDF1
0x18006dda1  mov     r9, r12
0x18006dda4  mov     [rsp+110h+var_F0], r13
0x18006dda9  lea     r8, aLogonrequestha; "LogonRequestHandler: Avoiding user '%ws"...
0x18006ddb0  mov     rdx, r15; struct _DOMAIN_INFO *
0x18006ddb3  mov     ecx, r10d; unsigned int
0x18006ddb6  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18006ddbb  cmp     edi, 2
0x18006ddbe  jnz     short loc_18006DDC8
0x18006ddc0  mov     r14d, 13h
0x18006ddc6  jmp     short loc_18006DDF1
0x18006ddc8  mov     edx, 6
0x18006ddcd  cmp     edi, 1
0x18006ddd0  jnz     short loc_18006DDD8
0x18006ddd2  movzx   r14d, dx
0x18006ddd6  jmp     short loc_18006DDF6
0x18006ddd8  mov     r14d, 10h
0x18006ddde  jmp     short loc_18006DDF6
0x18006dde0  mov     edi, [rbp+3Fh+arg_20]
0x18006dde3  cmp     edi, 2
0x18006dde6  jz      short loc_18006DDC0
0x18006dde8  cmp     edi, 1
0x18006ddeb  jnz     short loc_18006DDF1
0x18006dded  lea     r14d, [rdi+0Fh]
0x18006ddf1  mov     edx, 6
0x18006ddf6  movzx   ecx, r14w
0x18006ddfa  sub     ecx, edx
0x18006ddfc  jz      loc_18006DEC2
0x18006de02  sub     ecx, 9
0x18006de05  jz      loc_18006DEC2
0x18006de0b  sub     ecx, 1
0x18006de0e  jz      loc_18006DEC2
0x18006de14  sub     ecx, 3
0x18006de17  jz      short loc_18006DE27
0x18006de19  sub     ecx, 1
0x18006de1c  jz      short loc_18006DE27
0x18006de1e  cmp     ecx, 1
0x18006de21  jnz     loc_18006DF60
0x18006de27  mov     rcx, [rbp+3Fh+var_88]
0x18006de2b  mov     r9, r12; unsigned __int16 *
0x18006de2e  mov     eax, [rbp+3Fh+arg_58]
0x18006de34  movzx   r8d, r14w; unsigned __int16
0x18006de38  mov     dl, [rbp+3Fh+var_A0]; unsigned __int8
0x18006de3b  test    sil, 0Ch
0x18006de3f  jz      short loc_18006DE84
0x18006de41  mov     [rsp+110h+var_B0], rcx; unsigned int *
0x18006de46  mov     rcx, [rbp+3Fh+var_80]
0x18006de4a  mov     [rsp+110h+var_B8], rbx; unsigned __int8 *
0x18006de4f  mov     [rsp+110h+var_C0], eax; unsigned int
0x18006de53  mov     rax, [rbp+3Fh+var_90]
0x18006de57  mov     dword ptr [rsp+110h+var_C8], esi; unsigned int
0x18006de5b  mov     [rsp+110h+var_D0], rax; struct sockaddr *
0x18006de60  mov     rax, [rbp+3Fh+var_78]
0x18006de64  mov     [rsp+110h+var_D8], rax; unsigned __int16 *
0x18006de69  mov     eax, [rbp+3Fh+var_9C]
0x18006de6c  mov     [rsp+110h+var_E0], r13; unsigned __int16 *
0x18006de71  mov     [rsp+110h+var_E8], rcx; unsigned __int16 *
0x18006de76  mov     rcx, r15; struct _DOMAIN_INFO *
0x18006de79  mov     dword ptr [rsp+110h+var_F0], eax; int
0x18006de7d  call    ?BuildSamLogonResponseEx@@YAKPEAU_DOMAIN_INFO@@EGPEBGH111PEAUsockaddr@@KKQEAEPEAK@Z; BuildSamLogonResponseEx(_DOMAIN_INFO *,uchar,ushort,ushort const *,int,ushort const *,ushort const *,ushort const *,sockaddr *,ulong,ulong,uchar * const,ulong *)
0x18006de82  jmp     short loc_18006DEB1
0x18006de84  mov     [rsp+110h+var_C8], rcx; unsigned int *
0x18006de89  mov     rcx, [rbp+3Fh+var_80]
0x18006de8d  mov     [rsp+110h+var_D0], rbx; unsigned __int8 *
0x18006de92  mov     dword ptr [rsp+110h+var_D8], eax; unsigned int
0x18006de96  shr     esi, 1
0x18006de98  and     esi, 1
0x18006de9b  mov     dword ptr [rsp+110h+var_E0], esi; int
0x18006de9f  mov     [rsp+110h+var_E8], r13; unsigned __int16 *
0x18006dea4  mov     [rsp+110h+var_F0], rcx; unsigned __int16 *
0x18006dea9  mov     rcx, r15; struct _DOMAIN_INFO *
0x18006deac  call    ?BuildSamLogonResponse@@YAKPEAU_DOMAIN_INFO@@EGPEBG11HKQEAEPEAK@Z; BuildSamLogonResponse(_DOMAIN_INFO *,uchar,ushort,ushort const *,ushort const *,ushort const *,int,ulong,uchar * const,ulong *)
0x18006deb1  xor     ecx, ecx
0x18006deb3  test    eax, eax
0x18006deb5  jnz     loc_18006DF65
0x18006debb  mov     al, 1
0x18006debd  jmp     loc_18006DF67
0x18006dec2  lea     r8, asc_1800D6FA8; "\\\\"
0x18006dec9  mov     [rbx], r14w
0x18006decd  mov     edx, 12h; SizeInBytes
0x18006ded2  lea     rcx, [rbx+2]; Destination
0x18006ded6  call    cs:__imp_strcpy_s
0x18006dedc  lea     rax, [rbx+4]
0x18006dee0  mov     r11d, 10h
0x18006dee6  mov     edx, r11d
0x18006dee9  mov     [rbp+3Fh+var_90], rax
0x18006deed  lea     rcx, [r15+138h]
0x18006def4  lea     r8, [rbp+3Fh+var_90]
0x18006def8  call    NetpLogonPutOemString
0x18006defd  mov     rax, [rbp+3Fh+var_90]
0x18006df01  mov     rcx, [rbp+3Fh+var_88]
0x18006df05  mov     word ptr [rax], 0FFFFh
0x18006df0a  add     rax, 2
0x18006df0e  sub     eax, dword ptr [rbp+3Fh+var_98]
0x18006df11  mov     [rcx], eax
0x18006df13  movzx   ecx, r14w; unsigned __int16
0x18006df17  call    ?NlMailslotOpcode@@YAPEADG@Z; NlMailslotOpcode(ushort)
0x18006df1c  mov     rcx, [rbp+3Fh+var_80]
0x18006df20  lea     rdx, aUas; "Uas"
0x18006df27  mov     [rsp+110h+var_D8], rcx
0x18006df2c  lea     r9, aSam; "Sam"
0x18006df33  mov     [rsp+110h+var_E0], rax
0x18006df38  lea     r8, aHsLogonMailslo; "%hs logon mailslot message for %ws from"...
0x18006df3f  cmp     edi, 2
0x18006df42  mov     [rsp+110h+var_E8], r13
0x18006df47  mov     ecx, r11d; unsigned int
0x18006df4a  mov     [rsp+110h+var_F0], r12
0x18006df4f  cmovnz  r9, rdx
0x18006df53  mov     rdx, r15; struct _DOMAIN_INFO *
0x18006df56  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18006df5b  jmp     loc_18006DEBB
0x18006df60  mov     al, [rbp+3Fh+var_9F]
  ... truncated ...
```
