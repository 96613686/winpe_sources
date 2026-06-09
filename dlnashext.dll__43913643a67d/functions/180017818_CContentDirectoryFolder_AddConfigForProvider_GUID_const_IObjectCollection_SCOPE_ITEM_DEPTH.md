# CContentDirectoryFolder::_AddConfigForProvider(_GUID const &,IObjectCollection *,SCOPE_ITEM_DEPTH)

- ea: `0x180017818`
- end: `0x180017a84`
- name: `?_AddConfigForProvider@CContentDirectoryFolder@@AEAAJAEBU_GUID@@PEAUIObjectCollection@@W4SCOPE_ITEM_DEPTH@@@Z`
- size: `620`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180017490`

## callees

- `0x180001710`
- `0x180017818`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180017868`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180017868`
- `api-ms-win-shell-namespace-l1-1-0!ILGetSize` at `0x1800178f4`
- `api-ms-win-shell-namespace-l1-1-0!ILGetSize` at `0x1800178f4`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180017894`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180017894`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CContentDirectoryFolder::_AddConfigForProvider(__int64 a1, void *a2, __int64 a3, int a4)
{
  HRESULT v7; // ebx
  __int64 v8; // rax
  const ITEMIDLIST *v9; // rcx
  __int64 v10; // rax
  const WCHAR *v11; // rdx
  __int64 v12; // rax
  __int64 v13; // rax
  int v14; // edx
  __int64 v15; // rax
  LPVOID ppv; // [rsp+40h] [rbp-19h] BYREF
  __int64 v18; // [rsp+48h] [rbp-11h] BYREF
  __int64 v19; // [rsp+50h] [rbp-9h]
  const ITEMIDLIST *v20; // [rsp+58h] [rbp-1h]
  __int16 v21; // [rsp+60h] [rbp+7h] BYREF
  const WCHAR *v22; // [rsp+68h] [rbp+Fh]
  void *v23; // [rsp+C8h] [rbp+6Fh] BYREF

  v23 = a2;
  ppv = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&ppv);
  v7 = CoCreateInstance(
         &GUID_3722c3b1_82e8_4022_8b27_1f8a68b44ac7,
         0,
         1u,
         &GUID_628880f3_0dc6_4359_a29b_15ef9aecbd23,
         &ppv);
  if ( v7 >= 0 )
  {
    v23 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v23);
    v7 = PSCreateMemoryPropertyStore(&GUID_71604b0f_97b0_4764_8577_2f13e98a1422, &v23);
    if ( v7 >= 0 )
    {
      v8 = *(_QWORD *)v23;
      LOWORD(v18) = 31;
      v19 = *(_QWORD *)(a1 + 112);
      v7 = (*(__int64 (__fastcall **)(void *, const wchar_t *, __int64 *))(v8 + 32))(v23, L"UniqueDeviceName", &v18);
      if ( v7 >= 0 )
      {
        v9 = *(const ITEMIDLIST **)(a1 + 88);
        v18 = 0;
        v19 = 0;
        v20 = v9;
        LODWORD(v19) = ILGetSize(v9);
        LOWORD(v18) = 4113;
        v7 = (*(__int64 (__fastcall **)(void *, const wchar_t *, __int64 *))(*(_QWORD *)v23 + 32LL))(
               v23,
               L"AbsolutePIDL",
               &v18);
        if ( v7 >= 0 )
        {
          v10 = *(_QWORD *)v23;
          v11 = L"0";
          if ( *(_QWORD *)(a1 + 96) )
            v11 = *(const WCHAR **)(a1 + 96);
          v21 = 31;
          v22 = v11;
          v7 = (*(__int64 (__fastcall **)(void *, const wchar_t *, __int16 *))(v10 + 32))(v23, L"ObjectID", &v21);
          if ( v7 >= 0 )
          {
            v12 = *(_QWORD *)v23;
            v21 = 3;
            LODWORD(v22) = (a4 == 2) + 1;
            v7 = (*(__int64 (__fastcall **)(void *, const wchar_t *, __int16 *))(v12 + 32))(v23, L"Depth", &v21);
            if ( v7 >= 0 )
            {
              v13 = *(_QWORD *)v23;
              v21 = 31;
              v22 = *(const WCHAR **)(a1 + 104);
              v7 = (*(__int64 (__fastcall **)(void *, const wchar_t *, __int16 *))(v13 + 32))(v23, L"UPnPClass", &v21);
              if ( v7 >= 0 )
              {
                v14 = *(_DWORD *)(a1 + 132);
                if ( !v14
                  || (v15 = *(_QWORD *)v23,
                      v21 = 19,
                      LODWORD(v22) = v14,
                      v7 = (*(__int64 (__fastcall **)(void *, const wchar_t *, __int16 *))(v15 + 32))(
                             v23,
                             L"SortCaps",
                             &v21),
                      v7 >= 0) )
                {
                  v7 = (*(__int64 (__fastcall **)(LPVOID, GUID *, const wchar_t *, void *, _QWORD, _QWORD))(*(_QWORD *)ppv + 24LL))(
                         ppv,
                         &CLSID_ContentDirectoryProvider,
                         L"Merge Any",
                         v23,
                         0,
                         0);
                  if ( v7 >= 0 )
                    v7 = (*(__int64 (__fastcall **)(__int64, LPVOID))(*(_QWORD *)a3 + 40LL))(a3, ppv);
                }
              }
            }
          }
        }
      }
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v23);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&ppv);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180017818  mov     [rsp-8+arg_8], rdx
0x18001781d  push    rbp
0x18001781e  push    rbx
0x18001781f  push    rsi
0x180017820  push    rdi
0x180017821  push    r12
0x180017823  push    r14
0x180017825  lea     rbp, [rsp-2Fh]
0x18001782a  sub     rsp, 88h
0x180017831  mov     r14d, r9d
0x180017834  mov     rsi, r8
0x180017837  mov     rdi, rcx
0x18001783a  mov     [rbp+57h+var_70], 0
0x180017842  lea     rcx, [rbp+57h+var_70]
0x180017846  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18001784b  lea     rax, [rbp+57h+var_70]
0x18001784f  mov     [rsp+0B0h+ppv], rax; ppv
0x180017854  lea     r9, _GUID_628880f3_0dc6_4359_a29b_15ef9aecbd23; riid
0x18001785b  xor     edx, edx; pUnkOuter
0x18001785d  lea     r8d, [rdx+1]; dwClsContext
0x180017861  lea     rcx, _GUID_3722c3b1_82e8_4022_8b27_1f8a68b44ac7; rclsid
0x180017868  call    cs:__imp_CoCreateInstance
0x18001786e  mov     ebx, eax
0x180017870  test    eax, eax
0x180017872  js      loc_180017A69
0x180017878  mov     [rbp+57h+arg_8], 0
0x180017880  lea     rcx, [rbp+57h+arg_8]
0x180017884  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180017889  lea     rdx, [rbp+57h+arg_8]; ppv
0x18001788d  lea     rcx, _GUID_71604b0f_97b0_4764_8577_2f13e98a1422; riid
0x180017894  call    cs:__imp_PSCreateMemoryPropertyStore
0x18001789a  mov     ebx, eax
0x18001789c  test    eax, eax
0x18001789e  js      loc_180017A5F
0x1800178a4  mov     rcx, [rbp+57h+arg_8]
0x1800178a8  mov     rax, [rcx]
0x1800178ab  mov     r12d, 1Fh
0x1800178b1  mov     word ptr [rbp+57h+var_68], r12w
0x1800178b6  mov     rdx, [rdi+70h]
0x1800178ba  mov     [rbp+57h+var_60], rdx
0x1800178be  lea     r8, [rbp+57h+var_68]
0x1800178c2  lea     rdx, g_wszUDN; "UniqueDeviceName"
0x1800178c9  mov     rax, [rax+20h]
0x1800178cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800178d2  mov     ebx, eax
0x1800178d4  test    eax, eax
0x1800178d6  js      loc_180017A5F
0x1800178dc  mov     rcx, [rdi+58h]; pidl
0x1800178e0  mov     [rbp+57h+var_68], 0
0x1800178e8  mov     [rbp+57h+var_60], 0
0x1800178f0  mov     [rbp+57h+var_58], rcx
0x1800178f4  call    cs:__imp_ILGetSize
0x1800178fa  mov     dword ptr [rbp+57h+var_60], eax
0x1800178fd  mov     eax, 1011h
0x180017902  mov     word ptr [rbp+57h+var_68], ax
0x180017906  mov     rcx, [rbp+57h+arg_8]
0x18001790a  mov     rax, [rcx]
0x18001790d  lea     r8, [rbp+57h+var_68]
0x180017911  lea     rdx, g_wszAbsolutePIDL; "AbsolutePIDL"
0x180017918  mov     rax, [rax+20h]
0x18001791c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017921  mov     ebx, eax
0x180017923  test    eax, eax
0x180017925  js      loc_180017A5F
0x18001792b  mov     rcx, [rbp+57h+arg_8]
0x18001792f  mov     rax, [rcx]
0x180017932  lea     rdx, psz; "0"
0x180017939  cmp     qword ptr [rdi+60h], 0
0x18001793e  cmovnz  rdx, [rdi+60h]
0x180017943  mov     [rbp+57h+var_50], r12w
0x180017948  mov     [rbp+57h+var_48], rdx
0x18001794c  lea     r8, [rbp+57h+var_50]
0x180017950  lea     rdx, g_wszObjectID; "ObjectID"
0x180017957  mov     rax, [rax+20h]
0x18001795b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017960  mov     ebx, eax
0x180017962  test    eax, eax
0x180017964  js      loc_180017A5F
0x18001796a  mov     rcx, [rbp+57h+arg_8]
0x18001796e  mov     rax, [rcx]
0x180017971  lea     edx, [r12-1Ch]
0x180017976  mov     [rbp+57h+var_50], dx
0x18001797a  xor     edx, edx
0x18001797c  cmp     r14d, 2
0x180017980  setz    dl
0x180017983  inc     edx
0x180017985  mov     dword ptr [rbp+57h+var_48], edx
0x180017988  lea     r8, [rbp+57h+var_50]
0x18001798c  lea     rdx, g_wszDepth; "Depth"
0x180017993  mov     rax, [rax+20h]
0x180017997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001799c  mov     ebx, eax
0x18001799e  test    eax, eax
0x1800179a0  js      loc_180017A5F
0x1800179a6  mov     rcx, [rbp+57h+arg_8]
0x1800179aa  mov     rax, [rcx]
0x1800179ad  mov     [rbp+57h+var_50], r12w
0x1800179b2  mov     rdx, [rdi+68h]
0x1800179b6  mov     [rbp+57h+var_48], rdx
0x1800179ba  lea     r8, [rbp+57h+var_50]
0x1800179be  lea     rdx, g_wszUPnPClass; "UPnPClass"
0x1800179c5  mov     rax, [rax+20h]
0x1800179c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800179ce  mov     ebx, eax
0x1800179d0  test    eax, eax
0x1800179d2  js      loc_180017A5F
0x1800179d8  mov     edx, [rdi+84h]
0x1800179de  test    edx, edx
0x1800179e0  jz      short loc_180017A10
0x1800179e2  mov     rcx, [rbp+57h+arg_8]
0x1800179e6  mov     rax, [rcx]
0x1800179e9  lea     r8d, [r12-0Ch]
0x1800179ee  mov     [rbp+57h+var_50], r8w
0x1800179f3  mov     dword ptr [rbp+57h+var_48], edx
0x1800179f6  lea     r8, [rbp+57h+var_50]
0x1800179fa  lea     rdx, g_wszSortCapabilities; "SortCaps"
0x180017a01  mov     rax, [rax+20h]
0x180017a05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a0a  mov     ebx, eax
0x180017a0c  test    eax, eax
0x180017a0e  js      short loc_180017A5F
0x180017a10  mov     rcx, [rbp+57h+var_70]
0x180017a14  mov     rax, [rcx]
0x180017a17  mov     [rsp+0B0h+var_88], 0
0x180017a20  mov     [rsp+0B0h+ppv], 0
0x180017a29  mov     r9, [rbp+57h+arg_8]
0x180017a2d  lea     r8, aMergeAny; "Merge Any"
0x180017a34  lea     rdx, ?CLSID_ContentDirectoryProvider@@3U_GUID@@B; _GUID const CLSID_ContentDirectoryProvider
0x180017a3b  mov     rax, [rax+18h]
0x180017a3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a44  mov     ebx, eax
0x180017a46  test    eax, eax
0x180017a48  js      short loc_180017A5F
0x180017a4a  mov     rax, [rsi]
0x180017a4d  mov     rdx, [rbp+57h+var_70]
0x180017a51  mov     rcx, rsi
0x180017a54  mov     rax, [rax+28h]
0x180017a58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a5d  mov     ebx, eax
0x180017a5f  lea     rcx, [rbp+57h+arg_8]
0x180017a63  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180017a68  nop
0x180017a69  lea     rcx, [rbp+57h+var_70]
0x180017a6d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180017a72  mov     eax, ebx
0x180017a74  add     rsp, 88h
0x180017a7b  pop     r14
0x180017a7d  pop     r12
0x180017a7f  pop     rdi
0x180017a80  pop     rsi
0x180017a81  pop     rbx
0x180017a82  pop     rbp
0x180017a83  retn
```
