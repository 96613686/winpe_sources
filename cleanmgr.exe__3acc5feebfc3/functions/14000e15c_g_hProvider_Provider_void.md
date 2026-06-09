# g_hProvider::Provider(void)

- ea: `0x14000e15c`
- end: `0x14000e175`
- name: `?Provider@g_hProvider@@SAPEBU_tlgProvider_t@@XZ`
- size: `25`
- prototype: `const struct _tlgProvider_t *__fastcall(__int64)`
- caller_count: `19`
- callee_count: `1`
- tags: ``

## callers

- `0x14000bae4`
- `0x14000f314`
- `0x14000f660`
- `0x14000f788`
- `0x14000f8a8`
- `0x14000fd68`
- `0x14000fe8c`
- `0x140010030`
- `0x14001037c`
- `0x140010e00`
- `0x140011030`
- `0x140011260`
- `0x140011490`
- `0x1400116c0`
- `0x1400118f0`
- `0x140011b20`
- `0x140012a7c`
- `0x140013530`
- `0x140014fe0`

## callees

- `0x14000ed4c`

## pseudocode

```c
const struct _tlgProvider_t *__fastcall g_hProvider::Provider(__int64 a1)
{
  return *(const struct _tlgProvider_t **)(wil::details::static_lazy<g_hProvider>::get(
                                             a1,
                                             _lambda_5b68f498586f253f299c6877d40e642b_::_lambda_invoker_cdecl_)
                                         + 8);
}

```

## disassembly

```asm
0x14000e15c  sub     rsp, 28h
0x14000e160  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5b68f498586f253f299c6877d40e642b_@@CA@XZ; _lambda_5b68f498586f253f299c6877d40e642b_::_lambda_invoker_cdecl_(void)
0x14000e167  call    ?get@?$static_lazy@Vg_hProvider@@@details@wil@@QEAAPEAVg_hProvider@@P6AXXZ@Z; wil::details::static_lazy<g_hProvider>::get(void (*)(void))
0x14000e16c  mov     rax, [rax+8]
0x14000e170  add     rsp, 28h
0x14000e174  retn
```
