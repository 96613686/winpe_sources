# _CMSMQRuleHandler::InvokeCOMComponent_::_1_::catch$16

- ea: `0x18001f2e5`
- end: `0x18001f3e1`
- name: `_CMSMQRuleHandler::InvokeCOMComponent_::_1_::catch$16`
- size: `252`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004d20`
- `0x180004d88`
- `0x180014d30`
- `0x18001f2e5`

## pseudocode

```c
__int64 __fastcall CMSMQRuleHandler::InvokeCOMComponent_::_1_::catch_16(__int64 a1, __int64 a2)
{
  int v3; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2));
  *(_WORD *)(a2 + 256) = 210;
  *(_DWORD *)(a2 + 272) = -1072820730;
  if ( g_pMSMQErrorLoggingTrace )
  {
    v3 = mqwcslen(L"trigobjs/rulehdlr");
    CMSMQTrace::MSMQTraceEvent(
      (__int64)g_pMSMQErrorLoggingTrace,
      1,
      1u,
      2LL * (unsigned int)(v3 + 1),
      L"trigobjs/rulehdlr",
      2,
      a2 + 256,
      4,
      a2 + 272,
      0,
      0);
  }
  return 0;
}

```

## disassembly

```asm
0x18001f2e5  mov     [rsp+arg_8], rdx
0x18001f2ea  push    rbp
0x18001f2eb  sub     rsp, 60h
0x18001f2ef  mov     rbp, rdx
0x18001f2f2  lea     rax, WPP_GLOBAL_Control
0x18001f2f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f300  cmp     rcx, rax
0x18001f303  jz      short loc_18001F340
0x18001f305  test    byte ptr [rcx+1Ch], 1
0x18001f309  jz      short loc_18001F340
0x18001f30b  mov     rax, [rbp+100h]
0x18001f312  cmp     qword ptr [rax+90h], 0
0x18001f31a  jz      short loc_18001F328
0x18001f31c  mov     rax, [rax+90h]
0x18001f323  mov     r9, [rax]
0x18001f326  jmp     short loc_18001F32B
0x18001f328  xor     r9d, r9d
0x18001f32b  mov     edx, 19h
0x18001f330  lea     r8, WPP_07c04997ef9c358328a47f0c936100cf_Traceguids
0x18001f337  mov     rcx, [rcx+10h]; LoggerHandle
0x18001f33b  call    WPP_SF_S
0x18001f340  mov     eax, 0D2h
0x18001f345  mov     [rbp+100h], ax
0x18001f34c  mov     dword ptr [rbp+110h], 0C00E0E06h
0x18001f356  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, 0; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18001f35e  jz      short loc_18001F3D0
0x18001f360  lea     rcx, aTrigobjsRulehd; "trigobjs/rulehdlr"
0x18001f367  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18001f36c  lea     r9d, [rax+1]
0x18001f370  add     r9, r9
0x18001f373  mov     [rsp+68h+var_18], 0
0x18001f37c  mov     [rsp+68h+var_20], 0
0x18001f385  lea     rax, [rbp+110h]
0x18001f38c  mov     [rsp+68h+var_28], rax
0x18001f391  mov     [rsp+68h+var_30], 4
0x18001f39a  lea     rax, [rbp+100h]
0x18001f3a1  mov     [rsp+68h+var_38], rax
0x18001f3a6  mov     [rsp+68h+var_40], 2
0x18001f3af  lea     rax, aTrigobjsRulehd; "trigobjs/rulehdlr"
0x18001f3b6  mov     [rsp+68h+var_48], rax
0x18001f3bb  mov     edx, 1
0x18001f3c0  mov     r8d, edx
0x18001f3c3  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18001f3ca  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x18001f3cf  nop
0x18001f3d0  mov     rax, 0
0x18001f3da  add     rsp, 60h
0x18001f3de  pop     rbp
0x18001f3df  retn
```
