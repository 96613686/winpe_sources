# _dynamic_atexit_destructor_for__g_usageTipTest__

- ea: `0x180022320`
- end: `0x180022359`
- name: `_dynamic_atexit_destructor_for__g_usageTipTest__`
- size: `57`
- prototype: `void()`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180007ca4`
- `0x180022320`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002234d`
- `ole32!CoTaskMemFree` at `0x18002234d`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_usageTipTest__()
{
  struct _RTL_CRITICAL_SECTION *v0; // rbx

  v0 = (struct _RTL_CRITICAL_SECTION *)g_usageTipTest;
  if ( g_usageTipTest )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)g_usageTipTest + 84, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>::~merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>(v0);
      CoTaskMemFree(v0);
    }
  }
}

```

## disassembly

```asm
0x180022320  push    rbx
0x180022322  sub     rsp, 20h
0x180022326  mov     rbx, cs:?g_usageTipTest@@3V?$tip_test@V?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@A; tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>> g_usageTipTest
0x18002232d  test    rbx, rbx
0x180022330  jz      short loc_180022353
0x180022332  or      eax, 0FFFFFFFFh
0x180022335  lock xadd [rbx+150h], eax
0x18002233d  cmp     eax, 1
0x180022340  jnz     short loc_180022353
0x180022342  mov     rcx, rbx
0x180022345  call    ??1?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>::~merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>(void)
0x18002234a  mov     rcx, rbx; pv
0x18002234d  call    cs:__imp_CoTaskMemFree
0x180022353  add     rsp, 20h
0x180022357  pop     rbx
0x180022358  retn
```
