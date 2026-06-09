# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x18001eef0`
- end: `0x18001ef53`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001ef94`
- `0x18001fed0`

## callees

- `0x180016ddc`
- `0x18001eef0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ef10`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ef10`

## string_xrefs

- `0x18001ef41`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  _WORD *v6; // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a3 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF89,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      a4);
  v6 = LocalAlloc(0, 2 * a3 + 2);
  if ( v6 )
  {
    *v6 = 0;
    v6[a3] = 0;
  }
  *a1 = v6;
  return a1;
}

```

## disassembly

```asm
0x18001eef0  mov     [rsp+arg_0], rbx
0x18001eef5  push    rdi
0x18001eef6  sub     rsp, 20h
0x18001eefa  mov     rdi, r8
0x18001eefd  mov     rbx, rcx
0x18001ef00  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18001ef04  jz      short loc_18001EF3C
0x18001ef06  lea     rdx, ds:2[r8*2]; uBytes
0x18001ef0e  xor     ecx, ecx; uFlags
0x18001ef10  call    cs:__imp_LocalAlloc
0x18001ef17  nop     dword ptr [rax+rax+00h]
0x18001ef1c  test    rax, rax
0x18001ef1f  jz      short loc_18001EF2A
0x18001ef21  xor     ecx, ecx
0x18001ef23  mov     [rax], cx
0x18001ef26  mov     [rax+rdi*2], cx
0x18001ef2a  mov     [rbx], rax
0x18001ef2d  mov     rax, rbx
0x18001ef30  mov     rbx, [rsp+28h+arg_0]
0x18001ef35  add     rsp, 20h
0x18001ef39  pop     rdi
0x18001ef3a  retn
0x18001ef3c  mov     rcx, [rsp+28h]; this
0x18001ef41  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001ef48  mov     edx, 0F89h; void *
0x18001ef4d  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
