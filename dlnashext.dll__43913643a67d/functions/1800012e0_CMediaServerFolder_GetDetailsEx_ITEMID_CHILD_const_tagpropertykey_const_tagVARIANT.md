# CMediaServerFolder::GetDetailsEx(_ITEMID_CHILD const *,_tagpropertykey const *,tagVARIANT *)

- ea: `0x1800012e0`
- end: `0x1800016fc`
- name: `?GetDetailsEx@CMediaServerFolder@@UEAAJPEFBU_ITEMID_CHILD@@PEBU_tagpropertykey@@PEAUtagVARIANT@@@Z`
- size: `1052`
- prototype: `int(CMediaServerFolder *__hidden this, const struct _ITEMID_CHILD *, const struct _tagpropertykey *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x1800012e0`
- `0x180001710`
- `0x1800075a0`
- `0x18000a4a0`
- `0x180011930`
- `0x18001681c`
- `0x18001dd14`
- `0x18001f8ac`
- `0x1800200e8`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000167c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800016d3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000167c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800016d3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800014cc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800014cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800014d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800014d6`
- `OLEAUT32!__imp_VariantInit` at `0x18000131a`
- `OLEAUT32!__imp_VariantInit` at `0x18000131a`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x18000136e`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x18000136e`
- `PROPSYS!PropVariantToVariant` at `0x1800013e9`
- `PROPSYS!PropVariantToVariant` at `0x1800013e9`
- `PROPSYS!InitVariantFromBuffer` at `0x180001480`
- `PROPSYS!InitVariantFromBuffer` at `0x180001480`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180001670`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180001670`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CMediaServerFolder::GetDetailsEx(
        CMediaServerFolder *this,
        const struct _ITEMID_CHILD *a2,
        const struct _tagpropertykey *a3,
        struct tagVARIANT *a4)
{
  unsigned __int64 v8; // rax
  __int64 v9; // rdx
  int PropertyFromIDList; // ebx
  VARTYPE vt; // ax
  __int64 v12; // rax
  DWORD pid; // eax
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // rax
  signed int LastError; // eax
  HSTRING v18; // rdi
  const unsigned __int16 *v19; // rax
  struct Windows::Media::Streaming::IBasicDevice *v20; // rbx
  __int64 (__fastcall *v21)(struct Windows::Media::Streaming::IBasicDevice *, GUID *, __int64 *); // rsi
  __int64 v22; // rsi
  __int64 (__fastcall *v23)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, LONGLONG *)); // rbx
  __int64 (__fastcall ***v25)(_QWORD, GUID *, LONGLONG *); // [rsp+20h] [rbp-E0h] BYREF
  __int64 v26; // [rsp+28h] [rbp-D8h] BYREF
  struct Windows::Media::Streaming::IBasicDevice *v27; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING string; // [rsp+38h] [rbp-C8h] BYREF
  LONGLONG v29; // [rsp+40h] [rbp-C0h] BYREF
  PROPVARIANT ppropvar; // [rsp+48h] [rbp-B8h] BYREF
  PROPVARIANT pv; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Buffer[264]; // [rsp+80h] [rbp-80h] BYREF

  VariantInit(a4);
  memset(&ppropvar, 0, sizeof(ppropvar));
  if ( a2
    && (v8 = *(unsigned __int16 *)a2, (unsigned int)v8 >= 0x12)
    && *(_DWORD *)((char *)a2 + 6) == 1159165815
    && (v9 = *((unsigned __int16 *)a2 + 5), v8 >= v9 + 18)
    && (_WORD)v9 )
  {
    PropertyFromIDList = -2147024809;
    if ( a2 == (const struct _ITEMID_CHILD *)-18LL
      || (PropertyFromIDList = PSGetPropertyFromPropertyStorage(
                                 (const struct _ITEMID_CHILD *)((char *)a2 + 18),
                                 v9,
                                 a3,
                                 &ppropvar),
          PropertyFromIDList < 0) )
    {
      vt = ppropvar.vt;
    }
    else
    {
      vt = ppropvar.vt;
      if ( !ppropvar.vt )
      {
        PropertyFromIDList = -2147023288;
        goto LABEL_15;
      }
    }
    if ( PropertyFromIDList >= 0 && vt )
    {
LABEL_21:
      PropertyFromIDList = PropVariantToVariant(&ppropvar, a4);
      goto LABEL_63;
    }
  }
  else
  {
    PropertyFromIDList = -2147024809;
  }
LABEL_15:
  if ( PKEY_ItemNameDisplay.pid == a3->pid )
  {
    v12 = *(_QWORD *)&PKEY_ItemNameDisplay.fmtid.Data1 - *(_QWORD *)&a3->fmtid.Data1;
    if ( *(_QWORD *)&PKEY_ItemNameDisplay.fmtid.Data1 == *(_QWORD *)&a3->fmtid.Data1 )
      v12 = *(_QWORD *)PKEY_ItemNameDisplay.fmtid.Data4 - *(_QWORD *)a3->fmtid.Data4;
    if ( !v12 )
      PropertyFromIDList = CItemIDFactory<MEDIASERVER_ITEMID,1159165815>::GetPropertyFromIDList(
                             a2,
                             &PKEY_DeviceDisplay_FriendlyName,
                             &ppropvar);
  }
  if ( PropertyFromIDList >= 0 )
    goto LABEL_21;
  pid = a3->pid;
  if ( pid == PKEY_DescriptionID.pid )
  {
    v14 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_DescriptionID.fmtid.Data1;
    if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_DescriptionID.fmtid.Data1 )
      v14 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_DescriptionID.fmtid.Data4;
    if ( !v14 )
      goto LABEL_30;
  }
  if ( pid == 36 )
  {
    v15 = *(_QWORD *)&a3->fmtid.Data1 - PKEY_StorageSystemType;
    if ( *(_QWORD *)&a3->fmtid.Data1 == PKEY_StorageSystemType )
      v15 = *(_QWORD *)a3->fmtid.Data4 + 0x2FE726B03FFF294BLL;
    if ( !v15 )
    {
LABEL_30:
      *(_DWORD *)&pv.vt = 9;
      *(_OWORD *)&pv.decVal.Hi32 = 0;
      if ( pid == PKEY_DescriptionID.pid )
      {
        v16 = *(_QWORD *)&a3->fmtid.Data1 - *(_QWORD *)&PKEY_DescriptionID.fmtid.Data1;
        if ( *(_QWORD *)&a3->fmtid.Data1 == *(_QWORD *)&PKEY_DescriptionID.fmtid.Data1 )
          v16 = *(_QWORD *)a3->fmtid.Data4 - *(_QWORD *)PKEY_DescriptionID.fmtid.Data4;
        if ( !v16 )
        {
          PropertyFromIDList = InitVariantFromBuffer(&pv, 0x14u, a4);
          goto LABEL_63;
        }
      }
      a4->vt = 19;
      a4->lVal = 9;
LABEL_62:
      PropertyFromIDList = 0;
      goto LABEL_63;
    }
  }
  if ( (unsigned int)operator==(a3, &PKEY_ItemTypeText) )
  {
    if ( LoadStringW(g_hInstance, 0x2000u, Buffer, 260) )
    {
      PropertyFromIDList = InitVariantFromString(Buffer, a4);
    }
    else
    {
      LastError = GetLastError();
      PropertyFromIDList = LastError;
      if ( LastError > 0 )
        PropertyFromIDList = (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    if ( !(unsigned int)operator==(a3, qword_18003C390) )
    {
      if ( (unsigned int)operator==(a3, &PKEY_DeviceDisplay_Category) )
      {
        PropertyFromIDList = InitVariantFromString(L"Multimedia.DMS", a4);
        goto LABEL_63;
      }
      if ( !(unsigned int)operator==(a3, &PKEY_IsPinnedToNameSpaceTree) )
        goto LABEL_63;
      a4->vt = 11;
      a4->iVal = 0;
      goto LABEL_62;
    }
    pv.vt = 0;
    PropertyFromIDList = CItemIDFactory<MEDIASERVER_ITEMID,1159165815>::GetPropertyFromIDList(
                           a2,
                           &PKEY_PNPX_GlobalIdentity,
                           &pv);
    if ( PropertyFromIDList >= 0 )
    {
      v18 = 0;
      string = 0;
      v19 = CPropVariant::GetString((CPropVariant *)&pv);
      if ( v19 )
      {
        PropertyFromIDList = Windows::Internal::String::_InitializeHelper(&string, v19);
        if ( PropertyFromIDList < 0 )
        {
          v18 = string;
        }
        else
        {
          v27 = 0;
          v18 = string;
          PropertyFromIDList = CMediaServerFolder::_FindDeviceByUDN(
                                 (CMediaServerFolder *)((char *)this - 16),
                                 string,
                                 &v27);
          if ( PropertyFromIDList >= 0 )
          {
            v26 = 0;
            v20 = v27;
            v21 = **(__int64 (__fastcall ***)(struct Windows::Media::Streaming::IBasicDevice *, GUID *, __int64 *))v27;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v26);
            PropertyFromIDList = v21(v20, &GUID_27a9ba24_9a99_4f80_979b_4e22d449be11, &v26);
            if ( PropertyFromIDList >= 0 )
            {
              v25 = 0;
              v22 = v26;
              v23 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, LONGLONG *)))(*(_QWORD *)v26 + 56LL);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v25);
              PropertyFromIDList = v23(v22, &v25);
              if ( PropertyFromIDList >= 0 )
              {
                v29 = 0;
                PropertyFromIDList = (**v25)(v25, &GUID_33591c10_0bed_4f02_b0ab_1530d5533ee9, &v29);
                if ( PropertyFromIDList >= 0 )
                {
                  a4->vt = 13;
                  a4->llVal = v29;
                }
              }
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v25);
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v26);
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v27);
        }
      }
      else
      {
        PropertyFromIDList = -2147467261;
      }
      if ( v18 )
        WindowsDeleteString(v18);
    }
    PropVariantClear(&pv);
  }
LABEL_63:
  PropVariantClear(&ppropvar);
  return (unsigned int)PropertyFromIDList;
}

```

## disassembly

```asm
0x1800012e0  push    rbp
0x1800012e2  push    rbx
0x1800012e3  push    rsi
0x1800012e4  push    rdi
0x1800012e5  push    r13
0x1800012e7  push    r14
0x1800012e9  push    r15
0x1800012eb  lea     rbp, [rsp-1A0h]
0x1800012f3  sub     rsp, 2A0h
0x1800012fa  mov     rax, cs:__security_cookie
0x180001301  xor     rax, rsp
0x180001304  mov     [rbp+1D0h+var_40], rax
0x18000130b  mov     r14, r9
0x18000130e  mov     rsi, r8
0x180001311  mov     rdi, rdx
0x180001314  mov     r13, rcx
0x180001317  mov     rcx, r9; pvarg
0x18000131a  call    cs:__imp_VariantInit
0x180001320  nop
0x180001321  xorps   xmm0, xmm0
0x180001324  xor     eax, eax
0x180001326  movups  xmmword ptr [rsp+2D0h+ppropvar], xmm0
0x18000132b  mov     qword ptr [rsp+2D0h+ppropvar+10h], rax
0x180001330  test    rdi, rdi
0x180001333  jz      short loc_18000139B
0x180001335  movzx   eax, word ptr [rdi]
0x180001338  cmp     eax, 12h
0x18000133b  jb      short loc_18000139B
0x18000133d  cmp     dword ptr [rdi+6], 45177777h
0x180001344  jnz     short loc_18000139B
0x180001346  movzx   edx, word ptr [rdi+0Ah]; cb
0x18000134a  lea     rcx, [rdx+12h]
0x18000134e  cmp     rax, rcx
0x180001351  jb      short loc_18000139B
0x180001353  test    dx, dx
0x180001356  jz      short loc_18000139B
0x180001358  mov     ebx, 80070057h
0x18000135d  lea     rcx, [rdi+12h]; psps
0x180001361  test    rcx, rcx
0x180001364  jz      short loc_18000138B
0x180001366  lea     r9, [rsp+2D0h+ppropvar]; ppropvar
0x18000136b  mov     r8, rsi; rpkey
0x18000136e  call    cs:__imp_PSGetPropertyFromPropertyStorage
0x180001374  mov     ebx, eax
0x180001376  test    eax, eax
0x180001378  js      short loc_18000138B
0x18000137a  movzx   eax, word ptr [rsp+2D0h+ppropvar]
0x18000137f  test    ax, ax
0x180001382  jnz     short loc_180001390
0x180001384  mov     ebx, 80070648h
0x180001389  jmp     short loc_1800013A0
0x18000138b  movzx   eax, word ptr [rsp+2D0h+ppropvar]
0x180001390  test    ebx, ebx
0x180001392  js      short loc_1800013A0
0x180001394  test    ax, ax
0x180001397  jz      short loc_1800013A0
0x180001399  jmp     short loc_1800013E1
0x18000139b  mov     ebx, 80070057h
0x1800013a0  mov     eax, cs:PKEY_ItemNameDisplay.pid
0x1800013a6  cmp     eax, [rsi+10h]
0x1800013a9  jnz     short loc_1800013DD
0x1800013ab  mov     rax, qword ptr cs:PKEY_ItemNameDisplay.fmtid.Data1
0x1800013b2  sub     rax, [rsi]
0x1800013b5  jnz     short loc_1800013C2
0x1800013b7  mov     rax, qword ptr cs:PKEY_ItemNameDisplay.fmtid.Data4
0x1800013be  sub     rax, [rsi+8]
0x1800013c2  test    rax, rax
0x1800013c5  jnz     short loc_1800013DD
0x1800013c7  lea     r8, [rsp+2D0h+ppropvar]
0x1800013cc  lea     rdx, PKEY_DeviceDisplay_FriendlyName
0x1800013d3  mov     rcx, rdi
0x1800013d6  call    ?GetPropertyFromIDList@?$CItemIDFactory@UMEDIASERVER_ITEMID@@$0EFBHHHHH@@@SAJPEFBU_ITEMIDLIST_RELATIVE@@AEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z; CItemIDFactory<MEDIASERVER_ITEMID,1159165815>::GetPropertyFromIDList(_ITEMIDLIST_RELATIVE const *,_tagpropertykey const &,tagPROPVARIANT *)
0x1800013db  mov     ebx, eax
0x1800013dd  test    ebx, ebx
0x1800013df  js      short loc_1800013F6
0x1800013e1  mov     rdx, r14; pVar
0x1800013e4  lea     rcx, [rsp+2D0h+ppropvar]; pPropVar
0x1800013e9  call    cs:__imp_PropVariantToVariant
0x1800013ef  mov     ebx, eax
0x1800013f1  jmp     loc_1800016CE
0x1800013f6  mov     eax, [rsi+10h]
0x1800013f9  mov     ecx, cs:PKEY_DescriptionID.pid
0x1800013ff  cmp     eax, ecx
0x180001401  jnz     short loc_18000141F
0x180001403  mov     rdx, [rsi]
0x180001406  sub     rdx, qword ptr cs:PKEY_DescriptionID.fmtid.Data1
0x18000140d  jnz     short loc_18000141A
0x18000140f  mov     rdx, [rsi+8]
0x180001413  sub     rdx, qword ptr cs:PKEY_DescriptionID.fmtid.Data4
0x18000141a  test    rdx, rdx
0x18000141d  jz      short loc_180001443
0x18000141f  cmp     eax, cs:dword_18003B158
0x180001425  jnz     short loc_1800014A3
0x180001427  mov     rdx, [rsi]
0x18000142a  sub     rdx, cs:PKEY_StorageSystemType
0x180001431  jnz     short loc_18000143E
0x180001433  mov     rdx, [rsi+8]
0x180001437  sub     rdx, cs:qword_18003B150
0x18000143e  test    rdx, rdx
0x180001441  jnz     short loc_1800014A3
0x180001443  mov     [rsp+2D0h+pv], 9
0x18000144b  xorps   xmm0, xmm0
0x18000144e  movups  [rsp+2D0h+var_26C], xmm0
0x180001453  cmp     eax, ecx
0x180001455  jnz     short loc_18000148D
0x180001457  mov     rax, [rsi]
0x18000145a  sub     rax, qword ptr cs:PKEY_DescriptionID.fmtid.Data1
0x180001461  jnz     short loc_18000146E
0x180001463  mov     rax, [rsi+8]
0x180001467  sub     rax, qword ptr cs:PKEY_DescriptionID.fmtid.Data4
0x18000146e  test    rax, rax
0x180001471  jnz     short loc_18000148D
0x180001473  mov     r8, r14; pvar
0x180001476  mov     edx, 14h; cb
0x18000147b  lea     rcx, [rsp+2D0h+pv]; pv
0x180001480  call    cs:__imp_InitVariantFromBuffer
0x180001486  mov     ebx, eax
0x180001488  jmp     loc_1800016CE
0x18000148d  mov     word ptr [r14], 13h
0x180001493  mov     dword ptr [r14+8], 9
0x18000149b  xor     r15d, r15d
0x18000149e  jmp     loc_1800016CB
0x1800014a3  lea     rdx, PKEY_ItemTypeText
0x1800014aa  mov     rcx, rsi
0x1800014ad  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x1800014b2  test    eax, eax
0x1800014b4  jz      short loc_180001507
0x1800014b6  mov     r9d, 104h; cchBufferMax
0x1800014bc  lea     r8, [rbp+1D0h+Buffer]; lpBuffer
0x1800014c0  mov     edx, 2000h; uID
0x1800014c5  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x1800014cc  call    cs:__imp_LoadStringW
0x1800014d2  test    eax, eax
0x1800014d4  jnz     short loc_1800014F4
0x1800014d6  call    cs:__imp_GetLastError
0x1800014dc  mov     ebx, eax
0x1800014de  test    eax, eax
0x1800014e0  jle     loc_1800016CE
0x1800014e6  movzx   ebx, ax
0x1800014e9  or      ebx, 80070000h
0x1800014ef  jmp     loc_1800016CE
0x1800014f4  mov     rdx, r14; struct tagVARIANT *
0x1800014f7  lea     rcx, [rbp+1D0h+Buffer]; unsigned __int16 *
0x1800014fb  call    ?InitVariantFromString@@YAJPEBGPEAUtagVARIANT@@@Z; InitVariantFromString(ushort const *,tagVARIANT *)
0x180001500  mov     ebx, eax
0x180001502  jmp     loc_1800016CE
0x180001507  lea     rdx, qword_18003C390
0x18000150e  mov     rcx, rsi
0x180001511  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x180001516  test    eax, eax
0x180001518  jz      loc_180001684
0x18000151e  xor     r15d, r15d
0x180001521  mov     word ptr [rsp+2D0h+pv], r15w
0x180001527  lea     r8, [rsp+2D0h+pv]
0x18000152c  lea     rdx, PKEY_PNPX_GlobalIdentity
0x180001533  mov     rcx, rdi
0x180001536  call    ?GetPropertyFromIDList@?$CItemIDFactory@UMEDIASERVER_ITEMID@@$0EFBHHHHH@@@SAJPEFBU_ITEMIDLIST_RELATIVE@@AEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z; CItemIDFactory<MEDIASERVER_ITEMID,1159165815>::GetPropertyFromIDList(_ITEMIDLIST_RELATIVE const *,_tagpropertykey const &,tagPROPVARIANT *)
0x18000153b  mov     ebx, eax
0x18000153d  test    eax, eax
0x18000153f  js      loc_180001677
0x180001545  mov     edi, r15d
0x180001548  mov     [rsp+2D0h+string], r15
0x18000154d  lea     rcx, [rsp+2D0h+pv]; this
0x180001552  call    ?GetString@CPropVariant@@QEBAPEBGXZ; CPropVariant::GetString(void)
0x180001557  test    rax, rax
0x18000155a  jz      loc_180001663
0x180001560  mov     rdx, rax; unsigned __int16 *
0x180001563  lea     rcx, [rsp+2D0h+string]; this
0x180001568  call    ?_InitializeHelper@String@Internal@Windows@@AEAAJPEBG@Z; Windows::Internal::String::_InitializeHelper(ushort const *)
0x18000156d  mov     ebx, eax
0x18000156f  test    eax, eax
0x180001571  js      loc_18000165C
0x180001577  mov     [rsp+2D0h+var_2A0], r15
0x18000157c  lea     rcx, [r13-10h]; this
0x180001580  lea     r8, [rsp+2D0h+var_2A0]; struct Windows::Media::Streaming::IBasicDevice **
0x180001585  mov     rdi, [rsp+2D0h+string]
0x18000158a  mov     rdx, rdi; HSTRING
0x18000158d  call    ?_FindDeviceByUDN@CMediaServerFolder@@AEAAJPEAUHSTRING__@@PEAPEAUIBasicDevice@Streaming@Media@Windows@@@Z; CMediaServerFolder::_FindDeviceByUDN(HSTRING__ *,Windows::Media::Streaming::IBasicDevice * *)
0x180001592  mov     ebx, eax
0x180001594  test    eax, eax
0x180001596  js      loc_180001650
0x18000159c  mov     [rsp+2D0h+var_2A8], r15
0x1800015a1  mov     rbx, [rsp+2D0h+var_2A0]
0x1800015a6  mov     rax, [rbx]
0x1800015a9  mov     rsi, [rax]
0x1800015ac  lea     rcx, [rsp+2D0h+var_2A8]
0x1800015b1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x1800015b6  lea     r8, [rsp+2D0h+var_2A8]
0x1800015bb  lea     rdx, _GUID_27a9ba24_9a99_4f80_979b_4e22d449be11
0x1800015c2  mov     rcx, rbx
0x1800015c5  mov     rax, rsi
0x1800015c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800015cd  mov     ebx, eax
0x1800015cf  test    eax, eax
0x1800015d1  js      short loc_180001645
0x1800015d3  mov     [rsp+2D0h+var_2B0], r15
0x1800015d8  mov     rsi, [rsp+2D0h+var_2A8]
0x1800015dd  mov     rax, [rsi]
0x1800015e0  mov     rbx, [rax+38h]
0x1800015e4  lea     rcx, [rsp+2D0h+var_2B0]
0x1800015e9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x1800015ee  lea     rdx, [rsp+2D0h+var_2B0]
0x1800015f3  mov     rcx, rsi
0x1800015f6  mov     rax, rbx
0x1800015f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800015fe  mov     ebx, eax
0x180001600  test    eax, eax
0x180001602  js      short loc_18000163A
0x180001604  mov     [rsp+2D0h+var_290], r15
0x180001609  mov     rcx, [rsp+2D0h+var_2B0]
0x18000160e  mov     rax, [rcx]
0x180001611  lea     r8, [rsp+2D0h+var_290]
0x180001616  lea     rdx, _GUID_33591c10_0bed_4f02_b0ab_1530d5533ee9
0x18000161d  mov     rax, [rax]
0x180001620  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001625  mov     ebx, eax
0x180001627  test    eax, eax
0x180001629  js      short loc_18000163A
0x18000162b  mov     word ptr [r14], 0Dh
0x180001631  mov     rax, [rsp+2D0h+var_290]
0x180001636  mov     [r14+8], rax
0x18000163a  lea     rcx, [rsp+2D0h+var_2B0]
0x18000163f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180001644  nop
0x180001645  lea     rcx, [rsp+2D0h+var_2A8]
0x18000164a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18000164f  nop
0x180001650  lea     rcx, [rsp+2D0h+var_2A0]
0x180001655  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18000165a  jmp     short loc_180001668
0x18000165c  mov     rdi, [rsp+2D0h+string]
0x180001661  jmp     short loc_180001668
0x180001663  mov     ebx, 80004003h
0x180001668  test    rdi, rdi
0x18000166b  jz      short loc_180001677
0x18000166d  mov     rcx, rdi; string
0x180001670  call    cs:__imp_WindowsDeleteString
0x180001676  nop
0x180001677  lea     rcx, [rsp+2D0h+pv]; pvar
0x18000167c  call    cs:__imp_PropVariantClear
0x180001682  jmp     short loc_1800016CE
0x180001684  lea     rdx, PKEY_DeviceDisplay_Category
0x18000168b  mov     rcx, rsi
0x18000168e  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x180001693  test    eax, eax
0x180001695  jz      short loc_1800016AA
0x180001697  mov     rdx, r14; struct tagVARIANT *
0x18000169a  lea     rcx, aMultimediaDms; "Multimedia.DMS"
0x1800016a1  call    ?InitVariantFromString@@YAJPEBGPEAUtagVARIANT@@@Z; InitVariantFromString(ushort const *,tagVARIANT *)
0x1800016a6  mov     ebx, eax
0x1800016a8  jmp     short loc_1800016CE
0x1800016aa  lea     rdx, PKEY_IsPinnedToNameSpaceTree
0x1800016b1  mov     rcx, rsi
0x1800016b4  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x1800016b9  test    eax, eax
0x1800016bb  jz      short loc_1800016CE
0x1800016bd  mov     word ptr [r14], 0Bh
0x1800016c3  xor     r15d, r15d
0x1800016c6  mov     [r14+8], r15w
0x1800016cb  mov     ebx, r15d
0x1800016ce  lea     rcx, [rsp+2D0h+ppropvar]; pvar
0x1800016d3  call    cs:__imp_PropVariantClear
0x1800016d9  mov     eax, ebx
0x1800016db  mov     rcx, [rbp+1D0h+var_40]
0x1800016e2  xor     rcx, rsp; StackCookie
0x1800016e5  call    __security_check_cookie
0x1800016ea  add     rsp, 2A0h
0x1800016f1  pop     r15
0x1800016f3  pop     r14
0x1800016f5  pop     r13
0x1800016f7  pop     rdi
0x1800016f8  pop     rsi
0x1800016f9  pop     rbx
0x1800016fa  pop     rbp
0x1800016fb  retn
```
