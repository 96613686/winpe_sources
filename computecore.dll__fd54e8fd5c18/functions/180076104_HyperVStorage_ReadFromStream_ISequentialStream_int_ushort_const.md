# HyperVStorage::ReadFromStream(ISequentialStream *,int,ushort const *)

- ea: `0x180076104`
- end: `0x180076b20`
- name: `?ReadFromStream@HyperVStorage@@QEAAJPEAUISequentialStream@@HPEBG@Z`
- size: `2588`
- prototype: `int(HyperVStorage *__hidden this, struct ISequentialStream *, int, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `28`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180096370`
- `0x1800964f0`

## callees

- `0x1800067c0`
- `0x180007dbc`
- `0x180007e24`
- `0x180007fe1`
- `0x180009e8c`
- `0x180011894`
- `0x1800136d0`
- `0x180014380`
- `0x180028960`
- `0x180050b60`
- `0x1800518f4`
- `0x1800663a4`
- `0x18006d7ec`
- `0x18006de24`
- `0x180070b48`
- `0x1800737e8`
- `0x180075400`
- `0x180076104`
- `0x180076b28`
- `0x1800778a0`
- `0x180081f2c`
- `0x180082140`
- `0x180082244`
- `0x1800822a4`
- `0x18008d3dc`
- `0x18008dee8`
- `0x18008ecc0`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180076888`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180076888`
- `api-ms-win-crt-private-l1-1-0!_o__wtof` at `0x1800767e0`
- `api-ms-win-crt-private-l1-1-0!_o__wtof` at `0x1800767e0`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x18007676c`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x1800767a6`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x180076852`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x18007676c`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x1800767a6`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi64` at `0x180076852`
- `XmlLite!CreateXmlReaderInputWithEncodingName` at `0x1800761af`
- `XmlLite!CreateXmlReaderInputWithEncodingName` at `0x1800761af`
- `XmlLite!CreateXmlReader` at `0x18007616d`
- `XmlLite!CreateXmlReader` at `0x18007616d`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
__int64 __fastcall HyperVStorage::ReadFromStream(HyperVStorage *this, IUnknown *a2, int a3, unsigned __int16 *a4)
{
  HyperVStorage *v6; // r12
  HRESULT v7; // eax
  char v8; // r13
  HRESULT v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // esi
  __int64 v13; // rcx
  struct HyperVStorageOperation *v14; // r14
  HyperVStorageKeyTableEntry **v15; // r15
  int v16; // eax
  int v17; // eax
  int v18; // eax
  __int64 v19; // r8
  HyperVStorage *v20; // rcx
  int v21; // ebx
  HyperVStorage *v22; // rcx
  wchar_t **v23; // rax
  const WCHAR *v24; // rcx
  unsigned int v25; // r14d
  int v26; // r12d
  HyperVStorageKeyTableEntry *v27; // rbx
  const char *Name; // rax
  __int64 v29; // r8
  size_t v30; // r15
  void **v31; // rbx
  struct HyperVStorageKeyTableEntry *v32; // r15
  char *v33; // rcx
  char *v34; // r8
  const wchar_t *v35; // rcx
  __int64 *p_Buf1; // rax
  const wchar_t *v37; // rcx
  const wchar_t *v38; // rcx
  const wchar_t *v39; // rcx
  wchar_t **v40; // rdx
  bool v41; // bl
  wchar_t **v42; // rax
  unsigned __int16 *v43; // rax
  unsigned int v44; // ebx
  __int64 v46; // rax
  __int64 v47; // rdx
  __int64 v48; // r8
  __int64 v49; // rax
  LPCWSTR pwszBaseUri; // [rsp+20h] [rbp-198h]
  int ppInput; // [rsp+28h] [rbp-190h]
  int v52; // [rsp+30h] [rbp-188h]
  size_t Size; // [rsp+40h] [rbp-178h] BYREF
  struct HyperVStorageOperation *v54; // [rsp+48h] [rbp-170h] BYREF
  int v55; // [rsp+50h] [rbp-168h]
  struct HyperVStorageKeyTableEntry *v56; // [rsp+58h] [rbp-160h] BYREF
  int v57[2]; // [rsp+60h] [rbp-158h]
  unsigned __int16 *v58; // [rsp+68h] [rbp-150h]
  HyperVStorage *v59; // [rsp+70h] [rbp-148h]
  unsigned __int16 *v60; // [rsp+78h] [rbp-140h]
  struct _GUID v61; // [rsp+80h] [rbp-138h] BYREF
  char v62[8]; // [rsp+90h] [rbp-128h] BYREF
  __int128 v63; // [rsp+98h] [rbp-120h] BYREF
  __m128i si128; // [rsp+A8h] [rbp-110h]
  HyperVStorageKeyTableEntry *v65; // [rsp+B8h] [rbp-100h] BYREF
  HyperVStorage *v66; // [rsp+C0h] [rbp-F8h] BYREF
  void *ppvObject; // [rsp+C8h] [rbp-F0h] BYREF
  wchar_t *String[2]; // [rsp+D0h] [rbp-E8h] BYREF
  __int64 v69; // [rsp+E0h] [rbp-D8h]
  unsigned __int64 v70; // [rsp+E8h] [rbp-D0h]
  int v71; // [rsp+F0h] [rbp-C8h] BYREF
  int v72; // [rsp+F4h] [rbp-C4h] BYREF
  __int64 Buf1; // [rsp+F8h] [rbp-C0h] BYREF
  IXmlReaderInput *v74; // [rsp+100h] [rbp-B8h] BYREF
  void *v75[2]; // [rsp+108h] [rbp-B0h] BYREF
  size_t v76; // [rsp+118h] [rbp-A0h]
  unsigned __int64 v77; // [rsp+120h] [rbp-98h]
  __int64 v78; // [rsp+128h] [rbp-90h] BYREF
  double v79; // [rsp+130h] [rbp-88h] BYREF
  LPCWCH lpWideCharStr[2]; // [rsp+138h] [rbp-80h] BYREF
  int cchWideChar[4]; // [rsp+148h] [rbp-70h]
  __int128 v82; // [rsp+158h] [rbp-60h] BYREF
  __int64 v83; // [rsp+168h] [rbp-50h]

  v58 = a4;
  v6 = this;
  *(_QWORD *)v57 = this;
  v59 = this;
  v60 = a4;
  v55 = 0;
  ppvObject = 0;
  v7 = CreateXmlReader(&riid, &ppvObject, 0);
  try
  {
    if ( v7 < 0 )
      HvsThrowHResultError(v7);
    v74 = 0;
    v8 = 1;
    v9 = CreateXmlReaderInputWithEncodingName(a2, 0, L"UTF-16", 1, &HyperVStorage::CFG_XML_NAMESPACE_URI, &v74);
    if ( v9 < 0 )
      HvsThrowHResultError(v9);
    v10 = (*(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)ppvObject + 40LL))(
            ppvObject,
            1,
            (a3 != 0) + 1LL);
    if ( v10 < 0 )
      HvsThrowHResultError(v10);
    v11 = (*(__int64 (__fastcall **)(void *, IXmlReaderInput *))(*(_QWORD *)ppvObject + 24LL))(ppvObject, v74);
    if ( v11 < 0 )
      HvsThrowHResultError(v11);
    v12 = 1;
    *(_OWORD *)String = 0;
    v69 = 0;
    v70 = 7;
    LOWORD(String[0]) = 0;
    v72 = 0;
    v78 = 0;
    Buf1 = 0;
    v79 = 0.0;
    v71 = 0;
    Size = 0x100000000LL;
    v63 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v63) = 0;
    v82 = 0;
    v83 = 0;
    *(_OWORD *)lpWideCharStr = 0;
    *(__m128i *)cchWideChar = si128;
    LOWORD(lpWideCharStr[0]) = 0;
    *(_OWORD *)v75 = 0;
    v76 = 0;
    v77 = 15;
    LOBYTE(v75[0]) = 0;
    LODWORD(v54) = 1;
    v66 = v6;
    v13 = *((_QWORD *)v6 + 24);
    if ( v13 == *((_QWORD *)v6 + 25) )
    {
      std::vector<HyperVStorageOperation>::_Emplace_reallocate<HyperVStorage *,enum HyperVStorageOperationType>(
        (char *)v6 + 184,
        *((_QWORD *)v6 + 24),
        &v66,
        &v54);
    }
    else
    {
      HyperVStorageOperation::HyperVStorageOperation(
        v13,
        ((unsigned __int64)v6 + 8) & ((unsigned __int128)-(__int128)(unsigned __int64)v6 >> 64),
        1);
      *((_QWORD *)v6 + 24) += 88LL;
    }
    v14 = (struct HyperVStorageOperation *)(*((_QWORD *)v6 + 24) - 88LL);
    v54 = v14;
    v15 = (HyperVStorageKeyTableEntry **)((char *)v6 + 248);
    v56 = (HyperVStorage *)((char *)v6 + 248);
    if ( v58 )
    {
      v56 = 0;
      if ( !(unsigned int)HyperVStorage::GetOrCreateNode(v6, v58, v14, &v56, 0) )
        HvsThrowHResultError(-2147467259);
      v15 = (HyperVStorageKeyTableEntry **)*((_QWORD *)v56 + 5);
      v56 = (struct HyperVStorageKeyTableEntry *)v15;
    }
    while ( 1 )
    {
      v16 = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)ppvObject + 48LL))(ppvObject, &v72);
      if ( v16 )
        break;
      switch ( v72 )
      {
        case 1:
          v66 = 0;
          v18 = (*(__int64 (__fastcall **)(void *, HyperVStorage **, _QWORD))(*(_QWORD *)ppvObject + 112LL))(
                  ppvObject,
                  &v66,
                  0);
          if ( v18 < 0 )
            HvsThrowHResultError(v18);
          v19 = -1;
          do
            ++v19;
          while ( *((_WORD *)v66 + v19) );
          std::wstring::_Assign<unsigned short>(lpWideCharStr, v66);
          HyperVStorage::ReadAttributes(
            v20,
            (struct IXmlReader *)ppvObject,
            (enum HyperVStorageKeyType *)((char *)&Size + 4));
          v21 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject + 160LL))(ppvObject);
          HyperVStorage::ReadAttributes(
            v22,
            (struct IXmlReader *)ppvObject,
            (enum HyperVStorageKeyType *)((char *)&Size + 4));
          v69 = 0;
          v23 = String;
          if ( v70 > 7 )
            v23 = (wchar_t **)String[0];
          *(_WORD *)v23 = 0;
          v24 = (const WCHAR *)lpWideCharStr;
          if ( *(_QWORD *)&cchWideChar[2] > 7u )
            v24 = lpWideCharStr[0];
          HvsWideToMultiByte(v24, cchWideChar[0]);
          LOBYTE(v52) = 0;
          v15 = *(HyperVStorageKeyTableEntry ***)(*(_QWORD *)(*(__int64 (__fastcall **)(HyperVStorage *, char *, HyperVStorageKeyTableEntry **, void **, struct HyperVStorageOperation *, _DWORD, int))(*(_QWORD *)v6 + 168LL))(
                                                               v6,
                                                               v62,
                                                               v15,
                                                               v75,
                                                               v14,
                                                               0,
                                                               v52)
                                                + 40LL);
          v56 = (struct HyperVStorageKeyTableEntry *)v15;
          v12 = HIDWORD(Size);
          if ( v21 )
          {
LABEL_30:
            if ( v69 )
            {
              if ( v12 == 1 )
                v12 = 6;
            }
            else if ( (unsigned int)(v12 - 6) > 1 )
            {
              goto LABEL_92;
            }
            if ( v12 == 6 )
            {
              v25 = 2 * v69;
LABEL_46:
              LODWORD(Size) = v25;
              goto LABEL_47;
            }
            if ( v12 != 7 )
            {
              if ( v12 == 3 || v12 == 4 || v12 == 5 )
              {
                v25 = 8;
              }
              else
              {
                v25 = -1;
                if ( v12 == 8 )
                  v25 = 4;
              }
              goto LABEL_46;
            }
            if ( v69 )
            {
              HyperVStorage::ConvertArrayDataFromString(v69, String, &v82, &Size);
              v25 = Size;
            }
            else
            {
              v25 = 0;
              LODWORD(Size) = 0;
            }
LABEL_47:
            if ( v25 < 0x800 )
            {
              v26 = v25;
              if ( (unsigned int)(v12 - 6) <= 1 )
                v26 = v25 + 4;
            }
            else
            {
              v26 = 12;
            }
            v27 = v15[4];
            v65 = v27;
            if ( !v27 || *((_DWORD *)v15 + 6) )
              HvsThrowHResultError(-2147024809);
            Name = HyperVStorageKeyTableEntry::GetName((HyperVStorageKeyTableEntry *)v15);
            v30 = -1;
            do
              ++v30;
            while ( Name[v30] );
            if ( v30 > v77 )
            {
              std::string::_Reallocate_for<_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *>(v75, v30, v29, Name);
            }
            else
            {
              v31 = v75;
              if ( v77 > 0xF )
                v31 = (void **)v75[0];
              v76 = v30;
              memmove_0(v31, Name, v30);
              *((_BYTE *)v31 + v30) = 0;
              v27 = v65;
            }
            v32 = v56;
            HyperVStorageKeyTableEntry::RemoveChild(v27, v56);
            v33 = (char *)*((_QWORD *)v54 + 2);
            v34 = (char *)*((_QWORD *)v54 + 3);
            while ( v33 != v34 )
            {
              if ( *((struct HyperVStorageKeyTableEntry **)v33 + 1) == v32 )
              {
                memmove_0(v33, v33 + 16, v34 - (v33 + 16));
                *((_QWORD *)v54 + 3) -= 16LL;
                break;
              }
              v33 += 16;
            }
            (*(void (__fastcall **)(__int64, struct HyperVStorageKeyTableEntry *))(*(_QWORD *)(*(_QWORD *)v57 + 8LL)
                                                                                 + 8LL))(
              *(_QWORD *)v57 + 8LL,
              v32);
            LOBYTE(v52) = 0;
            ppInput = v26;
            v6 = *(HyperVStorage **)v57;
            v65 = *(HyperVStorageKeyTableEntry **)(*(__int64 (__fastcall **)(_QWORD, struct _GUID *, HyperVStorageKeyTableEntry *, void **, struct HyperVStorageOperation *, int, int))(**(_QWORD **)v57 + 168LL))(
                                                    *(_QWORD *)v57,
                                                    &v61,
                                                    v27,
                                                    v75,
                                                    v54,
                                                    ppInput,
                                                    v52);
            v15 = (HyperVStorageKeyTableEntry **)*((_QWORD *)v65 + 5);
            switch ( v12 )
            {
              case 3:
                v35 = (const wchar_t *)String;
                if ( v70 > 7 )
                  v35 = String[0];
                Buf1 = _wtoi64(v35);
                p_Buf1 = &Buf1;
                break;
              case 4:
                v37 = (const wchar_t *)String;
                if ( v70 > 7 )
                  v37 = String[0];
                v78 = _wtoi64(v37);
                p_Buf1 = &v78;
                break;
              case 5:
                v38 = (const wchar_t *)String;
                if ( v70 > 7 )
                  v38 = String[0];
                v79 = _wtof(v38);
                p_Buf1 = (__int64 *)&v79;
                break;
              case 6:
                p_Buf1 = (__int64 *)String;
                if ( v70 > 7 )
                  p_Buf1 = (__int64 *)String[0];
                break;
              case 7:
                p_Buf1 = (__int64 *)v82;
                break;
              case 8:
                v39 = (const wchar_t *)String;
                if ( v70 > 7 )
                  v39 = String[0];
                Buf1 = _wtoi64(v39);
                v71 = 0;
                v40 = String;
                if ( v70 > 7 )
                  v40 = (wchar_t **)String[0];
                if ( !(unsigned int)_o__wcsicmp(L"true", v40) || Buf1 == 1 )
                  v71 = 1;
                p_Buf1 = (__int64 *)&v71;
                break;
              default:
                if ( (unsigned int)HvsIsDebugTraceEnabled(0x4000u) )
                {
                  v41 = IsHyperVStorageTraceEnabled();
LABEL_98:
                  if ( dword_1800E4790 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                     + (unsigned int)tls_index)
                                                   + 16LL) )
                  {
                    Init_thread_header(&dword_1800E4790);
                    if ( dword_1800E4790 == -1 )
                    {
                      byte_1800E1F9C = v8;
                      byte_1800E1F9D = v41;
                      Init_thread_footer(&dword_1800E4790);
                    }
                  }
                  v46 = std::string::c_str(v75);
                  v49 = std::wstring::c_str(lpWideCharStr, v47, v48, v46);
                  HvsDebugTraceInternal(0x4000u, (const struct HvsDebugTraceParameters *)&off_1800E1F88, v49);
                }
                else
                {
                  v41 = IsHyperVStorageTraceEnabled();
                  if ( v41 )
                  {
                    v8 = 0;
                    goto LABEL_98;
                  }
                }
                HvsThrowHResultError(-2147024809);
            }
            LODWORD(pwszBaseUri) = v25;
            HyperVStorage::SetNodeValue((int)v6, (int)v27, (int)&v65, v12, (size_t)pwszBaseUri, p_Buf1, v54);
            v14 = v54;
LABEL_92:
            v15 = (HyperVStorageKeyTableEntry **)v15[4];
            v56 = (struct HyperVStorageKeyTableEntry *)v15;
            if ( !v15 )
              HvsThrowHResultError(-2147024809);
            v12 = 1;
            HIDWORD(Size) = 1;
            v69 = 0;
            v42 = String;
            if ( v70 > 7 )
              v42 = (wchar_t **)String[0];
            *(_WORD *)v42 = 0;
          }
          break;
        case 3:
        case 4:
LABEL_20:
          v65 = 0;
          v17 = (*(__int64 (__fastcall **)(void *, HyperVStorageKeyTableEntry **, _QWORD))(*(_QWORD *)ppvObject + 128LL))(
                  ppvObject,
                  &v65,
                  0);
          if ( v17 < 0 )
            HvsThrowHResultError(v17);
          std::wstring::append(String, v65);
          break;
        case 13:
          if ( v69 )
            goto LABEL_20;
          break;
        case 15:
          goto LABEL_30;
      }
    }
    if ( v16 < 0 )
      HvsThrowHResultError(v16);
    std::string::~string(v75);
    std::wstring::~wstring(lpWideCharStr);
    std::vector<unsigned char>::~vector<unsigned char>(&v82);
    std::wstring::~wstring(&v63);
    std::wstring::~wstring(String);
    if ( v74 )
      ((void (__fastcall *)(IXmlReaderInput *))v74->lpVtbl->Release)(v74);
    if ( ppvObject )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    v43 = v58;
  }
  catch ( ... )
  {
    HvsGetHResultForThrownException();
  }
  v44 = v55;
  v61 = *(struct _GUID *)((char *)v6 + 568);
  HyperVStorageTrace::ReadFromStream(&v61, a3 != 0, v43, v55);
  return v44;
}

```

## disassembly

```asm
0x180076104  mov     [rsp+arg_10], r8d
0x180076109  push    rbx
0x18007610a  push    rsi
0x18007610b  push    rdi
0x18007610c  push    r12
0x18007610e  push    r13
0x180076110  push    r14
0x180076112  push    r15
0x180076114  sub     rsp, 180h
0x18007611b  mov     rax, cs:__security_cookie
0x180076122  xor     rax, rsp
0x180076125  mov     [rsp+1B8h+var_48], rax
0x18007612d  mov     rax, r9
0x180076130  mov     [rsp+1B8h+var_150], rax
0x180076135  mov     esi, r8d
0x180076138  mov     rbx, rdx
0x18007613b  mov     r12, rcx
0x18007613e  mov     qword ptr [rsp+1B8h+var_158], rcx
0x180076143  mov     [rsp+1B8h+var_148], rcx
0x180076148  mov     [rsp+1B8h+var_140], rax
0x18007614d  xor     edi, edi
0x18007614f  mov     [rsp+1B8h+var_168], edi
0x180076153  mov     [rsp+1B8h+ppvObject], rdi
0x18007615b  xor     r8d, r8d; pMalloc
0x18007615e  lea     rdx, [rsp+1B8h+ppvObject]; ppvObject
0x180076166  lea     rcx, riid; riid
0x18007616d  call    cs:__imp_CreateXmlReader
0x180076173  test    eax, eax
0x180076175  js      loc_180076B17
0x18007617b  mov     [rsp+1B8h+var_B8], rdi
0x180076183  lea     rax, [rsp+1B8h+var_B8]
0x18007618b  mov     [rsp+1B8h+ppInput], rax; ppInput
0x180076190  lea     rax, ?CFG_XML_NAMESPACE_URI@HyperVStorage@@1QBGB; ushort const near * const HyperVStorage::CFG_XML_NAMESPACE_URI
0x180076197  mov     [rsp+1B8h+pwszBaseUri], rax; pwszBaseUri
0x18007619c  lea     r13d, [rdi+1]
0x1800761a0  mov     r9d, r13d; fEncodingHint
0x1800761a3  lea     r8, pwszEncodingName; "UTF-16"
0x1800761aa  xor     edx, edx; pMalloc
0x1800761ac  mov     rcx, rbx; pInputStream
0x1800761af  call    cs:__imp_CreateXmlReaderInputWithEncodingName
0x1800761b5  test    eax, eax
0x1800761b7  js      loc_180076B0F
0x1800761bd  mov     rcx, [rsp+1B8h+ppvObject]
0x1800761c5  mov     r9, [rcx]
0x1800761c8  mov     eax, esi
0x1800761ca  neg     eax
0x1800761cc  sbb     r8, r8
0x1800761cf  neg     r8
0x1800761d2  add     r8, r13
0x1800761d5  mov     edx, r13d
0x1800761d8  mov     rax, [r9+28h]
0x1800761dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800761e1  test    eax, eax
0x1800761e3  js      loc_180076B08
0x1800761e9  mov     rcx, [rsp+1B8h+ppvObject]
0x1800761f1  mov     rax, [rcx]
0x1800761f4  mov     rdx, [rsp+1B8h+var_B8]
0x1800761fc  mov     rax, [rax+18h]
0x180076200  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076205  test    eax, eax
0x180076207  js      loc_180076B01
0x18007620d  mov     esi, r13d
0x180076210  mov     dword ptr [rsp+1B8h+Size+4], r13d
0x180076215  xorps   xmm0, xmm0
0x180076218  movups  xmmword ptr [rsp+1B8h+String], xmm0
0x180076220  mov     [rsp+1B8h+var_D8], rdi
0x180076228  mov     [rsp+1B8h+var_D0], 7
0x180076234  mov     word ptr [rsp+1B8h+String], di
0x18007623c  mov     [rsp+1B8h+var_C4], edi
0x180076243  mov     [rsp+1B8h+var_90], rdi
0x18007624b  mov     [rsp+1B8h+Buf1], rdi
0x180076253  movsd   [rsp+1B8h+var_88], xmm0
0x18007625c  mov     [rsp+1B8h+var_C8], edi
0x180076263  mov     dword ptr [rsp+1B8h+Size], edi
0x180076267  movups  [rsp+1B8h+var_120], xmm0
0x18007626f  movdqa  xmm2, cs:__xmm@00000000000000070000000000000000
0x180076277  movdqu  [rsp+1B8h+var_110], xmm2
0x180076280  mov     word ptr [rsp+1B8h+var_120], di
0x180076288  xorps   xmm1, xmm1
0x18007628b  movdqu  [rsp+1B8h+var_60], xmm1
0x180076294  mov     [rsp+1B8h+var_50], rdi
0x18007629c  movups  xmmword ptr [rsp+1B8h+lpWideCharStr], xmm0
0x1800762a4  movdqu  xmmword ptr [rsp+1B8h+cchWideChar], xmm2
0x1800762ad  mov     word ptr [rsp+1B8h+lpWideCharStr], di
0x1800762b5  movups  xmmword ptr [rsp+1B8h+var_B0], xmm0
0x1800762bd  mov     [rsp+1B8h+var_A0], rdi
0x1800762c5  mov     [rsp+1B8h+var_98], 0Fh
0x1800762d1  mov     byte ptr [rsp+1B8h+var_B0], dil
0x1800762d9  lea     rbx, [r12+0B8h]
0x1800762e1  mov     dword ptr [rsp+1B8h+var_170], r13d
0x1800762e6  mov     [rsp+1B8h+var_F8], r12
0x1800762ee  mov     rcx, [rbx+8]
0x1800762f2  cmp     rcx, [rbx+10h]
0x1800762f6  jz      short loc_180076318
0x1800762f8  mov     rax, r12
0x1800762fb  lea     r8, [r12+8]
0x180076300  neg     rax
0x180076303  sbb     rdx, rdx
0x180076306  and     rdx, r8
0x180076309  mov     r8d, r13d
0x18007630c  call    ??0HyperVStorageOperation@@QEAA@PEAVHyperVStorageOperationsInterface@@W4HyperVStorageOperationType@@@Z; HyperVStorageOperation::HyperVStorageOperation(HyperVStorageOperationsInterface *,HyperVStorageOperationType)
0x180076311  add     qword ptr [rbx+8], 58h ; 'X'
0x180076316  jmp     short loc_180076330
0x180076318  lea     r9, [rsp+1B8h+var_170]
0x18007631d  lea     r8, [rsp+1B8h+var_F8]
0x180076325  mov     rdx, rcx
0x180076328  mov     rcx, rbx
0x18007632b  call    ??$_Emplace_reallocate@PEAVHyperVStorage@@W4HyperVStorageOperationType@@@?$vector@VHyperVStorageOperation@@V?$allocator@VHyperVStorageOperation@@@std@@@std@@AEAAPEAVHyperVStorageOperation@@QEAV2@$$QEAPEAVHyperVStorage@@$$QEAW4HyperVStorageOperationType@@@Z; std::vector<HyperVStorageOperation>::_Emplace_reallocate<HyperVStorage *,HyperVStorageOperationType>(HyperVStorageOperation * const,HyperVStorage * &&,HyperVStorageOperationType &&)
0x180076330  mov     r14, [r12+0C0h]
0x180076338  sub     r14, 58h ; 'X'
0x18007633c  mov     [rsp+1B8h+var_170], r14
0x180076341  lea     r15, [r12+0F8h]
0x180076349  mov     [rsp+1B8h+var_160], r15
0x18007634e  mov     rax, [rsp+1B8h+var_150]
0x180076353  test    rax, rax
0x180076356  jz      short loc_180076390
0x180076358  mov     [rsp+1B8h+var_160], rdi
0x18007635d  mov     byte ptr [rsp+1B8h+var_188], dil
0x180076362  mov     [rsp+1B8h+pwszBaseUri], rdi
0x180076367  lea     r9, [rsp+1B8h+var_160]
0x18007636c  mov     r8, r14
0x18007636f  mov     rdx, rax
0x180076372  mov     rcx, r12
0x180076375  call    ?GetOrCreateNode@HyperVStorage@@IEAAHPEBGPEAVHyperVStorageOperation@@AEAV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBDPEAVHyperVStorageKeyTableEntry@@@std@@@std@@@std@@@std@@PEAPEAVHyperVStorageKeyTableEntry@@IE@Z; HyperVStorage::GetOrCreateNode(ushort const *,HyperVStorageOperation *,std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<char const * const,HyperVStorageKeyTableEntry *>>>> &,HyperVStorageKeyTableEntry * *,uint,uchar)
0x18007637a  test    eax, eax
0x18007637c  jz      loc_180076A65
0x180076382  mov     rax, [rsp+1B8h+var_160]
0x180076387  mov     r15, [rax+28h]
0x18007638b  mov     [rsp+1B8h+var_160], r15
0x180076390  mov     ebx, 4
0x180076395  mov     rcx, [rsp+1B8h+ppvObject]
0x18007639d  mov     rax, [rcx]
0x1800763a0  lea     rdx, [rsp+1B8h+var_C4]
0x1800763a8  mov     rax, [rax+30h]
0x1800763ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800763b1  test    eax, eax
0x1800763b3  jnz     loc_180076978
0x1800763b9  mov     ecx, [rsp+1B8h+var_C4]
0x1800763c0  sub     ecx, 1
0x1800763c3  jz      short loc_180076434
0x1800763c5  sub     ecx, 2
0x1800763c8  jz      short loc_1800763E8
0x1800763ca  sub     ecx, 1
0x1800763cd  jz      short loc_1800763E8
0x1800763cf  sub     ecx, 9
0x1800763d2  jz      short loc_1800763DE
0x1800763d4  cmp     ecx, 2
0x1800763d7  jnz     short loc_180076395
0x1800763d9  jmp     loc_180076567
0x1800763de  cmp     [rsp+1B8h+var_D8], rdi
0x1800763e6  jz      short loc_180076395
0x1800763e8  mov     [rsp+1B8h+var_100], rdi
0x1800763f0  mov     rcx, [rsp+1B8h+ppvObject]
0x1800763f8  mov     rax, [rcx]
0x1800763fb  xor     r8d, r8d
0x1800763fe  lea     rdx, [rsp+1B8h+var_100]
0x180076406  mov     rax, [rax+80h]
0x18007640d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076412  test    eax, eax
0x180076414  js      loc_180076A70
0x18007641a  mov     rdx, [rsp+1B8h+var_100]; void *
0x180076422  lea     rcx, [rsp+1B8h+String]; Src
0x18007642a  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18007642f  jmp     loc_180076395
0x180076434  mov     [rsp+1B8h+var_F8], rdi
0x18007643c  mov     rcx, [rsp+1B8h+ppvObject]
0x180076444  mov     rax, [rcx]
0x180076447  xor     r8d, r8d
0x18007644a  lea     rdx, [rsp+1B8h+var_F8]
0x180076452  mov     rax, [rax+70h]
0x180076456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007645b  test    eax, eax
0x18007645d  js      loc_180076AF1
0x180076463  mov     rdx, [rsp+1B8h+var_F8]
0x18007646b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18007646f  inc     r8
0x180076472  cmp     [rdx+r8*2], di
0x180076477  jnz     short loc_18007646F
0x180076479  lea     rcx, [rsp+1B8h+lpWideCharStr]
0x180076481  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180076486  lea     r8, [rsp+1B8h+Size+4]; enum HyperVStorageKeyType *
0x18007648b  mov     rdx, [rsp+1B8h+ppvObject]; struct IXmlReader *
0x180076493  call    ?ReadAttributes@HyperVStorage@@IEAAXPEAUIXmlReader@@AEAW4HyperVStorageKeyType@@@Z; HyperVStorage::ReadAttributes(IXmlReader *,HyperVStorageKeyType &)
0x180076498  mov     rcx, [rsp+1B8h+ppvObject]
0x1800764a0  mov     rax, [rcx]
0x1800764a3  mov     rax, [rax+0A0h]
0x1800764aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800764af  mov     ebx, eax
0x1800764b1  lea     r8, [rsp+1B8h+Size+4]; enum HyperVStorageKeyType *
0x1800764b6  mov     rdx, [rsp+1B8h+ppvObject]; struct IXmlReader *
0x1800764be  call    ?ReadAttributes@HyperVStorage@@IEAAXPEAUIXmlReader@@AEAW4HyperVStorageKeyType@@@Z; HyperVStorage::ReadAttributes(IXmlReader *,HyperVStorageKeyType &)
0x1800764c3  mov     [rsp+1B8h+var_D8], rdi
0x1800764cb  lea     rax, [rsp+1B8h+String]
0x1800764d3  cmp     [rsp+1B8h+var_D0], 7
0x1800764dc  cmova   rax, [rsp+1B8h+String]
0x1800764e5  mov     [rax], di
0x1800764e8  mov     edx, [rsp+1B8h+cchWideChar]; cchWideChar
0x1800764ef  lea     rcx, [rsp+1B8h+lpWideCharStr]
0x1800764f7  cmp     qword ptr [rsp+1B8h+cchWideChar+8], 7
0x180076500  cmova   rcx, [rsp+1B8h+lpWideCharStr]; lpWideCharStr
0x180076509  lea     r9, [rsp+1B8h+var_B0]
0x180076511  call    ?HvsWideToMultiByte@@YA_KPEBG_KIAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; HvsWideToMultiByte(ushort const *,unsigned __int64,uint,std::string &)
0x180076516  mov     rax, [r12]
0x18007651a  mov     byte ptr [rsp+1B8h+var_188], dil
0x18007651f  mov     dword ptr [rsp+1B8h+ppInput], edi
0x180076523  mov     [rsp+1B8h+pwszBaseUri], r14
0x180076528  lea     r9, [rsp+1B8h+var_B0]
0x180076530  mov     r8, r15
0x180076533  lea     rdx, [rsp+1B8h+var_128]
0x18007653b  mov     rcx, r12
0x18007653e  mov     rax, [rax+0A8h]
0x180076545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007654a  mov     rax, [rax]
0x18007654d  mov     r15, [rax+28h]
0x180076551  mov     [rsp+1B8h+var_160], r15
0x180076556  mov     esi, dword ptr [rsp+1B8h+Size+4]
0x18007655a  test    ebx, ebx
0x18007655c  jz      loc_180076390
0x180076562  mov     ebx, 4
0x180076567  mov     rcx, [rsp+1B8h+var_D8]
0x18007656f  test    rcx, rcx
0x180076572  jz      short loc_180076580
0x180076574  cmp     esi, r13d
0x180076577  jnz     short loc_18007658C
0x180076579  mov     esi, 6
0x18007657e  jmp     short loc_18007658C
0x180076580  lea     eax, [rsi-6]
0x180076583  cmp     eax, r13d
0x180076586  ja      loc_1800768DB
0x18007658c  cmp     esi, 6
0x18007658f  jnz     short loc_180076597
0x180076591  lea     r14d, [rcx+rcx]
0x180076595  jmp     short loc_1800765EC
0x180076597  cmp     esi, 7
0x18007659a  jnz     short loc_1800765CB
0x18007659c  test    rcx, rcx
0x18007659f  jz      short loc_1800765C2
0x1800765a1  lea     r9, [rsp+1B8h+Size]
0x1800765a6  lea     r8, [rsp+1B8h+var_60]
0x1800765ae  lea     rdx, [rsp+1B8h+String]
0x1800765b6  call    ?ConvertArrayDataFromString@HyperVStorage@@IEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@EV?$allocator@E@std@@@3@AEAI@Z; HyperVStorage::ConvertArrayDataFromString(std::wstring const &,std::vector<uchar> &,uint &)
0x1800765bb  mov     r14d, dword ptr [rsp+1B8h+Size]
0x1800765c0  jmp     short loc_1800765F1
0x1800765c2  mov     r14d, edi
0x1800765c5  mov     dword ptr [rsp+1B8h+Size], edi
0x1800765c9  jmp     short loc_1800765F1
0x1800765cb  cmp     esi, 3
0x1800765ce  jnz     short loc_1800765D8
0x1800765d0  mov     r14d, 8
0x1800765d6  jmp     short loc_1800765EC
0x1800765d8  cmp     esi, ebx
0x1800765da  jz      short loc_1800765D0
0x1800765dc  cmp     esi, 5
0x1800765df  jz      short loc_1800765D0
0x1800765e1  or      r14d, 0FFFFFFFFh
0x1800765e5  cmp     esi, 8
0x1800765e8  cmovz   r14d, ebx
0x1800765ec  mov     dword ptr [rsp+1B8h+Size], r14d
0x1800765f1  cmp     r14d, 800h
0x1800765f8  jb      short loc_180076602
0x1800765fa  mov     r12d, 0Ch
0x180076600  jmp     short loc_180076611
0x180076602  lea     eax, [rsi-6]
0x180076605  cmp     eax, r13d
0x180076608  mov     r12d, r14d
0x18007660b  ja      short loc_180076611
0x18007660d  lea     r12d, [r14+4]
0x180076611  mov     rbx, [r15+20h]
0x180076615  mov     [rsp+1B8h+var_100], rbx
0x18007661d  test    rbx, rbx
0x180076620  jz      loc_180076AE7
0x180076626  cmp     [r15+18h], edi
0x18007662a  jnz     loc_180076AE7
0x180076630  mov     rcx, r15; this
0x180076633  call    ?GetName@HyperVStorageKeyTableEntry@@QEBAPEBDXZ; HyperVStorageKeyTableEntry::GetName(void)
0x180076638  or      r15, 0FFFFFFFFFFFFFFFFh
0x18007663c  inc     r15
0x18007663f  cmp     [rax+r15], dil
0x180076643  jnz     short loc_18007663C
0x180076645  cmp     r15, [rsp+1B8h+var_98]
0x18007664d  ja      short loc_18007668D
0x18007664f  lea     rbx, [rsp+1B8h+var_B0]
0x180076657  cmp     [rsp+1B8h+var_98], 0Fh
0x180076660  cmova   rbx, [rsp+1B8h+var_B0]
0x180076669  mov     [rsp+1B8h+var_A0], r15
0x180076671  mov     r8, r15; Size
0x180076674  mov     rdx, rax; Src
0x180076677  mov     rcx, rbx; void *
0x18007667a  call    memmove_0
0x18007667f  mov     [r15+rbx], dil
0x180076683  mov     rbx, [rsp+1B8h+var_100]
0x18007668b  jmp     short loc_1800766A0
0x18007668d  mov     r9, rax
0x180076690  mov     rdx, r15
0x180076693  lea     rcx, [rsp+1B8h+var_B0]
0x18007669b  call    ??$_Reallocate_for@V_lambda_a132b9f505f015b07a26cb4edca31da2_@@PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_a132b9f505f015b07a26cb4edca31da2_@@PEBD@Z; std::string::_Reallocate_for<_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *>(unsigned __int64,_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *)
0x1800766a0  mov     r15, [rsp+1B8h+var_160]
0x1800766a5  mov     rdx, r15; struct HyperVStorageKeyTableEntry *
0x1800766a8  mov     rcx, rbx; this
0x1800766ab  call    ?RemoveChild@HyperVStorageKeyTableEntry@@QEAAXPEAV1@@Z; HyperVStorageKeyTableEntry::RemoveChild(HyperVStorageKeyTableEntry *)
  ... truncated ...
```
