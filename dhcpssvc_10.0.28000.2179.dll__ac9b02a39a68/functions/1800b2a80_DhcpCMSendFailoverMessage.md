# DhcpCMSendFailoverMessage

- ea: `0x1800b2a80`
- end: `0x1800b3bd8`
- name: `DhcpCMSendFailoverMessage`
- size: `4440`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800b25b4`
- `0x1800b3be0`

## callees

- `0x18000282c`
- `0x18001c45c`
- `0x18008094c`
- `0x180080c8c`
- `0x1800b2a80`
- `0x1800b3e90`
- `0x1800cc414`
- `0x1800cda62`
- `0x1800cda7a`
- `0x1800cdac0`

## import_xrefs

- `msvcrt!time` at `0x1800b3113`
- `msvcrt!time` at `0x1800b3171`
- `msvcrt!time` at `0x1800b3113`
- `msvcrt!time` at `0x1800b3171`
- `ADVAPI32!RegCloseKey` at `0x1800b328f`
- `ADVAPI32!RegCloseKey` at `0x1800b328f`
- `ADVAPI32!RegOpenKeyExW` at `0x1800b2c8e`
- `ADVAPI32!RegOpenKeyExW` at `0x1800b2c8e`
- `ADVAPI32!RegQueryValueExW` at `0x1800b2d35`
- `ADVAPI32!RegQueryValueExW` at `0x1800b2ddd`
- `ADVAPI32!RegQueryValueExW` at `0x1800b2e41`
- `ADVAPI32!RegQueryValueExW` at `0x1800b2ea5`
- `ADVAPI32!RegQueryValueExW` at `0x1800b3156`
- `ADVAPI32!RegQueryValueExW` at `0x1800b2d35`
- `ADVAPI32!RegQueryValueExW` at `0x1800b2ddd`
- `ADVAPI32!RegQueryValueExW` at `0x1800b2e41`
- `ADVAPI32!RegQueryValueExW` at `0x1800b2ea5`
- `ADVAPI32!RegQueryValueExW` at `0x1800b3156`
- `ADVAPI32!RegSetValueExW` at `0x1800b31fa`
- `ADVAPI32!RegSetValueExW` at `0x1800b31fa`
- `WS2_32!WSAEnumNetworkEvents` at `0x1800b342e`
- `WS2_32!WSAEnumNetworkEvents` at `0x1800b342e`
- `WS2_32!WSAResetEvent` at `0x1800b34f9`
- `WS2_32!WSAResetEvent` at `0x1800b34f9`
- `WS2_32!WSASend` at `0x1800b336d`
- `WS2_32!WSASend` at `0x1800b336d`
- `WS2_32!WSACloseEvent` at `0x1800b3246`
- `WS2_32!WSACloseEvent` at `0x1800b3246`
- `WS2_32!WSACreateEvent` at `0x1800b30af`
- `WS2_32!WSACreateEvent` at `0x1800b30af`
- `WS2_32!WSAWaitForMultipleEvents` at `0x1800b33f7`
- `WS2_32!WSAWaitForMultipleEvents` at `0x1800b34d6`
- `WS2_32!WSAWaitForMultipleEvents` at `0x1800b33f7`
- `WS2_32!WSAWaitForMultipleEvents` at `0x1800b34d6`
- `WS2_32!__imp_ntohl` at `0x1800b35da`
- `WS2_32!__imp_ntohl` at `0x1800b3694`
- `WS2_32!__imp_ntohl` at `0x1800b374f`
- `WS2_32!__imp_ntohl` at `0x1800b37fe`
- `WS2_32!__imp_ntohl` at `0x1800b385d`
- `WS2_32!__imp_ntohl` at `0x1800b38bc`
- `WS2_32!__imp_ntohl` at `0x1800b391b`
- `WS2_32!__imp_ntohl` at `0x1800b397a`
- `WS2_32!__imp_ntohl` at `0x1800b3a29`
- `WS2_32!__imp_ntohl` at `0x1800b3aa0`
- `WS2_32!__imp_ntohl` at `0x1800b3b25`
- `WS2_32!__imp_ntohl` at `0x1800b3b75`
- `WS2_32!__imp_ntohl` at `0x1800b35da`
- `WS2_32!__imp_ntohl` at `0x1800b3694`
- `WS2_32!__imp_ntohl` at `0x1800b374f`
- `WS2_32!__imp_ntohl` at `0x1800b37fe`
- `WS2_32!__imp_ntohl` at `0x1800b385d`
- `WS2_32!__imp_ntohl` at `0x1800b38bc`
- `WS2_32!__imp_ntohl` at `0x1800b391b`
- `WS2_32!__imp_ntohl` at `0x1800b397a`
- `WS2_32!__imp_ntohl` at `0x1800b3a29`
- `WS2_32!__imp_ntohl` at `0x1800b3aa0`
- `WS2_32!__imp_ntohl` at `0x1800b3b25`
- `WS2_32!__imp_ntohl` at `0x1800b3b75`
- `WS2_32!__imp_WSAGetLastError` at `0x1800b326b`
- `WS2_32!__imp_WSAGetLastError` at `0x1800b3395`
- `WS2_32!__imp_WSAGetLastError` at `0x1800b351e`
- `WS2_32!__imp_WSAGetLastError` at `0x1800b326b`
- `WS2_32!__imp_WSAGetLastError` at `0x1800b3395`
- `WS2_32!__imp_WSAGetLastError` at `0x1800b351e`
- `KERNEL32!RegNotifyChangeKeyValue` at `0x1800b30fd`
- `KERNEL32!RegNotifyChangeKeyValue` at `0x1800b30fd`
- `KERNEL32!WaitForSingleObject` at `0x1800b319a`
- `KERNEL32!WaitForSingleObject` at `0x1800b319a`
- `KERNEL32!HeapAlloc` at `0x1800b2d89`
- `KERNEL32!HeapAlloc` at `0x1800b3312`
- `KERNEL32!HeapAlloc` at `0x1800b2d89`
- `KERNEL32!HeapAlloc` at `0x1800b3312`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800b2c1b`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800b2cc1`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800b2c1b`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800b2cc1`
- `KERNEL32!AcquireSRWLockShared` at `0x1800b2bf8`
- `KERNEL32!AcquireSRWLockShared` at `0x1800b2bf8`
- `KERNEL32!EnterCriticalSection` at `0x1800b2c30`
- `KERNEL32!EnterCriticalSection` at `0x1800b2c30`
- `KERNEL32!LeaveCriticalSection` at `0x1800b3ba5`
- `KERNEL32!LeaveCriticalSection` at `0x1800b3ba5`
- `KERNEL32!HeapFree` at `0x1800b32d3`
- `KERNEL32!HeapFree` at `0x1800b354d`
- `KERNEL32!HeapFree` at `0x1800b36df`
- `KERNEL32!HeapFree` at `0x1800b3791`
- `KERNEL32!HeapFree` at `0x1800b32d3`
- `KERNEL32!HeapFree` at `0x1800b354d`
- `KERNEL32!HeapFree` at `0x1800b36df`
- `KERNEL32!HeapFree` at `0x1800b3791`

## string_xrefs

- `0x1800b2c80`: `SYSTEM\CurrentControlSet\Services\DHCPServer\Parameters`
- `0x1800b2ca7`: `RegOpenKeyExW`

## pseudocode

```c
__int64 __fastcall DhcpCMSendFailoverMessage(
        __int64 *a1,
        RTL_SRWLOCK *a2,
        struct _RTL_CRITICAL_SECTION *a3,
        __int64 a4,
        int a5,
        void *a6,
        __int64 a7,
        __int64 a8)
{
  struct _RTL_CRITICAL_SECTION *v9; // r10
  unsigned int v11; // r12d
  __int64 v12; // r13
  int v13; // ebx
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
  HANDLE v47; // r13
  unsigned int v48; // eax
  int v49; // eax
  __int64 v50; // r12
  int v51; // ebx
  unsigned int v52; // eax
  int v53; // eax
  _QWORD *v54; // rcx
  __int64 v55; // rdx
  __int64 v56; // rbx
  unsigned int v57; // eax
  unsigned int v58; // eax
  int v59; // ebx
  unsigned int v60; // r12d
  void *v61; // r13
  unsigned int Error; // eax
  DWORD v63; // eax
  __int64 v64; // r9
  _QWORD *v65; // rcx
  __int64 v66; // rdx
  __int64 v67; // rbx
  unsigned int v68; // eax
  __int64 v69; // rsi
  _DWORD *v70; // rdx
  __int64 v71; // r13
  unsigned int v72; // r12d
  __int64 *v73; // r14
  __int64 v74; // r14
  const size_t *Ptr; // rsi
  __int64 v76; // rcx
  u_long v77; // edi
  wchar_t *v78; // rbx
  u_long v79; // eax
  _DWORD *v80; // rcx
  unsigned int v81; // eax
  __int64 v82; // r14
  _BYTE *v83; // rax
  __int64 *v84; // rsi
  u_long v85; // ebx
  __int64 v86; // rsi
  u_long v87; // ecx
  RTL_SRWLOCK v88; // rdi
  u_long v89; // eax
  __int64 *v90; // rax
  __int64 *v91; // rsi
  u_long v92; // ebx
  __int64 v93; // rsi
  u_long v94; // ecx
  RTL_SRWLOCK v95; // rdi
  u_long v96; // eax
  __int64 *v97; // rdi
  __int64 v98; // rdi
  u_long v99; // ecx
  RTL_SRWLOCK v100; // rbx
  u_long v101; // eax
  __int64 *v102; // rdi
  __int64 v103; // rdi
  u_long v104; // ecx
  RTL_SRWLOCK v105; // rbx
  u_long v106; // eax
  __int64 *v107; // rdi
  __int64 v108; // rdi
  u_long v109; // ecx
  RTL_SRWLOCK v110; // rbx
  u_long v111; // eax
  __int64 *v112; // rdi
  __int64 v113; // rdi
  u_long v114; // ecx
  RTL_SRWLOCK v115; // rbx
  u_long v116; // eax
  __int64 *v117; // rdi
  __int64 v118; // rdi
  u_long v119; // ecx
  RTL_SRWLOCK v120; // rbx
  u_long v121; // eax
  __int64 v122; // rax
  const size_t *v123; // rsi
  int v124; // eax
  int Ptr_high; // ecx
  __int64 *v126; // rdi
  wchar_t *v127; // r14
  __int64 v128; // rdi
  u_long v129; // ecx
  RTL_SRWLOCK v130; // rbx
  u_long v131; // edx
  __int64 *v132; // rdi
  wchar_t *v133; // r14
  __int64 v134; // rdi
  u_long v135; // ecx
  RTL_SRWLOCK v136; // rbx
  u_long v137; // edx
  unsigned __int8 *v138; // rcx
  __int64 v139; // rax
  __int64 *v140; // rax
  __int64 v141; // rdi
  const size_t *v142; // rbx
  u_long v143; // ecx
  u_long v144; // eax
  const size_t *v145; // rbx
  u_long v146; // ecx
  u_long v147; // eax
  int v148; // [rsp+40h] [rbp-C0h]
  unsigned int v149; // [rsp+40h] [rbp-C0h]
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v151; // [rsp+48h] [rbp-B8h]
  DWORD v152; // [rsp+50h] [rbp-B0h]
  DWORD Type[3]; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v154[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v155; // [rsp+70h] [rbp-90h]
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  BYTE v157[8]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v158; // [rsp+88h] [rbp-78h]
  BYTE Data[4]; // [rsp+90h] [rbp-70h] BYREF
  BYTE v160[4]; // [rsp+94h] [rbp-6Ch] BYREF
  DWORD NumberOfBytesSent; // [rsp+98h] [rbp-68h] BYREF
  BYTE v162[4]; // [rsp+9Ch] [rbp-64h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+A0h] [rbp-60h]
  LPVOID lpMem[2]; // [rsp+B0h] [rbp-50h] BYREF
  HANDLE hEvents; // [rsp+C0h] [rbp-40h] BYREF
  size_t Size[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v167; // [rsp+D8h] [rbp-28h]
  int v168[4]; // [rsp+E0h] [rbp-20h] BYREF
  HANDLE v169[2]; // [rsp+F0h] [rbp-10h] BYREF
  struct _WSANETWORKEVENTS NetworkEvents; // [rsp+100h] [rbp+0h] BYREF
  __int64 v171[64]; // [rsp+130h] [rbp+30h] BYREF

  *(_QWORD *)v168 = a8;
  v167 = a7;
  v9 = a3;
  hEvents = a6;
  v151 = a4;
  v11 = 0;
  lpCriticalSection = a3;
  LODWORD(v12) = 0;
  v152 = 0;
  v13 = 0;
  NumberOfBytesSent = 0;
  v155 = 0;
  hKey = HKEY_LOCAL_MACHINE;
  lpMem[0] = 0;
  *(_DWORD *)Data = 0;
  *(_DWORD *)v157 = 0;
  Type[0] = 0;
  cbData = 0;
  *(_DWORD *)v160 = 0;
  *(_DWORD *)v162 = 0;
  *(_OWORD *)Size = 0;
  *(_OWORD *)v169 = 0;
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
  v154[0] = *(_QWORD *)v16;
  if ( a2 && !*(_BYTE *)(v16 + 392) )
  {
    v17 = a2 + 9;
    AcquireSRWLockShared(a2 + 9);
    lpCriticalSection = (LPCRITICAL_SECTION)a2[61].Ptr;
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
    v13 = 0;
  }
  EnterCriticalSection(v9);
  v158 = *a1;
  if ( v158 )
  {
    if ( !*(_DWORD *)&isDhcpFailoverTestEnv )
    {
LABEL_129:
      v59 = *(_DWORD *)(*(_QWORD *)(v151 + 16) + 8LL);
      v148 = v59;
      if ( !v59 )
      {
LABEL_157:
        if ( !v11 )
        {
          v69 = v151;
          v70 = *(_DWORD **)(v151 + 16);
          v71 = *(_QWORD *)v70;
          if ( *(_BYTE *)(*(_QWORD *)v70 + 2LL) == 3 )
          {
            if ( v70[6] )
            {
              v72 = 0;
              do
              {
                v73 = (__int64 *)&a2[4];
                if ( LODWORD(a2[1].Ptr) )
                  v73 = (__int64 *)&a2[3];
                v74 = *v73;
                Ptr = (const size_t *)a2->Ptr;
                v76 = 38LL * v72;
                *(_OWORD *)v154 = SendBndUpdMessage;
                v77 = v70[v76 + 14];
                v78 = FailoverBindingStateDescription[BYTE1(v70[v76 + 15])];
                v79 = ntohl(*(_DWORD *)(v71 + 8));
                LogETWFailoverAuditLogEvent((int)v154, v79, v74, (int)Ptr, v77, (__int64)v78, 0);
                v69 = v151;
                ++v72;
                v70 = *(_DWORD **)(v151 + 16);
              }
              while ( v72 < v70[6] );
              v11 = v152;
            }
            _InterlockedIncrement(&DhcpGlobalFailoverBndUpdSent);
          }
          v80 = *(_DWORD **)(v69 + 16);
          if ( *(_BYTE *)(*(_QWORD *)v80 + 2LL) == 4 )
          {
            v81 = 0;
            v149 = 0;
            if ( v80[6] )
            {
              do
              {
                v82 = 8LL * v81;
                v83 = *(_BYTE **)&v80[v82 + 14];
                if ( v83 )
                {
                  if ( *v83 == 0xFE )
                    v90 = (__int64 *)&unk_1800FD760;
                  else
                    v90 = (__int64 *)&_ImageBase[4 * (unsigned __int8)*v83 + 518992];
                  v91 = (__int64 *)&a2[4];
                  v154[0] = *v90;
                  if ( LODWORD(a2[1].Ptr) )
                    v91 = (__int64 *)&a2[3];
                  v92 = v80[v82 + 12];
                  v93 = *v91;
                  v94 = *(_DWORD *)(v71 + 8);
                  v95.Ptr = a2->Ptr;
                  *(_OWORD *)lpMem = SendBndAckMessageRejectReason;
                  v96 = ntohl(v94);
                  LogETWFailoverBNDUPDAdminEvent((int)lpMem, v96, v93, (int)v95.Ptr, v92, v154[0]);
                  v69 = v151;
                  HeapFree(gDhcpHeap, 0, *(LPVOID *)(v82 * 4 + *(_QWORD *)(v151 + 16) + 56));
                  *(_QWORD *)(v82 * 4 + *(_QWORD *)(v69 + 16) + 56) = 0;
                }
                else
                {
                  v84 = (__int64 *)&a2[4];
                  if ( LODWORD(a2[1].Ptr) )
                    v84 = (__int64 *)&a2[3];
                  v85 = v80[v82 + 12];
                  v86 = *v84;
                  v87 = *(_DWORD *)(v71 + 8);
                  v88.Ptr = a2->Ptr;
                  *(_OWORD *)v154 = SendBndAckMessageNoRejectReason;
                  v89 = ntohl(v87);
                  LogETWFailoverAuditLogEvent((int)v154, v89, v86, (int)v88.Ptr, v85, 0, 0);
                  v69 = v151;
                }
                v80 = *(_DWORD **)(v69 + 16);
                v81 = v149 + 1;
                v149 = v81;
              }
              while ( v81 < v80[6] );
              v11 = v152;
            }
            _InterlockedIncrement(&DhcpGlobalFailoverBndAckSent);
          }
          if ( *(_BYTE *)(**(_QWORD **)(v69 + 16) + 2LL) == 11 )
          {
            v97 = (__int64 *)&a2[4];
            if ( LODWORD(a2[1].Ptr) )
              v97 = (__int64 *)&a2[3];
            v98 = *v97;
            v99 = *(_DWORD *)(v71 + 8);
            v100.Ptr = a2->Ptr;
            *(_OWORD *)v154 = SendContactMessage;
            v101 = ntohl(v99);
            LogETWFailoverAuditLogEvent((int)v154, v101, v98, (int)v100.Ptr, 0, 0, 0);
          }
          if ( *(_BYTE *)(**(_QWORD **)(v69 + 16) + 2LL) == 5 )
          {
            v102 = (__int64 *)&a2[4];
            if ( LODWORD(a2[1].Ptr) )
              v102 = (__int64 *)&a2[3];
            v103 = *v102;
            v104 = *(_DWORD *)(v71 + 8);
            v105.Ptr = a2->Ptr;
            *(_OWORD *)v154 = SendConnectMessage;
            v106 = ntohl(v104);
            LogETWFailoverAuditLogEvent((int)v154, v106, v103, (int)v105.Ptr, 0, 0, 0);
          }
          if ( *(_BYTE *)(**(_QWORD **)(v69 + 16) + 2LL) == 9 )
          {
            v107 = (__int64 *)&a2[4];
            if ( LODWORD(a2[1].Ptr) )
              v107 = (__int64 *)&a2[3];
            v108 = *v107;
            v109 = *(_DWORD *)(v71 + 8);
            v110.Ptr = a2->Ptr;
            *(_OWORD *)v154 = SendUpdReqMessage;
            v111 = ntohl(v109);
            LogETWFailoverAuditLogEvent((int)v154, v111, v108, (int)v110.Ptr, 0, 0, 0);
          }
          if ( *(_BYTE *)(**(_QWORD **)(v69 + 16) + 2LL) == 7 )
          {
            v112 = (__int64 *)&a2[4];
            if ( LODWORD(a2[1].Ptr) )
              v112 = (__int64 *)&a2[3];
            v113 = *v112;
            v114 = *(_DWORD *)(v71 + 8);
            v115.Ptr = a2->Ptr;
            *(_OWORD *)v154 = SendUpdReqAllMessage;
            v116 = ntohl(v114);
            LogETWFailoverAuditLogEvent((int)v154, v116, v113, (int)v115.Ptr, 0, 0, 0);
          }
          if ( *(_BYTE *)(**(_QWORD **)(v69 + 16) + 2LL) == 8 )
          {
            v117 = (__int64 *)&a2[4];
            if ( LODWORD(a2[1].Ptr) )
              v117 = (__int64 *)&a2[3];
            v118 = *v117;
            v119 = *(_DWORD *)(v71 + 8);
            v120.Ptr = a2->Ptr;
            *(_OWORD *)v154 = SendUpdDoneMessage;
            v121 = ntohl(v119);
            LogETWFailoverAuditLogEvent((int)v154, v121, v118, (int)v120.Ptr, 0, 0, 0);
          }
          v122 = *(_QWORD *)(v69 + 16);
          v123 = &Annotation;
          if ( *(_BYTE *)(*(_QWORD *)v122 + 2LL) == 10 )
          {
            memset_0(v171, 0, sizeof(v171));
            v124 = DhcpConvertSystemTime(LODWORD(a2[18].Ptr), v171);
            Ptr_high = (int)a2[7].Ptr;
            if ( v124 )
            {
              if ( Ptr_high == 2 )
                Ptr_high = HIDWORD(a2[7].Ptr);
              v132 = (__int64 *)&a2[4];
              v133 = FailoverRelationStateDescription[Ptr_high];
              if ( LODWORD(a2[1].Ptr) )
                v132 = (__int64 *)&a2[3];
              v134 = *v132;
              v135 = *(_DWORD *)(v71 + 8);
              v136.Ptr = a2->Ptr;
              *(_OWORD *)v154 = SendStateMessage;
              v137 = ntohl(v135);
              LogETWFailoverAuditLogEvent((int)v154, v137, v134, (int)v136.Ptr, 0, (__int64)v133, (__int64)&Annotation);
            }
            else
            {
              if ( Ptr_high == 2 )
                Ptr_high = HIDWORD(a2[7].Ptr);
              v126 = (__int64 *)&a2[4];
              v127 = FailoverRelationStateDescription[Ptr_high];
              if ( LODWORD(a2[1].Ptr) )
                v126 = (__int64 *)&a2[3];
              v128 = *v126;
              v129 = *(_DWORD *)(v71 + 8);
              v130.Ptr = a2->Ptr;
              *(_OWORD *)v154 = SendStateMessage;
              v131 = ntohl(v129);
              LogETWFailoverAuditLogEvent((int)v154, v131, v128, (int)v130.Ptr, 0, (__int64)v127, (__int64)v171);
            }
          }
          v138 = *(unsigned __int8 **)(v151 + 16);
          if ( *(_BYTE *)(*(_QWORD *)v138 + 2LL) == 6 )
          {
            v139 = v138[392];
            if ( (_BYTE)v139 )
            {
              if ( (_BYTE)v139 == 0xFE )
                v140 = (__int64 *)&unk_1800FD760;
              else
                v140 = (__int64 *)&_ImageBase[4 * v139 + 518992];
              v141 = *v140;
              v142 = &Annotation;
              v143 = *(_DWORD *)(v71 + 8);
              if ( v167 )
                LODWORD(v142) = v167;
              *(_OWORD *)v154 = SendConnectAckMessageRejectReason;
              if ( *(_QWORD *)v168 )
                LODWORD(v123) = v168[0];
              v144 = ntohl(v143);
              LogETWFailoverAuditLogEvent((int)v154, v144, (int)v123, (int)v142, 0, v141, 0);
            }
            else
            {
              if ( a2 )
              {
                v123 = (const size_t *)a2->Ptr;
                if ( LODWORD(a2[1].Ptr) )
                  v145 = (const size_t *)a2[3].Ptr;
                else
                  v145 = (const size_t *)a2[4].Ptr;
              }
              else
              {
                v145 = &Annotation;
              }
              v146 = *(_DWORD *)(v71 + 8);
              *(_OWORD *)v168 = SendConnectAckMessage;
              v147 = ntohl(v146);
              LogETWFailoverAuditLogEvent((int)v168, v147, (int)v145, (int)v123, 0, 0, 0);
            }
          }
        }
        goto LABEL_233;
      }
      while ( 1 )
      {
        v60 = v155;
        LODWORD(Size[0]) = v59 - v155;
        v61 = HeapAlloc(gDhcpHeap, 8u, v59 - v155);
        if ( !v61 )
          break;
        memcpy_0(v61, (const void *)(**(_QWORD **)(v151 + 16) + v60), LODWORD(Size[0]));
        Size[1] = (size_t)v61;
        v11 = WSASend(*(_QWORD *)(v158 + 8), (LPWSABUF)Size, 1u, &NumberOfBytesSent, 0, 0, 0);
        v152 = v11;
        v155 += NumberOfBytesSent;
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
            goto LABEL_173;
          if ( a5 )
          {
            v63 = WSAWaitForMultipleEvents(1u, &hEvents, 0, 0xFFFFFFFF, 0);
            v152 = v63;
            v11 = v63;
            if ( v63 == -1 || v63 == 258 )
              goto LABEL_173;
            WSAEnumNetworkEvents(*(_QWORD *)(v158 + 8), hEvents, &NetworkEvents);
            if ( (NetworkEvents.lNetworkEvents & 2) != 0 )
            {
              v64 = (unsigned int)NetworkEvents.iErrorCode[1];
              if ( NetworkEvents.iErrorCode[1] )
              {
                v11 = NetworkEvents.iErrorCode[1];
                v65 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
                {
                  v66 = 39;
                  goto LABEL_144;
                }
                goto LABEL_173;
              }
            }
            else if ( (NetworkEvents.lNetworkEvents & 0x20) != 0 )
            {
              v11 = NetworkEvents.iErrorCode[5];
              if ( NetworkEvents.iErrorCode[5] )
              {
                v65 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
                {
                  v66 = 40;
                  v64 = (unsigned int)NetworkEvents.iErrorCode[5];
LABEL_144:
                  WPP_SF_D(v65[2], v66, &WPP_5bd49953df5f3f59743b495ddca40749_Traceguids, v64);
                }
              }
              else
              {
                v11 = 10057;
              }
LABEL_173:
              HeapFree(gDhcpHeap, 0, v61);
              goto LABEL_233;
            }
          }
          else
          {
            v169[0] = *(HANDLE *)(v158 + 40);
            v169[1] = *(HANDLE *)(v158 + 48);
            v152 = WSAWaitForMultipleEvents(2u, v169, 0, 0xFFFFFFFF, 0);
            v11 = v152;
            if ( v152 )
              goto LABEL_173;
            if ( !WSAResetEvent(*(HANDLE *)(v158 + 40)) )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
              {
                v67 = *((_QWORD *)WPP_GLOBAL_Control + 2);
                v68 = WSAGetLastError();
                WPP_SF_D(v67, v11 + 41, &WPP_5bd49953df5f3f59743b495ddca40749_Traceguids, v68);
              }
              v59 = v148;
            }
          }
        }
        HeapFree(gDhcpHeap, 0, v61);
        if ( v155 == v59 )
          goto LABEL_157;
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
      goto LABEL_233;
    }
    v23 = RegQueryValueExW(hKey, L"DhcpHATestHookRelName", 0, Type, 0, &cbData);
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
      lpMem[0] = v26;
      if ( !v26 )
      {
        v19 = 1214;
LABEL_37:
        v20 = "DhcpAllocateMemory";
        v11 = 8;
        v21 = 8;
        goto LABEL_23;
      }
      v23 = RegQueryValueExW(hKey, L"DhcpHATestHookRelName", 0, Type, (LPBYTE)v26, &cbData);
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
    v27 = RegQueryValueExW(hKey, L"DhcpHATestHookPacketType", 0, Type, Data, &cbData);
    if ( v27
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_5bd49953df5f3f59743b495ddca40749_Traceguids, v27);
    }
    cbData = 4;
    v28 = RegQueryValueExW(hKey, L"DhcpHATestHookTimeOut", 0, Type, v157, &cbData);
    v152 = v28;
    v11 = v28;
    if ( v28
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_5bd49953df5f3f59743b495ddca40749_Traceguids, v28);
    }
    if ( lpMem[0] )
    {
      v29 = *(__int64 **)(v158 + 56);
      if ( v29 )
      {
        v30 = (unsigned __int16 *)lpMem[0];
        if ( *(_WORD *)lpMem[0] )
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
    v36 = *(__int64 **)(v158 + 56);
    if ( v36 )
      v12 = *v36;
    if ( v13 != 1 )
      goto LABEL_127;
    v37 = *(unsigned __int8 *)(v154[0] + 2);
    v38 = dword_1800E9F44[v37];
    if ( v38 != (*(_DWORD *)Data & v38) )
      goto LABEL_127;
    if ( (unsigned __int8)v37 > 8u )
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
    else if ( (_BYTE)v37 == 8 )
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
                  *(_DWORD *)(*(_QWORD *)(v151 + 16) + 8LL),
                  **(_QWORD **)(v151 + 16));
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
      v50 = v158;
      v51 = v49;
      while ( 1 )
      {
        cbData = 4;
        v52 = RegQueryValueExW(hKey, **(LPCWSTR **)(v50 + 56), 0, Type, v160, &cbData);
        if ( (v52 & 0xFFFFFFFD) != 0 )
          break;
        if ( *(_DWORD *)v160 != 1 )
        {
          v53 = time(0);
          if ( (unsigned int)(v53 - v51) <= *(_DWORD *)v157 )
          {
            *(_DWORD *)v157 += v51 - v53;
            if ( !WaitForSingleObject(v47, 1000 * *(_DWORD *)v157) )
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
      v48 = RegSetValueExW(hKey, **(LPCWSTR **)(v50 + 56), 0, 4u, v162, 4u);
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
      v56 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v57 = WSAGetLastError();
      WPP_SF_D(v56, 37, &WPP_5bd49953df5f3f59743b495ddca40749_Traceguids, v57);
    }
    v58 = RegCloseKey(hKey);
    v152 = v58;
    v11 = v58;
    if ( v58 )
      DhcpPrintFOErrorEx(v58, "DhcpCMSendFailoverMessage", "RegCloseKey", 1354);
LABEL_127:
    if ( lpMem[0] )
      HeapFree(gDhcpHeap, 0, lpMem[0]);
    goto LABEL_129;
  }
LABEL_233:
  LeaveCriticalSection(lpCriticalSection);
  return v11;
}

```

## disassembly

```asm
0x1800b2a80  push    rbp
0x1800b2a82  push    rbx
0x1800b2a83  push    rsi
0x1800b2a84  push    rdi
0x1800b2a85  push    r12
0x1800b2a87  push    r13
0x1800b2a89  push    r14
0x1800b2a8b  push    r15
0x1800b2a8d  lea     rbp, [rsp-248h]
0x1800b2a95  sub     rsp, 348h
0x1800b2a9c  mov     rax, cs:__security_cookie
0x1800b2aa3  xor     rax, rsp
0x1800b2aa6  mov     [rbp+280h+var_50], rax
0x1800b2aad  mov     rax, [rbp+280h+arg_38]
0x1800b2ab4  xor     esi, esi
0x1800b2ab6  xorps   xmm0, xmm0
0x1800b2ab9  mov     qword ptr [rbp+280h+var_2A0], rax
0x1800b2abd  mov     rax, [rbp+280h+arg_30]
0x1800b2ac4  mov     rdi, rcx
0x1800b2ac7  xor     ecx, ecx
0x1800b2ac9  mov     [rbp+280h+var_2A8], rax
0x1800b2acd  mov     rax, [rbp+280h+arg_28]
0x1800b2ad4  mov     r10, r8
0x1800b2ad7  mov     [rbp+280h+hEvents], rax
0x1800b2adb  mov     r15, rdx
0x1800b2ade  mov     [rsp+380h+var_338], r9
0x1800b2ae3  mov     r12d, esi
0x1800b2ae6  mov     [rbp+280h+lpCriticalSection], r8
0x1800b2aea  mov     r13d, esi
0x1800b2aed  mov     [rsp+380h+var_330], esi
0x1800b2af1  mov     ebx, esi
0x1800b2af3  mov     [rbp+280h+NumberOfBytesSent], esi
0x1800b2af6  mov     [rsp+380h+var_310], esi
0x1800b2afa  mov     [rsp+380h+hKey], 0FFFFFFFF80000002h
0x1800b2b03  mov     qword ptr [rbp+280h+NetworkEvents.iErrorCode+1Ch], rcx
0x1800b2b07  mov     [rbp+280h+NetworkEvents.iErrorCode+24h], ecx
0x1800b2b0a  mov     [rbp+280h+lpMem], rsi
0x1800b2b0e  mov     dword ptr [rbp+280h+Data], esi
0x1800b2b11  mov     dword ptr [rbp+280h+var_300], esi
0x1800b2b14  mov     [rsp+380h+Type], esi
0x1800b2b18  mov     [rsp+380h+cbData], esi
0x1800b2b1c  mov     dword ptr [rbp+280h+var_2EC], esi
0x1800b2b1f  mov     dword ptr [rbp+280h+var_2E4], esi
0x1800b2b22  movups  xmmword ptr [rbp+280h+Size], xmm0
0x1800b2b26  movups  xmmword ptr [rbp+280h+var_290], xmm0
0x1800b2b2a  movups  xmmword ptr [rbp+280h+NetworkEvents.lNetworkEvents], xmm0
0x1800b2b2e  movups  xmmword ptr [rbp+280h+NetworkEvents.iErrorCode+0Ch], xmm0
0x1800b2b32  test    rdi, rdi
0x1800b2b35  jnz     short loc_1800B2B65
0x1800b2b37  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b2b3e  lea     rsi, WPP_GLOBAL_Control
0x1800b2b45  cmp     rcx, rsi
0x1800b2b48  jz      loc_1800B2D05
0x1800b2b4e  mov     edi, 800000h
0x1800b2b53  test    [rcx+1Ch], edi
0x1800b2b56  jz      loc_1800B2D05
0x1800b2b5c  lea     edx, [r13+19h]
0x1800b2b60  jmp     loc_1800B2CEF
0x1800b2b65  cmp     [rbp+280h+arg_20], esi
0x1800b2b6b  jz      short loc_1800B2B9F
0x1800b2b6d  test    rax, rax
0x1800b2b70  jnz     short loc_1800B2B9F
0x1800b2b72  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b2b79  lea     rsi, WPP_GLOBAL_Control
0x1800b2b80  cmp     rcx, rsi
0x1800b2b83  jz      loc_1800B2D05
0x1800b2b89  mov     edi, 800000h
0x1800b2b8e  test    [rcx+1Ch], edi
0x1800b2b91  jz      loc_1800B2D05
0x1800b2b97  lea     edx, [rax+1Ah]
0x1800b2b9a  jmp     loc_1800B2CEF
0x1800b2b9f  test    r15, r15
0x1800b2ba2  jnz     short loc_1800B2BD7
0x1800b2ba4  test    r8, r8
0x1800b2ba7  jnz     short loc_1800B2BD7
0x1800b2ba9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b2bb0  lea     rsi, WPP_GLOBAL_Control
0x1800b2bb7  cmp     rcx, rsi
0x1800b2bba  jz      loc_1800B2D05
0x1800b2bc0  mov     edi, 800000h
0x1800b2bc5  test    [rcx+1Ch], edi
0x1800b2bc8  jz      loc_1800B2D05
0x1800b2bce  lea     edx, [r15+1Bh]
0x1800b2bd2  jmp     loc_1800B2CEF
0x1800b2bd7  mov     rax, [r9+10h]
0x1800b2bdb  mov     rcx, [rax]
0x1800b2bde  mov     [rsp+380h+var_320], rcx
0x1800b2be3  test    r15, r15
0x1800b2be6  jz      short loc_1800B2C2D
0x1800b2be8  cmp     [rax+188h], sil
0x1800b2bef  jnz     short loc_1800B2C2D
0x1800b2bf1  lea     rbx, [rdx+48h]
0x1800b2bf5  mov     rcx, rbx; SRWLock
0x1800b2bf8  call    cs:__imp_AcquireSRWLockShared
0x1800b2bff  nop     dword ptr [rax+rax+00h]
0x1800b2c04  mov     rax, [r15+1E8h]
0x1800b2c0b  mov     rcx, rbx; SRWLock
0x1800b2c0e  mov     [rbp+280h+lpCriticalSection], rax
0x1800b2c12  test    rax, rax
0x1800b2c15  jz      loc_1800B2CC1
0x1800b2c1b  call    cs:__imp_ReleaseSRWLockShared
0x1800b2c22  nop     dword ptr [rax+rax+00h]
0x1800b2c27  mov     r10, [rbp+280h+lpCriticalSection]
0x1800b2c2b  mov     ebx, esi
0x1800b2c2d  mov     rcx, r10; lpCriticalSection
0x1800b2c30  call    cs:__imp_EnterCriticalSection
0x1800b2c37  nop     dword ptr [rax+rax+00h]
0x1800b2c3c  mov     rax, [rdi]
0x1800b2c3f  mov     [rbp+280h+var_2F8], rax
0x1800b2c43  test    rax, rax
0x1800b2c46  jz      loc_1800B3BA1
0x1800b2c4c  xor     eax, eax
0x1800b2c4e  lea     rsi, WPP_GLOBAL_Control
0x1800b2c55  cmp     cs:isDhcpFailoverTestEnv, eax
0x1800b2c5b  lea     r14, WPP_5bd49953df5f3f59743b495ddca40749_Traceguids
0x1800b2c62  mov     edi, 800000h
0x1800b2c67  jz      loc_1800B32DF
0x1800b2c6d  lea     rax, [rsp+380h+hKey]
0x1800b2c72  mov     r9d, 1Fh; samDesired
0x1800b2c78  xor     r8d, r8d; ulOptions
0x1800b2c7b  mov     [rsp+380h+phkResult], rax; phkResult
0x1800b2c80  lea     rdx, aSystemCurrentc_4; "SYSTEM\\CurrentControlSet\\Services\\DH"...
0x1800b2c87  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800b2c8e  call    cs:__imp_RegOpenKeyExW
0x1800b2c95  nop     dword ptr [rax+rax+00h]
0x1800b2c9a  mov     r12d, eax
0x1800b2c9d  test    eax, eax
0x1800b2c9f  jz      short loc_1800B2D0F
0x1800b2ca1  mov     r9d, 4ACh
0x1800b2ca7  lea     r8, aRegopenkeyexw; "RegOpenKeyExW"
0x1800b2cae  mov     ecx, eax
0x1800b2cb0  lea     rdx, aDhcpcmsendfail; "DhcpCMSendFailoverMessage"
0x1800b2cb7  call    DhcpPrintFOErrorEx
0x1800b2cbc  jmp     loc_1800B3BA1
0x1800b2cc1  call    cs:__imp_ReleaseSRWLockShared
0x1800b2cc8  nop     dword ptr [rax+rax+00h]
0x1800b2ccd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b2cd4  lea     rsi, WPP_GLOBAL_Control
0x1800b2cdb  cmp     rcx, rsi
0x1800b2cde  jz      short loc_1800B2D05
0x1800b2ce0  mov     edi, 800000h
0x1800b2ce5  test    [rcx+1Ch], edi
0x1800b2ce8  jz      short loc_1800B2D05
0x1800b2cea  mov     edx, 1Ch
0x1800b2cef  mov     rcx, [rcx+10h]
0x1800b2cf3  lea     r8, WPP_5bd49953df5f3f59743b495ddca40749_Traceguids
0x1800b2cfa  mov     r9d, 57h ; 'W'
0x1800b2d00  call    WPP_SF_D
0x1800b2d05  mov     eax, 57h ; 'W'
0x1800b2d0a  jmp     loc_1800B3BB4
0x1800b2d0f  mov     rcx, [rsp+380h+hKey]; hKey
0x1800b2d14  lea     rax, [rsp+380h+cbData]
0x1800b2d19  mov     [rsp+380h+lpcbData], rax; lpcbData
0x1800b2d1e  lea     r9, [rsp+380h+Type]; lpType
0x1800b2d23  xor     r12d, r12d
0x1800b2d26  lea     rdx, aDhcphatesthook; "DhcpHATestHookRelName"
0x1800b2d2d  xor     r8d, r8d; lpReserved
0x1800b2d30  mov     [rsp+380h+phkResult], r12; lpData
0x1800b2d35  call    cs:__imp_RegQueryValueExW
0x1800b2d3c  nop     dword ptr [rax+rax+00h]
0x1800b2d41  cmp     eax, 2
0x1800b2d44  jnz     short loc_1800B2D4E
0x1800b2d46  lea     ebx, [rax-1]
0x1800b2d49  jmp     loc_1800B2E12
0x1800b2d4e  test    eax, eax
0x1800b2d50  jz      short loc_1800B2D75
0x1800b2d52  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b2d59  cmp     rcx, rsi
0x1800b2d5c  jz      loc_1800B2E12
0x1800b2d62  test    [rcx+1Ch], edi
0x1800b2d65  jz      loc_1800B2E12
0x1800b2d6b  mov     edx, 1Dh
0x1800b2d70  jmp     loc_1800B2E03
0x1800b2d75  mov     r8d, [rsp+380h+cbData]
0x1800b2d7a  mov     edx, 8; dwFlags
0x1800b2d7f  mov     rcx, cs:gDhcpHeap; hHeap
0x1800b2d86  add     r8, r8; dwBytes
0x1800b2d89  call    cs:__imp_HeapAlloc
0x1800b2d90  nop     dword ptr [rax+rax+00h]
0x1800b2d95  mov     [rbp+280h+lpMem], rax
0x1800b2d99  test    rax, rax
0x1800b2d9c  jnz     short loc_1800B2DBA
0x1800b2d9e  mov     r9d, 4BEh
0x1800b2da4  mov     eax, 8
0x1800b2da9  lea     r8, aDhcpallocateme; "DhcpAllocateMemory"
0x1800b2db0  mov     r12d, eax
0x1800b2db3  mov     ecx, eax
0x1800b2db5  jmp     loc_1800B2CB0
0x1800b2dba  lea     rcx, [rsp+380h+cbData]
0x1800b2dbf  xor     r8d, r8d; lpReserved
0x1800b2dc2  mov     [rsp+380h+lpcbData], rcx; lpcbData
0x1800b2dc7  lea     r9, [rsp+380h+Type]; lpType
0x1800b2dcc  mov     rcx, [rsp+380h+hKey]; hKey
0x1800b2dd1  lea     rdx, aDhcphatesthook; "DhcpHATestHookRelName"
0x1800b2dd8  mov     [rsp+380h+phkResult], rax; lpData
0x1800b2ddd  call    cs:__imp_RegQueryValueExW
0x1800b2de4  nop     dword ptr [rax+rax+00h]
0x1800b2de9  test    eax, eax
0x1800b2deb  jz      short loc_1800B2E12
0x1800b2ded  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b2df4  cmp     rcx, rsi
0x1800b2df7  jz      short loc_1800B2E12
0x1800b2df9  test    [rcx+1Ch], edi
0x1800b2dfc  jz      short loc_1800B2E12
0x1800b2dfe  mov     edx, 1Eh
0x1800b2e03  mov     rcx, [rcx+10h]
0x1800b2e07  mov     r9d, eax
0x1800b2e0a  mov     r8, r14
0x1800b2e0d  call    WPP_SF_D
0x1800b2e12  mov     rcx, [rsp+380h+hKey]; hKey
0x1800b2e17  lea     rax, [rsp+380h+cbData]
0x1800b2e1c  mov     [rsp+380h+lpcbData], rax; lpcbData
0x1800b2e21  lea     r9, [rsp+380h+Type]; lpType
0x1800b2e26  lea     rax, [rbp+280h+Data]
0x1800b2e2a  mov     [rsp+380h+cbData], 4
0x1800b2e32  xor     r8d, r8d; lpReserved
0x1800b2e35  mov     [rsp+380h+phkResult], rax; lpData
0x1800b2e3a  lea     rdx, aDhcphatesthook_0; "DhcpHATestHookPacketType"
0x1800b2e41  call    cs:__imp_RegQueryValueExW
0x1800b2e48  nop     dword ptr [rax+rax+00h]
0x1800b2e4d  test    eax, eax
0x1800b2e4f  jz      short loc_1800B2E76
0x1800b2e51  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b2e58  cmp     rcx, rsi
0x1800b2e5b  jz      short loc_1800B2E76
0x1800b2e5d  test    [rcx+1Ch], edi
0x1800b2e60  jz      short loc_1800B2E76
0x1800b2e62  mov     rcx, [rcx+10h]
0x1800b2e66  mov     edx, 1Fh
0x1800b2e6b  mov     r9d, eax
0x1800b2e6e  mov     r8, r14
0x1800b2e71  call    WPP_SF_D
0x1800b2e76  mov     rcx, [rsp+380h+hKey]; hKey
0x1800b2e7b  lea     rax, [rsp+380h+cbData]
0x1800b2e80  mov     [rsp+380h+lpcbData], rax; lpcbData
0x1800b2e85  lea     r9, [rsp+380h+Type]; lpType
0x1800b2e8a  lea     rax, [rbp+280h+var_300]
0x1800b2e8e  mov     [rsp+380h+cbData], 4
0x1800b2e96  xor     r8d, r8d; lpReserved
0x1800b2e99  mov     [rsp+380h+phkResult], rax; lpData
0x1800b2e9e  lea     rdx, aDhcphatesthook_1; "DhcpHATestHookTimeOut"
0x1800b2ea5  call    cs:__imp_RegQueryValueExW
0x1800b2eac  nop     dword ptr [rax+rax+00h]
0x1800b2eb1  xor     r8d, r8d
0x1800b2eb4  mov     [rsp+380h+var_330], eax
0x1800b2eb8  mov     r12d, eax
0x1800b2ebb  test    eax, eax
0x1800b2ebd  jz      short loc_1800B2EE6
0x1800b2ebf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b2ec6  cmp     rcx, rsi
0x1800b2ec9  jz      short loc_1800B2EE6
0x1800b2ecb  test    [rcx+1Ch], edi
0x1800b2ece  jz      short loc_1800B2EE6
0x1800b2ed0  mov     rcx, [rcx+10h]
0x1800b2ed4  lea     edx, [r8+20h]
0x1800b2ed8  mov     r8, r14
0x1800b2edb  mov     r9d, eax
0x1800b2ede  call    WPP_SF_D
0x1800b2ee3  xor     r8d, r8d
0x1800b2ee6  mov     rcx, [rbp+280h+lpMem]
0x1800b2eea  mov     r11, [rbp+280h+var_2F8]
0x1800b2eee  test    rcx, rcx
0x1800b2ef1  jz      short loc_1800B2F4D
0x1800b2ef3  mov     rax, [r11+38h]
0x1800b2ef7  test    rax, rax
0x1800b2efa  jz      short loc_1800B2F4D
0x1800b2efc  mov     r9, rcx
0x1800b2eff  cmp     r8w, [rcx]
0x1800b2f03  jz      short loc_1800B2F4D
0x1800b2f05  mov     r10, [rax]
0x1800b2f08  mov     r8, r10
0x1800b2f0b  mov     rax, r9
0x1800b2f0e  sub     r8, r9
0x1800b2f11  movzx   edx, word ptr [rax]
0x1800b2f14  movzx   ecx, word ptr [rax+r8]
0x1800b2f19  sub     edx, ecx
0x1800b2f1b  jnz     short loc_1800B2F25
0x1800b2f1d  add     rax, 2
0x1800b2f21  test    ecx, ecx
0x1800b2f23  jnz     short loc_1800B2F11
0x1800b2f25  xor     r8d, r8d
0x1800b2f28  test    edx, edx
0x1800b2f2a  jz      short loc_1800B2F48
0x1800b2f2c  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800b2f30  inc     rax
0x1800b2f33  cmp     [r9+rax*2], r8w
0x1800b2f38  jnz     short loc_1800B2F30
0x1800b2f3a  inc     eax
0x1800b2f3c  lea     r9, [r9+rax*2]
0x1800b2f40  cmp     r8w, [r9]
0x1800b2f44  jnz     short loc_1800B2F08
0x1800b2f46  jmp     short loc_1800B2F4D
0x1800b2f48  mov     ebx, 1
0x1800b2f4d  mov     rax, [r11+38h]
0x1800b2f51  test    rax, rax
0x1800b2f54  jz      short loc_1800B2F59
0x1800b2f56  mov     r13, [rax]
0x1800b2f59  cmp     ebx, 1
0x1800b2f5c  jnz     loc_1800B32C1
0x1800b2f62  mov     rax, [rsp+380h+var_320]
  ... truncated ...
```
