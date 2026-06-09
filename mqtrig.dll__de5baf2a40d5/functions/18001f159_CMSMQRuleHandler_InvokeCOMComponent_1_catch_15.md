# _CMSMQRuleHandler::InvokeCOMComponent_::_1_::catch$15

- ea: `0x18001f159`
- end: `0x18001f2df`
- name: `_CMSMQRuleHandler::InvokeCOMComponent_::_1_::catch$15`
- size: `390`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004d20`
- `0x180005d74`
- `0x180009ab0`
- `0x180009bb0`
- `0x180014920`
- `0x180014930`
- `0x180014d30`
- `0x18001f159`

## pseudocode

```c
__int64 __fastcall CMSMQRuleHandler::InvokeCOMComponent_::_1_::catch_15(__int64 a1, __int64 a2)
{
  __int64 v3; // rsi
  _QWORD *v4; // rax
  int v5; // edi
  __int64 v6; // rbx
  char *v7; // rax
  struct IErrorInfo *v8; // rdx
  char *v9; // rcx
  int v10; // eax

  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
  {
    v5 = *(_DWORD *)(a2 + 280);
  }
  else
  {
    v3 = *(_QWORD *)(a2 + 184);
    v4 = _com_error::Description(v3, (_QWORD *)(a2 + 272));
    LOBYTE(v5) = 1;
    *(_DWORD *)(a2 + 280) = 1;
    if ( *v4 )
    {
      v6 = *v4;
      if ( !*(_QWORD *)(*v4 + 8LL) )
      {
        v7 = _com_util::ConvertBSTRToString(*(LPCWCH *)v6);
        *(_QWORD *)(v6 + 8) = v7;
        if ( !v7 )
        {
          if ( *(_QWORD *)v6 )
            _com_issue_error(-2147024882, v8);
        }
      }
      v9 = *(char **)(v6 + 8);
    }
    else
    {
      v9 = 0;
    }
    WPP_SF_SDs(*((_QWORD *)WPP_GLOBAL_Control + 2), *(_DWORD *)(v3 + 8), v9);
  }
  if ( (v5 & 1) != 0 )
    _bstr_t::_Free((_bstr_t *)(a2 + 272));
  *(_WORD *)(a2 + 256) = 200;
  *(_DWORD *)(a2 + 272) = -1072820725;
  if ( g_pMSMQErrorLoggingTrace )
  {
    v10 = mqwcslen(L"trigobjs/rulehdlr");
    CMSMQTrace::MSMQTraceEvent(
      (__int64)g_pMSMQErrorLoggingTrace,
      1,
      1u,
      2LL * (unsigned int)(v10 + 1),
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
0x18001f159  mov     [rsp+arg_8], rdx
0x18001f15e  push    rbx
0x18001f15f  push    rbp
0x18001f160  push    rsi
0x18001f161  push    rdi
0x18001f162  sub     rsp, 68h
0x18001f166  mov     rbp, rdx
0x18001f169  lea     rcx, WPP_GLOBAL_Control
0x18001f170  mov     rax, cs:WPP_GLOBAL_Control
0x18001f177  cmp     rax, rcx
0x18001f17a  jz      loc_18001F223
0x18001f180  test    byte ptr [rax+1Ch], 1
0x18001f184  jz      loc_18001F223
0x18001f18a  lea     rdx, [rbp+110h]
0x18001f191  mov     rsi, [rbp+0B8h]
0x18001f198  mov     rcx, rsi
0x18001f19b  call    ?Description@_com_error@@QEBA?AV_bstr_t@@XZ; _com_error::Description(void)
0x18001f1a0  nop
0x18001f1a1  mov     edi, 1
0x18001f1a6  mov     [rbp+118h], edi
0x18001f1ac  cmp     qword ptr [rax], 0
0x18001f1b0  jz      short loc_18001F1E3
0x18001f1b2  mov     rbx, [rax]
0x18001f1b5  cmp     qword ptr [rbx+8], 0
0x18001f1ba  jnz     short loc_18001F1DD
0x18001f1bc  mov     rcx, [rbx]; lpWideCharStr
0x18001f1bf  call    ?ConvertBSTRToString@_com_util@@YAPEADPEAG@Z; _com_util::ConvertBSTRToString(ushort *)
0x18001f1c4  mov     [rbx+8], rax
0x18001f1c8  test    rax, rax
0x18001f1cb  jnz     short loc_18001F1DD
0x18001f1cd  cmp     [rbx], rax
0x18001f1d0  jz      short loc_18001F1DD
0x18001f1d2  mov     ecx, 8007000Eh; int
0x18001f1d7  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18001f1dd  mov     rcx, [rbx+8]
0x18001f1e1  jmp     short loc_18001F1E5
0x18001f1e3  xor     ecx, ecx
0x18001f1e5  mov     edx, [rsi+8]
0x18001f1e8  mov     rax, [rbp+100h]
0x18001f1ef  cmp     qword ptr [rax+90h], 0
0x18001f1f7  jz      short loc_18001F205
0x18001f1f9  mov     rax, [rax+90h]
0x18001f200  mov     r9, [rax]
0x18001f203  jmp     short loc_18001F208
0x18001f205  xor     r9d, r9d
0x18001f208  mov     [rsp+88h+var_60], rcx; char *
0x18001f20d  mov     dword ptr [rsp+88h+var_68], edx; char
0x18001f211  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f218  mov     rcx, [rcx+10h]; LoggerHandle
0x18001f21c  call    WPP_SF_SDs
0x18001f221  jmp     short loc_18001F229
0x18001f223  mov     edi, [rbp+118h]
0x18001f229  test    dil, 1
0x18001f22d  jz      short loc_18001F23B
0x18001f22f  lea     rcx, [rbp+110h]; this
0x18001f236  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18001f23b  mov     eax, 0C8h
0x18001f240  mov     [rbp+100h], ax
0x18001f247  mov     dword ptr [rbp+110h], 0C00E0E0Bh
0x18001f251  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, 0; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18001f259  jz      short loc_18001F2CB
0x18001f25b  lea     rcx, aTrigobjsRulehd; "trigobjs/rulehdlr"
0x18001f262  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18001f267  lea     r9d, [rax+1]
0x18001f26b  add     r9, r9
0x18001f26e  mov     [rsp+88h+var_38], 0
0x18001f277  mov     [rsp+88h+var_40], 0
0x18001f280  lea     rax, [rbp+110h]
0x18001f287  mov     [rsp+88h+var_48], rax
0x18001f28c  mov     [rsp+88h+var_50], 4
0x18001f295  lea     rax, [rbp+100h]
0x18001f29c  mov     [rsp+88h+var_58], rax
0x18001f2a1  mov     [rsp+88h+var_60], 2
0x18001f2aa  lea     rax, aTrigobjsRulehd; "trigobjs/rulehdlr"
0x18001f2b1  mov     qword ptr [rsp+88h+var_68], rax
0x18001f2b6  mov     edx, 1
0x18001f2bb  mov     r8d, edx
0x18001f2be  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x18001f2c5  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x18001f2ca  nop
0x18001f2cb  mov     rax, 0
0x18001f2d5  add     rsp, 68h
0x18001f2d9  pop     rdi
0x18001f2da  pop     rsi
0x18001f2db  pop     rbp
0x18001f2dc  pop     rbx
0x18001f2dd  retn
```
