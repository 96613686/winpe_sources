# MDns_HandlePacketUDP

- ea: `0x18000ddc0`
- end: `0x18000eb31`
- name: `MDns_HandlePacketUDP`
- size: `3441`
- prototype: ``
- caller_count: `1`
- callee_count: `30`
- tags: `file_ops, service_task`

## callers

- `0x18000f930`

## callees

- `0x18000b430`
- `0x18000cc80`
- `0x18000ddc0`
- `0x18000eb40`
- `0x18000f390`
- `0x18001030c`
- `0x180015760`
- `0x180015f3c`
- `0x18001af2c`
- `0x18001af4c`
- `0x18001b584`
- `0x18001bb00`
- `0x18001d6cc`
- `0x180030d68`
- `0x180033ad0`
- `0x18003aa8c`
- `0x18003e1d4`
- `0x180046a64`
- `0x180046a70`
- `0x180046ec0`
- `0x180047818`
- `0x18004b858`
- `0x18007f3c0`
- `0x180085fb8`
- `0x180086010`
- `0x180086384`
- `0x180086b1c`
- `0x180086e44`
- `0x180087dd0`
- `0x18008841c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18000e05f`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18000e565`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18000e58e`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18000e9ee`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18000e05f`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18000e565`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18000e58e`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18000e9ee`
- `DNSAPI!DnsRecordCopyEx` at `0x18000e09f`
- `DNSAPI!DnsRecordCopyEx` at `0x18000e09f`
- `DNSAPI!NetInfo_Free` at `0x18000e28a`
- `DNSAPI!NetInfo_Free` at `0x18000e28a`
- `DNSAPI!DnsFree` at `0x18000e6bc`
- `DNSAPI!DnsFree` at `0x18000e6bc`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000de70`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000de70`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e295`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e295`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000deb2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e1d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e39e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ea4b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000deb2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e1d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e39e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ea4b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000de99`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dfae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000de99`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dfae`

## pseudocode

```c
void __fastcall MDns_HandlePacketUDP(struct _McastSocketContext *a1)
{
  struct _DnsRecordW *appended; // r13
  char *v3; // r12
  struct _DnsNetInfo **v4; // r15
  unsigned int v5; // eax
  unsigned int v6; // ebx
  struct QueryTable *v7; // rdx
  int v8; // r8d
  int v9; // r9d
  __int64 v10; // rcx
  int v11; // r14d
  unsigned int j; // edi
  __int64 v13; // rsi
  __int64 v14; // rax
  unsigned int v15; // r8d
  int v16; // r14d
  struct _DnsNetInfo *v17; // rbx
  const WCHAR *v18; // rsi
  __int64 v19; // rdx
  MDnsTree *v20; // r15
  struct MDnsTree *v21; // rdi
  wchar_t *v22; // r9
  __int64 v23; // rcx
  const WCHAR *v24; // rdx
  __int64 v25; // r8
  wchar_t *v26; // rcx
  __int64 v27; // rbx
  wchar_t *v28; // rax
  DNS_RECORDA *v29; // rcx
  PDNS_RECORD v30; // rax
  unsigned int v31; // edi
  LPCWCH v32; // r14
  struct MDnsTree *v33; // r15
  wchar_t *v34; // r9
  __int64 v35; // rcx
  _WORD *v36; // rdx
  __int64 v37; // r8
  wchar_t *v38; // rcx
  __int64 v39; // rbx
  __int64 v40; // rdi
  MDnsTree *v41; // rsi
  int v42; // ecx
  unsigned int i; // edi
  __int64 v44; // rbx
  __int64 v45; // rcx
  __int64 v46; // rcx
  __int16 v47; // r9
  unsigned int v48; // eax
  int Table; // eax
  __int64 v50; // rcx
  _QWORD *v51; // r14
  struct MDnsTree *NodeUp; // rax
  struct _DnsRecordW *pNext; // rcx
  struct _DnsRecordW *v54; // r8
  struct _DnsRecordW *v55; // rcx
  _QWORD *k; // rdx
  unsigned int LocalAandAAAARecords; // eax
  __int64 v58; // rbx
  wchar_t *v59; // rax
  unsigned __int16 *v60; // rdi
  __int64 v61; // rsi
  unsigned __int64 v62; // r9
  __int64 v63; // rdx
  unsigned __int16 *v64; // r8
  unsigned __int16 *v65; // r10
  __int64 v66; // r11
  unsigned __int16 *v67; // rcx
  int v68; // ecx
  __int64 v69; // rax
  MDnsTree *v70; // rcx
  unsigned int v71; // edx
  struct _DnsNetInfo *v72; // rcx
  unsigned int v73; // ebx
  unsigned int v74; // eax
  int v75; // eax
  __int64 PtrTypeRecord; // rax
  struct MDnsTree *Node; // rax
  int v78; // eax
  __int64 v79; // r8
  unsigned __int16 *v80; // rdi
  __int64 v81; // rsi
  unsigned __int64 v82; // rdx
  __int64 v83; // r8
  unsigned __int16 *v84; // r9
  unsigned __int16 *v85; // r10
  __int64 v86; // r11
  unsigned __int16 *v87; // rcx
  int v88; // ecx
  __int64 v89; // rax
  unsigned int v90; // r8d
  __int64 v91; // rdx
  unsigned int v92; // [rsp+20h] [rbp-E0h]
  unsigned int v93; // [rsp+40h] [rbp-C0h] BYREF
  int v94; // [rsp+44h] [rbp-BCh]
  unsigned int v95; // [rsp+48h] [rbp-B8h]
  MDnsTree *v96[2]; // [rsp+50h] [rbp-B0h] BYREF
  LPCWCH lpWideCharStr; // [rsp+60h] [rbp-A0h]
  struct _DnsRecordW *v98; // [rsp+68h] [rbp-98h] BYREF
  __int64 v99; // [rsp+70h] [rbp-90h]
  wchar_t *Context; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v101[26]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t String[256]; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int16 v103[256]; // [rsp+350h] [rbp+250h] BYREF
  unsigned __int16 v104[256]; // [rsp+550h] [rbp+450h] BYREF

  appended = 0;
  v93 = 0;
  if ( a1 )
  {
    v46 = *((_QWORD *)a1 + 13);
    if ( v46 )
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      {
        v96[1] = 0;
        v96[0] = (MDnsTree *)(v46 + 700);
        if ( v46 == -700 )
          LOWORD(v96[1]) = 0;
        else
          LOWORD(v96[1]) = *(_WORD *)(v46 + 698);
        WPP_SF__COUNTEDSTRING_(v46, 22, WPP_81ad3f7966903d2125d0884c7a4f315d_Traceguids, v96);
      }
    }
  }
  v3 = (char *)operator new(0x78u);
  if ( v3 )
  {
    *((_QWORD *)v3 + 1) = 0;
    *((_OWORD *)v3 + 5) = 0;
    v4 = (struct _DnsNetInfo **)(v3 + 72);
    *((_OWORD *)v3 + 6) = 0;
    *((_QWORD *)v3 + 14) = 0;
    *(_QWORD *)v3 = 0;
    *((_QWORD *)v3 + 2) = 0;
    *((_QWORD *)v3 + 3) = 0;
    *((_QWORD *)v3 + 4) = 0;
    *((_QWORD *)v3 + 5) = 0;
    *((_QWORD *)v3 + 6) = 0;
    *((_QWORD *)v3 + 7) = 0;
    *((_QWORD *)v3 + 8) = 0;
    *((_QWORD *)v3 + 9) = 0;
    InitializeCriticalSection((LPCRITICAL_SECTION)v3 + 2);
    v5 = MDnsLookupInfo::Initialize((MDnsLookupInfo *)v3, a1);
    if ( v5 )
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        WPP_SF_d(1035, 23, WPP_81ad3f7966903d2125d0884c7a4f315d_Traceguids, v5);
      goto LABEL_67;
    }
    v6 = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)v3 + 2);
    if ( *v4 )
      goto LABEL_5;
    if ( g_fVelocityNetinfoCleanup )
    {
      v48 = GrabNetworkInfo(0, (__int64 *)v3 + 9, 0);
      v6 = v48;
      if ( !v48 )
        goto LABEL_87;
      if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      {
LABEL_207:
        LeaveCriticalSection((LPCRITICAL_SECTION)v3 + 2);
LABEL_88:
        if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
          WPP_SF_d(1035, 24, WPP_81ad3f7966903d2125d0884c7a4f315d_Traceguids, v6);
LABEL_67:
        if ( *((_QWORD *)v3 + 4) )
        {
          for ( i = 0; i < *((_DWORD *)v3 + 6); *(_QWORD *)(v44 + *((_QWORD *)v3 + 4)) = 0 )
          {
            v44 = 8LL * i;
            operator delete(*(void **)(v44 + *((_QWORD *)v3 + 4)));
            ++i;
          }
          operator delete(*((void **)v3 + 4));
        }
        operator delete(*((void **)v3 + 5));
        v45 = *((_QWORD *)v3 + 9);
        *((_QWORD *)v3 + 2) = 0;
        NetInfo_Free(v45);
        DeleteCriticalSection((LPCRITICAL_SECTION)v3 + 2);
        operator delete(v3);
        return;
      }
      v91 = 84;
    }
    else
    {
      v48 = GrabNetworkInfoOld(0, 1, (__int64 *)v3 + 9, 0);
      v6 = v48;
      if ( !v48 )
      {
LABEL_87:
        LeaveCriticalSection((LPCRITICAL_SECTION)v3 + 2);
        goto LABEL_6;
      }
      if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      {
LABEL_5:
        LeaveCriticalSection((LPCRITICAL_SECTION)v3 + 2);
        if ( !v6 )
        {
LABEL_6:
          if ( (unsigned __int8)v3[2] < 0x80u )
          {
            if ( MDnsProbeAnnounceTask::s_fProbeAndAnnounceInProgress
              || MDnsProbeAnnounceTask::s_fProbeInProgress
              || !*((_DWORD *)v3 + 6) )
            {
              goto LABEL_67;
            }
            v10 = *((_QWORD *)v3 + 6);
            v11 = 0;
            v94 = 0;
            Packet_InitializeMsgBuf(*(_QWORD *)(v10 + 104));
            if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
              WPP_SF_d(1035, 27, WPP_81ad3f7966903d2125d0884c7a4f315d_Traceguids, *((unsigned int *)v3 + 6));
            for ( j = 0; ; ++j )
            {
              v95 = j;
              if ( j >= *((_DWORD *)v3 + 6) )
              {
                if ( v11 )
                {
                  v74 = MDnsLookupInfo::SendResponse((MDnsLookupInfo *)v3);
                  if ( v74 )
                  {
                    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
                      WPP_SF_d(1035, 31, WPP_81ad3f7966903d2125d0884c7a4f315d_Traceguids, v74);
                  }
                }
                goto LABEL_67;
              }
              v13 = 8LL * j;
              v99 = v13;
              if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
                WPP_SF_S(
                  1035,
                  28,
                  WPP_81ad3f7966903d2125d0884c7a4f315d_Traceguids,
                  *(_QWORD *)(v13 + *((_QWORD *)v3 + 4)));
              else
                v99 = 8LL * j;
              v14 = *((_QWORD *)v3 + 5);
              v15 = *((_DWORD *)v3 + 15);
              v93 = v15;
              v98 = 0;
              v16 = *(unsigned __int16 *)(v14 + 2LL * j);
              v17 = *v4;
              v18 = *(const WCHAR **)(v13 + *((_QWORD *)v3 + 4));
              lpWideCharStr = v18;
              if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
              {
                WPP_SF_dSd(
                  1035,
                  78,
                  (unsigned int)WPP_81ad3f7966903d2125d0884c7a4f315d_Traceguids,
                  v15,
                  (__int64)v18,
                  v16);
                v15 = v93;
              }
              if ( v17 )
              {
                if ( v16 == 1 )
                {
                  v47 = 2;
                }
                else if ( v16 == 28 )
                {
                  v47 = 23;
                }
                else
                {
                  if ( (_WORD)v16 != 255 )
                    break;
                  v47 = 0;
                }
                LocalAandAAAARecords = MDnsGetLocalAandAAAARecords(v17, v18, v15, v47, v92, &v98);
                if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
                  WPP_SF_d(1035, 79, WPP_81ad3f7966903d2125d0884c7a4f315d_Traceguids, LocalAandAAAARecords);
              }
              if ( v16 != 1 && v16 != 28 )
                break;
LABEL_61:
              if ( g_fVelocityDnsKernelApi )
              {
                appended = (struct _DnsRecordW *)Dns_RecordListAppend_New(appended, v98);
              }
              else if ( v98 )
              {
                if ( appended )
                {
                  pNext = appended->pNext;
                  if ( appended->pNext )
                  {
                    do
                    {
                      v54 = pNext;
                      pNext = pNext->pNext;
                    }
                    while ( pNext );
                  }
                  else
                  {
                    v54 = appended;
                  }
                  v54->pNext = v98;
                }
                else
                {
                  appended = v98;
                }
                goto LABEL_140;
              }
              if ( !appended )
              {
                v11 = v94;
                goto LABEL_65;
              }
LABEL_140:
              if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
                WPP_SF_S(
                  1035,
                  29,
                  WPP_81ad3f7966903d2125d0884c7a4f315d_Traceguids,
                  *(_QWORD *)(v99 + *((_QWORD *)v3 + 4)));
              v71 = *((_DWORD *)v3 + 15);
              v72 = *v4;
              v94 = 1;
              v11 = 1;
              PostProcessRecords(v72, v71, 0, appended);
              v73 = MDnsLookupInfo::WriteQueryResponse((MDnsLookupInfo *)v3, appended);
              DnsFree(appended, DnsFreeRecordList);
              if ( v73 )
              {
                if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
                  WPP_SF_d(1035, 30, WPP_81ad3f7966903d2125d0884c7a4f315d_Traceguids, v73);
                goto LABEL_67;
              }
LABEL_65:
              appended = 0;
            }
            EnterCriticalSection(&g_csMdnsTree);
            v20 = g_MDnsTree;
            v96[0] = g_MDnsTree;
            if ( !g_MDnsTree )
            {
LABEL_60:
              LeaveCriticalSection(&g_csMdnsTree);
              v4 = (struct _DnsNetInfo **)(v3 + 72);
              goto LABEL_61;
            }
            v21 = 0;
            v103[0] = 0;
            if ( !v18 )
              goto LABEL_31;
            Context = 0;
            memset_0(v101, 0, 0xC8u);
            v22 = String;
            String[0] = 0;
            v23 = 2147483646;
            v103[1] = 0;
            v24 = v18;
            v25 = 256;
            do
            {
              if ( !v23 )
                break;
              if ( !*v24 )
                break;
              *v22++ = *v24++;
              --v23;
              --v25;
            }
            while ( v25 );
            v26 = v22 - 1;
            if ( v25 )
              v26 = v22;
            *v26 = 0;
            if ( !v25 )
            {
              appended = 0;
              goto LABEL_40;
            }
            v27 = 0;
            v28 = wcstok_s(String, L".", &Context);
            if ( !v28 )
              goto LABEL_31;
            do
            {
              if ( (unsigned int)v27 >= 0x19 )
                break;
              v101[v27] = v28;
              v27 = (unsigned int)(v27 + 1);
              v28 = wcstok_s(0, L".", &Context);
            }
            while ( v28 );
            if ( (_DWORD)v27 )
            {
              v80 = v103;
              v81 = 1;
              while ( 1 )
              {
                if ( !(_DWORD)v27 )
                {
                  v90 = v93;
                  *v80 = 0;
                  v21 = MDnsTree::InternalLookup(v20, v103, v90);
                  goto LABEL_31;
                }
                v82 = 256 - v81;
                if ( v81 == 256 )
                  break;
                if ( v82 > 0x7FFFFFFF )
                {
                  *v80 = 0;
                  break;
                }
                v83 = 2147483646;
                v84 = (unsigned __int16 *)v101[(unsigned int)(v27 - 1)];
                v85 = v80;
                v86 = 0;
                do
                {
                  if ( !v83 )
                    break;
                  if ( !*v84 )
                    break;
                  *v85++ = *v84++;
                  --v83;
                  ++v86;
                  --v82;
                }
                while ( v82 );
                v87 = v85 - 1;
                if ( v82 )
                  v87 = v85;
                *v87 = 0;
                v88 = -2147024774;
                if ( v82 )
                  v88 = 0;
                v89 = v86 - 1;
                if ( v82 )
                  v89 = v86;
                if ( v88 < 0 )
                  break;
                v80 += v89 + 1;
                v81 += ((2 * v89) >> 1) + 1;
                LODWORD(v27) = v27 - 1;
              }
              appended = 0;
            }
            else
            {
LABEL_31:
              appended = 0;
              if ( v21 )
              {
                v29 = (DNS_RECORDA *)*((_QWORD *)v21 + 2);
                if ( (_WORD)v16 == 255 )
                {
                  if ( !v29 )
                  {
LABEL_74:
                    v40 = 0;
                    if ( (_WORD)v16 != 255 )
                    {
LABEL_57:
                      if ( g_fVelocityDnsKernelApi )
                      {
                        appended = (struct _DnsRecordW *)Dns_RecordListAppend_New(appended, v40);
                      }
                      else if ( v40 )
                      {
                        if ( appended )
                        {
                          v55 = appended->pNext;
                          for ( k = &appended->pNext; v55; v55 = v55->pNext )
                            k = &v55->pNext;
                          *k = v40;
                        }
                        else
                        {
                          appended = (struct _DnsRecordW *)v40;
                        }
                      }
                      j = v95;
                      goto LABEL_60;
                    }
LABEL_41:
                    v31 = v93;
                    v32 = lpWideCharStr;
                    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
                      WPP_SF_SD(
                        1035,
                        16,
                        (unsigned int)WPP_9bfce7e00caf33ebc3e9c882382e7196_Traceguids,
                        (_DWORD)lpWideCharStr,
                        v93);
                    v33 = 0;
                    v104[0] = 0;
                    if ( !v32 )
                      goto LABEL_51;
                    Context = 0;
                    memset_0(v101, 0, 0xC8u);
                    v34 = String;
                    String[0] = 0;
                    v35 = 2147483646;
                    v104[1] = 0;
                    v36 = v32;
                    v37 = 256;
                    do
                    {
                      if ( !v35 )
                        break;
                      if ( !*v36 )
                        break;
                      *v34++ = *v36++;
                      --v35;
                      --v37;
                    }
                    while ( v37 );
                    v38 = v34 - 1;
                    if ( v37 )
                      v38 = v34;
                    *v38 = 0;
                    if ( !v37 )
                      goto LABEL_51;
                    v58 = 0;
                    v59 = wcstok_s(String, L".", &Context);
                    if ( !v59 )
                      goto LABEL_51;
                    do
                    {
                      if ( (unsigned int)v58 >= 0x19 )
                        break;
                      v101[v58] = v59;
                      v58 = (unsigned int)(v58 + 1);
                      v59 = wcstok_s(0, L".", &Context);
                    }
                    while ( v59 );
                    if ( (_DWORD)v58 )
                    {
                      v60 = v104;
                      v61 = 1;
                      while ( 1 )
                      {
                        if ( !(_DWORD)v58 )
                        {
                          v70 = v96[0];
                          *v60 = 0;
                          v31 = v93;
                          v33 = MDnsTree::InternalLookup(v70, v104, v93);
                          goto LABEL_51;
                        }
                        v62 = 256 - v61;
                        if ( v61 == 256 )
                          goto LABEL_52;
                        if ( v62 > 0x7FFFFFFF )
                          break;
                        v63 = 2147483646;
                        v64 = (unsigned __int16 *)v101[(unsigned int)(v58 - 1)];
                        v65 = v60;
                        v66 = 0;
                        do
                        {
                          if ( !v63 )
                            break;
                          if ( !*v64 )
                            break;
                          *v65++ = *v64++;
                          --v63;
                          ++v66;
                          --v62;
                        }
                        while ( v62 );
                        v67 = v65 - 1;
                        if ( v62 )
                          v67 = v65;
                        *v67 = 0;
                        v68 = -2147024774;
                        if ( v62 )
                          v68 = 0;
                        v69 = v66 - 1;
                        if ( v62 )
                          v69 = v66;
                        if ( v68 < 0 )
                          goto LABEL_52;
                        v60 += v69 + 1;
                        v61 += ((2 * v69) >> 1) + 1;
                        LODWORD(v58) = v58 - 1;
                      }
                      *v60 = 0;
                    }
                    else
                    {
LABEL_51:
                      if ( v33 )
                      {
                        v41 = (MDnsTree *)*((_QWORD *)v33 + 5);
                        v51 = 0;
                        if ( !v41 )
                        {
                          v41 = (MDnsTree *)*((_QWORD *)v33 + 4);
                          if ( !v41 )
                          {
                            NodeUp = MDnsTree::NextNodeUp(v33, v33);
                            goto LABEL_112;
                          }
                        }
                        do
                        {
                          NodeUp = (struct MDnsTree *)*((_QWORD *)v41 + 5);
                          if ( !NodeUp )
                            break;
LABEL_112:
                          v41 = NodeUp;
                        }
                        while ( NodeUp );
                        v39 = 0;
                        while ( 1 )
                        {
                          if ( !v41 )
                          {
                            v40 = v39;
                            v39 = 0;
                            goto LABEL_55;
                          }
                          if ( !v31 || (v75 = *((_DWORD *)v41 + 14)) == 0 || v75 == v31 )
                          {
                            v40 = 0;
                            if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
                              WPP_SF_S(1035, 18, WPP_9bfce7e00caf33ebc3e9c882382e7196_Traceguids, *(_QWORD *)v41);
                            if ( *((_QWORD *)v41 + 2) && *((_DWORD *)v41 + 19) )
                            {
                              PtrTypeRecord = Dns_CreatePtrTypeRecord(lpWideCharStr, 4500);
                              if ( !PtrTypeRecord )
                              {
                                LODWORD(v41) = 14;
                                goto LABEL_55;
                              }
                              *(_DWORD *)(PtrTypeRecord + 20) &= 0xFFFFFFED;
                              *(_DWORD *)(PtrTypeRecord + 20) |= 9u;
                              if ( v39 && v51 )
                                *v51 = PtrTypeRecord;
                              else
                                v39 = PtrTypeRecord;
                              v51 = (_QWORD *)PtrTypeRecord;
                            }
                            v31 = v93;
                          }
                          Node = (struct MDnsTree *)*((_QWORD *)v41 + 5);
                          if ( !Node )
                          {
                            Node = (struct MDnsTree *)*((_QWORD *)v41 + 4);
                            if ( !Node )
                              Node = MDnsTree::NextNodeUp(v41, v33);
                          }
                          while ( 1 )
                          {
                            v41 = Node;
                            if ( !Node || !*((_QWORD *)Node + 5) )
                              break;
                            Node = MDnsTree::NextNode(Node, v33);
                          }
                        }
                      }
                    }
LABEL_52:
                    v39 = 0;
                    v40 = 0;
                    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
                      WPP_SF_S(1035, 17, WPP_9bfce7e00caf33ebc3e9c882382e7196_Traceguids, v32);
                    LODWORD(v41) = 1168;
LABEL_55:
                    Dns_RecordFree(v39);
                    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
                      WPP_SF_Dq(
                        v42,
                        19,
                        (unsigned int)WPP_9bfce7e00caf33ebc3e9c882382e7196_Traceguids,
                        (_DWORD)v41,
                        v40);
                    goto LABEL_57;
                  }
                  v30 = (PDNS_RECORD)Dns_RecordListCopyEx(v29, v19, 1);
LABEL_38:
                  if ( v30 )
                  {
                    v30->Flags.DW &= 0xFFFFFFED;
                    v30->Flags.DW |= 9u;
                    v30->pNext = 0;
                    appended = (struct _DnsRecordW *)v30;
                  }
                }
                else
                {
                  while ( v29 )
                  {
                    if ( (_WORD)v16 == v29->wType )
                    {
                      v30 = DnsRecordCopyEx(v29, DnsCharSetUnicode, DnsCharSetUnicode);
                      goto LABEL_38;
                    }
                    v29 = v29->pNext;
                  }
                }
              }
            }
LABEL_40:
            if ( v16 == 12 )
              goto LABEL_41;
            goto LABEL_74;
          }
          if ( MDnsProbeAnnounceTask::s_fProbeInProgress )
          {
            v78 = MDnsLookupInfo::LookupAndRename((MDnsLookupInfo *)v3, (int *)&v93, v8, v9);
            if ( v93 )
              _InterlockedExchange(&MDnsProbeAnnounceTask::s_fProbeConflictDetected, 1);
            if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
              WPP_SF_dDd(v93, v7, v79, *((unsigned int *)v3 + 7), v78, v93);
          }
          if ( *((_DWORD *)v3 + 7) )
          {
            Table = MDnsLookupInfo::AddResponsesToQueryTable((MDnsLookupInfo *)v3, v7);
            if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
              WPP_SF_Dd(v50, 26, WPP_81ad3f7966903d2125d0884c7a4f315d_Traceguids, *((unsigned int *)v3 + 7), Table);
          }
          goto LABEL_67;
        }
        goto LABEL_88;
      }
      v91 = 85;
    }
    WPP_SF_d(1035, v91, WPP_81ad3f7966903d2125d0884c7a4f315d_Traceguids, v48);
    goto LABEL_207;
  }
}

```

## disassembly

```asm
0x18000ddc0  push    rbp
0x18000ddc2  push    rbx
0x18000ddc3  push    r12
0x18000ddc5  push    r13
0x18000ddc7  lea     rbp, [rsp-668h]
0x18000ddcf  sub     rsp, 768h
0x18000ddd6  mov     rax, cs:__security_cookie
0x18000dddd  xor     rax, rsp
0x18000dde0  mov     [rbp+680h+var_30], rax
0x18000dde7  xor     r13d, r13d
0x18000ddea  mov     rbx, rcx
0x18000dded  mov     [rsp+780h+var_740], r13d
0x18000ddf2  test    rcx, rcx
0x18000ddf5  jnz     loc_18000E2E6
0x18000ddfb  mov     ecx, 78h ; 'x'; Size
0x18000de00  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000de05  mov     r12, rax
0x18000de08  test    rax, rax
0x18000de0b  jz      loc_18000E2B0
0x18000de11  xor     eax, eax
0x18000de13  mov     [rsp+780h+arg_10], rdi
0x18000de1b  mov     [r12+8], rax
0x18000de20  lea     rcx, [r12+50h]; lpCriticalSection
0x18000de25  xorps   xmm0, xmm0
0x18000de28  mov     [rsp+780h+var_20], r15
0x18000de30  movups  xmmword ptr [r12+50h], xmm0
0x18000de36  lea     r15, [r12+48h]
0x18000de3b  movups  xmmword ptr [r12+60h], xmm0
0x18000de41  mov     [r12+70h], rax
0x18000de46  mov     [r12], rax
0x18000de4a  mov     [r12+10h], r13
0x18000de4f  mov     [r12+18h], r13
0x18000de54  mov     [r12+20h], r13
0x18000de59  mov     [r12+28h], r13
0x18000de5e  mov     [r12+30h], r13
0x18000de63  mov     [r12+38h], r13
0x18000de68  mov     [r12+40h], r13
0x18000de6d  mov     [r15], r13
0x18000de70  call    cs:__imp_InitializeCriticalSection
0x18000de76  mov     rdx, rbx; struct _McastSocketContext *
0x18000de79  mov     rcx, r12; this
0x18000de7c  call    ?Initialize@MDnsLookupInfo@@QEAAJPEAU_McastSocketContext@@@Z; MDnsLookupInfo::Initialize(_McastSocketContext *)
0x18000de81  test    eax, eax
0x18000de83  jnz     loc_18000E4B6
0x18000de89  lea     rcx, [r12+50h]; lpCriticalSection
0x18000de8e  mov     [rsp+780h+arg_8], rsi
0x18000de96  mov     ebx, r13d
0x18000de99  call    cs:__imp_EnterCriticalSection
0x18000de9f  mov     esi, 1
0x18000dea4  cmp     [r15], rbx
0x18000dea7  jz      loc_18000E374
0x18000dead  lea     rcx, [r12+50h]; lpCriticalSection
0x18000deb2  call    cs:__imp_LeaveCriticalSection
0x18000deb8  test    ebx, ebx
0x18000deba  jnz     loc_18000E3A9
0x18000dec0  cmp     byte ptr [r12+2], 80h
0x18000dec6  jnb     loc_18000E3D4
0x18000decc  cmp     cs:?s_fProbeAndAnnounceInProgress@MDnsProbeAnnounceTask@@0HA, r13d; int MDnsProbeAnnounceTask::s_fProbeAndAnnounceInProgress
0x18000ded3  jnz     loc_18000E21F
0x18000ded9  cmp     cs:?s_fProbeInProgress@MDnsProbeAnnounceTask@@0HA, r13d; int MDnsProbeAnnounceTask::s_fProbeInProgress
0x18000dee0  jnz     loc_18000E21F
0x18000dee6  cmp     [r12+18h], r13d
0x18000deeb  jz      loc_18000E21F
0x18000def1  mov     rcx, [r12+30h]
0x18000def6  mov     [rsp+780h+arg_18], r14
0x18000defe  mov     r14d, r13d
0x18000df01  mov     [rsp+780h+var_73C], r13d
0x18000df06  mov     rcx, [rcx+68h]
0x18000df0a  call    Packet_InitializeMsgBuf
0x18000df0f  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18000df16  jnz     loc_18000E8D3
0x18000df1c  mov     edi, r13d
0x18000df1f  mov     [rsp+780h+var_738], edi
0x18000df23  cmp     edi, [r12+18h]
0x18000df28  jnb     loc_18000E20E
0x18000df2e  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18000df35  mov     ebx, edi
0x18000df37  lea     rsi, ds:0[rbx*8]
0x18000df3f  mov     [rsp+780h+var_710], rsi
0x18000df44  jnz     loc_18000E864
0x18000df4a  mov     [rsp+780h+var_710], rsi
0x18000df4f  mov     rax, [r12+28h]
0x18000df54  mov     r8d, [r12+3Ch]; unsigned int
0x18000df59  mov     [rsp+780h+var_740], r8d
0x18000df5e  mov     [rsp+780h+var_718], 0
0x18000df67  movzx   r14d, word ptr [rax+rbx*2]
0x18000df6c  mov     rax, [r12+20h]
0x18000df71  mov     rbx, [r15]
0x18000df74  mov     rsi, [rsi+rax]
0x18000df78  mov     [rsp+780h+lpWideCharStr], rsi
0x18000df7d  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18000df84  jnz     loc_18000E888
0x18000df8a  test    rbx, rbx
0x18000df8d  jnz     loc_18000E349
0x18000df93  cmp     r14d, 1
0x18000df97  jz      loc_18000E1DB
0x18000df9d  cmp     r14d, 1Ch
0x18000dfa1  jz      loc_18000E1DB
0x18000dfa7  lea     rcx, ?g_csMdnsTree@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000dfae  call    cs:__imp_EnterCriticalSection
0x18000dfb4  mov     r15, cs:?g_MDnsTree@@3PEAVMDnsTree@@EA; MDnsTree * g_MDnsTree
0x18000dfbb  mov     [rsp+780h+var_730], r15
0x18000dfc0  test    r15, r15
0x18000dfc3  jz      loc_18000E1C9
0x18000dfc9  xor     eax, eax
0x18000dfcb  xor     edi, edi
0x18000dfcd  mov     [rbp+680h+var_430], ax
0x18000dfd4  test    rsi, rsi
0x18000dfd7  jz      loc_18000E06E
0x18000dfdd  xor     edx, edx; Val
0x18000dfdf  mov     [rsp+780h+Context], rax
0x18000dfe4  mov     r8d, 0C8h; Size
0x18000dfea  lea     rcx, [rbp+680h+var_700]; void *
0x18000dfee  call    memset_0
0x18000dff3  xor     eax, eax
0x18000dff5  lea     r9, [rbp+680h+String]
0x18000dff9  mov     [rbp+680h+String], ax
0x18000dffd  mov     ecx, 7FFFFFFEh
0x18000e002  mov     [rbp+680h+var_42E], ax
0x18000e009  mov     rdx, rsi
0x18000e00c  mov     r8d, 100h
0x18000e012  test    rcx, rcx
0x18000e015  jz      short loc_18000E034
0x18000e017  movzx   eax, word ptr [rdx]
0x18000e01a  test    ax, ax
0x18000e01d  jz      short loc_18000E034
0x18000e01f  mov     [r9], ax
0x18000e023  add     rdx, 2
0x18000e027  add     r9, 2
0x18000e02b  dec     rcx
0x18000e02e  sub     r8, 1
0x18000e032  jnz     short loc_18000E012
0x18000e034  test    r8, r8
0x18000e037  lea     rcx, [r9-2]
0x18000e03b  cmovnz  rcx, r9
0x18000e03f  xor     eax, eax
0x18000e041  mov     [rcx], ax
0x18000e044  test    r8, r8
0x18000e047  jz      loc_18000E4E1
0x18000e04d  lea     r8, [rsp+780h+Context]; Context
0x18000e052  xor     ebx, ebx
0x18000e054  lea     rdx, pszSrc; "."
0x18000e05b  lea     rcx, [rbp+680h+String]; String
0x18000e05f  call    cs:__imp_wcstok_s
0x18000e065  test    rax, rax
0x18000e068  jnz     loc_18000E9D0
0x18000e06e  xor     r13d, r13d
0x18000e071  test    rdi, rdi
0x18000e074  jz      short loc_18000E0CE
0x18000e076  mov     rcx, [rdi+10h]; pRecord
0x18000e07a  mov     eax, 0FFh
0x18000e07f  cmp     r14w, ax
0x18000e083  jz      short loc_18000E0A7
0x18000e085  test    rcx, rcx
0x18000e088  jz      short loc_18000E0D3
0x18000e08a  cmp     r14w, [rcx+10h]
0x18000e08f  jnz     loc_18000E2CD
0x18000e095  mov     eax, 1
0x18000e09a  mov     r8d, eax; CharSetOut
0x18000e09d  mov     edx, eax; CharSetIn
0x18000e09f  call    cs:__imp_DnsRecordCopyEx
0x18000e0a5  jmp     short loc_18000E0BB
0x18000e0a7  test    rcx, rcx
0x18000e0aa  jz      loc_18000E2D5
0x18000e0b0  mov     r8d, 1
0x18000e0b6  call    Dns_RecordListCopyEx
0x18000e0bb  test    rax, rax
0x18000e0be  jz      short loc_18000E0CE
0x18000e0c0  and     dword ptr [rax+14h], 0FFFFFFEDh
0x18000e0c4  or      dword ptr [rax+14h], 9
0x18000e0c8  mov     [rax], r13
0x18000e0cb  mov     r13, rax
0x18000e0ce  mov     eax, 0FFh
0x18000e0d3  cmp     r14d, 0Ch
0x18000e0d7  jnz     loc_18000E2D5
0x18000e0dd  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18000e0e4  mov     edi, [rsp+780h+var_740]
0x18000e0e8  mov     r14, [rsp+780h+lpWideCharStr]
0x18000e0ed  jnz     loc_18000EA82
0x18000e0f3  xor     eax, eax
0x18000e0f5  xor     r15d, r15d
0x18000e0f8  mov     [rbp+680h+var_230], ax
0x18000e0ff  test    r14, r14
0x18000e102  jz      short loc_18000E17B
0x18000e104  xor     edx, edx; Val
0x18000e106  mov     [rsp+780h+Context], rax
0x18000e10b  mov     r8d, 0C8h; Size
0x18000e111  lea     rcx, [rbp+680h+var_700]; void *
0x18000e115  call    memset_0
0x18000e11a  xor     eax, eax
0x18000e11c  lea     r9, [rbp+680h+String]
0x18000e120  mov     [rbp+680h+String], ax
0x18000e124  mov     ecx, 7FFFFFFEh
0x18000e129  mov     [rbp+680h+var_22E], ax
0x18000e130  mov     rdx, r14
0x18000e133  mov     r8d, 100h
0x18000e139  nop     dword ptr [rax+00000000h]
0x18000e140  test    rcx, rcx
0x18000e143  jz      short loc_18000E162
0x18000e145  movzx   eax, word ptr [rdx]
0x18000e148  test    ax, ax
0x18000e14b  jz      short loc_18000E162
0x18000e14d  mov     [r9], ax
0x18000e151  add     rdx, 2
0x18000e155  add     r9, 2
0x18000e159  dec     rcx
0x18000e15c  sub     r8, 1
0x18000e160  jnz     short loc_18000E140
0x18000e162  test    r8, r8
0x18000e165  lea     rcx, [r9-2]
0x18000e169  cmovnz  rcx, r9
0x18000e16d  xor     eax, eax
0x18000e16f  mov     [rcx], ax
0x18000e172  test    r8, r8
0x18000e175  jnz     loc_18000E553
0x18000e17b  test    r15, r15
0x18000e17e  jnz     loc_18000E420
0x18000e184  xor     ebx, ebx
0x18000e186  xor     edi, edi
0x18000e188  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18000e18f  jnz     loc_18000E8B5
0x18000e195  mov     esi, 490h
0x18000e19a  mov     rcx, rbx
0x18000e19d  call    Dns_RecordFree
0x18000e1a2  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18000e1a9  jnz     loc_18000EACC
0x18000e1af  cmp     cs:g_fVelocityDnsKernelApi, 0
0x18000e1b6  jnz     loc_18000E7E3
0x18000e1bc  test    rdi, rdi
0x18000e1bf  jnz     loc_18000E487
0x18000e1c5  mov     edi, [rsp+780h+var_738]
0x18000e1c9  lea     rcx, ?g_csMdnsTree@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000e1d0  call    cs:__imp_LeaveCriticalSection
0x18000e1d6  lea     r15, [r12+48h]
0x18000e1db  cmp     cs:g_fVelocityDnsKernelApi, 0
0x18000e1e2  mov     rdx, [rsp+780h+var_718]
0x18000e1e7  jnz     loc_18000E7D3
0x18000e1ed  test    rdx, rdx
0x18000e1f0  jnz     loc_18000E45B
0x18000e1f6  test    r13, r13
0x18000e1f9  jnz     loc_18000E67E
0x18000e1ff  mov     r14d, [rsp+780h+var_73C]
0x18000e204  inc     edi
0x18000e206  xor     r13d, r13d
0x18000e209  jmp     loc_18000DF1F
0x18000e20e  test    r14d, r14d
0x18000e211  jnz     loc_18000E6EF
0x18000e217  mov     r14, [rsp+780h+arg_18]
0x18000e21f  mov     rsi, [rsp+780h+arg_8]
0x18000e227  cmp     qword ptr [r12+20h], 0
0x18000e22d  mov     r15, [rsp+780h+var_20]
0x18000e235  jz      short loc_18000E276
0x18000e237  cmp     dword ptr [r12+18h], 0
0x18000e23d  mov     edi, r13d
0x18000e240  jbe     short loc_18000E26C
0x18000e242  mov     rcx, [r12+20h]
0x18000e247  mov     eax, edi
0x18000e249  lea     rbx, ds:0[rax*8]
0x18000e251  mov     rcx, [rbx+rcx]; void *
0x18000e255  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e25a  mov     rax, [r12+20h]
0x18000e25f  inc     edi
0x18000e261  mov     [rbx+rax], r13
0x18000e265  cmp     edi, [r12+18h]
0x18000e26a  jb      short loc_18000E242
0x18000e26c  mov     rcx, [r12+20h]; void *
0x18000e271  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e276  mov     rcx, [r12+28h]; void *
0x18000e27b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e280  mov     rcx, [r12+48h]
0x18000e285  mov     [r12+10h], r13
0x18000e28a  call    cs:__imp_NetInfo_Free
0x18000e290  lea     rcx, [r12+50h]; lpCriticalSection
0x18000e295  call    cs:__imp_DeleteCriticalSection
0x18000e29b  mov     edx, 78h ; 'x'; unsigned __int64
0x18000e2a0  mov     rcx, r12; void *
0x18000e2a3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e2a8  mov     rdi, [rsp+780h+arg_10]
0x18000e2b0  mov     rcx, [rbp+680h+var_30]
0x18000e2b7  xor     rcx, rsp; StackCookie
0x18000e2ba  call    __security_check_cookie
0x18000e2bf  add     rsp, 768h
0x18000e2c6  pop     r13
0x18000e2c8  pop     r12
0x18000e2ca  pop     rbx
0x18000e2cb  pop     rbp
0x18000e2cc  retn
0x18000e2cd  mov     rcx, [rcx]
0x18000e2d0  jmp     loc_18000E085
0x18000e2d5  xor     edi, edi
0x18000e2d7  cmp     r14w, ax
0x18000e2db  jnz     loc_18000E1AF
0x18000e2e1  jmp     loc_18000E0DD
0x18000e2e6  mov     rcx, [rcx+68h]
0x18000e2ea  test    rcx, rcx
0x18000e2ed  jz      loc_18000DDFB
0x18000e2f3  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18000e2fa  jz      loc_18000DDFB
0x18000e300  lea     rax, [rcx+2BCh]
0x18000e307  xorps   xmm0, xmm0
  ... truncated ...
```
