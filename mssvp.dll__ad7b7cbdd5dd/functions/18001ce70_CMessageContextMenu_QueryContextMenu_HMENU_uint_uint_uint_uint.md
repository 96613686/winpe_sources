# CMessageContextMenu::QueryContextMenu(HMENU__ *,uint,uint,uint,uint)

- ea: `0x18001ce70`
- end: `0x18001d307`
- name: `?QueryContextMenu@CMessageContextMenu@@UEAAJPEAUHMENU__@@IIII@Z`
- size: `1175`
- prototype: `__int64 __fastcall(CMessageContextMenu *__hidden this, HMENU, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800048c0`
- `0x18000557c`
- `0x180006270`
- `0x180006dcc`
- `0x180018808`
- `0x180018b34`
- `0x18001c9fc`
- `0x18001ca6c`
- `0x18001cadc`
- `0x18001cb60`
- `0x18001ce70`
- `0x18001dff8`
- `0x18001e01c`
- `0x180028538`
- `0x180038ab0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18001cec5`
- `OLEAUT32!__imp_VariantInit` at `0x18001cfde`
- `OLEAUT32!__imp_VariantInit` at `0x18001d05b`
- `OLEAUT32!__imp_VariantInit` at `0x18001cec5`
- `OLEAUT32!__imp_VariantInit` at `0x18001cfde`
- `OLEAUT32!__imp_VariantInit` at `0x18001d05b`
- `OLEAUT32!__imp_VariantClear` at `0x18001d038`
- `OLEAUT32!__imp_VariantClear` at `0x18001d0e7`
- `OLEAUT32!__imp_VariantClear` at `0x18001d2dc`
- `OLEAUT32!__imp_VariantClear` at `0x18001d038`
- `OLEAUT32!__imp_VariantClear` at `0x18001d0e7`
- `OLEAUT32!__imp_VariantClear` at `0x18001d2dc`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001d0be`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001d0be`
- `USER32!LoadMenuW` at `0x18001d137`
- `USER32!LoadMenuW` at `0x18001d137`
- `USER32!InsertMenuItemW` at `0x18001d262`
- `USER32!InsertMenuItemW` at `0x18001d2ab`
- `USER32!InsertMenuItemW` at `0x18001d262`
- `USER32!InsertMenuItemW` at `0x18001d2ab`
- `USER32!GetMenuItemInfoW` at `0x18001d1bb`
- `USER32!GetMenuItemInfoW` at `0x18001d249`
- `USER32!GetMenuItemInfoW` at `0x18001d1bb`
- `USER32!GetMenuItemInfoW` at `0x18001d249`
- `USER32!GetMenuItemCount` at `0x18001d160`
- `USER32!GetMenuItemCount` at `0x18001d1f4`
- `USER32!GetMenuItemCount` at `0x18001d160`
- `USER32!GetMenuItemCount` at `0x18001d1f4`
- `USER32!CreatePopupMenu` at `0x18001d1de`
- `USER32!CreatePopupMenu` at `0x18001d1de`
- `USER32!DestroyMenu` at `0x18001d2c6`
- `USER32!DestroyMenu` at `0x18001d2c6`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CMessageContextMenu::QueryContextMenu(CMessageContextMenu *this, HMENU a2, UINT a3, int a4)
{
  int v5; // r13d
  char v6; // si
  unsigned __int16 v7; // r9
  int PropertyDetail; // edi
  char v9; // r14
  int v10; // r15d
  int v11; // r12d
  __int64 v12; // rax
  int v13; // esi
  unsigned __int16 v14; // r9
  HMENU MenuW; // r14
  unsigned __int16 v16; // r9
  unsigned int i; // esi
  int MenuItemCount; // eax
  int v19; // esi
  UINT v20; // ebx
  HMENU PopupMenu; // rdi
  int v22; // r12d
  signed int v23; // r15d
  UINT v24; // edx
  int v26; // [rsp+30h] [rbp-D0h]
  VARIANTARG v29; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v30; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v31; // [rsp+60h] [rbp-A0h] BYREF
  HMENU hmenu; // [rsp+68h] [rbp-98h]
  VARIANTARG pvarg; // [rsp+70h] [rbp-90h] BYREF
  tagMENUITEMINFOW mii; // [rsp+90h] [rbp-70h] BYREF
  MENUITEMINFOW mi; // [rsp+E0h] [rbp-20h] BYREF
  PCNZWCH v36[12]; // [rsp+130h] [rbp+30h] BYREF
  char v37; // [rsp+190h] [rbp+90h] BYREF
  char v38; // [rsp+990h] [rbp+890h] BYREF

  hmenu = a2;
  v5 = 0;
  v6 = 0;
  VariantInit(&pvarg);
  PropertyDetail = GetPropertyDetail(
                     *((LPCITEMIDLIST *)this + 10),
                     **((const struct _ITEMID_CHILD ***)this + 11),
                     &PKEY_ParsingPath,
                     v7,
                     &pvarg);
  if ( PropertyDetail >= 0 )
  {
    *((_DWORD *)this + 25) = 0;
    CMapiUrl::CMapiUrl((CMapiUrl *)v36, pvarg.bstrVal);
    if ( !(unsigned int)CMapiUrl::IsUrlValid((CMapiUrl *)v36)
      || !CMapiUrl::IsUrlThisUsersSID(v36)
      || (v6 = 1, !*(_DWORD *)(*(_QWORD *)CMapiUrl::StoreWithoutHash(v36, &v31) - 16LL))
      || (v6 = 3, v9 = 0, !*(_DWORD *)(*(_QWORD *)CMapiUrl::StoreHash(v36, &v30) - 16LL)) )
    {
      v9 = 1;
    }
    if ( (v6 & 2) != 0 )
    {
      v6 &= ~2u;
      ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&v30);
    }
    if ( (v6 & 1) != 0 )
      ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&v31);
    if ( v9 )
    {
      PropertyDetail = -2147467259;
    }
    else
    {
      v10 = 0;
      v11 = 0;
      v12 = -1;
      do
        ++v12;
      while ( *(_WORD *)(pvarg.llVal + 2 * v12) );
      if ( v12 && *(_WORD *)(pvarg.llVal + 2 * v12 - 2) == 47 )
      {
        v13 = 1;
      }
      else
      {
        v13 = 0;
        if ( (unsigned int)IsAttachment(pvarg.bstrVal) )
        {
          v10 = 1;
        }
        else
        {
          VariantInit(&v29);
          PropertyDetail = GetPropertyDetail(
                             *((LPCITEMIDLIST *)this + 10),
                             **((const struct _ITEMID_CHILD ***)this + 11),
                             &PKEY_ItemType,
                             v14,
                             &v29);
          if ( PropertyDetail < 0 )
          {
            PropertyDetail = 0;
          }
          else if ( IsFreeDoc(pvarg.bstrVal, v29.bstrVal) )
          {
            *((_DWORD *)this + 25) = 1;
          }
          else
          {
            v11 = 1;
          }
          VariantClear(&v29);
        }
      }
      *((_DWORD *)this + 24) = 0;
      MenuW = 0;
      if ( v11 )
      {
        VariantInit(&v29);
        PropertyDetail = GetPropertyDetail(
                           *((LPCITEMIDLIST *)this + 10),
                           **((const struct _ITEMID_CHILD ***)this + 11),
                           &PKEY_ItemType,
                           v16,
                           &v29);
        if ( PropertyDetail >= 0 )
        {
          for ( i = 0; i < 0xC; ++i )
          {
            if ( CompareStringW(0x7Fu, 1u, v29.bstrVal, -1, (&off_1800532F0)[2 * (int)i], -1) == 2 )
            {
              *((_DWORD *)this + 24) = *((_DWORD *)&off_1800532F0 + 4 * (int)i + 2);
              break;
            }
          }
        }
        if ( !*((_DWORD *)this + 24) )
          *((_DWORD *)this + 24) = 1002;
        VariantClear(&v29);
      }
      else if ( v13 )
      {
        *((_DWORD *)this + 24) = 1007;
      }
      else if ( v10 || *((_DWORD *)this + 25) )
      {
        *((_DWORD *)this + 24) = 1001;
      }
      else
      {
        *((_DWORD *)this + 24) = 1000;
        v5 = 1;
      }
      if ( *((_DWORD *)this + 24) )
      {
        MenuW = LoadMenuW(hInstance, (LPCWSTR)*((unsigned __int16 *)this + 48));
        if ( !MenuW )
          PropertyDetail = ResultFromLastError();
      }
      if ( PropertyDetail >= 0 && MenuW )
      {
        MenuItemCount = GetMenuItemCount(MenuW);
        v19 = MenuItemCount;
        v26 = MenuItemCount;
        if ( MenuItemCount != -1 )
        {
          v20 = 0;
          if ( MenuItemCount > 0 )
          {
            do
            {
              memset_0(&mii, 0, sizeof(mii));
              mii.cbSize = 80;
              *(_QWORD *)&mii.fMask = 23;
              mii.dwTypeData = (LPWSTR)&v37;
              mii.cch = 1024;
              GetMenuItemInfoW(MenuW, v20, 1, &mii);
              if ( !v5 || v20 >= 3 )
              {
                if ( mii.hSubMenu )
                {
                  mii.fMask &= ~2u;
                  PopupMenu = CreatePopupMenu();
                  if ( !PopupMenu )
                    break;
                  v22 = GetMenuItemCount(mii.hSubMenu);
                  v23 = 0;
                  if ( v22 > 0 )
                  {
                    do
                    {
                      memset_0(&mi, 0, sizeof(mi));
                      mi.cbSize = 80;
                      *(_QWORD *)&mi.fMask = 23;
                      mi.dwTypeData = (LPWSTR)&v38;
                      mi.cch = 1024;
                      GetMenuItemInfoW(mii.hSubMenu, v23, 1, &mi);
                      mi.wID += a4;
                      InsertMenuItemW(PopupMenu, v23++, 1, &mi);
                    }
                    while ( v23 < v22 );
                    v19 = v26;
                  }
                  mii.hSubMenu = PopupMenu;
                }
                if ( mii.wID == 1 )
                  mii.fState |= 0x1000u;
                mii.wID += a4;
                v24 = a3++;
                InsertMenuItemW(hmenu, v24, 1, &mii);
              }
              ++v20;
            }
            while ( (int)v20 < v19 );
          }
          PropertyDetail = (unsigned __int16)(v20 + 1);
        }
        DestroyMenu(MenuW);
      }
    }
    CMapiUrl::~CMapiUrl((CMapiUrl *)v36);
  }
  VariantClear(&pvarg);
  return (unsigned int)PropertyDetail;
}

```

## disassembly

```asm
0x18001ce70  push    rbp
0x18001ce72  push    rbx
0x18001ce73  push    rsi
0x18001ce74  push    rdi
0x18001ce75  push    r12
0x18001ce77  push    r13
0x18001ce79  push    r14
0x18001ce7b  push    r15
0x18001ce7d  lea     rbp, [rsp-10A8h]
0x18001ce85  mov     eax, 11A8h
0x18001ce8a  call    _alloca_probe
0x18001ce8f  sub     rsp, rax
0x18001ce92  mov     rax, cs:__security_cookie
0x18001ce99  xor     rax, rsp
0x18001ce9c  mov     [rbp+10E0h+var_50], rax
0x18001cea3  mov     [rsp+11E0h+var_11AC], r9d
0x18001cea8  mov     [rsp+11E0h+item], r8d
0x18001cead  mov     [rsp+11E0h+hmenu], rdx
0x18001ceb2  mov     rbx, rcx
0x18001ceb5  xor     r13d, r13d
0x18001ceb8  mov     esi, r13d
0x18001cebb  mov     [rsp+11E0h+var_11B0], r13d
0x18001cec0  lea     rcx, [rsp+11E0h+pvarg]; pvarg
0x18001cec5  call    cs:__imp_VariantInit
0x18001cecb  nop
0x18001cecc  mov     rdx, [rbx+58h]
0x18001ced0  lea     rax, [rsp+11E0h+pvarg]
0x18001ced5  mov     [rsp+11E0h+lpString2], rax; struct tagVARIANT *
0x18001ceda  lea     r8, PKEY_ParsingPath; struct _tagpropertykey *
0x18001cee1  mov     rdx, [rdx]; struct _ITEMID_CHILD *
0x18001cee4  mov     rcx, [rbx+50h]; pidl
0x18001cee8  call    ?GetPropertyDetail@@YAJPEFBU_ITEMIDLIST_RELATIVE@@PEFBU_ITEMID_CHILD@@PEBU_tagpropertykey@@GPEAUtagVARIANT@@@Z; GetPropertyDetail(_ITEMIDLIST_RELATIVE const *,_ITEMID_CHILD const *,_tagpropertykey const *,ushort,tagVARIANT *)
0x18001ceed  mov     edi, eax
0x18001ceef  test    eax, eax
0x18001cef1  js      loc_18001D2D7
0x18001cef7  mov     [rbx+64h], r13d
0x18001cefb  mov     rdx, qword ptr [rsp+11E0h+pvarg+8]; wchar_t *
0x18001cf00  lea     rcx, [rbp+10E0h+var_10B0]; this
0x18001cf04  call    ??0CMapiUrl@@QEAA@PEB_W@Z; CMapiUrl::CMapiUrl(wchar_t const *)
0x18001cf09  nop
0x18001cf0a  lea     rcx, [rbp+10E0h+var_10B0]; this
0x18001cf0e  call    ?IsUrlValid@CMapiUrl@@QEAAHXZ; CMapiUrl::IsUrlValid(void)
0x18001cf13  test    eax, eax
0x18001cf15  jz      short loc_18001CF62
0x18001cf17  lea     rcx, [rbp+10E0h+var_10B0]; this
0x18001cf1b  call    ?IsUrlThisUsersSID@CMapiUrl@@QEAAHXZ; CMapiUrl::IsUrlThisUsersSID(void)
0x18001cf20  test    eax, eax
0x18001cf22  jz      short loc_18001CF62
0x18001cf24  lea     rdx, [rsp+11E0h+var_1180]
0x18001cf29  lea     rcx, [rbp+10E0h+var_10B0]
0x18001cf2d  call    ?StoreWithoutHash@CMapiUrl@@QEAA?AV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@XZ; CMapiUrl::StoreWithoutHash(void)
0x18001cf32  nop
0x18001cf33  lea     esi, [r13+1]
0x18001cf37  mov     [rsp+11E0h+var_11B0], esi
0x18001cf3b  mov     rax, [rax]
0x18001cf3e  cmp     [rax-10h], r13d
0x18001cf42  jz      short loc_18001CF62
0x18001cf44  lea     rdx, [rsp+11E0h+var_1188]
0x18001cf49  lea     rcx, [rbp+10E0h+var_10B0]
0x18001cf4d  call    ?StoreHash@CMapiUrl@@QEAA?AV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@XZ; CMapiUrl::StoreHash(void)
0x18001cf52  lea     esi, [r13+3]
0x18001cf56  mov     rax, [rax]
0x18001cf59  cmp     [rax-10h], r13d
0x18001cf5d  mov     r14b, r13b
0x18001cf60  jnz     short loc_18001CF65
0x18001cf62  mov     r14b, 1
0x18001cf65  test    sil, 2
0x18001cf69  jz      short loc_18001CF79
0x18001cf6b  and     esi, 0FFFFFFFDh
0x18001cf6e  lea     rcx, [rsp+11E0h+var_1188]
0x18001cf73  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x18001cf78  nop
0x18001cf79  test    sil, 1
0x18001cf7d  jz      short loc_18001CF89
0x18001cf7f  lea     rcx, [rsp+11E0h+var_1180]
0x18001cf84  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x18001cf89  test    r14b, r14b
0x18001cf8c  jz      short loc_18001CF98
0x18001cf8e  mov     edi, 80004005h
0x18001cf93  jmp     loc_18001D2CD
0x18001cf98  mov     r15d, r13d
0x18001cf9b  mov     r12d, r13d
0x18001cf9e  mov     rcx, qword ptr [rsp+11E0h+pvarg+8]; wchar_t *
0x18001cfa3  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001cfa7  inc     rax
0x18001cfaa  cmp     [rcx+rax*2], r13w
0x18001cfaf  jnz     short loc_18001CFA7
0x18001cfb1  test    rax, rax
0x18001cfb4  jz      short loc_18001CFC5
0x18001cfb6  cmp     word ptr [rcx+rax*2-2], 2Fh ; '/'
0x18001cfbc  jnz     short loc_18001CFC5
0x18001cfbe  mov     esi, 1
0x18001cfc3  jmp     short loc_18001D03E
0x18001cfc5  mov     esi, r13d
0x18001cfc8  call    ?IsAttachment@@YAHPEB_W@Z; IsAttachment(wchar_t const *)
0x18001cfcd  test    eax, eax
0x18001cfcf  jz      short loc_18001CFD9
0x18001cfd1  mov     r15d, 1
0x18001cfd7  jmp     short loc_18001D03E
0x18001cfd9  lea     rcx, [rsp+11E0h+var_11A0]; pvarg
0x18001cfde  call    cs:__imp_VariantInit
0x18001cfe4  nop
0x18001cfe5  mov     rdx, [rbx+58h]
0x18001cfe9  lea     rax, [rsp+11E0h+var_11A0]
0x18001cfee  mov     [rsp+11E0h+lpString2], rax; struct tagVARIANT *
0x18001cff3  lea     r8, PKEY_ItemType; struct _tagpropertykey *
0x18001cffa  mov     rdx, [rdx]; struct _ITEMID_CHILD *
0x18001cffd  mov     rcx, [rbx+50h]; pidl
0x18001d001  call    ?GetPropertyDetail@@YAJPEFBU_ITEMIDLIST_RELATIVE@@PEFBU_ITEMID_CHILD@@PEBU_tagpropertykey@@GPEAUtagVARIANT@@@Z; GetPropertyDetail(_ITEMIDLIST_RELATIVE const *,_ITEMID_CHILD const *,_tagpropertykey const *,ushort,tagVARIANT *)
0x18001d006  mov     edi, eax
0x18001d008  test    eax, eax
0x18001d00a  js      short loc_18001D030
0x18001d00c  mov     rdx, qword ptr [rsp+11E0h+var_11A0+8]; wchar_t *
0x18001d011  mov     rcx, qword ptr [rsp+11E0h+pvarg+8]; wchar_t *
0x18001d016  call    ?IsFreeDoc@@YAHPEB_W0@Z; IsFreeDoc(wchar_t const *,wchar_t const *)
0x18001d01b  test    eax, eax
0x18001d01d  jz      short loc_18001D028
0x18001d01f  mov     dword ptr [rbx+64h], 1
0x18001d026  jmp     short loc_18001D033
0x18001d028  mov     r12d, 1
0x18001d02e  jmp     short loc_18001D033
0x18001d030  mov     edi, r13d
0x18001d033  lea     rcx, [rsp+11E0h+var_11A0]; pvarg
0x18001d038  call    cs:__imp_VariantClear
0x18001d03e  mov     [rbx+60h], r13d
0x18001d042  test    edi, edi
0x18001d044  js      loc_18001D2CD
0x18001d04a  xor     r14d, r14d
0x18001d04d  test    r12d, r12d
0x18001d050  jz      loc_18001D0EF
0x18001d056  lea     rcx, [rsp+11E0h+var_11A0]; pvarg
0x18001d05b  call    cs:__imp_VariantInit
0x18001d061  nop
0x18001d062  mov     rdx, [rbx+58h]
0x18001d066  lea     rax, [rsp+11E0h+var_11A0]
0x18001d06b  mov     [rsp+11E0h+lpString2], rax; struct tagVARIANT *
0x18001d070  lea     r8, PKEY_ItemType; struct _tagpropertykey *
0x18001d077  mov     rdx, [rdx]; struct _ITEMID_CHILD *
0x18001d07a  mov     rcx, [rbx+50h]; pidl
0x18001d07e  call    ?GetPropertyDetail@@YAJPEFBU_ITEMIDLIST_RELATIVE@@PEFBU_ITEMID_CHILD@@PEBU_tagpropertykey@@GPEAUtagVARIANT@@@Z; GetPropertyDetail(_ITEMIDLIST_RELATIVE const *,_ITEMID_CHILD const *,_tagpropertykey const *,ushort,tagVARIANT *)
0x18001d083  mov     edi, eax
0x18001d085  test    eax, eax
0x18001d087  js      short loc_18001D0D5
0x18001d089  xor     esi, esi
0x18001d08b  lea     r12, off_1800532F0; "MAPI/IPM.Schedule.Meeting"
0x18001d092  cmp     esi, 0Ch
0x18001d095  jnb     short loc_18001D0D5
0x18001d097  movsxd  r15, esi
0x18001d09a  add     r15, r15
0x18001d09d  mov     [rsp+11E0h+cchCount2], 0FFFFFFFFh; cchCount2
0x18001d0a5  mov     rax, [r12+r15*8]
0x18001d0a9  mov     [rsp+11E0h+lpString2], rax; lpString2
0x18001d0ae  or      r9d, 0FFFFFFFFh; cchCount1
0x18001d0b2  mov     r8, qword ptr [rsp+11E0h+var_11A0+8]; lpString1
0x18001d0b7  lea     edx, [r9+2]; dwCmpFlags
0x18001d0bb  lea     ecx, [rdx+7Eh]; Locale
0x18001d0be  call    cs:__imp_CompareStringW
0x18001d0c4  cmp     eax, 2
0x18001d0c7  jz      short loc_18001D0CD
0x18001d0c9  inc     esi
0x18001d0cb  jmp     short loc_18001D092
0x18001d0cd  mov     eax, [r12+r15*8+8]
0x18001d0d2  mov     [rbx+60h], eax
0x18001d0d5  cmp     dword ptr [rbx+60h], 0
0x18001d0d9  jnz     short loc_18001D0E2
0x18001d0db  mov     dword ptr [rbx+60h], 3EAh
0x18001d0e2  lea     rcx, [rsp+11E0h+var_11A0]; pvarg
0x18001d0e7  call    cs:__imp_VariantClear
0x18001d0ed  jmp     short loc_18001D120
0x18001d0ef  test    esi, esi
0x18001d0f1  jz      short loc_18001D0FC
0x18001d0f3  mov     dword ptr [rbx+60h], 3EFh
0x18001d0fa  jmp     short loc_18001D120
0x18001d0fc  test    r15d, r15d
0x18001d0ff  jnz     short loc_18001D119
0x18001d101  cmp     [rbx+64h], r14d
0x18001d105  jnz     short loc_18001D119
0x18001d107  mov     dword ptr [rbx+60h], 3E8h
0x18001d10e  mov     r15d, 1
0x18001d114  mov     r13d, r15d
0x18001d117  jmp     short loc_18001D126
0x18001d119  mov     dword ptr [rbx+60h], 3E9h
0x18001d120  mov     r15d, 1
0x18001d126  cmp     dword ptr [rbx+60h], 0
0x18001d12a  jz      short loc_18001D14C
0x18001d12c  movzx   edx, word ptr [rbx+60h]; lpMenuName
0x18001d130  mov     rcx, cs:hInstance; hInstance
0x18001d137  call    cs:__imp_LoadMenuW
0x18001d13d  mov     r14, rax
0x18001d140  test    rax, rax
0x18001d143  jnz     short loc_18001D14C
0x18001d145  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18001d14a  mov     edi, eax
0x18001d14c  test    edi, edi
0x18001d14e  js      loc_18001D2CD
0x18001d154  test    r14, r14
0x18001d157  jz      loc_18001D2CD
0x18001d15d  mov     rcx, r14; hMenu
0x18001d160  call    cs:__imp_GetMenuItemCount
0x18001d166  mov     esi, eax
0x18001d168  mov     [rsp+11E0h+var_11B0], eax
0x18001d16c  cmp     eax, 0FFFFFFFFh
0x18001d16f  jz      loc_18001D2C3
0x18001d175  xor     ebx, ebx
0x18001d177  test    eax, eax
0x18001d179  jle     loc_18001D2BC
0x18001d17f  xor     edx, edx; Val
0x18001d181  lea     r8d, [rdx+50h]; Size
0x18001d185  lea     rcx, [rbp+10E0h+mii]; void *
0x18001d189  call    memset_0
0x18001d18e  mov     [rbp+10E0h+mii.cbSize], 50h ; 'P'
0x18001d195  mov     qword ptr [rbp+10E0h+mii.fMask], 17h
0x18001d19d  lea     rax, [rbp+10E0h+var_1050]
0x18001d1a4  mov     [rbp+10E0h+mii.dwTypeData], rax
0x18001d1a8  mov     [rbp+10E0h+mii.cch], 400h
0x18001d1af  lea     r9, [rbp+10E0h+mii]; lpmii
0x18001d1b3  mov     r8d, r15d; fByPosition
0x18001d1b6  mov     edx, ebx; item
0x18001d1b8  mov     rcx, r14; hmenu
0x18001d1bb  call    cs:__imp_GetMenuItemInfoW
0x18001d1c1  test    r13d, r13d
0x18001d1c4  jz      short loc_18001D1CF
0x18001d1c6  cmp     ebx, 3
0x18001d1c9  jb      loc_18001D2B1
0x18001d1cf  cmp     [rbp+10E0h+mii.hSubMenu], 0
0x18001d1d4  jz      loc_18001D27E
0x18001d1da  and     [rbp+10E0h+mii.fMask], 0FFFFFFFDh
0x18001d1de  call    cs:__imp_CreatePopupMenu
0x18001d1e4  mov     rdi, rax
0x18001d1e7  test    rax, rax
0x18001d1ea  jz      loc_18001D2BC
0x18001d1f0  mov     rcx, [rbp+10E0h+mii.hSubMenu]; hMenu
0x18001d1f4  call    cs:__imp_GetMenuItemCount
0x18001d1fa  mov     r12d, eax
0x18001d1fd  xor     r15d, r15d
0x18001d200  test    eax, eax
0x18001d202  jle     short loc_18001D274
0x18001d204  mov     esi, [rsp+11E0h+var_11AC]
0x18001d208  xor     edx, edx; Val
0x18001d20a  lea     r8d, [rdx+50h]; Size
0x18001d20e  lea     rcx, [rbp+10E0h+mi]; void *
0x18001d212  call    memset_0
0x18001d217  mov     [rbp+10E0h+mi.cbSize], 50h ; 'P'
0x18001d21e  mov     qword ptr [rbp+10E0h+mi.fMask], 17h
0x18001d226  lea     rax, [rbp+10E0h+var_850]
0x18001d22d  mov     [rbp+10E0h+mi.dwTypeData], rax
0x18001d231  mov     [rbp+10E0h+mi.cch], 400h
0x18001d238  lea     r9, [rbp+10E0h+mi]; lpmii
0x18001d23c  mov     r8d, 1; fByPosition
0x18001d242  mov     edx, r15d; item
0x18001d245  mov     rcx, [rbp+10E0h+mii.hSubMenu]; hmenu
0x18001d249  call    cs:__imp_GetMenuItemInfoW
0x18001d24f  add     [rbp+10E0h+mi.wID], esi
0x18001d252  lea     r9, [rbp+10E0h+mi]; lpmi
0x18001d256  mov     r8d, 1; fByPosition
0x18001d25c  mov     edx, r15d; item
0x18001d25f  mov     rcx, rdi; hmenu
0x18001d262  call    cs:__imp_InsertMenuItemW
0x18001d268  inc     r15d
0x18001d26b  cmp     r15d, r12d
0x18001d26e  jl      short loc_18001D208
0x18001d270  mov     esi, [rsp+11E0h+var_11B0]
0x18001d274  mov     [rbp+10E0h+mii.hSubMenu], rdi
0x18001d278  mov     r15d, 1
0x18001d27e  mov     eax, [rbp+10E0h+mii.wID]
0x18001d281  cmp     eax, r15d
0x18001d284  jnz     short loc_18001D28B
0x18001d286  bts     [rbp+10E0h+mii.fState], 0Ch
0x18001d28b  add     eax, [rsp+11E0h+var_11AC]
0x18001d28f  mov     [rbp+10E0h+mii.wID], eax
0x18001d292  mov     eax, [rsp+11E0h+item]
0x18001d296  mov     edx, eax; item
0x18001d298  add     eax, r15d
0x18001d29b  mov     [rsp+11E0h+item], eax
0x18001d29f  lea     r9, [rbp+10E0h+mii]; lpmi
0x18001d2a3  mov     r8d, r15d; fByPosition
0x18001d2a6  mov     rcx, [rsp+11E0h+hmenu]; hmenu
0x18001d2ab  call    cs:__imp_InsertMenuItemW
0x18001d2b1  add     ebx, r15d
0x18001d2b4  cmp     ebx, esi
0x18001d2b6  jl      loc_18001D17F
0x18001d2bc  add     bx, r15w
0x18001d2c0  movzx   edi, bx
0x18001d2c3  mov     rcx, r14; hMenu
0x18001d2c6  call    cs:__imp_DestroyMenu
0x18001d2cc  nop
0x18001d2cd  lea     rcx, [rbp+10E0h+var_10B0]; this
0x18001d2d1  call    ??1CMapiUrl@@QEAA@XZ; CMapiUrl::~CMapiUrl(void)
0x18001d2d6  nop
0x18001d2d7  lea     rcx, [rsp+11E0h+pvarg]; pvarg
0x18001d2dc  call    cs:__imp_VariantClear
0x18001d2e2  mov     eax, edi
0x18001d2e4  mov     rcx, [rbp+10E0h+var_50]
0x18001d2eb  xor     rcx, rsp; StackCookie
0x18001d2ee  call    __security_check_cookie
0x18001d2f3  add     rsp, 11A8h
0x18001d2fa  pop     r15
0x18001d2fc  pop     r14
0x18001d2fe  pop     r13
0x18001d300  pop     r12
  ... truncated ...
```
