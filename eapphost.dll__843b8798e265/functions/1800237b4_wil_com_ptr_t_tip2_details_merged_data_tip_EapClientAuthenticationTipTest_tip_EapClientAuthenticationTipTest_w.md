# wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>(void)

- ea: `0x1800237b4`
- end: `0x1800237cb`
- name: `??1?$com_ptr_t@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002386c`
- `0x180024604`
- `0x18002753c`
- `0x1800294d4`
- `0x18002aa10`
- `0x18002ad88`
- `0x18002b23c`
- `0x18002b310`
- `0x18002c794`

## callees

- `0x1800237b4`
- `0x1800295c4`

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
0x1800237b4  sub     rsp, 28h
0x1800237b8  mov     rcx, [rcx]; pv
0x1800237bb  test    rcx, rcx
0x1800237be  jz      short loc_1800237C5
0x1800237c0  call    ?Release@?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>::Release(void)
0x1800237c5  add     rsp, 28h
0x1800237c9  retn
```
