# DirectXDatabaseUpdaterLogging::Provider(void)

- ea: `0x14000946c`
- end: `0x140009485`
- name: `?Provider@DirectXDatabaseUpdaterLogging@@SAPEBU_tlgProvider_t@@XZ`
- size: `25`
- prototype: `const struct _tlgProvider_t *__fastcall(__int64)`
- caller_count: `18`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140008e10`
- `0x140009460`
- `0x14000ac0c`
- `0x14000ad00`
- `0x14000adcc`
- `0x14000ae8c`
- `0x14000af4c`
- `0x14000b00c`
- `0x14000b5fc`
- `0x14000b6e4`
- `0x14000b93c`
- `0x14000bb94`
- `0x14000be40`
- `0x14000c070`
- `0x14000c2a0`
- `0x14000c4d0`
- `0x14000c700`
- `0x14000c930`

## callees

- `0x14000e1c0`

## pseudocode

```c
const struct _tlgProvider_t *__fastcall DirectXDatabaseUpdaterLogging::Provider(__int64 a1)
{
  return (const struct _tlgProvider_t *)wil::details::static_lazy<DirectXDatabaseUpdaterLogging>::get(
                                          a1,
                                          (void (__cdecl *)())_lambda_4584331c7c235ab1bc19f4fa446ba6ef_::_lambda_invoker_cdecl_)[1];
}

```

## disassembly

```asm
0x14000946c  sub     rsp, 28h
0x140009470  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_4584331c7c235ab1bc19f4fa446ba6ef_@@CA@XZ; _lambda_4584331c7c235ab1bc19f4fa446ba6ef_::_lambda_invoker_cdecl_(void)
0x140009477  call    ?get@?$static_lazy@VDirectXDatabaseUpdaterLogging@@@details@wil@@QEAAPEAVDirectXDatabaseUpdaterLogging@@P6AXXZ@Z; wil::details::static_lazy<DirectXDatabaseUpdaterLogging>::get(void (*)(void))
0x14000947c  mov     rax, [rax+8]
0x140009480  add     rsp, 28h
0x140009484  retn
```
