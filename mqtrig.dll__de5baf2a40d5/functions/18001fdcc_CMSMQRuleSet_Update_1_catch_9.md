# _CMSMQRuleSet::Update_::_1_::catch$9

- ea: `0x18001fdcc`
- end: `0x18001fea6`
- name: `_CMSMQRuleSet::Update_::_1_::catch$9`
- size: `218`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180004d20`
- `0x18000bd0c`
- `0x18000c62c`
- `0x180014d30`
- `0x18001fdcc`

## pseudocode

```c
__int64 __fastcall CMSMQRuleSet::Update_::_1_::catch_9(__int64 a1, __int64 a2)
{
  CMSMQRuleSet *v3; // rcx
  int v4; // eax

  v3 = (CMSMQRuleSet *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_1456eb79f9cf3571852fcbdd2cc7a63a_Traceguids);
  CMSMQRuleSet::SetComClassError(v3, 0xC00E0E06);
  *(_WORD *)(a2 + 96) = 400;
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
0x18001fdcc  mov     [rsp+arg_8], rdx
0x18001fdd1  push    rbp
0x18001fdd2  sub     rsp, 60h
0x18001fdd6  mov     rbp, rdx
0x18001fdd9  lea     rax, WPP_GLOBAL_Control
0x18001fde0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fde7  cmp     rcx, rax
0x18001fdea  jz      short loc_18001FE07
0x18001fdec  test    byte ptr [rcx+1Ch], 1
0x18001fdf0  jz      short loc_18001FE07
0x18001fdf2  mov     edx, 33h ; '3'
0x18001fdf7  lea     r8, WPP_1456eb79f9cf3571852fcbdd2cc7a63a_Traceguids
0x18001fdfe  mov     rcx, [rcx+10h]
0x18001fe02  call    WPP_SF_
0x18001fe07  mov     edx, 0C00E0E06h; int
0x18001fe0c  call    ?SetComClassError@CMSMQRuleSet@@AEAAXJ@Z; CMSMQRuleSet::SetComClassError(long)
0x18001fe11  mov     eax, 190h
0x18001fe16  mov     [rbp+60h], ax
0x18001fe1a  mov     dword ptr [rbp+68h], 0C00E0E06h
0x18001fe21  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, 0; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18001fe29  jz      short loc_18001FE95
0x18001fe2b  lea     rcx, aTrigobjsRulese; "trigobjs/ruleset"
0x18001fe32  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18001fe37  lea     r9d, [rax+1]
0x18001fe3b  add     r9, r9
0x18001fe3e  mov     [rsp+68h+var_18], 0
0x18001fe47  mov     [rsp+68h+var_20], 0
0x18001fe50  lea     rax, [rbp+68h]
0x18001fe54  mov     [rsp+68h+var_28], rax
0x18001fe59  mov     [rsp+68h+var_30], 4
0x18001fe62  lea     rax, [rbp+60h]
0x18001fe66  mov     [rsp+68h+var_38], rax
0x18001fe6b  mov     [rsp+68h+var_40], 2
0x18001fe74  lea     rax, aTrigobjsRulese; "trigobjs/ruleset"
0x18001fe7b  mov     [rsp+68h+var_48], rax
0x18001fe80  mov     edx, 1
0x18001fe85  mov     r8d, edx
0x18001fe88  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18001fe8f  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x18001fe94  nop
0x18001fe95  mov     rax, 0
0x18001fe9f  add     rsp, 60h
0x18001fea3  pop     rbp
0x18001fea4  retn
```
