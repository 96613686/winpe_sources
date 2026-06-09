# FwOpenPort::SetRule(_tag_FW_RULE const *,_tag_FW_RULE *)

- ea: `0x18003bd9c`
- end: `0x18003bfba`
- name: `?SetRule@FwOpenPort@@AEAAJPEBU_tag_FW_RULE@@PEAU2@@Z`
- size: `542`
- prototype: `int(FwOpenPort *__hidden this, const struct _tag_FW_RULE *, struct _tag_FW_RULE *)`
- caller_count: `7`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180001edc`
- `0x18003c570`
- `0x18003c790`
- `0x18003c940`
- `0x18003cb30`
- `0x18003cd00`
- `0x18003cf10`

## callees

- `0x1800037dc`
- `0x18000be5c`
- `0x1800143d8`
- `0x1800294b0`
- `0x180030468`
- `0x180032840`
- `0x18003336c`
- `0x18003bd9c`

## import_xrefs

- `fwbase!FwBaseFree` at `0x18003bebe`
- `fwbase!FwBaseFree` at `0x18003bebe`
- `fwbase!FwReportReturnError` at `0x18003be36`
- `fwbase!FwReportReturnError` at `0x18003be4b`
- `fwbase!FwReportReturnError` at `0x18003bf00`
- `fwbase!FwReportReturnError` at `0x18003bf8e`
- `fwbase!FwReportReturnError` at `0x18003be36`
- `fwbase!FwReportReturnError` at `0x18003be4b`
- `fwbase!FwReportReturnError` at `0x18003bf00`
- `fwbase!FwReportReturnError` at `0x18003bf8e`
- `fwbase!FwStringCopy` at `0x18003bed6`
- `fwbase!FwStringCopy` at `0x18003bed6`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x18003bf10`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x18003bf64`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x18003bf10`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x18003bf64`
- `FWPolicyIOMgr!FwCopyRule` at `0x18003bdd7`
- `FWPolicyIOMgr!FwCopyRule` at `0x18003bdd7`

## string_xrefs

- `0x18003bde3`: `FwOpenPort::SetRule`
- `0x18003be2f`: `FwOpenPort::ValidateOpenPortRule`
- `0x18003be44`: `FwOpenPort::ValidateOpenPortRule`

## pseudocode

```c
__int64 __fastcall FwOpenPort::SetRule(FwOpenPort *this, const struct _tag_FW_RULE *a2, struct _tag_FW_RULE *a3)
{
  int v5; // eax
  int v6; // ebx
  _WORD *v7; // rax
  unsigned int v8; // ebx
  __int64 v9; // rdx
  struct _tag_FW_RULE *v10; // rcx
  unsigned int v11; // r8d
  struct _tag_FW_RULE *v12; // rdi
  struct _tag_FW_RULE *v14; // [rsp+20h] [rbp-20h] BYREF
  void *v15; // [rsp+28h] [rbp-18h] BYREF

  v14 = 0;
  v15 = 0;
  v5 = FwCopyRule(a2, &v14);
  v6 = v5;
  if ( v5 < 0 )
    goto LABEL_20;
  if ( !*((_DWORD *)this + 21) )
    goto LABEL_26;
  if ( *((_WORD *)v14 + 24) != 6 && *((_WORD *)v14 + 24) != 17 )
    goto LABEL_8;
  v7 = (_WORD *)*((_QWORD *)v14 + 3);
  if ( !v7 )
  {
    v8 = -2147467261;
    v9 = 2147500035LL;
    goto LABEL_9;
  }
  if ( !*v7 )
  {
LABEL_8:
    v9 = 2147942487LL;
    v8 = -2147024809;
LABEL_9:
    FwReportReturnError("FwOpenPort::ValidateOpenPortRule", v9);
    v5 = FwReportReturnError("FwOpenPort::ValidateOpenPortRule", v8);
    v6 = v5;
    if ( v5 < 0 )
      goto LABEL_20;
  }
  v5 = OpenLocalPolicyStore(2, &v15);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v10 = v14;
    v11 = *((_DWORD *)this + 16);
    v12 = v14;
    if ( a3 )
      v12 = a3;
    if ( (~v11 & *((_DWORD *)v12 + 10)) != 0 )
    {
      v5 = FwSplitRule(v15, v12, v11);
      v6 = v5;
      if ( v5 < 0 )
        goto LABEL_20;
      *((_DWORD *)v14 + 10) = *((_DWORD *)v12 + 10);
      v10 = v14;
    }
    if ( !a3 )
      goto LABEL_19;
    FwBaseFree(*((_QWORD *)v10 + 2));
    v5 = FwStringCopy(*((_QWORD *)a3 + 2), (char *)v14 + 16);
    v6 = v5;
    if ( v5 >= 0 )
    {
      v10 = v14;
LABEL_19:
      v5 = SaveRule(v10, v15);
      v6 = v5;
      if ( v5 < 0 )
        goto LABEL_20;
LABEL_26:
      FwFreeWFRule(*((_QWORD *)this + 9));
      *((_QWORD *)this + 9) = v14;
      v14 = 0;
      goto LABEL_27;
    }
  }
LABEL_20:
  FwReportReturnError("FwOpenPort::SetRule", (unsigned int)v5);
  FwFreeWFRule(v14);
  if ( v6 == -2147024891 && (unsigned int)AccessDeniedShouldBeSuppressed() )
  {
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_4cabb5b60cea3199fbe674e9f4ad4a38_Traceguids);
    v6 = 0;
  }
LABEL_27:
  CloseLocalPolicyStore(v15);
  if ( v6 < 0 )
    return (unsigned int)FwReportReturnError("FwOpenPort::SetRule", (unsigned int)v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003bd9c  push    rbp
0x18003bd9e  push    rbx
0x18003bd9f  push    rsi
0x18003bda0  push    rdi
0x18003bda1  push    r12
0x18003bda3  push    r14
0x18003bda5  push    r15
0x18003bda7  mov     rbp, rsp
0x18003bdaa  sub     rsp, 40h
0x18003bdae  mov     rax, cs:__security_cookie
0x18003bdb5  xor     rax, rsp
0x18003bdb8  mov     [rbp+var_10], rax
0x18003bdbc  mov     rax, rdx
0x18003bdbf  mov     rsi, rcx
0x18003bdc2  xor     r15d, r15d
0x18003bdc5  lea     rdx, [rbp+var_20]
0x18003bdc9  mov     rcx, rax
0x18003bdcc  mov     [rbp+var_20], r15
0x18003bdd0  mov     r14, r8
0x18003bdd3  mov     [rbp+var_18], r15
0x18003bdd7  call    cs:__imp_FwCopyRule
0x18003bdde  nop     dword ptr [rax+rax+00h]
0x18003bde3  lea     r12, aFwopenportSetr; "FwOpenPort::SetRule"
0x18003bdea  mov     ebx, eax
0x18003bdec  test    eax, eax
0x18003bdee  js      loc_18003BEFB
0x18003bdf4  cmp     [rsi+54h], r15d
0x18003bdf8  jz      loc_18003BF60
0x18003bdfe  mov     rax, [rbp+var_20]
0x18003be02  cmp     word ptr [rax+30h], 6
0x18003be07  jz      short loc_18003BE10
0x18003be09  cmp     word ptr [rax+30h], 11h
0x18003be0e  jnz     short loc_18003BE28
0x18003be10  mov     rax, [rax+18h]
0x18003be14  test    rax, rax
0x18003be17  jnz     short loc_18003BE22
0x18003be19  mov     ebx, 80004003h
0x18003be1e  mov     edx, ebx
0x18003be20  jmp     short loc_18003BE2F
0x18003be22  cmp     [rax], r15w
0x18003be26  jnz     short loc_18003BE61
0x18003be28  mov     edx, 80070057h
0x18003be2d  mov     ebx, edx
0x18003be2f  lea     rcx, aFwopenportVali; "FwOpenPort::ValidateOpenPortRule"
0x18003be36  call    cs:__imp_FwReportReturnError
0x18003be3d  nop     dword ptr [rax+rax+00h]
0x18003be42  mov     edx, ebx
0x18003be44  lea     rcx, aFwopenportVali; "FwOpenPort::ValidateOpenPortRule"
0x18003be4b  call    cs:__imp_FwReportReturnError
0x18003be52  nop     dword ptr [rax+rax+00h]
0x18003be57  mov     ebx, eax
0x18003be59  test    eax, eax
0x18003be5b  js      loc_18003BEFB
0x18003be61  lea     rdx, [rbp+var_18]
0x18003be65  mov     ecx, 2
0x18003be6a  call    ?OpenLocalPolicyStore@@YAJW4_tag_FW_POLICY_ACCESS_RIGHT@@PEAPEAX@Z; OpenLocalPolicyStore(_tag_FW_POLICY_ACCESS_RIGHT,void * *)
0x18003be6f  mov     ebx, eax
0x18003be71  test    eax, eax
0x18003be73  js      loc_18003BEFB
0x18003be79  mov     rcx, [rbp+var_20]
0x18003be7d  test    r14, r14
0x18003be80  mov     r8d, [rsi+40h]; unsigned int
0x18003be84  mov     rdi, rcx
0x18003be87  cmovnz  rdi, r14
0x18003be8b  mov     eax, r8d
0x18003be8e  not     eax
0x18003be90  test    [rdi+28h], eax
0x18003be93  jz      short loc_18003BEB5
0x18003be95  mov     rcx, [rbp+var_18]; void *
0x18003be99  mov     rdx, rdi; struct _tag_FW_RULE *
0x18003be9c  call    ?FwSplitRule@@YAJPEAXPEAU_tag_FW_RULE@@K@Z; FwSplitRule(void *,_tag_FW_RULE *,ulong)
0x18003bea1  mov     ebx, eax
0x18003bea3  test    eax, eax
0x18003bea5  js      short loc_18003BEFB
0x18003bea7  mov     rax, [rbp+var_20]
0x18003beab  mov     edx, [rdi+28h]
0x18003beae  mov     [rax+28h], edx
0x18003beb1  mov     rcx, [rbp+var_20]
0x18003beb5  test    r14, r14
0x18003beb8  jz      short loc_18003BEEC
0x18003beba  mov     rcx, [rcx+10h]
0x18003bebe  call    cs:__imp_FwBaseFree
0x18003bec5  nop     dword ptr [rax+rax+00h]
0x18003beca  mov     rdx, [rbp+var_20]
0x18003bece  mov     rcx, [r14+10h]
0x18003bed2  add     rdx, 10h
0x18003bed6  call    cs:__imp_FwStringCopy
0x18003bedd  nop     dword ptr [rax+rax+00h]
0x18003bee2  mov     ebx, eax
0x18003bee4  test    eax, eax
0x18003bee6  js      short loc_18003BEFB
0x18003bee8  mov     rcx, [rbp+var_20]; struct _tag_FW_RULE *
0x18003beec  mov     rdx, [rbp+var_18]; void *
0x18003bef0  call    ?SaveRule@@YAJPEAU_tag_FW_RULE@@PEAX@Z; SaveRule(_tag_FW_RULE *,void *)
0x18003bef5  mov     ebx, eax
0x18003bef7  test    eax, eax
0x18003bef9  jns     short loc_18003BF60
0x18003befb  mov     edx, eax
0x18003befd  mov     rcx, r12
0x18003bf00  call    cs:__imp_FwReportReturnError
0x18003bf07  nop     dword ptr [rax+rax+00h]
0x18003bf0c  mov     rcx, [rbp+var_20]
0x18003bf10  call    cs:__imp_FwFreeWFRule
0x18003bf17  nop     dword ptr [rax+rax+00h]
0x18003bf1c  cmp     ebx, 80070005h
0x18003bf22  jnz     short loc_18003BF7C
0x18003bf24  call    ?AccessDeniedShouldBeSuppressed@@YAHXZ; AccessDeniedShouldBeSuppressed(void)
0x18003bf29  test    eax, eax
0x18003bf2b  jz      short loc_18003BF7C
0x18003bf2d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bf34  lea     rax, WPP_GLOBAL_Control
0x18003bf3b  cmp     rcx, rax
0x18003bf3e  jz      short loc_18003BF5B
0x18003bf40  test    byte ptr [rcx+1Ch], 2
0x18003bf44  jz      short loc_18003BF5B
0x18003bf46  mov     rcx, [rcx+10h]
0x18003bf4a  lea     r8, WPP_4cabb5b60cea3199fbe674e9f4ad4a38_Traceguids
0x18003bf51  mov     edx, 0Ah
0x18003bf56  call    WPP_SF_
0x18003bf5b  mov     ebx, r15d
0x18003bf5e  jmp     short loc_18003BF7C
0x18003bf60  mov     rcx, [rsi+48h]
0x18003bf64  call    cs:__imp_FwFreeWFRule
0x18003bf6b  nop     dword ptr [rax+rax+00h]
0x18003bf70  mov     rax, [rbp+var_20]
0x18003bf74  mov     [rsi+48h], rax
0x18003bf78  mov     [rbp+var_20], r15
0x18003bf7c  mov     rcx, [rbp+var_18]; void *
0x18003bf80  call    ?CloseLocalPolicyStore@@YAXPEAX@Z; CloseLocalPolicyStore(void *)
0x18003bf85  test    ebx, ebx
0x18003bf87  jns     short loc_18003BF9C
0x18003bf89  mov     edx, ebx
0x18003bf8b  mov     rcx, r12
0x18003bf8e  call    cs:__imp_FwReportReturnError
0x18003bf95  nop     dword ptr [rax+rax+00h]
0x18003bf9a  mov     ebx, eax
0x18003bf9c  mov     eax, ebx
0x18003bf9e  mov     rcx, [rbp+var_10]
0x18003bfa2  xor     rcx, rsp; StackCookie
0x18003bfa5  call    __security_check_cookie
0x18003bfaa  add     rsp, 40h
0x18003bfae  pop     r15
0x18003bfb0  pop     r14
0x18003bfb2  pop     r12
0x18003bfb4  pop     rdi
0x18003bfb5  pop     rsi
0x18003bfb6  pop     rbx
0x18003bfb7  pop     rbp
0x18003bfb8  retn
```
