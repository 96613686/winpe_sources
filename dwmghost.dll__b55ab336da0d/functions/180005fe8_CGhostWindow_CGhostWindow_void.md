# CGhostWindow::~CGhostWindow(void)

- ea: `0x180005fe8`
- end: `0x180006061`
- name: `??1CGhostWindow@@UEAA@XZ`
- size: `121`
- prototype: `void __fastcall(CGhostWindow *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180005854`
- `0x180006070`
- `0x180009fac`

## callees

- `0x1800033c0`
- `0x180004dc4`
- `0x180005fe8`
- `0x1800075a0`

## import_xrefs

- `GDI32!DeleteObject` at `0x180006012`
- `GDI32!DeleteObject` at `0x180006012`
- `ext-ms-win-ntuser-gui-l1-1-0!DestroyIcon` at `0x180006024`
- `ext-ms-win-ntuser-gui-l1-1-0!DestroyIcon` at `0x180006036`
- `ext-ms-win-ntuser-gui-l1-1-0!DestroyIcon` at `0x180006024`
- `ext-ms-win-ntuser-gui-l1-1-0!DestroyIcon` at `0x180006036`
- `ext-ms-win-ntuser-window-l1-1-0!DestroyWindow` at `0x180006045`
- `ext-ms-win-ntuser-window-l1-1-0!DestroyWindow` at `0x180006045`

## pseudocode

```c
void __fastcall CGhostWindow::~CGhostWindow(CGhostWindow *this)
{
  bool v1; // zf
  void *v3; // rcx
  HICON v4; // rcx
  HICON v5; // rcx
  HWND v6; // rcx

  v1 = *((_DWORD *)this + 8) == 0;
  *(_QWORD *)this = &CGhostWindow::`vftable';
  if ( !v1 )
    CGhostWindow::RemoveGhostFromProcess(this);
  v3 = (void *)*((_QWORD *)this + 17);
  if ( v3 )
    DeleteObject(v3);
  v4 = (HICON)*((_QWORD *)this + 23);
  if ( v4 )
    DestroyIcon(v4);
  v5 = (HICON)*((_QWORD *)this + 24);
  if ( v5 )
    DestroyIcon(v5);
  v6 = (HWND)*((_QWORD *)this + 8);
  if ( v6 )
    DestroyWindow(v6);
  CCountedObject::Release(*((CCountedObject **)this + 2));
  CCountedObject::~CCountedObject(this);
}

```

## disassembly

```asm
0x180005fe8  push    rbx
0x180005fea  sub     rsp, 20h
0x180005fee  cmp     dword ptr [rcx+20h], 0
0x180005ff2  lea     rax, ??_7CGhostWindow@@6B@; const CGhostWindow::`vftable'
0x180005ff9  mov     [rcx], rax
0x180005ffc  mov     rbx, rcx
0x180005fff  jz      short loc_180006006
0x180006001  call    ?RemoveGhostFromProcess@CGhostWindow@@AEAAHXZ; CGhostWindow::RemoveGhostFromProcess(void)
0x180006006  mov     rcx, [rbx+88h]; ho
0x18000600d  test    rcx, rcx
0x180006010  jz      short loc_180006018
0x180006012  call    cs:__imp_DeleteObject
0x180006018  mov     rcx, [rbx+0B8h]; hIcon
0x18000601f  test    rcx, rcx
0x180006022  jz      short loc_18000602A
0x180006024  call    cs:__imp_DestroyIcon
0x18000602a  mov     rcx, [rbx+0C0h]; hIcon
0x180006031  test    rcx, rcx
0x180006034  jz      short loc_18000603C
0x180006036  call    cs:__imp_DestroyIcon
0x18000603c  mov     rcx, [rbx+40h]; hWnd
0x180006040  test    rcx, rcx
0x180006043  jz      short loc_18000604B
0x180006045  call    cs:__imp_DestroyWindow
0x18000604b  mov     rcx, [rbx+10h]; this
0x18000604f  call    ?Release@CCountedObject@@QEAAXXZ; CCountedObject::Release(void)
0x180006054  mov     rcx, rbx; this
0x180006057  add     rsp, 20h
0x18000605b  pop     rbx
0x18000605c  jmp     ??1CCountedObject@@MEAA@XZ; CCountedObject::~CCountedObject(void)
```
