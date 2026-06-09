# CContentDirectoryRowset::_QueryResults(Windows::Media::Streaming::Internal::IContentRequest *,ulong,int)

- ea: `0x18001dd80`
- end: `0x18001e218`
- name: `?_QueryResults@CContentDirectoryRowset@@AEAAJPEAUIContentRequest@Internal@Streaming@Media@Windows@@KH@Z`
- size: `1176`
- prototype: `__int64 __fastcall(CContentDirectoryRowset *__hidden this, struct Windows::Media::Streaming::Internal::IContentRequest *, unsigned int, int)`
- caller_count: `3`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18001c744`
- `0x18001cc50`
- `0x18001d840`

## callees

- `0x180001710`
- `0x180014a00`
- `0x180016ce4`
- `0x18001aec0`
- `0x18001dd80`
- `0x18001e5c0`
- `0x18001e734`
- `0x1800270b0`
- `0x180027260`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001df07`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001e1e0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001df07`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001e1e0`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CContentDirectoryRowset::_QueryResults(
        CContentDirectoryRowset *this,
        struct Windows::Media::Streaming::Internal::IContentRequest *a2,
        unsigned int a3,
        int a4)
{
  __int64 v5; // r15
  __int64 (__fastcall *v8)(struct Windows::Media::Streaming::Internal::IContentRequest *, __int64 *); // rbx
  int v9; // ebx
  __int64 (__fastcall *v10)(struct Windows::Media::Streaming::Internal::IContentRequest *, __int64 *); // rbx
  unsigned int v11; // ecx
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, const wchar_t *, PROPVARIANT *); // rbx
  unsigned int i; // r14d
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, _QWORD, __int64 *); // rbx
  char v17; // di
  unsigned int j; // r14d
  unsigned int v19; // r8d
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, _QWORD, __int64 *); // rbx
  __int64 v22; // r8
  char v23; // bl
  __int64 v24; // rcx
  int v25; // eax
  struct IPropertyStore *v27; // [rsp+50h] [rbp-39h] BYREF
  __int64 v28; // [rsp+58h] [rbp-31h] BYREF
  unsigned int v29; // [rsp+60h] [rbp-29h] BYREF
  __int64 v30; // [rsp+68h] [rbp-21h] BYREF
  __int64 v31; // [rsp+70h] [rbp-19h] BYREF
  __int64 v32; // [rsp+78h] [rbp-11h] BYREF
  __int64 v33; // [rsp+80h] [rbp-9h] BYREF
  PROPVARIANT pvar; // [rsp+88h] [rbp-1h] BYREF
  __int128 v35; // [rsp+A0h] [rbp+17h] BYREF
  __int64 v36; // [rsp+B0h] [rbp+27h]
  unsigned int v37; // [rsp+F0h] [rbp+67h] BYREF
  unsigned int v38; // [rsp+F8h] [rbp+6Fh] BYREF

  v5 = a3;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_ccc67dfc5e8536d1cefd651d689cad4f_Traceguids);
  v38 = 0;
  v37 = 0;
  v32 = 0;
  v31 = 0;
  pvar.vt = 0;
  v8 = *(__int64 (__fastcall **)(struct Windows::Media::Streaming::Internal::IContentRequest *, __int64 *))(*(_QWORD *)a2 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v32);
  v9 = v8(a2, &v32);
  if ( v9 >= 0 )
  {
    v9 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v32 + 56LL))(v32, &v38);
    if ( v9 >= 0 )
    {
      v10 = *(__int64 (__fastcall **)(struct Windows::Media::Streaming::Internal::IContentRequest *, __int64 *))(*(_QWORD *)a2 + 56LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v31);
      v9 = v10(a2, &v31);
      if ( v9 >= 0 )
        v9 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v31 + 56LL))(v31, &v37);
    }
  }
  v11 = 0;
  v29 = 0;
  if ( v9 >= 0 )
  {
    v9 = (*(__int64 (__fastcall **)(struct Windows::Media::Streaming::Internal::IContentRequest *, unsigned int *))(*(_QWORD *)a2 + 72LL))(
           a2,
           &v29);
    if ( v9 < 0 )
    {
      v11 = v29;
    }
    else
    {
      v11 = v29;
      if ( v29 )
        *((_QWORD *)this + 6) = v29;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_qDlDDD(*((_QWORD *)WPP_GLOBAL_Control + 2), a4 != 0, WPP_GLOBAL_Control, this, v5, a4 != 0, v38, v37, v11);
  }
  if ( v9 >= 0 )
  {
    v12 = *((_QWORD *)this + 36);
    v13 = *(__int64 (__fastcall **)(__int64, const wchar_t *, PROPVARIANT *))(*(_QWORD *)v12 + 24LL);
    PropVariantClear(&pvar);
    v9 = v13(v12, L"AbsolutePIDL", &pvar);
  }
  for ( i = *((_DWORD *)this + 94); v9 >= 0 && i < v38; ++i )
  {
    v28 = 0;
    v33 = 0;
    v15 = v32;
    v16 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v32 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v28);
    v9 = v16(v15, i, &v28);
    if ( v9 >= 0 )
    {
      v27 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((__int64 *)&v27);
      v17 = *((_BYTE *)this + 385);
      v30 = v28;
      if ( v28 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 8LL))(v28);
      v9 = CCdsItemSorterAndPropertyMapper::MapItem((__int64)this + 352, (unsigned __int16 *)&v30, v17, &v27);
      if ( v9 >= 0 )
      {
        v9 = PreparePropStoreForProvider(v27, &pvar);
        if ( v9 >= 0 )
          v9 = CContentDirectoryRowset::CACHED_RESULT_PAGE::AddRow(
                 (CContentDirectoryRowset *)((char *)this + 32 * v5 + 8 * v5 + 72),
                 v27);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((__int64 *)&v27);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v33);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v28);
  }
  *((_DWORD *)this + 94) = v38;
  for ( j = *((_DWORD *)this + 95); ; ++j )
  {
    v19 = v37;
    if ( v9 < 0 || j >= v37 )
      break;
    v28 = 0;
    v33 = 0;
    v20 = v31;
    v21 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v31 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v28);
    v9 = v21(v20, j, &v28);
    if ( v9 >= 0 )
    {
      v27 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((__int64 *)&v27);
      v23 = *((_BYTE *)this + 385);
      v24 = v28;
      v30 = v28;
      if ( v28 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 8LL))(v28);
      LOBYTE(v22) = v23;
      v9 = CCdsItemSorterAndPropertyMapper::MapContainer(v24, &v30, v22, &v27);
      if ( v9 >= 0 )
      {
        v25 = *((_DWORD *)this + 97);
        if ( v25 )
        {
          v35 = 0;
          v36 = 0;
          LOWORD(v35) = 19;
          DWORD2(v35) = v25;
          ((void (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, __int128 *))v27->lpVtbl->SetValue)(
            v27,
            &PKEY_SortCapabilities,
            &v35);
        }
        v9 = PreparePropStoreForProvider(v27, &pvar);
        if ( v9 >= 0 )
          v9 = CContentDirectoryRowset::CACHED_RESULT_PAGE::AddRow(
                 (CContentDirectoryRowset *)((char *)this + 32 * v5 + 8 * v5 + 72),
                 v27);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((__int64 *)&v27);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v33);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v28);
  }
  *((_DWORD *)this + 95) = v37;
  if ( v9 >= 0
    && (a4 && *((_DWORD *)this + 10 * v5 + 24) || *((_DWORD *)this + 10 * v5 + 24) >= *((_DWORD *)this + 10 * v5 + 20)) )
  {
    ++*((_DWORD *)this + 70);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_Ddddd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      24,
      &WPP_ccc67dfc5e8536d1cefd651d689cad4f_Traceguids,
      (unsigned int)v9,
      v5,
      *((_DWORD *)this + 10 * v5 + 24),
      v38,
      v19);
  }
  PropVariantClear(&pvar);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v31);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v32);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001dd80  mov     [rsp-8+arg_10], rbx
0x18001dd85  mov     [rsp-8+arg_18], rsi
0x18001dd8a  push    rbp
0x18001dd8b  push    rdi
0x18001dd8c  push    r12
0x18001dd8e  push    r14
0x18001dd90  push    r15
0x18001dd92  lea     rbp, [rsp-37h]
0x18001dd97  sub     rsp, 0C0h
0x18001dd9e  mov     r12d, r9d
0x18001dda1  mov     r15d, r8d
0x18001dda4  mov     rdi, rdx
0x18001dda7  mov     rsi, rcx
0x18001ddaa  lea     r14, WPP_GLOBAL_Control
0x18001ddb1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ddb8  cmp     rcx, r14
0x18001ddbb  jz      short loc_18001DDD8
0x18001ddbd  test    byte ptr [rcx+1Ch], 2
0x18001ddc1  jz      short loc_18001DDD8
0x18001ddc3  mov     edx, 16h
0x18001ddc8  lea     r8, WPP_ccc67dfc5e8536d1cefd651d689cad4f_Traceguids
0x18001ddcf  mov     rcx, [rcx+10h]
0x18001ddd3  call    WPP_SF_
0x18001ddd8  mov     [rbp+57h+arg_8], 0
0x18001dddf  mov     [rbp+57h+arg_0], 0
0x18001dde6  mov     [rbp+57h+var_68], 0
0x18001ddee  mov     [rbp+57h+var_70], 0
0x18001ddf6  xor     eax, eax
0x18001ddf8  mov     word ptr [rbp+57h+pvar], ax
0x18001ddfc  mov     rax, [rdi]
0x18001ddff  mov     rbx, [rax+30h]
0x18001de03  lea     rcx, [rbp+57h+var_68]
0x18001de07  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18001de0c  lea     rdx, [rbp+57h+var_68]
0x18001de10  mov     rcx, rdi
0x18001de13  mov     rax, rbx
0x18001de16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de1b  mov     ebx, eax
0x18001de1d  test    eax, eax
0x18001de1f  js      short loc_18001DE76
0x18001de21  mov     rcx, [rbp+57h+var_68]
0x18001de25  mov     rax, [rcx]
0x18001de28  lea     rdx, [rbp+57h+arg_8]
0x18001de2c  mov     rax, [rax+38h]
0x18001de30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de35  mov     ebx, eax
0x18001de37  test    eax, eax
0x18001de39  js      short loc_18001DE76
0x18001de3b  mov     rax, [rdi]
0x18001de3e  mov     rbx, [rax+38h]
0x18001de42  lea     rcx, [rbp+57h+var_70]
0x18001de46  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18001de4b  lea     rdx, [rbp+57h+var_70]
0x18001de4f  mov     rcx, rdi
0x18001de52  mov     rax, rbx
0x18001de55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de5a  mov     ebx, eax
0x18001de5c  test    eax, eax
0x18001de5e  js      short loc_18001DE76
0x18001de60  mov     rcx, [rbp+57h+var_70]
0x18001de64  mov     rax, [rcx]
0x18001de67  lea     rdx, [rbp+57h+arg_0]
0x18001de6b  mov     rax, [rax+38h]
0x18001de6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de74  mov     ebx, eax
0x18001de76  xor     ecx, ecx
0x18001de78  mov     [rbp+57h+var_80], ecx
0x18001de7b  test    ebx, ebx
0x18001de7d  js      short loc_18001DEA8
0x18001de7f  mov     rax, [rdi]
0x18001de82  lea     rdx, [rbp+57h+var_80]
0x18001de86  mov     rcx, rdi
0x18001de89  mov     rax, [rax+48h]
0x18001de8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de92  mov     ebx, eax
0x18001de94  test    eax, eax
0x18001de96  js      short loc_18001DEA5
0x18001de98  mov     ecx, [rbp+57h+var_80]
0x18001de9b  test    ecx, ecx
0x18001de9d  jz      short loc_18001DEA8
0x18001de9f  mov     [rsi+30h], rcx
0x18001dea3  jmp     short loc_18001DEA8
0x18001dea5  mov     ecx, [rbp+57h+var_80]
0x18001dea8  mov     r8, cs:WPP_GLOBAL_Control
0x18001deaf  cmp     r8, r14
0x18001deb2  jz      short loc_18001DEF1
0x18001deb4  test    byte ptr [r8+1Ch], 40h
0x18001deb9  jz      short loc_18001DEF1
0x18001debb  cmp     byte ptr [r8+19h], 4
0x18001dec0  jb      short loc_18001DEF1
0x18001dec2  xor     edx, edx
0x18001dec4  test    r12d, r12d
0x18001dec7  setnz   dl
0x18001deca  mov     [rsp+0E0h+var_A0], ecx
0x18001dece  mov     eax, [rbp+57h+arg_0]
0x18001ded1  mov     [rsp+0E0h+var_A8], eax
0x18001ded5  mov     eax, [rbp+57h+arg_8]
0x18001ded8  mov     [rsp+0E0h+var_B0], eax
0x18001dedc  mov     [rsp+0E0h+var_B8], edx
0x18001dee0  mov     [rsp+0E0h+var_C0], r15d
0x18001dee5  mov     r9, rsi
0x18001dee8  mov     rcx, [r8+10h]
0x18001deec  call    WPP_SF_qDlDDD
0x18001def1  test    ebx, ebx
0x18001def3  js      short loc_18001DF25
0x18001def5  mov     rdi, [rsi+120h]
0x18001defc  mov     rax, [rdi]
0x18001deff  mov     rbx, [rax+18h]
0x18001df03  lea     rcx, [rbp+57h+pvar]; pvar
0x18001df07  call    cs:__imp_PropVariantClear
0x18001df0d  lea     r8, [rbp+57h+pvar]
0x18001df11  lea     rdx, g_wszAbsolutePIDL; "AbsolutePIDL"
0x18001df18  mov     rcx, rdi
0x18001df1b  mov     rax, rbx
0x18001df1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df23  mov     ebx, eax
0x18001df25  mov     r14d, [rsi+178h]
0x18001df2c  jmp     loc_18001E017
0x18001df31  cmp     r14d, [rbp+57h+arg_8]
0x18001df35  jnb     loc_18001E01F
0x18001df3b  mov     [rbp+57h+var_88], 0
0x18001df43  mov     [rbp+57h+var_60], 0
0x18001df4b  mov     rdi, [rbp+57h+var_68]
0x18001df4f  mov     rax, [rdi]
0x18001df52  mov     rbx, [rax+30h]
0x18001df56  lea     rcx, [rbp+57h+var_88]
0x18001df5a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18001df5f  lea     r8, [rbp+57h+var_88]
0x18001df63  mov     edx, r14d
0x18001df66  mov     rcx, rdi
0x18001df69  mov     rax, rbx
0x18001df6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df71  mov     ebx, eax
0x18001df73  test    eax, eax
0x18001df75  js      loc_18001E001
0x18001df7b  mov     [rbp+57h+var_90], 0
0x18001df83  lea     rcx, [rbp+57h+var_90]
0x18001df87  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18001df8c  mov     dil, [rsi+181h]
0x18001df93  mov     rcx, [rbp+57h+var_88]
0x18001df97  mov     [rbp+57h+var_78], rcx
0x18001df9b  test    rcx, rcx
0x18001df9e  jz      short loc_18001DFAD
0x18001dfa0  mov     rax, [rcx]
0x18001dfa3  mov     rax, [rax+8]
0x18001dfa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dfac  nop
0x18001dfad  lea     r9, [rbp+57h+var_90]
0x18001dfb1  mov     r8b, dil
0x18001dfb4  lea     rdx, [rbp+57h+var_78]
0x18001dfb8  lea     rcx, [rsi+160h]
0x18001dfbf  call    ?MapItem@CCdsItemSorterAndPropertyMapper@@QEAAJV?$ComPtr@UIContentDirectoryItem@Internal@Streaming@Media@Windows@@@WRL@Microsoft@@EPEAPEAUIPropertyStore@@@Z; CCdsItemSorterAndPropertyMapper::MapItem(Microsoft::WRL::ComPtr<Windows::Media::Streaming::Internal::IContentDirectoryItem>,uchar,IPropertyStore * *)
0x18001dfc4  mov     ebx, eax
0x18001dfc6  test    eax, eax
0x18001dfc8  js      short loc_18001DFF7
0x18001dfca  lea     rdx, [rbp+57h+pvar]; struct tagPROPVARIANT *
0x18001dfce  mov     rcx, [rbp+57h+var_90]; struct IPropertyStore *
0x18001dfd2  call    ?PreparePropStoreForProvider@@YAJPEAUIPropertyStore@@AEBUtagPROPVARIANT@@@Z; PreparePropStoreForProvider(IPropertyStore *,tagPROPVARIANT const &)
0x18001dfd7  mov     ebx, eax
0x18001dfd9  test    eax, eax
0x18001dfdb  js      short loc_18001DFF7
0x18001dfdd  lea     rcx, ds:9[r15*4]
0x18001dfe5  add     rcx, r15
0x18001dfe8  lea     rcx, [rsi+rcx*8]; this
0x18001dfec  mov     rdx, [rbp+57h+var_90]; struct IPropertyStore *
0x18001dff0  call    ?AddRow@CACHED_RESULT_PAGE@CContentDirectoryRowset@@QEAAJPEAUIPropertyStore@@@Z; CContentDirectoryRowset::CACHED_RESULT_PAGE::AddRow(IPropertyStore *)
0x18001dff5  mov     ebx, eax
0x18001dff7  lea     rcx, [rbp+57h+var_90]
0x18001dffb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18001e000  nop
0x18001e001  lea     rcx, [rbp+57h+var_60]
0x18001e005  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18001e00a  nop
0x18001e00b  lea     rcx, [rbp+57h+var_88]
0x18001e00f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18001e014  inc     r14d
0x18001e017  test    ebx, ebx
0x18001e019  jns     loc_18001DF31
0x18001e01f  mov     eax, [rbp+57h+arg_8]
0x18001e022  mov     [rsi+178h], eax
0x18001e028  mov     r14d, [rsi+17Ch]
0x18001e02f  mov     r8d, [rbp+57h+arg_0]
0x18001e033  test    ebx, ebx
0x18001e035  js      loc_18001E15B
0x18001e03b  cmp     r14d, r8d
0x18001e03e  jnb     loc_18001E15B
0x18001e044  mov     [rbp+57h+var_88], 0
0x18001e04c  mov     [rbp+57h+var_60], 0
0x18001e054  mov     rdi, [rbp+57h+var_70]
0x18001e058  mov     rax, [rdi]
0x18001e05b  mov     rbx, [rax+30h]
0x18001e05f  lea     rcx, [rbp+57h+var_88]
0x18001e063  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18001e068  lea     r8, [rbp+57h+var_88]
0x18001e06c  mov     edx, r14d
0x18001e06f  mov     rcx, rdi
0x18001e072  mov     rax, rbx
0x18001e075  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e07a  mov     ebx, eax
0x18001e07c  test    eax, eax
0x18001e07e  js      loc_18001E140
0x18001e084  mov     [rbp+57h+var_90], 0
0x18001e08c  lea     rcx, [rbp+57h+var_90]
0x18001e090  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18001e095  mov     bl, [rsi+181h]
0x18001e09b  mov     rcx, [rbp+57h+var_88]
0x18001e09f  mov     [rbp+57h+var_78], rcx
0x18001e0a3  test    rcx, rcx
0x18001e0a6  jz      short loc_18001E0B5
0x18001e0a8  mov     rax, [rcx]
0x18001e0ab  mov     rax, [rax+8]
0x18001e0af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e0b4  nop
0x18001e0b5  lea     r9, [rbp+57h+var_90]
0x18001e0b9  mov     r8b, bl
0x18001e0bc  lea     rdx, [rbp+57h+var_78]
0x18001e0c0  call    ?MapContainer@CCdsItemSorterAndPropertyMapper@@QEAAJV?$ComPtr@UIContentDirectoryContainer@Internal@Streaming@Media@Windows@@@WRL@Microsoft@@EPEAPEAUIPropertyStore@@@Z; CCdsItemSorterAndPropertyMapper::MapContainer(Microsoft::WRL::ComPtr<Windows::Media::Streaming::Internal::IContentDirectoryContainer>,uchar,IPropertyStore * *)
0x18001e0c5  mov     ebx, eax
0x18001e0c7  test    eax, eax
0x18001e0c9  js      short loc_18001E136
0x18001e0cb  mov     eax, [rsi+184h]
0x18001e0d1  test    eax, eax
0x18001e0d3  jz      short loc_18001E109
0x18001e0d5  xorps   xmm0, xmm0
0x18001e0d8  xor     ecx, ecx
0x18001e0da  movups  [rbp+57h+var_40], xmm0
0x18001e0de  mov     [rbp+57h+var_30], rcx
0x18001e0e2  mov     ecx, 13h
0x18001e0e7  mov     word ptr [rbp+57h+var_40], cx
0x18001e0eb  mov     dword ptr [rbp+57h+var_40+8], eax
0x18001e0ee  mov     rcx, [rbp+57h+var_90]
0x18001e0f2  mov     rax, [rcx]
0x18001e0f5  lea     r8, [rbp+57h+var_40]
0x18001e0f9  lea     rdx, PKEY_SortCapabilities
0x18001e100  mov     rax, [rax+30h]
0x18001e104  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e109  lea     rdx, [rbp+57h+pvar]; struct tagPROPVARIANT *
0x18001e10d  mov     rcx, [rbp+57h+var_90]; struct IPropertyStore *
0x18001e111  call    ?PreparePropStoreForProvider@@YAJPEAUIPropertyStore@@AEBUtagPROPVARIANT@@@Z; PreparePropStoreForProvider(IPropertyStore *,tagPROPVARIANT const &)
0x18001e116  mov     ebx, eax
0x18001e118  test    eax, eax
0x18001e11a  js      short loc_18001E136
0x18001e11c  lea     rcx, ds:9[r15*4]
0x18001e124  add     rcx, r15
0x18001e127  lea     rcx, [rsi+rcx*8]; this
0x18001e12b  mov     rdx, [rbp+57h+var_90]; struct IPropertyStore *
0x18001e12f  call    ?AddRow@CACHED_RESULT_PAGE@CContentDirectoryRowset@@QEAAJPEAUIPropertyStore@@@Z; CContentDirectoryRowset::CACHED_RESULT_PAGE::AddRow(IPropertyStore *)
0x18001e134  mov     ebx, eax
0x18001e136  lea     rcx, [rbp+57h+var_90]
0x18001e13a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18001e13f  nop
0x18001e140  lea     rcx, [rbp+57h+var_60]
0x18001e144  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18001e149  nop
0x18001e14a  lea     rcx, [rbp+57h+var_88]
0x18001e14e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18001e153  inc     r14d
0x18001e156  jmp     loc_18001E02F
0x18001e15b  mov     [rsi+17Ch], r8d
0x18001e162  test    ebx, ebx
0x18001e164  js      short loc_18001E186
0x18001e166  lea     rcx, [r15+r15*4]
0x18001e16a  test    r12d, r12d
0x18001e16d  jz      short loc_18001E176
0x18001e16f  cmp     dword ptr [rsi+rcx*8+60h], 0
0x18001e174  ja      short loc_18001E180
0x18001e176  mov     eax, [rsi+rcx*8+50h]
0x18001e17a  cmp     [rsi+rcx*8+60h], eax
0x18001e17e  jb      short loc_18001E186
0x18001e180  inc     dword ptr [rsi+118h]
0x18001e186  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e18d  lea     rax, WPP_GLOBAL_Control
0x18001e194  cmp     rcx, rax
0x18001e197  jz      short loc_18001E1DC
0x18001e199  test    byte ptr [rcx+1Ch], 40h
0x18001e19d  jz      short loc_18001E1DC
0x18001e19f  cmp     byte ptr [rcx+19h], 4
0x18001e1a3  jb      short loc_18001E1DC
0x18001e1a5  lea     r9, [r15+r15*4]
0x18001e1a9  mov     edx, 18h
0x18001e1ae  mov     [rsp+0E0h+var_A8], r8d
0x18001e1b3  mov     eax, [rbp+57h+arg_8]
0x18001e1b6  mov     [rsp+0E0h+var_B0], eax
0x18001e1ba  mov     eax, [rsi+r9*8+60h]
0x18001e1bf  mov     [rsp+0E0h+var_B8], eax
0x18001e1c3  mov     [rsp+0E0h+var_C0], r15d
0x18001e1c8  mov     r9d, ebx
0x18001e1cb  lea     r8, WPP_ccc67dfc5e8536d1cefd651d689cad4f_Traceguids
0x18001e1d2  mov     rcx, [rcx+10h]
0x18001e1d6  call    WPP_SF_Ddddd
0x18001e1db  nop
0x18001e1dc  lea     rcx, [rbp+57h+pvar]; pvar
0x18001e1e0  call    cs:__imp_PropVariantClear
0x18001e1e6  nop
0x18001e1e7  lea     rcx, [rbp+57h+var_70]
0x18001e1eb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18001e1f0  nop
0x18001e1f1  lea     rcx, [rbp+57h+var_68]
0x18001e1f5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18001e1fa  mov     eax, ebx
  ... truncated ...
```
