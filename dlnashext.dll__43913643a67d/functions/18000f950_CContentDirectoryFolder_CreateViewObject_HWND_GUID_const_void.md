# CContentDirectoryFolder::CreateViewObject(HWND__ *,_GUID const &,void * *)

- ea: `0x18000f950`
- end: `0x18000fba2`
- name: `?CreateViewObject@CContentDirectoryFolder@@UEAAJPEAUHWND__@@AEBU_GUID@@PEAPEAX@Z`
- size: `594`
- prototype: `int(CContentDirectoryFolder *__hidden this, HWND, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `10`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001710`
- `0x180005790`
- `0x18000f950`
- `0x180013edc`
- `0x1800157cc`
- `0x1800195d4`
- `0x180019890`
- `0x180019b84`
- `0x180022ba0`
- `0x180035010`

## import_xrefs

- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromIDList` at `0x18000fa0b`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromIDList` at `0x18000fa0b`
- `ext-ms-win-casting-shell-l1-1-0!CreateViewObjectForContentDirectoryFolder` at `0x18000f9b5`
- `ext-ms-win-casting-shell-l1-1-0!CreateViewObjectForContentDirectoryFolder` at `0x18000f9b5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CContentDirectoryFolder::CreateViewObject(
        unsigned __int64 this,
        HWND a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 v8; // rax
  char *v9; // rdi
  HRESULT ViewObjectForContentDirectoryFolder; // ebx
  __int64 v11; // rax
  __int64 v12; // rax
  const struct _GUID *v13; // rcx
  __int64 v14; // r8
  _QWORD *v15; // r9
  __int64 v16; // r8
  _QWORD *v17; // r9
  __int64 v18; // rax
  struct CContentDirectoryChangeListener **v19; // r14
  PVOID *v20; // r10
  void *ppv; // [rsp+78h] [rbp+20h] BYREF

  *a4 = 0;
  v8 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&GUID_000214e3_0000_0000_c000_000000000046.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&GUID_000214e3_0000_0000_c000_000000000046.Data1 )
    v8 = *(_QWORD *)a3->Data4 - *(_QWORD *)GUID_000214e3_0000_0000_c000_000000000046.Data4;
  if ( !v8 )
  {
    v9 = (char *)(this - 16);
    ViewObjectForContentDirectoryFolder = CContentDirectoryFolder::_ValidateMediaServer((CContentDirectoryFolder *)(this - 16));
    if ( ViewObjectForContentDirectoryFolder >= 0 )
    {
      ViewObjectForContentDirectoryFolder = CreateViewObjectForContentDirectoryFolder(this & -(__int64)(v9 != 0), a4);
      if ( ViewObjectForContentDirectoryFolder == -2147467263 )
        ViewObjectForContentDirectoryFolder = -2147467262;
    }
    goto LABEL_34;
  }
  v11 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_ITransferSource.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_ITransferSource.Data1 )
    v11 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_ITransferSource.Data4;
  if ( !v11 )
  {
    ppv = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&ppv);
    ViewObjectForContentDirectoryFolder = SHCreateItemFromIDList(
                                            *(LPCITEMIDLIST *)(this + 72),
                                            &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                                            &ppv);
    if ( ViewObjectForContentDirectoryFolder >= 0 )
      ViewObjectForContentDirectoryFolder = CContentDirectoryTransfer_CreateInstance(
                                              a2,
                                              (struct IShellItem *)ppv,
                                              a3,
                                              a4);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&ppv);
    goto LABEL_34;
  }
  v12 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&GUID_bf2d36d6_72a6_4ee1_8553_3d90aa88800f.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&GUID_bf2d36d6_72a6_4ee1_8553_3d90aa88800f.Data1 )
    v12 = *(_QWORD *)a3->Data4 - *(_QWORD *)GUID_bf2d36d6_72a6_4ee1_8553_3d90aa88800f.Data4;
  if ( !v12 )
  {
    if ( (unsigned int)InlineIsEqualGUID(a3, &GUID_00000000_0000_0000_c000_000000000046) )
    {
      *v15 = v14;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
      ViewObjectForContentDirectoryFolder = 0;
      goto LABEL_34;
    }
    if ( (unsigned int)InlineIsEqualGUID(v13, &GUID_add8ba80_002b_11d0_8f0f_00c04fd7d062) )
    {
      *v17 = v16;
      ViewObjectForContentDirectoryFolder = 0;
    }
    else
    {
      ViewObjectForContentDirectoryFolder = Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::ChainInterfaces<IPersistFolder2,IPersistFolder,IPersist,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::ChainInterfaces<IShellFolder2,IShellFolder,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IThumbnailHandlerFactory,IProviderResolver,IExplorerPaneVisibility,IFileJunctionOptions,ISearchBoxSettings>::CanCastTo(
                                              v16 + 8,
                                              a3,
                                              a4);
      if ( ViewObjectForContentDirectoryFolder < 0 )
        goto LABEL_34;
    }
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a4 + 8LL))(*a4);
LABEL_34:
    v20 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_35;
  }
  ViewObjectForContentDirectoryFolder = -2147467262;
  v18 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&GUID_cad9ae9f_56e2_40f1_afb6_3813e320dcfd.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&GUID_cad9ae9f_56e2_40f1_afb6_3813e320dcfd.Data1 )
    v18 = *(_QWORD *)a3->Data4 - *(_QWORD *)GUID_cad9ae9f_56e2_40f1_afb6_3813e320dcfd.Data4;
  if ( v18 )
    goto LABEL_34;
  v19 = (struct CContentDirectoryChangeListener **)(this + 136);
  if ( !*(_QWORD *)(this + 136) )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(this + 136);
    ViewObjectForContentDirectoryFolder = CChangeListenerRegistrar::CreateChangeListener(
                                            (CChangeListenerRegistrar *)&CChangeListenerRegistrar::s_Singleton,
                                            *(const unsigned __int16 **)(this + 96),
                                            v19);
  }
  if ( *v19 )
    ViewObjectForContentDirectoryFolder = (**(__int64 (__fastcall ***)(struct CContentDirectoryChangeListener *, const struct _GUID *, void **))*v19)(
                                            *v19,
                                            a3,
                                            a4);
  v20 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
LABEL_35:
      if ( v20 != &WPP_GLOBAL_Control
        && (*((_BYTE *)v20 + 28) & 2) != 0
        && *((unsigned __int8 *)v20 + 25) >= ((ViewObjectForContentDirectoryFolder >> 31) & 0xFFFFFFFD) + 5 )
      {
        WPP_SF_d(
          v20[2],
          24,
          &WPP_84ae8ebcb53830fc05f9daa7a52d3aff_Traceguids,
          (unsigned int)ViewObjectForContentDirectoryFolder);
      }
      return (unsigned int)ViewObjectForContentDirectoryFolder;
    }
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, a3, (unsigned int)ViewObjectForContentDirectoryFolder);
    goto LABEL_34;
  }
  return (unsigned int)ViewObjectForContentDirectoryFolder;
}

```

## disassembly

```asm
0x18000f950  push    rbx
0x18000f952  push    rbp
0x18000f953  push    rsi
0x18000f954  push    rdi
0x18000f955  push    r12
0x18000f957  push    r14
0x18000f959  sub     rsp, 28h
0x18000f95d  mov     rsi, r9
0x18000f960  mov     rdi, r8
0x18000f963  mov     r14, rdx
0x18000f966  mov     rbp, rcx
0x18000f969  mov     qword ptr [r9], 0
0x18000f970  mov     rax, [r8]
0x18000f973  sub     rax, qword ptr cs:_GUID_000214e3_0000_0000_c000_000000000046.Data1
0x18000f97a  jnz     short loc_18000F987
0x18000f97c  mov     rax, [r8+8]
0x18000f980  sub     rax, qword ptr cs:_GUID_000214e3_0000_0000_c000_000000000046.Data4
0x18000f987  lea     r12, WPP_GLOBAL_Control
0x18000f98e  test    rax, rax
0x18000f991  jnz     short loc_18000F9D0
0x18000f993  lea     rdi, [rcx-10h]
0x18000f997  mov     rcx, rdi; this
0x18000f99a  call    ?_ValidateMediaServer@CContentDirectoryFolder@@AEAAJXZ; CContentDirectoryFolder::_ValidateMediaServer(void)
0x18000f99f  mov     ebx, eax
0x18000f9a1  test    eax, eax
0x18000f9a3  js      loc_18000FB54
0x18000f9a9  neg     rdi
0x18000f9ac  sbb     rcx, rcx
0x18000f9af  and     rcx, rbp
0x18000f9b2  mov     rdx, rsi
0x18000f9b5  call    cs:__imp_CreateViewObjectForContentDirectoryFolder
0x18000f9bb  mov     ebx, eax
0x18000f9bd  cmp     eax, 80004001h
0x18000f9c2  jnz     loc_18000FB54
0x18000f9c8  lea     ebx, [rax+1]
0x18000f9cb  jmp     loc_18000FB54
0x18000f9d0  mov     rax, [r8]
0x18000f9d3  sub     rax, qword ptr cs:IID_ITransferSource.Data1
0x18000f9da  jnz     short loc_18000F9E7
0x18000f9dc  mov     rax, [r8+8]
0x18000f9e0  sub     rax, qword ptr cs:IID_ITransferSource.Data4
0x18000f9e7  test    rax, rax
0x18000f9ea  jnz     short loc_18000FA3B
0x18000f9ec  mov     [rsp+58h+ppv], rax
0x18000f9f1  lea     rcx, [rsp+58h+ppv]
0x18000f9f6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18000f9fb  lea     r8, [rsp+58h+ppv]; ppv
0x18000fa00  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18000fa07  mov     rcx, [rbp+48h]; pidl
0x18000fa0b  call    cs:__imp_SHCreateItemFromIDList
0x18000fa11  mov     ebx, eax
0x18000fa13  test    eax, eax
0x18000fa15  js      short loc_18000FA2C
0x18000fa17  mov     r9, rsi; void **
0x18000fa1a  mov     r8, rdi; struct _GUID *
0x18000fa1d  mov     rdx, [rsp+58h+ppv]; struct IShellItem *
0x18000fa22  mov     rcx, r14; HWND
0x18000fa25  call    ?CContentDirectoryTransfer_CreateInstance@@YAJPEAUHWND__@@PEAUIShellItem@@AEBU_GUID@@PEAPEAX@Z; CContentDirectoryTransfer_CreateInstance(HWND__ *,IShellItem *,_GUID const &,void * *)
0x18000fa2a  mov     ebx, eax
0x18000fa2c  lea     rcx, [rsp+58h+ppv]
0x18000fa31  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18000fa36  jmp     loc_18000FB54
0x18000fa3b  mov     rax, [r8]
0x18000fa3e  sub     rax, qword ptr cs:_GUID_bf2d36d6_72a6_4ee1_8553_3d90aa88800f.Data1
0x18000fa45  jnz     short loc_18000FA52
0x18000fa47  mov     rax, [r8+8]
0x18000fa4b  sub     rax, qword ptr cs:_GUID_bf2d36d6_72a6_4ee1_8553_3d90aa88800f.Data4
0x18000fa52  test    rax, rax
0x18000fa55  jnz     short loc_18000FAC4
0x18000fa57  lea     r8, [rcx-10h]
0x18000fa5b  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; struct _GUID *
0x18000fa62  mov     rcx, rdi; struct _GUID *
0x18000fa65  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000fa6a  test    eax, eax
0x18000fa6c  jnz     short loc_18000FAAB
0x18000fa6e  lea     rdx, _GUID_add8ba80_002b_11d0_8f0f_00c04fd7d062; struct _GUID *
0x18000fa75  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000fa7a  test    eax, eax
0x18000fa7c  jz      short loc_18000FA85
0x18000fa7e  mov     [r9], r8
0x18000fa81  xor     ebx, ebx
0x18000fa83  jmp     short loc_18000FA9A
0x18000fa85  lea     rcx, [r8+8]
0x18000fa89  mov     r8, rsi
0x18000fa8c  mov     rdx, rdi
0x18000fa8f  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ChainInterfaces@UIPersistFolder2@@UIPersistFolder@@UIPersist@@VNil@Details@WRL@Microsoft@@V4567@V4567@V4567@V4567@V4567@V4567@@23@U?$ChainInterfaces@UIShellFolder2@@UIShellFolder@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIThumbnailHandlerFactory@@UIProviderResolver@@UIExplorerPaneVisibility@@UIFileJunctionOptions@@UISearchBoxSettings@@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::ChainInterfaces<IPersistFolder2,IPersistFolder,IPersist,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::ChainInterfaces<IShellFolder2,IShellFolder,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IThumbnailHandlerFactory,IProviderResolver,IExplorerPaneVisibility,IFileJunctionOptions,ISearchBoxSettings>::CanCastTo(_GUID const &,void * *,bool *)
0x18000fa94  mov     ebx, eax
0x18000fa96  test    eax, eax
0x18000fa98  js      short loc_18000FABF
0x18000fa9a  mov     rcx, [rsi]
0x18000fa9d  mov     rax, [rcx]
0x18000faa0  mov     rax, [rax+8]
0x18000faa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000faa9  jmp     short loc_18000FABF
0x18000faab  mov     [r9], r8
0x18000faae  mov     rax, [r8]
0x18000fab1  mov     rcx, r8
0x18000fab4  mov     rax, [rax+8]
0x18000fab8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fabd  xor     ebx, ebx
0x18000fabf  jmp     loc_18000FB54
0x18000fac4  mov     ebx, 80004002h
0x18000fac9  mov     rax, [r8]
0x18000facc  sub     rax, qword ptr cs:_GUID_cad9ae9f_56e2_40f1_afb6_3813e320dcfd.Data1
0x18000fad3  jnz     short loc_18000FAE0
0x18000fad5  mov     rax, [r8+8]
0x18000fad9  sub     rax, qword ptr cs:_GUID_cad9ae9f_56e2_40f1_afb6_3813e320dcfd.Data4
0x18000fae0  test    rax, rax
0x18000fae3  jnz     short loc_18000FB54
0x18000fae5  lea     r14, [rcx+88h]
0x18000faec  cmp     [r14], rax
0x18000faef  jnz     short loc_18000FB0E
0x18000faf1  mov     rcx, r14
0x18000faf4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18000faf9  mov     r8, r14; struct CContentDirectoryChangeListener **
0x18000fafc  mov     rdx, [rbp+60h]; unsigned __int16 *
0x18000fb00  lea     rcx, ?s_Singleton@CChangeListenerRegistrar@@0V1@A; this
0x18000fb07  call    ?CreateChangeListener@CChangeListenerRegistrar@@QEAAJPEBGPEAPEAVCContentDirectoryChangeListener@@@Z; CChangeListenerRegistrar::CreateChangeListener(ushort const *,CContentDirectoryChangeListener * *)
0x18000fb0c  mov     ebx, eax
0x18000fb0e  mov     rcx, [r14]
0x18000fb11  test    rcx, rcx
0x18000fb14  jz      short loc_18000FB29
0x18000fb16  mov     rax, [rcx]
0x18000fb19  mov     r8, rsi
0x18000fb1c  mov     rdx, rdi
0x18000fb1f  mov     rax, [rax]
0x18000fb22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb27  mov     ebx, eax
0x18000fb29  mov     r10, cs:WPP_GLOBAL_Control
0x18000fb30  cmp     r10, r12
0x18000fb33  jz      short loc_18000FB93
0x18000fb35  test    byte ptr [r10+1Ch], 40h
0x18000fb3a  jz      short loc_18000FB5B
0x18000fb3c  cmp     byte ptr [r10+19h], 4
0x18000fb41  jb      short loc_18000FB5B
0x18000fb43  mov     edx, 17h
0x18000fb48  mov     r9d, ebx
0x18000fb4b  mov     rcx, [r10+10h]
0x18000fb4f  call    WPP_SF_D
0x18000fb54  mov     r10, cs:WPP_GLOBAL_Control
0x18000fb5b  cmp     r10, r12
0x18000fb5e  jz      short loc_18000FB93
0x18000fb60  test    byte ptr [r10+1Ch], 2
0x18000fb65  jz      short loc_18000FB93
0x18000fb67  mov     ecx, ebx
0x18000fb69  sar     ecx, 1Fh
0x18000fb6c  and     ecx, 0FFFFFFFDh
0x18000fb6f  add     ecx, 5
0x18000fb72  movzx   eax, byte ptr [r10+19h]
0x18000fb77  cmp     eax, ecx
0x18000fb79  jb      short loc_18000FB93
0x18000fb7b  mov     edx, 18h
0x18000fb80  mov     r9d, ebx
0x18000fb83  lea     r8, WPP_84ae8ebcb53830fc05f9daa7a52d3aff_Traceguids
0x18000fb8a  mov     rcx, [r10+10h]
0x18000fb8e  call    WPP_SF_d
0x18000fb93  mov     eax, ebx
0x18000fb95  add     rsp, 28h
0x18000fb99  pop     r14
0x18000fb9b  pop     r12
0x18000fb9d  pop     rdi
0x18000fb9e  pop     rsi
0x18000fb9f  pop     rbp
0x18000fba0  pop     rbx
0x18000fba1  retn
```
