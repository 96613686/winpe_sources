# CTelemetryLogger::TraceErrorCdnComm(long,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,bool,HttpResponseInfo const *,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,unsigned __int64,unsigned __int64,unsigned __int64,PeerType,TraceLoggingCorrelationVector *)

- ea: `0x1800b5df8`
- end: `0x1800b68bb`
- name: `?TraceErrorCdnComm@CTelemetryLogger@@QEAAXJAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_NPEBUHttpResponseInfo@@0_K33W4PeerType@@PEAVTraceLoggingCorrelationVector@@@Z`
- size: `2755`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, __int64, __int64, __int64, int, TraceLoggingCorrelationVector *)`
- caller_count: `5`
- callee_count: `25`
- tags: `broker_com_uri`

## callers

- `0x180021bb4`
- `0x180022028`
- `0x180070864`
- `0x180076704`
- `0x1800bcd00`

## callees

- `0x180003934`
- `0x1800095a0`
- `0x18000a4fc`
- `0x18000d228`
- `0x1800179a4`
- `0x180027090`
- `0x180027188`
- `0x180027334`
- `0x18003ae04`
- `0x18003aebc`
- `0x18003af9c`
- `0x18003eedc`
- `0x18004341c`
- `0x180043d28`
- `0x18004c614`
- `0x18005125c`
- `0x1800a1ea4`
- `0x1800a90e0`
- `0x1800a9190`
- `0x1800abc60`
- `0x1800b5df8`
- `0x1800b8088`
- `0x1800b93b4`
- `0x1800f82f0`
- `0x180108ed0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b5ee8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b6890`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b5ee8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b6890`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b5e64`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b5e64`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800b6630`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800b6630`

## string_xrefs

- `0x1800b5eba`: `FailureCdnCommunication`
- `0x1800b5fc6`: `FailureCdnCommunication`
- `0x1800b5ed3`: `CTelemetryLogger::TraceErrorCdnComm`
- `0x1800b5fdf`: `CTelemetryLogger::TraceErrorCdnComm`
- `0x1800b685a`: `CTelemetryLogger::TraceErrorCdnComm`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
void __fastcall CTelemetryLogger::TraceErrorCdnComm(
        RTL_SRWLOCK *a1,
        int a2,
        __int64 a3,
        unsigned __int8 a4,
        int *a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        char *a9,
        int a10,
        TraceLoggingCorrelationVector *a11)
{
  const char *v13; // rdi
  RTL_SRWLOCK *v14; // r13
  struct _GUID *v15; // rbx
  __int64 *v16; // rdx
  __int64 *v17; // rax
  __int64 *v18; // r14
  __m128i si128; // xmm1
  int v20; // r13d
  const char *v21; // r14
  __int64 v22; // rax
  unsigned __int8 v23; // r12
  __int128 *v24; // rax
  __int64 v25; // rax
  __int64 *v26; // rax
  char *v27; // rdx
  int *v28; // rcx
  __int128 *v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // r8
  __int64 v33; // rbx
  signed __int64 v34; // rax
  char v35; // cl
  const char *v36; // rsi
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  __int128 *v40; // rdx
  __int64 v41; // rax
  __int64 v42; // rdx
  __int64 v43; // rax
  const char *v44; // rax
  const char *v45; // r8
  __int64 *p_Data1; // [rsp+28h] [rbp-310h]
  __int64 *v47; // [rsp+30h] [rbp-308h]
  __int64 *v48; // [rsp+38h] [rbp-300h]
  int *v49; // [rsp+40h] [rbp-2F8h]
  int *v50; // [rsp+48h] [rbp-2F0h]
  __int64 *v51; // [rsp+50h] [rbp-2E8h]
  __int64 *v52; // [rsp+58h] [rbp-2E0h]
  __int64 *v53; // [rsp+68h] [rbp-2D0h]
  __int64 *v54; // [rsp+70h] [rbp-2C8h]
  __int64 *v55; // [rsp+78h] [rbp-2C0h]
  __int64 *v56; // [rsp+80h] [rbp-2B8h]
  __int64 *v57; // [rsp+88h] [rbp-2B0h]
  __int64 *v58; // [rsp+90h] [rbp-2A8h]
  char v60; // [rsp+A1h] [rbp-297h]
  int v61; // [rsp+A8h] [rbp-290h] BYREF
  __int64 v62; // [rsp+B0h] [rbp-288h] BYREF
  int Data1; // [rsp+B8h] [rbp-280h] BYREF
  int v64; // [rsp+BCh] [rbp-27Ch] BYREF
  int v65; // [rsp+C0h] [rbp-278h] BYREF
  int v66; // [rsp+C4h] [rbp-274h] BYREF
  __int64 v67; // [rsp+C8h] [rbp-270h] BYREF
  __int64 v68; // [rsp+D0h] [rbp-268h] BYREF
  __int64 v69; // [rsp+D8h] [rbp-260h] BYREF
  char *v70; // [rsp+E0h] [rbp-258h] BYREF
  __int64 v71; // [rsp+E8h] [rbp-250h] BYREF
  __int64 v72; // [rsp+F0h] [rbp-248h] BYREF
  __int64 v73; // [rsp+F8h] [rbp-240h] BYREF
  __int64 v74; // [rsp+100h] [rbp-238h] BYREF
  __int64 v75; // [rsp+108h] [rbp-230h] BYREF
  __int64 v76; // [rsp+110h] [rbp-228h] BYREF
  __int64 v77; // [rsp+118h] [rbp-220h] BYREF
  PSRWLOCK SRWLock[2]; // [rsp+120h] [rbp-218h]
  _BYTE v79[32]; // [rsp+130h] [rbp-208h] BYREF
  __int128 v80; // [rsp+150h] [rbp-1E8h] BYREF
  __int128 v81; // [rsp+160h] [rbp-1D8h]
  __int128 v82; // [rsp+170h] [rbp-1C8h] BYREF
  __m128i v83; // [rsp+180h] [rbp-1B8h]
  struct _GUID v84; // [rsp+190h] [rbp-1A8h] BYREF
  __int128 v85; // [rsp+1A0h] [rbp-198h] BYREF
  __m128i v86; // [rsp+1B0h] [rbp-188h]
  char v87[48]; // [rsp+1C0h] [rbp-178h] BYREF
  char v88[256]; // [rsp+1F0h] [rbp-148h] BYREF

  v13 = (const char *)a6;
  v61 = a2;
  SRWLock[1] = (PSRWLOCK)1;
  v14 = a1 + 2;
  SRWLock[0] = a1 + 2;
  AcquireSRWLockExclusive(a1 + 2);
  v62 = 0;
  std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::find(
    a1,
    &v62,
    a6);
  v15 = (struct _GUID *)v62;
  if ( (PVOID)v62 == a1->Ptr )
  {
    if ( *(_QWORD *)(a6 + 24) > 0xFu )
      v13 = *(const char **)a6;
    LogMessage(
      4u,
      "CTelemetryLogger::TraceErrorCdnComm",
      0x42Bu,
      "%s event for unknown fileId: %s, hr: %x",
      "FailureCdnCommunication",
      v13,
      v61);
    ReleaseSRWLockExclusive(v14);
    return;
  }
  v60 = 1;
  v16 = *(__int64 **)(v62 + 64);
  v17 = (__int64 *)v16[1];
  HIDWORD(v80) = 0;
  v18 = v16;
  while ( !*((_BYTE *)v17 + 25) )
  {
    if ( *((_DWORD *)v17 + 8) >= v61 )
      v18 = v17;
    else
      v17 += 2;
    v17 = (__int64 *)*v17;
  }
  if ( *((_BYTE *)v18 + 25) || v61 < *((_DWORD *)v18 + 8) || v18 == v16 )
  {
    *(_WORD *)std::map<long,CTelemetryLogger::CdnErrorInfo>::operator[](v62 + 64, &v61) = 1;
  }
  else
  {
    CStopwatchMT::Elapsed(v18 + 6, &v62);
    if ( v62 <= 0x8BB2C96FFFLL )
    {
      v60 = 0;
      LogMessage(
        5u,
        "CTelemetryLogger::TraceErrorCdnComm",
        0x444u,
        "Too early to send %sevent. hr: %x, timeSinceLastEvent: %lld ms, errorsSinceLastEvent: %u",
        "FailureCdnCommunication",
        v61,
        v62 / 1000000,
        (unsigned __int16)++*((_WORD *)v18 + 20));
    }
  }
  v62 = std::map<long,CTelemetryLogger::CdnErrorInfo>::operator[](&v15[4], &v61);
  v84 = v15[7];
  if ( *(_QWORD *)(a3 + 24) > 0xFu )
    a3 = *(_QWORD *)a3;
  v82 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v83 = si128;
  LOBYTE(v82) = 0;
  v20 = 0;
  v21 = (const char *)&word_180129F2A;
  if ( a5 )
  {
    v20 = *a5;
    v22 = CTelemetryLogger::_BuildPeerAddrField(&v80, a5);
    std::string::operator=(&v82, v22);
    std::string::~string(&v80);
    v21 = (const char *)(a5 + 20);
    if ( *((_QWORD *)a5 + 13) > 0xFu )
      v21 = *(const char **)v21;
    if ( *((_QWORD *)a5 + 16) )
    {
      a3 = (__int64)(a5 + 28);
      if ( *((_QWORD *)a5 + 17) > 0xFu )
        a3 = *(_QWORD *)a3;
    }
    si128 = _mm_load_si128((const __m128i *)&_xmm);
  }
  if ( a11 )
  {
    TraceLoggingCorrelationVector::Increment(a11, 0);
    si128 = _mm_load_si128((const __m128i *)&_xmm);
  }
  if ( v60 )
  {
    if ( v15[9].Data4[0] )
    {
      if ( (unsigned int)dword_18017E248 > 2
        && (qword_18017E258 & 0x400000000000LL) != 0
        && (qword_18017E260 & 0x400000000000LL) == qword_18017E260 )
      {
        LODWORD(v68) = a10;
        v69 = (__int64)a9;
        v77 = a8;
        v76 = a7;
        v23 = a4;
        LODWORD(v67) = a4;
        v75 = (__int64)v21;
        v29 = &v82;
        if ( v83.m128i_i64[1] > 0xFuLL )
          v29 = (__int128 *)v82;
        v74 = (__int64)v29;
        v73 = a3;
        v72 = (__int64)&v84;
        v66 = *(unsigned __int16 *)v62;
        v65 = v20;
        v64 = v61;
        v30 = a6;
        if ( *(_QWORD *)(a6 + 24) > 0xFu )
          v30 = *(_QWORD *)a6;
        v71 = v30;
        Data1 = v15[9].Data1;
        if ( a11 )
          TraceLoggingCorrelationVector::ToStringImpl(
            a11,
            _InterlockedExchangeAdd64((volatile signed __int64 *)a11 + 17, 0),
            v88);
        else
          v88[0] = 0;
        v70 = v88;
        v58 = &v68;
        v57 = &v69;
        v56 = &v77;
        v55 = &v76;
        v54 = &v67;
        v53 = &v75;
        v52 = &v73;
        v51 = &v72;
        v50 = &v66;
        v49 = &v65;
        v48 = (__int64 *)&v64;
        v47 = &v71;
        p_Data1 = (__int64 *)&Data1;
        v26 = (__int64 *)&v70;
        v27 = (char *)&word_18015D1A6;
        v28 = &dword_18017E248;
        goto LABEL_52;
      }
    }
    else if ( (unsigned int)dword_18017E210 > 2
           && (qword_18017E220 & 0x800000000000LL) != 0
           && (qword_18017E228 & 0x800000000000LL) == qword_18017E228 )
    {
      Data1 = a10;
      v70 = a9;
      v71 = a8;
      v72 = a7;
      v23 = a4;
      v64 = a4;
      v73 = (__int64)v21;
      v24 = &v82;
      if ( v83.m128i_i64[1] > 0xFuLL )
        v24 = (__int128 *)v82;
      v74 = (__int64)v24;
      v75 = a3;
      v76 = (__int64)&v84;
      v65 = *(unsigned __int16 *)v62;
      v66 = v20;
      LODWORD(v67) = v61;
      v25 = a6;
      if ( *(_QWORD *)(a6 + 24) > 0xFu )
        v25 = *(_QWORD *)a6;
      v77 = v25;
      LODWORD(v68) = v15[9].Data1;
      if ( a11 )
        TraceLoggingCorrelationVector::ToStringImpl(
          a11,
          _InterlockedExchangeAdd64((volatile signed __int64 *)a11 + 17, 0),
          v88);
      else
        v88[0] = 0;
      v69 = (__int64)v88;
      v58 = (__int64 *)&Data1;
      v57 = (__int64 *)&v70;
      v56 = &v71;
      v55 = &v72;
      v54 = (__int64 *)&v64;
      v53 = &v73;
      v52 = &v75;
      v51 = &v76;
      v50 = &v65;
      v49 = &v66;
      v48 = &v67;
      v47 = &v77;
      p_Data1 = &v68;
      v26 = &v69;
      v27 = byte_18015D71D;
      v28 = &dword_18017E210;
LABEL_52:
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        (int)v28,
        (int)v27,
        (__int64)v26,
        (__int64)p_Data1,
        (__int64)v47,
        (__int64)v48,
        (__int64)v49,
        (__int64)v50,
        (__int64)v51,
        (__int64)v52,
        (__int64)&v74,
        (__int64)v53,
        (__int64)v54,
        (__int64)v55,
        (__int64)v56,
        (__int64)v57,
        (__int64)v58);
LABEL_54:
      v31 = v62;
      *(_WORD *)v62 = 0;
      CStopwatchMT::Restart((CStopwatchMT *)(v31 + 8));
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      goto LABEL_56;
    }
    v23 = a4;
    goto LABEL_54;
  }
  v23 = a4;
LABEL_56:
  v85 = 0;
  v86 = si128;
  LOBYTE(v85) = 0;
  if ( v20 == 403 )
  {
    v80 = 0;
    v81 = 0;
    v32 = -1;
    do
      ++v32;
    while ( *(_BYTE *)(a3 + v32) );
    std::string::_Construct<1,char const *>(&v80, a3);
    UrlGetExpirationTimestamp(&v69, &v80);
    std::string::~string(&v80);
    v33 = v69;
    if ( v69 != 0x8000000000000000uLL )
    {
      v68 = 0;
      GetSystemTimePreciseAsFileTime(&v68);
      v34 = (unsigned int)v68 + ((unsigned __int64)HIDWORD(v68) << 32) - 116444736000000000LL;
      if ( v33 == v34 )
      {
        v35 = 0;
      }
      else
      {
        v35 = -1;
        if ( v33 >= v34 )
          v35 = 1;
      }
      v36 = "no";
      if ( v35 <= 0 )
        v36 = "yes";
      SysTimePointToUTCString(&v80);
      memset(v88, 0, 0xF8u);
      std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v88);
      v37 = std::operator<<<std::char_traits<char>>(&v88[16], ", expired? ");
      v38 = std::operator<<<std::char_traits<char>>(v37, v36);
      v39 = std::operator<<<std::char_traits<char>>(v38, "(");
      v40 = &v80;
      if ( *((_QWORD *)&v81 + 1) > 0xFu )
        v40 = (__int128 *)v80;
      v41 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v39, v40, v81);
      LOBYTE(v42) = 41;
      std::operator<<<std::char_traits<char>>(v41, v42);
      v43 = std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::str(v88, v79);
      std::string::operator=(&v85, v43);
      std::string::~string(v79);
      std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(&v88[152]);
      *(_QWORD *)&v88[152] = &std::ios::`vftable';
      std::ios_base::~ios_base((std::ios_base *)&v88[152]);
      std::string::~string(&v80);
    }
  }
  CGuidToString::CGuidToString((CGuidToString *)v87, &v84);
  v44 = (const char *)&v82;
  if ( v83.m128i_i64[1] > 0xFuLL )
    v44 = (const char *)v82;
  if ( *(_QWORD *)(a6 + 24) > 0xFu )
    v13 = *(const char **)a6;
  v45 = (const char *)&v85;
  if ( v86.m128i_i64[1] > 0xFuLL )
    v45 = (const char *)v85;
  LogMessage(
    4u,
    "CTelemetryLogger::TraceErrorCdnComm",
    0x4ADu,
    "hr: %x, httpCode: %u%s, errorCount: %u, fileId: %s, sessionId: %s, url: %s, isHeadRequest: %u, requestOffset: %llu, "
    "requestSize: %llu, responseSize: %llu, serverIp: %s, headers: %s",
    v61,
    v20,
    v45,
    *(unsigned __int16 *)v62,
    v13,
    v87,
    (const char *)a3,
    v23,
    a7,
    a8,
    a9,
    v44,
    v21);
  std::string::~string(&v85);
  std::string::~string(&v82);
  ReleaseSRWLockExclusive(SRWLock[0]);
}

```

## disassembly

```asm
0x1800b5df8  push    rbx
0x1800b5dfa  push    rsi
0x1800b5dfb  push    rdi
0x1800b5dfc  push    r12
0x1800b5dfe  push    r13
0x1800b5e00  push    r14
0x1800b5e02  push    r15
0x1800b5e04  sub     rsp, 300h
0x1800b5e0b  mov     rax, cs:__security_cookie
0x1800b5e12  xor     rax, rsp
0x1800b5e15  mov     [rsp+338h+var_48], rax
0x1800b5e1d  mov     [rsp+338h+var_298], r9b
0x1800b5e25  mov     r15, r8
0x1800b5e28  mov     r14, rcx
0x1800b5e2b  mov     r12, [rsp+338h+arg_20]
0x1800b5e33  mov     rdi, [rsp+338h+arg_28]
0x1800b5e3b  mov     [rsp+338h+var_290], edx
0x1800b5e42  mov     rsi, [rsp+338h+arg_50]
0x1800b5e4a  xorps   xmm0, xmm0
0x1800b5e4d  movups  xmmword ptr [rsp+338h+SRWLock], xmm0
0x1800b5e55  lea     r13, [rcx+10h]
0x1800b5e59  mov     [rsp+338h+SRWLock], r13
0x1800b5e61  mov     rcx, r13; SRWLock
0x1800b5e64  call    cs:__imp_AcquireSRWLockExclusive
0x1800b5e6a  mov     eax, 1
0x1800b5e6f  mov     byte ptr [rsp+338h+SRWLock+8], al
0x1800b5e76  xor     eax, eax
0x1800b5e78  mov     [rsp+338h+var_288], rax
0x1800b5e80  mov     r8, rdi
0x1800b5e83  lea     rdx, [rsp+338h+var_288]
0x1800b5e8b  mov     rcx, r14
0x1800b5e8e  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEBA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::find(std::string const &)
0x1800b5e93  mov     rbx, [rsp+338h+var_288]
0x1800b5e9b  cmp     rbx, [r14]
0x1800b5e9e  jnz     short loc_1800B5EF3
0x1800b5ea0  cmp     qword ptr [rdi+18h], 0Fh
0x1800b5ea5  jbe     short loc_1800B5EAA
0x1800b5ea7  mov     rdi, [rdi]
0x1800b5eaa  mov     eax, [rsp+338h+var_290]
0x1800b5eb1  mov     dword ptr [rsp+338h+var_308], eax
0x1800b5eb5  mov     [rsp+338h+var_310], rdi
0x1800b5eba  lea     rax, aFailurecdncomm; "FailureCdnCommunication"
0x1800b5ec1  mov     [rsp+338h+var_318], rax
0x1800b5ec6  lea     r9, aSEventForUnkno; "%s event for unknown fileId: %s, hr: %x"
0x1800b5ecd  mov     r8d, 42Bh; unsigned int
0x1800b5ed3  lea     rdx, aCtelemetrylogg_5; "CTelemetryLogger::TraceErrorCdnComm"
0x1800b5eda  mov     ecx, 4; unsigned __int8
0x1800b5edf  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x1800b5ee4  nop
0x1800b5ee5  mov     rcx, r13; SRWLock
0x1800b5ee8  call    cs:__imp_ReleaseSRWLockExclusive
0x1800b5eee  jmp     loc_1800B6897
0x1800b5ef3  mov     [rsp+338h+var_297], 1
0x1800b5efb  lea     r13, [rbx+40h]
0x1800b5eff  mov     rdx, [r13+0]
0x1800b5f03  mov     rax, [rdx+8]
0x1800b5f07  xor     ecx, ecx
0x1800b5f09  mov     dword ptr [rsp+338h+var_1E8+0Ch], ecx
0x1800b5f10  mov     r14, rdx
0x1800b5f13  xor     r8d, r8d
0x1800b5f16  mov     ecx, [rsp+338h+var_290]
0x1800b5f1d  cmp     [rax+19h], r8b
0x1800b5f21  jnz     short loc_1800B5F36
0x1800b5f23  cmp     [rax+20h], ecx
0x1800b5f26  jge     short loc_1800B5F2E
0x1800b5f28  add     rax, 10h
0x1800b5f2c  jmp     short loc_1800B5F31
0x1800b5f2e  mov     r14, rax
0x1800b5f31  mov     rax, [rax]
0x1800b5f34  jmp     short loc_1800B5F1D
0x1800b5f36  cmp     [r14+19h], r8b
0x1800b5f3a  jnz     loc_1800B5FF2
0x1800b5f40  cmp     ecx, [r14+20h]
0x1800b5f44  jl      loc_1800B5FF2
0x1800b5f4a  cmp     r14, rdx
0x1800b5f4d  jz      loc_1800B5FF2
0x1800b5f53  lea     rcx, [r14+30h]
0x1800b5f57  lea     rdx, [rsp+338h+var_288]
0x1800b5f5f  call    ?Elapsed@CStopwatchMT@@QEBA?AV?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@chrono@std@@XZ; CStopwatchMT::Elapsed(void)
0x1800b5f64  mov     rax, 8BB2C96FFFh
0x1800b5f6e  cmp     [rsp+338h+var_288], rax
0x1800b5f76  jg      loc_1800B6007
0x1800b5f7c  xor     edx, edx
0x1800b5f7e  mov     [rsp+338h+var_297], dl
0x1800b5f85  lea     eax, [rdx+1]
0x1800b5f88  add     [r14+28h], ax
0x1800b5f8d  movzx   ecx, word ptr [r14+28h]
0x1800b5f92  mov     rax, 431BDE82D7B634DBh
0x1800b5f9c  imul    [rsp+338h+var_288]
0x1800b5fa4  sar     rdx, 12h
0x1800b5fa8  mov     rax, rdx
0x1800b5fab  shr     rax, 3Fh
0x1800b5faf  add     rdx, rax
0x1800b5fb2  mov     dword ptr [rsp+338h+var_300], ecx
0x1800b5fb6  mov     [rsp+338h+var_308], rdx
0x1800b5fbb  mov     eax, [rsp+338h+var_290]
0x1800b5fc2  mov     dword ptr [rsp+338h+var_310], eax
0x1800b5fc6  lea     rax, aFailurecdncomm; "FailureCdnCommunication"
0x1800b5fcd  mov     [rsp+338h+var_318], rax
0x1800b5fd2  lea     r9, aTooEarlyToSend; "Too early to send %sevent. hr: %x, time"...
0x1800b5fd9  mov     r8d, 444h; unsigned int
0x1800b5fdf  lea     rdx, aCtelemetrylogg_5; "CTelemetryLogger::TraceErrorCdnComm"
0x1800b5fe6  mov     ecx, 5; unsigned __int8
0x1800b5feb  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x1800b5ff0  jmp     short loc_1800B6007
0x1800b5ff2  lea     rdx, [rsp+338h+var_290]
0x1800b5ffa  mov     rcx, r13
0x1800b5ffd  call    ??A?$map@JUCdnErrorInfo@CTelemetryLogger@@U?$less@J@std@@V?$allocator@U?$pair@$$CBJUCdnErrorInfo@CTelemetryLogger@@@std@@@4@@std@@QEAAAEAUCdnErrorInfo@CTelemetryLogger@@AEBJ@Z; std::map<long,CTelemetryLogger::CdnErrorInfo>::operator[](long const &)
0x1800b6002  mov     word ptr [rax], 1
0x1800b6007  lea     rdx, [rsp+338h+var_290]
0x1800b600f  mov     rcx, r13
0x1800b6012  call    ??A?$map@JUCdnErrorInfo@CTelemetryLogger@@U?$less@J@std@@V?$allocator@U?$pair@$$CBJUCdnErrorInfo@CTelemetryLogger@@@std@@@4@@std@@QEAAAEAUCdnErrorInfo@CTelemetryLogger@@AEBJ@Z; std::map<long,CTelemetryLogger::CdnErrorInfo>::operator[](long const &)
0x1800b6017  mov     [rsp+338h+var_288], rax
0x1800b601f  movups  xmm0, xmmword ptr [rbx+70h]
0x1800b6023  movdqu  xmmword ptr [rsp+338h+var_1A8.Data1], xmm0
0x1800b602c  cmp     qword ptr [r15+18h], 0Fh
0x1800b6031  jbe     short loc_1800B6036
0x1800b6033  mov     r15, [r15]
0x1800b6036  xorps   xmm0, xmm0
0x1800b6039  movups  [rsp+338h+var_1C8], xmm0
0x1800b6041  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x1800b6049  movdqu  [rsp+338h+var_1B8], xmm1
0x1800b6052  xor     edx, edx
0x1800b6054  mov     byte ptr [rsp+338h+var_1C8], dl
0x1800b605b  mov     r13d, edx
0x1800b605e  lea     r14, word_180129F2A
0x1800b6065  test    r12, r12
0x1800b6068  jz      short loc_1800B60CD
0x1800b606a  mov     r13d, [r12]
0x1800b606e  mov     rdx, r12
0x1800b6071  lea     rcx, [rsp+338h+var_1E8]
0x1800b6079  call    ?_BuildPeerAddrField@CTelemetryLogger@@CA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBUHttpResponseInfo@@@Z; CTelemetryLogger::_BuildPeerAddrField(HttpResponseInfo const &)
0x1800b607e  mov     rdx, rax
0x1800b6081  lea     rcx, [rsp+338h+var_1C8]
0x1800b6089  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x1800b608e  lea     rcx, [rsp+338h+var_1E8]; void *
0x1800b6096  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800b609b  lea     r14, [r12+50h]
0x1800b60a0  cmp     qword ptr [r14+18h], 0Fh
0x1800b60a5  jbe     short loc_1800B60AA
0x1800b60a7  mov     r14, [r14]
0x1800b60aa  xor     edx, edx
0x1800b60ac  cmp     [r12+80h], rdx
0x1800b60b4  jz      short loc_1800B60C5
0x1800b60b6  lea     r15, [r12+70h]
0x1800b60bb  cmp     qword ptr [r15+18h], 0Fh
0x1800b60c0  jbe     short loc_1800B60C5
0x1800b60c2  mov     r15, [r15]
0x1800b60c5  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x1800b60cd  test    rsi, rsi
0x1800b60d0  jz      short loc_1800B60E6
0x1800b60d2  xor     edx, edx; char *
0x1800b60d4  mov     rcx, rsi; this
0x1800b60d7  call    ?Increment@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::Increment(char *)
0x1800b60dc  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x1800b60e4  xor     edx, edx
0x1800b60e6  cmp     [rsp+338h+var_297], dl
0x1800b60ed  jz      loc_1800B657E
0x1800b60f3  cmp     [rbx+98h], dl
0x1800b60f9  jnz     loc_1800B6326
0x1800b60ff  cmp     cs:dword_18017E210, 2
0x1800b6106  jbe     loc_1800B6554
0x1800b610c  mov     r8, 800000000000h
0x1800b6116  test    cs:qword_18017E220, r8
0x1800b611d  jz      loc_1800B6554
0x1800b6123  mov     rax, cs:qword_18017E228
0x1800b612a  and     rax, r8
0x1800b612d  cmp     rax, cs:qword_18017E228
0x1800b6134  jnz     loc_1800B6554
0x1800b613a  mov     eax, [rsp+338h+arg_48]
0x1800b6141  mov     dword ptr [rsp+338h+var_280], eax
0x1800b6148  mov     rax, [rsp+338h+arg_40]
0x1800b6150  mov     [rsp+338h+var_258], rax
0x1800b6158  mov     rax, [rsp+338h+arg_38]
0x1800b6160  mov     [rsp+338h+var_250], rax
0x1800b6168  mov     rax, [rsp+338h+arg_30]
0x1800b6170  mov     [rsp+338h+var_248], rax
0x1800b6178  movzx   r12d, [rsp+338h+var_298]
0x1800b6181  mov     dword ptr [rsp+338h+var_280+4], r12d
0x1800b6189  mov     [rsp+338h+var_240], r14
0x1800b6191  lea     rax, [rsp+338h+var_1C8]
0x1800b6199  cmp     qword ptr [rsp+338h+var_1B8+8], 0Fh
0x1800b61a2  cmova   rax, qword ptr [rsp+338h+var_1C8]
0x1800b61ab  mov     [rsp+338h+var_238], rax
0x1800b61b3  mov     [rsp+338h+var_230], r15
0x1800b61bb  lea     rax, [rsp+338h+var_1A8]
0x1800b61c3  mov     [rsp+338h+var_228], rax
0x1800b61cb  mov     rcx, [rsp+338h+var_288]
0x1800b61d3  movzx   eax, word ptr [rcx]
0x1800b61d6  mov     dword ptr [rsp+338h+var_278], eax
0x1800b61dd  mov     dword ptr [rsp+338h+var_278+4], r13d
0x1800b61e5  mov     eax, [rsp+338h+var_290]
0x1800b61ec  mov     dword ptr [rsp+338h+var_270], eax
0x1800b61f3  mov     rax, rdi
0x1800b61f6  cmp     qword ptr [rdi+18h], 0Fh
0x1800b61fb  jbe     short loc_1800B6200
0x1800b61fd  mov     rax, [rdi]
0x1800b6200  mov     [rsp+338h+var_220], rax
0x1800b6208  mov     eax, [rbx+90h]
0x1800b620e  mov     dword ptr [rsp+338h+var_268], eax
0x1800b6215  test    rsi, rsi
0x1800b6218  jz      short loc_1800B6235
0x1800b621a  lock xadd [rsi+88h], rdx; unsigned __int64
0x1800b6223  lea     r8, [rsp+338h+var_148]; char *
0x1800b622b  mov     rcx, rsi; this
0x1800b622e  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x1800b6233  jmp     short loc_1800B623C
0x1800b6235  mov     [rsp+338h+var_148], dl
0x1800b623c  lea     rax, [rsp+338h+var_148]
0x1800b6244  mov     [rsp+338h+var_260], rax
0x1800b624c  lea     rax, [rsp+338h+var_280]
0x1800b6254  mov     [rsp+338h+var_2A8], rax
0x1800b625c  lea     rax, [rsp+338h+var_258]
0x1800b6264  mov     [rsp+338h+var_2B0], rax
0x1800b626c  lea     rax, [rsp+338h+var_250]
0x1800b6274  mov     [rsp+338h+var_2B8], rax
0x1800b627c  lea     rax, [rsp+338h+var_248]
0x1800b6284  mov     [rsp+338h+var_2C0], rax
0x1800b6289  lea     rax, [rsp+338h+var_280+4]
0x1800b6291  mov     [rsp+338h+var_2C8], rax
0x1800b6296  lea     rax, [rsp+338h+var_240]
0x1800b629e  mov     [rsp+338h+var_2D0], rax
0x1800b62a3  lea     rax, [rsp+338h+var_238]
0x1800b62ab  mov     [rsp+338h+var_2D8], rax
0x1800b62b0  lea     rax, [rsp+338h+var_230]
0x1800b62b8  mov     [rsp+338h+var_2E0], rax
0x1800b62bd  lea     rax, [rsp+338h+var_228]
0x1800b62c5  mov     [rsp+338h+var_2E8], rax
0x1800b62ca  lea     rax, [rsp+338h+var_278]
0x1800b62d2  mov     [rsp+338h+var_2F0], rax
0x1800b62d7  lea     rax, [rsp+338h+var_278+4]
0x1800b62df  mov     [rsp+338h+var_2F8], rax
0x1800b62e4  lea     rax, [rsp+338h+var_270]
0x1800b62ec  mov     [rsp+338h+var_300], rax
0x1800b62f1  lea     rax, [rsp+338h+var_220]
0x1800b62f9  mov     [rsp+338h+var_308], rax
0x1800b62fe  lea     rax, [rsp+338h+var_268]
0x1800b6306  mov     [rsp+338h+var_310], rax
0x1800b630b  lea     rax, [rsp+338h+var_260]
0x1800b6313  lea     rdx, byte_18015D71D
0x1800b631a  lea     rcx, dword_18017E210
0x1800b6321  jmp     loc_1800B6548
0x1800b6326  cmp     cs:dword_18017E248, 2
0x1800b632d  jbe     loc_1800B6554
0x1800b6333  mov     r8, 400000000000h
0x1800b633d  test    cs:qword_18017E258, r8
0x1800b6344  jz      loc_1800B6554
0x1800b634a  mov     rax, cs:qword_18017E260
0x1800b6351  and     rax, r8
0x1800b6354  cmp     rax, cs:qword_18017E260
0x1800b635b  jnz     loc_1800B6554
0x1800b6361  mov     eax, [rsp+338h+arg_48]
0x1800b6368  mov     dword ptr [rsp+338h+var_268], eax
0x1800b636f  mov     rax, [rsp+338h+arg_40]
0x1800b6377  mov     [rsp+338h+var_260], rax
0x1800b637f  mov     rax, [rsp+338h+arg_38]
0x1800b6387  mov     [rsp+338h+var_220], rax
0x1800b638f  mov     rax, [rsp+338h+arg_30]
0x1800b6397  mov     [rsp+338h+var_228], rax
0x1800b639f  movzx   r12d, [rsp+338h+var_298]
0x1800b63a8  mov     dword ptr [rsp+338h+var_270], r12d
0x1800b63b0  mov     [rsp+338h+var_230], r14
0x1800b63b8  lea     rax, [rsp+338h+var_1C8]
0x1800b63c0  cmp     qword ptr [rsp+338h+var_1B8+8], 0Fh
0x1800b63c9  cmova   rax, qword ptr [rsp+338h+var_1C8]
0x1800b63d2  mov     [rsp+338h+var_238], rax
0x1800b63da  mov     [rsp+338h+var_240], r15
0x1800b63e2  lea     rax, [rsp+338h+var_1A8]
0x1800b63ea  mov     [rsp+338h+var_248], rax
0x1800b63f2  mov     rcx, [rsp+338h+var_288]
0x1800b63fa  movzx   eax, word ptr [rcx]
0x1800b63fd  mov     dword ptr [rsp+338h+var_278+4], eax
0x1800b6404  mov     dword ptr [rsp+338h+var_278], r13d
0x1800b640c  mov     eax, [rsp+338h+var_290]
0x1800b6413  mov     dword ptr [rsp+338h+var_280+4], eax
0x1800b641a  mov     rax, rdi
0x1800b641d  cmp     qword ptr [rdi+18h], 0Fh
0x1800b6422  jbe     short loc_1800B6427
0x1800b6424  mov     rax, [rdi]
0x1800b6427  mov     [rsp+338h+var_250], rax
0x1800b642f  mov     eax, [rbx+90h]
0x1800b6435  mov     dword ptr [rsp+338h+var_280], eax
0x1800b643c  test    rsi, rsi
0x1800b643f  jz      short loc_1800B645C
0x1800b6441  lock xadd [rsi+88h], rdx; unsigned __int64
0x1800b644a  lea     r8, [rsp+338h+var_148]; char *
0x1800b6452  mov     rcx, rsi; this
0x1800b6455  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x1800b645a  jmp     short loc_1800B6463
0x1800b645c  mov     [rsp+338h+var_148], dl
0x1800b6463  lea     rax, [rsp+338h+var_148]
0x1800b646b  mov     [rsp+338h+var_258], rax
0x1800b6473  lea     rax, [rsp+338h+var_268]
0x1800b647b  mov     [rsp+338h+var_2A8], rax; __int64
0x1800b6483  lea     rax, [rsp+338h+var_260]
0x1800b648b  mov     [rsp+338h+var_2B0], rax; __int64
0x1800b6493  lea     rax, [rsp+338h+var_220]
0x1800b649b  mov     [rsp+338h+var_2B8], rax; __int64
0x1800b64a3  lea     rax, [rsp+338h+var_228]
0x1800b64ab  mov     [rsp+338h+var_2C0], rax; __int64
  ... truncated ...
```
