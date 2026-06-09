# FwRule::FwFindMatchingRuleWithLocRuleName(_tag_FW_RULE * const,ulong,ushort const *,FwPolicyViewFlags)

- ea: `0x180010e50`
- end: `0x180010ff0`
- name: `?FwFindMatchingRuleWithLocRuleName@FwRule@@SAPEAU_tag_FW_RULE@@QEAU2@KPEBGW4FwPolicyViewFlags@@@Z`
- size: `416`
- prototype: `static struct _tag_FW_RULE *__high(struct _tag_FW_RULE *const, unsigned int, const unsigned __int16 *, enum FwPolicyViewFlags)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800042c0`
- `0x180004680`

## callees

- `0x180010e50`
- `0x180011000`
- `0x1800111a8`
- `0x1800294b0`
- `0x18003336c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180010f03`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180010f03`
- `fwbase!FwBaseFree` at `0x180010f21`
- `fwbase!FwBaseFree` at `0x180010f89`
- `fwbase!FwBaseFree` at `0x180010f9a`
- `fwbase!FwBaseFree` at `0x180010f21`
- `fwbase!FwBaseFree` at `0x180010f89`
- `fwbase!FwBaseFree` at `0x180010f9a`
- `fwbase!FwLoadIndirectString` at `0x180010ee9`
- `fwbase!FwLoadIndirectString` at `0x180010ee9`
- `fwbase!FwReportReturnError` at `0x180010f63`
- `fwbase!FwReportReturnError` at `0x180010f78`
- `fwbase!FwReportReturnError` at `0x180010f63`
- `fwbase!FwReportReturnError` at `0x180010f78`
- `fwbase!FwStringCopy` at `0x180010f48`
- `fwbase!FwStringCopy` at `0x180010f48`

## pseudocode

```c
_QWORD *__fastcall FwRule::FwFindMatchingRuleWithLocRuleName(
        _QWORD *a1,
        unsigned int a2,
        const unsigned __int16 *a3,
        unsigned int a4)
{
  _QWORD *v8; // rsi
  int v9; // eax
  unsigned int i; // edi
  _WORD *v11; // rbp
  int v12; // eax
  unsigned int v13; // ebp
  __int64 v14; // rdx
  __int64 v16; // [rsp+20h] [rbp-48h] BYREF
  unsigned __int16 *v17; // [rsp+28h] [rbp-40h] BYREF

  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 98, WPP_92d7822da2e63f0d2b29182cb9b878d1_Traceguids);
  v8 = 0;
  v17 = 0;
  v16 = 0;
  v9 = FwTryResolveString(a3, a2, &v17);
  if ( v9 < 0 )
  {
    v14 = (unsigned int)v9;
LABEL_15:
    FwReportReturnError("FwRule::FwFindMatchingRuleWithLocRuleName", v14);
  }
  else
  {
    for ( i = 0; i < a2 && !v8; ++i )
    {
      if ( (unsigned int)FwRule::FwIsValidRule(a1, a4) )
      {
        v11 = (_WORD *)a1[3];
        if ( *v11 != 64 || (int)FwLoadIndirectString(a1[3], &v16) < 0 )
        {
          v12 = FwStringCopy(v11, &v16);
          v13 = v12;
          if ( v12 < 0 )
          {
            FwReportReturnError("FwTryResolveString", (unsigned int)v12);
            v14 = v13;
            goto LABEL_15;
          }
        }
        v8 = a1;
        if ( (unsigned int)_o__wcsicmp(v17, v16) )
          v8 = 0;
        FwBaseFree(v16);
        v16 = 0;
      }
      a1 = (_QWORD *)*a1;
    }
  }
  FwBaseFree(v17);
  FwBaseFree(v16);
  return v8;
}

```

## disassembly

```asm
0x180010e50  mov     [rsp+arg_8], rbx
0x180010e55  push    rbp
0x180010e56  push    rsi
0x180010e57  push    rdi
0x180010e58  push    r14
0x180010e5a  push    r15
0x180010e5c  sub     rsp, 40h
0x180010e60  mov     rax, cs:__security_cookie
0x180010e67  xor     rax, rsp
0x180010e6a  mov     [rsp+68h+var_38], rax
0x180010e6f  mov     r15d, r9d
0x180010e72  mov     rdi, r8
0x180010e75  mov     r14d, edx
0x180010e78  mov     rbx, rcx
0x180010e7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180010e82  lea     rax, WPP_GLOBAL_Control
0x180010e89  cmp     rcx, rax
0x180010e8c  jnz     loc_180010FC8
0x180010e92  xor     esi, esi
0x180010e94  lea     r8, [rsp+68h+var_40]; unsigned __int16 **
0x180010e99  mov     rcx, rdi; unsigned __int16 *
0x180010e9c  mov     [rsp+68h+var_40], rsi
0x180010ea1  mov     [rsp+68h+var_48], rsi
0x180010ea6  call    ?FwTryResolveString@@YAJPEBGHPEAPEAG@Z; FwTryResolveString(ushort const *,int,ushort * *)
0x180010eab  test    eax, eax
0x180010ead  js      loc_180010FEC
0x180010eb3  xor     edi, edi
0x180010eb5  cmp     edi, r14d
0x180010eb8  jnb     loc_180010F84
0x180010ebe  test    rsi, rsi
0x180010ec1  jnz     loc_180010F84
0x180010ec7  mov     edx, r15d
0x180010eca  mov     rcx, rbx
0x180010ecd  call    ?FwIsValidRule@FwRule@@SAHQEAU_tag_FW_RULE@@W4FwPolicyViewFlags@@@Z; FwRule::FwIsValidRule(_tag_FW_RULE * const,FwPolicyViewFlags)
0x180010ed2  test    eax, eax
0x180010ed4  jz      short loc_180010F36
0x180010ed6  mov     rbp, [rbx+18h]
0x180010eda  cmp     word ptr [rbp+0], 40h ; '@'
0x180010edf  jnz     short loc_180010F40
0x180010ee1  lea     rdx, [rsp+68h+var_48]
0x180010ee6  mov     rcx, rbp
0x180010ee9  call    cs:__imp_FwLoadIndirectString
0x180010ef0  nop     dword ptr [rax+rax+00h]
0x180010ef5  test    eax, eax
0x180010ef7  js      short loc_180010F40
0x180010ef9  mov     rdx, [rsp+68h+var_48]
0x180010efe  mov     rcx, [rsp+68h+var_40]
0x180010f03  call    cs:__imp__o__wcsicmp
0x180010f0a  nop     dword ptr [rax+rax+00h]
0x180010f0f  mov     ecx, eax
0x180010f11  mov     rsi, rbx
0x180010f14  xor     eax, eax
0x180010f16  test    ecx, ecx
0x180010f18  mov     rcx, [rsp+68h+var_48]
0x180010f1d  cmovnz  rsi, rax
0x180010f21  call    cs:__imp_FwBaseFree
0x180010f28  nop     dword ptr [rax+rax+00h]
0x180010f2d  mov     [rsp+68h+var_48], 0
0x180010f36  mov     rbx, [rbx]
0x180010f39  inc     edi
0x180010f3b  jmp     loc_180010EB5
0x180010f40  lea     rdx, [rsp+68h+var_48]
0x180010f45  mov     rcx, rbp
0x180010f48  call    cs:__imp_FwStringCopy
0x180010f4f  nop     dword ptr [rax+rax+00h]
0x180010f54  mov     ebp, eax
0x180010f56  test    eax, eax
0x180010f58  jns     short loc_180010EF9
0x180010f5a  mov     edx, eax
0x180010f5c  lea     rcx, aFwtryresolvest; "FwTryResolveString"
0x180010f63  call    cs:__imp_FwReportReturnError
0x180010f6a  nop     dword ptr [rax+rax+00h]
0x180010f6f  mov     edx, ebp
0x180010f71  lea     rcx, aFwruleFwfindma; "FwRule::FwFindMatchingRuleWithLocRuleNa"...
0x180010f78  call    cs:__imp_FwReportReturnError
0x180010f7f  nop     dword ptr [rax+rax+00h]
0x180010f84  mov     rcx, [rsp+68h+var_40]
0x180010f89  call    cs:__imp_FwBaseFree
0x180010f90  nop     dword ptr [rax+rax+00h]
0x180010f95  mov     rcx, [rsp+68h+var_48]
0x180010f9a  call    cs:__imp_FwBaseFree
0x180010fa1  nop     dword ptr [rax+rax+00h]
0x180010fa6  mov     rax, rsi
0x180010fa9  mov     rcx, [rsp+68h+var_38]
0x180010fae  xor     rcx, rsp; StackCookie
0x180010fb1  call    __security_check_cookie
0x180010fb6  mov     rbx, [rsp+68h+arg_8]
0x180010fbb  add     rsp, 40h
0x180010fbf  pop     r15
0x180010fc1  pop     r14
0x180010fc3  pop     rdi
0x180010fc4  pop     rsi
0x180010fc5  pop     rbp
0x180010fc6  retn
0x180010fc8  test    byte ptr [rcx+1Ch], 8
0x180010fcc  jz      loc_180010E92
0x180010fd2  mov     rcx, [rcx+10h]
0x180010fd6  lea     r8, WPP_92d7822da2e63f0d2b29182cb9b878d1_Traceguids
0x180010fdd  mov     edx, 62h ; 'b'
0x180010fe2  call    WPP_SF_
0x180010fe7  jmp     loc_180010E92
0x180010fec  mov     edx, eax
0x180010fee  jmp     short loc_180010F71
```
