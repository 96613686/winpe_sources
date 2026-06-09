# _CRtSend::SignMessageForSrmpProtocol_::_1_::catch$0

- ea: `0x18002514f`
- end: `0x1800251da`
- name: `_CRtSend::SignMessageForSrmpProtocol_::_1_::catch$0`
- size: `139`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800087f8`
- `0x180013c74`
- `0x18002514f`
- `0x180026010`

## pseudocode

```c
__int64 __fastcall CRtSend::SignMessageForSrmpProtocol_::_1_::catch_0(__int64 a1, __int64 a2)
{
  unsigned int v3; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
  {
    v3 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a2 + 32) + 16LL))(*(_QWORD *)(a2 + 32));
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 28, &WPP_8fb0d8d8e9e23c3edf86dbd32a942155_Traceguids, v3);
  }
  *(_DWORD *)(a2 + 64) = -1072824272;
  LogMsgHR(-1072824272, (wchar_t *)L"rt/CRtSend", 0xA7u);
  return 0;
}

```

## disassembly

```asm
0x18002514f  mov     [rsp+arg_8], rdx
0x180025154  push    rbp
0x180025155  sub     rsp, 20h
0x180025159  mov     rbp, rdx
0x18002515c  lea     rcx, WPP_GLOBAL_Control
0x180025163  mov     rax, cs:WPP_GLOBAL_Control
0x18002516a  cmp     rax, rcx
0x18002516d  jz      short loc_1800251AA
0x18002516f  test    byte ptr [rax+10Ch], 1
0x180025176  jz      short loc_1800251AA
0x180025178  mov     rcx, [rbp+20h]
0x18002517c  mov     rax, [rcx]
0x18002517f  mov     rax, [rax+10h]
0x180025183  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025188  mov     edx, 1Ch
0x18002518d  mov     r9d, eax
0x180025190  lea     r8, WPP_8fb0d8d8e9e23c3edf86dbd32a942155_Traceguids
0x180025197  mov     rcx, cs:WPP_GLOBAL_Control
0x18002519e  mov     rcx, [rcx+100h]
0x1800251a5  call    WPP_SF_d
0x1800251aa  mov     dword ptr [rbp+40h], 0C00E0030h
0x1800251b1  mov     r8d, 0A7h; unsigned __int16
0x1800251b7  lea     rdx, aRtCrtsend; "rt/CRtSend"
0x1800251be  mov     ecx, 0C00E0030h; int
0x1800251c3  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800251c8  nop
0x1800251c9  mov     rax, 0
0x1800251d3  add     rsp, 20h
0x1800251d7  pop     rbp
0x1800251d8  retn
```
