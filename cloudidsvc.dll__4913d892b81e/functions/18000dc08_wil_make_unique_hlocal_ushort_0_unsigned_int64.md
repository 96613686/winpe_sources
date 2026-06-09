# wil::make_unique_hlocal<ushort [0]>(unsigned __int64)

- ea: `0x18000dc08`
- end: `0x18000dc51`
- name: `??$make_unique_hlocal@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z`
- size: `73`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000eaf4`
- `0x18000f4ac`
- `0x180010488`

## callees

- `0x18000dc08`
- `0x18000dc58`
- `0x18000fd54`

## string_xrefs

- `0x18000dc35`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_hlocal<unsigned short [0]>(_QWORD *a1)
{
  const char *v2; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  wil::make_unique_hlocal_nothrow<unsigned short [0]>(a1);
  if ( !*a1 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x1321,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v2);
  return a1;
}

```

## disassembly

```asm
0x18000dc08  mov     [rsp+arg_0], rcx
0x18000dc0d  push    rbx
0x18000dc0e  sub     rsp, 30h
0x18000dc12  mov     rbx, rcx
0x18000dc15  mov     [rsp+38h+var_18], 0
0x18000dc1d  call    ??$make_unique_hlocal_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<ushort [0]>(unsigned __int64)
0x18000dc22  mov     [rsp+38h+var_18], 1
0x18000dc2a  mov     rcx, [rsp+38h]; this
0x18000dc2f  cmp     qword ptr [rbx], 0
0x18000dc33  jnz     short loc_18000DC47
0x18000dc35  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000dc3c  mov     edx, 1321h; void *
0x18000dc41  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18000dc47  mov     rax, rbx
0x18000dc4a  add     rsp, 30h
0x18000dc4e  pop     rbx
0x18000dc4f  retn
```
