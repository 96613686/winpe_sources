# _dynamic_initializer_for__CDataObject::s_cfSnapinClsid__

- ea: `0x180001300`
- end: `0x18000131c`
- name: `_dynamic_initializer_for__CDataObject::s_cfSnapinClsid__`
- size: `28`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## import_xrefs

- `USER32!RegisterClipboardFormatW` at `0x18000130b`
- `USER32!RegisterClipboardFormatW` at `0x18000130b`

## string_xrefs

- `0x180001304`: `CCF_SNAPIN_CLASSID`

## pseudocode

```c
UINT dynamic_initializer_for__CDataObject::s_cfSnapinClsid__()
{
  UINT result; // eax

  result = RegisterClipboardFormatW(L"CCF_SNAPIN_CLASSID");
  CDataObject::s_cfSnapinClsid = result;
  return result;
}

```

## disassembly

```asm
0x180001300  sub     rsp, 28h
0x180001304  lea     rcx, aCcfSnapinClass; "CCF_SNAPIN_CLASSID"
0x18000130b  call    cs:__imp_RegisterClipboardFormatW
0x180001311  mov     cs:?s_cfSnapinClsid@CDataObject@@2IB, eax; uint const CDataObject::s_cfSnapinClsid
0x180001317  add     rsp, 28h
0x18000131b  retn
```
