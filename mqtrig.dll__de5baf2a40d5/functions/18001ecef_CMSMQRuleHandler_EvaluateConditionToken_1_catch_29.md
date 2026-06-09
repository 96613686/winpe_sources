# _CMSMQRuleHandler::EvaluateConditionToken_::_1_::catch$29

- ea: `0x18001ecef`
- end: `0x18001ee14`
- name: `_CMSMQRuleHandler::EvaluateConditionToken_::_1_::catch$29`
- size: `293`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180004d20`
- `0x180009c74`
- `0x180014d30`
- `0x18001ecef`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18001ed00`
- `OLEAUT32!__imp_VariantClear` at `0x18001ed00`

## pseudocode

```c
__int64 __fastcall CMSMQRuleHandler::EvaluateConditionToken_::_1_::catch_29(__int64 a1, __int64 a2)
{
  __int64 v3; // rcx
  wchar_t *v4; // r8
  int v5; // eax

  VariantClear((VARIANTARG *)(a2 + 120));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v3 = *(_QWORD *)(a2 + 272);
    if ( *(_QWORD *)(v3 + 144) )
      v4 = **(wchar_t ***)(v3 + 144);
    else
      v4 = 0;
    WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), v4);
  }
  *(_WORD *)(a2 + 280) = 80;
  *(_DWORD *)(a2 + 296) = -1072820729;
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
      a2 + 280,
      4,
      a2 + 296,
      0,
      0);
  }
  return 0;
}

```

## disassembly

```asm
0x18001ecef  mov     [rsp+arg_8], rdx
0x18001ecf4  push    rbp
0x18001ecf5  sub     rsp, 60h
0x18001ecf9  mov     rbp, rdx
0x18001ecfc  lea     rcx, [rbp+78h]; pvarg
0x18001ed00  call    cs:__imp_VariantClear
0x18001ed06  lea     rax, WPP_GLOBAL_Control
0x18001ed0d  mov     r10, cs:WPP_GLOBAL_Control
0x18001ed14  cmp     r10, rax
0x18001ed17  jz      short loc_18001ED73
0x18001ed19  test    byte ptr [r10+1Ch], 1
0x18001ed1e  jz      short loc_18001ED73
0x18001ed20  mov     rcx, [rbp+110h]
0x18001ed27  cmp     qword ptr [rcx+90h], 0
0x18001ed2f  jz      short loc_18001ED3D
0x18001ed31  mov     rax, [rcx+90h]
0x18001ed38  mov     r8, [rax]
0x18001ed3b  jmp     short loc_18001ED40
0x18001ed3d  xor     r8d, r8d
0x18001ed40  cmp     qword ptr [rcx+98h], 0
0x18001ed48  jz      short loc_18001ED56
0x18001ed4a  mov     rax, [rcx+98h]
0x18001ed51  mov     r9, [rax]
0x18001ed54  jmp     short loc_18001ED59
0x18001ed56  xor     r9d, r9d
0x18001ed59  mov     edx, 14h
0x18001ed5e  mov     [rsp+68h+var_48], r8; wchar_t *
0x18001ed63  lea     r8, WPP_07c04997ef9c358328a47f0c936100cf_Traceguids
0x18001ed6a  mov     rcx, [r10+10h]; LoggerHandle
0x18001ed6e  call    WPP_SF_SS
0x18001ed73  mov     eax, 50h ; 'P'
0x18001ed78  mov     [rbp+118h], ax
0x18001ed7f  mov     dword ptr [rbp+128h], 0C00E0E07h
0x18001ed89  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, 0; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18001ed91  jz      short loc_18001EE03
0x18001ed93  lea     rcx, aTrigobjsRulehd; "trigobjs/rulehdlr"
0x18001ed9a  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18001ed9f  lea     r9d, [rax+1]
0x18001eda3  add     r9, r9
0x18001eda6  mov     [rsp+68h+var_18], 0
0x18001edaf  mov     [rsp+68h+var_20], 0
0x18001edb8  lea     rax, [rbp+128h]
0x18001edbf  mov     [rsp+68h+var_28], rax
0x18001edc4  mov     [rsp+68h+var_30], 4
0x18001edcd  lea     rax, [rbp+118h]
0x18001edd4  mov     [rsp+68h+var_38], rax
0x18001edd9  mov     [rsp+68h+var_40], 2
0x18001ede2  lea     rax, aTrigobjsRulehd; "trigobjs/rulehdlr"
0x18001ede9  mov     [rsp+68h+var_48], rax
0x18001edee  mov     edx, 1
0x18001edf3  mov     r8d, edx
0x18001edf6  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18001edfd  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x18001ee02  nop
0x18001ee03  mov     rax, 0
0x18001ee0d  add     rsp, 60h
0x18001ee11  pop     rbp
0x18001ee12  retn
```
