# CMSMQRuleHandler::PrepareMethodParameters(IMSMQPropertyBag *,tagDISPPARAMS *)

- ea: `0x180009420`
- end: `0x180009771`
- name: `?PrepareMethodParameters@CMSMQRuleHandler@@QEAAXPEAUIMSMQPropertyBag@@PEAUtagDISPPARAMS@@@Z`
- size: `849`
- prototype: `void __fastcall(CMSMQRuleHandler *__hidden this, struct IMSMQPropertyBag *, struct tagDISPPARAMS *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800084d0`

## callees

- `0x180001ce6`
- `0x180004d20`
- `0x18000544c`
- `0x180005574`
- `0x180006ef0`
- `0x180009420`
- `0x180009ab0`
- `0x180014ae8`
- `0x180014d30`
- `0x180015888`
- `0x180022010`

## import_xrefs

- `msvcrt!free` at `0x1800094c3`
- `msvcrt!free` at `0x180009764`
- `msvcrt!free` at `0x1800094c3`
- `msvcrt!free` at `0x180009764`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x180009706`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x180009706`
- `OLEAUT32!__imp_VariantInit` at `0x180009528`
- `OLEAUT32!__imp_VariantInit` at `0x180009543`
- `OLEAUT32!__imp_VariantInit` at `0x180009528`
- `OLEAUT32!__imp_VariantInit` at `0x180009543`
- `OLEAUT32!__imp_VariantClear` at `0x180009559`
- `OLEAUT32!__imp_VariantClear` at `0x180009559`
- `OLEAUT32!__imp_VariantCopy` at `0x18000966a`
- `OLEAUT32!__imp_VariantCopy` at `0x18000966a`

## pseudocode

```c
void __fastcall CMSMQRuleHandler::PrepareMethodParameters(
        CMSMQRuleHandler *this,
        struct IMSMQPropertyBag *a2,
        struct tagDISPPARAMS *a3)
{
  struct tagDISPPARAMS *v3; // r14
  int v6; // esi
  struct tagVARIANT *v7; // rax
  __int64 v8; // r15
  struct tagVARIANT *v9; // r14
  int v10; // r13d
  signed int ArgumentValue; // r15d
  unsigned int v12; // eax
  VARIANTARG *v13; // r15
  HRESULT v14; // eax
  unsigned int v15; // eax
  wchar_t *v16; // rdx
  wchar_t *v17; // r8
  __int64 v18; // [rsp+60h] [rbp-B8h] BYREF
  __int64 v19; // [rsp+68h] [rbp-B0h] BYREF
  struct tagVARIANT *v20; // [rsp+70h] [rbp-A8h]
  VARIANTARG pvarg; // [rsp+78h] [rbp-A0h] BYREF
  struct IMSMQPropertyBag *v22; // [rsp+90h] [rbp-88h]
  const _com_error *v23; // [rsp+98h] [rbp-80h] BYREF
  _QWORD v24[3]; // [rsp+A0h] [rbp-78h] BYREF
  _BYTE pExceptionObject[96]; // [rsp+B8h] [rbp-60h] BYREF
  struct tagVARIANT *v26; // [rsp+128h] [rbp+10h] BYREF
  struct tagDISPPARAMS *v27; // [rsp+130h] [rbp+18h]
  int v28; // [rsp+138h] [rbp+20h]

  v27 = a3;
  v3 = a3;
  ((void (__stdcall *)(_bstr_t *, const wchar_t *))_bstr_t::_bstr_t)((_bstr_t *)&v19, &psz);
  memset(&pvarg, 0, sizeof(pvarg));
  v20 = 0;
  v22 = a2;
  if ( a2 )
    (*(void (__fastcall **)(struct IMSMQPropertyBag *))(*(_QWORD *)a2 + 8LL))(a2);
  *(_OWORD *)&v3->rgvarg = 0;
  *(_QWORD *)&v3->cArgs = 0;
  v6 = *((_DWORD *)this + 34) - 3;
  v28 = v6;
  if ( v6 )
  {
    v7 = (struct tagVARIANT *)MmAllocate(saturated_mul(v6, 0x18u));
    v26 = v7;
    v20 = v7;
    v8 = 0;
    if ( v6 > 0 )
    {
      v9 = v7;
      do
      {
        VariantInit(&v9[v8]);
        v8 = (unsigned int)(v8 + 1);
      }
      while ( (int)v8 < v6 );
      v3 = v27;
    }
    VariantInit(&pvarg);
    v10 = 1;
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v13 = v26;
      while ( 1 )
      {
        VariantClear(&pvarg);
        if ( v10 > v6 )
          break;
        CStringTokens::GetToken((CMSMQRuleHandler *)((char *)this + 112), v10 + 2, (struct _bstr_t *)&v19);
        v18 = v19;
        if ( v19 )
          _InterlockedAdd((volatile signed __int32 *)(v19 + 16), 1u);
        ArgumentValue = CMSMQRuleHandler::GetArgumentValue((__int64)this, (__int64)a2, (const wchar_t ***)&v18, &pvarg);
        if ( ArgumentValue < 0 )
        {
          LOWORD(v26) = 250;
          LODWORD(v18) = ArgumentValue;
          if ( g_pMSMQErrorLoggingTrace )
          {
            v12 = mqwcslen(L"trigobjs/rulehdlr");
            CMSMQTrace::MSMQTraceEvent(
              (__int64)g_pMSMQErrorLoggingTrace,
              1,
              1,
              2LL * (v12 + 1),
              L"trigobjs/rulehdlr",
              2,
              &v26,
              4,
              &v18,
              0,
              0);
          }
          bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, ArgumentValue);
          throw (bad_hresult *)pExceptionObject;
        }
        v13 = v26;
        v14 = VariantCopy(&v26[v6 - v10], &pvarg);
        if ( v14 < 0 )
        {
          LOWORD(v26) = 270;
          LODWORD(v18) = v14;
          if ( g_pMSMQErrorLoggingTrace )
          {
            v15 = mqwcslen(L"trigobjs/rulehdlr");
            CMSMQTrace::MSMQTraceEvent(
              (__int64)g_pMSMQErrorLoggingTrace,
              1,
              1,
              2LL * (v15 + 1),
              L"trigobjs/rulehdlr",
              2,
              &v26,
              4,
              &v18,
              0,
              0);
          }
          exception::exception((exception *)v24, &std::_bad_alloc_Message, 1);
          v24[0] = &std::bad_alloc::`vftable';
          throw (std::bad_alloc *)v24;
        }
        ++v10;
      }
      v20 = 0;
      v3->rgvarg = v13;
      v3->cArgs = v6;
      v3->cNamedArgs = 0;
      v3->rgdispidNamedArgs = 0;
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &_com_error `RTTI Type Descriptor', &v23) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          if ( v19 )
            v16 = *(wchar_t **)v19;
          else
            v16 = 0;
          WPP_SF_SSd(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, *((_DWORD *)v23 + 2));
        }
        VariantArrayClear(v20, v28);
        LogIllegalPoint((wchar_t *)L"trigobjs/rulehdlr", 0x118u);
        throw;
      }
      if ( __eh34_catch_type(0, &exception `RTTI Type Descriptor', 0) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          if ( v19 )
            v17 = *(wchar_t **)v19;
          else
            v17 = 0;
          WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), v17);
        }
        VariantArrayClear(v20, v28);
        LogIllegalPoint((wchar_t *)L"trigobjs/rulehdlr", 0x122u);
        throw;
      }
    }
    if ( a2 )
      (*(void (__fastcall **)(struct IMSMQPropertyBag *))(*(_QWORD *)a2 + 16LL))(a2);
    free(0);
  }
  else
  {
    if ( a2 )
      (*(void (__fastcall **)(struct IMSMQPropertyBag *))(*(_QWORD *)a2 + 16LL))(a2);
    free(0);
  }
  _bstr_t::_Free((_bstr_t *)&v19);
}

```

## disassembly

```asm
0x180009420  mov     [rsp+arg_10], r8
0x180009425  mov     [rsp+arg_0], rcx
0x18000942a  push    rbx
0x18000942b  push    rsi
0x18000942c  push    rdi
0x18000942d  push    r12
0x18000942f  push    r13
0x180009431  push    r14
0x180009433  push    r15
0x180009435  sub     rsp, 0E0h
0x18000943c  mov     r14, r8
0x18000943f  mov     rbx, rdx
0x180009442  mov     r12, rcx
0x180009445  lea     rdx, psz; wchar_t *
0x18000944c  lea     rcx, [rsp+118h+var_B0]; this
0x180009451  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x180009456  nop
0x180009457  xorps   xmm0, xmm0
0x18000945a  xor     eax, eax
0x18000945c  movups  xmmword ptr [rsp+118h+pvarg], xmm0
0x180009461  mov     qword ptr [rsp+118h+pvarg+10h], rax
0x180009469  mov     [rsp+118h+var_A8], rax
0x18000946e  mov     [rsp+118h+var_88], rbx
0x180009476  test    rbx, rbx
0x180009479  jz      short loc_18000948B
0x18000947b  mov     rax, [rbx]
0x18000947e  mov     rcx, rbx
0x180009481  mov     rax, [rax+8]
0x180009485  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000948a  nop
0x18000948b  xorps   xmm0, xmm0
0x18000948e  xor     eax, eax
0x180009490  movups  xmmword ptr [r14], xmm0
0x180009494  mov     [r14+10h], rax
0x180009498  mov     esi, [r12+88h]
0x1800094a0  sub     esi, 3
0x1800094a3  mov     [rsp+118h+arg_18], esi
0x1800094aa  jnz     short loc_1800094E7
0x1800094ac  test    rbx, rbx
0x1800094af  jz      short loc_1800094C1
0x1800094b1  mov     rax, [rbx]
0x1800094b4  mov     rcx, rbx
0x1800094b7  mov     rax, [rax+10h]
0x1800094bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094c0  nop
0x1800094c1  xor     ecx, ecx; Block
0x1800094c3  call    cs:__imp_free
0x1800094c9  nop
0x1800094ca  lea     rcx, [rsp+118h+var_B0]; this
0x1800094cf  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800094d4  add     rsp, 0E0h
0x1800094db  pop     r15
0x1800094dd  pop     r14
0x1800094df  pop     r13
0x1800094e1  pop     r12
0x1800094e3  pop     rdi
0x1800094e4  pop     rsi
0x1800094e5  pop     rbx
0x1800094e6  retn
0x1800094e7  movsxd  rcx, esi
0x1800094ea  mov     eax, 18h
0x1800094ef  mul     rcx
0x1800094f2  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800094f9  cmovb   rax, rcx
0x1800094fd  mov     rcx, rax; unsigned __int64
0x180009500  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180009505  mov     [rsp+118h+arg_8], rax
0x18000950d  mov     [rsp+118h+var_A8], rax
0x180009512  xor     r15d, r15d
0x180009515  lea     edi, [r15+1]
0x180009519  test    esi, esi
0x18000951b  jle     short loc_18000953E
0x18000951d  mov     r14, rax
0x180009520  lea     rdx, [r15+r15*2]
0x180009524  lea     rcx, [r14+rdx*8]; pvarg
0x180009528  call    cs:__imp_VariantInit
0x18000952e  add     r15d, edi
0x180009531  cmp     r15d, esi
0x180009534  jl      short loc_180009520
0x180009536  mov     r14, [rsp+118h+arg_10]
0x18000953e  lea     rcx, [rsp+118h+pvarg]; pvarg
0x180009543  call    cs:__imp_VariantInit
0x180009549  mov     r13d, edi
0x18000954c  mov     r15, [rsp+118h+arg_8]
0x180009554  lea     rcx, [rsp+118h+pvarg]; pvarg
0x180009559  call    cs:__imp_VariantClear
0x18000955f  cmp     r13d, esi
0x180009562  jg      loc_180009737
0x180009568  lea     edx, [r13+2]; unsigned int
0x18000956c  lea     rcx, [r12+70h]; this
0x180009571  lea     r8, [rsp+118h+var_B0]; struct _bstr_t *
0x180009576  call    ?GetToken@CStringTokens@@QEAAXKAEAV_bstr_t@@@Z; CStringTokens::GetToken(ulong,_bstr_t &)
0x18000957b  mov     rax, [rsp+118h+var_B0]
0x180009580  mov     [rsp+118h+var_B8], rax
0x180009585  test    rax, rax
0x180009588  jz      short loc_18000958E
0x18000958a  lock add [rax+10h], edi
0x18000958e  lea     r9, [rsp+118h+pvarg]
0x180009593  lea     r8, [rsp+118h+var_B8]
0x180009598  mov     rdx, rbx
0x18000959b  mov     rcx, r12
0x18000959e  call    ?GetArgumentValue@CMSMQRuleHandler@@QEAAJPEAUIMSMQPropertyBag@@V_bstr_t@@PEAUtagVARIANT@@@Z; CMSMQRuleHandler::GetArgumentValue(IMSMQPropertyBag *,_bstr_t,tagVARIANT *)
0x1800095a3  mov     r15d, eax
0x1800095a6  test    eax, eax
0x1800095a8  jns     loc_18000964E
0x1800095ae  mov     eax, 0FAh
0x1800095b3  mov     word ptr [rsp+118h+arg_8], ax
0x1800095bb  mov     dword ptr [rsp+118h+var_B8], r15d
0x1800095c0  xor     esi, esi
0x1800095c2  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, rsi; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x1800095c9  jz      short loc_18000962A
0x1800095cb  lea     rbx, aTrigobjsRulehd; "trigobjs/rulehdlr"
0x1800095d2  mov     rcx, rbx; wchar_t *
0x1800095d5  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x1800095da  lea     r9d, [rax+1]
0x1800095de  add     r9, r9
0x1800095e1  mov     [rsp+118h+var_C8], rsi
0x1800095e6  mov     [rsp+118h+var_D0], rsi
0x1800095eb  lea     rax, [rsp+118h+var_B8]
0x1800095f0  mov     [rsp+118h+var_D8], rax
0x1800095f5  mov     [rsp+118h+var_E0], 4
0x1800095fe  lea     rax, [rsp+118h+arg_8]
0x180009606  mov     [rsp+118h+var_E8], rax
0x18000960b  mov     [rsp+118h+var_F0], 2
0x180009614  mov     [rsp+118h+var_F8], rbx
0x180009619  mov     r8d, edi
0x18000961c  mov     edx, edi
0x18000961e  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180009625  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x18000962a  mov     edx, r15d; unsigned int
0x18000962d  lea     rcx, [rsp+118h+pExceptionObject]; this
0x180009635  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x18000963a  lea     rdx, _TI3?AVbad_hresult@@; pThrowInfo
0x180009641  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x180009649  call    _CxxThrowException_0
0x18000964e  mov     eax, esi
0x180009650  sub     eax, r13d
0x180009653  cdqe
0x180009655  lea     rcx, [rax+rax*2]
0x180009659  mov     r15, [rsp+118h+arg_8]
0x180009661  lea     rcx, [r15+rcx*8]; pvargDest
0x180009665  lea     rdx, [rsp+118h+pvarg]; pvargSrc
0x18000966a  call    cs:__imp_VariantCopy
0x180009670  test    eax, eax
0x180009672  jns     loc_18000972F
0x180009678  mov     ecx, 10Eh
0x18000967d  mov     word ptr [rsp+118h+arg_8], cx
0x180009685  mov     dword ptr [rsp+118h+var_B8], eax
0x180009689  xor     esi, esi
0x18000968b  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, rsi; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180009692  jz      short loc_1800096F4
0x180009694  lea     rbx, aTrigobjsRulehd; "trigobjs/rulehdlr"
0x18000969b  mov     rcx, rbx; wchar_t *
0x18000969e  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x1800096a3  lea     r9d, [rax+1]
0x1800096a7  add     r9, r9
0x1800096aa  mov     [rsp+118h+var_C8], rsi
0x1800096af  mov     [rsp+118h+var_D0], rsi
0x1800096b4  lea     rax, [rsp+118h+var_B8]
0x1800096b9  mov     [rsp+118h+var_D8], rax
0x1800096be  mov     [rsp+118h+var_E0], 4
0x1800096c7  lea     rax, [rsp+118h+arg_8]
0x1800096cf  mov     [rsp+118h+var_E8], rax
0x1800096d4  mov     [rsp+118h+var_F0], 2
0x1800096dd  mov     [rsp+118h+var_F8], rbx
0x1800096e2  mov     r8d, edi
0x1800096e5  mov     edx, edi
0x1800096e7  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x1800096ee  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x1800096f3  nop
0x1800096f4  mov     r8d, edi
0x1800096f7  lea     rdx, ?_bad_alloc_Message@std@@3PEBDEB; char const * const std::_bad_alloc_Message
0x1800096fe  lea     rcx, [rsp+118h+var_78]
0x180009706  call    cs:__imp_??0exception@@QEAA@AEBQEBDH@Z; exception::exception(char const * const &,int)
0x18000970c  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180009713  mov     [rsp+118h+var_78], rax
0x18000971b  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180009722  lea     rcx, [rsp+118h+var_78]; pExceptionObject
0x18000972a  call    _CxxThrowException_0
0x18000972f  add     r13d, edi
0x180009732  jmp     loc_180009554
0x180009737  xor     eax, eax
0x180009739  mov     [rsp+118h+var_A8], rax
0x18000973e  mov     [r14], r15
0x180009741  mov     [r14+10h], esi
0x180009745  mov     [r14+14h], eax
0x180009749  mov     [r14+8], rax
0x18000974d  test    rbx, rbx
0x180009750  jz      short loc_180009762
0x180009752  mov     rax, [rbx]
0x180009755  mov     rcx, rbx
0x180009758  mov     rax, [rax+10h]
0x18000975c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009761  nop
0x180009762  xor     ecx, ecx; Block
0x180009764  call    cs:__imp_free
0x18000976a  nop
0x18000976b  jmp     loc_1800094CA
```
