# tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>::~merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>(void)

- ea: `0x180007c18`
- end: `0x180007c9d`
- name: `??1?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@QEAA@XZ`
- size: `133`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *)`
- caller_count: `5`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180007d5c`
- `0x180015010`
- `0x180015e38`
- `0x180018a48`
- `0x180022270`

## callees

- `0x180007c18`
- `0x180007e0c`
- `0x180007fc4`
- `0x180008048`
- `0x1800080c8`
- `0x180015a4c`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180007c57`
- `KERNEL32!DeleteCriticalSection` at `0x180007c57`
- `ole32!CoTaskMemFree` at `0x180007c8c`
- `ole32!CoTaskMemFree` at `0x180007c8c`

## pseudocode

```c
void __fastcall tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>::~merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>(
        struct _RTL_CRITICAL_SECTION *a1)
{
  LONG *p_LockCount; // rcx
  LONG *v3; // rdi
  HANDLE OwningThread; // rcx

  a1->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>::`vftable';
  p_LockCount = &a1->LockCount;
  v3 = p_LockCount + 60;
  if ( *((_QWORD *)p_LockCount + 30) && (p_LockCount[5] & 1) == 0 )
    tip2::details::shared_data<0,0,0>::complete_helper(p_LockCount, 4);
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
0x180007c18  mov     [rsp+arg_0], rbx
0x180007c1d  push    rdi
0x180007c1e  sub     rsp, 20h
0x180007c22  lea     rax, ??_7?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>::`vftable'
0x180007c29  mov     rbx, rcx
0x180007c2c  mov     [rcx], rax
0x180007c2f  add     rcx, 8
0x180007c33  lea     rdi, [rcx+0F0h]
0x180007c3a  cmp     qword ptr [rdi], 0
0x180007c3e  jz      short loc_180007C50
0x180007c40  test    byte ptr [rcx+14h], 1
0x180007c44  jnz     short loc_180007C50
0x180007c46  mov     edx, 4
0x180007c4b  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x180007c50  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180007c57  call    cs:__imp_DeleteCriticalSection
0x180007c5d  mov     rcx, rdi
0x180007c60  call    ??1?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(void)
0x180007c65  lea     rcx, [rbx+80h]
0x180007c6c  call    ??1?$vector_nothrow@Utest_flag@tip2@@@tip2@@QEAA@XZ; tip2::vector_nothrow<tip2::test_flag>::~vector_nothrow<tip2::test_flag>(void)
0x180007c71  lea     rcx, [rbx+68h]
0x180007c75  call    ??1?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(void)
0x180007c7a  lea     rcx, [rbx+50h]
0x180007c7e  call    ??1?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::StoredFailureInfo>::~vector_nothrow<wil::StoredFailureInfo>(void)
0x180007c83  mov     rcx, [rbx+10h]; pv
0x180007c87  test    rcx, rcx
0x180007c8a  jz      short loc_180007C92
0x180007c8c  call    cs:__imp_CoTaskMemFree
0x180007c92  mov     rbx, [rsp+28h+arg_0]
0x180007c97  add     rsp, 20h
0x180007c9b  pop     rdi
0x180007c9c  retn
```
