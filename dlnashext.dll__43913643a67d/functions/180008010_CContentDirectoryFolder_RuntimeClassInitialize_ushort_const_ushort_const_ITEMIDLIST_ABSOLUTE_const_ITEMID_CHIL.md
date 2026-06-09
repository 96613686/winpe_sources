# CContentDirectoryFolder::RuntimeClassInitialize(ushort const *,ushort const *,_ITEMIDLIST_ABSOLUTE const *,_ITEMID_CHILD const *)

- ea: `0x180008010`
- end: `0x1800082ab`
- name: `?RuntimeClassInitialize@CContentDirectoryFolder@@QEAAJPEBG0PEBU_ITEMIDLIST_ABSOLUTE@@PEFBU_ITEMID_CHILD@@@Z`
- size: `667`
- prototype: `int(CContentDirectoryFolder *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const struct _ITEMIDLIST_ABSOLUTE *, const struct _ITEMID_CHILD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e8f0`

## callees

- `0x180008010`
- `0x1800082b4`
- `0x18000dbb8`
- `0x180015994`
- `0x18001681c`
- `0x1800199f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000808b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800080ec`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000816e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008292`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000808b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800080ec`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000816e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008292`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008038`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008046`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000822f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008255`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008276`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008038`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008046`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000822f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008255`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008276`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18000823c`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180008262`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18000823c`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180008262`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x1800080cb`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x18000812c`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x1800081ae`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x1800080cb`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x18000812c`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x1800081ae`

## pseudocode

```c
__int64 __fastcall CContentDirectoryFolder::RuntimeClassInitialize(
        CContentDirectoryFolder *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const struct _ITEMIDLIST_ABSOLUTE *a4,
        const struct _ITEMID_CHILD *a5)
{
  void *v6; // rcx
  void *v10; // rcx
  __int64 IsValid; // rax
  DWORD v12; // edx
  __int64 v13; // rax
  DWORD v14; // edx
  const unsigned __int16 *String; // rax
  int v16; // ecx
  int v17; // edx
  __int64 v18; // rax
  DWORD v19; // edx
  void *v20; // rcx
  HRESULT v21; // ebx
  void *v22; // rcx
  void *v23; // rcx
  PROPVARIANT pvar; // [rsp+50h] [rbp-68h] BYREF

  v6 = (void *)*((_QWORD *)this + 13);
  *((_QWORD *)this + 13) = 0;
  CoTaskMemFree(v6);
  v10 = (void *)*((_QWORD *)this + 12);
  *((_QWORD *)this + 12) = 0;
  CoTaskMemFree(v10);
  CContentDirectoryFolder::_GetString(this, a5, &PKEY_ItemClass, (unsigned __int16 **)this + 13);
  CContentDirectoryFolder::_GetString(this, a5, &PKEY_CDSObjectID, (unsigned __int16 **)this + 12);
  pvar.vt = 0;
  PropVariantClear(&pvar);
  memset(&pvar, 0, sizeof(pvar));
  IsValid = CItemIDFactory<CDSFOLDER_ITEMID,1158816290>::_IsValid(a5);
  if ( IsValid )
  {
    v12 = *(unsigned __int16 *)(IsValid + 10);
    if ( (_WORD)v12 )
    {
      if ( IsValid != -18
        && PSGetPropertyFromPropertyStorage((PCUSERIALIZEDPROPSTORAGE)(IsValid + 18), v12, &PKEY_SearchClass, &pvar) >= 0
        && pvar.vt )
      {
        *((_DWORD *)this + 32) = pvar.lVal;
      }
    }
  }
  PropVariantClear(&pvar);
  memset(&pvar, 0, sizeof(pvar));
  v13 = CItemIDFactory<CDSFOLDER_ITEMID,1158816290>::_IsValid(a5);
  if ( v13 )
  {
    v14 = *(unsigned __int16 *)(v13 + 10);
    if ( (_WORD)v14 )
    {
      if ( v13 != -18
        && PSGetPropertyFromPropertyStorage((PCUSERIALIZEDPROPSTORAGE)(v13 + 18), v14, &PKEY_Searchable, &pvar) >= 0
        && pvar.vt )
      {
        String = CPropVariant::GetString((CPropVariant *)&pvar);
        v16 = *String;
        v17 = 49 - v16;
        if ( v16 == 49 )
          v17 = -String[1];
        *((_BYTE *)this + 136) = v17 == 0;
      }
    }
  }
  PropVariantClear(&pvar);
  memset(&pvar, 0, sizeof(pvar));
  v18 = CItemIDFactory<CDSFOLDER_ITEMID,1158816290>::_IsValid(a5);
  if ( v18 )
  {
    v19 = *(unsigned __int16 *)(v18 + 10);
    if ( (_WORD)v19 )
    {
      if ( v18 != -18
        && PSGetPropertyFromPropertyStorage((PCUSERIALIZEDPROPSTORAGE)(v18 + 18), v19, &PKEY_SortCapabilities, &pvar) >= 0
        && pvar.vt == 19 )
      {
        *((_DWORD *)this + 33) = pvar.lVal;
      }
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_SSSDlD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (__int64)a3,
      *((_QWORD *)this + 12),
      *((_DWORD *)this + 32),
      *((_BYTE *)this + 136),
      *((_DWORD *)this + 33));
  }
  if ( !a2
    || (v20 = (void *)*((_QWORD *)this + 14),
        *((_QWORD *)this + 14) = 0,
        CoTaskMemFree(v20),
        v21 = SHStrDupW(a2, (LPWSTR *)this + 14),
        v21 >= 0) )
  {
    if ( !a3
      || (v22 = (void *)*((_QWORD *)this + 15),
          *((_QWORD *)this + 15) = 0,
          CoTaskMemFree(v22),
          v21 = SHStrDupW(a3, (LPWSTR *)this + 15),
          v21 >= 0) )
    {
      v23 = (void *)*((_QWORD *)this + 11);
      *((_QWORD *)this + 11) = 0;
      CoTaskMemFree(v23);
      v21 = CombineIDLists(a4, a5, (struct _ITEMIDLIST_ABSOLUTE **)this + 11);
    }
  }
  PropVariantClear(&pvar);
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x180008010  push    rbx
0x180008012  push    rbp
0x180008013  push    rsi
0x180008014  push    rdi
0x180008015  push    r12
0x180008017  push    r13
0x180008019  push    r14
0x18000801b  push    r15
0x18000801d  sub     rsp, 78h
0x180008021  mov     rsi, rcx
0x180008024  xor     r13d, r13d
0x180008027  mov     rcx, [rcx+68h]; pv
0x18000802b  mov     r12, r9
0x18000802e  mov     r15, r8
0x180008031  mov     rbp, rdx
0x180008034  mov     [rsi+68h], r13
0x180008038  call    cs:__imp_CoTaskMemFree
0x18000803e  mov     rcx, [rsi+60h]; pv
0x180008042  mov     [rsi+60h], r13
0x180008046  call    cs:__imp_CoTaskMemFree
0x18000804c  mov     rdi, [rsp+0B8h+arg_20]
0x180008054  lea     r9, [rsi+68h]; unsigned __int16 **
0x180008058  mov     rdx, rdi; struct _ITEMID_CHILD *
0x18000805b  lea     r8, PKEY_ItemClass; struct _tagpropertykey *
0x180008062  mov     rcx, rsi; this
0x180008065  call    ?_GetString@CContentDirectoryFolder@@AEAAJPEFBU_ITEMID_CHILD@@AEBU_tagpropertykey@@PEAPEAG@Z; CContentDirectoryFolder::_GetString(_ITEMID_CHILD const *,_tagpropertykey const &,ushort * *)
0x18000806a  lea     r9, [rsi+60h]; unsigned __int16 **
0x18000806e  mov     rdx, rdi; struct _ITEMID_CHILD *
0x180008071  lea     r8, PKEY_CDSObjectID; struct _tagpropertykey *
0x180008078  mov     rcx, rsi; this
0x18000807b  call    ?_GetString@CContentDirectoryFolder@@AEAAJPEFBU_ITEMID_CHILD@@AEBU_tagpropertykey@@PEAPEAG@Z; CContentDirectoryFolder::_GetString(_ITEMID_CHILD const *,_tagpropertykey const &,ushort * *)
0x180008080  lea     rcx, [rsp+0B8h+pvar]; pvar
0x180008085  mov     word ptr [rsp+0B8h+pvar], r13w
0x18000808b  call    cs:__imp_PropVariantClear
0x180008091  xor     eax, eax
0x180008093  xorps   xmm0, xmm0
0x180008096  mov     rcx, rdi
0x180008099  mov     qword ptr [rsp+0B8h+pvar+10h], rax
0x18000809e  movups  xmmword ptr [rsp+0B8h+pvar], xmm0
0x1800080a3  call    ?_IsValid@?$CItemIDFactory@UCDSFOLDER_ITEMID@@$0EFBCCCCC@@@CAPEFBUCHILDITEMID@1@PEFBU_ITEMIDLIST_RELATIVE@@@Z; CItemIDFactory<CDSFOLDER_ITEMID,1158816290>::_IsValid(_ITEMIDLIST_RELATIVE const *)
0x1800080a8  test    rax, rax
0x1800080ab  jz      short loc_1800080E7
0x1800080ad  movzx   edx, word ptr [rax+0Ah]; cb
0x1800080b1  test    dx, dx
0x1800080b4  jz      short loc_1800080E7
0x1800080b6  lea     rcx, [rax+12h]; psps
0x1800080ba  test    rcx, rcx
0x1800080bd  jz      short loc_1800080E7
0x1800080bf  lea     r9, [rsp+0B8h+pvar]; ppropvar
0x1800080c4  lea     r8, PKEY_SearchClass; rpkey
0x1800080cb  call    cs:__imp_PSGetPropertyFromPropertyStorage
0x1800080d1  test    eax, eax
0x1800080d3  js      short loc_1800080E7
0x1800080d5  cmp     word ptr [rsp+0B8h+pvar], r13w
0x1800080db  jz      short loc_1800080E7
0x1800080dd  mov     eax, dword ptr [rsp+0B8h+pvar+8]
0x1800080e1  mov     [rsi+80h], eax
0x1800080e7  lea     rcx, [rsp+0B8h+pvar]; pvar
0x1800080ec  call    cs:__imp_PropVariantClear
0x1800080f2  xor     eax, eax
0x1800080f4  xorps   xmm0, xmm0
0x1800080f7  mov     rcx, rdi
0x1800080fa  mov     qword ptr [rsp+0B8h+pvar+10h], rax
0x1800080ff  movups  xmmword ptr [rsp+0B8h+pvar], xmm0
0x180008104  call    ?_IsValid@?$CItemIDFactory@UCDSFOLDER_ITEMID@@$0EFBCCCCC@@@CAPEFBUCHILDITEMID@1@PEFBU_ITEMIDLIST_RELATIVE@@@Z; CItemIDFactory<CDSFOLDER_ITEMID,1158816290>::_IsValid(_ITEMIDLIST_RELATIVE const *)
0x180008109  test    rax, rax
0x18000810c  jz      short loc_180008169
0x18000810e  movzx   edx, word ptr [rax+0Ah]; cb
0x180008112  test    dx, dx
0x180008115  jz      short loc_180008169
0x180008117  lea     rcx, [rax+12h]; psps
0x18000811b  test    rcx, rcx
0x18000811e  jz      short loc_180008169
0x180008120  lea     r9, [rsp+0B8h+pvar]; ppropvar
0x180008125  lea     r8, PKEY_Searchable; rpkey
0x18000812c  call    cs:__imp_PSGetPropertyFromPropertyStorage
0x180008132  test    eax, eax
0x180008134  js      short loc_180008169
0x180008136  cmp     word ptr [rsp+0B8h+pvar], r13w
0x18000813c  jz      short loc_180008169
0x18000813e  lea     rcx, [rsp+0B8h+pvar]; this
0x180008143  call    ?GetString@CPropVariant@@QEBAPEBGXZ; CPropVariant::GetString(void)
0x180008148  mov     edx, 31h ; '1'
0x18000814d  movzx   ecx, word ptr [rax]
0x180008150  sub     edx, ecx
0x180008152  jnz     short loc_18000815E
0x180008154  movzx   eax, word ptr [rax+2]
0x180008158  movzx   edx, r13w
0x18000815c  sub     edx, eax
0x18000815e  test    edx, edx
0x180008160  setz    al
0x180008163  mov     [rsi+88h], al
0x180008169  lea     rcx, [rsp+0B8h+pvar]; pvar
0x18000816e  call    cs:__imp_PropVariantClear
0x180008174  xor     eax, eax
0x180008176  xorps   xmm0, xmm0
0x180008179  mov     rcx, rdi
0x18000817c  mov     qword ptr [rsp+0B8h+pvar+10h], rax
0x180008181  movups  xmmword ptr [rsp+0B8h+pvar], xmm0
0x180008186  call    ?_IsValid@?$CItemIDFactory@UCDSFOLDER_ITEMID@@$0EFBCCCCC@@@CAPEFBUCHILDITEMID@1@PEFBU_ITEMIDLIST_RELATIVE@@@Z; CItemIDFactory<CDSFOLDER_ITEMID,1158816290>::_IsValid(_ITEMIDLIST_RELATIVE const *)
0x18000818b  test    rax, rax
0x18000818e  jz      short loc_1800081CA
0x180008190  movzx   edx, word ptr [rax+0Ah]; cb
0x180008194  test    dx, dx
0x180008197  jz      short loc_1800081CA
0x180008199  lea     rcx, [rax+12h]; psps
0x18000819d  test    rcx, rcx
0x1800081a0  jz      short loc_1800081CA
0x1800081a2  lea     r9, [rsp+0B8h+pvar]; ppropvar
0x1800081a7  lea     r8, PKEY_SortCapabilities; rpkey
0x1800081ae  call    cs:__imp_PSGetPropertyFromPropertyStorage
0x1800081b4  test    eax, eax
0x1800081b6  js      short loc_1800081CA
0x1800081b8  cmp     word ptr [rsp+0B8h+pvar], 13h
0x1800081be  jnz     short loc_1800081CA
0x1800081c0  mov     eax, dword ptr [rsp+0B8h+pvar+8]
0x1800081c4  mov     [rsi+84h], eax
0x1800081ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800081d1  lea     rax, WPP_GLOBAL_Control
0x1800081d8  cmp     rcx, rax
0x1800081db  jz      short loc_180008222
0x1800081dd  test    byte ptr [rcx+1Ch], 40h
0x1800081e1  jz      short loc_180008222
0x1800081e3  cmp     byte ptr [rcx+19h], 4
0x1800081e7  jb      short loc_180008222
0x1800081e9  mov     eax, [rsi+84h]
0x1800081ef  mov     r9, rbp
0x1800081f2  movzx   edx, byte ptr [rsi+88h]
0x1800081f9  mov     rcx, [rcx+10h]; LoggerHandle
0x1800081fd  mov     dword ptr [rsp+0B8h+var_78], eax; char
0x180008201  mov     eax, [rsi+80h]
0x180008207  mov     dword ptr [rsp+0B8h+var_80], edx; char
0x18000820b  mov     dword ptr [rsp+0B8h+var_88], eax; char
0x18000820f  mov     rax, [rsi+60h]
0x180008213  mov     [rsp+0B8h+var_90], rax; __int64
0x180008218  mov     [rsp+0B8h+var_98], r15; __int64
0x18000821d  call    WPP_SF_SSSDlD
0x180008222  test    rbp, rbp
0x180008225  jz      short loc_180008248
0x180008227  mov     rcx, [rsi+70h]; pv
0x18000822b  mov     [rsi+70h], r13
0x18000822f  call    cs:__imp_CoTaskMemFree
0x180008235  lea     rdx, [rsi+70h]; ppwsz
0x180008239  mov     rcx, rbp; psz
0x18000823c  call    cs:__imp_SHStrDupW
0x180008242  mov     ebx, eax
0x180008244  test    eax, eax
0x180008246  js      short loc_18000828D
0x180008248  test    r15, r15
0x18000824b  jz      short loc_18000826E
0x18000824d  mov     rcx, [rsi+78h]; pv
0x180008251  mov     [rsi+78h], r13
0x180008255  call    cs:__imp_CoTaskMemFree
0x18000825b  lea     rdx, [rsi+78h]; ppwsz
0x18000825f  mov     rcx, r15; psz
0x180008262  call    cs:__imp_SHStrDupW
0x180008268  mov     ebx, eax
0x18000826a  test    eax, eax
0x18000826c  js      short loc_18000828D
0x18000826e  mov     rcx, [rsi+58h]; pv
0x180008272  mov     [rsi+58h], r13
0x180008276  call    cs:__imp_CoTaskMemFree
0x18000827c  lea     r8, [rsi+58h]; struct _ITEMIDLIST_ABSOLUTE **
0x180008280  mov     rdx, rdi; struct _ITEMIDLIST_RELATIVE *
0x180008283  mov     rcx, r12; struct _ITEMIDLIST_ABSOLUTE *
0x180008286  call    ?CombineIDLists@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@PEFBU_ITEMIDLIST_RELATIVE@@PEAPEAU1@@Z; CombineIDLists(_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_ABSOLUTE * *)
0x18000828b  mov     ebx, eax
0x18000828d  lea     rcx, [rsp+0B8h+pvar]; pvar
0x180008292  call    cs:__imp_PropVariantClear
0x180008298  mov     eax, ebx
0x18000829a  add     rsp, 78h
0x18000829e  pop     r15
0x1800082a0  pop     r14
0x1800082a2  pop     r13
0x1800082a4  pop     r12
0x1800082a6  pop     rdi
0x1800082a7  pop     rsi
0x1800082a8  pop     rbp
0x1800082a9  pop     rbx
0x1800082aa  retn
```
