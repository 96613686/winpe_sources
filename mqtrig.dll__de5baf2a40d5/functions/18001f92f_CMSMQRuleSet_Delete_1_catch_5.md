# _CMSMQRuleSet::Delete_::_1_::catch$5

- ea: `0x18001f92f`
- end: `0x18001fa09`
- name: `_CMSMQRuleSet::Delete_::_1_::catch$5`
- size: `218`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180004d20`
- `0x18000bd0c`
- `0x18000c62c`
- `0x180014d30`
- `0x18001f92f`

## pseudocode

```c
__int64 __fastcall CMSMQRuleSet::Delete_::_1_::catch_5(__int64 a1, __int64 a2)
{
  CMSMQRuleSet *v3; // rcx
  int v4; // eax

  v3 = (CMSMQRuleSet *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_1456eb79f9cf3571852fcbdd2cc7a63a_Traceguids);
  CMSMQRuleSet::SetComClassError(v3, 0xC00E0E06);
  *(_WORD *)(a2 + 96) = 230;
  *(_DWORD *)(a2 + 104) = -1072820730;
  if ( g_pMSMQErrorLoggingTrace )
  {
    v4 = mqwcslen(L"trigobjs/ruleset");
    CMSMQTrace::MSMQTraceEvent(
      (__int64)g_pMSMQErrorLoggingTrace,
      1,
      1u,
      2LL * (unsigned int)(v4 + 1),
      L"trigobjs/ruleset",
      2,
      a2 + 96,
      4,
      a2 + 104,
      0,
      0);
  }
  return 0;
}

```

## disassembly

```asm
0x18001f92f  mov     [rsp+arg_8], rdx
0x18001f934  push    rbp
0x18001f935  sub     rsp, 60h
0x18001f939  mov     rbp, rdx
0x18001f93c  lea     rax, WPP_GLOBAL_Control
0x18001f943  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f94a  cmp     rcx, rax
0x18001f94d  jz      short loc_18001F96A
0x18001f94f  test    byte ptr [rcx+1Ch], 1
0x18001f953  jz      short loc_18001F96A
0x18001f955  mov     edx, 21h ; '!'
0x18001f95a  lea     r8, WPP_1456eb79f9cf3571852fcbdd2cc7a63a_Traceguids
0x18001f961  mov     rcx, [rcx+10h]
0x18001f965  call    WPP_SF_
0x18001f96a  mov     edx, 0C00E0E06h; int
0x18001f96f  call    ?SetComClassError@CMSMQRuleSet@@AEAAXJ@Z; CMSMQRuleSet::SetComClassError(long)
0x18001f974  mov     eax, 0E6h
0x18001f979  mov     [rbp+60h], ax
0x18001f97d  mov     dword ptr [rbp+68h], 0C00E0E06h
0x18001f984  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, 0; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18001f98c  jz      short loc_18001F9F8
0x18001f98e  lea     rcx, aTrigobjsRulese; "trigobjs/ruleset"
0x18001f995  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18001f99a  lea     r9d, [rax+1]
0x18001f99e  add     r9, r9
0x18001f9a1  mov     [rsp+68h+var_18], 0
0x18001f9aa  mov     [rsp+68h+var_20], 0
0x18001f9b3  lea     rax, [rbp+68h]
0x18001f9b7  mov     [rsp+68h+var_28], rax
0x18001f9bc  mov     [rsp+68h+var_30], 4
0x18001f9c5  lea     rax, [rbp+60h]
0x18001f9c9  mov     [rsp+68h+var_38], rax
0x18001f9ce  mov     [rsp+68h+var_40], 2
0x18001f9d7  lea     rax, aTrigobjsRulese; "trigobjs/ruleset"
0x18001f9de  mov     [rsp+68h+var_48], rax
0x18001f9e3  mov     edx, 1
0x18001f9e8  mov     r8d, edx
0x18001f9eb  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18001f9f2  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x18001f9f7  nop
0x18001f9f8  mov     rax, 0
0x18001fa02  add     rsp, 60h
0x18001fa06  pop     rbp
0x18001fa07  retn
```
