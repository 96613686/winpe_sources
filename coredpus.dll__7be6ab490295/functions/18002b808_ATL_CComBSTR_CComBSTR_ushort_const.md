# ATL::CComBSTR::CComBSTR(ushort const *)

- ea: `0x18002b808`
- end: `0x18002b840`
- name: `??0CComBSTR@ATL@@QEAA@PEBG@Z`
- size: `56`
- prototype: `_QWORD(ATL::CComBSTR *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180012d80`
- `0x18002c344`
- `0x18002d240`

## callees

- `0x180028a28`
- `0x18002b808`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002b826`
- `OLEAUT32!__imp_SysAllocString` at `0x18002b826`

## pseudocode

```c
ATL::CComBSTR *__fastcall ATL::CComBSTR::CComBSTR(ATL::CComBSTR *this, const unsigned __int16 *a2)
{
  BSTR v4; // rax
  int v5; // ecx

  if ( a2 )
  {
    v4 = SysAllocString(a2);
    *(_QWORD *)this = v4;
    if ( !v4 )
      ATL::AtlThrowImpl(v5);
  }
  else
  {
    *(_QWORD *)this = 0;
  }
  return this;
}

```

## disassembly

```asm
0x18002b808  push    rbx
0x18002b80a  sub     rsp, 20h
0x18002b80e  mov     rbx, rcx
0x18002b811  test    rdx, rdx
0x18002b814  jnz     short loc_18002B823
0x18002b816  mov     [rcx], rdx
0x18002b819  mov     rax, rbx
0x18002b81c  add     rsp, 20h
0x18002b820  pop     rbx
0x18002b821  retn
0x18002b823  mov     rcx, rdx; psz
0x18002b826  call    cs:__imp_SysAllocString
0x18002b82d  nop     dword ptr [rax+rax+00h]
0x18002b832  mov     [rbx], rax
0x18002b835  test    rax, rax
0x18002b838  jnz     short loc_18002B819
0x18002b83a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
