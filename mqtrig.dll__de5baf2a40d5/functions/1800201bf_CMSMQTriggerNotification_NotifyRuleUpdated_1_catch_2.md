# _CMSMQTriggerNotification::NotifyRuleUpdated_::_1_::catch$2

- ea: `0x1800201bf`
- end: `0x180020242`
- name: `_CMSMQTriggerNotification::NotifyRuleUpdated_::_1_::catch$2`
- size: `131`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x18000c654`
- `0x1800201bf`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall CMSMQTriggerNotification::NotifyRuleUpdated_::_1_::catch_2(__int64 a1, __int64 a2)
{
  __int64 v3; // rbx
  unsigned int v4; // eax

  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
  {
    v3 = *(_QWORD *)(a2 + 48);
  }
  else
  {
    v3 = *(_QWORD *)(a2 + 48);
    v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_6d1c6f0186f431bde13e7207227cdc41_Traceguids, v4);
  }
  *(_DWORD *)(a2 + 104) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  return 0;
}

```

## disassembly

```asm
0x1800201bf  mov     [rsp+arg_8], rdx
0x1800201c4  push    rbx
0x1800201c5  push    rbp
0x1800201c6  sub     rsp, 28h
0x1800201ca  mov     rbp, rdx
0x1800201cd  lea     rcx, WPP_GLOBAL_Control
0x1800201d4  mov     rax, cs:WPP_GLOBAL_Control
0x1800201db  cmp     rax, rcx
0x1800201de  jz      short loc_18002021A
0x1800201e0  test    byte ptr [rax+1Ch], 1
0x1800201e4  jz      short loc_18002021A
0x1800201e6  mov     rbx, [rbp+30h]
0x1800201ea  mov     rax, [rbx]
0x1800201ed  mov     rcx, rbx
0x1800201f0  mov     rax, [rax+10h]
0x1800201f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800201f9  mov     edx, 12h
0x1800201fe  mov     r9d, eax
0x180020201  lea     r8, WPP_6d1c6f0186f431bde13e7207227cdc41_Traceguids
0x180020208  mov     rcx, cs:WPP_GLOBAL_Control
0x18002020f  mov     rcx, [rcx+10h]
0x180020213  call    WPP_SF_d
0x180020218  jmp     short loc_18002021E
0x18002021a  mov     rbx, [rbp+30h]
0x18002021e  mov     rax, [rbx]
0x180020221  mov     rcx, rbx
0x180020224  mov     rax, [rax+10h]
0x180020228  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002022d  mov     [rbp+68h], eax
0x180020230  mov     rax, 0
0x18002023a  add     rsp, 28h
0x18002023e  pop     rbp
0x18002023f  pop     rbx
0x180020240  retn
```
