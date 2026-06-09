# _SmsWapMsgHandler::CopyToPushRouterStructure_::_1_::catch$14

- ea: `0x1800119a9`
- end: `0x1800119ce`
- name: `_SmsWapMsgHandler::CopyToPushRouterStructure_::_1_::catch$14`
- size: `37`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
__int64 __fastcall SmsWapMsgHandler::CopyToPushRouterStructure_::_1_::catch_14(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 68) = -2147024882;
  return 0;
}

```

## disassembly

```asm
0x1800119a9  mov     [rsp+arg_8], rdx
0x1800119ae  push    rbp
0x1800119af  sub     rsp, 40h
0x1800119b3  mov     rbp, rdx
0x1800119b6  mov     dword ptr [rbp+44h], 8007000Eh
0x1800119bd  mov     rax, 0
0x1800119c7  add     rsp, 40h
0x1800119cb  pop     rbp
0x1800119cc  retn
```
