# CMSMQRuleHandler::InvokeCOMComponent(IMSMQPropertyBag *)

- ea: `0x1800084d0`
- end: `0x180008975`
- name: `?InvokeCOMComponent@CMSMQRuleHandler@@QEAAJPEAUIMSMQPropertyBag@@@Z`
- size: `1189`
- prototype: `__int64 __fastcall(wchar_t ***this, struct IMSMQPropertyBag *)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180006bec`

## callees

- `0x1800030d8`
- `0x180004d20`
- `0x180004fc4`
- `0x180005078`
- `0x18000544c`
- `0x1800084d0`
- `0x180009420`
- `0x180009778`
- `0x180009ab0`
- `0x180009d2c`
- `0x180009ee4`
- `0x180014d30`
- `0x180015888`
- `0x180022010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800086d9`
- `OLEAUT32!__imp_VariantInit` at `0x1800086d9`

## pseudocode

```c
__int64 __fastcall CMSMQRuleHandler::InvokeCOMComponent(wchar_t ***this, struct IMSMQPropertyBag *a2)
{
  wchar_t *v4; // rdx
  int v5; // eax
  char v6; // r10
  wchar_t **v7; // rax
  wchar_t *v8; // rcx
  unsigned int v9; // eax
  wchar_t *v11; // rdx
  CMSMQRuleHandler *v12; // rcx
  unsigned int v13; // eax
  int v14; // [rsp+60h] [rbp-98h] BYREF
  struct IDispatch *v15; // [rsp+68h] [rbp-90h] BYREF
  wchar_t **v16; // [rsp+70h] [rbp-88h] BYREF
  wchar_t **v17; // [rsp+78h] [rbp-80h] BYREF
  VARIANTARG pvarg; // [rsp+80h] [rbp-78h] BYREF
  struct tagDISPPARAMS v19; // [rsp+98h] [rbp-60h] BYREF
  struct IMSMQPropertyBag *v20; // [rsp+B0h] [rbp-48h]
  __int16 v21; // [rsp+110h] [rbp+18h] BYREF
  int v22; // [rsp+118h] [rbp+20h]

  v22 = 0;
  memset(&v19, 0, sizeof(v19));
  _bstr_t::_bstr_t((_bstr_t *)&v17, &psz);
  _bstr_t::_bstr_t((_bstr_t *)&v16, &psz);
  v15 = 0;
  v20 = a2;
  if ( a2 )
    (*(void (__fastcall **)(struct IMSMQPropertyBag *))(*(_QWORD *)a2 + 8LL))(a2);
  CStringTokens::GetToken((CStringTokens *)(this + 14), 1u, (struct _bstr_t *)&v17);
  CStringTokens::GetToken((CStringTokens *)(this + 14), 2u, (struct _bstr_t *)&v16);
  if ( v17 )
    v4 = *v17;
  else
    v4 = 0;
  v5 = CDispatchInterfaceProxy::CreateObjectFromProgID(&v15, v4);
  v6 = v5;
  if ( v5 >= 0 )
  {
    CMSMQRuleHandler::PrepareMethodParameters((CMSMQRuleHandler *)this, a2, &v19);
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    if ( v16 )
      v11 = *v16;
    else
      v11 = 0;
    if ( (int)CDispatchInterfaceProxy::InvokeMethod((CDispatchInterfaceProxy *)&v15, v11, &v19, &pvarg) >= 0 )
    {
      if ( pvarg.vt == 3 )
        *((_DWORD *)this + 42) = pvarg.lVal != 0;
      CMSMQRuleHandler::ReleaseMethodParameters(v12, &v19);
      if ( a2 )
        (*(void (__fastcall **)(struct IMSMQPropertyBag *))(*(_QWORD *)a2 + 16LL))(a2);
      ATL::CComPtr<ITypeInfo>::~CComPtr<ITypeInfo>(&v15);
      _bstr_t::_Free((_bstr_t *)&v16);
      _bstr_t::_Free((_bstr_t *)&v17);
      return 0;
    }
    else
    {
      CMSMQRuleHandler::ReleaseMethodParameters(v12, &v19);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_SSSSD(*((_QWORD *)WPP_GLOBAL_Control + 2));
      v21 = 190;
      v14 = -1072820725;
      if ( g_pMSMQErrorLoggingTrace )
      {
        v13 = mqwcslen(L"trigobjs/rulehdlr");
        CMSMQTrace::MSMQTraceEvent(
          g_pMSMQErrorLoggingTrace,
          1,
          1,
          2LL * (v13 + 1),
          L"trigobjs/rulehdlr",
          2,
          &v21,
          4,
          &v14,
          0,
          0);
      }
      if ( a2 )
        (*(void (__fastcall **)(struct IMSMQPropertyBag *))(*(_QWORD *)a2 + 16LL))(a2);
      ATL::CComPtr<ITypeInfo>::~CComPtr<ITypeInfo>(&v15);
      _bstr_t::_Free((_bstr_t *)&v16);
      _bstr_t::_Free((_bstr_t *)&v17);
      return 3222146571LL;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = this[18];
      if ( v7 )
        v8 = *v7;
      else
        v8 = 0;
      WPP_SF_SSD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, v6);
    }
    v21 = 180;
    v14 = -1072820726;
    if ( g_pMSMQErrorLoggingTrace )
    {
      v9 = mqwcslen(L"trigobjs/rulehdlr");
      CMSMQTrace::MSMQTraceEvent(
        g_pMSMQErrorLoggingTrace,
        1,
        1,
        2LL * (v9 + 1),
        L"trigobjs/rulehdlr",
        2,
        &v21,
        4,
        &v14,
        0,
        0);
    }
    if ( a2 )
      (*(void (__fastcall **)(struct IMSMQPropertyBag *))(*(_QWORD *)a2 + 16LL))(a2);
    ATL::CComPtr<ITypeInfo>::~CComPtr<ITypeInfo>(&v15);
    _bstr_t::_Free((_bstr_t *)&v16);
    _bstr_t::_Free((_bstr_t *)&v17);
    return 3222146570LL;
  }
}

```

## disassembly

```asm
0x1800084d0  mov     r11, rsp
0x1800084d3  mov     [r11+10h], rdx
0x1800084d7  mov     [r11+8], rcx
0x1800084db  push    rbx
0x1800084dc  push    rsi
0x1800084dd  push    rdi
0x1800084de  push    r12
0x1800084e0  push    r13
0x1800084e2  push    r14
0x1800084e4  push    r15
0x1800084e6  sub     rsp, 0C0h
0x1800084ed  mov     r14, rdx
0x1800084f0  mov     r15, rcx
0x1800084f3  xor     esi, esi
0x1800084f5  mov     [r11+20h], esi
0x1800084f9  xorps   xmm0, xmm0
0x1800084fc  xor     eax, eax
0x1800084fe  movups  xmmword ptr [r11-60h], xmm0
0x180008503  mov     [r11-50h], rax
0x180008507  lea     rdx, psz; wchar_t *
0x18000850e  lea     rcx, [r11-80h]; this
0x180008512  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x180008517  nop
0x180008518  lea     rdx, psz; wchar_t *
0x18000851f  lea     rcx, [rsp+0F8h+var_88]; this
0x180008524  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x180008529  nop
0x18000852a  mov     [rsp+0F8h+var_90], rsi
0x18000852f  mov     [rsp+0F8h+var_48], r14
0x180008537  test    r14, r14
0x18000853a  jz      short loc_18000854C
0x18000853c  mov     rax, [r14]
0x18000853f  mov     rcx, r14
0x180008542  mov     rax, [rax+8]
0x180008546  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000854b  nop
0x18000854c  lea     r8, [rsp+0F8h+var_80]; struct _bstr_t *
0x180008551  mov     r13d, 1
0x180008557  mov     edx, r13d; unsigned int
0x18000855a  lea     rcx, [r15+70h]; this
0x18000855e  call    ?GetToken@CStringTokens@@QEAAXKAEAV_bstr_t@@@Z; CStringTokens::GetToken(ulong,_bstr_t &)
0x180008563  lea     r8, [rsp+0F8h+var_88]; struct _bstr_t *
0x180008568  lea     r12d, [r13+1]
0x18000856c  mov     edx, r12d; unsigned int
0x18000856f  lea     rcx, [r15+70h]; this
0x180008573  call    ?GetToken@CStringTokens@@QEAAXKAEAV_bstr_t@@@Z; CStringTokens::GetToken(ulong,_bstr_t &)
0x180008578  mov     rbx, [rsp+0F8h+var_80]
0x18000857d  test    rbx, rbx
0x180008580  jz      short loc_180008587
0x180008582  mov     rdx, [rbx]
0x180008585  jmp     short loc_18000858A
0x180008587  mov     rdx, rsi; wchar_t *
0x18000858a  lea     rcx, [rsp+0F8h+var_90]; this
0x18000858f  call    ?CreateObjectFromProgID@CDispatchInterfaceProxy@@QEAAJPEA_W@Z; CDispatchInterfaceProxy::CreateObjectFromProgID(wchar_t *)
0x180008594  mov     r10d, eax
0x180008597  test    eax, eax
0x180008599  jns     loc_1800086A9
0x18000859f  lea     rcx, WPP_GLOBAL_Control
0x1800085a6  mov     r8, cs:WPP_GLOBAL_Control
0x1800085ad  cmp     r8, rcx
0x1800085b0  jz      short loc_1800085F1
0x1800085b2  test    [r8+1Ch], r13b
0x1800085b6  jz      short loc_1800085F1
0x1800085b8  mov     rax, [r15+90h]
0x1800085bf  test    rax, rax
0x1800085c2  jz      short loc_1800085C9
0x1800085c4  mov     rcx, [rax]
0x1800085c7  jmp     short loc_1800085CC
0x1800085c9  mov     rcx, rsi
0x1800085cc  test    rbx, rbx
0x1800085cf  jz      short loc_1800085D6
0x1800085d1  mov     r9, [rbx]
0x1800085d4  jmp     short loc_1800085D9
0x1800085d6  mov     r9, rsi
0x1800085d9  mov     edx, 16h
0x1800085de  mov     dword ptr [rsp+0F8h+var_D0], r10d; char
0x1800085e3  mov     [rsp+0F8h+var_D8], rcx; wchar_t *
0x1800085e8  mov     rcx, [r8+10h]; LoggerHandle
0x1800085ec  call    WPP_SF_SSD
0x1800085f1  mov     eax, 0B4h
0x1800085f6  mov     [rsp+0F8h+arg_10], ax
0x1800085fe  mov     edi, 0C00E0E0Ah
0x180008603  mov     [rsp+0F8h+var_98], edi
0x180008607  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, rsi; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18000860e  jz      short loc_18000866D
0x180008610  lea     rbx, aTrigobjsRulehd; "trigobjs/rulehdlr"
0x180008617  mov     rcx, rbx; wchar_t *
0x18000861a  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18000861f  lea     r9d, [rax+1]
0x180008623  add     r9, r9
0x180008626  mov     [rsp+0F8h+var_A8], rsi
0x18000862b  mov     [rsp+0F8h+var_B0], rsi
0x180008630  lea     rax, [rsp+0F8h+var_98]
0x180008635  mov     [rsp+0F8h+var_B8], rax
0x18000863a  mov     [rsp+0F8h+var_C0], 4
0x180008643  lea     rax, [rsp+0F8h+arg_10]
0x18000864b  mov     [rsp+0F8h+var_C8], rax
0x180008650  mov     qword ptr [rsp+0F8h+var_D0], r12
0x180008655  mov     [rsp+0F8h+var_D8], rbx
0x18000865a  mov     r8d, r13d
0x18000865d  mov     edx, r13d
0x180008660  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180008667  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x18000866c  nop
0x18000866d  test    r14, r14
0x180008670  jz      short loc_180008682
0x180008672  mov     rax, [r14]
0x180008675  mov     rcx, r14
0x180008678  mov     rax, [rax+10h]
0x18000867c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008681  nop
0x180008682  lea     rcx, [rsp+0F8h+var_90]
0x180008687  call    ??1?$CComPtr@UITypeInfo@@@ATL@@QEAA@XZ; ATL::CComPtr<ITypeInfo>::~CComPtr<ITypeInfo>(void)
0x18000868c  nop
0x18000868d  lea     rcx, [rsp+0F8h+var_88]; this
0x180008692  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180008697  nop
0x180008698  lea     rcx, [rsp+0F8h+var_80]; this
0x18000869d  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800086a2  mov     eax, edi
0x1800086a4  jmp     loc_180008962
0x1800086a9  lea     r8, [rsp+0F8h+var_60]; struct tagDISPPARAMS *
0x1800086b1  mov     rdx, r14; struct IMSMQPropertyBag *
0x1800086b4  mov     rcx, r15; this
0x1800086b7  call    ?PrepareMethodParameters@CMSMQRuleHandler@@QEAAXPEAUIMSMQPropertyBag@@PEAUtagDISPPARAMS@@@Z; CMSMQRuleHandler::PrepareMethodParameters(IMSMQPropertyBag *,tagDISPPARAMS *)
0x1800086bc  xorps   xmm0, xmm0
0x1800086bf  xor     eax, eax
0x1800086c1  movups  xmmword ptr [rsp+0F8h+pvarg], xmm0
0x1800086c9  mov     qword ptr [rsp+0F8h+pvarg+10h], rax
0x1800086d1  lea     rcx, [rsp+0F8h+pvarg]; pvarg
0x1800086d9  call    cs:__imp_VariantInit
0x1800086df  mov     rdi, [rsp+0F8h+var_88]
0x1800086e4  test    rdi, rdi
0x1800086e7  jz      short loc_1800086EE
0x1800086e9  mov     rdx, [rdi]
0x1800086ec  jmp     short loc_1800086F1
0x1800086ee  mov     rdx, rsi; wchar_t *
0x1800086f1  lea     r9, [rsp+0F8h+pvarg]; struct tagVARIANT *
0x1800086f9  lea     r8, [rsp+0F8h+var_60]; struct tagDISPPARAMS *
0x180008701  lea     rcx, [rsp+0F8h+var_90]; this
0x180008706  call    ?InvokeMethod@CDispatchInterfaceProxy@@QEAAJPEA_WPEAUtagDISPPARAMS@@PEAUtagVARIANT@@@Z; CDispatchInterfaceProxy::InvokeMethod(wchar_t *,tagDISPPARAMS *,tagVARIANT *)
0x18000870b  mov     r12d, eax
0x18000870e  test    eax, eax
0x180008710  jns     loc_180008857
0x180008716  lea     rdx, [rsp+0F8h+var_60]; struct tagDISPPARAMS *
0x18000871e  call    ?ReleaseMethodParameters@CMSMQRuleHandler@@QEAAXPEAUtagDISPPARAMS@@@Z; CMSMQRuleHandler::ReleaseMethodParameters(tagDISPPARAMS *)
0x180008723  lea     rcx, WPP_GLOBAL_Control
0x18000872a  mov     rdx, cs:WPP_GLOBAL_Control
0x180008731  cmp     rdx, rcx
0x180008734  jz      short loc_18000879B
0x180008736  test    [rdx+1Ch], r13b
0x18000873a  jz      short loc_18000879B
0x18000873c  mov     rax, [r15+0A0h]
0x180008743  test    rax, rax
0x180008746  jz      short loc_18000874D
0x180008748  mov     r8, [rax]
0x18000874b  jmp     short loc_180008750
0x18000874d  mov     r8, rsi
0x180008750  mov     rax, [r15+90h]
0x180008757  test    rax, rax
0x18000875a  jz      short loc_180008761
0x18000875c  mov     rcx, [rax]
0x18000875f  jmp     short loc_180008764
0x180008761  mov     rcx, rsi
0x180008764  test    rbx, rbx
0x180008767  jz      short loc_18000876E
0x180008769  mov     rax, [rbx]
0x18000876c  jmp     short loc_180008771
0x18000876e  mov     rax, rsi
0x180008771  test    rdi, rdi
0x180008774  jz      short loc_18000877B
0x180008776  mov     r9, [rdi]
0x180008779  jmp     short loc_18000877E
0x18000877b  mov     r9, rsi
0x18000877e  mov     dword ptr [rsp+0F8h+var_C0], r12d
0x180008783  mov     [rsp+0F8h+var_C8], r8
0x180008788  mov     qword ptr [rsp+0F8h+var_D0], rcx
0x18000878d  mov     [rsp+0F8h+var_D8], rax
0x180008792  mov     rcx, [rdx+10h]
0x180008796  call    WPP_SF_SSSSD
0x18000879b  mov     eax, 0BEh
0x1800087a0  mov     [rsp+0F8h+arg_10], ax
0x1800087a8  mov     edi, 0C00E0E0Bh
0x1800087ad  mov     [rsp+0F8h+var_98], edi
0x1800087b1  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, rsi; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x1800087b8  jz      short loc_18000881B
0x1800087ba  lea     rbx, aTrigobjsRulehd; "trigobjs/rulehdlr"
0x1800087c1  mov     rcx, rbx; wchar_t *
0x1800087c4  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x1800087c9  lea     r9d, [rax+1]
0x1800087cd  add     r9, r9
0x1800087d0  mov     [rsp+0F8h+var_A8], rsi
0x1800087d5  mov     [rsp+0F8h+var_B0], rsi
0x1800087da  lea     rax, [rsp+0F8h+var_98]
0x1800087df  mov     [rsp+0F8h+var_B8], rax
0x1800087e4  mov     [rsp+0F8h+var_C0], 4
0x1800087ed  lea     rax, [rsp+0F8h+arg_10]
0x1800087f5  mov     [rsp+0F8h+var_C8], rax
0x1800087fa  mov     qword ptr [rsp+0F8h+var_D0], 2
0x180008803  mov     [rsp+0F8h+var_D8], rbx
0x180008808  mov     r8d, r13d
0x18000880b  mov     edx, r13d
0x18000880e  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180008815  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x18000881a  nop
0x18000881b  test    r14, r14
0x18000881e  jz      short loc_180008830
0x180008820  mov     rax, [r14]
0x180008823  mov     rcx, r14
0x180008826  mov     rax, [rax+10h]
0x18000882a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000882f  nop
0x180008830  lea     rcx, [rsp+0F8h+var_90]
0x180008835  call    ??1?$CComPtr@UITypeInfo@@@ATL@@QEAA@XZ; ATL::CComPtr<ITypeInfo>::~CComPtr<ITypeInfo>(void)
0x18000883a  nop
0x18000883b  lea     rcx, [rsp+0F8h+var_88]; this
0x180008840  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180008845  nop
0x180008846  lea     rcx, [rsp+0F8h+var_80]; this
0x18000884b  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180008850  mov     eax, edi
0x180008852  jmp     loc_180008962
0x180008857  cmp     word ptr [rsp+0F8h+pvarg], 3
0x180008860  jnz     short loc_180008875
0x180008862  mov     eax, esi
0x180008864  cmp     dword ptr [rsp+0F8h+pvarg+8], esi
0x18000886b  setnz   al
0x18000886e  mov     [r15+0A8h], eax
0x180008875  lea     rdx, [rsp+0F8h+var_60]; struct tagDISPPARAMS *
0x18000887d  call    ?ReleaseMethodParameters@CMSMQRuleHandler@@QEAAXPEAUtagDISPPARAMS@@@Z; CMSMQRuleHandler::ReleaseMethodParameters(tagDISPPARAMS *)
0x180008882  nop
0x180008883  test    r14, r14
0x180008886  jz      short loc_180008898
0x180008888  mov     rax, [r14]
0x18000888b  mov     rcx, r14
0x18000888e  mov     rax, [rax+10h]
0x180008892  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008897  nop
0x180008898  lea     rcx, [rsp+0F8h+var_90]
0x18000889d  call    ??1?$CComPtr@UITypeInfo@@@ATL@@QEAA@XZ; ATL::CComPtr<ITypeInfo>::~CComPtr<ITypeInfo>(void)
0x1800088a2  nop
0x1800088a3  lea     rcx, [rsp+0F8h+var_88]; this
0x1800088a8  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800088ad  nop
0x1800088ae  lea     rcx, [rsp+0F8h+var_80]; this
0x1800088b3  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800088b8  xor     eax, eax
0x1800088ba  jmp     loc_180008962
0x1800088bf  mov     rcx, [rsp+0F8h+arg_8]
0x1800088c7  test    rcx, rcx
0x1800088ca  jz      short loc_1800088D9
0x1800088cc  mov     rax, [rcx]
0x1800088cf  mov     rax, [rax+10h]
0x1800088d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088d8  nop
0x1800088d9  mov     ebx, 0C00E0E0Bh
0x1800088de  jmp     short loc_1800088FF
0x1800088e0  mov     rcx, [rsp+0F8h+arg_8]
0x1800088e8  test    rcx, rcx
0x1800088eb  jz      short loc_1800088FA
0x1800088ed  mov     rax, [rcx]
0x1800088f0  mov     rax, [rax+10h]
0x1800088f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088f9  nop
0x1800088fa  mov     ebx, 0C00E0E06h
0x1800088ff  lea     rcx, [rsp+0F8h+var_90]
0x180008904  call    ??1?$CComPtr@UITypeInfo@@@ATL@@QEAA@XZ; ATL::CComPtr<ITypeInfo>::~CComPtr<ITypeInfo>(void)
0x180008909  nop
0x18000890a  lea     rcx, [rsp+0F8h+var_88]; this
0x18000890f  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180008914  nop
0x180008915  lea     rcx, [rsp+0F8h+var_80]; this
0x18000891a  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000891f  mov     eax, ebx
0x180008921  jmp     short loc_180008962
0x180008923  mov     rcx, [rsp+0F8h+arg_8]
0x18000892b  test    rcx, rcx
0x18000892e  jz      short loc_18000893D
0x180008930  mov     rax, [rcx]
0x180008933  mov     rax, [rax+10h]
0x180008937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000893c  nop
0x18000893d  lea     rcx, [rsp+0F8h+var_90]
0x180008942  call    ??1?$CComPtr@UITypeInfo@@@ATL@@QEAA@XZ; ATL::CComPtr<ITypeInfo>::~CComPtr<ITypeInfo>(void)
0x180008947  nop
0x180008948  lea     rcx, [rsp+0F8h+var_88]; this
0x18000894d  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180008952  nop
0x180008953  lea     rcx, [rsp+0F8h+var_80]; this
0x180008958  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000895d  mov     eax, 0C00E0E08h
0x180008962  add     rsp, 0C0h
0x180008969  pop     r15
0x18000896b  pop     r14
0x18000896d  pop     r13
0x18000896f  pop     r12
0x180008971  pop     rdi
0x180008972  pop     rsi
0x180008973  pop     rbx
0x180008974  retn
  ... truncated ...
```
