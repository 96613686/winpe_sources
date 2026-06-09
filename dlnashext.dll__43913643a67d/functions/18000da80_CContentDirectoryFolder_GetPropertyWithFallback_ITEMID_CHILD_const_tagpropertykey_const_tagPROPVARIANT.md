# CContentDirectoryFolder::GetPropertyWithFallback(_ITEMID_CHILD const *,_tagpropertykey const &,tagPROPVARIANT *)

- ea: `0x18000da80`
- end: `0x18000dbaf`
- name: `?GetPropertyWithFallback@CContentDirectoryFolder@@QEAAJPEFBU_ITEMID_CHILD@@AEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z`
- size: `303`
- prototype: `int(CContentDirectoryFolder *__hidden this, const struct _ITEMID_CHILD *, const struct _tagpropertykey *, struct tagPROPVARIANT *)`
- caller_count: `4`
- callee_count: `8`
- tags: ``

## callers

- `0x1800159c0`
- `0x1800161f0`
- `0x1800162e0`
- `0x1800285e0`

## callees

- `0x18000a4a0`
- `0x18000da0c`
- `0x18000da80`
- `0x18000dbb8`
- `0x1800187b8`
- `0x180018864`
- `0x180018934`
- `0x180019370`

## import_xrefs

- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x18000dad1`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x18000dad1`

## pseudocode

```c
__int64 __fastcall CContentDirectoryFolder::GetPropertyWithFallback(
        CContentDirectoryFolder *this,
        const struct _ITEMID_CHILD *a2,
        const struct _tagpropertykey *a3,
        struct tagPROPVARIANT *a4)
{
  __int64 IsValid; // rax
  PROPVARIANT *v9; // r9
  HRESULT v10; // r8d
  CContentDirectoryFolder *v11; // rcx
  __int64 v13; // rcx
  CContentDirectoryFolder *v14; // rcx
  CContentDirectoryFolder *v15; // rcx

  *(_OWORD *)&a4->vt = 0;
  a4->bstrblobVal.pData = 0;
  IsValid = CItemIDFactory<CDSFOLDER_ITEMID,1158816290>::_IsValid(a2);
  if ( !IsValid
    || !*(_WORD *)(IsValid + 10)
    || (v10 = -2147024809, IsValid != -18)
    && (v10 = PSGetPropertyFromPropertyStorage(
                (PCUSERIALIZEDPROPSTORAGE)(IsValid + 18),
                *(unsigned __int16 *)(IsValid + 10),
                a3,
                v9),
        v10 >= 0)
    && !a4->vt
    || v10 < 0
    || !a4->vt )
  {
    if ( (unsigned int)operator==(a3, &PKEY_ItemDate) )
      return (unsigned int)CContentDirectoryFolder::_GetItemDate(v11, a2, a4);
    if ( (unsigned int)operator==(v11, &PKEY_ItemNameDisplay) )
      return (unsigned int)CItemIDFactory<CDSFOLDER_ITEMID,1158816290>::GetPropertyFromIDList(a2, &PKEY_ItemName, a4);
    if ( (unsigned int)operator==(v13, &PKEY_ItemType) )
      return (unsigned int)CContentDirectoryFolder::_GetItemTypeProperty(v14, a2, a4);
    if ( (unsigned int)operator==(v14, &PKEY_ItemTypeText) )
      return (unsigned int)CContentDirectoryFolder::_GetItemTypeTextProperty(v15, a2, a4);
    if ( (unsigned int)operator==(v15, &PKEY_ThumbnailStream) )
      return (unsigned int)CContentDirectoryFolder::_GetThumbnailStreamProperty(this, a2, a4);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000da80  push    rbx
0x18000da82  push    rbp
0x18000da83  push    rsi
0x18000da84  push    rdi
0x18000da85  push    r14
0x18000da87  sub     rsp, 20h
0x18000da8b  xor     eax, eax
0x18000da8d  xorps   xmm0, xmm0
0x18000da90  movups  xmmword ptr [r9], xmm0
0x18000da94  mov     rbp, rcx
0x18000da97  mov     [r9+10h], rax
0x18000da9b  mov     rcx, rdx
0x18000da9e  mov     rbx, r9
0x18000daa1  mov     rsi, r8
0x18000daa4  mov     rdi, rdx
0x18000daa7  call    ?_IsValid@?$CItemIDFactory@UCDSFOLDER_ITEMID@@$0EFBCCCCC@@@CAPEFBUCHILDITEMID@1@PEFBU_ITEMIDLIST_RELATIVE@@@Z; CItemIDFactory<CDSFOLDER_ITEMID,1158816290>::_IsValid(_ITEMIDLIST_RELATIVE const *)
0x18000daac  xor     r14d, r14d
0x18000daaf  test    rax, rax
0x18000dab2  jz      short loc_18000DAFC
0x18000dab4  cmp     [rax+0Ah], r14w
0x18000dab9  jz      short loc_18000DAFC
0x18000dabb  lea     rcx, [rax+12h]; psps
0x18000dabf  mov     r8d, 80070057h
0x18000dac5  test    rcx, rcx
0x18000dac8  jz      short loc_18000DAEC
0x18000daca  movzx   edx, word ptr [rax+0Ah]; cb
0x18000dace  mov     r8, rsi; rpkey
0x18000dad1  call    cs:__imp_PSGetPropertyFromPropertyStorage
0x18000dad7  mov     r8d, eax
0x18000dada  test    eax, eax
0x18000dadc  js      short loc_18000DAEC
0x18000dade  cmp     [rbx], r14w
0x18000dae2  jnz     short loc_18000DAEC
0x18000dae4  mov     r8d, 80070648h
0x18000daea  jmp     short loc_18000DB02
0x18000daec  test    r8d, r8d
0x18000daef  js      short loc_18000DB02
0x18000daf1  cmp     [rbx], r14w
0x18000daf5  jz      short loc_18000DB02
0x18000daf7  jmp     loc_18000DBA1
0x18000dafc  mov     r8d, 80070057h
0x18000db02  lea     rdx, PKEY_ItemDate
0x18000db09  mov     rcx, rsi
0x18000db0c  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x18000db11  test    eax, eax
0x18000db13  jz      short loc_18000DB22
0x18000db15  mov     r8, rbx; struct tagPROPVARIANT *
0x18000db18  mov     rdx, rdi; struct _ITEMID_CHILD *
0x18000db1b  call    ?_GetItemDate@CContentDirectoryFolder@@AEAAJPEFBU_ITEMID_CHILD@@PEAUtagPROPVARIANT@@@Z; CContentDirectoryFolder::_GetItemDate(_ITEMID_CHILD const *,tagPROPVARIANT *)
0x18000db20  jmp     short loc_18000DB9E
0x18000db22  lea     rdx, PKEY_ItemNameDisplay
0x18000db29  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x18000db2e  test    eax, eax
0x18000db30  jz      short loc_18000DB46
0x18000db32  mov     r8, rbx
0x18000db35  lea     rdx, PKEY_ItemName
0x18000db3c  mov     rcx, rdi
0x18000db3f  call    ?GetPropertyFromIDList@?$CItemIDFactory@UCDSFOLDER_ITEMID@@$0EFBCCCCC@@@SAJPEFBU_ITEMIDLIST_RELATIVE@@AEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z; CItemIDFactory<CDSFOLDER_ITEMID,1158816290>::GetPropertyFromIDList(_ITEMIDLIST_RELATIVE const *,_tagpropertykey const &,tagPROPVARIANT *)
0x18000db44  jmp     short loc_18000DB9E
0x18000db46  lea     rdx, PKEY_ItemType
0x18000db4d  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x18000db52  test    eax, eax
0x18000db54  jz      short loc_18000DB63
0x18000db56  mov     r8, rbx; struct tagPROPVARIANT *
0x18000db59  mov     rdx, rdi; struct _ITEMID_CHILD *
0x18000db5c  call    ?_GetItemTypeProperty@CContentDirectoryFolder@@AEAAJPEFBU_ITEMID_CHILD@@PEAUtagPROPVARIANT@@@Z; CContentDirectoryFolder::_GetItemTypeProperty(_ITEMID_CHILD const *,tagPROPVARIANT *)
0x18000db61  jmp     short loc_18000DB9E
0x18000db63  lea     rdx, PKEY_ItemTypeText
0x18000db6a  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x18000db6f  test    eax, eax
0x18000db71  jz      short loc_18000DB80
0x18000db73  mov     r8, rbx; struct tagPROPVARIANT *
0x18000db76  mov     rdx, rdi; struct _ITEMID_CHILD *
0x18000db79  call    ?_GetItemTypeTextProperty@CContentDirectoryFolder@@AEAAJPEFBU_ITEMID_CHILD@@PEAUtagPROPVARIANT@@@Z; CContentDirectoryFolder::_GetItemTypeTextProperty(_ITEMID_CHILD const *,tagPROPVARIANT *)
0x18000db7e  jmp     short loc_18000DB9E
0x18000db80  lea     rdx, PKEY_ThumbnailStream
0x18000db87  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x18000db8c  test    eax, eax
0x18000db8e  jz      short loc_18000DBA1
0x18000db90  mov     r8, rbx; struct tagPROPVARIANT *
0x18000db93  mov     rdx, rdi; struct _ITEMID_CHILD *
0x18000db96  mov     rcx, rbp; this
0x18000db99  call    ?_GetThumbnailStreamProperty@CContentDirectoryFolder@@AEAAJPEFBU_ITEMID_CHILD@@PEAUtagPROPVARIANT@@@Z; CContentDirectoryFolder::_GetThumbnailStreamProperty(_ITEMID_CHILD const *,tagPROPVARIANT *)
0x18000db9e  mov     r8d, eax
0x18000dba1  mov     eax, r8d
0x18000dba4  add     rsp, 20h
0x18000dba8  pop     r14
0x18000dbaa  pop     rdi
0x18000dbab  pop     rsi
0x18000dbac  pop     rbp
0x18000dbad  pop     rbx
0x18000dbae  retn
```
