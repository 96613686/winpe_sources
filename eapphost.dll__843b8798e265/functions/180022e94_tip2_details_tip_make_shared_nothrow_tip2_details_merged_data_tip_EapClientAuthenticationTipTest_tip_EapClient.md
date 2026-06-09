# tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,_GUID * &>(_GUID * &)

- ea: `0x180022e94`
- end: `0x180022edd`
- name: `??$tip_make_shared_nothrow@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@AEAPEAU_GUID@@@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@AEAPEAU_GUID@@@Z`
- size: `73`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180024604`
- `0x18002753c`
- `0x1800294d4`
- `0x18002aa10`
- `0x18002ad88`
- `0x18002b23c`

## callees

- `0x180009b10`
- `0x180022e94`
- `0x1800230a8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022ea9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022ea9`

## pseudocode

```c
_QWORD *__fastcall tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,_GUID * &>(
        _QWORD *a1,
        _QWORD *a2)
{
  LPVOID v4; // rax
  wil::details::in1diag3 *v5; // rcx

  v4 = CoTaskMemAlloc(0x158u);
  if ( !v4 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v5);
  *a1 = tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>(
          v4,
          *a2);
  return a1;
}

```

## disassembly

```asm
0x180022e94  mov     [rsp+arg_0], rbx
0x180022e99  push    rdi
0x180022e9a  sub     rsp, 20h
0x180022e9e  mov     rbx, rcx
0x180022ea1  mov     rdi, rdx
0x180022ea4  mov     ecx, 158h; cb
0x180022ea9  call    cs:__imp_CoTaskMemAlloc
0x180022eb0  nop     dword ptr [rax+rax+00h]
0x180022eb5  test    rax, rax
0x180022eb8  jz      short loc_180022ED7
0x180022eba  mov     rdx, [rdi]
0x180022ebd  mov     rcx, rax
0x180022ec0  call    ??0?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@QEAA@PEAU_GUID@@@Z; tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>(_GUID *)
0x180022ec5  mov     [rbx], rax
0x180022ec8  mov     rax, rbx
0x180022ecb  mov     rbx, [rsp+28h+arg_0]
0x180022ed0  add     rsp, 20h
0x180022ed4  pop     rdi
0x180022ed5  retn
0x180022ed7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
