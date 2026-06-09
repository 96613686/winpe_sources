# _PaginateControls(HWND__ *,uint,ushort const *,uint *,uint,uint)

- ea: `0x140045eb4`
- end: `0x14004605a`
- name: `?_PaginateControls@@YAXPEAUHWND__@@IPEBGPEAIII@Z`
- size: `422`
- prototype: `void __fastcall(HWND, unsigned int nIDDlgItem, LPCWSTR lpchText, unsigned int *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140045074`

## callees

- `0x14000b7d8`
- `0x14000cfb0`
- `0x140045eb4`
- `0x140046060`
- `0x140046148`
- `0x140111220`

## import_xrefs

- `USER32!DrawTextW` at `0x140045f65`
- `USER32!DrawTextW` at `0x140045f65`
- `USER32!GetClientRect` at `0x140045f1a`
- `USER32!GetClientRect` at `0x140045f1a`
- `USER32!GetDlgItem` at `0x140045efe`
- `USER32!GetDlgItem` at `0x140045efe`
- `USER32!SendMessageW` at `0x140045f34`
- `USER32!SendMessageW` at `0x140045f34`
- `GDI32!CreateCompatibleDC` at `0x140045ee7`
- `GDI32!CreateCompatibleDC` at `0x140045ee7`
- `GDI32!SelectObject` at `0x140045f45`
- `GDI32!SelectObject` at `0x140045f7e`
- `GDI32!SelectObject` at `0x140045f45`
- `GDI32!SelectObject` at `0x140045f7e`
- `GDI32!DeleteObject` at `0x140045f87`
- `GDI32!DeleteObject` at `0x140045f87`

## pseudocode

```c
void __fastcall _PaginateControls(HWND a1, int nIDDlgItem, LPCWSTR lpchText, unsigned int *a4, unsigned int a5)
{
  HDC CompatibleDC; // rdi
  HWND DlgItem; // rax
  HWND v11; // rbx
  HGDIOBJ v12; // rsi
  int v13; // ebp
  void *v14; // rax
  int v15; // ebx
  int v16; // edx
  PVOID *v17; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v19; // eax
  int v20; // ebx
  unsigned int v21; // edx
  int v22; // r8d
  struct tagRECT Rect; // [rsp+30h] [rbp-58h] BYREF

  Rect = 0;
  CompatibleDC = CreateCompatibleDC(0);
  if ( CompatibleDC )
  {
    DlgItem = GetDlgItem(a1, nIDDlgItem);
    v11 = DlgItem;
    if ( DlgItem )
    {
      v12 = 0;
      GetClientRect(DlgItem, &Rect);
      v13 = Rect.bottom - Rect.top;
      v14 = (void *)SendMessageW(v11, 0x31u, 0, 0);
      if ( v14 )
        v12 = SelectObject(CompatibleDC, v14);
      DrawTextW(CompatibleDC, lpchText, -1, &Rect, 0x410u);
      v15 = Rect.bottom - Rect.top;
      if ( v12 )
        SelectObject(CompatibleDC, v12);
      DeleteObject(CompatibleDC);
      v17 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            &WPP_b2859179a69931166002029bec6a3d1f_Traceguids,
            CurrentThreadActivityIdPrefix,
            v15);
          v17 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 1) != 0 && *((_BYTE *)v17 + 25) >= 5u )
        {
          v19 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_b2859179a69931166002029bec6a3d1f_Traceguids, v19, v13);
        }
      }
      if ( v15 <= v13 )
      {
        v20 = v15 - v13;
        _RepositionControls(a1, v16, v20, a4, a5);
        _ResizeComponent(a1, v21, v22, v20);
      }
    }
  }
}

```

## disassembly

```asm
0x140045eb4  push    rbx
0x140045eb6  push    rbp
0x140045eb7  push    rsi
0x140045eb8  push    rdi
0x140045eb9  push    r12
0x140045ebb  push    r14
0x140045ebd  push    r15
0x140045ebf  sub     rsp, 50h
0x140045ec3  mov     rax, cs:__security_cookie
0x140045eca  xor     rax, rsp
0x140045ecd  mov     [rsp+88h+var_48], rax
0x140045ed2  mov     r14, rcx
0x140045ed5  xorps   xmm0, xmm0
0x140045ed8  xor     ecx, ecx; hdc
0x140045eda  mov     r12, r9
0x140045edd  movups  xmmword ptr [rsp+88h+Rect.left], xmm0
0x140045ee2  mov     r15, r8
0x140045ee5  mov     ebx, edx
0x140045ee7  call    cs:__imp_CreateCompatibleDC
0x140045eed  mov     rdi, rax
0x140045ef0  test    rax, rax
0x140045ef3  jz      loc_14004603E
0x140045ef9  mov     edx, ebx; nIDDlgItem
0x140045efb  mov     rcx, r14; hDlg
0x140045efe  call    cs:__imp_GetDlgItem
0x140045f04  mov     rbx, rax
0x140045f07  test    rax, rax
0x140045f0a  jz      loc_14004603E
0x140045f10  lea     rdx, [rsp+88h+Rect]; lpRect
0x140045f15  mov     rcx, rax; hWnd
0x140045f18  xor     esi, esi
0x140045f1a  call    cs:__imp_GetClientRect
0x140045f20  mov     ebp, [rsp+88h+Rect.bottom]
0x140045f24  lea     edx, [rsi+31h]; Msg
0x140045f27  sub     ebp, [rsp+88h+Rect.top]
0x140045f2b  xor     r9d, r9d; lParam
0x140045f2e  xor     r8d, r8d; wParam
0x140045f31  mov     rcx, rbx; hWnd
0x140045f34  call    cs:__imp_SendMessageW
0x140045f3a  test    rax, rax
0x140045f3d  jz      short loc_140045F4E
0x140045f3f  mov     rdx, rax; h
0x140045f42  mov     rcx, rdi; hdc
0x140045f45  call    cs:__imp_SelectObject
0x140045f4b  mov     rsi, rax
0x140045f4e  lea     r9, [rsp+88h+Rect]; lprc
0x140045f53  mov     [rsp+88h+format], 410h; format
0x140045f5b  or      r8d, 0FFFFFFFFh; cchText
0x140045f5f  mov     rdx, r15; lpchText
0x140045f62  mov     rcx, rdi; hdc
0x140045f65  call    cs:__imp_DrawTextW
0x140045f6b  mov     ebx, [rsp+88h+Rect.bottom]
0x140045f6f  sub     ebx, [rsp+88h+Rect.top]
0x140045f73  test    rsi, rsi
0x140045f76  jz      short loc_140045F84
0x140045f78  mov     rdx, rsi; h
0x140045f7b  mov     rcx, rdi; hdc
0x140045f7e  call    cs:__imp_SelectObject
0x140045f84  mov     rcx, rdi; ho
0x140045f87  call    cs:__imp_DeleteObject
0x140045f8d  mov     rax, cs:WPP_GLOBAL_Control
0x140045f94  lea     rdi, WPP_GLOBAL_Control
0x140045f9b  cmp     rax, rdi
0x140045f9e  jz      short loc_140046014
0x140045fa0  test    byte ptr [rax+1Ch], 1
0x140045fa4  jz      short loc_140045FDB
0x140045fa6  cmp     byte ptr [rax+19h], 5
0x140045faa  jb      short loc_140045FDB
0x140045fac  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140045fb1  mov     rcx, cs:WPP_GLOBAL_Control
0x140045fb8  lea     r8, WPP_b2859179a69931166002029bec6a3d1f_Traceguids
0x140045fbf  mov     edx, 0Fh
0x140045fc4  mov     [rsp+88h+format], ebx
0x140045fc8  mov     r9d, eax
0x140045fcb  mov     rcx, [rcx+10h]
0x140045fcf  call    WPP_SF_Dd
0x140045fd4  mov     rax, cs:WPP_GLOBAL_Control
0x140045fdb  cmp     rax, rdi
0x140045fde  jz      short loc_140046014
0x140045fe0  test    byte ptr [rax+1Ch], 1
0x140045fe4  jz      short loc_140046014
0x140045fe6  cmp     byte ptr [rax+19h], 5
0x140045fea  jb      short loc_140046014
0x140045fec  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140045ff1  mov     rcx, cs:WPP_GLOBAL_Control
0x140045ff8  lea     r8, WPP_b2859179a69931166002029bec6a3d1f_Traceguids
0x140045fff  mov     edx, 10h
0x140046004  mov     [rsp+88h+format], ebp
0x140046008  mov     r9d, eax
0x14004600b  mov     rcx, [rcx+10h]
0x14004600f  call    WPP_SF_Dd
0x140046014  cmp     ebx, ebp
0x140046016  jg      short loc_14004603E
0x140046018  mov     eax, [rsp+88h+arg_20]
0x14004601f  sub     ebx, ebp
0x140046021  mov     r8d, ebx; int
0x140046024  mov     [rsp+88h+format], eax; int
0x140046028  mov     r9, r12; unsigned int *
0x14004602b  mov     rcx, r14; hWndTo
0x14004602e  call    ?_RepositionControls@@YAXPEAUHWND__@@HHPEAIH@Z; _RepositionControls(HWND__ *,int,int,uint *,int)
0x140046033  mov     r9d, ebx; int
0x140046036  mov     rcx, r14; HWND
0x140046039  call    ?_ResizeComponent@@YAHPEAUHWND__@@IHH@Z; _ResizeComponent(HWND__ *,uint,int,int)
0x14004603e  mov     rcx, [rsp+88h+var_48]
0x140046043  xor     rcx, rsp; StackCookie
0x140046046  call    __security_check_cookie
0x14004604b  add     rsp, 50h
0x14004604f  pop     r15
0x140046051  pop     r14
0x140046053  pop     r12
0x140046055  pop     rdi
0x140046056  pop     rsi
0x140046057  pop     rbp
0x140046058  pop     rbx
0x140046059  retn
```
