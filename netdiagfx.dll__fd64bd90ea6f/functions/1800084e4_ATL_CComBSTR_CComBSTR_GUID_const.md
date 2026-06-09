# ATL::CComBSTR::CComBSTR(_GUID const &)

- ea: `0x1800084e4`
- end: `0x180008553`
- name: `??0CComBSTR@ATL@@QEAA@AEBU_GUID@@@Z`
- size: `111`
- prototype: `ATL::CComBSTR *__fastcall(ATL::CComBSTR *this, const struct _GUID *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000d2d8`
- `0x180028f00`
- `0x18002b178`

## callees

- `0x180005c18`
- `0x1800084e4`
- `0x18002c840`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000851e`
- `OLEAUT32!__imp_SysAllocString` at `0x18000851e`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180008513`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180008513`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
ATL::CComBSTR *__fastcall ATL::CComBSTR::CComBSTR(ATL::CComBSTR *this, const struct _GUID *a2)
{
  BSTR v3; // rax
  OLECHAR sz[64]; // [rsp+20h] [rbp-98h] BYREF

  StringFromGUID2(a2, sz, 64);
  v3 = SysAllocString(sz);
  *(_QWORD *)this = v3;
  if ( !v3 )
    ATL::AtlThrowImpl(-2147024882);
  return this;
}

```

## disassembly

```asm
0x1800084e4  push    rbx
0x1800084e6  sub     rsp, 0B0h
0x1800084ed  mov     rax, cs:__security_cookie
0x1800084f4  xor     rax, rsp
0x1800084f7  mov     [rsp+0B8h+var_18], rax
0x1800084ff  mov     rax, rdx
0x180008502  mov     rbx, rcx
0x180008505  mov     rcx, rax; rguid
0x180008508  lea     rdx, [rsp+0B8h+sz]; lpsz
0x18000850d  mov     r8d, 40h ; '@'; cchMax
0x180008513  call    cs:__imp_StringFromGUID2
0x180008519  lea     rcx, [rsp+0B8h+sz]; psz
0x18000851e  call    cs:__imp_SysAllocString
0x180008524  mov     [rbx], rax
0x180008527  test    rax, rax
0x18000852a  jnz     short loc_180008537
0x18000852c  mov     ecx, 8007000Eh; int
0x180008531  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180008537  mov     rax, rbx
0x18000853a  mov     rcx, [rsp+0B8h+var_18]
0x180008542  xor     rcx, rsp; StackCookie
0x180008545  call    __security_check_cookie
0x18000854a  add     rsp, 0B0h
0x180008551  pop     rbx
0x180008552  retn
```
