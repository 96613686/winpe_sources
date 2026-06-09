# V2DhcpBuildReplyMessage(_V2_DHCP_INTERFACE *,_NH_BUFFER *,_DHCP_OPTION * *,uchar,uchar,_DHCP_OPTION * * const)

- ea: `0x180004bd8`
- end: `0x1800055ab`
- name: `?V2DhcpBuildReplyMessage@@YAXPEAU_V2_DHCP_INTERFACE@@PEAU_NH_BUFFER@@PEAPEFAU_DHCP_OPTION@@EEQEAPEFAU3@@Z`
- size: `2515`
- prototype: `void(struct _V2_DHCP_INTERFACE *, struct _NH_BUFFER *, struct _DHCP_OPTION **, unsigned __int8, unsigned __int8, struct _DHCP_OPTION **const)`
- caller_count: `4`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004070`
- `0x18004d200`
- `0x18008cad8`
- `0x18008d408`

## callees

- `0x180004bd8`
- `0x18000ca20`
- `0x18000d090`
- `0x1800136a4`
- `0x1800202e0`
- `0x18002cae8`
- `0x18003c400`
- `0x180040bb0`
- `0x180041d80`
- `0x180051f30`
- `0x180052bf4`
- `0x1800566bc`
- `0x180059a04`
- `0x1800827b4`
- `0x18008c850`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x1800052af`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x180005363`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x18000542c`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x180005473`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x1800052af`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x180005363`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x18000542c`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x180005473`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800052f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800053c3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000543b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800054f1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800052f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800053c3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000543b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800054f1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005309`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005452`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005309`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005452`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800053d7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005505`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800053d7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005505`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004d97`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005414`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004d97`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005414`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004daa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005486`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004daa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005486`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000523d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000523d`
- `WINHTTP!WinHttpDetectAutoProxyConfigUrl` at `0x180005205`
- `WINHTTP!WinHttpDetectAutoProxyConfigUrl` at `0x180005205`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800053e7`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800053e7`
- `WS2_32!__imp_htonl` at `0x180004dbe`
- `WS2_32!__imp_htonl` at `0x180004dd3`
- `WS2_32!__imp_htonl` at `0x180004de6`
- `WS2_32!__imp_htonl` at `0x180004dbe`
- `WS2_32!__imp_htonl` at `0x180004dd3`
- `WS2_32!__imp_htonl` at `0x180004de6`

## pseudocode

```c
void __fastcall V2DhcpBuildReplyMessage(
        struct _V2_DHCP_INTERFACE *a1,
        struct _NH_RCSOCKET **a2,
        struct _DHCP_OPTION **a3,
        unsigned __int8 a4,
        unsigned __int8 a5)
{
  int v5; // edi
  unsigned int AddressSocket; // eax
  int v10; // r15d
  unsigned int v11; // esi
  PVOID *v12; // rcx
  u_long v13; // ebx
  u_long v14; // r13d
  unsigned int DnsServerList; // eax
  unsigned __int8 v16; // bl
  unsigned __int8 *v17; // r9
  unsigned __int8 v18; // r8
  __int64 v19; // rdi
  DWORD LastError; // eax
  int v21; // eax
  int v22; // ebx
  __int64 v23; // rsi
  HANDLE ProcessHeap; // rax
  unsigned __int8 *v25; // rax
  unsigned __int8 *v26; // rbx
  __int64 v27; // r8
  HANDLE v28; // rax
  unsigned int v29; // esi
  HANDLE v30; // rax
  unsigned __int8 *v31; // rax
  unsigned __int8 *SharedConnectionDomainName; // rbx
  HANDLE v33; // rax
  unsigned __int8 v34[8]; // [rsp+40h] [rbp-89h] BYREF
  unsigned __int8 v35[8]; // [rsp+48h] [rbp-81h] BYREF
  unsigned __int8 v36[4]; // [rsp+50h] [rbp-79h] BYREF
  unsigned __int8 v37[4]; // [rsp+54h] [rbp-75h] BYREF
  unsigned __int8 v38[8]; // [rsp+58h] [rbp-71h] BYREF
  LPWSTR ppwstrAutoConfigUrl; // [rsp+60h] [rbp-69h] BYREF
  unsigned __int8 v40[8]; // [rsp+68h] [rbp-61h] BYREF
  unsigned int v41[20]; // [rsp+70h] [rbp-59h] BYREF

  v5 = a4;
  v35[0] = a4;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_Dc(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_bdbb9979ae51315066150bc8512c706a_Traceguids, a4, a5 != 0);
  }
  ppwstrAutoConfigUrl = 0;
  memset_0(v41, 0, sizeof(v41));
  AddressSocket = NhQueryAddressSocket(a2[2]);
  v10 = *((_DWORD *)a2 + 10);
  v11 = AddressSocket;
  *(_DWORD *)v34 = AddressSocket;
  *(_DWORD *)v36 = v10;
  v12 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      WPP_bdbb9979ae51315066150bc8512c706a_Traceguids,
      AddressSocket,
      v10);
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( (_BYTE)v5 )
  {
    if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 2) != 0 && *((_BYTE *)v12 + 25) >= 5u )
      WPP_SF_Dd(v12[2], 17, WPP_bdbb9979ae51315066150bc8512c706a_Traceguids, 53, v5);
    V2DhcpAppendOptionToMessage(a3, 0x35u, 1u, v35);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_ddddd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        WPP_bdbb9979ae51315066150bc8512c706a_Traceguids,
        54,
        (unsigned __int8)v11,
        v34[1],
        v34[2],
        v34[3]);
    }
    V2DhcpAppendOptionToMessage(a3, 0x36u, 4u, v34);
    LOBYTE(v11) = v34[0];
    LOBYTE(v5) = v35[0];
  }
  else
  {
    *((_DWORD *)a2 + 62) = v11;
  }
  if ( (_BYTE)v5 != 6 )
  {
    v35[0] = 4;
    EnterCriticalSection(&NhLock);
    LeaveCriticalSection(&NhLock);
    v13 = 60 * *((_DWORD *)a1 + 19);
    *(_DWORD *)v38 = htonl(v13);
    *(_DWORD *)v37 = htonl((3 * v13) >> 2);
    v14 = htonl(v13 >> 1);
    *(_DWORD *)v40 = v14;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_ddddd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        WPP_bdbb9979ae51315066150bc8512c706a_Traceguids,
        1,
        (unsigned __int8)v10,
        v36[1],
        v36[2],
        v36[3]);
    }
    V2DhcpAppendOptionToMessage(a3, 1u, 4u, v36);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_ddddd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        WPP_bdbb9979ae51315066150bc8512c706a_Traceguids,
        3,
        (unsigned __int8)v11,
        v34[1],
        v34[2],
        v34[3]);
    }
    V2DhcpAppendOptionToMessage(a3, 3u, 4u, v34);
    if ( (_BYTE)v5 )
    {
      if ( (*((_BYTE *)a1 + 120) & 1) != 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_bdbb9979ae51315066150bc8512c706a_Traceguids);
        }
        *(_DWORD *)v36 = 20;
        DnsServerList = GetDnsServerList(v41, (unsigned int *)v36);
        if ( DnsServerList )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              23,
              WPP_bdbb9979ae51315066150bc8512c706a_Traceguids,
              DnsServerList);
          }
          goto LABEL_51;
        }
        v16 = v36[0];
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            22,
            WPP_bdbb9979ae51315066150bc8512c706a_Traceguids,
            *(unsigned int *)v36);
        }
        v17 = (unsigned __int8 *)v41;
        v18 = 4 * v16;
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_ddddd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            24,
            WPP_bdbb9979ae51315066150bc8512c706a_Traceguids,
            6,
            v34[0],
            v34[1],
            v34[2],
            v34[3]);
        }
        v17 = v34;
        v18 = 4;
      }
      V2DhcpAppendOptionToMessage(a3, 6u, v18, v17);
LABEL_51:
      if ( NhIsWinsProxyEnabled() )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_ddddd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            25,
            WPP_bdbb9979ae51315066150bc8512c706a_Traceguids,
            44,
            v34[0],
            v34[1],
            v34[2],
            v34[3]);
        }
        V2DhcpAppendOptionToMessage(a3, 0x2Cu, 4u, v34);
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_bdbb9979ae51315066150bc8512c706a_Traceguids, 58, v14);
      }
      V2DhcpAppendOptionToMessage(a3, 0x3Au, 4u, v40);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          27,
          WPP_bdbb9979ae51315066150bc8512c706a_Traceguids,
          59,
          *(_DWORD *)v37);
      }
      V2DhcpAppendOptionToMessage(a3, 0x3Bu, 4u, v37);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          28,
          WPP_bdbb9979ae51315066150bc8512c706a_Traceguids,
          51,
          *(_DWORD *)v38);
      }
      V2DhcpAppendOptionToMessage(a3, 0x33u, 4u, v38);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_bdbb9979ae51315066150bc8512c706a_Traceguids, 46, 4);
      }
      V2DhcpAppendOptionToMessage(a3, 0x2Eu, 1u, v35);
      if ( a5 )
      {
        *(_WORD *)v34 = 3;
        v34[2] = 0;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_bdbb9979ae51315066150bc8512c706a_Traceguids, 81);
        }
        V2DhcpAppendOptionToMessage(a3, 0x51u, 3u, v34);
      }
      v19 = -1;
      if ( WinHttpDetectAutoProxyConfigUrl(1u, &ppwstrAutoConfigUrl) )
      {
        if ( ppwstrAutoConfigUrl )
        {
          v21 = _o_wcstombs(0, ppwstrAutoConfigUrl, 0);
          v22 = v21;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              33,
              (unsigned int)WPP_bdbb9979ae51315066150bc8512c706a_Traceguids,
              (_DWORD)ppwstrAutoConfigUrl,
              v21);
          }
          v23 = (unsigned int)(v22 + 1);
          ProcessHeap = GetProcessHeap();
          v25 = (unsigned __int8 *)HeapAlloc(ProcessHeap, 8u, (unsigned int)v23);
          v26 = v25;
          if ( v25 )
          {
            _o_wcstombs(v25, ppwstrAutoConfigUrl, v23);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              WPP_SF_Ds(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                35,
                (unsigned int)WPP_bdbb9979ae51315066150bc8512c706a_Traceguids,
                252,
                (__int64)v26);
            }
            v27 = -1;
            do
              ++v27;
            while ( v26[v27] );
            V2DhcpAppendOptionToMessage(a3, 0xFCu, v27 + 1, v26);
            v28 = GetProcessHeap();
            HeapFree(v28, 0, v26);
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_bdbb9979ae51315066150bc8512c706a_Traceguids);
          }
          GlobalFree(ppwstrAutoConfigUrl);
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_bdbb9979ae51315066150bc8512c706a_Traceguids);
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_bdbb9979ae51315066150bc8512c706a_Traceguids, LastError);
      }
      if ( DnsGlobalInfo && DnsICSDomainSuffix )
      {
        EnterCriticalSection(&DnsGlobalInfoLock);
        v29 = _o_wcstombs(0, DnsICSDomainSuffix, 0) + 1;
        v30 = GetProcessHeap();
        v31 = (unsigned __int8 *)HeapAlloc(v30, 8u, v29);
        SharedConnectionDomainName = v31;
        if ( v31 )
          _o_wcstombs(v31, DnsICSDomainSuffix, v29);
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
            36,
            (unsigned int)WPP_bdbb9979ae51315066150bc8512c706a_Traceguids,
            15,
            (__int64)SharedConnectionDomainName);
        }
        do
          ++v19;
        while ( SharedConnectionDomainName[v19] );
        V2DhcpAppendOptionToMessage(a3, 0xFu, v19 + 1, SharedConnectionDomainName);
        v33 = GetProcessHeap();
        HeapFree(v33, 0, SharedConnectionDomainName);
      }
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_bdbb9979ae51315066150bc8512c706a_Traceguids, 255);
  }
  V2DhcpAppendOptionToMessage(a3, 0xFFu, 0, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_bdbb9979ae51315066150bc8512c706a_Traceguids);
  }
}

```

## disassembly

```asm
0x180004bd8  push    rbp
0x180004bda  push    rbx
0x180004bdb  push    rsi
0x180004bdc  push    rdi
0x180004bdd  push    r12
0x180004bdf  push    r13
0x180004be1  push    r14
0x180004be3  push    r15
0x180004be5  lea     rbp, [rsp-0Fh]
0x180004bea  sub     rsp, 0D8h
0x180004bf1  mov     rax, cs:__security_cookie
0x180004bf8  xor     rax, rsp
0x180004bfb  mov     [rbp+47h+var_50], rax
0x180004bff  movzx   edi, r9b
0x180004c03  mov     r14, r8
0x180004c06  mov     [rsp+110h+var_C8], dil
0x180004c0b  mov     rbx, rdx
0x180004c0e  mov     r12, rcx
0x180004c11  mov     rcx, cs:WPP_GLOBAL_Control
0x180004c18  lea     r13, WPP_GLOBAL_Control
0x180004c1f  cmp     rcx, r13
0x180004c22  jz      short loc_180004C53
0x180004c24  test    byte ptr [rcx+1Ch], 2
0x180004c28  jz      short loc_180004C53
0x180004c2a  cmp     byte ptr [rcx+19h], 6
0x180004c2e  jb      short loc_180004C53
0x180004c30  cmp     [rbp+47h+arg_20], 0
0x180004c34  lea     r8, WPP_bdbb9979ae51315066150bc8512c706a_Traceguids
0x180004c3b  mov     rcx, [rcx+10h]
0x180004c3f  mov     r9d, edi
0x180004c42  setnz   al
0x180004c45  mov     edx, 0Fh
0x180004c4a  mov     byte ptr [rsp+110h+var_F0], al
0x180004c4e  call    WPP_SF_Dc
0x180004c53  xor     edx, edx; Val
0x180004c55  mov     [rbp+47h+ppwstrAutoConfigUrl], 0
0x180004c5d  lea     rcx, [rbp+47h+var_A0]; void *
0x180004c61  lea     r8d, [rdx+50h]; Size
0x180004c65  call    memset_0
0x180004c6a  mov     rcx, [rbx+10h]; struct _NH_RCSOCKET *
0x180004c6e  call    ?NhQueryAddressSocket@@YAKPEAU_NH_RCSOCKET@@@Z; NhQueryAddressSocket(_NH_RCSOCKET *)
0x180004c73  mov     r15d, [rbx+28h]
0x180004c77  mov     esi, eax
0x180004c79  mov     dword ptr [rsp+110h+var_D0], eax
0x180004c7d  mov     dword ptr [rbp+47h+var_C0], r15d
0x180004c81  mov     rcx, cs:WPP_GLOBAL_Control
0x180004c88  cmp     rcx, r13
0x180004c8b  jz      short loc_180004CBD
0x180004c8d  test    byte ptr [rcx+1Ch], 2
0x180004c91  jz      short loc_180004CBD
0x180004c93  cmp     byte ptr [rcx+19h], 5
0x180004c97  jb      short loc_180004CBD
0x180004c99  mov     rcx, [rcx+10h]
0x180004c9d  lea     r8, WPP_bdbb9979ae51315066150bc8512c706a_Traceguids
0x180004ca4  mov     edx, 10h
0x180004ca9  mov     dword ptr [rsp+110h+var_F0], r15d
0x180004cae  mov     r9d, eax
0x180004cb1  call    WPP_SF_Dd
0x180004cb6  mov     rcx, cs:WPP_GLOBAL_Control
0x180004cbd  test    dil, dil
0x180004cc0  jnz     short loc_180004CCD
0x180004cc2  mov     [rbx+0F8h], esi
0x180004cc8  jmp     loc_180004D81
0x180004ccd  cmp     rcx, r13
0x180004cd0  jz      short loc_180004CFB
0x180004cd2  test    byte ptr [rcx+1Ch], 2
0x180004cd6  jz      short loc_180004CFB
0x180004cd8  cmp     byte ptr [rcx+19h], 5
0x180004cdc  jb      short loc_180004CFB
0x180004cde  mov     rcx, [rcx+10h]
0x180004ce2  lea     r8, WPP_bdbb9979ae51315066150bc8512c706a_Traceguids
0x180004ce9  mov     edx, 11h
0x180004cee  mov     dword ptr [rsp+110h+var_F0], edi
0x180004cf2  lea     r9d, [rdx+24h]
0x180004cf6  call    WPP_SF_Dd
0x180004cfb  lea     r9, [rsp+110h+var_C8]; unsigned __int8 *
0x180004d00  mov     r8b, 1; unsigned __int8
0x180004d03  mov     dl, 35h ; '5'; unsigned __int8
0x180004d05  mov     rcx, r14; struct _DHCP_OPTION **
0x180004d08  call    ?V2DhcpAppendOptionToMessage@@YAXPEAPEFAU_DHCP_OPTION@@EEQEAE@Z; V2DhcpAppendOptionToMessage(_DHCP_OPTION * *,uchar,uchar,uchar * const)
0x180004d0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180004d14  cmp     rcx, r13
0x180004d17  jz      short loc_180004D66
0x180004d19  test    byte ptr [rcx+1Ch], 2
0x180004d1d  jz      short loc_180004D66
0x180004d1f  cmp     byte ptr [rcx+19h], 5
0x180004d23  jb      short loc_180004D66
0x180004d25  movzx   r9d, [rsp+110h+var_D0+1]
0x180004d2b  mov     edx, 12h
0x180004d30  movzx   eax, [rsp+110h+var_D0+3]
0x180004d35  movzx   r8d, [rsp+110h+var_D0+2]
0x180004d3b  mov     rcx, [rcx+10h]
0x180004d3f  mov     [rsp+110h+var_D8], eax
0x180004d43  mov     [rsp+110h+var_E0], r8d
0x180004d48  lea     r8, WPP_bdbb9979ae51315066150bc8512c706a_Traceguids
0x180004d4f  mov     [rsp+110h+var_E8], r9d
0x180004d54  lea     r9d, [rdx+24h]
0x180004d58  movzx   r10d, sil
0x180004d5c  mov     dword ptr [rsp+110h+var_F0], r10d
0x180004d61  call    WPP_SF_ddddd
0x180004d66  lea     r9, [rsp+110h+var_D0]; unsigned __int8 *
0x180004d6b  mov     r8b, 4; unsigned __int8
0x180004d6e  mov     dl, 36h ; '6'; unsigned __int8
0x180004d70  mov     rcx, r14; struct _DHCP_OPTION **
0x180004d73  call    ?V2DhcpAppendOptionToMessage@@YAXPEAPEFAU_DHCP_OPTION@@EEQEAE@Z; V2DhcpAppendOptionToMessage(_DHCP_OPTION * *,uchar,uchar,uchar * const)
0x180004d78  mov     esi, dword ptr [rsp+110h+var_D0]
0x180004d7c  mov     dil, [rsp+110h+var_C8]
0x180004d81  cmp     dil, 6
0x180004d85  jz      loc_180005513
0x180004d8b  lea     rcx, ?NhLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180004d92  mov     [rsp+110h+var_C8], 4
0x180004d97  call    cs:__imp_EnterCriticalSection
0x180004d9e  nop     dword ptr [rax+rax+00h]
0x180004da3  lea     rcx, ?NhLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180004daa  call    cs:__imp_LeaveCriticalSection
0x180004db1  nop     dword ptr [rax+rax+00h]
0x180004db6  imul    ebx, [r12+4Ch], 3Ch ; '<'
0x180004dbc  mov     ecx, ebx; hostlong
0x180004dbe  call    cs:__imp_htonl
0x180004dc5  nop     dword ptr [rax+rax+00h]
0x180004dca  lea     ecx, [rbx+rbx*2]
0x180004dcd  mov     dword ptr [rbp+47h+var_B8], eax
0x180004dd0  shr     ecx, 2; hostlong
0x180004dd3  call    cs:__imp_htonl
0x180004dda  nop     dword ptr [rax+rax+00h]
0x180004ddf  shr     ebx, 1
0x180004de1  mov     ecx, ebx; hostlong
0x180004de3  mov     dword ptr [rbp+47h+var_BC], eax
0x180004de6  call    cs:__imp_htonl
0x180004ded  nop     dword ptr [rax+rax+00h]
0x180004df2  mov     r13d, eax
0x180004df5  mov     dword ptr [rbp+47h+var_A8], eax
0x180004df8  mov     rcx, cs:WPP_GLOBAL_Control
0x180004dff  lea     rbx, WPP_GLOBAL_Control
0x180004e06  cmp     rcx, rbx
0x180004e09  jz      short loc_180004E55
0x180004e0b  test    byte ptr [rcx+1Ch], 2
0x180004e0f  jz      short loc_180004E55
0x180004e11  cmp     byte ptr [rcx+19h], 5
0x180004e15  jb      short loc_180004E55
0x180004e17  movzx   r9d, [rbp+47h+var_C0+1]
0x180004e1c  mov     edx, 13h
0x180004e21  movzx   eax, [rbp+47h+var_C0+3]
0x180004e25  movzx   r8d, [rbp+47h+var_C0+2]
0x180004e2a  mov     rcx, [rcx+10h]
0x180004e2e  mov     [rsp+110h+var_D8], eax
0x180004e32  mov     [rsp+110h+var_E0], r8d
0x180004e37  lea     r8, WPP_bdbb9979ae51315066150bc8512c706a_Traceguids
0x180004e3e  mov     [rsp+110h+var_E8], r9d
0x180004e43  lea     r9d, [rdx-12h]
0x180004e47  movzx   r10d, r15b
0x180004e4b  mov     dword ptr [rsp+110h+var_F0], r10d
0x180004e50  call    WPP_SF_ddddd
0x180004e55  lea     r9, [rbp+47h+var_C0]; unsigned __int8 *
0x180004e59  mov     r8b, 4; unsigned __int8
0x180004e5c  mov     dl, 1; unsigned __int8
0x180004e5e  mov     rcx, r14; struct _DHCP_OPTION **
0x180004e61  call    ?V2DhcpAppendOptionToMessage@@YAXPEAPEFAU_DHCP_OPTION@@EEQEAE@Z; V2DhcpAppendOptionToMessage(_DHCP_OPTION * *,uchar,uchar,uchar * const)
0x180004e66  mov     rcx, cs:WPP_GLOBAL_Control
0x180004e6d  mov     r15b, 2
0x180004e70  cmp     rcx, rbx
0x180004e73  jz      short loc_180004EC7
0x180004e75  test    [rcx+1Ch], r15b
0x180004e79  jz      short loc_180004EC7
0x180004e7b  cmp     byte ptr [rcx+19h], 5
0x180004e7f  jb      short loc_180004EC7
0x180004e81  movzx   r9d, [rsp+110h+var_D0+1]
0x180004e87  mov     edx, 14h
0x180004e8c  movzx   eax, [rsp+110h+var_D0+3]
0x180004e91  movzx   r8d, [rsp+110h+var_D0+2]
0x180004e97  mov     rcx, [rcx+10h]
0x180004e9b  mov     [rsp+110h+var_D8], eax
0x180004e9f  mov     [rsp+110h+var_E0], r8d
0x180004ea4  movzx   r10d, sil
0x180004ea8  lea     rsi, WPP_bdbb9979ae51315066150bc8512c706a_Traceguids
0x180004eaf  mov     [rsp+110h+var_E8], r9d
0x180004eb4  mov     r8, rsi
0x180004eb7  lea     r9d, [rdx-11h]
0x180004ebb  mov     dword ptr [rsp+110h+var_F0], r10d
0x180004ec0  call    WPP_SF_ddddd
0x180004ec5  jmp     short loc_180004ECE
0x180004ec7  lea     rsi, WPP_bdbb9979ae51315066150bc8512c706a_Traceguids
0x180004ece  lea     r9, [rsp+110h+var_D0]; unsigned __int8 *
0x180004ed3  mov     r8b, 4; unsigned __int8
0x180004ed6  mov     dl, 3; unsigned __int8
0x180004ed8  mov     rcx, r14; struct _DHCP_OPTION **
0x180004edb  call    ?V2DhcpAppendOptionToMessage@@YAXPEAPEFAU_DHCP_OPTION@@EEQEAE@Z; V2DhcpAppendOptionToMessage(_DHCP_OPTION * *,uchar,uchar,uchar * const)
0x180004ee0  test    dil, dil
0x180004ee3  jz      loc_180005513
0x180004ee9  test    byte ptr [r12+78h], 1
0x180004eef  jz      loc_180004FB3
0x180004ef5  mov     rcx, cs:WPP_GLOBAL_Control
0x180004efc  lea     r12, WPP_GLOBAL_Control
0x180004f03  cmp     rcx, r12
0x180004f06  jz      short loc_180004F25
0x180004f08  test    [rcx+1Ch], r15b
0x180004f0c  jz      short loc_180004F25
0x180004f0e  cmp     byte ptr [rcx+19h], 4
0x180004f12  jb      short loc_180004F25
0x180004f14  mov     rcx, [rcx+10h]
0x180004f18  mov     edx, 15h
0x180004f1d  mov     r8, rsi
0x180004f20  call    WPP_SF_
0x180004f25  lea     rdx, [rbp+47h+var_C0]; unsigned int *
0x180004f29  mov     dword ptr [rbp+47h+var_C0], 14h
0x180004f30  lea     rcx, [rbp+47h+var_A0]; unsigned int *
0x180004f34  call    ?GetDnsServerList@@YAKPEAK0@Z; GetDnsServerList(ulong *,ulong *)
0x180004f39  test    eax, eax
0x180004f3b  jnz     short loc_180004F79
0x180004f3d  mov     rcx, cs:WPP_GLOBAL_Control
0x180004f44  mov     ebx, dword ptr [rbp+47h+var_C0]
0x180004f47  cmp     rcx, r12
0x180004f4a  jz      short loc_180004F6A
0x180004f4c  test    [rcx+1Ch], r15b
0x180004f50  jz      short loc_180004F6A
0x180004f52  cmp     byte ptr [rcx+19h], 4
0x180004f56  jb      short loc_180004F6A
0x180004f58  mov     rcx, [rcx+10h]
0x180004f5c  lea     edx, [rax+16h]
0x180004f5f  mov     r9d, ebx
0x180004f62  mov     r8, rsi
0x180004f65  call    WPP_SF_d
0x180004f6a  shl     bl, 2
0x180004f6d  lea     r9, [rbp+47h+var_A0]
0x180004f71  mov     r8b, bl
0x180004f74  jmp     loc_180005019
0x180004f79  mov     rcx, cs:WPP_GLOBAL_Control
0x180004f80  cmp     rcx, r12
0x180004f83  jz      loc_180005023
0x180004f89  test    [rcx+1Ch], r15b
0x180004f8d  jz      loc_180005023
0x180004f93  cmp     byte ptr [rcx+19h], 4
0x180004f97  jb      loc_180005023
0x180004f9d  mov     rcx, [rcx+10h]
0x180004fa1  mov     edx, 17h
0x180004fa6  mov     r9d, eax
0x180004fa9  mov     r8, rsi
0x180004fac  call    WPP_SF_d
0x180004fb1  jmp     short loc_180005023
0x180004fb3  mov     rcx, cs:WPP_GLOBAL_Control
0x180004fba  lea     r12, WPP_GLOBAL_Control
0x180004fc1  cmp     rcx, r12
0x180004fc4  jz      short loc_180005011
0x180004fc6  test    [rcx+1Ch], r15b
0x180004fca  jz      short loc_180005011
0x180004fcc  cmp     byte ptr [rcx+19h], 4
0x180004fd0  jb      short loc_180005011
0x180004fd2  movzx   r9d, [rsp+110h+var_D0+1]
0x180004fd8  mov     edx, 18h
0x180004fdd  movzx   eax, [rsp+110h+var_D0+3]
0x180004fe2  movzx   r8d, [rsp+110h+var_D0+2]
0x180004fe8  movzx   r10d, [rsp+110h+var_D0]
0x180004fee  mov     rcx, [rcx+10h]
0x180004ff2  mov     [rsp+110h+var_D8], eax
0x180004ff6  mov     [rsp+110h+var_E0], r8d
0x180004ffb  mov     r8, rsi
0x180004ffe  mov     [rsp+110h+var_E8], r9d
0x180005003  lea     r9d, [rdx-12h]
0x180005007  mov     dword ptr [rsp+110h+var_F0], r10d
0x18000500c  call    WPP_SF_ddddd
0x180005011  lea     r9, [rsp+110h+var_D0]; unsigned __int8 *
0x180005016  mov     r8b, 4; unsigned __int8
0x180005019  mov     dl, 6; unsigned __int8
0x18000501b  mov     rcx, r14; struct _DHCP_OPTION **
0x18000501e  call    ?V2DhcpAppendOptionToMessage@@YAXPEAPEFAU_DHCP_OPTION@@EEQEAE@Z; V2DhcpAppendOptionToMessage(_DHCP_OPTION * *,uchar,uchar,uchar * const)
0x180005023  call    ?NhIsWinsProxyEnabled@@YAEXZ; NhIsWinsProxyEnabled(void)
0x180005028  test    al, al
0x18000502a  jz      short loc_180005095
0x18000502c  mov     rcx, cs:WPP_GLOBAL_Control
0x180005033  cmp     rcx, r12
0x180005036  jz      short loc_180005083
0x180005038  test    [rcx+1Ch], r15b
0x18000503c  jz      short loc_180005083
0x18000503e  cmp     byte ptr [rcx+19h], 4
0x180005042  jb      short loc_180005083
0x180005044  movzx   r9d, [rsp+110h+var_D0+1]
0x18000504a  mov     edx, 19h
0x18000504f  movzx   eax, [rsp+110h+var_D0+3]
0x180005054  movzx   r8d, [rsp+110h+var_D0+2]
0x18000505a  movzx   r10d, [rsp+110h+var_D0]
0x180005060  mov     rcx, [rcx+10h]
0x180005064  mov     [rsp+110h+var_D8], eax
0x180005068  mov     [rsp+110h+var_E0], r8d
0x18000506d  mov     r8, rsi
0x180005070  mov     [rsp+110h+var_E8], r9d
0x180005075  lea     r9d, [rdx+13h]
0x180005079  mov     dword ptr [rsp+110h+var_F0], r10d
0x18000507e  call    WPP_SF_ddddd
0x180005083  lea     r9, [rsp+110h+var_D0]; unsigned __int8 *
0x180005088  mov     r8b, 4; unsigned __int8
0x18000508b  mov     dl, 2Ch ; ','; unsigned __int8
0x18000508d  mov     rcx, r14; struct _DHCP_OPTION **
0x180005090  call    ?V2DhcpAppendOptionToMessage@@YAXPEAPEFAU_DHCP_OPTION@@EEQEAE@Z; V2DhcpAppendOptionToMessage(_DHCP_OPTION * *,uchar,uchar,uchar * const)
0x180005095  mov     rcx, cs:WPP_GLOBAL_Control
0x18000509c  cmp     rcx, r12
0x18000509f  jz      short loc_1800050C7
0x1800050a1  test    [rcx+1Ch], r15b
0x1800050a5  jz      short loc_1800050C7
0x1800050a7  cmp     byte ptr [rcx+19h], 4
0x1800050ab  jb      short loc_1800050C7
  ... truncated ...
```
