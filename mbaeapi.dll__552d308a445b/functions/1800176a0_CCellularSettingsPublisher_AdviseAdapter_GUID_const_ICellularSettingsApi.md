# CCellularSettingsPublisher::AdviseAdapter(_GUID const &,ICellularSettingsApi * *)

- ea: `0x1800176a0`
- end: `0x180017d43`
- name: `?AdviseAdapter@CCellularSettingsPublisher@@UEAAJAEBU_GUID@@PEAPEAUICellularSettingsApi@@@Z`
- size: `1699`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, const struct _GUID *, struct ICellularSettingsApi **)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x1800016ec`
- `0x18000178c`
- `0x1800024e0`
- `0x1800040cd`
- `0x180009474`
- `0x180009ffc`
- `0x18001105c`
- `0x180016bc0`
- `0x180016d8c`
- `0x1800172bc`
- `0x1800176a0`
- `0x18001adf8`
- `0x18001d8d0`
- `0x18001dd10`
- `0x18004d618`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800178a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017970`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017b07`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017bf2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017c3c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800178a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017970`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017b07`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017bf2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017c3c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800177e3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800177e3`

## string_xrefs

- `0x1800178ec`: `The setting helper associated with this GUID has been created.`
- `0x180017abe`: `Cannot create instance for modem.`
- `0x180017ba9`: `Cannot copy helper object.`

## pseudocode

```c
__int64 __fastcall CCellularSettingsPublisher::AdviseAdapter(
        struct _RTL_CRITICAL_SECTION *this,
        const struct _GUID *a2,
        struct ICellularSettingsApi **a3)
{
  unsigned __int16 *v6; // r13
  const struct _tlgProvider_t *v7; // rax
  __int64 v8; // r8
  __int64 v9; // r9
  const struct _tlgProvider_t *v10; // rax
  char v11; // si
  struct _RTL_CRITICAL_SECTION *v12; // r14
  __int64 *p_LockCount; // r12
  __int64 v14; // rdx
  __int64 v15; // rbx
  int v16; // esi
  __int64 v17; // rcx
  const struct _tlgProvider_t *v19; // rax
  __int64 v20; // r8
  __int64 v21; // r9
  ULONG_PTR SpinCount; // rdx
  __int64 v23; // r8
  signed __int32 v24; // eax
  signed __int32 v25; // ett
  const unsigned __int16 *v26; // rdi
  unsigned __int16 **v27; // rax
  unsigned __int16 *v28; // rbx
  unsigned __int16 *v29; // rcx
  unsigned __int16 *v30; // rcx
  int v31; // edi
  const unsigned __int16 *v32; // rdi
  const struct _tlgProvider_t *v33; // rax
  __int64 v34; // r8
  __int64 v35; // r9
  int v36[2]; // [rsp+20h] [rbp-59h]
  char *v37; // [rsp+28h] [rbp-51h]
  unsigned __int16 *v38; // [rsp+30h] [rbp-49h] BYREF
  unsigned __int16 *v39; // [rsp+38h] [rbp-41h] BYREF
  struct _RTL_CRITICAL_SECTION *v40; // [rsp+40h] [rbp-39h]
  unsigned __int16 *v41[2]; // [rsp+48h] [rbp-31h] BYREF
  unsigned __int16 *v42; // [rsp+58h] [rbp-21h]
  unsigned __int16 *v43[2]; // [rsp+60h] [rbp-19h] BYREF
  __int64 v44; // [rsp+70h] [rbp-9h]
  const struct _GUID *v45; // [rsp+80h] [rbp+7h]
  __int64 v46; // [rsp+88h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v39 = (unsigned __int16 *)a3;
  v40 = this;
  v6 = 0;
  LODWORD(v38) = 0;
  *(_OWORD *)v41 = 0;
  v42 = 0;
  *(_OWORD *)v43 = 0;
  v44 = 0;
  std::vector<unsigned short>::resize(v41);
  std::vector<unsigned short>::resize(v43);
  StringCchPrintfW(v41[0], v41[1] - v41[0], L"Enter");
  v37 = (char *)v41[0];
  v36[0] = 96;
  StringCchPrintfW(v43[0], v43[1] - v43[0], L"%S(%d):%s", "CCellularSettingsPublisher::AdviseAdapter");
  v7 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v7 > 5u )
  {
    v38 = v43[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v7,
      (__int64)&dword_18007516C,
      v8,
      v9,
      (const unsigned __int16 **)&v38);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v43);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v41);
  v10 = MbaeApiLogging::Provider();
  v11 = 3;
  if ( *(_DWORD *)v10 > 5u )
  {
    v45 = a2;
    v46 = 16;
    tlgWriteTransfer_EventWriteTransfer(v10, &unk_180075128, 0, 0, 3, v43);
  }
  v38 = 0;
  v12 = this + 10;
  EnterCriticalSection(this + 10);
  p_LockCount = (__int64 *)&this[2].LockCount;
  v14 = std::_Tree<std::_Tmap_traits<_GUID,ATL::CComPtr<ICellularSettingsApi>,GUID_COMP,std::allocator<std::pair<_GUID const,ATL::CComPtr<ICellularSettingsApi>>>,0>>::_Find_lower_bound<_GUID>(
          (__int64)&this[2].LockCount,
          v43,
          a2)[2];
  if ( !*(_BYTE *)(v14 + 25) && memcmp_0(a2, (const void *)(v14 + 32), 0x10u) >= 0 )
  {
    std::_Tree<std::_Tmap_traits<_GUID,ATL::CComPtr<ICellularSettingsApi>,GUID_COMP,std::allocator<std::pair<_GUID const,ATL::CComPtr<ICellularSettingsApi>>>,0>>::_Find_lower_bound<_GUID>(
      (__int64)&this[2].LockCount,
      v43,
      a2);
    v15 = v44;
    if ( *(_BYTE *)(v44 + 25) || memcmp_0(a2, (const void *)(v44 + 32), 0x10u) < 0 )
      v15 = *p_LockCount;
    if ( a3 )
    {
      *a3 = *(struct ICellularSettingsApi **)(v15 + 48);
      v17 = *(_QWORD *)(v15 + 48);
      if ( v17 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 8LL))(v17);
      v16 = 0;
    }
    else
    {
      v16 = -2147467261;
    }
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x71,
        (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccspublisher.cpp",
        (const char *)(unsigned int)v16,
        v36[0]);
      if ( v12 )
        LeaveCriticalSection(v12);
      return (unsigned int)v16;
    }
    *(_OWORD *)v41 = 0;
    v42 = 0;
    *(_OWORD *)v43 = 0;
    v44 = 0;
    std::vector<unsigned short>::resize(v41);
    std::vector<unsigned short>::resize(v43);
    StringCchPrintfW(v41[0], v41[1] - v41[0], L"The setting helper associated with this GUID has been created.");
    v36[0] = 114;
    StringCchPrintfW(
      v43[0],
      v43[1] - v43[0],
      L"%S(%d):%s",
      "CCellularSettingsPublisher::AdviseAdapter",
      *(_QWORD *)v36,
      v41[0]);
    v19 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v19 > 4u )
    {
      v38 = v43[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v19,
        (__int64)qword_180075108,
        v20,
        v21,
        (const unsigned __int16 **)&v38);
    }
    std::vector<unsigned short>::~vector<unsigned short>((char **)v43);
    std::vector<unsigned short>::~vector<unsigned short>((char **)v41);
    if ( v12 )
      LeaveCriticalSection(v12);
    return 0;
  }
  SpinCount = this[1].SpinCount;
  if ( SpinCount )
  {
    v23 = *(_QWORD *)(SpinCount + 8);
    if ( !v23 )
LABEL_86:
      std::_Throw_bad_weak_ptr();
    v24 = *(_DWORD *)(v23 + 8);
    do
    {
      if ( !v24 )
        goto LABEL_86;
      v25 = v24;
      v24 = _InterlockedCompareExchange((volatile signed __int32 *)(v23 + 8), v24 + 1, v24);
    }
    while ( v25 != v24 );
    v26 = *(const unsigned __int16 **)(SpinCount + 8);
    v41[1] = 0;
    if ( v26 )
    {
      v6 = *(unsigned __int16 **)SpinCount;
      v41[1] = (unsigned __int16 *)v26;
      _InterlockedIncrement((volatile signed __int32 *)v26 + 3);
    }
    v27 = v41;
  }
  else
  {
    v43[1] = 0;
    v27 = v43;
    v11 = 4;
    v26 = v39;
  }
  v28 = v27[1];
  *v27 = 0;
  v27[1] = 0;
  if ( (v11 & 4) != 0 )
  {
    v11 &= ~4u;
    v29 = v43[1];
    if ( v43[1] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v43[1] + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v29 + 8LL))(v29);
    }
  }
  if ( (v11 & 2) != 0 )
  {
    v11 &= ~2u;
    v30 = v41[1];
    if ( v41[1] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v41[1] + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v30 + 8LL))(v30);
    }
  }
  if ( (v11 & 1) != 0 )
  {
    if ( v26 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v26 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(const unsigned __int16 *))v26)(v26);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v26 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)v26 + 8LL))(v26);
      }
    }
  }
  *(_OWORD *)v41 = 0;
  if ( v28 )
  {
    v41[0] = v6;
    v41[1] = v28;
    _InterlockedIncrement((volatile signed __int32 *)v28 + 3);
  }
  v31 = CCellularSettingHelperWwan::CreateInstance(a2, v40, v41, &v38);
  if ( v31 >= 0 )
  {
    *(struct _GUID *)v41 = *a2;
    v32 = v38;
    v42 = v38;
    if ( v38 )
      (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v38 + 8LL))(v38);
    std::map<_GUID,ATL::CComPtr<ICellularSettingsApi>,GUID_COMP,std::allocator<std::pair<_GUID const,ATL::CComPtr<ICellularSettingsApi>>>>::insert<std::pair<_GUID,ATL::CComPtr<ICellularSettingsApi>>,0>(
      p_LockCount,
      (__int64)v43,
      v41);
    if ( v42 )
      (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v42 + 16LL))(v42);
    if ( v39 )
    {
      *(_QWORD *)v39 = v32;
      if ( v32 )
        (*(void (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)v32 + 8LL))(v32);
      v16 = 0;
    }
    else
    {
      v16 = -2147467261;
    }
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x7F,
        (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccspublisher.cpp",
        (const char *)(unsigned int)v16,
        (int)"Cannot copy helper object.",
        v37);
      if ( v28 && _InterlockedExchangeAdd((volatile signed __int32 *)v28 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v28 + 8LL))(v28);
      if ( v12 )
        LeaveCriticalSection(v12);
      if ( v32 )
        (*(void (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)v32 + 16LL))(v32);
      return (unsigned int)v16;
    }
    if ( v28 && _InterlockedExchangeAdd((volatile signed __int32 *)v28 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v28 + 8LL))(v28);
    if ( v12 )
      LeaveCriticalSection(v12);
    *(_OWORD *)v41 = 0;
    v42 = 0;
    *(_OWORD *)v43 = 0;
    v44 = 0;
    std::vector<unsigned short>::resize(v41);
    std::vector<unsigned short>::resize(v43);
    StringCchPrintfW(v41[0], v41[1] - v41[0], L"Exit");
    v36[0] = 130;
    StringCchPrintfW(
      v43[0],
      v43[1] - v43[0],
      L"%S(%d):%s",
      "CCellularSettingsPublisher::AdviseAdapter",
      *(_QWORD *)v36,
      v41[0]);
    v33 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v33 > 5u )
    {
      v39 = v43[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v33,
        (__int64)byte_1800750E5,
        v34,
        v35,
        (const unsigned __int16 **)&v39);
    }
    std::vector<unsigned short>::~vector<unsigned short>((char **)v43);
    std::vector<unsigned short>::~vector<unsigned short>((char **)v41);
    if ( v32 )
      (*(void (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)v32 + 16LL))(v32);
    return 0;
  }
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0x7A,
    (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\ccspublisher.cpp",
    (const char *)(unsigned int)v31,
    (int)"Cannot create instance for modem.",
    v37);
  if ( v28 && _InterlockedExchangeAdd((volatile signed __int32 *)v28 + 3, 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v28 + 8LL))(v28);
  if ( v12 )
    LeaveCriticalSection(v12);
  if ( v38 )
    (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v38 + 16LL))(v38);
  return (unsigned int)v31;
}

```

## disassembly

```asm
0x1800176a0  mov     [rsp-8+arg_18], rbx
0x1800176a5  push    rbp
0x1800176a6  push    rsi
0x1800176a7  push    rdi
0x1800176a8  push    r12
0x1800176aa  push    r13
0x1800176ac  push    r14
0x1800176ae  push    r15
0x1800176b0  lea     rbp, [rsp-27h]
0x1800176b5  sub     rsp, 0A0h
0x1800176bc  mov     rax, cs:__security_cookie
0x1800176c3  xor     rax, rsp
0x1800176c6  mov     [rbp+57h+var_40], rax
0x1800176ca  mov     rdi, r8
0x1800176cd  mov     [rbp+57h+var_98], r8
0x1800176d1  mov     r15, rdx
0x1800176d4  mov     rbx, rcx
0x1800176d7  mov     [rbp+57h+var_90], rcx
0x1800176db  xor     r13d, r13d
0x1800176de  mov     dword ptr [rbp+57h+var_A0], r13d
0x1800176e2  xorps   xmm0, xmm0
0x1800176e5  movdqu  xmmword ptr [rbp+57h+var_88], xmm0
0x1800176ea  mov     [rbp+57h+var_78], r13
0x1800176ee  xorps   xmm1, xmm1
0x1800176f1  movdqu  xmmword ptr [rbp+57h+var_70], xmm1
0x1800176f6  mov     [rbp+57h+var_60], r13
0x1800176fa  lea     rcx, [rbp+57h+var_88]
0x1800176fe  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180017703  lea     rcx, [rbp+57h+var_70]
0x180017707  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18001770c  mov     rdx, [rbp+57h+var_88+8]
0x180017710  mov     rcx, [rbp+57h+var_88]; unsigned __int16 *
0x180017714  sub     rdx, rcx
0x180017717  sar     rdx, 1; unsigned __int64
0x18001771a  lea     r8, aEnter; "Enter"
0x180017721  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180017726  mov     rdx, [rbp+57h+var_70+8]
0x18001772a  mov     rcx, [rbp+57h+var_70]; unsigned __int16 *
0x18001772e  sub     rdx, rcx
0x180017731  sar     rdx, 1; unsigned __int64
0x180017734  mov     rax, [rbp+57h+var_88]
0x180017738  mov     [rsp+0D0h+var_A8], rax
0x18001773d  mov     [rsp+0D0h+var_B0], 60h ; '`'
0x180017745  lea     r9, aCcellularsetti_1; "CCellularSettingsPublisher::AdviseAdapt"...
0x18001774c  lea     r8, aSDS; "%S(%d):%s"
0x180017753  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180017758  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18001775d  mov     ecx, [rax]
0x18001775f  cmp     ecx, 5
0x180017762  jbe     short loc_180017784
0x180017764  mov     rcx, [rbp+57h+var_70]
0x180017768  mov     [rbp+57h+var_A0], rcx
0x18001776c  lea     rcx, [rbp+57h+var_A0]
0x180017770  mov     qword ptr [rsp+0D0h+var_B0], rcx
0x180017775  lea     rdx, dword_18007516C
0x18001777c  mov     rcx, rax
0x18001777f  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180017784  lea     rcx, [rbp+57h+var_70]
0x180017788  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18001778d  lea     rcx, [rbp+57h+var_88]
0x180017791  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180017796  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18001779b  mov     ecx, [rax]
0x18001779d  mov     esi, 3
0x1800177a2  cmp     ecx, 5
0x1800177a5  jbe     short loc_1800177D5
0x1800177a7  mov     [rbp+57h+var_50], r15
0x1800177ab  mov     [rbp+57h+var_48], 10h
0x1800177b3  lea     rcx, [rbp+57h+var_70]
0x1800177b7  mov     [rsp+0D0h+var_A8], rcx; char *
0x1800177bc  mov     [rsp+0D0h+var_B0], esi; int
0x1800177c0  xor     r9d, r9d
0x1800177c3  xor     r8d, r8d
0x1800177c6  lea     rdx, unk_180075128
0x1800177cd  mov     rcx, rax
0x1800177d0  call    _tlgWriteTransfer_EventWriteTransfer
0x1800177d5  mov     [rbp+57h+var_A0], r13
0x1800177d9  lea     r14, [rbx+190h]
0x1800177e0  mov     rcx, r14; lpCriticalSection
0x1800177e3  call    cs:__imp_EnterCriticalSection
0x1800177e9  lea     r12, [rbx+58h]
0x1800177ed  mov     r8, r15
0x1800177f0  lea     rdx, [rbp+57h+var_70]
0x1800177f4  mov     rcx, r12
0x1800177f7  call    ??$_Find_lower_bound@U_GUID@@@?$_Tree@V?$_Tmap_traits@U_GUID@@V?$CComPtr@UICellularSettingsApi@@@ATL@@UGUID_COMP@@V?$allocator@U?$pair@$$CBU_GUID@@V?$CComPtr@UICellularSettingsApi@@@ATL@@@std@@@std@@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$CComPtr@UICellularSettingsApi@@@ATL@@@std@@PEAX@std@@@1@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,ATL::CComPtr<ICellularSettingsApi>,GUID_COMP,std::allocator<std::pair<_GUID const,ATL::CComPtr<ICellularSettingsApi>>>,0>>::_Find_lower_bound<_GUID>(_GUID const &)
0x1800177fc  mov     rdx, [rax+10h]
0x180017800  cmp     [rdx+19h], r13b
0x180017804  jnz     loc_18001797C
0x18001780a  add     rdx, 20h ; ' '; Buf2
0x18001780e  mov     r8d, 10h; Size
0x180017814  mov     rcx, r15; Buf1
0x180017817  call    memcmp_0
0x18001781c  test    eax, eax
0x18001781e  js      loc_18001797C
0x180017824  mov     r8, r15
0x180017827  lea     rdx, [rbp+57h+var_70]
0x18001782b  mov     rcx, r12
0x18001782e  call    ??$_Find_lower_bound@U_GUID@@@?$_Tree@V?$_Tmap_traits@U_GUID@@V?$CComPtr@UICellularSettingsApi@@@ATL@@UGUID_COMP@@V?$allocator@U?$pair@$$CBU_GUID@@V?$CComPtr@UICellularSettingsApi@@@ATL@@@std@@@std@@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$CComPtr@UICellularSettingsApi@@@ATL@@@std@@PEAX@std@@@1@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,ATL::CComPtr<ICellularSettingsApi>,GUID_COMP,std::allocator<std::pair<_GUID const,ATL::CComPtr<ICellularSettingsApi>>>,0>>::_Find_lower_bound<_GUID>(_GUID const &)
0x180017833  mov     rbx, [rbp+57h+var_60]
0x180017837  cmp     [rbx+19h], r13b
0x18001783b  jnz     short loc_180017853
0x18001783d  lea     rdx, [rbx+20h]; Buf2
0x180017841  mov     r8d, 10h; Size
0x180017847  mov     rcx, r15; Buf1
0x18001784a  call    memcmp_0
0x18001784f  test    eax, eax
0x180017851  jns     short loc_180017857
0x180017853  mov     rbx, [r12]
0x180017857  test    rdi, rdi
0x18001785a  jnz     short loc_180017863
0x18001785c  mov     esi, 80004003h
0x180017861  jmp     short loc_180017882
0x180017863  mov     rax, [rbx+30h]
0x180017867  mov     [rdi], rax
0x18001786a  mov     rcx, [rbx+30h]
0x18001786e  test    rcx, rcx
0x180017871  jz      short loc_18001787F
0x180017873  mov     rax, [rcx]
0x180017876  mov     rax, [rax+8]
0x18001787a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001787f  mov     esi, r13d
0x180017882  test    esi, esi
0x180017884  jns     short loc_1800178B4
0x180017886  mov     rcx, [rbp+5Fh]; this
0x18001788a  mov     r9d, esi; char *
0x18001788d  lea     r8, aOnecoreuapNetM_0; "onecoreuap\\net\\mobilebroadbandexperie"...
0x180017894  mov     edx, 71h ; 'q'; void *
0x180017899  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001789e  test    r14, r14
0x1800178a1  jz      short loc_1800178AD
0x1800178a3  mov     rcx, r14; lpCriticalSection
0x1800178a6  call    cs:__imp_LeaveCriticalSection
0x1800178ac  nop
0x1800178ad  mov     eax, esi
0x1800178af  jmp     loc_180017D16
0x1800178b4  xorps   xmm0, xmm0
0x1800178b7  movdqu  xmmword ptr [rbp+57h+var_88], xmm0
0x1800178bc  mov     [rbp+57h+var_78], r13
0x1800178c0  xorps   xmm1, xmm1
0x1800178c3  movdqu  xmmword ptr [rbp+57h+var_70], xmm1
0x1800178c8  mov     [rbp+57h+var_60], r13
0x1800178cc  lea     rcx, [rbp+57h+var_88]
0x1800178d0  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800178d5  lea     rcx, [rbp+57h+var_70]
0x1800178d9  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800178de  mov     rdx, [rbp+57h+var_88+8]
0x1800178e2  mov     rcx, [rbp+57h+var_88]; unsigned __int16 *
0x1800178e6  sub     rdx, rcx
0x1800178e9  sar     rdx, 1; unsigned __int64
0x1800178ec  lea     r8, aTheSettingHelp; "The setting helper associated with this"...
0x1800178f3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800178f8  mov     rdx, [rbp+57h+var_70+8]
0x1800178fc  mov     rcx, [rbp+57h+var_70]; unsigned __int16 *
0x180017900  sub     rdx, rcx
0x180017903  sar     rdx, 1; unsigned __int64
0x180017906  mov     rax, [rbp+57h+var_88]
0x18001790a  mov     [rsp+0D0h+var_A8], rax
0x18001790f  mov     [rsp+0D0h+var_B0], 72h ; 'r'
0x180017917  lea     r9, aCcellularsetti_1; "CCellularSettingsPublisher::AdviseAdapt"...
0x18001791e  lea     r8, aSDS; "%S(%d):%s"
0x180017925  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001792a  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18001792f  mov     ecx, [rax]
0x180017931  cmp     ecx, 4
0x180017934  jbe     short loc_180017956
0x180017936  mov     rcx, [rbp+57h+var_70]
0x18001793a  mov     [rbp+57h+var_A0], rcx
0x18001793e  lea     rcx, [rbp+57h+var_A0]
0x180017942  mov     qword ptr [rsp+0D0h+var_B0], rcx
0x180017947  lea     rdx, qword_180075108
0x18001794e  mov     rcx, rax
0x180017951  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180017956  lea     rcx, [rbp+57h+var_70]
0x18001795a  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18001795f  lea     rcx, [rbp+57h+var_88]
0x180017963  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180017968  test    r14, r14
0x18001796b  jz      short loc_180017977
0x18001796d  mov     rcx, r14; lpCriticalSection
0x180017970  call    cs:__imp_LeaveCriticalSection
0x180017976  nop
0x180017977  jmp     loc_180017D14
0x18001797c  mov     rdx, [rbx+48h]
0x180017980  test    rdx, rdx
0x180017983  jz      short loc_1800179CB
0x180017985  mov     r8, [rdx+8]
0x180017989  test    r8, r8
0x18001798c  jz      loc_180017D3D
0x180017992  mov     eax, [r8+8]
0x180017996  jmp     short loc_1800179A3
0x180017998  lea     ecx, [rax+1]
0x18001799b  lock cmpxchg [r8+8], ecx
0x1800179a1  jz      short loc_1800179AD
0x1800179a3  test    eax, eax
0x1800179a5  jz      loc_180017D3D
0x1800179ab  jmp     short loc_180017998
0x1800179ad  mov     rdi, [rdx+8]
0x1800179b1  mov     [rbp+57h+var_88+8], r13
0x1800179b5  test    rdi, rdi
0x1800179b8  jz      short loc_1800179C5
0x1800179ba  mov     r13, [rdx]
0x1800179bd  mov     [rbp+57h+var_88+8], rdi
0x1800179c1  lock inc dword ptr [rdi+0Ch]
0x1800179c5  lea     rax, [rbp+57h+var_88]
0x1800179c9  jmp     short loc_1800179DC
0x1800179cb  mov     [rbp+57h+var_70+8], r13
0x1800179cf  lea     rax, [rbp+57h+var_70]
0x1800179d3  mov     esi, 4
0x1800179d8  mov     rdi, [rbp+57h+var_98]
0x1800179dc  mov     rbx, [rax+8]
0x1800179e0  mov     qword ptr [rax], 0
0x1800179e7  mov     qword ptr [rax+8], 0
0x1800179ef  test    sil, 4
0x1800179f3  jz      short loc_180017A1A
0x1800179f5  and     esi, 0FFFFFFFBh
0x1800179f8  mov     rcx, [rbp+57h+var_70+8]
0x1800179fc  test    rcx, rcx
0x1800179ff  jz      short loc_180017A1A
0x180017a01  or      eax, 0FFFFFFFFh
0x180017a04  lock xadd [rcx+0Ch], eax
0x180017a09  cmp     eax, 1
0x180017a0c  jnz     short loc_180017A1A
0x180017a0e  mov     rax, [rcx]
0x180017a11  mov     rax, [rax+8]
0x180017a15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a1a  test    sil, 2
0x180017a1e  jz      short loc_180017A45
0x180017a20  and     esi, 0FFFFFFFDh
0x180017a23  mov     rcx, [rbp+57h+var_88+8]
0x180017a27  test    rcx, rcx
0x180017a2a  jz      short loc_180017A45
0x180017a2c  or      eax, 0FFFFFFFFh
0x180017a2f  lock xadd [rcx+0Ch], eax
0x180017a34  cmp     eax, 1
0x180017a37  jnz     short loc_180017A45
0x180017a39  mov     rax, [rcx]
0x180017a3c  mov     rax, [rax+8]
0x180017a40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a45  test    sil, 1
0x180017a49  jz      short loc_180017A87
0x180017a4b  test    rdi, rdi
0x180017a4e  jz      short loc_180017A87
0x180017a50  or      eax, 0FFFFFFFFh
0x180017a53  lock xadd [rdi+8], eax
0x180017a58  cmp     eax, 1
0x180017a5b  jnz     short loc_180017A87
0x180017a5d  mov     rax, [rdi]
0x180017a60  mov     rcx, rdi
0x180017a63  mov     rax, [rax]
0x180017a66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a6b  or      eax, 0FFFFFFFFh
0x180017a6e  lock xadd [rdi+0Ch], eax
0x180017a73  cmp     eax, 1
0x180017a76  jnz     short loc_180017A87
0x180017a78  mov     rax, [rdi]
0x180017a7b  mov     rcx, rdi
0x180017a7e  mov     rax, [rax+8]
0x180017a82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a87  xorps   xmm0, xmm0
0x180017a8a  movdqu  xmmword ptr [rbp+57h+var_88], xmm0
0x180017a8f  test    rbx, rbx
0x180017a92  jz      short loc_180017AA0
0x180017a94  mov     [rbp+57h+var_88], r13
0x180017a98  mov     [rbp+57h+var_88+8], rbx
0x180017a9c  lock inc dword ptr [rbx+0Ch]
0x180017aa0  lea     r9, [rbp+57h+var_A0]
0x180017aa4  lea     r8, [rbp+57h+var_88]
0x180017aa8  mov     rdx, [rbp+57h+var_90]
0x180017aac  mov     rcx, r15
0x180017aaf  call    ?CreateInstance@CCellularSettingHelperWwan@@SAJAEBU_GUID@@PEAVCCellularSettingsPublisher@@V?$weak_ptr@VCWwanTranslator@@@std@@PEAPEAUICellularSettingsApi@@@Z; CCellularSettingHelperWwan::CreateInstance(_GUID const &,CCellularSettingsPublisher *,std::weak_ptr<CWwanTranslator>,ICellularSettingsApi * *)
0x180017ab4  mov     edi, eax
0x180017ab6  test    eax, eax
0x180017ab8  jns     short loc_180017B2B
0x180017aba  mov     rcx, [rbp+5Fh]; this
0x180017abe  lea     rax, aCannotCreateIn; "Cannot create instance for modem."
0x180017ac5  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x180017aca  mov     r9d, edi; char *
0x180017acd  lea     r8, aOnecoreuapNetM_0; "onecoreuap\\net\\mobilebroadbandexperie"...
0x180017ad4  mov     edx, 7Ah ; 'z'; void *
0x180017ad9  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180017ade  test    rbx, rbx
0x180017ae1  jz      short loc_180017AFF
0x180017ae3  or      eax, 0FFFFFFFFh
0x180017ae6  lock xadd [rbx+0Ch], eax
0x180017aeb  cmp     eax, 1
0x180017aee  jnz     short loc_180017AFF
0x180017af0  mov     rax, [rbx]
0x180017af3  mov     rcx, rbx
0x180017af6  mov     rax, [rax+8]
0x180017afa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017aff  test    r14, r14
0x180017b02  jz      short loc_180017B0E
0x180017b04  mov     rcx, r14; lpCriticalSection
0x180017b07  call    cs:__imp_LeaveCriticalSection
0x180017b0d  nop
0x180017b0e  mov     rcx, [rbp+57h+var_A0]
0x180017b12  test    rcx, rcx
0x180017b15  jz      short loc_180017B24
0x180017b17  mov     rax, [rcx]
0x180017b1a  mov     rax, [rax+10h]
  ... truncated ...
```
