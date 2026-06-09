# V2DhcpBuildReplyMessage(_V2_DHCP_INTERFACE *,_NH_BUFFER *,_DHCP_OPTION * *,uchar,uchar,_DHCP_OPTION * * const)

- ea: `0x180004a44`
- end: `0x180005387`
- name: `?V2DhcpBuildReplyMessage@@YAXPEAU_V2_DHCP_INTERFACE@@PEAU_NH_BUFFER@@PEAPEFAU_DHCP_OPTION@@EEQEAPEFAU3@@Z`
- size: `2371`
- prototype: `void(struct _V2_DHCP_INTERFACE *, struct _NH_BUFFER *, struct _DHCP_OPTION **, unsigned __int8, unsigned __int8, struct _DHCP_OPTION **const)`
- caller_count: `4`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003f10`
- `0x18004959c`
- `0x180085ff4`
- `0x180086904`

## callees

- `0x180004a44`
- `0x18000c110`
- `0x18000c750`
- `0x180012780`
- `0x18001ec08`
- `0x1800207b8`
- `0x180039464`
- `0x18003d854`
- `0x18003eb48`
- `0x18004e0c0`
- `0x18004ed64`
- `0x18005267c`
- `0x180055728`
- `0x18007c4bc`
- `0x180085da8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x1800050f1`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x180005190`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x180005233`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x180005268`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x1800050f1`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x180005190`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x180005233`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x180005268`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000512e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800051ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000523c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800052da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000512e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800051ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000523c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800052da`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000513f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000524d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000513f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000524d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800051f8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800052e8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800051f8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800052e8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004c03`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005221`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004c03`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005221`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004c10`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005275`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004c10`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005275`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005085`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005085`
- `WINHTTP!WinHttpDetectAutoProxyConfigUrl` at `0x180005053`
- `WINHTTP!WinHttpDetectAutoProxyConfigUrl` at `0x180005053`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180005202`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180005202`
- `WS2_32!__imp_htonl` at `0x180004c1e`
- `WS2_32!__imp_htonl` at `0x180004c2d`
- `WS2_32!__imp_htonl` at `0x180004c3a`
- `WS2_32!__imp_htonl` at `0x180004c1e`
- `WS2_32!__imp_htonl` at `0x180004c2d`
- `WS2_32!__imp_htonl` at `0x180004c3a`

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
0x180004a44  push    rbp
0x180004a46  push    rbx
0x180004a47  push    rsi
0x180004a48  push    rdi
0x180004a49  push    r12
0x180004a4b  push    r13
0x180004a4d  push    r14
0x180004a4f  push    r15
0x180004a51  lea     rbp, [rsp-0Fh]
0x180004a56  sub     rsp, 0D8h
0x180004a5d  mov     rax, cs:__security_cookie
0x180004a64  xor     rax, rsp
0x180004a67  mov     [rbp+47h+var_50], rax
0x180004a6b  movzx   edi, r9b
0x180004a6f  mov     r14, r8
0x180004a72  mov     [rsp+110h+var_C8], dil
0x180004a77  mov     rbx, rdx
0x180004a7a  mov     r12, rcx
0x180004a7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180004a84  lea     r13, WPP_GLOBAL_Control
0x180004a8b  cmp     rcx, r13
0x180004a8e  jz      short loc_180004ABF
0x180004a90  test    byte ptr [rcx+1Ch], 2
0x180004a94  jz      short loc_180004ABF
0x180004a96  cmp     byte ptr [rcx+19h], 6
0x180004a9a  jb      short loc_180004ABF
0x180004a9c  cmp     [rbp+47h+arg_20], 0
0x180004aa0  lea     r8, WPP_bdbb9979ae51315066150bc8512c706a_Traceguids
0x180004aa7  mov     rcx, [rcx+10h]
0x180004aab  mov     r9d, edi
0x180004aae  setnz   al
0x180004ab1  mov     edx, 0Fh
0x180004ab6  mov     byte ptr [rsp+110h+var_F0], al
0x180004aba  call    WPP_SF_Dc
0x180004abf  xor     edx, edx; Val
0x180004ac1  mov     [rbp+47h+ppwstrAutoConfigUrl], 0
0x180004ac9  lea     rcx, [rbp+47h+var_A0]; void *
0x180004acd  lea     r8d, [rdx+50h]; Size
0x180004ad1  call    memset_0
0x180004ad6  mov     rcx, [rbx+10h]; struct _NH_RCSOCKET *
0x180004ada  call    ?NhQueryAddressSocket@@YAKPEAU_NH_RCSOCKET@@@Z; NhQueryAddressSocket(_NH_RCSOCKET *)
0x180004adf  mov     r15d, [rbx+28h]
0x180004ae3  mov     esi, eax
0x180004ae5  mov     dword ptr [rsp+110h+var_D0], eax
0x180004ae9  mov     dword ptr [rbp+47h+var_C0], r15d
0x180004aed  mov     rcx, cs:WPP_GLOBAL_Control
0x180004af4  cmp     rcx, r13
0x180004af7  jz      short loc_180004B29
0x180004af9  test    byte ptr [rcx+1Ch], 2
0x180004afd  jz      short loc_180004B29
0x180004aff  cmp     byte ptr [rcx+19h], 5
0x180004b03  jb      short loc_180004B29
0x180004b05  mov     rcx, [rcx+10h]
0x180004b09  lea     r8, WPP_bdbb9979ae51315066150bc8512c706a_Traceguids
0x180004b10  mov     edx, 10h
0x180004b15  mov     dword ptr [rsp+110h+var_F0], r15d
0x180004b1a  mov     r9d, eax
0x180004b1d  call    WPP_SF_Dd
0x180004b22  mov     rcx, cs:WPP_GLOBAL_Control
0x180004b29  test    dil, dil
0x180004b2c  jnz     short loc_180004B39
0x180004b2e  mov     [rbx+0F8h], esi
0x180004b34  jmp     loc_180004BED
0x180004b39  cmp     rcx, r13
0x180004b3c  jz      short loc_180004B67
0x180004b3e  test    byte ptr [rcx+1Ch], 2
0x180004b42  jz      short loc_180004B67
0x180004b44  cmp     byte ptr [rcx+19h], 5
0x180004b48  jb      short loc_180004B67
0x180004b4a  mov     rcx, [rcx+10h]
0x180004b4e  lea     r8, WPP_bdbb9979ae51315066150bc8512c706a_Traceguids
0x180004b55  mov     edx, 11h
0x180004b5a  mov     dword ptr [rsp+110h+var_F0], edi
0x180004b5e  lea     r9d, [rdx+24h]
0x180004b62  call    WPP_SF_Dd
0x180004b67  lea     r9, [rsp+110h+var_C8]; unsigned __int8 *
0x180004b6c  mov     r8b, 1; unsigned __int8
0x180004b6f  mov     dl, 35h ; '5'; unsigned __int8
0x180004b71  mov     rcx, r14; struct _DHCP_OPTION **
0x180004b74  call    ?V2DhcpAppendOptionToMessage@@YAXPEAPEFAU_DHCP_OPTION@@EEQEAE@Z; V2DhcpAppendOptionToMessage(_DHCP_OPTION * *,uchar,uchar,uchar * const)
0x180004b79  mov     rcx, cs:WPP_GLOBAL_Control
0x180004b80  cmp     rcx, r13
0x180004b83  jz      short loc_180004BD2
0x180004b85  test    byte ptr [rcx+1Ch], 2
0x180004b89  jz      short loc_180004BD2
0x180004b8b  cmp     byte ptr [rcx+19h], 5
0x180004b8f  jb      short loc_180004BD2
0x180004b91  movzx   r9d, [rsp+110h+var_D0+1]
0x180004b97  mov     edx, 12h
0x180004b9c  movzx   eax, [rsp+110h+var_D0+3]
0x180004ba1  movzx   r8d, [rsp+110h+var_D0+2]
0x180004ba7  mov     rcx, [rcx+10h]
0x180004bab  mov     [rsp+110h+var_D8], eax
0x180004baf  mov     [rsp+110h+var_E0], r8d
0x180004bb4  lea     r8, WPP_bdbb9979ae51315066150bc8512c706a_Traceguids
0x180004bbb  mov     [rsp+110h+var_E8], r9d
0x180004bc0  lea     r9d, [rdx+24h]
0x180004bc4  movzx   r10d, sil
0x180004bc8  mov     dword ptr [rsp+110h+var_F0], r10d
0x180004bcd  call    WPP_SF_ddddd
0x180004bd2  lea     r9, [rsp+110h+var_D0]; unsigned __int8 *
0x180004bd7  mov     r8b, 4; unsigned __int8
0x180004bda  mov     dl, 36h ; '6'; unsigned __int8
0x180004bdc  mov     rcx, r14; struct _DHCP_OPTION **
0x180004bdf  call    ?V2DhcpAppendOptionToMessage@@YAXPEAPEFAU_DHCP_OPTION@@EEQEAE@Z; V2DhcpAppendOptionToMessage(_DHCP_OPTION * *,uchar,uchar,uchar * const)
0x180004be4  mov     esi, dword ptr [rsp+110h+var_D0]
0x180004be8  mov     dil, [rsp+110h+var_C8]
0x180004bed  cmp     dil, 6
0x180004bf1  jz      loc_1800052F0
0x180004bf7  lea     rcx, ?NhLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180004bfe  mov     [rsp+110h+var_C8], 4
0x180004c03  call    cs:__imp_EnterCriticalSection
0x180004c09  lea     rcx, ?NhLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180004c10  call    cs:__imp_LeaveCriticalSection
0x180004c16  imul    ebx, [r12+4Ch], 3Ch ; '<'
0x180004c1c  mov     ecx, ebx; hostlong
0x180004c1e  call    cs:__imp_htonl
0x180004c24  lea     ecx, [rbx+rbx*2]
0x180004c27  mov     dword ptr [rbp+47h+var_B8], eax
0x180004c2a  shr     ecx, 2; hostlong
0x180004c2d  call    cs:__imp_htonl
0x180004c33  shr     ebx, 1
0x180004c35  mov     ecx, ebx; hostlong
0x180004c37  mov     dword ptr [rbp+47h+var_BC], eax
0x180004c3a  call    cs:__imp_htonl
0x180004c40  mov     r13d, eax
0x180004c43  mov     dword ptr [rbp+47h+var_A8], eax
0x180004c46  mov     rcx, cs:WPP_GLOBAL_Control
0x180004c4d  lea     rbx, WPP_GLOBAL_Control
0x180004c54  cmp     rcx, rbx
0x180004c57  jz      short loc_180004CA3
0x180004c59  test    byte ptr [rcx+1Ch], 2
0x180004c5d  jz      short loc_180004CA3
0x180004c5f  cmp     byte ptr [rcx+19h], 5
0x180004c63  jb      short loc_180004CA3
0x180004c65  movzx   r9d, [rbp+47h+var_C0+1]
0x180004c6a  mov     edx, 13h
0x180004c6f  movzx   eax, [rbp+47h+var_C0+3]
0x180004c73  movzx   r8d, [rbp+47h+var_C0+2]
0x180004c78  mov     rcx, [rcx+10h]
0x180004c7c  mov     [rsp+110h+var_D8], eax
0x180004c80  mov     [rsp+110h+var_E0], r8d
0x180004c85  lea     r8, WPP_bdbb9979ae51315066150bc8512c706a_Traceguids
0x180004c8c  mov     [rsp+110h+var_E8], r9d
0x180004c91  lea     r9d, [rdx-12h]
0x180004c95  movzx   r10d, r15b
0x180004c99  mov     dword ptr [rsp+110h+var_F0], r10d
0x180004c9e  call    WPP_SF_ddddd
0x180004ca3  lea     r9, [rbp+47h+var_C0]; unsigned __int8 *
0x180004ca7  mov     r8b, 4; unsigned __int8
0x180004caa  mov     dl, 1; unsigned __int8
0x180004cac  mov     rcx, r14; struct _DHCP_OPTION **
0x180004caf  call    ?V2DhcpAppendOptionToMessage@@YAXPEAPEFAU_DHCP_OPTION@@EEQEAE@Z; V2DhcpAppendOptionToMessage(_DHCP_OPTION * *,uchar,uchar,uchar * const)
0x180004cb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180004cbb  mov     r15b, 2
0x180004cbe  cmp     rcx, rbx
0x180004cc1  jz      short loc_180004D15
0x180004cc3  test    [rcx+1Ch], r15b
0x180004cc7  jz      short loc_180004D15
0x180004cc9  cmp     byte ptr [rcx+19h], 5
0x180004ccd  jb      short loc_180004D15
0x180004ccf  movzx   r9d, [rsp+110h+var_D0+1]
0x180004cd5  mov     edx, 14h
0x180004cda  movzx   eax, [rsp+110h+var_D0+3]
0x180004cdf  movzx   r8d, [rsp+110h+var_D0+2]
0x180004ce5  mov     rcx, [rcx+10h]
0x180004ce9  mov     [rsp+110h+var_D8], eax
0x180004ced  mov     [rsp+110h+var_E0], r8d
0x180004cf2  movzx   r10d, sil
0x180004cf6  lea     rsi, WPP_bdbb9979ae51315066150bc8512c706a_Traceguids
0x180004cfd  mov     [rsp+110h+var_E8], r9d
0x180004d02  mov     r8, rsi
0x180004d05  lea     r9d, [rdx-11h]
0x180004d09  mov     dword ptr [rsp+110h+var_F0], r10d
0x180004d0e  call    WPP_SF_ddddd
0x180004d13  jmp     short loc_180004D1C
0x180004d15  lea     rsi, WPP_bdbb9979ae51315066150bc8512c706a_Traceguids
0x180004d1c  lea     r9, [rsp+110h+var_D0]; unsigned __int8 *
0x180004d21  mov     r8b, 4; unsigned __int8
0x180004d24  mov     dl, 3; unsigned __int8
0x180004d26  mov     rcx, r14; struct _DHCP_OPTION **
0x180004d29  call    ?V2DhcpAppendOptionToMessage@@YAXPEAPEFAU_DHCP_OPTION@@EEQEAE@Z; V2DhcpAppendOptionToMessage(_DHCP_OPTION * *,uchar,uchar,uchar * const)
0x180004d2e  test    dil, dil
0x180004d31  jz      loc_1800052F0
0x180004d37  test    byte ptr [r12+78h], 1
0x180004d3d  jz      loc_180004E01
0x180004d43  mov     rcx, cs:WPP_GLOBAL_Control
0x180004d4a  lea     r12, WPP_GLOBAL_Control
0x180004d51  cmp     rcx, r12
0x180004d54  jz      short loc_180004D73
0x180004d56  test    [rcx+1Ch], r15b
0x180004d5a  jz      short loc_180004D73
0x180004d5c  cmp     byte ptr [rcx+19h], 4
0x180004d60  jb      short loc_180004D73
0x180004d62  mov     rcx, [rcx+10h]
0x180004d66  mov     edx, 15h
0x180004d6b  mov     r8, rsi
0x180004d6e  call    WPP_SF_
0x180004d73  lea     rdx, [rbp+47h+var_C0]; unsigned int *
0x180004d77  mov     dword ptr [rbp+47h+var_C0], 14h
0x180004d7e  lea     rcx, [rbp+47h+var_A0]; unsigned int *
0x180004d82  call    ?GetDnsServerList@@YAKPEAK0@Z; GetDnsServerList(ulong *,ulong *)
0x180004d87  test    eax, eax
0x180004d89  jnz     short loc_180004DC7
0x180004d8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180004d92  mov     ebx, dword ptr [rbp+47h+var_C0]
0x180004d95  cmp     rcx, r12
0x180004d98  jz      short loc_180004DB8
0x180004d9a  test    [rcx+1Ch], r15b
0x180004d9e  jz      short loc_180004DB8
0x180004da0  cmp     byte ptr [rcx+19h], 4
0x180004da4  jb      short loc_180004DB8
0x180004da6  mov     rcx, [rcx+10h]
0x180004daa  lea     edx, [rax+16h]
0x180004dad  mov     r9d, ebx
0x180004db0  mov     r8, rsi
0x180004db3  call    WPP_SF_d
0x180004db8  shl     bl, 2
0x180004dbb  lea     r9, [rbp+47h+var_A0]
0x180004dbf  mov     r8b, bl
0x180004dc2  jmp     loc_180004E67
0x180004dc7  mov     rcx, cs:WPP_GLOBAL_Control
0x180004dce  cmp     rcx, r12
0x180004dd1  jz      loc_180004E71
0x180004dd7  test    [rcx+1Ch], r15b
0x180004ddb  jz      loc_180004E71
0x180004de1  cmp     byte ptr [rcx+19h], 4
0x180004de5  jb      loc_180004E71
0x180004deb  mov     rcx, [rcx+10h]
0x180004def  mov     edx, 17h
0x180004df4  mov     r9d, eax
0x180004df7  mov     r8, rsi
0x180004dfa  call    WPP_SF_d
0x180004dff  jmp     short loc_180004E71
0x180004e01  mov     rcx, cs:WPP_GLOBAL_Control
0x180004e08  lea     r12, WPP_GLOBAL_Control
0x180004e0f  cmp     rcx, r12
0x180004e12  jz      short loc_180004E5F
0x180004e14  test    [rcx+1Ch], r15b
0x180004e18  jz      short loc_180004E5F
0x180004e1a  cmp     byte ptr [rcx+19h], 4
0x180004e1e  jb      short loc_180004E5F
0x180004e20  movzx   r9d, [rsp+110h+var_D0+1]
0x180004e26  mov     edx, 18h
0x180004e2b  movzx   eax, [rsp+110h+var_D0+3]
0x180004e30  movzx   r8d, [rsp+110h+var_D0+2]
0x180004e36  movzx   r10d, [rsp+110h+var_D0]
0x180004e3c  mov     rcx, [rcx+10h]
0x180004e40  mov     [rsp+110h+var_D8], eax
0x180004e44  mov     [rsp+110h+var_E0], r8d
0x180004e49  mov     r8, rsi
0x180004e4c  mov     [rsp+110h+var_E8], r9d
0x180004e51  lea     r9d, [rdx-12h]
0x180004e55  mov     dword ptr [rsp+110h+var_F0], r10d
0x180004e5a  call    WPP_SF_ddddd
0x180004e5f  lea     r9, [rsp+110h+var_D0]; unsigned __int8 *
0x180004e64  mov     r8b, 4; unsigned __int8
0x180004e67  mov     dl, 6; unsigned __int8
0x180004e69  mov     rcx, r14; struct _DHCP_OPTION **
0x180004e6c  call    ?V2DhcpAppendOptionToMessage@@YAXPEAPEFAU_DHCP_OPTION@@EEQEAE@Z; V2DhcpAppendOptionToMessage(_DHCP_OPTION * *,uchar,uchar,uchar * const)
0x180004e71  call    ?NhIsWinsProxyEnabled@@YAEXZ; NhIsWinsProxyEnabled(void)
0x180004e76  test    al, al
0x180004e78  jz      short loc_180004EE3
0x180004e7a  mov     rcx, cs:WPP_GLOBAL_Control
0x180004e81  cmp     rcx, r12
0x180004e84  jz      short loc_180004ED1
0x180004e86  test    [rcx+1Ch], r15b
0x180004e8a  jz      short loc_180004ED1
0x180004e8c  cmp     byte ptr [rcx+19h], 4
0x180004e90  jb      short loc_180004ED1
0x180004e92  movzx   r9d, [rsp+110h+var_D0+1]
0x180004e98  mov     edx, 19h
0x180004e9d  movzx   eax, [rsp+110h+var_D0+3]
0x180004ea2  movzx   r8d, [rsp+110h+var_D0+2]
0x180004ea8  movzx   r10d, [rsp+110h+var_D0]
0x180004eae  mov     rcx, [rcx+10h]
0x180004eb2  mov     [rsp+110h+var_D8], eax
0x180004eb6  mov     [rsp+110h+var_E0], r8d
0x180004ebb  mov     r8, rsi
0x180004ebe  mov     [rsp+110h+var_E8], r9d
0x180004ec3  lea     r9d, [rdx+13h]
0x180004ec7  mov     dword ptr [rsp+110h+var_F0], r10d
0x180004ecc  call    WPP_SF_ddddd
0x180004ed1  lea     r9, [rsp+110h+var_D0]; unsigned __int8 *
0x180004ed6  mov     r8b, 4; unsigned __int8
0x180004ed9  mov     dl, 2Ch ; ','; unsigned __int8
0x180004edb  mov     rcx, r14; struct _DHCP_OPTION **
0x180004ede  call    ?V2DhcpAppendOptionToMessage@@YAXPEAPEFAU_DHCP_OPTION@@EEQEAE@Z; V2DhcpAppendOptionToMessage(_DHCP_OPTION * *,uchar,uchar,uchar * const)
0x180004ee3  mov     rcx, cs:WPP_GLOBAL_Control
0x180004eea  cmp     rcx, r12
0x180004eed  jz      short loc_180004F15
0x180004eef  test    [rcx+1Ch], r15b
0x180004ef3  jz      short loc_180004F15
0x180004ef5  cmp     byte ptr [rcx+19h], 4
0x180004ef9  jb      short loc_180004F15
0x180004efb  mov     rcx, [rcx+10h]
0x180004eff  mov     edx, 1Ah
0x180004f04  mov     r8, rsi
0x180004f07  mov     dword ptr [rsp+110h+var_F0], r13d
0x180004f0c  lea     r9d, [rdx+20h]
  ... truncated ...
```
