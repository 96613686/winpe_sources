# FwRules::Item(ushort *,INetFwRule * *)

- ea: `0x180004680`
- end: `0x1800049d5`
- name: `?Item@FwRules@@UEAAJPEAGPEAPEAUINetFwRule@@@Z`
- size: `853`
- prototype: `int(FwRules *__hidden this, unsigned __int16 *, struct INetFwRule **)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config`

## callees

- `0x180004680`
- `0x1800049e0`
- `0x180004ae8`
- `0x180005100`
- `0x180009780`
- `0x18000c3f0`
- `0x180010e50`
- `0x18001d578`
- `0x1800294b0`
- `0x18003336c`
- `0x18003a5bc`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetThreadUILanguage` at `0x180004990`
- `api-ms-win-core-localization-l1-2-0!GetThreadUILanguage` at `0x180004990`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLangID` at `0x18000499f`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLangID` at `0x18000499f`
- `OLEAUT32!__imp_SysStringLen` at `0x1800046ea`
- `OLEAUT32!__imp_SysStringLen` at `0x1800046ea`
- `fwbase!FwBaseFree` at `0x1800047c2`
- `fwbase!FwBaseFree` at `0x1800047c2`
- `fwbase!FwLoadIndirectString` at `0x18000470f`
- `fwbase!FwLoadIndirectString` at `0x18000470f`
- `fwbase!FwReportReturnError` at `0x1800047b2`
- `fwbase!FwReportReturnError` at `0x180004839`
- `fwbase!FwReportReturnError` at `0x180004915`
- `fwbase!FwReportReturnError` at `0x1800049c2`
- `fwbase!FwReportReturnError` at `0x1800047b2`
- `fwbase!FwReportReturnError` at `0x180004839`
- `fwbase!FwReportReturnError` at `0x180004915`
- `fwbase!FwReportReturnError` at `0x1800049c2`
- `fwbase!FwStringCopy` at `0x18000481a`
- `fwbase!FwStringCopy` at `0x18000481a`

## pseudocode

```c
__int64 __fastcall FwRules::Item(FwRules *this, unsigned __int16 *a2, struct INetFwRule **a3)
{
  struct _tag_FW_RULE *v3; // rsi
  FwPolicy2 *v7; // rcx
  int PolicyStoreHandle; // eax
  signed int v9; // ebx
  int v10; // eax
  struct _tag_FW_RULE *MatchingRuleWithRuleName; // rax
  __int64 v12; // rdx
  int v14; // eax
  int v15; // eax
  __int64 MatchingRuleWithLocRuleName; // rax
  int v17; // eax
  LANGID ThreadUILanguage; // bx
  void *v19; // [rsp+30h] [rbp-40h] BYREF
  struct _tag_FW_RULE *v20; // [rsp+38h] [rbp-38h] BYREF
  struct INetFwRule *v21; // [rsp+40h] [rbp-30h] BYREF
  unsigned int v22; // [rsp+48h] [rbp-28h] BYREF
  __int64 v23; // [rsp+50h] [rbp-20h] BYREF
  __int64 v24; // [rsp+58h] [rbp-18h] BYREF

  v3 = 0;
  v23 = 0;
  v20 = 0;
  v22 = 0;
  v19 = 0;
  v21 = 0;
  v24 = 0;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_4cf7a87c86333f9f8c34ccce893540da_Traceguids);
      v7 = WPP_GLOBAL_Control;
    }
    if ( v7 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 4) != 0 )
      WPP_SF_S(*((_QWORD *)v7 + 2), 17, WPP_4cf7a87c86333f9f8c34ccce893540da_Traceguids, a2);
  }
  if ( !a3 )
  {
    v9 = -2147467261;
    goto LABEL_22;
  }
  if ( !SysStringLen(a2) )
  {
    v9 = -2147024809;
    goto LABEL_22;
  }
  if ( *a2 != 64 || (int)FwLoadIndirectString(a2, &v24) < 0 )
  {
    v14 = FwStringCopy(a2, &v24);
    v9 = v14;
    if ( v14 < 0 )
    {
      FwReportReturnError("FwTryResolveString", (unsigned int)v14);
LABEL_22:
      v12 = (unsigned int)v9;
      goto LABEL_13;
    }
  }
  *a3 = 0;
  PolicyStoreHandle = FwRules::GetPolicyStoreHandle(this, &v19);
  v9 = PolicyStoreHandle;
  if ( PolicyStoreHandle < 0 )
  {
LABEL_12:
    v12 = (unsigned int)PolicyStoreHandle;
LABEL_13:
    FwReportReturnError("FwRules::Item", v12);
    goto LABEL_14;
  }
  v10 = FWEnumFirewallRules((__int64)v19, 196608, 0x7FFFFFFF, 7, (__int64)&v22, (__int64)&v23);
  v9 = v10;
  if ( v10 > 0 )
    v9 = (unsigned __int16)v10 | 0x80070000;
  if ( v9 < 0 )
    goto LABEL_22;
  MatchingRuleWithRuleName = (struct _tag_FW_RULE *)FwRule::FwFindMatchingRuleWithRuleName(
                                                      v23,
                                                      v22,
                                                      v24,
                                                      *((unsigned int *)this + 6));
  if ( !MatchingRuleWithRuleName )
  {
    ThreadUILanguage = GetThreadUILanguage();
    if ( GetSystemDefaultLangID() == ThreadUILanguage )
      goto LABEL_21;
    FWFreeFirewallRules(v23);
    v23 = 0;
    v15 = FWEnumFirewallRules((__int64)v19, 196608, 0x7FFFFFFF, 0, (__int64)&v22, (__int64)&v23);
    v9 = v15;
    if ( v15 > 0 )
      v9 = (unsigned __int16)v15 | 0x80070000;
    if ( v9 < 0 )
      goto LABEL_22;
    MatchingRuleWithLocRuleName = FwRule::FwFindMatchingRuleWithRuleName(v23, v22, a2, *((unsigned int *)this + 6));
    if ( !MatchingRuleWithLocRuleName )
    {
      MatchingRuleWithLocRuleName = FwRule::FwFindMatchingRuleWithLocRuleName(v23, v22, a2, *((unsigned int *)this + 6));
      if ( !MatchingRuleWithLocRuleName )
        goto LABEL_21;
    }
    v17 = FwRuleLookup(v19, *(const unsigned __int16 **)(MatchingRuleWithLocRuleName + 16), 0, &v20);
    v9 = v17;
    if ( v17 < 0 )
    {
      FwReportReturnError("FwRules::Item", (unsigned int)v17);
      v3 = v20;
      goto LABEL_14;
    }
    v3 = v20;
    MatchingRuleWithRuleName = v20;
    if ( !v20 )
    {
LABEL_21:
      v9 = -2147024894;
      goto LABEL_22;
    }
  }
  PolicyStoreHandle = FwRule::CreateInstance(*((unsigned int *)this + 6), MatchingRuleWithRuleName, &v21);
  v9 = PolicyStoreHandle;
  if ( PolicyStoreHandle < 0 )
    goto LABEL_12;
  *a3 = v21;
LABEL_14:
  FwBaseFree(v24);
  FWFreeFirewallRules(v23);
  FWFreeFirewallRules((__int64)v3);
  if ( v9 < 0 )
    return (unsigned int)FwReportReturnError("FwRules::Item", (unsigned int)v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180004680  mov     [rsp-28h+arg_18], rbx
0x180004685  push    rbp
0x180004686  push    rsi
0x180004687  push    rdi
0x180004688  push    r14
0x18000468a  push    r15
0x18000468c  mov     rbp, rsp
0x18000468f  sub     rsp, 70h
0x180004693  mov     rax, cs:__security_cookie
0x18000469a  xor     rax, rsp
0x18000469d  mov     [rbp+var_10], rax
0x1800046a1  xor     esi, esi
0x1800046a3  mov     [rbp+var_20], 0
0x1800046ab  mov     [rbp+var_38], rsi
0x1800046af  mov     r15, r8
0x1800046b2  mov     [rbp+var_28], esi
0x1800046b5  mov     rdi, rdx
0x1800046b8  mov     [rbp+var_40], rsi
0x1800046bc  mov     r14, rcx
0x1800046bf  mov     [rbp+var_30], rsi
0x1800046c3  mov     [rbp+var_18], rsi
0x1800046c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800046ce  lea     rbx, WPP_GLOBAL_Control
0x1800046d5  cmp     rcx, rbx
0x1800046d8  jnz     loc_18000492A
0x1800046de  test    r15, r15
0x1800046e1  jz      loc_18000497C
0x1800046e7  mov     rcx, rdi; pbstr
0x1800046ea  call    cs:__imp_SysStringLen
0x1800046f1  nop     dword ptr [rax+rax+00h]
0x1800046f6  test    eax, eax
0x1800046f8  jz      loc_180004986
0x1800046fe  cmp     word ptr [rdi], 40h ; '@'
0x180004702  jnz     loc_180004813
0x180004708  lea     rdx, [rbp+var_18]
0x18000470c  mov     rcx, rdi
0x18000470f  call    cs:__imp_FwLoadIndirectString
0x180004716  nop     dword ptr [rax+rax+00h]
0x18000471b  test    eax, eax
0x18000471d  js      loc_180004813
0x180004723  lea     rdx, [rbp+var_40]; void **
0x180004727  mov     [r15], rsi
0x18000472a  mov     rcx, r14; this
0x18000472d  call    ?GetPolicyStoreHandle@FwRules@@AEAAJPEAPEAX@Z; FwRules::GetPolicyStoreHandle(void * *)
0x180004732  mov     ebx, eax
0x180004734  test    eax, eax
0x180004736  js      short loc_1800047A9
0x180004738  mov     rcx, [rbp+var_40]
0x18000473c  lea     rax, [rbp+var_20]
0x180004740  mov     [rsp+70h+var_48], rax
0x180004745  mov     r9d, 7
0x18000474b  lea     rax, [rbp+var_28]
0x18000474f  mov     edx, 30000h
0x180004754  mov     r8d, 7FFFFFFFh
0x18000475a  mov     [rsp+70h+var_50], rax
0x18000475f  call    FWEnumFirewallRules
0x180004764  mov     ebx, eax
0x180004766  test    eax, eax
0x180004768  jg      loc_180004847
0x18000476e  test    ebx, ebx
0x180004770  js      loc_18000486A
0x180004776  mov     r9d, [r14+18h]
0x18000477a  mov     r8, [rbp+var_18]
0x18000477e  mov     edx, [rbp+var_28]
0x180004781  mov     rcx, [rbp+var_20]
0x180004785  call    ?FwFindMatchingRuleWithRuleName@FwRule@@SAPEAU_tag_FW_RULE@@QEAU2@KPEBGW4FwPolicyViewFlags@@@Z; FwRule::FwFindMatchingRuleWithRuleName(_tag_FW_RULE * const,ulong,ushort const *,FwPolicyViewFlags)
0x18000478a  test    rax, rax
0x18000478d  jz      loc_180004990
0x180004793  mov     ecx, [r14+18h]
0x180004797  lea     r8, [rbp+var_30]
0x18000479b  mov     rdx, rax
0x18000479e  call    ?CreateInstance@FwRule@@SAJW4FwPolicyViewFlags@@PEAU_tag_FW_RULE@@PEAPEAV1@@Z; FwRule::CreateInstance(FwPolicyViewFlags,_tag_FW_RULE *,FwRule * *)
0x1800047a3  mov     ebx, eax
0x1800047a5  test    eax, eax
0x1800047a7  jns     short loc_18000480A
0x1800047a9  mov     edx, eax
0x1800047ab  lea     rcx, aFwrulesItem; "FwRules::Item"
0x1800047b2  call    cs:__imp_FwReportReturnError
0x1800047b9  nop     dword ptr [rax+rax+00h]
0x1800047be  mov     rcx, [rbp+var_18]
0x1800047c2  call    cs:__imp_FwBaseFree
0x1800047c9  nop     dword ptr [rax+rax+00h]
0x1800047ce  mov     rcx, [rbp+var_20]
0x1800047d2  call    FWFreeFirewallRules
0x1800047d7  mov     rcx, rsi
0x1800047da  call    FWFreeFirewallRules
0x1800047df  test    ebx, ebx
0x1800047e1  js      loc_1800049B9
0x1800047e7  mov     eax, ebx
0x1800047e9  mov     rcx, [rbp+var_10]
0x1800047ed  xor     rcx, rsp; StackCookie
0x1800047f0  call    __security_check_cookie
0x1800047f5  mov     rbx, [rsp+70h+arg_18]
0x1800047fd  add     rsp, 70h
0x180004801  pop     r15
0x180004803  pop     r14
0x180004805  pop     rdi
0x180004806  pop     rsi
0x180004807  pop     rbp
0x180004808  retn
0x18000480a  mov     rax, [rbp+var_30]
0x18000480e  mov     [r15], rax
0x180004811  jmp     short loc_1800047BE
0x180004813  lea     rdx, [rbp+var_18]
0x180004817  mov     rcx, rdi
0x18000481a  call    cs:__imp_FwStringCopy
0x180004821  nop     dword ptr [rax+rax+00h]
0x180004826  mov     ebx, eax
0x180004828  test    eax, eax
0x18000482a  jns     loc_180004723
0x180004830  mov     edx, eax
0x180004832  lea     rcx, aFwtryresolvest; "FwTryResolveString"
0x180004839  call    cs:__imp_FwReportReturnError
0x180004840  nop     dword ptr [rax+rax+00h]
0x180004845  jmp     short loc_18000486A
0x180004847  movzx   ebx, ax
0x18000484a  or      ebx, 80070000h
0x180004850  jmp     loc_18000476E
0x180004855  mov     rsi, [rbp+var_38]
0x180004859  mov     rax, rsi
0x18000485c  test    rsi, rsi
0x18000485f  jnz     loc_180004793
0x180004865  mov     ebx, 80070002h
0x18000486a  mov     edx, ebx
0x18000486c  jmp     loc_1800047AB
0x180004871  mov     rcx, [rbp+var_20]
0x180004875  call    FWFreeFirewallRules
0x18000487a  mov     rcx, [rbp+var_40]
0x18000487e  lea     rax, [rbp+var_20]
0x180004882  mov     [rsp+70h+var_48], rax
0x180004887  xor     r9d, r9d
0x18000488a  lea     rax, [rbp+var_28]
0x18000488e  mov     [rbp+var_20], rsi
0x180004892  mov     edx, 30000h
0x180004897  mov     [rsp+70h+var_50], rax
0x18000489c  mov     r8d, 7FFFFFFFh
0x1800048a2  call    FWEnumFirewallRules
0x1800048a7  mov     ebx, eax
0x1800048a9  test    eax, eax
0x1800048ab  jle     short loc_1800048B6
0x1800048ad  movzx   ebx, ax
0x1800048b0  or      ebx, 80070000h
0x1800048b6  test    ebx, ebx
0x1800048b8  js      short loc_18000486A
0x1800048ba  mov     r9d, [r14+18h]
0x1800048be  mov     r8, rdi
0x1800048c1  mov     edx, [rbp+var_28]
0x1800048c4  mov     rcx, [rbp+var_20]
0x1800048c8  call    ?FwFindMatchingRuleWithRuleName@FwRule@@SAPEAU_tag_FW_RULE@@QEAU2@KPEBGW4FwPolicyViewFlags@@@Z; FwRule::FwFindMatchingRuleWithRuleName(_tag_FW_RULE * const,ulong,ushort const *,FwPolicyViewFlags)
0x1800048cd  test    rax, rax
0x1800048d0  jnz     short loc_1800048EE
0x1800048d2  mov     r9d, [r14+18h]
0x1800048d6  mov     r8, rdi
0x1800048d9  mov     edx, [rbp+var_28]
0x1800048dc  mov     rcx, [rbp+var_20]
0x1800048e0  call    ?FwFindMatchingRuleWithLocRuleName@FwRule@@SAPEAU_tag_FW_RULE@@QEAU2@KPEBGW4FwPolicyViewFlags@@@Z; FwRule::FwFindMatchingRuleWithLocRuleName(_tag_FW_RULE * const,ulong,ushort const *,FwPolicyViewFlags)
0x1800048e5  test    rax, rax
0x1800048e8  jz      loc_180004865
0x1800048ee  mov     rdx, [rax+10h]; unsigned __int16 *
0x1800048f2  lea     r9, [rbp+var_38]; struct _tag_FW_RULE **
0x1800048f6  mov     rcx, [rbp+var_40]; void *
0x1800048fa  xor     r8d, r8d; int
0x1800048fd  call    ?FwRuleLookup@@YAJPEAXPEBGHPEAPEAU_tag_FW_RULE@@@Z; FwRuleLookup(void *,ushort const *,int,_tag_FW_RULE * *)
0x180004902  mov     ebx, eax
0x180004904  test    eax, eax
0x180004906  jns     loc_180004855
0x18000490c  mov     edx, eax
0x18000490e  lea     rcx, aFwrulesItem; "FwRules::Item"
0x180004915  call    cs:__imp_FwReportReturnError
0x18000491c  nop     dword ptr [rax+rax+00h]
0x180004921  mov     rsi, [rbp+var_38]
0x180004925  jmp     loc_1800047BE
0x18000492a  test    byte ptr [rcx+1Ch], 8
0x18000492e  jz      short loc_18000494C
0x180004930  mov     rcx, [rcx+10h]
0x180004934  lea     r8, WPP_4cf7a87c86333f9f8c34ccce893540da_Traceguids
0x18000493b  mov     edx, 10h
0x180004940  call    WPP_SF_
0x180004945  mov     rcx, cs:WPP_GLOBAL_Control
0x18000494c  cmp     rcx, rbx
0x18000494f  jz      loc_1800046DE
0x180004955  test    byte ptr [rcx+1Ch], 4
0x180004959  jz      loc_1800046DE
0x18000495f  mov     rcx, [rcx+10h]
0x180004963  lea     r8, WPP_4cf7a87c86333f9f8c34ccce893540da_Traceguids
0x18000496a  mov     edx, 11h
0x18000496f  mov     r9, rdi
0x180004972  call    WPP_SF_S
0x180004977  jmp     loc_1800046DE
0x18000497c  mov     ebx, 80004003h
0x180004981  jmp     loc_18000486A
0x180004986  mov     ebx, 80070057h
0x18000498b  jmp     loc_18000486A
0x180004990  call    cs:__imp_GetThreadUILanguage
0x180004997  nop     dword ptr [rax+rax+00h]
0x18000499c  movzx   ebx, ax
0x18000499f  call    cs:__imp_GetSystemDefaultLangID
0x1800049a6  nop     dword ptr [rax+rax+00h]
0x1800049ab  cmp     ax, bx
0x1800049ae  jz      loc_180004865
0x1800049b4  jmp     loc_180004871
0x1800049b9  mov     edx, ebx
0x1800049bb  lea     rcx, aFwrulesItem; "FwRules::Item"
0x1800049c2  call    cs:__imp_FwReportReturnError
0x1800049c9  nop     dword ptr [rax+rax+00h]
0x1800049ce  mov     ebx, eax
0x1800049d0  jmp     loc_1800047E7
```
