# CContentDirectoryFolder::_GetThumbnailStreamProperty(_ITEMID_CHILD const *,tagPROPVARIANT *)

- ea: `0x180019370`
- end: `0x180019496`
- name: `?_GetThumbnailStreamProperty@CContentDirectoryFolder@@AEAAJPEFBU_ITEMID_CHILD@@PEAUtagPROPVARIANT@@@Z`
- size: `294`
- prototype: `__int64 __fastcall(CContentDirectoryFolder *__hidden this, const struct _ITEMID_CHILD *, struct tagPROPVARIANT *)`
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800082b4`
- `0x18000da80`

## callees

- `0x180001710`
- `0x18000ab48`
- `0x18000da0c`
- `0x18000de1c`
- `0x180011204`
- `0x180014f68`
- `0x180017330`
- `0x180019370`
- `0x18002c988`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001947b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001947b`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CContentDirectoryFolder::_GetThumbnailStreamProperty(
        CContentDirectoryFolder *this,
        const struct _ITEMID_CHILD *a2,
        struct tagPROPVARIANT *a3)
{
  int PropertyFromIDList; // ebx
  LARGE_INTEGER v7; // rcx
  LARGE_INTEGER v9; // [rsp+20h] [rbp-30h] BYREF
  unsigned __int16 *v10; // [rsp+28h] [rbp-28h] BYREF
  void *v11; // [rsp+30h] [rbp-20h] BYREF
  PROPVARIANT pvar; // [rsp+38h] [rbp-18h] BYREF
  void *v13; // [rsp+88h] [rbp+38h] BYREF

  pvar.vt = 0;
  *(_OWORD *)&a3->vt = 0;
  a3->bstrblobVal.pData = 0;
  PropertyFromIDList = CItemIDFactory<CDSFOLDER_ITEMID,1158816290>::GetPropertyFromIDList(a2, &PKEY_ItemClass, &pvar);
  if ( PropertyFromIDList >= 0 )
  {
    v10 = 0;
    PropertyFromIDList = CPropVariant::GetAsOrStealString((CPropVariant *)&pvar, &v10);
    if ( PropertyFromIDList >= 0 )
    {
      if ( (unsigned int)CCDSResultsParser::GetMediaTypeFromClass(v10) == 8 )
      {
        PropertyFromIDList = -2147023288;
      }
      else
      {
        v13 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((__int64 *)&v13);
        if ( (int)CContentDirectoryFolder::_GetThumbnailProvider(
                    this,
                    a2,
                    &GUID_e357fccd_a995_4576_b01f_234630154e96,
                    &v13) < 0 )
        {
          PropertyFromIDList = -2147023288;
        }
        else
        {
          v11 = v13;
          v9.QuadPart = 0;
          PropertyFromIDList = Microsoft::WRL::Details::MakeAndInitialize<COnDemandThumbnailStream,COnDemandThumbnailStream,CContentDirectoryThumbnailProvider * &>(
                                 &v9,
                                 &v11);
          if ( PropertyFromIDList < 0 )
          {
            v7 = v9;
          }
          else
          {
            a3->vt = 66;
            v7.QuadPart = 0;
            a3->hVal = v9;
          }
          if ( v7.QuadPart )
            Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IStream,Microsoft::WRL::FtmBase>::Release();
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((__int64 *)&v13);
      }
    }
    CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>((void **)&v10);
  }
  PropVariantClear(&pvar);
  return (unsigned int)PropertyFromIDList;
}

```

## disassembly

```asm
0x180019370  mov     [rsp-18h+arg_0], rbx
0x180019375  mov     [rsp-18h+arg_8], rsi
0x18001937a  push    rbp
0x18001937b  push    rdi
0x18001937c  push    r14
0x18001937e  mov     rbp, rsp
0x180019381  sub     rsp, 50h
0x180019385  mov     rdi, r8
0x180019388  mov     rsi, rdx
0x18001938b  mov     r14, rcx
0x18001938e  xor     eax, eax
0x180019390  mov     word ptr [rbp+pvar], ax
0x180019394  xorps   xmm0, xmm0
0x180019397  movups  xmmword ptr [r8], xmm0
0x18001939b  mov     [r8+10h], rax
0x18001939f  lea     r8, [rbp+pvar]
0x1800193a3  lea     rdx, PKEY_ItemClass
0x1800193aa  mov     rcx, rsi
0x1800193ad  call    ?GetPropertyFromIDList@?$CItemIDFactory@UCDSFOLDER_ITEMID@@$0EFBCCCCC@@@SAJPEFBU_ITEMIDLIST_RELATIVE@@AEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z; CItemIDFactory<CDSFOLDER_ITEMID,1158816290>::GetPropertyFromIDList(_ITEMIDLIST_RELATIVE const *,_tagpropertykey const &,tagPROPVARIANT *)
0x1800193b2  mov     ebx, eax
0x1800193b4  test    eax, eax
0x1800193b6  js      loc_180019477
0x1800193bc  mov     [rbp+var_28], 0
0x1800193c4  lea     rdx, [rbp+var_28]; unsigned __int16 **
0x1800193c8  lea     rcx, [rbp+pvar]; this
0x1800193cc  call    ?GetAsOrStealString@CPropVariant@@QEAAJPEAPEAG@Z; CPropVariant::GetAsOrStealString(ushort * *)
0x1800193d1  mov     ebx, eax
0x1800193d3  test    eax, eax
0x1800193d5  js      loc_18001946D
0x1800193db  mov     rcx, [rbp+var_28]
0x1800193df  call    ?GetMediaTypeFromClass@CCDSResultsParser@@SA?AW4_CDS_MEDIA_TYPE@@PEBG@Z; CCDSResultsParser::GetMediaTypeFromClass(ushort const *)
0x1800193e4  cmp     eax, 8
0x1800193e7  jz      short loc_180019468
0x1800193e9  mov     [rbp+arg_18], 0
0x1800193f1  lea     rcx, [rbp+arg_18]
0x1800193f5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x1800193fa  lea     r9, [rbp+arg_18]; void **
0x1800193fe  lea     r8, _GUID_e357fccd_a995_4576_b01f_234630154e96; struct _GUID *
0x180019405  mov     rdx, rsi; struct _ITEMID_CHILD *
0x180019408  mov     rcx, r14; this
0x18001940b  call    ?_GetThumbnailProvider@CContentDirectoryFolder@@AEAAJPEFBU_ITEMID_CHILD@@AEBU_GUID@@PEAPEAX@Z; CContentDirectoryFolder::_GetThumbnailProvider(_ITEMID_CHILD const *,_GUID const &,void * *)
0x180019410  test    eax, eax
0x180019412  js      short loc_180019458
0x180019414  mov     rax, [rbp+arg_18]
0x180019418  mov     [rbp+var_20], rax
0x18001941c  mov     [rbp+var_30], 0
0x180019424  lea     rdx, [rbp+var_20]
0x180019428  lea     rcx, [rbp+var_30]
0x18001942c  call    ??$MakeAndInitialize@VCOnDemandThumbnailStream@@V1@AEAPEAVCContentDirectoryThumbnailProvider@@@Details@WRL@Microsoft@@YAJPEAPEAVCOnDemandThumbnailStream@@AEAPEAVCContentDirectoryThumbnailProvider@@@Z; Microsoft::WRL::Details::MakeAndInitialize<COnDemandThumbnailStream,COnDemandThumbnailStream,CContentDirectoryThumbnailProvider * &>(COnDemandThumbnailStream * *,CContentDirectoryThumbnailProvider * &)
0x180019431  mov     ebx, eax
0x180019433  test    eax, eax
0x180019435  js      short loc_180019448
0x180019437  mov     word ptr [rdi], 42h ; 'B'
0x18001943c  mov     rax, [rbp+var_30]
0x180019440  xor     ecx, ecx
0x180019442  mov     [rdi+8], rax
0x180019446  jmp     short loc_18001944C
0x180019448  mov     rcx, [rbp+var_30]
0x18001944c  test    rcx, rcx
0x18001944f  jz      short loc_18001945D
0x180019451  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIStream@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IStream,Microsoft::WRL::FtmBase>::Release(void)
0x180019456  jmp     short loc_18001945D
0x180019458  mov     ebx, 80070648h
0x18001945d  lea     rcx, [rbp+arg_18]
0x180019461  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180019466  jmp     short loc_18001946D
0x180019468  mov     ebx, 80070648h
0x18001946d  lea     rcx, [rbp+var_28]
0x180019471  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180019476  nop
0x180019477  lea     rcx, [rbp+pvar]; pvar
0x18001947b  call    cs:__imp_PropVariantClear
0x180019481  mov     eax, ebx
0x180019483  mov     rbx, [rsp+50h+arg_0]
0x180019488  mov     rsi, [rsp+50h+arg_8]
0x18001948d  add     rsp, 50h
0x180019491  pop     r14
0x180019493  pop     rdi
0x180019494  pop     rbp
0x180019495  retn
```
