# FwAuthApp::Initialize(_tag_FW_PROFILE_TYPE,ushort const *)

- ea: `0x180003080`
- end: `0x180003285`
- name: `?Initialize@FwAuthApp@@AEAAJW4_tag_FW_PROFILE_TYPE@@PEBG@Z`
- size: `517`
- prototype: `int __high(enum _tag_FW_PROFILE_TYPE, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18000265c`

## callees

- `0x180003080`
- `0x18000328c`
- `0x1800037dc`
- `0x180009780`
- `0x18000c3f0`
- `0x18000d0f0`
- `0x1800294b0`

## import_xrefs

- `fwbase!FwReportReturnError` at `0x180003198`
- `fwbase!FwReportReturnError` at `0x1800031e7`
- `fwbase!FwReportReturnError` at `0x180003198`
- `fwbase!FwReportReturnError` at `0x1800031e7`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x180003217`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x18000322f`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x180003217`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x18000322f`
- `FWPolicyIOMgr!FwCopyRule` at `0x180003179`
- `FWPolicyIOMgr!FwCopyRule` at `0x180003254`
- `FWPolicyIOMgr!FwCopyRule` at `0x180003179`
- `FWPolicyIOMgr!FwCopyRule` at `0x180003254`

## pseudocode

```c
__int64 __fastcall FwAuthApp::Initialize(__int64 a1, int a2, const unsigned __int16 *a3)
{
  int v5; // eax
  signed int v6; // ebx
  int v7; // eax
  struct _tag_FW_RULE *MatchingAppRule; // rbx
  struct _tag_FW_RULE *v9; // rax
  struct _tag_FW_RULE *v10; // rsi
  int v11; // eax
  __int64 v12; // rdx
  __int64 v14; // rcx
  unsigned int v15; // [rsp+30h] [rbp-20h] BYREF
  struct _tag_FW_RULE *v16; // [rsp+38h] [rbp-18h] BYREF
  void *v17; // [rsp+40h] [rbp-10h] BYREF

  *(_DWORD *)(a1 + 64) = a2;
  v16 = 0;
  v15 = 0;
  v17 = 0;
  v5 = FWOpenPolicyStore(0x221u, 0, 2u, 1u, 0, &v17);
  v6 = v5;
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  if ( v6 < 0 )
    goto LABEL_10;
  v7 = FWEnumFirewallRules((__int64)v17, 196608, *(_DWORD *)(a1 + 64), 7, (__int64)&v15, (__int64)&v16);
  v6 = v7;
  if ( v7 > 0 )
    v6 = (unsigned __int16)v7 | 0x80070000;
  if ( v6 < 0 )
    goto LABEL_10;
  MatchingAppRule = FwFindMatchingAppRule(v16, v15, a3, 6u);
  v9 = FwFindMatchingAppRule(v16, v15, a3, 0x11u);
  v10 = v9;
  if ( !MatchingAppRule )
  {
    if ( v9 )
    {
LABEL_18:
      v11 = FwCopyRule(v10, a1 + 80);
      v6 = v11;
      if ( v11 < 0 )
        goto LABEL_9;
      goto LABEL_19;
    }
    v6 = -2147024894;
LABEL_10:
    v12 = (unsigned int)v6;
    goto LABEL_11;
  }
  v11 = FwCopyRule(MatchingAppRule, a1 + 72);
  v6 = v11;
  if ( v11 < 0 )
  {
LABEL_9:
    v12 = (unsigned int)v11;
LABEL_11:
    FwReportReturnError("FwAuthApp::Initialize", v12);
    goto LABEL_12;
  }
  if ( v10 )
    goto LABEL_18;
LABEL_19:
  *(_DWORD *)(a1 + 88) = 1;
LABEL_12:
  FWFreeFirewallRules((__int64)v16);
  if ( v6 < 0 )
  {
    FwFreeWFRule(*(_QWORD *)(a1 + 72));
    v14 = *(_QWORD *)(a1 + 80);
    *(_QWORD *)(a1 + 72) = 0;
    FwFreeWFRule(v14);
    *(_QWORD *)(a1 + 80) = 0;
  }
  CloseLocalPolicyStore(v17);
  if ( v6 < 0 )
    return (unsigned int)FwReportReturnError("FwAuthApp::Initialize", (unsigned int)v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180003080  mov     [rsp-18h+arg_8], rbx
0x180003085  mov     [rsp-18h+arg_18], rsi
0x18000308a  push    rbp
0x18000308b  push    rdi
0x18000308c  push    r15
0x18000308e  mov     rbp, rsp
0x180003091  sub     rsp, 50h
0x180003095  mov     rax, cs:__security_cookie
0x18000309c  xor     rax, rsp
0x18000309f  mov     [rbp+var_8], rax
0x1800030a3  mov     [rcx+40h], edx
0x1800030a6  lea     rax, [rbp+var_10]
0x1800030aa  xor     edx, edx
0x1800030ac  mov     [rsp+50h+var_28], rax
0x1800030b1  mov     rsi, r8
0x1800030b4  mov     [rbp+var_18], 0
0x1800030bc  mov     rdi, rcx
0x1800030bf  mov     [rbp+var_20], 0
0x1800030c6  mov     ecx, 221h
0x1800030cb  mov     [rbp+var_10], 0
0x1800030d3  lea     r9d, [rdx+1]
0x1800030d7  mov     dword ptr [rsp+50h+var_30], 0
0x1800030df  lea     r8d, [rdx+2]
0x1800030e3  call    FWOpenPolicyStore
0x1800030e8  mov     ebx, eax
0x1800030ea  test    eax, eax
0x1800030ec  jg      loc_1800031F7
0x1800030f2  lea     r15, aFwauthappIniti; "FwAuthApp::Initialize"
0x1800030f9  test    ebx, ebx
0x1800030fb  js      loc_180003193
0x180003101  mov     r8d, [rdi+40h]
0x180003105  lea     rax, [rbp+var_18]
0x180003109  mov     rcx, [rbp+var_10]
0x18000310d  mov     r9d, 7
0x180003113  mov     [rsp+50h+var_28], rax
0x180003118  mov     edx, 30000h
0x18000311d  lea     rax, [rbp+var_20]
0x180003121  mov     [rsp+50h+var_30], rax
0x180003126  call    FWEnumFirewallRules
0x18000312b  mov     ebx, eax
0x18000312d  test    eax, eax
0x18000312f  jg      loc_180003205
0x180003135  test    ebx, ebx
0x180003137  js      short loc_180003193
0x180003139  mov     edx, [rbp+var_20]; unsigned int
0x18000313c  mov     r9d, 6; unsigned __int16
0x180003142  mov     rcx, [rbp+var_18]; struct _tag_FW_RULE *
0x180003146  mov     r8, rsi; unsigned __int16 *
0x180003149  call    ?FwFindMatchingAppRule@@YAPEAU_tag_FW_RULE@@QEAU1@KPEBGG@Z; FwFindMatchingAppRule(_tag_FW_RULE * const,ulong,ushort const *,ushort)
0x18000314e  mov     edx, [rbp+var_20]; unsigned int
0x180003151  mov     r9d, 11h; unsigned __int16
0x180003157  mov     rcx, [rbp+var_18]; struct _tag_FW_RULE *
0x18000315b  mov     r8, rsi; unsigned __int16 *
0x18000315e  mov     rbx, rax
0x180003161  call    ?FwFindMatchingAppRule@@YAPEAU_tag_FW_RULE@@QEAU1@KPEBGG@Z; FwFindMatchingAppRule(_tag_FW_RULE * const,ulong,ushort const *,ushort)
0x180003166  mov     rsi, rax
0x180003169  test    rbx, rbx
0x18000316c  jz      loc_180003276
0x180003172  lea     rdx, [rdi+48h]
0x180003176  mov     rcx, rbx
0x180003179  call    cs:__imp_FwCopyRule
0x180003180  nop     dword ptr [rax+rax+00h]
0x180003185  mov     ebx, eax
0x180003187  test    eax, eax
0x180003189  jns     loc_180003248
0x18000318f  mov     edx, eax
0x180003191  jmp     short loc_180003195
0x180003193  mov     edx, ebx
0x180003195  mov     rcx, r15
0x180003198  call    cs:__imp_FwReportReturnError
0x18000319f  nop     dword ptr [rax+rax+00h]
0x1800031a4  mov     rcx, [rbp+var_18]
0x1800031a8  call    FWFreeFirewallRules
0x1800031ad  test    ebx, ebx
0x1800031af  js      short loc_180003213
0x1800031b1  mov     rcx, [rbp+var_10]; void *
0x1800031b5  call    ?CloseLocalPolicyStore@@YAXPEAX@Z; CloseLocalPolicyStore(void *)
0x1800031ba  test    ebx, ebx
0x1800031bc  js      short loc_1800031E2
0x1800031be  mov     eax, ebx
0x1800031c0  mov     rcx, [rbp+var_8]
0x1800031c4  xor     rcx, rsp; StackCookie
0x1800031c7  call    __security_check_cookie
0x1800031cc  lea     r11, [rsp+50h+var_s0]
0x1800031d1  mov     rbx, [r11+28h]
0x1800031d5  mov     rsi, [r11+38h]
0x1800031d9  mov     rsp, r11
0x1800031dc  pop     r15
0x1800031de  pop     rdi
0x1800031df  pop     rbp
0x1800031e0  retn
0x1800031e2  mov     edx, ebx
0x1800031e4  mov     rcx, r15
0x1800031e7  call    cs:__imp_FwReportReturnError
0x1800031ee  nop     dword ptr [rax+rax+00h]
0x1800031f3  mov     ebx, eax
0x1800031f5  jmp     short loc_1800031BE
0x1800031f7  movzx   ebx, ax
0x1800031fa  or      ebx, 80070000h
0x180003200  jmp     loc_1800030F2
0x180003205  movzx   ebx, ax
0x180003208  or      ebx, 80070000h
0x18000320e  jmp     loc_180003135
0x180003213  mov     rcx, [rdi+48h]
0x180003217  call    cs:__imp_FwFreeWFRule
0x18000321e  nop     dword ptr [rax+rax+00h]
0x180003223  mov     rcx, [rdi+50h]
0x180003227  mov     qword ptr [rdi+48h], 0
0x18000322f  call    cs:__imp_FwFreeWFRule
0x180003236  nop     dword ptr [rax+rax+00h]
0x18000323b  mov     qword ptr [rdi+50h], 0
0x180003243  jmp     loc_1800031B1
0x180003248  test    rsi, rsi
0x18000324b  jz      short loc_18000326A
0x18000324d  lea     rdx, [rdi+50h]
0x180003251  mov     rcx, rsi
0x180003254  call    cs:__imp_FwCopyRule
0x18000325b  nop     dword ptr [rax+rax+00h]
0x180003260  mov     ebx, eax
0x180003262  test    eax, eax
0x180003264  js      loc_18000318F
0x18000326a  mov     dword ptr [rdi+58h], 1
0x180003271  jmp     loc_1800031A4
0x180003276  test    rsi, rsi
0x180003279  jnz     short loc_18000324D
0x18000327b  mov     ebx, 80070002h
0x180003280  jmp     loc_180003193
```
