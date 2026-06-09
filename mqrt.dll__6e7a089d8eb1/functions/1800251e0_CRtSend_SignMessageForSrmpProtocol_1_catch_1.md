# _CRtSend::SignMessageForSrmpProtocol_::_1_::catch$1

- ea: `0x1800251e0`
- end: `0x180025251`
- name: `_CRtSend::SignMessageForSrmpProtocol_::_1_::catch$1`
- size: `113`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000a33c`
- `0x180013c74`
- `0x1800251e0`

## pseudocode

```c
__int64 __fastcall CRtSend::SignMessageForSrmpProtocol_::_1_::catch_1(__int64 a1, __int64 a2)
{
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 29, &WPP_8fb0d8d8e9e23c3edf86dbd32a942155_Traceguids);
  *(_DWORD *)(a2 + 64) = -1072824314;
  LogMsgHR(-1072824314, (wchar_t *)L"rt/CRtSend", 0xA8u);
  return 0;
}

```

## disassembly

```asm
0x1800251e0  mov     [rsp+arg_8], rdx
0x1800251e5  push    rbp
0x1800251e6  sub     rsp, 20h
0x1800251ea  mov     rbp, rdx
0x1800251ed  lea     rax, WPP_GLOBAL_Control
0x1800251f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800251fb  cmp     rcx, rax
0x1800251fe  jz      short loc_180025221
0x180025200  test    byte ptr [rcx+10Ch], 1
0x180025207  jz      short loc_180025221
0x180025209  mov     edx, 1Dh
0x18002520e  lea     r8, WPP_8fb0d8d8e9e23c3edf86dbd32a942155_Traceguids
0x180025215  mov     rcx, [rcx+100h]
0x18002521c  call    WPP_SF_
0x180025221  mov     dword ptr [rbp+40h], 0C00E0006h
0x180025228  mov     r8d, 0A8h; unsigned __int16
0x18002522e  lea     rdx, aRtCrtsend; "rt/CRtSend"
0x180025235  mov     ecx, 0C00E0006h; int
0x18002523a  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18002523f  nop
0x180025240  mov     rax, 0
0x18002524a  add     rsp, 20h
0x18002524e  pop     rbp
0x18002524f  retn
```
