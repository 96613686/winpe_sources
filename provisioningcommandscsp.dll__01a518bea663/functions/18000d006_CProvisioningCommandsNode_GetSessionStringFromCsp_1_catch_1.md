# _CProvisioningCommandsNode::GetSessionStringFromCsp_::_1_::catch$1

- ea: `0x18000d006`
- end: `0x18000d04d`
- name: `_CProvisioningCommandsNode::GetSessionStringFromCsp_::_1_::catch$1`
- size: `71`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall CProvisioningCommandsNode::GetSessionStringFromCsp_::_1_::catch_1(__int64 a1, __int64 a2)
{
  __int64 v2; // rax

  v2 = *(_QWORD *)(a2 + 80);
  *(_QWORD *)(v2 + 16) = 0;
  *(_QWORD *)(v2 + 24) = 0;
  *(_QWORD *)(v2 + 24) = 7;
  *(_QWORD *)(v2 + 16) = 0;
  *(_WORD *)v2 = 0;
  return 0;
}

```

## disassembly

```asm
0x18000d006  mov     [rsp+arg_8], rdx
0x18000d00b  push    rbp
0x18000d00c  sub     rsp, 20h
0x18000d010  mov     rbp, rdx
0x18000d013  mov     rax, [rbp+50h]
0x18000d017  mov     qword ptr [rax+10h], 0
0x18000d01f  mov     qword ptr [rax+18h], 0
0x18000d027  mov     qword ptr [rax+18h], 7
0x18000d02f  mov     qword ptr [rax+10h], 0
0x18000d037  xor     ecx, ecx
0x18000d039  mov     [rax], cx
0x18000d03c  mov     rax, 0
0x18000d046  add     rsp, 20h
0x18000d04a  pop     rbp
0x18000d04b  retn
```
