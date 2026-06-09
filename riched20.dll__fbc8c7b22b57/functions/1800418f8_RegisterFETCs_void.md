# RegisterFETCs(void)

- ea: `0x1800418f8`
- end: `0x180041a3a`
- name: `?RegisterFETCs@@YAXXZ`
- size: `322`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18002c7c0`

## import_xrefs

- `USER32!RegisterClipboardFormatA` at `0x180041903`
- `USER32!RegisterClipboardFormatA` at `0x18004191d`
- `USER32!RegisterClipboardFormatA` at `0x180041937`
- `USER32!RegisterClipboardFormatA` at `0x180041951`
- `USER32!RegisterClipboardFormatA` at `0x18004196b`
- `USER32!RegisterClipboardFormatA` at `0x180041985`
- `USER32!RegisterClipboardFormatA` at `0x18004199f`
- `USER32!RegisterClipboardFormatA` at `0x1800419b9`
- `USER32!RegisterClipboardFormatA` at `0x1800419d3`
- `USER32!RegisterClipboardFormatA` at `0x1800419ed`
- `USER32!RegisterClipboardFormatA` at `0x180041a07`
- `USER32!RegisterClipboardFormatA` at `0x180041a21`
- `USER32!RegisterClipboardFormatA` at `0x180041903`
- `USER32!RegisterClipboardFormatA` at `0x18004191d`
- `USER32!RegisterClipboardFormatA` at `0x180041937`
- `USER32!RegisterClipboardFormatA` at `0x180041951`
- `USER32!RegisterClipboardFormatA` at `0x18004196b`
- `USER32!RegisterClipboardFormatA` at `0x180041985`
- `USER32!RegisterClipboardFormatA` at `0x18004199f`
- `USER32!RegisterClipboardFormatA` at `0x1800419b9`
- `USER32!RegisterClipboardFormatA` at `0x1800419d3`
- `USER32!RegisterClipboardFormatA` at `0x1800419ed`
- `USER32!RegisterClipboardFormatA` at `0x180041a07`
- `USER32!RegisterClipboardFormatA` at `0x180041a21`

## string_xrefs

- `0x1800419c5`: `Link Source`
- `0x180041977`: `Object Descriptor`

## pseudocode

```c
void RegisterFETCs(void)
{
  LOWORD(xmmword_1800A61F0) = RegisterClipboardFormatA("Rich Text Format");
  LOWORD(g_rgFETC) = RegisterClipboardFormatA("RTF in UTF8");
  LOWORD(xmmword_1800A6210) = RegisterClipboardFormatA("RTF with NCRs for nonASCII");
  LOWORD(xmmword_1800A6390) = RegisterClipboardFormatA("RTF As Text");
  word_1800A63D0 = RegisterClipboardFormatA("RICHEDIT");
  LOWORD(xmmword_1800A6270) = RegisterClipboardFormatA("Object Descriptor");
  LOWORD(xmmword_1800A6230) = RegisterClipboardFormatA("Embedded Object");
  word_1800A6250 = RegisterClipboardFormatA("Embed Source");
  word_1800A6290 = RegisterClipboardFormatA("Link Source");
  LOWORD(xmmword_1800A6310) = RegisterClipboardFormatA("Rich Text Format Without Objects");
  word_1800A63B0 = RegisterClipboardFormatA("RichEdit Text and Objects");
  word_1800A6370 = RegisterClipboardFormatA("FileName");
}

```

## disassembly

```asm
0x1800418f8  sub     rsp, 28h
0x1800418fc  lea     rcx, szFormat; "Rich Text Format"
0x180041903  call    cs:__imp_RegisterClipboardFormatA
0x18004190a  nop     dword ptr [rax+rax+00h]
0x18004190f  lea     rcx, aRtfInUtf8; "RTF in UTF8"
0x180041916  mov     word ptr cs:xmmword_1800A61F0, ax
0x18004191d  call    cs:__imp_RegisterClipboardFormatA
0x180041924  nop     dword ptr [rax+rax+00h]
0x180041929  lea     rcx, aRtfWithNcrsFor; "RTF with NCRs for nonASCII"
0x180041930  mov     word ptr cs:?g_rgFETC@@3PAUtagFORMATETC@@A, ax; tagFORMATETC near * g_rgFETC
0x180041937  call    cs:__imp_RegisterClipboardFormatA
0x18004193e  nop     dword ptr [rax+rax+00h]
0x180041943  lea     rcx, aRtfAsText; "RTF As Text"
0x18004194a  mov     word ptr cs:xmmword_1800A6210, ax
0x180041951  call    cs:__imp_RegisterClipboardFormatA
0x180041958  nop     dword ptr [rax+rax+00h]
0x18004195d  lea     rcx, aRichedit; "RICHEDIT"
0x180041964  mov     word ptr cs:xmmword_1800A6390, ax
0x18004196b  call    cs:__imp_RegisterClipboardFormatA
0x180041972  nop     dword ptr [rax+rax+00h]
0x180041977  lea     rcx, aObjectDescript; "Object Descriptor"
0x18004197e  mov     cs:word_1800A63D0, ax
0x180041985  call    cs:__imp_RegisterClipboardFormatA
0x18004198c  nop     dword ptr [rax+rax+00h]
0x180041991  lea     rcx, aEmbeddedObject; "Embedded Object"
0x180041998  mov     word ptr cs:xmmword_1800A6270, ax
0x18004199f  call    cs:__imp_RegisterClipboardFormatA
0x1800419a6  nop     dword ptr [rax+rax+00h]
0x1800419ab  lea     rcx, aEmbedSource; "Embed Source"
0x1800419b2  mov     word ptr cs:xmmword_1800A6230, ax
0x1800419b9  call    cs:__imp_RegisterClipboardFormatA
0x1800419c0  nop     dword ptr [rax+rax+00h]
0x1800419c5  lea     rcx, aLinkSource; "Link Source"
0x1800419cc  mov     cs:word_1800A6250, ax
0x1800419d3  call    cs:__imp_RegisterClipboardFormatA
0x1800419da  nop     dword ptr [rax+rax+00h]
0x1800419df  lea     rcx, aRichTextFormat_0; "Rich Text Format Without Objects"
0x1800419e6  mov     cs:word_1800A6290, ax
0x1800419ed  call    cs:__imp_RegisterClipboardFormatA
0x1800419f4  nop     dword ptr [rax+rax+00h]
0x1800419f9  lea     rcx, aRicheditTextAn; "RichEdit Text and Objects"
0x180041a00  mov     word ptr cs:xmmword_1800A6310, ax
0x180041a07  call    cs:__imp_RegisterClipboardFormatA
0x180041a0e  nop     dword ptr [rax+rax+00h]
0x180041a13  lea     rcx, aFilename; "FileName"
0x180041a1a  mov     cs:word_1800A63B0, ax
0x180041a21  call    cs:__imp_RegisterClipboardFormatA
0x180041a28  nop     dword ptr [rax+rax+00h]
0x180041a2d  mov     cs:word_1800A6370, ax
0x180041a34  add     rsp, 28h
0x180041a38  retn
```
