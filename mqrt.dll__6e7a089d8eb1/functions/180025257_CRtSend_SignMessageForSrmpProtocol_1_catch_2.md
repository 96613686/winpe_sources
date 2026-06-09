# _CRtSend::SignMessageForSrmpProtocol_::_1_::catch$2

- ea: `0x180025257`
- end: `0x1800252b0`
- name: `_CRtSend::SignMessageForSrmpProtocol_::_1_::catch$2`
- size: `89`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000a33c`
- `0x180025257`

## pseudocode

```c
__int64 __fastcall CRtSend::SignMessageForSrmpProtocol_::_1_::catch_2(__int64 a1, __int64 a2)
{
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 30, &WPP_8fb0d8d8e9e23c3edf86dbd32a942155_Traceguids);
  *(_DWORD *)(a2 + 64) = -1072824281;
  return 0;
}

```

## disassembly

```asm
0x180025257  mov     [rsp+arg_8], rdx
0x18002525c  push    rbp
0x18002525d  sub     rsp, 20h
0x180025261  mov     rbp, rdx
0x180025264  lea     rax, WPP_GLOBAL_Control
0x18002526b  mov     rcx, cs:WPP_GLOBAL_Control
0x180025272  cmp     rcx, rax
0x180025275  jz      short loc_180025298
0x180025277  test    byte ptr [rcx+10Ch], 1
0x18002527e  jz      short loc_180025298
0x180025280  mov     edx, 1Eh
0x180025285  lea     r8, WPP_8fb0d8d8e9e23c3edf86dbd32a942155_Traceguids
0x18002528c  mov     rcx, [rcx+100h]
0x180025293  call    WPP_SF_
0x180025298  mov     dword ptr [rbp+40h], 0C00E0027h
0x18002529f  mov     rax, 0
0x1800252a9  add     rsp, 20h
0x1800252ad  pop     rbp
0x1800252ae  retn
```
