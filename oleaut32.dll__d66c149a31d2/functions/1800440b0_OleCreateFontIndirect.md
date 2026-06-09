# OleCreateFontIndirect

- ea: `0x1800440b0`
- end: `0x1800440f7`
- name: `OleCreateFontIndirect`
- size: `71`
- prototype: `HRESULT __stdcall(LPFONTDESC lpFontDesc, const IID *const riid, LPVOID *lplpvObj)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800440b0`
- `0x18004e87c`

## import_xrefs

- `ext-ms-win-ole32-oleautomation-l1-1-0!OleCreateFontIndirectExt` at `0x1800440e1`
- `ext-ms-win-ole32-oleautomation-l1-1-0!OleCreateFontIndirectExt` at `0x1800440e1`

## pseudocode

```c
HRESULT __stdcall OleCreateFontIndirect(LPFONTDESC lpFontDesc, const IID *const riid, LPVOID *lplpvObj)
{
  if ( (unsigned __int8)IsMonikerLoadTypeLibPresent() )
    return OleCreateFontIndirectExt(lpFontDesc, riid, lplpvObj);
  else
    return -2147467263;
}

```

## disassembly

```asm
0x1800440b0  mov     [rsp+arg_0], rbx
0x1800440b5  mov     [rsp+arg_8], rsi
0x1800440ba  push    rdi
0x1800440bb  sub     rsp, 20h
0x1800440bf  mov     rbx, r8
0x1800440c2  mov     rdi, rdx
0x1800440c5  mov     rsi, rcx
0x1800440c8  call    IsMonikerLoadTypeLibPresent
0x1800440cd  test    al, al
0x1800440cf  jnz     short loc_1800440D8
0x1800440d1  mov     eax, 80004001h
0x1800440d6  jmp     short loc_1800440E7
0x1800440d8  mov     r8, rbx
0x1800440db  mov     rdx, rdi
0x1800440de  mov     rcx, rsi
0x1800440e1  call    cs:__imp_OleCreateFontIndirectExt
0x1800440e7  mov     rbx, [rsp+28h+arg_0]
0x1800440ec  mov     rsi, [rsp+28h+arg_8]
0x1800440f1  add     rsp, 20h
0x1800440f5  pop     rdi
0x1800440f6  retn
```
