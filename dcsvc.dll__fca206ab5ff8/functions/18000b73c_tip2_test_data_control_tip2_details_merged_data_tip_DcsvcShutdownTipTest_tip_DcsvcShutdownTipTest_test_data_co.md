# tip2::test_data_control<tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>>::~test_data_control<tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>>(void)

- ea: `0x18000b73c`
- end: `0x18000b7be`
- name: `??1?$test_data_control@V?$merged_data@U_tip_DcsvcShutdownTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ`
- size: `130`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18000c200`

## callees

- `0x18000b6b0`
- `0x18000b73c`
- `0x18000c6b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b784`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b7ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b784`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b7ad`

## pseudocode

```c
void __fastcall tip2::test_data_control<tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>>::~test_data_control<tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>>(
        struct _RTL_CRITICAL_SECTION **a1)
{
  struct _RTL_CRITICAL_SECTION *v2; // rcx
  struct _RTL_CRITICAL_SECTION *v3; // rbx
  struct _RTL_CRITICAL_SECTION *v4; // rbx

  v2 = *a1;
  if ( v2 )
  {
    tip2::details::shared_data<0,0,0>::end_update(&v2->LockCount);
    v3 = *a1;
    *a1 = 0;
    if ( v3 )
    {
      if ( _InterlockedExchangeAdd(&v3[7].LockCount, 0xFFFFFFFF) == 1 )
      {
        tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>::~merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>(v3);
        CoTaskMemFree(v3);
      }
    }
  }
  v4 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd(&v4[7].LockCount, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>::~merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>(v4);
      CoTaskMemFree(v4);
    }
  }
}

```

## disassembly

```asm
0x18000b73c  mov     [rsp+arg_8], rbx
0x18000b741  push    rdi
0x18000b742  sub     rsp, 20h
0x18000b746  mov     rdi, rcx
0x18000b749  mov     rcx, [rcx]
0x18000b74c  test    rcx, rcx
0x18000b74f  jz      short loc_18000B78A
0x18000b751  add     rcx, 8
0x18000b755  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x18000b75a  mov     rbx, [rdi]
0x18000b75d  mov     qword ptr [rdi], 0
0x18000b764  test    rbx, rbx
0x18000b767  jz      short loc_18000B78A
0x18000b769  or      eax, 0FFFFFFFFh
0x18000b76c  lock xadd [rbx+120h], eax
0x18000b774  cmp     eax, 1
0x18000b777  jnz     short loc_18000B78A
0x18000b779  mov     rcx, rbx
0x18000b77c  call    ??1?$merged_data@U_tip_DcsvcShutdownTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>::~merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>(void)
0x18000b781  mov     rcx, rbx; pv
0x18000b784  call    cs:__imp_CoTaskMemFree
0x18000b78a  mov     rbx, [rdi]
0x18000b78d  test    rbx, rbx
0x18000b790  jz      short loc_18000B7B3
0x18000b792  or      eax, 0FFFFFFFFh
0x18000b795  lock xadd [rbx+120h], eax
0x18000b79d  cmp     eax, 1
0x18000b7a0  jnz     short loc_18000B7B3
0x18000b7a2  mov     rcx, rbx
0x18000b7a5  call    ??1?$merged_data@U_tip_DcsvcShutdownTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>::~merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>(void)
0x18000b7aa  mov     rcx, rbx; pv
0x18000b7ad  call    cs:__imp_CoTaskMemFree
0x18000b7b3  mov     rbx, [rsp+28h+arg_8]
0x18000b7b8  add     rsp, 20h
0x18000b7bc  pop     rdi
0x18000b7bd  retn
```
