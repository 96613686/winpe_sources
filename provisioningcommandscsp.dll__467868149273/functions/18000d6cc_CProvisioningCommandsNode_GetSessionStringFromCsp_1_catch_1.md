# _CProvisioningCommandsNode::GetSessionStringFromCsp_::_1_::catch$1

- ea: `0x18000d6cc`
- end: `0x18000d713`
- name: `_CProvisioningCommandsNode::GetSessionStringFromCsp_::_1_::catch$1`
- size: `71`
- prototype: ``
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
0x18000d6cc  mov     [rsp+arg_8], rdx
0x18000d6d1  push    rbp
0x18000d6d2  sub     rsp, 20h
0x18000d6d6  mov     rbp, rdx
0x18000d6d9  mov     rax, [rbp+50h]
0x18000d6dd  mov     qword ptr [rax+10h], 0
0x18000d6e5  mov     qword ptr [rax+18h], 0
0x18000d6ed  mov     qword ptr [rax+18h], 7
0x18000d6f5  mov     qword ptr [rax+10h], 0
0x18000d6fd  xor     ecx, ecx
0x18000d6ff  mov     [rax], cx
0x18000d702  mov     rax, 0
0x18000d70c  add     rsp, 20h
0x18000d710  pop     rbp
0x18000d711  retn
```
