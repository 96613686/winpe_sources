# tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>::~merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>(void)

- ea: `0x180007ca4`
- end: `0x180007d54`
- name: `??1?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@QEAA@XZ`
- size: `176`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180015010`
- `0x180018c48`
- `0x180022320`

## callees

- `0x180007ca4`
- `0x180007e0c`
- `0x180007fc4`
- `0x180008048`
- `0x1800080c8`
- `0x180015928`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180007d09`
- `KERNEL32!DeleteCriticalSection` at `0x180007d09`
- `ole32!CoTaskMemFree` at `0x180007d3e`
- `ole32!CoTaskMemFree` at `0x180007d3e`

## pseudocode

```c
void __fastcall tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>::~merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>(
        struct _RTL_CRITICAL_SECTION *a1)
{
  LONG *p_LockCount; // rcx
  LONG *v3; // rsi
  HANDLE OwningThread; // rcx

  a1->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>::`vftable';
  p_LockCount = &a1->LockCount;
  v3 = p_LockCount + 60;
  if ( *((_QWORD *)p_LockCount + 30) && (p_LockCount[5] & 1) == 0 )
    tip2::details::shared_data<0,0,1>::complete_helper(p_LockCount, 4);
  tip2::vector_nothrow<tip2::test_flag>::~vector_nothrow<tip2::test_flag>(&a1[7].SpinCount);
  tip2::vector_nothrow<tip2::test_flag>::~vector_nothrow<tip2::test_flag>(&a1[7].LockCount);
  tip2::vector_nothrow<tip2::test_flag>::~vector_nothrow<tip2::test_flag>(&a1[6].LockSemaphore);
  DeleteCriticalSection(a1 + 5);
  wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&void TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&void TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(v3);
  tip2::vector_nothrow<tip2::test_flag>::~vector_nothrow<tip2::test_flag>(&a1[3].LockCount);
  tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(&a1[2].LockSemaphore);
  tip2::vector_nothrow<wil::StoredFailureInfo>::~vector_nothrow<wil::StoredFailureInfo>(&a1[2]);
  OwningThread = a1->OwningThread;
  if ( OwningThread )
    CoTaskMemFree(OwningThread);
}

```

## disassembly

```asm
0x180007ca4  mov     [rsp+arg_0], rbx
0x180007ca9  mov     [rsp+arg_8], rsi
0x180007cae  push    rdi
0x180007caf  sub     rsp, 20h
0x180007cb3  lea     rax, ??_7?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@6B@; const tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>::`vftable'
0x180007cba  mov     rdi, rcx
0x180007cbd  mov     [rcx], rax
0x180007cc0  add     rcx, 8
0x180007cc4  lea     rsi, [rcx+0F0h]
0x180007ccb  cmp     qword ptr [rsi], 0
0x180007ccf  jz      short loc_180007CE1
0x180007cd1  test    byte ptr [rcx+14h], 1
0x180007cd5  jnz     short loc_180007CE1
0x180007cd7  mov     edx, 4
0x180007cdc  call    ?complete_helper@?$shared_data@$0A@$0A@$00@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,1>::complete_helper(TestQueryOptions)
0x180007ce1  lea     rbx, [rdi+108h]
0x180007ce8  lea     rcx, [rbx+30h]
0x180007cec  call    ??1?$vector_nothrow@Utest_flag@tip2@@@tip2@@QEAA@XZ; tip2::vector_nothrow<tip2::test_flag>::~vector_nothrow<tip2::test_flag>(void)
0x180007cf1  lea     rcx, [rbx+18h]
0x180007cf5  call    ??1?$vector_nothrow@Utest_flag@tip2@@@tip2@@QEAA@XZ; tip2::vector_nothrow<tip2::test_flag>::~vector_nothrow<tip2::test_flag>(void)
0x180007cfa  mov     rcx, rbx
0x180007cfd  call    ??1?$vector_nothrow@Utest_flag@tip2@@@tip2@@QEAA@XZ; tip2::vector_nothrow<tip2::test_flag>::~vector_nothrow<tip2::test_flag>(void)
0x180007d02  lea     rcx, [rdi+0C8h]; lpCriticalSection
0x180007d09  call    cs:__imp_DeleteCriticalSection
0x180007d0f  mov     rcx, rsi
0x180007d12  call    ??1?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(void)
0x180007d17  lea     rcx, [rdi+80h]
0x180007d1e  call    ??1?$vector_nothrow@Utest_flag@tip2@@@tip2@@QEAA@XZ; tip2::vector_nothrow<tip2::test_flag>::~vector_nothrow<tip2::test_flag>(void)
0x180007d23  lea     rcx, [rdi+68h]
0x180007d27  call    ??1?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(void)
0x180007d2c  lea     rcx, [rdi+50h]
0x180007d30  call    ??1?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::StoredFailureInfo>::~vector_nothrow<wil::StoredFailureInfo>(void)
0x180007d35  mov     rcx, [rdi+10h]; pv
0x180007d39  test    rcx, rcx
0x180007d3c  jz      short loc_180007D44
0x180007d3e  call    cs:__imp_CoTaskMemFree
0x180007d44  mov     rbx, [rsp+28h+arg_0]
0x180007d49  mov     rsi, [rsp+28h+arg_8]
0x180007d4e  add     rsp, 20h
0x180007d52  pop     rdi
0x180007d53  retn
```
