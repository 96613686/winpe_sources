# _CMSMQRuleHandler::InvokeCOMComponent_::_1_::catch$17

- ea: `0x18001f3e7`
- end: `0x18001f502`
- name: `_CMSMQRuleHandler::InvokeCOMComponent_::_1_::catch$17`
- size: `283`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004d20`
- `0x180009c74`
- `0x180014d30`
- `0x18001f3e7`

## pseudocode

```c
__int64 __fastcall CMSMQRuleHandler::InvokeCOMComponent_::_1_::catch_17(__int64 a1, __int64 a2)
{
  __int64 v3; // rcx
  wchar_t *v4; // r8
  int v5; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v3 = *(_QWORD *)(a2 + 256);
    if ( *(_QWORD *)(v3 + 144) )
      v4 = **(wchar_t ***)(v3 + 144);
    else
      v4 = 0;
    WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), v4);
  }
  *(_WORD *)(a2 + 256) = 220;
  *(_DWORD *)(a2 + 272) = -1072820728;
  if ( g_pMSMQErrorLoggingTrace )
  {
    v5 = mqwcslen(L"trigobjs/rulehdlr");
    CMSMQTrace::MSMQTraceEvent(
      (__int64)g_pMSMQErrorLoggingTrace,
      1,
      1u,
      2LL * (unsigned int)(v5 + 1),
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
0x18001f3e7  mov     [rsp+arg_8], rdx
0x18001f3ec  push    rbp
0x18001f3ed  sub     rsp, 60h
0x18001f3f1  mov     rbp, rdx
0x18001f3f4  lea     rax, WPP_GLOBAL_Control
0x18001f3fb  mov     r10, cs:WPP_GLOBAL_Control
0x18001f402  cmp     r10, rax
0x18001f405  jz      short loc_18001F461
0x18001f407  test    byte ptr [r10+1Ch], 1
0x18001f40c  jz      short loc_18001F461
0x18001f40e  mov     rcx, [rbp+100h]
0x18001f415  cmp     qword ptr [rcx+90h], 0
0x18001f41d  jz      short loc_18001F42B
0x18001f41f  mov     rax, [rcx+90h]
0x18001f426  mov     r8, [rax]
0x18001f429  jmp     short loc_18001F42E
0x18001f42b  xor     r8d, r8d
0x18001f42e  cmp     qword ptr [rcx+0A0h], 0
0x18001f436  jz      short loc_18001F444
0x18001f438  mov     rax, [rcx+0A0h]
0x18001f43f  mov     r9, [rax]
0x18001f442  jmp     short loc_18001F447
0x18001f444  xor     r9d, r9d
0x18001f447  mov     edx, 1Ah
0x18001f44c  mov     [rsp+68h+var_48], r8; wchar_t *
0x18001f451  lea     r8, WPP_07c04997ef9c358328a47f0c936100cf_Traceguids
0x18001f458  mov     rcx, [r10+10h]; LoggerHandle
0x18001f45c  call    WPP_SF_SS
0x18001f461  mov     eax, 0DCh
0x18001f466  mov     [rbp+100h], ax
0x18001f46d  mov     dword ptr [rbp+110h], 0C00E0E08h
0x18001f477  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, 0; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18001f47f  jz      short loc_18001F4F1
0x18001f481  lea     rcx, aTrigobjsRulehd; "trigobjs/rulehdlr"
0x18001f488  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18001f48d  lea     r9d, [rax+1]
0x18001f491  add     r9, r9
0x18001f494  mov     [rsp+68h+var_18], 0
0x18001f49d  mov     [rsp+68h+var_20], 0
0x18001f4a6  lea     rax, [rbp+110h]
0x18001f4ad  mov     [rsp+68h+var_28], rax
0x18001f4b2  mov     [rsp+68h+var_30], 4
0x18001f4bb  lea     rax, [rbp+100h]
0x18001f4c2  mov     [rsp+68h+var_38], rax
0x18001f4c7  mov     [rsp+68h+var_40], 2
0x18001f4d0  lea     rax, aTrigobjsRulehd; "trigobjs/rulehdlr"
0x18001f4d7  mov     [rsp+68h+var_48], rax
0x18001f4dc  mov     edx, 1
0x18001f4e1  mov     r8d, edx
0x18001f4e4  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18001f4eb  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x18001f4f0  nop
0x18001f4f1  mov     rax, 0
0x18001f4fb  add     rsp, 60h
0x18001f4ff  pop     rbp
0x18001f500  retn
```
