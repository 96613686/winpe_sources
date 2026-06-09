# tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>::deserialize(tson::input_archive &)

- ea: `0x18000c690`
- end: `0x18000c6a7`
- name: `?deserialize@?$merged_data@U_tip_DcsvcShutdownTipTest@@U1@@details@tip2@@EEAAXAEAVinput_archive@tson@@@Z`
- size: `23`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000ac90`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>::deserialize(
        __int64 a1,
        __int64 a2)
{
  *(_BYTE *)(a2 + 24) = 4;
  *(_QWORD *)(a2 + 16) = "test";
  return tson::input_archive::operator()<_tip_DcsvcShutdownTipTest &>(a2);
}

```

## disassembly

```asm
0x18000c690  lea     rax, aTest; "test"
0x18000c697  mov     byte ptr [rdx+18h], 4
0x18000c69b  mov     rcx, rdx
0x18000c69e  mov     [rdx+10h], rax
0x18000c6a2  jmp     ??$?RAEAU_tip_DcsvcShutdownTipTest@@@input_archive@tson@@QEAAAEAV01@AEAU_tip_DcsvcShutdownTipTest@@@Z; tson::input_archive::operator()<_tip_DcsvcShutdownTipTest &>(_tip_DcsvcShutdownTipTest &)
```
