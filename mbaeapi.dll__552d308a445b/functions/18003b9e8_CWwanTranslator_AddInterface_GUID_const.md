# CWwanTranslator::_AddInterface(_GUID const &)

- ea: `0x18003b9e8`
- end: `0x18003bdf3`
- name: `?_AddInterface@CWwanTranslator@@AEAAJAEBU_GUID@@@Z`
- size: `1035`
- prototype: `__int64 __fastcall(CWwanTranslator *this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180033768`

## callees

- `0x1800016ec`
- `0x18000178c`
- `0x1800024e0`
- `0x1800040cd`
- `0x180009ffc`
- `0x18001105c`
- `0x180016bc0`
- `0x1800171b8`
- `0x1800172bc`
- `0x18001dd10`
- `0x1800293b8`
- `0x180033330`
- `0x180034f14`
- `0x18003b9e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003bcfb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003bcfb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18003bccd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18003bccd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003bcbd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003bcbd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ba6a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ba6a`

## string_xrefs

- `0x18003baf7`: `The interface has already been added.`

## pseudocode

```c
__int64 __fastcall CWwanTranslator::_AddInterface(CWwanTranslator *this, const struct _GUID *a2)
{
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // rdx
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // r8
  __int64 v8; // r9
  SlotBindingMap *v9; // rcx
  const struct _tlgProvider_t *v10; // rax
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v14; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v15[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v16; // [rsp+40h] [rbp-C0h]
  unsigned __int16 *v17; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v18; // [rsp+50h] [rbp-B0h]
  __int128 v19; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v20; // [rsp+68h] [rbp-98h]
  __int64 v21; // [rsp+70h] [rbp-90h]
  __int128 v22; // [rsp+78h] [rbp-88h] BYREF
  __int64 v23; // [rsp+88h] [rbp-78h]
  __int64 v24; // [rsp+90h] [rbp-70h]
  __int128 v25; // [rsp+98h] [rbp-68h] BYREF
  __int64 v26; // [rsp+A8h] [rbp-58h]
  __int64 v27; // [rsp+B0h] [rbp-50h]
  char v28; // [rsp+B8h] [rbp-48h]
  __int128 v29; // [rsp+BCh] [rbp-44h]
  __int128 v30; // [rsp+CCh] [rbp-34h]
  __int128 v31; // [rsp+DCh] [rbp-24h]
  __int128 v32; // [rsp+ECh] [rbp-14h]
  __int128 v33; // [rsp+FCh] [rbp-4h]
  int v34; // [rsp+10Ch] [rbp+Ch]
  char v35; // [rsp+110h] [rbp+10h]
  struct _GUID v36; // [rsp+120h] [rbp+20h] BYREF
  __int16 v37; // [rsp+130h] [rbp+30h] BYREF
  char *v38[4]; // [rsp+138h] [rbp+38h] BYREF
  char *v39[4]; // [rsp+158h] [rbp+58h] BYREF
  char *v40[4]; // [rsp+178h] [rbp+78h] BYREF
  char v41; // [rsp+198h] [rbp+98h]
  __int128 v42; // [rsp+19Ch] [rbp+9Ch]
  __int128 v43; // [rsp+1ACh] [rbp+ACh]
  __int128 v44; // [rsp+1BCh] [rbp+BCh]
  __int128 v45; // [rsp+1CCh] [rbp+CCh]
  __int128 v46; // [rsp+1DCh] [rbp+DCh]
  int v47; // [rsp+1ECh] [rbp+ECh]
  char v48; // [rsp+1F0h] [rbp+F0h]
  unsigned __int16 *v49[2]; // [rsp+200h] [rbp+100h] BYREF
  __int64 v50; // [rsp+210h] [rbp+110h]
  const struct _GUID *v51; // [rsp+220h] [rbp+120h]
  __int64 v52; // [rsp+228h] [rbp+128h]

  v4 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v4 > 5u )
  {
    v51 = a2;
    v52 = 16;
    tlgWriteTransfer_EventWriteTransfer(v4, &byte_1800787C7, 0, 0, 3, v49);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
  v17 = (unsigned __int16 *)((char *)this + 40);
  v5 = std::_Tree<std::_Tmap_traits<_GUID,ATL::CComPtr<ICellularSettingsApi>,GUID_COMP,std::allocator<std::pair<_GUID const,ATL::CComPtr<ICellularSettingsApi>>>,0>>::_Find_lower_bound<_GUID>(
         (__int64)this + 16,
         v49,
         a2)[2];
  if ( *(_BYTE *)(v5 + 25) || memcmp_0(a2, (const void *)(v5 + 32), 0x10u) < 0 )
  {
    v19 = 0;
    v20 = 0;
    v21 = 7;
    LOWORD(v19) = 0;
    v22 = 0;
    v23 = 0;
    v24 = 7;
    LOWORD(v22) = 0;
    v25 = 0;
    v26 = 0;
    v27 = 7;
    LOWORD(v25) = 0;
    v18 = 0;
    v28 = 0;
    v34 = 0;
    v36 = *a2;
    v15[0] = (unsigned __int16 *)&v37;
    v37 = 0;
    std::wstring::wstring(v38, &v19);
    std::wstring::wstring(v39, &v22);
    std::wstring::wstring(v40, &v25);
    v41 = v28;
    v42 = v29;
    v43 = v30;
    v44 = v31;
    v45 = v32;
    v46 = v33;
    v47 = v34;
    v48 = v35;
    std::map<_GUID,WTModemParameters,GUID_COMP,std::allocator<std::pair<_GUID const,WTModemParameters>>>::insert<std::pair<_GUID,WTModemParameters>,0>(
      (__int64 *)this + 2,
      (__int64)v15,
      &v36);
    std::wstring::~wstring(v40);
    std::wstring::~wstring(v39);
    std::wstring::~wstring(v38);
    std::wstring::~wstring((char **)&v25);
    std::wstring::~wstring((char **)&v22);
    std::wstring::~wstring((char **)&v19);
  }
  else
  {
    *(_OWORD *)v49 = 0;
    v50 = 0;
    *(_OWORD *)v15 = 0;
    v16 = 0;
    std::vector<unsigned short>::resize(v49);
    std::vector<unsigned short>::resize(v15);
    StringCchPrintfW(v49[0], v49[1] - v49[0], L"The interface has already been added.");
    LODWORD(v14) = 245;
    StringCchPrintfW(v15[0], v15[1] - v15[0], L"%S(%d):%s", "CWwanTranslator::_AddInterface", v14, v49[0]);
    v6 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v6 > 4u )
    {
      v17 = v15[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v6,
        (__int64)byte_180078761,
        v7,
        v8,
        (const unsigned __int16 **)&v17);
    }
    std::vector<unsigned short>::~vector<unsigned short>((char **)v15);
    std::vector<unsigned short>::~vector<unsigned short>((char **)v49);
  }
  if ( this != (CWwanTranslator *)-40LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)this + 1);
  AcquireSRWLockShared((PSRWLOCK)this + 19);
  v15[0] = (unsigned __int16 *)((char *)this + 152);
  if ( *((_QWORD *)this + 4) )
  {
    v9 = (SlotBindingMap *)*((_QWORD *)this + 17);
    if ( v9 )
      SlotBindingMap::GetAdapterUiccBinding(v9, a2);
  }
  if ( this != (CWwanTranslator *)-152LL )
    ReleaseSRWLockShared((PSRWLOCK)this + 19);
  *(_OWORD *)v15 = 0;
  v16 = 0;
  *(_OWORD *)v49 = 0;
  v50 = 0;
  std::vector<unsigned short>::resize(v15);
  std::vector<unsigned short>::resize(v49);
  StringCchPrintfW(v15[0], v15[1] - v15[0], L"Exit");
  LODWORD(v14) = 258;
  StringCchPrintfW(v49[0], v49[1] - v49[0], L"%S(%d):%s", "CWwanTranslator::_AddInterface", v14, v15[0]);
  v10 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v10 > 5u )
  {
    v17 = v49[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v10,
      (__int64)byte_180078781,
      v11,
      v12,
      (const unsigned __int16 **)&v17);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v49);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v15);
  return 0;
}

```

## disassembly

```asm
0x18003b9e8  push    rbp
0x18003b9ea  push    rbx
0x18003b9eb  push    rsi
0x18003b9ec  push    rdi
0x18003b9ed  push    r14
0x18003b9ef  push    r15
0x18003b9f1  lea     rbp, [rsp-148h]
0x18003b9f9  sub     rsp, 248h
0x18003ba00  mov     rax, cs:__security_cookie
0x18003ba07  xor     rax, rsp
0x18003ba0a  mov     [rbp+170h+var_40], rax
0x18003ba11  mov     rsi, rdx
0x18003ba14  mov     rdi, rcx
0x18003ba17  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18003ba1c  mov     r8d, [rax]
0x18003ba1f  xor     r15d, r15d
0x18003ba22  cmp     r8d, 5
0x18003ba26  jbe     short loc_18003BA63
0x18003ba28  mov     [rbp+170h+var_50], rsi
0x18003ba2f  mov     [rbp+170h+var_48], 10h
0x18003ba3a  lea     rcx, [rbp+170h+var_70]
0x18003ba41  mov     [rsp+270h+var_248], rcx
0x18003ba46  mov     dword ptr [rsp+270h+var_250], 3
0x18003ba4e  xor     r9d, r9d
0x18003ba51  xor     r8d, r8d
0x18003ba54  lea     rdx, byte_1800787C7
0x18003ba5b  mov     rcx, rax
0x18003ba5e  call    _tlgWriteTransfer_EventWriteTransfer
0x18003ba63  lea     rbx, [rdi+28h]
0x18003ba67  mov     rcx, rbx; lpCriticalSection
0x18003ba6a  call    cs:__imp_EnterCriticalSection
0x18003ba70  mov     [rsp+270h+var_228], rbx
0x18003ba75  mov     r8, rsi
0x18003ba78  lea     rdx, [rbp+170h+var_70]
0x18003ba7f  lea     rcx, [rdi+10h]
0x18003ba83  call    ??$_Find_lower_bound@U_GUID@@@?$_Tree@V?$_Tmap_traits@U_GUID@@V?$CComPtr@UICellularSettingsApi@@@ATL@@UGUID_COMP@@V?$allocator@U?$pair@$$CBU_GUID@@V?$CComPtr@UICellularSettingsApi@@@ATL@@@std@@@std@@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$CComPtr@UICellularSettingsApi@@@ATL@@@std@@PEAX@std@@@1@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,ATL::CComPtr<ICellularSettingsApi>,GUID_COMP,std::allocator<std::pair<_GUID const,ATL::CComPtr<ICellularSettingsApi>>>,0>>::_Find_lower_bound<_GUID>(_GUID const &)
0x18003ba88  mov     rdx, [rax+10h]
0x18003ba8c  cmp     [rdx+19h], r15b
0x18003ba90  jnz     loc_18003BB86
0x18003ba96  add     rdx, 20h ; ' '; Buf2
0x18003ba9a  mov     r8d, 10h; Size
0x18003baa0  mov     rcx, rsi; Buf1
0x18003baa3  call    memcmp_0
0x18003baa8  test    eax, eax
0x18003baaa  js      loc_18003BB86
0x18003bab0  xorps   xmm0, xmm0
0x18003bab3  movdqu  xmmword ptr [rbp+170h+var_70], xmm0
0x18003babb  mov     [rbp+170h+var_60], r15
0x18003bac2  movdqu  xmmword ptr [rsp+270h+var_240], xmm0
0x18003bac8  mov     [rsp+270h+var_230], r15
0x18003bacd  lea     rcx, [rbp+170h+var_70]
0x18003bad4  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003bad9  lea     rcx, [rsp+270h+var_240]
0x18003bade  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003bae3  mov     rdx, [rbp+170h+var_70+8]
0x18003baea  mov     rcx, [rbp+170h+var_70]; unsigned __int16 *
0x18003baf1  sub     rdx, rcx
0x18003baf4  sar     rdx, 1; unsigned __int64
0x18003baf7  lea     r8, aTheInterfaceHa; "The interface has already been added."
0x18003bafe  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003bb03  mov     rdx, [rsp+270h+var_240+8]
0x18003bb08  mov     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x18003bb0d  sub     rdx, rcx
0x18003bb10  sar     rdx, 1; unsigned __int64
0x18003bb13  mov     rax, [rbp+170h+var_70]
0x18003bb1a  mov     [rsp+270h+var_248], rax
0x18003bb1f  mov     dword ptr [rsp+270h+var_250], 0F5h
0x18003bb27  lea     r9, aCwwantranslato_55; "CWwanTranslator::_AddInterface"
0x18003bb2e  lea     r8, aSDS; "%S(%d):%s"
0x18003bb35  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003bb3a  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18003bb3f  mov     ecx, [rax]
0x18003bb41  cmp     ecx, 4
0x18003bb44  jbe     short loc_18003BB6A
0x18003bb46  mov     rcx, [rsp+270h+var_240]
0x18003bb4b  mov     [rsp+270h+var_228], rcx
0x18003bb50  lea     rcx, [rsp+270h+var_228]
0x18003bb55  mov     [rsp+270h+var_250], rcx
0x18003bb5a  lea     rdx, byte_180078761
0x18003bb61  mov     rcx, rax
0x18003bb64  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18003bb69  nop
0x18003bb6a  lea     rcx, [rsp+270h+var_240]
0x18003bb6f  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003bb74  nop
0x18003bb75  lea     rcx, [rbp+170h+var_70]
0x18003bb7c  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003bb81  jmp     loc_18003BCB5
0x18003bb86  xorps   xmm0, xmm0
0x18003bb89  movups  [rsp+270h+var_218], xmm0
0x18003bb8e  mov     [rsp+270h+var_208], r15
0x18003bb93  mov     ecx, 7
0x18003bb98  mov     [rsp+270h+var_200], rcx
0x18003bb9d  mov     word ptr [rsp+270h+var_218], r15w
0x18003bba3  movups  [rsp+270h+var_1F8], xmm0
0x18003bba8  mov     [rbp+170h+var_1E8], r15
0x18003bbac  mov     [rbp+170h+var_1E0], rcx
0x18003bbb0  mov     word ptr [rsp+270h+var_1F8], r15w
0x18003bbb6  movups  [rbp+170h+var_1D8], xmm0
0x18003bbba  mov     [rbp+170h+var_1C8], r15
0x18003bbbe  mov     [rbp+170h+var_1C0], rcx
0x18003bbc2  mov     word ptr [rbp+170h+var_1D8], r15w
0x18003bbc7  mov     [rsp+270h+var_220], r15w
0x18003bbcd  mov     [rbp+170h+var_1B8], r15b
0x18003bbd1  mov     [rbp+170h+var_164], r15d
0x18003bbd5  movups  xmm0, xmmword ptr [rsi]
0x18003bbd8  movdqu  [rbp+170h+var_150], xmm0
0x18003bbdd  lea     rax, [rbp+170h+var_140]
0x18003bbe1  mov     [rsp+270h+var_240], rax
0x18003bbe6  mov     [rbp+170h+var_140], r15w
0x18003bbeb  lea     rdx, [rsp+270h+var_218]
0x18003bbf0  lea     rcx, [rbp+170h+var_138]
0x18003bbf4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003bbf9  nop
0x18003bbfa  lea     rdx, [rsp+270h+var_1F8]
0x18003bbff  lea     rcx, [rbp+170h+var_118]
0x18003bc03  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003bc08  nop
0x18003bc09  lea     rdx, [rbp+170h+var_1D8]
0x18003bc0d  lea     rcx, [rbp+170h+var_F8]
0x18003bc11  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003bc16  mov     al, [rbp+170h+var_1B8]
0x18003bc19  mov     [rbp+170h+var_D8], al
0x18003bc1f  movups  xmm0, [rbp+170h+var_1B4]
0x18003bc23  movups  [rbp+170h+var_D4], xmm0
0x18003bc2a  movups  xmm1, [rbp+170h+var_1A4]
0x18003bc2e  movups  [rbp+170h+var_C4], xmm1
0x18003bc35  movups  xmm0, [rbp+170h+var_194]
0x18003bc39  movups  [rbp+170h+var_B4], xmm0
0x18003bc40  movups  xmm1, [rbp+170h+var_184]
0x18003bc44  movups  [rbp+170h+var_A4], xmm1
0x18003bc4b  movups  xmm0, [rbp+170h+var_174]
0x18003bc4f  movups  [rbp+170h+var_94], xmm0
0x18003bc56  mov     eax, [rbp+170h+var_164]
0x18003bc59  mov     [rbp+170h+var_84], eax
0x18003bc5f  mov     al, [rbp+170h+var_160]
0x18003bc62  mov     [rbp+170h+var_80], al
0x18003bc68  lea     r8, [rbp+170h+var_150]
0x18003bc6c  lea     rdx, [rsp+270h+var_240]
0x18003bc71  lea     rcx, [rdi+10h]
0x18003bc75  call    ??$insert@U?$pair@U_GUID@@UWTModemParameters@@@std@@$0A@@?$map@U_GUID@@UWTModemParameters@@UGUID_COMP@@V?$allocator@U?$pair@$$CBU_GUID@@UWTModemParameters@@@std@@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@UWTModemParameters@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@U_GUID@@UWTModemParameters@@@1@@Z; std::map<_GUID,WTModemParameters,GUID_COMP,std::allocator<std::pair<_GUID const,WTModemParameters>>>::insert<std::pair<_GUID,WTModemParameters>,0>(std::pair<_GUID,WTModemParameters> &&)
0x18003bc7a  nop
0x18003bc7b  lea     rcx, [rbp+170h+var_F8]
0x18003bc7f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003bc84  lea     rcx, [rbp+170h+var_118]
0x18003bc88  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003bc8d  lea     rcx, [rbp+170h+var_138]
0x18003bc91  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003bc96  nop
0x18003bc97  lea     rcx, [rbp+170h+var_1D8]
0x18003bc9b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003bca0  lea     rcx, [rsp+270h+var_1F8]
0x18003bca5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003bcaa  lea     rcx, [rsp+270h+var_218]
0x18003bcaf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003bcb4  nop
0x18003bcb5  test    rbx, rbx
0x18003bcb8  jz      short loc_18003BCC3
0x18003bcba  mov     rcx, rbx; lpCriticalSection
0x18003bcbd  call    cs:__imp_LeaveCriticalSection
0x18003bcc3  lea     rbx, [rdi+98h]
0x18003bcca  mov     rcx, rbx; SRWLock
0x18003bccd  call    cs:__imp_AcquireSRWLockShared
0x18003bcd3  mov     [rsp+270h+var_240], rbx
0x18003bcd8  cmp     [rdi+20h], r15
0x18003bcdc  jz      short loc_18003BCF3
0x18003bcde  mov     rcx, [rdi+88h]; this
0x18003bce5  test    rcx, rcx
0x18003bce8  jz      short loc_18003BCF3
0x18003bcea  mov     rdx, rsi; Buf1
0x18003bced  call    ?GetAdapterUiccBinding@SlotBindingMap@@QEAAJAEBU_GUID@@@Z; SlotBindingMap::GetAdapterUiccBinding(_GUID const &)
0x18003bcf2  nop
0x18003bcf3  test    rbx, rbx
0x18003bcf6  jz      short loc_18003BD01
0x18003bcf8  mov     rcx, rbx; SRWLock
0x18003bcfb  call    cs:__imp_ReleaseSRWLockShared
0x18003bd01  xorps   xmm0, xmm0
0x18003bd04  movdqu  xmmword ptr [rsp+270h+var_240], xmm0
0x18003bd0a  mov     [rsp+270h+var_230], r15
0x18003bd0f  movdqu  xmmword ptr [rbp+170h+var_70], xmm0
0x18003bd17  mov     [rbp+170h+var_60], r15
0x18003bd1e  lea     rcx, [rsp+270h+var_240]
0x18003bd23  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003bd28  lea     rcx, [rbp+170h+var_70]
0x18003bd2f  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003bd34  mov     rdx, [rsp+270h+var_240+8]
0x18003bd39  mov     rcx, [rsp+270h+var_240]; unsigned __int16 *
0x18003bd3e  sub     rdx, rcx
0x18003bd41  sar     rdx, 1; unsigned __int64
0x18003bd44  lea     r8, aExit; "Exit"
0x18003bd4b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003bd50  mov     rdx, [rbp+170h+var_70+8]
0x18003bd57  mov     rcx, [rbp+170h+var_70]; unsigned __int16 *
0x18003bd5e  sub     rdx, rcx
0x18003bd61  sar     rdx, 1; unsigned __int64
0x18003bd64  mov     rax, [rsp+270h+var_240]
0x18003bd69  mov     [rsp+270h+var_248], rax
0x18003bd6e  mov     dword ptr [rsp+270h+var_250], 102h
0x18003bd76  lea     r9, aCwwantranslato_55; "CWwanTranslator::_AddInterface"
0x18003bd7d  lea     r8, aSDS; "%S(%d):%s"
0x18003bd84  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003bd89  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18003bd8e  mov     ecx, [rax]
0x18003bd90  cmp     ecx, 5
0x18003bd93  jbe     short loc_18003BDBB
0x18003bd95  mov     rcx, [rbp+170h+var_70]
0x18003bd9c  mov     [rsp+270h+var_228], rcx
0x18003bda1  lea     rcx, [rsp+270h+var_228]
0x18003bda6  mov     [rsp+270h+var_250], rcx
0x18003bdab  lea     rdx, byte_180078781
0x18003bdb2  mov     rcx, rax
0x18003bdb5  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18003bdba  nop
0x18003bdbb  lea     rcx, [rbp+170h+var_70]
0x18003bdc2  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003bdc7  nop
0x18003bdc8  lea     rcx, [rsp+270h+var_240]
0x18003bdcd  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003bdd2  xor     eax, eax
0x18003bdd4  mov     rcx, [rbp+170h+var_40]
0x18003bddb  xor     rcx, rsp; StackCookie
0x18003bdde  call    __security_check_cookie
0x18003bde3  add     rsp, 248h
0x18003bdea  pop     r15
0x18003bdec  pop     r14
0x18003bdee  pop     rdi
0x18003bdef  pop     rsi
0x18003bdf0  pop     rbx
0x18003bdf1  pop     rbp
0x18003bdf2  retn
```
