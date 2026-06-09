# BcpUdpSendAndReceive(ushort const *,ushort const *,uchar *,unsigned __int64,uchar *,unsigned __int64)

- ea: `0x18004b9cc`
- end: `0x18004c450`
- name: `?BcpUdpSendAndReceive@@YAJPEBG0PEAE_K12@Z`
- size: `2692`
- prototype: `__int64 __fastcall(wchar_t *, const unsigned __int16 *, char *, unsigned __int64, unsigned __int8 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800a5d3c`

## callees

- `0x180023800`
- `0x180046e6c`
- `0x18004b9cc`
- `0x18004c458`
- `0x18004c678`
- `0x1800f5498`
- `0x1800f5c74`
- `0x1800f7030`
- `0x1800f71d4`
- `0x1800f72e4`
- `0x1800f73f8`
- `0x18011efce`
- `0x18011f010`

## import_xrefs

- `msvcrt!wcstombs_s` at `0x18004bbad`
- `msvcrt!wcstombs_s` at `0x18004bc4b`
- `msvcrt!wcstombs_s` at `0x18004bbad`
- `msvcrt!wcstombs_s` at `0x18004bc4b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004bb80`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004bbe6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004bc26`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004bc82`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004bcbf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004bcd4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004bd4b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004bd60`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004bd7c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004bea3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004beb8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004bedf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004bf74`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004bf89`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c02f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c044`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c088`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c09d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c17d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c192`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c1d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c25e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c273`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c330`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c345`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c389`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c39e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c3fb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c410`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004bb80`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004bbe6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004bc26`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004bc82`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004bcbf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004bcd4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004bd4b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004bd60`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004bd7c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004bea3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004beb8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004bedf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004bf74`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004bf89`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c02f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c044`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c088`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c09d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c17d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c192`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c1d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c25e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c273`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c330`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c345`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c389`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c39e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c3fb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c410`
- `WS2_32!inet_pton` at `0x18004bdb5`
- `WS2_32!inet_pton` at `0x18004bdf9`
- `WS2_32!inet_pton` at `0x18004bdb5`
- `WS2_32!inet_pton` at `0x18004bdf9`
- `WS2_32!__imp_bind` at `0x18004be4c`
- `WS2_32!__imp_bind` at `0x18004be4c`
- `WS2_32!__imp_closesocket` at `0x18004bf52`
- `WS2_32!__imp_closesocket` at `0x18004c00d`
- `WS2_32!__imp_closesocket` at `0x18004c066`
- `WS2_32!__imp_closesocket` at `0x18004c15b`
- `WS2_32!__imp_closesocket` at `0x18004c1b4`
- `WS2_32!__imp_closesocket` at `0x18004c23c`
- `WS2_32!__imp_closesocket` at `0x18004c30e`
- `WS2_32!__imp_closesocket` at `0x18004c367`
- `WS2_32!__imp_closesocket` at `0x18004c3d9`
- `WS2_32!__imp_closesocket` at `0x18004bf52`
- `WS2_32!__imp_closesocket` at `0x18004c00d`
- `WS2_32!__imp_closesocket` at `0x18004c066`
- `WS2_32!__imp_closesocket` at `0x18004c15b`
- `WS2_32!__imp_closesocket` at `0x18004c1b4`
- `WS2_32!__imp_closesocket` at `0x18004c23c`
- `WS2_32!__imp_closesocket` at `0x18004c30e`
- `WS2_32!__imp_closesocket` at `0x18004c367`
- `WS2_32!__imp_closesocket` at `0x18004c3d9`
- `WS2_32!__imp_htons` at `0x18004bdcd`
- `WS2_32!__imp_htons` at `0x18004be11`
- `WS2_32!__imp_htons` at `0x18004bdcd`
- `WS2_32!__imp_htons` at `0x18004be11`
- `WS2_32!__imp_recvfrom` at `0x18004c2a9`
- `WS2_32!__imp_recvfrom` at `0x18004c2a9`
- `WS2_32!__imp_sendto` at `0x18004bfbb`
- `WS2_32!__imp_sendto` at `0x18004bfbb`
- `WS2_32!__imp_setsockopt` at `0x18004c109`
- `WS2_32!__imp_setsockopt` at `0x18004c109`
- `WS2_32!__imp_socket` at `0x18004be2c`
- `WS2_32!__imp_socket` at `0x18004be2c`
- `WS2_32!__imp_WSAGetLastError` at `0x18004bd16`
- `WS2_32!__imp_WSAGetLastError` at `0x18004be61`
- `WS2_32!__imp_WSAGetLastError` at `0x18004bfd0`
- `WS2_32!__imp_WSAGetLastError` at `0x18004c11e`
- `WS2_32!__imp_WSAGetLastError` at `0x18004c2be`
- `WS2_32!__imp_WSAGetLastError` at `0x18004bd16`
- `WS2_32!__imp_WSAGetLastError` at `0x18004be61`
- `WS2_32!__imp_WSAGetLastError` at `0x18004bfd0`
- `WS2_32!__imp_WSAGetLastError` at `0x18004c11e`
- `WS2_32!__imp_WSAGetLastError` at `0x18004c2be`
- `WS2_32!__imp_WSAStartup` at `0x18004bd05`
- `WS2_32!__imp_WSAStartup` at `0x18004bd05`
- `WS2_32!__imp_WSACleanup` at `0x18004be8e`
- `WS2_32!__imp_WSACleanup` at `0x18004beca`
- `WS2_32!__imp_WSACleanup` at `0x18004bf5f`
- `WS2_32!__imp_WSACleanup` at `0x18004c01a`
- `WS2_32!__imp_WSACleanup` at `0x18004c073`
- `WS2_32!__imp_WSACleanup` at `0x18004c168`
- `WS2_32!__imp_WSACleanup` at `0x18004c1c1`
- `WS2_32!__imp_WSACleanup` at `0x18004c249`
- `WS2_32!__imp_WSACleanup` at `0x18004c31b`
- `WS2_32!__imp_WSACleanup` at `0x18004c374`
- `WS2_32!__imp_WSACleanup` at `0x18004c3e6`
- `WS2_32!__imp_WSACleanup` at `0x18004be8e`
- `WS2_32!__imp_WSACleanup` at `0x18004beca`
- `WS2_32!__imp_WSACleanup` at `0x18004bf5f`
- `WS2_32!__imp_WSACleanup` at `0x18004c01a`
- `WS2_32!__imp_WSACleanup` at `0x18004c073`
- `WS2_32!__imp_WSACleanup` at `0x18004c168`
- `WS2_32!__imp_WSACleanup` at `0x18004c1c1`
- `WS2_32!__imp_WSACleanup` at `0x18004c249`
- `WS2_32!__imp_WSACleanup` at `0x18004c31b`
- `WS2_32!__imp_WSACleanup` at `0x18004c374`
- `WS2_32!__imp_WSACleanup` at `0x18004c3e6`

## string_xrefs

- `0x18004baaf`: `onecore\base\ngscb\cornerstone\nkpcommonlib\network.cpp`
- `0x18004bb2a`: `onecore\base\ngscb\cornerstone\nkpcommonlib\network.cpp`
- `0x18004bb66`: `onecore\base\ngscb\cornerstone\nkpcommonlib\network.cpp`
- `0x18004bbcd`: `onecore\base\ngscb\cornerstone\nkpcommonlib\network.cpp`
- `0x18004bc0c`: `onecore\base\ngscb\cornerstone\nkpcommonlib\network.cpp`
- `0x18004bc68`: `onecore\base\ngscb\cornerstone\nkpcommonlib\network.cpp`
- `0x18004bca5`: `onecore\base\ngscb\cornerstone\nkpcommonlib\network.cpp`
- `0x18004bd30`: `onecore\base\ngscb\cornerstone\nkpcommonlib\network.cpp`
- `0x18004be7b`: `onecore\base\ngscb\cornerstone\nkpcommonlib\network.cpp`
- `0x18004bf31`: `onecore\base\ngscb\cornerstone\nkpcommonlib\network.cpp`
- `0x18004bfea`: `onecore\base\ngscb\cornerstone\nkpcommonlib\network.cpp`
- `0x18004c138`: `onecore\base\ngscb\cornerstone\nkpcommonlib\network.cpp`
- `0x18004c21a`: `onecore\base\ngscb\cornerstone\nkpcommonlib\network.cpp`
- `0x18004c2eb`: `onecore\base\ngscb\cornerstone\nkpcommonlib\network.cpp`

## pseudocode

```c
__int64 __fastcall BcpUdpSendAndReceive(
        wchar_t *a1,
        const unsigned __int16 *a2,
        char *a3,
        unsigned __int64 a4,
        unsigned __int8 *a5,
        unsigned __int64 a6)
{
  BclStageOutput *v9; // rcx
  BclStageOutput *v10; // rcx
  int v11; // eax
  unsigned __int64 v12; // r10
  unsigned int v13; // ebx
  __int64 v14; // r9
  __int64 v15; // rdx
  size_t v16; // r15
  SIZE_T v17; // r14
  int v18; // eax
  size_t v19; // r13
  SIZE_T v20; // rsi
  HLOCAL v21; // rbx
  HLOCAL v22; // rdi
  unsigned int Error; // eax
  int v24; // esi
  unsigned int v25; // eax
  int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // eax
  int v29; // eax
  unsigned int v30; // eax
  unsigned int v31; // esi
  int MaxCountInBytes; // [rsp+20h] [rbp-E0h]
  int MaxCountInBytesa; // [rsp+20h] [rbp-E0h]
  unsigned int MaxCountInBytesb; // [rsp+20h] [rbp-E0h]
  unsigned int MaxCountInBytesc; // [rsp+20h] [rbp-E0h]
  unsigned int MaxCountInBytesd; // [rsp+20h] [rbp-E0h]
  unsigned int MaxCountInBytese; // [rsp+20h] [rbp-E0h]
  SOCKET s; // [rsp+30h] [rbp-D0h] BYREF
  int len; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v41; // [rsp+40h] [rbp-C0h] BYREF
  size_t v42; // [rsp+48h] [rbp-B8h] BYREF
  int pAddrBuf; // [rsp+50h] [rbp-B0h] BYREF
  int v44; // [rsp+54h] [rbp-ACh] BYREF
  size_t PtNumOfCharConverted; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t *Src; // [rsp+60h] [rbp-A0h] BYREF
  char v47; // [rsp+69h] [rbp-97h]
  char *buf; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v49[8]; // [rsp+78h] [rbp-88h] BYREF
  HLOCAL hMem; // [rsp+80h] [rbp-80h] BYREF
  HLOCAL v51; // [rsp+88h] [rbp-78h] BYREF
  char *v52; // [rsp+90h] [rbp-70h]
  SOCKET *p_s; // [rsp+98h] [rbp-68h]
  char v54; // [rsp+A0h] [rbp-60h]
  sockaddr name; // [rsp+A8h] [rbp-58h] BYREF
  struct sockaddr to; // [rsp+B8h] [rbp-48h] BYREF
  struct sockaddr from; // [rsp+C8h] [rbp-38h] BYREF
  WSAData WSAData; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  v41 = a4;
  buf = a3;
  Src = a1;
  v52 = (char *)a5;
  BclStageOutput::BclStageOutput((BclStageOutput *)v49, 12);
  BclStageOutput::LogFormat((BclStageOutput *)v49, L"RequestPacketSize", L"0x%x", a4);
  BclStageOutput::LogString(v9, L"SourceIpAddress", a1);
  BclStageOutput::LogString(v10, L"DestinationIpAddress", a2);
  v42 = 0;
  v11 = StringCchLengthW(a1, 0x7FFFFFFFu, &v42);
  v13 = v11;
  if ( v11 < 0 )
  {
    v14 = (unsigned int)v11;
    v15 = 31;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\base\\ngscb\\cornerstone\\nkpcommonlib\\network.cpp",
      (const char *)v14,
      MaxCountInBytes);
    goto LABEL_109;
  }
  v16 = v42;
  v17 = v42 + 1;
  if ( v42 + 1 < v42 )
  {
    v15 = 32;
LABEL_5:
    v13 = -2147024362;
    v14 = 2147942934LL;
    goto LABEL_6;
  }
  v42 = 0;
  v18 = StringCchLengthW(a2, v12, &v42);
  v13 = v18;
  if ( v18 < 0 )
  {
    v14 = (unsigned int)v18;
    v15 = 34;
    goto LABEL_6;
  }
  v19 = v42;
  v20 = v42 + 1;
  if ( v42 + 1 < v42 )
  {
    v15 = 35;
    goto LABEL_5;
  }
  wil::make_unique_hlocal_nothrow<char [0]>(&hMem, v17);
  v21 = hMem;
  if ( !hMem )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x25,
      (unsigned int)"onecore\\base\\ngscb\\cornerstone\\nkpcommonlib\\network.cpp",
      (const char *)0x8007000ELL,
      MaxCountInBytes);
LABEL_13:
    v13 = -2147024882;
    goto LABEL_109;
  }
  wil::make_unique_hlocal_nothrow<char [0]>(&v51, v20);
  v22 = v51;
  if ( !v51 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x27,
      (unsigned int)"onecore\\base\\ngscb\\cornerstone\\nkpcommonlib\\network.cpp",
      (const char *)0x8007000ELL,
      MaxCountInBytes);
    if ( v21 )
      LocalFree(v21);
    goto LABEL_13;
  }
  PtNumOfCharConverted = 0;
  if ( !wcstombs_s(&PtNumOfCharConverted, (char *)v21, v17, Src, v16) )
  {
    if ( PtNumOfCharConverted != v17 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2B,
        (unsigned int)"onecore\\base\\ngscb\\cornerstone\\nkpcommonlib\\network.cpp",
        (const char *)0x80070057LL,
        MaxCountInBytesa);
      if ( v22 )
        LocalFree(v22);
      goto LABEL_33;
    }
    if ( wcstombs_s(&PtNumOfCharConverted, (char *)v22, v20, a2, v19) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2D,
        (unsigned int)"onecore\\base\\ngscb\\cornerstone\\nkpcommonlib\\network.cpp",
        (const char *)0x80070057LL,
        MaxCountInBytesb);
      if ( v22 )
        LocalFree(v22);
      goto LABEL_33;
    }
    if ( PtNumOfCharConverted != v20 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2E,
        (unsigned int)"onecore\\base\\ngscb\\cornerstone\\nkpcommonlib\\network.cpp",
        (const char *)0x80070057LL,
        MaxCountInBytesb);
      if ( v22 )
        LocalFree(v22);
      goto LABEL_33;
    }
    memset_0(&WSAData, 0, sizeof(WSAData));
    if ( WSAStartup(0x202u, &WSAData) == -1 )
    {
      Error = WSAGetLastError();
      if ( Error )
      {
        v24 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x34,
                (unsigned int)"onecore\\base\\ngscb\\cornerstone\\nkpcommonlib\\network.cpp",
                (const char *)Error,
                MaxCountInBytesb);
        if ( v22 )
          LocalFree(v22);
        if ( v21 )
          LocalFree(v21);
LABEL_42:
        v13 = v24;
        goto LABEL_109;
      }
      if ( v22 )
        LocalFree(v22);
      goto LABEL_106;
    }
    v47 = 1;
    name = 0;
    name.sa_family = 2;
    pAddrBuf = 0;
    inet_pton(2, (PCSTR)v21, &pAddrBuf);
    *(_DWORD *)&name.sa_data[2] = pAddrBuf;
    *(_WORD *)name.sa_data = htons(0x44u);
    to = 0;
    to.sa_family = 2;
    v44 = 0;
    inet_pton(2, (PCSTR)v22, &v44);
    *(_DWORD *)&to.sa_data[2] = v44;
    *(_WORD *)to.sa_data = htons(0x43u);
    s = socket(2, 2, 17);
    if ( bind(s, &name, 16) == -1 )
    {
      v25 = WSAGetLastError();
      if ( v25 )
      {
        v24 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x4D,
                (unsigned int)"onecore\\base\\ngscb\\cornerstone\\nkpcommonlib\\network.cpp",
                (const char *)v25,
                MaxCountInBytesb);
        WSACleanup();
        if ( v22 )
          LocalFree(v22);
        if ( v21 )
          LocalFree(v21);
        goto LABEL_42;
      }
      WSACleanup();
      if ( v22 )
        LocalFree(v22);
      goto LABEL_106;
    }
    p_s = &s;
    v54 = 1;
    BclStageOutput::BclStageOutput((BclStageOutput *)&v42, 13);
    len = 0;
    v26 = UIntPtrToInt(v41, &len);
    v24 = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x58,
        (unsigned int)"onecore\\base\\ngscb\\cornerstone\\nkpcommonlib\\network.cpp",
        (const char *)(unsigned int)v26,
        MaxCountInBytesb);
      BclStageOutput::~BclStageOutput((BclStageOutput *)&v42);
      closesocket(s);
      WSACleanup();
      if ( v22 )
        LocalFree(v22);
      if ( v21 )
        LocalFree(v21);
      goto LABEL_42;
    }
    if ( sendto(s, buf, len, 0, &to, 16) == -1 )
    {
      v27 = WSAGetLastError();
      if ( v27 )
      {
        v24 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x5C,
                (unsigned int)"onecore\\base\\ngscb\\cornerstone\\nkpcommonlib\\network.cpp",
                (const char *)v27,
                MaxCountInBytesc);
        BclStageOutput::~BclStageOutput((BclStageOutput *)&v42);
        closesocket(s);
        WSACleanup();
        if ( v22 )
          LocalFree(v22);
        if ( v21 )
          LocalFree(v21);
        goto LABEL_42;
      }
      BclStageOutput::~BclStageOutput((BclStageOutput *)&v42);
      closesocket(s);
      WSACleanup();
      if ( v22 )
        LocalFree(v22);
      if ( v21 )
        LocalFree(v21);
LABEL_108:
      v13 = 0;
      goto LABEL_109;
    }
    BclStageOutput::~BclStageOutput((BclStageOutput *)&v42);
    BclStageOutput::BclStageOutput((BclStageOutput *)&v41, 14);
    Src = (wchar_t *)15000;
    BclStageOutput::LogFormat((BclStageOutput *)&v41, L"ReceiveTimeout", L"%u");
    if ( setsockopt(s, 0xFFFF, 4102, (const char *)&Src, 8) == -1 )
    {
      v28 = WSAGetLastError();
      if ( v28 )
      {
        v24 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x6B,
                (unsigned int)"onecore\\base\\ngscb\\cornerstone\\nkpcommonlib\\network.cpp",
                (const char *)v28,
                MaxCountInBytesd);
        BclStageOutput::~BclStageOutput((BclStageOutput *)&v41);
        closesocket(s);
        WSACleanup();
        if ( v22 )
          LocalFree(v22);
        if ( v21 )
          LocalFree(v21);
        goto LABEL_42;
      }
      BclStageOutput::~BclStageOutput((BclStageOutput *)&v41);
      closesocket(s);
      WSACleanup();
      if ( v22 )
        LocalFree(v22);
      goto LABEL_101;
    }
    from = 0;
    LODWORD(buf) = 16;
    len = 0;
    v29 = UIntPtrToInt(a6, &len);
    v24 = v29;
    if ( v29 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x72,
        (unsigned int)"onecore\\base\\ngscb\\cornerstone\\nkpcommonlib\\network.cpp",
        (const char *)(unsigned int)v29,
        MaxCountInBytesd);
      BclStageOutput::~BclStageOutput((BclStageOutput *)&v41);
      closesocket(s);
      WSACleanup();
      if ( v22 )
        LocalFree(v22);
      if ( v21 )
        LocalFree(v21);
      goto LABEL_42;
    }
    v30 = recvfrom(s, v52, len, 0, &from, (int *)&buf);
    if ( v30 != -1 )
    {
      BclStageOutput::LogFormat((BclStageOutput *)&v41, L"ResponsePacketSize", L"0x%x", v30);
      BclStageOutput::~BclStageOutput((BclStageOutput *)&v41);
      closesocket(s);
      WSACleanup();
      if ( v22 )
        LocalFree(v22);
LABEL_106:
      if ( v21 )
        LocalFree(v21);
      goto LABEL_108;
    }
    v31 = WSAGetLastError();
    if ( v31 == 10060 )
    {
      BclSaveKnownFailure(2);
    }
    else if ( !v31 )
    {
      BclStageOutput::~BclStageOutput((BclStageOutput *)&v41);
      closesocket(s);
      WSACleanup();
      if ( v22 )
        LocalFree(v22);
LABEL_101:
      if ( v21 )
        LocalFree(v21);
      goto LABEL_108;
    }
    v24 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x7C,
            (unsigned int)"onecore\\base\\ngscb\\cornerstone\\nkpcommonlib\\network.cpp",
            (const char *)v31,
            MaxCountInBytese);
    BclStageOutput::~BclStageOutput((BclStageOutput *)&v41);
    closesocket(s);
    WSACleanup();
    if ( v22 )
      LocalFree(v22);
    if ( v21 )
      LocalFree(v21);
    goto LABEL_42;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2A,
    (unsigned int)"onecore\\base\\ngscb\\cornerstone\\nkpcommonlib\\network.cpp",
    (const char *)0x80070057LL,
    MaxCountInBytesa);
  if ( v22 )
    LocalFree(v22);
LABEL_33:
  if ( v21 )
    LocalFree(v21);
  v13 = -2147024809;
LABEL_109:
  BclStageOutput::~BclStageOutput((BclStageOutput *)v49);
  return v13;
}

```

## disassembly

```asm
0x18004b9cc  push    rbp
0x18004b9ce  push    rbx
0x18004b9cf  push    rsi
0x18004b9d0  push    rdi
0x18004b9d1  push    r12
0x18004b9d3  push    r13
0x18004b9d5  push    r14
0x18004b9d7  push    r15
0x18004b9d9  lea     rbp, [rsp-198h]
0x18004b9e1  sub     rsp, 298h
0x18004b9e8  mov     rax, cs:__security_cookie
0x18004b9ef  xor     rax, rsp
0x18004b9f2  mov     [rbp+1D0h+var_50], rax
0x18004b9f9  mov     rdi, r9
0x18004b9fc  mov     [rsp+2D0h+var_290], r9
0x18004ba01  mov     [rsp+2D0h+buf], r8
0x18004ba06  mov     r12, rdx
0x18004ba09  mov     rbx, rcx
0x18004ba0c  mov     [rsp+2D0h+Src], rcx
0x18004ba11  mov     rax, [rbp+1D0h+arg_20]
0x18004ba18  mov     [rbp+1D0h+var_240], rax
0x18004ba1c  mov     edx, 0Ch
0x18004ba21  lea     rcx, [rsp+2D0h+var_258]
0x18004ba26  call    ??0BclStageOutput@@QEAA@W4BCL_STAGE_ID@@@Z; BclStageOutput::BclStageOutput(BCL_STAGE_ID)
0x18004ba2b  nop
0x18004ba2c  mov     r9, rdi
0x18004ba2f  lea     r8, a0xX; "0x%x"
0x18004ba36  lea     rdx, aRequestpackets; "RequestPacketSize"
0x18004ba3d  lea     rcx, [rsp+2D0h+var_258]; this
0x18004ba42  call    ?LogFormat@BclStageOutput@@QEAAXPEBG0ZZ; BclStageOutput::LogFormat(ushort const *,ushort const *,...)
0x18004ba47  mov     r8, rbx; unsigned __int16 *
0x18004ba4a  lea     rdx, aSourceipaddres; "SourceIpAddress"
0x18004ba51  call    ?LogString@BclStageOutput@@QEAAXPEBG0@Z; BclStageOutput::LogString(ushort const *,ushort const *)
0x18004ba56  mov     r8, r12; unsigned __int16 *
0x18004ba59  lea     rdx, aDestinationipa; "DestinationIpAddress"
0x18004ba60  call    ?LogString@BclStageOutput@@QEAAXPEBG0@Z; BclStageOutput::LogString(ushort const *,ushort const *)
0x18004ba65  mov     [rsp+2D0h+var_288], 0
0x18004ba6e  lea     r8, [rsp+2D0h+var_288]; unsigned __int64 *
0x18004ba73  mov     r10d, 7FFFFFFFh
0x18004ba79  mov     edx, r10d; unsigned __int64
0x18004ba7c  mov     rcx, rbx; unsigned __int16 *
0x18004ba7f  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18004ba84  mov     ebx, eax
0x18004ba86  test    eax, eax
0x18004ba88  jns     short loc_18004BA94
0x18004ba8a  mov     r9d, eax
0x18004ba8d  mov     edx, 1Fh
0x18004ba92  jmp     short loc_18004BAAF
0x18004ba94  mov     r15, [rsp+2D0h+var_288]
0x18004ba99  lea     r14, [r15+1]
0x18004ba9d  cmp     r14, r15
0x18004baa0  jnb     short loc_18004BAC7
0x18004baa2  mov     edx, 20h ; ' '; void *
0x18004baa7  mov     ebx, 80070216h
0x18004baac  mov     r9d, ebx; char *
0x18004baaf  lea     r8, aOnecoreBaseNgs_4; "onecore\\base\\ngscb\\cornerstone\\nkpc"...
0x18004bab6  mov     rcx, [rbp+1D8h]; this
0x18004babd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004bac2  jmp     loc_18004C420
0x18004bac7  mov     [rsp+2D0h+var_288], 0
0x18004bad0  lea     r8, [rsp+2D0h+var_288]; unsigned __int64 *
0x18004bad5  mov     rdx, r10; unsigned __int64
0x18004bad8  mov     rcx, r12; unsigned __int16 *
0x18004badb  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18004bae0  mov     ebx, eax
0x18004bae2  test    eax, eax
0x18004bae4  jns     short loc_18004BAF0
0x18004bae6  mov     r9d, eax
0x18004bae9  mov     edx, 22h ; '"'
0x18004baee  jmp     short loc_18004BAAF
0x18004baf0  mov     r13, [rsp+2D0h+var_288]
0x18004baf5  lea     rsi, [r13+1]
0x18004baf9  cmp     rsi, r13
0x18004bafc  jnb     short loc_18004BB05
0x18004bafe  mov     edx, 23h ; '#'
0x18004bb03  jmp     short loc_18004BAA7
0x18004bb05  mov     rdx, r14
0x18004bb08  lea     rcx, [rbp+1D0h+hMem]
0x18004bb0c  call    ??$make_unique_hlocal_nothrow@$$BY0A@D@wil@@YA?AV?$unique_ptr@$$BY0A@DU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<char [0]>(unsigned __int64)
0x18004bb11  nop
0x18004bb12  mov     rbx, [rbp+1D0h+hMem]
0x18004bb16  test    rbx, rbx
0x18004bb19  jnz     short loc_18004BB41
0x18004bb1b  mov     rcx, [rbp+1D8h]; this
0x18004bb22  mov     edi, 8007000Eh
0x18004bb27  mov     r9d, edi; char *
0x18004bb2a  lea     r8, aOnecoreBaseNgs_4; "onecore\\base\\ngscb\\cornerstone\\nkpc"...
0x18004bb31  lea     edx, [rbx+25h]; void *
0x18004bb34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004bb39  nop
0x18004bb3a  mov     ebx, edi
0x18004bb3c  jmp     loc_18004C420
0x18004bb41  mov     rdx, rsi
0x18004bb44  lea     rcx, [rbp+1D0h+var_248]
0x18004bb48  call    ??$make_unique_hlocal_nothrow@$$BY0A@D@wil@@YA?AV?$unique_ptr@$$BY0A@DU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<char [0]>(unsigned __int64)
0x18004bb4d  nop
0x18004bb4e  mov     rdi, [rbp+1D0h+var_248]
0x18004bb52  test    rdi, rdi
0x18004bb55  jnz     short loc_18004BB8F
0x18004bb57  mov     rcx, [rbp+1D8h]; this
0x18004bb5e  mov     edi, 8007000Eh
0x18004bb63  mov     r9d, edi; char *
0x18004bb66  lea     r8, aOnecoreBaseNgs_4; "onecore\\base\\ngscb\\cornerstone\\nkpc"...
0x18004bb6d  mov     edx, 27h ; '''; void *
0x18004bb72  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004bb77  nop
0x18004bb78  test    rbx, rbx
0x18004bb7b  jz      short loc_18004BB8D
0x18004bb7d  mov     rcx, rbx; hMem
0x18004bb80  call    cs:__imp_LocalFree
0x18004bb87  nop     dword ptr [rax+rax+00h]
0x18004bb8c  nop
0x18004bb8d  jmp     short loc_18004BB3A
0x18004bb8f  mov     [rsp+2D0h+PtNumOfCharConverted], 0
0x18004bb98  mov     [rsp+2D0h+MaxCountInBytes], r15; int
0x18004bb9d  mov     r9, [rsp+2D0h+Src]; Src
0x18004bba2  mov     r8, r14; DstSizeInBytes
0x18004bba5  mov     rdx, rbx; Dst
0x18004bba8  lea     rcx, [rsp+2D0h+PtNumOfCharConverted]; PtNumOfCharConverted
0x18004bbad  call    cs:__imp_wcstombs_s
0x18004bbb4  nop     dword ptr [rax+rax+00h]
0x18004bbb9  xor     r15d, r15d
0x18004bbbc  test    eax, eax
0x18004bbbe  jz      short loc_18004BBF8
0x18004bbc0  mov     rcx, [rbp+1D8h]; this
0x18004bbc7  mov     r9d, 80070057h; char *
0x18004bbcd  lea     r8, aOnecoreBaseNgs_4; "onecore\\base\\ngscb\\cornerstone\\nkpc"...
0x18004bbd4  lea     edx, [r15+2Ah]; void *
0x18004bbd8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004bbdd  nop
0x18004bbde  test    rdi, rdi
0x18004bbe1  jz      short loc_18004BBF3
0x18004bbe3  mov     rcx, rdi; hMem
0x18004bbe6  call    cs:__imp_LocalFree
0x18004bbed  nop     dword ptr [rax+rax+00h]
0x18004bbf2  nop
0x18004bbf3  jmp     loc_18004BCCC
0x18004bbf8  cmp     [rsp+2D0h+PtNumOfCharConverted], r14
0x18004bbfd  jz      short loc_18004BC38
0x18004bbff  mov     rcx, [rbp+1D8h]; this
0x18004bc06  mov     r9d, 80070057h; char *
0x18004bc0c  lea     r8, aOnecoreBaseNgs_4; "onecore\\base\\ngscb\\cornerstone\\nkpc"...
0x18004bc13  mov     edx, 2Bh ; '+'; void *
0x18004bc18  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004bc1d  nop
0x18004bc1e  test    rdi, rdi
0x18004bc21  jz      short loc_18004BC33
0x18004bc23  mov     rcx, rdi; hMem
0x18004bc26  call    cs:__imp_LocalFree
0x18004bc2d  nop     dword ptr [rax+rax+00h]
0x18004bc32  nop
0x18004bc33  jmp     loc_18004BCCC
0x18004bc38  mov     [rsp+2D0h+MaxCountInBytes], r13; int
0x18004bc3d  mov     r9, r12; Src
0x18004bc40  mov     r8, rsi; DstSizeInBytes
0x18004bc43  mov     rdx, rdi; Dst
0x18004bc46  lea     rcx, [rsp+2D0h+PtNumOfCharConverted]; PtNumOfCharConverted
0x18004bc4b  call    cs:__imp_wcstombs_s
0x18004bc52  nop     dword ptr [rax+rax+00h]
0x18004bc57  test    eax, eax
0x18004bc59  jz      short loc_18004BC91
0x18004bc5b  mov     rcx, [rbp+1D8h]; this
0x18004bc62  mov     r9d, 80070057h; char *
0x18004bc68  lea     r8, aOnecoreBaseNgs_4; "onecore\\base\\ngscb\\cornerstone\\nkpc"...
0x18004bc6f  mov     edx, 2Dh ; '-'; void *
0x18004bc74  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004bc79  nop
0x18004bc7a  test    rdi, rdi
0x18004bc7d  jz      short loc_18004BC8F
0x18004bc7f  mov     rcx, rdi; hMem
0x18004bc82  call    cs:__imp_LocalFree
0x18004bc89  nop     dword ptr [rax+rax+00h]
0x18004bc8e  nop
0x18004bc8f  jmp     short loc_18004BCCC
0x18004bc91  cmp     [rsp+2D0h+PtNumOfCharConverted], rsi
0x18004bc96  jz      short loc_18004BCEB
0x18004bc98  mov     rcx, [rbp+1D8h]; this
0x18004bc9f  mov     r9d, 80070057h; char *
0x18004bca5  lea     r8, aOnecoreBaseNgs_4; "onecore\\base\\ngscb\\cornerstone\\nkpc"...
0x18004bcac  mov     edx, 2Eh ; '.'; void *
0x18004bcb1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004bcb6  nop
0x18004bcb7  test    rdi, rdi
0x18004bcba  jz      short loc_18004BCCC
0x18004bcbc  mov     rcx, rdi; hMem
0x18004bcbf  call    cs:__imp_LocalFree
0x18004bcc6  nop     dword ptr [rax+rax+00h]
0x18004bccb  nop
0x18004bccc  test    rbx, rbx
0x18004bccf  jz      short loc_18004BCE1
0x18004bcd1  mov     rcx, rbx; hMem
0x18004bcd4  call    cs:__imp_LocalFree
0x18004bcdb  nop     dword ptr [rax+rax+00h]
0x18004bce0  nop
0x18004bce1  mov     ebx, 80070057h
0x18004bce6  jmp     loc_18004C420
0x18004bceb  xor     edx, edx; Val
0x18004bced  mov     r8d, 198h; Size
0x18004bcf3  lea     rcx, [rbp+1D0h+WSAData]; void *
0x18004bcf7  call    memset_0
0x18004bcfc  mov     ecx, 202h; wVersionRequested
0x18004bd01  lea     rdx, [rbp+1D0h+WSAData]; lpWSAData
0x18004bd05  call    cs:__imp_WSAStartup
0x18004bd0c  nop     dword ptr [rax+rax+00h]
0x18004bd11  cmp     eax, 0FFFFFFFFh
0x18004bd14  jnz     short loc_18004BD8E
0x18004bd16  call    cs:__imp_WSAGetLastError
0x18004bd1d  nop     dword ptr [rax+rax+00h]
0x18004bd22  test    eax, eax
0x18004bd24  jz      short loc_18004BD74
0x18004bd26  mov     rcx, [rbp+1D8h]; this
0x18004bd2d  mov     r9d, eax; char *
0x18004bd30  lea     r8, aOnecoreBaseNgs_4; "onecore\\base\\ngscb\\cornerstone\\nkpc"...
0x18004bd37  mov     edx, 34h ; '4'; void *
0x18004bd3c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004bd41  mov     esi, eax
0x18004bd43  test    rdi, rdi
0x18004bd46  jz      short loc_18004BD58
0x18004bd48  mov     rcx, rdi; hMem
0x18004bd4b  call    cs:__imp_LocalFree
0x18004bd52  nop     dword ptr [rax+rax+00h]
0x18004bd57  nop
0x18004bd58  test    rbx, rbx
0x18004bd5b  jz      short loc_18004BD6D
0x18004bd5d  mov     rcx, rbx; hMem
0x18004bd60  call    cs:__imp_LocalFree
0x18004bd67  nop     dword ptr [rax+rax+00h]
0x18004bd6c  nop
0x18004bd6d  mov     ebx, esi
0x18004bd6f  jmp     loc_18004C420
0x18004bd74  test    rdi, rdi
0x18004bd77  jz      short loc_18004BD89
0x18004bd79  mov     rcx, rdi; hMem
0x18004bd7c  call    cs:__imp_LocalFree
0x18004bd83  nop     dword ptr [rax+rax+00h]
0x18004bd88  nop
0x18004bd89  jmp     loc_18004C408
0x18004bd8e  mov     [rsp+2D0h+var_267], 1
0x18004bd93  xorps   xmm0, xmm0
0x18004bd96  movups  xmmword ptr [rbp+1D0h+name.sa_family], xmm0
0x18004bd9a  mov     r12d, 2
0x18004bda0  mov     [rbp+1D0h+name.sa_family], r12w
0x18004bda5  mov     [rsp+2D0h+pAddrBuf], r15d
0x18004bdaa  lea     r8, [rsp+2D0h+pAddrBuf]; pAddrBuf
0x18004bdaf  mov     rdx, rbx; pszAddrString
0x18004bdb2  mov     ecx, r12d; Family
0x18004bdb5  call    cs:__imp_inet_pton
0x18004bdbc  nop     dword ptr [rax+rax+00h]
0x18004bdc1  mov     eax, [rsp+2D0h+pAddrBuf]
0x18004bdc5  mov     dword ptr [rbp+1D0h+name.sa_data+2], eax
0x18004bdc8  lea     ecx, [r12+42h]; hostshort
0x18004bdcd  call    cs:__imp_htons
0x18004bdd4  nop     dword ptr [rax+rax+00h]
0x18004bdd9  mov     word ptr [rbp+1D0h+name.sa_data], ax
0x18004bddd  xorps   xmm0, xmm0
0x18004bde0  movups  xmmword ptr [rbp+1D0h+to.sa_family], xmm0
0x18004bde4  mov     [rbp+1D0h+to.sa_family], r12w
0x18004bde9  mov     [rsp+2D0h+var_27C], r15d
0x18004bdee  lea     r8, [rsp+2D0h+var_27C]; pAddrBuf
0x18004bdf3  mov     rdx, rdi; pszAddrString
0x18004bdf6  mov     ecx, r12d; Family
0x18004bdf9  call    cs:__imp_inet_pton
0x18004be00  nop     dword ptr [rax+rax+00h]
0x18004be05  mov     eax, [rsp+2D0h+var_27C]
0x18004be09  mov     dword ptr [rbp+1D0h+to.sa_data+2], eax
0x18004be0c  lea     ecx, [r12+41h]; hostshort
0x18004be11  call    cs:__imp_htons
0x18004be18  nop     dword ptr [rax+rax+00h]
0x18004be1d  mov     word ptr [rbp+1D0h+to.sa_data], ax
0x18004be21  lea     r8d, [r12+0Fh]; protocol
0x18004be26  mov     edx, r12d; type
0x18004be29  mov     ecx, r12d; af
0x18004be2c  call    cs:__imp_socket
0x18004be33  nop     dword ptr [rax+rax+00h]
0x18004be38  mov     [rsp+2D0h+s], rax
0x18004be3d  lea     r14d, [r12+0Eh]
0x18004be42  mov     r8d, r14d; namelen
0x18004be45  lea     rdx, [rbp+1D0h+name]; name
0x18004be49  mov     rcx, rax; s
0x18004be4c  call    cs:__imp_bind
0x18004be53  nop     dword ptr [rax+rax+00h]
0x18004be58  cmp     eax, 0FFFFFFFFh
0x18004be5b  jnz     loc_18004BEF1
0x18004be61  call    cs:__imp_WSAGetLastError
0x18004be68  nop     dword ptr [rax+rax+00h]
0x18004be6d  test    eax, eax
0x18004be6f  jz      short loc_18004BECA
0x18004be71  mov     rcx, [rbp+1D8h]; this
0x18004be78  mov     r9d, eax; char *
0x18004be7b  lea     r8, aOnecoreBaseNgs_4; "onecore\\base\\ngscb\\cornerstone\\nkpc"...
0x18004be82  lea     edx, [r12+4Bh]; void *
0x18004be87  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004be8c  mov     esi, eax
0x18004be8e  call    cs:__imp_WSACleanup
0x18004be95  nop     dword ptr [rax+rax+00h]
0x18004be9a  nop
0x18004be9b  test    rdi, rdi
0x18004be9e  jz      short loc_18004BEB0
0x18004bea0  mov     rcx, rdi; hMem
0x18004bea3  call    cs:__imp_LocalFree
  ... truncated ...
```
