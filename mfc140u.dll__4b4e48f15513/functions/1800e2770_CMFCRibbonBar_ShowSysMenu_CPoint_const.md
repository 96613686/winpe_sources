# CMFCRibbonBar::ShowSysMenu(CPoint const &)

- ea: `0x1800e2770`
- end: `0x1800e29c5`
- name: `?ShowSysMenu@CMFCRibbonBar@@IEAAXAEBVCPoint@@@Z`
- size: `597`
- prototype: `void __fastcall(CMFCRibbonBar *this, const CPoint *point)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800df300`
- `0x1800e29d0`
- `0x1800e7290`

## callees

- `0x1800e2770`
- `0x180296d00`
- `0x1802b4cb0`
- `0x1802b62e0`
- `0x1802c7020`

## import_xrefs

- `USER32!EnableMenuItem` at `0x1800e281b`
- `USER32!EnableMenuItem` at `0x1800e282d`
- `USER32!EnableMenuItem` at `0x1800e283f`
- `USER32!EnableMenuItem` at `0x1800e2857`
- `USER32!EnableMenuItem` at `0x1800e2869`
- `USER32!EnableMenuItem` at `0x1800e287b`
- `USER32!EnableMenuItem` at `0x1800e288d`
- `USER32!EnableMenuItem` at `0x1800e281b`
- `USER32!EnableMenuItem` at `0x1800e282d`
- `USER32!EnableMenuItem` at `0x1800e283f`
- `USER32!EnableMenuItem` at `0x1800e2857`
- `USER32!EnableMenuItem` at `0x1800e2869`
- `USER32!EnableMenuItem` at `0x1800e287b`
- `USER32!EnableMenuItem` at `0x1800e288d`
- `USER32!GetSystemMenu` at `0x1800e27b5`
- `USER32!GetSystemMenu` at `0x1800e27b5`
- `USER32!IsZoomed` at `0x1800e2800`
- `USER32!IsZoomed` at `0x1800e2800`
- `USER32!DeleteMenu` at `0x1800e28bf`
- `USER32!DeleteMenu` at `0x1800e28d1`
- `USER32!DeleteMenu` at `0x1800e2903`
- `USER32!DeleteMenu` at `0x1800e28bf`
- `USER32!DeleteMenu` at `0x1800e28d1`
- `USER32!DeleteMenu` at `0x1800e2903`
- `USER32!SetMenuDefaultItem` at `0x1800e27e4`
- `USER32!SetMenuDefaultItem` at `0x1800e27e4`
- `USER32!TrackPopupMenu` at `0x1800e29a9`
- `USER32!TrackPopupMenu` at `0x1800e29a9`
- `USER32!GetParent` at `0x1800e278f`
- `USER32!GetParent` at `0x1800e27ee`
- `USER32!GetParent` at `0x1800e2897`
- `USER32!GetParent` at `0x1800e28db`
- `USER32!GetParent` at `0x1800e2920`
- `USER32!GetParent` at `0x1800e2972`
- `USER32!GetParent` at `0x1800e278f`
- `USER32!GetParent` at `0x1800e27ee`
- `USER32!GetParent` at `0x1800e2897`
- `USER32!GetParent` at `0x1800e28db`
- `USER32!GetParent` at `0x1800e2920`
- `USER32!GetParent` at `0x1800e2972`

## pseudocode

```c
void __fastcall CMFCRibbonBar::ShowSysMenu(CMFCRibbonBar *this, const CPoint *point)
{
  HWND Parent; // rax
  CWnd *v5; // rax
  HWND m_hWnd; // rcx
  HMENU SystemMenu; // rax
  CMenu *v8; // rax
  CMenu *v9; // rdi
  HMENU m_hMenu; // rcx
  HWND v11; // rax
  CWnd *v12; // rax
  BOOL v13; // eax
  HMENU v14; // rcx
  UINT v15; // edx
  HWND v16; // rax
  CWnd *v17; // rax
  HWND v18; // rax
  CWnd *v19; // rax
  CMFCPopupMenu *(__fastcall *ShowPopupMenu)(CContextMenuManager *, HMENU__ *, int, int, CWnd *, int, int, int); // rbx
  HWND v21; // rax
  CWnd *v22; // rax
  HWND__ *m_hWndOwner; // rax
  HWND hWnd; // rax

  Parent = GetParent(this->m_hWnd);
  v5 = CWnd::FromHandle(Parent);
  if ( v5 )
  {
    m_hWnd = v5->m_hWnd;
    if ( m_hWnd )
    {
      SystemMenu = GetSystemMenu(m_hWnd, 0);
      v8 = CMenu::FromHandle(SystemMenu);
      v9 = v8;
      if ( v8 )
      {
        m_hMenu = v8->m_hMenu;
        if ( m_hMenu )
        {
          SetMenuDefaultItem(m_hMenu, 0xF060u, 0);
          v11 = GetParent(this->m_hWnd);
          v12 = CWnd::FromHandle(v11);
          v13 = IsZoomed(v12->m_hWnd);
          v14 = v9->m_hMenu;
          if ( v13 )
          {
            EnableMenuItem(v14, 0xF000u, 3u);
            EnableMenuItem(v9->m_hMenu, 0xF010u, 3u);
            EnableMenuItem(v9->m_hMenu, 0xF030u, 3u);
            v15 = 61728;
          }
          else
          {
            EnableMenuItem(v14, 0xF120u, 3u);
            EnableMenuItem(v9->m_hMenu, 0xF000u, 0);
            EnableMenuItem(v9->m_hMenu, 0xF010u, 0);
            v15 = 61488;
          }
          EnableMenuItem(v9->m_hMenu, v15, 0);
          v16 = GetParent(this->m_hWnd);
          v17 = CWnd::FromHandle(v16);
          if ( (CWnd::GetStyle(v17) & 0x10000) == 0 )
          {
            DeleteMenu(v9->m_hMenu, 0xF120u, 0);
            DeleteMenu(v9->m_hMenu, 0xF030u, 0);
          }
          v18 = GetParent(this->m_hWnd);
          v19 = CWnd::FromHandle(v18);
          if ( (CWnd::GetStyle(v19) & 0x20000) == 0 )
            DeleteMenu(v9->m_hMenu, 0xF020u, 0);
          if ( afxContextMenuManager )
          {
            ShowPopupMenu = afxContextMenuManager->ShowPopupMenu;
            v21 = GetParent(this->m_hWnd);
            v22 = CWnd::FromHandle(v21);
            ShowPopupMenu(afxContextMenuManager, v9->m_hMenu, point->x, point->y, v22, 1, 1, 0);
          }
          else
          {
            m_hWndOwner = this->m_hWndOwner;
            if ( !m_hWndOwner )
              m_hWndOwner = GetParent(this->m_hWnd);
            hWnd = (HWND)CWnd::FromHandle(m_hWndOwner);
            if ( hWnd )
              hWnd = (HWND)*((_QWORD *)hWnd + 8);
            TrackPopupMenu(v9->m_hMenu, 4u, point->x, point->y, 0, hWnd, 0);
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1800e2770  mov     [rsp+arg_0], rbx
0x1800e2775  mov     [rsp+arg_8], rsi
0x1800e277a  mov     [rsp+arg_10], rdi
0x1800e277f  push    r14
0x1800e2781  sub     rsp, 50h
0x1800e2785  mov     rsi, this
0x1800e2788  mov     r14, point
0x1800e278b  mov     this, [this+40h]; hWnd
0x1800e278f  call    cs:__imp_GetParent
0x1800e2795  mov     this, rax; hWnd
0x1800e2798  call    ?FromHandle@CWnd@@SAPEAV1@PEAUHWND__@@@Z; CWnd::FromHandle(HWND__ *)
0x1800e279d  test    rax, rax
0x1800e27a0  jz      loc_1800E29AF
0x1800e27a6  mov     this, [rax+40h]; hWnd
0x1800e27aa  test    this, this
0x1800e27ad  jz      loc_1800E29AF
0x1800e27b3  xor     edx, edx; bRevert
0x1800e27b5  call    cs:__imp_GetSystemMenu
0x1800e27bb  mov     this, rax; hMenu
0x1800e27be  call    ?FromHandle@CMenu@@SAPEAV1@PEAUHMENU__@@@Z; CMenu::FromHandle(HMENU__ *)
0x1800e27c3  mov     rdi, rax
0x1800e27c6  test    rax, rax
0x1800e27c9  jz      loc_1800E29AF
0x1800e27cf  mov     this, [rax+8]; hMenu
0x1800e27d3  test    this, this
0x1800e27d6  jz      loc_1800E29AF
0x1800e27dc  xor     r8d, r8d; fByPos
0x1800e27df  mov     edx, 0F060h; uItem
0x1800e27e4  call    cs:__imp_SetMenuDefaultItem
0x1800e27ea  mov     this, [rsi+40h]; hWnd
0x1800e27ee  call    cs:__imp_GetParent
0x1800e27f4  mov     this, rax; hWnd
0x1800e27f7  call    ?FromHandle@CWnd@@SAPEAV1@PEAUHWND__@@@Z; CWnd::FromHandle(HWND__ *)
0x1800e27fc  mov     this, [rax+40h]; hWnd
0x1800e2800  call    cs:__imp_IsZoomed
0x1800e2806  mov     this, [rdi+8]; hMenu
0x1800e280a  test    eax, eax
0x1800e280c  jz      short loc_1800E284C
0x1800e280e  mov     ebx, 3
0x1800e2813  mov     edx, 0F000h; uIDEnableItem
0x1800e2818  mov     r8d, ebx; uEnable
0x1800e281b  call    cs:__imp_EnableMenuItem
0x1800e2821  mov     this, [rdi+8]; hMenu
0x1800e2825  mov     r8d, ebx; uEnable
0x1800e2828  mov     edx, 0F010h; uIDEnableItem
0x1800e282d  call    cs:__imp_EnableMenuItem
0x1800e2833  mov     this, [rdi+8]; hMenu
0x1800e2837  mov     r8d, ebx; uEnable
0x1800e283a  mov     edx, 0F030h; uIDEnableItem
0x1800e283f  call    cs:__imp_EnableMenuItem
0x1800e2845  mov     edx, 0F120h
0x1800e284a  jmp     short loc_1800E2886
0x1800e284c  mov     edx, 0F120h; uIDEnableItem
0x1800e2851  mov     r8d, 3; uEnable
0x1800e2857  call    cs:__imp_EnableMenuItem
0x1800e285d  mov     this, [rdi+8]; hMenu
0x1800e2861  xor     r8d, r8d; uEnable
0x1800e2864  mov     edx, 0F000h; uIDEnableItem
0x1800e2869  call    cs:__imp_EnableMenuItem
0x1800e286f  mov     this, [rdi+8]; hMenu
0x1800e2873  xor     r8d, r8d; uEnable
0x1800e2876  mov     edx, 0F010h; uIDEnableItem
0x1800e287b  call    cs:__imp_EnableMenuItem
0x1800e2881  mov     edx, 0F030h; uIDEnableItem
0x1800e2886  mov     this, [rdi+8]; hMenu
0x1800e288a  xor     r8d, r8d; uEnable
0x1800e288d  call    cs:__imp_EnableMenuItem
0x1800e2893  mov     this, [rsi+40h]; hWnd
0x1800e2897  call    cs:__imp_GetParent
0x1800e289d  mov     this, rax; hWnd
0x1800e28a0  call    ?FromHandle@CWnd@@SAPEAV1@PEAUHWND__@@@Z; CWnd::FromHandle(HWND__ *)
0x1800e28a5  mov     this, rax; this
0x1800e28a8  call    ?GetStyle@CWnd@@QEBAKXZ; CWnd::GetStyle(void)
0x1800e28ad  bt      eax, 10h
0x1800e28b1  jb      short loc_1800E28D7
0x1800e28b3  mov     this, [rdi+8]; hMenu
0x1800e28b7  xor     r8d, r8d; uFlags
0x1800e28ba  mov     edx, 0F120h; uPosition
0x1800e28bf  call    cs:__imp_DeleteMenu
0x1800e28c5  mov     this, [rdi+8]; hMenu
0x1800e28c9  xor     r8d, r8d; uFlags
0x1800e28cc  mov     edx, 0F030h; uPosition
0x1800e28d1  call    cs:__imp_DeleteMenu
0x1800e28d7  mov     this, [rsi+40h]; hWnd
0x1800e28db  call    cs:__imp_GetParent
0x1800e28e1  mov     this, rax; hWnd
0x1800e28e4  call    ?FromHandle@CWnd@@SAPEAV1@PEAUHWND__@@@Z; CWnd::FromHandle(HWND__ *)
0x1800e28e9  mov     this, rax; this
0x1800e28ec  call    ?GetStyle@CWnd@@QEBAKXZ; CWnd::GetStyle(void)
0x1800e28f1  bt      eax, 11h
0x1800e28f5  jb      short loc_1800E2909
0x1800e28f7  mov     this, [rdi+8]; hMenu
0x1800e28fb  xor     r8d, r8d; uFlags
0x1800e28fe  mov     edx, 0F020h; uPosition
0x1800e2903  call    cs:__imp_DeleteMenu
0x1800e2909  mov     rax, cs:?afxContextMenuManager@@3PEAVCContextMenuManager@@EA; CContextMenuManager * afxContextMenuManager
0x1800e2910  test    rax, rax
0x1800e2913  jz      short loc_1800E2962
0x1800e2915  mov     rax, [rax]
0x1800e2918  mov     this, [rsi+40h]; hWnd
0x1800e291c  mov     rbx, [rax+28h]
0x1800e2920  call    cs:__imp_GetParent
0x1800e2926  mov     this, rax; hWnd
0x1800e2929  call    ?FromHandle@CWnd@@SAPEAV1@PEAUHWND__@@@Z; CWnd::FromHandle(HWND__ *)
0x1800e292e  and     [rsp+58h+var_20], 0
0x1800e2933  mov     ecx, 1
0x1800e2938  mov     r9d, [r14+4]
0x1800e293c  mov     r8d, [r14]
0x1800e293f  mov     point, [rdi+8]
0x1800e2943  mov     dword ptr [rsp+58h+var_28], ecx
0x1800e2947  mov     dword ptr [rsp+58h+hWnd], ecx
0x1800e294b  mov     this, cs:?afxContextMenuManager@@3PEAVCContextMenuManager@@EA; CContextMenuManager * afxContextMenuManager
0x1800e2952  mov     [rsp+58h+var_38], rax
0x1800e2957  mov     rax, rbx
0x1800e295a  call    cs:__guard_dispatch_icall_fptr
0x1800e2960  jmp     short loc_1800E29AF
0x1800e2962  mov     rax, [rsi+0A0h]
0x1800e2969  test    rax, rax
0x1800e296c  jnz     short loc_1800E2978
0x1800e296e  mov     this, [rsi+40h]; hWnd
0x1800e2972  call    cs:__imp_GetParent
0x1800e2978  mov     this, rax; hWnd
0x1800e297b  call    ?FromHandle@CWnd@@SAPEAV1@PEAUHWND__@@@Z; CWnd::FromHandle(HWND__ *)
0x1800e2980  test    rax, rax
0x1800e2983  jz      short loc_1800E2989
0x1800e2985  mov     rax, [rax+40h]
0x1800e2989  and     [rsp+58h+var_28], 0
0x1800e298f  mov     edx, 4; uFlags
0x1800e2994  mov     r9d, [r14+4]; y
0x1800e2998  mov     r8d, [r14]; x
0x1800e299b  mov     this, [rdi+8]; hMenu
0x1800e299f  mov     [rsp+58h+hWnd], rax; hWnd
0x1800e29a4  and     dword ptr [rsp+58h+var_38], 0
0x1800e29a9  call    cs:__imp_TrackPopupMenu
0x1800e29af  mov     rbx, [rsp+58h+arg_0]
0x1800e29b4  mov     rsi, [rsp+58h+arg_8]
0x1800e29b9  mov     rdi, [rsp+58h+arg_10]
0x1800e29be  add     rsp, 50h
0x1800e29c2  pop     r14
0x1800e29c4  retn
```
