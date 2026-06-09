# DataSharingServiceProvider::Provider(void)

- ea: `0x180005c54`
- end: `0x180005c6d`
- name: `?Provider@DataSharingServiceProvider@@SAPEBU_tlgProvider_t@@XZ`
- size: `25`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `13`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18000363c`
- `0x1800036c8`
- `0x180003754`
- `0x1800037e0`
- `0x18000386c`
- `0x1800038f8`
- `0x18000dd00`
- `0x18000e0d0`
- `0x18000e2a4`
- `0x18000e91c`
- `0x18000eacc`
- `0x18000ed70`
- `0x18000fe6c`

## callees

- `0x180007008`

## pseudocode

```c
const struct _tlgProvider_t *__fastcall DataSharingServiceProvider::Provider(__int64 a1)
{
  return (const struct _tlgProvider_t *)wil::details::static_lazy<DataSharingServiceProvider>::get(
                                          a1,
                                          (void (__cdecl *)())_lambda_516246e1a7538b052c962fd1d8e5a4d6_::_lambda_invoker_cdecl_)[1];
}

```

## disassembly

```asm
0x180005c54  sub     rsp, 28h
0x180005c58  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_516246e1a7538b052c962fd1d8e5a4d6_@@CA@XZ; _lambda_516246e1a7538b052c962fd1d8e5a4d6_::_lambda_invoker_cdecl_(void)
0x180005c5f  call    ?get@?$static_lazy@VDataSharingServiceProvider@@@details@wil@@QEAAPEAVDataSharingServiceProvider@@P6AXXZ@Z; wil::details::static_lazy<DataSharingServiceProvider>::get(void (*)(void))
0x180005c64  mov     rax, [rax+8]
0x180005c68  add     rsp, 28h
0x180005c6c  retn
```
