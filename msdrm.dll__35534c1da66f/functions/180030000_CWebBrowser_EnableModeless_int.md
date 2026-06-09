# CWebBrowser::EnableModeless(int)

- ea: `0x180030000`
- end: `0x180030019`
- name: `?EnableModeless@CWebBrowser@@UEAAJH@Z`
- size: `25`
- prototype: `__int64 __fastcall(CWebBrowser *__hidden this, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180030020`

## callees

- `0x180030000`

## import_xrefs

- `USER32!UpdateWindow` at `0x18003000c`
- `USER32!UpdateWindow` at `0x18003000c`

## pseudocode

```c
__int64 __fastcall CWebBrowser::EnableModeless(HWND *this, int a2)
{
  if ( a2 )
    UpdateWindow(this[5]);
  return 0;
}

```

## disassembly

```asm
0x180030000  sub     rsp, 28h
0x180030004  test    edx, edx
0x180030006  jz      short loc_180030012
0x180030008  mov     rcx, [rcx+28h]; hWnd
0x18003000c  call    cs:__imp_UpdateWindow
0x180030012  xor     eax, eax
0x180030014  add     rsp, 28h
0x180030018  retn
```
