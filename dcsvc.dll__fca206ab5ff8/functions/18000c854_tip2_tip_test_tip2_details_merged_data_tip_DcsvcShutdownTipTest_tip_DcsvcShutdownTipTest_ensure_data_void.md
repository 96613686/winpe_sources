# tip2::tip_test<tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>>::ensure_data(void)

- ea: `0x18000c854`
- end: `0x18000c8e0`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_DcsvcShutdownTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_DcsvcShutdownTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `140`
- prototype: `struct _RTL_CRITICAL_SECTION **__fastcall(struct _RTL_CRITICAL_SECTION **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c200`

## callees

- `0x18000b488`
- `0x18000b6b0`
- `0x18000c854`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c8a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c8cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c8a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c8cc`

## pseudocode

```c
struct _RTL_CRITICAL_SECTION **__fastcall tip2::tip_test<tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>>::ensure_data(
        struct _RTL_CRITICAL_SECTION **a1)
{
  struct _RTL_CRITICAL_SECTION **v2; // rax
  struct _RTL_CRITICAL_SECTION *v3; // rdx
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  LPVOID pv; // [rsp+38h] [rbp+10h] BYREF

  if ( !*a1 )
  {
    v2 = (struct _RTL_CRITICAL_SECTION **)tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>,>(&pv);
    v3 = *v2;
    *v2 = 0;
    v4 = *a1;
    *a1 = v3;
    if ( v4 && _InterlockedExchangeAdd(&v4[7].LockCount, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>::~merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>(v4);
      CoTaskMemFree(v4);
    }
    v5 = (struct _RTL_CRITICAL_SECTION *)pv;
    if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 72, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>::~merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>(v5);
      CoTaskMemFree(v5);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18000c854  mov     [rsp+arg_10], rbx
0x18000c859  push    rdi
0x18000c85a  sub     rsp, 20h
0x18000c85e  cmp     qword ptr [rcx], 0
0x18000c862  mov     rdi, rcx
0x18000c865  jnz     short loc_18000C8D2
0x18000c867  lea     rcx, [rsp+28h+pv]
0x18000c86c  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_DcsvcShutdownTipTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_DcsvcShutdownTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>,>(void)
0x18000c871  mov     rdx, [rax]
0x18000c874  mov     qword ptr [rax], 0
0x18000c87b  mov     rbx, [rdi]
0x18000c87e  mov     [rdi], rdx
0x18000c881  test    rbx, rbx
0x18000c884  jz      short loc_18000C8A7
0x18000c886  or      eax, 0FFFFFFFFh
0x18000c889  lock xadd [rbx+120h], eax
0x18000c891  cmp     eax, 1
0x18000c894  jnz     short loc_18000C8A7
0x18000c896  mov     rcx, rbx
0x18000c899  call    ??1?$merged_data@U_tip_DcsvcShutdownTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>::~merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>(void)
0x18000c89e  mov     rcx, rbx; pv
0x18000c8a1  call    cs:__imp_CoTaskMemFree
0x18000c8a7  mov     rbx, [rsp+28h+pv]
0x18000c8ac  test    rbx, rbx
0x18000c8af  jz      short loc_18000C8D2
0x18000c8b1  or      eax, 0FFFFFFFFh
0x18000c8b4  lock xadd [rbx+120h], eax
0x18000c8bc  cmp     eax, 1
0x18000c8bf  jnz     short loc_18000C8D2
0x18000c8c1  mov     rcx, rbx
0x18000c8c4  call    ??1?$merged_data@U_tip_DcsvcShutdownTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>::~merged_data<_tip_DcsvcShutdownTipTest,_tip_DcsvcShutdownTipTest>(void)
0x18000c8c9  mov     rcx, rbx; pv
0x18000c8cc  call    cs:__imp_CoTaskMemFree
0x18000c8d2  mov     rbx, [rsp+28h+arg_10]
0x18000c8d7  mov     rax, rdi
0x18000c8da  add     rsp, 20h
0x18000c8de  pop     rdi
0x18000c8df  retn
```
