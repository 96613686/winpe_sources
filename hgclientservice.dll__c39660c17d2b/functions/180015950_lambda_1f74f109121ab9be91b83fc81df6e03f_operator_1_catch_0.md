# __lambda_1f74f109121ab9be91b83fc81df6e03f_::operator()_::_1_::catch$0

- ea: `0x180015950`
- end: `0x180015984`
- name: `__lambda_1f74f109121ab9be91b83fc81df6e03f_::operator()_::_1_::catch$0`
- size: `52`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180005d84`

## string_xrefs

- `0x180015961`: `servercommon\base\securehostingservice\common\service\lib\hgservice.cpp`

## pseudocode

```c
__int64 __fastcall _lambda_1f74f109121ab9be91b83fc81df6e03f_::operator()_::_1_::catch_0(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 88),
    (void *)0x4E,
    (int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservice.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x180015950  mov     [rsp+arg_8], rdx
0x180015955  push    rbp
0x180015956  sub     rsp, 30h
0x18001595a  mov     rbp, rdx
0x18001595d  mov     rcx, [rbp+58h]; this
0x180015961  lea     r8, aServercommonBa_0; "servercommon\\base\\securehostingservic"...
0x180015968  mov     edx, 4Eh ; 'N'; void *
0x18001596d  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x180015972  nop
0x180015973  mov     rax, 0
0x18001597d  add     rsp, 30h
0x180015981  pop     rbp
0x180015982  retn
```
