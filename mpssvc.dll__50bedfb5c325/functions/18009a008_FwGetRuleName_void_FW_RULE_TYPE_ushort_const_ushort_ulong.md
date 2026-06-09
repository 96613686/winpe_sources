# FwGetRuleName(void *,FW_RULE_TYPE,ushort const *,ushort * *,ulong *)

- ea: `0x18009a008`
- end: `0x18009a1d8`
- name: `?FwGetRuleName@@YAJPEAXW4FW_RULE_TYPE@@PEBGPEAPEAGPEAK@Z`
- size: `464`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18009e988`
- `0x18009f98c`

## callees

- `0x1800729c0`
- `0x18008ba34`
- `0x18009a008`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009a0c6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009a122`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009a0c6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009a122`
- `fwbase!FwResolveIndirectString` at `0x18009a0ed`
- `fwbase!FwResolveIndirectString` at `0x18009a161`
- `fwbase!FwResolveIndirectString` at `0x18009a0ed`
- `fwbase!FwResolveIndirectString` at `0x18009a161`
- `fwbase!FwStringCopy` at `0x18009a0ff`
- `fwbase!FwStringCopy` at `0x18009a173`
- `fwbase!FwStringCopy` at `0x18009a0ff`
- `fwbase!FwStringCopy` at `0x18009a173`
- `fwbase!FwReportReturnError` at `0x18009a087`
- `fwbase!FwReportReturnError` at `0x18009a1a9`
- `fwbase!FwReportReturnError` at `0x18009a087`
- `fwbase!FwReportReturnError` at `0x18009a1a9`
- `FWPolicyIOMgr!FwFreeRules` at `0x18009a190`
- `FWPolicyIOMgr!FwFreeRules` at `0x18009a190`
- `FWPolicyIOMgr!FwEnumRules` at `0x18009a06c`
- `FWPolicyIOMgr!FwEnumRules` at `0x18009a06c`

## pseudocode

```c
__int64 __fastcall FwGetRuleName(__int64 a1, __int64 a2, __int64 a3, __int64 a4, _DWORD *a5)
{
  unsigned int v7; // r14d
  int v8; // eax
  int v9; // edi
  unsigned int v10; // edx
  int v11; // esi
  __int64 *v12; // rbx
  int v13; // ebp
  __int64 *v15; // [rsp+40h] [rbp-68h] BYREF
  unsigned int v16; // [rsp+48h] [rbp-60h] BYREF

  v7 = a2;
  v15 = 0;
  v16 = 0;
  v8 = FwEnumRules(a1, a2, &v15, &v16, 196608, 0x7FFFFFFF, 0);
  v9 = v8;
  if ( v8 < 0 )
  {
    FwReportReturnError("FwGetRuleName", (unsigned int)v8);
    goto LABEL_18;
  }
  v10 = v16;
  v11 = 0;
  v12 = v15;
  v13 = 0;
  if ( v16 )
  {
    while ( v7 )
    {
      if ( v7 - 1 <= 1 )
      {
        if ( !(unsigned int)_o__wcsicmp(v12[2], a3) )
        {
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load>::GetImpl'::`2'::impl) )
            FwResolveIndirectString(v12 + 3);
          v9 = FwStringCopy(v12[3], a4);
          v11 = 1;
          *a5 = *((_DWORD *)v12 + 10);
        }
LABEL_11:
        if ( v11 == 1 )
          goto LABEL_18;
        v10 = v16;
      }
      v12 = (__int64 *)*v12;
      if ( ++v13 >= v10 )
        goto LABEL_18;
    }
    if ( !(unsigned int)_o__wcsicmp(v12[2], a3) )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load>::GetImpl'::`2'::impl) )
        FwResolveIndirectString(v12 + 3);
      v9 = FwStringCopy(v12[3], a4);
      *a5 = *((_DWORD *)v12 + 10);
      goto LABEL_18;
    }
    goto LABEL_11;
  }
LABEL_18:
  FwFreeRules(v15, v7);
  if ( v9 < 0 )
    return (unsigned int)FwReportReturnError("FwGetRuleName", (unsigned int)v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18009a008  push    rbx
0x18009a00a  push    rbp
0x18009a00b  push    rsi
0x18009a00c  push    rdi
0x18009a00d  push    r12
0x18009a00f  push    r13
0x18009a011  push    r14
0x18009a013  push    r15
0x18009a015  sub     rsp, 68h
0x18009a019  mov     rax, cs:__security_cookie
0x18009a020  xor     rax, rsp
0x18009a023  mov     [rsp+0A8h+var_58], rax
0x18009a028  mov     r13, [rsp+0A8h+arg_20]
0x18009a030  mov     r12, r9
0x18009a033  mov     r15, r8
0x18009a036  mov     [rsp+0A8h+var_78], 0
0x18009a03e  mov     [rsp+0A8h+var_80], 7FFFFFFFh
0x18009a046  lea     r9, [rsp+0A8h+var_60]
0x18009a04b  lea     r8, [rsp+0A8h+var_68]
0x18009a050  mov     [rsp+0A8h+var_88], 30000h
0x18009a058  mov     r14d, edx
0x18009a05b  mov     [rsp+0A8h+var_68], 0
0x18009a064  mov     [rsp+0A8h+var_60], 0
0x18009a06c  call    cs:__imp_FwEnumRules
0x18009a073  nop     dword ptr [rax+rax+00h]
0x18009a078  mov     edi, eax
0x18009a07a  test    eax, eax
0x18009a07c  jns     short loc_18009A098
0x18009a07e  mov     edx, eax
0x18009a080  lea     rcx, aFwgetrulename; "FwGetRuleName"
0x18009a087  call    cs:__imp_FwReportReturnError
0x18009a08e  nop     dword ptr [rax+rax+00h]
0x18009a093  jmp     loc_18009A188
0x18009a098  mov     edx, [rsp+0A8h+var_60]
0x18009a09c  xor     esi, esi
0x18009a09e  mov     rbx, [rsp+0A8h+var_68]
0x18009a0a3  xor     ebp, ebp
0x18009a0a5  test    edx, edx
0x18009a0a7  jz      loc_18009A188
0x18009a0ad  mov     ecx, r14d
0x18009a0b0  test    r14d, r14d
0x18009a0b3  jz      short loc_18009A11B
0x18009a0b5  sub     ecx, 1
0x18009a0b8  jz      short loc_18009A0BF
0x18009a0ba  cmp     ecx, 1
0x18009a0bd  jnz     short loc_18009A13B
0x18009a0bf  mov     rcx, [rbx+10h]
0x18009a0c3  mov     rdx, r15
0x18009a0c6  call    cs:__imp__o__wcsicmp
0x18009a0cd  nop     dword ptr [rax+rax+00h]
0x18009a0d2  test    eax, eax
0x18009a0d4  jnz     short loc_18009A132
0x18009a0d6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load> `wil::Feature<__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load>::GetImpl(void)'::`2'::impl
0x18009a0dd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load>::__private_IsEnabled(void)
0x18009a0e2  lea     rdi, [rbx+18h]
0x18009a0e6  test    al, al
0x18009a0e8  jz      short loc_18009A0F9
0x18009a0ea  mov     rcx, rdi
0x18009a0ed  call    cs:__imp_FwResolveIndirectString
0x18009a0f4  nop     dword ptr [rax+rax+00h]
0x18009a0f9  mov     rcx, [rdi]
0x18009a0fc  mov     rdx, r12
0x18009a0ff  call    cs:__imp_FwStringCopy
0x18009a106  nop     dword ptr [rax+rax+00h]
0x18009a10b  mov     edi, eax
0x18009a10d  mov     esi, 1
0x18009a112  mov     eax, [rbx+28h]
0x18009a115  mov     [r13+0], eax
0x18009a119  jmp     short loc_18009A132
0x18009a11b  mov     rcx, [rbx+10h]
0x18009a11f  mov     rdx, r15
0x18009a122  call    cs:__imp__o__wcsicmp
0x18009a129  nop     dword ptr [rax+rax+00h]
0x18009a12e  test    eax, eax
0x18009a130  jz      short loc_18009A14A
0x18009a132  cmp     esi, 1
0x18009a135  jz      short loc_18009A188
0x18009a137  mov     edx, [rsp+0A8h+var_60]
0x18009a13b  mov     rbx, [rbx]
0x18009a13e  inc     ebp
0x18009a140  cmp     ebp, edx
0x18009a142  jb      loc_18009A0AD
0x18009a148  jmp     short loc_18009A188
0x18009a14a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load> `wil::Feature<__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load>::GetImpl(void)'::`2'::impl
0x18009a151  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_BugFixes_25D_Indirect_Strings_Delay_Load>::__private_IsEnabled(void)
0x18009a156  lea     rdi, [rbx+18h]
0x18009a15a  test    al, al
0x18009a15c  jz      short loc_18009A16D
0x18009a15e  mov     rcx, rdi
0x18009a161  call    cs:__imp_FwResolveIndirectString
0x18009a168  nop     dword ptr [rax+rax+00h]
0x18009a16d  mov     rcx, [rdi]
0x18009a170  mov     rdx, r12
0x18009a173  call    cs:__imp_FwStringCopy
0x18009a17a  nop     dword ptr [rax+rax+00h]
0x18009a17f  mov     edi, eax
0x18009a181  mov     eax, [rbx+28h]
0x18009a184  mov     [r13+0], eax
0x18009a188  mov     rcx, [rsp+0A8h+var_68]
0x18009a18d  mov     edx, r14d
0x18009a190  call    cs:__imp_FwFreeRules
0x18009a197  nop     dword ptr [rax+rax+00h]
0x18009a19c  test    edi, edi
0x18009a19e  jns     short loc_18009A1B7
0x18009a1a0  mov     edx, edi
0x18009a1a2  lea     rcx, aFwgetrulename; "FwGetRuleName"
0x18009a1a9  call    cs:__imp_FwReportReturnError
0x18009a1b0  nop     dword ptr [rax+rax+00h]
0x18009a1b5  mov     edi, eax
0x18009a1b7  mov     eax, edi
0x18009a1b9  mov     rcx, [rsp+0A8h+var_58]
0x18009a1be  xor     rcx, rsp; StackCookie
0x18009a1c1  call    __security_check_cookie
0x18009a1c6  add     rsp, 68h
0x18009a1ca  pop     r15
0x18009a1cc  pop     r14
0x18009a1ce  pop     r13
0x18009a1d0  pop     r12
0x18009a1d2  pop     rdi
0x18009a1d3  pop     rsi
0x18009a1d4  pop     rbp
0x18009a1d5  pop     rbx
0x18009a1d6  retn
```
