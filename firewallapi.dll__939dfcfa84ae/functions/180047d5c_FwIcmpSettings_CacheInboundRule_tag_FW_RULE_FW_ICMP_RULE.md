# FwIcmpSettings::CacheInboundRule(_tag_FW_RULE *,FW_ICMP_RULE_ *)

- ea: `0x180047d5c`
- end: `0x180047e07`
- name: `?CacheInboundRule@FwIcmpSettings@@AEAAJPEAU_tag_FW_RULE@@PEAUFW_ICMP_RULE_@@@Z`
- size: `171`
- prototype: `__int64 __fastcall(FwIcmpSettings *__hidden this, struct _tag_FW_RULE *, struct FW_ICMP_RULE_ *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180047ec4`

## callees

- `0x18003336c`
- `0x180047d5c`

## import_xrefs

- `fwbase!FwReportReturnError` at `0x180047dab`
- `fwbase!FwReportReturnError` at `0x180047dc0`
- `fwbase!FwReportReturnError` at `0x180047dab`
- `fwbase!FwReportReturnError` at `0x180047dc0`
- `FWPolicyIOMgr!FwCopyRule` at `0x180047d90`
- `FWPolicyIOMgr!FwCopyRule` at `0x180047d90`

## string_xrefs

- `0x180047da4`: `FwIcmpSettings::CacheInboundRule`
- `0x180047db9`: `FwIcmpSettings::CacheInboundRule`

## pseudocode

```c
__int64 __fastcall FwIcmpSettings::CacheInboundRule(
        FwIcmpSettings *this,
        struct _tag_FW_RULE *a2,
        struct FW_ICMP_RULE_ *a3)
{
  int v3; // eax
  int v4; // eax
  unsigned int v5; // ebx

  if ( *((_QWORD *)a3 + 1) )
  {
    v5 = 0;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_20be8c82b411374fbd35ad9fa76ebe93_Traceguids);
  }
  else
  {
    if ( *((_DWORD *)a2 + 72) != 3 || (v3 = 1, (*((_BYTE *)a2 + 292) & 1) == 0) )
      v3 = 0;
    *((_DWORD *)a3 + 6) = v3;
    v4 = FwCopyRule(a2, (char *)a3 + 8);
    v5 = v4;
    if ( v4 < 0 )
    {
      FwReportReturnError("FwIcmpSettings::CacheInboundRule", (unsigned int)v4);
      return (unsigned int)FwReportReturnError("FwIcmpSettings::CacheInboundRule", v5);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180047d5c  push    rbx
0x180047d5e  sub     rsp, 20h
0x180047d62  mov     r9, rdx
0x180047d65  lea     rdx, [r8+8]
0x180047d69  cmp     qword ptr [rdx], 0
0x180047d6d  jnz     short loc_180047DD0
0x180047d6f  cmp     dword ptr [r9+120h], 3
0x180047d77  jnz     short loc_180047D87
0x180047d79  mov     eax, 1
0x180047d7e  test    [r9+124h], al
0x180047d85  jnz     short loc_180047D89
0x180047d87  xor     eax, eax
0x180047d89  mov     rcx, r9
0x180047d8c  mov     [r8+18h], eax
0x180047d90  call    cs:__imp_FwCopyRule
0x180047d97  nop     dword ptr [rax+rax+00h]
0x180047d9c  mov     ebx, eax
0x180047d9e  test    eax, eax
0x180047da0  jns     short loc_180047DFE
0x180047da2  mov     edx, eax
0x180047da4  lea     rcx, aFwicmpsettings_11; "FwIcmpSettings::CacheInboundRule"
0x180047dab  call    cs:__imp_FwReportReturnError
0x180047db2  nop     dword ptr [rax+rax+00h]
0x180047db7  mov     edx, ebx
0x180047db9  lea     rcx, aFwicmpsettings_11; "FwIcmpSettings::CacheInboundRule"
0x180047dc0  call    cs:__imp_FwReportReturnError
0x180047dc7  nop     dword ptr [rax+rax+00h]
0x180047dcc  mov     ebx, eax
0x180047dce  jmp     short loc_180047DFE
0x180047dd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180047dd7  lea     rax, WPP_GLOBAL_Control
0x180047dde  xor     ebx, ebx
0x180047de0  cmp     rcx, rax
0x180047de3  jz      short loc_180047DFE
0x180047de5  test    byte ptr [rcx+1Ch], 2
0x180047de9  jz      short loc_180047DFE
0x180047deb  mov     rcx, [rcx+10h]
0x180047def  lea     edx, [rbx+0Ah]
0x180047df2  lea     r8, WPP_20be8c82b411374fbd35ad9fa76ebe93_Traceguids
0x180047df9  call    WPP_SF_
0x180047dfe  mov     eax, ebx
0x180047e00  add     rsp, 20h
0x180047e04  pop     rbx
0x180047e05  retn
```
