# CMediaServerFolder::BindToObject(_ITEMIDLIST_RELATIVE const *,IBindCtx *,_GUID const &,void * *)

- ea: `0x180005f90`
- end: `0x18000634a`
- name: `?BindToObject@CMediaServerFolder@@UEAAJPEFBU_ITEMIDLIST_RELATIVE@@PEAUIBindCtx@@AEBU_GUID@@PEAPEAX@Z`
- size: `954`
- prototype: `int(CMediaServerFolder *__hidden this, const struct _ITEMIDLIST_RELATIVE *, struct IBindCtx *, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `9`
- tags: `reparse_path, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180001c70`
- `0x180013ed0`

## callees

- `0x180001710`
- `0x180005790`
- `0x180005f90`
- `0x180006350`
- `0x18000de1c`
- `0x18000e6b0`
- `0x18000e8f0`
- `0x180013edc`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800061fe`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006269`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800061fe`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006269`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000631a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006329`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000631a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006329`
- `api-ms-win-shell-namespace-l1-1-0!SHBindToFolderIDListParent` at `0x180006017`
- `api-ms-win-shell-namespace-l1-1-0!SHBindToFolderIDListParent` at `0x180006017`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x1800061d1`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x180006247`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x1800061d1`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x180006247`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180006110`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180006110`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CMediaServerFolder::BindToObject(
        IShellFolder *this,
        const struct _ITEMIDLIST_RELATIVE *a2,
        struct IBindCtx *a3,
        const struct _GUID *a4,
        void **ppv)
{
  void **v9; // r14
  _WORD *v10; // rdx
  HRESULT v11; // ebx
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  HRESULT AsOrStealString; // esi
  unsigned __int64 v17; // rax
  __int64 v18; // r15
  char *v19; // rbx
  __int64 IsValid; // rax
  DWORD v21; // edx
  __int64 v22; // rax
  DWORD v23; // edx
  char *v24; // rbx
  const struct _GUID *v25; // rcx
  void **v26; // rcx
  ITEMIDLIST *v27; // rcx
  char *v28; // [rsp+30h] [rbp-30h] BYREF
  const struct _ITEMIDLIST_RELATIVE *v29; // [rsp+38h] [rbp-28h] BYREF
  PROPVARIANT ppropvar; // [rsp+40h] [rbp-20h] BYREF
  LPCITEMIDLIST ppidlLast; // [rsp+98h] [rbp+38h] BYREF

  v9 = ppv;
  *ppv = 0;
  if ( !a2 || !*(_WORD *)a2 || (v10 = (_WORD *)((char *)a2 + *(unsigned __int16 *)a2)) == 0 || !*v10 )
  {
    v13 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&GUID_000214e6_0000_0000_c000_000000000046.Data1;
    if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&GUID_000214e6_0000_0000_c000_000000000046.Data1 )
      v13 = *(_QWORD *)a4->Data4 - *(_QWORD *)GUID_000214e6_0000_0000_c000_000000000046.Data4;
    if ( v13 )
    {
      v14 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1.Data1;
      if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1.Data1 )
        v14 = *(_QWORD *)a4->Data4 - *(_QWORD *)GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1.Data4;
      if ( v14 )
      {
        v15 = *(_QWORD *)&a4->Data1 - *(_QWORD *)&GUID_bc110b6d_57e8_4148_a9c6_91015ab2f3a5.Data1;
        if ( *(_QWORD *)&a4->Data1 == *(_QWORD *)&GUID_bc110b6d_57e8_4148_a9c6_91015ab2f3a5.Data1 )
          v15 = *(_QWORD *)a4->Data4 - *(_QWORD *)GUID_bc110b6d_57e8_4148_a9c6_91015ab2f3a5.Data4;
        if ( v15 )
          return 2147500034LL;
        AsOrStealString = -2147024809;
        if ( a2 )
        {
          v17 = *(unsigned __int16 *)a2;
          if ( (unsigned int)v17 >= 0x12 && *(_DWORD *)((char *)a2 + 6) == 1159165815 )
          {
            v18 = *((unsigned __int16 *)a2 + 5);
            if ( v17 >= v18 + 18 )
            {
              if ( (_WORD)v18 )
              {
                v19 = (char *)a2 + 18;
                if ( v19 )
                {
                  ppv = 0;
                  AsOrStealString = PSCreateMemoryPropertyStore(
                                      &GUID_e318ad57_0aa0_450f_aca5_6fab7103d917,
                                      (void **)&ppv);
                  if ( AsOrStealString >= 0 )
                  {
                    AsOrStealString = (*((__int64 (__fastcall **)(void **, char *, _QWORD))*ppv + 4))(
                                        ppv,
                                        v19,
                                        (unsigned int)v18);
                    if ( AsOrStealString >= 0 )
                    {
                      AsOrStealString = (*((__int64 (__fastcall **)(void **, __int64))*ppv + 3))(ppv, 1);
                      if ( AsOrStealString >= 0 )
                        AsOrStealString = (*(__int64 (__fastcall **)(void **, const struct _GUID *, void **))*ppv)(
                                            ppv,
                                            a4,
                                            v9);
                    }
                    (*((void (__fastcall **)(void **))*ppv + 2))(ppv);
                  }
                }
              }
            }
          }
        }
        return (unsigned int)AsOrStealString;
      }
    }
    v29 = a2;
    ppidlLast = 0;
    memset(&ppropvar, 0, sizeof(ppropvar));
    AsOrStealString = -2147024809;
    IsValid = CItemIDFactory<MEDIASERVER_ITEMID,1159165815>::_IsValid(a2);
    if ( IsValid )
    {
      v21 = *(unsigned __int16 *)(IsValid + 10);
      if ( (_WORD)v21 )
      {
        if ( IsValid != -18 )
        {
          AsOrStealString = PSGetPropertyFromPropertyStorage(
                              (PCUSERIALIZEDPROPSTORAGE)(IsValid + 18),
                              v21,
                              &PKEY_PNPX_GlobalIdentity,
                              &ppropvar);
          if ( AsOrStealString >= 0 )
          {
            if ( ppropvar.vt )
              AsOrStealString = CPropVariant::GetAsOrStealString(
                                  (CPropVariant *)&ppropvar,
                                  (unsigned __int16 **)&ppidlLast);
            else
              AsOrStealString = -2147023288;
          }
        }
      }
    }
    PropVariantClear(&ppropvar);
    if ( AsOrStealString < 0 )
    {
LABEL_55:
      v27 = (ITEMIDLIST *)ppidlLast;
      ppidlLast = 0;
      CoTaskMemFree(v27);
      return (unsigned int)AsOrStealString;
    }
    ppv = 0;
    memset(&ppropvar, 0, sizeof(ppropvar));
    v22 = CItemIDFactory<MEDIASERVER_ITEMID,1159165815>::_IsValid(a2);
    if ( v22 )
    {
      v23 = *(unsigned __int16 *)(v22 + 10);
      if ( (_WORD)v23 )
      {
        if ( v22 != -18
          && PSGetPropertyFromPropertyStorage(
               (PCUSERIALIZEDPROPSTORAGE)(v22 + 18),
               v23,
               &PKEY_DeviceDisplay_FriendlyName,
               &ppropvar) >= 0
          && ppropvar.vt )
        {
          CPropVariant::GetAsOrStealString((CPropVariant *)&ppropvar, (unsigned __int16 **)&ppv);
        }
      }
    }
    PropVariantClear(&ppropvar);
    v28 = 0;
    AsOrStealString = Microsoft::WRL::Details::MakeAndInitialize<CContentDirectoryFolder,CContentDirectoryFolder,CCoTaskMemPtr<unsigned short> &,CCoTaskMemPtr<unsigned short> &,CCoTaskMemPtr<_ITEMIDLIST_ABSOLUTE> &,_ITEMID_CHILD const __unaligned * &>(
                        (unsigned int)&v28,
                        (unsigned int)&ppidlLast,
                        (unsigned int)&ppv,
                        (int)this + 96,
                        (__int64)&v29);
    v24 = v28;
    if ( AsOrStealString >= 0 )
    {
      *v9 = 0;
      if ( (unsigned int)InlineIsEqualGUID(a4, &GUID_00000000_0000_0000_c000_000000000046) )
      {
        *v9 = v24;
        (*(void (__fastcall **)(char *))(*(_QWORD *)v24 + 8LL))(v24);
        AsOrStealString = 0;
        goto LABEL_52;
      }
      if ( (unsigned int)InlineIsEqualGUID(v25, &GUID_add8ba80_002b_11d0_8f0f_00c04fd7d062) )
      {
        *v9 = v24;
        AsOrStealString = 0;
LABEL_50:
        (*(void (__fastcall **)(void *))(*(_QWORD *)*v9 + 8LL))(*v9);
        goto LABEL_52;
      }
      AsOrStealString = Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::ChainInterfaces<IPersistFolder2,IPersistFolder,IPersist,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::ChainInterfaces<IShellFolder2,IShellFolder,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IThumbnailHandlerFactory,IProviderResolver,IExplorerPaneVisibility,IFileJunctionOptions,ISearchBoxSettings>::CanCastTo(
                          v24 + 8,
                          a4,
                          v9);
      if ( AsOrStealString >= 0 )
        goto LABEL_50;
    }
LABEL_52:
    if ( v24 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IDelegateFolder,Microsoft::WRL::ChainInterfaces<IPersistFolder2,IPersistFolder,IPersist,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::ChainInterfaces<IShellFolder2,IShellFolder,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IThumbnailHandlerFactory,IProviderResolver,IExplorerPaneVisibility,IFileJunctionOptions,ISearchBoxSettings>::Release(v24);
    v26 = ppv;
    ppv = 0;
    CoTaskMemFree(v26);
    goto LABEL_55;
  }
  ppv = 0;
  ppidlLast = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&ppv);
  if ( this == (IShellFolder *)16 )
    this = 0;
  v11 = SHBindToFolderIDListParent(
          this,
          (LPCITEMIDLIST)a2,
          &GUID_000214e6_0000_0000_c000_000000000046,
          (void **)&ppv,
          &ppidlLast);
  if ( v11 >= 0 )
    v11 = (*((__int64 (__fastcall **)(void **, LPCITEMIDLIST, struct IBindCtx *, const struct _GUID *, void **))*ppv + 5))(
            ppv,
            ppidlLast,
            a3,
            a4,
            v9);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&ppv);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180005f90  mov     [rsp-28h+arg_0], rbx
0x180005f95  mov     [rsp-28h+arg_10], rsi
0x180005f9a  push    rbp
0x180005f9b  push    rdi
0x180005f9c  push    r12
0x180005f9e  push    r14
0x180005fa0  push    r15
0x180005fa2  mov     rbp, rsp
0x180005fa5  sub     rsp, 60h
0x180005fa9  mov     rdi, r9
0x180005fac  mov     rsi, r8
0x180005faf  mov     rbx, rdx
0x180005fb2  mov     r15, rcx
0x180005fb5  xor     r12d, r12d
0x180005fb8  mov     r14, [rbp+ppv]
0x180005fbc  mov     [r14], r12
0x180005fbf  test    rdx, rdx
0x180005fc2  jz      loc_180006054
0x180005fc8  movzx   eax, word ptr [rdx]
0x180005fcb  test    ax, ax
0x180005fce  jz      loc_180006054
0x180005fd4  mov     edx, eax
0x180005fd6  add     rdx, rbx
0x180005fd9  jz      short loc_180006054
0x180005fdb  cmp     [rdx], r12w
0x180005fdf  jz      short loc_180006054
0x180005fe1  mov     [rbp+ppv], r12
0x180005fe5  mov     [rbp+arg_8], r12
0x180005fe9  lea     rcx, [rbp+ppv]
0x180005fed  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180005ff2  lea     rcx, [r15-10h]
0x180005ff6  test    rcx, rcx
0x180005ff9  cmovz   r15, r12
0x180005ffd  lea     rax, [rbp+arg_8]
0x180006001  mov     [rsp+60h+ppidlLast], rax; ppidlLast
0x180006006  lea     r9, [rbp+ppv]; ppv
0x18000600a  lea     r8, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x180006011  mov     rdx, rbx; pidl
0x180006014  mov     rcx, r15; psfRoot
0x180006017  call    cs:__imp_SHBindToFolderIDListParent
0x18000601d  mov     ebx, eax
0x18000601f  test    eax, eax
0x180006021  js      short loc_180006044
0x180006023  mov     rcx, [rbp+ppv]
0x180006027  mov     rax, [rcx]
0x18000602a  mov     [rsp+60h+ppidlLast], r14
0x18000602f  mov     r9, rdi
0x180006032  mov     r8, rsi
0x180006035  mov     rdx, [rbp+arg_8]
0x180006039  mov     rax, [rax+28h]
0x18000603d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006042  mov     ebx, eax
0x180006044  lea     rcx, [rbp+ppv]
0x180006048  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18000604d  mov     eax, ebx
0x18000604f  jmp     loc_180006331
0x180006054  mov     rax, [r9]
0x180006057  sub     rax, qword ptr cs:_GUID_000214e6_0000_0000_c000_000000000046.Data1
0x18000605e  jnz     short loc_18000606B
0x180006060  mov     rax, [r9+8]
0x180006064  sub     rax, qword ptr cs:_GUID_000214e6_0000_0000_c000_000000000046.Data4
0x18000606b  test    rax, rax
0x18000606e  jz      loc_18000618D
0x180006074  mov     rax, [r9]
0x180006077  sub     rax, qword ptr cs:_GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1.Data1
0x18000607e  jnz     short loc_18000608B
0x180006080  mov     rax, [r9+8]
0x180006084  sub     rax, qword ptr cs:_GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1.Data4
0x18000608b  test    rax, rax
0x18000608e  jz      loc_18000618D
0x180006094  mov     rax, [r9]
0x180006097  sub     rax, qword ptr cs:_GUID_bc110b6d_57e8_4148_a9c6_91015ab2f3a5.Data1
0x18000609e  jnz     short loc_1800060AB
0x1800060a0  mov     rax, [r9+8]
0x1800060a4  sub     rax, qword ptr cs:_GUID_bc110b6d_57e8_4148_a9c6_91015ab2f3a5.Data4
0x1800060ab  test    rax, rax
0x1800060ae  jnz     loc_180006183
0x1800060b4  mov     esi, 80070057h
0x1800060b9  test    rbx, rbx
0x1800060bc  jz      loc_18000632F
0x1800060c2  movzx   eax, word ptr [rbx]
0x1800060c5  cmp     eax, 12h
0x1800060c8  jb      loc_18000632F
0x1800060ce  cmp     dword ptr [rbx+6], 45177777h
0x1800060d5  jnz     loc_18000632F
0x1800060db  movzx   r15d, word ptr [rbx+0Ah]
0x1800060e0  lea     rcx, [r15+12h]
0x1800060e4  cmp     rax, rcx
0x1800060e7  jb      loc_18000632F
0x1800060ed  test    r15w, r15w
0x1800060f1  jz      loc_18000632F
0x1800060f7  add     rbx, 12h
0x1800060fb  jz      loc_18000632F
0x180006101  mov     [rbp+ppv], r12
0x180006105  lea     rdx, [rbp+ppv]; ppv
0x180006109  lea     rcx, _GUID_e318ad57_0aa0_450f_aca5_6fab7103d917; riid
0x180006110  call    cs:__imp_PSCreateMemoryPropertyStore
0x180006116  mov     esi, eax
0x180006118  test    eax, eax
0x18000611a  js      loc_18000632F
0x180006120  mov     rcx, [rbp+ppv]
0x180006124  mov     rax, [rcx]
0x180006127  mov     r8d, r15d
0x18000612a  mov     rdx, rbx
0x18000612d  mov     rax, [rax+20h]
0x180006131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006136  mov     esi, eax
0x180006138  test    eax, eax
0x18000613a  js      short loc_18000616E
0x18000613c  mov     rcx, [rbp+ppv]
0x180006140  mov     rax, [rcx]
0x180006143  mov     edx, 1
0x180006148  mov     rax, [rax+18h]
0x18000614c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006151  mov     esi, eax
0x180006153  test    eax, eax
0x180006155  js      short loc_18000616E
0x180006157  mov     rcx, [rbp+ppv]
0x18000615b  mov     rax, [rcx]
0x18000615e  mov     r8, r14
0x180006161  mov     rdx, rdi
0x180006164  mov     rax, [rax]
0x180006167  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000616c  mov     esi, eax
0x18000616e  mov     rcx, [rbp+ppv]
0x180006172  mov     rax, [rcx]
0x180006175  mov     rax, [rax+10h]
0x180006179  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000617e  jmp     loc_18000632F
0x180006183  mov     eax, 80004002h
0x180006188  jmp     loc_180006331
0x18000618d  mov     [rbp+var_28], rbx
0x180006191  mov     [rbp+arg_8], r12
0x180006195  xorps   xmm0, xmm0
0x180006198  xor     eax, eax
0x18000619a  movups  xmmword ptr [rbp+ppropvar], xmm0
0x18000619e  mov     qword ptr [rbp+ppropvar+10h], rax
0x1800061a2  mov     esi, 80070057h
0x1800061a7  mov     rcx, rbx
0x1800061aa  call    ?_IsValid@?$CItemIDFactory@UMEDIASERVER_ITEMID@@$0EFBHHHHH@@@CAPEFBUCHILDITEMID@1@PEFBU_ITEMIDLIST_RELATIVE@@@Z; CItemIDFactory<MEDIASERVER_ITEMID,1159165815>::_IsValid(_ITEMIDLIST_RELATIVE const *)
0x1800061af  test    rax, rax
0x1800061b2  jz      short loc_1800061FA
0x1800061b4  movzx   edx, word ptr [rax+0Ah]; cb
0x1800061b8  test    dx, dx
0x1800061bb  jz      short loc_1800061FA
0x1800061bd  lea     rcx, [rax+12h]; psps
0x1800061c1  test    rcx, rcx
0x1800061c4  jz      short loc_1800061FA
0x1800061c6  lea     r9, [rbp+ppropvar]; ppropvar
0x1800061ca  lea     r8, PKEY_PNPX_GlobalIdentity; rpkey
0x1800061d1  call    cs:__imp_PSGetPropertyFromPropertyStorage
0x1800061d7  mov     esi, eax
0x1800061d9  test    eax, eax
0x1800061db  js      short loc_1800061FA
0x1800061dd  cmp     word ptr [rbp+ppropvar], 0
0x1800061e2  jnz     short loc_1800061EB
0x1800061e4  mov     esi, 80070648h
0x1800061e9  jmp     short loc_1800061FA
0x1800061eb  lea     rdx, [rbp+arg_8]; unsigned __int16 **
0x1800061ef  lea     rcx, [rbp+ppropvar]; this
0x1800061f3  call    ?GetAsOrStealString@CPropVariant@@QEAAJPEAPEAG@Z; CPropVariant::GetAsOrStealString(ushort * *)
0x1800061f8  mov     esi, eax
0x1800061fa  lea     rcx, [rbp+ppropvar]; pvar
0x1800061fe  call    cs:__imp_PropVariantClear
0x180006204  test    esi, esi
0x180006206  js      loc_180006321
0x18000620c  mov     [rbp+ppv], r12
0x180006210  xorps   xmm0, xmm0
0x180006213  xor     eax, eax
0x180006215  movups  xmmword ptr [rbp+ppropvar], xmm0
0x180006219  mov     qword ptr [rbp+ppropvar+10h], rax
0x18000621d  mov     rcx, rbx
0x180006220  call    ?_IsValid@?$CItemIDFactory@UMEDIASERVER_ITEMID@@$0EFBHHHHH@@@CAPEFBUCHILDITEMID@1@PEFBU_ITEMIDLIST_RELATIVE@@@Z; CItemIDFactory<MEDIASERVER_ITEMID,1159165815>::_IsValid(_ITEMIDLIST_RELATIVE const *)
0x180006225  test    rax, rax
0x180006228  jz      short loc_180006265
0x18000622a  movzx   edx, word ptr [rax+0Ah]; cb
0x18000622e  test    dx, dx
0x180006231  jz      short loc_180006265
0x180006233  lea     rcx, [rax+12h]; psps
0x180006237  test    rcx, rcx
0x18000623a  jz      short loc_180006265
0x18000623c  lea     r9, [rbp+ppropvar]; ppropvar
0x180006240  lea     r8, PKEY_DeviceDisplay_FriendlyName; rpkey
0x180006247  call    cs:__imp_PSGetPropertyFromPropertyStorage
0x18000624d  test    eax, eax
0x18000624f  js      short loc_180006265
0x180006251  cmp     word ptr [rbp+ppropvar], 0
0x180006256  jz      short loc_180006265
0x180006258  lea     rdx, [rbp+ppv]; unsigned __int16 **
0x18000625c  lea     rcx, [rbp+ppropvar]; this
0x180006260  call    ?GetAsOrStealString@CPropVariant@@QEAAJPEAPEAG@Z; CPropVariant::GetAsOrStealString(ushort * *)
0x180006265  lea     rcx, [rbp+ppropvar]; pvar
0x180006269  call    cs:__imp_PropVariantClear
0x18000626f  mov     [rbp+var_30], r12
0x180006273  lea     r9, [r15+60h]
0x180006277  lea     rax, [rbp+var_28]
0x18000627b  mov     [rsp+60h+ppidlLast], rax
0x180006280  lea     r8, [rbp+ppv]
0x180006284  lea     rdx, [rbp+arg_8]
0x180006288  lea     rcx, [rbp+var_30]
0x18000628c  call    ??$MakeAndInitialize@VCContentDirectoryFolder@@V1@AEAV?$CCoTaskMemPtr@G@@AEAV2@AEAV?$CCoTaskMemPtr@U_ITEMIDLIST_ABSOLUTE@@@@AEAPEFBU_ITEMID_CHILD@@@Details@WRL@Microsoft@@YAJPEAPEAVCContentDirectoryFolder@@AEAV?$CCoTaskMemPtr@G@@1AEAV?$CCoTaskMemPtr@U_ITEMIDLIST_ABSOLUTE@@@@AEAPEFBU_ITEMID_CHILD@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CContentDirectoryFolder,CContentDirectoryFolder,CCoTaskMemPtr<ushort> &,CCoTaskMemPtr<ushort> &,CCoTaskMemPtr<_ITEMIDLIST_ABSOLUTE> &,_ITEMID_CHILD const * &>(CContentDirectoryFolder * *,CCoTaskMemPtr<ushort> &,CCoTaskMemPtr<ushort> &,CCoTaskMemPtr<_ITEMIDLIST_ABSOLUTE> &,_ITEMID_CHILD const * &)
0x180006291  mov     esi, eax
0x180006293  mov     rbx, [rbp+var_30]
0x180006297  test    eax, eax
0x180006299  js      short loc_180006304
0x18000629b  mov     [r14], r12
0x18000629e  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; struct _GUID *
0x1800062a5  mov     rcx, rdi; struct _GUID *
0x1800062a8  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x1800062ad  test    eax, eax
0x1800062af  jnz     short loc_1800062EF
0x1800062b1  lea     rdx, _GUID_add8ba80_002b_11d0_8f0f_00c04fd7d062; struct _GUID *
0x1800062b8  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x1800062bd  test    eax, eax
0x1800062bf  jz      short loc_1800062C9
0x1800062c1  mov     [r14], rbx
0x1800062c4  mov     esi, r12d
0x1800062c7  jmp     short loc_1800062DE
0x1800062c9  lea     rcx, [rbx+8]
0x1800062cd  mov     r8, r14
0x1800062d0  mov     rdx, rdi
0x1800062d3  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ChainInterfaces@UIPersistFolder2@@UIPersistFolder@@UIPersist@@VNil@Details@WRL@Microsoft@@V4567@V4567@V4567@V4567@V4567@V4567@@23@U?$ChainInterfaces@UIShellFolder2@@UIShellFolder@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIThumbnailHandlerFactory@@UIProviderResolver@@UIExplorerPaneVisibility@@UIFileJunctionOptions@@UISearchBoxSettings@@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::ChainInterfaces<IPersistFolder2,IPersistFolder,IPersist,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::ChainInterfaces<IShellFolder2,IShellFolder,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IThumbnailHandlerFactory,IProviderResolver,IExplorerPaneVisibility,IFileJunctionOptions,ISearchBoxSettings>::CanCastTo(_GUID const &,void * *,bool *)
0x1800062d8  mov     esi, eax
0x1800062da  test    eax, eax
0x1800062dc  js      short loc_180006304
0x1800062de  mov     rcx, [r14]
0x1800062e1  mov     rax, [rcx]
0x1800062e4  mov     rax, [rax+8]
0x1800062e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062ed  jmp     short loc_180006304
0x1800062ef  mov     [r14], rbx
0x1800062f2  mov     rax, [rbx]
0x1800062f5  mov     rcx, rbx
0x1800062f8  mov     rax, [rax+8]
0x1800062fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006301  mov     esi, r12d
0x180006304  test    rbx, rbx
0x180006307  jz      short loc_180006312
0x180006309  mov     rcx, rbx
0x18000630c  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIDelegateFolder@@U?$ChainInterfaces@UIPersistFolder2@@UIPersistFolder@@UIPersist@@VNil@Details@WRL@Microsoft@@V4567@V4567@V4567@V4567@V4567@V4567@@23@U?$ChainInterfaces@UIShellFolder2@@UIShellFolder@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIThumbnailHandlerFactory@@UIProviderResolver@@UIExplorerPaneVisibility@@UIFileJunctionOptions@@UISearchBoxSettings@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IDelegateFolder,Microsoft::WRL::ChainInterfaces<IPersistFolder2,IPersistFolder,IPersist,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::ChainInterfaces<IShellFolder2,IShellFolder,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IThumbnailHandlerFactory,IProviderResolver,IExplorerPaneVisibility,IFileJunctionOptions,ISearchBoxSettings>::Release(void)
0x180006311  nop
0x180006312  mov     rcx, [rbp+ppv]; pv
0x180006316  mov     [rbp+ppv], r12
0x18000631a  call    cs:__imp_CoTaskMemFree
0x180006320  nop
0x180006321  mov     rcx, [rbp+arg_8]; pv
0x180006325  mov     [rbp+arg_8], r12
0x180006329  call    cs:__imp_CoTaskMemFree
0x18000632f  mov     eax, esi
0x180006331  lea     r11, [rsp+60h+var_s0]
0x180006336  mov     rbx, [r11+30h]
0x18000633a  mov     rsi, [r11+40h]
0x18000633e  mov     rsp, r11
0x180006341  pop     r15
0x180006343  pop     r14
0x180006345  pop     r12
0x180006347  pop     rdi
0x180006348  pop     rbp
0x180006349  retn
```
