# CTriggerMonitorPool::CTriggerMonitorPool(_com_ptr_t<_com_IIID<IMSMQTriggersConfig,&__s_GUID const _GUID_7c55d6a1_f584_11d2_89b2_000000000000>>,wchar_t const *)

- ea: `0x14000a6dc`
- end: `0x14000aae5`
- name: `??0CTriggerMonitorPool@@QEAA@V?$_com_ptr_t@V?$_com_IIID@UIMSMQTriggersConfig@@$1?_GUID_7c55d6a1_f584_11d2_89b2_000000000000@@3U__s_GUID@@B@@@@PEB_W@Z`
- size: `1033`
- prototype: `char *__fastcall(char *ArgList, __int64 *, const wchar_t *)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000e768`

## callees

- `0x140001cc6`
- `0x1400030ac`
- `0x140003868`
- `0x140003dc8`
- `0x140004648`
- `0x1400046bc`
- `0x140004eb4`
- `0x140005cb0`
- `0x140006a9c`
- `0x14000752c`
- `0x140007554`
- `0x1400076a8`
- `0x140008034`
- `0x14000a6b4`
- `0x14000a6dc`
- `0x14000ab14`
- `0x14000b23c`
- `0x14000c9b0`
- `0x14000ec38`
- `0x14000f444`
- `0x14000f858`
- `0x140020010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000a7df`
- `KERNEL32!GetLastError` at `0x14000a7df`
- `KERNEL32!CreateEventW` at `0x14000a74d`
- `KERNEL32!CreateEventW` at `0x14000a74d`
- `msvcrt!_wcsicmp` at `0x14000a8c4`
- `msvcrt!_wcsicmp` at `0x14000a8c4`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x14000a815`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x14000a815`
- `OLEAUT32!__imp_SysFreeString` at `0x14000aabb`
- `OLEAUT32!__imp_SysFreeString` at `0x14000aabb`

## pseudocode

```c
char *__fastcall CTriggerMonitorPool::CTriggerMonitorPool(char *ArgList, __int64 *a2, const wchar_t *a3)
{
  __int64 v6; // rdx
  __int64 v7; // r8
  int v8; // esi
  int v9; // esi
  int v10; // edi
  int Instance; // edi
  __int64 v12; // rax
  struct IUnknown *v13; // rdi
  OLECHAR *v14; // rax
  _bstr_t *v15; // rsi
  __int64 v16; // rdx
  int v17; // eax
  BSTR bstrString[2]; // [rsp+30h] [rbp-40h] BYREF
  _QWORD pExceptionObject[3]; // [rsp+40h] [rbp-30h] BYREF
  int v21; // [rsp+58h] [rbp-18h]
  __int64 v22; // [rsp+60h] [rbp-10h]
  __int64 v23; // [rsp+C8h] [rbp+58h] BYREF

  v23 = *a2;
  _com_ptr_t<_com_IIID<IMSMQTriggersConfig,&__s_GUID const _GUID_7c55d6a1_f584_11d2_89b2_000000000000>>::_AddRef(&v23);
  CThread::CThread(ArgList, v6, v7, (__int64)L"CTriggerMonitorPool", &v23);
  *(_QWORD *)ArgList = &CTriggerMonitorPool::`vftable';
  CCriticalSection::CCriticalSection((CCriticalSection *)(ArgList + 96));
  *((_QWORD *)ArgList + 19) = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)ArgList + 21) = 0;
  *((_QWORD *)ArgList + 23) = std::list<CRuntimeRuleInfo *>::_Buynode();
  *((_QWORD *)ArgList + 24) = 0;
  std::list<CAdminMessage *>::list<CAdminMessage *>(ArgList + 200);
  CCriticalSection::CCriticalSection((CCriticalSection *)(ArgList + 224));
  *((_QWORD *)ArgList + 33) = 0;
  *((_QWORD *)ArgList + 34) = 0;
  *((_QWORD *)ArgList + 35) = 0;
  *((_QWORD *)ArgList + 36) = 0;
  *(_QWORD *)(ArgList + 1324) = 0;
  if ( !*((_QWORD *)ArgList + 19) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_f3298f65ec353b4f3993aea62a87602f_Traceguids);
    }
    exception::exception((exception *)pExceptionObject, &std::_bad_alloc_Message, 1);
    pExceptionObject[0] = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)pExceptionObject;
  }
  ArgList[88] = 0;
  *((_DWORD *)ArgList + 40) = 0;
  GetTimeAsBSTR((struct _bstr_t *)(ArgList + 272));
  GetTimeAsBSTR((struct _bstr_t *)(ArgList + 280));
  v8 = StringCchCopyW((wchar_t *)ArgList + 148, 0x200u, L"Software\\Microsoft\\MSMQ\\Triggers");
  if ( v8 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_f3298f65ec353b4f3993aea62a87602f_Traceguids);
    bad_string_result::bad_string_result((bad_string_result *)pExceptionObject, v8);
    throw (bad_string_result *)pExceptionObject;
  }
  if ( _wcsicmp(a3, L"MSMQTriggers") )
  {
    v9 = StringCchCatW((wchar_t *)ArgList + 148, 0x200u, L"\\Clustered\\");
    if ( v9 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_f3298f65ec353b4f3993aea62a87602f_Traceguids);
      bad_string_result::bad_string_result((bad_string_result *)pExceptionObject, v9);
      throw (bad_string_result *)pExceptionObject;
    }
    v10 = StringCchCatW((wchar_t *)ArgList + 148, 0x200u, a3);
    if ( v10 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_f3298f65ec353b4f3993aea62a87602f_Traceguids);
      bad_string_result::bad_string_result((bad_string_result *)pExceptionObject, v10);
      throw (bad_string_result *)pExceptionObject;
    }
  }
  LODWORD(pExceptionObject[0]) = 0;
  pExceptionObject[1] = L"Software\\Microsoft\\MSMQ\\Triggers";
  pExceptionObject[2] = L"RemoteQueueRefreshFrequency";
  v21 = 0;
  v22 = -2147483646;
  *((_DWORD *)ArgList + 330) = 0;
  QueryValueInternal((struct RegEntry *)pExceptionObject);
  Instance = _com_ptr_t<_com_IIID<IMSMQTriggerSet,&__s_GUID const _GUID_1d9f85bf_9666_11d2_8927_0008c70c0622>>::CreateInstance((LPVOID *)ArgList + 21);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_f3298f65ec353b4f3993aea62a87602f_Traceguids);
    bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, Instance);
    throw (bad_hresult *)pExceptionObject;
  }
  bstrString[0] = 0;
  v12 = _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->(ArgList + 16);
  (*(void (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v12 + 56LL))(v12, bstrString);
  v13 = (struct IUnknown *)_com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->(ArgList + 168);
  v14 = (OLECHAR *)_bstr_t::_bstr_t((_bstr_t *)&v23, bstrString[0]);
  v15 = (_bstr_t *)v14;
  bstrString[1] = v14;
  if ( *(_QWORD *)v14 )
    v16 = **(_QWORD **)v14;
  else
    v16 = 0;
  v17 = ((__int64 (__fastcall *)(struct IUnknown *, __int64))v13->lpVtbl[6].AddRef)(v13, v16);
  if ( v17 < 0 )
    _com_issue_errorex(v17, v13, &GUID_1d9f85bf_9666_11d2_8927_0008c70c0622);
  _bstr_t::_Free(v15);
  SysFreeString(bstrString[0]);
  R<IObjectContext>::~R<IObjectContext>(a2);
  return ArgList;
}

```

## disassembly

```asm
0x14000a6dc  mov     [rsp-38h+arg_10], rbx
0x14000a6e1  mov     [rsp-38h+arg_8], rdx
0x14000a6e6  mov     [rsp-38h+arg_0], rcx
0x14000a6eb  push    rbp
0x14000a6ec  push    rsi
0x14000a6ed  push    rdi
0x14000a6ee  push    r12
0x14000a6f0  push    r13
0x14000a6f2  push    r14
0x14000a6f4  push    r15
0x14000a6f6  mov     rbp, rsp
0x14000a6f9  sub     rsp, 70h
0x14000a6fd  mov     r14, r8
0x14000a700  mov     r12, rdx
0x14000a703  mov     rbx, rcx
0x14000a706  mov     rax, [rdx]
0x14000a709  mov     [rbp+arg_18], rax
0x14000a70d  lea     rcx, [rbp+arg_18]
0x14000a711  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIMSMQTriggersConfig@@$1?_GUID_7c55d6a1_f584_11d2_89b2_000000000000@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IMSMQTriggersConfig,&__s_GUID const _GUID_7c55d6a1_f584_11d2_89b2_000000000000>>::_AddRef(void)
0x14000a716  lea     rax, [rbp+arg_18]
0x14000a71a  mov     [rsp+70h+var_50], rax; __int64
0x14000a71f  lea     r9, aCtriggermonito; "CTriggerMonitorPool"
0x14000a726  mov     rcx, rbx; ArgList
0x14000a729  call    ??0CThread@@QEAA@KKPEB_WV?$_com_ptr_t@V?$_com_IIID@UIMSMQTriggersConfig@@$1?_GUID_7c55d6a1_f584_11d2_89b2_000000000000@@3U__s_GUID@@B@@@@@Z; CThread::CThread(ulong,ulong,wchar_t const *,_com_ptr_t<_com_IIID<IMSMQTriggersConfig,&__s_GUID const _GUID_7c55d6a1_f584_11d2_89b2_000000000000>>)
0x14000a72e  nop
0x14000a72f  lea     rax, ??_7CTriggerMonitorPool@@6B@; const CTriggerMonitorPool::`vftable'
0x14000a736  mov     [rbx], rax
0x14000a739  lea     rcx, [rbx+60h]; this
0x14000a73d  call    ??0CCriticalSection@@QEAA@XZ; CCriticalSection::CCriticalSection(void)
0x14000a742  nop
0x14000a743  xor     r9d, r9d; lpName
0x14000a746  xor     r8d, r8d; bInitialState
0x14000a749  xor     edx, edx; bManualReset
0x14000a74b  xor     ecx, ecx; lpEventAttributes
0x14000a74d  call    cs:__imp_CreateEventW
0x14000a753  mov     [rbx+98h], rax
0x14000a75a  lea     r15, [rbx+0A8h]
0x14000a761  xor     r13d, r13d
0x14000a764  mov     [r15], r13
0x14000a767  call    ?_Buynode@?$list@PEAVCRuntimeRuleInfo@@V?$allocator@PEAVCRuntimeRuleInfo@@@std@@@std@@IEAAPEAU_Node@?$_List_nod@PEAVCRuntimeRuleInfo@@V?$allocator@PEAVCRuntimeRuleInfo@@@std@@@2@XZ; std::list<CRuntimeRuleInfo *>::_Buynode(void)
0x14000a76c  mov     [rbx+0B8h], rax
0x14000a773  mov     [rbx+0C0h], r13
0x14000a77a  lea     rcx, [rbx+0C8h]
0x14000a781  call    ??0?$list@PEAVCAdminMessage@@V?$allocator@PEAVCAdminMessage@@@std@@@std@@QEAA@XZ; std::list<CAdminMessage *>::list<CAdminMessage *>(void)
0x14000a786  nop
0x14000a787  lea     rcx, [rbx+0E0h]; this
0x14000a78e  call    ??0CCriticalSection@@QEAA@XZ; CCriticalSection::CCriticalSection(void)
0x14000a793  nop
0x14000a794  mov     [rbx+108h], r13
0x14000a79b  lea     rcx, [rbx+110h]; struct _bstr_t *
0x14000a7a2  mov     [rcx], r13
0x14000a7a5  lea     rdi, [rbx+118h]
0x14000a7ac  mov     [rdi], r13
0x14000a7af  mov     [rbx+120h], r13
0x14000a7b6  mov     [rbx+52Ch], r13
0x14000a7bd  cmp     [rbx+98h], r13
0x14000a7c4  jnz     short loc_14000A837
0x14000a7c6  lea     rax, WPP_GLOBAL_Control
0x14000a7cd  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a7d4  cmp     rcx, rax
0x14000a7d7  jz      short loc_14000A804
0x14000a7d9  test    byte ptr [rcx+1Ch], 1
0x14000a7dd  jz      short loc_14000A804
0x14000a7df  call    cs:__imp_GetLastError
0x14000a7e5  lea     edx, [r13+0Ah]
0x14000a7e9  mov     r9d, eax
0x14000a7ec  lea     r8, WPP_f3298f65ec353b4f3993aea62a87602f_Traceguids
0x14000a7f3  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a7fa  mov     rcx, [rcx+10h]
0x14000a7fe  call    WPP_SF_d
0x14000a803  nop
0x14000a804  mov     r8d, 1
0x14000a80a  lea     rdx, ?_bad_alloc_Message@std@@3PEBDEB; char const * const std::_bad_alloc_Message
0x14000a811  lea     rcx, [rbp+pExceptionObject]
0x14000a815  call    cs:__imp_??0exception@@QEAA@AEBQEBDH@Z; exception::exception(char const * const &,int)
0x14000a81b  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x14000a822  mov     [rbp+pExceptionObject], rax
0x14000a826  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x14000a82d  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14000a831  call    _CxxThrowException_0
0x14000a837  mov     [rbx+58h], r13b
0x14000a83b  mov     [rbx+0A0h], r13d
0x14000a842  call    ?GetTimeAsBSTR@@YAXAEAV_bstr_t@@@Z; GetTimeAsBSTR(_bstr_t &)
0x14000a847  mov     rcx, rdi; struct _bstr_t *
0x14000a84a  call    ?GetTimeAsBSTR@@YAXAEAV_bstr_t@@@Z; GetTimeAsBSTR(_bstr_t &)
0x14000a84f  lea     rdi, [rbx+128h]
0x14000a856  lea     r8, aSoftwareMicros; "Software\\Microsoft\\MSMQ\\Triggers"
0x14000a85d  mov     edx, 200h; unsigned __int64
0x14000a862  mov     rcx, rdi; wchar_t *
0x14000a865  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x14000a86a  mov     esi, eax
0x14000a86c  test    eax, eax
0x14000a86e  jns     short loc_14000A8BA
0x14000a870  lea     rax, WPP_GLOBAL_Control
0x14000a877  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a87e  cmp     rcx, rax
0x14000a881  jz      short loc_14000A89E
0x14000a883  test    byte ptr [rcx+1Ch], 1
0x14000a887  jz      short loc_14000A89E
0x14000a889  mov     edx, 0Bh
0x14000a88e  lea     r8, WPP_f3298f65ec353b4f3993aea62a87602f_Traceguids
0x14000a895  mov     rcx, [rcx+10h]
0x14000a899  call    WPP_SF_
0x14000a89e  mov     edx, esi; int
0x14000a8a0  lea     rcx, [rbp+pExceptionObject]; this
0x14000a8a4  call    ??0bad_string_result@@QEAA@J@Z; bad_string_result::bad_string_result(long)
0x14000a8a9  lea     rdx, _TI4?AVbad_string_result@@; pThrowInfo
0x14000a8b0  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14000a8b4  call    _CxxThrowException_0
0x14000a8ba  lea     rdx, aMsmqtriggers; "MSMQTriggers"
0x14000a8c1  mov     rcx, r14; String1
0x14000a8c4  call    cs:__imp__wcsicmp
0x14000a8ca  test    eax, eax
0x14000a8cc  jz      loc_14000A996
0x14000a8d2  lea     r8, aClustered; "\\Clustered\\"
0x14000a8d9  mov     edx, 200h; unsigned __int64
0x14000a8de  mov     rcx, rdi; wchar_t *
0x14000a8e1  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x14000a8e6  mov     esi, eax
0x14000a8e8  test    eax, eax
0x14000a8ea  jns     short loc_14000A936
0x14000a8ec  lea     rax, WPP_GLOBAL_Control
0x14000a8f3  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a8fa  cmp     rcx, rax
0x14000a8fd  jz      short loc_14000A91A
0x14000a8ff  test    byte ptr [rcx+1Ch], 1
0x14000a903  jz      short loc_14000A91A
0x14000a905  mov     edx, 0Ch
0x14000a90a  lea     r8, WPP_f3298f65ec353b4f3993aea62a87602f_Traceguids
0x14000a911  mov     rcx, [rcx+10h]
0x14000a915  call    WPP_SF_
0x14000a91a  mov     edx, esi; int
0x14000a91c  lea     rcx, [rbp+pExceptionObject]; this
0x14000a920  call    ??0bad_string_result@@QEAA@J@Z; bad_string_result::bad_string_result(long)
0x14000a925  lea     rdx, _TI4?AVbad_string_result@@; pThrowInfo
0x14000a92c  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14000a930  call    _CxxThrowException_0
0x14000a936  mov     r8, r14; wchar_t *
0x14000a939  mov     edx, 200h; unsigned __int64
0x14000a93e  mov     rcx, rdi; wchar_t *
0x14000a941  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x14000a946  mov     edi, eax
0x14000a948  test    eax, eax
0x14000a94a  jns     short loc_14000A996
0x14000a94c  lea     rax, WPP_GLOBAL_Control
0x14000a953  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a95a  cmp     rcx, rax
0x14000a95d  jz      short loc_14000A97A
0x14000a95f  test    byte ptr [rcx+1Ch], 1
0x14000a963  jz      short loc_14000A97A
0x14000a965  mov     edx, 0Dh
0x14000a96a  lea     r8, WPP_f3298f65ec353b4f3993aea62a87602f_Traceguids
0x14000a971  mov     rcx, [rcx+10h]
0x14000a975  call    WPP_SF_
0x14000a97a  mov     edx, edi; int
0x14000a97c  lea     rcx, [rbp+pExceptionObject]; this
0x14000a980  call    ??0bad_string_result@@QEAA@J@Z; bad_string_result::bad_string_result(long)
0x14000a985  lea     rdx, _TI4?AVbad_string_result@@; pThrowInfo
0x14000a98c  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14000a990  call    _CxxThrowException_0
0x14000a996  mov     dword ptr [rbp+pExceptionObject], r13d
0x14000a99a  lea     rax, aSoftwareMicros; "Software\\Microsoft\\MSMQ\\Triggers"
0x14000a9a1  mov     [rbp+var_28], rax
0x14000a9a5  lea     rax, aRemotequeueref; "RemoteQueueRefreshFrequency"
0x14000a9ac  mov     [rbp+var_20], rax
0x14000a9b0  mov     [rbp+var_18], r13d
0x14000a9b4  mov     [rbp+var_10], 0FFFFFFFF80000002h
0x14000a9bc  lea     r8, [rbx+528h]
0x14000a9c3  mov     [r8], r13d
0x14000a9c6  mov     edx, 4
0x14000a9cb  mov     r9d, edx
0x14000a9ce  lea     rcx, [rbp+pExceptionObject]; struct RegEntry *
0x14000a9d2  call    QueryValueInternal
0x14000a9d7  mov     r9d, 17h
0x14000a9dd  mov     rcx, r15; ppv
0x14000a9e0  call    ?CreateInstance@?$_com_ptr_t@V?$_com_IIID@UIMSMQTriggerSet@@$1?_GUID_1d9f85bf_9666_11d2_8927_0008c70c0622@@3U__s_GUID@@B@@@@QEAAJAEBU_GUID@@PEAUIUnknown@@K@Z; _com_ptr_t<_com_IIID<IMSMQTriggerSet,&__s_GUID const _GUID_1d9f85bf_9666_11d2_8927_0008c70c0622>>::CreateInstance(_GUID const &,IUnknown *,ulong)
0x14000a9e5  mov     edi, eax
0x14000a9e7  test    eax, eax
0x14000a9e9  jns     short loc_14000AA38
0x14000a9eb  lea     rax, WPP_GLOBAL_Control
0x14000a9f2  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a9f9  cmp     rcx, rax
0x14000a9fc  jz      short loc_14000AA1C
0x14000a9fe  test    byte ptr [rcx+1Ch], 1
0x14000aa02  jz      short loc_14000AA1C
0x14000aa04  mov     edx, 0Eh
0x14000aa09  mov     r9d, edi
0x14000aa0c  lea     r8, WPP_f3298f65ec353b4f3993aea62a87602f_Traceguids
0x14000aa13  mov     rcx, [rcx+10h]
0x14000aa17  call    WPP_SF_d
0x14000aa1c  mov     edx, edi; unsigned int
0x14000aa1e  lea     rcx, [rbp+pExceptionObject]; this
0x14000aa22  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x14000aa27  lea     rdx, _TI3?AVbad_hresult@@; pThrowInfo
0x14000aa2e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14000aa32  call    _CxxThrowException_0
0x14000aa38  mov     [rbp+bstrString], r13
0x14000aa3c  lea     rcx, [rbx+10h]
0x14000aa40  call    ??C?$_com_ptr_t@V?$_com_IIID@UIMSMQRuleHandler@@$1?_GUID_b0cdbf11_9774_11d2_8929_000000000000@@3U__s_GUID@@B@@@@QEBAPEAUIMSMQRuleHandler@@XZ; _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->(void)
0x14000aa45  mov     rcx, rax
0x14000aa48  mov     rdx, [rax]
0x14000aa4b  mov     rax, [rdx+38h]
0x14000aa4f  lea     rdx, [rbp+bstrString]
0x14000aa53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aa58  mov     rcx, r15
0x14000aa5b  call    ??C?$_com_ptr_t@V?$_com_IIID@UIMSMQRuleHandler@@$1?_GUID_b0cdbf11_9774_11d2_8929_000000000000@@3U__s_GUID@@B@@@@QEBAPEAUIMSMQRuleHandler@@XZ; _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->(void)
0x14000aa60  mov     rdi, rax
0x14000aa63  mov     rdx, [rbp+bstrString]; wchar_t *
0x14000aa67  lea     rcx, [rbp+arg_18]; this
0x14000aa6b  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x14000aa70  mov     rsi, rax
0x14000aa73  mov     [rbp+var_38], rax
0x14000aa77  mov     rcx, [rdi]
0x14000aa7a  mov     rax, [rcx+98h]
0x14000aa81  mov     rdx, [rsi]
0x14000aa84  test    rdx, rdx
0x14000aa87  jz      short loc_14000AA8E
0x14000aa89  mov     rdx, [rdx]
0x14000aa8c  jmp     short loc_14000AA91
0x14000aa8e  mov     rdx, r13
0x14000aa91  mov     rcx, rdi
0x14000aa94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aa99  test    eax, eax
0x14000aa9b  jns     short loc_14000AAAF
0x14000aa9d  lea     r8, _GUID_1d9f85bf_9666_11d2_8927_0008c70c0622; struct _GUID *
0x14000aaa4  mov     rdx, rdi; struct IUnknown *
0x14000aaa7  mov     ecx, eax; int
0x14000aaa9  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x14000aaaf  mov     rcx, rsi; this
0x14000aab2  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x14000aab7  mov     rcx, [rbp+bstrString]; bstrString
0x14000aabb  call    cs:__imp_SysFreeString
0x14000aac1  nop
0x14000aac2  mov     rcx, r12
0x14000aac5  call    ??1?$R@UIObjectContext@@@@QEAA@XZ; R<IObjectContext>::~R<IObjectContext>(void)
0x14000aaca  mov     rax, rbx
0x14000aacd  mov     rbx, [rsp+70h+arg_10]
0x14000aad5  add     rsp, 70h
0x14000aad9  pop     r15
0x14000aadb  pop     r14
0x14000aadd  pop     r13
0x14000aadf  pop     r12
0x14000aae1  pop     rdi
0x14000aae2  pop     rsi
0x14000aae3  pop     rbp
0x14000aae4  retn
```
