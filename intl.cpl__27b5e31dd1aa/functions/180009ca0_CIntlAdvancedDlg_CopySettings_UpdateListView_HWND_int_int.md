# CIntlAdvancedDlg::_CopySettings_UpdateListView(HWND__ *,int,int)

- ea: `0x180009ca0`
- end: `0x180009ce7`
- name: `?_CopySettings_UpdateListView@CIntlAdvancedDlg@@AEAAXPEAUHWND__@@HH@Z`
- size: `71`
- prototype: `void(CIntlAdvancedDlg *__hidden this, HWND, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x180009870`
- `0x180009a14`

## callees

- `0x1800087f8`
- `0x180009ca0`

## import_xrefs

- `USER32!LockWindowUpdate` at `0x180009cbc`
- `USER32!LockWindowUpdate` at `0x180009cd8`
- `USER32!LockWindowUpdate` at `0x180009cbc`
- `USER32!LockWindowUpdate` at `0x180009cd8`

## pseudocode

```c
void __fastcall CIntlAdvancedDlg::_CopySettings_UpdateListView(CAccountListView **this, HWND a2, int a3, int a4)
{
  BOOL v7; // ebx

  if ( this[2] )
  {
    v7 = LockWindowUpdate(a2);
    CAccountListView::Refresh(this[2], a3, a4);
    if ( v7 )
      LockWindowUpdate(0);
  }
}

```

## disassembly

```asm
0x180009ca0  push    rbx
0x180009ca2  push    rbp
0x180009ca3  push    rsi
0x180009ca4  push    rdi
0x180009ca5  sub     rsp, 28h
0x180009ca9  cmp     qword ptr [rcx+10h], 0
0x180009cae  mov     esi, r9d
0x180009cb1  mov     ebp, r8d
0x180009cb4  mov     rdi, rcx
0x180009cb7  jz      short loc_180009CDE
0x180009cb9  mov     rcx, rdx; hWndLock
0x180009cbc  call    cs:__imp_LockWindowUpdate
0x180009cc2  mov     rcx, [rdi+10h]; this
0x180009cc6  mov     r8d, esi; int
0x180009cc9  mov     edx, ebp; int
0x180009ccb  mov     ebx, eax
0x180009ccd  call    ?Refresh@CAccountListView@@QEAAXHH@Z; CAccountListView::Refresh(int,int)
0x180009cd2  test    ebx, ebx
0x180009cd4  jz      short loc_180009CDE
0x180009cd6  xor     ecx, ecx; hWndLock
0x180009cd8  call    cs:__imp_LockWindowUpdate
0x180009cde  add     rsp, 28h
0x180009ce2  pop     rdi
0x180009ce3  pop     rsi
0x180009ce4  pop     rbp
0x180009ce5  pop     rbx
0x180009ce6  retn
```
