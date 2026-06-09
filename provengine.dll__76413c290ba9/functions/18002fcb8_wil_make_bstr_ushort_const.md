# wil::make_bstr(ushort const *)

- ea: `0x18002fcb8`
- end: `0x18002fd06`
- name: `?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z`
- size: `78`
- prototype: `BSTR *__fastcall(BSTR *, const OLECHAR *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002fd10`

## callees

- `0x180021d14`
- `0x18002fcb8`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002fcd0`
- `OLEAUT32!__imp_SysAllocString` at `0x18002fcd0`

## string_xrefs

- `0x18002fcf4`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v4);
  return a1;
}

```

## disassembly

```asm
0x18002fcb8  mov     [rsp+arg_0], rcx
0x18002fcbd  push    rbx
0x18002fcbe  sub     rsp, 30h
0x18002fcc2  mov     rbx, rcx
0x18002fcc5  mov     [rsp+38h+var_18], 0
0x18002fccd  mov     rcx, rdx; psz
0x18002fcd0  call    cs:__imp_SysAllocString
0x18002fcd6  mov     [rbx], rax
0x18002fcd9  mov     [rsp+38h+var_18], 1
0x18002fce1  mov     rcx, [rsp+38h]; this
0x18002fce6  test    rax, rax
0x18002fce9  jz      short loc_18002FCF4
0x18002fceb  mov     rax, rbx
0x18002fcee  add     rsp, 30h
0x18002fcf2  pop     rbx
0x18002fcf3  retn
0x18002fcf4  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002fcfb  mov     edx, 15F3h; void *
0x18002fd00  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
