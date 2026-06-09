# ProcessUnreachablePaths(NCSI_PASSIVE_POLL_DATA_IN const &,NCSI_PASSIVE_POLL_DATA_OUT &,NCSI_INTERFACE_ATTRIBUTES *)

- ea: `0x180010870`
- end: `0x180010bae`
- name: `?ProcessUnreachablePaths@@YAXAEBUNCSI_PASSIVE_POLL_DATA_IN@@AEAUNCSI_PASSIVE_POLL_DATA_OUT@@PEAVNCSI_INTERFACE_ATTRIBUTES@@@Z`
- size: `830`
- prototype: `void __fastcall(const struct NCSI_PASSIVE_POLL_DATA_IN *, struct NCSI_PASSIVE_POLL_DATA_OUT *, struct NCSI_INTERFACE_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180010060`

## callees

- `0x180009804`
- `0x18000d990`
- `0x18000e350`
- `0x18000e3c4`
- `0x18000e870`
- `0x180010870`
- `0x18001f66c`
- `0x180032650`
- `0x180033010`
- `0x180047240`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x1800109b9`
- `ntdll!EtwEventWriteTransfer` at `0x1800109b9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010b79`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010b79`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010ac9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010ac9`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall ProcessUnreachablePaths(
        const struct NCSI_PASSIVE_POLL_DATA_IN *a1,
        struct NCSI_PASSIVE_POLL_DATA_OUT *a2,
        const char **a3)
{
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  const char *v10; // rax
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  Ncsi::Proxy::Info *v14; // r9
  Ncsi::Proxy::Info *v15; // r9
  const char *v16; // [rsp+40h] [rbp-C0h] BYREF
  const char *v17; // [rsp+48h] [rbp-B8h] BYREF
  _OWORD v18[3]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v19; // [rsp+80h] [rbp-80h]
  _OWORD v20[3]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v21; // [rsp+B8h] [rbp-48h]
  const unsigned __int16 *v22[2]; // [rsp+C0h] [rbp-40h] BYREF
  char *v23; // [rsp+D0h] [rbp-30h] BYREF
  int v24; // [rsp+D8h] [rbp-28h]
  int v25; // [rsp+DCh] [rbp-24h]
  int *v26; // [rsp+E0h] [rbp-20h]
  int v27; // [rsp+E8h] [rbp-18h]
  int v28; // [rsp+ECh] [rbp-14h]
  const char *v29; // [rsp+F0h] [rbp-10h]
  __int64 v30; // [rsp+F8h] [rbp-8h]
  const char *v31; // [rsp+100h] [rbp+0h]
  __int64 v32; // [rsp+108h] [rbp+8h]
  const char **v33; // [rsp+110h] [rbp+10h]
  __int64 v34; // [rsp+118h] [rbp+18h]

  memset(v18, 0, sizeof(v18));
  v19 = 0;
  NCSI_INTERFACE_ATTRIBUTES::GetConnectionProxyInfo(a3, v18);
  memset(v20, 0, sizeof(v20));
  v21 = 0;
  Ncsi::Proxy::Detector::GetProxyInfo(v6, v20);
  if ( *((_DWORD *)a3 + 6) )
  {
    if ( (unsigned int)dword_18009A080 > 5 )
    {
      v17 = *a3;
      v33 = &v17;
      v34 = 8;
      v31 = "pInterface is disconnected";
      v32 = 27;
      v29 = "Skipping";
      v30 = 9;
      v22[0] = (const unsigned __int16 *)0x50B000000LL;
      v22[1] = 0;
      v23 = (char *)off_18009A088;
      v24 = *(unsigned __int16 *)off_18009A088;
      v25 = 2;
      v26 = &dword_180088F14;
      v27 = 57;
      v28 = 1;
      LODWORD(v16) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EtwEventWriteTransfer(qword_18009A0A0, v22, 0, 0, 5, &v23);
    }
  }
  else
  {
    v10 = a3[1596];
    if ( v10 && *((_DWORD *)v10 + 26) == 5 )
    {
      if ( (unsigned int)dword_18009A080 > 5 )
      {
        v17 = *a3;
        v16 = "pInterface is dormant";
        v22[0] = (const unsigned __int16 *)"Skipping";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
          v7,
          (unsigned __int8 *)byte_180088E7F,
          v8,
          v9,
          v22,
          (const unsigned __int16 **)&v16,
          (__int64)&v17);
      }
    }
    else if ( (!(unsigned __int8)NCSI_INTERFACE_ATTRIBUTES::IsBehindHotspot(a3, 0)
            || (unsigned __int8)NCSI_INTERFACE_ATTRIBUTES::HasInternetBehindHotspot())
           && (!(unsigned __int8)NCSI_INTERFACE_ATTRIBUTES::IsBehindHotspot(a3, 1)
            || (unsigned __int8)NCSI_INTERFACE_ATTRIBUTES::HasInternetBehindHotspot()) )
    {
      EnterCriticalSection(&g_ncsiLock);
      v22[0] = (const unsigned __int16 *)&g_ncsiLock;
      if ( *((_BYTE *)a1 + 2) )
      {
        v14 = (Ncsi::Proxy::Info *)v20;
        if ( LODWORD(v18[0]) == 3 )
          v14 = (Ncsi::Proxy::Info *)v18;
        ProcessUnreachablePathsByFamily<_IPV4_PATH_KEY,_IPV4_PATH_ROD>(
          0,
          (__int64)a3,
          (unsigned int)(*((_DWORD *)a1 + 8) - g_unreachablePathsLastProcessedTime),
          v14,
          (int)&g_nsiPathTablev4,
          (int)a1,
          (_BYTE *)a2 + 8);
      }
      if ( *((_BYTE *)a1 + 3) )
      {
        v15 = (Ncsi::Proxy::Info *)v20;
        if ( LODWORD(v18[0]) == 3 )
          v15 = (Ncsi::Proxy::Info *)v18;
        ProcessUnreachablePathsByFamily<_IPV6_PATH_KEY,_IPV6_PATH_ROD>(
          1,
          (NCSI_INTERFACE_ATTRIBUTES *)a3,
          *((_DWORD *)a1 + 8) - g_unreachablePathsLastProcessedTime,
          v15,
          (__int64)&g_nsiPathTablev6,
          (__int64)a1,
          (_BYTE *)a2 + 9);
      }
      LeaveCriticalSection(&g_ncsiLock);
    }
    else if ( (unsigned int)dword_18009A080 > 5 )
    {
      v22[0] = (const unsigned __int16 *)*a3;
      v17 = "Behind HotSpot";
      v16 = "Skipping";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        v11,
        (unsigned __int8 *)&dword_180088EC4,
        v12,
        v13,
        (const unsigned __int16 **)&v16,
        (const unsigned __int16 **)&v17,
        (__int64)v22);
    }
  }
  Ncsi::Proxy::Info::~Info((Ncsi::Proxy::Info *)v20);
  Ncsi::Proxy::Info::~Info((Ncsi::Proxy::Info *)v18);
}

```

## disassembly

```asm
0x180010870  push    rbp
0x180010872  push    rbx
0x180010873  push    rsi
0x180010874  push    rdi
0x180010875  push    r14
0x180010877  lea     rbp, [rsp-30h]
0x18001087c  sub     rsp, 130h
0x180010883  mov     rax, cs:__security_cookie
0x18001088a  xor     rax, rsp
0x18001088d  mov     [rbp+50h+var_30], rax
0x180010891  mov     rbx, r8
0x180010894  mov     rsi, rdx
0x180010897  mov     rdi, rcx
0x18001089a  xorps   xmm0, xmm0
0x18001089d  xor     eax, eax
0x18001089f  movups  [rsp+150h+var_100], xmm0
0x1800108a4  movups  [rsp+150h+var_F0], xmm0
0x1800108a9  movups  [rsp+150h+var_E0], xmm0
0x1800108ae  mov     [rbp+50h+var_D0], rax
0x1800108b2  lea     rdx, [rsp+150h+var_100]
0x1800108b7  mov     rcx, r8
0x1800108ba  call    ?GetConnectionProxyInfo@NCSI_INTERFACE_ATTRIBUTES@@QEAA?AVInfo@Proxy@Ncsi@@XZ; NCSI_INTERFACE_ATTRIBUTES::GetConnectionProxyInfo(void)
0x1800108bf  nop
0x1800108c0  xorps   xmm0, xmm0
0x1800108c3  xor     eax, eax
0x1800108c5  movups  [rbp+50h+var_C8], xmm0
0x1800108c9  movups  [rbp+50h+var_B8], xmm0
0x1800108cd  movups  [rbp+50h+var_A8], xmm0
0x1800108d1  mov     [rbp+50h+var_98], rax
0x1800108d5  lea     rdx, [rbp+50h+var_C8]
0x1800108d9  call    ?GetProxyInfo@Detector@Proxy@Ncsi@@QEAA?AVInfo@23@XZ; Ncsi::Proxy::Detector::GetProxyInfo(void)
0x1800108de  nop
0x1800108df  cmp     dword ptr [rbx+18h], 0
0x1800108e3  jz      loc_1800109C4
0x1800108e9  mov     eax, cs:dword_18009A080
0x1800108ef  cmp     eax, 5
0x1800108f2  jbe     loc_180010B80
0x1800108f8  mov     rax, [rbx]
0x1800108fb  mov     [rsp+150h+var_108], rax
0x180010900  lea     rax, [rsp+150h+var_108]
0x180010905  mov     [rbp+50h+var_40], rax
0x180010909  mov     [rbp+50h+var_38], 8
0x180010911  xor     ecx, ecx
0x180010913  lea     rax, aPinterfaceIsDi; "pInterface is disconnected"
0x18001091a  mov     [rbp+50h+var_50], rax
0x18001091e  mov     [rbp+50h+var_48], 1Bh
0x180010926  lea     rax, aSkipping; "Skipping"
0x18001092d  mov     [rbp+50h+var_60], rax
0x180010931  mov     [rbp+50h+var_58], 9
0x180010939  mov     dword ptr [rbp+50h+var_90], 0B000000h
0x180010940  movzx   eax, cs:word_180088F0A
0x180010947  mov     dword ptr [rbp+50h+var_90+4], eax
0x18001094a  mov     [rbp+50h+var_88], rcx
0x18001094e  mov     rax, cs:off_18009A088
0x180010955  mov     [rbp+50h+var_80], rax
0x180010959  movzx   eax, word ptr [rax]
0x18001095c  mov     [rbp+50h+var_78], eax
0x18001095f  mov     [rbp+50h+var_74], 2
0x180010966  lea     rax, dword_180088F14
0x18001096d  mov     [rbp+50h+var_70], rax
0x180010971  mov     [rbp+50h+var_68], 39h ; '9'
0x180010978  mov     [rbp+50h+var_64], 1
0x18001097f  lea     rax, _TraceLoggingMetadataEnd
0x180010986  lea     rcx, _TraceLoggingMetadata
0x18001098d  sub     eax, ecx
0x18001098f  mov     dword ptr [rsp+150h+var_110], eax
0x180010993  mov     eax, dword ptr [rsp+150h+var_110]
0x180010997  lea     rax, [rbp+50h+var_80]
0x18001099b  mov     [rsp+150h+var_128], rax
0x1800109a0  mov     dword ptr [rsp+150h+var_130], 5
0x1800109a8  xor     r9d, r9d
0x1800109ab  xor     r8d, r8d
0x1800109ae  lea     rdx, [rbp+50h+var_90]
0x1800109b2  mov     rcx, cs:qword_18009A0A0
0x1800109b9  call    cs:__imp_EtwEventWriteTransfer
0x1800109bf  jmp     loc_180010B80
0x1800109c4  mov     rax, [rbx+31E0h]
0x1800109cb  test    rax, rax
0x1800109ce  jz      short loc_180010A32
0x1800109d0  cmp     dword ptr [rax+68h], 5
0x1800109d4  jnz     short loc_180010A32
0x1800109d6  mov     eax, cs:dword_18009A080
0x1800109dc  cmp     eax, 5
0x1800109df  jbe     loc_180010B80
0x1800109e5  mov     rax, [rbx]
0x1800109e8  mov     [rsp+150h+var_108], rax
0x1800109ed  lea     rax, aPinterfaceIsDo; "pInterface is dormant"
0x1800109f4  mov     [rsp+150h+var_110], rax
0x1800109f9  lea     rax, aSkipping; "Skipping"
0x180010a00  mov     [rbp+50h+var_90], rax
0x180010a04  lea     rax, [rsp+150h+var_108]
0x180010a09  mov     [rsp+150h+var_120], rax
0x180010a0e  lea     rax, [rsp+150h+var_110]
0x180010a13  mov     [rsp+150h+var_128], rax
0x180010a18  lea     rax, [rbp+50h+var_90]
0x180010a1c  lea     rdx, byte_180088E7F
0x180010a23  mov     [rsp+150h+var_130], rax
0x180010a28  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x180010a2d  jmp     loc_180010B80
0x180010a32  xor     edx, edx
0x180010a34  mov     rcx, rbx
0x180010a37  call    ?IsBehindHotspot@NCSI_INTERFACE_ATTRIBUTES@@QEBA_NW4_NLA_CONNECTIVITY_FAMILY@@@Z; NCSI_INTERFACE_ATTRIBUTES::IsBehindHotspot(_NLA_CONNECTIVITY_FAMILY)
0x180010a3c  test    al, al
0x180010a3e  jz      short loc_180010A49
0x180010a40  call    ?HasInternetBehindHotspot@NCSI_INTERFACE_ATTRIBUTES@@QEBA_NW4_NLA_CONNECTIVITY_FAMILY@@@Z; NCSI_INTERFACE_ATTRIBUTES::HasInternetBehindHotspot(_NLA_CONNECTIVITY_FAMILY)
0x180010a45  test    al, al
0x180010a47  jz      short loc_180010A63
0x180010a49  mov     edx, 1
0x180010a4e  mov     rcx, rbx
0x180010a51  call    ?IsBehindHotspot@NCSI_INTERFACE_ATTRIBUTES@@QEBA_NW4_NLA_CONNECTIVITY_FAMILY@@@Z; NCSI_INTERFACE_ATTRIBUTES::IsBehindHotspot(_NLA_CONNECTIVITY_FAMILY)
0x180010a56  test    al, al
0x180010a58  jz      short loc_180010ABF
0x180010a5a  call    ?HasInternetBehindHotspot@NCSI_INTERFACE_ATTRIBUTES@@QEBA_NW4_NLA_CONNECTIVITY_FAMILY@@@Z; NCSI_INTERFACE_ATTRIBUTES::HasInternetBehindHotspot(_NLA_CONNECTIVITY_FAMILY)
0x180010a5f  test    al, al
0x180010a61  jnz     short loc_180010ABF
0x180010a63  mov     eax, cs:dword_18009A080
0x180010a69  cmp     eax, 5
0x180010a6c  jbe     loc_180010B80
0x180010a72  mov     rax, [rbx]
0x180010a75  mov     [rbp+50h+var_90], rax
0x180010a79  lea     rax, aBehindHotspot; "Behind HotSpot"
0x180010a80  mov     [rsp+150h+var_108], rax
0x180010a85  lea     rax, aSkipping; "Skipping"
0x180010a8c  mov     [rsp+150h+var_110], rax
0x180010a91  lea     rax, [rbp+50h+var_90]
0x180010a95  mov     [rsp+150h+var_120], rax
0x180010a9a  lea     rax, [rsp+150h+var_108]
0x180010a9f  mov     [rsp+150h+var_128], rax
0x180010aa4  lea     rax, [rsp+150h+var_110]
0x180010aa9  lea     rdx, dword_180088EC4
0x180010ab0  mov     [rsp+150h+var_130], rax
0x180010ab5  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x180010aba  jmp     loc_180010B80
0x180010abf  lea     r14, ?g_ncsiLock@@3Vcritical_section@wil@@A; wil::critical_section g_ncsiLock
0x180010ac6  mov     rcx, r14; lpCriticalSection
0x180010ac9  call    cs:__imp_EnterCriticalSection
0x180010acf  mov     [rbp+50h+var_90], r14
0x180010ad3  cmp     byte ptr [rdi+2], 0
0x180010ad7  jz      short loc_180010B22
0x180010ad9  cmp     dword ptr [rsp+150h+var_100], 3
0x180010ade  setz    al
0x180010ae1  lea     r9, [rbp+50h+var_C8]
0x180010ae5  lea     rcx, [rsp+150h+var_100]
0x180010aea  test    al, al
0x180010aec  cmovnz  r9, rcx
0x180010af0  mov     r8d, [rdi+20h]
0x180010af4  mov     ecx, cs:?g_unreachablePathsLastProcessedTime@@3U?$atomic@K@std@@A; std::atomic<ulong> g_unreachablePathsLastProcessedTime
0x180010afa  nop
0x180010afb  lea     rax, [rsi+8]
0x180010aff  sub     r8d, ecx
0x180010b02  mov     [rsp+150h+var_120], rax
0x180010b07  mov     [rsp+150h+var_128], rdi
0x180010b0c  lea     rax, ?g_nsiPathTablev4@@3V?$TNcsiNsiTable@U_IPV4_PATH_KEY@@U_IPV4_PATH_ROD@@@@A; TNcsiNsiTable<_IPV4_PATH_KEY,_IPV4_PATH_ROD> g_nsiPathTablev4
0x180010b13  mov     [rsp+150h+var_130], rax
0x180010b18  mov     rdx, rbx
0x180010b1b  xor     ecx, ecx
0x180010b1d  call    ??$ProcessUnreachablePathsByFamily@U_IPV4_PATH_KEY@@U_IPV4_PATH_ROD@@@@YAXW4_NLA_CONNECTIVITY_FAMILY@@PEAVNCSI_INTERFACE_ATTRIBUTES@@KAEBVInfo@Proxy@Ncsi@@AEBV?$TNcsiNsiTable@U_IPV4_PATH_KEY@@U_IPV4_PATH_ROD@@@@AEBUNCSI_PASSIVE_POLL_DATA_IN@@AEA_N@Z; ProcessUnreachablePathsByFamily<_IPV4_PATH_KEY,_IPV4_PATH_ROD>(_NLA_CONNECTIVITY_FAMILY,NCSI_INTERFACE_ATTRIBUTES *,ulong,Ncsi::Proxy::Info const &,TNcsiNsiTable<_IPV4_PATH_KEY,_IPV4_PATH_ROD> const &,NCSI_PASSIVE_POLL_DATA_IN const &,bool &)
0x180010b22  cmp     byte ptr [rdi+3], 0
0x180010b26  jz      short loc_180010B76
0x180010b28  cmp     dword ptr [rsp+150h+var_100], 3
0x180010b2d  setz    al
0x180010b30  lea     r9, [rbp+50h+var_C8]
0x180010b34  lea     rcx, [rsp+150h+var_100]
0x180010b39  test    al, al
0x180010b3b  cmovnz  r9, rcx
0x180010b3f  mov     r8d, [rdi+20h]
0x180010b43  mov     r10d, cs:?g_unreachablePathsLastProcessedTime@@3U?$atomic@K@std@@A; std::atomic<ulong> g_unreachablePathsLastProcessedTime
0x180010b4a  nop
0x180010b4b  lea     rax, [rsi+9]
0x180010b4f  sub     r8d, r10d
0x180010b52  mov     [rsp+150h+var_120], rax
0x180010b57  mov     [rsp+150h+var_128], rdi
0x180010b5c  lea     rax, ?g_nsiPathTablev6@@3V?$TNcsiNsiTable@U_IPV6_PATH_KEY@@U_IPV6_PATH_ROD@@@@A; TNcsiNsiTable<_IPV6_PATH_KEY,_IPV6_PATH_ROD> g_nsiPathTablev6
0x180010b63  mov     [rsp+150h+var_130], rax
0x180010b68  mov     rdx, rbx
0x180010b6b  mov     ecx, 1
0x180010b70  call    ??$ProcessUnreachablePathsByFamily@U_IPV6_PATH_KEY@@U_IPV6_PATH_ROD@@@@YAXW4_NLA_CONNECTIVITY_FAMILY@@PEAVNCSI_INTERFACE_ATTRIBUTES@@KAEBVInfo@Proxy@Ncsi@@AEBV?$TNcsiNsiTable@U_IPV6_PATH_KEY@@U_IPV6_PATH_ROD@@@@AEBUNCSI_PASSIVE_POLL_DATA_IN@@AEA_N@Z; ProcessUnreachablePathsByFamily<_IPV6_PATH_KEY,_IPV6_PATH_ROD>(_NLA_CONNECTIVITY_FAMILY,NCSI_INTERFACE_ATTRIBUTES *,ulong,Ncsi::Proxy::Info const &,TNcsiNsiTable<_IPV6_PATH_KEY,_IPV6_PATH_ROD> const &,NCSI_PASSIVE_POLL_DATA_IN const &,bool &)
0x180010b75  nop
0x180010b76  mov     rcx, r14; lpCriticalSection
0x180010b79  call    cs:__imp_LeaveCriticalSection
0x180010b7f  nop
0x180010b80  lea     rcx, [rbp+50h+var_C8]; this
0x180010b84  call    ??1Info@Proxy@Ncsi@@QEAA@XZ; Ncsi::Proxy::Info::~Info(void)
0x180010b89  nop
0x180010b8a  lea     rcx, [rsp+150h+var_100]; this
0x180010b8f  call    ??1Info@Proxy@Ncsi@@QEAA@XZ; Ncsi::Proxy::Info::~Info(void)
0x180010b94  mov     rcx, [rbp+50h+var_30]
0x180010b98  xor     rcx, rsp; StackCookie
0x180010b9b  call    __security_check_cookie
0x180010ba0  add     rsp, 130h
0x180010ba7  pop     r14
0x180010ba9  pop     rdi
0x180010baa  pop     rsi
0x180010bab  pop     rbx
0x180010bac  pop     rbp
0x180010bad  retn
```
