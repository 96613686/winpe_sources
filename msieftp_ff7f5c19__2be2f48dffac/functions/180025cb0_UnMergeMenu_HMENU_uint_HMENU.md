# UnMergeMenu(HMENU__ *,uint,HMENU__ *)

- ea: `0x180025cb0`
- end: `0x180025d74`
- name: `?UnMergeMenu@@YAJPEAUHMENU__@@I0@Z`
- size: `196`
- prototype: `__int64 __fastcall(HMENU, unsigned int, HMENU)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180025cb0`
- `0x1800264b0`

## callees

- `0x180002b60`
- `0x180025cb0`

## import_xrefs

- `USER32!GetMenuItemID` at `0x180025ce2`
- `USER32!GetMenuItemID` at `0x180025ce2`
- `USER32!GetMenuItemInfoW` at `0x180025d3a`
- `USER32!GetMenuItemInfoW` at `0x180025d3a`
- `USER32!GetMenuItemCount` at `0x180025ccb`
- `USER32!GetMenuItemCount` at `0x180025ccb`
- `USER32!DeleteMenu` at `0x180025cfa`
- `USER32!DeleteMenu` at `0x180025cfa`

## pseudocode

```c
__int64 __fastcall UnMergeMenu(HMENU a1, unsigned int a2, HMENU a3)
{
  unsigned int v6; // edi
  UINT v7; // ebx
  unsigned int MenuItemCount; // ebp
  UINT MenuItemID; // eax
  struct tagMENUITEMINFOW mii; // [rsp+20h] [rbp-88h] BYREF

  v6 = 0;
  v7 = 0;
  MenuItemCount = GetMenuItemCount(a3);
  if ( MenuItemCount )
  {
    do
    {
      MenuItemID = GetMenuItemID(a3, v7);
      if ( MenuItemID == -1 )
      {
        memset_0(&mii, 0, sizeof(mii));
        mii.cbSize = 80;
        mii.fMask = 4;
        mii.cch = 0;
        if ( GetMenuItemInfoW(a3, v7, 1, &mii) && mii.hSubMenu )
          v6 = UnMergeMenu(a1, a2, mii.hSubMenu);
      }
      else
      {
        DeleteMenu(a1, MenuItemID + a2, 0x400u);
      }
      ++v7;
    }
    while ( v7 < MenuItemCount );
  }
  return v6;
}

```

## disassembly

```asm
0x180025cb0  push    rbx
0x180025cb2  push    rbp
0x180025cb3  push    rsi
0x180025cb4  push    rdi
0x180025cb5  push    r14
0x180025cb7  push    r15
0x180025cb9  sub     rsp, 78h
0x180025cbd  mov     r15, rcx
0x180025cc0  mov     rsi, r8
0x180025cc3  mov     rcx, r8; hMenu
0x180025cc6  mov     r14d, edx
0x180025cc9  xor     edi, edi
0x180025ccb  call    cs:__imp_GetMenuItemCount
0x180025cd1  xor     ebx, ebx
0x180025cd3  mov     ebp, eax
0x180025cd5  test    eax, eax
0x180025cd7  jz      loc_180025D65
0x180025cdd  mov     edx, ebx; nPos
0x180025cdf  mov     rcx, rsi; hMenu
0x180025ce2  call    cs:__imp_GetMenuItemID
0x180025ce8  cmp     eax, 0FFFFFFFFh
0x180025ceb  jz      short loc_180025D02
0x180025ced  lea     edx, [rax+r14]; uPosition
0x180025cf1  mov     r8d, 400h; uFlags
0x180025cf7  mov     rcx, r15; hMenu
0x180025cfa  call    cs:__imp_DeleteMenu
0x180025d00  jmp     short loc_180025D5B
0x180025d02  xor     edx, edx; Val
0x180025d04  lea     rcx, [rsp+0A8h+mii]; void *
0x180025d09  lea     r8d, [rdx+50h]; Size
0x180025d0d  call    memset_0
0x180025d12  lea     r9, [rsp+0A8h+mii]; lpmii
0x180025d17  mov     [rsp+0A8h+mii.cbSize], 50h ; 'P'
0x180025d1f  mov     r8d, 1; fByPosition
0x180025d25  mov     [rsp+0A8h+mii.fMask], 4
0x180025d2d  mov     edx, ebx; item
0x180025d2f  mov     [rsp+0A8h+mii.cch], 0
0x180025d37  mov     rcx, rsi; hmenu
0x180025d3a  call    cs:__imp_GetMenuItemInfoW
0x180025d40  test    eax, eax
0x180025d42  jz      short loc_180025D5B
0x180025d44  mov     r8, [rsp+0A8h+mii.hSubMenu]; HMENU
0x180025d49  test    r8, r8
0x180025d4c  jz      short loc_180025D5B
0x180025d4e  mov     edx, r14d; unsigned int
0x180025d51  mov     rcx, r15; HMENU
0x180025d54  call    ?UnMergeMenu@@YAJPEAUHMENU__@@I0@Z; UnMergeMenu(HMENU__ *,uint,HMENU__ *)
0x180025d59  mov     edi, eax
0x180025d5b  inc     ebx
0x180025d5d  cmp     ebx, ebp
0x180025d5f  jb      loc_180025CDD
0x180025d65  mov     eax, edi
0x180025d67  add     rsp, 78h
0x180025d6b  pop     r15
0x180025d6d  pop     r14
0x180025d6f  pop     rdi
0x180025d70  pop     rsi
0x180025d71  pop     rbp
0x180025d72  pop     rbx
0x180025d73  retn
```
