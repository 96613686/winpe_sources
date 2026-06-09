# wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>(void)

- ea: `0x180022b84`
- end: `0x180022b9a`
- name: `??1?$com_ptr_t@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ`
- size: `22`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180022c34`
- `0x180023924`
- `0x1800267d0`
- `0x1800286c8`
- `0x180029bc0`
- `0x180029f3c`
- `0x18002a414`
- `0x18002a4fc`
- `0x18002b814`

## callees

- `0x180022b84`
- `0x1800287e0`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>(
        volatile signed __int32 **a1)
{
  volatile signed __int32 *v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>::Release(v1);
  return result;
}

```

## disassembly

```asm
0x180022b84  sub     rsp, 28h
0x180022b88  mov     rcx, [rcx]; pv
0x180022b8b  test    rcx, rcx
0x180022b8e  jz      short loc_180022B95
0x180022b90  call    ?Release@?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>::Release(void)
0x180022b95  add     rsp, 28h
0x180022b99  retn
```
