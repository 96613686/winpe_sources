# CTriggerMonitor::InvokeRegularRuleHandlers(_com_ptr_t<_com_IIID<IMSMQPropertyBag,&__s_GUID const _GUID_07f19951_ab28_11d2_8936_000000000000>> &,CRuntimeTriggerInfo *,CQueue *)

- ea: `0x140009358`
- end: `0x14000954a`
- name: `?InvokeRegularRuleHandlers@CTriggerMonitor@@AEAAJAEAV?$_com_ptr_t@V?$_com_IIID@UIMSMQPropertyBag@@$1?_GUID_07f19951_ab28_11d2_8936_000000000000@@3U__s_GUID@@B@@@@PEAVCRuntimeTriggerInfo@@PEAVCQueue@@@Z`
- size: `498`
- prototype: `__int64 __fastcall(__int64, __int64 *, __int64, struct CQueue *)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140009238`

## callees

- `0x1400030ac`
- `0x1400031a0`
- `0x140003dc8`
- `0x14000752c`
- `0x1400082d4`
- `0x140008b60`
- `0x140009358`
- `0x140009e04`
- `0x140009e74`
- `0x14000a48c`
- `0x14000a5fc`
- `0x140011ed0`
- `0x140017cb0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x14000949d`
- `OLEAUT32!__imp_VariantInit` at `0x14000949d`

## pseudocode

```c
__int64 __fastcall CTriggerMonitor::InvokeRegularRuleHandlers(__int64 a1, __int64 *a2, __int64 a3, struct CQueue *a4)
{
  unsigned int v7; // r14d
  char v8; // r15
  unsigned int i; // edi
  struct CRuntimeRuleInfo *Rule; // rbx
  __int64 v11; // r9
  __int64 *v12; // rax
  __int64 v13; // r8
  wchar_t **v14; // rax
  wchar_t *v15; // r8
  __int64 v16; // rbx
  _bstr_t *v17; // rax
  int v18; // ebx
  VARIANTARG pvarg; // [rsp+30h] [rbp-40h] BYREF
  VARIANTARG pvargSrc; // [rsp+50h] [rbp-20h] BYREF
  __int64 v22; // [rsp+B0h] [rbp+40h] BYREF
  int v23; // [rsp+C0h] [rbp+50h] BYREF

  v22 = a1;
  v7 = *(_DWORD *)(a3 + 2128);
  v8 = 0;
  for ( i = 0; i < v7; ++i )
  {
    Rule = CRuntimeTriggerInfo::GetRule((CRuntimeTriggerInfo *)a3, i);
    LODWORD(v22) = 0;
    v23 = 0;
    CheckRuleCondition(Rule, a2, &v22);
    if ( (_DWORD)v22 )
    {
      v8 = 1;
      ExecuteRule(Rule, a2, &v23);
      if ( CSafeSet<_bstr_t>::erase(qword_14002AE28, Rule) )
      {
        if ( *(_QWORD *)Rule )
          v11 = **(_QWORD **)Rule;
        else
          v11 = 0;
        v12 = (__int64 *)*((_QWORD *)Rule + 1);
        if ( v12 )
          v13 = *v12;
        else
          v13 = 0;
        EvReport(0x400008A9u, 2u, v13, v11);
      }
      if ( (v23 & 1) != 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v14 = *(wchar_t ***)(a3 + 2088);
          if ( v14 )
            v15 = *v14;
          else
            v15 = 0;
          WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), v15);
        }
        break;
      }
    }
  }
  if ( *(_DWORD *)(a3 + 20) != 1 || !v8 )
    return 0;
  VariantInit(&pvarg);
  v16 = _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->(a2);
  v17 = _bstr_t::_bstr_t((_bstr_t *)&v22, L"LookupId");
  IMSMQPropertyBag::Read(v16, v17, &pvarg);
  pvargSrc = pvarg;
  v18 = ReceiveMessage(&pvargSrc, a4);
  if ( v18 >= 0 )
  {
    _variant_t::~_variant_t(&pvarg);
    return 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_1833f040ae3e358d840c1ed912348424_Traceguids);
  _variant_t::~_variant_t(&pvarg);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x140009358  mov     [rsp-38h+arg_8], rbx
0x14000935d  mov     [rsp-38h+arg_0], rcx
0x140009362  push    rbp
0x140009363  push    rsi
0x140009364  push    rdi
0x140009365  push    r12
0x140009367  push    r13
0x140009369  push    r14
0x14000936b  push    r15
0x14000936d  mov     rbp, rsp
0x140009370  sub     rsp, 70h
0x140009374  mov     r13, r9
0x140009377  mov     rsi, r8
0x14000937a  mov     r12, rdx
0x14000937d  mov     r14d, [r8+850h]
0x140009384  xor     r15b, r15b
0x140009387  xor     edi, edi
0x140009389  cmp     edi, r14d
0x14000938c  jnb     loc_14000947F
0x140009392  mov     edx, edi; int
0x140009394  mov     rcx, rsi; this
0x140009397  call    ?GetRule@CRuntimeTriggerInfo@@QEAAPEAVCRuntimeRuleInfo@@J@Z; CRuntimeTriggerInfo::GetRule(long)
0x14000939c  mov     rbx, rax
0x14000939f  mov     dword ptr [rbp+arg_0], 0
0x1400093a6  mov     [rbp+arg_10], 0
0x1400093ad  lea     r8, [rbp+arg_0]
0x1400093b1  mov     rdx, r12
0x1400093b4  mov     rcx, rax
0x1400093b7  call    CheckRuleCondition
0x1400093bc  cmp     dword ptr [rbp+arg_0], 0
0x1400093c0  jz      short loc_14000941E
0x1400093c2  mov     r15b, 1
0x1400093c5  lea     r8, [rbp+arg_10]
0x1400093c9  mov     rdx, r12
0x1400093cc  mov     rcx, rbx
0x1400093cf  call    ExecuteRule
0x1400093d4  mov     rdx, rbx
0x1400093d7  lea     rcx, qword_14002AE28
0x1400093de  call    ?erase@?$CSafeSet@V_bstr_t@@@@QEAA_KAEBV_bstr_t@@@Z; CSafeSet<_bstr_t>::erase(_bstr_t const &)
0x1400093e3  test    rax, rax
0x1400093e6  jz      short loc_140009418
0x1400093e8  mov     rax, [rbx]
0x1400093eb  test    rax, rax
0x1400093ee  jz      short loc_1400093F5
0x1400093f0  mov     r9, [rax]
0x1400093f3  jmp     short loc_1400093F8
0x1400093f5  xor     r9d, r9d
0x1400093f8  mov     rax, [rbx+8]
0x1400093fc  test    rax, rax
0x1400093ff  jz      short loc_140009406
0x140009401  mov     r8, [rax]
0x140009404  jmp     short loc_140009409
0x140009406  xor     r8d, r8d
0x140009409  mov     edx, 2; unsigned __int16
0x14000940e  mov     ecx, 400008A9h; unsigned int
0x140009413  call    ?EvReport@@YAXKGZZ; EvReport(ulong,ushort,...)
0x140009418  test    byte ptr [rbp+arg_10], r15b
0x14000941c  jnz     short loc_140009425
0x14000941e  inc     edi
0x140009420  jmp     loc_140009389
0x140009425  mov     rcx, cs:WPP_GLOBAL_Control
0x14000942c  lea     rdi, WPP_GLOBAL_Control
0x140009433  cmp     rcx, rdi
0x140009436  jz      short loc_140009486
0x140009438  test    byte ptr [rcx+1Ch], 4
0x14000943c  jz      short loc_140009486
0x14000943e  mov     rax, [rsi+828h]
0x140009445  test    rax, rax
0x140009448  jz      short loc_14000944F
0x14000944a  mov     r8, [rax]
0x14000944d  jmp     short loc_140009452
0x14000944f  xor     r8d, r8d
0x140009452  mov     rax, [rbx+8]
0x140009456  test    rax, rax
0x140009459  jz      short loc_140009460
0x14000945b  mov     r9, [rax]
0x14000945e  jmp     short loc_140009463
0x140009460  xor     r9d, r9d
0x140009463  mov     edx, 26h ; '&'
0x140009468  mov     [rsp+70h+var_50], r8; wchar_t *
0x14000946d  lea     r8, WPP_1833f040ae3e358d840c1ed912348424_Traceguids
0x140009474  mov     rcx, [rcx+10h]; LoggerHandle
0x140009478  call    WPP_SF_SS
0x14000947d  jmp     short loc_140009486
0x14000947f  lea     rdi, WPP_GLOBAL_Control
0x140009486  cmp     dword ptr [rsi+14h], 1
0x14000948a  jnz     loc_140009530
0x140009490  test    r15b, r15b
0x140009493  jz      loc_140009530
0x140009499  lea     rcx, [rbp+pvarg]; pvarg
0x14000949d  call    cs:__imp_VariantInit
0x1400094a3  nop
0x1400094a4  mov     rcx, r12
0x1400094a7  call    ??C?$_com_ptr_t@V?$_com_IIID@UIMSMQRuleHandler@@$1?_GUID_b0cdbf11_9774_11d2_8929_000000000000@@3U__s_GUID@@B@@@@QEBAPEAUIMSMQRuleHandler@@XZ; _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->(void)
0x1400094ac  mov     rbx, rax
0x1400094af  lea     rdx, aLookupid; "LookupId"
0x1400094b6  lea     rcx, [rbp+arg_0]; this
0x1400094ba  call    ??0_bstr_t@@QEAA@PEB_W@Z; _bstr_t::_bstr_t(wchar_t const *)
0x1400094bf  lea     r8, [rbp+pvarg]
0x1400094c3  mov     rdx, rax
0x1400094c6  mov     rcx, rbx
0x1400094c9  call    ?Read@IMSMQPropertyBag@@QEAAJV_bstr_t@@PEAUtagVARIANT@@@Z; IMSMQPropertyBag::Read(_bstr_t,tagVARIANT *)
0x1400094ce  movups  xmm0, xmmword ptr [rbp+pvarg]
0x1400094d2  movaps  xmmword ptr [rbp+pvargSrc], xmm0
0x1400094d6  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x1400094db  movsd   qword ptr [rbp+pvargSrc+10h], xmm1
0x1400094e0  mov     rdx, r13; struct CQueue *
0x1400094e3  lea     rcx, [rbp+pvargSrc]; pvargSrc
0x1400094e7  call    ?ReceiveMessage@@YAJUtagVARIANT@@PEAVCQueue@@@Z; ReceiveMessage(tagVARIANT,CQueue *)
0x1400094ec  mov     ebx, eax
0x1400094ee  test    eax, eax
0x1400094f0  jns     short loc_140009527
0x1400094f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400094f9  cmp     rcx, rdi
0x1400094fc  jz      short loc_14000951A
0x1400094fe  test    byte ptr [rcx+1Ch], 1
0x140009502  jz      short loc_14000951A
0x140009504  mov     edx, 27h ; '''
0x140009509  lea     r8, WPP_1833f040ae3e358d840c1ed912348424_Traceguids
0x140009510  mov     rcx, [rcx+10h]
0x140009514  call    WPP_SF_
0x140009519  nop
0x14000951a  lea     rcx, [rbp+pvarg]; this
0x14000951e  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x140009523  mov     eax, ebx
0x140009525  jmp     short loc_140009532
0x140009527  lea     rcx, [rbp+pvarg]; this
0x14000952b  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x140009530  xor     eax, eax
0x140009532  mov     rbx, [rsp+70h+arg_8]
0x14000953a  add     rsp, 70h
0x14000953e  pop     r15
0x140009540  pop     r14
0x140009542  pop     r13
0x140009544  pop     r12
0x140009546  pop     rdi
0x140009547  pop     rsi
0x140009548  pop     rbp
0x140009549  retn
```
