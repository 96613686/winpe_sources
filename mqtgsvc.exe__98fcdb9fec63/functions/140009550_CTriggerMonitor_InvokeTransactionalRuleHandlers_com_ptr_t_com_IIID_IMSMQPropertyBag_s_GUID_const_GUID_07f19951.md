# CTriggerMonitor::InvokeTransactionalRuleHandlers(_com_ptr_t<_com_IIID<IMSMQPropertyBag,&__s_GUID const _GUID_07f19951_ab28_11d2_8936_000000000000>> &,CRuntimeTriggerInfo *)

- ea: `0x140009550`
- end: `0x1400096a5`
- name: `?InvokeTransactionalRuleHandlers@CTriggerMonitor@@AEAAJAEAV?$_com_ptr_t@V?$_com_IIID@UIMSMQPropertyBag@@$1?_GUID_07f19951_ab28_11d2_8936_000000000000@@3U__s_GUID@@B@@@@PEAVCRuntimeTriggerInfo@@@Z`
- size: `341`
- prototype: `__int64 __fastcall(__int64, struct IUnknown **, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140009238`

## callees

- `0x140003d08`
- `0x140006ac8`
- `0x1400082d4`
- `0x140008c44`
- `0x140009550`
- `0x140009ea4`
- `0x14000a434`
- `0x140011ed0`
- `0x14001c9a0`

## pseudocode

```c
__int64 __fastcall CTriggerMonitor::InvokeTransactionalRuleHandlers(__int64 a1, struct IUnknown **a2, __int64 a3)
{
  struct IUnknown **v4; // rbx
  unsigned int v5; // eax
  unsigned int v6; // r15d
  bool v7; // r14
  unsigned int v8; // r12d
  int v9; // esi
  _bstr_t::Data_t **Rule; // r13
  __int64 v11; // rax
  __int64 v12; // rbx
  __int64 v13; // rcx
  int v14; // eax
  bool v15; // bl
  int v17; // [rsp+30h] [rbp-58h] BYREF
  unsigned int v18; // [rsp+34h] [rbp-54h]
  CReadWriteLock *v19; // [rsp+38h] [rbp-50h] BYREF
  const _com_error *v20; // [rsp+40h] [rbp-48h] BYREF
  char v24; // [rsp+A8h] [rbp+20h]

  v4 = a2;
  v5 = *(_DWORD *)(a3 + 2128);
  v18 = v5;
  v24 = 0;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  v9 = 1;
  try
  {
    while ( v8 < v5 )
    {
      Rule = (_bstr_t::Data_t **)CRuntimeTriggerInfo::GetRule((CRuntimeTriggerInfo *)a3, v8);
      v17 = 0;
      CheckRuleCondition(Rule, v4, &v17);
      if ( v17 )
      {
        v24 = 1;
        v6 |= v9;
      }
      v19 = (CReadWriteLock *)qword_14002AE28;
      CReadWriteLock::LockRead((CReadWriteLock *)qword_14002AE28);
      v11 = std::_Tree<std::_Tset_traits<_bstr_t,std::less<_bstr_t>,std::allocator<_bstr_t>,0>>::_Lbound(
              &qword_14002AE40,
              Rule);
      v12 = v11;
      v13 = qword_14002AE48;
      v9 *= 2;
      if ( v11 == qword_14002AE48
        || (v14 = _bstr_t::_Compare(Rule, (const struct _bstr_t::Data_t **)(v11 + 24)), v13 = qword_14002AE48, v14 < 0) )
      {
        v12 = v13;
      }
      v15 = v12 != v13;
      CSR::~CSR(&v19);
      if ( v15 )
        v7 = 1;
      ++v8;
      v4 = a2;
      v5 = v18;
    }
    if ( v24 )
    {
      ExecuteRulesInTransaction((wchar_t ***)(a3 + 2080), (wchar_t *)(*(_QWORD *)(a1 + 104) + 296LL), v4, v6);
      ReportSucessfullInvocation((struct CRuntimeTriggerInfo *)a3, v7);
    }
  }
  catch ( const _com_error *v20 )
  {
    if ( (unsigned __int8)CSafeSet<_bstr_t>::insert(qword_14002AE88, a3 + 2080) )
    {
      EvReportWithError(0xC00008A2, *((_DWORD *)v20 + 2), 2u, *(_QWORD *)(a3 + 2088), *(_QWORD *)(a3 + 2080));
      throw;
    }
  }
  while ( v8 < v5 )
  {
    Rule = (_bstr_t::Data_t **)CRuntimeTriggerInfo::GetRule((CRuntimeTriggerInfo *)a3, v8);
    v17 = 0;
    CheckRuleCondition(Rule, v4, &v17);
    if ( v17 )
    {
      v24 = 1;
      v6 |= v9;
    }
    v19 = (CReadWriteLock *)qword_14002AE28;
    CReadWriteLock::LockRead((CReadWriteLock *)qword_14002AE28);
    v11 = std::_Tree<std::_Tset_traits<_bstr_t,std::less<_bstr_t>,std::allocator<_bstr_t>,0>>::_Lbound(
            &qword_14002AE40,
            Rule);
    v12 = v11;
    v13 = qword_14002AE48;
    v9 *= 2;
    if ( v11 == qword_14002AE48
      || (v14 = _bstr_t::_Compare(Rule, (const struct _bstr_t::Data_t **)(v11 + 24)), v13 = qword_14002AE48, v14 < 0) )
    {
      v12 = v13;
    }
    v15 = v12 != v13;
    CSR::~CSR(&v19);
    if ( v15 )
      v7 = 1;
    ++v8;
    v4 = a2;
    v5 = v18;
  }
}

```

## disassembly

```asm
0x140009550  mov     [rsp+arg_10], r8
0x140009555  mov     [rsp+arg_8], rdx
0x14000955a  mov     [rsp+arg_0], rcx
0x14000955f  push    rbx
0x140009560  push    rsi
0x140009561  push    rdi
0x140009562  push    r12
0x140009564  push    r13
0x140009566  push    r14
0x140009568  push    r15
0x14000956a  sub     rsp, 50h
0x14000956e  mov     rdi, r8
0x140009571  mov     rbx, rdx
0x140009574  mov     eax, [r8+850h]
0x14000957b  mov     [rsp+88h+var_54], eax
0x14000957f  mov     [rsp+88h+arg_18], 0
0x140009587  xor     r15d, r15d
0x14000958a  xor     r14b, r14b
0x14000958d  xor     r12d, r12d
0x140009590  lea     esi, [r15+1]
0x140009594  cmp     r12d, eax
0x140009597  jnb     loc_140009656
0x14000959d  mov     edx, r12d; int
0x1400095a0  mov     rcx, rdi; this
0x1400095a3  call    ?GetRule@CRuntimeTriggerInfo@@QEAAPEAVCRuntimeRuleInfo@@J@Z; CRuntimeTriggerInfo::GetRule(long)
0x1400095a8  mov     r13, rax
0x1400095ab  mov     [rsp+88h+var_58], 0
0x1400095b3  lea     r8, [rsp+88h+var_58]
0x1400095b8  mov     rdx, rbx
0x1400095bb  mov     rcx, rax
0x1400095be  call    CheckRuleCondition
0x1400095c3  cmp     [rsp+88h+var_58], 0
0x1400095c8  jz      short loc_1400095D5
0x1400095ca  mov     [rsp+88h+arg_18], 1
0x1400095d2  or      r15d, esi
0x1400095d5  lea     rax, qword_14002AE28
0x1400095dc  mov     [rsp+88h+var_50], rax
0x1400095e1  mov     rcx, rax; this
0x1400095e4  call    ?LockRead@CReadWriteLock@@QEAAXXZ; CReadWriteLock::LockRead(void)
0x1400095e9  mov     rdx, r13
0x1400095ec  lea     rcx, qword_14002AE40
0x1400095f3  call    ?_Lbound@?$_Tree@V?$_Tset_traits@V_bstr_t@@U?$less@V_bstr_t@@@std@@V?$allocator@V_bstr_t@@@3@$0A@@std@@@std@@IEBAPEAU_Node@?$_Tree_nod@V?$_Tset_traits@V_bstr_t@@U?$less@V_bstr_t@@@std@@V?$allocator@V_bstr_t@@@3@$0A@@std@@@2@AEBV_bstr_t@@@Z; std::_Tree<std::_Tset_traits<_bstr_t,std::less<_bstr_t>,std::allocator<_bstr_t>,0>>::_Lbound(_bstr_t const &)
0x1400095f8  mov     rbx, rax
0x1400095fb  mov     rcx, cs:qword_14002AE48
0x140009602  add     esi, esi
0x140009604  cmp     rax, rcx
0x140009607  jz      short loc_140009620
0x140009609  lea     rdx, [rax+18h]; struct _bstr_t *
0x14000960d  mov     rcx, r13; this
0x140009610  call    ?_Compare@_bstr_t@@AEBAHAEBV1@@Z; _bstr_t::_Compare(_bstr_t const &)
0x140009615  mov     rcx, cs:qword_14002AE48
0x14000961c  test    eax, eax
0x14000961e  jns     short loc_140009623
0x140009620  mov     rbx, rcx
0x140009623  cmp     rbx, rcx
0x140009626  setnz   bl
0x140009629  lea     rcx, [rsp+88h+var_50]; this
0x14000962e  call    ??1CSR@@QEAA@XZ; CSR::~CSR(void)
0x140009633  movzx   r14d, r14b
0x140009637  test    bl, bl
0x140009639  mov     eax, 1
0x14000963e  cmovnz  r14d, eax
0x140009642  add     r12d, eax
0x140009645  mov     rbx, [rsp+88h+arg_8]
0x14000964d  mov     eax, [rsp+88h+var_54]
0x140009651  jmp     loc_140009594
0x140009656  cmp     [rsp+88h+arg_18], 0
0x14000965e  jz      short loc_140009691
0x140009660  mov     rdx, [rsp+88h+arg_0]
0x140009668  mov     rdx, [rdx+68h]
0x14000966c  add     rdx, 128h
0x140009673  lea     rcx, [rdi+820h]
0x14000967a  mov     r9d, r15d
0x14000967d  mov     r8, rbx
0x140009680  call    ExecuteRulesInTransaction
0x140009685  mov     dl, r14b; bool
0x140009688  mov     rcx, rdi; this
0x14000968b  call    ?ReportSucessfullInvocation@@YAXPEAVCRuntimeTriggerInfo@@_N@Z; ReportSucessfullInvocation(CRuntimeTriggerInfo *,bool)
0x140009690  nop
0x140009691  jmp     short $+2
0x140009693  xor     eax, eax
0x140009695  add     rsp, 50h
0x140009699  pop     r15
0x14000969b  pop     r14
0x14000969d  pop     r13
0x14000969f  pop     r12
0x1400096a1  pop     rdi
0x1400096a2  pop     rsi
0x1400096a3  pop     rbx
0x1400096a4  retn
```
