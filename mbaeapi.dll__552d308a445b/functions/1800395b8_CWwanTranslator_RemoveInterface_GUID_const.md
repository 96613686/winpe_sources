# CWwanTranslator::RemoveInterface(_GUID const &)

- ea: `0x1800395b8`
- end: `0x180039945`
- name: `?RemoveInterface@CWwanTranslator@@QEAAJAEBU_GUID@@@Z`
- size: `909`
- prototype: `int(CWwanTranslator *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001b080`

## callees

- `0x1800016ec`
- `0x18000178c`
- `0x1800024e0`
- `0x1800028b0`
- `0x1800040cd`
- `0x180009ffc`
- `0x18001105c`
- `0x180016bc0`
- `0x1800171b8`
- `0x1800172bc`
- `0x18001c950`
- `0x18001dd10`
- `0x1800395b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800397a2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003991e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800397a2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003991e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800396dc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800396dc`

## string_xrefs

- `0x180039644`: `CWwanTranslator::RemoveInterface`
- `0x180039808`: `CWwanTranslator::RemoveInterface`
- `0x1800398c2`: `CWwanTranslator::RemoveInterface`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CWwanTranslator::RemoveInterface(struct _RTL_CRITICAL_SECTION *this, const struct _GUID *a2)
{
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // r8
  __int64 v6; // r9
  const struct _tlgProvider_t *v7; // rax
  _QWORD *v8; // rbx
  __int64 **v9; // rcx
  _QWORD *v10; // rdx
  __int64 i; // rax
  __int64 *j; // rcx
  char **v13; // rbx
  const struct _tlgProvider_t *v14; // rax
  __int64 v15; // r8
  __int64 v16; // r9
  const struct _tlgProvider_t *v18; // rax
  __int64 v19; // r8
  __int64 v20; // r9
  int v21; // [rsp+20h] [rbp-49h]
  __int64 v22; // [rsp+20h] [rbp-49h]
  unsigned __int16 *v23; // [rsp+30h] [rbp-39h] BYREF
  unsigned __int16 *v24[2]; // [rsp+38h] [rbp-31h] BYREF
  __int64 v25; // [rsp+48h] [rbp-21h]
  unsigned __int16 *v26[2]; // [rsp+50h] [rbp-19h] BYREF
  __int64 v27; // [rsp+60h] [rbp-9h]
  const struct _GUID *v28; // [rsp+70h] [rbp+7h]
  __int64 v29; // [rsp+78h] [rbp+Fh]

  *(_OWORD *)v26 = 0;
  v27 = 0;
  *(_OWORD *)v24 = 0;
  v25 = 0;
  std::vector<unsigned short>::resize(v26);
  std::vector<unsigned short>::resize(v24);
  StringCchPrintfW(v26[0], v26[1] - v26[0], L"Enter");
  v21 = 264;
  StringCchPrintfW(v24[0], v24[1] - v24[0], L"%S(%d):%s", "CWwanTranslator::RemoveInterface", v21, v26[0]);
  v4 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v4 > 5u )
  {
    v23 = v24[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v4,
      (__int64)byte_180078703,
      v5,
      v6,
      (const unsigned __int16 **)&v23);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v24);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v26);
  v7 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v7 > 5u )
  {
    v28 = a2;
    v29 = 16;
    tlgWriteTransfer_EventWriteTransfer(
      (__int64)v7,
      (unsigned __int8 *)&word_180078726,
      0,
      0,
      3u,
      (PEVENT_DATA_DESCRIPTOR)v26);
  }
  EnterCriticalSection(this + 1);
  v23 = (unsigned __int16 *)&this[1];
  std::_Tree<std::_Tmap_traits<_GUID,ATL::CComPtr<ICellularSettingsApi>,GUID_COMP,std::allocator<std::pair<_GUID const,ATL::CComPtr<ICellularSettingsApi>>>,0>>::_Find_lower_bound<_GUID>(
    (__int64)&this->OwningThread,
    v26,
    a2);
  v8 = (_QWORD *)v27;
  if ( *(_BYTE *)(v27 + 25) || memcmp_0(a2, (const void *)(v27 + 32), 0x10u) < 0 || this->OwningThread == v8 )
  {
    *(_OWORD *)v24 = 0;
    v25 = 0;
    *(_OWORD *)v26 = 0;
    v27 = 0;
    std::vector<unsigned short>::resize(v24);
    std::vector<unsigned short>::resize(v26);
    StringCchPrintfW(v24[0], v24[1] - v24[0], L"Cannot find the given adapter in current adapter list.");
    LODWORD(v22) = 274;
    StringCchPrintfW(v26[0], v26[1] - v26[0], L"%S(%d):%s", "CWwanTranslator::RemoveInterface", v22, v24[0]);
    v18 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v18 > 2u )
    {
      v23 = v26[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v18,
        (__int64)&byte_1800786BF,
        v19,
        v20,
        (const unsigned __int16 **)&v23);
    }
    std::vector<unsigned short>::~vector<unsigned short>((char **)v26);
    std::vector<unsigned short>::~vector<unsigned short>((char **)v24);
    if ( this != (struct _RTL_CRITICAL_SECTION *)-40LL )
      LeaveCriticalSection(this + 1);
    return 2147942487LL;
  }
  else
  {
    v9 = (__int64 **)v8[2];
    v10 = v8;
    if ( *((_BYTE *)v9 + 25) )
    {
      for ( i = v8[1]; !*(_BYTE *)(i + 25) && v8 == *(_QWORD **)(i + 16); i = *(_QWORD *)(i + 8) )
        v8 = (_QWORD *)i;
    }
    else
    {
      for ( j = *v9; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        ;
    }
    v13 = (char **)std::_Tree_val<std::_Tree_simple_types<std::pair<std::pair<_GUID,enum SimSlot> const,bool>>>::_Extract(
                     &this->OwningThread,
                     v10);
    std::wstring::~wstring(v13 + 15);
    std::wstring::~wstring(v13 + 11);
    std::wstring::~wstring(v13 + 7);
    operator delete(v13);
    if ( this != (struct _RTL_CRITICAL_SECTION *)-40LL )
      LeaveCriticalSection(this + 1);
    *(_OWORD *)v24 = 0;
    v25 = 0;
    *(_OWORD *)v26 = 0;
    v27 = 0;
    std::vector<unsigned short>::resize(v24);
    std::vector<unsigned short>::resize(v26);
    StringCchPrintfW(v24[0], v24[1] - v24[0], L"Exit");
    LODWORD(v22) = 283;
    StringCchPrintfW(v26[0], v26[1] - v26[0], L"%S(%d):%s", "CWwanTranslator::RemoveInterface", v22, v24[0]);
    v14 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v14 > 5u )
    {
      v23 = v26[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v14,
        (__int64)qword_1800786E0,
        v15,
        v16,
        (const unsigned __int16 **)&v23);
    }
    std::vector<unsigned short>::~vector<unsigned short>((char **)v26);
    std::vector<unsigned short>::~vector<unsigned short>((char **)v24);
    return 0;
  }
}

```

## disassembly

```asm
0x1800395b8  push    rbp
0x1800395ba  push    rbx
0x1800395bb  push    rsi
0x1800395bc  push    rdi
0x1800395bd  push    r14
0x1800395bf  push    r15
0x1800395c1  lea     rbp, [rsp-2Fh]
0x1800395c6  sub     rsp, 98h
0x1800395cd  mov     rax, cs:__security_cookie
0x1800395d4  xor     rax, rsp
0x1800395d7  mov     [rbp+57h+var_40], rax
0x1800395db  mov     r14, rdx
0x1800395de  mov     rsi, rcx
0x1800395e1  xorps   xmm0, xmm0
0x1800395e4  movdqu  xmmword ptr [rbp+57h+var_70], xmm0
0x1800395e9  xor     r15d, r15d
0x1800395ec  mov     [rbp+57h+var_60], r15
0x1800395f0  movdqu  xmmword ptr [rbp+57h+var_88], xmm0
0x1800395f5  mov     [rbp+57h+var_78], r15
0x1800395f9  lea     rcx, [rbp+57h+var_70]
0x1800395fd  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180039602  lea     rcx, [rbp+57h+var_88]
0x180039606  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003960b  mov     rdx, [rbp+57h+var_70+8]
0x18003960f  mov     rcx, [rbp+57h+var_70]; unsigned __int16 *
0x180039613  sub     rdx, rcx
0x180039616  sar     rdx, 1; unsigned __int64
0x180039619  lea     r8, aEnter; "Enter"
0x180039620  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180039625  mov     rdx, [rbp+57h+var_88+8]
0x180039629  mov     rcx, [rbp+57h+var_88]; unsigned __int16 *
0x18003962d  sub     rdx, rcx
0x180039630  sar     rdx, 1; unsigned __int64
0x180039633  mov     rax, [rbp+57h+var_70]
0x180039637  mov     [rsp+0C0h+var_98], rax
0x18003963c  mov     dword ptr [rsp+0C0h+var_A0], 108h
0x180039644  lea     r9, aCwwantranslato_6; "CWwanTranslator::RemoveInterface"
0x18003964b  lea     r8, aSDS; "%S(%d):%s"
0x180039652  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180039657  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18003965c  mov     ecx, [rax]
0x18003965e  cmp     ecx, 5
0x180039661  jbe     short loc_180039684
0x180039663  mov     rcx, [rbp+57h+var_88]
0x180039667  mov     [rbp+57h+var_90], rcx
0x18003966b  lea     rcx, [rbp+57h+var_90]
0x18003966f  mov     [rsp+0C0h+var_A0], rcx
0x180039674  lea     rdx, byte_180078703
0x18003967b  mov     rcx, rax
0x18003967e  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180039683  nop
0x180039684  lea     rcx, [rbp+57h+var_88]
0x180039688  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003968d  nop
0x18003968e  lea     rcx, [rbp+57h+var_70]
0x180039692  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180039697  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18003969c  mov     ecx, [rax]
0x18003969e  cmp     ecx, 5
0x1800396a1  jbe     short loc_1800396D5
0x1800396a3  mov     [rbp+57h+var_50], r14
0x1800396a7  mov     [rbp+57h+var_48], 10h
0x1800396af  lea     rcx, [rbp+57h+var_70]
0x1800396b3  mov     [rsp+0C0h+var_98], rcx
0x1800396b8  mov     dword ptr [rsp+0C0h+var_A0], 3
0x1800396c0  xor     r9d, r9d
0x1800396c3  xor     r8d, r8d
0x1800396c6  lea     rdx, word_180078726
0x1800396cd  mov     rcx, rax
0x1800396d0  call    _tlgWriteTransfer_EventWriteTransfer
0x1800396d5  lea     rdi, [rsi+28h]
0x1800396d9  mov     rcx, rdi; lpCriticalSection
0x1800396dc  call    cs:__imp_EnterCriticalSection
0x1800396e2  mov     [rbp+57h+var_90], rdi
0x1800396e6  mov     r8, r14
0x1800396e9  lea     rdx, [rbp+57h+var_70]
0x1800396ed  lea     rcx, [rsi+10h]
0x1800396f1  call    ??$_Find_lower_bound@U_GUID@@@?$_Tree@V?$_Tmap_traits@U_GUID@@V?$CComPtr@UICellularSettingsApi@@@ATL@@UGUID_COMP@@V?$allocator@U?$pair@$$CBU_GUID@@V?$CComPtr@UICellularSettingsApi@@@ATL@@@std@@@std@@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$CComPtr@UICellularSettingsApi@@@ATL@@@std@@PEAX@std@@@1@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,ATL::CComPtr<ICellularSettingsApi>,GUID_COMP,std::allocator<std::pair<_GUID const,ATL::CComPtr<ICellularSettingsApi>>>,0>>::_Find_lower_bound<_GUID>(_GUID const &)
0x1800396f6  mov     rbx, [rbp+57h+var_60]
0x1800396fa  cmp     [rbx+19h], r15b
0x1800396fe  jnz     loc_180039862
0x180039704  lea     rdx, [rbx+20h]; Buf2
0x180039708  mov     r8d, 10h; Size
0x18003970e  mov     rcx, r14; Buf1
0x180039711  call    memcmp_0
0x180039716  test    eax, eax
0x180039718  js      loc_180039862
0x18003971e  cmp     [rsi+10h], rbx
0x180039722  jz      loc_180039862
0x180039728  mov     rcx, [rbx+10h]
0x18003972c  mov     rdx, rbx
0x18003972f  cmp     [rcx+19h], r15b
0x180039733  jz      short loc_180039750
0x180039735  mov     rax, [rbx+8]
0x180039739  jmp     short loc_180039748
0x18003973b  cmp     rbx, [rax+10h]
0x18003973f  jnz     short loc_180039765
0x180039741  mov     rbx, rax
0x180039744  mov     rax, [rax+8]
0x180039748  cmp     [rax+19h], r15b
0x18003974c  jz      short loc_18003973B
0x18003974e  jmp     short loc_180039765
0x180039750  mov     rcx, [rcx]
0x180039753  cmp     [rcx+19h], r15b
0x180039757  jnz     short loc_180039765
0x180039759  mov     rax, [rcx]
0x18003975c  mov     rcx, rax
0x18003975f  cmp     [rax+19h], r15b
0x180039763  jz      short loc_180039759
0x180039765  lea     rcx, [rsi+10h]
0x180039769  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU?$pair@U_GUID@@W4SimSlot@@@std@@_N@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBU?$pair@U_GUID@@W4SimSlot@@@std@@_N@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU?$pair@U_GUID@@W4SimSlot@@@std@@_N@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::pair<_GUID,SimSlot> const,bool>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::pair<_GUID,SimSlot> const,bool>>>,std::_Iterator_base0>)
0x18003976e  mov     rbx, rax
0x180039771  lea     rcx, [rax+78h]
0x180039775  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003977a  lea     rcx, [rbx+58h]
0x18003977e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180039783  lea     rcx, [rbx+38h]
0x180039787  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003978c  mov     edx, 0F8h
0x180039791  mov     rcx, rbx; Block
0x180039794  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180039799  nop
0x18003979a  test    rdi, rdi
0x18003979d  jz      short loc_1800397A8
0x18003979f  mov     rcx, rdi; lpCriticalSection
0x1800397a2  call    cs:__imp_LeaveCriticalSection
0x1800397a8  xorps   xmm0, xmm0
0x1800397ab  movdqu  xmmword ptr [rbp+57h+var_88], xmm0
0x1800397b0  mov     [rbp+57h+var_78], r15
0x1800397b4  movdqu  xmmword ptr [rbp+57h+var_70], xmm0
0x1800397b9  mov     [rbp+57h+var_60], r15
0x1800397bd  lea     rcx, [rbp+57h+var_88]
0x1800397c1  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800397c6  lea     rcx, [rbp+57h+var_70]
0x1800397ca  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800397cf  mov     rdx, [rbp+57h+var_88+8]
0x1800397d3  mov     rcx, [rbp+57h+var_88]; unsigned __int16 *
0x1800397d7  sub     rdx, rcx
0x1800397da  sar     rdx, 1; unsigned __int64
0x1800397dd  lea     r8, aExit; "Exit"
0x1800397e4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800397e9  mov     rdx, [rbp+57h+var_70+8]
0x1800397ed  mov     rcx, [rbp+57h+var_70]; unsigned __int16 *
0x1800397f1  sub     rdx, rcx
0x1800397f4  sar     rdx, 1; unsigned __int64
0x1800397f7  mov     rax, [rbp+57h+var_88]
0x1800397fb  mov     [rsp+0C0h+var_98], rax
0x180039800  mov     dword ptr [rsp+0C0h+var_A0], 11Bh
0x180039808  lea     r9, aCwwantranslato_6; "CWwanTranslator::RemoveInterface"
0x18003980f  lea     r8, aSDS; "%S(%d):%s"
0x180039816  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003981b  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180039820  mov     ecx, [rax]
0x180039822  cmp     ecx, 5
0x180039825  jbe     short loc_180039848
0x180039827  mov     rcx, [rbp+57h+var_70]
0x18003982b  mov     [rbp+57h+var_90], rcx
0x18003982f  lea     rcx, [rbp+57h+var_90]
0x180039833  mov     [rsp+0C0h+var_A0], rcx
0x180039838  lea     rdx, qword_1800786E0
0x18003983f  mov     rcx, rax
0x180039842  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180039847  nop
0x180039848  lea     rcx, [rbp+57h+var_70]
0x18003984c  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180039851  nop
0x180039852  lea     rcx, [rbp+57h+var_88]
0x180039856  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003985b  xor     eax, eax
0x18003985d  jmp     loc_180039929
0x180039862  xorps   xmm0, xmm0
0x180039865  movdqu  xmmword ptr [rbp+57h+var_88], xmm0
0x18003986a  mov     [rbp+57h+var_78], r15
0x18003986e  movdqu  xmmword ptr [rbp+57h+var_70], xmm0
0x180039873  mov     [rbp+57h+var_60], r15
0x180039877  lea     rcx, [rbp+57h+var_88]
0x18003987b  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180039880  lea     rcx, [rbp+57h+var_70]
0x180039884  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180039889  mov     rdx, [rbp+57h+var_88+8]
0x18003988d  mov     rcx, [rbp+57h+var_88]; unsigned __int16 *
0x180039891  sub     rdx, rcx
0x180039894  sar     rdx, 1; unsigned __int64
0x180039897  lea     r8, aCannotFindTheG; "Cannot find the given adapter in curren"...
0x18003989e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800398a3  mov     rdx, [rbp+57h+var_70+8]
0x1800398a7  mov     rcx, [rbp+57h+var_70]; unsigned __int16 *
0x1800398ab  sub     rdx, rcx
0x1800398ae  sar     rdx, 1; unsigned __int64
0x1800398b1  mov     rax, [rbp+57h+var_88]
0x1800398b5  mov     [rsp+0C0h+var_98], rax
0x1800398ba  mov     dword ptr [rsp+0C0h+var_A0], 112h
0x1800398c2  lea     r9, aCwwantranslato_6; "CWwanTranslator::RemoveInterface"
0x1800398c9  lea     r8, aSDS; "%S(%d):%s"
0x1800398d0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800398d5  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x1800398da  mov     ecx, [rax]
0x1800398dc  cmp     ecx, 2
0x1800398df  jbe     short loc_180039902
0x1800398e1  mov     rcx, [rbp+57h+var_70]
0x1800398e5  mov     [rbp+57h+var_90], rcx
0x1800398e9  lea     rcx, [rbp+57h+var_90]
0x1800398ed  mov     [rsp+0C0h+var_A0], rcx
0x1800398f2  lea     rdx, byte_1800786BF
0x1800398f9  mov     rcx, rax
0x1800398fc  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180039901  nop
0x180039902  lea     rcx, [rbp+57h+var_70]
0x180039906  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003990b  nop
0x18003990c  lea     rcx, [rbp+57h+var_88]
0x180039910  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180039915  nop
0x180039916  test    rdi, rdi
0x180039919  jz      short loc_180039924
0x18003991b  mov     rcx, rdi; lpCriticalSection
0x18003991e  call    cs:__imp_LeaveCriticalSection
0x180039924  mov     eax, 80070057h
0x180039929  mov     rcx, [rbp+57h+var_40]
0x18003992d  xor     rcx, rsp; StackCookie
0x180039930  call    __security_check_cookie
0x180039935  add     rsp, 98h
0x18003993c  pop     r15
0x18003993e  pop     r14
0x180039940  pop     rdi
0x180039941  pop     rsi
0x180039942  pop     rbx
0x180039943  pop     rbp
0x180039944  retn
```
