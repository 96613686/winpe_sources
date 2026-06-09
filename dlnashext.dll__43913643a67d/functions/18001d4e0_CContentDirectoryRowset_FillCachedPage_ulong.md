# CContentDirectoryRowset::_FillCachedPage(ulong)

- ea: `0x18001d4e0`
- end: `0x18001d7cd`
- name: `?_FillCachedPage@CContentDirectoryRowset@@AEAAJK@Z`
- size: `749`
- prototype: `__int64 __fastcall(CContentDirectoryRowset *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18001dab8`

## callees

- `0x180001710`
- `0x1800104d8`
- `0x180011930`
- `0x18001681c`
- `0x180017e84`
- `0x18001c744`
- `0x18001cc50`
- `0x18001d4e0`
- `0x18001dd14`
- `0x180025860`
- `0x180025acc`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001d540`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001d662`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001d6d5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001d741`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001d79d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001d540`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001d662`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001d6d5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001d741`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001d79d`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18001d5e3`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18001d5e3`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CContentDirectoryRowset::_FillCachedPage(CContentDirectoryRowset *this, unsigned int a2)
{
  char *v4; // r15
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, const wchar_t *, PROPVARIANT *); // rbx
  int MediaServerByUDN; // esi
  const unsigned __int16 *String; // rax
  __int64 v9; // rbx
  __int64 v10; // rax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, const wchar_t *, PROPVARIANT *); // rbx
  const unsigned __int16 *v13; // rax
  __int64 v14; // rdi
  int (__fastcall *v15)(__int64, const wchar_t *, PROPVARIANT *); // rbx
  LONG lVal; // eax
  int v17; // esi
  __int64 v18; // rdi
  int (__fastcall *v19)(__int64, const wchar_t *, PROPVARIANT *); // rbx
  int v20; // eax
  struct Windows::Media::Streaming::Internal::IMediaServer *v22; // [rsp+20h] [rbp-60h] BYREF
  __int64 v23; // [rsp+28h] [rbp-58h] BYREF
  PROPVARIANT pvar; // [rsp+30h] [rbp-50h] BYREF
  __int64 v25; // [rsp+48h] [rbp-38h] BYREF
  __int64 v26; // [rsp+50h] [rbp-30h] BYREF
  HSTRING v27[4]; // [rsp+58h] [rbp-28h] BYREF

  pvar.vt = 0;
  v22 = 0;
  v4 = (char *)this + 288;
  if ( !*((_QWORD *)this + 43) )
  {
    v25 = 0;
    v5 = *(_QWORD *)v4;
    v6 = *(__int64 (__fastcall **)(__int64, const wchar_t *, PROPVARIANT *))(**(_QWORD **)v4 + 24LL);
    PropVariantClear(&pvar);
    MediaServerByUDN = v6(v5, L"UniqueDeviceName", &pvar);
    if ( MediaServerByUDN >= 0 )
    {
      String = CPropVariant::GetString((CPropVariant *)&pvar);
      Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v27, String);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((__int64 *)&v22);
      MediaServerByUDN = FindMediaServerByUDN(v27, &v22);
      if ( MediaServerByUDN >= 0 )
      {
        MediaServerByUDN = (*(__int64 (__fastcall **)(struct Windows::Media::Streaming::Internal::IMediaServer *, __int64 *))(*(_QWORD *)v22 + 56LL))(
                             v22,
                             &v25);
        if ( MediaServerByUDN >= 0 )
        {
          v9 = v25;
          v10 = 0;
          v23 = 0;
          MediaServerByUDN = 0;
          if ( v25 )
          {
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v23);
            MediaServerByUDN = RoGetAgileReference(0, &GUID_6550c614_7e79_4549_8064_681b3fca61df, v9, &v23);
            v10 = v23;
          }
          v23 = 0;
          v26 = *((_QWORD *)this + 43);
          *((_QWORD *)this + 43) = v10;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v26);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v23);
          if ( MediaServerByUDN >= 0 )
          {
            *((_BYTE *)this + 385) = IsMicrosoftMediaServer(v22);
            MediaServerByUDN = (*(__int64 (__fastcall **)(struct Windows::Media::Streaming::Internal::IMediaServer *, char *))(*(_QWORD *)v22 + 80LL))(
                                 v22,
                                 (char *)this + 384);
            if ( MediaServerByUDN >= 0 )
            {
              v11 = *(_QWORD *)v4;
              v12 = *(__int64 (__fastcall **)(__int64, const wchar_t *, PROPVARIANT *))(**(_QWORD **)v4 + 24LL);
              PropVariantClear(&pvar);
              MediaServerByUDN = v12(v11, L"UPnPClass", &pvar);
              if ( MediaServerByUDN >= 0 )
              {
                if ( pvar.vt == 31 && pvar.hVal.QuadPart )
                {
                  v13 = CPropVariant::GetString((CPropVariant *)&pvar);
                  if ( !v13 )
                  {
                    MediaServerByUDN = -2147467261;
                    goto LABEL_22;
                  }
                }
                else
                {
                  v13 = &String1;
                }
                MediaServerByUDN = Windows::Internal::String::_InitializeHelper((HSTRING *)this + 49, v13);
                if ( MediaServerByUDN >= 0 )
                {
                  v14 = *(_QWORD *)v4;
                  v15 = *(int (__fastcall **)(__int64, const wchar_t *, PROPVARIANT *))(**(_QWORD **)v4 + 24LL);
                  PropVariantClear(&pvar);
                  if ( v15(v14, L"SortCaps", &pvar) >= 0 )
                  {
                    lVal = 0;
                    if ( pvar.vt == 19 )
                      lVal = pvar.lVal;
                    *((_DWORD *)this + 97) = lVal;
                  }
                  if ( !*((_DWORD *)this + 97) )
                    CContentDirectoryRowset::_GetSortCapabilitiesFromCDS(this);
                }
              }
            }
          }
        }
      }
    }
LABEL_22:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v25);
    if ( MediaServerByUDN < 0 )
      goto LABEL_31;
  }
  if ( !*((_BYTE *)this + 384)
    || (v17 = 0,
        v18 = *(_QWORD *)v4,
        v19 = *(int (__fastcall **)(__int64, const wchar_t *, PROPVARIANT *))(**(_QWORD **)v4 + 24LL),
        PropVariantClear(&pvar),
        v19(v18, L"Depth", &pvar) >= 0)
    && pvar.lVal == 1 )
  {
    v17 = 1;
  }
  *((_QWORD *)this + 47) = 0;
  if ( v17 )
    v20 = CContentDirectoryRowset::_ContentDirectoryBrowse(this, a2);
  else
    v20 = CContentDirectoryRowset::_ContentDirectorySearch(this, a2);
  MediaServerByUDN = v20;
LABEL_31:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((__int64 *)&v22);
  PropVariantClear(&pvar);
  return (unsigned int)MediaServerByUDN;
}

```

## disassembly

```asm
0x18001d4e0  mov     [rsp-28h+arg_10], rbx
0x18001d4e5  mov     [rsp-28h+arg_18], rsi
0x18001d4ea  push    rbp
0x18001d4eb  push    rdi
0x18001d4ec  push    r12
0x18001d4ee  push    r14
0x18001d4f0  push    r15
0x18001d4f2  mov     rbp, rsp
0x18001d4f5  sub     rsp, 80h
0x18001d4fc  mov     rax, cs:__security_cookie
0x18001d503  xor     rax, rsp
0x18001d506  mov     [rbp+var_8], rax
0x18001d50a  mov     r12d, edx
0x18001d50d  mov     r14, rcx
0x18001d510  xor     eax, eax
0x18001d512  mov     word ptr [rbp+pvar], ax
0x18001d516  mov     [rbp+var_60], rax
0x18001d51a  lea     r15, [rcx+120h]
0x18001d521  cmp     [rcx+158h], rax
0x18001d528  jnz     loc_18001D727
0x18001d52e  mov     [rbp+var_38], rax
0x18001d532  mov     rdi, [r15]
0x18001d535  mov     rax, [rdi]
0x18001d538  mov     rbx, [rax+18h]
0x18001d53c  lea     rcx, [rbp+pvar]; pvar
0x18001d540  call    cs:__imp_PropVariantClear
0x18001d546  lea     r8, [rbp+pvar]
0x18001d54a  lea     rdx, g_wszUDN; "UniqueDeviceName"
0x18001d551  mov     rcx, rdi
0x18001d554  mov     rax, rbx
0x18001d557  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d55c  mov     esi, eax
0x18001d55e  test    eax, eax
0x18001d560  js      loc_18001D71A
0x18001d566  lea     rcx, [rbp+pvar]; this
0x18001d56a  call    ?GetString@CPropVariant@@QEBAPEBGXZ; CPropVariant::GetString(void)
0x18001d56f  mov     rdx, rax; unsigned __int16 *
0x18001d572  lea     rcx, [rbp+var_28]; this
0x18001d576  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18001d57b  lea     rcx, [rbp+var_60]
0x18001d57f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18001d584  lea     rdx, [rbp+var_60]; struct Windows::Media::Streaming::Internal::IMediaServer **
0x18001d588  lea     rcx, [rbp+var_28]; struct Windows::Internal::String *
0x18001d58c  call    ?FindMediaServerByUDN@@YAJAEBVString@Internal@Windows@@PEAPEAUIMediaServer@2Streaming@Media@3@@Z; FindMediaServerByUDN(Windows::Internal::String const &,Windows::Media::Streaming::Internal::IMediaServer * *)
0x18001d591  mov     esi, eax
0x18001d593  test    eax, eax
0x18001d595  js      loc_18001D71A
0x18001d59b  mov     rcx, [rbp+var_60]
0x18001d59f  mov     rax, [rcx]
0x18001d5a2  lea     rdx, [rbp+var_38]
0x18001d5a6  mov     rax, [rax+38h]
0x18001d5aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d5af  mov     esi, eax
0x18001d5b1  test    eax, eax
0x18001d5b3  js      loc_18001D71A
0x18001d5b9  mov     rbx, [rbp+var_38]
0x18001d5bd  xor     eax, eax
0x18001d5bf  mov     [rbp+var_58], rax
0x18001d5c3  xor     esi, esi
0x18001d5c5  test    rbx, rbx
0x18001d5c8  jz      short loc_18001D5EF
0x18001d5ca  lea     rcx, [rbp+var_58]
0x18001d5ce  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18001d5d3  lea     r9, [rbp+var_58]
0x18001d5d7  mov     r8, rbx
0x18001d5da  lea     rdx, _GUID_6550c614_7e79_4549_8064_681b3fca61df
0x18001d5e1  xor     ecx, ecx
0x18001d5e3  call    cs:__imp_RoGetAgileReference
0x18001d5e9  mov     esi, eax
0x18001d5eb  mov     rax, [rbp+var_58]
0x18001d5ef  mov     [rbp+var_58], 0
0x18001d5f7  mov     rcx, [r14+158h]
0x18001d5fe  mov     [rbp+var_30], rcx
0x18001d602  mov     [r14+158h], rax
0x18001d609  lea     rcx, [rbp+var_30]
0x18001d60d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18001d612  lea     rcx, [rbp+var_58]
0x18001d616  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18001d61b  test    esi, esi
0x18001d61d  js      loc_18001D71A
0x18001d623  mov     rcx, [rbp+var_60]; struct Windows::Media::Streaming::Internal::IMediaServer *
0x18001d627  call    ?IsMicrosoftMediaServer@@YAEPEAUIMediaServer@Internal@Streaming@Media@Windows@@@Z; IsMicrosoftMediaServer(Windows::Media::Streaming::Internal::IMediaServer *)
0x18001d62c  mov     [r14+181h], al
0x18001d633  mov     rcx, [rbp+var_60]
0x18001d637  mov     rax, [rcx]
0x18001d63a  lea     rdx, [r14+180h]
0x18001d641  mov     rax, [rax+50h]
0x18001d645  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d64a  mov     esi, eax
0x18001d64c  test    eax, eax
0x18001d64e  js      loc_18001D71A
0x18001d654  mov     rdi, [r15]
0x18001d657  mov     rax, [rdi]
0x18001d65a  mov     rbx, [rax+18h]
0x18001d65e  lea     rcx, [rbp+pvar]; pvar
0x18001d662  call    cs:__imp_PropVariantClear
0x18001d668  lea     r8, [rbp+pvar]
0x18001d66c  lea     rdx, g_wszUPnPClass; "UPnPClass"
0x18001d673  mov     rcx, rdi
0x18001d676  mov     rax, rbx
0x18001d679  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d67e  mov     esi, eax
0x18001d680  test    eax, eax
0x18001d682  js      loc_18001D71A
0x18001d688  cmp     word ptr [rbp+pvar], 1Fh
0x18001d68d  jnz     short loc_18001D6AB
0x18001d68f  cmp     qword ptr [rbp+pvar+8], 0
0x18001d694  jz      short loc_18001D6AB
0x18001d696  lea     rcx, [rbp+pvar]; this
0x18001d69a  call    ?GetString@CPropVariant@@QEBAPEBGXZ; CPropVariant::GetString(void)
0x18001d69f  test    rax, rax
0x18001d6a2  jnz     short loc_18001D6B2
0x18001d6a4  mov     esi, 80004003h
0x18001d6a9  jmp     short loc_18001D71A
0x18001d6ab  lea     rax, String1
0x18001d6b2  lea     rcx, [r14+188h]; this
0x18001d6b9  mov     rdx, rax; unsigned __int16 *
0x18001d6bc  call    ?_InitializeHelper@String@Internal@Windows@@AEAAJPEBG@Z; Windows::Internal::String::_InitializeHelper(ushort const *)
0x18001d6c1  mov     esi, eax
0x18001d6c3  test    eax, eax
0x18001d6c5  js      short loc_18001D71A
0x18001d6c7  mov     rdi, [r15]
0x18001d6ca  mov     rax, [rdi]
0x18001d6cd  mov     rbx, [rax+18h]
0x18001d6d1  lea     rcx, [rbp+pvar]; pvar
0x18001d6d5  call    cs:__imp_PropVariantClear
0x18001d6db  lea     r8, [rbp+pvar]
0x18001d6df  lea     rdx, g_wszSortCapabilities; "SortCaps"
0x18001d6e6  mov     rcx, rdi
0x18001d6e9  mov     rax, rbx
0x18001d6ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d6f1  test    eax, eax
0x18001d6f3  js      short loc_18001D707
0x18001d6f5  xor     eax, eax
0x18001d6f7  cmp     word ptr [rbp+pvar], 13h
0x18001d6fc  cmovz   eax, dword ptr [rbp+pvar+8]
0x18001d700  mov     [r14+184h], eax
0x18001d707  cmp     dword ptr [r14+184h], 0
0x18001d70f  jnz     short loc_18001D71A
0x18001d711  mov     rcx, r14; this
0x18001d714  call    ?_GetSortCapabilitiesFromCDS@CContentDirectoryRowset@@AEAAJXZ; CContentDirectoryRowset::_GetSortCapabilitiesFromCDS(void)
0x18001d719  nop
0x18001d71a  lea     rcx, [rbp+var_38]
0x18001d71e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18001d723  test    esi, esi
0x18001d725  js      short loc_18001D78F
0x18001d727  cmp     byte ptr [r14+180h], 0
0x18001d72f  jz      short loc_18001D767
0x18001d731  xor     esi, esi
0x18001d733  mov     rdi, [r15]
0x18001d736  mov     rax, [rdi]
0x18001d739  mov     rbx, [rax+18h]
0x18001d73d  lea     rcx, [rbp+pvar]; pvar
0x18001d741  call    cs:__imp_PropVariantClear
0x18001d747  lea     r8, [rbp+pvar]
0x18001d74b  lea     rdx, g_wszDepth; "Depth"
0x18001d752  mov     rcx, rdi
0x18001d755  mov     rax, rbx
0x18001d758  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d75d  test    eax, eax
0x18001d75f  js      short loc_18001D76C
0x18001d761  cmp     dword ptr [rbp+pvar+8], 1
0x18001d765  jnz     short loc_18001D76C
0x18001d767  mov     esi, 1
0x18001d76c  mov     qword ptr [r14+178h], 0
0x18001d777  mov     edx, r12d; unsigned int
0x18001d77a  mov     rcx, r14; this
0x18001d77d  test    esi, esi
0x18001d77f  jnz     short loc_18001D788
0x18001d781  call    ?_ContentDirectorySearch@CContentDirectoryRowset@@AEAAJK@Z; CContentDirectoryRowset::_ContentDirectorySearch(ulong)
0x18001d786  jmp     short loc_18001D78D
0x18001d788  call    ?_ContentDirectoryBrowse@CContentDirectoryRowset@@AEAAJK@Z; CContentDirectoryRowset::_ContentDirectoryBrowse(ulong)
0x18001d78d  mov     esi, eax
0x18001d78f  lea     rcx, [rbp+var_60]
0x18001d793  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18001d798  nop
0x18001d799  lea     rcx, [rbp+pvar]; pvar
0x18001d79d  call    cs:__imp_PropVariantClear
0x18001d7a3  mov     eax, esi
0x18001d7a5  mov     rcx, [rbp+var_8]
0x18001d7a9  xor     rcx, rsp; StackCookie
0x18001d7ac  call    __security_check_cookie
0x18001d7b1  lea     r11, [rsp+80h+var_s0]
0x18001d7b9  mov     rbx, [r11+40h]
0x18001d7bd  mov     rsi, [r11+48h]
0x18001d7c1  mov     rsp, r11
0x18001d7c4  pop     r15
0x18001d7c6  pop     r14
0x18001d7c8  pop     r12
0x18001d7ca  pop     rdi
0x18001d7cb  pop     rbp
0x18001d7cc  retn
```
