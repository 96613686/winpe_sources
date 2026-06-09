# tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>::~merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>(void)

- ea: `0x18000b6b0`
- end: `0x18000b735`
- name: `??1?$merged_data@U_tip_DcsvcShutdownTipTest@@U1@@details@tip2@@QEAA@XZ`
- size: `133`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000b73c`
- `0x18000c200`
- `0x18000c854`

## callees

- `0x18000b6b0`
- `0x18000b7c4`
- `0x18000b830`
- `0x18000b8b4`
- `0x18000b934`
- `0x18000c568`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b6ef`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b6ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b724`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b724`

## pseudocode

```c
void __fastcall tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>::~merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>(
        struct _RTL_CRITICAL_SECTION *a1)
{
  LONG *p_LockCount; // rcx
  LONG *v3; // rdi
  HANDLE OwningThread; // rcx

  a1->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>::`vftable';
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
0x18000b6b0  mov     [rsp+arg_0], rbx
0x18000b6b5  push    rdi
0x18000b6b6  sub     rsp, 20h
0x18000b6ba  lea     rax, ??_7?$merged_data@U_tip_DcsvcShutdownTipTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>::`vftable'
0x18000b6c1  mov     rbx, rcx
0x18000b6c4  mov     [rcx], rax
0x18000b6c7  add     rcx, 8
0x18000b6cb  lea     rdi, [rcx+0F0h]
0x18000b6d2  cmp     qword ptr [rdi], 0
0x18000b6d6  jz      short loc_18000B6E8
0x18000b6d8  test    byte ptr [rcx+14h], 1
0x18000b6dc  jnz     short loc_18000B6E8
0x18000b6de  mov     edx, 4
0x18000b6e3  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x18000b6e8  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18000b6ef  call    cs:__imp_DeleteCriticalSection
0x18000b6f5  mov     rcx, rdi
0x18000b6f8  call    ??1?$unique_storage@U?$resource_policy@PEAUHTIPTEST__@@P6AXPEAU1@@Z$1?TestClose@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HTIPTEST__ *,void (*)(HTIPTEST__ *),&TestClose(HTIPTEST__ *),wistd::integral_constant<unsigned __int64,0>,HTIPTEST__ *,HTIPTEST__ *,0,std::nullptr_t>>(void)
0x18000b6fd  lea     rcx, [rbx+80h]
0x18000b704  call    ??1?$vector_nothrow@Utest_flag@tip2@@@tip2@@QEAA@XZ; tip2::vector_nothrow<tip2::test_flag>::~vector_nothrow<tip2::test_flag>(void)
0x18000b709  lea     rcx, [rbx+68h]
0x18000b70d  call    ??1?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(void)
0x18000b712  lea     rcx, [rbx+50h]
0x18000b716  call    ??1?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@QEAA@XZ; tip2::vector_nothrow<wil::StoredFailureInfo>::~vector_nothrow<wil::StoredFailureInfo>(void)
0x18000b71b  mov     rcx, [rbx+10h]; pv
0x18000b71f  test    rcx, rcx
0x18000b722  jz      short loc_18000B72A
0x18000b724  call    cs:__imp_CoTaskMemFree
0x18000b72a  mov     rbx, [rsp+28h+arg_0]
0x18000b72f  add     rsp, 20h
0x18000b733  pop     rdi
0x18000b734  retn
```
