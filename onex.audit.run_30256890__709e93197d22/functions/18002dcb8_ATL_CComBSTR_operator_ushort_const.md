# ATL::CComBSTR::operator=(ushort const *)

- ea: `0x18002dcb8`
- end: `0x18002dd07`
- name: `??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002dd30`

## callees

- `0x18002dcb8`
- `0x18002dd10`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002dcde`
- `OLEAUT32!__imp_SysAllocString` at `0x18002dcde`
- `OLEAUT32!__imp_SysFreeString` at `0x18002dcd0`
- `OLEAUT32!__imp_SysFreeString` at `0x18002dcd0`

## pseudocode

```c
BSTR *__fastcall ATL::CComBSTR::operator=(BSTR *a1, const OLECHAR *a2)
{
  BSTR v4; // rax
  int v5; // ecx

  if ( a2 != *a1 )
  {
    SysFreeString(*a1);
    if ( a2 )
    {
      v4 = SysAllocString(a2);
      *a1 = v4;
      if ( !v4 )
        ATL::AtlThrowImpl(v5);
    }
    else
    {
      *a1 = 0;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18002dcb8  mov     [rsp+arg_0], rbx
0x18002dcbd  push    rdi
0x18002dcbe  sub     rsp, 20h
0x18002dcc2  mov     rdi, rdx
0x18002dcc5  mov     rbx, rcx
0x18002dcc8  cmp     rdx, [rcx]
0x18002dccb  jz      short loc_18002DCF9
0x18002dccd  mov     rcx, [rcx]; bstrString
0x18002dcd0  call    cs:__imp_SysFreeString
0x18002dcd6  test    rdi, rdi
0x18002dcd9  jz      short loc_18002DCF2
0x18002dcdb  mov     rcx, rdi; psz
0x18002dcde  call    cs:__imp_SysAllocString
0x18002dce4  mov     [rbx], rax
0x18002dce7  test    rax, rax
0x18002dcea  jnz     short loc_18002DCF9
0x18002dcec  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002dcf2  mov     qword ptr [rbx], 0
0x18002dcf9  mov     rax, rbx
0x18002dcfc  mov     rbx, [rsp+28h+arg_0]
0x18002dd01  add     rsp, 20h
0x18002dd05  pop     rdi
0x18002dd06  retn
```
