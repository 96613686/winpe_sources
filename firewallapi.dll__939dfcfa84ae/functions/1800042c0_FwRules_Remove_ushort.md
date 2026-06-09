# FwRules::Remove(ushort *)

- ea: `0x1800042c0`
- end: `0x18000466c`
- name: `?Remove@FwRules@@UEAAJPEAG@Z`
- size: `940`
- prototype: `int(FwRules *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, registry_config`

## callees

- `0x1800042c0`
- `0x1800049e0`
- `0x180004ae8`
- `0x180005630`
- `0x180009780`
- `0x18000c3f0`
- `0x180010e50`
- `0x18001d578`
- `0x1800294b0`
- `0x18003336c`
- `0x18003a5bc`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetThreadUILanguage` at `0x1800044c8`
- `api-ms-win-core-localization-l1-2-0!GetThreadUILanguage` at `0x1800044c8`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLangID` at `0x1800044d7`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLangID` at `0x1800044d7`
- `OLEAUT32!__imp_SysStringLen` at `0x18000431e`
- `OLEAUT32!__imp_SysStringLen` at `0x18000431e`
- `fwbase!FwBaseFree` at `0x180004464`
- `fwbase!FwBaseFree` at `0x180004464`
- `fwbase!FwResolveIndirectString` at `0x18000435a`
- `fwbase!FwResolveIndirectString` at `0x18000435a`
- `fwbase!FwReportReturnError` at `0x180004456`
- `fwbase!FwReportReturnError` at `0x18000462f`
- `fwbase!FwReportReturnError` at `0x180004659`
- `fwbase!FwReportReturnError` at `0x180004456`
- `fwbase!FwReportReturnError` at `0x18000462f`
- `fwbase!FwReportReturnError` at `0x180004659`
- `fwbase!FwStringCopy` at `0x180004340`
- `fwbase!FwStringCopy` at `0x180004340`

## string_xrefs

- `0x18000432a`: `FwRules::Remove`
- `0x180004569`: `FwRules::Remove`
- `0x180004628`: `FwRules::Remove`
- `0x180004644`: `FwRules::Remove`
- `0x180004652`: `FwRules::Remove`

## pseudocode

```c
__int64 __fastcall FwRules::Remove(FwRules *this, unsigned __int16 *a2)
{
  struct _tag_FW_RULE *v2; // rsi
  FwPolicy2 *v5; // rcx
  int PolicyStoreHandle; // eax
  signed int v7; // edi
  int v8; // eax
  struct _tag_FW_RULE *MatchingRuleWithRuleName; // rax
  int v10; // eax
  __int64 v11; // rdx
  LANGID ThreadUILanguage; // bx
  int v14; // eax
  __int64 MatchingRuleWithLocRuleName; // rbx
  int v16; // eax
  void *v17; // [rsp+30h] [rbp-30h] BYREF
  struct _tag_FW_RULE *v18; // [rsp+38h] [rbp-28h] BYREF
  unsigned int v19; // [rsp+40h] [rbp-20h] BYREF
  __int64 v20; // [rsp+48h] [rbp-18h] BYREF
  __int64 v21; // [rsp+50h] [rbp-10h] BYREF

  v2 = 0;
  v20 = 0;
  v18 = 0;
  v21 = 0;
  v17 = 0;
  v19 = 0;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_4cf7a87c86333f9f8c34ccce893540da_Traceguids);
      v5 = WPP_GLOBAL_Control;
    }
    if ( v5 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 4) != 0 )
      WPP_SF_S(*((_QWORD *)v5 + 2), 13, WPP_4cf7a87c86333f9f8c34ccce893540da_Traceguids, a2);
  }
  if ( !SysStringLen(a2) )
  {
    v7 = -2147024809;
    goto LABEL_13;
  }
  PolicyStoreHandle = FwStringCopy(a2, &v21);
  v7 = PolicyStoreHandle;
  if ( PolicyStoreHandle < 0
    || (PolicyStoreHandle = FwResolveIndirectString(&v21), v7 = PolicyStoreHandle, PolicyStoreHandle < 0)
    || (PolicyStoreHandle = FwRules::GetPolicyStoreHandle(this, &v17), v7 = PolicyStoreHandle, PolicyStoreHandle < 0) )
  {
    v11 = (unsigned int)PolicyStoreHandle;
    goto LABEL_21;
  }
  v8 = FWEnumFirewallRules((_DWORD)v17, 196608, 0x7FFFFFFF, 7, (__int64)&v19, (__int64)&v20);
  v7 = v8;
  if ( v8 > 0 )
    v7 = (unsigned __int16)v8 | 0x80070000;
  if ( v7 < 0 )
  {
LABEL_13:
    v11 = (unsigned int)v7;
LABEL_21:
    FwReportReturnError("FwRules::Remove", v11);
    goto LABEL_15;
  }
  MatchingRuleWithRuleName = (struct _tag_FW_RULE *)FwRule::FwFindMatchingRuleWithRuleName(
                                                      v20,
                                                      v19,
                                                      v21,
                                                      *((unsigned int *)this + 6));
  if ( !MatchingRuleWithRuleName )
  {
    ThreadUILanguage = GetThreadUILanguage();
    if ( GetSystemDefaultLangID() == ThreadUILanguage )
      goto LABEL_15;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_4cf7a87c86333f9f8c34ccce893540da_Traceguids, v21);
    FWFreeFirewallRules(v20);
    v20 = 0;
    v14 = FWEnumFirewallRules((_DWORD)v17, 196608, 0x7FFFFFFF, 0, (__int64)&v19, (__int64)&v20);
    v7 = v14;
    if ( v14 > 0 )
      v7 = (unsigned __int16)v14 | 0x80070000;
    if ( v7 < 0 )
    {
      v11 = (unsigned int)v7;
      goto LABEL_21;
    }
    MatchingRuleWithLocRuleName = FwRule::FwFindMatchingRuleWithRuleName(v20, v19, a2, *((unsigned int *)this + 6));
    if ( !MatchingRuleWithLocRuleName )
    {
      MatchingRuleWithLocRuleName = FwRule::FwFindMatchingRuleWithLocRuleName(v20, v19, a2, *((unsigned int *)this + 6));
      if ( !MatchingRuleWithLocRuleName )
        goto LABEL_15;
    }
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_4cf7a87c86333f9f8c34ccce893540da_Traceguids);
    v16 = FwRuleLookup(v17, *(const unsigned __int16 **)(MatchingRuleWithLocRuleName + 16), 0, &v18);
    v7 = v16;
    if ( v16 < 0 )
    {
      FwReportReturnError("FwRules::Remove", (unsigned int)v16);
      v2 = v18;
      goto LABEL_15;
    }
    v2 = v18;
    MatchingRuleWithRuleName = v18;
    if ( !v18 )
      goto LABEL_15;
  }
  v10 = FWDeleteFirewallRule(v17, *((_QWORD *)MatchingRuleWithRuleName + 2));
  v7 = v10;
  if ( v10 > 0 )
    v7 = (unsigned __int16)v10 | 0x80070000;
  if ( v7 < 0 )
    goto LABEL_13;
LABEL_15:
  if ( v21 )
    FwBaseFree(v21);
  FWFreeFirewallRules(v20);
  FWFreeFirewallRules(v2);
  if ( v7 < 0 )
    return (unsigned int)FwReportReturnError("FwRules::Remove", (unsigned int)v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800042c0  mov     [rsp-28h+arg_10], rbx
0x1800042c5  push    rbp
0x1800042c6  push    rsi
0x1800042c7  push    rdi
0x1800042c8  push    r13
0x1800042ca  push    r14
0x1800042cc  mov     rbp, rsp
0x1800042cf  sub     rsp, 60h
0x1800042d3  mov     rax, cs:__security_cookie
0x1800042da  xor     rax, rsp
0x1800042dd  mov     [rbp+var_8], rax
0x1800042e1  xor     esi, esi
0x1800042e3  mov     [rbp+var_18], 0
0x1800042eb  mov     [rbp+var_28], rsi
0x1800042ef  mov     r14, rdx
0x1800042f2  mov     [rbp+var_10], rsi
0x1800042f6  mov     r13, rcx
0x1800042f9  mov     [rbp+var_30], rsi
0x1800042fd  mov     [rbp+var_20], 0
0x180004304  mov     rcx, cs:WPP_GLOBAL_Control
0x18000430b  lea     rbx, WPP_GLOBAL_Control
0x180004312  cmp     rcx, rbx
0x180004315  jnz     loc_180004480
0x18000431b  mov     rcx, r14; pbstr
0x18000431e  call    cs:__imp_SysStringLen
0x180004325  nop     dword ptr [rax+rax+00h]
0x18000432a  lea     rbx, aFwrulesRemove; "FwRules::Remove"
0x180004331  test    eax, eax
0x180004333  jz      loc_180004596
0x180004339  lea     rdx, [rbp+var_10]
0x18000433d  mov     rcx, r14
0x180004340  call    cs:__imp_FwStringCopy
0x180004347  nop     dword ptr [rax+rax+00h]
0x18000434c  mov     edi, eax
0x18000434e  test    eax, eax
0x180004350  js      loc_180004451
0x180004356  lea     rcx, [rbp+var_10]
0x18000435a  call    cs:__imp_FwResolveIndirectString
0x180004361  nop     dword ptr [rax+rax+00h]
0x180004366  mov     edi, eax
0x180004368  test    eax, eax
0x18000436a  js      loc_180004451
0x180004370  lea     rdx, [rbp+var_30]; void **
0x180004374  mov     rcx, r13; this
0x180004377  call    ?GetPolicyStoreHandle@FwRules@@AEAAJPEAPEAX@Z; FwRules::GetPolicyStoreHandle(void * *)
0x18000437c  mov     edi, eax
0x18000437e  test    eax, eax
0x180004380  js      loc_180004451
0x180004386  mov     rcx, [rbp+var_30]
0x18000438a  lea     rax, [rbp+var_18]
0x18000438e  mov     [rsp+60h+var_38], rax
0x180004393  mov     r9d, 7
0x180004399  lea     rax, [rbp+var_20]
0x18000439d  mov     edx, 30000h
0x1800043a2  mov     r8d, 7FFFFFFFh
0x1800043a8  mov     [rsp+60h+var_40], rax
0x1800043ad  call    FWEnumFirewallRules
0x1800043b2  mov     edi, eax
0x1800043b4  test    eax, eax
0x1800043b6  jg      loc_180004472
0x1800043bc  test    edi, edi
0x1800043be  js      short loc_1800043F8
0x1800043c0  mov     r9d, [r13+18h]
0x1800043c4  mov     r8, [rbp+var_10]
0x1800043c8  mov     edx, [rbp+var_20]
0x1800043cb  mov     rcx, [rbp+var_18]
0x1800043cf  call    ?FwFindMatchingRuleWithRuleName@FwRule@@SAPEAU_tag_FW_RULE@@QEAU2@KPEBGW4FwPolicyViewFlags@@@Z; FwRule::FwFindMatchingRuleWithRuleName(_tag_FW_RULE * const,ulong,ushort const *,FwPolicyViewFlags)
0x1800043d4  test    rax, rax
0x1800043d7  jz      loc_1800044C8
0x1800043dd  mov     rdx, [rax+10h]
0x1800043e1  mov     rcx, [rbp+var_30]
0x1800043e5  call    FWDeleteFirewallRule
0x1800043ea  mov     edi, eax
0x1800043ec  test    eax, eax
0x1800043ee  jg      loc_1800044BA
0x1800043f4  test    edi, edi
0x1800043f6  jns     short loc_18000440C
0x1800043f8  mov     edx, edi
0x1800043fa  jmp     short loc_180004453
0x1800043fc  mov     rsi, [rbp+var_28]
0x180004400  mov     rax, rsi
0x180004403  test    rsi, rsi
0x180004406  jnz     loc_180004644
0x18000440c  mov     rcx, [rbp+var_10]
0x180004410  test    rcx, rcx
0x180004413  jnz     short loc_180004464
0x180004415  mov     rcx, [rbp+var_18]
0x180004419  call    FWFreeFirewallRules
0x18000441e  mov     rcx, rsi
0x180004421  call    FWFreeFirewallRules
0x180004426  test    edi, edi
0x180004428  js      loc_180004650
0x18000442e  mov     eax, edi
0x180004430  mov     rcx, [rbp+var_8]
0x180004434  xor     rcx, rsp; StackCookie
0x180004437  call    __security_check_cookie
0x18000443c  mov     rbx, [rsp+60h+arg_10]
0x180004444  add     rsp, 60h
0x180004448  pop     r14
0x18000444a  pop     r13
0x18000444c  pop     rdi
0x18000444d  pop     rsi
0x18000444e  pop     rbp
0x18000444f  retn
0x180004451  mov     edx, eax
0x180004453  mov     rcx, rbx
0x180004456  call    cs:__imp_FwReportReturnError
0x18000445d  nop     dword ptr [rax+rax+00h]
0x180004462  jmp     short loc_18000440C
0x180004464  call    cs:__imp_FwBaseFree
0x18000446b  nop     dword ptr [rax+rax+00h]
0x180004470  jmp     short loc_180004415
0x180004472  movzx   edi, ax
0x180004475  or      edi, 80070000h
0x18000447b  jmp     loc_1800043BC
0x180004480  test    byte ptr [rcx+1Ch], 8
0x180004484  jnz     loc_180004575
0x18000448a  cmp     rcx, rbx
0x18000448d  jz      loc_18000431B
0x180004493  test    byte ptr [rcx+1Ch], 4
0x180004497  jz      loc_18000431B
0x18000449d  mov     rcx, [rcx+10h]
0x1800044a1  lea     r8, WPP_4cf7a87c86333f9f8c34ccce893540da_Traceguids
0x1800044a8  mov     edx, 0Dh
0x1800044ad  mov     r9, r14
0x1800044b0  call    WPP_SF_S
0x1800044b5  jmp     loc_18000431B
0x1800044ba  movzx   edi, ax
0x1800044bd  or      edi, 80070000h
0x1800044c3  jmp     loc_1800043F4
0x1800044c8  call    cs:__imp_GetThreadUILanguage
0x1800044cf  nop     dword ptr [rax+rax+00h]
0x1800044d4  movzx   ebx, ax
0x1800044d7  call    cs:__imp_GetSystemDefaultLangID
0x1800044de  nop     dword ptr [rax+rax+00h]
0x1800044e3  cmp     ax, bx
0x1800044e6  jz      loc_18000440C
0x1800044ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800044f3  lea     rax, WPP_GLOBAL_Control
0x1800044fa  cmp     rcx, rax
0x1800044fd  jz      short loc_18000451E
0x1800044ff  test    byte ptr [rcx+1Ch], 4
0x180004503  jz      short loc_18000451E
0x180004505  mov     r9, [rbp+var_10]
0x180004509  lea     r8, WPP_4cf7a87c86333f9f8c34ccce893540da_Traceguids
0x180004510  mov     rcx, [rcx+10h]
0x180004514  mov     edx, 0Eh
0x180004519  call    WPP_SF_S
0x18000451e  mov     rcx, [rbp+var_18]
0x180004522  call    FWFreeFirewallRules
0x180004527  mov     rcx, [rbp+var_30]
0x18000452b  lea     rax, [rbp+var_18]
0x18000452f  mov     [rsp+60h+var_38], rax
0x180004534  xor     r9d, r9d
0x180004537  lea     rax, [rbp+var_20]
0x18000453b  mov     [rbp+var_18], rsi
0x18000453f  mov     edx, 30000h
0x180004544  mov     [rsp+60h+var_40], rax
0x180004549  mov     r8d, 7FFFFFFFh
0x18000454f  call    FWEnumFirewallRules
0x180004554  mov     edi, eax
0x180004556  test    eax, eax
0x180004558  jle     short loc_180004563
0x18000455a  movzx   edi, ax
0x18000455d  or      edi, 80070000h
0x180004563  test    edi, edi
0x180004565  jns     short loc_1800045A0
0x180004567  mov     edx, edi
0x180004569  lea     rcx, aFwrulesRemove; "FwRules::Remove"
0x180004570  jmp     loc_180004456
0x180004575  mov     rcx, [rcx+10h]
0x180004579  lea     r8, WPP_4cf7a87c86333f9f8c34ccce893540da_Traceguids
0x180004580  mov     edx, 0Ch
0x180004585  call    WPP_SF_
0x18000458a  mov     rcx, cs:WPP_GLOBAL_Control
0x180004591  jmp     loc_18000448A
0x180004596  mov     edi, 80070057h
0x18000459b  jmp     loc_1800043F8
0x1800045a0  mov     r9d, [r13+18h]
0x1800045a4  mov     r8, r14
0x1800045a7  mov     edx, [rbp+var_20]
0x1800045aa  mov     rcx, [rbp+var_18]
0x1800045ae  call    ?FwFindMatchingRuleWithRuleName@FwRule@@SAPEAU_tag_FW_RULE@@QEAU2@KPEBGW4FwPolicyViewFlags@@@Z; FwRule::FwFindMatchingRuleWithRuleName(_tag_FW_RULE * const,ulong,ushort const *,FwPolicyViewFlags)
0x1800045b3  mov     rbx, rax
0x1800045b6  test    rax, rax
0x1800045b9  jnz     short loc_1800045DA
0x1800045bb  mov     r9d, [r13+18h]
0x1800045bf  mov     r8, r14
0x1800045c2  mov     edx, [rbp+var_20]
0x1800045c5  mov     rcx, [rbp+var_18]
0x1800045c9  call    ?FwFindMatchingRuleWithLocRuleName@FwRule@@SAPEAU_tag_FW_RULE@@QEAU2@KPEBGW4FwPolicyViewFlags@@@Z; FwRule::FwFindMatchingRuleWithLocRuleName(_tag_FW_RULE * const,ulong,ushort const *,FwPolicyViewFlags)
0x1800045ce  mov     rbx, rax
0x1800045d1  test    rax, rax
0x1800045d4  jz      loc_18000440C
0x1800045da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800045e1  lea     rax, WPP_GLOBAL_Control
0x1800045e8  cmp     rcx, rax
0x1800045eb  jz      short loc_180004608
0x1800045ed  test    byte ptr [rcx+1Ch], 4
0x1800045f1  jz      short loc_180004608
0x1800045f3  mov     rcx, [rcx+10h]
0x1800045f7  lea     r8, WPP_4cf7a87c86333f9f8c34ccce893540da_Traceguids
0x1800045fe  mov     edx, 0Fh
0x180004603  call    WPP_SF_
0x180004608  mov     rdx, [rbx+10h]; unsigned __int16 *
0x18000460c  lea     r9, [rbp+var_28]; struct _tag_FW_RULE **
0x180004610  mov     rcx, [rbp+var_30]; void *
0x180004614  xor     r8d, r8d; int
0x180004617  call    ?FwRuleLookup@@YAJPEAXPEBGHPEAPEAU_tag_FW_RULE@@@Z; FwRuleLookup(void *,ushort const *,int,_tag_FW_RULE * *)
0x18000461c  mov     edi, eax
0x18000461e  test    eax, eax
0x180004620  jns     loc_1800043FC
0x180004626  mov     edx, eax
0x180004628  lea     rcx, aFwrulesRemove; "FwRules::Remove"
0x18000462f  call    cs:__imp_FwReportReturnError
0x180004636  nop     dword ptr [rax+rax+00h]
0x18000463b  mov     rsi, [rbp+var_28]
0x18000463f  jmp     loc_18000440C
0x180004644  lea     rbx, aFwrulesRemove; "FwRules::Remove"
0x18000464b  jmp     loc_1800043DD
0x180004650  mov     edx, edi
0x180004652  lea     rcx, aFwrulesRemove; "FwRules::Remove"
0x180004659  call    cs:__imp_FwReportReturnError
0x180004660  nop     dword ptr [rax+rax+00h]
0x180004665  mov     edi, eax
0x180004667  jmp     loc_18000442E
```
