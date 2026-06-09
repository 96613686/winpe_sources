# wil::make_unique_ansistring_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(char const *,unsigned __int64)

- ea: `0x18002b184`
- end: `0x18002b1fd`
- name: `??$make_unique_ansistring_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@0@PEBD_K@Z`
- size: `121`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, __int64, const char *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800345cc`
- `0x180043bc4`

## callees

- `0x18000b5c8`
- `0x18002b184`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002b1b7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002b1b7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002b19f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002b19f`

## string_xrefs

- `0x18002b1eb`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_ansistring_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  HANDLE ProcessHeap; // rax
  _BYTE *v7; // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a3 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xFBD,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      a4);
  ProcessHeap = GetProcessHeap();
  v7 = HeapAlloc(ProcessHeap, 8u, a3 + 1);
  if ( v7 )
  {
    *v7 = 0;
    v7[a3] = 0;
  }
  *a1 = v7;
  return a1;
}

```

## disassembly

```asm
0x18002b184  mov     [rsp+arg_0], rbx
0x18002b189  mov     [rsp+arg_8], rsi
0x18002b18e  push    rdi
0x18002b18f  sub     rsp, 20h
0x18002b193  mov     rdi, r8
0x18002b196  mov     rsi, rcx
0x18002b199  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18002b19d  jz      short loc_18002B1E6
0x18002b19f  call    cs:__imp_GetProcessHeap
0x18002b1a6  nop     dword ptr [rax+rax+00h]
0x18002b1ab  lea     r8, [rdi+1]; dwBytes
0x18002b1af  mov     edx, 8; dwFlags
0x18002b1b4  mov     rcx, rax; hHeap
0x18002b1b7  call    cs:__imp_HeapAlloc
0x18002b1be  nop     dword ptr [rax+rax+00h]
0x18002b1c3  test    rax, rax
0x18002b1c6  jz      short loc_18002B1CF
0x18002b1c8  mov     byte ptr [rax], 0
0x18002b1cb  mov     byte ptr [rax+rdi], 0
0x18002b1cf  mov     rbx, [rsp+28h+arg_0]
0x18002b1d4  mov     [rsi], rax
0x18002b1d7  mov     rax, rsi
0x18002b1da  mov     rsi, [rsp+28h+arg_8]
0x18002b1df  add     rsp, 20h
0x18002b1e3  pop     rdi
0x18002b1e4  retn
0x18002b1e6  mov     rcx, [rsp+28h]; this
0x18002b1eb  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002b1f2  mov     edx, 0FBDh; void *
0x18002b1f7  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
