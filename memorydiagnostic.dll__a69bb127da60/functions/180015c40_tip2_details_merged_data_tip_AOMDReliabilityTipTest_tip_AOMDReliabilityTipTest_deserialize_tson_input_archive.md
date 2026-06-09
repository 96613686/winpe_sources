# tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>::deserialize(tson::input_archive &)

- ea: `0x180015c40`
- end: `0x180015c6d`
- name: `?deserialize@?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@EEAAXAEAVinput_archive@tson@@@Z`
- size: `45`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x1800168c8`
- `0x180018ea8`

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
0x180015c40  push    rbx
0x180015c42  sub     rsp, 20h
0x180015c46  lea     rax, aTest; "test"
0x180015c4d  mov     byte ptr [rdx+18h], 4
0x180015c51  mov     rcx, rdx; this
0x180015c54  mov     [rdx+10h], rax
0x180015c58  mov     rbx, rdx
0x180015c5b  call    ?startNode@input_archive@tson@@QEAAXXZ; tson::input_archive::startNode(void)
0x180015c60  mov     rcx, rbx; this
0x180015c63  add     rsp, 20h
0x180015c67  pop     rbx
0x180015c68  jmp     ?finishNode@input_archive@tson@@QEAAXXZ; tson::input_archive::finishNode(void)
```
