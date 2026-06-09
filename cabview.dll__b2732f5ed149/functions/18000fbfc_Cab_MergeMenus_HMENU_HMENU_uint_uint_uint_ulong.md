# Cab_MergeMenus(HMENU__ *,HMENU__ *,uint,uint,uint,ulong)

- ea: `0x18000fbfc`
- end: `0x18000fef4`
- name: `?Cab_MergeMenus@@YAIPEAUHMENU__@@0IIIK@Z`
- size: `760`
- prototype: `unsigned int __fastcall(HMENU, HMENU, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000fbfc`
- `0x180010ba0`

## callees

- `0x180002620`
- `0x180002f40`
- `0x18000fbfc`

## import_xrefs

- `USER32!GetMenuItemCount` at `0x18000fc6a`
- `USER32!GetMenuItemCount` at `0x18000fcf5`
- `USER32!GetMenuItemCount` at `0x18000fc6a`
- `USER32!GetMenuItemCount` at `0x18000fcf5`
- `USER32!GetMenuItemInfoW` at `0x18000fca9`
- `USER32!GetMenuItemInfoW` at `0x18000fd49`
- `USER32!GetMenuItemInfoW` at `0x18000fe7c`
- `USER32!GetMenuItemInfoW` at `0x18000fca9`
- `USER32!GetMenuItemInfoW` at `0x18000fd49`
- `USER32!GetMenuItemInfoW` at `0x18000fe7c`
- `USER32!DeleteMenu` at `0x18000fe9e`
- `USER32!DeleteMenu` at `0x18000fe9e`
- `USER32!InsertMenuW` at `0x18000fcea`
- `USER32!InsertMenuW` at `0x18000fec8`
- `USER32!InsertMenuW` at `0x18000fcea`
- `USER32!InsertMenuW` at `0x18000fec8`
- `USER32!CreatePopupMenu` at `0x18000fdb4`
- `USER32!CreatePopupMenu` at `0x18000fdb4`
- `USER32!InsertMenuItemW` at `0x18000fe2f`
- `USER32!InsertMenuItemW` at `0x18000fe2f`

## pseudocode

```c
__int64 __fastcall Cab_MergeMenus(HMENU a1, HMENU a2, UINT a3, unsigned int a4, UINT a5, char a6)
{
  UINT v10; // r15d
  unsigned int MenuItemCount; // eax
  int v12; // ebx
  UINT v13; // r12d
  unsigned int v14; // r13d
  UINT v15; // ecx
  UINT v16; // eax
  HMENU PopupMenu; // rax
  unsigned int v18; // eax
  UINT v19; // ecx
  UINT v20; // eax
  UINT v21; // edx
  HMENU hMenu; // [rsp+40h] [rbp-C0h]
  MENUITEMINFOW mi; // [rsp+50h] [rbp-B0h] BYREF
  tagMENUITEMINFOW mii; // [rsp+A0h] [rbp-60h] BYREF
  char v28; // [rsp+F0h] [rbp-10h] BYREF

  memset_0(&mi, 0, sizeof(mi));
  v10 = a4;
  if ( !a1 || !a2 )
    return v10;
  MenuItemCount = GetMenuItemCount(a1);
  if ( a3 < MenuItemCount )
  {
    mii.cbSize = 80;
    memset_0(&mii.fMask, 0, 0x4Cu);
    mii.fMask = 18;
    if ( !GetMenuItemInfoW(a1, a3, 1, &mii) || (mii.fType & 0x800) == 0 )
    {
      v12 = 0;
      goto LABEL_9;
    }
  }
  else
  {
    a3 = MenuItemCount;
  }
  v12 = 1;
LABEL_9:
  if ( (a6 & 1) != 0 && !v12 )
  {
    InsertMenuW(a1, a3, 0xC00u, 0, 0);
    v12 = 1;
  }
  v13 = GetMenuItemCount(a2);
LABEL_13:
  v14 = a5;
  while ( (--v13 & 0x80000000) == 0 )
  {
    mi.dwTypeData = (LPWSTR)&v28;
    mi.cbSize = 80;
    *(_QWORD *)&mi.fMask = 63;
    mi.dwItemData = 0;
    mi.cch = 256;
    if ( GetMenuItemInfoW(a2, v13, 1, &mi) )
    {
      if ( (mi.fType & 0x800) != 0 )
      {
        if ( !v12 )
        {
          v12 = 1;
          goto LABEL_33;
        }
      }
      else
      {
        hMenu = mi.hSubMenu;
        if ( mi.hSubMenu )
        {
          if ( (a6 & 2) != 0 )
          {
            v15 = a4 + mi.wID;
            mi.wID = v15;
            if ( v15 > a5 )
              goto LABEL_13;
            v16 = v15 + 1;
            if ( v10 > v15 )
              v16 = v10;
            v10 = v16;
          }
          else
          {
            mi.fMask &= ~2u;
          }
          PopupMenu = CreatePopupMenu();
          mi.hSubMenu = PopupMenu;
          if ( !PopupMenu )
            return v10;
          v18 = Cab_MergeMenus(PopupMenu, hMenu, 0, a4, a5, a6 & 2);
          v14 = a5;
          if ( v10 <= v18 )
            v10 = v18;
          v12 = 0;
LABEL_33:
          if ( !InsertMenuItemW(a1, a3, 1, &mi) )
            return v10;
        }
        else
        {
          v19 = v10;
          v20 = a4 + mi.wID;
          mi.wID = v20;
          if ( v20 <= v14 )
          {
            v12 = 0;
            v10 = v20 + 1;
            if ( v19 > v20 )
              v10 = v19;
            goto LABEL_33;
          }
        }
      }
    }
  }
  if ( a3 )
  {
    mii.cbSize = 80;
    memset_0(&mii.fMask, 0, 0x4Cu);
    mii.fMask = 18;
    if ( GetMenuItemInfoW(a1, a3 - 1, 1, &mii) && (mii.fType & 0x800) != 0 )
    {
      if ( v12 )
      {
        v21 = a3;
LABEL_42:
        DeleteMenu(a1, v21, 0x400u);
      }
    }
    else if ( (a6 & 1) != 0 && !v12 )
    {
      InsertMenuW(a1, a3, 0xC00u, 0, 0);
    }
  }
  else if ( v12 )
  {
    v21 = 0;
    goto LABEL_42;
  }
  return v10;
}

```

## disassembly

```asm
0x18000fbfc  push    rbp
0x18000fbfe  push    rbx
0x18000fbff  push    rsi
0x18000fc00  push    rdi
0x18000fc01  push    r12
0x18000fc03  push    r13
0x18000fc05  push    r14
0x18000fc07  push    r15
0x18000fc09  lea     rbp, [rsp-208h]
0x18000fc11  sub     rsp, 308h
0x18000fc18  mov     rax, cs:__security_cookie
0x18000fc1f  xor     rax, rsp
0x18000fc22  mov     [rbp+240h+var_50], rax
0x18000fc29  mov     ebx, r9d
0x18000fc2c  mov     [rsp+340h+hmenu], rdx
0x18000fc31  mov     esi, r8d
0x18000fc34  mov     [rsp+340h+var_310], ebx
0x18000fc38  mov     r12, rdx
0x18000fc3b  mov     r14, rcx
0x18000fc3e  mov     edi, 50h ; 'P'
0x18000fc43  lea     rcx, [rsp+340h+mi]; void *
0x18000fc48  mov     r8d, edi; Size
0x18000fc4b  xor     edx, edx; Val
0x18000fc4d  call    memset_0
0x18000fc52  mov     r15d, ebx
0x18000fc55  test    r14, r14
0x18000fc58  jz      loc_18000FECE
0x18000fc5e  test    r12, r12
0x18000fc61  jz      loc_18000FECE
0x18000fc67  mov     rcx, r14; hMenu
0x18000fc6a  call    cs:__imp_GetMenuItemCount
0x18000fc70  cmp     esi, eax
0x18000fc72  jb      short loc_18000FC7F
0x18000fc74  mov     esi, eax
0x18000fc76  mov     edi, 1
0x18000fc7b  mov     ebx, edi
0x18000fc7d  jmp     short loc_18000FCBE
0x18000fc7f  xor     edx, edx; Val
0x18000fc81  mov     [rbp+240h+mii.cbSize], edi
0x18000fc84  lea     rcx, [rbp+240h+mii.fMask]; void *
0x18000fc88  lea     r8d, [rdx+4Ch]; Size
0x18000fc8c  call    memset_0
0x18000fc91  mov     edi, 1
0x18000fc96  mov     [rbp+240h+mii.fMask], 12h
0x18000fc9d  mov     r8d, edi; fByPosition
0x18000fca0  lea     r9, [rbp+240h+mii]; lpmii
0x18000fca4  mov     edx, esi; item
0x18000fca6  mov     rcx, r14; hmenu
0x18000fca9  call    cs:__imp_GetMenuItemInfoW
0x18000fcaf  test    eax, eax
0x18000fcb1  jz      short loc_18000FCBC
0x18000fcb3  test    [rbp+240h+mii.fType], 800h
0x18000fcba  jnz     short loc_18000FC7B
0x18000fcbc  xor     ebx, ebx
0x18000fcbe  mov     r13d, [rbp+240h+arg_28]
0x18000fcc5  and     r13d, edi
0x18000fcc8  mov     [rsp+340h+var_30C], r13d
0x18000fccd  jz      short loc_18000FCF2
0x18000fccf  test    ebx, ebx
0x18000fcd1  jnz     short loc_18000FCF2
0x18000fcd3  xor     r9d, r9d; uIDNewItem
0x18000fcd6  mov     [rsp+340h+lpNewItem], 0; lpNewItem
0x18000fcdf  mov     r8d, 0C00h; uFlags
0x18000fce5  mov     edx, esi; uPosition
0x18000fce7  mov     rcx, r14; hMenu
0x18000fcea  call    cs:__imp_InsertMenuW
0x18000fcf0  mov     ebx, edi
0x18000fcf2  mov     rcx, r12; hMenu
0x18000fcf5  call    cs:__imp_GetMenuItemCount
0x18000fcfb  mov     r12d, eax
0x18000fcfe  mov     r13d, [rbp+240h+arg_20]
0x18000fd05  sub     r12d, edi
0x18000fd08  test    r12d, r12d
0x18000fd0b  js      loc_18000FE42
0x18000fd11  mov     rcx, [rsp+340h+hmenu]; hmenu
0x18000fd16  lea     rax, [rbp+240h+var_250]
0x18000fd1a  lea     r9, [rsp+340h+mi]; lpmii
0x18000fd1f  mov     [rbp+240h+mi.dwTypeData], rax
0x18000fd23  mov     r8d, edi; fByPosition
0x18000fd26  mov     [rsp+340h+mi.cbSize], 50h ; 'P'
0x18000fd2e  mov     edx, r12d; item
0x18000fd31  mov     qword ptr [rsp+340h+mi.fMask], 3Fh ; '?'
0x18000fd3a  mov     [rbp+240h+mi.dwItemData], 0
0x18000fd42  mov     [rbp+240h+mi.cch], 100h
0x18000fd49  call    cs:__imp_GetMenuItemInfoW
0x18000fd4f  test    eax, eax
0x18000fd51  jz      short loc_18000FD05
0x18000fd53  test    [rsp+340h+mi.fType], 800h
0x18000fd5b  jz      short loc_18000FD68
0x18000fd5d  test    ebx, ebx
0x18000fd5f  jnz     short loc_18000FD05
0x18000fd61  mov     ebx, edi
0x18000fd63  jmp     loc_18000FE22
0x18000fd68  mov     rax, [rsp+340h+mi.hSubMenu]
0x18000fd6d  mov     [rsp+340h+hMenu], rax
0x18000fd72  test    rax, rax
0x18000fd75  jz      loc_18000FDFE
0x18000fd7b  mov     r13d, [rbp+240h+arg_28]
0x18000fd82  and     r13d, 2
0x18000fd86  jz      short loc_18000FDAF
0x18000fd88  mov     ecx, [rsp+340h+mi.wID]
0x18000fd8c  add     ecx, [rsp+340h+var_310]
0x18000fd90  mov     [rsp+340h+mi.wID], ecx
0x18000fd94  cmp     ecx, [rbp+240h+arg_20]
0x18000fd9a  ja      loc_18000FCFE
0x18000fda0  cmp     r15d, ecx
0x18000fda3  lea     eax, [rcx+1]
0x18000fda6  cmova   eax, r15d
0x18000fdaa  mov     r15d, eax
0x18000fdad  jmp     short loc_18000FDB4
0x18000fdaf  and     [rsp+340h+mi.fMask], 0FFFFFFFDh
0x18000fdb4  call    cs:__imp_CreatePopupMenu
0x18000fdba  mov     [rsp+340h+mi.hSubMenu], rax
0x18000fdbf  test    rax, rax
0x18000fdc2  jz      loc_18000FECE
0x18000fdc8  mov     ecx, [rbp+240h+arg_20]
0x18000fdce  xor     r8d, r8d; unsigned int
0x18000fdd1  mov     r9d, [rsp+340h+var_310]; unsigned int
0x18000fdd6  mov     rdx, [rsp+340h+hMenu]; HMENU
0x18000fddb  mov     [rsp+340h+var_318], r13d; unsigned int
0x18000fde0  mov     dword ptr [rsp+340h+lpNewItem], ecx; unsigned int
0x18000fde4  mov     rcx, rax; HMENU
0x18000fde7  call    ?Cab_MergeMenus@@YAIPEAUHMENU__@@0IIIK@Z; Cab_MergeMenus(HMENU__ *,HMENU__ *,uint,uint,uint,ulong)
0x18000fdec  mov     r13d, [rbp+240h+arg_20]
0x18000fdf3  cmp     r15d, eax
0x18000fdf6  cmovbe  r15d, eax
0x18000fdfa  xor     ebx, ebx
0x18000fdfc  jmp     short loc_18000FE22
0x18000fdfe  mov     eax, [rsp+340h+mi.wID]
0x18000fe02  mov     ecx, r15d
0x18000fe05  add     eax, [rsp+340h+var_310]
0x18000fe09  mov     [rsp+340h+mi.wID], eax
0x18000fe0d  cmp     eax, r13d
0x18000fe10  ja      loc_18000FD05
0x18000fe16  xor     ebx, ebx
0x18000fe18  lea     r15d, [rax+1]
0x18000fe1c  cmp     ecx, eax
0x18000fe1e  cmova   r15d, ecx
0x18000fe22  lea     r9, [rsp+340h+mi]; lpmi
0x18000fe27  mov     r8d, edi; fByPosition
0x18000fe2a  mov     edx, esi; item
0x18000fe2c  mov     rcx, r14; hmenu
0x18000fe2f  call    cs:__imp_InsertMenuItemW
0x18000fe35  test    eax, eax
0x18000fe37  jz      loc_18000FECE
0x18000fe3d  jmp     loc_18000FD05
0x18000fe42  test    esi, esi
0x18000fe44  jnz     short loc_18000FE52
0x18000fe46  test    ebx, ebx
0x18000fe48  jz      loc_18000FECE
0x18000fe4e  xor     edx, edx
0x18000fe50  jmp     short loc_18000FE95
0x18000fe52  xor     edx, edx; Val
0x18000fe54  mov     [rbp+240h+mii.cbSize], 50h ; 'P'
0x18000fe5b  lea     rcx, [rbp+240h+mii.fMask]; void *
0x18000fe5f  lea     r8d, [rdx+4Ch]; Size
0x18000fe63  call    memset_0
0x18000fe68  lea     edx, [rsi-1]; item
0x18000fe6b  mov     [rbp+240h+mii.fMask], 12h
0x18000fe72  lea     r9, [rbp+240h+mii]; lpmii
0x18000fe76  mov     r8d, edi; fByPosition
0x18000fe79  mov     rcx, r14; hmenu
0x18000fe7c  call    cs:__imp_GetMenuItemInfoW
0x18000fe82  test    eax, eax
0x18000fe84  jz      short loc_18000FEA6
0x18000fe86  test    [rbp+240h+mii.fType], 800h
0x18000fe8d  jz      short loc_18000FEA6
0x18000fe8f  test    ebx, ebx
0x18000fe91  jz      short loc_18000FECE
0x18000fe93  mov     edx, esi; uPosition
0x18000fe95  mov     r8d, 400h; uFlags
0x18000fe9b  mov     rcx, r14; hMenu
0x18000fe9e  call    cs:__imp_DeleteMenu
0x18000fea4  jmp     short loc_18000FECE
0x18000fea6  cmp     [rsp+340h+var_30C], 0
0x18000feab  jz      short loc_18000FECE
0x18000fead  test    ebx, ebx
0x18000feaf  jnz     short loc_18000FECE
0x18000feb1  xor     r9d, r9d; uIDNewItem
0x18000feb4  mov     [rsp+340h+lpNewItem], 0; lpNewItem
0x18000febd  mov     r8d, 0C00h; uFlags
0x18000fec3  mov     edx, esi; uPosition
0x18000fec5  mov     rcx, r14; hMenu
0x18000fec8  call    cs:__imp_InsertMenuW
0x18000fece  mov     eax, r15d
0x18000fed1  mov     rcx, [rbp+240h+var_50]
0x18000fed8  xor     rcx, rsp; StackCookie
0x18000fedb  call    __security_check_cookie
0x18000fee0  add     rsp, 308h
0x18000fee7  pop     r15
0x18000fee9  pop     r14
0x18000feeb  pop     r13
0x18000feed  pop     r12
0x18000feef  pop     rdi
0x18000fef0  pop     rsi
0x18000fef1  pop     rbx
0x18000fef2  pop     rbp
0x18000fef3  retn
```
