# wil::com_ptr_t<tip2::details::merged_data<_tip_OSKLifeTimeTest,_tip_OSKLifeTimeTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_OSKLifeTimeTest,_tip_OSKLifeTimeTest>,wil::err_returncode_policy>(void)

- ea: `0x140004f1c`
- end: `0x140004f32`
- name: `??1?$com_ptr_t@V?$merged_data@U_tip_OSKLifeTimeTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ`
- size: `22`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140004fd8`
- `0x140005010`
- `0x140005038`
- `0x140007f54`
- `0x14000ba30`

## callees

- `0x140004f1c`
- `0x1400094e4`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<tip2::details::merged_data<_tip_OSKLifeTimeTest,_tip_OSKLifeTimeTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_OSKLifeTimeTest,_tip_OSKLifeTimeTest>,wil::err_returncode_policy>(
        volatile signed __int32 **a1)
{
  volatile signed __int32 *v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return tip2::details::merged_data<_tip_OSKLifeTimeTest,_tip_OSKLifeTimeTest>::Release(v1);
  return result;
}

```

## disassembly

```asm
0x140004f1c  sub     rsp, 28h
0x140004f20  mov     rcx, [rcx]; pv
0x140004f23  test    rcx, rcx
0x140004f26  jz      short loc_140004F2D
0x140004f28  call    ?Release@?$merged_data@U_tip_OSKLifeTimeTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_OSKLifeTimeTest,_tip_OSKLifeTimeTest>::Release(void)
0x140004f2d  add     rsp, 28h
0x140004f31  retn
```
