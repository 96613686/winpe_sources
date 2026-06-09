# LPA::EnterpriseManager::SetWipeEsimResultToRegistry(ushort const (*)[33],long)

- ea: `0x18007ff80`
- end: `0x18008020e`
- name: `?SetWipeEsimResultToRegistry@EnterpriseManager@LPA@@AEAAJPEAY0CB@$$CBGJ@Z`
- size: `654`
- prototype: `__int64 __fastcall(LPA::EnterpriseManager *__hidden this, const unsigned __int16 (*)[33], struct _SECURITY_ATTRIBUTES *)`
- caller_count: `2`
- callee_count: `18`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18007fee0`
- `0x180080a10`

## callees

- `0x180002290`
- `0x18000df90`
- `0x18000ebf4`
- `0x180063668`
- `0x1800653e8`
- `0x180071344`
- `0x180071650`
- `0x1800741d0`
- `0x180075554`
- `0x1800759d4`
- `0x1800769bc`
- `0x1800775b4`
- `0x180077854`
- `0x18007ed6c`
- `0x18007ff80`
- `0x180080a28`
- `0x180081010`
- `0x180101010`

## string_xrefs

- `0x18008013a`: `LpaServiceEnterpriseManager`
- `0x18008019e`: `LpaServiceEnterpriseManager`
- `0x18008012e`: `LPA::EnterpriseManager::SetWipeEsimResultToRegistry`
- `0x180080192`: `LPA::EnterpriseManager::SetWipeEsimResultToRegistry`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall LPA::EnterpriseManager::SetWipeEsimResultToRegistry(
        LPA::EnterpriseManager *this,
        unsigned __int16 (*a2)[33],
        struct _SECURITY_ATTRIBUTES *a3)
{
  unsigned int v3; // edi
  const WCHAR *v6; // rax
  const unsigned __int16 *v7; // r8
  int v8; // ebx
  __int64 v9; // rcx
  _DWORD *v10; // rax
  __int64 v11; // rax
  unsigned __int16 (*v12)[33]; // r8
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  __int64 v17; // [rsp+50h] [rbp-B0h] BYREF
  int v18; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v19; // [rsp+60h] [rbp-A0h] BYREF
  struct LPA_ENTERPRISE_ESIM_DETAILS *v20; // [rsp+68h] [rbp-98h]
  unsigned __int16 *v21; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v22[4]; // [rsp+78h] [rbp-88h] BYREF
  _OWORD v23[2]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v24[40]; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 v25[33]; // [rsp+E0h] [rbp-20h] BYREF

  v3 = (unsigned int)a3;
  v23[0] = 0;
  v23[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v23[0]) = 0;
  LPA::EnterpriseManager::AssembleEuiccRegKey(this, (unsigned __int16 *)a2, 0, v23);
  v6 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v23);
  v8 = CommonUtil::SetDwordToRegistry(v6, L"ActionResult", v7, (struct _SECURITY_ATTRIBUTES *)v3, 0);
  if ( v8 >= 0 )
  {
    std::wstring::wstring(v22, (unsigned __int16 *)a2);
    std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<LPA::EnterpriseManager::StagedEsimDetails>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<LPA::EnterpriseManager::StagedEsimDetails>>>,0>>::find(
      (char *)this + 88,
      &v17,
      v22);
    std::wstring::_Tidy_deallocate(v22);
    v9 = v17;
    if ( *((_QWORD *)this + 11) == v17 )
    {
      std::make_unique<LPA::EnterpriseManager::EsimDetails,,0>(&v17);
      v10 = (_DWORD *)v17;
      *(_DWORD *)(v17 + 8) = v3;
      *v10 |= 2u;
      std::wstring::wstring(v24, (unsigned __int16 *)a2);
      v11 = std::map<std::wstring,std::unique_ptr<LPA::EnterpriseManager::EsimDetails>>::_Try_emplace<std::wstring,>(
              (char *)this + 88,
              v22,
              v24);
      std::unique_ptr<LPA::EnterpriseManager::EsimDetails>::operator=<std::default_delete<LPA::EnterpriseManager::EsimDetails>,0>(
        (__int64 *)(*(_QWORD *)v11 + 64LL),
        &v17);
      std::wstring::_Tidy_deallocate(v24);
      std::unique_ptr<LPA::EnterpriseManager::EsimDetails>::~unique_ptr<LPA::EnterpriseManager::EsimDetails>(&v17);
    }
    else
    {
      *(_DWORD *)(*(_QWORD *)(v17 + 64) + 8LL) = v3;
      **(_DWORD **)(v9 + 64) |= 2u;
    }
    v19 = (unsigned __int16 *)LPA::Util::CustomDeleter;
    v20 = 0;
    v8 = (*(__int64 (__fastcall **)(char *, unsigned __int16 *, unsigned __int16 **))(*((_QWORD *)this + 1) + 64LL))(
           (char *)this + 8,
           (unsigned __int16 *)a2,
           &v19);
    if ( v8 >= 0 )
      LPA::EnterpriseManager::BroadcastEsimUpdates(this, v20);
    std::unique_ptr<LPA_SERVICE_INFO,void (*)(void *)>::~unique_ptr<LPA_SERVICE_INFO,void (*)(void *)>(&v19);
  }
  v25[0] = 0;
  memset_0(&v25[1], 0, 0x40u);
  CommonUtil::WritePiiFilteredEsimIdToBuffer((CommonUtil *)a2, (const unsigned __int16 (*)[33])v25, v12);
  if ( v8 < 0 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(v17) = v3;
      v19 = v25;
      v18 = v8;
      v22[0] = "LPA::EnterpriseManager::SetWipeEsimResultToRegistry";
      v21 = (unsigned __int16 *)"LpaServiceEnterpriseManager";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v13,
        (unsigned int)&byte_18012B157,
        v14,
        v15,
        (__int64)&v21,
        (__int64)v22,
        (__int64)&v18,
        (__int64)&v19,
        (__int64)&v17);
    }
  }
  else if ( (unsigned int)CallbackContext > 4 )
  {
    v18 = v3;
    v21 = v25;
    LODWORD(v17) = v8;
    v22[0] = "LPA::EnterpriseManager::SetWipeEsimResultToRegistry";
    v19 = (unsigned __int16 *)"LpaServiceEnterpriseManager";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v13,
      (unsigned int)byte_18012B1AB,
      v14,
      v15,
      (__int64)&v19,
      (__int64)v22,
      (__int64)&v17,
      (__int64)&v21,
      (__int64)&v18);
  }
  std::wstring::_Tidy_deallocate(v23);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18007ff80  push    rbp
0x18007ff82  push    rbx
0x18007ff83  push    rsi
0x18007ff84  push    rdi
0x18007ff85  push    r14
0x18007ff87  lea     rbp, [rsp-40h]
0x18007ff8c  sub     rsp, 140h
0x18007ff93  mov     rax, cs:__security_cookie
0x18007ff9a  xor     rax, rsp
0x18007ff9d  mov     [rbp+60h+var_30], rax
0x18007ffa1  mov     edi, r8d
0x18007ffa4  mov     rsi, rdx
0x18007ffa7  mov     r14, rcx
0x18007ffaa  xorps   xmm0, xmm0
0x18007ffad  movups  [rbp+60h+var_C8], xmm0
0x18007ffb1  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18007ffb9  movdqu  [rbp+60h+var_B8], xmm1
0x18007ffbe  xor     eax, eax
0x18007ffc0  mov     word ptr [rbp+60h+var_C8], ax
0x18007ffc4  lea     r9, [rbp+60h+var_C8]
0x18007ffc8  xor     r8d, r8d
0x18007ffcb  call    ?AssembleEuiccRegKey@EnterpriseManager@LPA@@AEAAXAEAY0CB@$$CBG_NAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; LPA::EnterpriseManager::AssembleEuiccRegKey(ushort const (&)[33],bool,std::wstring &)
0x18007ffd0  lea     rcx, [rbp+60h+var_C8]
0x18007ffd4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007ffd9  mov     rcx, rax; lpSubKey
0x18007ffdc  mov     [rsp+160h+var_140], 0; unsigned int
0x18007ffe4  mov     r9d, edi; struct _SECURITY_ATTRIBUTES *
0x18007ffe7  lea     rdx, aActionresult; "ActionResult"
0x18007ffee  call    ?SetDwordToRegistry@CommonUtil@@YAJPEBG0PEAU_SECURITY_ATTRIBUTES@@KK@Z; CommonUtil::SetDwordToRegistry(ushort const *,ushort const *,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x18007fff3  mov     ebx, eax
0x18007fff5  test    eax, eax
0x18007fff7  js      loc_1800800E9
0x18007fffd  mov     rdx, rsi
0x180080000  lea     rcx, [rsp+160h+var_E8]
0x180080005  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008000a  lea     rbx, [r14+58h]
0x18008000e  lea     r8, [rsp+160h+var_E8]
0x180080013  lea     rdx, [rsp+160h+var_110]
0x180080018  mov     rcx, rbx
0x18008001b  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UStagedEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UStagedEsimDetails@EnterpriseManager@LPA@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UStagedEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UStagedEsimDetails@EnterpriseManager@LPA@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UStagedEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UStagedEsimDetails@EnterpriseManager@LPA@@@std@@@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<LPA::EnterpriseManager::StagedEsimDetails>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<LPA::EnterpriseManager::StagedEsimDetails>>>,0>>::find(std::wstring const &)
0x180080020  lea     rcx, [rsp+160h+var_E8]
0x180080025  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008002a  mov     rcx, [rsp+160h+var_110]
0x18008002f  cmp     [rbx], rcx
0x180080032  jnz     short loc_180080090
0x180080034  lea     rcx, [rsp+160h+var_110]
0x180080039  call    ??$make_unique@UEsimDetails@EnterpriseManager@LPA@@$$V$0A@@std@@YA?AV?$unique_ptr@UEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UEsimDetails@EnterpriseManager@LPA@@@std@@@0@XZ; std::make_unique<LPA::EnterpriseManager::EsimDetails,,0>(void)
0x18008003e  nop
0x18008003f  mov     rax, [rsp+160h+var_110]
0x180080044  mov     [rax+8], edi
0x180080047  or      dword ptr [rax], 2
0x18008004a  mov     rdx, rsi
0x18008004d  lea     rcx, [rbp+60h+var_A8]
0x180080051  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180080056  nop
0x180080057  lea     r8, [rbp+60h+var_A8]
0x18008005b  lea     rdx, [rsp+160h+var_E8]
0x180080060  mov     rcx, rbx
0x180080063  call    ??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UEsimDetails@EnterpriseManager@LPA@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UEsimDetails@EnterpriseManager@LPA@@@std@@@2@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UEsimDetails@EnterpriseManager@LPA@@@std@@@2@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::unique_ptr<LPA::EnterpriseManager::EsimDetails>>::_Try_emplace<std::wstring,>(std::wstring &&)
0x180080068  mov     rcx, [rax]
0x18008006b  add     rcx, 40h ; '@'
0x18008006f  lea     rdx, [rsp+160h+var_110]
0x180080074  call    ??$?4U?$default_delete@UEsimDetails@EnterpriseManager@LPA@@@std@@$0A@@?$unique_ptr@UEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UEsimDetails@EnterpriseManager@LPA@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<LPA::EnterpriseManager::EsimDetails>::operator=<std::default_delete<LPA::EnterpriseManager::EsimDetails>,0>(std::unique_ptr<LPA::EnterpriseManager::EsimDetails> &&)
0x180080079  nop
0x18008007a  lea     rcx, [rbp+60h+var_A8]
0x18008007e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180080083  nop
0x180080084  lea     rcx, [rsp+160h+var_110]
0x180080089  call    ??1?$unique_ptr@UEsimDetails@EnterpriseManager@LPA@@U?$default_delete@UEsimDetails@EnterpriseManager@LPA@@@std@@@std@@QEAA@XZ; std::unique_ptr<LPA::EnterpriseManager::EsimDetails>::~unique_ptr<LPA::EnterpriseManager::EsimDetails>(void)
0x18008008e  jmp     short loc_18008009E
0x180080090  mov     rax, [rcx+40h]
0x180080094  mov     [rax+8], edi
0x180080097  mov     rax, [rcx+40h]
0x18008009b  or      dword ptr [rax], 2
0x18008009e  lea     rax, ?CustomDeleter@Util@LPA@@YAXPEAX@Z; LPA::Util::CustomDeleter(void *)
0x1800800a5  mov     [rsp+160h+var_100], rax
0x1800800aa  mov     [rsp+160h+var_F8], 0
0x1800800b3  lea     rcx, [r14+8]
0x1800800b7  mov     rax, [rcx]
0x1800800ba  lea     r8, [rsp+160h+var_100]
0x1800800bf  mov     rdx, rsi
0x1800800c2  mov     rax, [rax+40h]
0x1800800c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800800cb  mov     ebx, eax
0x1800800cd  test    eax, eax
0x1800800cf  js      short loc_1800800DF
0x1800800d1  mov     rdx, [rsp+160h+var_F8]; struct LPA_ENTERPRISE_ESIM_DETAILS *
0x1800800d6  mov     rcx, r14; this
0x1800800d9  call    ?BroadcastEsimUpdates@EnterpriseManager@LPA@@AEAAXPEBULPA_ENTERPRISE_ESIM_DETAILS@@@Z; LPA::EnterpriseManager::BroadcastEsimUpdates(LPA_ENTERPRISE_ESIM_DETAILS const *)
0x1800800de  nop
0x1800800df  lea     rcx, [rsp+160h+var_100]
0x1800800e4  call    ??1?$unique_ptr@ULPA_SERVICE_INFO@@P6AXPEAX@Z@std@@QEAA@XZ; std::unique_ptr<LPA_SERVICE_INFO,void (*)(void *)>::~unique_ptr<LPA_SERVICE_INFO,void (*)(void *)>(void)
0x1800800e9  xor     eax, eax
0x1800800eb  mov     [rbp+60h+var_80], ax
0x1800800ef  xor     edx, edx; Val
0x1800800f1  lea     r8d, [rax+40h]; Size
0x1800800f5  lea     rcx, [rbp+60h+var_80+2]; void *
0x1800800f9  call    memset_0
0x1800800fe  lea     rdx, [rbp+60h+var_80]; unsigned __int16 (*)[33]
0x180080102  mov     rcx, rsi; this
0x180080105  call    ?WritePiiFilteredEsimIdToBuffer@CommonUtil@@YAXPEAY0CB@$$CBGAEAY0CB@G@Z; CommonUtil::WritePiiFilteredEsimIdToBuffer(ushort const (*)[33],ushort (&)[33])
0x18008010a  mov     eax, cs:CallbackContext
0x180080110  test    ebx, ebx
0x180080112  js      short loc_18008017C
0x180080114  cmp     eax, 4
0x180080117  jbe     loc_1800801E9
0x18008011d  mov     [rsp+160h+var_108], edi
0x180080121  lea     rax, [rbp+60h+var_80]
0x180080125  mov     [rsp+160h+var_F0], rax
0x18008012a  mov     dword ptr [rsp+160h+var_110], ebx
0x18008012e  lea     rax, aLpaEnterprisem_14; "LPA::EnterpriseManager::SetWipeEsimResu"...
0x180080135  mov     [rsp+160h+var_E8], rax
0x18008013a  lea     rax, aLpaserviceente; "LpaServiceEnterpriseManager"
0x180080141  mov     [rsp+160h+var_100], rax
0x180080146  lea     rax, [rsp+160h+var_108]
0x18008014b  mov     [rsp+160h+var_120], rax
0x180080150  lea     rax, [rsp+160h+var_F0]
0x180080155  mov     [rsp+160h+var_128], rax
0x18008015a  lea     rax, [rsp+160h+var_110]
0x18008015f  mov     [rsp+160h+var_130], rax
0x180080164  lea     rax, [rsp+160h+var_E8]
0x180080169  mov     [rsp+160h+var_138], rax
0x18008016e  lea     rax, [rsp+160h+var_100]
0x180080173  lea     rdx, byte_18012B1AB
0x18008017a  jmp     short loc_1800801DE
0x18008017c  cmp     eax, 2
0x18008017f  jbe     short loc_1800801E9
0x180080181  mov     dword ptr [rsp+160h+var_110], edi
0x180080185  lea     rax, [rbp+60h+var_80]
0x180080189  mov     [rsp+160h+var_100], rax
0x18008018e  mov     [rsp+160h+var_108], ebx
0x180080192  lea     rax, aLpaEnterprisem_14; "LPA::EnterpriseManager::SetWipeEsimResu"...
0x180080199  mov     [rsp+160h+var_E8], rax
0x18008019e  lea     rax, aLpaserviceente; "LpaServiceEnterpriseManager"
0x1800801a5  mov     [rsp+160h+var_F0], rax
0x1800801aa  lea     rax, [rsp+160h+var_110]
0x1800801af  mov     [rsp+160h+var_120], rax
0x1800801b4  lea     rax, [rsp+160h+var_100]
0x1800801b9  mov     [rsp+160h+var_128], rax
0x1800801be  lea     rax, [rsp+160h+var_108]
0x1800801c3  mov     [rsp+160h+var_130], rax
0x1800801c8  lea     rax, [rsp+160h+var_E8]
0x1800801cd  mov     [rsp+160h+var_138], rax
0x1800801d2  lea     rax, [rsp+160h+var_F0]
0x1800801d7  lea     rdx, byte_18012B157
0x1800801de  mov     qword ptr [rsp+160h+var_140], rax
0x1800801e3  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800801e8  nop
0x1800801e9  lea     rcx, [rbp+60h+var_C8]
0x1800801ed  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800801f2  mov     eax, ebx
0x1800801f4  mov     rcx, [rbp+60h+var_30]
0x1800801f8  xor     rcx, rsp; StackCookie
0x1800801fb  call    __security_check_cookie
0x180080200  add     rsp, 140h
0x180080207  pop     r14
0x180080209  pop     rdi
0x18008020a  pop     rsi
0x18008020b  pop     rbx
0x18008020c  pop     rbp
0x18008020d  retn
```
