# tip2::tip_test<tip2::details::merged_data<_tip_OSKLifeTimeTest,_tip_OSKLifeTimeTest>>::ensure_data(void)

- ea: `0x14000ba30`
- end: `0x14000ba76`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_OSKLifeTimeTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_OSKLifeTimeTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `70`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400055c4`
- `0x140007f54`

## callees

- `0x14000454c`
- `0x140004f1c`
- `0x1400094e4`
- `0x14000ba30`

## pseudocode

```c
volatile signed __int32 **__fastcall tip2::tip_test<tip2::details::merged_data<_tip_OSKLifeTimeTest,_tip_OSKLifeTimeTest>>::ensure_data(
        volatile signed __int32 **a1)
{
  volatile signed __int32 **v2; // rax
  volatile signed __int32 *v3; // rdx
  volatile signed __int32 *v4; // rcx
  volatile signed __int32 *v6; // [rsp+30h] [rbp+8h] BYREF

  if ( !*a1 )
  {
    v2 = (volatile signed __int32 **)tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_OSKLifeTimeTest,_tip_OSKLifeTimeTest>,>(&v6);
    v3 = *v2;
    *v2 = 0;
    v4 = *a1;
    *a1 = v3;
    if ( v4 )
      tip2::details::merged_data<_tip_OSKLifeTimeTest,_tip_OSKLifeTimeTest>::Release(v4);
    wil::com_ptr_t<tip2::details::merged_data<_tip_OSKLifeTimeTest,_tip_OSKLifeTimeTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_OSKLifeTimeTest,_tip_OSKLifeTimeTest>,wil::err_returncode_policy>(&v6);
  }
  return a1;
}

```

## disassembly

```asm
0x14000ba30  push    rbx
0x14000ba32  sub     rsp, 20h
0x14000ba36  cmp     qword ptr [rcx], 0
0x14000ba3a  mov     rbx, rcx
0x14000ba3d  jnz     short loc_14000BA6D
0x14000ba3f  lea     rcx, [rsp+28h+arg_0]
0x14000ba44  call    ??$tip_make_shared_nothrow@V?$merged_data@U_tip_OSKLifeTimeTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_OSKLifeTimeTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_OSKLifeTimeTest,_tip_OSKLifeTimeTest>,>(void)
0x14000ba49  mov     rdx, [rax]
0x14000ba4c  mov     qword ptr [rax], 0
0x14000ba53  mov     rcx, [rbx]; pv
0x14000ba56  mov     [rbx], rdx
0x14000ba59  test    rcx, rcx
0x14000ba5c  jz      short loc_14000BA63
0x14000ba5e  call    ?Release@?$merged_data@U_tip_OSKLifeTimeTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_OSKLifeTimeTest,_tip_OSKLifeTimeTest>::Release(void)
0x14000ba63  lea     rcx, [rsp+28h+arg_0]
0x14000ba68  call    ??1?$com_ptr_t@V?$merged_data@U_tip_OSKLifeTimeTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_OSKLifeTimeTest,_tip_OSKLifeTimeTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_OSKLifeTimeTest,_tip_OSKLifeTimeTest>,wil::err_returncode_policy>(void)
0x14000ba6d  mov     rax, rbx
0x14000ba70  add     rsp, 20h
0x14000ba74  pop     rbx
0x14000ba75  retn
```
