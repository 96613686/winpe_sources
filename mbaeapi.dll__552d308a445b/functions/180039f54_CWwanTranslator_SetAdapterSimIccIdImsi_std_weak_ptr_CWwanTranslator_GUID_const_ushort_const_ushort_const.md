# CWwanTranslator::SetAdapterSimIccIdImsi(std::weak_ptr<CWwanTranslator>,_GUID const &,ushort const *,ushort const *)

- ea: `0x180039f54`
- end: `0x18003a676`
- name: `?SetAdapterSimIccIdImsi@CWwanTranslator@@SAJV?$weak_ptr@VCWwanTranslator@@@std@@AEBU_GUID@@PEBG2@Z`
- size: `1826`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180043834`
- `0x180047470`

## callees

- `0x18000178c`
- `0x1800040cd`
- `0x1800040e5`
- `0x180009474`
- `0x180009ffc`
- `0x18001105c`
- `0x180016bc0`
- `0x1800172bc`
- `0x18001dd10`
- `0x18001e3fc`
- `0x180039f54`
- `0x180044954`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a535`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a5fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a535`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a5fb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a25a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a25a`

## string_xrefs

- `0x180039fe7`: `CWwanTranslator::SetAdapterSimIccIdImsi`
- `0x18003a0d7`: `CWwanTranslator::SetAdapterSimIccIdImsi`
- `0x18003a18a`: `CWwanTranslator::SetAdapterSimIccIdImsi`
- `0x18003a340`: `CWwanTranslator::SetAdapterSimIccIdImsi`
- `0x18003a485`: `CWwanTranslator::SetAdapterSimIccIdImsi`
- `0x18003a45a`: `Need query profiles due to imsi change.`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CWwanTranslator::SetAdapterSimIccIdImsi(
        const unsigned __int16 *a1,
        void *a2,
        void *a3,
        unsigned __int16 *a4)
{
  const unsigned __int16 *v5; // r13
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rdx
  signed __int32 v10; // eax
  signed __int32 v11; // ett
  CWwanTranslator *v12; // r14
  volatile signed __int32 *v13; // rdi
  const struct _tlgProvider_t *v14; // rax
  __int64 v15; // r8
  __int64 v16; // r9
  const struct _tlgProvider_t *v17; // rax
  __int64 v18; // r8
  __int64 v19; // r9
  volatile signed __int32 *v20; // rcx
  _QWORD *v22; // r15
  char **v23; // rbx
  char *v24; // rax
  char *v25; // r8
  int v26; // ecx
  int v27; // edx
  const struct _tlgProvider_t *v28; // rax
  __int64 v29; // r8
  __int64 v30; // r9
  __int64 v31; // r8
  unsigned __int64 v32; // rdx
  void *v33; // rax
  char *v34; // r13
  __int64 v35; // rbx
  char **v36; // rbx
  char *v37; // rax
  unsigned __int16 *v38; // r15
  char *v39; // r8
  int v40; // edx
  int v41; // ecx
  const struct _tlgProvider_t *v42; // rax
  __int64 v43; // r8
  __int64 v44; // r9
  __int64 v45; // r8
  unsigned __int64 v46; // rdx
  char *v47; // r15
  __int64 v48; // rbx
  int WwanProfilesForAdapter; // eax
  unsigned int v50; // ebx
  volatile signed __int32 *v51; // rcx
  volatile signed __int32 *v52; // rcx
  int v53[2]; // [rsp+28h] [rbp-59h]
  int v54[2]; // [rsp+38h] [rbp-49h] BYREF
  char *v55; // [rsp+40h] [rbp-41h]
  CWwanTranslator *v56[2]; // [rsp+48h] [rbp-39h] BYREF
  __int64 v57; // [rsp+58h] [rbp-29h]
  unsigned __int16 *v58[2]; // [rsp+60h] [rbp-21h] BYREF
  __int64 v59; // [rsp+70h] [rbp-11h]
  unsigned __int16 *v60[2]; // [rsp+78h] [rbp-9h] BYREF
  __int64 v61; // [rsp+88h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+E0h] [rbp+5Fh]
  unsigned __int16 *v63; // [rsp+E8h] [rbp+67h] BYREF
  void *Buf1; // [rsp+F0h] [rbp+6Fh]
  void *Src; // [rsp+F8h] [rbp+77h]
  unsigned __int16 *v66; // [rsp+100h] [rbp+7Fh]

  v66 = a4;
  Src = a3;
  Buf1 = a2;
  v63 = (unsigned __int16 *)a1;
  v5 = a1;
  *(_OWORD *)v58 = 0;
  v59 = 0;
  *(_OWORD *)v56 = 0;
  v57 = 0;
  std::vector<unsigned short>::resize(v58);
  std::vector<unsigned short>::resize(v56);
  StringCchPrintfW(v58[0], v58[1] - v58[0], L"Enter");
  v53[0] = 818;
  StringCchPrintfW(
    (unsigned __int16 *)v56[0],
    (v56[1] - v56[0]) >> 1,
    L"%S(%d):%s",
    "CWwanTranslator::SetAdapterSimIccIdImsi");
  v6 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v6 > 5u )
  {
    *(CWwanTranslator **)v54 = v56[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v6,
      (__int64)word_1800774D2,
      v7,
      v8,
      (const unsigned __int16 **)v54);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v56);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v58);
  *(_OWORD *)v56 = 0;
  v9 = *((_QWORD *)v5 + 1);
  if ( v9 )
  {
    v10 = *(_DWORD *)(v9 + 8);
    while ( v10 )
    {
      v11 = v10;
      v10 = _InterlockedCompareExchange((volatile signed __int32 *)(v9 + 8), v10 + 1, v10);
      if ( v11 == v10 )
      {
        v12 = *(CWwanTranslator **)v5;
        v56[0] = *(CWwanTranslator **)v5;
        v13 = (volatile signed __int32 *)*((_QWORD *)v5 + 1);
        v56[1] = (CWwanTranslator *)v13;
        goto LABEL_8;
      }
    }
  }
  v12 = v56[0];
  v13 = (volatile signed __int32 *)v56[1];
LABEL_8:
  if ( !v12 )
  {
    *(_OWORD *)v60 = 0;
    v61 = 0;
    *(_OWORD *)v58 = 0;
    v59 = 0;
    std::vector<unsigned short>::resize(v60);
    std::vector<unsigned short>::resize(v58);
    StringCchPrintfW(v60[0], v60[1] - v60[0], L"The weakptr is no long valid");
    v53[0] = 824;
    StringCchPrintfW(
      v58[0],
      v58[1] - v58[0],
      L"%S(%d):%s",
      "CWwanTranslator::SetAdapterSimIccIdImsi",
      *(_QWORD *)v53,
      v60[0]);
    v14 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v14 > 3u )
    {
      *(unsigned __int16 **)v54 = v58[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v14,
        (__int64)&dword_18007746C,
        v15,
        v16,
        (const unsigned __int16 **)v54);
    }
    std::vector<unsigned short>::~vector<unsigned short>((char **)v58);
    std::vector<unsigned short>::~vector<unsigned short>((char **)v60);
LABEL_12:
    *(_OWORD *)v58 = 0;
    v59 = 0;
    *(_OWORD *)v60 = 0;
    v61 = 0;
    std::vector<unsigned short>::resize(v58);
    std::vector<unsigned short>::resize(v60);
    StringCchPrintfW(v58[0], v58[1] - v58[0], L"Exit");
    v53[0] = 849;
    StringCchPrintfW(
      v60[0],
      v60[1] - v60[0],
      L"%S(%d):%s",
      "CWwanTranslator::SetAdapterSimIccIdImsi",
      *(_QWORD *)v53,
      v58[0]);
    v17 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v17 > 5u )
    {
      v63 = v60[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v17,
        (__int64)byte_180077449,
        v18,
        v19,
        (const unsigned __int16 **)&v63);
    }
    std::vector<unsigned short>::~vector<unsigned short>((char **)v60);
    std::vector<unsigned short>::~vector<unsigned short>((char **)v58);
    if ( v13 )
    {
      if ( _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
        if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
      }
    }
    v20 = (volatile signed __int32 *)*((_QWORD *)v5 + 1);
    if ( v20 )
    {
      if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
    }
    return 0;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)v12 + 1);
  v55 = (char *)v12 + 40;
  std::_Tree<std::_Tmap_traits<_GUID,ATL::CComPtr<ICellularSettingsApi>,GUID_COMP,std::allocator<std::pair<_GUID const,ATL::CComPtr<ICellularSettingsApi>>>,0>>::_Find_lower_bound<_GUID>(
    (__int64)v12 + 16,
    v60,
    a2);
  v22 = (_QWORD *)v61;
  if ( *(_BYTE *)(v61 + 25) || memcmp_0(Buf1, (const void *)(v61 + 32), 0x10u) < 0 || v22 == *((_QWORD **)v12 + 2) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x33F,
      (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cwwantranslator.cpp",
      (const char *)0x80070057LL,
      v53[0]);
    if ( v12 != (CWwanTranslator *)-40LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)v12 + 1);
    if ( v13 )
    {
      if ( _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
        if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
      }
    }
    v52 = (volatile signed __int32 *)*((_QWORD *)v5 + 1);
    if ( v52 && _InterlockedExchangeAdd(v52 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v52 + 8LL))(v52);
    return 2147942487LL;
  }
  else
  {
    v23 = (char **)(v22 + 7);
    if ( v22[10] <= 7u )
      v24 = (char *)(v22 + 7);
    else
      v24 = *v23;
    v25 = (char *)((_BYTE *)Src - v24);
    do
    {
      v26 = *(unsigned __int16 *)&v25[(_QWORD)v24];
      v27 = *(unsigned __int16 *)v24 - v26;
      if ( v27 )
        break;
      v24 += 2;
    }
    while ( v26 );
    if ( v27 )
    {
      *(_OWORD *)v58 = 0;
      v59 = 0;
      *(_OWORD *)v60 = 0;
      v61 = 0;
      std::vector<unsigned short>::resize(v58);
      std::vector<unsigned short>::resize(v60);
      StringCchPrintfW(v58[0], v58[1] - v58[0], L"Need query profiles due to iccid change.");
      v53[0] = 835;
      StringCchPrintfW(v60[0], v60[1] - v60[0], L"%S(%d):%s", "CWwanTranslator::SetAdapterSimIccIdImsi");
      v28 = MbaeApiLogging::Provider();
      if ( *(_DWORD *)v28 > 4u )
      {
        *(unsigned __int16 **)v54 = v60[0];
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (__int64)v28,
          (__int64)&byte_18007748F,
          v29,
          v30,
          (const unsigned __int16 **)v54);
      }
      std::vector<unsigned short>::~vector<unsigned short>((char **)v60);
      std::vector<unsigned short>::~vector<unsigned short>((char **)v58);
      v32 = -1;
      v33 = Src;
      do
        ++v32;
      while ( *((_WORD *)Src + v32) );
      if ( v32 > v22[10] )
      {
        ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
          v22 + 7,
          v32,
          v31,
          Src);
      }
      else
      {
        if ( v22[10] <= 7u )
          v34 = (char *)(v22 + 7);
        else
          v34 = *v23;
        v22[9] = v32;
        v35 = 2 * v32;
        memmove_0(v34, v33, 2 * v32);
        *(_WORD *)&v34[v35] = 0;
        v5 = v63;
      }
    }
    v36 = (char **)(v22 + 11);
    if ( v22[14] <= 7u )
      v37 = (char *)(v22 + 11);
    else
      v37 = *v36;
    v38 = v66;
    v39 = (char *)((char *)v66 - v37);
    do
    {
      v40 = *(unsigned __int16 *)&v39[(_QWORD)v37];
      v41 = *(unsigned __int16 *)v37 - v40;
      if ( v41 )
        break;
      v37 += 2;
    }
    while ( v40 );
    if ( v41 )
    {
      *(_OWORD *)v58 = 0;
      v59 = 0;
      *(_OWORD *)v60 = 0;
      v61 = 0;
      std::vector<unsigned short>::resize(v58);
      std::vector<unsigned short>::resize(v60);
      StringCchPrintfW(v58[0], v58[1] - v58[0], L"Need query profiles due to imsi change.");
      v53[0] = 841;
      StringCchPrintfW(v60[0], v60[1] - v60[0], L"%S(%d):%s", "CWwanTranslator::SetAdapterSimIccIdImsi");
      v42 = MbaeApiLogging::Provider();
      if ( *(_DWORD *)v42 > 4u )
      {
        *(unsigned __int16 **)v54 = v60[0];
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (__int64)v42,
          (__int64)byte_180077429,
          v43,
          v44,
          (const unsigned __int16 **)v54);
      }
      std::vector<unsigned short>::~vector<unsigned short>((char **)v60);
      std::vector<unsigned short>::~vector<unsigned short>((char **)v58);
      v46 = -1;
      do
        ++v46;
      while ( v38[v46] );
      if ( v46 > (unsigned __int64)v36[3] )
      {
        ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
          v36,
          v46,
          v45,
          v38);
      }
      else
      {
        if ( (unsigned __int64)v36[3] <= 7 )
          v47 = (char *)v36;
        else
          v47 = *v36;
        v36[2] = (char *)v46;
        v48 = 2 * v46;
        memmove_0(v47, v66, 2 * v46);
        *(_WORD *)&v47[v48] = 0;
        v38 = v66;
      }
    }
    if ( v12 != (CWwanTranslator *)-40LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)v12 + 1);
    WwanProfilesForAdapter = CWwanTranslator::_QueryWwanProfilesForAdapter(
                               v12,
                               (const struct _GUID *)Buf1,
                               (const unsigned __int16 *)Src,
                               v38);
    v50 = WwanProfilesForAdapter;
    if ( WwanProfilesForAdapter >= 0 )
      goto LABEL_12;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x34E,
      (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cwwantranslator.cpp",
      (const char *)(unsigned int)WwanProfilesForAdapter,
      v53[0]);
    if ( v13 )
    {
      if ( _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
        if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
      }
    }
    v51 = (volatile signed __int32 *)*((_QWORD *)v5 + 1);
    if ( v51 && _InterlockedExchangeAdd(v51 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v51 + 8LL))(v51);
    return v50;
  }
}

```

## disassembly

```asm
0x180039f54  mov     rax, rsp
0x180039f57  mov     [rax+20h], r9
0x180039f5b  mov     [rax+18h], r8
0x180039f5f  mov     [rax+10h], rdx
0x180039f63  mov     [rax+8], rcx
0x180039f67  push    rbp
0x180039f68  push    rbx
0x180039f69  push    rsi
0x180039f6a  push    rdi
0x180039f6b  push    r12
0x180039f6d  push    r13
0x180039f6f  push    r14
0x180039f71  push    r15
0x180039f73  lea     rbp, [rax-5Fh]
0x180039f77  sub     rsp, 98h
0x180039f7e  mov     r15, rdx
0x180039f81  mov     r13, rcx
0x180039f84  xorps   xmm0, xmm0
0x180039f87  movdqu  xmmword ptr [rbp+57h+var_78], xmm0
0x180039f8c  xor     r12d, r12d
0x180039f8f  mov     [rbp+57h+var_68], r12
0x180039f93  movdqu  xmmword ptr [rbp+57h+var_90], xmm0
0x180039f98  mov     [rbp+57h+var_80], r12
0x180039f9c  lea     rcx, [rbp+57h+var_78]
0x180039fa0  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180039fa5  lea     rcx, [rbp+57h+var_90]
0x180039fa9  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180039fae  mov     rdx, [rbp+57h+var_78+8]
0x180039fb2  mov     rcx, [rbp+57h+var_78]; unsigned __int16 *
0x180039fb6  sub     rdx, rcx
0x180039fb9  sar     rdx, 1; unsigned __int64
0x180039fbc  lea     r8, aEnter; "Enter"
0x180039fc3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180039fc8  mov     rdx, [rbp+57h+var_90+8]
0x180039fcc  mov     rcx, [rbp+57h+var_90]; unsigned __int16 *
0x180039fd0  sub     rdx, rcx
0x180039fd3  sar     rdx, 1; unsigned __int64
0x180039fd6  mov     rax, [rbp+57h+var_78]
0x180039fda  mov     qword ptr [rsp+0D0h+var_B0+8], rax
0x180039fdf  mov     [rsp+0D0h+var_B0], 332h
0x180039fe7  lea     r9, aCwwantranslato_57; "CWwanTranslator::SetAdapterSimIccIdImsi"
0x180039fee  lea     r8, aSDS; "%S(%d):%s"
0x180039ff5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180039ffa  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180039fff  mov     ecx, [rax]
0x18003a001  cmp     ecx, 5
0x18003a004  jbe     short loc_18003A027
0x18003a006  mov     rcx, [rbp+57h+var_90]
0x18003a00a  mov     qword ptr [rbp+57h+var_A0], rcx
0x18003a00e  lea     rcx, [rbp+57h+var_A0]
0x18003a012  mov     qword ptr [rsp+0D0h+var_B0], rcx
0x18003a017  lea     rdx, word_1800774D2
0x18003a01e  mov     rcx, rax
0x18003a021  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18003a026  nop
0x18003a027  lea     rcx, [rbp+57h+var_90]
0x18003a02b  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003a030  nop
0x18003a031  lea     rcx, [rbp+57h+var_78]
0x18003a035  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003a03a  xorps   xmm0, xmm0
0x18003a03d  movdqu  xmmword ptr [rbp+57h+var_90], xmm0
0x18003a042  mov     rdx, [r13+8]
0x18003a046  test    rdx, rdx
0x18003a049  jz      short loc_18003A062
0x18003a04b  mov     eax, [rdx+8]
0x18003a04e  jmp     short loc_18003A05E
0x18003a050  lea     ecx, [rax+1]
0x18003a053  lock cmpxchg [rdx+8], ecx
0x18003a058  jz      loc_18003A23E
0x18003a05e  test    eax, eax
0x18003a060  jnz     short loc_18003A050
0x18003a062  mov     r14, [rbp+57h+var_90]
0x18003a066  mov     rdi, [rbp+57h+var_90+8]
0x18003a06a  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18003a06e  test    r14, r14
0x18003a071  jnz     loc_18003A253
0x18003a077  xorps   xmm0, xmm0
0x18003a07a  movdqu  xmmword ptr [rbp+57h+var_60], xmm0
0x18003a07f  mov     [rbp+57h+var_50], r12
0x18003a083  movdqu  xmmword ptr [rbp+57h+var_78], xmm0
0x18003a088  mov     [rbp+57h+var_68], r12
0x18003a08c  lea     rcx, [rbp+57h+var_60]
0x18003a090  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003a095  lea     rcx, [rbp+57h+var_78]
0x18003a099  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003a09e  mov     rdx, [rbp+57h+var_60+8]
0x18003a0a2  mov     rcx, [rbp+57h+var_60]; unsigned __int16 *
0x18003a0a6  sub     rdx, rcx
0x18003a0a9  sar     rdx, 1; unsigned __int64
0x18003a0ac  lea     r8, aTheWeakptrIsNo; "The weakptr is no long valid"
0x18003a0b3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003a0b8  mov     rdx, [rbp+57h+var_78+8]
0x18003a0bc  mov     rcx, [rbp+57h+var_78]; unsigned __int16 *
0x18003a0c0  sub     rdx, rcx
0x18003a0c3  sar     rdx, 1; unsigned __int64
0x18003a0c6  mov     rax, [rbp+57h+var_60]
0x18003a0ca  mov     qword ptr [rsp+0D0h+var_B0+8], rax
0x18003a0cf  mov     [rsp+0D0h+var_B0], 338h
0x18003a0d7  lea     r9, aCwwantranslato_57; "CWwanTranslator::SetAdapterSimIccIdImsi"
0x18003a0de  lea     r8, aSDS; "%S(%d):%s"
0x18003a0e5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003a0ea  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18003a0ef  mov     ecx, [rax]
0x18003a0f1  cmp     ecx, 3
0x18003a0f4  jbe     short loc_18003A117
0x18003a0f6  mov     rcx, [rbp+57h+var_78]
0x18003a0fa  mov     qword ptr [rbp+57h+var_A0], rcx
0x18003a0fe  lea     rcx, [rbp+57h+var_A0]
0x18003a102  mov     qword ptr [rsp+0D0h+var_B0], rcx
0x18003a107  lea     rdx, dword_18007746C
0x18003a10e  mov     rcx, rax
0x18003a111  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18003a116  nop
0x18003a117  lea     rcx, [rbp+57h+var_78]
0x18003a11b  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003a120  nop
0x18003a121  lea     rcx, [rbp+57h+var_60]
0x18003a125  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003a12a  xorps   xmm0, xmm0
0x18003a12d  movdqu  xmmword ptr [rbp+57h+var_78], xmm0
0x18003a132  mov     [rbp+57h+var_68], r12
0x18003a136  movdqu  xmmword ptr [rbp+57h+var_60], xmm0
0x18003a13b  mov     [rbp+57h+var_50], r12
0x18003a13f  lea     rcx, [rbp+57h+var_78]
0x18003a143  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003a148  lea     rcx, [rbp+57h+var_60]
0x18003a14c  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003a151  mov     rdx, [rbp+57h+var_78+8]
0x18003a155  mov     rcx, [rbp+57h+var_78]; unsigned __int16 *
0x18003a159  sub     rdx, rcx
0x18003a15c  sar     rdx, 1; unsigned __int64
0x18003a15f  lea     r8, aExit; "Exit"
0x18003a166  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003a16b  mov     rdx, [rbp+57h+var_60+8]
0x18003a16f  mov     rcx, [rbp+57h+var_60]; unsigned __int16 *
0x18003a173  sub     rdx, rcx
0x18003a176  sar     rdx, 1; unsigned __int64
0x18003a179  mov     rax, [rbp+57h+var_78]
0x18003a17d  mov     qword ptr [rsp+0D0h+var_B0+8], rax
0x18003a182  mov     [rsp+0D0h+var_B0], 351h
0x18003a18a  lea     r9, aCwwantranslato_57; "CWwanTranslator::SetAdapterSimIccIdImsi"
0x18003a191  lea     r8, aSDS; "%S(%d):%s"
0x18003a198  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003a19d  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18003a1a2  mov     ecx, [rax]
0x18003a1a4  cmp     ecx, 5
0x18003a1a7  jbe     short loc_18003A1CA
0x18003a1a9  mov     rcx, [rbp+57h+var_60]
0x18003a1ad  mov     [rbp+57h+arg_0], rcx
0x18003a1b1  lea     rcx, [rbp+57h+arg_0]
0x18003a1b5  mov     qword ptr [rsp+0D0h+var_B0], rcx
0x18003a1ba  lea     rdx, byte_180077449
0x18003a1c1  mov     rcx, rax
0x18003a1c4  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18003a1c9  nop
0x18003a1ca  lea     rcx, [rbp+57h+var_60]
0x18003a1ce  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003a1d3  nop
0x18003a1d4  lea     rcx, [rbp+57h+var_78]
0x18003a1d8  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003a1dd  nop
0x18003a1de  test    rdi, rdi
0x18003a1e1  jz      short loc_18003A217
0x18003a1e3  mov     eax, esi
0x18003a1e5  lock xadd [rdi+8], eax
0x18003a1ea  add     eax, esi
0x18003a1ec  jnz     short loc_18003A217
0x18003a1ee  mov     rax, [rdi]
0x18003a1f1  mov     rcx, rdi
0x18003a1f4  mov     rax, [rax]
0x18003a1f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a1fc  mov     eax, esi
0x18003a1fe  lock xadd [rdi+0Ch], eax
0x18003a203  add     eax, esi
0x18003a205  jnz     short loc_18003A217
0x18003a207  mov     rax, [rdi]
0x18003a20a  mov     rcx, rdi
0x18003a20d  mov     rax, [rax+8]
0x18003a211  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a216  nop
0x18003a217  mov     rcx, [r13+8]
0x18003a21b  test    rcx, rcx
0x18003a21e  jz      short loc_18003A237
0x18003a220  mov     eax, esi
0x18003a222  lock xadd [rcx+0Ch], eax
0x18003a227  add     eax, esi
0x18003a229  jnz     short loc_18003A237
0x18003a22b  mov     rax, [rcx]
0x18003a22e  mov     rax, [rax+8]
0x18003a232  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a237  xor     eax, eax
0x18003a239  jmp     loc_18003A662
0x18003a23e  mov     r14, [r13+0]
0x18003a242  mov     [rbp+57h+var_90], r14
0x18003a246  mov     rdi, [r13+8]
0x18003a24a  mov     [rbp+57h+var_90+8], rdi
0x18003a24e  jmp     loc_18003A06A
0x18003a253  lea     r12, [r14+28h]
0x18003a257  mov     rcx, r12; lpCriticalSection
0x18003a25a  call    cs:__imp_EnterCriticalSection
0x18003a260  mov     [rbp+57h+var_98], r12
0x18003a264  mov     r8, r15
0x18003a267  lea     rdx, [rbp+57h+var_60]
0x18003a26b  lea     rcx, [r14+10h]
0x18003a26f  call    ??$_Find_lower_bound@U_GUID@@@?$_Tree@V?$_Tmap_traits@U_GUID@@V?$CComPtr@UICellularSettingsApi@@@ATL@@UGUID_COMP@@V?$allocator@U?$pair@$$CBU_GUID@@V?$CComPtr@UICellularSettingsApi@@@ATL@@@std@@@std@@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$CComPtr@UICellularSettingsApi@@@ATL@@@std@@PEAX@std@@@1@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,ATL::CComPtr<ICellularSettingsApi>,GUID_COMP,std::allocator<std::pair<_GUID const,ATL::CComPtr<ICellularSettingsApi>>>,0>>::_Find_lower_bound<_GUID>(_GUID const &)
0x18003a274  mov     r15, [rbp+57h+var_50]
0x18003a278  xor     ecx, ecx
0x18003a27a  cmp     [r15+19h], cl
0x18003a27e  jnz     loc_18003A5D4
0x18003a284  lea     rdx, [r15+20h]; Buf2
0x18003a288  lea     r8d, [rcx+10h]; Size
0x18003a28c  mov     rcx, [rbp+57h+Buf1]; Buf1
0x18003a290  call    memcmp_0
0x18003a295  xor     r9d, r9d
0x18003a298  test    eax, eax
0x18003a29a  js      loc_18003A5D4
0x18003a2a0  cmp     r15, [r14+10h]
0x18003a2a4  jz      loc_18003A5D4
0x18003a2aa  lea     rbx, [r15+38h]
0x18003a2ae  cmp     qword ptr [rbx+18h], 7
0x18003a2b3  jbe     short loc_18003A2BA
0x18003a2b5  mov     rax, [rbx]
0x18003a2b8  jmp     short loc_18003A2BD
0x18003a2ba  mov     rax, rbx
0x18003a2bd  mov     r8, [rbp+57h+Src]
0x18003a2c1  sub     r8, rax
0x18003a2c4  movzx   edx, word ptr [rax]
0x18003a2c7  movzx   ecx, word ptr [rax+r8]
0x18003a2cc  sub     edx, ecx
0x18003a2ce  jnz     short loc_18003A2D8
0x18003a2d0  add     rax, 2
0x18003a2d4  test    ecx, ecx
0x18003a2d6  jnz     short loc_18003A2C4
0x18003a2d8  test    edx, edx
0x18003a2da  jz      loc_18003A3EC
0x18003a2e0  xorps   xmm0, xmm0
0x18003a2e3  movdqu  xmmword ptr [rbp+57h+var_78], xmm0
0x18003a2e8  mov     [rbp+57h+var_68], r9
0x18003a2ec  movdqu  xmmword ptr [rbp+57h+var_60], xmm0
0x18003a2f1  mov     [rbp+57h+var_50], r9
0x18003a2f5  lea     rcx, [rbp+57h+var_78]
0x18003a2f9  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003a2fe  lea     rcx, [rbp+57h+var_60]
0x18003a302  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003a307  mov     rdx, [rbp+57h+var_78+8]
0x18003a30b  mov     rcx, [rbp+57h+var_78]; unsigned __int16 *
0x18003a30f  sub     rdx, rcx
0x18003a312  sar     rdx, 1; unsigned __int64
0x18003a315  lea     r8, aNeedQueryProfi_0; "Need query profiles due to iccid change"...
0x18003a31c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003a321  mov     rdx, [rbp+57h+var_60+8]
0x18003a325  mov     rcx, [rbp+57h+var_60]; unsigned __int16 *
0x18003a329  sub     rdx, rcx
0x18003a32c  sar     rdx, 1; unsigned __int64
0x18003a32f  mov     rax, [rbp+57h+var_78]
0x18003a333  mov     qword ptr [rsp+0D0h+var_B0+8], rax
0x18003a338  mov     [rsp+0D0h+var_B0], 343h
0x18003a340  lea     r9, aCwwantranslato_57; "CWwanTranslator::SetAdapterSimIccIdImsi"
0x18003a347  lea     r8, aSDS; "%S(%d):%s"
0x18003a34e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003a353  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18003a358  mov     ecx, [rax]
0x18003a35a  cmp     ecx, 4
0x18003a35d  jbe     short loc_18003A380
0x18003a35f  mov     rcx, [rbp+57h+var_60]
0x18003a363  mov     qword ptr [rbp+57h+var_A0], rcx
0x18003a367  lea     rcx, [rbp+57h+var_A0]
0x18003a36b  mov     qword ptr [rsp+0D0h+var_B0], rcx
0x18003a370  lea     rdx, byte_18007748F
0x18003a377  mov     rcx, rax
0x18003a37a  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18003a37f  nop
0x18003a380  lea     rcx, [rbp+57h+var_60]
0x18003a384  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003a389  nop
0x18003a38a  lea     rcx, [rbp+57h+var_78]
0x18003a38e  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003a393  mov     rdx, rsi
0x18003a396  mov     rax, [rbp+57h+Src]
0x18003a39a  xor     ecx, ecx
0x18003a39c  inc     rdx
0x18003a39f  cmp     [rax+rdx*2], cx
0x18003a3a3  jnz     short loc_18003A39C
0x18003a3a5  cmp     rdx, [rbx+18h]
0x18003a3a9  ja      short loc_18003A3DE
0x18003a3ab  cmp     qword ptr [rbx+18h], 7
0x18003a3b0  jbe     short loc_18003A3B7
0x18003a3b2  mov     r13, [rbx]
0x18003a3b5  jmp     short loc_18003A3BA
0x18003a3b7  mov     r13, rbx
0x18003a3ba  mov     [rbx+10h], rdx
0x18003a3be  lea     rbx, [rdx+rdx]
0x18003a3c2  mov     r8, rbx; Size
0x18003a3c5  mov     rdx, rax; Src
0x18003a3c8  mov     rcx, r13; void *
0x18003a3cb  call    memmove_0
0x18003a3d0  xor     r9d, r9d
0x18003a3d3  mov     [rbx+r13], r9w
0x18003a3d8  mov     r13, [rbp+57h+arg_0]
  ... truncated ...
```
