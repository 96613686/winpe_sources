# wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x180042b40`
- end: `0x180042ba2`
- name: `??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `98`
- prototype: `__int64 __fastcall(HSTRING *string, PCNZWCH sourceString)`
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001fb70`
- `0x180020cb0`
- `0x180021de0`
- `0x18002ba90`
- `0x18002c8d0`
- `0x18002d710`

## callees

- `0x18001ae50`
- `0x180042b40`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180042b71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180042b71`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HSTRING *__fastcall wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
        HSTRING *string,
        PCNZWCH sourceString)
{
  __int64 v4; // rdx
  unsigned int v5; // r8d
  const char *v6; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v4 = -1;
  do
    ++v4;
  while ( sourceString[v4] );
  *string = 0;
  WindowsCreateString(sourceString, v4, string);
  if ( !*string )
    wil::details::in1diag3::_Throw_NullAlloc(retaddr, (void *)0xFF8, v5, v6);
  return string;
}

```

## disassembly

```asm
0x180042b40  mov     [rsp+arg_8], rbx
0x180042b45  mov     [rsp+arg_0], rcx
0x180042b4a  push    rdi
0x180042b4b  sub     rsp, 30h
0x180042b4f  mov     rax, rdx
0x180042b52  mov     rbx, rcx
0x180042b55  xor     edi, edi
0x180042b57  mov     [rsp+38h+var_18], edi
0x180042b5b  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180042b5f  inc     rdx; length
0x180042b62  cmp     [rax+rdx*2], di
0x180042b66  jnz     short loc_180042B5F
0x180042b68  mov     [rcx], rdi
0x180042b6b  mov     r8, rbx; string
0x180042b6e  mov     rcx, rax; sourceString
0x180042b71  call    cs:__imp_WindowsCreateString
0x180042b77  mov     [rsp+38h+var_18], 1
0x180042b7f  mov     rcx, [rsp+38h]; this
0x180042b84  cmp     [rbx], rdi
0x180042b87  jz      short loc_180042B97
0x180042b89  mov     rax, rbx
0x180042b8c  mov     rbx, [rsp+38h+arg_8]
0x180042b91  add     rsp, 30h
0x180042b95  pop     rdi
0x180042b96  retn
0x180042b97  mov     edx, 0FF8h; void *
0x180042b9c  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
