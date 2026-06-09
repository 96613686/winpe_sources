# tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>::deserialize(tson::input_archive &)

- ea: `0x180016940`
- end: `0x18001696d`
- name: `?deserialize@?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@EEAAXAEAVinput_archive@tson@@@Z`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180017500`
- `0x180019c60`

## pseudocode

```c
void __fastcall tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>::deserialize(
        __int64 a1,
        __int64 a2)
{
  *(_BYTE *)(a2 + 24) = 4;
  *(_QWORD *)(a2 + 16) = "test";
  tson::input_archive::startNode((tson::input_archive *)a2);
  tson::input_archive::finishNode((tson::input_archive *)a2);
}

```

## disassembly

```asm
0x180016940  push    rbx
0x180016942  sub     rsp, 20h
0x180016946  lea     rax, aTest; "test"
0x18001694d  mov     byte ptr [rdx+18h], 4
0x180016951  mov     rcx, rdx; this
0x180016954  mov     [rdx+10h], rax
0x180016958  mov     rbx, rdx
0x18001695b  call    ?startNode@input_archive@tson@@QEAAXXZ; tson::input_archive::startNode(void)
0x180016960  mov     rcx, rbx; this
0x180016963  add     rsp, 20h
0x180016967  pop     rbx
0x180016968  jmp     ?finishNode@input_archive@tson@@QEAAXXZ; tson::input_archive::finishNode(void)
```
