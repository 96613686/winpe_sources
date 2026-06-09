# tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>::deserialize(tson::input_archive &)

- ea: `0x180016980`
- end: `0x180016a57`
- name: `?deserialize@?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@EEAAXAEAVinput_archive@tson@@@Z`
- size: `215`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180006300`
- `0x180016980`
- `0x180017500`
- `0x180019c60`

## pseudocode

```c
void __fastcall tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>::deserialize(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rbx

  *(_BYTE *)(a2 + 24) = 4;
  *(_QWORD *)(a2 + 16) = "test";
  v3 = (a1 + 256) & -(__int64)(a1 != 0);
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
0x180016980  mov     [rsp+arg_0], rbx
0x180016985  push    rdi
0x180016986  sub     rsp, 20h
0x18001698a  lea     rax, aTest; "test"
0x180016991  mov     byte ptr [rdx+18h], 4
0x180016995  mov     [rdx+10h], rax
0x180016999  mov     rdi, rdx
0x18001699c  lea     rax, [rcx+100h]
0x1800169a3  neg     rcx
0x1800169a6  mov     rcx, rdx; this
0x1800169a9  sbb     rbx, rbx
0x1800169ac  and     rbx, rax
0x1800169af  call    ?startNode@input_archive@tson@@QEAAXXZ; tson::input_archive::startNode(void)
0x1800169b4  mov     rax, [rbx]
0x1800169b7  test    dword ptr [rax+0Ch], 40000h
0x1800169be  jz      loc_180016A45
0x1800169c4  lea     rax, aReqSet; "req_set"
0x1800169cb  mov     byte ptr [rdi+18h], 7
0x1800169cf  mov     rcx, rdi; this
0x1800169d2  mov     [rdi+10h], rax
0x1800169d6  call    ?startNode@input_archive@tson@@QEAAXXZ; tson::input_archive::startNode(void)
0x1800169db  lea     rdx, [rbx+8]
0x1800169df  mov     rcx, rdi; this
0x1800169e2  call    ??$load_nothrow@Utest_flag@tip2@@@tson@@YAXAEAVinput_archive@0@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@Z; tson::load_nothrow<tip2::test_flag>(tson::input_archive &,tip2::vector_nothrow<tip2::test_flag> &)
0x1800169e7  mov     rcx, rdi; this
0x1800169ea  call    ?finishNode@input_archive@tson@@QEAAXXZ; tson::input_archive::finishNode(void)
0x1800169ef  lea     rcx, aReqAny; "req_any"
0x1800169f6  mov     byte ptr [rdi+18h], 7
0x1800169fa  mov     [rdi+10h], rcx
0x1800169fe  mov     rcx, rdi; this
0x180016a01  call    ?startNode@input_archive@tson@@QEAAXXZ; tson::input_archive::startNode(void)
0x180016a06  lea     rdx, [rbx+20h]
0x180016a0a  mov     rcx, rdi; this
0x180016a0d  call    ??$load_nothrow@Utest_flag@tip2@@@tson@@YAXAEAVinput_archive@0@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@Z; tson::load_nothrow<tip2::test_flag>(tson::input_archive &,tip2::vector_nothrow<tip2::test_flag> &)
0x180016a12  mov     rcx, rdi; this
0x180016a15  call    ?finishNode@input_archive@tson@@QEAAXXZ; tson::input_archive::finishNode(void)
0x180016a1a  lea     rcx, aReqClear; "req_clear"
0x180016a21  mov     byte ptr [rdi+18h], 9
0x180016a25  mov     [rdi+10h], rcx
0x180016a29  mov     rcx, rdi; this
0x180016a2c  call    ?startNode@input_archive@tson@@QEAAXXZ; tson::input_archive::startNode(void)
0x180016a31  lea     rdx, [rbx+38h]
0x180016a35  mov     rcx, rdi; this
0x180016a38  call    ??$load_nothrow@Utest_flag@tip2@@@tson@@YAXAEAVinput_archive@0@AEAV?$vector_nothrow@Utest_flag@tip2@@@tip2@@@Z; tson::load_nothrow<tip2::test_flag>(tson::input_archive &,tip2::vector_nothrow<tip2::test_flag> &)
0x180016a3d  mov     rcx, rdi; this
0x180016a40  call    ?finishNode@input_archive@tson@@QEAAXXZ; tson::input_archive::finishNode(void)
0x180016a45  mov     rcx, rdi; this
0x180016a48  mov     rbx, [rsp+28h+arg_0]
0x180016a4d  add     rsp, 20h
0x180016a51  pop     rdi
0x180016a52  jmp     ?finishNode@input_archive@tson@@QEAAXXZ; tson::input_archive::finishNode(void)
```
