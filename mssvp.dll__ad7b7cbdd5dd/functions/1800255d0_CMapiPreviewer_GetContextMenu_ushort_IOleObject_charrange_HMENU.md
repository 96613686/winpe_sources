# CMapiPreviewer::GetContextMenu(ushort,IOleObject *,_charrange *,HMENU__ * *)

- ea: `0x1800255d0`
- end: `0x180025698`
- name: `?GetContextMenu@CMapiPreviewer@@UEAAJGPEAUIOleObject@@PEAU_charrange@@PEAPEAUHMENU__@@@Z`
- size: `200`
- prototype: `__int64 __fastcall(CMapiPreviewer *__hidden this, unsigned __int16, struct IOleObject *, struct _charrange *, HMENU *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800255d0`

## import_xrefs

- `USER32!LoadMenuW` at `0x180025610`
- `USER32!LoadMenuW` at `0x18002562a`
- `USER32!LoadMenuW` at `0x180025610`
- `USER32!LoadMenuW` at `0x18002562a`
- `USER32!EnableMenuItem` at `0x18002567a`
- `USER32!EnableMenuItem` at `0x18002567a`
- `USER32!DestroyMenu` at `0x180025661`
- `USER32!DestroyMenu` at `0x180025661`
- `USER32!RemoveMenu` at `0x180025658`
- `USER32!RemoveMenu` at `0x180025658`
- `USER32!GetSubMenu` at `0x180025644`
- `USER32!GetSubMenu` at `0x180025644`

## pseudocode

```c
__int64 __fastcall CMapiPreviewer::GetContextMenu(
        CMapiPreviewer *this,
        __int16 a2,
        struct IOleObject *a3,
        struct _charrange *a4,
        HMENU *a5)
{
  unsigned int v7; // edi
  HMENU MenuW; // rax
  HMENU v9; // rsi
  HMENU SubMenu; // rbx

  v7 = 1;
  if ( a2 >= 0 )
  {
    if ( *((_DWORD *)this + 299) || !*((_DWORD *)this + 298) )
    {
      MenuW = LoadMenuW(hInstance, (LPCWSTR)0x3EB);
      *((_DWORD *)this + 300) = 0;
    }
    else
    {
      MenuW = LoadMenuW(hInstance, (LPCWSTR)0x3EE);
      *((_DWORD *)this + 300) = 1;
    }
    v9 = MenuW;
    if ( MenuW )
    {
      SubMenu = GetSubMenu(MenuW, 0);
      RemoveMenu(v9, 0, 0x400u);
      DestroyMenu(v9);
      if ( a4->cpMin == a4->cpMax )
        EnableMenuItem(SubMenu, 1u, 3u);
      v7 = 0;
      *a5 = SubMenu;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x1800255d0  push    rbx
0x1800255d2  push    rbp
0x1800255d3  push    rsi
0x1800255d4  push    rdi
0x1800255d5  push    r14
0x1800255d7  sub     rsp, 20h
0x1800255db  xor     r14d, r14d
0x1800255de  mov     rbp, r9
0x1800255e1  mov     rbx, rcx
0x1800255e4  mov     edi, 1
0x1800255e9  test    dx, dx
0x1800255ec  js      loc_18002568B
0x1800255f2  cmp     [rcx+4ACh], r14d
0x1800255f9  jnz     short loc_18002561E
0x1800255fb  cmp     [rcx+4A8h], r14d
0x180025602  jz      short loc_18002561E
0x180025604  mov     rcx, cs:hInstance; hInstance
0x18002560b  mov     edx, 3EEh; lpMenuName
0x180025610  call    cs:__imp_LoadMenuW
0x180025616  mov     [rbx+4B0h], edi
0x18002561c  jmp     short loc_180025637
0x18002561e  mov     rcx, cs:hInstance; hInstance
0x180025625  mov     edx, 3EBh; lpMenuName
0x18002562a  call    cs:__imp_LoadMenuW
0x180025630  mov     [rbx+4B0h], r14d
0x180025637  mov     rsi, rax
0x18002563a  test    rax, rax
0x18002563d  jz      short loc_18002568B
0x18002563f  xor     edx, edx; nPos
0x180025641  mov     rcx, rax; hMenu
0x180025644  call    cs:__imp_GetSubMenu
0x18002564a  xor     edx, edx; uPosition
0x18002564c  mov     r8d, 400h; uFlags
0x180025652  mov     rcx, rsi; hMenu
0x180025655  mov     rbx, rax
0x180025658  call    cs:__imp_RemoveMenu
0x18002565e  mov     rcx, rsi; hMenu
0x180025661  call    cs:__imp_DestroyMenu
0x180025667  mov     eax, [rbp+4]
0x18002566a  cmp     [rbp+0], eax
0x18002566d  jnz     short loc_180025680
0x18002566f  mov     r8d, 3; uEnable
0x180025675  mov     edx, edi; uIDEnableItem
0x180025677  mov     rcx, rbx; hMenu
0x18002567a  call    cs:__imp_EnableMenuItem
0x180025680  mov     rcx, [rsp+48h+arg_20]
0x180025685  mov     edi, r14d
0x180025688  mov     [rcx], rbx
0x18002568b  mov     eax, edi
0x18002568d  add     rsp, 20h
0x180025691  pop     r14
0x180025693  pop     rdi
0x180025694  pop     rsi
0x180025695  pop     rbp
0x180025696  pop     rbx
0x180025697  retn
```
