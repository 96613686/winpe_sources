# CMediaServerFolder::_GetItem(ushort const *,_ITEMID_CHILD * *)

- ea: `0x1800021b0`
- end: `0x1800024e1`
- name: `?_GetItem@CMediaServerFolder@@AEAAJPEBGPEAPEAU_ITEMID_CHILD@@@Z`
- size: `817`
- prototype: `__int64 __fastcall(CMediaServerFolder *__hidden this, const unsigned __int16 *, struct _ITEMID_CHILD **)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180001c70`
- `0x18001fdc0`

## callees

- `0x180001710`
- `0x180001bf0`
- `0x1800021b0`
- `0x180002aa4`
- `0x180008460`
- `0x180008780`
- `0x180014a00`
- `0x18001681c`
- `0x1800198d4`
- `0x18001ec9c`
- `0x180035010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800024c1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800024c1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800022d8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180002350`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800023dd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180002455`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800022d8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180002350`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800023dd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180002455`
- `PROPSYS!PropVariantCompareEx` at `0x1800022c0`
- `PROPSYS!PropVariantCompareEx` at `0x1800023c5`
- `PROPSYS!PropVariantCompareEx` at `0x1800022c0`
- `PROPSYS!PropVariantCompareEx` at `0x1800023c5`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CMediaServerFolder::_GetItem(
        CMediaServerFolder *this,
        const unsigned __int16 *a2,
        struct _ITEMID_CHILD **a3)
{
  _QWORD *v6; // rdi
  unsigned __int64 v7; // r14
  int MediaServerPropertyArray; // esi
  CTrackedMediaServerCollection *v9; // rbx
  unsigned __int64 i; // r12
  __int64 v11; // rbx
  const unsigned __int16 *String; // rax
  __int64 v13; // r10
  unsigned __int64 j; // r12
  __int64 v15; // rbx
  const unsigned __int16 *v16; // rax
  __int64 v17; // r10
  unsigned __int64 k; // rbx
  PROPVARIANT propvar1; // [rsp+20h] [rbp-50h] BYREF
  PROPVARIANT propvar2; // [rsp+38h] [rbp-38h] BYREF
  _QWORD *v22; // [rsp+50h] [rbp-20h] BYREF
  unsigned __int64 v23; // [rsp+58h] [rbp-18h]
  __int64 v24; // [rsp+60h] [rbp-10h]
  int v25; // [rsp+68h] [rbp-8h]
  int v26; // [rsp+B0h] [rbp+40h] BYREF
  __int64 v27; // [rsp+C0h] [rbp+50h] BYREF

  v6 = 0;
  v22 = 0;
  v7 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  *a3 = 0;
  if ( *((_QWORD *)this + 19)
    || (Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((char *)this + 152),
        MediaServerPropertyArray = CChangeListenerRegistrar::GetTrackedMediaServerCollection(
                                     (LPCRITICAL_SECTION)&CChangeListenerRegistrar::s_Singleton,
                                     (struct CTrackedMediaServerCollection **)this + 19),
        MediaServerPropertyArray >= 0) )
  {
    v9 = (CTrackedMediaServerCollection *)*((_QWORD *)this + 19);
    CTrackedMediaServerCollection::StartTracking(v9);
    MediaServerPropertyArray = CMediaServerCollectionChangeListener::GetMediaServerPropertyArray(
                                 *((_QWORD *)v9 + 2),
                                 &v22);
    v7 = v23;
    v6 = v22;
    if ( MediaServerPropertyArray >= 0 )
    {
      *(_QWORD *)&propvar2.vt = 31;
      *(_OWORD *)&propvar2.decVal.Lo32 = (unsigned __int64)a2;
      for ( i = 0; i < v7; ++i )
      {
        propvar1.vt = 0;
        v11 = v6[i];
        v27 = v11;
        if ( v11 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
        MediaServerPropertyArray = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v11 + 40LL))(
                                     v11,
                                     &PKEY_ParsingName,
                                     &propvar1);
        if ( MediaServerPropertyArray >= 0 && !PropVariantCompareEx(&propvar1, &propvar2, PVCU_DEFAULT, 0) )
        {
          v26 = 1;
          MediaServerPropertyArray = CItemIDFactory<MEDIASERVER_ITEMID,1159165815>::s_CreateItemID(
                                       &v26,
                                       v11,
                                       a3,
                                       *((_QWORD *)this + 13),
                                       *(_DWORD *)&propvar1.vt);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            String = CPropVariant::GetString((CPropVariant *)&propvar1);
            WPP_SF_S(*(_QWORD *)(v13 + 16), 10, &WPP_6632fb49d9da3da9a4f7f4d7d56b782d_Traceguids, String);
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v27);
          PropVariantClear(&propvar1);
          break;
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v27);
        PropVariantClear(&propvar1);
      }
      if ( MediaServerPropertyArray >= 0 && !*a3 )
      {
        for ( j = 0; j < v7; ++j )
        {
          propvar1.vt = 0;
          v15 = v6[j];
          v27 = v15;
          if ( v15 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
          MediaServerPropertyArray = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v15 + 40LL))(
                                       v15,
                                       &PKEY_DeviceDisplay_FriendlyName,
                                       &propvar1);
          if ( MediaServerPropertyArray >= 0 && !PropVariantCompareEx(&propvar1, &propvar2, PVCU_DEFAULT, 0) )
          {
            v26 = 1;
            MediaServerPropertyArray = CItemIDFactory<MEDIASERVER_ITEMID,1159165815>::s_CreateItemID(
                                         &v26,
                                         v15,
                                         a3,
                                         *((_QWORD *)this + 13),
                                         *(_DWORD *)&propvar1.vt);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              v16 = CPropVariant::GetString((CPropVariant *)&propvar1);
              WPP_SF_S(*(_QWORD *)(v17 + 16), 11, &WPP_6632fb49d9da3da9a4f7f4d7d56b782d_Traceguids, v16);
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v27);
            PropVariantClear(&propvar1);
            break;
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v27);
          PropVariantClear(&propvar1);
        }
        if ( MediaServerPropertyArray >= 0 && !*a3 )
        {
          MediaServerPropertyArray = -2147024829;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_6632fb49d9da3da9a4f7f4d7d56b782d_Traceguids);
          }
        }
      }
    }
  }
  if ( v6 )
  {
    for ( k = 0; k < v7; ++k )
      ATL::CComPtrBase<IPropertyStore>::~CComPtrBase<IPropertyStore>(&v6[k]);
    free(v6);
  }
  return (unsigned int)MediaServerPropertyArray;
}

```

## disassembly

```asm
0x1800021b0  mov     [rsp-38h+arg_8], rbx
0x1800021b5  push    rbp
0x1800021b6  push    rsi
0x1800021b7  push    rdi
0x1800021b8  push    r12
0x1800021ba  push    r13
0x1800021bc  push    r14
0x1800021be  push    r15
0x1800021c0  mov     rbp, rsp
0x1800021c3  sub     rsp, 70h
0x1800021c7  mov     r15, r8
0x1800021ca  mov     r12, rdx
0x1800021cd  mov     r13, rcx
0x1800021d0  xor     eax, eax
0x1800021d2  mov     edi, eax
0x1800021d4  mov     [rbp+var_20], rax
0x1800021d8  mov     r14d, eax
0x1800021db  mov     [rbp+var_18], rax
0x1800021df  mov     [rbp+var_10], rax
0x1800021e3  mov     [rbp+var_8], eax
0x1800021e6  mov     [r8], rax
0x1800021e9  cmp     [rcx+98h], rax
0x1800021f0  jnz     short loc_18000221B
0x1800021f2  add     rcx, 98h
0x1800021f9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x1800021fe  lea     rdx, [r13+98h]; struct CTrackedMediaServerCollection **
0x180002205  lea     rcx, ?s_Singleton@CChangeListenerRegistrar@@0V1@A; lpCriticalSection
0x18000220c  call    ?GetTrackedMediaServerCollection@CChangeListenerRegistrar@@QEAAJPEAPEAVCTrackedMediaServerCollection@@@Z; CChangeListenerRegistrar::GetTrackedMediaServerCollection(CTrackedMediaServerCollection * *)
0x180002211  mov     esi, eax
0x180002213  test    eax, eax
0x180002215  js      loc_1800024A1
0x18000221b  mov     rbx, [r13+98h]
0x180002222  mov     rcx, rbx; this
0x180002225  call    ?StartTracking@CTrackedMediaServerCollection@@QEAAXXZ; CTrackedMediaServerCollection::StartTracking(void)
0x18000222a  lea     rdx, [rbp+var_20]
0x18000222e  mov     rcx, [rbx+10h]
0x180002232  call    ?GetMediaServerPropertyArray@CMediaServerCollectionChangeListener@@QEAAJAEAV?$CInterfaceArray@UIPropertyStore@@$1?_GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99@@3U__s_GUID@@B@ATL@@@Z; CMediaServerCollectionChangeListener::GetMediaServerPropertyArray(ATL::CInterfaceArray<IPropertyStore,&__s_GUID const _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99> &)
0x180002237  mov     esi, eax
0x180002239  mov     r14, [rbp+var_18]
0x18000223d  mov     rdi, [rbp+var_20]
0x180002241  test    eax, eax
0x180002243  js      loc_1800024A1
0x180002249  xorps   xmm0, xmm0
0x18000224c  xor     eax, eax
0x18000224e  movups  xmmword ptr [rbp+propvar2], xmm0
0x180002252  mov     qword ptr [rbp+propvar2+10h], rax
0x180002256  mov     eax, 1Fh
0x18000225b  mov     word ptr [rbp+propvar2], ax
0x18000225f  mov     qword ptr [rbp+propvar2+8], r12
0x180002263  xor     r12d, r12d
0x180002266  cmp     r12, r14
0x180002269  jnb     loc_180002356
0x18000226f  xor     eax, eax
0x180002271  mov     word ptr [rbp+propvar1], ax
0x180002275  mov     rbx, [rdi+r12*8]
0x180002279  mov     [rbp+arg_10], rbx
0x18000227d  test    rbx, rbx
0x180002280  jz      short loc_180002292
0x180002282  mov     rax, [rbx]
0x180002285  mov     rcx, rbx
0x180002288  mov     rax, [rax+8]
0x18000228c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002291  nop
0x180002292  mov     rax, [rbx]
0x180002295  lea     r8, [rbp+propvar1]
0x180002299  lea     rdx, PKEY_ParsingName
0x1800022a0  mov     rcx, rbx
0x1800022a3  mov     rax, [rax+28h]
0x1800022a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022ac  mov     esi, eax
0x1800022ae  test    eax, eax
0x1800022b0  js      short loc_1800022CA
0x1800022b2  xor     r9d, r9d; flags
0x1800022b5  xor     r8d, r8d; unit
0x1800022b8  lea     rdx, [rbp+propvar2]; propvar2
0x1800022bc  lea     rcx, [rbp+propvar1]; propvar1
0x1800022c0  call    cs:__imp_PropVariantCompareEx
0x1800022c6  test    eax, eax
0x1800022c8  jz      short loc_1800022E3
0x1800022ca  lea     rcx, [rbp+arg_10]
0x1800022ce  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x1800022d3  nop
0x1800022d4  lea     rcx, [rbp+propvar1]; pvar
0x1800022d8  call    cs:__imp_PropVariantClear
0x1800022de  inc     r12
0x1800022e1  jmp     short loc_180002266
0x1800022e3  mov     [rbp+arg_0], 1
0x1800022ea  mov     r9, [r13+68h]
0x1800022ee  mov     r8, r15
0x1800022f1  mov     rdx, rbx
0x1800022f4  lea     rcx, [rbp+arg_0]
0x1800022f8  call    ?s_CreateItemID@?$CItemIDFactory@UMEDIASERVER_ITEMID@@$0EFBHHHHH@@@SAJPEFBUMEDIASERVER_ITEMID@@PEAUIPropertyStore@@PEAPEAU_ITEMID_CHILD@@PEAUIMalloc@@@Z; CItemIDFactory<MEDIASERVER_ITEMID,1159165815>::s_CreateItemID(MEDIASERVER_ITEMID const *,IPropertyStore *,_ITEMID_CHILD * *,IMalloc *)
0x1800022fd  mov     esi, eax
0x1800022ff  mov     r10, cs:WPP_GLOBAL_Control
0x180002306  lea     rbx, WPP_GLOBAL_Control
0x18000230d  cmp     r10, rbx
0x180002310  jz      short loc_180002342
0x180002312  test    byte ptr [r10+1Ch], 40h
0x180002317  jz      short loc_180002342
0x180002319  cmp     byte ptr [r10+19h], 4
0x18000231e  jb      short loc_180002342
0x180002320  lea     rcx, [rbp+propvar1]; this
0x180002324  call    ?GetString@CPropVariant@@QEBAPEBGXZ; CPropVariant::GetString(void)
0x180002329  mov     r9, rax
0x18000232c  mov     edx, 0Ah
0x180002331  lea     r8, WPP_6632fb49d9da3da9a4f7f4d7d56b782d_Traceguids
0x180002338  mov     rcx, [r10+10h]
0x18000233c  call    WPP_SF_S
0x180002341  nop
0x180002342  lea     rcx, [rbp+arg_10]
0x180002346  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18000234b  nop
0x18000234c  lea     rcx, [rbp+propvar1]; pvar
0x180002350  call    cs:__imp_PropVariantClear
0x180002356  test    esi, esi
0x180002358  js      loc_1800024A1
0x18000235e  cmp     qword ptr [r15], 0
0x180002362  jnz     loc_1800024A1
0x180002368  xor     r12d, r12d
0x18000236b  cmp     r12, r14
0x18000236e  jnb     loc_18000245D
0x180002374  xor     eax, eax
0x180002376  mov     word ptr [rbp+propvar1], ax
0x18000237a  mov     rbx, [rdi+r12*8]
0x18000237e  mov     [rbp+arg_10], rbx
0x180002382  test    rbx, rbx
0x180002385  jz      short loc_180002397
0x180002387  mov     rax, [rbx]
0x18000238a  mov     rcx, rbx
0x18000238d  mov     rax, [rax+8]
0x180002391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002396  nop
0x180002397  mov     rax, [rbx]
0x18000239a  lea     r8, [rbp+propvar1]
0x18000239e  lea     rdx, PKEY_DeviceDisplay_FriendlyName
0x1800023a5  mov     rcx, rbx
0x1800023a8  mov     rax, [rax+28h]
0x1800023ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023b1  mov     esi, eax
0x1800023b3  test    eax, eax
0x1800023b5  js      short loc_1800023CF
0x1800023b7  xor     r9d, r9d; flags
0x1800023ba  xor     r8d, r8d; unit
0x1800023bd  lea     rdx, [rbp+propvar2]; propvar2
0x1800023c1  lea     rcx, [rbp+propvar1]; propvar1
0x1800023c5  call    cs:__imp_PropVariantCompareEx
0x1800023cb  test    eax, eax
0x1800023cd  jz      short loc_1800023E8
0x1800023cf  lea     rcx, [rbp+arg_10]
0x1800023d3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x1800023d8  nop
0x1800023d9  lea     rcx, [rbp+propvar1]; pvar
0x1800023dd  call    cs:__imp_PropVariantClear
0x1800023e3  inc     r12
0x1800023e6  jmp     short loc_18000236B
0x1800023e8  mov     [rbp+arg_0], 1
0x1800023ef  mov     r9, [r13+68h]
0x1800023f3  mov     r8, r15
0x1800023f6  mov     rdx, rbx
0x1800023f9  lea     rcx, [rbp+arg_0]
0x1800023fd  call    ?s_CreateItemID@?$CItemIDFactory@UMEDIASERVER_ITEMID@@$0EFBHHHHH@@@SAJPEFBUMEDIASERVER_ITEMID@@PEAUIPropertyStore@@PEAPEAU_ITEMID_CHILD@@PEAUIMalloc@@@Z; CItemIDFactory<MEDIASERVER_ITEMID,1159165815>::s_CreateItemID(MEDIASERVER_ITEMID const *,IPropertyStore *,_ITEMID_CHILD * *,IMalloc *)
0x180002402  mov     esi, eax
0x180002404  mov     r10, cs:WPP_GLOBAL_Control
0x18000240b  lea     rbx, WPP_GLOBAL_Control
0x180002412  cmp     r10, rbx
0x180002415  jz      short loc_180002447
0x180002417  test    byte ptr [r10+1Ch], 40h
0x18000241c  jz      short loc_180002447
0x18000241e  cmp     byte ptr [r10+19h], 4
0x180002423  jb      short loc_180002447
0x180002425  lea     rcx, [rbp+propvar1]; this
0x180002429  call    ?GetString@CPropVariant@@QEBAPEBGXZ; CPropVariant::GetString(void)
0x18000242e  mov     r9, rax
0x180002431  mov     edx, 0Bh
0x180002436  lea     r8, WPP_6632fb49d9da3da9a4f7f4d7d56b782d_Traceguids
0x18000243d  mov     rcx, [r10+10h]
0x180002441  call    WPP_SF_S
0x180002446  nop
0x180002447  lea     rcx, [rbp+arg_10]
0x18000244b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180002450  nop
0x180002451  lea     rcx, [rbp+propvar1]; pvar
0x180002455  call    cs:__imp_PropVariantClear
0x18000245b  jmp     short loc_180002464
0x18000245d  lea     rbx, WPP_GLOBAL_Control
0x180002464  test    esi, esi
0x180002466  js      short loc_1800024A1
0x180002468  cmp     qword ptr [r15], 0
0x18000246c  jnz     short loc_1800024A1
0x18000246e  mov     esi, 80070043h
0x180002473  mov     rcx, cs:WPP_GLOBAL_Control
0x18000247a  cmp     rcx, rbx
0x18000247d  jz      short loc_1800024A1
0x18000247f  test    byte ptr [rcx+1Ch], 40h
0x180002483  jz      short loc_1800024A1
0x180002485  cmp     byte ptr [rcx+19h], 4
0x180002489  jb      short loc_1800024A1
0x18000248b  mov     edx, 0Ch
0x180002490  lea     r8, WPP_6632fb49d9da3da9a4f7f4d7d56b782d_Traceguids
0x180002497  mov     rcx, [rcx+10h]
0x18000249b  call    WPP_SF_
0x1800024a0  nop
0x1800024a1  test    rdi, rdi
0x1800024a4  jz      short loc_1800024C7
0x1800024a6  xor     ebx, ebx
0x1800024a8  test    r14, r14
0x1800024ab  jz      short loc_1800024BE
0x1800024ad  lea     rcx, [rdi+rbx*8]
0x1800024b1  call    ??1?$CComPtrBase@UIPropertyStore@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IPropertyStore>::~CComPtrBase<IPropertyStore>(void)
0x1800024b6  inc     rbx
0x1800024b9  cmp     rbx, r14
0x1800024bc  jb      short loc_1800024AD
0x1800024be  mov     rcx, rdi; Block
0x1800024c1  call    cs:__imp_free
0x1800024c7  mov     eax, esi
0x1800024c9  mov     rbx, [rsp+70h+arg_8]
0x1800024d1  add     rsp, 70h
0x1800024d5  pop     r15
0x1800024d7  pop     r14
0x1800024d9  pop     r13
0x1800024db  pop     r12
0x1800024dd  pop     rdi
0x1800024de  pop     rsi
0x1800024df  pop     rbp
0x1800024e0  retn
```
