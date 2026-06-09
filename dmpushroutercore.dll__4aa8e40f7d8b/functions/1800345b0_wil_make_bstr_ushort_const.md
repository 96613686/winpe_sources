# wil::make_bstr(ushort const *)

- ea: `0x1800345b0`
- end: `0x1800345f6`
- name: `?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z`
- size: `70`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18002feec`

## callees

- `0x180034394`
- `0x1800345b0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800345cc`
- `OLEAUT32!__imp_SysAllocString` at `0x1800345cc`

## string_xrefs

- `0x1800345c5`: `OMADM::TargetedUserSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
BSTR *__fastcall wil::make_bstr(BSTR *a1)
{
  BSTR v2; // rax
  void *v3; // rdx
  unsigned int v4; // r8d
  const char *v5; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v2 = SysAllocString(L"OMADM::TargetedUserSID");
  *a1 = v2;
  if ( !v2 )
    wil::details::in1diag3::_Throw_NullAlloc(retaddr, v3, v4, v5);
  return a1;
}

```

## disassembly

```asm
0x1800345b0  mov     [rsp+arg_0], rcx
0x1800345b5  push    rbx
0x1800345b6  sub     rsp, 30h
0x1800345ba  mov     rbx, rcx
0x1800345bd  mov     [rsp+38h+var_18], 0
0x1800345c5  lea     rcx, psz; "OMADM::TargetedUserSID"
0x1800345cc  call    cs:__imp_SysAllocString
0x1800345d2  mov     [rbx], rax
0x1800345d5  mov     [rsp+38h+var_18], 1
0x1800345dd  mov     rcx, [rsp+38h]; this
0x1800345e2  test    rax, rax
0x1800345e5  jz      short loc_1800345F0
0x1800345e7  mov     rax, rbx
0x1800345ea  add     rsp, 30h
0x1800345ee  pop     rbx
0x1800345ef  retn
0x1800345f0  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
