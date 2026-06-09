# _SvcpServiceMain_::_1_::catch$0

- ea: `0x14001f025`
- end: `0x14001f072`
- name: `_SvcpServiceMain_::_1_::catch$0`
- size: `77`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x14000752c`
- `0x14001f025`

## pseudocode

```c
__int64 SvcpServiceMain_::_1_::catch_0()
{
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_e256a6a9c48f38ddd38dc91143465c3b_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x14001f025  mov     [rsp+arg_8], rdx
0x14001f02a  push    rbp
0x14001f02b  sub     rsp, 20h
0x14001f02f  mov     rbp, rdx
0x14001f032  lea     rax, WPP_GLOBAL_Control
0x14001f039  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f040  cmp     rcx, rax
0x14001f043  jz      short loc_14001F061
0x14001f045  test    byte ptr [rcx+1Ch], 1
0x14001f049  jz      short loc_14001F061
0x14001f04b  mov     edx, 0Bh
0x14001f050  lea     r8, WPP_e256a6a9c48f38ddd38dc91143465c3b_Traceguids
0x14001f057  mov     rcx, [rcx+10h]
0x14001f05b  call    WPP_SF_
0x14001f060  nop
0x14001f061  mov     rax, 0
0x14001f06b  add     rsp, 20h
0x14001f06f  pop     rbp
0x14001f070  retn
```
