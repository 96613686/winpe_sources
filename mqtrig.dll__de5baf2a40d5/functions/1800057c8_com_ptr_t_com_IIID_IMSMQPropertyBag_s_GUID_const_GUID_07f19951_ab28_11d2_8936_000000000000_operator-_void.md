# _com_ptr_t<_com_IIID<IMSMQPropertyBag,&__s_GUID const _GUID_07f19951_ab28_11d2_8936_000000000000>>::operator->(void)

- ea: `0x1800057c8`
- end: `0x1800057e4`
- name: `??C?$_com_ptr_t@V?$_com_IIID@UIMSMQPropertyBag@@$1?_GUID_07f19951_ab28_11d2_8936_000000000000@@3U__s_GUID@@B@@@@QEBAPEAUIMSMQPropertyBag@@XZ`
- size: `28`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005df4`
- `0x180006ef0`

## callees

- `0x1800057c8`
- `0x180014920`

## pseudocode

```c
__int64 __fastcall _com_ptr_t<_com_IIID<IMSMQPropertyBag,&__s_GUID const _GUID_07f19951_ab28_11d2_8936_000000000000>>::operator->(
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
0x1800057c8  sub     rsp, 28h
0x1800057cc  mov     rax, [rcx]
0x1800057cf  test    rax, rax
0x1800057d2  jnz     short loc_1800057DF
0x1800057d4  mov     ecx, 80004003h; int
0x1800057d9  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1800057df  add     rsp, 28h
0x1800057e3  retn
```
