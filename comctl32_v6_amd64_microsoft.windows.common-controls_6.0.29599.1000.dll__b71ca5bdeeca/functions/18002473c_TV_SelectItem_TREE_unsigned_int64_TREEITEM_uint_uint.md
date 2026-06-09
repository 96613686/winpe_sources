# TV_SelectItem(_TREE *,unsigned __int64,_TREEITEM *,uint,uint)

- ea: `0x18002473c`
- end: `0x180024b1d`
- name: `?TV_SelectItem@@YAHPEAU_TREE@@_KPEAU_TREEITEM@@II@Z`
- size: `993`
- prototype: `__int64 __usercall@<rax>(struct _TREE *@<rcx>, unsigned __int64@<rdx>, struct _TREEITEM *@<r8>, unsigned int@<r9d>, unsigned int)`
- caller_count: `9`
- callee_count: `12`
- tags: `installer_update`

## callers

- `0x18001d900`
- `0x180023aa4`
- `0x180024238`
- `0x180026000`
- `0x1800bf000`
- `0x1800d7fc8`
- `0x1800e8ebc`
- `0x180138248`
- `0x18013870c`

## callees

- `0x18001faf8`
- `0x180023848`
- `0x180023dd8`
- `0x18002473c`
- `0x180024b24`
- `0x180024db0`
- `0x180025ad0`
- `0x1800c8ba8`
- `0x1800c8c14`
- `0x1800c8ea8`
- `0x180137b20`
- `0x1801504f0`

## import_xrefs

- `USER32!GetDoubleClickTime` at `0x1800249cb`
- `USER32!GetDoubleClickTime` at `0x1800249cb`
- `USER32!GetKeyState` at `0x1800247cf`
- `USER32!GetKeyState` at `0x1800247dd`
- `USER32!GetKeyState` at `0x1800247cf`
- `USER32!GetKeyState` at `0x1800247dd`
- `USER32!SetTimer` at `0x1800249de`
- `USER32!SetTimer` at `0x1800249de`
- `USER32!UpdateWindow` at `0x1800248bb`
- `USER32!UpdateWindow` at `0x180024909`
- `USER32!UpdateWindow` at `0x1800248bb`
- `USER32!UpdateWindow` at `0x180024909`
- `USER32!NotifyWinEvent` at `0x180024925`
- `USER32!NotifyWinEvent` at `0x180024943`
- `USER32!NotifyWinEvent` at `0x180024925`
- `USER32!NotifyWinEvent` at `0x180024943`

## pseudocode

```c
__int64 __fastcall TV_SelectItem(struct _TREE *a1, __int64 a2, struct _TREEITEM *a3, char a4, unsigned int a5)
{
  unsigned int v9; // r14d
  __int64 v10; // rsi
  __int64 v11; // rsi
  struct _TREEITEM *v12; // r8
  int v13; // r13d
  SHORT KeyState; // bp
  SHORT v15; // ax
  BOOL v16; // r15d
  struct _TREEITEM *v17; // rdx
  struct _TREEITEM *v18; // rbp
  struct _TREEITEM *i; // r15
  LONG v20; // r9d
  struct _TREEITEM *v21; // rax
  __int64 v22; // rax
  LONG v23; // r9d
  DWORD v24; // ecx
  UINT DoubleClickTime; // eax
  int v27; // ebp

  v9 = (unsigned int)TV_HasTransparentImage(a1, 0) != 0 ? 5 : 1;
  if ( !(unsigned int)ValidateTreeItem(a3, 1u) )
    return 0;
  v10 = a2 - 5;
  if ( v10 )
  {
    v11 = v10 - 3;
    if ( !v11 )
    {
      v21 = (struct _TREEITEM *)*((_QWORD *)a1 + 12);
      if ( a3 != v21 )
      {
        if ( v21 )
        {
          *((_WORD *)v21 + 26) &= ~8u;
          TV_InvalidateItem(a1, *((struct _TREEITEM **)a1 + 12), v9);
        }
        v22 = *((_QWORD *)a1 + 10);
        if ( v22 )
        {
          *(_WORD *)(v22 + 52) &= ~8u;
          TV_InvalidateItem(a1, *((struct _TREEITEM **)a1 + 10), v9);
        }
        if ( a3 )
        {
          *((_WORD *)a3 + 26) |= 8u;
          TV_InvalidateItem(a1, a3, v9);
        }
        *((_QWORD *)a1 + 12) = a3;
        if ( (a4 & 2) != 0 )
          UpdateWindow(*(HWND *)a1);
      }
      return 1;
    }
    if ( v11 == 1 )
    {
      v12 = (struct _TREEITEM *)*((_QWORD *)a1 + 10);
      if ( v12 != a3 )
      {
        v13 = a4 & 1;
        if ( (a4 & 1) != 0 && (*((_BYTE *)a1 + 500) & 2) == 0 && (unsigned int)TV_SendSelChange(a1, -450, v12, a3, a5) )
          return 0;
        KeyState = GetKeyState(16);
        v15 = GetKeyState(17);
        v16 = 0;
        if ( (*((_BYTE *)a1 + 500) & 2) != 0 )
        {
          if ( (v27 = KeyState & 0x8000, (a5 & 1) != 0) && (v27 || v15 < 0) || a5 && v27 )
            v16 = 1;
        }
        v17 = (struct _TREEITEM *)*((_QWORD *)a1 + 10);
        if ( v17 && !v16 )
        {
          TV_SetItemState(a1, v17, 0, 2u);
          TV_InvalidateItem(a1, *((struct _TREEITEM **)a1 + 10), v9);
        }
        v18 = (struct _TREEITEM *)*((_QWORD *)a1 + 10);
        *((_QWORD *)a1 + 10) = a3;
        if ( a3 )
        {
          if ( !v16 )
          {
            for ( i = (struct _TREEITEM *)*((_QWORD *)a1 + 11); i; i = (struct _TREEITEM *)*((_QWORD *)i + 3) )
            {
              TV_SetItemState(a1, i, 0, 2u);
              TV_InvalidateItem(a1, i, v9);
            }
          }
          TV_SetItemState(a1, a3, 2u, 2u);
          TV_ExpandParents(a1, a3, v13);
          TV_InvalidateItem(a1, a3, v9);
          if ( a5 == 1 )
          {
            DoubleClickTime = GetDoubleClickTime();
            SetTimer(*(HWND *)a1, 0x2Bu, DoubleClickTime, 0);
            *((_DWORD *)a1 + 16) |= 0x20u;
          }
          else if ( (*((_BYTE *)a1 + 64) & 0x10) != 0 )
          {
            TV_ScrollVertIntoView(a1, a3);
          }
          if ( (*((_BYTE *)a1 + 500) & 0x20) != 0 )
            TV_AutoScrollStart(a1, a3);
        }
        else
        {
          TV_InvalidateItem(a1, v18, v9);
        }
        if ( v13 && (*((_BYTE *)a1 + 500) & 2) == 0 )
          TV_SendSelChange(a1, -451, v18, a3, a5);
        if ( (*((_DWORD *)a1 + 4) & 0x400) != 0 && (a4 & 4) == 0 && a5 != 2 && v18 )
          TV_ExpandOnSelChange(a1, *((struct _TREEITEM **)a1 + 10), v18);
        if ( (a4 & 2) != 0 )
          UpdateWindow(*(HWND *)a1);
        if ( a3 )
          v20 = *((_DWORD *)a3 + 12);
        else
          v20 = 0;
        NotifyWinEvent(0x8005u, *(HWND *)a1, -4, v20);
        if ( a3 )
        {
          v23 = *((_DWORD *)a3 + 12);
          v24 = 32774;
        }
        else
        {
          if ( v18 )
            v23 = *((_DWORD *)v18 + 12);
          else
            v23 = 0;
          v24 = 32776;
        }
        NotifyWinEvent(v24, *(HWND *)a1, -4, v23);
      }
      return 1;
    }
  }
  else if ( a3 )
  {
    TV_EnsureVisible(a1, a3);
    if ( (*((_BYTE *)a1 + 64) & 2) != 0 )
      TV_SmoothSetTopItem(a1, *((_DWORD *)a3 + 15), 0);
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x18002473c  mov     [rsp+arg_18], r9d
0x180024741  push    rbx
0x180024742  push    rbp
0x180024743  push    rsi
0x180024744  push    rdi
0x180024745  push    r12
0x180024747  push    r13
0x180024749  push    r14
0x18002474b  push    r15
0x18002474d  sub     rsp, 38h
0x180024751  mov     rsi, rdx
0x180024754  mov     ebp, r9d
0x180024757  xor     edx, edx; int
0x180024759  mov     rdi, r8
0x18002475c  mov     rbx, rcx
0x18002475f  call    ?TV_HasTransparentImage@@YAHPEAU_TREE@@H@Z; TV_HasTransparentImage(_TREE *,int)
0x180024764  neg     eax
0x180024766  mov     edx, 1; unsigned int
0x18002476b  mov     rcx, rdi; struct _TREEITEM *
0x18002476e  sbb     r14d, r14d
0x180024771  and     r14d, 4
0x180024775  inc     r14d
0x180024778  call    ?ValidateTreeItem@@YAHPEAU_TREEITEM@@I@Z; ValidateTreeItem(_TREEITEM *,uint)
0x18002477d  test    eax, eax
0x18002477f  jz      loc_18002499C
0x180024785  sub     rsi, 5
0x180024789  jz      loc_180024AE7
0x18002478f  sub     rsi, 3
0x180024793  jz      loc_1800248CB
0x180024799  cmp     rsi, 1
0x18002479d  jnz     loc_18002499C
0x1800247a3  mov     r8, [rbx+50h]; struct _TREEITEM *
0x1800247a7  cmp     r8, rdi
0x1800247aa  jz      loc_180024949
0x1800247b0  mov     r12d, [rsp+78h+arg_20]
0x1800247b8  mov     r13d, ebp
0x1800247bb  mov     esi, 2
0x1800247c0  and     r13d, 1
0x1800247c4  jnz     loc_180024972
0x1800247ca  mov     ecx, 10h; nVirtKey
0x1800247cf  call    cs:__imp_GetKeyState
0x1800247d5  mov     ecx, 11h; nVirtKey
0x1800247da  movzx   ebp, ax
0x1800247dd  call    cs:__imp_GetKeyState
0x1800247e3  test    [rbx+1F4h], sil
0x1800247ea  jnz     loc_180024A05
0x1800247f0  xor     r15d, r15d
0x1800247f3  mov     rdx, [rbx+50h]; struct _TREEITEM *
0x1800247f7  test    rdx, rdx
0x1800247fa  jnz     loc_1800249A0
0x180024800  mov     rbp, [rbx+50h]
0x180024804  mov     [rbx+50h], rdi
0x180024808  test    rdi, rdi
0x18002480b  jz      loc_18002495F
0x180024811  test    r15d, r15d
0x180024814  jnz     short loc_180024823
0x180024816  mov     r15, [rbx+58h]
0x18002481a  test    r15, r15
0x18002481d  jnz     loc_180024A37
0x180024823  mov     r9d, esi; unsigned int
0x180024826  mov     r8d, esi; unsigned int
0x180024829  mov     rdx, rdi; struct _TREEITEM *
0x18002482c  mov     rcx, rbx; struct _TREE *
0x18002482f  call    ?TV_SetItemState@@YAIPEAU_TREE@@PEAU_TREEITEM@@II@Z; TV_SetItemState(_TREE *,_TREEITEM *,uint,uint)
0x180024834  mov     r8d, r13d; int
0x180024837  mov     rdx, rdi; struct _TREEITEM *
0x18002483a  mov     rcx, rbx; struct _TREE *
0x18002483d  call    ?TV_ExpandParents@@YAXPEAU_TREE@@PEAU_TREEITEM@@H@Z; TV_ExpandParents(_TREE *,_TREEITEM *,int)
0x180024842  mov     r8d, r14d; unsigned int
0x180024845  mov     rdx, rdi; struct _TREEITEM *
0x180024848  mov     rcx, rbx; struct _TREE *
0x18002484b  call    ?TV_InvalidateItem@@YAXPEAU_TREE@@PEAU_TREEITEM@@I@Z; TV_InvalidateItem(_TREE *,_TREEITEM *,uint)
0x180024850  cmp     r12d, 1
0x180024854  jz      loc_1800249CB
0x18002485a  test    byte ptr [rbx+40h], 10h
0x18002485e  jz      short loc_18002486B
0x180024860  mov     rdx, rdi; struct _TREEITEM *
0x180024863  mov     rcx, rbx; struct _TREE *
0x180024866  call    ?TV_ScrollVertIntoView@@YAHPEAU_TREE@@PEAU_TREEITEM@@@Z; TV_ScrollVertIntoView(_TREE *,_TREEITEM *)
0x18002486b  test    byte ptr [rbx+1F4h], 20h
0x180024872  jnz     loc_180024A5F
0x180024878  test    r13d, r13d
0x18002487b  jz      short loc_18002489E
0x18002487d  test    [rbx+1F4h], sil
0x180024884  jnz     short loc_18002489E
0x180024886  mov     r9, rdi; struct _TREEITEM *
0x180024889  mov     [rsp+78h+var_58], r12d; unsigned int
0x18002488e  mov     r8, rbp; struct _TREEITEM *
0x180024891  mov     edx, 0FFFFFE3Dh; int
0x180024896  mov     rcx, rbx; struct _TREE *
0x180024899  call    ?TV_SendSelChange@@YAHPEAU_TREE@@HPEAU_TREEITEM@@1I@Z; TV_SendSelChange(_TREE *,int,_TREEITEM *,_TREEITEM *,uint)
0x18002489e  test    dword ptr [rbx+10h], 400h
0x1800248a5  mov     r14d, [rsp+78h+arg_18]
0x1800248ad  jnz     loc_180024A6F
0x1800248b3  test    sil, r14b
0x1800248b6  jz      short loc_1800248C1
0x1800248b8  mov     rcx, [rbx]; hWnd
0x1800248bb  call    cs:__imp_UpdateWindow
0x1800248c1  test    rdi, rdi
0x1800248c4  jnz     short loc_180024911
0x1800248c6  xor     r9d, r9d
0x1800248c9  jmp     short loc_180024915
0x1800248cb  mov     rax, [rbx+60h]
0x1800248cf  cmp     rdi, rax
0x1800248d2  jz      short loc_180024949
0x1800248d4  mov     esi, 0FFF7h
0x1800248d9  test    rax, rax
0x1800248dc  jnz     loc_1800249ED
0x1800248e2  mov     rax, [rbx+50h]
0x1800248e6  test    rax, rax
0x1800248e9  jnz     loc_180024AB7
0x1800248ef  test    rdi, rdi
0x1800248f2  jnz     loc_180024ACF
0x1800248f8  mov     esi, 2
0x1800248fd  mov     [rbx+60h], rdi
0x180024901  test    sil, bpl
0x180024904  jz      short loc_180024949
0x180024906  mov     rcx, [rbx]; hWnd
0x180024909  call    cs:__imp_UpdateWindow
0x18002490f  jmp     short loc_180024949
0x180024911  mov     r9d, [rdi+30h]; idChild
0x180024915  mov     rdx, [rbx]; hwnd
0x180024918  mov     esi, 0FFFFFFFCh
0x18002491d  mov     r8d, esi; idObject
0x180024920  mov     ecx, 8005h; event
0x180024925  call    cs:__imp_NotifyWinEvent
0x18002492b  test    rdi, rdi
0x18002492e  jz      loc_180024A9F
0x180024934  mov     r9d, [rdi+30h]; idChild
0x180024938  mov     ecx, 8006h; event
0x18002493d  mov     rdx, [rbx]; hwnd
0x180024940  mov     r8d, esi; idObject
0x180024943  call    cs:__imp_NotifyWinEvent
0x180024949  mov     eax, 1
0x18002494e  add     rsp, 38h
0x180024952  pop     r15
0x180024954  pop     r14
0x180024956  pop     r13
0x180024958  pop     r12
0x18002495a  pop     rdi
0x18002495b  pop     rsi
0x18002495c  pop     rbp
0x18002495d  pop     rbx
0x18002495e  retn
0x18002495f  mov     r8d, r14d; unsigned int
0x180024962  mov     rdx, rbp; struct _TREEITEM *
0x180024965  mov     rcx, rbx; struct _TREE *
0x180024968  call    ?TV_InvalidateItem@@YAXPEAU_TREE@@PEAU_TREEITEM@@I@Z; TV_InvalidateItem(_TREE *,_TREEITEM *,uint)
0x18002496d  jmp     loc_180024878
0x180024972  test    [rbx+1F4h], sil
0x180024979  jnz     loc_1800247CA
0x18002497f  mov     r9, rdi; struct _TREEITEM *
0x180024982  mov     [rsp+78h+var_58], r12d; unsigned int
0x180024987  mov     edx, 0FFFFFE3Eh; int
0x18002498c  mov     rcx, rbx; struct _TREE *
0x18002498f  call    ?TV_SendSelChange@@YAHPEAU_TREE@@HPEAU_TREEITEM@@1I@Z; TV_SendSelChange(_TREE *,int,_TREEITEM *,_TREEITEM *,uint)
0x180024994  test    eax, eax
0x180024996  jz      loc_1800247CA
0x18002499c  xor     eax, eax
0x18002499e  jmp     short loc_18002494E
0x1800249a0  test    r15d, r15d
0x1800249a3  jnz     loc_180024800
0x1800249a9  mov     r9d, esi; unsigned int
0x1800249ac  xor     r8d, r8d; unsigned int
0x1800249af  mov     rcx, rbx; struct _TREE *
0x1800249b2  call    ?TV_SetItemState@@YAIPEAU_TREE@@PEAU_TREEITEM@@II@Z; TV_SetItemState(_TREE *,_TREEITEM *,uint,uint)
0x1800249b7  mov     rdx, [rbx+50h]; struct _TREEITEM *
0x1800249bb  mov     r8d, r14d; unsigned int
0x1800249be  mov     rcx, rbx; struct _TREE *
0x1800249c1  call    ?TV_InvalidateItem@@YAXPEAU_TREE@@PEAU_TREEITEM@@I@Z; TV_InvalidateItem(_TREE *,_TREEITEM *,uint)
0x1800249c6  jmp     loc_180024800
0x1800249cb  call    cs:__imp_GetDoubleClickTime
0x1800249d1  mov     rcx, [rbx]; hWnd
0x1800249d4  xor     r9d, r9d; lpTimerFunc
0x1800249d7  mov     r8d, eax; uElapse
0x1800249da  lea     edx, [r9+2Bh]; nIDEvent
0x1800249de  call    cs:__imp_SetTimer
0x1800249e4  or      dword ptr [rbx+40h], 20h
0x1800249e8  jmp     loc_18002486B
0x1800249ed  and     [rax+34h], si
0x1800249f1  mov     r8d, r14d; unsigned int
0x1800249f4  mov     rdx, [rbx+60h]; struct _TREEITEM *
0x1800249f8  mov     rcx, rbx; struct _TREE *
0x1800249fb  call    ?TV_InvalidateItem@@YAXPEAU_TREE@@PEAU_TREEITEM@@I@Z; TV_InvalidateItem(_TREE *,_TREEITEM *,uint)
0x180024a00  jmp     loc_1800248E2
0x180024a05  mov     ecx, 8000h
0x180024a0a  and     ebp, ecx
0x180024a0c  test    r12b, 1
0x180024a10  jz      short loc_180024A1B
0x180024a12  test    ebp, ebp
0x180024a14  jnz     short loc_180024A2C
0x180024a16  test    cx, ax
0x180024a19  jnz     short loc_180024A2C
0x180024a1b  test    r12d, r12d
0x180024a1e  jz      loc_1800247F0
0x180024a24  test    ebp, ebp
0x180024a26  jz      loc_1800247F0
0x180024a2c  mov     r15d, 1
0x180024a32  jmp     loc_1800247F3
0x180024a37  mov     r9d, esi; unsigned int
0x180024a3a  xor     r8d, r8d; unsigned int
0x180024a3d  mov     rdx, r15; struct _TREEITEM *
0x180024a40  mov     rcx, rbx; struct _TREE *
0x180024a43  call    ?TV_SetItemState@@YAIPEAU_TREE@@PEAU_TREEITEM@@II@Z; TV_SetItemState(_TREE *,_TREEITEM *,uint,uint)
0x180024a48  mov     r8d, r14d; unsigned int
0x180024a4b  mov     rdx, r15; struct _TREEITEM *
0x180024a4e  mov     rcx, rbx; struct _TREE *
0x180024a51  call    ?TV_InvalidateItem@@YAXPEAU_TREE@@PEAU_TREEITEM@@I@Z; TV_InvalidateItem(_TREE *,_TREEITEM *,uint)
0x180024a56  mov     r15, [r15+18h]
0x180024a5a  jmp     loc_18002481A
0x180024a5f  mov     rdx, rdi; struct _TREEITEM *
0x180024a62  mov     rcx, rbx; struct _TREE *
0x180024a65  call    ?TV_AutoScrollStart@@YAXPEAU_TREE@@PEAU_TREEITEM@@@Z; TV_AutoScrollStart(_TREE *,_TREEITEM *)
0x180024a6a  jmp     loc_180024878
0x180024a6f  test    r14b, 4
0x180024a73  jnz     loc_1800248B3
0x180024a79  cmp     r12d, esi
0x180024a7c  jz      loc_1800248B3
0x180024a82  test    rbp, rbp
0x180024a85  jz      loc_1800248B3
0x180024a8b  mov     rdx, [rbx+50h]; struct _TREEITEM *
0x180024a8f  mov     r8, rbp; struct _TREEITEM *
0x180024a92  mov     rcx, rbx; struct _TREE *
0x180024a95  call    ?TV_ExpandOnSelChange@@YAXPEAU_TREE@@PEAU_TREEITEM@@1@Z; TV_ExpandOnSelChange(_TREE *,_TREEITEM *,_TREEITEM *)
0x180024a9a  jmp     loc_1800248B3
0x180024a9f  test    rbp, rbp
0x180024aa2  jz      short loc_180024AAA
0x180024aa4  mov     r9d, [rbp+30h]
0x180024aa8  jmp     short loc_180024AAD
0x180024aaa  xor     r9d, r9d
0x180024aad  mov     ecx, 8008h
0x180024ab2  jmp     loc_18002493D
0x180024ab7  and     [rax+34h], si
0x180024abb  mov     r8d, r14d; unsigned int
0x180024abe  mov     rdx, [rbx+50h]; struct _TREEITEM *
0x180024ac2  mov     rcx, rbx; struct _TREE *
0x180024ac5  call    ?TV_InvalidateItem@@YAXPEAU_TREE@@PEAU_TREEITEM@@I@Z; TV_InvalidateItem(_TREE *,_TREEITEM *,uint)
0x180024aca  jmp     loc_1800248EF
0x180024acf  or      word ptr [rdi+34h], 8
0x180024ad4  mov     r8d, r14d; unsigned int
0x180024ad7  mov     rdx, rdi; struct _TREEITEM *
0x180024ada  mov     rcx, rbx; struct _TREE *
0x180024add  call    ?TV_InvalidateItem@@YAXPEAU_TREE@@PEAU_TREEITEM@@I@Z; TV_InvalidateItem(_TREE *,_TREEITEM *,uint)
0x180024ae2  jmp     loc_1800248F8
0x180024ae7  test    rdi, rdi
0x180024aea  jz      loc_18002499C
0x180024af0  mov     rdx, rdi; struct _TREEITEM *
0x180024af3  mov     rcx, rbx; struct _TREE *
0x180024af6  call    ?TV_EnsureVisible@@YAHPEAU_TREE@@PEAU_TREEITEM@@@Z; TV_EnsureVisible(_TREE *,_TREEITEM *)
0x180024afb  mov     esi, 2
0x180024b00  test    [rbx+40h], sil
0x180024b04  jz      loc_180024949
0x180024b0a  mov     edx, [rdi+3Ch]; unsigned int
0x180024b0d  xor     r8d, r8d; unsigned int
0x180024b10  mov     rcx, rbx; struct _TREE *
0x180024b13  call    ?TV_SmoothSetTopItem@@YAHPEAU_TREE@@II@Z; TV_SmoothSetTopItem(_TREE *,uint,uint)
0x180024b18  jmp     loc_180024949
```
