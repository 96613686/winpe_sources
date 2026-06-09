# ATL::CComBSTR::operator=(ATL::CComBSTR const &)

- ea: `0x180003b70`
- end: `0x180003bac`
- name: `??4CComBSTR@ATL@@QEAAAEAV01@AEBV01@@Z`
- size: `60`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180004bb4`
- `0x180005eac`
- `0x180005f34`
- `0x180006c40`
- `0x1800085c0`
- `0x180008720`

## callees

- `0x180003b70`
- `0x18000406c`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180003b8d`
- `OLEAUT32!__imp_SysFreeString` at `0x180003b8d`

## pseudocode

```c
OLECHAR **__fastcall ATL::CComBSTR::operator=(OLECHAR **a1, ATL::CComBSTR *a2)
{
  OLECHAR *v4; // rcx

  v4 = *a1;
  if ( v4 != *(OLECHAR **)a2 )
  {
    if ( v4 )
      SysFreeString(v4);
    *a1 = ATL::CComBSTR::Copy(a2);
  }
  return a1;
}

```

## disassembly

```asm
0x180003b70  mov     [rsp+arg_0], rbx
0x180003b75  push    rdi
0x180003b76  sub     rsp, 20h
0x180003b7a  mov     rbx, rcx
0x180003b7d  mov     rdi, rdx
0x180003b80  mov     rcx, [rcx]; bstrString
0x180003b83  cmp     rcx, [rdx]
0x180003b86  jz      short loc_180003B9E
0x180003b88  test    rcx, rcx
0x180003b8b  jz      short loc_180003B93
0x180003b8d  call    cs:__imp_SysFreeString
0x180003b93  mov     rcx, rdi; this
0x180003b96  call    ?Copy@CComBSTR@ATL@@QEBAPEA_WXZ; ATL::CComBSTR::Copy(void)
0x180003b9b  mov     [rbx], rax
0x180003b9e  mov     rax, rbx
0x180003ba1  mov     rbx, [rsp+28h+arg_0]
0x180003ba6  add     rsp, 20h
0x180003baa  pop     rdi
0x180003bab  retn
```
