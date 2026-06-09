# CContentDirectoryFolder::_GetQueryAssociations(_ITEMID_CHILD const *,_GUID const &,void * *)

- ea: `0x18000fda8`
- end: `0x18001001b`
- name: `?_GetQueryAssociations@CContentDirectoryFolder@@AEAAJPEFBU_ITEMID_CHILD@@AEBU_GUID@@PEAPEAX@Z`
- size: `627`
- prototype: `int(CContentDirectoryFolder *__hidden this, const struct _ITEMID_CHILD *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000fc50`

## callees

- `0x180001710`
- `0x18000ab30`
- `0x18000ab48`
- `0x18000c84c`
- `0x18000da0c`
- `0x18000de1c`
- `0x18000fda8`
- `0x180018354`
- `0x18001882c`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000ffec`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000ffec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ffc6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ffc6`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!AssocCreate` at `0x18000fe8b`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!AssocCreate` at `0x18000fe8b`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CContentDirectoryFolder::_GetQueryAssociations(
        CContentDirectoryFolder *this,
        const struct _ITEMID_CHILD *a2,
        const struct _GUID *a3,
        void **a4)
{
  CContentDirectoryFolder *v8; // rcx
  int ItemType; // ebx
  __int64 v10; // r8
  unsigned __int64 v11; // rsi
  __int64 v12; // r14
  const wchar_t *v13; // r8
  void *v14; // rbx
  __int64 (__fastcall *v15)(void *, GUID *, CLSID *); // rdi
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, __int64 *); // rbx
  int i; // edi
  unsigned __int64 j; // rdi
  __int64 v21; // [rsp+30h] [rbp-49h] BYREF
  void *ppv; // [rsp+38h] [rbp-41h] BYREF
  unsigned __int16 *v23[2]; // [rsp+40h] [rbp-39h] BYREF
  CLSID clsid; // [rsp+50h] [rbp-29h] BYREF
  __int64 v25; // [rsp+60h] [rbp-19h] BYREF
  unsigned __int64 v26; // [rsp+68h] [rbp-11h]
  __int64 v27; // [rsp+70h] [rbp-9h]
  int v28; // [rsp+78h] [rbp-1h]
  PROPVARIANT pvar; // [rsp+80h] [rbp+7h] BYREF

  LODWORD(v21) = 0;
  v23[0] = 0;
  pvar.vt = 0;
  if ( (int)CItemIDFactory<CDSFOLDER_ITEMID,1158816290>::GetPropertyFromIDList(a2, &PKEY_FileExtension, &pvar) >= 0 )
    CPropVariant::GetAsOrStealString((CPropVariant *)&pvar, v23);
  ItemType = CContentDirectoryFolder::_GetItemType(v8, a2, (enum CDS_ITEM_TYPE *)&v21);
  if ( ItemType >= 0 )
  {
    v25 = 0;
    v26 = 0;
    v27 = 0;
    v28 = 0;
    ItemType = CContentDirectoryFolder::_GetAssocProgID(this, a2, v10, (__int64)&v25, v23[0] == 0);
    if ( ItemType >= 0 )
    {
      ppv = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&ppv);
      clsid = CLSID_QueryAssociations;
      ItemType = AssocCreate(&clsid, &GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57, &ppv);
      v11 = v26;
      v12 = v25;
      if ( ItemType >= 0 )
      {
        if ( (_DWORD)v21 == 1 )
        {
          v13 = L"Folder";
        }
        else
        {
          v13 = v23[0];
          if ( !v23[0] || !*v23[0] )
            v13 = L"Unknown";
        }
        ItemType = (*(__int64 (__fastcall **)(void *, _QWORD, const wchar_t *, _QWORD, _QWORD))(*(_QWORD *)ppv + 24LL))(
                     ppv,
                     0,
                     v13,
                     0,
                     0);
        if ( ItemType >= 0 )
        {
          *(_QWORD *)&clsid.Data1 = 0;
          v14 = ppv;
          v15 = **(__int64 (__fastcall ***)(void *, GUID *, CLSID *))ppv;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&clsid);
          ItemType = v15(v14, &GUID_d8820afb_ada1_45db_bd57_cf29047ee2bf, &clsid);
          if ( ItemType >= 0 )
          {
            v21 = 0;
            v16 = *(_QWORD *)&clsid.Data1;
            v17 = *(__int64 (__fastcall **)(__int64, __int64 *))(**(_QWORD **)&clsid.Data1 + 32LL);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v21);
            ItemType = v17(v16, &v21);
            if ( ItemType >= 0 )
            {
              for ( i = v11 - 1; i >= 0; --i )
              {
                if ( i >= v11 )
                  ATL::AtlThrowImpl(-2147024809);
                (*(void (__fastcall **)(__int64, GUID *, _QWORD))(*(_QWORD *)v21 + 32LL))(
                  v21,
                  &GUID_9016d0dd_7c41_46cc_a664_bf22f7cb186a,
                  *(_QWORD *)(v12 + 8LL * i));
              }
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v21);
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&clsid);
          if ( ItemType >= 0 )
            ItemType = (**(__int64 (__fastcall ***)(void *, const struct _GUID *, void **))ppv)(ppv, a3, a4);
        }
      }
      for ( j = 0; j < v11; ++j )
        CoTaskMemFree(*(LPVOID *)(v12 + 8 * j));
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&ppv);
    }
    ATL::CAtlArray<unsigned short *,ATL::CElementTraits<unsigned short *>>::~CAtlArray<unsigned short *,ATL::CElementTraits<unsigned short *>>(&v25);
  }
  PropVariantClear(&pvar);
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(v23);
  return (unsigned int)ItemType;
}

```

## disassembly

```asm
0x18000fda8  push    rbp
0x18000fdaa  push    rbx
0x18000fdab  push    rsi
0x18000fdac  push    rdi
0x18000fdad  push    r12
0x18000fdaf  push    r14
0x18000fdb1  push    r15
0x18000fdb3  lea     rbp, [rsp-27h]
0x18000fdb8  sub     rsp, 0A0h
0x18000fdbf  mov     r15, r9
0x18000fdc2  mov     r12, r8
0x18000fdc5  mov     rdi, rdx
0x18000fdc8  mov     rsi, rcx
0x18000fdcb  mov     dword ptr [rbp+57h+var_A0], 0
0x18000fdd2  mov     [rbp+57h+var_90], 0
0x18000fdda  xor     eax, eax
0x18000fddc  mov     word ptr [rbp+57h+pvar], ax
0x18000fde0  lea     r8, [rbp+57h+pvar]
0x18000fde4  lea     rdx, PKEY_FileExtension
0x18000fdeb  mov     rcx, rdi
0x18000fdee  call    ?GetPropertyFromIDList@?$CItemIDFactory@UCDSFOLDER_ITEMID@@$0EFBCCCCC@@@SAJPEFBU_ITEMIDLIST_RELATIVE@@AEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z; CItemIDFactory<CDSFOLDER_ITEMID,1158816290>::GetPropertyFromIDList(_ITEMIDLIST_RELATIVE const *,_tagpropertykey const &,tagPROPVARIANT *)
0x18000fdf3  test    eax, eax
0x18000fdf5  js      short loc_18000FE04
0x18000fdf7  lea     rdx, [rbp+57h+var_90]; unsigned __int16 **
0x18000fdfb  lea     rcx, [rbp+57h+pvar]; this
0x18000fdff  call    ?GetAsOrStealString@CPropVariant@@QEAAJPEAPEAG@Z; CPropVariant::GetAsOrStealString(ushort * *)
0x18000fe04  lea     r8, [rbp+57h+var_A0]; enum CDS_ITEM_TYPE *
0x18000fe08  mov     rdx, rdi; struct _ITEMID_CHILD *
0x18000fe0b  call    ?_GetItemType@CContentDirectoryFolder@@AEAAJPEFBU_ITEMID_CHILD@@PEAW4CDS_ITEM_TYPE@@@Z; CContentDirectoryFolder::_GetItemType(_ITEMID_CHILD const *,CDS_ITEM_TYPE *)
0x18000fe10  mov     ebx, eax
0x18000fe12  test    eax, eax
0x18000fe14  js      loc_18000FFE8
0x18000fe1a  mov     [rbp+57h+var_70], 0
0x18000fe22  mov     [rbp+57h+var_68], 0
0x18000fe2a  mov     [rbp+57h+var_60], 0
0x18000fe32  mov     [rbp+57h+var_58], 0
0x18000fe39  xor     eax, eax
0x18000fe3b  cmp     [rbp+57h+var_90], rax
0x18000fe3f  setz    al
0x18000fe42  mov     dword ptr [rsp+0D0h+var_B0], eax
0x18000fe46  lea     r9, [rbp+57h+var_70]
0x18000fe4a  mov     rdx, rdi
0x18000fe4d  mov     rcx, rsi
0x18000fe50  call    ?_GetAssocProgID@CContentDirectoryFolder@@AEAAJPEFBU_ITEMID_CHILD@@W4CDS_ITEM_TYPE@@AEAV?$CAtlArray@PEAGV?$CElementTraits@PEAG@ATL@@@ATL@@H@Z; CContentDirectoryFolder::_GetAssocProgID(_ITEMID_CHILD const *,CDS_ITEM_TYPE,ATL::CAtlArray<ushort *,ATL::CElementTraits<ushort *>> &,int)
0x18000fe55  mov     ebx, eax
0x18000fe57  test    eax, eax
0x18000fe59  js      loc_18000FFDE
0x18000fe5f  mov     [rbp+57h+ppv], 0
0x18000fe67  lea     rcx, [rbp+57h+ppv]
0x18000fe6b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18000fe70  movups  xmm0, xmmword ptr cs:CLSID_QueryAssociations.Data1
0x18000fe77  movdqu  xmmword ptr [rbp+57h+clsid.Data1], xmm0
0x18000fe7c  lea     r8, [rbp+57h+ppv]; ppv
0x18000fe80  lea     rdx, _GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57; riid
0x18000fe87  lea     rcx, [rbp+57h+clsid]; clsid
0x18000fe8b  call    cs:__imp_AssocCreate
0x18000fe91  mov     ebx, eax
0x18000fe93  mov     rsi, [rbp+57h+var_68]
0x18000fe97  mov     r14, [rbp+57h+var_70]
0x18000fe9b  test    eax, eax
0x18000fe9d  js      loc_18000FFBB
0x18000fea3  cmp     dword ptr [rbp+57h+var_A0], 1
0x18000fea7  jnz     short loc_18000FEB2
0x18000fea9  lea     r8, Source; "Folder"
0x18000feb0  jmp     short loc_18000FECA
0x18000feb2  mov     r8, [rbp+57h+var_90]
0x18000feb6  test    r8, r8
0x18000feb9  jz      short loc_18000FEC3
0x18000febb  xor     eax, eax
0x18000febd  cmp     [r8], ax
0x18000fec1  jnz     short loc_18000FECA
0x18000fec3  lea     r8, aUnknown; "Unknown"
0x18000feca  mov     rcx, [rbp+57h+ppv]
0x18000fece  mov     rax, [rcx]
0x18000fed1  mov     [rsp+0D0h+var_B0], 0
0x18000feda  xor     r9d, r9d
0x18000fedd  xor     edx, edx
0x18000fedf  mov     rax, [rax+18h]
0x18000fee3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fee8  mov     ebx, eax
0x18000feea  test    eax, eax
0x18000feec  js      loc_18000FFBB
0x18000fef2  mov     qword ptr [rbp+57h+clsid.Data1], 0
0x18000fefa  mov     rbx, [rbp+57h+ppv]
0x18000fefe  mov     rax, [rbx]
0x18000ff01  mov     rdi, [rax]
0x18000ff04  lea     rcx, [rbp+57h+clsid]
0x18000ff08  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18000ff0d  lea     r8, [rbp+57h+clsid]
0x18000ff11  lea     rdx, _GUID_d8820afb_ada1_45db_bd57_cf29047ee2bf
0x18000ff18  mov     rcx, rbx
0x18000ff1b  mov     rax, rdi
0x18000ff1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff23  mov     ebx, eax
0x18000ff25  test    eax, eax
0x18000ff27  js      short loc_18000FF97
0x18000ff29  mov     [rbp+57h+var_A0], 0
0x18000ff31  mov     rdi, qword ptr [rbp+57h+clsid.Data1]
0x18000ff35  mov     rax, [rdi]
0x18000ff38  mov     rbx, [rax+20h]
0x18000ff3c  lea     rcx, [rbp+57h+var_A0]
0x18000ff40  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18000ff45  lea     rdx, [rbp+57h+var_A0]
0x18000ff49  mov     rcx, rdi
0x18000ff4c  mov     rax, rbx
0x18000ff4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff54  mov     ebx, eax
0x18000ff56  test    eax, eax
0x18000ff58  js      short loc_18000FF8D
0x18000ff5a  lea     edi, [rsi-1]
0x18000ff5d  test    edi, edi
0x18000ff5f  js      short loc_18000FF8D
0x18000ff61  movsxd  r8, edi
0x18000ff64  cmp     r8, rsi
0x18000ff67  jnb     loc_180010010
0x18000ff6d  mov     rcx, [rbp+57h+var_A0]
0x18000ff71  mov     rax, [rcx]
0x18000ff74  mov     r8, [r14+r8*8]
0x18000ff78  lea     rdx, _GUID_9016d0dd_7c41_46cc_a664_bf22f7cb186a
0x18000ff7f  mov     rax, [rax+20h]
0x18000ff83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff88  sub     edi, 1
0x18000ff8b  jns     short loc_18000FF61
0x18000ff8d  lea     rcx, [rbp+57h+var_A0]
0x18000ff91  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18000ff96  nop
0x18000ff97  lea     rcx, [rbp+57h+clsid]
0x18000ff9b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18000ffa0  test    ebx, ebx
0x18000ffa2  js      short loc_18000FFBB
0x18000ffa4  mov     rcx, [rbp+57h+ppv]
0x18000ffa8  mov     rax, [rcx]
0x18000ffab  mov     r8, r15
0x18000ffae  mov     rdx, r12
0x18000ffb1  mov     rax, [rax]
0x18000ffb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffb9  mov     ebx, eax
0x18000ffbb  xor     edi, edi
0x18000ffbd  test    rsi, rsi
0x18000ffc0  jz      short loc_18000FFD4
0x18000ffc2  mov     rcx, [r14+rdi*8]; pv
0x18000ffc6  call    cs:__imp_CoTaskMemFree
0x18000ffcc  inc     rdi
0x18000ffcf  cmp     rdi, rsi
0x18000ffd2  jb      short loc_18000FFC2
0x18000ffd4  lea     rcx, [rbp+57h+ppv]
0x18000ffd8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18000ffdd  nop
0x18000ffde  lea     rcx, [rbp+57h+var_70]
0x18000ffe2  call    ??1?$CAtlArray@PEAGV?$CElementTraits@PEAG@ATL@@@ATL@@QEAA@XZ; ATL::CAtlArray<ushort *,ATL::CElementTraits<ushort *>>::~CAtlArray<ushort *,ATL::CElementTraits<ushort *>>(void)
0x18000ffe7  nop
0x18000ffe8  lea     rcx, [rbp+57h+pvar]; pvar
0x18000ffec  call    cs:__imp_PropVariantClear
0x18000fff2  nop
0x18000fff3  lea     rcx, [rbp+57h+var_90]
0x18000fff7  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x18000fffc  mov     eax, ebx
0x18000fffe  add     rsp, 0A0h
0x180010005  pop     r15
0x180010007  pop     r14
0x180010009  pop     r12
0x18001000b  pop     rdi
0x18001000c  pop     rsi
0x18001000d  pop     rbx
0x18001000e  pop     rbp
0x18001000f  retn
0x180010010  mov     ecx, 80070057h; int
0x180010015  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
