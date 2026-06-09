# tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_OSKLifeTimeTest,_tip_OSKLifeTimeTest>,>(void)

- ea: `0x14000454c`
- end: `0x14000457f`
- name: `??$tip_make_shared_nothrow@V?$merged_data@U_tip_OSKLifeTimeTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_OSKLifeTimeTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `51`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x140007f54`
- `0x14000ba30`

## callees

- `0x14000454c`
- `0x140004754`
- `0x14000b134`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x14000455a`
- `ole32!CoTaskMemAlloc` at `0x14000455a`

## pseudocode

```c
_QWORD *__fastcall tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_OSKLifeTimeTest,_tip_OSKLifeTimeTest>,>(
        _QWORD *a1)
{
  LPVOID v2; // rax
  wil::details::in1diag3 *v3; // rcx

  v2 = CoTaskMemAlloc(0x120u);
  if ( !v2 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v3);
  *a1 = tip2::details::merged_data<_tip_OSKLifeTimeTest,_tip_OSKLifeTimeTest>::merged_data<_tip_OSKLifeTimeTest,_tip_OSKLifeTimeTest>(v2);
  return a1;
}

```

## disassembly

```asm
0x14000454c  push    rbx
0x14000454e  sub     rsp, 20h
0x140004552  mov     rbx, rcx
0x140004555  mov     ecx, 120h; cb
0x14000455a  call    cs:__imp_CoTaskMemAlloc
0x140004560  test    rax, rax
0x140004563  jz      short loc_140004579
0x140004565  mov     rcx, rax
0x140004568  call    ??0?$merged_data@U_tip_OSKLifeTimeTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_OSKLifeTimeTest,_tip_OSKLifeTimeTest>::merged_data<_tip_OSKLifeTimeTest,_tip_OSKLifeTimeTest>(void)
0x14000456d  mov     [rbx], rax
0x140004570  mov     rax, rbx
0x140004573  add     rsp, 20h
0x140004577  pop     rbx
0x140004578  retn
0x140004579  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
