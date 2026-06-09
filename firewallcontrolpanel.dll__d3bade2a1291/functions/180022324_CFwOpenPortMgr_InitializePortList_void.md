# CFwOpenPortMgr::InitializePortList(void)

- ea: `0x180022324`
- end: `0x180022aa4`
- name: `?InitializePortList@CFwOpenPortMgr@@AEAAJXZ`
- size: `1920`
- prototype: `__int64 __fastcall(CFwOpenPortMgr *__hidden this)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config`

## callers

- `0x18001d014`

## callees

- `0x1800096a8`
- `0x18000994c`
- `0x180009b30`
- `0x18000c358`
- `0x18000c49c`
- `0x180018180`
- `0x180021774`
- `0x180021fa0`
- `0x180022324`
- `0x180022aac`
- `0x180022ae4`
- `0x180022b1c`
- `0x180022be8`
- `0x180022c34`
- `0x180022f40`
- `0x180022fdc`
- `0x18002308c`
- `0x180023140`
- `0x1800231f4`
- `0x18002481c`
- `0x180030ea0`
- `0x180032010`

## import_xrefs

- `FirewallAPI!FWOpenPolicyStore` at `0x1800223de`
- `FirewallAPI!FWOpenPolicyStore` at `0x1800223de`
- `FirewallAPI!FWClosePolicyStore` at `0x180022a17`
- `FirewallAPI!FWClosePolicyStore` at `0x180022a17`
- `FirewallAPI!FWEnumFirewallRules` at `0x180022460`
- `FirewallAPI!FWEnumFirewallRules` at `0x180022460`
- `FirewallAPI!FWFreeFirewallRules` at `0x1800229fd`
- `FirewallAPI!FWFreeFirewallRules` at `0x1800229fd`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CFwOpenPortMgr::InitializePortList(CFwOpenPortMgr *this, __int64 a2)
{
  int v3; // r12d
  char *v4; // rbx
  __int64 v5; // rdx
  float v6; // xmm4_4
  int v7; // xmm5_4
  int v8; // eax
  signed int v9; // edi
  CFwCplLua *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  int v13; // eax
  struct _tag_FW_RULE *v14; // rsi
  struct _tag_FW_RULE *v15; // rax
  struct _tag_FW_RULE *i; // r15
  BOOL v17; // r13d
  unsigned __int64 v18; // rdx
  int v19; // ecx
  int v20; // eax
  unsigned __int64 v21; // rdx
  unsigned __int16 v22; // ax
  __int64 v23; // r15
  int v24; // edx
  int v25; // eax
  int v26; // ecx
  unsigned __int64 v27; // rdx
  int v28; // edx
  int v29; // eax
  int v30; // ecx
  int v31; // ecx
  int v32; // eax
  int v33; // eax
  unsigned int j; // ecx
  __int64 v35; // rax
  unsigned __int64 v36; // rdx
  struct _tag_FW_RULE *v37; // rsi
  int v38; // ecx
  int v39; // eax
  struct _tag_FW_RULE *v41; // [rsp+30h] [rbp-D0h] BYREF
  const unsigned __int16 *v42; // [rsp+38h] [rbp-C8h] BYREF
  struct _tag_FW_RULE *v43; // [rsp+40h] [rbp-C0h]
  __int64 v44; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v45; // [rsp+50h] [rbp-B0h] BYREF
  int v46; // [rsp+58h] [rbp-A8h] BYREF
  struct _tag_FW_RULE *v47; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v48; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v49[2]; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v50; // [rsp+80h] [rbp-80h]
  _BYTE v51[80]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v52[1024]; // [rsp+110h] [rbp+10h] BYREF

  v3 = 0;
  v47 = 0;
  v48 = 0;
  v46 = 0;
  v4 = 0;
  ATL::CAtlMap<_FW_CPL_TRAITS,CFwOpenPortBase *,CFwRuleGroupTraits,ATL::CElementTraits<CFwOpenPortBase *>>::CAtlMap<_FW_CPL_TRAITS,CFwOpenPortBase *,CFwRuleGroupTraits,ATL::CElementTraits<CFwOpenPortBase *>>(
    (__int64)v51,
    a2,
    0.75,
    0.25,
    SLODWORD(FLOAT_2_25));
  ATL::CAtlMap<_FW_CPL_TRAITS,CFwOpenPortBase *,CFwRuleGroupTraits,ATL::CElementTraits<CFwOpenPortBase *>>::CAtlMap<_FW_CPL_TRAITS,CFwOpenPortBase *,CFwRuleGroupTraits,ATL::CElementTraits<CFwOpenPortBase *>>(
    (__int64)v49,
    v5,
    v6,
    0.25,
    v7);
  v45 = 0;
  v44 = 0;
  v42 = WTL::_atltmpPchNil;
  v8 = FWOpenPolicyStore(545, 0, 5, 1, 0, &v48);
  v9 = v8;
  if ( v8 > 0 )
    v9 = (unsigned __int16)v8 | 0x80070000;
  if ( v9 >= 0 )
  {
    v13 = FWEnumFirewallRules(v48, 196608, 0x7FFFFFFF, 1, &v46, &v47);
    v9 = v13;
    if ( v13 > 0 )
      v9 = (unsigned __int16)v13 | 0x80070000;
    if ( v9 < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CFwCplLua *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_78;
      v11 = 14;
      goto LABEL_7;
    }
    v14 = v47;
    v41 = v47;
    v15 = v47;
    for ( i = v47; ; i = v15 )
    {
      if ( !v15 )
      {
        if ( v49[1] )
        {
          for ( j = 0; j < v50; ++j )
          {
            v35 = *(_QWORD *)(v49[0] + 8LL * j);
            if ( v35 )
              goto LABEL_65;
          }
        }
        v35 = 0;
LABEL_65:
        v45 = v35;
        while ( v45 )
        {
          v37 = *(struct _tag_FW_RULE **)ATL::CAtlMap<_FW_CPL_TRAITS,_tag_FW_RULE *,CFwAppTraits,ATL::CElementTraits<_tag_FW_RULE *>>::GetNextValue(
                                           v49,
                                           &v45);
          if ( v37 )
          {
            v4 = (char *)DirectUI::HAllocAndZero((DirectUI *)0x48, v36);
            v41 = (struct _tag_FW_RULE *)v4;
            if ( !v4 )
            {
              v4 = 0;
              v12 = 2147942414LL;
              v9 = -2147024882;
              v10 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v11 = 18;
                goto LABEL_8;
              }
              goto LABEL_78;
            }
            v38 = *((_DWORD *)this + 18);
            v39 = *((_DWORD *)this + 19);
            *(_QWORD *)v4 = &CRefObject::`vftable';
            *((_DWORD *)v4 + 2) = 1;
            *((_QWORD *)v4 + 2) = 0;
            *((_QWORD *)v4 + 3) = 0;
            *((_QWORD *)v4 + 4) = 0;
            *((_QWORD *)v4 + 5) = 0;
            *((_QWORD *)v4 + 6) = 0;
            *((_DWORD *)v4 + 14) = 0;
            *((_DWORD *)v4 + 15) = v39;
            *((_DWORD *)v4 + 16) = v38;
            *(_QWORD *)v4 = &CFwOpenPortCustom::`vftable';
            v41 = (struct _tag_FW_RULE *)v4;
            v33 = CFwOpenPortBase::Initialize((CFwOpenPortBase *)v4, v37);
            v9 = v33;
            if ( v33 < 0 )
            {
              v10 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v11 = 19;
                goto LABEL_55;
              }
              goto LABEL_78;
            }
            ATL::CAtlList<CListViewItemState *,ATL::CElementTraits<CListViewItemState *>>::AddTail(
              (__int64 *)this + 2,
              (__int64)&v41);
            v4 = 0;
          }
        }
        goto LABEL_77;
      }
      if ( !(unsigned int)CFwOpenPortMgr::ShouldProcessRule(this, v14) )
        goto LABEL_32;
      v17 = 0;
      if ( (unsigned int)IsRuleGroup(v14, v52) )
      {
        WTL::CString::operator=((WTL::CString *)&v42, v52);
        v43 = v14;
        if ( (unsigned __int8)ATL::CAtlMap<_FW_CPL_TRAITS,CFwOpenPortBase *,CFwRuleGroupTraits,ATL::CElementTraits<CFwOpenPortBase *>>::Lookup(
                                v51,
                                &v42,
                                &v45) == 1 )
        {
          (*(void (__fastcall **)(__int64, struct _tag_FW_RULE *))(*(_QWORD *)v45 + 80LL))(v45, v14);
          goto LABEL_32;
        }
        v4 = (char *)DirectUI::HAllocAndZero((DirectUI *)0x68, v18);
        v41 = (struct _tag_FW_RULE *)v4;
        if ( v4 )
        {
          v19 = *((_DWORD *)this + 18);
          v20 = *((_DWORD *)this + 19);
          *(_QWORD *)v4 = &CRefObject::`vftable';
          *((_DWORD *)v4 + 2) = 1;
          *((_QWORD *)v4 + 2) = 0;
          *((_QWORD *)v4 + 3) = 0;
          *((_QWORD *)v4 + 4) = 0;
          *((_QWORD *)v4 + 5) = 0;
          *((_QWORD *)v4 + 6) = 0;
          *((_DWORD *)v4 + 14) = 0;
          *((_DWORD *)v4 + 15) = v20;
          *((_DWORD *)v4 + 16) = v19;
          *(_QWORD *)v4 = &CFwOpenPortGroup::`vftable';
          *((_QWORD *)v4 + 9) = 0;
          *((_QWORD *)v4 + 10) = 0;
          *((_DWORD *)v4 + 22) = 0;
          *(_QWORD *)(v4 + 92) = 0;
          *((_DWORD *)v4 + 25) = 0;
        }
        else
        {
          v4 = 0;
        }
        v3 = 1;
        goto LABEL_40;
      }
      if ( (unsigned int)IsAuthApp(v14) )
      {
        WTL::CString::operator=((WTL::CString *)&v42, *((unsigned __int16 **)i + 34));
        v43 = v14;
        if ( !(unsigned __int8)ATL::CAtlMap<_FW_CPL_TRAITS,_tag_FW_RULE *,CFwAppTraits,ATL::CElementTraits<_tag_FW_RULE *>>::Lookup(
                                 v49,
                                 &v42,
                                 &v44) )
        {
          ATL::CAtlMap<_FW_CPL_TRAITS,_tag_FW_RULE *,CFwAppTraits,ATL::CElementTraits<_tag_FW_RULE *>>::SetAt(
            v49,
            &v42,
            &v41);
LABEL_31:
          v3 = 0;
          goto LABEL_32;
        }
        v22 = *((_WORD *)i + 24);
        v23 = v44;
        v17 = *(_WORD *)(v44 + 48) != v22;
        v4 = (char *)DirectUI::HAllocAndZero((DirectUI *)0x58, v21);
        v41 = (struct _tag_FW_RULE *)v4;
        if ( v4 )
        {
          v24 = *((_DWORD *)this + 19);
          v25 = *((_DWORD *)this + 18);
          v26 = *((_DWORD *)this + 16);
          *(_QWORD *)v4 = &CRefObject::`vftable';
          *((_DWORD *)v4 + 2) = 1;
          *((_QWORD *)v4 + 2) = 0;
          *((_QWORD *)v4 + 3) = 0;
          *((_QWORD *)v4 + 4) = 0;
          *((_QWORD *)v4 + 5) = 0;
          *((_QWORD *)v4 + 6) = 0;
          *((_DWORD *)v4 + 14) = 0;
          *((_DWORD *)v4 + 16) = v25;
          *(_QWORD *)v4 = &CFwOpenPortApp::`vftable';
          *((_QWORD *)v4 + 9) = 0;
          *((_DWORD *)v4 + 20) = v26;
          *((_DWORD *)v4 + 15) = v24;
        }
        else
        {
          v4 = 0;
        }
        goto LABEL_41;
      }
      if ( IsOpenPort(v14) )
      {
        v4 = (char *)DirectUI::HAllocAndZero((DirectUI *)0x58, v27);
        v41 = (struct _tag_FW_RULE *)v4;
        if ( !v4 )
          goto LABEL_39;
        v28 = *((_DWORD *)this + 19);
        v29 = *((_DWORD *)this + 18);
        v30 = *((_DWORD *)this + 17);
        *(_QWORD *)v4 = &CRefObject::`vftable';
        *((_DWORD *)v4 + 2) = 1;
        *((_QWORD *)v4 + 2) = 0;
        *((_QWORD *)v4 + 3) = 0;
        *((_QWORD *)v4 + 4) = 0;
        *((_QWORD *)v4 + 5) = 0;
        *((_QWORD *)v4 + 6) = 0;
        *((_DWORD *)v4 + 14) = 0;
        *((_DWORD *)v4 + 16) = v29;
        *(_QWORD *)v4 = &CFwOpenPort::`vftable';
        *((_WORD *)v4 + 36) = 0;
        *((_DWORD *)v4 + 19) = 6;
        *((_DWORD *)v4 + 20) = v30;
        *((_DWORD *)v4 + 15) = v28;
      }
      else
      {
        if ( *((_DWORD *)i + 11) != 1 )
          goto LABEL_31;
        v4 = (char *)DirectUI::HAllocAndZero((DirectUI *)0x48, v27);
        v41 = (struct _tag_FW_RULE *)v4;
        if ( !v4 )
        {
LABEL_39:
          v4 = 0;
          goto LABEL_40;
        }
        v31 = *((_DWORD *)this + 18);
        v32 = *((_DWORD *)this + 19);
        *(_QWORD *)v4 = &CRefObject::`vftable';
        *((_DWORD *)v4 + 2) = 1;
        *((_QWORD *)v4 + 2) = 0;
        *((_QWORD *)v4 + 3) = 0;
        *((_QWORD *)v4 + 4) = 0;
        *((_QWORD *)v4 + 5) = 0;
        *((_QWORD *)v4 + 6) = 0;
        *((_DWORD *)v4 + 14) = 0;
        *((_DWORD *)v4 + 15) = v32;
        *((_DWORD *)v4 + 16) = v31;
        *(_QWORD *)v4 = &CFwOpenPortCustom::`vftable';
      }
LABEL_40:
      v23 = v44;
LABEL_41:
      v41 = (struct _tag_FW_RULE *)v4;
      if ( !v4 )
      {
        v12 = 2147942414LL;
        v9 = -2147024882;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v11 = 15;
          goto LABEL_8;
        }
        goto LABEL_78;
      }
      v33 = CFwOpenPortBase::Initialize((CFwOpenPortBase *)v4, v14);
      v9 = v33;
      if ( v33 < 0 )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v11 = 16;
          goto LABEL_55;
        }
        goto LABEL_78;
      }
      if ( v3 )
      {
        WTL::CString::operator=((WTL::CString *)&v42, v52);
        v43 = v14;
        ATL::CAtlMap<_FW_CPL_TRAITS,CFwOpenPortBase *,CFwRuleGroupTraits,ATL::CElementTraits<CFwOpenPortBase *>>::SetAt(
          v51,
          &v42,
          &v41);
        v3 = 0;
      }
      else
      {
        v3 = 0;
        if ( v17 )
        {
          v33 = (*(__int64 (__fastcall **)(char *, __int64))(*(_QWORD *)v4 + 80LL))(v4, v23);
          v9 = v33;
          if ( v33 < 0 )
          {
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CFwCplLua *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v11 = 17;
LABEL_55:
              v12 = (unsigned int)v33;
              goto LABEL_8;
            }
            goto LABEL_78;
          }
          WTL::CString::operator=((WTL::CString *)&v42, *((unsigned __int16 **)v14 + 34));
          v43 = v14;
          ATL::CAtlMap<_FW_CPL_TRAITS,_tag_FW_RULE *,CFwAppTraits,ATL::CElementTraits<_tag_FW_RULE *>>::RemoveKey(
            v49,
            &v42);
        }
      }
      ATL::CAtlList<CListViewItemState *,ATL::CElementTraits<CListViewItemState *>>::AddTail(
        (__int64 *)this + 2,
        (__int64)&v41);
      v4 = 0;
LABEL_32:
      v15 = *(struct _tag_FW_RULE **)v14;
      v14 = v15;
      v41 = v15;
    }
  }
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CFwCplLua *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    goto LABEL_78;
  v11 = 13;
LABEL_7:
  v12 = (unsigned int)v9;
LABEL_8:
  WPP_SF_d(*((_QWORD *)v10 + 2), v11, WPP_1aaa36be460e3ec051e4f2cd9cb11fbc_Traceguids, v12);
LABEL_77:
  v10 = WPP_GLOBAL_Control;
LABEL_78:
  if ( v47 )
  {
    FWFreeFirewallRules(v47);
    v10 = WPP_GLOBAL_Control;
  }
  if ( v48 )
  {
    FWClosePolicyStore(v48);
    v10 = WPP_GLOBAL_Control;
  }
  if ( v9 < 0 && v4 )
  {
    CRefObject::Release((CRefObject *)v4);
    v10 = WPP_GLOBAL_Control;
  }
  if ( v10 != (CFwCplLua *)&WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)v10 + 2), 20, WPP_1aaa36be460e3ec051e4f2cd9cb11fbc_Traceguids, (unsigned int)v9);
  WTL::CString::~CString((WTL::CString *)&v42);
  ATL::CAtlMap<_FW_CPL_TRAITS,CFwOpenPortBase *,CFwRuleGroupTraits,ATL::CElementTraits<CFwOpenPortBase *>>::RemoveAll(v49);
  ATL::CAtlMap<_FW_CPL_TRAITS,CFwOpenPortBase *,CFwRuleGroupTraits,ATL::CElementTraits<CFwOpenPortBase *>>::RemoveAll(v51);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180022324  push    rbp
0x180022326  push    rbx
0x180022327  push    rsi
0x180022328  push    rdi
0x180022329  push    r12
0x18002232b  push    r13
0x18002232d  push    r14
0x18002232f  push    r15
0x180022331  lea     rbp, [rsp-828h]
0x180022339  sub     rsp, 928h
0x180022340  mov     rax, cs:__security_cookie
0x180022347  xor     rax, rsp
0x18002234a  mov     [rbp+860h+var_50], rax
0x180022351  mov     r14, rcx
0x180022354  xor     r12d, r12d
0x180022357  mov     [rsp+960h+var_900], r12
0x18002235c  mov     [rsp+960h+var_8F8], r12
0x180022361  mov     [rsp+960h+var_908], r12d
0x180022366  mov     ebx, r12d
0x180022369  movss   xmm5, cs:__real@40100000
0x180022371  movss   dword ptr [rsp+960h+var_940], xmm5
0x180022377  movss   xmm3, cs:__real@3e800000
0x18002237f  movss   xmm4, cs:__real@3f400000
0x180022387  movaps  xmm2, xmm4
0x18002238a  lea     rcx, [rbp+860h+var_8A0]
0x18002238e  call    ??0?$CAtlMap@U_FW_CPL_TRAITS@@PEAVCFwOpenPortBase@@VCFwRuleGroupTraits@@V?$CElementTraits@PEAVCFwOpenPortBase@@@ATL@@@ATL@@QEAA@IMMMI@Z; ATL::CAtlMap<_FW_CPL_TRAITS,CFwOpenPortBase *,CFwRuleGroupTraits,ATL::CElementTraits<CFwOpenPortBase *>>::CAtlMap<_FW_CPL_TRAITS,CFwOpenPortBase *,CFwRuleGroupTraits,ATL::CElementTraits<CFwOpenPortBase *>>(uint,float,float,float,uint)
0x180022393  nop
0x180022394  movss   dword ptr [rsp+960h+var_940], xmm5
0x18002239a  movaps  xmm2, xmm4
0x18002239d  lea     rcx, [rsp+960h+var_8F0]
0x1800223a2  call    ??0?$CAtlMap@U_FW_CPL_TRAITS@@PEAVCFwOpenPortBase@@VCFwRuleGroupTraits@@V?$CElementTraits@PEAVCFwOpenPortBase@@@ATL@@@ATL@@QEAA@IMMMI@Z; ATL::CAtlMap<_FW_CPL_TRAITS,CFwOpenPortBase *,CFwRuleGroupTraits,ATL::CElementTraits<CFwOpenPortBase *>>::CAtlMap<_FW_CPL_TRAITS,CFwOpenPortBase *,CFwRuleGroupTraits,ATL::CElementTraits<CFwOpenPortBase *>>(uint,float,float,float,uint)
0x1800223a7  nop
0x1800223a8  mov     [rsp+960h+var_910], r12
0x1800223ad  mov     [rsp+960h+var_918], r12
0x1800223b2  mov     rax, cs:?_atltmpPchNil@WTL@@3PEBGEB; ushort const * const WTL::_atltmpPchNil
0x1800223b9  mov     [rsp+960h+var_928], rax
0x1800223be  mov     ecx, 221h
0x1800223c3  lea     rax, [rsp+960h+var_8F8]
0x1800223c8  mov     [rsp+960h+var_938], rax
0x1800223cd  mov     dword ptr [rsp+960h+var_940], r12d
0x1800223d2  xor     edx, edx
0x1800223d4  lea     r9d, [r12+1]
0x1800223d9  lea     r8d, [r12+5]
0x1800223de  call    cs:__imp_FWOpenPolicyStore
0x1800223e4  mov     edi, eax
0x1800223e6  mov     esi, 80070000h
0x1800223eb  test    eax, eax
0x1800223ed  jle     short loc_1800223F4
0x1800223ef  movzx   edi, ax
0x1800223f2  or      edi, esi
0x1800223f4  lea     r13, WPP_GLOBAL_Control
0x1800223fb  test    edi, edi
0x1800223fd  jns     short loc_180022436
0x1800223ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180022406  cmp     rcx, r13
0x180022409  jz      loc_1800229F0
0x18002240f  test    byte ptr [rcx+1Ch], 1
0x180022413  jz      loc_1800229F0
0x180022419  mov     edx, 0Dh
0x18002241e  mov     r9d, edi
0x180022421  lea     r8, WPP_1aaa36be460e3ec051e4f2cd9cb11fbc_Traceguids
0x180022428  mov     rcx, [rcx+10h]
0x18002242c  call    WPP_SF_d
0x180022431  jmp     loc_1800229E9
0x180022436  mov     r9d, 1
0x18002243c  lea     rax, [rsp+960h+var_900]
0x180022441  mov     [rsp+960h+var_938], rax
0x180022446  lea     rax, [rsp+960h+var_908]
0x18002244b  mov     [rsp+960h+var_940], rax
0x180022450  mov     edx, 30000h
0x180022455  mov     r8d, 7FFFFFFFh
0x18002245b  mov     rcx, [rsp+960h+var_8F8]
0x180022460  call    cs:__imp_FWEnumFirewallRules
0x180022466  mov     edi, eax
0x180022468  test    eax, eax
0x18002246a  jle     short loc_180022471
0x18002246c  movzx   edi, ax
0x18002246f  or      edi, esi
0x180022471  test    edi, edi
0x180022473  jns     short loc_180022496
0x180022475  mov     rcx, cs:WPP_GLOBAL_Control
0x18002247c  cmp     rcx, r13
0x18002247f  jz      loc_1800229F0
0x180022485  test    byte ptr [rcx+1Ch], 1
0x180022489  jz      loc_1800229F0
0x18002248f  mov     edx, 0Eh
0x180022494  jmp     short loc_18002241E
0x180022496  mov     rsi, [rsp+960h+var_900]
0x18002249b  mov     [rsp+960h+var_930], rsi
0x1800224a0  mov     rax, rsi
0x1800224a3  mov     r15, rsi
0x1800224a6  test    rax, rax
0x1800224a9  jz      loc_1800228B2
0x1800224af  mov     rdx, rsi; struct _tag_FW_RULE *
0x1800224b2  mov     rcx, r14; this
0x1800224b5  call    ?ShouldProcessRule@CFwOpenPortMgr@@AEAAHPEAU_tag_FW_RULE@@@Z; CFwOpenPortMgr::ShouldProcessRule(_tag_FW_RULE *)
0x1800224ba  test    eax, eax
0x1800224bc  jz      loc_18002267C
0x1800224c2  mov     r13d, r12d
0x1800224c5  lea     rdx, [rbp+860h+var_850]; unsigned __int16 *
0x1800224c9  mov     rcx, rsi; struct _tag_FW_RULE *
0x1800224cc  call    ?IsRuleGroup@@YAHPEAU_tag_FW_RULE@@PEAGK@Z; IsRuleGroup(_tag_FW_RULE *,ushort *,ulong)
0x1800224d1  test    eax, eax
0x1800224d3  jz      loc_18002259E
0x1800224d9  lea     rdx, [rbp+860h+var_850]; unsigned __int16 *
0x1800224dd  lea     rcx, [rsp+960h+var_928]; this
0x1800224e2  call    ??4CString@WTL@@QEAAAEAV01@PEBG@Z; WTL::CString::operator=(ushort const *)
0x1800224e7  mov     [rsp+960h+var_920], rsi
0x1800224ec  lea     r8, [rsp+960h+var_910]
0x1800224f1  lea     rdx, [rsp+960h+var_928]
0x1800224f6  lea     rcx, [rbp+860h+var_8A0]
0x1800224fa  call    ?Lookup@?$CAtlMap@U_FW_CPL_TRAITS@@PEAVCFwOpenPortBase@@VCFwRuleGroupTraits@@V?$CElementTraits@PEAVCFwOpenPortBase@@@ATL@@@ATL@@QEBA_NAEBU_FW_CPL_TRAITS@@AEAPEAVCFwOpenPortBase@@@Z; ATL::CAtlMap<_FW_CPL_TRAITS,CFwOpenPortBase *,CFwRuleGroupTraits,ATL::CElementTraits<CFwOpenPortBase *>>::Lookup(_FW_CPL_TRAITS const &,CFwOpenPortBase * &)
0x1800224ff  mov     r15d, 1
0x180022505  cmp     al, r15b
0x180022508  jnz     short loc_180022523
0x18002250a  mov     rcx, [rsp+960h+var_910]
0x18002250f  mov     rax, [rcx]
0x180022512  mov     rdx, rsi
0x180022515  mov     rax, [rax+50h]
0x180022519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002251e  jmp     loc_18002267C
0x180022523  mov     ecx, 68h ; 'h'; this
0x180022528  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x18002252d  mov     rbx, rax
0x180022530  mov     [rsp+960h+var_930], rax
0x180022535  test    rax, rax
0x180022538  jz      short loc_180022593
0x18002253a  mov     ecx, [r14+48h]
0x18002253e  mov     eax, [r14+4Ch]
0x180022542  lea     rdx, ??_7CRefObject@@6B@; const CRefObject::`vftable'
0x180022549  mov     [rbx], rdx
0x18002254c  mov     [rbx+8], r15d
0x180022550  mov     qword ptr [rbx+10h], 0
0x180022558  mov     [rbx+18h], r12
0x18002255c  mov     [rbx+20h], r12
0x180022560  mov     [rbx+28h], r12
0x180022564  mov     [rbx+30h], r12
0x180022568  mov     [rbx+38h], r12d
0x18002256c  mov     [rbx+3Ch], eax
0x18002256f  mov     [rbx+40h], ecx
0x180022572  lea     rax, ??_7CFwOpenPortGroup@@6B@; const CFwOpenPortGroup::`vftable'
0x180022579  mov     [rbx], rax
0x18002257c  mov     [rbx+48h], r12
0x180022580  mov     [rbx+50h], r12
0x180022584  mov     [rbx+58h], r12d
0x180022588  xor     eax, eax
0x18002258a  mov     [rbx+5Ch], rax
0x18002258e  mov     [rbx+64h], eax
0x180022591  jmp     short loc_180022596
0x180022593  mov     rbx, r12
0x180022596  mov     r12d, r15d
0x180022599  jmp     loc_180022775
0x18002259e  mov     rcx, rsi; struct _tag_FW_RULE *
0x1800225a1  call    ?IsAuthApp@@YAHPEAU_tag_FW_RULE@@@Z; IsAuthApp(_tag_FW_RULE *)
0x1800225a6  test    eax, eax
0x1800225a8  jz      loc_18002268F
0x1800225ae  mov     rdx, [r15+110h]; unsigned __int16 *
0x1800225b5  lea     rcx, [rsp+960h+var_928]; this
0x1800225ba  call    ??4CString@WTL@@QEAAAEAV01@PEBG@Z; WTL::CString::operator=(ushort const *)
0x1800225bf  mov     [rsp+960h+var_920], rsi
0x1800225c4  lea     r8, [rsp+960h+var_918]
0x1800225c9  lea     rdx, [rsp+960h+var_928]
0x1800225ce  lea     rcx, [rsp+960h+var_8F0]
0x1800225d3  call    ?Lookup@?$CAtlMap@U_FW_CPL_TRAITS@@PEAU_tag_FW_RULE@@VCFwAppTraits@@V?$CElementTraits@PEAU_tag_FW_RULE@@@ATL@@@ATL@@QEBA_NAEBU_FW_CPL_TRAITS@@AEAPEAU_tag_FW_RULE@@@Z; ATL::CAtlMap<_FW_CPL_TRAITS,_tag_FW_RULE *,CFwAppTraits,ATL::CElementTraits<_tag_FW_RULE *>>::Lookup(_FW_CPL_TRAITS const &,_tag_FW_RULE * &)
0x1800225d8  test    al, al
0x1800225da  jz      loc_180022665
0x1800225e0  xor     edi, edi
0x1800225e2  mov     r13d, edi
0x1800225e5  movzx   eax, word ptr [r15+30h]
0x1800225ea  mov     r15, [rsp+960h+var_918]
0x1800225ef  cmp     [r15+30h], ax
0x1800225f4  setnz   r13b
0x1800225f8  lea     ecx, [rdi+58h]; this
0x1800225fb  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x180022600  mov     rbx, rax
0x180022603  mov     [rsp+960h+var_930], rax
0x180022608  test    rax, rax
0x18002260b  jz      short loc_18002265D
0x18002260d  mov     edx, [r14+4Ch]
0x180022611  mov     eax, [r14+48h]
0x180022615  mov     ecx, [r14+40h]
0x180022619  lea     r8, ??_7CRefObject@@6B@; const CRefObject::`vftable'
0x180022620  mov     [rbx], r8
0x180022623  mov     dword ptr [rbx+8], 1
0x18002262a  mov     [rbx+10h], rdi
0x18002262e  mov     [rbx+18h], rdi
0x180022632  mov     [rbx+20h], rdi
0x180022636  mov     [rbx+28h], rdi
0x18002263a  mov     [rbx+30h], rdi
0x18002263e  mov     [rbx+38h], edi
0x180022641  mov     [rbx+40h], eax
0x180022644  lea     rax, ??_7CFwOpenPortApp@@6B@; const CFwOpenPortApp::`vftable'
0x18002264b  mov     [rbx], rax
0x18002264e  mov     [rbx+48h], rdi
0x180022652  mov     [rbx+50h], ecx
0x180022655  mov     [rbx+3Ch], edx
0x180022658  jmp     loc_18002277A
0x18002265d  mov     rbx, rdi
0x180022660  jmp     loc_18002277A
0x180022665  lea     r8, [rsp+960h+var_930]
0x18002266a  lea     rdx, [rsp+960h+var_928]
0x18002266f  lea     rcx, [rsp+960h+var_8F0]
0x180022674  call    ?SetAt@?$CAtlMap@U_FW_CPL_TRAITS@@PEAU_tag_FW_RULE@@VCFwAppTraits@@V?$CElementTraits@PEAU_tag_FW_RULE@@@ATL@@@ATL@@QEAAPEAU__POSITION@@AEBU_FW_CPL_TRAITS@@AEBQEAU_tag_FW_RULE@@@Z; ATL::CAtlMap<_FW_CPL_TRAITS,_tag_FW_RULE *,CFwAppTraits,ATL::CElementTraits<_tag_FW_RULE *>>::SetAt(_FW_CPL_TRAITS const &,_tag_FW_RULE * const &)
0x180022679  xor     r12d, r12d
0x18002267c  mov     rax, [rsi]
0x18002267f  mov     rsi, rax
0x180022682  mov     [rsp+960h+var_930], rax
0x180022687  mov     r15, rax
0x18002268a  jmp     loc_1800224A6
0x18002268f  mov     rcx, rsi; struct _tag_FW_RULE *
0x180022692  call    ?IsOpenPort@@YAHPEAU_tag_FW_RULE@@@Z; IsOpenPort(_tag_FW_RULE *)
0x180022697  test    eax, eax
0x180022699  jz      short loc_18002270C
0x18002269b  mov     ecx, 58h ; 'X'; this
0x1800226a0  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x1800226a5  mov     rbx, rax
0x1800226a8  mov     [rsp+960h+var_930], rax
0x1800226ad  xor     edi, edi
0x1800226af  test    rax, rax
0x1800226b2  jz      loc_180022772
0x1800226b8  mov     edx, [r14+4Ch]
0x1800226bc  mov     eax, [r14+48h]
0x1800226c0  mov     ecx, [r14+44h]
0x1800226c4  lea     r8, ??_7CRefObject@@6B@; const CRefObject::`vftable'
0x1800226cb  mov     [rbx], r8
0x1800226ce  mov     dword ptr [rbx+8], 1
0x1800226d5  mov     [rbx+10h], rdi
0x1800226d9  mov     [rbx+18h], rdi
0x1800226dd  mov     [rbx+20h], rdi
0x1800226e1  mov     [rbx+28h], rdi
0x1800226e5  mov     [rbx+30h], rdi
0x1800226e9  mov     [rbx+38h], edi
0x1800226ec  mov     [rbx+40h], eax
0x1800226ef  lea     rax, ??_7CFwOpenPort@@6B@; const CFwOpenPort::`vftable'
0x1800226f6  mov     [rbx], rax
0x1800226f9  mov     [rbx+48h], di
0x1800226fd  mov     dword ptr [rbx+4Ch], 6
0x180022704  mov     [rbx+50h], ecx
0x180022707  mov     [rbx+3Ch], edx
0x18002270a  jmp     short loc_180022775
0x18002270c  cmp     dword ptr [r15+2Ch], 1
0x180022711  jnz     loc_180022679
0x180022717  mov     ecx, 48h ; 'H'; this
0x18002271c  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x180022721  mov     rbx, rax
0x180022724  mov     [rsp+960h+var_930], rax
0x180022729  xor     edi, edi
0x18002272b  test    rax, rax
0x18002272e  jz      short loc_180022772
0x180022730  mov     ecx, [r14+48h]
0x180022734  mov     eax, [r14+4Ch]
0x180022738  lea     rdx, ??_7CRefObject@@6B@; const CRefObject::`vftable'
0x18002273f  mov     [rbx], rdx
0x180022742  mov     dword ptr [rbx+8], 1
0x180022749  mov     [rbx+10h], rdi
0x18002274d  mov     [rbx+18h], rdi
0x180022751  mov     [rbx+20h], rdi
0x180022755  mov     [rbx+28h], rdi
0x180022759  mov     [rbx+30h], rdi
0x18002275d  mov     [rbx+38h], edi
0x180022760  mov     [rbx+3Ch], eax
0x180022763  mov     [rbx+40h], ecx
0x180022766  lea     rax, ??_7CFwOpenPortCustom@@6B@; const CFwOpenPortCustom::`vftable'
0x18002276d  mov     [rbx], rax
0x180022770  jmp     short loc_180022775
0x180022772  mov     rbx, rdi
0x180022775  mov     r15, [rsp+960h+var_918]
0x18002277a  mov     [rsp+960h+var_930], rbx
0x18002277f  test    rbx, rbx
0x180022782  jz      loc_18002287E
0x180022788  mov     rdx, rsi; struct _tag_FW_RULE *
0x18002278b  mov     rcx, rbx; this
0x18002278e  call    ?Initialize@CFwOpenPortBase@@QEAAJPEAU_tag_FW_RULE@@@Z; CFwOpenPortBase::Initialize(_tag_FW_RULE *)
0x180022793  mov     edi, eax
0x180022795  test    eax, eax
0x180022797  js      loc_180022850
0x18002279d  test    r12d, r12d
0x1800227a0  jz      short loc_1800227CD
0x1800227a2  lea     rdx, [rbp+860h+var_850]; unsigned __int16 *
0x1800227a6  lea     rcx, [rsp+960h+var_928]; this
0x1800227ab  call    ??4CString@WTL@@QEAAAEAV01@PEBG@Z; WTL::CString::operator=(ushort const *)
0x1800227b0  mov     [rsp+960h+var_920], rsi
0x1800227b5  lea     r8, [rsp+960h+var_930]
0x1800227ba  lea     rdx, [rsp+960h+var_928]
0x1800227bf  lea     rcx, [rbp+860h+var_8A0]
0x1800227c3  call    ?SetAt@?$CAtlMap@U_FW_CPL_TRAITS@@PEAVCFwOpenPortBase@@VCFwRuleGroupTraits@@V?$CElementTraits@PEAVCFwOpenPortBase@@@ATL@@@ATL@@QEAAPEAU__POSITION@@AEBU_FW_CPL_TRAITS@@AEBQEAVCFwOpenPortBase@@@Z; ATL::CAtlMap<_FW_CPL_TRAITS,CFwOpenPortBase *,CFwRuleGroupTraits,ATL::CElementTraits<CFwOpenPortBase *>>::SetAt(_FW_CPL_TRAITS const &,CFwOpenPortBase * const &)
0x1800227c8  xor     r12d, r12d
0x1800227cb  jmp     short loc_180022812
0x1800227cd  xor     r12d, r12d
0x1800227d0  test    r13d, r13d
0x1800227d3  jz      short loc_180022812
0x1800227d5  mov     rax, [rbx]
0x1800227d8  mov     rdx, r15
0x1800227db  mov     rcx, rbx
0x1800227de  mov     rax, [rax+50h]
0x1800227e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800227e7  mov     edi, eax
0x1800227e9  test    eax, eax
0x1800227eb  js      short loc_180022828
0x1800227ed  mov     rdx, [rsi+110h]; unsigned __int16 *
  ... truncated ...
```
