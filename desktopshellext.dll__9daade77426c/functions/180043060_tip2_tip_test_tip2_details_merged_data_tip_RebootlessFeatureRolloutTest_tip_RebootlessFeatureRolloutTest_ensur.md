# tip2::tip_test<tip2::details::merged_data<_tip_RebootlessFeatureRolloutTest,_tip_RebootlessFeatureRolloutTest>>::ensure_data(void)

- ea: `0x180043060`
- end: `0x1800430b9`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_RebootlessFeatureRolloutTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_RebootlessFeatureRolloutTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `89`
- prototype: ``
- caller_count: `6`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180019b1c`
- `0x180019bd4`
- `0x180019cb4`
- `0x180019ce8`
- `0x180041090`
- `0x180041810`

## callees

- `0x180015cd4`
- `0x18002ed14`
- `0x180038edc`
- `0x180040434`
- `0x180043060`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180043074`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180043074`

## pseudocode

```c
void **__fastcall tip2::tip_test<tip2::details::merged_data<_tip_RebootlessFeatureRolloutTest,_tip_RebootlessFeatureRolloutTest>>::ensure_data(
        void **a1)
{
  LPVOID v2; // rax
  wil::details::in1diag3 *v3; // rcx
  __int64 v4; // rax
  void *v5; // rcx
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF

  if ( !*a1 )
  {
    v2 = CoTaskMemAlloc(0x140u);
    if ( !v2 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v3);
    v4 = tip2::details::merged_data<_tip_RebootlessFeatureRolloutTest,_tip_RebootlessFeatureRolloutTest>::merged_data<_tip_RebootlessFeatureRolloutTest,_tip_RebootlessFeatureRolloutTest>(v2);
    v5 = *a1;
    v7 = 0;
    *a1 = (void *)v4;
    if ( v5 )
      tip2::details::merged_data<_tip_RebootlessFeatureRolloutTest,_tip_RebootlessFeatureRolloutTest>::Release(v5);
    wil::com_ptr_t<tip2::details::merged_data<_tip_RebootlessFeatureRolloutTest,_tip_RebootlessFeatureRolloutTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_RebootlessFeatureRolloutTest,_tip_RebootlessFeatureRolloutTest>,wil::err_returncode_policy>(&v7);
  }
  return a1;
}

```

## disassembly

```asm
0x180043060  push    rbx
0x180043062  sub     rsp, 20h
0x180043066  cmp     qword ptr [rcx], 0
0x18004306a  mov     rbx, rcx
0x18004306d  jnz     short loc_1800430B0
0x18004306f  mov     ecx, 140h; cb
0x180043074  call    cs:__imp_CoTaskMemAlloc
0x18004307a  test    rax, rax
0x18004307d  jnz     short loc_180043085
0x18004307f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180043085  mov     rcx, rax
0x180043088  call    ??0?$merged_data@U_tip_RebootlessFeatureRolloutTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_RebootlessFeatureRolloutTest,_tip_RebootlessFeatureRolloutTest>::merged_data<_tip_RebootlessFeatureRolloutTest,_tip_RebootlessFeatureRolloutTest>(void)
0x18004308d  mov     rcx, [rbx]; pv
0x180043090  mov     [rsp+28h+arg_0], 0
0x180043099  mov     [rbx], rax
0x18004309c  test    rcx, rcx
0x18004309f  jz      short loc_1800430A6
0x1800430a1  call    ?Release@?$merged_data@U_tip_RebootlessFeatureRolloutTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_RebootlessFeatureRolloutTest,_tip_RebootlessFeatureRolloutTest>::Release(void)
0x1800430a6  lea     rcx, [rsp+28h+arg_0]
0x1800430ab  call    ??1?$com_ptr_t@V?$merged_data@U_tip_RebootlessFeatureRolloutTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_RebootlessFeatureRolloutTest,_tip_RebootlessFeatureRolloutTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_RebootlessFeatureRolloutTest,_tip_RebootlessFeatureRolloutTest>,wil::err_returncode_policy>(void)
0x1800430b0  mov     rax, rbx
0x1800430b3  add     rsp, 20h
0x1800430b7  pop     rbx
0x1800430b8  retn
```
