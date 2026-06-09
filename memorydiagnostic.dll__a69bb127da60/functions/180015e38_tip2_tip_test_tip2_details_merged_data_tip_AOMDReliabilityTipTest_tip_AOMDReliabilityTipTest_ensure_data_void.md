# tip2::tip_test<tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>>::ensure_data(void)

- ea: `0x180015e38`
- end: `0x180015ec4`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `140`
- prototype: `__int64 *__fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180015010`
- `0x180018a48`

## callees

- `0x180006b88`
- `0x180007c18`
- `0x180015e38`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180015e85`
- `ole32!CoTaskMemFree` at `0x180015eb0`
- `ole32!CoTaskMemFree` at `0x180015e85`
- `ole32!CoTaskMemFree` at `0x180015eb0`

## pseudocode

```c
__int64 *__fastcall tip2::tip_test<tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>>::ensure_data(
        __int64 *a1)
{
  __int64 *v2; // rax
  __int64 v3; // rdx
  __int64 v4; // rbx
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  LPVOID pv; // [rsp+38h] [rbp+10h] BYREF

  if ( !*a1 )
  {
    v2 = tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>,>(&pv);
    v3 = *v2;
    *v2 = 0;
    v4 = *a1;
    *a1 = v3;
    if ( v4 && _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 272), 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>::~merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>((struct _RTL_CRITICAL_SECTION *)v4);
      CoTaskMemFree((LPVOID)v4);
    }
    v5 = (struct _RTL_CRITICAL_SECTION *)pv;
    if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 68, 0xFFFFFFFF) == 1 )
    {
      tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>::~merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>(v5);
      CoTaskMemFree(v5);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180015e38  mov     [rsp+arg_10], rbx
0x180015e3d  push    rdi
0x180015e3e  sub     rsp, 20h
0x180015e42  cmp     qword ptr [rcx], 0
0x180015e46  mov     rdi, rcx
0x180015e49  jnz     short loc_180015EB6
0x180015e4b  lea     rcx, [rsp+28h+pv]
0x180015e50  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>,>(void)
0x180015e55  mov     rdx, [rax]
0x180015e58  mov     qword ptr [rax], 0
0x180015e5f  mov     rbx, [rdi]
0x180015e62  mov     [rdi], rdx
0x180015e65  test    rbx, rbx
0x180015e68  jz      short loc_180015E8B
0x180015e6a  or      eax, 0FFFFFFFFh
0x180015e6d  lock xadd [rbx+110h], eax
0x180015e75  cmp     eax, 1
0x180015e78  jnz     short loc_180015E8B
0x180015e7a  mov     rcx, rbx
0x180015e7d  call    ??1?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>::~merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>(void)
0x180015e82  mov     rcx, rbx; pv
0x180015e85  call    cs:__imp_CoTaskMemFree
0x180015e8b  mov     rbx, [rsp+28h+pv]
0x180015e90  test    rbx, rbx
0x180015e93  jz      short loc_180015EB6
0x180015e95  or      eax, 0FFFFFFFFh
0x180015e98  lock xadd [rbx+110h], eax
0x180015ea0  cmp     eax, 1
0x180015ea3  jnz     short loc_180015EB6
0x180015ea5  mov     rcx, rbx
0x180015ea8  call    ??1?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>::~merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>(void)
0x180015ead  mov     rcx, rbx; pv
0x180015eb0  call    cs:__imp_CoTaskMemFree
0x180015eb6  mov     rbx, [rsp+28h+arg_10]
0x180015ebb  mov     rax, rdi
0x180015ebe  add     rsp, 20h
0x180015ec2  pop     rdi
0x180015ec3  retn
```
