# wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>::operator=(wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy> &&)

- ea: `0x180023b80`
- end: `0x180023bad`
- name: `??4?$com_ptr_t@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z`
- size: `45`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024604`
- `0x18002753c`
- `0x1800294d4`
- `0x18002aa10`
- `0x18002ad88`
- `0x18002b23c`
- `0x18002c794`

## callees

- `0x180023b80`
- `0x1800295c4`

## pseudocode

```c
volatile signed __int32 **__fastcall wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>::operator=(
        volatile signed __int32 **a1,
        volatile signed __int32 **a2)
{
  volatile signed __int32 *v2; // rax
  volatile signed __int32 *v4; // rcx

  v2 = *a2;
  *a2 = 0;
  v4 = *a1;
  *a1 = v2;
  if ( v4 )
    tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>::Release(v4);
  return a1;
}

```

## disassembly

```asm
0x180023b80  push    rbx
0x180023b82  sub     rsp, 20h
0x180023b86  mov     rax, [rdx]
0x180023b89  mov     rbx, rcx
0x180023b8c  mov     qword ptr [rdx], 0
0x180023b93  mov     rcx, [rcx]; pv
0x180023b96  mov     [rbx], rax
0x180023b99  test    rcx, rcx
0x180023b9c  jz      short loc_180023BA3
0x180023b9e  call    ?Release@?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>::Release(void)
0x180023ba3  mov     rax, rbx
0x180023ba6  add     rsp, 20h
0x180023baa  pop     rbx
0x180023bab  retn
```
