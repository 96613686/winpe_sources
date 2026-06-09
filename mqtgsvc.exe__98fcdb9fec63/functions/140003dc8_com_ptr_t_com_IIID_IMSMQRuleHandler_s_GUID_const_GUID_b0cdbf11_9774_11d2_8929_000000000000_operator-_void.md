# _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->(void)

- ea: `0x140003dc8`
- end: `0x140003de4`
- name: `??C?$_com_ptr_t@V?$_com_IIID@UIMSMQRuleHandler@@$1?_GUID_b0cdbf11_9774_11d2_8929_000000000000@@3U__s_GUID@@B@@@@QEBAPEAUIMSMQRuleHandler@@XZ`
- size: `28`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `18`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140003f54`
- `0x1400082d4`
- `0x14000858c`
- `0x140008b60`
- `0x140008f50`
- `0x140009358`
- `0x140009854`
- `0x14000a6dc`
- `0x14000b43c`
- `0x14000b6f0`
- `0x14000b984`
- `0x14000baa8`
- `0x14000bdc0`
- `0x14000c0e0`
- `0x14000d110`
- `0x14000d4a8`
- `0x14000d648`
- `0x14000e768`

## callees

- `0x140003dc8`
- `0x14000ec24`

## pseudocode

```c
__int64 __fastcall _com_ptr_t<_com_IIID<IMSMQRuleHandler,&__s_GUID const _GUID_b0cdbf11_9774_11d2_8929_000000000000>>::operator->(
        __int64 *a1)
{
  __int64 result; // rax

  result = *a1;
  if ( !*a1 )
    _com_issue_error(-2147467261);
  return result;
}

```

## disassembly

```asm
0x140003dc8  sub     rsp, 28h
0x140003dcc  mov     rax, [rcx]
0x140003dcf  test    rax, rax
0x140003dd2  jnz     short loc_140003DDF
0x140003dd4  mov     ecx, 80004003h; int
0x140003dd9  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x140003ddf  add     rsp, 28h
0x140003de3  retn
```
