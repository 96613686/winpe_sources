# _CMSMQTriggerSet::UpdateTrigger_::_1_::catch$8

- ea: `0x180020a9c`
- end: `0x180020af3`
- name: `_CMSMQTriggerSet::UpdateTrigger_::_1_::catch$8`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000c62c`
- `0x180012bf8`
- `0x180020a9c`

## pseudocode

```c
__int64 CMSMQTriggerSet::UpdateTrigger_::_1_::catch_8()
{
  CMSMQTriggerSet *v0; // rcx

  v0 = (CMSMQTriggerSet *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_83e6074f69a43ee6ab6af28f69519449_Traceguids);
  CMSMQTriggerSet::SetComClassError(v0, 0xC00E0E06);
  return 0;
}

```

## disassembly

```asm
0x180020a9c  mov     [rsp+arg_8], rdx
0x180020aa1  push    rbp
0x180020aa2  sub     rsp, 20h
0x180020aa6  mov     rbp, rdx
0x180020aa9  lea     rax, WPP_GLOBAL_Control
0x180020ab0  mov     rcx, cs:WPP_GLOBAL_Control
0x180020ab7  cmp     rcx, rax
0x180020aba  jz      short loc_180020AD7
0x180020abc  test    byte ptr [rcx+1Ch], 1
0x180020ac0  jz      short loc_180020AD7
0x180020ac2  mov     edx, 36h ; '6'
0x180020ac7  lea     r8, WPP_83e6074f69a43ee6ab6af28f69519449_Traceguids
0x180020ace  mov     rcx, [rcx+10h]
0x180020ad2  call    WPP_SF_
0x180020ad7  mov     edx, 0C00E0E06h; int
0x180020adc  call    ?SetComClassError@CMSMQTriggerSet@@AEAAXJ@Z; CMSMQTriggerSet::SetComClassError(long)
0x180020ae1  nop
0x180020ae2  mov     rax, 0
0x180020aec  add     rsp, 20h
0x180020af0  pop     rbp
0x180020af1  retn
```
