# CMSMQRuleHandler::PrepareEXECommandLine(IMSMQPropertyBag *,_bstr_t *,_bstr_t *)

- ea: `0x180008d68`
- end: `0x180009417`
- name: `?PrepareEXECommandLine@CMSMQRuleHandler@@QEAAJPEAUIMSMQPropertyBag@@PEAV_bstr_t@@1@Z`
- size: `1711`
- prototype: `__int64 __fastcall(CMSMQRuleHandler *__hidden this, struct IMSMQPropertyBag *, struct _bstr_t *, struct _bstr_t *)`
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000897c`

## callees

- `0x180004d20`
- `0x180004d88`
- `0x180004dfc`
- `0x1800053ac`
- `0x18000544c`
- `0x1800056c8`
- `0x180005704`
- `0x180005888`
- `0x180006ef0`
- `0x1800082b8`
- `0x180008d68`
- `0x180009ab0`
- `0x180009d2c`
- `0x180014d30`
- `0x180015888`
- `0x180016270`
- `0x18001e380`
- `0x180022010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180008fde`
- `msvcrt!_wcsicmp` at `0x180008ffb`
- `msvcrt!_wcsicmp` at `0x180008fde`
- `msvcrt!_wcsicmp` at `0x180008ffb`
- `OLEAUT32!__imp_VariantInit` at `0x180008f1a`
- `OLEAUT32!__imp_VariantInit` at `0x180008f53`
- `OLEAUT32!__imp_VariantInit` at `0x180008f1a`
- `OLEAUT32!__imp_VariantInit` at `0x180008f53`
- `OLEAUT32!__imp_VariantClear` at `0x180009087`
- `OLEAUT32!__imp_VariantClear` at `0x18000912c`
- `OLEAUT32!__imp_VariantClear` at `0x1800092a1`
- `OLEAUT32!__imp_VariantClear` at `0x180009087`
- `OLEAUT32!__imp_VariantClear` at `0x18000912c`
- `OLEAUT32!__imp_VariantClear` at `0x1800092a1`
- `OLEAUT32!__imp_VariantChangeType` at `0x180008f6b`
- `OLEAUT32!__imp_VariantChangeType` at `0x180008f6b`

## pseudocode

```c
__int64 __fastcall CMSMQRuleHandler::PrepareEXECommandLine(
        CMSMQRuleHandler *this,
        struct IMSMQPropertyBag *a2,
        struct _bstr_t *a3,
        struct _bstr_t *a4)
{
  unsigned int v7; // eax
  unsigned int i; // r15d
  wchar_t **v10; // rbx
  int ArgumentValue; // eax
  HRESULT v12; // eax
  const wchar_t *v13; // rcx
  unsigned int v14; // r8d
  const wchar_t *v15; // rcx
  struct _bstr_t *v16; // rax
  _bstr_t *v17; // rcx
  unsigned int v18; // eax
  char v19; // r8
  unsigned int v20; // eax
  unsigned int v21; // eax
  char v22; // r10
  wchar_t *v23; // r8
  unsigned int v24; // eax
  __int16 v25; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v26; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v27[8]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v28; // [rsp+78h] [rbp-88h] BYREF
  __int64 v29; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v30[8]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v31[8]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v32[8]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v33[8]; // [rsp+A0h] [rbp-60h] BYREF
  VARIANTARG pvarg; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v35[8]; // [rsp+C0h] [rbp-40h] BYREF
  struct _bstr_t *v36; // [rsp+C8h] [rbp-38h]
  VARIANTARG pvargDest; // [rsp+D0h] [rbp-30h] BYREF
  struct IMSMQPropertyBag *v38; // [rsp+E8h] [rbp-18h]
  wchar_t v39[256]; // [rsp+F0h] [rbp-10h] BYREF

  v36 = a4;
  v38 = a2;
  if ( a2 )
    (*(void (__fastcall **)(struct IMSMQPropertyBag *))(*(_QWORD *)a2 + 8LL))(a2);
  if ( *((_DWORD *)this + 34) )
  {
    v29 = 0;
    CStringTokens::GetToken((CMSMQRuleHandler *)((char *)this + 112), 1u, (struct _bstr_t *)&v29);
    CMSMQRuleHandler::GetExeName(this, v27);
    for ( i = 2; i < *((_DWORD *)this + 34); ++i )
    {
      v28 = 0;
      CStringTokens::GetToken((CMSMQRuleHandler *)((char *)this + 112), i, (struct _bstr_t *)&v28);
      memset(&pvarg, 0, sizeof(pvarg));
      VariantInit(&pvarg);
      v10 = (wchar_t **)v28;
      v26 = v28;
      if ( v28 )
        _InterlockedIncrement((volatile signed __int32 *)(v28 + 16));
      ArgumentValue = CMSMQRuleHandler::GetArgumentValue(this, a2, &v26, &pvarg);
      if ( ArgumentValue < 0 )
      {
        v25 = 320;
        LODWORD(v26) = ArgumentValue;
        if ( g_pMSMQErrorLoggingTrace )
        {
          v21 = mqwcslen(L"trigobjs/rulehdlr");
          CMSMQTrace::MSMQTraceEvent(
            g_pMSMQErrorLoggingTrace,
            1,
            1,
            2LL * (v21 + 1),
            L"trigobjs/rulehdlr",
            2,
            &v25,
            4,
            &v26,
            0,
            0);
        }
        v22 = VariantClear(&pvarg);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          if ( v10 )
            v23 = *v10;
          else
            v23 = 0;
          WPP_SF_SSD(*((_QWORD *)WPP_GLOBAL_Control + 2), v23, v22);
        }
        v25 = 330;
        LODWORD(v26) = -1072820724;
        if ( g_pMSMQErrorLoggingTrace )
        {
          v24 = mqwcslen(L"trigobjs/rulehdlr");
          CMSMQTrace::MSMQTraceEvent(
            g_pMSMQErrorLoggingTrace,
            1,
            1,
            2LL * (v24 + 1),
            L"trigobjs/rulehdlr",
            2,
            &v25,
            4,
            &v26,
            0,
            0);
        }
        _bstr_t::_Free((_bstr_t *)&v28);
        _bstr_t::_Free((_bstr_t *)v27);
        _bstr_t::_Free((_bstr_t *)&v29);
        if ( a2 )
LABEL_49:
          (*(void (__fastcall **)(struct IMSMQPropertyBag *))(*(_QWORD *)a2 + 16LL))(a2);
        return 3222146572LL;
      }
      VariantInit(&pvargDest);
      v12 = VariantChangeType(&pvargDest, &pvarg, 0, 8u);
      if ( v12 < 0 )
      {
        v25 = 340;
        LODWORD(v26) = v12;
        if ( g_pMSMQErrorLoggingTrace )
        {
          v18 = mqwcslen(L"trigobjs/rulehdlr");
          CMSMQTrace::MSMQTraceEvent(
            g_pMSMQErrorLoggingTrace,
            1,
            1,
            2LL * (v18 + 1),
            L"trigobjs/rulehdlr",
            2,
            &v25,
            4,
            &v26,
            0,
            0);
        }
        v19 = VariantClear(&pvarg);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), v19);
        v25 = 350;
        LODWORD(v26) = -1072820724;
        if ( g_pMSMQErrorLoggingTrace )
        {
          v20 = mqwcslen(L"trigobjs/rulehdlr");
          CMSMQTrace::MSMQTraceEvent(
            g_pMSMQErrorLoggingTrace,
            1,
            1,
            2LL * (v20 + 1),
            L"trigobjs/rulehdlr",
            2,
            &v25,
            4,
            &v26,
            0,
            0);
        }
        _variant_t::~_variant_t((_variant_t *)&pvargDest);
        _bstr_t::_Free((_bstr_t *)&v28);
        _bstr_t::_Free((_bstr_t *)v27);
        _bstr_t::_Free((_bstr_t *)&v29);
        if ( a2 )
          goto LABEL_49;
        return 3222146572LL;
      }
      _bstr_t::_bstr_t((_bstr_t *)v30, L" ");
      _bstr_t::operator+=((struct _bstr_t *)v27, (struct _bstr_t *)v30);
      _bstr_t::_Free((_bstr_t *)v30);
      _bstr_t::_bstr_t((_bstr_t *)v31, L"\"");
      _bstr_t::operator+=((struct _bstr_t *)v27, (struct _bstr_t *)v31);
      _bstr_t::_Free((_bstr_t *)v31);
      if ( v10 )
        v13 = *v10;
      else
        v13 = 0;
      if ( _wcsicmp(v13, L"$MSG_ID") && (!v10 ? (v15 = 0) : (v15 = *v10), _wcsicmp(v15, L"$MSG_CORRELATION_ID")) )
      {
        v16 = _bstr_t::_bstr_t((_bstr_t *)v35, (const struct _variant_t *)&pvargDest);
        _bstr_t::operator+=((struct _bstr_t *)v27, v16);
        v17 = (_bstr_t *)v35;
      }
      else
      {
        ObjectIDToString((const struct _OBJECTID *)pvargDest.llVal, v39, v14);
        _bstr_t::_bstr_t((_bstr_t *)v32, v39);
        _bstr_t::operator+=((struct _bstr_t *)v27, (struct _bstr_t *)v32);
        v17 = (_bstr_t *)v32;
      }
      _bstr_t::_Free(v17);
      _bstr_t::_bstr_t((_bstr_t *)v33, L"\"");
      _bstr_t::operator+=((struct _bstr_t *)v27, (struct _bstr_t *)v33);
      _bstr_t::_Free((_bstr_t *)v33);
      VariantClear(&pvarg);
      _variant_t::~_variant_t((_variant_t *)&pvargDest);
      _bstr_t::_Free((_bstr_t *)&v28);
    }
    _bstr_t::operator=(a3, &v29);
    _bstr_t::operator=(v36, v27);
    _bstr_t::_Free((_bstr_t *)v27);
    _bstr_t::_Free((_bstr_t *)&v29);
    if ( a2 )
      (*(void (__fastcall **)(struct IMSMQPropertyBag *))(*(_QWORD *)a2 + 16LL))(a2);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2));
    v25 = 300;
    LODWORD(v26) = -1072820728;
    if ( g_pMSMQErrorLoggingTrace )
    {
      v7 = mqwcslen(L"trigobjs/rulehdlr");
      CMSMQTrace::MSMQTraceEvent(
        g_pMSMQErrorLoggingTrace,
        1,
        1,
        2LL * (v7 + 1),
        L"trigobjs/rulehdlr",
        2,
        &v25,
        4,
        &v26,
        0,
        0);
    }
    if ( a2 )
      (*(void (__fastcall **)(struct IMSMQPropertyBag *))(*(_QWORD *)a2 + 16LL))(a2);
    return 3222146568LL;
  }
}

```

## disassembly

```asm
0x180008d68  mov     [rsp-8+arg_8], rbx
0x180008d6d  push    rbp
0x180008d6e  push    rsi
0x180008d6f  push    rdi
0x180008d70  push    r12
0x180008d72  push    r13
0x180008d74  push    r14
0x180008d76  push    r15
0x180008d78  lea     rbp, [rsp-200h]
0x180008d80  sub     rsp, 300h
0x180008d87  mov     rax, cs:__security_cookie
0x180008d8e  xor     rax, rsp
0x180008d91  mov     [rbp+230h+var_40], rax
0x180008d98  mov     [rbp+230h+var_268], r9
0x180008d9c  mov     r13, r8
0x180008d9f  mov     rdi, rdx
0x180008da2  mov     r14, rcx
0x180008da5  mov     [rbp+230h+var_248], rdx
0x180008da9  test    rdx, rdx
0x180008dac  jz      short loc_180008DBE
0x180008dae  mov     rax, [rdx]
0x180008db1  mov     rcx, rdx
0x180008db4  mov     rax, [rax+8]
0x180008db8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008dbd  nop
0x180008dbe  mov     ebx, 1
0x180008dc3  cmp     [r14+88h], ebx
0x180008dca  jnb     loc_180008EB4
0x180008dd0  lea     rax, WPP_GLOBAL_Control
0x180008dd7  mov     rcx, cs:WPP_GLOBAL_Control
0x180008dde  cmp     rcx, rax
0x180008de1  jz      short loc_180008E11
0x180008de3  test    [rcx+1Ch], bl
0x180008de6  jz      short loc_180008E11
0x180008de8  mov     rax, [r14+0A0h]
0x180008def  test    rax, rax
0x180008df2  jz      short loc_180008DF9
0x180008df4  mov     r9, [rax]
0x180008df7  jmp     short loc_180008DFC
0x180008df9  xor     r9d, r9d
0x180008dfc  mov     edx, 20h ; ' '
0x180008e01  lea     r8, WPP_07c04997ef9c358328a47f0c936100cf_Traceguids
0x180008e08  mov     rcx, [rcx+10h]; LoggerHandle
0x180008e0c  call    WPP_SF_S
0x180008e11  mov     eax, 12Ch
0x180008e16  mov     [rsp+330h+var_2D0], ax
0x180008e1b  mov     r14d, 0C00E0E08h
0x180008e21  mov     dword ptr [rsp+330h+var_2C8], r14d
0x180008e26  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, 0; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180008e2e  jz      short loc_180008E97
0x180008e30  lea     rsi, aTrigobjsRulehd; "trigobjs/rulehdlr"
0x180008e37  mov     rcx, rsi; wchar_t *
0x180008e3a  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x180008e3f  lea     r9d, [rbx+rax]
0x180008e43  add     r9, r9
0x180008e46  mov     [rsp+330h+var_2E0], 0
0x180008e4f  mov     [rsp+330h+var_2E8], 0
0x180008e58  lea     rax, [rsp+330h+var_2C8]
0x180008e5d  mov     [rsp+330h+var_2F0], rax
0x180008e62  mov     r15d, 4
0x180008e68  mov     [rsp+330h+var_2F8], r15
0x180008e6d  lea     rax, [rsp+330h+var_2D0]
0x180008e72  mov     [rsp+330h+var_300], rax
0x180008e77  lea     r12d, [r15-2]
0x180008e7b  mov     qword ptr [rsp+330h+var_308], r12
0x180008e80  mov     [rsp+330h+var_310], rsi
0x180008e85  mov     r8d, ebx
0x180008e88  mov     edx, ebx
0x180008e8a  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180008e91  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x180008e96  nop
0x180008e97  test    rdi, rdi
0x180008e9a  jz      short loc_180008EAC
0x180008e9c  mov     rcx, [rdi]
0x180008e9f  mov     rax, [rcx+10h]
0x180008ea3  mov     rcx, rdi
0x180008ea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008eab  nop
0x180008eac  mov     eax, r14d
0x180008eaf  jmp     loc_1800093ED
0x180008eb4  mov     [rbp+230h+var_2B0], 0
0x180008ebc  lea     r8, [rbp+230h+var_2B0]; struct _bstr_t *
0x180008ec0  mov     edx, ebx; unsigned int
0x180008ec2  lea     rcx, [r14+70h]; this
0x180008ec6  call    ?GetToken@CStringTokens@@QEAAXKAEAV_bstr_t@@@Z; CStringTokens::GetToken(ulong,_bstr_t &)
0x180008ecb  lea     rdx, [rsp+330h+var_2C0]
0x180008ed0  mov     rcx, r14
0x180008ed3  call    ?GetExeName@CMSMQRuleHandler@@AEAA?AV_bstr_t@@XZ; CMSMQRuleHandler::GetExeName(void)
0x180008ed8  nop
0x180008ed9  mov     r12d, 2
0x180008edf  mov     r15d, r12d
0x180008ee2  cmp     r15d, [r14+88h]
0x180008ee9  jnb     loc_1800093A6
0x180008eef  mov     [rsp+330h+var_2B8], 0
0x180008ef8  lea     r8, [rsp+330h+var_2B8]; struct _bstr_t *
0x180008efd  mov     edx, r15d; unsigned int
0x180008f00  lea     rcx, [r14+70h]; this
0x180008f04  call    ?GetToken@CStringTokens@@QEAAXKAEAV_bstr_t@@@Z; CStringTokens::GetToken(ulong,_bstr_t &)
0x180008f09  xorps   xmm0, xmm0
0x180008f0c  xor     eax, eax
0x180008f0e  movups  xmmword ptr [rbp+230h+pvarg], xmm0
0x180008f12  mov     qword ptr [rbp+230h+pvarg+10h], rax
0x180008f16  lea     rcx, [rbp+230h+pvarg]; pvarg
0x180008f1a  call    cs:__imp_VariantInit
0x180008f20  mov     rbx, [rsp+330h+var_2B8]
0x180008f25  mov     [rsp+330h+var_2C8], rbx
0x180008f2a  test    rbx, rbx
0x180008f2d  jz      short loc_180008F33
0x180008f2f  lock inc dword ptr [rbx+10h]
0x180008f33  lea     r9, [rbp+230h+pvarg]
0x180008f37  lea     r8, [rsp+330h+var_2C8]
0x180008f3c  mov     rdx, rdi
0x180008f3f  mov     rcx, r14
0x180008f42  call    ?GetArgumentValue@CMSMQRuleHandler@@QEAAJPEAUIMSMQPropertyBag@@V_bstr_t@@PEAUtagVARIANT@@@Z; CMSMQRuleHandler::GetArgumentValue(IMSMQPropertyBag *,_bstr_t,tagVARIANT *)
0x180008f47  test    eax, eax
0x180008f49  js      loc_180009225
0x180008f4f  lea     rcx, [rbp+230h+pvargDest]; pvarg
0x180008f53  call    cs:__imp_VariantInit
0x180008f59  nop
0x180008f5a  mov     r9d, 8; vt
0x180008f60  xor     r8d, r8d; wFlags
0x180008f63  lea     rdx, [rbp+230h+pvarg]; pvarSrc
0x180008f67  lea     rcx, [rbp+230h+pvargDest]; pvargDest
0x180008f6b  call    cs:__imp_VariantChangeType
0x180008f71  test    eax, eax
0x180008f73  js      loc_1800090AA
0x180008f79  lea     rdx, asc_180025330; " "
0x180008f80  lea     rcx, [rbp+230h+var_2A8]; this
0x180008f84  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x180008f89  nop
0x180008f8a  lea     rdx, [rbp+230h+var_2A8]; struct _bstr_t *
0x180008f8e  lea     rcx, [rsp+330h+var_2C0]; struct _bstr_t *
0x180008f93  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x180008f98  nop
0x180008f99  lea     rcx, [rbp+230h+var_2A8]; this
0x180008f9d  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180008fa2  lea     rdx, asc_18002532C; "\""
0x180008fa9  lea     rcx, [rbp+230h+var_2A0]; this
0x180008fad  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x180008fb2  nop
0x180008fb3  lea     rdx, [rbp+230h+var_2A0]; struct _bstr_t *
0x180008fb7  lea     rcx, [rsp+330h+var_2C0]; struct _bstr_t *
0x180008fbc  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x180008fc1  nop
0x180008fc2  lea     rcx, [rbp+230h+var_2A0]; this
0x180008fc6  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180008fcb  test    rbx, rbx
0x180008fce  jz      short loc_180008FD5
0x180008fd0  mov     rcx, [rbx]
0x180008fd3  jmp     short loc_180008FD7
0x180008fd5  xor     ecx, ecx; String1
0x180008fd7  lea     rdx, aMsgId; "$MSG_ID"
0x180008fde  call    cs:__imp__wcsicmp
0x180008fe4  test    eax, eax
0x180008fe6  jz      short loc_180009027
0x180008fe8  test    rbx, rbx
0x180008feb  jz      short loc_180008FF2
0x180008fed  mov     rcx, [rbx]
0x180008ff0  jmp     short loc_180008FF4
0x180008ff2  xor     ecx, ecx; String1
0x180008ff4  lea     rdx, aMsgCorrelation; "$MSG_CORRELATION_ID"
0x180008ffb  call    cs:__imp__wcsicmp
0x180009001  test    eax, eax
0x180009003  jz      short loc_180009027
0x180009005  lea     rdx, [rbp+230h+pvargDest]; struct _variant_t *
0x180009009  lea     rcx, [rbp+230h+var_270]; this
0x18000900d  call    ??0_bstr_t@@QEAA@AEBV_variant_t@@@Z; _bstr_t::_bstr_t(_variant_t const &)
0x180009012  nop
0x180009013  mov     rdx, rax; struct _bstr_t *
0x180009016  lea     rcx, [rsp+330h+var_2C0]; struct _bstr_t *
0x18000901b  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x180009020  nop
0x180009021  lea     rcx, [rbp+230h+var_270]
0x180009025  jmp     short loc_180009055
0x180009027  lea     rdx, [rbp+230h+var_240]; wchar_t *
0x18000902b  mov     rcx, qword ptr [rbp+230h+pvargDest+8]; struct _OBJECTID *
0x18000902f  call    ?ObjectIDToString@@YAXPEBU_OBJECTID@@PEA_WK@Z; ObjectIDToString(_OBJECTID const *,wchar_t *,ulong)
0x180009034  lea     rdx, [rbp+230h+var_240]; wchar_t *
0x180009038  lea     rcx, [rbp+230h+var_298]; this
0x18000903c  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x180009041  nop
0x180009042  lea     rdx, [rbp+230h+var_298]; struct _bstr_t *
0x180009046  lea     rcx, [rsp+330h+var_2C0]; struct _bstr_t *
0x18000904b  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x180009050  nop
0x180009051  lea     rcx, [rbp+230h+var_298]; this
0x180009055  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000905a  lea     rdx, asc_18002532C; "\""
0x180009061  lea     rcx, [rbp+230h+var_290]; this
0x180009065  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x18000906a  nop
0x18000906b  lea     rdx, [rbp+230h+var_290]; struct _bstr_t *
0x18000906f  lea     rcx, [rsp+330h+var_2C0]; struct _bstr_t *
0x180009074  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x180009079  nop
0x18000907a  lea     rcx, [rbp+230h+var_290]; this
0x18000907e  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180009083  lea     rcx, [rbp+230h+pvarg]; pvarg
0x180009087  call    cs:__imp_VariantClear
0x18000908d  nop
0x18000908e  lea     rcx, [rbp+230h+pvargDest]; this
0x180009092  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180009097  nop
0x180009098  lea     rcx, [rsp+330h+var_2B8]; this
0x18000909d  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800090a2  inc     r15d
0x1800090a5  jmp     loc_180008EE2
0x1800090aa  mov     ecx, 154h
0x1800090af  mov     [rsp+330h+var_2D0], cx
0x1800090b4  mov     dword ptr [rsp+330h+var_2C8], eax
0x1800090b8  lea     rsi, aTrigobjsRulehd; "trigobjs/rulehdlr"
0x1800090bf  xor     ebx, ebx
0x1800090c1  lea     r15d, [rbx+4]
0x1800090c5  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, rbx; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x1800090cc  jz      short loc_180009122
0x1800090ce  mov     rcx, rsi; wchar_t *
0x1800090d1  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x1800090d6  lea     r13d, [rbx+1]
0x1800090da  lea     r9d, [rax+r13]
0x1800090de  add     r9, r9
0x1800090e1  mov     [rsp+330h+var_2E0], rbx
0x1800090e6  mov     [rsp+330h+var_2E8], rbx
0x1800090eb  lea     rax, [rsp+330h+var_2C8]
0x1800090f0  mov     [rsp+330h+var_2F0], rax
0x1800090f5  mov     [rsp+330h+var_2F8], r15
0x1800090fa  lea     rax, [rsp+330h+var_2D0]
0x1800090ff  mov     [rsp+330h+var_300], rax
0x180009104  mov     qword ptr [rsp+330h+var_308], r12
0x180009109  mov     [rsp+330h+var_310], rsi
0x18000910e  mov     r8d, r13d
0x180009111  mov     edx, r13d
0x180009114  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18000911b  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x180009120  jmp     short loc_180009128
0x180009122  mov     r13d, 1
0x180009128  lea     rcx, [rbp+230h+pvarg]; pvarg
0x18000912c  call    cs:__imp_VariantClear
0x180009132  mov     r8d, eax
0x180009135  lea     rax, WPP_GLOBAL_Control
0x18000913c  mov     rcx, cs:WPP_GLOBAL_Control
0x180009143  cmp     rcx, rax
0x180009146  jz      short loc_18000917C
0x180009148  test    [rcx+1Ch], r13b
0x18000914c  jz      short loc_18000917C
0x18000914e  mov     rdx, [r14+90h]
0x180009155  test    rdx, rdx
0x180009158  jz      short loc_18000915F
0x18000915a  mov     r9, [rdx]
0x18000915d  jmp     short loc_180009162
0x18000915f  mov     r9, rbx
0x180009162  mov     edx, 22h ; '"'
0x180009167  mov     dword ptr [rsp+330h+var_310], r8d; char
0x18000916c  lea     r8, WPP_07c04997ef9c358328a47f0c936100cf_Traceguids
0x180009173  mov     rcx, [rcx+10h]; LoggerHandle
0x180009177  call    WPP_SF_SD
0x18000917c  mov     eax, 15Eh
0x180009181  mov     [rsp+330h+var_2D0], ax
0x180009186  mov     dword ptr [rsp+330h+var_2C8], 0C00E0E0Ch
0x18000918e  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, rbx; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180009195  jz      short loc_1800091E6
0x180009197  mov     rcx, rsi; wchar_t *
0x18000919a  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18000919f  lea     r9d, [rax+r13]
0x1800091a3  add     r9, r9
0x1800091a6  mov     [rsp+330h+var_2E0], rbx
0x1800091ab  mov     [rsp+330h+var_2E8], rbx
0x1800091b0  lea     rax, [rsp+330h+var_2C8]
0x1800091b5  mov     [rsp+330h+var_2F0], rax
0x1800091ba  mov     [rsp+330h+var_2F8], r15
0x1800091bf  lea     rax, [rsp+330h+var_2D0]
0x1800091c4  mov     [rsp+330h+var_300], rax
0x1800091c9  mov     qword ptr [rsp+330h+var_308], r12
0x1800091ce  mov     [rsp+330h+var_310], rsi
0x1800091d3  mov     r8d, r13d
0x1800091d6  mov     edx, r13d
0x1800091d9  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x1800091e0  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x1800091e5  nop
0x1800091e6  lea     rcx, [rbp+230h+pvargDest]; this
0x1800091ea  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x1800091ef  nop
0x1800091f0  lea     rcx, [rsp+330h+var_2B8]; this
0x1800091f5  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800091fa  nop
0x1800091fb  lea     rcx, [rsp+330h+var_2C0]; this
0x180009200  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180009205  nop
0x180009206  lea     rcx, [rbp+230h+var_2B0]; this
0x18000920a  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000920f  nop
0x180009210  test    rdi, rdi
0x180009213  jz      loc_18000939F
0x180009219  mov     rax, [rdi]
0x18000921c  mov     rax, [rax+10h]
0x180009220  jmp     loc_180009396
0x180009225  mov     ecx, 140h
0x18000922a  mov     [rsp+330h+var_2D0], cx
0x18000922f  mov     dword ptr [rsp+330h+var_2C8], eax
0x180009233  lea     rsi, aTrigobjsRulehd; "trigobjs/rulehdlr"
0x18000923a  mov     r15d, 4
  ... truncated ...
```
