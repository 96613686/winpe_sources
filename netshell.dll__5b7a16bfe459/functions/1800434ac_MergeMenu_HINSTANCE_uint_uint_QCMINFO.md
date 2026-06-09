# MergeMenu(HINSTANCE__ *,uint,uint,_QCMINFO *)

- ea: `0x1800434ac`
- end: `0x180043581`
- name: `?MergeMenu@@YAXPEAUHINSTANCE__@@IIPEAU_QCMINFO@@@Z`
- size: `213`
- prototype: `void __fastcall(HINSTANCE hInstance, unsigned int, unsigned int, struct _QCMINFO *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180048060`

## callees

- `0x180034ba0`
- `0x1800433a8`
- `0x1800434ac`

## import_xrefs

- `SHELL32!__imp_Shell_MergeMenus` at `0x18004352b`
- `SHELL32!__imp_Shell_MergeMenus` at `0x18004352b`
- `USER32!LoadMenuW` at `0x1800434c6`
- `USER32!LoadMenuW` at `0x180043544`
- `USER32!LoadMenuW` at `0x1800434c6`
- `USER32!LoadMenuW` at `0x180043544`
- `USER32!GetSubMenu` at `0x1800434e6`
- `USER32!GetSubMenu` at `0x1800434e6`
- `USER32!RemoveMenu` at `0x1800434fa`
- `USER32!RemoveMenu` at `0x1800434fa`
- `USER32!DestroyMenu` at `0x180043503`
- `USER32!DestroyMenu` at `0x180043536`
- `USER32!DestroyMenu` at `0x18004356d`
- `USER32!DestroyMenu` at `0x180043503`
- `USER32!DestroyMenu` at `0x180043536`
- `USER32!DestroyMenu` at `0x18004356d`

## pseudocode

```c
void __fastcall MergeMenu(HINSTANCE hInstance, __int64 a2, __int64 a3, struct _QCMINFO *a4)
{
  UINT idCmdFirst; // edi
  HMENU MenuW; // rax
  HMENU v8; // rbp
  HMENU SubMenu; // rsi
  HMENU v10; // rax
  HMENU v11; // rsi
  UINT v12; // eax

  idCmdFirst = a4->idCmdFirst;
  MenuW = LoadMenuW(hInstance, (LPCWSTR)0x2B68);
  v8 = MenuW;
  if ( MenuW )
  {
    SubMenu = GetSubMenu(MenuW, 0);
    RemoveMenu(v8, 0, 0x400u);
    DestroyMenu(v8);
  }
  else
  {
    SubMenu = 0;
    if ( (int)HrFromLastWin32Error() < 0 )
      goto LABEL_7;
  }
  if ( SubMenu )
  {
    idCmdFirst = Shell_MergeMenus(a4->hmenu, SubMenu, a4->indexMenu, a4->idCmdFirst, a4->idCmdLast, 2u);
    DestroyMenu(SubMenu);
  }
LABEL_7:
  v10 = LoadMenuW(hInstance, (LPCWSTR)0x2B5C);
  v11 = v10;
  if ( v10 )
  {
    v12 = IMergePopupMenus(a4->hmenu, v10, a4->idCmdFirst, a4->idCmdLast);
    if ( idCmdFirst < v12 )
      idCmdFirst = v12;
    DestroyMenu(v11);
  }
  a4->idCmdFirst = idCmdFirst;
}

```

## disassembly

```asm
0x1800434ac  push    rbx
0x1800434ae  push    rbp
0x1800434af  push    rsi
0x1800434b0  push    rdi
0x1800434b1  push    r14
0x1800434b3  sub     rsp, 30h
0x1800434b7  mov     edi, [r9+0Ch]
0x1800434bb  mov     edx, 2B68h; lpMenuName
0x1800434c0  mov     rbx, r9
0x1800434c3  mov     r14, rcx
0x1800434c6  call    cs:__imp_LoadMenuW
0x1800434cc  mov     rbp, rax
0x1800434cf  test    rax, rax
0x1800434d2  jnz     short loc_1800434E1
0x1800434d4  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x1800434d9  xor     esi, esi
0x1800434db  test    eax, eax
0x1800434dd  js      short loc_18004353C
0x1800434df  jmp     short loc_180043509
0x1800434e1  xor     edx, edx; nPos
0x1800434e3  mov     rcx, rbp; hMenu
0x1800434e6  call    cs:__imp_GetSubMenu
0x1800434ec  xor     edx, edx; uPosition
0x1800434ee  mov     r8d, 400h; uFlags
0x1800434f4  mov     rcx, rbp; hMenu
0x1800434f7  mov     rsi, rax
0x1800434fa  call    cs:__imp_RemoveMenu
0x180043500  mov     rcx, rbp; hMenu
0x180043503  call    cs:__imp_DestroyMenu
0x180043509  test    rsi, rsi
0x18004350c  jz      short loc_18004353C
0x18004350e  mov     eax, [rbx+10h]
0x180043511  mov     rdx, rsi; hmSrc
0x180043514  mov     r9d, [rbx+0Ch]; uIDAdjust
0x180043518  mov     r8d, [rbx+8]; uInsert
0x18004351c  mov     rcx, [rbx]; hmDst
0x18004351f  mov     [rsp+58h+uFlags], 2; uFlags
0x180043527  mov     [rsp+58h+uIDAdjustMax], eax; uIDAdjustMax
0x18004352b  call    cs:__imp_Shell_MergeMenus
0x180043531  mov     rcx, rsi; hMenu
0x180043534  mov     edi, eax
0x180043536  call    cs:__imp_DestroyMenu
0x18004353c  mov     edx, 2B5Ch; lpMenuName
0x180043541  mov     rcx, r14; hInstance
0x180043544  call    cs:__imp_LoadMenuW
0x18004354a  mov     rsi, rax
0x18004354d  test    rax, rax
0x180043550  jz      short loc_180043573
0x180043552  mov     r9d, [rbx+10h]; uIDAdjustMax
0x180043556  mov     rdx, rax; HMENU
0x180043559  mov     r8d, [rbx+0Ch]; uIDAdjust
0x18004355d  mov     rcx, [rbx]; hmenu
0x180043560  call    ?IMergePopupMenus@@YAHPEAUHMENU__@@0HH@Z; IMergePopupMenus(HMENU__ *,HMENU__ *,int,int)
0x180043565  cmp     edi, eax
0x180043567  mov     rcx, rsi; hMenu
0x18004356a  cmovb   edi, eax
0x18004356d  call    cs:__imp_DestroyMenu
0x180043573  mov     [rbx+0Ch], edi
0x180043576  add     rsp, 30h
0x18004357a  pop     r14
0x18004357c  pop     rdi
0x18004357d  pop     rsi
0x18004357e  pop     rbp
0x18004357f  pop     rbx
0x180043580  retn
```
