# FwFindMatchingAppRule(_tag_FW_RULE * const,ulong,ushort const *,ushort)

- ea: `0x18000328c`
- end: `0x18000339b`
- name: `?FwFindMatchingAppRule@@YAPEAU_tag_FW_RULE@@QEAU1@KPEBGG@Z`
- size: `271`
- prototype: `struct _tag_FW_RULE *__fastcall(struct _tag_FW_RULE *const, unsigned int, const unsigned __int16 *, unsigned __int16)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003080`

## callees

- `0x18000328c`
- `0x1800294b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180003353`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180003353`
- `fwbase!FwBaseFree` at `0x1800032f8`
- `fwbase!FwBaseFree` at `0x1800032f8`
- `fwbase!FwGetExpandedCanonicalLongPathName` at `0x180003335`
- `fwbase!FwGetExpandedCanonicalLongPathName` at `0x180003335`
- `fwbase!IsRuleOldAuthApp` at `0x180003314`
- `fwbase!IsRuleOldAuthApp` at `0x180003314`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x1800032e3`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x1800032e3`

## pseudocode

```c
struct _tag_FW_RULE *__fastcall FwFindMatchingAppRule(
        struct _tag_FW_RULE *const a1,
        unsigned int a2,
        const unsigned __int16 *a3,
        __int16 a4)
{
  unsigned int i; // edi
  BOOL v9; // esi
  __int64 v11; // [rsp+20h] [rbp-48h] BYREF
  int v12; // [rsp+28h] [rbp-40h] BYREF

  for ( i = 0; i < a2; ++i )
  {
    v11 = 0;
    v12 = 0;
    v9 = 0;
    if ( (unsigned int)IsRuleOpenPortOrAuthApp(a1)
      && (unsigned int)IsRuleOldAuthApp(a1)
      && (int)FwGetExpandedCanonicalLongPathName(*((_QWORD *)a1 + 34), &v11, &v12) >= 0
      && v12 )
    {
      v9 = _o__wcsicmp(a3, v11) == 0;
    }
    FwBaseFree(v11);
    if ( v9 && a4 == *((_WORD *)a1 + 24) )
      return a1;
    a1 = *(struct _tag_FW_RULE *const *)a1;
  }
  return 0;
}

```

## disassembly

```asm
0x18000328c  mov     [rsp+arg_8], rbx
0x180003291  mov     [rsp+arg_18], rbp
0x180003296  push    rsi
0x180003297  push    rdi
0x180003298  push    r13
0x18000329a  push    r14
0x18000329c  push    r15
0x18000329e  sub     rsp, 40h
0x1800032a2  mov     rax, cs:__security_cookie
0x1800032a9  xor     rax, rsp
0x1800032ac  mov     [rsp+68h+var_38], rax
0x1800032b1  xor     edi, edi
0x1800032b3  movzx   ebp, r9w
0x1800032b7  mov     r15, r8
0x1800032ba  mov     r14d, edx
0x1800032bd  mov     rbx, rcx
0x1800032c0  lea     r13d, [rdi+1]
0x1800032c4  cmp     edi, r14d
0x1800032c7  jnb     loc_180003372
0x1800032cd  mov     rcx, rbx
0x1800032d0  mov     [rsp+68h+var_48], 0
0x1800032d9  mov     [rsp+68h+var_40], 0
0x1800032e1  xor     esi, esi
0x1800032e3  call    cs:__imp_IsRuleOpenPortOrAuthApp
0x1800032ea  nop     dword ptr [rax+rax+00h]
0x1800032ef  test    eax, eax
0x1800032f1  jnz     short loc_180003311
0x1800032f3  mov     rcx, [rsp+68h+var_48]
0x1800032f8  call    cs:__imp_FwBaseFree
0x1800032ff  nop     dword ptr [rax+rax+00h]
0x180003304  cmp     esi, r13d
0x180003307  jz      short loc_180003367
0x180003309  mov     rbx, [rbx]
0x18000330c  add     edi, r13d
0x18000330f  jmp     short loc_1800032C4
0x180003311  mov     rcx, rbx
0x180003314  call    cs:__imp_IsRuleOldAuthApp
0x18000331b  nop     dword ptr [rax+rax+00h]
0x180003320  test    eax, eax
0x180003322  jz      short loc_1800032F3
0x180003324  mov     rcx, [rbx+110h]
0x18000332b  lea     r8, [rsp+68h+var_40]
0x180003330  lea     rdx, [rsp+68h+var_48]
0x180003335  call    cs:__imp_FwGetExpandedCanonicalLongPathName
0x18000333c  nop     dword ptr [rax+rax+00h]
0x180003341  test    eax, eax
0x180003343  js      short loc_1800032F3
0x180003345  cmp     [rsp+68h+var_40], esi
0x180003349  jz      short loc_1800032F3
0x18000334b  mov     rdx, [rsp+68h+var_48]
0x180003350  mov     rcx, r15
0x180003353  call    cs:__imp__o__wcsicmp
0x18000335a  nop     dword ptr [rax+rax+00h]
0x18000335f  test    eax, eax
0x180003361  cmovz   esi, r13d
0x180003365  jmp     short loc_1800032F3
0x180003367  cmp     bp, [rbx+30h]
0x18000336b  jnz     short loc_180003309
0x18000336d  mov     rax, rbx
0x180003370  jmp     short loc_180003374
0x180003372  xor     eax, eax
0x180003374  mov     rcx, [rsp+68h+var_38]
0x180003379  xor     rcx, rsp; StackCookie
0x18000337c  call    __security_check_cookie
0x180003381  lea     r11, [rsp+68h+var_28]
0x180003386  mov     rbx, [r11+38h]
0x18000338a  mov     rbp, [r11+48h]
0x18000338e  mov     rsp, r11
0x180003391  pop     r15
0x180003393  pop     r14
0x180003395  pop     r13
0x180003397  pop     rdi
0x180003398  pop     rsi
0x180003399  retn
```
