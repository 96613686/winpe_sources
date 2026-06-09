# CCabItemMenu::QueryContextMenu(HMENU__ *,uint,uint,uint,uint)

- ea: `0x180010ba0`
- end: `0x180010c72`
- name: `?QueryContextMenu@CCabItemMenu@@UEAAJPEAUHMENU__@@IIII@Z`
- size: `210`
- prototype: `int(CCabItemMenu *__hidden this, HMENU, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000fbfc`
- `0x180010ba0`

## import_xrefs

- `USER32!DestroyMenu` at `0x180010bf4`
- `USER32!DestroyMenu` at `0x180010c45`
- `USER32!DestroyMenu` at `0x180010bf4`
- `USER32!DestroyMenu` at `0x180010c45`
- `USER32!LoadMenuW` at `0x180010bc0`
- `USER32!LoadMenuW` at `0x180010bc0`
- `USER32!GetSubMenu` at `0x180010bd7`
- `USER32!GetSubMenu` at `0x180010bd7`
- `USER32!RemoveMenu` at `0x180010beb`
- `USER32!RemoveMenu` at `0x180010c16`
- `USER32!RemoveMenu` at `0x180010beb`
- `USER32!RemoveMenu` at `0x180010c16`
- `USER32!SetMenuDefaultItem` at `0x180010c54`
- `USER32!SetMenuDefaultItem` at `0x180010c54`

## pseudocode

```c
__int64 __fastcall CCabItemMenu::QueryContextMenu(
        CCabItemMenu *this,
        HMENU a2,
        UINT a3,
        unsigned int a4,
        UINT a5,
        unsigned int a6)
{
  HMENU MenuW; // rax
  HMENU v10; // rbx
  HMENU SubMenu; // rdi
  __int16 v12; // bx

  MenuW = LoadMenuW(g_hinst, (LPCWSTR)0x65);
  v10 = MenuW;
  if ( !MenuW )
    return 2147942414LL;
  SubMenu = GetSubMenu(MenuW, 0);
  RemoveMenu(v10, 0, 0x400u);
  DestroyMenu(v10);
  if ( !SubMenu )
    return 2147942414LL;
  if ( (a6 & 0x10000) != 0 )
    RemoveMenu(SubMenu, 8u, 0);
  v12 = Cab_MergeMenus(a2, SubMenu, a3, a4, a5, 1);
  DestroyMenu(SubMenu);
  SetMenuDefaultItem(a2, a4 + 1, 0);
  return (unsigned __int16)(v12 - a4);
}

```

## disassembly

```asm
0x180010ba0  push    rbx
0x180010ba2  push    rbp
0x180010ba3  push    rsi
0x180010ba4  push    rdi
0x180010ba5  push    r14
0x180010ba7  sub     rsp, 30h
0x180010bab  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hInstance
0x180010bb2  mov     rbp, rdx
0x180010bb5  mov     edx, 65h ; 'e'; lpMenuName
0x180010bba  mov     esi, r9d
0x180010bbd  mov     r14d, r8d
0x180010bc0  call    cs:__imp_LoadMenuW
0x180010bc6  mov     rbx, rax
0x180010bc9  test    rax, rax
0x180010bcc  jz      loc_180010C62
0x180010bd2  xor     edx, edx; nPos
0x180010bd4  mov     rcx, rax; hMenu
0x180010bd7  call    cs:__imp_GetSubMenu
0x180010bdd  xor     edx, edx; uPosition
0x180010bdf  mov     r8d, 400h; uFlags
0x180010be5  mov     rcx, rbx; hMenu
0x180010be8  mov     rdi, rax
0x180010beb  call    cs:__imp_RemoveMenu
0x180010bf1  mov     rcx, rbx; hMenu
0x180010bf4  call    cs:__imp_DestroyMenu
0x180010bfa  test    rdi, rdi
0x180010bfd  jz      short loc_180010C62
0x180010bff  test    [rsp+58h+arg_28], 10000h
0x180010c0a  jz      short loc_180010C1C
0x180010c0c  xor     r8d, r8d; uFlags
0x180010c0f  mov     rcx, rdi; hMenu
0x180010c12  lea     edx, [r8+8]; uPosition
0x180010c16  call    cs:__imp_RemoveMenu
0x180010c1c  mov     eax, [rsp+58h+arg_20]
0x180010c23  mov     r9d, esi; unsigned int
0x180010c26  mov     [rsp+58h+var_30], 1; unsigned int
0x180010c2e  mov     r8d, r14d; unsigned int
0x180010c31  mov     rdx, rdi; HMENU
0x180010c34  mov     [rsp+58h+var_38], eax; unsigned int
0x180010c38  mov     rcx, rbp; HMENU
0x180010c3b  call    ?Cab_MergeMenus@@YAIPEAUHMENU__@@0IIIK@Z; Cab_MergeMenus(HMENU__ *,HMENU__ *,uint,uint,uint,ulong)
0x180010c40  mov     rcx, rdi; hMenu
0x180010c43  mov     ebx, eax
0x180010c45  call    cs:__imp_DestroyMenu
0x180010c4b  lea     edx, [rsi+1]; uItem
0x180010c4e  xor     r8d, r8d; fByPos
0x180010c51  mov     rcx, rbp; hMenu
0x180010c54  call    cs:__imp_SetMenuDefaultItem
0x180010c5a  sub     bx, si
0x180010c5d  movzx   eax, bx
0x180010c60  jmp     short loc_180010C67
0x180010c62  mov     eax, 8007000Eh
0x180010c67  add     rsp, 30h
0x180010c6b  pop     r14
0x180010c6d  pop     rdi
0x180010c6e  pop     rsi
0x180010c6f  pop     rbp
0x180010c70  pop     rbx
0x180010c71  retn
```
