# CBasePropertyPage::Move(tagRECT const *)

- ea: `0x18001cfa0`
- end: `0x18001cfec`
- name: `?Move@CBasePropertyPage@@UEAAJPEBUtagRECT@@@Z`
- size: `76`
- prototype: `__int64 __fastcall(CBasePropertyPage *__hidden this, const struct tagRECT *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18001cfa0`

## import_xrefs

- `USER32!MoveWindow` at `0x18001cfdf`
- `USER32!MoveWindow` at `0x18001cfdf`

## pseudocode

```c
__int64 __fastcall CBasePropertyPage::Move(CBasePropertyPage *this, const struct tagRECT *a2)
{
  HWND v3; // rcx

  if ( !a2 )
    return 2147500035LL;
  v3 = (HWND)*((_QWORD *)this + 5);
  if ( !v3 )
    return 2147549183LL;
  MoveWindow(v3, a2->left, a2->top, a2->right - a2->left, a2->bottom - a2->top, 1);
  return 0;
}

```

## disassembly

```asm
0x18001cfa0  sub     rsp, 38h
0x18001cfa4  test    rdx, rdx
0x18001cfa7  jnz     short loc_18001CFB0
0x18001cfa9  mov     eax, 80004003h
0x18001cfae  jmp     short loc_18001CFE7
0x18001cfb0  mov     rcx, [rcx+28h]; hWnd
0x18001cfb4  test    rcx, rcx
0x18001cfb7  jnz     short loc_18001CFC0
0x18001cfb9  mov     eax, 8000FFFFh
0x18001cfbe  jmp     short loc_18001CFE7
0x18001cfc0  mov     eax, [rdx+0Ch]
0x18001cfc3  mov     r9d, [rdx+8]
0x18001cfc7  mov     r8d, [rdx+4]; Y
0x18001cfcb  sub     eax, r8d
0x18001cfce  sub     r9d, [rdx]; nWidth
0x18001cfd1  mov     edx, [rdx]; X
0x18001cfd3  mov     [rsp+38h+bRepaint], 1; bRepaint
0x18001cfdb  mov     [rsp+38h+nHeight], eax; nHeight
0x18001cfdf  call    cs:__imp_MoveWindow
0x18001cfe5  xor     eax, eax
0x18001cfe7  add     rsp, 38h
0x18001cfeb  retn
```
