# CToc::OnSiteMapTVMsg(tagNMTREEVIEWA *)

- ea: `0x18001bc88`
- end: `0x18001c3c6`
- name: `?OnSiteMapTVMsg@CToc@@QEAA_JPEAUtagNMTREEVIEWA@@@Z`
- size: `1854`
- prototype: `__int64 __fastcall(CToc *__hidden this, struct tagNMTREEVIEWA *)`
- caller_count: `2`
- callee_count: `23`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001b4e0`
- `0x180033700`

## callees

- `0x180001728`
- `0x180011104`
- `0x180012cd0`
- `0x180012f60`
- `0x180013174`
- `0x18001341c`
- `0x1800137b0`
- `0x18001969c`
- `0x18001b428`
- `0x18001bc88`
- `0x18001c904`
- `0x18001c974`
- `0x18001d270`
- `0x18002e344`
- `0x18002fef8`
- `0x180030704`
- `0x180033118`
- `0x1800559d0`
- `0x180064acc`
- `0x180067798`
- `0x18006a480`
- `0x180075c42`
- `0x180078010`

## import_xrefs

- `USER32!ScreenToClient` at `0x18001be9c`
- `USER32!ScreenToClient` at `0x18001c0d3`
- `USER32!ScreenToClient` at `0x18001be9c`
- `USER32!ScreenToClient` at `0x18001c0d3`
- `USER32!AppendMenuW` at `0x18001c15a`
- `USER32!AppendMenuW` at `0x18001c178`
- `USER32!AppendMenuW` at `0x18001c1ab`
- `USER32!AppendMenuW` at `0x18001c2e9`
- `USER32!AppendMenuW` at `0x18001c35e`
- `USER32!AppendMenuW` at `0x18001c15a`
- `USER32!AppendMenuW` at `0x18001c178`
- `USER32!AppendMenuW` at `0x18001c1ab`
- `USER32!AppendMenuW` at `0x18001c2e9`
- `USER32!AppendMenuW` at `0x18001c35e`
- `USER32!TrackPopupMenu` at `0x18001c38e`
- `USER32!TrackPopupMenu` at `0x18001c38e`
- `USER32!AppendMenuA` at `0x18001c315`
- `USER32!AppendMenuA` at `0x18001c315`
- `USER32!GetKeyState` at `0x18001bd50`
- `USER32!GetKeyState` at `0x18001bd50`
- `USER32!CreatePopupMenu` at `0x18001c124`
- `USER32!CreatePopupMenu` at `0x18001c124`
- `USER32!SendMessageA` at `0x18001beb5`
- `USER32!SendMessageA` at `0x18001bf1c`
- `USER32!SendMessageA` at `0x18001bf70`
- `USER32!SendMessageA` at `0x18001c057`
- `USER32!SendMessageA` at `0x18001c076`
- `USER32!SendMessageA` at `0x18001c0ec`
- `USER32!SendMessageA` at `0x18001c10d`
- `USER32!SendMessageA` at `0x18001beb5`
- `USER32!SendMessageA` at `0x18001bf1c`
- `USER32!SendMessageA` at `0x18001bf70`
- `USER32!SendMessageA` at `0x18001c057`
- `USER32!SendMessageA` at `0x18001c076`
- `USER32!SendMessageA` at `0x18001c0ec`
- `USER32!SendMessageA` at `0x18001c10d`
- `USER32!DestroyMenu` at `0x18001c397`
- `USER32!DestroyMenu` at `0x18001c397`
- `USER32!ClientToScreen` at `0x18001c11e`
- `USER32!ClientToScreen` at `0x18001c11e`
- `USER32!GetCursorPos` at `0x18001be8b`
- `USER32!GetCursorPos` at `0x18001c0c2`
- `USER32!GetCursorPos` at `0x18001be8b`
- `USER32!GetCursorPos` at `0x18001c0c2`
- `USER32!PostMessageA` at `0x18001bf40`
- `USER32!PostMessageA` at `0x18001bf40`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CToc::OnSiteMapTVMsg(CToc *this, struct tagNMTVCUSTOMDRAW *a2)
{
  UINT code; // eax
  unsigned __int64 dwItemSpec_low; // rbx
  const unsigned __int16 *StringResourceW; // rax
  struct _tagSiteMapEntry *v7; // r10
  UINT v8; // eax
  unsigned __int8 v9; // al
  int v10; // edx
  struct _TREEITEM *hItem; // r8
  LRESULT v12; // rbx
  HWND MessageParent; // rax
  __int64 v14; // r14
  CHtmlHelpControl *v15; // rcx
  __int64 v17; // rcx
  HWND v18; // rcx
  char v19; // cl
  unsigned __int8 ImageNumber; // al
  const unsigned int *v21; // rdx
  HMENU PopupMenu; // rsi
  unsigned int v23; // r8d
  const WCHAR *v24; // rax
  const WCHAR *v25; // rax
  __int64 v26; // rax
  const WCHAR *v27; // rax
  __int64 v28; // rax
  __int64 v29; // rcx
  CInfoType *v30; // rax
  CInfoType *v31; // rax
  CInfoType *v32; // rax
  CInfoType *v33; // rax
  CInfoType *v34; // rcx
  __int64 v35; // rax
  const WCHAR *v36; // rax
  HWND v37; // rax
  const char *v38; // rax
  unsigned int v39; // edx
  HHUrlSecurityManager::InternalSecurityManager *v40; // rcx
  const WCHAR *v41; // rax
  HWND hWnd; // rax
  LPARAM v43[2]; // [rsp+40h] [rbp-29h] BYREF
  LPARAM v44; // [rsp+50h] [rbp-19h]
  struct tagPOINT Point[2]; // [rsp+58h] [rbp-11h] BYREF
  struct _TREEITEM *v46; // [rsp+68h] [rbp-1h]
  struct tagTVITEMW lParam; // [rsp+70h] [rbp+7h] BYREF

  *(_OWORD *)v43 = 0;
  v44 = 0;
  code = a2->nmcd.hdr.code;
  if ( code > 0xFFFFFE6F )
  {
    if ( code == -12 )
      return CToc::OnCustomDraw(this, a2);
    if ( code != -5 )
    {
      if ( code != -4 && code != -3 )
      {
        if ( code == -2 && !*((_DWORD *)this + 102) )
        {
          *(_OWORD *)&Point[0].x = 0;
          v46 = 0;
          GetCursorPos(Point);
          ScreenToClient(*((HWND *)this + 53), Point);
          SendMessageA(*((HWND *)this + 53), 0x1111u, 0, (LPARAM)Point);
          if ( (Point[1].x & 0x10) == 0 )
          {
            *(_QWORD *)&lParam.mask = 0;
            memset(&lParam.state, 0, 40);
            lParam.hItem = v46;
            if ( v46 )
            {
              *((_QWORD *)this + 50) = v46;
              lParam.mask = 4;
              W_TreeView_GetItem_fn(*((HWND *)this + 53), &lParam);
              v12 = SendMessageA(*((HWND *)this + 53), 0x110Au, 9u, 0);
              MessageParent = FindMessageParent(*((HWND *)this + 53));
              PostMessageA(MessageParent, 0x111u, 0x100u, v12);
            }
          }
        }
        return 0;
      }
      memset(&lParam, 0, sizeof(lParam));
      lParam.hItem = (HTREEITEM)SendMessageA(*((HWND *)this + 53), 0x110Au, 9u, 0);
      if ( !lParam.hItem )
        return 0;
      lParam.mask = 4;
      W_TreeView_GetItem_fn(*((HWND *)this + 53), &lParam);
      v14 = *(_QWORD *)(*((_QWORD *)this + 6) + 8LL * SLODWORD(lParam.lParam));
      if ( *(_QWORD *)(v14 + 32) )
      {
        *((_DWORD *)this + 133) = 1;
        if ( (*(_BYTE *)(v14 + 27) & 0x20) != 0 )
        {
          v15 = (CHtmlHelpControl *)*((_QWORD *)this + 62);
          if ( v15 )
          {
            CHtmlHelpControl::SendEvent(v15, *(const char **)(*(_QWORD *)(v14 + 32) + 8LL));
            return 0;
          }
        }
        JumpToUrl(
          *((struct IUnknown **)this + 63),
          *((HWND *)this + 53),
          (struct _tagSiteMapEntry *)v14,
          *((struct CInfoType **)this + 70),
          (PCSTR *)this + 4,
          0,
          0,
          *((struct CHtmlHelpControl **)this + 62));
        v17 = *((_QWORD *)this + 67);
        if ( v17 )
          *(_QWORD *)(v17 + 328) = *((_QWORD *)this + 53);
      }
      if ( a2->nmcd.hdr.code != -4 )
        return 0;
      v18 = (HWND)*((_QWORD *)this + 53);
      if ( (lParam.state & 0x20) != 0 )
      {
        SendMessageA(v18, 0x1102u, 1u, (LPARAM)lParam.hItem);
        v19 = *(_BYTE *)(v14 + 24);
        if ( (unsigned __int8)(v19 - 2) <= 6u )
          *(_BYTE *)(v14 + 24) = v19 - 1;
      }
      else
      {
        SendMessageA(v18, 0x1102u, 2u, (LPARAM)lParam.hItem);
        if ( (lParam.state & 0x40) != 0 )
        {
          ImageNumber = *(_BYTE *)(v14 + 24);
          if ( !ImageNumber )
          {
            ImageNumber = CSiteMap::GetImageNumber((CToc *)((char *)this + 32), (struct _tagSiteMapEntry *)v14);
            *(_BYTE *)(v14 + 24) = ImageNumber;
          }
          if ( ImageNumber < 8u )
            *(_BYTE *)(v14 + 24) = ImageNumber + 1;
        }
      }
      v10 = *(unsigned __int8 *)(v14 + 24);
      hItem = lParam.hItem;
LABEL_60:
      Tree_SetImage(*((HWND *)this + 53), v10, hItem);
      return 0;
    }
    GetCursorPos((LPPOINT)v43);
    ScreenToClient(*((HWND *)this + 53), (LPPOINT)v43);
    SendMessageA(*((HWND *)this + 53), 0x1111u, 0, (LPARAM)v43);
    if ( v44 )
      SendMessageA(*((HWND *)this + 53), 0x110Bu, 9u, v44);
  }
  else
  {
    switch ( code )
    {
      case 0xFFFFFE6F:
LABEL_9:
        *((_QWORD *)this + 50) = a2[1].nmcd.hdr.hwndFrom;
        return 0;
      case 0xFFFFFE3A:
        goto LABEL_18;
      case 0xFFFFFE3C:
        if ( (a2->nmcd.dwDrawStage & 1) != 0
          && _tagSiteMapEntry::GetKeyword(
               *(_tagSiteMapEntry **)(*((_QWORD *)this + 6) + 8LL * SLODWORD(a2->nmcd.lItemlParam)),
               *(unsigned __int16 **)&a2->nmcd.rc.right,
               a2->nmcd.dwItemSpec) < 0 )
        {
          dwItemSpec_low = SLODWORD(a2->nmcd.dwItemSpec);
          StringResourceW = GetStringResourceW(0x412u);
          StringCchCopyNW(
            *(unsigned __int16 **)&a2->nmcd.rc.right,
            SLODWORD(a2->nmcd.dwItemSpec),
            StringResourceW,
            dwItemSpec_low);
        }
        return 0;
    }
    if ( code != -412 )
    {
      if ( code != -405 )
      {
        if ( code == -403 )
        {
          if ( (a2->nmcd.dwDrawStage & 1) != 0 )
            StringCchCopyNA(
              *(char **)&a2->nmcd.rc.right,
              SLODWORD(a2->nmcd.dwItemSpec),
              *(const char **)(*(_QWORD *)(*((_QWORD *)this + 6) + 8LL * SLODWORD(a2->nmcd.lItemlParam)) + 8LL),
              SLODWORD(a2->nmcd.dwItemSpec));
          return 0;
        }
        if ( code == -402 )
          goto LABEL_9;
        return 0;
      }
LABEL_18:
      if ( *((_DWORD *)this + 128) )
      {
        *((_DWORD *)this + 128) = 0;
        return 0;
      }
      v7 = *(struct _tagSiteMapEntry **)(*((_QWORD *)this + 6) + 8LL * a2[1].nmcd.rc.left);
      if ( !v7 )
        return 0;
      v8 = a2[1].nmcd.hdr.idFrom & 0x20;
      if ( (a2->nmcd.dwDrawStage & 2) != 0 )
      {
        if ( v8 )
          return 0;
        v9 = *((_BYTE *)v7 + 24);
        if ( !v9 )
        {
          v9 = CSiteMap::GetImageNumber((CToc *)((char *)this + 32), v7);
          *((_BYTE *)v7 + 24) = v9;
        }
        if ( v9 >= 8u )
          goto LABEL_32;
        ++v9;
      }
      else
      {
        if ( !v8 )
          return 0;
        v9 = *((_BYTE *)v7 + 24);
        if ( v9 <= 1u || v9 > 8u )
          goto LABEL_32;
        --v9;
      }
      *((_BYTE *)v7 + 24) = v9;
LABEL_32:
      v10 = v9;
      hItem = (struct _TREEITEM *)a2[1].nmcd.hdr.hwndFrom;
      goto LABEL_60;
    }
    if ( LOWORD(a2->nmcd.dwDrawStage) != 121 || GetKeyState(16) >= 0 )
      return 0;
    v43[0] = 0;
  }
  ClientToScreen(*((HWND *)this + 53), (LPPOINT)v43);
  PopupMenu = CreatePopupMenu();
  if ( !PopupMenu )
    return 0;
  if ( (*((_DWORD *)this + 130) & 0x400) == 0 )
  {
    v24 = GetStringResourceW(0x405u);
    AppendMenuW(PopupMenu, 0, 0xFAu, v24);
    v25 = GetStringResourceW(0x406u);
    AppendMenuW(PopupMenu, 0, 0xFBu, v25);
  }
  v26 = *((_QWORD *)this + 67);
  if ( !v26 || *(_QWORD *)(v26 + 600) )
  {
    v27 = GetStringResourceW(0x407u);
    AppendMenuW(PopupMenu, 0, 0xFDu, v27);
  }
  if ( !*((_QWORD *)this + 70) )
  {
    v28 = *((_QWORD *)this + 67);
    if ( v28 && (v29 = *(_QWORD *)(v28 + 608)) != 0 && *(_QWORD *)(v29 + 24) )
    {
      v30 = (CInfoType *)operator new(0x70u);
      if ( v30 )
        v31 = CInfoType::CInfoType(v30);
      else
        v31 = 0;
      *((_QWORD *)this + 70) = v31;
      CInfoType::CopyTo(v31, *(struct CHmData *const *)(*((_QWORD *)this + 67) + 608LL));
      v21 = *(const unsigned int **)(*(_QWORD *)(*((_QWORD *)this + 67) + 608LL) + 32LL);
      if ( v21 && CInfoType::AnyInfoTypes(*((CInfoType **)this + 70), v21) )
        memcpy_0(
          *(void **)(*((_QWORD *)this + 70) + 80LL),
          *(const void **)(*(_QWORD *)(*((_QWORD *)this + 67) + 608LL) + 32LL),
          4 * *(_DWORD *)(*((_QWORD *)this + 70) + 44LL));
    }
    else
    {
      v32 = (CInfoType *)operator new(0x70u);
      if ( v32 )
        v33 = CInfoType::CInfoType(v32);
      else
        v33 = 0;
      *((_QWORD *)this + 70) = v33;
      CInfoType::operator=(v33);
    }
  }
  v34 = (CInfoType *)*((_QWORD *)this + 70);
  if ( v34 )
  {
    v35 = *((_QWORD *)v34 + 1);
    if ( v35 )
    {
      if ( *(_DWORD *)(v35 + 32) != 1 && (unsigned int)CInfoType::GetFirstHidden(v34, (int)v21, v23) != 1 )
      {
        v36 = GetStringResourceW(0x40Fu);
        AppendMenuW(PopupMenu, 0, 0xFCu, v36);
      }
    }
  }
  v37 = FindMessageParent(*((HWND *)this + 53));
  if ( (unsigned int)IsHelpAuthor(v37) )
  {
    AppendMenuA(PopupMenu, 0x800u, 0, 0);
    v38 = (const char *)((__int64 (__fastcall *)(__int64))pGetDllStringResource)(120584);
    HxAppendMenu(PopupMenu, v39, 0xEFFEu, v38);
    if ( !NoRun(v40) )
    {
      v41 = GetStringResourceW(0x455u);
      AppendMenuW(PopupMenu, 0, 0xEFFFu, v41);
    }
  }
  hWnd = FindMessageParent(*((HWND *)this + 53));
  TrackPopupMenu(PopupMenu, 2u, v43[0], SHIDWORD(v43[0]), 0, hWnd, 0);
  DestroyMenu(PopupMenu);
  return 1;
}

```

## disassembly

```asm
0x18001bc88  mov     [rsp-8+arg_0], rbx
0x18001bc8d  mov     [rsp-8+arg_10], rsi
0x18001bc92  push    rbp
0x18001bc93  push    rdi
0x18001bc94  push    r14
0x18001bc96  lea     rbp, [rsp-47h]
0x18001bc9b  sub     rsp, 0B0h
0x18001bca2  mov     rsi, rdx
0x18001bca5  mov     rdi, rcx
0x18001bca8  xorps   xmm0, xmm0
0x18001bcab  xor     eax, eax
0x18001bcad  movups  xmmword ptr [rbp+57h+var_80], xmm0
0x18001bcb1  mov     [rbp+57h+var_70], rax
0x18001bcb5  mov     eax, [rdx+10h]
0x18001bcb8  mov     ecx, 0FFFFFE6Fh
0x18001bcbd  cmp     eax, ecx
0x18001bcbf  ja      loc_18001BE42
0x18001bcc5  jz      short loc_18001BD01
0x18001bcc7  cmp     eax, 0FFFFFE3Ah
0x18001bccc  jz      loc_18001BDBB
0x18001bcd2  cmp     eax, 0FFFFFE3Ch
0x18001bcd7  jz      loc_18001BD6A
0x18001bcdd  cmp     eax, 0FFFFFE64h
0x18001bce2  jz      short loc_18001BD40
0x18001bce4  cmp     eax, 0FFFFFE6Bh
0x18001bce9  jz      loc_18001BDBB
0x18001bcef  cmp     eax, 0FFFFFE6Dh
0x18001bcf4  jz      short loc_18001BD11
0x18001bcf6  cmp     eax, 0FFFFFE6Eh
0x18001bcfb  jnz     loc_18001BFD8
0x18001bd01  mov     rax, [rdx+60h]
0x18001bd05  mov     [rdi+190h], rax
0x18001bd0c  jmp     loc_18001BFD8
0x18001bd11  test    byte ptr [rdx+18h], 1
0x18001bd15  jz      loc_18001BFD8
0x18001bd1b  movsxd  rdx, dword ptr [rdx+38h]; unsigned __int64
0x18001bd1f  movsxd  rcx, dword ptr [rsi+48h]
0x18001bd23  mov     rax, [rdi+30h]
0x18001bd27  mov     r8, [rax+rcx*8]
0x18001bd2b  mov     r9, rdx; unsigned __int64
0x18001bd2e  mov     r8, [r8+8]; char *
0x18001bd32  mov     rcx, [rsi+30h]; char *
0x18001bd36  call    ?StringCchCopyNA@@YAJPEAD_KPEBD1@Z; StringCchCopyNA(char *,unsigned __int64,char const *,unsigned __int64)
0x18001bd3b  jmp     loc_18001BFD8
0x18001bd40  cmp     word ptr [rdx+18h], 79h ; 'y'
0x18001bd45  jnz     loc_18001BFD8
0x18001bd4b  mov     ecx, 10h; nVirtKey
0x18001bd50  call    cs:__imp_GetKeyState
0x18001bd56  xor     ebx, ebx
0x18001bd58  test    ax, ax
0x18001bd5b  jns     loc_18001BFD8
0x18001bd61  mov     [rbp+57h+var_80], rbx
0x18001bd65  jmp     loc_18001C113
0x18001bd6a  test    byte ptr [rdx+18h], 1
0x18001bd6e  jz      loc_18001BFD8
0x18001bd74  movsxd  rax, dword ptr [rdx+48h]
0x18001bd78  mov     rcx, [rdi+30h]
0x18001bd7c  mov     r8d, [rdx+38h]; int
0x18001bd80  mov     rdx, [rdx+30h]; unsigned __int16 *
0x18001bd84  mov     rcx, [rcx+rax*8]; this
0x18001bd88  call    ?GetKeyword@_tagSiteMapEntry@@QEAAJPEAGH@Z; _tagSiteMapEntry::GetKeyword(ushort *,int)
0x18001bd8d  test    eax, eax
0x18001bd8f  jns     loc_18001BFD8
0x18001bd95  movsxd  rbx, dword ptr [rsi+38h]
0x18001bd99  mov     ecx, 412h; uID
0x18001bd9e  call    ?GetStringResourceW@@YAPEBGH@Z; GetStringResourceW(int)
0x18001bda3  movsxd  rdx, dword ptr [rsi+38h]; unsigned __int64
0x18001bda7  mov     r9, rbx; unsigned __int64
0x18001bdaa  mov     r8, rax; unsigned __int16 *
0x18001bdad  mov     rcx, [rsi+30h]; unsigned __int16 *
0x18001bdb1  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18001bdb6  jmp     loc_18001BFD8
0x18001bdbb  xor     ebx, ebx
0x18001bdbd  cmp     [rdi+200h], ebx
0x18001bdc3  jz      short loc_18001BDD0
0x18001bdc5  mov     [rdi+200h], ebx
0x18001bdcb  jmp     loc_18001BFD8
0x18001bdd0  movsxd  rcx, dword ptr [rdx+88h]
0x18001bdd7  mov     rax, [rdi+30h]
0x18001bddb  mov     r10, [rax+rcx*8]
0x18001bddf  test    r10, r10
0x18001bde2  jz      loc_18001BFD8
0x18001bde8  mov     eax, [rdx+68h]
0x18001bdeb  and     eax, 20h
0x18001bdee  test    byte ptr [rdx+18h], 2
0x18001bdf2  jz      short loc_18001BE1C
0x18001bdf4  test    eax, eax
0x18001bdf6  jnz     loc_18001BFD8
0x18001bdfc  mov     al, [r10+18h]
0x18001be00  test    al, al
0x18001be02  jnz     short loc_18001BE14
0x18001be04  lea     rcx, [rdi+20h]; this
0x18001be08  mov     rdx, r10; struct _tagSiteMapEntry *
0x18001be0b  call    ?GetImageNumber@CSiteMap@@QEBAHPEAU_tagSiteMapEntry@@@Z; CSiteMap::GetImageNumber(_tagSiteMapEntry *)
0x18001be10  mov     [r10+18h], al
0x18001be14  cmp     al, 8
0x18001be16  jnb     short loc_18001BE36
0x18001be18  inc     al
0x18001be1a  jmp     short loc_18001BE32
0x18001be1c  test    eax, eax
0x18001be1e  jz      loc_18001BFD8
0x18001be24  mov     al, [r10+18h]
0x18001be28  cmp     al, 1
0x18001be2a  jbe     short loc_18001BE36
0x18001be2c  cmp     al, 8
0x18001be2e  ja      short loc_18001BE36
0x18001be30  dec     al
0x18001be32  mov     [r10+18h], al
0x18001be36  movzx   edx, al
0x18001be39  mov     r8, [rsi+60h]
0x18001be3d  jmp     loc_18001C0AD
0x18001be42  cmp     eax, 0FFFFFFF4h
0x18001be45  jz      loc_18001C3A4
0x18001be4b  cmp     eax, 0FFFFFFFBh
0x18001be4e  jz      loc_18001C0BE
0x18001be54  cmp     eax, 0FFFFFFFCh
0x18001be57  jz      loc_18001BF4B
0x18001be5d  cmp     eax, 0FFFFFFFDh
0x18001be60  jz      loc_18001BF4B
0x18001be66  cmp     eax, 0FFFFFFFEh
0x18001be69  jnz     loc_18001BFD8
0x18001be6f  xor     ebx, ebx
0x18001be71  cmp     [rdi+198h], ebx
0x18001be77  jnz     loc_18001BFD8
0x18001be7d  xor     eax, eax
0x18001be7f  movups  xmmword ptr [rbp+57h+Point.x], xmm0
0x18001be83  mov     [rbp+57h+var_58], rax
0x18001be87  lea     rcx, [rbp+57h+Point]; lpPoint
0x18001be8b  call    cs:__imp_GetCursorPos
0x18001be91  lea     rdx, [rbp+57h+Point]; lpPoint
0x18001be95  mov     rcx, [rdi+1A8h]; hWnd
0x18001be9c  call    cs:__imp_ScreenToClient
0x18001bea2  lea     r9, [rbp+57h+Point]; lParam
0x18001bea6  xor     r8d, r8d; wParam
0x18001bea9  mov     edx, 1111h; Msg
0x18001beae  mov     rcx, [rdi+1A8h]; hWnd
0x18001beb5  call    cs:__imp_SendMessageA
0x18001bebb  test    byte ptr [rbp+57h+Point.x+8], 10h
0x18001bebf  jnz     loc_18001BFD8
0x18001bec5  xorps   xmm0, xmm0
0x18001bec8  xor     eax, eax
0x18001beca  movups  xmmword ptr [rbp+57h+lParam], xmm0
0x18001bece  movups  [rbp+57h+var_40], xmm0
0x18001bed2  movups  [rbp+57h+var_30], xmm0
0x18001bed6  mov     [rbp+57h+var_20], rax
0x18001beda  mov     rax, [rbp+57h+var_58]
0x18001bede  mov     [rbp+57h+lParam+8], rax
0x18001bee2  test    rax, rax
0x18001bee5  jz      loc_18001BFD8
0x18001beeb  mov     [rdi+190h], rax
0x18001bef2  mov     dword ptr [rbp+57h+lParam], 4
0x18001bef9  lea     rdx, [rbp+57h+lParam]; struct tagTVITEMW *
0x18001befd  mov     rcx, [rdi+1A8h]; HWND
0x18001bf04  call    ?W_TreeView_GetItem_fn@@YAHPEAUHWND__@@PEAUtagTVITEMW@@@Z; W_TreeView_GetItem_fn(HWND__ *,tagTVITEMW *)
0x18001bf09  xor     r9d, r9d; lParam
0x18001bf0c  mov     edx, 110Ah; Msg
0x18001bf11  lea     r8d, [rbx+9]; wParam
0x18001bf15  mov     rcx, [rdi+1A8h]; hWnd
0x18001bf1c  call    cs:__imp_SendMessageA
0x18001bf22  mov     rbx, rax
0x18001bf25  mov     rcx, [rdi+1A8h]; HWND
0x18001bf2c  call    ?FindMessageParent@@YAPEAUHWND__@@PEAU1@@Z; FindMessageParent(HWND__ *)
0x18001bf31  mov     r9, rbx; lParam
0x18001bf34  mov     edx, 111h; Msg
0x18001bf39  lea     r8d, [rdx-11h]; wParam
0x18001bf3d  mov     rcx, rax; hWnd
0x18001bf40  call    cs:__imp_PostMessageA
0x18001bf46  jmp     loc_18001BFD8
0x18001bf4b  xor     eax, eax
0x18001bf4d  movups  xmmword ptr [rbp+57h+lParam], xmm0
0x18001bf51  movups  [rbp+57h+var_40], xmm0
0x18001bf55  movups  [rbp+57h+var_30], xmm0
0x18001bf59  mov     [rbp+57h+var_20], rax
0x18001bf5d  xor     r9d, r9d; lParam
0x18001bf60  mov     edx, 110Ah; Msg
0x18001bf65  lea     r8d, [rax+9]; wParam
0x18001bf69  mov     rcx, [rdi+1A8h]; hWnd
0x18001bf70  call    cs:__imp_SendMessageA
0x18001bf76  mov     [rbp+57h+lParam+8], rax
0x18001bf7a  xor     ebx, ebx
0x18001bf7c  test    rax, rax
0x18001bf7f  jz      short loc_18001BFD8
0x18001bf81  mov     dword ptr [rbp+57h+lParam], 4
0x18001bf88  lea     rdx, [rbp+57h+lParam]; struct tagTVITEMW *
0x18001bf8c  mov     rcx, [rdi+1A8h]; HWND
0x18001bf93  call    ?W_TreeView_GetItem_fn@@YAHPEAUHWND__@@PEAUtagTVITEMW@@@Z; W_TreeView_GetItem_fn(HWND__ *,tagTVITEMW *)
0x18001bf98  movsxd  rcx, dword ptr [rbp+57h+var_20]
0x18001bf9c  mov     rax, [rdi+30h]
0x18001bfa0  mov     r14, [rax+rcx*8]
0x18001bfa4  cmp     [r14+20h], rbx
0x18001bfa8  jz      loc_18001C035
0x18001bfae  mov     dword ptr [rdi+214h], 1
0x18001bfb8  test    byte ptr [r14+1Bh], 20h
0x18001bfbd  jz      short loc_18001BFDF
0x18001bfbf  mov     rcx, [rdi+1F0h]; this
0x18001bfc6  test    rcx, rcx
0x18001bfc9  jz      short loc_18001BFDF
0x18001bfcb  mov     rdx, [r14+20h]
0x18001bfcf  mov     rdx, [rdx+8]; char *
0x18001bfd3  call    ?SendEvent@CHtmlHelpControl@@QEAAJPEBD@Z; CHtmlHelpControl::SendEvent(char const *)
0x18001bfd8  xor     eax, eax
0x18001bfda  jmp     loc_18001C3AE
0x18001bfdf  lea     rcx, [rdi+20h]
0x18001bfe3  mov     rax, [rdi+1F0h]
0x18001bfea  mov     [rsp+0C0h+var_88], rax; struct CHtmlHelpControl *
0x18001bfef  mov     [rsp+0C0h+prcRect], rbx; struct IWebBrowserAppImpl *
0x18001bff4  mov     [rsp+0C0h+hWnd], rbx; struct SITE_ENTRY_URL *
0x18001bff9  mov     qword ptr [rsp+0C0h+nReserved], rcx; struct CSiteMap *
0x18001bffe  mov     r9, [rdi+230h]; struct CInfoType *
0x18001c005  mov     r8, r14; struct _tagSiteMapEntry *
0x18001c008  mov     rdx, [rdi+1A8h]; HWND
0x18001c00f  mov     rcx, [rdi+1F8h]; struct IUnknown *
0x18001c016  call    ?JumpToUrl@@YAPEAUHWND__@@PEAUIUnknown@@PEAU1@PEAU_tagSiteMapEntry@@PEAVCInfoType@@PEAVCSiteMap@@PEAUSITE_ENTRY_URL@@PEAVIWebBrowserAppImpl@@PEAVCHtmlHelpControl@@@Z; JumpToUrl(IUnknown *,HWND__ *,_tagSiteMapEntry *,CInfoType *,CSiteMap *,SITE_ENTRY_URL *,IWebBrowserAppImpl *,CHtmlHelpControl *)
0x18001c01b  mov     rcx, [rdi+218h]
0x18001c022  test    rcx, rcx
0x18001c025  jz      short loc_18001C035
0x18001c027  mov     rax, [rdi+1A8h]
0x18001c02e  mov     [rcx+148h], rax
0x18001c035  cmp     dword ptr [rsi+10h], 0FFFFFFFCh
0x18001c039  jnz     short loc_18001BFD8
0x18001c03b  mov     rcx, [rdi+1A8h]; hWnd
0x18001c042  mov     r9, [rbp+57h+lParam+8]; lParam
0x18001c046  mov     edx, 1102h; Msg
0x18001c04b  test    byte ptr [rbp+57h+var_40], 20h
0x18001c04f  jz      short loc_18001C070
0x18001c051  mov     r8d, 1; wParam
0x18001c057  call    cs:__imp_SendMessageA
0x18001c05d  mov     cl, [r14+18h]
0x18001c061  lea     eax, [rcx-2]
0x18001c064  cmp     al, 6
0x18001c066  ja      short loc_18001C0A4
0x18001c068  dec     cl
0x18001c06a  mov     [r14+18h], cl
0x18001c06e  jmp     short loc_18001C0A4
0x18001c070  mov     r8d, 2; wParam
0x18001c076  call    cs:__imp_SendMessageA
0x18001c07c  test    byte ptr [rbp+57h+var_40], 40h
0x18001c080  jz      short loc_18001C0A4
0x18001c082  mov     al, [r14+18h]
0x18001c086  test    al, al
0x18001c088  jnz     short loc_18001C09A
0x18001c08a  lea     rcx, [rdi+20h]; this
0x18001c08e  mov     rdx, r14; struct _tagSiteMapEntry *
0x18001c091  call    ?GetImageNumber@CSiteMap@@QEBAHPEAU_tagSiteMapEntry@@@Z; CSiteMap::GetImageNumber(_tagSiteMapEntry *)
0x18001c096  mov     [r14+18h], al
0x18001c09a  cmp     al, 8
0x18001c09c  jnb     short loc_18001C0A4
0x18001c09e  inc     al
0x18001c0a0  mov     [r14+18h], al
0x18001c0a4  movzx   edx, byte ptr [r14+18h]; int
0x18001c0a9  mov     r8, [rbp+57h+lParam+8]; struct _TREEITEM *
0x18001c0ad  mov     rcx, [rdi+1A8h]; HWND
0x18001c0b4  call    ?Tree_SetImage@@YAXPEAUHWND__@@HPEAU_TREEITEM@@@Z; Tree_SetImage(HWND__ *,int,_TREEITEM *)
0x18001c0b9  jmp     loc_18001BFD8
0x18001c0be  lea     rcx, [rbp+57h+var_80]; lpPoint
0x18001c0c2  call    cs:__imp_GetCursorPos
0x18001c0c8  lea     rdx, [rbp+57h+var_80]; lpPoint
0x18001c0cc  mov     rcx, [rdi+1A8h]; hWnd
0x18001c0d3  call    cs:__imp_ScreenToClient
0x18001c0d9  lea     r9, [rbp+57h+var_80]; lParam
0x18001c0dd  xor     r8d, r8d; wParam
0x18001c0e0  mov     edx, 1111h; Msg
0x18001c0e5  mov     rcx, [rdi+1A8h]; hWnd
0x18001c0ec  call    cs:__imp_SendMessageA
0x18001c0f2  mov     r9, [rbp+57h+var_70]; lParam
0x18001c0f6  xor     ebx, ebx
0x18001c0f8  test    r9, r9
0x18001c0fb  jz      short loc_18001C113
0x18001c0fd  mov     edx, 110Bh; Msg
0x18001c102  lea     r8d, [rbx+9]; wParam
0x18001c106  mov     rcx, [rdi+1A8h]; hWnd
0x18001c10d  call    cs:__imp_SendMessageA
0x18001c113  lea     rdx, [rbp+57h+var_80]; lpPoint
0x18001c117  mov     rcx, [rdi+1A8h]; hWnd
0x18001c11e  call    cs:__imp_ClientToScreen
0x18001c124  call    cs:__imp_CreatePopupMenu
0x18001c12a  mov     rsi, rax
0x18001c12d  test    rax, rax
0x18001c130  jz      loc_18001BFD8
0x18001c136  test    dword ptr [rdi+208h], 400h
0x18001c140  jnz     short loc_18001C17E
0x18001c142  mov     ecx, 405h; uID
0x18001c147  call    ?GetStringResourceW@@YAPEBGH@Z; GetStringResourceW(int)
0x18001c14c  mov     r9, rax; lpNewItem
0x18001c14f  xor     edx, edx; uFlags
0x18001c151  mov     r8d, 0FAh; uIDNewItem
0x18001c157  mov     rcx, rsi; hMenu
0x18001c15a  call    cs:__imp_AppendMenuW
0x18001c160  mov     ecx, 406h; uID
0x18001c165  call    ?GetStringResourceW@@YAPEBGH@Z; GetStringResourceW(int)
0x18001c16a  mov     r9, rax; lpNewItem
0x18001c16d  xor     edx, edx; uFlags
0x18001c16f  mov     r8d, 0FBh; uIDNewItem
0x18001c175  mov     rcx, rsi; hMenu
0x18001c178  call    cs:__imp_AppendMenuW
0x18001c17e  mov     rax, [rdi+218h]
0x18001c185  test    rax, rax
0x18001c188  jz      short loc_18001C193
0x18001c18a  cmp     [rax+258h], rbx
0x18001c191  jz      short loc_18001C1B1
  ... truncated ...
```
