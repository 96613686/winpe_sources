# FileExplorerLogging::Provider(void)

- ea: `0x180010b7c`
- end: `0x180010b95`
- name: `?Provider@FileExplorerLogging@@SAPEBU_tlgProvider_t@@XZ`
- size: `25`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x18000fa08`
- `0x180010790`
- `0x180011308`
- `0x1800113c8`
- `0x1800114fc`
- `0x1800115e0`
- `0x180011810`
- `0x180011d2c`

## callees

- `0x180011ba0`

## pseudocode

```c
const struct _tlgProvider_t *__fastcall FileExplorerLogging::Provider(__int64 a1)
{
  return *(const struct _tlgProvider_t **)(wil::details::static_lazy<FileExplorerLogging>::get(
                                             a1,
                                             _lambda_ef118433b3637342f6c5dfe6692936b5_::_lambda_invoker_cdecl_)
                                         + 8);
}

```

## disassembly

```asm
0x180010b7c  sub     rsp, 28h
0x180010b80  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_ef118433b3637342f6c5dfe6692936b5_@@CA@XZ; _lambda_ef118433b3637342f6c5dfe6692936b5_::_lambda_invoker_cdecl_(void)
0x180010b87  call    ?get@?$static_lazy@VFileExplorerLogging@@@details@wil@@QEAAPEAVFileExplorerLogging@@P6AXXZ@Z; wil::details::static_lazy<FileExplorerLogging>::get(void (*)(void))
0x180010b8c  mov     rax, [rax+8]
0x180010b90  add     rsp, 28h
0x180010b94  retn
```
