# CCabObj::InitFileGroupDesc(void)

- ea: `0x18000c0bc`
- end: `0x18000c0f1`
- name: `?InitFileGroupDesc@CCabObj@@AEAAHXZ`
- size: `53`
- prototype: `__int64 __fastcall(CCabObj *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b2e0`
- `0x18000ba40`
- `0x18000c390`

## callees

- `0x18000c0bc`

## import_xrefs

- `USER32!RegisterClipboardFormatW` at `0x18000c0d7`
- `USER32!RegisterClipboardFormatW` at `0x18000c0d7`

## string_xrefs

- `0x18000c0d0`: `FileGroupDescriptorW`

## pseudocode

```c
_BOOL8 __fastcall CCabObj::InitFileGroupDesc(CCabObj *this)
{
  if ( CCabObj::s_uFileGroupDesc )
    return 1;
  CCabObj::s_uFileGroupDesc = RegisterClipboardFormatW(L"FileGroupDescriptorW");
  return CCabObj::s_uFileGroupDesc != 0;
}

```

## disassembly

```asm
0x18000c0bc  sub     rsp, 28h
0x18000c0c0  cmp     cs:?s_uFileGroupDesc@CCabObj@@0IA, 0; uint CCabObj::s_uFileGroupDesc
0x18000c0c7  jz      short loc_18000C0D0
0x18000c0c9  mov     eax, 1
0x18000c0ce  jmp     short loc_18000C0EC
0x18000c0d0  lea     rcx, aFilegroupdescr; "FileGroupDescriptorW"
0x18000c0d7  call    cs:__imp_RegisterClipboardFormatW
0x18000c0dd  xor     ecx, ecx
0x18000c0df  mov     cs:?s_uFileGroupDesc@CCabObj@@0IA, eax; uint CCabObj::s_uFileGroupDesc
0x18000c0e5  test    eax, eax
0x18000c0e7  setnz   cl
0x18000c0ea  mov     eax, ecx
0x18000c0ec  add     rsp, 28h
0x18000c0f0  retn
```
