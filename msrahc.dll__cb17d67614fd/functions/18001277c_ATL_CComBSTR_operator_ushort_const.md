# ATL::CComBSTR::operator=(ushort const *)

- ea: `0x18001277c`
- end: `0x1800127d0`
- name: `??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z`
- size: `84`
- prototype: `BSTR *__fastcall(BSTR *, const OLECHAR *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800142c0`
- `0x1800142e0`
- `0x180014300`

## callees

- `0x180009e80`
- `0x18001277c`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800127a2`
- `OLEAUT32!__imp_SysAllocString` at `0x1800127a2`
- `OLEAUT32!__imp_SysFreeString` at `0x180012794`
- `OLEAUT32!__imp_SysFreeString` at `0x180012794`

## pseudocode

```c
BSTR *__fastcall ATL::CComBSTR::operator=(BSTR *a1, const OLECHAR *a2)
{
  BSTR v4; // rax

  if ( a2 != *a1 )
  {
    SysFreeString(*a1);
    if ( a2 )
    {
      v4 = SysAllocString(a2);
      *a1 = v4;
      if ( !v4 )
        ATL::AtlThrowImpl(-2147024882);
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
0x18001277c  mov     [rsp+arg_0], rbx
0x180012781  push    rdi
0x180012782  sub     rsp, 20h
0x180012786  mov     rdi, rdx
0x180012789  mov     rbx, rcx
0x18001278c  cmp     rdx, [rcx]
0x18001278f  jz      short loc_1800127C2
0x180012791  mov     rcx, [rcx]; bstrString
0x180012794  call    cs:__imp_SysFreeString
0x18001279a  test    rdi, rdi
0x18001279d  jz      short loc_1800127BB
0x18001279f  mov     rcx, rdi; psz
0x1800127a2  call    cs:__imp_SysAllocString
0x1800127a8  mov     [rbx], rax
0x1800127ab  test    rax, rax
0x1800127ae  jnz     short loc_1800127C2
0x1800127b0  mov     ecx, 8007000Eh; int
0x1800127b5  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800127bb  mov     qword ptr [rbx], 0
0x1800127c2  mov     rax, rbx
0x1800127c5  mov     rbx, [rsp+28h+arg_0]
0x1800127ca  add     rsp, 20h
0x1800127ce  pop     rdi
0x1800127cf  retn
```
