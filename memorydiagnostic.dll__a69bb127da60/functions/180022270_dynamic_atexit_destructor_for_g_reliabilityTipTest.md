# _dynamic_atexit_destructor_for__g_reliabilityTipTest__

- ea: `0x180022270`
- end: `0x1800222a9`
- name: `_dynamic_atexit_destructor_for__g_reliabilityTipTest__`
- size: `57`
- prototype: `void()`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180007c18`
- `0x180022270`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002229d`
- `ole32!CoTaskMemFree` at `0x18002229d`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_reliabilityTipTest__()
{
  struct _RTL_CRITICAL_SECTION *v0; // rbx

  v0 = (struct _RTL_CRITICAL_SECTION *)g_reliabilityTipTest;
  if ( g_reliabilityTipTest )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)g_reliabilityTipTest + 68, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>::~merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>(v0);
      CoTaskMemFree(v0);
    }
  }
}

```

## disassembly

```asm
0x180022270  push    rbx
0x180022272  sub     rsp, 20h
0x180022276  mov     rbx, cs:?g_reliabilityTipTest@@3V?$tip_test@V?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@@tip2@@A; tip2::tip_test<tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>> g_reliabilityTipTest
0x18002227d  test    rbx, rbx
0x180022280  jz      short loc_1800222A3
0x180022282  or      eax, 0FFFFFFFFh
0x180022285  lock xadd [rbx+110h], eax
0x18002228d  cmp     eax, 1
0x180022290  jnz     short loc_1800222A3
0x180022292  mov     rcx, rbx
0x180022295  call    ??1?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>::~merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>(void)
0x18002229a  mov     rcx, rbx; pv
0x18002229d  call    cs:__imp_CoTaskMemFree
0x1800222a3  add     rsp, 20h
0x1800222a7  pop     rbx
0x1800222a8  retn
```
