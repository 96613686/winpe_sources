# wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>::operator=(wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy> &&)

- ea: `0x180022f18`
- end: `0x180022f44`
- name: `??4?$com_ptr_t@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z`
- size: `44`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023924`
- `0x1800267d0`
- `0x1800286c8`
- `0x180029bc0`
- `0x180029f3c`
- `0x18002a414`
- `0x18002b814`

## callees

- `0x180022f18`
- `0x1800287e0`

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
0x180022f18  push    rbx
0x180022f1a  sub     rsp, 20h
0x180022f1e  mov     rax, [rdx]
0x180022f21  mov     rbx, rcx
0x180022f24  mov     qword ptr [rdx], 0
0x180022f2b  mov     rcx, [rcx]; pv
0x180022f2e  mov     [rbx], rax
0x180022f31  test    rcx, rcx
0x180022f34  jz      short loc_180022F3B
0x180022f36  call    ?Release@?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>::Release(void)
0x180022f3b  mov     rax, rbx
0x180022f3e  add     rsp, 20h
0x180022f42  pop     rbx
0x180022f43  retn
```
