# tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>::deserialize(tson::input_archive &)

- ea: `0x180015c80`
- end: `0x180015d57`
- name: `?deserialize@?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@EEAAXAEAVinput_archive@tson@@@Z`
- size: `215`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x1800063d8`
- `0x180015c80`
- `0x1800168c8`
- `0x180018ea8`

## pseudocode

```c
void __fastcall tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>::deserialize(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rbx

  *(_BYTE *)(a2 + 24) = 4;
  v3 = (a1 + 256) & -(__int64)(a1 != 0);
  *(_QWORD *)(a2 + 16) = "test";
  tson::input_archive::startNode((tson::input_archive *)a2);
  if ( (*(_DWORD *)(*(_QWORD *)v3 + 12LL) & 0x40000) != 0 )
  {
    *(_BYTE *)(a2 + 24) = 7;
    *(_QWORD *)(a2 + 16) = "req_set";
    tson::input_archive::startNode((tson::input_archive *)a2);
    tson::load_nothrow<tip2::test_flag>((tson *)a2);
    tson::input_archive::finishNode((tson::input_archive *)a2);
    *(_BYTE *)(a2 + 24) = 7;
    *(_QWORD *)(a2 + 16) = "req_any";
    tson::input_archive::startNode((tson::input_archive *)a2);
    tson::load_nothrow<tip2::test_flag>((tson *)a2);
    tson::input_archive::finishNode((tson::input_archive *)a2);
    *(_BYTE *)(a2 + 24) = 9;
    *(_QWORD *)(a2 + 16) = "req_clear";
    tson::input_archive::startNode((tson::input_archive *)a2);
    tson::load_nothrow<tip2::test_flag>((tson *)a2);
    tson::input_archive::finishNode((tson::input_archive *)a2);
  }
  tson::input_archive::finishNode((tson::input_archive *)a2);
}

```

## disassembly

```asm
0x180015c80  mov     [rsp+arg_0], rbx
0x180015c85  push    rdi
0x180015c86  sub     rsp, 20h
0x180015c8a  lea     rax, [rcx+100h]
0x180015c91  mov     byte ptr [rdx+18h], 4
0x180015c95  neg     rcx
0x180015c98  mov     rdi, rdx
0x180015c9b  mov     rcx, rdx; this
0x180015c9e  sbb     rbx, rbx
0x180015ca1  and     rbx, rax
0x180015ca4  lea     rax, aTest; "test"
0x180015cab  mov     [rdx+10h], rax
0x180015caf  call    ?startNode@input_archive@tson@@QEAAXXZ; tson::input_archive::startNode(void)
0x180015cb4  mov     rax, [rbx]
0x180015cb7  test    dword ptr [rax+0Ch], 40000h
0x180015cbe  jz      loc_180015D45
0x180015cc4  lea     rax, aReqSet; "req_set"
0x180015ccb  mov     byte ptr [rdi+18h], 7
0x180015ccf  mov     rcx, rdi; this
0x180015cd2  mov     [rdi+10h], rax
0x180015cd6  call    ?startNode@input_archive@tson@@QEAAXXZ; tson::input_archive::startNode(void)
0x180015cdb  lea     rdx, [rbx+8]
0x180015cdf  mov     rcx, rdi; this
0x180015ce2  call    ??$load_nothrow@Utest_flag@tip2@@@tson@@YAXAEAVinput_archive@0@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@Z; tson::load_nothrow<tip2::test_flag>(tson::input_archive &,tip2::vector_nothrow<tip2::test_flag> &)
0x180015ce7  mov     rcx, rdi; this
0x180015cea  call    ?finishNode@input_archive@tson@@QEAAXXZ; tson::input_archive::finishNode(void)
0x180015cef  lea     rcx, aReqAny; "req_any"
0x180015cf6  mov     byte ptr [rdi+18h], 7
0x180015cfa  mov     [rdi+10h], rcx
0x180015cfe  mov     rcx, rdi; this
0x180015d01  call    ?startNode@input_archive@tson@@QEAAXXZ; tson::input_archive::startNode(void)
0x180015d06  lea     rdx, [rbx+20h]
0x180015d0a  mov     rcx, rdi; this
0x180015d0d  call    ??$load_nothrow@Utest_flag@tip2@@@tson@@YAXAEAVinput_archive@0@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@Z; tson::load_nothrow<tip2::test_flag>(tson::input_archive &,tip2::vector_nothrow<tip2::test_flag> &)
0x180015d12  mov     rcx, rdi; this
0x180015d15  call    ?finishNode@input_archive@tson@@QEAAXXZ; tson::input_archive::finishNode(void)
0x180015d1a  lea     rcx, aReqClear; "req_clear"
0x180015d21  mov     byte ptr [rdi+18h], 9
0x180015d25  mov     [rdi+10h], rcx
0x180015d29  mov     rcx, rdi; this
0x180015d2c  call    ?startNode@input_archive@tson@@QEAAXXZ; tson::input_archive::startNode(void)
0x180015d31  lea     rdx, [rbx+38h]
0x180015d35  mov     rcx, rdi; this
0x180015d38  call    ??$load_nothrow@Utest_flag@tip2@@@tson@@YAXAEAVinput_archive@0@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@Z; tson::load_nothrow<tip2::test_flag>(tson::input_archive &,tip2::vector_nothrow<tip2::test_flag> &)
0x180015d3d  mov     rcx, rdi; this
0x180015d40  call    ?finishNode@input_archive@tson@@QEAAXXZ; tson::input_archive::finishNode(void)
0x180015d45  mov     rcx, rdi; this
0x180015d48  mov     rbx, [rsp+28h+arg_0]
0x180015d4d  add     rsp, 20h
0x180015d51  pop     rdi
0x180015d52  jmp     ?finishNode@input_archive@tson@@QEAAXXZ; tson::input_archive::finishNode(void)
```
