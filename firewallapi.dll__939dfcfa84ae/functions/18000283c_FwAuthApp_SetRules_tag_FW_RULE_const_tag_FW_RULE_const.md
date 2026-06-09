# FwAuthApp::SetRules(_tag_FW_RULE const *,_tag_FW_RULE const *)

- ea: `0x18000283c`
- end: `0x180002b6d`
- name: `?SetRules@FwAuthApp@@AEAAJPEBU_tag_FW_RULE@@0@Z`
- size: `817`
- prototype: `__int64 __fastcall(FwAuthApp *__hidden this, const struct _tag_FW_RULE *, const struct _tag_FW_RULE *)`
- caller_count: `6`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x1800018e0`
- `0x180001b40`
- `0x1800256f4`
- `0x1800441d0`
- `0x180044490`
- `0x180044760`

## callees

- `0x18000283c`
- `0x1800037dc`
- `0x180003e5c`
- `0x18000d0f0`
- `0x1800143d8`
- `0x180025870`
- `0x1800294b0`
- `0x180030468`
- `0x180032840`
- `0x18003336c`

## import_xrefs

- `fwbase!FwBaseFree` at `0x180002964`
- `fwbase!FwBaseFree` at `0x1800029d1`
- `fwbase!FwBaseFree` at `0x180002b27`
- `fwbase!FwBaseFree` at `0x180002964`
- `fwbase!FwBaseFree` at `0x1800029d1`
- `fwbase!FwBaseFree` at `0x180002b27`
- `fwbase!FwGetExpandedCanonicalLongPathName` at `0x180002a20`
- `fwbase!FwGetExpandedCanonicalLongPathName` at `0x180002a20`
- `fwbase!FwReportReturnError` at `0x180002a74`
- `fwbase!FwReportReturnError` at `0x180002b45`
- `fwbase!FwReportReturnError` at `0x180002a74`
- `fwbase!FwReportReturnError` at `0x180002b45`
- `fwbase!FwStringCopy` at `0x180002980`
- `fwbase!FwStringCopy` at `0x1800029ed`
- `fwbase!FwStringCopy` at `0x180002980`
- `fwbase!FwStringCopy` at `0x1800029ed`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x180002a84`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x180002a94`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x180002ae7`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x180002af7`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x180002a84`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x180002a94`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x180002ae7`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x180002af7`
- `FWPolicyIOMgr!FwCopyRule` at `0x18000288f`
- `FWPolicyIOMgr!FwCopyRule` at `0x1800028b3`
- `FWPolicyIOMgr!FwCopyRule` at `0x18000288f`
- `FWPolicyIOMgr!FwCopyRule` at `0x1800028b3`

## pseudocode

```c
__int64 __fastcall FwAuthApp::SetRules(FwAuthApp *this, const struct _tag_FW_RULE *a2, const struct _tag_FW_RULE *a3)
{
  int ExpandedCanonicalLongPathName; // eax
  signed int v6; // ebx
  FwAuthApp *v7; // rcx
  FwAuthApp *v8; // rcx
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // rdx
  struct _tag_FW_RULE *v14; // [rsp+30h] [rbp-30h] BYREF
  struct _tag_FW_RULE *v15; // [rsp+38h] [rbp-28h] BYREF
  void *v16; // [rsp+40h] [rbp-20h] BYREF
  __int64 v17; // [rsp+48h] [rbp-18h] BYREF
  int v18; // [rsp+50h] [rbp-10h] BYREF

  v14 = 0;
  v15 = 0;
  v17 = 0;
  v18 = 0;
  v16 = 0;
  ExpandedCanonicalLongPathName = FwCopyRule(a2, &v14);
  v6 = ExpandedCanonicalLongPathName;
  if ( ExpandedCanonicalLongPathName < 0 )
    goto LABEL_23;
  ExpandedCanonicalLongPathName = FwCopyRule(a3, &v15);
  v6 = ExpandedCanonicalLongPathName;
  if ( ExpandedCanonicalLongPathName < 0 )
    goto LABEL_23;
  if ( !*((_DWORD *)this + 22) )
    goto LABEL_30;
  ExpandedCanonicalLongPathName = FwAuthApp::ValidateAuthAppRule(v7, v14);
  v6 = ExpandedCanonicalLongPathName;
  if ( ExpandedCanonicalLongPathName < 0 )
    goto LABEL_23;
  ExpandedCanonicalLongPathName = FwAuthApp::ValidateAuthAppRule(v8, v15);
  v6 = ExpandedCanonicalLongPathName;
  if ( ExpandedCanonicalLongPathName < 0 )
    goto LABEL_23;
  v9 = FWOpenPolicyStore(0x221u, 0, 2u, 2u, 0, &v16);
  v6 = v9;
  if ( v9 > 0 )
    v6 = (unsigned __int16)v9 | 0x80070000;
  if ( v6 >= 0 )
  {
    v11 = *((_QWORD *)this + 9);
    if ( (~*((_DWORD *)this + 16) & *(_DWORD *)(v11 + 40)) != 0 )
    {
      ExpandedCanonicalLongPathName = FwSplitRule(v16, (struct _tag_FW_RULE *)v11, *((_DWORD *)this + 16));
      v6 = ExpandedCanonicalLongPathName;
      if ( ExpandedCanonicalLongPathName < 0 )
        goto LABEL_23;
      FwBaseFree(*((_QWORD *)v14 + 2));
      ExpandedCanonicalLongPathName = FwStringCopy(*(_QWORD *)(*((_QWORD *)this + 9) + 16LL), (char *)v14 + 16);
      v6 = ExpandedCanonicalLongPathName;
      if ( ExpandedCanonicalLongPathName < 0 )
        goto LABEL_23;
      *((_DWORD *)v14 + 10) = *(_DWORD *)(*((_QWORD *)this + 9) + 40LL);
    }
    v12 = *((_QWORD *)this + 10);
    if ( (~*((_DWORD *)this + 16) & *(_DWORD *)(v12 + 40)) == 0 )
    {
LABEL_18:
      ExpandedCanonicalLongPathName = FwGetExpandedCanonicalLongPathName(*((_QWORD *)v14 + 34), &v17, &v18);
      v6 = ExpandedCanonicalLongPathName;
      if ( ExpandedCanonicalLongPathName < 0 )
        goto LABEL_23;
      if ( v18 == 1 )
        DeleteAllMatchingAuthAppRules(v16, v17, *((unsigned int *)this + 16));
      ExpandedCanonicalLongPathName = SaveRule(v14, v16);
      v6 = ExpandedCanonicalLongPathName;
      if ( ExpandedCanonicalLongPathName < 0 )
        goto LABEL_23;
      ExpandedCanonicalLongPathName = SaveRule(v15, v16);
      v6 = ExpandedCanonicalLongPathName;
      if ( ExpandedCanonicalLongPathName < 0 )
        goto LABEL_23;
LABEL_30:
      FwFreeWFRule(*((_QWORD *)this + 9));
      FwFreeWFRule(*((_QWORD *)this + 10));
      *((_QWORD *)this + 9) = v14;
      *((_QWORD *)this + 10) = v15;
      v14 = 0;
      v15 = 0;
      goto LABEL_31;
    }
    ExpandedCanonicalLongPathName = FwSplitRule(v16, (struct _tag_FW_RULE *)v12, *((_DWORD *)this + 16));
    v6 = ExpandedCanonicalLongPathName;
    if ( ExpandedCanonicalLongPathName >= 0 )
    {
      FwBaseFree(*((_QWORD *)v15 + 2));
      ExpandedCanonicalLongPathName = FwStringCopy(*(_QWORD *)(*((_QWORD *)this + 10) + 16LL), (char *)v15 + 16);
      v6 = ExpandedCanonicalLongPathName;
      if ( ExpandedCanonicalLongPathName >= 0 )
      {
        *((_DWORD *)v15 + 10) = *(_DWORD *)(*((_QWORD *)this + 10) + 40LL);
        goto LABEL_18;
      }
    }
LABEL_23:
    v10 = (unsigned int)ExpandedCanonicalLongPathName;
    goto LABEL_24;
  }
  v10 = (unsigned int)v6;
LABEL_24:
  FwReportReturnError("FwAuthApp::SetRules", v10);
  FwFreeWFRule(v14);
  FwFreeWFRule(v15);
  if ( v6 == -2147024891 && (unsigned int)AccessDeniedShouldBeSuppressed() )
  {
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_91ff551a1acd3d9c8802511a4aa67041_Traceguids);
    v6 = 0;
  }
LABEL_31:
  FwBaseFree(v17);
  CloseLocalPolicyStore(v16);
  if ( v6 < 0 )
    return (unsigned int)FwReportReturnError("FwAuthApp::SetRules", (unsigned int)v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000283c  push    rbp
0x18000283e  push    rbx
0x18000283f  push    rsi
0x180002840  push    rdi
0x180002841  push    r15
0x180002843  mov     rbp, rsp
0x180002846  sub     rsp, 60h
0x18000284a  mov     rax, cs:__security_cookie
0x180002851  xor     rax, rsp
0x180002854  mov     [rbp+var_8], rax
0x180002858  mov     rax, rdx
0x18000285b  mov     [rbp+var_30], 0
0x180002863  mov     rdi, rcx
0x180002866  mov     [rbp+var_28], 0
0x18000286e  mov     rcx, rax
0x180002871  mov     [rbp+var_18], 0
0x180002879  lea     rdx, [rbp+var_30]
0x18000287d  mov     [rbp+var_10], 0
0x180002884  mov     rsi, r8
0x180002887  mov     [rbp+var_20], 0
0x18000288f  call    cs:__imp_FwCopyRule
0x180002896  nop     dword ptr [rax+rax+00h]
0x18000289b  lea     r15, aFwauthappSetru; "FwAuthApp::SetRules"
0x1800028a2  mov     ebx, eax
0x1800028a4  test    eax, eax
0x1800028a6  js      loc_180002A6F
0x1800028ac  lea     rdx, [rbp+var_28]
0x1800028b0  mov     rcx, rsi
0x1800028b3  call    cs:__imp_FwCopyRule
0x1800028ba  nop     dword ptr [rax+rax+00h]
0x1800028bf  mov     ebx, eax
0x1800028c1  test    eax, eax
0x1800028c3  js      loc_180002A6F
0x1800028c9  cmp     dword ptr [rdi+58h], 0
0x1800028cd  jz      loc_180002AE3
0x1800028d3  mov     rdx, [rbp+var_30]; struct _tag_FW_RULE *
0x1800028d7  call    ?ValidateAuthAppRule@FwAuthApp@@AEAAJPEBU_tag_FW_RULE@@@Z; FwAuthApp::ValidateAuthAppRule(_tag_FW_RULE const *)
0x1800028dc  mov     ebx, eax
0x1800028de  test    eax, eax
0x1800028e0  js      loc_180002A6F
0x1800028e6  mov     rdx, [rbp+var_28]; struct _tag_FW_RULE *
0x1800028ea  call    ?ValidateAuthAppRule@FwAuthApp@@AEAAJPEBU_tag_FW_RULE@@@Z; FwAuthApp::ValidateAuthAppRule(_tag_FW_RULE const *)
0x1800028ef  mov     ebx, eax
0x1800028f1  test    eax, eax
0x1800028f3  js      loc_180002A6F
0x1800028f9  xor     edx, edx
0x1800028fb  lea     rax, [rbp+var_20]
0x1800028ff  mov     [rsp+60h+var_38], rax
0x180002904  mov     ecx, 221h
0x180002909  mov     [rsp+60h+var_40], 0
0x180002911  lea     r9d, [rdx+2]
0x180002915  mov     r8d, r9d
0x180002918  call    FWOpenPolicyStore
0x18000291d  mov     ebx, eax
0x18000291f  test    eax, eax
0x180002921  jle     short loc_18000292C
0x180002923  movzx   ebx, ax
0x180002926  or      ebx, 80070000h
0x18000292c  test    ebx, ebx
0x18000292e  jns     short loc_180002937
0x180002930  mov     edx, ebx
0x180002932  jmp     loc_180002A71
0x180002937  mov     r8d, [rdi+40h]; unsigned int
0x18000293b  mov     eax, r8d
0x18000293e  mov     rdx, [rdi+48h]; struct _tag_FW_RULE *
0x180002942  not     eax
0x180002944  test    [rdx+28h], eax
0x180002947  jz      short loc_1800029A4
0x180002949  mov     rcx, [rbp+var_20]; void *
0x18000294d  call    ?FwSplitRule@@YAJPEAXPEAU_tag_FW_RULE@@K@Z; FwSplitRule(void *,_tag_FW_RULE *,ulong)
0x180002952  mov     ebx, eax
0x180002954  test    eax, eax
0x180002956  js      loc_180002A6F
0x18000295c  mov     rcx, [rbp+var_30]
0x180002960  mov     rcx, [rcx+10h]
0x180002964  call    cs:__imp_FwBaseFree
0x18000296b  nop     dword ptr [rax+rax+00h]
0x180002970  mov     rcx, [rdi+48h]
0x180002974  mov     rdx, [rbp+var_30]
0x180002978  add     rdx, 10h
0x18000297c  mov     rcx, [rcx+10h]
0x180002980  call    cs:__imp_FwStringCopy
0x180002987  nop     dword ptr [rax+rax+00h]
0x18000298c  mov     ebx, eax
0x18000298e  test    eax, eax
0x180002990  js      loc_180002A6F
0x180002996  mov     rax, [rdi+48h]
0x18000299a  mov     ecx, [rax+28h]
0x18000299d  mov     rax, [rbp+var_30]
0x1800029a1  mov     [rax+28h], ecx
0x1800029a4  mov     r8d, [rdi+40h]; unsigned int
0x1800029a8  mov     eax, r8d
0x1800029ab  mov     rdx, [rdi+50h]; struct _tag_FW_RULE *
0x1800029af  not     eax
0x1800029b1  test    [rdx+28h], eax
0x1800029b4  jz      short loc_180002A0D
0x1800029b6  mov     rcx, [rbp+var_20]; void *
0x1800029ba  call    ?FwSplitRule@@YAJPEAXPEAU_tag_FW_RULE@@K@Z; FwSplitRule(void *,_tag_FW_RULE *,ulong)
0x1800029bf  mov     ebx, eax
0x1800029c1  test    eax, eax
0x1800029c3  js      loc_180002A6F
0x1800029c9  mov     rcx, [rbp+var_28]
0x1800029cd  mov     rcx, [rcx+10h]
0x1800029d1  call    cs:__imp_FwBaseFree
0x1800029d8  nop     dword ptr [rax+rax+00h]
0x1800029dd  mov     rcx, [rdi+50h]
0x1800029e1  mov     rdx, [rbp+var_28]
0x1800029e5  add     rdx, 10h
0x1800029e9  mov     rcx, [rcx+10h]
0x1800029ed  call    cs:__imp_FwStringCopy
0x1800029f4  nop     dword ptr [rax+rax+00h]
0x1800029f9  mov     ebx, eax
0x1800029fb  test    eax, eax
0x1800029fd  js      short loc_180002A6F
0x1800029ff  mov     rax, [rdi+50h]
0x180002a03  mov     ecx, [rax+28h]
0x180002a06  mov     rax, [rbp+var_28]
0x180002a0a  mov     [rax+28h], ecx
0x180002a0d  mov     rcx, [rbp+var_30]
0x180002a11  lea     r8, [rbp+var_10]
0x180002a15  lea     rdx, [rbp+var_18]
0x180002a19  mov     rcx, [rcx+110h]
0x180002a20  call    cs:__imp_FwGetExpandedCanonicalLongPathName
0x180002a27  nop     dword ptr [rax+rax+00h]
0x180002a2c  mov     ebx, eax
0x180002a2e  test    eax, eax
0x180002a30  js      short loc_180002A6F
0x180002a32  cmp     [rbp+var_10], 1
0x180002a36  jnz     short loc_180002A49
0x180002a38  mov     r8d, [rdi+40h]
0x180002a3c  mov     rdx, [rbp+var_18]
0x180002a40  mov     rcx, [rbp+var_20]
0x180002a44  call    ?DeleteAllMatchingAuthAppRules@@YAJPEAXPEAGW4_tag_FW_PROFILE_TYPE@@@Z; DeleteAllMatchingAuthAppRules(void *,ushort *,_tag_FW_PROFILE_TYPE)
0x180002a49  mov     rdx, [rbp+var_20]; void *
0x180002a4d  mov     rcx, [rbp+var_30]; struct _tag_FW_RULE *
0x180002a51  call    ?SaveRule@@YAJPEAU_tag_FW_RULE@@PEAX@Z; SaveRule(_tag_FW_RULE *,void *)
0x180002a56  mov     ebx, eax
0x180002a58  test    eax, eax
0x180002a5a  js      short loc_180002A6F
0x180002a5c  mov     rdx, [rbp+var_20]; void *
0x180002a60  mov     rcx, [rbp+var_28]; struct _tag_FW_RULE *
0x180002a64  call    ?SaveRule@@YAJPEAU_tag_FW_RULE@@PEAX@Z; SaveRule(_tag_FW_RULE *,void *)
0x180002a69  mov     ebx, eax
0x180002a6b  test    eax, eax
0x180002a6d  jns     short loc_180002AE3
0x180002a6f  mov     edx, eax
0x180002a71  mov     rcx, r15
0x180002a74  call    cs:__imp_FwReportReturnError
0x180002a7b  nop     dword ptr [rax+rax+00h]
0x180002a80  mov     rcx, [rbp+var_30]
0x180002a84  call    cs:__imp_FwFreeWFRule
0x180002a8b  nop     dword ptr [rax+rax+00h]
0x180002a90  mov     rcx, [rbp+var_28]
0x180002a94  call    cs:__imp_FwFreeWFRule
0x180002a9b  nop     dword ptr [rax+rax+00h]
0x180002aa0  cmp     ebx, 80070005h
0x180002aa6  jnz     short loc_180002B23
0x180002aa8  call    ?AccessDeniedShouldBeSuppressed@@YAHXZ; AccessDeniedShouldBeSuppressed(void)
0x180002aad  test    eax, eax
0x180002aaf  jz      short loc_180002B23
0x180002ab1  mov     rcx, cs:WPP_GLOBAL_Control
0x180002ab8  lea     rax, WPP_GLOBAL_Control
0x180002abf  cmp     rcx, rax
0x180002ac2  jz      short loc_180002ADF
0x180002ac4  test    byte ptr [rcx+1Ch], 2
0x180002ac8  jz      short loc_180002ADF
0x180002aca  mov     rcx, [rcx+10h]
0x180002ace  lea     r8, WPP_91ff551a1acd3d9c8802511a4aa67041_Traceguids
0x180002ad5  mov     edx, 0Ah
0x180002ada  call    WPP_SF_
0x180002adf  xor     ebx, ebx
0x180002ae1  jmp     short loc_180002B23
0x180002ae3  mov     rcx, [rdi+48h]
0x180002ae7  call    cs:__imp_FwFreeWFRule
0x180002aee  nop     dword ptr [rax+rax+00h]
0x180002af3  mov     rcx, [rdi+50h]
0x180002af7  call    cs:__imp_FwFreeWFRule
0x180002afe  nop     dword ptr [rax+rax+00h]
0x180002b03  mov     rax, [rbp+var_30]
0x180002b07  mov     [rdi+48h], rax
0x180002b0b  mov     rax, [rbp+var_28]
0x180002b0f  mov     [rdi+50h], rax
0x180002b13  mov     [rbp+var_30], 0
0x180002b1b  mov     [rbp+var_28], 0
0x180002b23  mov     rcx, [rbp+var_18]
0x180002b27  call    cs:__imp_FwBaseFree
0x180002b2e  nop     dword ptr [rax+rax+00h]
0x180002b33  mov     rcx, [rbp+var_20]; void *
0x180002b37  call    ?CloseLocalPolicyStore@@YAXPEAX@Z; CloseLocalPolicyStore(void *)
0x180002b3c  test    ebx, ebx
0x180002b3e  jns     short loc_180002B53
0x180002b40  mov     edx, ebx
0x180002b42  mov     rcx, r15
0x180002b45  call    cs:__imp_FwReportReturnError
0x180002b4c  nop     dword ptr [rax+rax+00h]
0x180002b51  mov     ebx, eax
0x180002b53  mov     eax, ebx
0x180002b55  mov     rcx, [rbp+var_8]
0x180002b59  xor     rcx, rsp; StackCookie
0x180002b5c  call    __security_check_cookie
0x180002b61  add     rsp, 60h
0x180002b65  pop     r15
0x180002b67  pop     rdi
0x180002b68  pop     rsi
0x180002b69  pop     rbx
0x180002b6a  pop     rbp
0x180002b6b  retn
```
