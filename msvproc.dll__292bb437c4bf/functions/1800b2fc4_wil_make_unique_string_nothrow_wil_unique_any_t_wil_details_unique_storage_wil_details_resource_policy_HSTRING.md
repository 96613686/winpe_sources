# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x1800b2fc4`
- end: `0x1800b3013`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `79`
- prototype: `__int64 __fastcall(HSTRING *string, PCNZWCH sourceString)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800444ec`

## callees

- `0x180066474`
- `0x1800b2fc4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800b2ffa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800b2ffa`

## pseudocode

```c
HSTRING *__fastcall wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
        HSTRING *string,
        PCNZWCH sourceString)
{
  __int64 v2; // rbx

  v2 = -1;
  do
    ++v2;
  while ( sourceString[v2] );
  *string = 0;
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
    string,
    0);
  WindowsCreateString(sourceString, v2, string);
  return string;
}

```

## disassembly

```asm
0x1800b2fc4  mov     [rsp+arg_0], rbx
0x1800b2fc9  mov     [rsp+arg_8], rsi
0x1800b2fce  push    rdi
0x1800b2fcf  sub     rsp, 20h
0x1800b2fd3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800b2fd7  mov     rsi, rdx
0x1800b2fda  xor     eax, eax
0x1800b2fdc  mov     rdi, rcx
0x1800b2fdf  inc     rbx
0x1800b2fe2  cmp     [rdx+rbx*2], ax
0x1800b2fe6  jnz     short loc_1800B2FDF
0x1800b2fe8  xor     edx, edx
0x1800b2fea  mov     [rcx], rax
0x1800b2fed  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x1800b2ff2  mov     edx, ebx; length
0x1800b2ff4  mov     r8, rdi; string
0x1800b2ff7  mov     rcx, rsi; sourceString
0x1800b2ffa  call    cs:__imp_WindowsCreateString
0x1800b3000  mov     rbx, [rsp+28h+arg_0]
0x1800b3005  mov     rax, rdi
0x1800b3008  mov     rsi, [rsp+28h+arg_8]
0x1800b300d  add     rsp, 20h
0x1800b3011  pop     rdi
0x1800b3012  retn
```
