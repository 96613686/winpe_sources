# CAdvancedSearchNavPane::~CAdvancedSearchNavPane(void)

- ea: `0x180003f20`
- end: `0x180003fa5`
- name: `??1CAdvancedSearchNavPane@@UEAA@XZ`
- size: `133`
- prototype: `void __fastcall(CAdvancedSearchNavPane *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180004310`

## callees

- `0x18000171c`
- `0x180003f20`
- `0x180008c20`
- `0x180028570`

## import_xrefs

- `USER32!DestroyWindow` at `0x180003f5f`
- `USER32!DestroyWindow` at `0x180003f5f`
- `GDI32!DeleteObject` at `0x180003f41`
- `GDI32!DeleteObject` at `0x180003f50`
- `GDI32!DeleteObject` at `0x180003f41`
- `GDI32!DeleteObject` at `0x180003f50`

## pseudocode

```c
void __fastcall CAdvancedSearchNavPane::~CAdvancedSearchNavPane(void **this)
{
  void *v2; // rcx
  void *v3; // rcx
  HWND v4; // rcx
  struct _search_result **v5; // rax

  *this = &CAdvancedSearchNavPane::`vftable';
  CAdvancedSearchNavPane::SaveKeywordCombo((CAdvancedSearchNavPane *)this);
  v2 = this[2];
  if ( v2 )
    DeleteObject(v2);
  v3 = this[4];
  if ( v3 )
    DeleteObject(v3);
  v4 = (HWND)this[1];
  if ( v4 )
    DestroyWindow(v4);
  v5 = (struct _search_result **)this[138];
  if ( v5 )
  {
    if ( *v5 )
      CFullTextSearch::FreeResults(*((CFullTextSearch **)this[137] + 2), *v5);
    operator delete(this[138]);
  }
  *this = &INavUI::`vftable';
}

```

## disassembly

```asm
0x180003f20  push    rbx
0x180003f22  sub     rsp, 20h
0x180003f26  mov     rbx, rcx
0x180003f29  lea     rax, ??_7CAdvancedSearchNavPane@@6B@; const CAdvancedSearchNavPane::`vftable'
0x180003f30  mov     [rcx], rax
0x180003f33  call    ?SaveKeywordCombo@CAdvancedSearchNavPane@@AEAAXXZ; CAdvancedSearchNavPane::SaveKeywordCombo(void)
0x180003f38  mov     rcx, [rbx+10h]; ho
0x180003f3c  test    rcx, rcx
0x180003f3f  jz      short loc_180003F47
0x180003f41  call    cs:__imp_DeleteObject
0x180003f47  mov     rcx, [rbx+20h]; ho
0x180003f4b  test    rcx, rcx
0x180003f4e  jz      short loc_180003F56
0x180003f50  call    cs:__imp_DeleteObject
0x180003f56  mov     rcx, [rbx+8]; hWnd
0x180003f5a  test    rcx, rcx
0x180003f5d  jz      short loc_180003F65
0x180003f5f  call    cs:__imp_DestroyWindow
0x180003f65  mov     rax, [rbx+450h]
0x180003f6c  test    rax, rax
0x180003f6f  jz      short loc_180003F95
0x180003f71  mov     rdx, [rax]; struct _search_result *
0x180003f74  test    rdx, rdx
0x180003f77  jz      short loc_180003F89
0x180003f79  mov     rcx, [rbx+448h]
0x180003f80  mov     rcx, [rcx+10h]; this
0x180003f84  call    ?FreeResults@CFullTextSearch@@QEAAXPEAU_search_result@@@Z; CFullTextSearch::FreeResults(_search_result *)
0x180003f89  mov     rcx, [rbx+450h]; Block
0x180003f90  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003f95  lea     rax, ??_7INavUI@@6B@; const INavUI::`vftable'
0x180003f9c  mov     [rbx], rax
0x180003f9f  add     rsp, 20h
0x180003fa3  pop     rbx
0x180003fa4  retn
```
