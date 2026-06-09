# MCReloadMenus

- ea: `0x180046298`
- end: `0x180046341`
- name: `MCReloadMenus`
- size: `169`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180042bec`
- `0x180046d90`

## callees

- `0x180046298`

## import_xrefs

- `USER32!DestroyMenu` at `0x1800462b6`
- `USER32!DestroyMenu` at `0x1800462c8`
- `USER32!DestroyMenu` at `0x1800462b6`
- `USER32!DestroyMenu` at `0x1800462c8`
- `USER32!CreatePopupMenu` at `0x1800462ce`
- `USER32!CreatePopupMenu` at `0x1800462f3`
- `USER32!CreatePopupMenu` at `0x1800462ce`
- `USER32!CreatePopupMenu` at `0x1800462f3`
- `USER32!AppendMenuW` at `0x1800462ed`
- `USER32!AppendMenuW` at `0x180046324`
- `USER32!AppendMenuW` at `0x1800462ed`
- `USER32!AppendMenuW` at `0x180046324`

## pseudocode

```c
HMENU __fastcall MCReloadMenus(__int64 a1)
{
  HMENU v2; // rcx
  HMENU v3; // rcx
  HMENU PopupMenu; // rax
  HMENU result; // rax
  int v6; // ebx

  v2 = *(HMENU *)(a1 + 1752);
  if ( v2 )
    DestroyMenu(v2);
  v3 = *(HMENU *)(a1 + 1760);
  if ( v3 )
    DestroyMenu(v3);
  PopupMenu = CreatePopupMenu();
  *(_QWORD *)(a1 + 1752) = PopupMenu;
  if ( PopupMenu )
    AppendMenuW(PopupMenu, 0, 1u, (LPCWSTR)(a1 + 120));
  result = CreatePopupMenu();
  *(_QWORD *)(a1 + 1760) = result;
  if ( result )
  {
    result = 0;
    do
    {
      v6 = (_DWORD)result + 1;
      AppendMenuW(*(HMENU *)(a1 + 1760), 0, (int)result + 1, (LPCWSTR)(a1 + 304 + 84LL * (_QWORD)result));
      result = (HMENU)(unsigned int)v6;
    }
    while ( v6 < 12 );
  }
  return result;
}

```

## disassembly

```asm
0x180046298  mov     [rsp+arg_0], rbx
0x18004629d  mov     [rsp+arg_8], rsi
0x1800462a2  push    rdi
0x1800462a3  sub     rsp, 20h
0x1800462a7  mov     rdi, rcx
0x1800462aa  mov     rcx, [rcx+6D8h]; hMenu
0x1800462b1  test    rcx, rcx
0x1800462b4  jz      short loc_1800462BC
0x1800462b6  call    cs:__imp_DestroyMenu
0x1800462bc  mov     rcx, [rdi+6E0h]; hMenu
0x1800462c3  test    rcx, rcx
0x1800462c6  jz      short loc_1800462CE
0x1800462c8  call    cs:__imp_DestroyMenu
0x1800462ce  call    cs:__imp_CreatePopupMenu
0x1800462d4  mov     [rdi+6D8h], rax
0x1800462db  test    rax, rax
0x1800462de  jz      short loc_1800462F3
0x1800462e0  xor     edx, edx; uFlags
0x1800462e2  lea     r9, [rdi+78h]; lpNewItem
0x1800462e6  mov     rcx, rax; hMenu
0x1800462e9  lea     r8d, [rdx+1]; uIDNewItem
0x1800462ed  call    cs:__imp_AppendMenuW
0x1800462f3  call    cs:__imp_CreatePopupMenu
0x1800462f9  mov     [rdi+6E0h], rax
0x180046300  test    rax, rax
0x180046303  jz      short loc_180046331
0x180046305  xor     eax, eax
0x180046307  lea     rsi, [rdi+130h]
0x18004630e  mov     rcx, [rdi+6E0h]; hMenu
0x180046315  lea     ebx, [rax+1]
0x180046318  imul    r9, rax, 54h ; 'T'
0x18004631c  movsxd  r8, ebx; uIDNewItem
0x18004631f  xor     edx, edx; uFlags
0x180046321  add     r9, rsi; lpNewItem
0x180046324  call    cs:__imp_AppendMenuW
0x18004632a  mov     eax, ebx
0x18004632c  cmp     ebx, 0Ch
0x18004632f  jl      short loc_18004630E
0x180046331  mov     rbx, [rsp+28h+arg_0]
0x180046336  mov     rsi, [rsp+28h+arg_8]
0x18004633b  add     rsp, 20h
0x18004633f  pop     rdi
0x180046340  retn
```
