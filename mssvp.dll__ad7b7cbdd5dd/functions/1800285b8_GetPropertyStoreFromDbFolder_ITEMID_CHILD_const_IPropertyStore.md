# GetPropertyStoreFromDbFolder(_ITEMID_CHILD const *,IPropertyStore * *)

- ea: `0x1800285b8`
- end: `0x18002869a`
- name: `?GetPropertyStoreFromDbFolder@@YAJPEFBU_ITEMID_CHILD@@PEAPEAUIPropertyStore@@@Z`
- size: `226`
- prototype: `__int64 __fastcall(const struct _ITEMID_CHILD *, struct IPropertyStore **)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180015bc0`
- `0x18001fd10`

## callees

- `0x1800047b0`
- `0x180005210`
- `0x1800285b8`
- `0x180028788`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180028676`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180028676`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromIDList` at `0x180028635`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromIDList` at `0x180028635`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetPropertyStoreFromDbFolder(const struct _ITEMID_CHILD *a1, struct IPropertyStore **a2)
{
  HRESULT v3; // ebx
  struct tagPROPVARIANT pvar; // [rsp+30h] [rbp-40h] BYREF
  _OWORD v6[2]; // [rsp+48h] [rbp-28h] BYREF
  __int64 v7; // [rsp+68h] [rbp-8h]
  void *ppv; // [rsp+88h] [rbp+18h] BYREF

  *a2 = 0;
  memset(v6, 0, sizeof(v6));
  v7 = 0;
  memset(&pvar, 0, sizeof(pvar));
  v3 = CPidlMgr::PropVariantFromPIDL((CPidlMgr *)v6, a1, &PKEY_DBFolderPidl, &pvar);
  if ( v3 >= 0 )
  {
    if ( pvar.vt == 65 )
    {
      ppv = 0;
      v3 = SHCreateItemFromIDList(
             (LPCITEMIDLIST)pvar.bstrblobVal.pData,
             &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93,
             &ppv);
      if ( v3 >= 0 )
        v3 = (*(__int64 (__fastcall **)(void *, __int64, GUID *, struct IPropertyStore **))(*(_QWORD *)ppv + 64LL))(
               ppv,
               96,
               &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
               a2);
      ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>((__int64 *)&ppv);
    }
    else
    {
      v3 = -2147467259;
    }
  }
  PropVariantClear((PROPVARIANT *)&pvar);
  CPidlMgr::~CPidlMgr((CPidlMgr *)v6);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800285b8  mov     [rsp-8+arg_0], rbx
0x1800285bd  mov     [rsp-8+arg_10], rdi
0x1800285c2  push    rbp
0x1800285c3  mov     rbp, rsp
0x1800285c6  sub     rsp, 70h
0x1800285ca  mov     rdi, rdx
0x1800285cd  mov     qword ptr [rdx], 0
0x1800285d4  xorps   xmm0, xmm0
0x1800285d7  movdqu  [rbp+var_28], xmm0
0x1800285dc  xorps   xmm1, xmm1
0x1800285df  movdqu  [rbp+var_18], xmm1
0x1800285e4  mov     [rbp+var_8], 0
0x1800285ec  xor     eax, eax
0x1800285ee  movups  xmmword ptr [rbp+pvar], xmm0
0x1800285f2  mov     [rbp+pidl], rax
0x1800285f6  lea     r9, [rbp+pvar]; struct tagPROPVARIANT *
0x1800285fa  lea     r8, PKEY_DBFolderPidl; struct _tagpropertykey *
0x180028601  mov     rdx, rcx; struct _ITEMIDLIST_RELATIVE *
0x180028604  lea     rcx, [rbp+var_28]; this
0x180028608  call    ?PropVariantFromPIDL@CPidlMgr@@QEAAJPEFBU_ITEMIDLIST_RELATIVE@@PEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z; CPidlMgr::PropVariantFromPIDL(_ITEMIDLIST_RELATIVE const *,_tagpropertykey const *,tagPROPVARIANT *)
0x18002860d  mov     ebx, eax
0x18002860f  test    eax, eax
0x180028611  js      short loc_180028672
0x180028613  mov     eax, 41h ; 'A'
0x180028618  cmp     ax, word ptr [rbp+pvar]
0x18002861c  jnz     short loc_18002866D
0x18002861e  mov     [rbp+ppv], 0
0x180028626  lea     r8, [rbp+ppv]; ppv
0x18002862a  lea     rdx, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x180028631  mov     rcx, [rbp+pidl]; pidl
0x180028635  call    cs:__imp_SHCreateItemFromIDList
0x18002863b  mov     ebx, eax
0x18002863d  test    eax, eax
0x18002863f  js      short loc_180028662
0x180028641  mov     rcx, [rbp+ppv]
0x180028645  mov     rax, [rcx]
0x180028648  mov     r9, rdi
0x18002864b  lea     r8, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x180028652  mov     edx, 60h ; '`'
0x180028657  mov     rax, [rax+40h]
0x18002865b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028660  mov     ebx, eax
0x180028662  lea     rcx, [rbp+ppv]
0x180028666  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x18002866b  jmp     short loc_180028672
0x18002866d  mov     ebx, 80004005h
0x180028672  lea     rcx, [rbp+pvar]; pvar
0x180028676  call    cs:__imp_PropVariantClear
0x18002867c  nop
0x18002867d  lea     rcx, [rbp+var_28]; this
0x180028681  call    ??1CPidlMgr@@QEAA@XZ; CPidlMgr::~CPidlMgr(void)
0x180028686  mov     eax, ebx
0x180028688  lea     r11, [rsp+70h+var_s0]
0x18002868d  mov     rbx, [r11+10h]
0x180028691  mov     rdi, [r11+20h]
0x180028695  mov     rsp, r11
0x180028698  pop     rbp
0x180028699  retn
```
