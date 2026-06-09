# DhcpBuildReplyMessage(_DHCP_INTERFACE *,_NH_BUFFER *,_DHCP_OPTION * *,uchar,uchar,_DHCP_OPTION * * const)

- ea: `0x180003650`
- end: `0x180004069`
- name: `?DhcpBuildReplyMessage@@YAXPEAU_DHCP_INTERFACE@@PEAU_NH_BUFFER@@PEAPEFAU_DHCP_OPTION@@EEQEAPEFAU3@@Z`
- size: `2585`
- prototype: `void __fastcall(struct _DHCP_INTERFACE *, struct _NH_BUFFER *, struct _DHCP_OPTION **, unsigned __int8, unsigned __int8, struct _DHCP_OPTION **const)`
- caller_count: `4`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800027d0`
- `0x18004898c`
- `0x1800492ec`
- `0x180064384`

## callees

- `0x180002394`
- `0x180003650`
- `0x18000ca20`
- `0x18000d090`
- `0x1800136a4`
- `0x1800202e0`
- `0x18002cae8`
- `0x180040bb0`
- `0x180041d80`
- `0x180056644`
- `0x1800566bc`
- `0x180059a04`
- `0x1800827b4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x180003d73`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x180003e25`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x180003ef1`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x180003f36`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x180003d73`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x180003e25`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x180003ef1`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x180003f36`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003db6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003e86`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003f00`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003fb4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003db6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003e86`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003f00`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003fb4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003dcb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003f15`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003dcb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003f15`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003e9a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003fc8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003e9a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003fc8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800037ff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000382c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003ed9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800037ff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000382c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003ed9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003819`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000384a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003f49`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003819`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000384a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003f49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c99`
- `WINHTTP!WinHttpDetectAutoProxyConfigUrl` at `0x180003c57`
- `WINHTTP!WinHttpDetectAutoProxyConfigUrl` at `0x180003c57`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180003eaa`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180003eaa`
- `WS2_32!__imp_htonl` at `0x180003858`
- `WS2_32!__imp_htonl` at `0x18000386d`
- `WS2_32!__imp_htonl` at `0x180003880`
- `WS2_32!__imp_htonl` at `0x180003858`
- `WS2_32!__imp_htonl` at `0x18000386d`
- `WS2_32!__imp_htonl` at `0x180003880`

## pseudocode

```c
void __fastcall DhcpBuildReplyMessage(
        struct _DHCP_INTERFACE *a1,
        struct _NH_BUFFER *a2,
        struct _DHCP_OPTION **a3,
        unsigned __int8 a4,
        unsigned __int8 a5,
        struct _DHCP_OPTION **const a6)
{
  int v6; // edi
  struct _NH_RCSOCKET *v10; // rcx
  unsigned int AddressSocket; // eax
  int v12; // r15d
  unsigned int v13; // esi
  PVOID *v14; // rcx
  int v15; // r12d
  u_long v16; // ebx
  u_long v17; // ebx
  PVOID *v18; // r11
  __int64 v19; // rbx
  __int64 v20; // rdi
  DWORD LastError; // eax
  int v22; // eax
  int v23; // ebx
  __int64 v24; // rsi
  HANDLE ProcessHeap; // rax
  unsigned __int8 *v26; // rax
  unsigned __int8 *v27; // rbx
  __int64 v28; // r8
  HANDLE v29; // rax
  unsigned int v30; // esi
  HANDLE v31; // rax
  unsigned __int8 *v32; // rax
  unsigned __int8 *SharedConnectionDomainName; // rbx
  HANDLE v34; // rax
  unsigned __int8 v35[4]; // [rsp+40h] [rbp-20h] BYREF
  unsigned __int8 v36[4]; // [rsp+44h] [rbp-1Ch] BYREF
  unsigned __int8 v37[8]; // [rsp+48h] [rbp-18h] BYREF
  LPWSTR ppwstrAutoConfigUrl; // [rsp+50h] [rbp-10h] BYREF
  unsigned int v39; // [rsp+A8h] [rbp+48h] BYREF
  __int16 v40; // [rsp+B8h] [rbp+58h] BYREF
  char v41; // [rsp+BAh] [rbp+5Ah]

  LOBYTE(v40) = a4;
  v6 = a4;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_Dc(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_07854302ac4e3c674a76622ff55d2da5_Traceguids, a4, a5 != 0);
  }
  v10 = (struct _NH_RCSOCKET *)*((_QWORD *)a2 + 2);
  ppwstrAutoConfigUrl = 0;
  AddressSocket = NhQueryAddressSocket(v10);
  v12 = *((_DWORD *)a2 + 10);
  v13 = AddressSocket;
  v39 = AddressSocket;
  LODWORD(a6) = v12;
  v14 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      WPP_07854302ac4e3c674a76622ff55d2da5_Traceguids,
      AddressSocket,
      v12);
    v14 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !(_BYTE)v6 )
  {
    *((_DWORD *)a2 + 62) = v13;
    goto LABEL_21;
  }
  if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 2) != 0 && *((_BYTE *)v14 + 25) >= 5u )
    WPP_SF_Dd(v14[2], 14, WPP_07854302ac4e3c674a76622ff55d2da5_Traceguids, 53, v6);
  DhcpAppendOptionToMessage(a3, 0x35u, 1u, (unsigned __int8 *const)&v40);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_ddddd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      WPP_07854302ac4e3c674a76622ff55d2da5_Traceguids,
      54,
      (unsigned __int8)v13,
      BYTE1(v39),
      BYTE2(v39),
      HIBYTE(v39));
  }
  DhcpAppendOptionToMessage(a3, 0x36u, 4u, (unsigned __int8 *const)&v39);
  LOBYTE(v6) = v40;
  if ( (_BYTE)v40 != 6 )
  {
    LOBYTE(v13) = v39;
LABEL_21:
    LOBYTE(v40) = 4;
    EnterCriticalSection(&NhLock);
    v15 = NhComponentMode;
    LeaveCriticalSection(&NhLock);
    EnterCriticalSection(&DhcpGlobalInfoLock);
    v16 = 60 * *((_DWORD *)DhcpGlobalInfo + 2);
    LeaveCriticalSection(&DhcpGlobalInfoLock);
    *(_DWORD *)v37 = htonl(v16);
    *(_DWORD *)v36 = htonl((3 * v16) >> 2);
    v17 = htonl(v16 >> 1);
    *(_DWORD *)v35 = v17;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_ddddd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        WPP_07854302ac4e3c674a76622ff55d2da5_Traceguids,
        1,
        (unsigned __int8)v12,
        BYTE1(a6),
        BYTE2(a6),
        BYTE3(a6));
    }
    DhcpAppendOptionToMessage(a3, 1u, 4u, (unsigned __int8 *const)&a6);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_ddddd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        WPP_07854302ac4e3c674a76622ff55d2da5_Traceguids,
        3,
        (unsigned __int8)v13,
        BYTE1(v39),
        BYTE2(v39),
        HIBYTE(v39));
    }
    DhcpAppendOptionToMessage(a3, 3u, 4u, (unsigned __int8 *const)&v39);
    if ( (_BYTE)v6 )
    {
      if ( v15 != 3 && (NhIsDnsProxyEnabled() || !NoLocalDns) )
      {
        v18 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            18,
            WPP_07854302ac4e3c674a76622ff55d2da5_Traceguids,
            *((unsigned int *)a1 + 24));
          v18 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( *((_DWORD *)a1 + 24) )
        {
          v19 = 0;
          do
          {
            if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 2) != 0 && *((_BYTE *)v18 + 25) >= 5u )
            {
              WPP_SF_ddddd(
                v18[2],
                19,
                WPP_07854302ac4e3c674a76622ff55d2da5_Traceguids,
                6,
                *(unsigned __int8 *)(*((_QWORD *)a1 + 13) + 4 * v19),
                *(unsigned __int8 *)(*((_QWORD *)a1 + 13) + 4 * v19 + 1),
                *(unsigned __int8 *)(*((_QWORD *)a1 + 13) + 4 * v19 + 2),
                *(unsigned __int8 *)(*((_QWORD *)a1 + 13) + 4 * v19 + 3));
              v18 = (PVOID *)WPP_GLOBAL_Control;
            }
            v19 = (unsigned int)(v19 + 1);
          }
          while ( (unsigned int)v19 < *((_DWORD *)a1 + 24) );
          DhcpAppendOptionToMessage(a3, 6u, 4 * *((_BYTE *)a1 + 96), *((unsigned __int8 *const *)a1 + 13));
          v17 = *(_DWORD *)v35;
        }
        else
        {
          if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 2) != 0 && *((_BYTE *)v18 + 25) >= 5u )
            WPP_SF_ddddd(
              v18[2],
              20,
              WPP_07854302ac4e3c674a76622ff55d2da5_Traceguids,
              6,
              (unsigned __int8)v39,
              BYTE1(v39),
              BYTE2(v39),
              HIBYTE(v39));
          DhcpAppendOptionToMessage(a3, 6u, 4u, (unsigned __int8 *const)&v39);
        }
      }
      if ( NhIsWinsProxyEnabled() )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_ddddd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            21,
            WPP_07854302ac4e3c674a76622ff55d2da5_Traceguids,
            44,
            (unsigned __int8)v39,
            BYTE1(v39),
            BYTE2(v39),
            HIBYTE(v39));
        }
        DhcpAppendOptionToMessage(a3, 0x2Cu, 4u, (unsigned __int8 *const)&v39);
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_07854302ac4e3c674a76622ff55d2da5_Traceguids, 58, v17);
      }
      DhcpAppendOptionToMessage(a3, 0x3Au, 4u, v35);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          23,
          WPP_07854302ac4e3c674a76622ff55d2da5_Traceguids,
          59,
          *(_DWORD *)v36);
      }
      DhcpAppendOptionToMessage(a3, 0x3Bu, 4u, v36);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          24,
          WPP_07854302ac4e3c674a76622ff55d2da5_Traceguids,
          51,
          *(_DWORD *)v37);
      }
      DhcpAppendOptionToMessage(a3, 0x33u, 4u, v37);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_07854302ac4e3c674a76622ff55d2da5_Traceguids, 46, 4);
      }
      DhcpAppendOptionToMessage(a3, 0x2Eu, 1u, (unsigned __int8 *const)&v40);
      if ( a5 )
      {
        v40 = 3;
        v41 = 0;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_07854302ac4e3c674a76622ff55d2da5_Traceguids, 81);
        }
        DhcpAppendOptionToMessage(a3, 0x51u, 3u, (unsigned __int8 *const)&v40);
      }
      v20 = -1;
      if ( WinHttpDetectAutoProxyConfigUrl(1u, &ppwstrAutoConfigUrl) )
      {
        if ( ppwstrAutoConfigUrl )
        {
          v22 = _o_wcstombs(0, ppwstrAutoConfigUrl, 0);
          v23 = v22;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              29,
              (unsigned int)WPP_07854302ac4e3c674a76622ff55d2da5_Traceguids,
              (_DWORD)ppwstrAutoConfigUrl,
              v22);
          }
          v24 = (unsigned int)(v23 + 1);
          ProcessHeap = GetProcessHeap();
          v26 = (unsigned __int8 *)HeapAlloc(ProcessHeap, 8u, (unsigned int)v24);
          v27 = v26;
          if ( v26 )
          {
            _o_wcstombs(v26, ppwstrAutoConfigUrl, v24);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              WPP_SF_Ds(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                31,
                (unsigned int)WPP_07854302ac4e3c674a76622ff55d2da5_Traceguids,
                252,
                (__int64)v27);
            }
            v28 = -1;
            do
              ++v28;
            while ( v27[v28] );
            DhcpAppendOptionToMessage(a3, 0xFCu, v28 + 1, v27);
            v29 = GetProcessHeap();
            HeapFree(v29, 0, v27);
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_07854302ac4e3c674a76622ff55d2da5_Traceguids);
          }
          GlobalFree(ppwstrAutoConfigUrl);
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_07854302ac4e3c674a76622ff55d2da5_Traceguids);
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_07854302ac4e3c674a76622ff55d2da5_Traceguids, LastError);
      }
      if ( DnsGlobalInfo && DnsICSDomainSuffix )
      {
        EnterCriticalSection(&DnsGlobalInfoLock);
        v30 = _o_wcstombs(0, DnsICSDomainSuffix, 0) + 1;
        v31 = GetProcessHeap();
        v32 = (unsigned __int8 *)HeapAlloc(v31, 8u, v30);
        SharedConnectionDomainName = v32;
        if ( v32 )
          _o_wcstombs(v32, DnsICSDomainSuffix, v30);
        LeaveCriticalSection(&DnsGlobalInfoLock);
      }
      else
      {
        SharedConnectionDomainName = (unsigned __int8 *)NatQuerySharedConnectionDomainName();
      }
      if ( SharedConnectionDomainName )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_Ds(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            32,
            (unsigned int)WPP_07854302ac4e3c674a76622ff55d2da5_Traceguids,
            15,
            (__int64)SharedConnectionDomainName);
        }
        do
          ++v20;
        while ( SharedConnectionDomainName[v20] );
        DhcpAppendOptionToMessage(a3, 0xFu, v20 + 1, SharedConnectionDomainName);
        v34 = GetProcessHeap();
        HeapFree(v34, 0, SharedConnectionDomainName);
      }
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_07854302ac4e3c674a76622ff55d2da5_Traceguids, 255);
  }
  DhcpAppendOptionToMessage(a3, 0xFFu, 0, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_07854302ac4e3c674a76622ff55d2da5_Traceguids);
  }
}

```

## disassembly

```asm
0x180003650  mov     [rsp-38h+arg_0], rbx
0x180003655  mov     byte ptr [rsp-38h+arg_18], r9b
0x18000365a  push    rbp
0x18000365b  push    rsi
0x18000365c  push    rdi
0x18000365d  push    r12
0x18000365f  push    r13
0x180003661  push    r14
0x180003663  push    r15
0x180003665  mov     rbp, rsp
0x180003668  sub     rsp, 60h
0x18000366c  movzx   edi, r9b
0x180003670  mov     r14, r8
0x180003673  mov     rbx, rdx
0x180003676  mov     r13, rcx
0x180003679  mov     rcx, cs:WPP_GLOBAL_Control
0x180003680  lea     rax, WPP_GLOBAL_Control
0x180003687  mov     r12b, 2
0x18000368a  cmp     rcx, rax
0x18000368d  jz      short loc_1800036BE
0x18000368f  test    [rcx+1Ch], r12b
0x180003693  jz      short loc_1800036BE
0x180003695  cmp     byte ptr [rcx+19h], 6
0x180003699  jb      short loc_1800036BE
0x18000369b  cmp     [rbp+arg_20], 0
0x18000369f  lea     r8, WPP_07854302ac4e3c674a76622ff55d2da5_Traceguids
0x1800036a6  mov     rcx, [rcx+10h]
0x1800036aa  mov     r9d, edi
0x1800036ad  setnz   al
0x1800036b0  mov     edx, 0Ch
0x1800036b5  mov     byte ptr [rsp+60h+var_40], al
0x1800036b9  call    WPP_SF_Dc
0x1800036be  mov     rcx, [rbx+10h]; struct _NH_RCSOCKET *
0x1800036c2  mov     [rbp+ppwstrAutoConfigUrl], 0
0x1800036ca  call    ?NhQueryAddressSocket@@YAKPEAU_NH_RCSOCKET@@@Z; NhQueryAddressSocket(_NH_RCSOCKET *)
0x1800036cf  mov     r15d, [rbx+28h]
0x1800036d3  mov     esi, eax
0x1800036d5  mov     [rbp+arg_8], eax
0x1800036d8  mov     dword ptr [rbp+arg_28], r15d
0x1800036dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800036e3  lea     rax, WPP_GLOBAL_Control
0x1800036ea  cmp     rcx, rax
0x1800036ed  jz      short loc_180003726
0x1800036ef  test    [rcx+1Ch], r12b
0x1800036f3  jz      short loc_180003726
0x1800036f5  cmp     byte ptr [rcx+19h], 5
0x1800036f9  jb      short loc_180003726
0x1800036fb  mov     rcx, [rcx+10h]
0x1800036ff  lea     r8, WPP_07854302ac4e3c674a76622ff55d2da5_Traceguids
0x180003706  mov     edx, 0Dh
0x18000370b  mov     dword ptr [rsp+60h+var_40], r15d
0x180003710  mov     r9d, esi
0x180003713  call    WPP_SF_Dd
0x180003718  mov     rcx, cs:WPP_GLOBAL_Control
0x18000371f  lea     rax, WPP_GLOBAL_Control
0x180003726  test    dil, dil
0x180003729  jnz     short loc_180003736
0x18000372b  mov     [rbx+0F8h], esi
0x180003731  jmp     loc_1800037F4
0x180003736  cmp     rcx, rax
0x180003739  jz      short loc_180003764
0x18000373b  test    [rcx+1Ch], r12b
0x18000373f  jz      short loc_180003764
0x180003741  cmp     byte ptr [rcx+19h], 5
0x180003745  jb      short loc_180003764
0x180003747  mov     rcx, [rcx+10h]
0x18000374b  lea     r8, WPP_07854302ac4e3c674a76622ff55d2da5_Traceguids
0x180003752  mov     edx, 0Eh
0x180003757  mov     dword ptr [rsp+60h+var_40], edi
0x18000375b  lea     r9d, [rdx+27h]
0x18000375f  call    WPP_SF_Dd
0x180003764  lea     r9, [rbp+arg_18]; unsigned __int8 *
0x180003768  mov     r8b, 1; unsigned __int8
0x18000376b  mov     dl, 35h ; '5'; unsigned __int8
0x18000376d  mov     rcx, r14; struct _DHCP_OPTION **
0x180003770  call    ?DhcpAppendOptionToMessage@@YAXPEAPEFAU_DHCP_OPTION@@EEQEAE@Z; DhcpAppendOptionToMessage(_DHCP_OPTION * *,uchar,uchar,uchar * const)
0x180003775  mov     rcx, cs:WPP_GLOBAL_Control
0x18000377c  lea     rax, WPP_GLOBAL_Control
0x180003783  cmp     rcx, rax
0x180003786  jz      short loc_1800037D2
0x180003788  test    [rcx+1Ch], r12b
0x18000378c  jz      short loc_1800037D2
0x18000378e  cmp     byte ptr [rcx+19h], 5
0x180003792  jb      short loc_1800037D2
0x180003794  movzx   r9d, byte ptr [rbp+arg_8+1]
0x180003799  mov     edx, 0Fh
0x18000379e  movzx   eax, byte ptr [rbp+arg_8+3]
0x1800037a2  movzx   r8d, byte ptr [rbp+arg_8+2]
0x1800037a7  mov     rcx, [rcx+10h]
0x1800037ab  mov     [rsp+60h+var_28], eax
0x1800037af  mov     [rsp+60h+var_30], r8d
0x1800037b4  lea     r8, WPP_07854302ac4e3c674a76622ff55d2da5_Traceguids
0x1800037bb  mov     [rsp+60h+var_38], r9d
0x1800037c0  lea     r9d, [rdx+27h]
0x1800037c4  movzx   r10d, sil
0x1800037c8  mov     dword ptr [rsp+60h+var_40], r10d
0x1800037cd  call    WPP_SF_ddddd
0x1800037d2  lea     r9, [rbp+arg_8]; unsigned __int8 *
0x1800037d6  mov     r8b, 4; unsigned __int8
0x1800037d9  mov     dl, 36h ; '6'; unsigned __int8
0x1800037db  mov     rcx, r14; struct _DHCP_OPTION **
0x1800037de  call    ?DhcpAppendOptionToMessage@@YAXPEAPEFAU_DHCP_OPTION@@EEQEAE@Z; DhcpAppendOptionToMessage(_DHCP_OPTION * *,uchar,uchar,uchar * const)
0x1800037e3  mov     dil, byte ptr [rbp+arg_18]
0x1800037e7  cmp     dil, 6
0x1800037eb  jz      loc_180003FD9
0x1800037f1  mov     esi, [rbp+arg_8]
0x1800037f4  lea     rcx, ?NhLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800037fb  mov     byte ptr [rbp+arg_18], 4
0x1800037ff  call    cs:__imp_EnterCriticalSection
0x180003806  nop     dword ptr [rax+rax+00h]
0x18000380b  mov     r12d, cs:?NhComponentMode@@3W4NH_COMPONENT_MODE@@A; NH_COMPONENT_MODE NhComponentMode
0x180003812  lea     rcx, ?NhLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180003819  call    cs:__imp_LeaveCriticalSection
0x180003820  nop     dword ptr [rax+rax+00h]
0x180003825  lea     rcx, ?DhcpGlobalInfoLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000382c  call    cs:__imp_EnterCriticalSection
0x180003833  nop     dword ptr [rax+rax+00h]
0x180003838  mov     rax, cs:?DhcpGlobalInfo@@3PEAU_IP_AUTO_DHCP_GLOBAL_INFO@@EA; _IP_AUTO_DHCP_GLOBAL_INFO * DhcpGlobalInfo
0x18000383f  lea     rcx, ?DhcpGlobalInfoLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180003846  imul    ebx, [rax+8], 3Ch ; '<'
0x18000384a  call    cs:__imp_LeaveCriticalSection
0x180003851  nop     dword ptr [rax+rax+00h]
0x180003856  mov     ecx, ebx; hostlong
0x180003858  call    cs:__imp_htonl
0x18000385f  nop     dword ptr [rax+rax+00h]
0x180003864  lea     ecx, [rbx+rbx*2]
0x180003867  mov     dword ptr [rbp+var_18], eax
0x18000386a  shr     ecx, 2; hostlong
0x18000386d  call    cs:__imp_htonl
0x180003874  nop     dword ptr [rax+rax+00h]
0x180003879  shr     ebx, 1
0x18000387b  mov     ecx, ebx; hostlong
0x18000387d  mov     dword ptr [rbp+var_1C], eax
0x180003880  call    cs:__imp_htonl
0x180003887  nop     dword ptr [rax+rax+00h]
0x18000388c  mov     ebx, eax
0x18000388e  mov     dword ptr [rbp+var_20], eax
0x180003891  mov     rcx, cs:WPP_GLOBAL_Control
0x180003898  lea     rax, WPP_GLOBAL_Control
0x18000389f  cmp     rcx, rax
0x1800038a2  jz      short loc_1800038EE
0x1800038a4  test    byte ptr [rcx+1Ch], 2
0x1800038a8  jz      short loc_1800038EE
0x1800038aa  cmp     byte ptr [rcx+19h], 5
0x1800038ae  jb      short loc_1800038EE
0x1800038b0  movzx   r9d, byte ptr [rbp+arg_28+1]
0x1800038b5  mov     edx, 10h
0x1800038ba  movzx   eax, byte ptr [rbp+arg_28+3]
0x1800038be  movzx   r8d, byte ptr [rbp+arg_28+2]
0x1800038c3  mov     rcx, [rcx+10h]
0x1800038c7  mov     [rsp+60h+var_28], eax
0x1800038cb  mov     [rsp+60h+var_30], r8d
0x1800038d0  lea     r8, WPP_07854302ac4e3c674a76622ff55d2da5_Traceguids
0x1800038d7  mov     [rsp+60h+var_38], r9d
0x1800038dc  lea     r9d, [rdx-0Fh]
0x1800038e0  movzx   r10d, r15b
0x1800038e4  mov     dword ptr [rsp+60h+var_40], r10d
0x1800038e9  call    WPP_SF_ddddd
0x1800038ee  lea     r9, [rbp+arg_28]; unsigned __int8 *
0x1800038f2  mov     r8b, 4; unsigned __int8
0x1800038f5  mov     dl, 1; unsigned __int8
0x1800038f7  mov     rcx, r14; struct _DHCP_OPTION **
0x1800038fa  call    ?DhcpAppendOptionToMessage@@YAXPEAPEFAU_DHCP_OPTION@@EEQEAE@Z; DhcpAppendOptionToMessage(_DHCP_OPTION * *,uchar,uchar,uchar * const)
0x1800038ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180003906  lea     rax, WPP_GLOBAL_Control
0x18000390d  mov     r15b, 2
0x180003910  cmp     rcx, rax
0x180003913  jz      short loc_180003964
0x180003915  test    [rcx+1Ch], r15b
0x180003919  jz      short loc_180003964
0x18000391b  cmp     byte ptr [rcx+19h], 5
0x18000391f  jb      short loc_180003964
0x180003921  movzx   r9d, byte ptr [rbp+arg_8+1]
0x180003926  mov     edx, 11h
0x18000392b  movzx   eax, byte ptr [rbp+arg_8+3]
0x18000392f  movzx   r8d, byte ptr [rbp+arg_8+2]
0x180003934  mov     rcx, [rcx+10h]
0x180003938  mov     [rsp+60h+var_28], eax
0x18000393c  mov     [rsp+60h+var_30], r8d
0x180003941  movzx   r10d, sil
0x180003945  lea     rsi, WPP_07854302ac4e3c674a76622ff55d2da5_Traceguids
0x18000394c  mov     [rsp+60h+var_38], r9d
0x180003951  mov     r8, rsi
0x180003954  lea     r9d, [rdx-0Eh]
0x180003958  mov     dword ptr [rsp+60h+var_40], r10d
0x18000395d  call    WPP_SF_ddddd
0x180003962  jmp     short loc_18000396B
0x180003964  lea     rsi, WPP_07854302ac4e3c674a76622ff55d2da5_Traceguids
0x18000396b  lea     r9, [rbp+arg_8]; unsigned __int8 *
0x18000396f  mov     r8b, 4; unsigned __int8
0x180003972  mov     dl, 3; unsigned __int8
0x180003974  mov     rcx, r14; struct _DHCP_OPTION **
0x180003977  call    ?DhcpAppendOptionToMessage@@YAXPEAPEFAU_DHCP_OPTION@@EEQEAE@Z; DhcpAppendOptionToMessage(_DHCP_OPTION * *,uchar,uchar,uchar * const)
0x18000397c  test    dil, dil
0x18000397f  jz      loc_180003FD6
0x180003985  cmp     r12d, 3
0x180003989  jz      loc_180003A77
0x18000398f  call    ?NhIsDnsProxyEnabled@@YAEXZ; NhIsDnsProxyEnabled(void)
0x180003994  test    al, al
0x180003996  jnz     short loc_1800039A4
0x180003998  cmp     cs:?NoLocalDns@@3EA, al; uchar NoLocalDns
0x18000399e  jnz     loc_180003A77
0x1800039a4  mov     r11, cs:WPP_GLOBAL_Control
0x1800039ab  lea     rax, WPP_GLOBAL_Control
0x1800039b2  cmp     r11, rax
0x1800039b5  jz      short loc_1800039E7
0x1800039b7  test    [r11+1Ch], r15b
0x1800039bb  jz      short loc_1800039E7
0x1800039bd  cmp     byte ptr [r11+19h], 5
0x1800039c2  jb      short loc_1800039E7
0x1800039c4  mov     r9d, [r13+60h]
0x1800039c8  mov     edx, 12h
0x1800039cd  mov     rcx, [r11+10h]
0x1800039d1  mov     r8, rsi
0x1800039d4  call    WPP_SF_d
0x1800039d9  mov     r11, cs:WPP_GLOBAL_Control
0x1800039e0  lea     rax, WPP_GLOBAL_Control
0x1800039e7  cmp     dword ptr [r13+60h], 0
0x1800039ec  jbe     loc_180003CC3
0x1800039f2  xor     ebx, ebx
0x1800039f4  cmp     r11, rax
0x1800039f7  jz      short loc_180003A56
0x1800039f9  test    [r11+1Ch], r15b
0x1800039fd  jz      short loc_180003A56
0x1800039ff  cmp     byte ptr [r11+19h], 5
0x180003a04  jb      short loc_180003A56
0x180003a06  mov     rax, [r13+68h]
0x180003a0a  mov     edx, 13h
0x180003a0f  movzx   ecx, byte ptr [rax+rbx*4+3]
0x180003a14  movzx   r8d, byte ptr [rax+rbx*4+2]
0x180003a1a  movzx   r9d, byte ptr [rax+rbx*4+1]
0x180003a20  movzx   r10d, byte ptr [rax+rbx*4]
0x180003a25  mov     [rsp+60h+var_28], ecx
0x180003a29  mov     rcx, [r11+10h]
0x180003a2d  mov     [rsp+60h+var_30], r8d
0x180003a32  mov     r8, rsi
0x180003a35  mov     [rsp+60h+var_38], r9d
0x180003a3a  lea     r9d, [rdx-0Dh]
0x180003a3e  mov     dword ptr [rsp+60h+var_40], r10d
0x180003a43  call    WPP_SF_ddddd
0x180003a48  mov     r11, cs:WPP_GLOBAL_Control
0x180003a4f  lea     rax, WPP_GLOBAL_Control
0x180003a56  inc     ebx
0x180003a58  cmp     ebx, [r13+60h]
0x180003a5c  jb      short loc_1800039F4
0x180003a5e  mov     r8b, [r13+60h]
0x180003a62  mov     dl, 6; unsigned __int8
0x180003a64  mov     r9, [r13+68h]; unsigned __int8 *
0x180003a68  mov     rcx, r14; struct _DHCP_OPTION **
0x180003a6b  shl     r8b, 2; unsigned __int8
0x180003a6f  call    ?DhcpAppendOptionToMessage@@YAXPEAPEFAU_DHCP_OPTION@@EEQEAE@Z; DhcpAppendOptionToMessage(_DHCP_OPTION * *,uchar,uchar,uchar * const)
0x180003a74  mov     ebx, dword ptr [rbp+var_20]
0x180003a77  lea     r13, WPP_GLOBAL_Control
0x180003a7e  call    ?NhIsWinsProxyEnabled@@YAEXZ; NhIsWinsProxyEnabled(void)
0x180003a83  test    al, al
0x180003a85  jz      short loc_180003AEB
0x180003a87  mov     rcx, cs:WPP_GLOBAL_Control
0x180003a8e  cmp     rcx, r13
0x180003a91  jz      short loc_180003ADA
0x180003a93  test    [rcx+1Ch], r15b
0x180003a97  jz      short loc_180003ADA
0x180003a99  cmp     byte ptr [rcx+19h], 4
0x180003a9d  jb      short loc_180003ADA
0x180003a9f  movzx   r9d, byte ptr [rbp+arg_8+1]
0x180003aa4  mov     edx, 15h
0x180003aa9  movzx   eax, byte ptr [rbp+arg_8+3]
0x180003aad  movzx   r8d, byte ptr [rbp+arg_8+2]
0x180003ab2  movzx   r10d, byte ptr [rbp+arg_8]
0x180003ab7  mov     rcx, [rcx+10h]
0x180003abb  mov     [rsp+60h+var_28], eax
0x180003abf  mov     [rsp+60h+var_30], r8d
0x180003ac4  mov     r8, rsi
0x180003ac7  mov     [rsp+60h+var_38], r9d
0x180003acc  lea     r9d, [rdx+17h]
0x180003ad0  mov     dword ptr [rsp+60h+var_40], r10d
0x180003ad5  call    WPP_SF_ddddd
0x180003ada  lea     r9, [rbp+arg_8]; unsigned __int8 *
0x180003ade  mov     r8b, 4; unsigned __int8
0x180003ae1  mov     dl, 2Ch ; ','; unsigned __int8
0x180003ae3  mov     rcx, r14; struct _DHCP_OPTION **
0x180003ae6  call    ?DhcpAppendOptionToMessage@@YAXPEAPEFAU_DHCP_OPTION@@EEQEAE@Z; DhcpAppendOptionToMessage(_DHCP_OPTION * *,uchar,uchar,uchar * const)
0x180003aeb  mov     rcx, cs:WPP_GLOBAL_Control
0x180003af2  mov     r12b, 2
0x180003af5  cmp     rcx, r13
0x180003af8  jz      short loc_180003B1F
0x180003afa  test    [rcx+1Ch], r12b
0x180003afe  jz      short loc_180003B1F
0x180003b00  cmp     byte ptr [rcx+19h], 4
0x180003b04  jb      short loc_180003B1F
0x180003b06  mov     rcx, [rcx+10h]
0x180003b0a  mov     edx, 16h
0x180003b0f  mov     r8, rsi
0x180003b12  mov     dword ptr [rsp+60h+var_40], ebx
0x180003b16  lea     r9d, [rdx+24h]
0x180003b1a  call    WPP_SF_Dd
0x180003b1f  lea     r9, [rbp+var_20]; unsigned __int8 *
0x180003b23  mov     r8b, 4; unsigned __int8
0x180003b26  mov     dl, 3Ah ; ':'; unsigned __int8
0x180003b28  mov     rcx, r14; struct _DHCP_OPTION **
0x180003b2b  call    ?DhcpAppendOptionToMessage@@YAXPEAPEFAU_DHCP_OPTION@@EEQEAE@Z; DhcpAppendOptionToMessage(_DHCP_OPTION * *,uchar,uchar,uchar * const)
  ... truncated ...
```
