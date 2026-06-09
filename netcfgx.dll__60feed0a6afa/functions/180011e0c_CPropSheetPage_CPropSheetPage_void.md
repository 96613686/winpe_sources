# CPropSheetPage::~CPropSheetPage(void)

- ea: `0x180011e0c`
- end: `0x180011e50`
- name: `??1CPropSheetPage@@UEAA@XZ`
- size: `68`
- prototype: `void __fastcall(CPropSheetPage *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180008b0c`
- `0x180008b80`
- `0x180010790`
- `0x18001277f`

## callees

- `0x180011e0c`

## import_xrefs

- `USER32!GetWindowLongPtrW` at `0x180011e2d`
- `USER32!GetWindowLongPtrW` at `0x180011e2d`
- `USER32!SetWindowLongPtrW` at `0x180011e43`
- `USER32!SetWindowLongPtrW` at `0x180011e43`

## pseudocode

```c
void __fastcall CPropSheetPage::~CPropSheetPage(CPropSheetPage *this)
{
  HWND v2; // rcx

  *(_QWORD *)this = &CPropSheetPage::`vftable';
  v2 = (HWND)*((_QWORD *)this + 1);
  if ( v2 )
  {
    if ( GetWindowLongPtrW(v2, 16) )
      SetWindowLongPtrW(*((HWND *)this + 1), 16, 0);
  }
}

```

## disassembly

```asm
0x180011e0c  push    rbx
0x180011e0e  sub     rsp, 20h
0x180011e12  mov     rbx, rcx
0x180011e15  lea     rax, ??_7CPropSheetPage@@6B@; const CPropSheetPage::`vftable'
0x180011e1c  mov     [rcx], rax
0x180011e1f  mov     rcx, [rcx+8]; hWnd
0x180011e23  test    rcx, rcx
0x180011e26  jz      short loc_180011E4A
0x180011e28  mov     edx, 10h; nIndex
0x180011e2d  call    cs:__imp_GetWindowLongPtrW
0x180011e33  test    rax, rax
0x180011e36  jz      short loc_180011E4A
0x180011e38  xor     r8d, r8d; dwNewLong
0x180011e3b  lea     edx, [r8+10h]; nIndex
0x180011e3f  mov     rcx, [rbx+8]; hWnd
0x180011e43  call    cs:__imp_SetWindowLongPtrW
0x180011e49  nop
0x180011e4a  add     rsp, 20h
0x180011e4e  pop     rbx
0x180011e4f  retn
```
