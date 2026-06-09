# _CMSMQTriggersConfig::get_TriggerStoreMachineName_::_1_::catch$1

- ea: `0x18001ffa4`
- end: `0x18001fffb`
- name: `_CMSMQTriggersConfig::get_TriggerStoreMachineName_::_1_::catch$1`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000c62c`
- `0x18000c720`
- `0x18001ffa4`

## pseudocode

```c
__int64 CMSMQTriggersConfig::get_TriggerStoreMachineName_::_1_::catch_1()
{
  CMSMQTriggersConfig *v0; // rcx

  v0 = (CMSMQTriggersConfig *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_6b65e4473ce9379ef69ffc1a5d8b7100_Traceguids);
  CMSMQTriggersConfig::SetComClassError(v0, 0xC00E0E06);
  return 0;
}

```

## disassembly

```asm
0x18001ffa4  mov     [rsp+arg_8], rdx
0x18001ffa9  push    rbp
0x18001ffaa  sub     rsp, 20h
0x18001ffae  mov     rbp, rdx
0x18001ffb1  lea     rax, WPP_GLOBAL_Control
0x18001ffb8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ffbf  cmp     rcx, rax
0x18001ffc2  jz      short loc_18001FFDF
0x18001ffc4  test    byte ptr [rcx+1Ch], 1
0x18001ffc8  jz      short loc_18001FFDF
0x18001ffca  mov     edx, 0Bh
0x18001ffcf  lea     r8, WPP_6b65e4473ce9379ef69ffc1a5d8b7100_Traceguids
0x18001ffd6  mov     rcx, [rcx+10h]
0x18001ffda  call    WPP_SF_
0x18001ffdf  mov     edx, 0C00E0E06h; int
0x18001ffe4  call    ?SetComClassError@CMSMQTriggersConfig@@AEAAXJ@Z; CMSMQTriggersConfig::SetComClassError(long)
0x18001ffe9  nop
0x18001ffea  mov     rax, 0
0x18001fff4  add     rsp, 20h
0x18001fff8  pop     rbp
0x18001fff9  retn
```
