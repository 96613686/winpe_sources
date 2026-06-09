# FsmTpiControlFrameSendComplete

- ea: `0x140014e50`
- end: `0x140014ee4`
- name: `FsmTpiControlFrameSendComplete`
- size: `148`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140018054`

## callees

- `0x140002bd8`
- `0x140014e50`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140014e9f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140014e9f`

## pseudocode

```c
void __fastcall FsmTpiControlFrameSendComplete(PVOID Entry)
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x84) == 0x84 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 132, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids);
  ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)SstpFsmGlobalInfo + 1, Entry);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x84) == 0x84 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 133, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids);
}

```

## disassembly

```asm
0x140014e50  mov     [rsp+arg_0], rbx
0x140014e55  push    rsi
0x140014e56  sub     rsp, 20h
0x140014e5a  mov     rbx, rcx
0x140014e5d  mov     rcx, cs:WPP_GLOBAL_Control
0x140014e64  lea     rsi, WPP_GLOBAL_Control
0x140014e6b  cmp     rcx, rsi
0x140014e6e  jz      short loc_140014E91
0x140014e70  mov     eax, [rcx+2Ch]
0x140014e73  and     eax, 84h
0x140014e78  cmp     al, 84h
0x140014e7a  jnz     short loc_140014E91
0x140014e7c  mov     rcx, [rcx+18h]
0x140014e80  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x140014e87  mov     edx, 84h
0x140014e8c  call    WPP_SF_
0x140014e91  mov     rcx, cs:SstpFsmGlobalInfo
0x140014e98  mov     rdx, rbx; Entry
0x140014e9b  sub     rcx, 0FFFFFFFFFFFFFF80h; Lookaside
0x140014e9f  call    cs:__imp_ExFreeToNPagedLookasideList
0x140014ea6  nop     dword ptr [rax+rax+00h]
0x140014eab  mov     rcx, cs:WPP_GLOBAL_Control
0x140014eb2  cmp     rcx, rsi
0x140014eb5  jz      short loc_140014ED8
0x140014eb7  mov     eax, [rcx+2Ch]
0x140014eba  and     eax, 84h
0x140014ebf  cmp     al, 84h
0x140014ec1  jnz     short loc_140014ED8
0x140014ec3  mov     rcx, [rcx+18h]
0x140014ec7  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x140014ece  mov     edx, 85h
0x140014ed3  call    WPP_SF_
0x140014ed8  mov     rbx, [rsp+28h+arg_0]
0x140014edd  add     rsp, 20h
0x140014ee1  pop     rsi
0x140014ee2  retn
```
