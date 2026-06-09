# FwGetRuleName(void *,FW_RULE_TYPE,ushort const *,ushort * *,ulong *)

- ea: `0x180095170`
- end: `0x1800952ff`
- name: `?FwGetRuleName@@YAJPEAXW4FW_RULE_TYPE@@PEBGPEAPEAGPEAK@Z`
- size: `399`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180099770`
- `0x18009a6a0`

## callees

- `0x18006f520`
- `0x1800873dc`
- `0x180095170`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180095222`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009526c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180095222`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009526c`
- `fwbase!FwResolveIndirectString` at `0x180095243`
- `fwbase!FwResolveIndirectString` at `0x1800952a1`
- `fwbase!FwResolveIndirectString` at `0x180095243`
- `fwbase!FwResolveIndirectString` at `0x1800952a1`
- `fwbase!FwStringCopy` at `0x18009524f`
- `fwbase!FwStringCopy` at `0x1800952ad`
- `fwbase!FwStringCopy` at `0x18009524f`
- `fwbase!FwStringCopy` at `0x1800952ad`
- `fwbase!FwReportReturnError` at `0x1800951e9`
- `fwbase!FwReportReturnError` at `0x1800952d7`
- `fwbase!FwReportReturnError` at `0x1800951e9`
- `fwbase!FwReportReturnError` at `0x1800952d7`
- `FWPolicyIOMgr!FwFreeRules` at `0x1800952c4`
- `FWPolicyIOMgr!FwFreeRules` at `0x1800952c4`
- `FWPolicyIOMgr!FwEnumRules` at `0x1800951d4`
- `FWPolicyIOMgr!FwEnumRules` at `0x1800951d4`

## pseudocode

```c
__int64 __fastcall FwGetRuleName(__int64 a1, __int64 a2, __int64 a3, __int64 a4, _DWORD *a5)
{
  unsigned int v7; // r14d
  int v8; // eax
  __int64 v9; // r8
  int v10; // edi
  unsigned int v11; // edx
  int v12; // esi
  __int64 *v13; // rbx
  int v14; // ebp
  __int64 v15; // r8
  __int64 *v17; // [rsp+40h] [rbp-68h] BYREF
  unsigned int v18; // [rsp+48h] [rbp-60h] BYREF

  v7 = a2;
  v17 = 0;
  v18 = 0;
  v8 = FwEnumRules(a1, a2, &v17, &v18, 196608, 0x7FFFFFFF, 0);
  v10 = v8;
  if ( v8 < 0 )
  {
    FwReportReturnError("FwGetRuleName", (unsigned int)v8, v9);
    goto LABEL_18;
  }
  v11 = v18;
  v12 = 0;
  v13 = v17;
  v14 = 0;
  if ( v18 )
  {
    while ( v7 )
    {
      if ( v7 - 1 <= 1 )
      {
        if ( !(unsigned int)_o__wcsicmp(v13[2], a3) )
        {
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load>::GetImpl'::`2'::impl) )
            FwResolveIndirectString(v13 + 3);
          v10 = FwStringCopy(v13[3], a4);
          v12 = 1;
          *a5 = *((_DWORD *)v13 + 10);
        }
LABEL_11:
        if ( v12 == 1 )
          goto LABEL_18;
        v11 = v18;
      }
      v13 = (__int64 *)*v13;
      if ( ++v14 >= v11 )
        goto LABEL_18;
    }
    if ( !(unsigned int)_o__wcsicmp(v13[2], a3) )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load>::GetImpl'::`2'::impl) )
        FwResolveIndirectString(v13 + 3);
      v10 = FwStringCopy(v13[3], a4);
      *a5 = *((_DWORD *)v13 + 10);
      goto LABEL_18;
    }
    goto LABEL_11;
  }
LABEL_18:
  FwFreeRules(v17, v7);
  if ( v10 < 0 )
    return (unsigned int)FwReportReturnError("FwGetRuleName", (unsigned int)v10, v15);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180095170  push    rbx
0x180095172  push    rbp
0x180095173  push    rsi
0x180095174  push    rdi
0x180095175  push    r12
0x180095177  push    r13
0x180095179  push    r14
0x18009517b  push    r15
0x18009517d  sub     rsp, 68h
0x180095181  mov     rax, cs:__security_cookie
0x180095188  xor     rax, rsp
0x18009518b  mov     [rsp+0A8h+var_58], rax
0x180095190  mov     r13, [rsp+0A8h+arg_20]
0x180095198  mov     r12, r9
0x18009519b  mov     r15, r8
0x18009519e  mov     [rsp+0A8h+var_78], 0
0x1800951a6  mov     [rsp+0A8h+var_80], 7FFFFFFFh
0x1800951ae  lea     r9, [rsp+0A8h+var_60]
0x1800951b3  lea     r8, [rsp+0A8h+var_68]
0x1800951b8  mov     [rsp+0A8h+var_88], 30000h
0x1800951c0  mov     r14d, edx
0x1800951c3  mov     [rsp+0A8h+var_68], 0
0x1800951cc  mov     [rsp+0A8h+var_60], 0
0x1800951d4  call    cs:__imp_FwEnumRules
0x1800951da  mov     edi, eax
0x1800951dc  test    eax, eax
0x1800951de  jns     short loc_1800951F4
0x1800951e0  mov     edx, eax
0x1800951e2  lea     rcx, aFwgetrulename; "FwGetRuleName"
0x1800951e9  call    cs:__imp_FwReportReturnError
0x1800951ef  jmp     loc_1800952BC
0x1800951f4  mov     edx, [rsp+0A8h+var_60]
0x1800951f8  xor     esi, esi
0x1800951fa  mov     rbx, [rsp+0A8h+var_68]
0x1800951ff  xor     ebp, ebp
0x180095201  test    edx, edx
0x180095203  jz      loc_1800952BC
0x180095209  mov     ecx, r14d
0x18009520c  test    r14d, r14d
0x18009520f  jz      short loc_180095265
0x180095211  sub     ecx, 1
0x180095214  jz      short loc_18009521B
0x180095216  cmp     ecx, 1
0x180095219  jnz     short loc_18009527F
0x18009521b  mov     rcx, [rbx+10h]
0x18009521f  mov     rdx, r15
0x180095222  call    cs:__imp__o__wcsicmp
0x180095228  test    eax, eax
0x18009522a  jnz     short loc_180095276
0x18009522c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load> `wil::Feature<__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load>::GetImpl(void)'::`2'::impl
0x180095233  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load>::__private_IsEnabled(void)
0x180095238  lea     rdi, [rbx+18h]
0x18009523c  test    al, al
0x18009523e  jz      short loc_180095249
0x180095240  mov     rcx, rdi
0x180095243  call    cs:__imp_FwResolveIndirectString
0x180095249  mov     rcx, [rdi]
0x18009524c  mov     rdx, r12
0x18009524f  call    cs:__imp_FwStringCopy
0x180095255  mov     edi, eax
0x180095257  mov     esi, 1
0x18009525c  mov     eax, [rbx+28h]
0x18009525f  mov     [r13+0], eax
0x180095263  jmp     short loc_180095276
0x180095265  mov     rcx, [rbx+10h]
0x180095269  mov     rdx, r15
0x18009526c  call    cs:__imp__o__wcsicmp
0x180095272  test    eax, eax
0x180095274  jz      short loc_18009528A
0x180095276  cmp     esi, 1
0x180095279  jz      short loc_1800952BC
0x18009527b  mov     edx, [rsp+0A8h+var_60]
0x18009527f  mov     rbx, [rbx]
0x180095282  inc     ebp
0x180095284  cmp     ebp, edx
0x180095286  jb      short loc_180095209
0x180095288  jmp     short loc_1800952BC
0x18009528a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load> `wil::Feature<__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load>::GetImpl(void)'::`2'::impl
0x180095291  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load>::__private_IsEnabled(void)
0x180095296  lea     rdi, [rbx+18h]
0x18009529a  test    al, al
0x18009529c  jz      short loc_1800952A7
0x18009529e  mov     rcx, rdi
0x1800952a1  call    cs:__imp_FwResolveIndirectString
0x1800952a7  mov     rcx, [rdi]
0x1800952aa  mov     rdx, r12
0x1800952ad  call    cs:__imp_FwStringCopy
0x1800952b3  mov     edi, eax
0x1800952b5  mov     eax, [rbx+28h]
0x1800952b8  mov     [r13+0], eax
0x1800952bc  mov     rcx, [rsp+0A8h+var_68]
0x1800952c1  mov     edx, r14d
0x1800952c4  call    cs:__imp_FwFreeRules
0x1800952ca  test    edi, edi
0x1800952cc  jns     short loc_1800952DF
0x1800952ce  mov     edx, edi
0x1800952d0  lea     rcx, aFwgetrulename; "FwGetRuleName"
0x1800952d7  call    cs:__imp_FwReportReturnError
0x1800952dd  mov     edi, eax
0x1800952df  mov     eax, edi
0x1800952e1  mov     rcx, [rsp+0A8h+var_58]
0x1800952e6  xor     rcx, rsp; StackCookie
0x1800952e9  call    __security_check_cookie
0x1800952ee  add     rsp, 68h
0x1800952f2  pop     r15
0x1800952f4  pop     r14
0x1800952f6  pop     r13
0x1800952f8  pop     r12
0x1800952fa  pop     rdi
0x1800952fb  pop     rsi
0x1800952fc  pop     rbp
0x1800952fd  pop     rbx
0x1800952fe  retn
```
