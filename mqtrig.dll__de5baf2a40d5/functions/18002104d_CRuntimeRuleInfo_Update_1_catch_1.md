# _CRuntimeRuleInfo::Update_::_1_::catch$1

- ea: `0x18002104d`
- end: `0x1800210af`
- name: `_CRuntimeRuleInfo::Update_::_1_::catch$1`
- size: `98`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x180004d88`
- `0x18002104d`

## pseudocode

```c
__int64 CRuntimeRuleInfo::Update_::_1_::catch_1()
{
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2));
  return 0;
}

```

## disassembly

```asm
0x18002104d  mov     [rsp+arg_8], rdx
0x180021052  push    rbp
0x180021053  sub     rsp, 20h
0x180021057  mov     rbp, rdx
0x18002105a  lea     rax, WPP_GLOBAL_Control
0x180021061  mov     rcx, cs:WPP_GLOBAL_Control
0x180021068  cmp     rcx, rax
0x18002106b  jz      short loc_18002109E
0x18002106d  test    byte ptr [rcx+1Ch], 1
0x180021071  jz      short loc_18002109E
0x180021073  mov     rax, [rbp+30h]
0x180021077  cmp     qword ptr [rax], 0
0x18002107b  jz      short loc_180021085
0x18002107d  mov     rax, [rax]
0x180021080  mov     r9, [rax]
0x180021083  jmp     short loc_180021088
0x180021085  xor     r9d, r9d
0x180021088  mov     edx, 0Fh
0x18002108d  lea     r8, WPP_d76c01569fa63fba5f13379e908326ce_Traceguids
0x180021094  mov     rcx, [rcx+10h]; LoggerHandle
0x180021098  call    WPP_SF_S
0x18002109d  nop
0x18002109e  mov     rax, 0
0x1800210a8  add     rsp, 20h
0x1800210ac  pop     rbp
0x1800210ad  retn
```
