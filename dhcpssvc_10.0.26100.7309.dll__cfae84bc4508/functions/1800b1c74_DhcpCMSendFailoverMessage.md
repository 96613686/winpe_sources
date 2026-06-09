# DhcpCMSendFailoverMessage

- ea: `0x1800b1c74`
- end: `0x1800b2d86`
- name: `DhcpCMSendFailoverMessage`
- size: `4370`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800b1794`
- `0x1800b2d90`

## callees

- `0x180002854`
- `0x18001ceb4`
- `0x180080a8c`
- `0x180080dcc`
- `0x1800b1c74`
- `0x1800b3034`
- `0x1800cb37c`
- `0x1800cc982`
- `0x1800cc99a`
- `0x1800cc9e0`

## import_xrefs

- `msvcrt!time` at `0x1800b2318`
- `msvcrt!time` at `0x1800b2375`
- `msvcrt!time` at `0x1800b2318`
- `msvcrt!time` at `0x1800b2375`
- `ADVAPI32!RegCloseKey` at `0x1800b2498`
- `ADVAPI32!RegCloseKey` at `0x1800b2498`
- `ADVAPI32!RegOpenKeyExW` at `0x1800b1e8b`
- `ADVAPI32!RegOpenKeyExW` at `0x1800b1e8b`
- `ADVAPI32!RegQueryValueExW` at `0x1800b1f32`
- `ADVAPI32!RegQueryValueExW` at `0x1800b1fdb`
- `ADVAPI32!RegQueryValueExW` at `0x1800b203f`
- `ADVAPI32!RegQueryValueExW` at `0x1800b20a3`
- `ADVAPI32!RegQueryValueExW` at `0x1800b235a`
- `ADVAPI32!RegQueryValueExW` at `0x1800b1f32`
- `ADVAPI32!RegQueryValueExW` at `0x1800b1fdb`
- `ADVAPI32!RegQueryValueExW` at `0x1800b203f`
- `ADVAPI32!RegQueryValueExW` at `0x1800b20a3`
- `ADVAPI32!RegQueryValueExW` at `0x1800b235a`
- `ADVAPI32!RegSetValueExW` at `0x1800b23ff`
- `ADVAPI32!RegSetValueExW` at `0x1800b23ff`
- `WS2_32!WSAResetEvent` at `0x1800b2700`
- `WS2_32!WSAResetEvent` at `0x1800b2700`
- `WS2_32!WSAEnumNetworkEvents` at `0x1800b2635`
- `WS2_32!WSAEnumNetworkEvents` at `0x1800b2635`
- `WS2_32!WSASend` at `0x1800b2574`
- `WS2_32!WSASend` at `0x1800b2574`
- `WS2_32!WSACloseEvent` at `0x1800b244b`
- `WS2_32!WSACloseEvent` at `0x1800b244b`
- `WS2_32!WSACreateEvent` at `0x1800b22b4`
- `WS2_32!WSACreateEvent` at `0x1800b22b4`
- `WS2_32!WSAWaitForMultipleEvents` at `0x1800b25fe`
- `WS2_32!WSAWaitForMultipleEvents` at `0x1800b26dd`
- `WS2_32!WSAWaitForMultipleEvents` at `0x1800b25fe`
- `WS2_32!WSAWaitForMultipleEvents` at `0x1800b26dd`
- `WS2_32!__imp_ntohl` at `0x1800b27f9`
- `WS2_32!__imp_ntohl` at `0x1800b28b9`
- `WS2_32!__imp_ntohl` at `0x1800b2932`
- `WS2_32!__imp_ntohl` at `0x1800b29da`
- `WS2_32!__imp_ntohl` at `0x1800b2a33`
- `WS2_32!__imp_ntohl` at `0x1800b2a8c`
- `WS2_32!__imp_ntohl` at `0x1800b2ae5`
- `WS2_32!__imp_ntohl` at `0x1800b2b3e`
- `WS2_32!__imp_ntohl` at `0x1800b2be7`
- `WS2_32!__imp_ntohl` at `0x1800b2c59`
- `WS2_32!__imp_ntohl` at `0x1800b2cd3`
- `WS2_32!__imp_ntohl` at `0x1800b2d23`
- `WS2_32!__imp_ntohl` at `0x1800b27f9`
- `WS2_32!__imp_ntohl` at `0x1800b28b9`
- `WS2_32!__imp_ntohl` at `0x1800b2932`
- `WS2_32!__imp_ntohl` at `0x1800b29da`
- `WS2_32!__imp_ntohl` at `0x1800b2a33`
- `WS2_32!__imp_ntohl` at `0x1800b2a8c`
- `WS2_32!__imp_ntohl` at `0x1800b2ae5`
- `WS2_32!__imp_ntohl` at `0x1800b2b3e`
- `WS2_32!__imp_ntohl` at `0x1800b2be7`
- `WS2_32!__imp_ntohl` at `0x1800b2c59`
- `WS2_32!__imp_ntohl` at `0x1800b2cd3`
- `WS2_32!__imp_ntohl` at `0x1800b2d23`
- `WS2_32!__imp_WSAGetLastError` at `0x1800b246c`
- `WS2_32!__imp_WSAGetLastError` at `0x1800b259c`
- `WS2_32!__imp_WSAGetLastError` at `0x1800b2721`
- `WS2_32!__imp_WSAGetLastError` at `0x1800b246c`
- `WS2_32!__imp_WSAGetLastError` at `0x1800b259c`
- `WS2_32!__imp_WSAGetLastError` at `0x1800b2721`
- `KERNEL32!RegNotifyChangeKeyValue` at `0x1800b2302`
- `KERNEL32!RegNotifyChangeKeyValue` at `0x1800b2302`
- `KERNEL32!WaitForSingleObject` at `0x1800b23a0`
- `KERNEL32!WaitForSingleObject` at `0x1800b23a0`
- `KERNEL32!HeapAlloc` at `0x1800b1f87`
- `KERNEL32!HeapAlloc` at `0x1800b2519`
- `KERNEL32!HeapAlloc` at `0x1800b1f87`
- `KERNEL32!HeapAlloc` at `0x1800b2519`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800b1e1a`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800b1ebe`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800b1e1a`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800b1ebe`
- `KERNEL32!AcquireSRWLockShared` at `0x1800b1df7`
- `KERNEL32!AcquireSRWLockShared` at `0x1800b1df7`
- `KERNEL32!EnterCriticalSection` at `0x1800b1e2d`
- `KERNEL32!EnterCriticalSection` at `0x1800b1e2d`
- `KERNEL32!LeaveCriticalSection` at `0x1800b2d53`
- `KERNEL32!LeaveCriticalSection` at `0x1800b2d53`
- `KERNEL32!HeapFree` at `0x1800b24dc`
- `KERNEL32!HeapFree` at `0x1800b2753`
- `KERNEL32!HeapFree` at `0x1800b27b8`
- `KERNEL32!HeapFree` at `0x1800b2977`
- `KERNEL32!HeapFree` at `0x1800b24dc`
- `KERNEL32!HeapFree` at `0x1800b2753`
- `KERNEL32!HeapFree` at `0x1800b27b8`
- `KERNEL32!HeapFree` at `0x1800b2977`

## string_xrefs

- `0x1800b1e7d`: `SYSTEM\CurrentControlSet\Services\DHCPServer\Parameters`
- `0x1800b1ea4`: `RegOpenKeyExW`

## pseudocode

```c
__int64 __fastcall DhcpCMSendFailoverMessage(
        _QWORD *a1,
        __int64 a2,
        struct _RTL_CRITICAL_SECTION *a3,
        __int64 a4,
        int a5,
        void *a6,
        __int64 a7,
        __int64 a8)
{
  struct _RTL_CRITICAL_SECTION *v9; // r10
  unsigned int v11; // r14d
  __int64 v12; // r13
  int v13; // r12d
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rax
  RTL_SRWLOCK *v17; // rbx
  unsigned int v18; // eax
  __int64 v19; // r9
  const char *v20; // r8
  __int64 v21; // rcx
  unsigned int v23; // eax
  _QWORD *v24; // rcx
  __int64 v25; // rdx
  void *v26; // rax
  unsigned int v27; // eax
  unsigned int v28; // eax
  __int64 *v29; // rax
  unsigned __int16 *v30; // r9
  __int64 v31; // r10
  unsigned __int16 *v32; // rax
  int v33; // ecx
  int v34; // edx
  __int64 v35; // rax
  __int64 *v36; // rax
  __int64 v37; // rdx
  int v38; // ecx
  int v39; // edx
  int v40; // edx
  int v41; // edx
  int v42; // edx
  void *v43; // rdx
  int v44; // edx
  int v45; // edx
  int v46; // edx
  HANDLE v47; // r12
  unsigned int v48; // eax
  int v49; // eax
  __int64 v50; // r13
  int v51; // r14d
  unsigned int v52; // eax
  int v53; // eax
  _QWORD *v54; // rcx
  __int64 v55; // rdx
  unsigned int v56; // eax
  unsigned int v57; // eax
  int v58; // r13d
  unsigned int v59; // r14d
  void *v60; // r12
  unsigned int Error; // eax
  DWORD v62; // eax
  __int64 v63; // r9
  _QWORD *v64; // rcx
  __int64 v65; // rdx
  unsigned int v66; // eax
  __int64 v67; // r13
  _DWORD *v68; // r12
  __int64 v69; // r15
  unsigned int v70; // r14d
  __int64 v71; // r13
  u_long v72; // ecx
  __int64 v73; // rdi
  __int64 v74; // rbx
  u_long v75; // eax
  _DWORD *v76; // rbx
  unsigned int v77; // r12d
  __int64 v78; // rdi
  _BYTE *v79; // rax
  __int64 v80; // r13
  u_long v81; // ecx
  u_long v82; // eax
  void *v83; // rax
  __int64 v84; // r13
  u_long v85; // ecx
  u_long v86; // eax
  __int64 v87; // rbx
  u_long v88; // ecx
  u_long v89; // eax
  __int64 v90; // rbx
  u_long v91; // ecx
  u_long v92; // eax
  __int64 v93; // rbx
  u_long v94; // ecx
  u_long v95; // eax
  __int64 v96; // rbx
  u_long v97; // ecx
  u_long v98; // eax
  __int64 v99; // rbx
  u_long v100; // ecx
  u_long v101; // eax
  const size_t *v102; // rdi
  int v103; // eax
  int v104; // ecx
  __int64 v105; // rax
  wchar_t *v106; // r12
  __int64 v107; // rbx
  u_long v108; // ecx
  u_long v109; // edx
  __int64 v110; // rax
  wchar_t *v111; // r12
  __int64 v112; // rbx
  u_long v113; // ecx
  u_long v114; // edx
  unsigned __int8 *v115; // rcx
  __int64 v116; // rax
  __int64 v117; // rsi
  const size_t *v118; // rbx
  u_long v119; // ecx
  u_long v120; // eax
  const size_t *v121; // rbx
  u_long v122; // ecx
  u_long v123; // eax
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v125; // [rsp+48h] [rbp-B8h]
  DWORD v126; // [rsp+50h] [rbp-B0h]
  unsigned int v127; // [rsp+54h] [rbp-ACh]
  DWORD Type; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  int v130[4]; // [rsp+70h] [rbp-90h] BYREF
  BYTE v131[8]; // [rsp+80h] [rbp-80h] BYREF
  LPVOID lpMem; // [rsp+88h] [rbp-78h]
  BYTE Data[4]; // [rsp+90h] [rbp-70h] BYREF
  BYTE v134[4]; // [rsp+94h] [rbp-6Ch] BYREF
  DWORD NumberOfBytesSent; // [rsp+98h] [rbp-68h] BYREF
  int v136[4]; // [rsp+A0h] [rbp-60h] BYREF
  BYTE v137[8]; // [rsp+B0h] [rbp-50h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+B8h] [rbp-48h]
  HANDLE hEvents; // [rsp+C0h] [rbp-40h] BYREF
  size_t Size[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v141; // [rsp+D8h] [rbp-28h]
  int v142[4]; // [rsp+E0h] [rbp-20h] BYREF
  HANDLE v143[2]; // [rsp+F0h] [rbp-10h] BYREF
  int v144[4]; // [rsp+100h] [rbp+0h] BYREF
  struct _WSANETWORKEVENTS NetworkEvents; // [rsp+110h] [rbp+10h] BYREF
  __int64 v146[64]; // [rsp+140h] [rbp+40h] BYREF

  *(_QWORD *)v142 = a8;
  v141 = a7;
  v9 = a3;
  hEvents = a6;
  v125 = a4;
  v11 = 0;
  lpCriticalSection = a3;
  LODWORD(v12) = 0;
  v126 = 0;
  v13 = 0;
  NumberOfBytesSent = 0;
  v127 = 0;
  hKey = HKEY_LOCAL_MACHINE;
  lpMem = 0;
  *(_DWORD *)Data = 0;
  *(_DWORD *)v131 = 0;
  Type = 0;
  cbData = 0;
  *(_DWORD *)v134 = 0;
  *(_DWORD *)v137 = 0;
  *(_OWORD *)Size = 0;
  *(_OWORD *)v143 = 0;
  memset(&NetworkEvents, 0, sizeof(NetworkEvents));
  if ( !a1 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) == 0 )
      return 87;
    v15 = 25;
LABEL_27:
    WPP_SF_D(v14[2], v15, &WPP_5bd49953df5f3f59743b495ddca40749_Traceguids, 87);
    return 87;
  }
  if ( a5 && !a6 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) == 0 )
      return 87;
    v15 = 26;
    goto LABEL_27;
  }
  if ( !a2 && !a3 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) == 0 )
      return 87;
    v15 = 27;
    goto LABEL_27;
  }
  v16 = *(_QWORD *)(a4 + 16);
  *(_QWORD *)v130 = *(_QWORD *)v16;
  if ( a2 && !*(_BYTE *)(v16 + 392) )
  {
    v17 = (RTL_SRWLOCK *)(a2 + 72);
    AcquireSRWLockShared((PSRWLOCK)(a2 + 72));
    lpCriticalSection = *(LPCRITICAL_SECTION *)(a2 + 488);
    if ( !lpCriticalSection )
    {
      ReleaseSRWLockShared(v17);
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) == 0 )
      {
        return 87;
      }
      v15 = 28;
      goto LABEL_27;
    }
    ReleaseSRWLockShared(v17);
    v9 = lpCriticalSection;
  }
  EnterCriticalSection(v9);
  *(_QWORD *)v136 = *a1;
  if ( *(_QWORD *)v136 )
  {
    if ( !*(_DWORD *)&isDhcpFailoverTestEnv )
    {
LABEL_129:
      v58 = *(_DWORD *)(*(_QWORD *)(v125 + 16) + 8LL);
      if ( !v58 )
      {
LABEL_156:
        if ( !v11 )
        {
          v67 = v125;
          v68 = *(_DWORD **)(v125 + 16);
          v69 = *(_QWORD *)v68;
          if ( *(_BYTE *)(*(_QWORD *)v68 + 2LL) == 3 )
          {
            if ( v68[6] )
            {
              v70 = 0;
              do
              {
                if ( *(_DWORD *)(a2 + 8) )
                  v71 = *(_QWORD *)(a2 + 24);
                else
                  v71 = *(_QWORD *)(a2 + 32);
                v72 = *(_DWORD *)(v69 + 8);
                v73 = 38LL * v70;
                *(_OWORD *)v130 = SendBndUpdMessage;
                v74 = BYTE1(v68[v73 + 15]);
                v75 = ntohl(v72);
                LogETWFailoverAuditLogEvent(
                  (int)v130,
                  v75,
                  v71,
                  *(_QWORD *)a2,
                  v68[v73 + 14],
                  (__int64)FailoverBindingStateDescription[v74],
                  0);
                v67 = v125;
                ++v70;
                v68 = *(_DWORD **)(v125 + 16);
              }
              while ( v70 < v68[6] );
              v11 = v126;
            }
            _InterlockedIncrement(&DhcpGlobalFailoverBndUpdSent);
          }
          v76 = *(_DWORD **)(v67 + 16);
          if ( *(_BYTE *)(*(_QWORD *)v76 + 2LL) == 4 )
          {
            v77 = 0;
            if ( v76[6] )
            {
              do
              {
                v78 = 8LL * v77;
                v79 = *(_BYTE **)&v76[v78 + 14];
                if ( v79 )
                {
                  if ( *v79 == 0xFE )
                    v83 = (void *)qword_1800FB780;
                  else
                    v83 = (void *)FailoverRejectReasonDescription[(unsigned __int8)*v79];
                  lpMem = v83;
                  if ( *(_DWORD *)(a2 + 8) )
                    v84 = *(_QWORD *)(a2 + 24);
                  else
                    v84 = *(_QWORD *)(a2 + 32);
                  v85 = *(_DWORD *)(v69 + 8);
                  *(_OWORD *)v144 = SendBndAckMessageRejectReason;
                  v86 = ntohl(v85);
                  LogETWFailoverBNDUPDAdminEvent((int)v144, v86, v84, *(_QWORD *)a2, v76[v78 + 12], (__int64)lpMem);
                  v67 = v125;
                  HeapFree(gDhcpHeap, 0, *(LPVOID *)(*(_QWORD *)(v125 + 16) + v78 * 4 + 56));
                  *(_QWORD *)(*(_QWORD *)(v67 + 16) + v78 * 4 + 56) = 0;
                }
                else
                {
                  if ( *(_DWORD *)(a2 + 8) )
                    v80 = *(_QWORD *)(a2 + 24);
                  else
                    v80 = *(_QWORD *)(a2 + 32);
                  v81 = *(_DWORD *)(v69 + 8);
                  *(_OWORD *)v136 = SendBndAckMessageNoRejectReason;
                  v82 = ntohl(v81);
                  LogETWFailoverAuditLogEvent((int)v136, v82, v80, *(_QWORD *)a2, v76[v78 + 12], 0, 0);
                  v67 = v125;
                }
                v76 = *(_DWORD **)(v67 + 16);
                ++v77;
              }
              while ( v77 < v76[6] );
              v11 = v126;
            }
            _InterlockedIncrement(&DhcpGlobalFailoverBndAckSent);
          }
          if ( *(_BYTE *)(**(_QWORD **)(v67 + 16) + 2LL) == 11 )
          {
            if ( *(_DWORD *)(a2 + 8) )
              v87 = *(_QWORD *)(a2 + 24);
            else
              v87 = *(_QWORD *)(a2 + 32);
            v88 = *(_DWORD *)(v69 + 8);
            *(_OWORD *)v130 = SendContactMessage;
            v89 = ntohl(v88);
            LogETWFailoverAuditLogEvent((int)v130, v89, v87, *(_QWORD *)a2, 0, 0, 0);
          }
          if ( *(_BYTE *)(**(_QWORD **)(v67 + 16) + 2LL) == 5 )
          {
            if ( *(_DWORD *)(a2 + 8) )
              v90 = *(_QWORD *)(a2 + 24);
            else
              v90 = *(_QWORD *)(a2 + 32);
            v91 = *(_DWORD *)(v69 + 8);
            *(_OWORD *)v130 = SendConnectMessage;
            v92 = ntohl(v91);
            LogETWFailoverAuditLogEvent((int)v130, v92, v90, *(_QWORD *)a2, 0, 0, 0);
          }
          if ( *(_BYTE *)(**(_QWORD **)(v67 + 16) + 2LL) == 9 )
          {
            if ( *(_DWORD *)(a2 + 8) )
              v93 = *(_QWORD *)(a2 + 24);
            else
              v93 = *(_QWORD *)(a2 + 32);
            v94 = *(_DWORD *)(v69 + 8);
            *(_OWORD *)v130 = SendUpdReqMessage;
            v95 = ntohl(v94);
            LogETWFailoverAuditLogEvent((int)v130, v95, v93, *(_QWORD *)a2, 0, 0, 0);
          }
          if ( *(_BYTE *)(**(_QWORD **)(v67 + 16) + 2LL) == 7 )
          {
            if ( *(_DWORD *)(a2 + 8) )
              v96 = *(_QWORD *)(a2 + 24);
            else
              v96 = *(_QWORD *)(a2 + 32);
            v97 = *(_DWORD *)(v69 + 8);
            *(_OWORD *)v130 = SendUpdReqAllMessage;
            v98 = ntohl(v97);
            LogETWFailoverAuditLogEvent((int)v130, v98, v96, *(_QWORD *)a2, 0, 0, 0);
          }
          if ( *(_BYTE *)(**(_QWORD **)(v67 + 16) + 2LL) == 8 )
          {
            if ( *(_DWORD *)(a2 + 8) )
              v99 = *(_QWORD *)(a2 + 24);
            else
              v99 = *(_QWORD *)(a2 + 32);
            v100 = *(_DWORD *)(v69 + 8);
            *(_OWORD *)v130 = SendUpdDoneMessage;
            v101 = ntohl(v100);
            LogETWFailoverAuditLogEvent((int)v130, v101, v99, *(_QWORD *)a2, 0, 0, 0);
          }
          v102 = &Annotation;
          if ( *(_BYTE *)(**(_QWORD **)(v67 + 16) + 2LL) == 10 )
          {
            memset_0(v146, 0, sizeof(v146));
            v103 = DhcpConvertSystemTime(*(unsigned int *)(a2 + 144), v146);
            v104 = *(_DWORD *)(a2 + 56);
            if ( v103 )
            {
              if ( v104 == 2 )
                v110 = *(unsigned int *)(a2 + 60);
              else
                v110 = *(unsigned int *)(a2 + 56);
              v111 = FailoverRelationStateDescription[v110];
              if ( *(_DWORD *)(a2 + 8) )
                v112 = *(_QWORD *)(a2 + 24);
              else
                v112 = *(_QWORD *)(a2 + 32);
              v113 = *(_DWORD *)(v69 + 8);
              *(_OWORD *)v130 = SendStateMessage;
              v114 = ntohl(v113);
              LogETWFailoverAuditLogEvent((int)v130, v114, v112, *(_QWORD *)a2, 0, (__int64)v111, (__int64)&Annotation);
            }
            else
            {
              if ( v104 == 2 )
                v105 = *(unsigned int *)(a2 + 60);
              else
                v105 = *(unsigned int *)(a2 + 56);
              v106 = FailoverRelationStateDescription[v105];
              if ( *(_DWORD *)(a2 + 8) )
                v107 = *(_QWORD *)(a2 + 24);
              else
                v107 = *(_QWORD *)(a2 + 32);
              v108 = *(_DWORD *)(v69 + 8);
              *(_OWORD *)v130 = SendStateMessage;
              v109 = ntohl(v108);
              LogETWFailoverAuditLogEvent((int)v130, v109, v107, *(_QWORD *)a2, 0, (__int64)v106, (__int64)v146);
            }
          }
          v115 = *(unsigned __int8 **)(v67 + 16);
          if ( *(_BYTE *)(*(_QWORD *)v115 + 2LL) == 6 )
          {
            v116 = v115[392];
            if ( (_BYTE)v116 )
            {
              if ( (_BYTE)v116 == 0xFE )
                v117 = qword_1800FB780;
              else
                v117 = FailoverRejectReasonDescription[v116];
              v118 = &Annotation;
              v119 = *(_DWORD *)(v69 + 8);
              if ( v141 )
                LODWORD(v118) = v141;
              *(_OWORD *)v130 = SendConnectAckMessageRejectReason;
              if ( *(_QWORD *)v142 )
                LODWORD(v102) = v142[0];
              v120 = ntohl(v119);
              LogETWFailoverAuditLogEvent((int)v130, v120, (int)v102, (int)v118, 0, v117, 0);
            }
            else
            {
              if ( a2 )
              {
                v102 = *(const size_t **)a2;
                if ( *(_DWORD *)(a2 + 8) )
                  v121 = *(const size_t **)(a2 + 24);
                else
                  v121 = *(const size_t **)(a2 + 32);
              }
              else
              {
                v121 = &Annotation;
              }
              v122 = *(_DWORD *)(v69 + 8);
              *(_OWORD *)v142 = SendConnectAckMessage;
              v123 = ntohl(v122);
              LogETWFailoverAuditLogEvent((int)v142, v123, (int)v121, (int)v102, 0, 0, 0);
            }
          }
        }
        goto LABEL_244;
      }
      while ( 1 )
      {
        v59 = v127;
        LODWORD(Size[0]) = v58 - v127;
        v60 = HeapAlloc(gDhcpHeap, 8u, v58 - v127);
        if ( !v60 )
          break;
        memcpy_0(v60, (const void *)(**(_QWORD **)(v125 + 16) + v59), LODWORD(Size[0]));
        Size[1] = (size_t)v60;
        v11 = WSASend(*(_QWORD *)(*(_QWORD *)v136 + 8LL), (LPWSABUF)Size, 1u, &NumberOfBytesSent, 0, 0, 0);
        v126 = v11;
        v127 += NumberOfBytesSent;
        if ( v11 == -1 )
        {
          Error = WSAGetLastError();
          v11 = Error;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_5bd49953df5f3f59743b495ddca40749_Traceguids, Error);
          }
          if ( v11 != 10035 )
            goto LABEL_163;
          if ( a5 )
          {
            v62 = WSAWaitForMultipleEvents(1u, &hEvents, 0, 0xFFFFFFFF, 0);
            v126 = v62;
            v11 = v62;
            if ( v62 == -1 || v62 == 258 )
              goto LABEL_163;
            WSAEnumNetworkEvents(*(_QWORD *)(*(_QWORD *)v136 + 8LL), hEvents, &NetworkEvents);
            if ( (NetworkEvents.lNetworkEvents & 2) != 0 )
            {
              v63 = (unsigned int)NetworkEvents.iErrorCode[1];
              if ( NetworkEvents.iErrorCode[1] )
              {
                v11 = NetworkEvents.iErrorCode[1];
                v64 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
                {
                  v65 = 39;
                  goto LABEL_144;
                }
                goto LABEL_163;
              }
            }
            else if ( (NetworkEvents.lNetworkEvents & 0x20) != 0 )
            {
              v11 = NetworkEvents.iErrorCode[5];
              if ( NetworkEvents.iErrorCode[5] )
              {
                v64 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
                {
                  v65 = 40;
                  v63 = (unsigned int)NetworkEvents.iErrorCode[5];
LABEL_144:
                  WPP_SF_D(v64[2], v65, &WPP_5bd49953df5f3f59743b495ddca40749_Traceguids, v63);
                }
              }
              else
              {
                v11 = 10057;
              }
LABEL_163:
              HeapFree(gDhcpHeap, 0, v60);
              goto LABEL_244;
            }
          }
          else
          {
            v143[0] = *(HANDLE *)(*(_QWORD *)v136 + 40LL);
            v143[1] = *(HANDLE *)(*(_QWORD *)v136 + 48LL);
            v126 = WSAWaitForMultipleEvents(2u, v143, 0, 0xFFFFFFFF, 0);
            v11 = v126;
            if ( v126 )
              goto LABEL_163;
            if ( !WSAResetEvent(*(HANDLE *)(*(_QWORD *)v136 + 40LL))
              && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
            {
              v66 = WSAGetLastError();
              WPP_SF_D(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v11 + 41,
                &WPP_5bd49953df5f3f59743b495ddca40749_Traceguids,
                v66);
            }
          }
        }
        HeapFree(gDhcpHeap, 0, v60);
        if ( v127 == v58 )
          goto LABEL_156;
      }
      v19 = 1367;
      goto LABEL_37;
    }
    v18 = RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"SYSTEM\\CurrentControlSet\\Services\\DHCPServer\\Parameters",
            0,
            0x1Fu,
            &hKey);
    v11 = v18;
    if ( v18 )
    {
      v19 = 1196;
      v20 = "RegOpenKeyExW";
      v21 = v18;
LABEL_23:
      DhcpPrintFOErrorEx(v21, "DhcpCMSendFailoverMessage", v20, v19);
      goto LABEL_244;
    }
    v23 = RegQueryValueExW(hKey, L"DhcpHATestHookRelName", 0, &Type, 0, &cbData);
    if ( v23 == 2 )
    {
      v13 = 1;
      goto LABEL_43;
    }
    if ( v23 )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
      {
        v25 = 29;
LABEL_42:
        WPP_SF_D(v24[2], v25, &WPP_5bd49953df5f3f59743b495ddca40749_Traceguids, v23);
      }
    }
    else
    {
      v26 = HeapAlloc(gDhcpHeap, 8u, 2LL * cbData);
      lpMem = v26;
      if ( !v26 )
      {
        v19 = 1214;
LABEL_37:
        v20 = "DhcpAllocateMemory";
        v11 = 8;
        v21 = 8;
        goto LABEL_23;
      }
      v23 = RegQueryValueExW(hKey, L"DhcpHATestHookRelName", 0, &Type, (LPBYTE)v26, &cbData);
      if ( v23 )
      {
        v24 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
        {
          v25 = 30;
          goto LABEL_42;
        }
      }
    }
LABEL_43:
    cbData = 4;
    v27 = RegQueryValueExW(hKey, L"DhcpHATestHookPacketType", 0, &Type, Data, &cbData);
    if ( v27
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_5bd49953df5f3f59743b495ddca40749_Traceguids, v27);
    }
    cbData = 4;
    v28 = RegQueryValueExW(hKey, L"DhcpHATestHookTimeOut", 0, &Type, v131, &cbData);
    v126 = v28;
    v11 = v28;
    if ( v28
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_5bd49953df5f3f59743b495ddca40749_Traceguids, v28);
    }
    if ( lpMem )
    {
      v29 = *(__int64 **)(*(_QWORD *)v136 + 56LL);
      if ( v29 )
      {
        v30 = (unsigned __int16 *)lpMem;
        if ( *(_WORD *)lpMem )
        {
          v31 = *v29;
          while ( 1 )
          {
            v32 = v30;
            do
            {
              v33 = *(unsigned __int16 *)((char *)v32 + v31 - (_QWORD)v30);
              v34 = *v32 - v33;
              if ( v34 )
                break;
              ++v32;
            }
            while ( v33 );
            if ( !v34 )
              break;
            v35 = -1;
            do
              ++v35;
            while ( v30[v35] );
            v30 += (unsigned int)(v35 + 1);
            if ( !*v30 )
              goto LABEL_64;
          }
          v13 = 1;
        }
      }
    }
LABEL_64:
    v36 = *(__int64 **)(*(_QWORD *)v136 + 56LL);
    if ( v36 )
      v12 = *v36;
    if ( v13 != 1 )
      goto LABEL_127;
    v37 = *(unsigned __int8 *)(*(_QWORD *)v130 + 2LL);
    v38 = dword_1800E81FC[v37];
    if ( v38 != (*(_DWORD *)Data & v38) )
      goto LABEL_127;
    if ( (unsigned int)v37 > 8 )
    {
      v44 = v37 - 9;
      if ( v44 )
      {
        v45 = v44 - 1;
        if ( v45 )
        {
          v46 = v45 - 1;
          if ( v46 )
          {
            if ( v46 == 1 && (Microsoft_Windows_DHCP_ServerEnableBits & 1) != 0 )
            {
              v43 = &Disconnect;
              goto LABEL_99;
            }
          }
          else if ( (Microsoft_Windows_DHCP_ServerEnableBits & 1) != 0 )
          {
            v43 = &Contact;
            goto LABEL_99;
          }
        }
        else if ( (Microsoft_Windows_DHCP_ServerEnableBits & 1) != 0 )
        {
          v43 = &State;
          goto LABEL_99;
        }
      }
      else if ( (Microsoft_Windows_DHCP_ServerEnableBits & 1) != 0 )
      {
        v43 = &UpdReq;
        goto LABEL_99;
      }
    }
    else if ( (_DWORD)v37 == 8 )
    {
      if ( (Microsoft_Windows_DHCP_ServerEnableBits & 1) != 0 )
      {
        v43 = &UpdDone;
        goto LABEL_99;
      }
    }
    else
    {
      v39 = v37 - 3;
      if ( v39 )
      {
        v40 = v39 - 1;
        if ( v40 )
        {
          v41 = v40 - 1;
          if ( v41 )
          {
            v42 = v41 - 1;
            if ( v42 )
            {
              if ( v42 == 1 && (Microsoft_Windows_DHCP_ServerEnableBits & 1) != 0 )
              {
                v43 = &UpdReqAll;
LABEL_99:
                McTemplateU0zqbr1_EventWriteTransfer(
                  v38,
                  (_DWORD)v43,
                  v12,
                  *(_DWORD *)(*(_QWORD *)(v125 + 16) + 8LL),
                  **(_QWORD **)(v125 + 16));
              }
            }
            else if ( (Microsoft_Windows_DHCP_ServerEnableBits & 1) != 0 )
            {
              v43 = &ConnectAck;
              goto LABEL_99;
            }
          }
          else if ( (Microsoft_Windows_DHCP_ServerEnableBits & 1) != 0 )
          {
            v43 = &Connect;
            goto LABEL_99;
          }
        }
        else if ( (Microsoft_Windows_DHCP_ServerEnableBits & 1) != 0 )
        {
          v43 = &BndAck;
          goto LABEL_99;
        }
      }
      else if ( (Microsoft_Windows_DHCP_ServerEnableBits & 1) != 0 )
      {
        v43 = &BndUpd;
        goto LABEL_99;
      }
    }
    v47 = WSACreateEvent();
    if ( !v47
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_5bd49953df5f3f59743b495ddca40749_Traceguids, v11);
    }
    v48 = RegNotifyChangeKeyValue(hKey, 1, 4u, v47, 1);
    if ( v48 )
    {
      v54 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) == 0 )
      {
        goto LABEL_121;
      }
      v55 = 36;
    }
    else
    {
      v49 = time(0);
      v50 = *(_QWORD *)v136;
      v51 = v49;
      while ( 1 )
      {
        cbData = 4;
        v52 = RegQueryValueExW(hKey, **(LPCWSTR **)(v50 + 56), 0, &Type, v134, &cbData);
        if ( (v52 & 0xFFFFFFFD) != 0 )
          break;
        if ( *(_DWORD *)v134 != 1 )
        {
          v53 = time(0);
          if ( (unsigned int)(v53 - v51) <= *(_DWORD *)v131 )
          {
            *(_DWORD *)v131 += v51 - v53;
            if ( !WaitForSingleObject(v47, 1000 * *(_DWORD *)v131) )
              continue;
          }
        }
        goto LABEL_114;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_5bd49953df5f3f59743b495ddca40749_Traceguids, v52);
      }
LABEL_114:
      v48 = RegSetValueExW(hKey, **(LPCWSTR **)(v50 + 56), 0, 4u, v137, 4u);
      v54 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) == 0 )
      {
        goto LABEL_121;
      }
      v55 = 35;
    }
    WPP_SF_D(v54[2], v55, &WPP_5bd49953df5f3f59743b495ddca40749_Traceguids, v48);
LABEL_121:
    if ( !WSACloseEvent(v47)
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
    {
      v56 = WSAGetLastError();
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_5bd49953df5f3f59743b495ddca40749_Traceguids, v56);
    }
    v57 = RegCloseKey(hKey);
    v126 = v57;
    v11 = v57;
    if ( v57 )
      DhcpPrintFOErrorEx(v57, "DhcpCMSendFailoverMessage", "RegCloseKey", 1354);
LABEL_127:
    if ( lpMem )
      HeapFree(gDhcpHeap, 0, lpMem);
    goto LABEL_129;
  }
LABEL_244:
  LeaveCriticalSection(lpCriticalSection);
  return v11;
}

```

## disassembly

```asm
0x1800b1c74  push    rbp
0x1800b1c76  push    rbx
0x1800b1c77  push    rsi
0x1800b1c78  push    rdi
0x1800b1c79  push    r12
0x1800b1c7b  push    r13
0x1800b1c7d  push    r14
0x1800b1c7f  push    r15
0x1800b1c81  lea     rbp, [rsp-258h]
0x1800b1c89  sub     rsp, 358h
0x1800b1c90  mov     rax, cs:__security_cookie
0x1800b1c97  xor     rax, rsp
0x1800b1c9a  mov     [rbp+290h+var_50], rax
0x1800b1ca1  mov     rax, [rbp+290h+arg_38]
0x1800b1ca8  xor     r15d, r15d
0x1800b1cab  xorps   xmm0, xmm0
0x1800b1cae  mov     qword ptr [rbp+290h+var_2B0], rax
0x1800b1cb2  mov     rax, [rbp+290h+arg_30]
0x1800b1cb9  mov     rdi, rcx
0x1800b1cbc  xor     ecx, ecx
0x1800b1cbe  mov     [rbp+290h+var_2B8], rax
0x1800b1cc2  mov     rax, [rbp+290h+arg_28]
0x1800b1cc9  mov     r10, r8
0x1800b1ccc  mov     [rbp+290h+hEvents], rax
0x1800b1cd0  mov     rsi, rdx
0x1800b1cd3  mov     [rsp+390h+var_348], r9
0x1800b1cd8  mov     r14d, r15d
0x1800b1cdb  mov     [rbp+290h+lpCriticalSection], r8
0x1800b1cdf  mov     r13d, r15d
0x1800b1ce2  mov     [rsp+390h+var_340], r15d
0x1800b1ce7  mov     r12d, r15d
0x1800b1cea  mov     [rbp+290h+NumberOfBytesSent], r15d
0x1800b1cee  mov     [rsp+390h+var_33C], r15d
0x1800b1cf3  mov     [rsp+390h+hKey], 0FFFFFFFF80000002h
0x1800b1cfc  mov     qword ptr [rbp+290h+NetworkEvents.iErrorCode+1Ch], rcx
0x1800b1d00  mov     [rbp+290h+NetworkEvents.iErrorCode+24h], ecx
0x1800b1d03  mov     [rbp+290h+lpMem], r15
0x1800b1d07  mov     dword ptr [rbp+290h+Data], r15d
0x1800b1d0b  mov     dword ptr [rbp+290h+var_310], r15d
0x1800b1d0f  mov     [rsp+390h+Type], r15d
0x1800b1d14  mov     [rsp+390h+cbData], r15d
0x1800b1d19  mov     dword ptr [rbp+290h+var_2FC], r15d
0x1800b1d1d  mov     dword ptr [rbp+290h+var_2E0], r15d
0x1800b1d21  movups  xmmword ptr [rbp+290h+Size], xmm0
0x1800b1d25  movups  xmmword ptr [rbp+290h+var_2A0], xmm0
0x1800b1d29  movups  xmmword ptr [rbp+290h+NetworkEvents.lNetworkEvents], xmm0
0x1800b1d2d  movups  xmmword ptr [rbp+290h+NetworkEvents.iErrorCode+0Ch], xmm0
0x1800b1d31  test    rdi, rdi
0x1800b1d34  jnz     short loc_1800B1D64
0x1800b1d36  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b1d3d  lea     rdi, WPP_GLOBAL_Control
0x1800b1d44  cmp     rcx, rdi
0x1800b1d47  jz      loc_1800B1F02
0x1800b1d4d  mov     ebx, 800000h
0x1800b1d52  test    [rcx+1Ch], ebx
0x1800b1d55  jz      loc_1800B1F02
0x1800b1d5b  lea     edx, [r15+19h]
0x1800b1d5f  jmp     loc_1800B1EEC
0x1800b1d64  cmp     [rbp+290h+arg_20], r15d
0x1800b1d6b  jz      short loc_1800B1D9F
0x1800b1d6d  test    rax, rax
0x1800b1d70  jnz     short loc_1800B1D9F
0x1800b1d72  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b1d79  lea     rdi, WPP_GLOBAL_Control
0x1800b1d80  cmp     rcx, rdi
0x1800b1d83  jz      loc_1800B1F02
0x1800b1d89  mov     ebx, 800000h
0x1800b1d8e  test    [rcx+1Ch], ebx
0x1800b1d91  jz      loc_1800B1F02
0x1800b1d97  lea     edx, [rax+1Ah]
0x1800b1d9a  jmp     loc_1800B1EEC
0x1800b1d9f  test    rsi, rsi
0x1800b1da2  jnz     short loc_1800B1DD6
0x1800b1da4  test    r8, r8
0x1800b1da7  jnz     short loc_1800B1DD6
0x1800b1da9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b1db0  lea     rdi, WPP_GLOBAL_Control
0x1800b1db7  cmp     rcx, rdi
0x1800b1dba  jz      loc_1800B1F02
0x1800b1dc0  mov     ebx, 800000h
0x1800b1dc5  test    [rcx+1Ch], ebx
0x1800b1dc8  jz      loc_1800B1F02
0x1800b1dce  lea     edx, [rsi+1Bh]
0x1800b1dd1  jmp     loc_1800B1EEC
0x1800b1dd6  mov     rax, [r9+10h]
0x1800b1dda  mov     rcx, [rax]
0x1800b1ddd  mov     qword ptr [rsp+390h+var_320], rcx
0x1800b1de2  test    rsi, rsi
0x1800b1de5  jz      short loc_1800B1E2A
0x1800b1de7  cmp     [rax+188h], r15b
0x1800b1dee  jnz     short loc_1800B1E2A
0x1800b1df0  lea     rbx, [rdx+48h]
0x1800b1df4  mov     rcx, rbx; SRWLock
0x1800b1df7  call    cs:__imp_AcquireSRWLockShared
0x1800b1dfe  nop     dword ptr [rax+rax+00h]
0x1800b1e03  mov     rax, [rsi+1E8h]
0x1800b1e0a  mov     rcx, rbx; SRWLock
0x1800b1e0d  mov     [rbp+290h+lpCriticalSection], rax
0x1800b1e11  test    rax, rax
0x1800b1e14  jz      loc_1800B1EBE
0x1800b1e1a  call    cs:__imp_ReleaseSRWLockShared
0x1800b1e21  nop     dword ptr [rax+rax+00h]
0x1800b1e26  mov     r10, [rbp+290h+lpCriticalSection]
0x1800b1e2a  mov     rcx, r10; lpCriticalSection
0x1800b1e2d  call    cs:__imp_EnterCriticalSection
0x1800b1e34  nop     dword ptr [rax+rax+00h]
0x1800b1e39  mov     rax, [rdi]
0x1800b1e3c  mov     qword ptr [rbp+290h+var_2F0], rax
0x1800b1e40  test    rax, rax
0x1800b1e43  jz      loc_1800B2D4F
0x1800b1e49  xor     eax, eax
0x1800b1e4b  lea     rdi, WPP_GLOBAL_Control
0x1800b1e52  cmp     cs:isDhcpFailoverTestEnv, eax
0x1800b1e58  lea     r15, WPP_5bd49953df5f3f59743b495ddca40749_Traceguids
0x1800b1e5f  mov     ebx, 800000h
0x1800b1e64  jz      loc_1800B24E8
0x1800b1e6a  lea     rax, [rsp+390h+hKey]
0x1800b1e6f  mov     r9d, 1Fh; samDesired
0x1800b1e75  xor     r8d, r8d; ulOptions
0x1800b1e78  mov     [rsp+390h+phkResult], rax; phkResult
0x1800b1e7d  lea     rdx, aSystemCurrentc_4; "SYSTEM\\CurrentControlSet\\Services\\DH"...
0x1800b1e84  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800b1e8b  call    cs:__imp_RegOpenKeyExW
0x1800b1e92  nop     dword ptr [rax+rax+00h]
0x1800b1e97  mov     r14d, eax
0x1800b1e9a  test    eax, eax
0x1800b1e9c  jz      short loc_1800B1F0C
0x1800b1e9e  mov     r9d, 4ACh
0x1800b1ea4  lea     r8, aRegopenkeyexw; "RegOpenKeyExW"
0x1800b1eab  mov     ecx, eax
0x1800b1ead  lea     rdx, aDhcpcmsendfail; "DhcpCMSendFailoverMessage"
0x1800b1eb4  call    DhcpPrintFOErrorEx
0x1800b1eb9  jmp     loc_1800B2D4F
0x1800b1ebe  call    cs:__imp_ReleaseSRWLockShared
0x1800b1ec5  nop     dword ptr [rax+rax+00h]
0x1800b1eca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b1ed1  lea     rdi, WPP_GLOBAL_Control
0x1800b1ed8  cmp     rcx, rdi
0x1800b1edb  jz      short loc_1800B1F02
0x1800b1edd  mov     ebx, 800000h
0x1800b1ee2  test    [rcx+1Ch], ebx
0x1800b1ee5  jz      short loc_1800B1F02
0x1800b1ee7  mov     edx, 1Ch
0x1800b1eec  mov     rcx, [rcx+10h]
0x1800b1ef0  lea     r8, WPP_5bd49953df5f3f59743b495ddca40749_Traceguids
0x1800b1ef7  mov     r9d, 57h ; 'W'
0x1800b1efd  call    WPP_SF_D
0x1800b1f02  mov     eax, 57h ; 'W'
0x1800b1f07  jmp     loc_1800B2D62
0x1800b1f0c  mov     rcx, [rsp+390h+hKey]; hKey
0x1800b1f11  lea     rax, [rsp+390h+cbData]
0x1800b1f16  mov     [rsp+390h+lpcbData], rax; lpcbData
0x1800b1f1b  lea     r9, [rsp+390h+Type]; lpType
0x1800b1f20  xor     r14d, r14d
0x1800b1f23  lea     rdx, aDhcphatesthook; "DhcpHATestHookRelName"
0x1800b1f2a  xor     r8d, r8d; lpReserved
0x1800b1f2d  mov     [rsp+390h+phkResult], r14; lpData
0x1800b1f32  call    cs:__imp_RegQueryValueExW
0x1800b1f39  nop     dword ptr [rax+rax+00h]
0x1800b1f3e  cmp     eax, 2
0x1800b1f41  jnz     short loc_1800B1F4C
0x1800b1f43  lea     r12d, [r14+1]
0x1800b1f47  jmp     loc_1800B2010
0x1800b1f4c  test    eax, eax
0x1800b1f4e  jz      short loc_1800B1F73
0x1800b1f50  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b1f57  cmp     rcx, rdi
0x1800b1f5a  jz      loc_1800B2010
0x1800b1f60  test    [rcx+1Ch], ebx
0x1800b1f63  jz      loc_1800B2010
0x1800b1f69  mov     edx, 1Dh
0x1800b1f6e  jmp     loc_1800B2001
0x1800b1f73  mov     r8d, [rsp+390h+cbData]
0x1800b1f78  mov     edx, 8; dwFlags
0x1800b1f7d  mov     rcx, cs:gDhcpHeap; hHeap
0x1800b1f84  add     r8, r8; dwBytes
0x1800b1f87  call    cs:__imp_HeapAlloc
0x1800b1f8e  nop     dword ptr [rax+rax+00h]
0x1800b1f93  mov     [rbp+290h+lpMem], rax
0x1800b1f97  test    rax, rax
0x1800b1f9a  jnz     short loc_1800B1FB8
0x1800b1f9c  mov     r9d, 4BEh
0x1800b1fa2  mov     eax, 8
0x1800b1fa7  lea     r8, aDhcpallocateme; "DhcpAllocateMemory"
0x1800b1fae  mov     r14d, eax
0x1800b1fb1  mov     ecx, eax
0x1800b1fb3  jmp     loc_1800B1EAD
0x1800b1fb8  lea     rcx, [rsp+390h+cbData]
0x1800b1fbd  xor     r8d, r8d; lpReserved
0x1800b1fc0  mov     [rsp+390h+lpcbData], rcx; lpcbData
0x1800b1fc5  lea     r9, [rsp+390h+Type]; lpType
0x1800b1fca  mov     rcx, [rsp+390h+hKey]; hKey
0x1800b1fcf  lea     rdx, aDhcphatesthook; "DhcpHATestHookRelName"
0x1800b1fd6  mov     [rsp+390h+phkResult], rax; lpData
0x1800b1fdb  call    cs:__imp_RegQueryValueExW
0x1800b1fe2  nop     dword ptr [rax+rax+00h]
0x1800b1fe7  test    eax, eax
0x1800b1fe9  jz      short loc_1800B2010
0x1800b1feb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b1ff2  cmp     rcx, rdi
0x1800b1ff5  jz      short loc_1800B2010
0x1800b1ff7  test    [rcx+1Ch], ebx
0x1800b1ffa  jz      short loc_1800B2010
0x1800b1ffc  mov     edx, 1Eh
0x1800b2001  mov     rcx, [rcx+10h]
0x1800b2005  mov     r9d, eax
0x1800b2008  mov     r8, r15
0x1800b200b  call    WPP_SF_D
0x1800b2010  mov     rcx, [rsp+390h+hKey]; hKey
0x1800b2015  lea     rax, [rsp+390h+cbData]
0x1800b201a  mov     [rsp+390h+lpcbData], rax; lpcbData
0x1800b201f  lea     r9, [rsp+390h+Type]; lpType
0x1800b2024  lea     rax, [rbp+290h+Data]
0x1800b2028  mov     [rsp+390h+cbData], 4
0x1800b2030  xor     r8d, r8d; lpReserved
0x1800b2033  mov     [rsp+390h+phkResult], rax; lpData
0x1800b2038  lea     rdx, aDhcphatesthook_0; "DhcpHATestHookPacketType"
0x1800b203f  call    cs:__imp_RegQueryValueExW
0x1800b2046  nop     dword ptr [rax+rax+00h]
0x1800b204b  test    eax, eax
0x1800b204d  jz      short loc_1800B2074
0x1800b204f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b2056  cmp     rcx, rdi
0x1800b2059  jz      short loc_1800B2074
0x1800b205b  test    [rcx+1Ch], ebx
0x1800b205e  jz      short loc_1800B2074
0x1800b2060  mov     rcx, [rcx+10h]
0x1800b2064  mov     edx, 1Fh
0x1800b2069  mov     r9d, eax
0x1800b206c  mov     r8, r15
0x1800b206f  call    WPP_SF_D
0x1800b2074  mov     rcx, [rsp+390h+hKey]; hKey
0x1800b2079  lea     rax, [rsp+390h+cbData]
0x1800b207e  mov     [rsp+390h+lpcbData], rax; lpcbData
0x1800b2083  lea     r9, [rsp+390h+Type]; lpType
0x1800b2088  lea     rax, [rbp+290h+var_310]
0x1800b208c  mov     [rsp+390h+cbData], 4
0x1800b2094  xor     r8d, r8d; lpReserved
0x1800b2097  mov     [rsp+390h+phkResult], rax; lpData
0x1800b209c  lea     rdx, aDhcphatesthook_1; "DhcpHATestHookTimeOut"
0x1800b20a3  call    cs:__imp_RegQueryValueExW
0x1800b20aa  nop     dword ptr [rax+rax+00h]
0x1800b20af  xor     r8d, r8d
0x1800b20b2  mov     [rsp+390h+var_340], eax
0x1800b20b6  mov     r14d, eax
0x1800b20b9  test    eax, eax
0x1800b20bb  jz      short loc_1800B20E4
0x1800b20bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b20c4  cmp     rcx, rdi
0x1800b20c7  jz      short loc_1800B20E4
0x1800b20c9  test    [rcx+1Ch], ebx
0x1800b20cc  jz      short loc_1800B20E4
0x1800b20ce  mov     rcx, [rcx+10h]
0x1800b20d2  lea     edx, [r8+20h]
0x1800b20d6  mov     r8, r15
0x1800b20d9  mov     r9d, eax
0x1800b20dc  call    WPP_SF_D
0x1800b20e1  xor     r8d, r8d
0x1800b20e4  mov     rcx, [rbp+290h+lpMem]
0x1800b20e8  mov     r11, qword ptr [rbp+290h+var_2F0]
0x1800b20ec  test    rcx, rcx
0x1800b20ef  jz      short loc_1800B214C
0x1800b20f1  mov     rax, [r11+38h]
0x1800b20f5  test    rax, rax
0x1800b20f8  jz      short loc_1800B214C
0x1800b20fa  mov     r9, rcx
0x1800b20fd  cmp     r8w, [rcx]
0x1800b2101  jz      short loc_1800B214C
0x1800b2103  mov     r10, [rax]
0x1800b2106  mov     r8, r10
0x1800b2109  mov     rax, r9
0x1800b210c  sub     r8, r9
0x1800b210f  movzx   edx, word ptr [rax]
0x1800b2112  movzx   ecx, word ptr [rax+r8]
0x1800b2117  sub     edx, ecx
0x1800b2119  jnz     short loc_1800B2123
0x1800b211b  add     rax, 2
0x1800b211f  test    ecx, ecx
0x1800b2121  jnz     short loc_1800B210F
0x1800b2123  xor     r8d, r8d
0x1800b2126  test    edx, edx
0x1800b2128  jz      short loc_1800B2146
0x1800b212a  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800b212e  inc     rax
0x1800b2131  cmp     [r9+rax*2], r8w
0x1800b2136  jnz     short loc_1800B212E
0x1800b2138  inc     eax
0x1800b213a  lea     r9, [r9+rax*2]
0x1800b213e  cmp     r8w, [r9]
0x1800b2142  jnz     short loc_1800B2106
0x1800b2144  jmp     short loc_1800B214C
0x1800b2146  mov     r12d, 1
0x1800b214c  mov     rax, [r11+38h]
0x1800b2150  test    rax, rax
0x1800b2153  jz      short loc_1800B2158
0x1800b2155  mov     r13, [rax]
0x1800b2158  cmp     r12d, 1
0x1800b215c  jnz     loc_1800B24CA
0x1800b2162  mov     rax, qword ptr [rsp+390h+var_320]
0x1800b2167  lea     rcx, __ImageBase
  ... truncated ...
```
