# _CRuntimeTriggerInfo::Update_::_1_::catch$1

- ea: `0x180021860`
- end: `0x1800218ca`
- name: `_CRuntimeTriggerInfo::Update_::_1_::catch$1`
- size: `106`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x180004d88`
- `0x180021860`

## pseudocode

```c
__int64 CRuntimeTriggerInfo::Update_::_1_::catch_1()
{
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2));
  return 0;
}

```

## disassembly

```asm
0x180021860  mov     [rsp+arg_8], rdx
0x180021865  push    rbp
0x180021866  sub     rsp, 20h
0x18002186a  mov     rbp, rdx
0x18002186d  lea     rax, WPP_GLOBAL_Control
0x180021874  mov     rcx, cs:WPP_GLOBAL_Control
0x18002187b  cmp     rcx, rax
0x18002187e  jz      short loc_1800218B9
0x180021880  test    byte ptr [rcx+1Ch], 1
0x180021884  jz      short loc_1800218B9
0x180021886  mov     rax, [rbp+30h]
0x18002188a  cmp     qword ptr [rax+820h], 0
0x180021892  jz      short loc_1800218A0
0x180021894  mov     rax, [rax+820h]
0x18002189b  mov     r9, [rax]
0x18002189e  jmp     short loc_1800218A3
0x1800218a0  xor     r9d, r9d
0x1800218a3  mov     edx, 12h
0x1800218a8  lea     r8, WPP_5d468cdb8ea734f7fb134a242ccb11b7_Traceguids
0x1800218af  mov     rcx, [rcx+10h]; LoggerHandle
0x1800218b3  call    WPP_SF_S
0x1800218b8  nop
0x1800218b9  mov     rax, 0
0x1800218c3  add     rsp, 20h
0x1800218c7  pop     rbp
0x1800218c8  retn
```
