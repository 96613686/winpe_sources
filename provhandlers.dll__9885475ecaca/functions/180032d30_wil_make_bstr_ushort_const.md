# wil::make_bstr(ushort const *)

- ea: `0x180032d30`
- end: `0x180032d7e`
- name: `?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z`
- size: `78`
- prototype: `BSTR *__fastcall(BSTR *, const OLECHAR *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18002cec4`
- `0x1800317c4`

## callees

- `0x180012da0`
- `0x180032d30`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180032d48`
- `OLEAUT32!__imp_SysAllocString` at `0x180032d48`

## string_xrefs

- `0x180032d6c`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
BSTR *__fastcall wil::make_bstr(BSTR *a1, const OLECHAR *a2)
{
  BSTR v3; // rax
  const char *v4; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v3 = SysAllocString(a2);
  *a1 = v3;
  if ( !v3 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x15F3,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      v4);
  return a1;
}

```

## disassembly

```asm
0x180032d30  mov     [rsp+arg_0], rcx
0x180032d35  push    rbx
0x180032d36  sub     rsp, 30h
0x180032d3a  mov     rbx, rcx
0x180032d3d  mov     [rsp+38h+var_18], 0
0x180032d45  mov     rcx, rdx; psz
0x180032d48  call    cs:__imp_SysAllocString
0x180032d4e  mov     [rbx], rax
0x180032d51  mov     [rsp+38h+var_18], 1
0x180032d59  mov     rcx, [rsp+38h]; this
0x180032d5e  test    rax, rax
0x180032d61  jz      short loc_180032D6C
0x180032d63  mov     rax, rbx
0x180032d66  add     rsp, 30h
0x180032d6a  pop     rbx
0x180032d6b  retn
0x180032d6c  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180032d73  mov     edx, 15F3h; void *
0x180032d78  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
