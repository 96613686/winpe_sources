# CCellularSettingHelperWwan::RefreshAdapterStatus(void)

- ea: `0x18004ea60`
- end: `0x18004f083`
- name: `?RefreshAdapterStatus@CCellularSettingHelperWwan@@UEAAJXZ`
- size: `1571`
- prototype: `__int64 __fastcall(CCellularSettingHelperWwan *__hidden this)`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x18000178c`
- `0x180009474`
- `0x180009ffc`
- `0x18001105c`
- `0x1800156cc`
- `0x180016134`
- `0x1800172bc`
- `0x18001dd10`
- `0x180037d04`
- `0x180037f14`
- `0x180047de0`
- `0x18004ea60`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004eba0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004ed4c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004eba0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004ed4c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004eb60`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004ed1a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004eb60`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004ed1a`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004f069`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18004f069`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004edb7`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004eee1`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004f05a`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004edb7`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004eee1`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18004f05a`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18004ebbb`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18004ebbb`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x18004ec18`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x18004ec18`

## string_xrefs

- `0x18004edef`: `Ready object is not ready. The setting page may not be notified with SIM state. `
- `0x18004ef17`: `Register object is not ready. The setting page may not be notified with registration state. `

## pseudocode

```c
int __fastcall CCellularSettingHelperWwan::RefreshAdapterStatus(CCellularSettingHelperWwan *this)
{
  const struct _tlgProvider_t *v2; // rax
  __int64 v3; // r8
  __int64 v4; // r9
  int refreshed; // eax
  __int64 v6; // rcx
  unsigned int v7; // eax
  unsigned int Interface; // eax
  int v10; // ebx
  __int64 v11; // r14
  int v12; // r8d
  int v13; // edx
  int v14; // ecx
  int v15; // edx
  int v16; // ecx
  int v17; // edx
  int v18; // ecx
  int v19; // edx
  int v20; // ecx
  int v21; // edx
  int v22; // ecx
  int v23; // edx
  int v24; // ecx
  unsigned int v25; // r15d
  __int64 v26; // rcx
  __int64 v27; // rcx
  int ready; // eax
  int v29; // esi
  const struct _tlgProvider_t *v30; // rax
  __int64 v31; // r8
  __int64 v32; // r9
  __int64 v33; // rcx
  int v34; // eax
  const struct _tlgProvider_t *v35; // rax
  __int64 v36; // r8
  __int64 v37; // r9
  const struct _tlgProvider_t *v38; // rax
  __int64 v39; // r8
  __int64 v40; // r9
  unsigned int *v41; // [rsp+20h] [rbp-49h]
  unsigned int *v42; // [rsp+20h] [rbp-49h]
  __int64 v43; // [rsp+40h] [rbp-29h] BYREF
  __int64 v44; // [rsp+48h] [rbp-21h] BYREF
  int v45[4]; // [rsp+50h] [rbp-19h] BYREF
  unsigned __int16 *v46[2]; // [rsp+60h] [rbp-9h] BYREF
  __int64 v47; // [rsp+70h] [rbp+7h]
  unsigned __int16 *v48[2]; // [rsp+78h] [rbp+Fh] BYREF
  __int64 v49; // [rsp+88h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  unsigned int v51; // [rsp+D0h] [rbp+67h] BYREF
  int v52; // [rsp+D8h] [rbp+6Fh] BYREF
  int v53; // [rsp+E0h] [rbp+77h] BYREF
  unsigned int v54; // [rsp+E8h] [rbp+7Fh] BYREF

  *(_OWORD *)v48 = 0;
  v49 = 0;
  *(_OWORD *)v46 = 0;
  v47 = 0;
  std::vector<unsigned short>::resize(v48);
  std::vector<unsigned short>::resize(v46);
  StringCchPrintfW(v48[0], v48[1] - v48[0], L"Enter");
  LODWORD(v41) = 109;
  StringCchPrintfW(v46[0], v46[1] - v46[0], L"%S(%d):%s", "CCellularSettingHelperWwan::RefreshAdapterStatus");
  v2 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v2 > 5u )
  {
    *(unsigned __int16 **)v45 = v46[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v2,
      (__int64)byte_18007989D,
      v3,
      v4,
      (const unsigned __int16 **)v45);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v46);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v48);
  refreshed = CCellularSettingHelperCommon::RefreshAdapterStatus(this);
  if ( refreshed < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x6E,
      (int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelperwwan.cpp",
      (const char *)(unsigned int)refreshed);
  LOBYTE(v51) = 1;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v6 = *((_QWORD *)this + 3);
  if ( v6 )
  {
    v41 = &v51;
    (*(void (__fastcall **)(__int64, char *, __int64))(*(_QWORD *)v6 + 320LL))(v6, (char *)this + 8, 2);
  }
  if ( this != (CCellularSettingHelperWwan *)-48LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v44 = 0;
  v52 = 0;
  v7 = WwanOpenHandle(1, 0, &v52, &v44);
  if ( v7 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x7C,
             (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelperwwan.cpp",
             (const char *)v7,
             (unsigned int)v41);
  v43 = 0;
  v42 = &v54;
  v54 = 0;
  v53 = 0;
  Interface = WwanQueryInterface(v44, (char *)this + 8, 7);
  if ( Interface )
  {
    v10 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x8A,
            (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelperwwan.cpp",
            (const char *)Interface,
            (unsigned int)&v54);
    goto LABEL_58;
  }
  v11 = v43;
  v12 = *(_DWORD *)(v43 + 568);
  v13 = v12 & 1 | 2;
  if ( (v12 & 2) == 0 )
    v13 = *(_DWORD *)(v43 + 568) & 1;
  v14 = v13 | 4;
  if ( (v12 & 4) == 0 )
    v14 = v13;
  v15 = v14 | 8;
  if ( (v12 & 8) == 0 )
    v15 = v14;
  v16 = v15 | 0x10;
  if ( (v12 & 0x10) == 0 )
    v16 = v15;
  v17 = v16 | 0x20;
  if ( (v12 & 0x20) == 0 )
    v17 = v16;
  v18 = v17 | 0x1000;
  if ( (v12 & 0x1000) == 0 )
    v18 = v17;
  v19 = v18 | 0x10000;
  if ( (v12 & 0x10000) == 0 )
    v19 = v18;
  v20 = v19 | 0x20000;
  if ( (v12 & 0x20000) == 0 )
    v20 = v19;
  v21 = v20 | 0x40000;
  if ( (v12 & 0x40000) == 0 )
    v21 = v20;
  v22 = v21 | 0x80000;
  if ( (v12 & 0x80000) == 0 )
    v22 = v21;
  v23 = v22 | 0x100000;
  if ( (v12 & 0x100000) == 0 )
    v23 = v22;
  v24 = v23 | 0x200000;
  if ( (v12 & 0x200000) == 0 )
    v24 = v23;
  v25 = v24 | 0x400000;
  if ( (v12 & 0x400000) == 0 )
    v25 = v24;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v26 = *((_QWORD *)this + 3);
  if ( v26 )
    (*(void (__fastcall **)(__int64, char *, __int64, _QWORD, unsigned int *, __int64 *, int *, _QWORD))(*(_QWORD *)v26 + 216LL))(
      v26,
      (char *)this + 8,
      1,
      v25,
      &v54,
      &v43,
      &v53,
      0);
  if ( this != (CCellularSettingHelperWwan *)-48LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  if ( *(_DWORD *)(v11 + 1024) )
  {
    v47 = 0;
    v49 = 0;
    *(_OWORD *)v48 = 0;
    *(_OWORD *)v46 = 0;
    std::vector<unsigned short>::resize(v46);
    std::vector<unsigned short>::resize(v48);
    StringCchPrintfW(
      v46[0],
      v46[1] - v46[0],
      L"Ready object is not ready. The setting page may not be notified with SIM state. ");
    LODWORD(v42) = 179;
    StringCchPrintfW(v48[0], v48[1] - v48[0], L"%S(%d):%s", "CCellularSettingHelperWwan::RefreshAdapterStatus");
    v30 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v30 > 3u )
    {
      *(unsigned __int16 **)v45 = v48[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v30,
        (__int64)&byte_180079857,
        v31,
        v32,
        (const unsigned __int16 **)v45);
    }
    std::vector<unsigned short>::~vector<unsigned short>((char **)v48);
    std::vector<unsigned short>::~vector<unsigned short>((char **)v46);
  }
  else
  {
    v27 = *((_QWORD *)this + 5);
    *(_OWORD *)v45 = 0;
    if ( v27 )
    {
      *(_QWORD *)v45 = *((_QWORD *)this + 4);
      *(_QWORD *)&v45[2] = v27;
      _InterlockedIncrement((volatile signed __int32 *)(v27 + 12));
    }
    ready = CWwanTranslator::ProcessReadyState(v45, (char *)this + 8);
    v29 = ready;
    if ( ready < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAF,
        (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelperwwan.cpp",
        (const char *)(unsigned int)ready,
        (int)v42);
      if ( v43 )
        WwanFreeMemory(v43);
      v10 = v29;
      goto LABEL_68;
    }
  }
  if ( *(_DWORD *)(v11 + 1648) )
  {
    v47 = 0;
    v49 = 0;
    *(_OWORD *)v48 = 0;
    *(_OWORD *)v46 = 0;
    std::vector<unsigned short>::resize(v46);
    std::vector<unsigned short>::resize(v48);
    StringCchPrintfW(
      v46[0],
      v46[1] - v46[0],
      L"Register object is not ready. The setting page may not be notified with registration state. ");
    LODWORD(v42) = 193;
    StringCchPrintfW(
      v48[0],
      v48[1] - v48[0],
      L"%S(%d):%s",
      "CCellularSettingHelperWwan::RefreshAdapterStatus",
      v42,
      v46[0]);
    v35 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v35 > 3u )
    {
      *(unsigned __int16 **)v45 = v48[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v35,
        (__int64)word_18007987A,
        v36,
        v37,
        (const unsigned __int16 **)v45);
    }
    std::vector<unsigned short>::~vector<unsigned short>((char **)v48);
    std::vector<unsigned short>::~vector<unsigned short>((char **)v46);
    goto LABEL_63;
  }
  v33 = *((_QWORD *)this + 5);
  *(_OWORD *)v45 = 0;
  if ( v33 )
  {
    *(_QWORD *)v45 = *((_QWORD *)this + 4);
    *(_QWORD *)&v45[2] = v33;
    _InterlockedIncrement((volatile signed __int32 *)(v33 + 12));
  }
  v34 = CWwanTranslator::ProcessRegisterState(v45, (char *)this + 8);
  v10 = v34;
  if ( v34 >= 0 )
  {
LABEL_63:
    v47 = 0;
    v49 = 0;
    *(_OWORD *)v46 = 0;
    *(_OWORD *)v48 = 0;
    std::vector<unsigned short>::resize(v46);
    std::vector<unsigned short>::resize(v48);
    StringCchPrintfW(v46[0], v46[1] - v46[0], L"Exit");
    LODWORD(v42) = 196;
    StringCchPrintfW(
      v48[0],
      v48[1] - v48[0],
      L"%S(%d):%s",
      "CCellularSettingHelperWwan::RefreshAdapterStatus",
      v42,
      v46[0]);
    v38 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v38 > 5u )
    {
      *(unsigned __int16 **)v45 = v48[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v38,
        (__int64)&dword_1800797EC,
        v39,
        v40,
        (const unsigned __int16 **)v45);
    }
    std::vector<unsigned short>::~vector<unsigned short>((char **)v48);
    std::vector<unsigned short>::~vector<unsigned short>((char **)v46);
    if ( v43 )
      WwanFreeMemory(v43);
    v10 = 0;
    goto LABEL_68;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xBD,
    (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccshelperwwan.cpp",
    (const char *)(unsigned int)v34,
    (int)v42);
LABEL_58:
  if ( v43 )
    WwanFreeMemory(v43);
LABEL_68:
  WwanCloseHandle(v44, 0);
  return v10;
}

```

## disassembly

```asm
0x18004ea60  push    rbp
0x18004ea62  push    rbx
0x18004ea63  push    rsi
0x18004ea64  push    rdi
0x18004ea65  push    r12
0x18004ea67  push    r14
0x18004ea69  push    r15
0x18004ea6b  lea     rbp, [rsp-27h]
0x18004ea70  sub     rsp, 90h
0x18004ea77  xorps   xmm0, xmm0
0x18004ea7a  mov     rbx, rcx
0x18004ea7d  xor     r12d, r12d
0x18004ea80  lea     rcx, [rbp+57h+var_48]
0x18004ea84  movdqu  xmmword ptr [rbp+57h+var_48], xmm0
0x18004ea89  mov     [rbp+57h+var_38], r12
0x18004ea8d  movdqu  xmmword ptr [rbp+57h+var_60], xmm0
0x18004ea92  mov     [rbp+57h+var_50], r12
0x18004ea96  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004ea9b  lea     rcx, [rbp+57h+var_60]
0x18004ea9f  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004eaa4  mov     rdx, [rbp+57h+var_48+8]
0x18004eaa8  lea     r8, aEnter; "Enter"
0x18004eaaf  mov     rcx, [rbp+57h+var_48]; unsigned __int16 *
0x18004eab3  sub     rdx, rcx
0x18004eab6  sar     rdx, 1; unsigned __int64
0x18004eab9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004eabe  mov     rdx, [rbp+57h+var_60+8]
0x18004eac2  lea     r9, aCcellularsetti_6; "CCellularSettingHelperWwan::RefreshAdap"...
0x18004eac9  mov     rcx, [rbp+57h+var_60]; unsigned __int16 *
0x18004eacd  lea     r8, aSDS; "%S(%d):%s"
0x18004ead4  mov     rax, [rbp+57h+var_48]
0x18004ead8  sub     rdx, rcx
0x18004eadb  mov     [rsp+0C0h+var_98], rax
0x18004eae0  sar     rdx, 1; unsigned __int64
0x18004eae3  mov     [rsp+0C0h+var_A0], 6Dh ; 'm'
0x18004eaeb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004eaf0  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18004eaf5  mov     ecx, [rax]
0x18004eaf7  cmp     ecx, 5
0x18004eafa  jbe     short loc_18004EB1C
0x18004eafc  mov     rcx, [rbp+57h+var_60]
0x18004eb00  lea     rdx, byte_18007989D
0x18004eb07  mov     qword ptr [rbp+57h+var_70], rcx
0x18004eb0b  lea     rcx, [rbp+57h+var_70]
0x18004eb0f  mov     qword ptr [rsp+0C0h+var_A0], rcx; int
0x18004eb14  mov     rcx, rax
0x18004eb17  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18004eb1c  lea     rcx, [rbp+57h+var_60]
0x18004eb20  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004eb25  lea     rcx, [rbp+57h+var_48]
0x18004eb29  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004eb2e  mov     rcx, rbx; this
0x18004eb31  call    ?RefreshAdapterStatus@CCellularSettingHelperCommon@@UEAAJXZ; CCellularSettingHelperCommon::RefreshAdapterStatus(void)
0x18004eb36  lea     r14, aOnecoreuapNetM_2; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004eb3d  test    eax, eax
0x18004eb3f  jns     short loc_18004EB55
0x18004eb41  mov     rcx, [rbp+5Fh]; this
0x18004eb45  mov     r9d, eax; char *
0x18004eb48  mov     r8, r14; unsigned int
0x18004eb4b  mov     edx, 6Eh ; 'n'; void *
0x18004eb50  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004eb55  lea     rsi, [rbx+30h]
0x18004eb59  mov     byte ptr [rbp+57h+arg_0], 1
0x18004eb5d  mov     rcx, rsi; lpCriticalSection
0x18004eb60  call    cs:__imp_EnterCriticalSection
0x18004eb66  mov     rcx, [rbx+18h]
0x18004eb6a  lea     rdi, [rbx+8]
0x18004eb6e  test    rcx, rcx
0x18004eb71  jz      short loc_18004EB98
0x18004eb73  mov     rax, [rcx]
0x18004eb76  lea     rdx, [rbp+57h+arg_0]
0x18004eb7a  mov     r9d, 1
0x18004eb80  mov     qword ptr [rsp+0C0h+var_A0], rdx; unsigned int
0x18004eb85  mov     rdx, rdi
0x18004eb88  mov     rax, [rax+140h]
0x18004eb8f  lea     r8d, [r9+1]
0x18004eb93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eb98  test    rsi, rsi
0x18004eb9b  jz      short loc_18004EBA6
0x18004eb9d  mov     rcx, rsi; lpCriticalSection
0x18004eba0  call    cs:__imp_LeaveCriticalSection
0x18004eba6  xor     edx, edx
0x18004eba8  mov     [rbp+57h+var_78], r12
0x18004ebac  lea     r9, [rbp+57h+var_78]
0x18004ebb0  mov     [rbp+57h+arg_8], r12d
0x18004ebb4  lea     r8, [rbp+57h+arg_8]
0x18004ebb8  lea     ecx, [rdx+1]
0x18004ebbb  call    cs:__imp_WwanOpenHandle
0x18004ebc1  test    eax, eax
0x18004ebc3  jz      short loc_18004EBDE
0x18004ebc5  mov     rcx, [rbp+5Fh]; this
0x18004ebc9  mov     r9d, eax; char *
0x18004ebcc  mov     r8, r14; unsigned int
0x18004ebcf  mov     edx, 7Ch ; '|'; void *
0x18004ebd4  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004ebd9  jmp     loc_18004F071
0x18004ebde  mov     rcx, [rbp+57h+var_78]
0x18004ebe2  lea     rax, [rbp+57h+arg_10]
0x18004ebe6  mov     [rsp+0C0h+var_88], r12
0x18004ebeb  xor     r9d, r9d
0x18004ebee  mov     [rsp+0C0h+var_90], rax
0x18004ebf3  mov     rdx, rdi
0x18004ebf6  lea     rax, [rbp+57h+var_80]
0x18004ebfa  mov     [rbp+57h+var_80], r12
0x18004ebfe  mov     [rsp+0C0h+var_98], rax
0x18004ec03  lea     rax, [rbp+57h+arg_18]
0x18004ec07  lea     r8d, [r9+7]
0x18004ec0b  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x18004ec10  mov     [rbp+57h+arg_18], r12d
0x18004ec14  mov     [rbp+57h+arg_10], r12d
0x18004ec18  call    cs:__imp_WwanQueryInterface
0x18004ec1e  test    eax, eax
0x18004ec20  jz      short loc_18004EC3D
0x18004ec22  mov     rcx, [rbp+5Fh]; this
0x18004ec26  mov     r9d, eax; char *
0x18004ec29  mov     r8, r14; unsigned int
0x18004ec2c  mov     edx, 8Ah; void *
0x18004ec31  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004ec36  mov     ebx, eax
0x18004ec38  jmp     loc_18004EED4
0x18004ec3d  mov     r14, [rbp+57h+var_80]
0x18004ec41  lea     rsi, [rbx+30h]
0x18004ec45  mov     r9d, 1000h
0x18004ec4b  mov     eax, 400000h
0x18004ec50  mov     r8d, [r14+238h]
0x18004ec57  mov     ecx, r8d
0x18004ec5a  and     ecx, 1
0x18004ec5d  mov     edx, ecx
0x18004ec5f  or      edx, 2
0x18004ec62  test    r8b, 2
0x18004ec66  cmovz   edx, ecx
0x18004ec69  mov     ecx, edx
0x18004ec6b  or      ecx, 4
0x18004ec6e  test    r8b, 4
0x18004ec72  cmovz   ecx, edx
0x18004ec75  mov     edx, ecx
0x18004ec77  or      edx, 8
0x18004ec7a  test    r8b, 8
0x18004ec7e  cmovz   edx, ecx
0x18004ec81  mov     ecx, edx
0x18004ec83  or      ecx, 10h
0x18004ec86  test    r8b, 10h
0x18004ec8a  cmovz   ecx, edx
0x18004ec8d  mov     edx, ecx
0x18004ec8f  or      edx, 20h
0x18004ec92  test    r8b, 20h
0x18004ec96  cmovz   edx, ecx
0x18004ec99  mov     ecx, edx
0x18004ec9b  or      ecx, r9d
0x18004ec9e  test    r9d, r8d
0x18004eca1  mov     r9d, 10000h
0x18004eca7  cmovz   ecx, edx
0x18004ecaa  mov     edx, ecx
0x18004ecac  or      edx, r9d
0x18004ecaf  test    r9d, r8d
0x18004ecb2  mov     r9d, 20000h
0x18004ecb8  cmovz   edx, ecx
0x18004ecbb  mov     ecx, edx
0x18004ecbd  or      ecx, r9d
0x18004ecc0  test    r9d, r8d
0x18004ecc3  mov     r9d, 40000h
0x18004ecc9  cmovz   ecx, edx
0x18004eccc  mov     edx, ecx
0x18004ecce  or      edx, r9d
0x18004ecd1  test    r9d, r8d
0x18004ecd4  mov     r9d, 80000h
0x18004ecda  cmovz   edx, ecx
0x18004ecdd  mov     ecx, edx
0x18004ecdf  or      ecx, r9d
0x18004ece2  test    r9d, r8d
0x18004ece5  mov     r9d, 100000h
0x18004eceb  cmovz   ecx, edx
0x18004ecee  mov     edx, ecx
0x18004ecf0  or      edx, r9d
0x18004ecf3  test    r9d, r8d
0x18004ecf6  mov     r9d, 200000h
0x18004ecfc  cmovz   edx, ecx
0x18004ecff  mov     ecx, edx
0x18004ed01  or      ecx, r9d
0x18004ed04  test    r9d, r8d
0x18004ed07  cmovz   ecx, edx
0x18004ed0a  mov     r15d, ecx
0x18004ed0d  or      r15d, eax
0x18004ed10  test    eax, r8d
0x18004ed13  cmovz   r15d, ecx
0x18004ed17  mov     rcx, rsi; lpCriticalSection
0x18004ed1a  call    cs:__imp_EnterCriticalSection
0x18004ed20  mov     rcx, [rbx+18h]
0x18004ed24  test    rcx, rcx
0x18004ed27  jz      short loc_18004ED44
0x18004ed29  mov     rax, [rcx]
0x18004ed2c  mov     r9d, r15d
0x18004ed2f  mov     r8d, 1
0x18004ed35  mov     rdx, rdi
0x18004ed38  mov     rax, [rax+0D8h]
0x18004ed3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ed44  test    rsi, rsi
0x18004ed47  jz      short loc_18004ED52
0x18004ed49  mov     rcx, rsi; lpCriticalSection
0x18004ed4c  call    cs:__imp_LeaveCriticalSection
0x18004ed52  lea     r8, [r14+390h]
0x18004ed59  xorps   xmm0, xmm0
0x18004ed5c  cmp     [r8+70h], r12d
0x18004ed60  jnz     short loc_18004EDC4
0x18004ed62  mov     rcx, [rbx+28h]
0x18004ed66  movdqu  xmmword ptr [rbp+57h+var_70], xmm0
0x18004ed6b  test    rcx, rcx
0x18004ed6e  jz      short loc_18004ED80
0x18004ed70  mov     rax, [rbx+20h]
0x18004ed74  mov     qword ptr [rbp+57h+var_70], rax
0x18004ed78  mov     qword ptr [rbp+57h+var_70+8], rcx
0x18004ed7c  lock inc dword ptr [rcx+0Ch]
0x18004ed80  mov     rdx, rdi
0x18004ed83  lea     rcx, [rbp+57h+var_70]
0x18004ed87  call    ?ProcessReadyState@CWwanTranslator@@SAJV?$weak_ptr@VCWwanTranslator@@@std@@AEBU_GUID@@PEAEI@Z; CWwanTranslator::ProcessReadyState(std::weak_ptr<CWwanTranslator>,_GUID const &,uchar *,uint)
0x18004ed8c  mov     esi, eax
0x18004ed8e  test    eax, eax
0x18004ed90  jns     loc_18004EE75
0x18004ed96  mov     rcx, [rbp+5Fh]; this
0x18004ed9a  lea     r8, aOnecoreuapNetM_2; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004eda1  mov     r9d, eax; char *
0x18004eda4  mov     edx, 0AFh; void *
0x18004eda9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004edae  mov     rcx, [rbp+57h+var_80]
0x18004edb2  test    rcx, rcx
0x18004edb5  jz      short loc_18004EDBD
0x18004edb7  call    cs:__imp_WwanFreeMemory
0x18004edbd  mov     ebx, esi
0x18004edbf  jmp     loc_18004F063
0x18004edc4  xorps   xmm1, xmm1
0x18004edc7  mov     [rbp+57h+var_50], r12
0x18004edcb  lea     rcx, [rbp+57h+var_60]
0x18004edcf  mov     [rbp+57h+var_38], r12
0x18004edd3  movdqu  xmmword ptr [rbp+57h+var_48], xmm1
0x18004edd8  movdqu  xmmword ptr [rbp+57h+var_60], xmm0
0x18004eddd  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004ede2  lea     rcx, [rbp+57h+var_48]
0x18004ede6  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18004edeb  mov     rdx, [rbp+57h+var_60+8]
0x18004edef  lea     r8, aReadyObjectIsN; "Ready object is not ready. The setting "...
0x18004edf6  mov     rcx, [rbp+57h+var_60]; unsigned __int16 *
0x18004edfa  sub     rdx, rcx
0x18004edfd  sar     rdx, 1; unsigned __int64
0x18004ee00  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004ee05  mov     rdx, [rbp+57h+var_48+8]
0x18004ee09  lea     r9, aCcellularsetti_6; "CCellularSettingHelperWwan::RefreshAdap"...
0x18004ee10  mov     rcx, [rbp+57h+var_48]; unsigned __int16 *
0x18004ee14  lea     r8, aSDS; "%S(%d):%s"
0x18004ee1b  mov     rax, [rbp+57h+var_60]
0x18004ee1f  sub     rdx, rcx
0x18004ee22  mov     [rsp+0C0h+var_98], rax
0x18004ee27  sar     rdx, 1; unsigned __int64
0x18004ee2a  mov     [rsp+0C0h+var_A0], 0B3h
0x18004ee32  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004ee37  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18004ee3c  mov     ecx, [rax]
0x18004ee3e  cmp     ecx, 3
0x18004ee41  jbe     short loc_18004EE63
0x18004ee43  mov     rcx, [rbp+57h+var_48]
0x18004ee47  lea     rdx, byte_180079857
0x18004ee4e  mov     qword ptr [rbp+57h+var_70], rcx
0x18004ee52  lea     rcx, [rbp+57h+var_70]
0x18004ee56  mov     qword ptr [rsp+0C0h+var_A0], rcx; int
0x18004ee5b  mov     rcx, rax
0x18004ee5e  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18004ee63  lea     rcx, [rbp+57h+var_48]
0x18004ee67  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004ee6c  lea     rcx, [rbp+57h+var_60]
0x18004ee70  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18004ee75  lea     r8, [r14+5A0h]
0x18004ee7c  xorps   xmm0, xmm0
0x18004ee7f  cmp     [r8+0D0h], r12d
0x18004ee86  jnz     short loc_18004EEEC
0x18004ee88  mov     rcx, [rbx+28h]
0x18004ee8c  movdqu  xmmword ptr [rbp+57h+var_70], xmm0
0x18004ee91  test    rcx, rcx
0x18004ee94  jz      short loc_18004EEA6
0x18004ee96  mov     rax, [rbx+20h]
0x18004ee9a  mov     qword ptr [rbp+57h+var_70], rax
0x18004ee9e  mov     qword ptr [rbp+57h+var_70+8], rcx
0x18004eea2  lock inc dword ptr [rcx+0Ch]
0x18004eea6  mov     rdx, rdi
0x18004eea9  lea     rcx, [rbp+57h+var_70]
0x18004eead  call    ?ProcessRegisterState@CWwanTranslator@@SAJV?$weak_ptr@VCWwanTranslator@@@std@@AEBU_GUID@@PEAEK@Z; CWwanTranslator::ProcessRegisterState(std::weak_ptr<CWwanTranslator>,_GUID const &,uchar *,ulong)
0x18004eeb2  mov     ebx, eax
0x18004eeb4  test    eax, eax
0x18004eeb6  jns     loc_18004EF9D
0x18004eebc  mov     rcx, [rbp+5Fh]; this
0x18004eec0  lea     r8, aOnecoreuapNetM_2; "onecoreuap\\net\\mobilebroadbandexperie"...
0x18004eec7  mov     r9d, eax; char *
0x18004eeca  mov     edx, 0BDh; void *
0x18004eecf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004eed4  mov     rcx, [rbp+57h+var_80]
0x18004eed8  test    rcx, rcx
0x18004eedb  jz      loc_18004F063
0x18004eee1  call    cs:__imp_WwanFreeMemory
0x18004eee7  jmp     loc_18004F063
0x18004eeec  xorps   xmm1, xmm1
0x18004eeef  mov     [rbp+57h+var_50], r12
0x18004eef3  lea     rcx, [rbp+57h+var_60]
  ... truncated ...
```
