# CAttMenu::BuildMenu(void)

- ea: `0x18008f4ec`
- end: `0x18008f70e`
- name: `?BuildMenu@CAttMenu@@AEAAJXZ`
- size: `546`
- prototype: `__int64 __fastcall(CAttMenu *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18009034c`

## callees

- `0x18008e390`
- `0x18008f4ec`
- `0x18008f714`
- `0x18008f884`
- `0x1800cc9ba`
- `0x1800cd010`

## import_xrefs

- `USER32!GetSystemMetrics` at `0x18008f54b`
- `USER32!GetSystemMetrics` at `0x18008f576`
- `USER32!GetSystemMetrics` at `0x18008f586`
- `USER32!GetSystemMetrics` at `0x18008f54b`
- `USER32!GetSystemMetrics` at `0x18008f576`
- `USER32!GetSystemMetrics` at `0x18008f586`
- `USER32!CreatePopupMenu` at `0x18008f51d`
- `USER32!CreatePopupMenu` at `0x18008f51d`
- `USER32!InsertMenuItemA` at `0x18008f641`
- `USER32!InsertMenuItemA` at `0x18008f69f`
- `USER32!InsertMenuItemA` at `0x18008f6e1`
- `USER32!InsertMenuItemA` at `0x18008f641`
- `USER32!InsertMenuItemA` at `0x18008f69f`
- `USER32!InsertMenuItemA` at `0x18008f6e1`

## pseudocode

```c
__int64 __fastcall CAttMenu::BuildMenu(CAttMenu *this)
{
  HMENU PopupMenu; // rax
  int v4; // edi
  UINT v5; // r15d
  int v6; // esi
  LONG v7; // eax
  LONG cy; // ecx
  int v9; // r13d
  unsigned int v10; // r14d
  __int64 v11; // rdx
  UINT v12; // ecx
  ULONG_PTR v13; // r12
  int v14; // eax
  HMENU v15; // rcx
  MENUITEMINFOA mi; // [rsp+20h] [rbp-58h] BYREF
  int v17; // [rsp+C0h] [rbp+48h]
  int SystemMetrics; // [rsp+C8h] [rbp+50h]
  struct tagSIZE v19; // [rsp+D0h] [rbp+58h] BYREF
  ULONG_PTR v20; // [rsp+D8h] [rbp+60h] BYREF

  memset_0(&mi, 0, sizeof(mi));
  v19 = 0;
  v20 = 0;
  PopupMenu = CreatePopupMenu();
  *(_QWORD *)this = PopupMenu;
  if ( !PopupMenu )
    return 2147942414LL;
  v17 = 0;
  v4 = 0;
  v5 = 0;
  v6 = 0;
  SystemMetrics = GetSystemMetrics(1);
  CAttMenu::GetItemTextExtent(this, 0, L"BIGGERMAXATTACHMENTNAME.TXT", &v19);
  *((_DWORD *)this + 8) = v19.cx;
  v7 = GetSystemMetrics(50);
  cy = v19.cy;
  if ( v19.cy <= v7 )
    cy = GetSystemMetrics(50);
  mi.wID = 1;
  v9 = cy + 8;
  v10 = 0;
  mi.cbSize = 80;
  mi.fMask = 50;
  mi.fType = 256;
  while ( v10 < *((_DWORD *)this + 4) )
  {
    v11 = *(_QWORD *)(*((_QWORD *)this + 14) + 8LL * v10);
    if ( v11 != *((_QWORD *)this + 13) )
    {
      v4 = HrAttachDataFromBodyPart(*((_QWORD *)this + 10), v11, &v20, *((unsigned int *)this + 7));
      if ( v4 >= 0 )
      {
        v12 = 256;
        v13 = v20;
        mi.dwItemData = v20;
        if ( v9 + v17 >= SystemMetrics )
          v12 = 288;
        v14 = v9;
        if ( v9 + v17 < SystemMetrics )
          v14 = v9 + v17;
        mi.fType = v12;
        v17 = v14;
        if ( !v20 || *(_DWORD *)(v20 + 1592) || *((_DWORD *)this + 7) )
        {
          ++v6;
        }
        else
        {
          mi.fMask |= 1u;
          mi.fState = 3;
        }
        if ( !InsertMenuItemA(*(HMENU *)this, v5, 1, &mi) )
        {
          ((void (__fastcall *)(LPMALLOC, ULONG_PTR))g_pMalloc->lpVtbl->Free)(g_pMalloc, v13);
          v4 = -2147467259;
LABEL_27:
          if ( *(_QWORD *)this )
            CAttMenu::DestroyMenu(this, *(HMENU *)this);
          return (unsigned int)v4;
        }
        mi.fMask &= ~1u;
        ++v5;
        mi.fState = 0;
        ++mi.wID;
      }
    }
    ++v10;
  }
  v15 = *(HMENU *)this;
  mi.fType = 2048;
  mi.dwItemData = 0;
  InsertMenuItemA(v15, v5, 1, &mi);
  mi.fType = 256;
  mi.dwTypeData = 0;
  mi.dwItemData = 0;
  mi.wID = 214;
  if ( !*((_DWORD *)this + 7) )
  {
    if ( !v6 )
    {
      mi.fMask |= 1u;
      mi.fState = 3;
    }
    *((_DWORD *)this + 6) = v6;
  }
  InsertMenuItemA(*(HMENU *)this, v5 + 1, 1, &mi);
  if ( v4 < 0 )
    goto LABEL_27;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18008f4ec  push    rbp
0x18008f4ee  push    rbx
0x18008f4ef  push    rsi
0x18008f4f0  push    rdi
0x18008f4f1  push    r12
0x18008f4f3  push    r13
0x18008f4f5  push    r14
0x18008f4f7  push    r15
0x18008f4f9  mov     rbp, rsp
0x18008f4fc  sub     rsp, 78h
0x18008f500  xor     edx, edx; Val
0x18008f502  mov     rbx, rcx
0x18008f505  lea     rcx, [rbp+mi]; void *
0x18008f509  lea     r8d, [rdx+50h]; Size
0x18008f50d  call    memset_0
0x18008f512  xor     r12d, r12d
0x18008f515  mov     qword ptr [rbp+arg_10.cx], r12
0x18008f519  mov     [rbp+arg_18], r12
0x18008f51d  call    cs:__imp_CreatePopupMenu
0x18008f523  mov     [rbx], rax
0x18008f526  test    rax, rax
0x18008f529  jnz     short loc_18008F535
0x18008f52b  mov     eax, 8007000Eh
0x18008f530  jmp     loc_18008F6FD
0x18008f535  mov     r14d, 1
0x18008f53b  mov     [rbp+arg_0], r12d
0x18008f53f  mov     ecx, r14d; nIndex
0x18008f542  mov     edi, r12d
0x18008f545  mov     r15d, r12d
0x18008f548  mov     esi, r12d
0x18008f54b  call    cs:__imp_GetSystemMetrics
0x18008f551  lea     r9, [rbp+arg_10]; struct tagSIZE *
0x18008f555  xor     edx, edx; HWND
0x18008f557  lea     r8, aBiggermaxattac; "BIGGERMAXATTACHMENTNAME.TXT"
0x18008f55e  mov     [rbp+arg_8], eax
0x18008f561  mov     rcx, rbx; this
0x18008f564  call    ?GetItemTextExtent@CAttMenu@@AEAAJPEAUHWND__@@PEBGPEAUtagSIZE@@@Z; CAttMenu::GetItemTextExtent(HWND__ *,ushort const *,tagSIZE *)
0x18008f569  mov     ecx, [rbp+arg_10.cx]
0x18008f56c  lea     r13d, [r14+31h]
0x18008f570  mov     [rbx+20h], ecx
0x18008f573  mov     ecx, r13d; nIndex
0x18008f576  call    cs:__imp_GetSystemMetrics
0x18008f57c  mov     ecx, [rbp+arg_10.cy]
0x18008f57f  cmp     ecx, eax
0x18008f581  jg      short loc_18008F58E
0x18008f583  mov     ecx, r13d; nIndex
0x18008f586  call    cs:__imp_GetSystemMetrics
0x18008f58c  mov     ecx, eax
0x18008f58e  mov     [rbp+mi.wID], r14d
0x18008f592  lea     r13d, [rcx+8]
0x18008f596  mov     r14d, r12d
0x18008f599  mov     [rbp+mi.cbSize], 50h ; 'P'
0x18008f5a0  mov     [rbp+mi.fMask], 32h ; '2'
0x18008f5a7  mov     [rbp+mi.fType], 100h
0x18008f5ae  cmp     r14d, [rbx+10h]
0x18008f5b2  jnb     loc_18008F681
0x18008f5b8  mov     rax, [rbx+70h]
0x18008f5bc  mov     ecx, r14d
0x18008f5bf  mov     rdx, [rax+rcx*8]
0x18008f5c3  cmp     rdx, [rbx+68h]
0x18008f5c7  jz      loc_18008F65C
0x18008f5cd  mov     r9d, [rbx+1Ch]
0x18008f5d1  lea     r8, [rbp+arg_18]
0x18008f5d5  mov     rcx, [rbx+50h]
0x18008f5d9  call    HrAttachDataFromBodyPart
0x18008f5de  mov     edi, eax
0x18008f5e0  test    eax, eax
0x18008f5e2  js      short loc_18008F65C
0x18008f5e4  mov     edx, [rbp+arg_0]
0x18008f5e7  mov     ecx, 100h
0x18008f5ec  mov     r12, [rbp+arg_18]
0x18008f5f0  add     edx, r13d
0x18008f5f3  cmp     edx, [rbp+arg_8]
0x18008f5f6  mov     [rbp+mi.dwItemData], r12
0x18008f5fa  lea     eax, [rcx+20h]
0x18008f5fd  cmovge  ecx, eax
0x18008f600  mov     eax, r13d
0x18008f603  cmovl   eax, edx
0x18008f606  mov     [rbp+mi.fType], ecx
0x18008f609  mov     [rbp+arg_0], eax
0x18008f60c  test    r12, r12
0x18008f60f  jz      short loc_18008F62F
0x18008f611  cmp     dword ptr [r12+638h], 0
0x18008f61a  jnz     short loc_18008F62F
0x18008f61c  cmp     dword ptr [rbx+1Ch], 0
0x18008f620  jnz     short loc_18008F62F
0x18008f622  or      [rbp+mi.fMask], 1
0x18008f626  mov     [rbp+mi.fState], 3
0x18008f62d  jmp     short loc_18008F631
0x18008f62f  inc     esi
0x18008f631  mov     rcx, [rbx]; hmenu
0x18008f634  lea     r9, [rbp+mi]; lpmi
0x18008f638  mov     r8d, 1; fByPosition
0x18008f63e  mov     edx, r15d; item
0x18008f641  call    cs:__imp_InsertMenuItemA
0x18008f647  test    eax, eax
0x18008f649  jz      short loc_18008F664
0x18008f64b  and     [rbp+mi.fMask], 0FFFFFFFEh
0x18008f64f  xor     r12d, r12d
0x18008f652  inc     r15d
0x18008f655  mov     [rbp+mi.fState], r12d
0x18008f659  inc     [rbp+mi.wID]
0x18008f65c  inc     r14d
0x18008f65f  jmp     loc_18008F5AE
0x18008f664  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18008f66b  mov     rdx, r12
0x18008f66e  mov     rax, [rcx]
0x18008f671  mov     rax, [rax+28h]
0x18008f675  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f67a  mov     edi, 80004005h
0x18008f67f  jmp     short loc_18008F6EB
0x18008f681  mov     rcx, [rbx]; hmenu
0x18008f684  lea     r9, [rbp+mi]; lpmi
0x18008f688  mov     r13d, 1
0x18008f68e  mov     [rbp+mi.fType], 800h
0x18008f695  mov     r8d, r13d; fByPosition
0x18008f698  mov     [rbp+mi.dwItemData], r12
0x18008f69c  mov     edx, r15d; item
0x18008f69f  call    cs:__imp_InsertMenuItemA
0x18008f6a5  mov     [rbp+mi.fType], 100h
0x18008f6ac  mov     [rbp+mi.dwTypeData], r12
0x18008f6b0  mov     [rbp+mi.dwItemData], r12
0x18008f6b4  mov     [rbp+mi.wID], 0D6h
0x18008f6bb  cmp     [rbx+1Ch], r12d
0x18008f6bf  jnz     short loc_18008F6D3
0x18008f6c1  test    esi, esi
0x18008f6c3  jnz     short loc_18008F6D0
0x18008f6c5  or      [rbp+mi.fMask], r13d
0x18008f6c9  mov     [rbp+mi.fState], 3
0x18008f6d0  mov     [rbx+18h], esi
0x18008f6d3  mov     rcx, [rbx]; hmenu
0x18008f6d6  lea     r9, [rbp+mi]; lpmi
0x18008f6da  mov     r8d, r13d; fByPosition
0x18008f6dd  lea     edx, [r15+1]; item
0x18008f6e1  call    cs:__imp_InsertMenuItemA
0x18008f6e7  test    edi, edi
0x18008f6e9  jns     short loc_18008F6FB
0x18008f6eb  mov     rdx, [rbx]; hMenu
0x18008f6ee  test    rdx, rdx
0x18008f6f1  jz      short loc_18008F6FB
0x18008f6f3  mov     rcx, rbx; this
0x18008f6f6  call    ?DestroyMenu@CAttMenu@@AEAAJPEAUHMENU__@@@Z; CAttMenu::DestroyMenu(HMENU__ *)
0x18008f6fb  mov     eax, edi
0x18008f6fd  add     rsp, 78h
0x18008f701  pop     r15
0x18008f703  pop     r14
0x18008f705  pop     r13
0x18008f707  pop     r12
0x18008f709  pop     rdi
0x18008f70a  pop     rsi
0x18008f70b  pop     rbx
0x18008f70c  pop     rbp
0x18008f70d  retn
```
