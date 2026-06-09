# ValidateXmlFormat

- ea: `0x18000d3e4`
- end: `0x18000d44b`
- name: `ValidateXmlFormat`
- size: `103`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000c3a0`

## callees

- `0x180007e10`
- `0x18000d3e4`
- `0x18001ecfc`
- `0x18001edc0`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ValidateXmlFormat(const wchar_t *a1)
{
  unsigned int v3; // [rsp+20h] [rbp-18h] BYREF
  const wchar_t *v4; // [rsp+28h] [rbp-10h]

  try
  {
    v3 = mqwcslen(a1);
    v4 = a1;
    XmlParseDocument((int *)&v3);
  }
  catch ( bad_document )
  {
    LogMsgHR(-1072824174, (wchar_t *)L"rt/property", 0x4C3u);
    return 3222143122LL;
  }
  return 0;
}

```

## disassembly

```asm
0x18000d3e4  push    rbx
0x18000d3e6  sub     rsp, 30h
0x18000d3ea  mov     rbx, rcx
0x18000d3ed  mov     [rsp+38h+arg_8], 0
0x18000d3f6  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18000d3fb  mov     [rsp+38h+var_18], eax
0x18000d3ff  mov     [rsp+38h+var_10], rbx
0x18000d404  lea     rdx, [rsp+38h+arg_8]
0x18000d409  lea     rcx, [rsp+38h+var_18]
0x18000d40e  call    ?XmlParseDocument@@YAPEB_WAEBV?$basic_xstr_t@_W@@PEAPEAVXmlNode@@PEBVINamespaceToId@@@Z; XmlParseDocument(basic_xstr_t<wchar_t> const &,XmlNode * *,INamespaceToId const *)
0x18000d413  nop
0x18000d414  mov     rcx, [rsp+38h+arg_8]; struct XmlNode *
0x18000d419  test    rcx, rcx
0x18000d41c  jz      short loc_18000D42C
0x18000d41e  call    ?XmlFreeTree@@YAXPEAVXmlNode@@@Z; XmlFreeTree(XmlNode *)
0x18000d423  mov     [rsp+38h+arg_8], 0
0x18000d42c  xor     eax, eax
0x18000d42e  jmp     short loc_18000D445
0x18000d430  mov     rcx, [rsp+38h+arg_8]; struct XmlNode *
0x18000d435  test    rcx, rcx
0x18000d438  jz      short loc_18000D440
0x18000d43a  call    ?XmlFreeTree@@YAXPEAVXmlNode@@@Z; XmlFreeTree(XmlNode *)
0x18000d43f  nop
0x18000d440  mov     eax, 0C00E0092h
0x18000d445  add     rsp, 30h
0x18000d449  pop     rbx
0x18000d44a  retn
```
