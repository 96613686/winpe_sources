# CContentDirectoryRowset::_ContentDirectorySearch(ulong)

- ea: `0x18001cc50`
- end: `0x18001d2d6`
- name: `?_ContentDirectorySearch@CContentDirectoryRowset@@AEAAJK@Z`
- size: `1670`
- prototype: `__int64 __fastcall(CContentDirectoryRowset *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x18001d4e0`

## callees

- `0x180001710`
- `0x1800097c0`
- `0x18000de58`
- `0x180014a00`
- `0x18001681c`
- `0x18001a28c`
- `0x18001bb64`
- `0x18001bba8`
- `0x18001c0ec`
- `0x18001c670`
- `0x18001cc50`
- `0x18001db80`
- `0x18001dd14`
- `0x18001dd80`
- `0x18001e220`
- `0x18001e3ac`
- `0x18001e7c0`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001cd26`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001d1de`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001cd26`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001d1de`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18001cff6`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18001cff6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001ce22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001ce30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001ce3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001ce4c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001cf12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d0b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d0c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d0cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d0dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d146`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d154`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d162`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d170`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001ce22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001ce30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001ce3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001ce4c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001cf12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d0b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d0c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d0cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d0dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d146`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d154`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d162`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001d170`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CContentDirectoryRowset::_ContentDirectorySearch(CContentDirectoryRowset *this, unsigned int a2)
{
  unsigned int v2; // r14d
  CContentDirectoryRowset *v3; // r12
  HSTRING v4; // rbx
  HSTRING v5; // rdi
  HSTRING v6; // rsi
  __int64 v7; // r15
  __int64 (__fastcall *v8)(__int64, const wchar_t *, PROPVARIANT *); // r14
  const unsigned __int16 *v9; // rax
  const unsigned __int16 *v10; // rdx
  int v11; // r13d
  PCWSTR StringRawBuffer; // r12
  PCWSTR v13; // r15
  unsigned int v14; // r14d
  unsigned int v15; // eax
  int AgileReference; // r13d
  struct Windows::Media::Streaming::Internal::IContentRequest *v17; // r13
  int v18; // r15d
  int v19; // r14d
  PCWSTR v20; // rax
  int v21; // r8d
  void *v22; // r15
  __int64 (__fastcall *v23)(void *, HSTRING, HSTRING, HSTRING, _DWORD, _DWORD, HSTRING, __int64 *); // r14
  struct Windows::Media::Streaming::Internal::IContentRequest **v24; // r15
  __int64 v25; // r14
  struct Windows::Media::Streaming::Internal::IContentRequest *v26; // rax
  CContentRequestDelegate **v27; // r14
  unsigned int v28; // r14d
  int v29; // r13d
  PCWSTR v30; // r12
  PCWSTR v31; // r15
  PCWSTR v32; // r14
  PCWSTR v33; // rax
  int v34; // r12d
  int v35; // r15d
  PCWSTR v36; // r14
  PCWSTR v37; // rsi
  unsigned int v38; // edi
  unsigned int v39; // eax
  int v40; // ecx
  unsigned int v42; // edx
  __int64 v43; // r15
  __int64 (__fastcall *v44)(__int64, struct Windows::Media::Streaming::Internal::IContentRequest **); // r14
  char v45; // [rsp+40h] [rbp-59h]
  __int64 v46; // [rsp+60h] [rbp-39h] BYREF
  HSTRING v47; // [rsp+68h] [rbp-31h] BYREF
  HSTRING string; // [rsp+70h] [rbp-29h] BYREF
  HSTRING v49; // [rsp+78h] [rbp-21h] BYREF
  struct Windows::Media::Streaming::Internal::IContentRequest *v50; // [rsp+80h] [rbp-19h] BYREF
  HSTRING v51; // [rsp+88h] [rbp-11h] BYREF
  PROPVARIANT pvar; // [rsp+90h] [rbp-9h] BYREF
  int SortCriteriaForFolder; // [rsp+110h] [rbp+77h]
  void *v56; // [rsp+118h] [rbp+7Fh] BYREF

  v2 = a2;
  v3 = this;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_ccc67dfc5e8536d1cefd651d689cad4f_Traceguids);
  v46 = 0;
  pvar.vt = 0;
  v4 = 0;
  v47 = 0;
  v5 = 0;
  v49 = 0;
  v6 = 0;
  v51 = 0;
  string = 0;
  if ( *((_QWORD *)v3 + 34) )
  {
    v7 = *((_QWORD *)v3 + 36);
    v8 = *(__int64 (__fastcall **)(__int64, const wchar_t *, PROPVARIANT *))(*(_QWORD *)v7 + 24LL);
    PropVariantClear(&pvar);
    SortCriteriaForFolder = v8(v7, L"ObjectID", &pvar);
    if ( SortCriteriaForFolder >= 0 )
    {
      v9 = CPropVariant::GetString((CPropVariant *)&pvar);
      if ( v9 )
      {
        SortCriteriaForFolder = Windows::Internal::String::_InitializeHelper(&v47, v9);
        if ( SortCriteriaForFolder >= 0 )
        {
          v10 = (const unsigned __int16 *)*((_QWORD *)v3 + 34);
          if ( v10 )
          {
            SortCriteriaForFolder = Windows::Internal::String::_InitializeHelper(&v49, v10);
            if ( SortCriteriaForFolder < 0 )
            {
              v4 = v47;
              v5 = v49;
            }
            else
            {
              SortCriteriaForFolder = Windows::Internal::String::Initialize(&v51, L"*", 1u);
              if ( SortCriteriaForFolder >= 0 )
                SortCriteriaForFolder = CContentDirectoryRowset::_GetSortCriteriaForFolder(
                                          (HSTRING *)v3,
                                          *((_DWORD *)v3 + 97),
                                          &string);
              v4 = v47;
              v5 = v49;
              v6 = v51;
            }
            goto LABEL_22;
          }
          SortCriteriaForFolder = -2147467261;
        }
        v4 = v47;
      }
      else
      {
        SortCriteriaForFolder = -2147467261;
      }
    }
LABEL_22:
    v2 = a2;
    goto LABEL_23;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_ccc67dfc5e8536d1cefd651d689cad4f_Traceguids);
  }
  SortCriteriaForFolder = -2147024809;
LABEL_23:
  v50 = (struct Windows::Media::Streaming::Internal::IContentRequest *)v2;
  if ( (Microsoft_Windows_DLNA_NamespaceEnableBits & 1) != 0 )
  {
    LODWORD(v56) = *((_DWORD *)v3 + 10 * v2 + 20);
    v11 = *((_DWORD *)v3 + 10 * v2 + 18);
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v13 = WindowsGetStringRawBuffer(v6, 0);
    v14 = (unsigned int)WindowsGetStringRawBuffer(v5, 0);
    v15 = (unsigned int)WindowsGetStringRawBuffer(v4, 0);
    McTemplateU0zzzzqqqqq_EventWriteTransfer(
      (_DWORD)v56,
      (unsigned int)ContentDirectory_Search_Start,
      v15,
      v14,
      (__int64)v13,
      (__int64)StringRawBuffer,
      v11,
      (char)v56,
      0,
      0,
      0);
    v3 = this;
    v2 = a2;
  }
  AgileReference = SortCriteriaForFolder;
  if ( SortCriteriaForFolder < 0 )
    goto LABEL_39;
  v56 = 0;
  AgileReference = AgileGitPtr::CopyLocal(
                     (CContentDirectoryRowset *)((char *)v3 + 344),
                     &GUID_6550c614_7e79_4549_8064_681b3fca61df,
                     &v56);
  SortCriteriaForFolder = AgileReference;
  if ( AgileReference >= 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v17 = v50;
    }
    else
    {
      v17 = (struct Windows::Media::Streaming::Internal::IContentRequest *)v2;
      v18 = *((_DWORD *)v3 + 10 * v2 + 20);
      v19 = *((_DWORD *)v3 + 10 * v2 + 18);
      v20 = WindowsGetStringRawBuffer(v4, 0);
      WPP_SF_qSDD(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, v21, (_DWORD)v3, (__int64)v20, v19, v18);
    }
    v22 = v56;
    v23 = *(__int64 (__fastcall **)(void *, HSTRING, HSTRING, HSTRING, _DWORD, _DWORD, HSTRING, __int64 *))(*(_QWORD *)v56 + 96LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v46);
    AgileReference = v23(
                       v22,
                       v4,
                       v5,
                       v6,
                       *((_DWORD *)v3 + 10 * (_QWORD)v17 + 18),
                       *((_DWORD *)v3 + 10 * (_QWORD)v17 + 20),
                       string,
                       &v46);
    SortCriteriaForFolder = AgileReference;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v56);
  if ( AgileReference < 0 )
    goto LABEL_39;
  v24 = (struct Windows::Media::Streaming::Internal::IContentRequest **)((char *)v3 + 400);
  v25 = v46;
  v26 = 0;
  v56 = 0;
  AgileReference = 0;
  SortCriteriaForFolder = 0;
  if ( v46 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v56);
    AgileReference = RoGetAgileReference(0, &GUID_d459d20d_1e3a_543c_bb1c_569c96afdca7, v25, &v56);
    SortCriteriaForFolder = AgileReference;
    v26 = (struct Windows::Media::Streaming::Internal::IContentRequest *)v56;
  }
  v56 = 0;
  v50 = *v24;
  *v24 = v26;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v50);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v56);
  if ( AgileReference < 0 )
    goto LABEL_39;
  v27 = (CContentRequestDelegate **)((char *)v3 + 408);
  AgileReference = Microsoft::WRL::Details::MakeAndInitialize<CContentRequestDelegate,CContentRequestDelegate,>((char *)v3 + 408);
  SortCriteriaForFolder = AgileReference;
  if ( AgileReference < 0 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((char *)v3 + 408);
    AgileGitPtr::Revoke((CContentDirectoryRowset *)((char *)v3 + 400));
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v46);
LABEL_39:
    v28 = a2;
    goto LABEL_40;
  }
  AgileReference = (*(__int64 (__fastcall **)(__int64, CContentRequestDelegate *))(*(_QWORD *)v46 + 64LL))(v46, *v27);
  SortCriteriaForFolder = AgileReference;
  if ( AgileReference < 0 )
    goto LABEL_39;
  AgileReference = (*(__int64 (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)v46 + 48LL))(
                     v46,
                     ((unsigned __int64)*v27 + 8) & -(__int64)(*v27 != 0));
  SortCriteriaForFolder = AgileReference;
  if ( AgileReference < 0 )
    goto LABEL_39;
  AgileReference = CContentRequestDelegate::Wait(*v27, v42);
  SortCriteriaForFolder = AgileReference;
  if ( AgileReference < 0 )
    goto LABEL_39;
  v50 = 0;
  LODWORD(v56) = CContentRequestDelegate::IsCompleted(*v27);
  v43 = v46;
  v44 = *(__int64 (__fastcall **)(__int64, struct Windows::Media::Streaming::Internal::IContentRequest **))(*(_QWORD *)v46 + 80LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v50);
  AgileReference = v44(v43, &v50);
  SortCriteriaForFolder = AgileReference;
  v28 = a2;
  if ( AgileReference >= 0 )
  {
    AgileReference = CContentDirectoryRowset::_QueryResults(v3, v50, a2, (int)v56);
    SortCriteriaForFolder = AgileReference;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v50);
LABEL_40:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    LODWORD(v56) = *((_DWORD *)v3 + 10 * v28 + 20);
    v29 = *((_DWORD *)v3 + 10 * v28 + 18);
    v30 = WindowsGetStringRawBuffer(string, 0);
    v31 = WindowsGetStringRawBuffer(v6, 0);
    v32 = WindowsGetStringRawBuffer(v5, 0);
    v33 = WindowsGetStringRawBuffer(v4, 0);
    v45 = v29;
    AgileReference = SortCriteriaForFolder;
    WPP_SF_DSSSSdd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (__int64)v33,
      (__int64)v32,
      (__int64)v31,
      (__int64)v30,
      v45,
      (char)v56);
  }
  if ( (Microsoft_Windows_DLNA_NamespaceEnableBits & 1) != 0 )
  {
    v34 = *((_DWORD *)this + 10 * a2 + 20);
    v35 = *((_DWORD *)this + 10 * a2 + 18);
    v36 = WindowsGetStringRawBuffer(string, 0);
    v37 = WindowsGetStringRawBuffer(v6, 0);
    v38 = (unsigned int)WindowsGetStringRawBuffer(v5, 0);
    v39 = (unsigned int)WindowsGetStringRawBuffer(v4, 0);
    McTemplateU0zzzzqqqqq_EventWriteTransfer(
      v40,
      (unsigned int)ContentDirectory_Search_Stop,
      v39,
      v38,
      (__int64)v37,
      (__int64)v36,
      v35,
      v34,
      0,
      0,
      AgileReference);
  }
  Windows::Internal::String::~String(&string);
  Windows::Internal::String::~String(&v51);
  Windows::Internal::String::~String(&v49);
  Windows::Internal::String::~String(&v47);
  PropVariantClear(&pvar);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v46);
  return (unsigned int)AgileReference;
}

```

## disassembly

```asm
0x18001cc50  mov     [rsp-8+arg_8], edx
0x18001cc54  mov     [rsp-8+arg_0], rcx
0x18001cc59  push    rbp
0x18001cc5a  push    rbx
0x18001cc5b  push    rsi
0x18001cc5c  push    rdi
0x18001cc5d  push    r12
0x18001cc5f  push    r13
0x18001cc61  push    r14
0x18001cc63  push    r15
0x18001cc65  lea     rbp, [rsp-1Fh]
0x18001cc6a  sub     rsp, 0B8h
0x18001cc71  mov     r14d, edx
0x18001cc74  mov     r12, rcx
0x18001cc77  lea     rcx, WPP_GLOBAL_Control
0x18001cc7e  mov     rax, cs:WPP_GLOBAL_Control
0x18001cc85  cmp     rax, rcx
0x18001cc88  jz      short loc_18001CCAC
0x18001cc8a  test    byte ptr [rax+1Ch], 2
0x18001cc8e  jz      short loc_18001CCAC
0x18001cc90  mov     edx, 12h
0x18001cc95  lea     r8, WPP_ccc67dfc5e8536d1cefd651d689cad4f_Traceguids
0x18001cc9c  mov     rcx, [rax+10h]
0x18001cca0  call    WPP_SF_
0x18001cca5  lea     rcx, WPP_GLOBAL_Control
0x18001ccac  xor     r13d, r13d
0x18001ccaf  mov     [rbp+57h+var_90], r13
0x18001ccb3  mov     word ptr [rbp+57h+pvar], r13w
0x18001ccb8  mov     ebx, r13d
0x18001ccbb  mov     [rbp+57h+var_88], rbx
0x18001ccbf  mov     edi, r13d
0x18001ccc2  mov     [rbp+57h+var_78], r13
0x18001ccc6  mov     esi, r13d
0x18001ccc9  mov     [rbp+57h+var_68], r13
0x18001cccd  mov     [rbp+57h+string], r13
0x18001ccd1  cmp     [r12+110h], r13
0x18001ccd9  jnz     short loc_18001CD13
0x18001ccdb  mov     rax, cs:WPP_GLOBAL_Control
0x18001cce2  cmp     rax, rcx
0x18001cce5  jz      short loc_18001CD07
0x18001cce7  test    byte ptr [rax+1Ch], 40h
0x18001cceb  jz      short loc_18001CD07
0x18001cced  cmp     byte ptr [rax+19h], 4
0x18001ccf1  jb      short loc_18001CD07
0x18001ccf3  lea     edx, [r13+13h]
0x18001ccf7  lea     r8, WPP_ccc67dfc5e8536d1cefd651d689cad4f_Traceguids
0x18001ccfe  mov     rcx, [rax+10h]
0x18001cd02  call    WPP_SF_
0x18001cd07  mov     [rbp+57h+arg_10], 80070057h
0x18001cd0e  jmp     loc_18001CDF3
0x18001cd13  mov     r15, [r12+120h]
0x18001cd1b  mov     rax, [r15]
0x18001cd1e  mov     r14, [rax+18h]
0x18001cd22  lea     rcx, [rbp+57h+pvar]; pvar
0x18001cd26  call    cs:__imp_PropVariantClear
0x18001cd2c  lea     r8, [rbp+57h+pvar]
0x18001cd30  lea     rdx, g_wszObjectID; "ObjectID"
0x18001cd37  mov     rcx, r15
0x18001cd3a  mov     rax, r14
0x18001cd3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd42  mov     [rbp+57h+arg_10], eax
0x18001cd45  test    eax, eax
0x18001cd47  js      loc_18001CDEF
0x18001cd4d  lea     rcx, [rbp+57h+pvar]; this
0x18001cd51  call    ?GetString@CPropVariant@@QEBAPEBGXZ; CPropVariant::GetString(void)
0x18001cd56  test    rax, rax
0x18001cd59  jz      loc_18001CDE8
0x18001cd5f  mov     rdx, rax; unsigned __int16 *
0x18001cd62  lea     rcx, [rbp+57h+var_88]; this
0x18001cd66  call    ?_InitializeHelper@String@Internal@Windows@@AEAAJPEBG@Z; Windows::Internal::String::_InitializeHelper(ushort const *)
0x18001cd6b  mov     [rbp+57h+arg_10], eax
0x18001cd6e  test    eax, eax
0x18001cd70  js      short loc_18001CDE2
0x18001cd72  mov     rdx, [r12+110h]; unsigned __int16 *
0x18001cd7a  test    rdx, rdx
0x18001cd7d  jz      short loc_18001CDDB
0x18001cd7f  lea     rcx, [rbp+57h+var_78]; this
0x18001cd83  call    ?_InitializeHelper@String@Internal@Windows@@AEAAJPEBG@Z; Windows::Internal::String::_InitializeHelper(ushort const *)
0x18001cd88  mov     [rbp+57h+arg_10], eax
0x18001cd8b  test    eax, eax
0x18001cd8d  js      short loc_18001CDD1
0x18001cd8f  mov     r8d, 1; length
0x18001cd95  lea     rdx, Src; "*"
0x18001cd9c  lea     rcx, [rbp+57h+var_68]; this
0x18001cda0  call    ?Initialize@String@Internal@Windows@@QEAAJPEBGI@Z; Windows::Internal::String::Initialize(ushort const *,uint)
0x18001cda5  mov     [rbp+57h+arg_10], eax
0x18001cda8  test    eax, eax
0x18001cdaa  js      short loc_18001CDC3
0x18001cdac  lea     r8, [rbp+57h+string]; HSTRING *
0x18001cdb0  mov     edx, [r12+184h]; unsigned int
0x18001cdb8  mov     rcx, r12; this
0x18001cdbb  call    ?_GetSortCriteriaForFolder@CContentDirectoryRowset@@AEAAJKPEAPEAUHSTRING__@@@Z; CContentDirectoryRowset::_GetSortCriteriaForFolder(ulong,HSTRING__ * *)
0x18001cdc0  mov     [rbp+57h+arg_10], eax
0x18001cdc3  mov     rbx, [rbp+57h+var_88]
0x18001cdc7  mov     rdi, [rbp+57h+var_78]
0x18001cdcb  mov     rsi, [rbp+57h+var_68]
0x18001cdcf  jmp     short loc_18001CDEF
0x18001cdd1  mov     rbx, [rbp+57h+var_88]
0x18001cdd5  mov     rdi, [rbp+57h+var_78]
0x18001cdd9  jmp     short loc_18001CDEF
0x18001cddb  mov     [rbp+57h+arg_10], 80004003h
0x18001cde2  mov     rbx, [rbp+57h+var_88]
0x18001cde6  jmp     short loc_18001CDEF
0x18001cde8  mov     [rbp+57h+arg_10], 80004003h
0x18001cdef  mov     r14d, [rbp+57h+arg_8]
0x18001cdf3  mov     ecx, r14d
0x18001cdf6  mov     [rbp+57h+var_70], rcx
0x18001cdfa  test    cs:Microsoft_Windows_DLNA_NamespaceEnableBits, 1
0x18001ce01  jz      loc_18001CE90
0x18001ce07  lea     rax, [rcx+rcx*4]
0x18001ce0b  mov     eax, [r12+rax*8+50h]
0x18001ce10  mov     dword ptr [rbp+57h+arg_18], eax
0x18001ce13  lea     rax, [rcx+rcx*4]
0x18001ce17  mov     r13d, [r12+rax*8+48h]
0x18001ce1c  xor     edx, edx; length
0x18001ce1e  mov     rcx, [rbp+57h+string]; string
0x18001ce22  call    cs:__imp_WindowsGetStringRawBuffer
0x18001ce28  mov     r12, rax
0x18001ce2b  xor     edx, edx; length
0x18001ce2d  mov     rcx, rsi; string
0x18001ce30  call    cs:__imp_WindowsGetStringRawBuffer
0x18001ce36  mov     r15, rax
0x18001ce39  xor     edx, edx; length
0x18001ce3b  mov     rcx, rdi; string
0x18001ce3e  call    cs:__imp_WindowsGetStringRawBuffer
0x18001ce44  mov     r14, rax
0x18001ce47  xor     edx, edx; length
0x18001ce49  mov     rcx, rbx; string
0x18001ce4c  call    cs:__imp_WindowsGetStringRawBuffer
0x18001ce52  xor     ecx, ecx
0x18001ce54  mov     [rsp+0F0h+var_A0], ecx
0x18001ce58  mov     dword ptr [rsp+0F0h+var_A8], ecx
0x18001ce5c  mov     dword ptr [rsp+0F0h+var_B0], ecx
0x18001ce60  mov     ecx, dword ptr [rbp+57h+arg_18]
0x18001ce63  mov     dword ptr [rsp+0F0h+var_B8], ecx
0x18001ce67  mov     dword ptr [rsp+0F0h+var_C0], r13d
0x18001ce6c  mov     [rsp+0F0h+var_C8], r12
0x18001ce71  mov     [rsp+0F0h+var_D0], r15
0x18001ce76  mov     r9, r14
0x18001ce79  mov     r8, rax
0x18001ce7c  lea     rdx, ContentDirectory_Search_Start
0x18001ce83  call    McTemplateU0zzzzqqqqq_EventWriteTransfer
0x18001ce88  mov     r12, [rbp+57h+arg_0]
0x18001ce8c  mov     r14d, [rbp+57h+arg_8]
0x18001ce90  mov     r13d, [rbp+57h+arg_10]
0x18001ce94  test    r13d, r13d
0x18001ce97  js      loc_18001D066
0x18001ce9d  mov     [rbp+57h+arg_18], 0
0x18001cea5  lea     rcx, [r12+158h]; this
0x18001cead  lea     r8, [rbp+57h+arg_18]; void **
0x18001ceb1  lea     rdx, _GUID_6550c614_7e79_4549_8064_681b3fca61df; struct _GUID *
0x18001ceb8  call    ?CopyLocal@AgileGitPtr@@QEBAJAEBU_GUID@@PEAPEAX@Z; AgileGitPtr::CopyLocal(_GUID const &,void * *)
0x18001cebd  mov     r13d, eax
0x18001cec0  mov     [rbp+57h+arg_10], eax
0x18001cec3  test    eax, eax
0x18001cec5  js      loc_18001CFAD
0x18001cecb  mov     rax, cs:WPP_GLOBAL_Control
0x18001ced2  lea     rcx, WPP_GLOBAL_Control
0x18001ced9  cmp     rax, rcx
0x18001cedc  jz      short loc_18001CF41
0x18001cede  test    byte ptr [rax+1Ch], 40h
0x18001cee2  jz      short loc_18001CF41
0x18001cee4  cmp     byte ptr [rax+19h], 4
0x18001cee8  jb      short loc_18001CF41
0x18001ceea  mov     r13d, r14d
0x18001ceed  lea     rax, ds:0[r13*4]
0x18001cef5  add     rax, r13
0x18001cef8  mov     r15d, [r12+rax*8+50h]
0x18001cefd  lea     rax, ds:0[r13*4]
0x18001cf05  add     rax, r13
0x18001cf08  mov     r14d, [r12+rax*8+48h]
0x18001cf0d  xor     edx, edx; length
0x18001cf0f  mov     rcx, rbx; string
0x18001cf12  call    cs:__imp_WindowsGetStringRawBuffer
0x18001cf18  mov     edx, 14h
0x18001cf1d  mov     dword ptr [rsp+0F0h+var_C0], r15d
0x18001cf22  mov     dword ptr [rsp+0F0h+var_C8], r14d
0x18001cf27  mov     [rsp+0F0h+var_D0], rax
0x18001cf2c  mov     r9, r12
0x18001cf2f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cf36  mov     rcx, [rcx+10h]
0x18001cf3a  call    WPP_SF_qSDD
0x18001cf3f  jmp     short loc_18001CF45
0x18001cf41  mov     r13, [rbp+57h+var_70]
0x18001cf45  mov     r15, [rbp+57h+arg_18]
0x18001cf49  mov     rax, [r15]
0x18001cf4c  mov     r14, [rax+60h]
0x18001cf50  lea     rcx, [rbp+57h+var_90]
0x18001cf54  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18001cf59  mov     r9, [rbp+57h+string]
0x18001cf5d  lea     rdx, ds:0[r13*4]
0x18001cf65  add     rdx, r13
0x18001cf68  lea     r8, ds:0[r13*4]
0x18001cf70  add     r8, r13
0x18001cf73  lea     rax, [rbp+57h+var_90]
0x18001cf77  mov     [rsp+0F0h+var_B8], rax
0x18001cf7c  mov     [rsp+0F0h+var_C0], r9
0x18001cf81  mov     edx, [r12+rdx*8+50h]
0x18001cf86  mov     dword ptr [rsp+0F0h+var_C8], edx
0x18001cf8a  mov     edx, [r12+r8*8+48h]
0x18001cf8f  mov     dword ptr [rsp+0F0h+var_D0], edx
0x18001cf93  mov     r9, rsi
0x18001cf96  mov     r8, rdi
0x18001cf99  mov     rdx, rbx
0x18001cf9c  mov     rcx, r15
0x18001cf9f  mov     rax, r14
0x18001cfa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cfa7  mov     r13d, eax
0x18001cfaa  mov     [rbp+57h+arg_10], eax
0x18001cfad  lea     rcx, [rbp+57h+arg_18]
0x18001cfb1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18001cfb6  test    r13d, r13d
0x18001cfb9  js      loc_18001D066
0x18001cfbf  lea     r15, [r12+190h]
0x18001cfc7  mov     r14, [rbp+57h+var_90]
0x18001cfcb  xor     eax, eax
0x18001cfcd  mov     [rbp+57h+arg_18], rax
0x18001cfd1  xor     r13d, r13d
0x18001cfd4  mov     [rbp+57h+arg_10], r13d
0x18001cfd8  test    r14, r14
0x18001cfdb  jz      short loc_18001D006
0x18001cfdd  lea     rcx, [rbp+57h+arg_18]
0x18001cfe1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18001cfe6  lea     r9, [rbp+57h+arg_18]
0x18001cfea  mov     r8, r14
0x18001cfed  lea     rdx, _GUID_d459d20d_1e3a_543c_bb1c_569c96afdca7
0x18001cff4  xor     ecx, ecx
0x18001cff6  call    cs:__imp_RoGetAgileReference
0x18001cffc  mov     r13d, eax
0x18001cfff  mov     [rbp+57h+arg_10], eax
0x18001d002  mov     rax, [rbp+57h+arg_18]
0x18001d006  mov     [rbp+57h+arg_18], 0
0x18001d00e  mov     rcx, [r15]
0x18001d011  mov     [rbp+57h+var_70], rcx
0x18001d015  mov     [r15], rax
0x18001d018  lea     rcx, [rbp+57h+var_70]
0x18001d01c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18001d021  lea     rcx, [rbp+57h+arg_18]
0x18001d025  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18001d02a  test    r13d, r13d
0x18001d02d  js      short loc_18001D066
0x18001d02f  lea     r14, [r12+198h]
0x18001d037  mov     rcx, r14
0x18001d03a  call    ??$MakeAndInitialize@VCContentRequestDelegate@@V1@$$V@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VCContentRequestDelegate@@@WRL@Microsoft@@@012@@Z; Microsoft::WRL::Details::MakeAndInitialize<CContentRequestDelegate,CContentRequestDelegate,>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<CContentRequestDelegate>>)
0x18001d03f  mov     r13d, eax
0x18001d042  mov     [rbp+57h+arg_10], eax
0x18001d045  test    eax, eax
0x18001d047  jns     loc_18001D205
0x18001d04d  mov     rcx, r14
0x18001d050  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18001d055  mov     rcx, r15; this
0x18001d058  call    ?Revoke@AgileGitPtr@@QEAAJXZ; AgileGitPtr::Revoke(void)
0x18001d05d  lea     rcx, [rbp+57h+var_90]
0x18001d061  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18001d066  mov     r14d, [rbp+57h+arg_8]
0x18001d06a  mov     rax, cs:WPP_GLOBAL_Control
0x18001d071  lea     rcx, WPP_GLOBAL_Control
0x18001d078  cmp     rax, rcx
0x18001d07b  jz      loc_18001D11A
0x18001d081  test    byte ptr [rax+1Ch], 40h
0x18001d085  jz      loc_18001D11A
0x18001d08b  cmp     byte ptr [rax+19h], 4
0x18001d08f  jb      loc_18001D11A
0x18001d095  mov     ecx, r14d
0x18001d098  lea     rax, [rcx+rcx*4]
0x18001d09c  mov     eax, [r12+rax*8+50h]
0x18001d0a1  mov     dword ptr [rbp+57h+arg_18], eax
0x18001d0a4  lea     rax, [rcx+rcx*4]
0x18001d0a8  mov     r13d, [r12+rax*8+48h]
0x18001d0ad  xor     edx, edx; length
0x18001d0af  mov     rcx, [rbp+57h+string]; string
0x18001d0b3  call    cs:__imp_WindowsGetStringRawBuffer
0x18001d0b9  mov     r12, rax
0x18001d0bc  xor     edx, edx; length
0x18001d0be  mov     rcx, rsi; string
0x18001d0c1  call    cs:__imp_WindowsGetStringRawBuffer
0x18001d0c7  mov     r15, rax
0x18001d0ca  xor     edx, edx; length
0x18001d0cc  mov     rcx, rdi; string
0x18001d0cf  call    cs:__imp_WindowsGetStringRawBuffer
0x18001d0d5  mov     r14, rax
0x18001d0d8  xor     edx, edx; length
0x18001d0da  mov     rcx, rbx; string
0x18001d0dd  call    cs:__imp_WindowsGetStringRawBuffer
0x18001d0e3  mov     ecx, dword ptr [rbp+57h+arg_18]
0x18001d0e6  mov     dword ptr [rsp+0F0h+var_A8], ecx; char
0x18001d0ea  mov     dword ptr [rsp+0F0h+var_B0], r13d; char
0x18001d0ef  mov     [rsp+0F0h+var_B8], r12; __int64
0x18001d0f4  mov     [rsp+0F0h+var_C0], r15; __int64
0x18001d0f9  mov     [rsp+0F0h+var_C8], r14; __int64
0x18001d0fe  mov     [rsp+0F0h+var_D0], rax; __int64
0x18001d103  mov     r13d, [rbp+57h+arg_10]
0x18001d107  mov     r9d, r13d
0x18001d10a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d111  mov     rcx, [rcx+10h]; LoggerHandle
0x18001d115  call    WPP_SF_DSSSSdd
0x18001d11a  test    cs:Microsoft_Windows_DLNA_NamespaceEnableBits, 1
0x18001d121  jz      loc_18001D1B2
0x18001d127  mov     ecx, [rbp+57h+arg_8]
0x18001d12a  lea     rax, [rcx+rcx*4]
  ... truncated ...
```
