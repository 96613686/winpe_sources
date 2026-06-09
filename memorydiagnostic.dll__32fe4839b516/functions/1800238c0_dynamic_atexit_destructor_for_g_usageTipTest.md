# _dynamic_atexit_destructor_for__g_usageTipTest__

- ea: `0x1800238c0`
- end: `0x180023900`
- name: `_dynamic_atexit_destructor_for__g_usageTipTest__`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180007bf0`
- `0x1800238c0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800238ed`
- `ole32!CoTaskMemFree` at `0x1800238ed`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_usageTipTest__()
{
  void *v0; // rbx

  v0 = g_usageTipTest;
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
0x1800238c0  push    rbx
0x1800238c2  sub     rsp, 20h
0x1800238c6  mov     rbx, cs:?g_usageTipTest@@3V?$tip_test@V?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@@tip2@@A; tip2::tip_test<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>> g_usageTipTest
0x1800238cd  test    rbx, rbx
0x1800238d0  jz      short loc_1800238F9
0x1800238d2  or      eax, 0FFFFFFFFh
0x1800238d5  lock xadd [rbx+150h], eax
0x1800238dd  cmp     eax, 1
0x1800238e0  jnz     short loc_1800238F9
0x1800238e2  mov     rcx, rbx
0x1800238e5  call    ??1?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>::~merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>(void)
0x1800238ea  mov     rcx, rbx; pv
0x1800238ed  call    cs:__imp_CoTaskMemFree
0x1800238f4  nop     dword ptr [rax+rax+00h]
0x1800238f9  add     rsp, 20h
0x1800238fd  pop     rbx
0x1800238fe  retn
```
