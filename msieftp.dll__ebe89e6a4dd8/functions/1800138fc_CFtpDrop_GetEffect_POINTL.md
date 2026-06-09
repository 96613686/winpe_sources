# CFtpDrop::GetEffect(_POINTL)

- ea: `0x1800138fc`
- end: `0x1800139ea`
- name: `?GetEffect@CFtpDrop@@IEAAKU_POINTL@@@Z`
- size: `238`
- prototype: `unsigned int(CFtpDrop *__hidden this, struct _POINTL)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180013070`

## callees

- `0x1800138fc`

## import_xrefs

- `USER32!DeleteMenu` at `0x180013971`
- `USER32!DeleteMenu` at `0x18001398a`
- `USER32!DeleteMenu` at `0x180013971`
- `USER32!DeleteMenu` at `0x18001398a`
- `USER32!SetMenuDefaultItem` at `0x180013958`
- `USER32!SetMenuDefaultItem` at `0x180013958`
- `USER32!LoadMenuW` at `0x18001392f`
- `USER32!LoadMenuW` at `0x18001392f`
- `USER32!GetSubMenu` at `0x180013946`
- `USER32!GetSubMenu` at `0x180013946`
- `USER32!SetForegroundWindow` at `0x180013999`
- `USER32!SetForegroundWindow` at `0x180013999`
- `USER32!TrackPopupMenuEx` at `0x1800139c1`
- `USER32!TrackPopupMenuEx` at `0x1800139c1`
- `USER32!DestroyMenu` at `0x1800139cc`
- `USER32!DestroyMenu` at `0x1800139cc`

## pseudocode

```c
__int64 __fastcall CFtpDrop::GetEffect(CFtpDrop *this, struct _POINTL a2)
{
  LONG x; // ebx
  HMENU MenuW; // rax
  HMENU v5; // rbp
  HMENU SubMenu; // rsi
  HWND v7; // rcx
  BOOL v8; // ebx
  LONG y; // [rsp+6Ch] [rbp+14h]

  y = a2.y;
  x = a2.x;
  if ( *((_DWORD *)this + 12) )
  {
    if ( (*((_BYTE *)this + 40) & 2) != 0 )
    {
      MenuW = LoadMenuW(g_hinst, (LPCWSTR)3);
      v5 = MenuW;
      if ( MenuW )
      {
        SubMenu = GetSubMenu(MenuW, 0);
        SetMenuDefaultItem(SubMenu, *((_DWORD *)this + 12), 0);
        if ( (**((_BYTE **)this + 7) & 1) == 0 )
          DeleteMenu(SubMenu, 1u, 0);
        if ( (**((_BYTE **)this + 7) & 2) == 0 )
          DeleteMenu(SubMenu, 2u, 0);
        v7 = (HWND)*((_QWORD *)this + 4);
        if ( v7 )
          SetForegroundWindow(v7);
        v8 = TrackPopupMenuEx(SubMenu, 0x142u, x, y, *((HWND *)this + 4), 0);
        DestroyMenu(v5);
        *((_DWORD *)this + 12) = v8;
      }
    }
  }
  **((_DWORD **)this + 7) = *((_DWORD *)this + 12);
  return *((unsigned int *)this + 12);
}

```

## disassembly

```asm
0x1800138fc  mov     qword ptr [rsp+y], rdx
0x180013901  push    rbx
0x180013902  push    rbp
0x180013903  push    rsi
0x180013904  push    rdi
0x180013905  sub     rsp, 38h
0x180013909  cmp     dword ptr [rcx+30h], 0
0x18001390d  mov     rbx, rdx
0x180013910  mov     rdi, rcx
0x180013913  jz      loc_1800139D5
0x180013919  test    byte ptr [rcx+28h], 2
0x18001391d  jz      loc_1800139D5
0x180013923  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hInstance
0x18001392a  mov     edx, 3; lpMenuName
0x18001392f  call    cs:__imp_LoadMenuW
0x180013935  mov     rbp, rax
0x180013938  test    rax, rax
0x18001393b  jz      loc_1800139D5
0x180013941  xor     edx, edx; nPos
0x180013943  mov     rcx, rax; hMenu
0x180013946  call    cs:__imp_GetSubMenu
0x18001394c  mov     edx, [rdi+30h]; uItem
0x18001394f  xor     r8d, r8d; fByPos
0x180013952  mov     rcx, rax; hMenu
0x180013955  mov     rsi, rax
0x180013958  call    cs:__imp_SetMenuDefaultItem
0x18001395e  mov     rcx, [rdi+38h]
0x180013962  mov     edx, 1; uPosition
0x180013967  test    [rcx], dl
0x180013969  jnz     short loc_180013977
0x18001396b  xor     r8d, r8d; uFlags
0x18001396e  mov     rcx, rsi; hMenu
0x180013971  call    cs:__imp_DeleteMenu
0x180013977  mov     rax, [rdi+38h]
0x18001397b  test    byte ptr [rax], 2
0x18001397e  jnz     short loc_180013990
0x180013980  xor     r8d, r8d; uFlags
0x180013983  mov     rcx, rsi; hMenu
0x180013986  lea     edx, [r8+2]; uPosition
0x18001398a  call    cs:__imp_DeleteMenu
0x180013990  mov     rcx, [rdi+20h]; hWnd
0x180013994  test    rcx, rcx
0x180013997  jz      short loc_18001399F
0x180013999  call    cs:__imp_SetForegroundWindow
0x18001399f  mov     rax, [rdi+20h]
0x1800139a3  mov     r8d, ebx; x
0x1800139a6  mov     r9d, [rsp+6Ch]; y
0x1800139ab  mov     edx, 142h; uFlags
0x1800139b0  mov     [rsp+58h+lptpm], 0; lptpm
0x1800139b9  mov     rcx, rsi; hMenu
0x1800139bc  mov     [rsp+58h+hwnd], rax; hwnd
0x1800139c1  call    cs:__imp_TrackPopupMenuEx
0x1800139c7  mov     rcx, rbp; hMenu
0x1800139ca  mov     ebx, eax
0x1800139cc  call    cs:__imp_DestroyMenu
0x1800139d2  mov     [rdi+30h], ebx
0x1800139d5  mov     eax, [rdi+30h]
0x1800139d8  mov     rcx, [rdi+38h]
0x1800139dc  mov     [rcx], eax
0x1800139de  mov     eax, [rdi+30h]
0x1800139e1  add     rsp, 38h
0x1800139e5  pop     rdi
0x1800139e6  pop     rsi
0x1800139e7  pop     rbp
0x1800139e8  pop     rbx
0x1800139e9  retn
```
