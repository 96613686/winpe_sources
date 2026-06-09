# _CMSMQTriggerSet::DeleteTrigger_::_1_::catch$2

- ea: `0x18002060c`
- end: `0x180020663`
- name: `_CMSMQTriggerSet::DeleteTrigger_::_1_::catch$2`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000c62c`
- `0x180012bf8`
- `0x18002060c`

## pseudocode

```c
__int64 CMSMQTriggerSet::DeleteTrigger_::_1_::catch_2()
{
  CMSMQTriggerSet *v0; // rcx

  v0 = (CMSMQTriggerSet *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_83e6074f69a43ee6ab6af28f69519449_Traceguids);
  CMSMQTriggerSet::SetComClassError(v0, 0xC00E0E06);
  return 0;
}

```

## disassembly

```asm
0x18002060c  mov     [rsp+arg_8], rdx
0x180020611  push    rbp
0x180020612  sub     rsp, 20h
0x180020616  mov     rbp, rdx
0x180020619  lea     rax, WPP_GLOBAL_Control
0x180020620  mov     rcx, cs:WPP_GLOBAL_Control
0x180020627  cmp     rcx, rax
0x18002062a  jz      short loc_180020647
0x18002062c  test    byte ptr [rcx+1Ch], 1
0x180020630  jz      short loc_180020647
0x180020632  mov     edx, 2Dh ; '-'
0x180020637  lea     r8, WPP_83e6074f69a43ee6ab6af28f69519449_Traceguids
0x18002063e  mov     rcx, [rcx+10h]
0x180020642  call    WPP_SF_
0x180020647  mov     edx, 0C00E0E06h; int
0x18002064c  call    ?SetComClassError@CMSMQTriggerSet@@AEAAXJ@Z; CMSMQTriggerSet::SetComClassError(long)
0x180020651  nop
0x180020652  mov     rax, 0
0x18002065c  add     rsp, 20h
0x180020660  pop     rbp
0x180020661  retn
```
