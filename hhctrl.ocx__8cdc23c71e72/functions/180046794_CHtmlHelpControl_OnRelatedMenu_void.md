# CHtmlHelpControl::OnRelatedMenu(void)

- ea: `0x180046794`
- end: `0x180046931`
- name: `?OnRelatedMenu@CHtmlHelpControl@@QEAAXXZ`
- size: `413`
- prototype: `void __fastcall(CHtmlHelpControl *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800450a0`

## callees

- `0x180030704`
- `0x180046794`
- `0x180064acc`
- `0x180075c90`

## import_xrefs

- `USER32!TrackPopupMenu` at `0x1800468c4`
- `USER32!TrackPopupMenu` at `0x1800468c4`
- `USER32!CreatePopupMenu` at `0x18004683a`
- `USER32!CreatePopupMenu` at `0x18004683a`
- `USER32!GetWindowLongA` at `0x1800467d9`
- `USER32!GetWindowLongA` at `0x1800467d9`
- `USER32!GetWindowRect` at `0x1800467f5`
- `USER32!GetWindowRect` at `0x1800467f5`
- `USER32!DestroyMenu` at `0x180046915`
- `USER32!DestroyMenu` at `0x180046915`
- `USER32!GetCursorPos` at `0x1800467bd`
- `USER32!GetCursorPos` at `0x1800467bd`
- `USER32!GetFocus` at `0x1800467c3`
- `USER32!GetFocus` at `0x1800467c3`

## pseudocode

```c
void __fastcall CHtmlHelpControl::OnRelatedMenu(CHtmlHelpControl *this)
{
  HWND Focus; // rax
  HWND v3; // rsi
  HMENU PopupMenu; // rdi
  __int64 v5; // rdx
  signed int v6; // ebp
  HWND hWnd; // rax
  BOOL v8; // eax
  struct tagPOINT Point; // [rsp+40h] [rbp-48h] BYREF
  struct tagRECT Rect; // [rsp+48h] [rbp-40h] BYREF

  Point = 0;
  GetCursorPos(&Point);
  Focus = GetFocus();
  v3 = Focus;
  if ( Focus )
  {
    if ( (GetWindowLongA(Focus, -16) & 0x4000) != 0 )
    {
      Rect = 0;
      if ( GetWindowRect(v3, &Rect) )
      {
        Point.y = Rect.top + (Rect.bottom - Rect.top) / 2;
        Point.x = Rect.left + 2 * ((Rect.bottom - Rect.top) / 3);
      }
    }
  }
  PopupMenu = CreatePopupMenu();
  if ( PopupMenu )
  {
    v5 = *((_QWORD *)this + 67);
    if ( *(_DWORD *)(v5 + 32) - 1 >= 1 )
    {
      v6 = 1;
      do
      {
        HxAppendMenu(PopupMenu, v5, v6, *(const char **)(*(_QWORD *)(*(_QWORD *)(v5 + 16) + 8LL * v6) + 8LL));
        v5 = *((_QWORD *)this + 67);
        ++v6;
      }
      while ( v6 <= *(_DWORD *)(v5 + 32) - 1 );
    }
    hWnd = (HWND)*((_QWORD *)this + 28);
    if ( !hWnd )
      hWnd = v3;
    v8 = TrackPopupMenu(PopupMenu, 0x182u, Point.x, Point.y, 0, hWnd, 0);
    if ( v8 )
      JumpToUrl(
        *((struct IUnknown **)this + 1),
        *((HWND *)this + 29),
        *(struct _tagSiteMapEntry **)(*(_QWORD *)(*((_QWORD *)this + 67) + 16LL) + 8LL * v8),
        *((struct CInfoType **)this + 68),
        *((PCSTR **)this + 67),
        0,
        0,
        this);
    DestroyMenu(PopupMenu);
  }
}

```

## disassembly

```asm
0x180046794  push    rbx
0x180046796  push    rbp
0x180046797  push    rsi
0x180046798  push    rdi
0x180046799  sub     rsp, 68h
0x18004679d  mov     rax, cs:__security_cookie
0x1800467a4  xor     rax, rsp
0x1800467a7  mov     [rsp+88h+var_30], rax
0x1800467ac  mov     rbx, rcx
0x1800467af  mov     qword ptr [rsp+88h+Point.x], 0
0x1800467b8  lea     rcx, [rsp+88h+Point]; lpPoint
0x1800467bd  call    cs:__imp_GetCursorPos
0x1800467c3  call    cs:__imp_GetFocus
0x1800467c9  mov     rsi, rax
0x1800467cc  test    rax, rax
0x1800467cf  jz      short loc_18004683A
0x1800467d1  mov     edx, 0FFFFFFF0h; nIndex
0x1800467d6  mov     rcx, rax; hWnd
0x1800467d9  call    cs:__imp_GetWindowLongA
0x1800467df  bt      eax, 0Eh
0x1800467e3  jnb     short loc_18004683A
0x1800467e5  xorps   xmm0, xmm0
0x1800467e8  lea     rdx, [rsp+88h+Rect]; lpRect
0x1800467ed  mov     rcx, rsi; hWnd
0x1800467f0  movups  xmmword ptr [rsp+88h+Rect.left], xmm0
0x1800467f5  call    cs:__imp_GetWindowRect
0x1800467fb  test    eax, eax
0x1800467fd  jz      short loc_18004683A
0x1800467ff  mov     ecx, [rsp+88h+Rect.top]
0x180046803  mov     r9d, 2
0x180046809  mov     r8d, [rsp+88h+Rect.bottom]
0x18004680e  mov     eax, r8d
0x180046811  sub     eax, ecx
0x180046813  sub     r8d, ecx
0x180046816  cdq
0x180046817  idiv    r9d
0x18004681a  add     eax, ecx
0x18004681c  mov     [rsp+88h+Point.y], eax
0x180046820  mov     eax, 55555556h
0x180046825  imul    r8d
0x180046828  mov     eax, edx
0x18004682a  shr     eax, 1Fh
0x18004682d  add     edx, eax
0x18004682f  mov     eax, [rsp+88h+Rect.left]
0x180046833  lea     ecx, [rax+rdx*2]
0x180046836  mov     [rsp+88h+Point.x], ecx
0x18004683a  call    cs:__imp_CreatePopupMenu
0x180046840  mov     rdi, rax
0x180046843  test    rax, rax
0x180046846  jz      loc_18004691B
0x18004684c  mov     rdx, [rbx+218h]; unsigned int
0x180046853  mov     ecx, [rdx+20h]
0x180046856  dec     ecx
0x180046858  cmp     ecx, 1
0x18004685b  jl      short loc_18004688E
0x18004685d  mov     ebp, 1
0x180046862  mov     rax, [rdx+10h]
0x180046866  mov     r8d, ebp; unsigned int
0x180046869  movsxd  r9, ebp
0x18004686c  mov     rcx, rdi; hMenu
0x18004686f  mov     r9, [rax+r9*8]
0x180046873  mov     r9, [r9+8]; char *
0x180046877  call    ?HxAppendMenu@@YAHPEAUHMENU__@@IIPEBD@Z; HxAppendMenu(HMENU__ *,uint,uint,char const *)
0x18004687c  mov     rdx, [rbx+218h]
0x180046883  inc     ebp
0x180046885  mov     eax, [rdx+20h]
0x180046888  dec     eax
0x18004688a  cmp     ebp, eax
0x18004688c  jle     short loc_180046862
0x18004688e  mov     rax, [rbx+0E0h]
0x180046895  mov     edx, 182h; uFlags
0x18004689a  mov     r9d, [rsp+88h+Point.y]; y
0x18004689f  test    rax, rax
0x1800468a2  mov     r8d, [rsp+88h+Point.x]; x
0x1800468a7  mov     rcx, rdi; hMenu
0x1800468aa  cmovz   rax, rsi
0x1800468ae  mov     [rsp+88h+prcRect], 0; prcRect
0x1800468b7  mov     [rsp+88h+hWnd], rax; hWnd
0x1800468bc  mov     [rsp+88h+nReserved], 0; nReserved
0x1800468c4  call    cs:__imp_TrackPopupMenu
0x1800468ca  test    eax, eax
0x1800468cc  jz      short loc_180046912
0x1800468ce  mov     rdx, [rbx+218h]
0x1800468d5  mov     r9, [rbx+220h]; struct CInfoType *
0x1800468dc  mov     rcx, [rbx+8]; struct IUnknown *
0x1800468e0  mov     [rsp+88h+var_50], rbx; struct CHtmlHelpControl *
0x1800468e5  mov     r8, [rdx+10h]
0x1800468e9  cdqe
0x1800468eb  mov     [rsp+88h+prcRect], 0; struct IWebBrowserAppImpl *
0x1800468f4  mov     [rsp+88h+hWnd], 0; struct SITE_ENTRY_URL *
0x1800468fd  mov     qword ptr [rsp+88h+nReserved], rdx; struct CSiteMap *
0x180046902  mov     r8, [r8+rax*8]; struct _tagSiteMapEntry *
0x180046906  mov     rdx, [rbx+0E8h]; HWND
0x18004690d  call    ?JumpToUrl@@YAPEAUHWND__@@PEAUIUnknown@@PEAU1@PEAU_tagSiteMapEntry@@PEAVCInfoType@@PEAVCSiteMap@@PEAUSITE_ENTRY_URL@@PEAVIWebBrowserAppImpl@@PEAVCHtmlHelpControl@@@Z; JumpToUrl(IUnknown *,HWND__ *,_tagSiteMapEntry *,CInfoType *,CSiteMap *,SITE_ENTRY_URL *,IWebBrowserAppImpl *,CHtmlHelpControl *)
0x180046912  mov     rcx, rdi; hMenu
0x180046915  call    cs:__imp_DestroyMenu
0x18004691b  mov     rcx, [rsp+88h+var_30]
0x180046920  xor     rcx, rsp; StackCookie
0x180046923  call    __security_check_cookie
0x180046928  add     rsp, 68h
0x18004692c  pop     rdi
0x18004692d  pop     rsi
0x18004692e  pop     rbp
0x18004692f  pop     rbx
0x180046930  retn
```
