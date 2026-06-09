# _unknown<IXMLNodeFactory>::`vector deleting destructor'(uint)

- ea: `0x180010f50`
- end: `0x180010f77`
- name: `??_E?$_unknown@UIXMLNodeFactory@@@@UEAAPEAXI@Z`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0x180010f50`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180010f68`
- `ole32!CoTaskMemFree` at `0x180010f68`

## pseudocode

```c
_QWORD *__fastcall _unknown<IXMLNodeFactory>::`vector deleting destructor'(_QWORD *a1, char a2)
{
  *a1 = &_unknown<IXMLNodeFactory>::`vftable';
  if ( (a2 & 1) != 0 )
    CoTaskMemFree(a1);
  return a1;
}

```

## disassembly

```asm
0x180010f50  push    rbx
0x180010f52  sub     rsp, 20h
0x180010f56  lea     rax, ??_7?$_unknown@UIXMLNodeFactory@@@@6B@; const _unknown<IXMLNodeFactory>::`vftable'
0x180010f5d  mov     rbx, rcx
0x180010f60  mov     [rcx], rax
0x180010f63  test    dl, 1
0x180010f66  jz      short loc_180010F6E
0x180010f68  call    cs:__imp_CoTaskMemFree
0x180010f6e  mov     rax, rbx
0x180010f71  add     rsp, 20h
0x180010f75  pop     rbx
0x180010f76  retn
```
