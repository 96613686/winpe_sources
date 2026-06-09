# CContentDirectoryFolder::_GetString(_ITEMID_CHILD const *,_tagpropertykey const &,ushort * *)

- ea: `0x1800082b4`
- end: `0x180008421`
- name: `?_GetString@CContentDirectoryFolder@@AEAAJPEFBU_ITEMID_CHILD@@AEBU_tagpropertykey@@PEAPEAG@Z`
- size: `365`
- prototype: `int(CContentDirectoryFolder *__hidden this, const struct _ITEMID_CHILD *, const struct _tagpropertykey *, unsigned __int16 **)`
- caller_count: `8`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180008010`
- `0x180011204`
- `0x1800164d0`
- `0x1800180f0`
- `0x1800181dc`
- `0x180018354`
- `0x180018728`
- `0x180019298`

## callees

- `0x1800082b4`
- `0x18000a4a0`
- `0x18000da0c`
- `0x18000dbb8`
- `0x18000de1c`
- `0x1800187b8`
- `0x180018864`
- `0x180018934`
- `0x180019370`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000840a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000840a`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x18000830f`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x18000830f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CContentDirectoryFolder::_GetString(
        CContentDirectoryFolder *this,
        const struct _ITEMID_CHILD *a2,
        const struct _tagpropertykey *a3,
        unsigned __int16 **a4)
{
  __int64 IsValid; // rax
  const PROPERTYKEY *v9; // r8
  HRESULT AsOrStealString; // ebx
  VARTYPE vt; // ax
  CContentDirectoryFolder *v12; // rcx
  int ItemDate; // eax
  CContentDirectoryFolder *v14; // rcx
  CContentDirectoryFolder *v15; // rcx
  PROPVARIANT ppropvar; // [rsp+20h] [rbp-20h] BYREF

  *a4 = 0;
  memset(&ppropvar, 0, sizeof(ppropvar));
  IsValid = CItemIDFactory<CDSFOLDER_ITEMID,1158816290>::_IsValid(a2);
  if ( IsValid && *(_WORD *)(IsValid + 10) )
  {
    AsOrStealString = -2147024809;
    if ( IsValid == -18
      || (AsOrStealString = PSGetPropertyFromPropertyStorage(
                              (PCUSERIALIZEDPROPSTORAGE)(IsValid + 18),
                              *(unsigned __int16 *)(IsValid + 10),
                              v9,
                              &ppropvar),
          AsOrStealString < 0) )
    {
      vt = ppropvar.vt;
    }
    else
    {
      vt = ppropvar.vt;
      if ( !ppropvar.vt )
      {
        AsOrStealString = -2147023288;
        goto LABEL_12;
      }
    }
    if ( AsOrStealString >= 0 && vt )
      goto LABEL_24;
  }
  else
  {
    AsOrStealString = -2147024809;
  }
LABEL_12:
  if ( (unsigned int)operator==(a3, &PKEY_ItemDate) )
  {
    ItemDate = CContentDirectoryFolder::_GetItemDate(v12, a2, &ppropvar);
  }
  else if ( (unsigned int)operator==(a3, &PKEY_ItemNameDisplay) )
  {
    ItemDate = CItemIDFactory<CDSFOLDER_ITEMID,1158816290>::GetPropertyFromIDList(a2, &PKEY_ItemName, &ppropvar);
  }
  else if ( (unsigned int)operator==(a3, &PKEY_ItemType) )
  {
    ItemDate = CContentDirectoryFolder::_GetItemTypeProperty(v14, a2, &ppropvar);
  }
  else if ( (unsigned int)operator==(a3, &PKEY_ItemTypeText) )
  {
    ItemDate = CContentDirectoryFolder::_GetItemTypeTextProperty(v15, a2, &ppropvar);
  }
  else
  {
    if ( !(unsigned int)operator==(a3, &PKEY_ThumbnailStream) )
      goto LABEL_23;
    ItemDate = CContentDirectoryFolder::_GetThumbnailStreamProperty(this, a2, &ppropvar);
  }
  AsOrStealString = ItemDate;
LABEL_23:
  if ( AsOrStealString >= 0 )
LABEL_24:
    AsOrStealString = CPropVariant::GetAsOrStealString((CPropVariant *)&ppropvar, a4);
  PropVariantClear(&ppropvar);
  return (unsigned int)AsOrStealString;
}

```

## disassembly

```asm
0x1800082b4  push    rbp
0x1800082b6  push    rbx
0x1800082b7  push    rsi
0x1800082b8  push    rdi
0x1800082b9  push    r12
0x1800082bb  push    r14
0x1800082bd  push    r15
0x1800082bf  mov     rbp, rsp
0x1800082c2  sub     rsp, 40h
0x1800082c6  mov     r14, r9
0x1800082c9  mov     rsi, r8
0x1800082cc  mov     rdi, rdx
0x1800082cf  mov     r15, rcx
0x1800082d2  xor     r12d, r12d
0x1800082d5  mov     [r9], r12
0x1800082d8  xorps   xmm0, xmm0
0x1800082db  xor     eax, eax
0x1800082dd  movups  xmmword ptr [rbp+ppropvar], xmm0
0x1800082e1  mov     qword ptr [rbp+ppropvar+10h], rax
0x1800082e5  mov     rcx, rdx
0x1800082e8  call    ?_IsValid@?$CItemIDFactory@UCDSFOLDER_ITEMID@@$0EFBCCCCC@@@CAPEFBUCHILDITEMID@1@PEFBU_ITEMIDLIST_RELATIVE@@@Z; CItemIDFactory<CDSFOLDER_ITEMID,1158816290>::_IsValid(_ITEMIDLIST_RELATIVE const *)
0x1800082ed  test    rax, rax
0x1800082f0  jz      short loc_18000833D
0x1800082f2  cmp     [rax+0Ah], r12w
0x1800082f7  jz      short loc_18000833D
0x1800082f9  mov     ebx, 80070057h
0x1800082fe  lea     rcx, [rax+12h]; psps
0x180008302  test    rcx, rcx
0x180008305  jz      short loc_18000832B
0x180008307  movzx   edx, word ptr [rax+0Ah]; cb
0x18000830b  lea     r9, [rbp+ppropvar]; ppropvar
0x18000830f  call    cs:__imp_PSGetPropertyFromPropertyStorage
0x180008315  mov     ebx, eax
0x180008317  test    eax, eax
0x180008319  js      short loc_18000832B
0x18000831b  movzx   eax, word ptr [rbp+ppropvar]
0x18000831f  test    ax, ax
0x180008322  jnz     short loc_18000832F
0x180008324  mov     ebx, 80070648h
0x180008329  jmp     short loc_180008342
0x18000832b  movzx   eax, word ptr [rbp+ppropvar]
0x18000832f  test    ebx, ebx
0x180008331  js      short loc_180008342
0x180008333  test    ax, ax
0x180008336  jz      short loc_180008342
0x180008338  jmp     loc_1800083F8
0x18000833d  mov     ebx, 80070057h
0x180008342  lea     rdx, PKEY_ItemDate
0x180008349  mov     rcx, rsi
0x18000834c  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x180008351  test    eax, eax
0x180008353  jz      short loc_180008366
0x180008355  lea     r8, [rbp+ppropvar]; struct tagPROPVARIANT *
0x180008359  mov     rdx, rdi; struct _ITEMID_CHILD *
0x18000835c  call    ?_GetItemDate@CContentDirectoryFolder@@AEAAJPEFBU_ITEMID_CHILD@@PEAUtagPROPVARIANT@@@Z; CContentDirectoryFolder::_GetItemDate(_ITEMID_CHILD const *,tagPROPVARIANT *)
0x180008361  jmp     loc_1800083F2
0x180008366  lea     rdx, PKEY_ItemNameDisplay
0x18000836d  mov     rcx, rsi
0x180008370  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x180008375  test    eax, eax
0x180008377  jz      short loc_18000838E
0x180008379  lea     r8, [rbp+ppropvar]
0x18000837d  lea     rdx, PKEY_ItemName
0x180008384  mov     rcx, rdi
0x180008387  call    ?GetPropertyFromIDList@?$CItemIDFactory@UCDSFOLDER_ITEMID@@$0EFBCCCCC@@@SAJPEFBU_ITEMIDLIST_RELATIVE@@AEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z; CItemIDFactory<CDSFOLDER_ITEMID,1158816290>::GetPropertyFromIDList(_ITEMIDLIST_RELATIVE const *,_tagpropertykey const &,tagPROPVARIANT *)
0x18000838c  jmp     short loc_1800083F2
0x18000838e  lea     rdx, PKEY_ItemType
0x180008395  mov     rcx, rsi
0x180008398  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x18000839d  test    eax, eax
0x18000839f  jz      short loc_1800083AF
0x1800083a1  lea     r8, [rbp+ppropvar]; struct tagPROPVARIANT *
0x1800083a5  mov     rdx, rdi; struct _ITEMID_CHILD *
0x1800083a8  call    ?_GetItemTypeProperty@CContentDirectoryFolder@@AEAAJPEFBU_ITEMID_CHILD@@PEAUtagPROPVARIANT@@@Z; CContentDirectoryFolder::_GetItemTypeProperty(_ITEMID_CHILD const *,tagPROPVARIANT *)
0x1800083ad  jmp     short loc_1800083F2
0x1800083af  lea     rdx, PKEY_ItemTypeText
0x1800083b6  mov     rcx, rsi
0x1800083b9  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x1800083be  test    eax, eax
0x1800083c0  jz      short loc_1800083D0
0x1800083c2  lea     r8, [rbp+ppropvar]; struct tagPROPVARIANT *
0x1800083c6  mov     rdx, rdi; struct _ITEMID_CHILD *
0x1800083c9  call    ?_GetItemTypeTextProperty@CContentDirectoryFolder@@AEAAJPEFBU_ITEMID_CHILD@@PEAUtagPROPVARIANT@@@Z; CContentDirectoryFolder::_GetItemTypeTextProperty(_ITEMID_CHILD const *,tagPROPVARIANT *)
0x1800083ce  jmp     short loc_1800083F2
0x1800083d0  lea     rdx, PKEY_ThumbnailStream
0x1800083d7  mov     rcx, rsi
0x1800083da  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x1800083df  test    eax, eax
0x1800083e1  jz      short loc_1800083F4
0x1800083e3  lea     r8, [rbp+ppropvar]; struct tagPROPVARIANT *
0x1800083e7  mov     rdx, rdi; struct _ITEMID_CHILD *
0x1800083ea  mov     rcx, r15; this
0x1800083ed  call    ?_GetThumbnailStreamProperty@CContentDirectoryFolder@@AEAAJPEFBU_ITEMID_CHILD@@PEAUtagPROPVARIANT@@@Z; CContentDirectoryFolder::_GetThumbnailStreamProperty(_ITEMID_CHILD const *,tagPROPVARIANT *)
0x1800083f2  mov     ebx, eax
0x1800083f4  test    ebx, ebx
0x1800083f6  js      short loc_180008406
0x1800083f8  mov     rdx, r14; unsigned __int16 **
0x1800083fb  lea     rcx, [rbp+ppropvar]; this
0x1800083ff  call    ?GetAsOrStealString@CPropVariant@@QEAAJPEAPEAG@Z; CPropVariant::GetAsOrStealString(ushort * *)
0x180008404  mov     ebx, eax
0x180008406  lea     rcx, [rbp+ppropvar]; pvar
0x18000840a  call    cs:__imp_PropVariantClear
0x180008410  mov     eax, ebx
0x180008412  add     rsp, 40h
0x180008416  pop     r15
0x180008418  pop     r14
0x18000841a  pop     r12
0x18000841c  pop     rdi
0x18000841d  pop     rsi
0x18000841e  pop     rbx
0x18000841f  pop     rbp
0x180008420  retn
```
