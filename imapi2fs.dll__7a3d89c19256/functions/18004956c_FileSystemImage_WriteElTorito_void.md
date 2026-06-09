# FileSystemImage::WriteElTorito(void)

- ea: `0x18004956c`
- end: `0x180049e7a`
- name: `?WriteElTorito@FileSystemImage@@AEAAXXZ`
- size: `2318`
- prototype: `void __fastcall(FileSystemImage *__hidden this)`
- caller_count: `1`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x180042f58`

## callees

- `0x180003580`
- `0x180003a20`
- `0x180005040`
- `0x18000960c`
- `0x180018e20`
- `0x18001f27c`
- `0x1800251dc`
- `0x180028568`
- `0x18002d4e4`
- `0x18002dc70`
- `0x18002f620`
- `0x18003c4bc`
- `0x1800423d0`
- `0x180042880`
- `0x180049128`
- `0x18004956c`
- `0x180049e80`
- `0x18008170e`
- `0x18008171a`
- `0x180081750`
- `0x180088010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800496da`
- `OLEAUT32!__imp_SysAllocString` at `0x1800496da`
- `OLEAUT32!__imp_SysFreeString` at `0x180049703`
- `OLEAUT32!__imp_SysFreeString` at `0x180049711`
- `OLEAUT32!__imp_SysFreeString` at `0x18004995c`
- `OLEAUT32!__imp_SysFreeString` at `0x18004996c`
- `OLEAUT32!__imp_SysFreeString` at `0x180049a29`
- `OLEAUT32!__imp_SysFreeString` at `0x180049a39`
- `OLEAUT32!__imp_SysFreeString` at `0x180049b9f`
- `OLEAUT32!__imp_SysFreeString` at `0x180049baf`
- `OLEAUT32!__imp_SysFreeString` at `0x180049703`
- `OLEAUT32!__imp_SysFreeString` at `0x180049711`
- `OLEAUT32!__imp_SysFreeString` at `0x18004995c`
- `OLEAUT32!__imp_SysFreeString` at `0x18004996c`
- `OLEAUT32!__imp_SysFreeString` at `0x180049a29`
- `OLEAUT32!__imp_SysFreeString` at `0x180049a39`
- `OLEAUT32!__imp_SysFreeString` at `0x180049b9f`
- `OLEAUT32!__imp_SysFreeString` at `0x180049baf`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall FileSystemImage::WriteElTorito(FileSystemImage *this)
{
  unsigned __int8 *v2; // rcx
  __int16 v3; // r12
  unsigned __int8 *v4; // r8
  unsigned int v5; // ebx
  unsigned int i; // edi
  __int64 v7; // rax
  __int64 v8; // rax
  wchar_t *v9; // rbx
  OLECHAR *v10; // rbx
  __int64 v11; // rax
  unsigned __int8 *v12; // rdi
  int v13; // r14d
  __int64 v14; // rax
  __int64 v15; // rax
  bool v16; // r8
  const char *v17; // rax
  unsigned int v18; // ecx
  __m128i v19; // xmm1
  __m128i v20; // xmm0
  __m128i v21; // xmm1
  __m128i v22; // xmm1
  __int64 v23; // rax
  char v24; // dl
  __int64 v25; // rax
  unsigned int v26; // eax
  int j; // ecx
  __int64 v28; // rbx
  __int64 v29; // rax
  BSTR v30; // rax
  int v31; // edx
  int v32; // r8d
  bool v33; // bl
  unsigned int v34; // ebx
  char v35; // al
  char *v36; // r15
  __int64 v37; // rax
  __int64 v38; // rax
  BSTR v39; // rax
  int v40; // edx
  int v41; // r8d
  bool v42; // zf
  char *v43; // rbx
  __int64 v44; // rax
  __int64 v45; // rax
  bool v46; // r8
  const char *v47; // rax
  char v48; // r15
  unsigned int k; // ebx
  char *v50; // r12
  __int64 v51; // rax
  __int64 v52; // rax
  BSTR v53; // rax
  int v54; // edx
  int v55; // r8d
  bool v56; // zf
  char *v57; // r12
  __int64 v58; // rax
  __int64 v59; // rax
  unsigned int v60; // eax
  unsigned int m; // r14d
  unsigned int v62; // r15d
  __int64 v63; // rdi
  void (__fastcall *v64)(__int64, __int64 *); // rbx
  __int64 v65; // rax
  __int64 v66; // rax
  unsigned int v67; // edx
  CIMAPIException *v68; // rax
  CIMAPIException *v69; // rax
  CIMAPIException **v70; // rbx
  BSTR v71; // [rsp+30h] [rbp-D0h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v73; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *String1; // [rsp+48h] [rbp-B8h] BYREF
  CIMAPIException **v75; // [rsp+50h] [rbp-B0h] BYREF
  int v76; // [rsp+58h] [rbp-A8h] BYREF
  CIMAPIException **pExceptionObject; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v78; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int8 **v79; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v80; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int8 v81[96]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int8 v82[2048]; // [rsp+E0h] [rbp-20h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 49, &WPP_a4ce3c455c623a57c7cb4594e9846ff6_Traceguids);
  }
  Utility::CreateBaseVD(&v79);
  if ( v79 )
    v2 = *v79;
  else
    v2 = 0;
  *v2 = 0;
  v3 = 1;
  v2[6] = 1;
  qmemcpy(v2 + 7, "EL TORITO SPECIFICATION", 23);
  *(_DWORD *)(v2 + 71) = *((_DWORD *)this + 105);
  if ( v79 )
    v4 = *v79;
  else
    v4 = 0;
  FileSystemImage::WriteImageBlock(this, *((_DWORD *)this + 101), v4, 1u);
  v5 = *((_DWORD *)this + 16);
  if ( v5 > 1 )
  {
    for ( i = 0; i < v5; ++i )
    {
      if ( *((_QWORD *)this + (int)i + 9) )
      {
        LODWORD(bstrString) = 0;
        String1 = 0;
        v7 = _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::operator->((char *)this + 8 * (int)i + 72);
        (*(void (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v7 + 80LL))(v7, &bstrString);
        v8 = _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::operator->((char *)this + 8 * (int)i + 72);
        (*(void (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v8 + 64LL))(v8, &String1);
        v9 = String1;
        if ( String1 && (_DWORD)bstrString == 239 && !wcscmp_0(String1, L"Microsoft IMAPIv2") )
        {
          v10 = SysAllocString(&psz);
          v11 = _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::operator->((char *)this + 8 * (int)i + 72);
          (*(void (__fastcall **)(__int64, OLECHAR *))(*(_QWORD *)v11 + 72LL))(v11, v10);
          SysFreeString(v10);
          v9 = String1;
        }
        SysFreeString(v9);
      }
      v5 = *((_DWORD *)this + 16);
    }
  }
  memset_0(v82, 0, sizeof(v82));
  v12 = v82;
  v13 = 0;
  if ( !v5 )
    goto LABEL_78;
  do
  {
    if ( !v13 )
    {
      *v12 = 1;
      LODWORD(bstrString) = 0;
      v14 = _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::operator->((char *)this + 72);
      (*(void (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v14 + 80LL))(v14, &bstrString);
      v12[1] = (unsigned __int8)bstrString;
      v80 = 0;
      v15 = _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::operator->((char *)this + 72);
      (*(void (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v15 + 64LL))(v15, &v80);
      _bstr_t::_bstr_t((_bstr_t *)&pExceptionObject, v80, v16);
      v17 = (const char *)_bstr_t::operator char *(&pExceptionObject);
      StringCbCopyA((char *)v12 + 4, 0x17u, v17);
      *((_WORD *)v12 + 15) = -21931;
      v18 = 0;
      v19 = 0;
      do
      {
        v20 = _mm_add_epi16(_mm_loadu_si128((const __m128i *)&v12[2 * v18]), v19);
        v19 = v20;
        v18 += 8;
      }
      while ( v18 < 0x10 );
      v21 = _mm_add_epi16(v20, _mm_srli_si128(v20, 8));
      v22 = _mm_add_epi16(v21, _mm_srli_si128(v21, 4));
      *((_WORD *)v12 + 14) = -(__int16)_mm_cvtsi128_si32(_mm_add_epi16(v22, _mm_srli_si128(v22, 2)));
      v12[32] = -120;
      v76 = 0;
      v23 = _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::operator->((char *)this + 72);
      (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v23 + 96LL))(v23, &v76);
      v24 = v76;
      v12[33] = v76;
      *((_WORD *)v12 + 17) = 0;
      if ( v24 )
      {
        LOWORD(v26) = 1;
      }
      else
      {
        LODWORD(v71) = 0;
        v25 = _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::operator->((char *)this + 72);
        (*(void (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v25 + 112LL))(v25, &v71);
        v26 = (unsigned int)v71 >> 9;
      }
      *((_WORD *)v12 + 19) = v26;
      *((_DWORD *)v12 + 10) = *((_DWORD *)this + 107);
      v12 += 64;
      _bstr_t::~_bstr_t((_bstr_t *)&pExceptionObject);
      goto LABEL_77;
    }
    if ( v13 <= 0 )
      goto LABEL_77;
    if ( v13 != 1 )
    {
      for ( j = v13 - 1; ; --j )
      {
        if ( j < 0 )
          goto LABEL_59;
        v28 = *((_QWORD *)this + j + 9);
        if ( v28 )
          break;
      }
      bstrString = 0;
      v71 = 0;
      v29 = _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::operator->((char *)this + 8 * v13 + 72);
      (*(void (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v29 + 64LL))(v29, &bstrString);
      (*(void (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v28 + 64LL))(v28, &v71);
      if ( bstrString )
      {
        if ( v71 )
        {
          v30 = bstrString;
          do
          {
            v31 = *(BSTR)((char *)v30 + (char *)v71 - (char *)bstrString);
            v32 = *v30 - v31;
            if ( v32 )
              break;
            ++v30;
          }
          while ( v31 );
          v33 = v32 != 0;
LABEL_42:
          SysFreeString(bstrString);
          bstrString = 0;
          SysFreeString(v71);
          if ( !v33 )
            goto LABEL_59;
          goto LABEL_43;
        }
      }
      else
      {
        v33 = 0;
        if ( !v71 )
          goto LABEL_42;
      }
      v33 = 1;
      goto LABEL_42;
    }
LABEL_43:
    v34 = v13 + 1;
    v35 = 1;
    while ( v34 < *((_DWORD *)this + 16) )
    {
      v36 = (char *)this + 8 * (int)v34;
      if ( *((_QWORD *)v36 + 9) )
      {
        bstrString = 0;
        v71 = 0;
        v37 = _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::operator->((char *)this + 8 * v13 + 72);
        (*(void (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v37 + 64LL))(v37, &bstrString);
        v38 = _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::operator->(v36 + 72);
        (*(void (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v38 + 64LL))(v38, &v71);
        if ( bstrString )
        {
          if ( !v71 )
            goto LABEL_57;
          v39 = bstrString;
          do
          {
            v40 = *(BSTR)((char *)v39 + (char *)v71 - (char *)bstrString);
            v41 = *v39 - v40;
            if ( v41 )
              break;
            ++v39;
          }
          while ( v40 );
          v42 = v41 == 0;
        }
        else
        {
          v42 = v71 == 0;
        }
        if ( !v42 )
        {
LABEL_57:
          v35 = 0;
          break;
        }
        SysFreeString(bstrString);
        bstrString = 0;
        SysFreeString(v71);
        v35 = 1;
        ++v3;
      }
      else
      {
        v35 = 1;
      }
      ++v34;
    }
    *v12 = v35 - 112;
    *((_WORD *)v12 + 1) = v3;
    LODWORD(v73) = 0;
    v43 = (char *)this + 8 * v13;
    v44 = _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::operator->(v43 + 72);
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v44 + 80LL))(v44, &v73);
    v12[1] = v73;
    v78 = 0;
    v45 = _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::operator->(v43 + 72);
    (*(void (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v45 + 64LL))(v45, &v78);
    _bstr_t::_bstr_t((_bstr_t *)&v75, v78, v46);
    v47 = (const char *)_bstr_t::operator char *(&v75);
    StringCbCopyA((char *)v12 + 4, 0x1Bu, v47);
    v12 += 32;
    _bstr_t::~_bstr_t((_bstr_t *)&v75);
LABEL_59:
    v48 = 0;
    for ( k = v13 + 1; k < *((_DWORD *)this + 16); ++k )
    {
      v50 = (char *)this + 8 * (int)k;
      if ( !*((_QWORD *)v50 + 9) )
        continue;
      bstrString = 0;
      v71 = 0;
      v51 = _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::operator->((char *)this + 8 * v13 + 72);
      (*(void (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v51 + 64LL))(v51, &bstrString);
      v52 = _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::operator->(v50 + 72);
      (*(void (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v52 + 64LL))(v52, &v71);
      if ( !bstrString )
      {
        v56 = v71 == 0;
        goto LABEL_69;
      }
      if ( v71 )
      {
        v53 = bstrString;
        do
        {
          v54 = *(BSTR)((char *)v53 + (char *)v71 - (char *)bstrString);
          v55 = *v53 - v54;
          if ( v55 )
            break;
          ++v53;
        }
        while ( v54 );
        v56 = v55 == 0;
LABEL_69:
        if ( v56 )
        {
          v48 = 1;
          break;
        }
      }
      SysFreeString(bstrString);
      bstrString = 0;
      SysFreeString(v71);
    }
    *v12 = -120;
    LODWORD(String1) = 0;
    v57 = (char *)this + 8 * v13;
    v58 = _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::operator->(v57 + 72);
    (*(void (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v58 + 96LL))(v58, &String1);
    *((_WORD *)v12 + 1) = 0;
    v12[1] &= 0xD0u;
    v12[1] |= (unsigned __int8)(32 * v48) | (unsigned __int8)String1 & 0xF;
    if ( (v12[1] & 0xF) != 0 )
    {
      v3 = 1;
      LOWORD(v60) = 1;
    }
    else
    {
      LODWORD(v71) = 0;
      v59 = _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::operator->(v57 + 72);
      (*(void (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v59 + 112LL))(v59, &v71);
      v60 = (unsigned int)v71 >> 9;
      v3 = 1;
    }
    *((_WORD *)v12 + 3) = v60;
    *((_DWORD *)v12 + 2) = *((_DWORD *)this + v13 + 107);
    v12 += 32;
LABEL_77:
    ++v13;
  }
  while ( (unsigned int)v13 < *((_DWORD *)this + 16) );
LABEL_78:
  FileSystemImage::WriteImageBlock(this, *((_DWORD *)this + 105), v82, 1u);
  for ( m = 0; m < *((_DWORD *)this + 16); ++m )
  {
    v62 = *((_DWORD *)this + (int)m + 107);
    if ( v62 )
    {
      v73 = 0;
      v63 = _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::operator->((char *)this + 8 * (int)m + 72);
      v64 = *(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v63 + 56LL);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v73);
      v73 = 0;
      v64(v63, &v73);
      v75 = 0;
      v78 = 0;
      v65 = _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::operator->(&v73);
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD, unsigned __int16 **))(*(_QWORD *)v65 + 40LL))(v65, 0, 0, &v78);
      LODWORD(String1) = 0;
      do
      {
        memset_0(v82, 0, sizeof(v82));
        v66 = _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::operator->(&v73);
        if ( (*(int (__fastcall **)(__int64, unsigned __int8 *, __int64, wchar_t **))(*(_QWORD *)v66 + 24LL))(
               v66,
               v82,
               2048,
               &String1) < 0 )
        {
          v68 = (CIMAPIException *)operator new(0x58u);
          v75 = (CIMAPIException **)v68;
          if ( v68 )
            v69 = CIMAPIException::CIMAPIException(v68, -1062555320);
          else
            v69 = 0;
          SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v75, v69);
          v70 = v75;
          if ( v75 && *v75 )
          {
            CIMAPIException::SetCodeRefInfo(*v75, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsifsi.cpp", 1578);
            pExceptionObject = v70;
            if ( v70 )
              ++*((_DWORD *)v70 + 2);
            throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
          }
          CIMAPIException::CIMAPIException(
            (CIMAPIException *)v81,
            (const struct CIMAPIException *)&CIMAPIException::badAlloc);
          throw (CIMAPIException *)v81;
        }
        v67 = v62++;
        FileSystemImage::WriteImageBlock(this, v67, v82, 1u);
      }
      while ( (unsigned int)String1 >= 0x800 );
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v73);
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 50, &WPP_a4ce3c455c623a57c7cb4594e9846ff6_Traceguids);
  }
  SmartArrayPtr<unsigned char>::~SmartArrayPtr<unsigned char>(&v79);
}

```

## disassembly

```asm
0x18004956c  push    rbp
0x18004956e  push    rbx
0x18004956f  push    rsi
0x180049570  push    rdi
0x180049571  push    r12
0x180049573  push    r13
0x180049575  push    r14
0x180049577  push    r15
0x180049579  lea     rbp, [rsp-7F8h]
0x180049581  sub     rsp, 8F8h
0x180049588  mov     rax, cs:__security_cookie
0x18004958f  xor     rax, rsp
0x180049592  mov     [rbp+830h+var_50], rax
0x180049599  mov     rsi, rcx
0x18004959c  lea     r15, WPP_GLOBAL_Control
0x1800495a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800495aa  cmp     rcx, r15
0x1800495ad  jz      short loc_1800495D0
0x1800495af  test    byte ptr [rcx+44h], 8
0x1800495b3  jz      short loc_1800495D0
0x1800495b5  cmp     byte ptr [rcx+41h], 5
0x1800495b9  jb      short loc_1800495D0
0x1800495bb  mov     edx, 31h ; '1'
0x1800495c0  lea     r8, WPP_a4ce3c455c623a57c7cb4594e9846ff6_Traceguids
0x1800495c7  mov     rcx, [rcx+38h]
0x1800495cb  call    WPP_SF_
0x1800495d0  lea     rcx, [rsp+930h+var_8C0]
0x1800495d5  call    ?CreateBaseVD@Utility@@SA?AV?$SmartArrayPtr@E@@XZ; Utility::CreateBaseVD(void)
0x1800495da  nop
0x1800495db  mov     rax, [rsp+930h+var_8C0]
0x1800495e0  xor     r13d, r13d
0x1800495e3  test    rax, rax
0x1800495e6  jz      short loc_1800495ED
0x1800495e8  mov     rcx, [rax]
0x1800495eb  jmp     short loc_1800495F0
0x1800495ed  mov     rcx, r13
0x1800495f0  mov     [rcx], r13b
0x1800495f3  mov     r12d, 1
0x1800495f9  mov     [rcx+6], r12b
0x1800495fd  movups  xmm0, cs:xmmword_180098910
0x180049604  movups  xmmword ptr [rcx+7], xmm0
0x180049608  movsd   xmm1, qword ptr cs:xmmword_180098910+0Fh
0x180049610  movsd   qword ptr [rcx+16h], xmm1
0x180049615  mov     eax, [rsi+1A4h]
0x18004961b  mov     [rcx+47h], eax
0x18004961e  mov     rax, [rsp+930h+var_8C0]
0x180049623  test    rax, rax
0x180049626  jz      short loc_18004962D
0x180049628  mov     r8, [rax]
0x18004962b  jmp     short loc_180049630
0x18004962d  mov     r8, r13; unsigned __int8 *
0x180049630  mov     r9d, r12d; unsigned int
0x180049633  mov     edx, [rsi+194h]; unsigned int
0x180049639  mov     rcx, rsi; this
0x18004963c  call    ?WriteImageBlock@FileSystemImage@@QEAAXKPEAEK@Z; FileSystemImage::WriteImageBlock(ulong,uchar *,ulong)
0x180049641  mov     ebx, [rsi+40h]
0x180049644  cmp     ebx, r12d
0x180049647  jbe     loc_180049725
0x18004964d  mov     edi, r13d
0x180049650  movsxd  r14, edi
0x180049653  add     r14, 9
0x180049657  lea     r14, [rsi+r14*8]
0x18004965b  cmp     [r14], r13
0x18004965e  jz      loc_180049717
0x180049664  mov     dword ptr [rsp+930h+bstrString], r13d
0x180049669  mov     [rsp+930h+String1], r13
0x18004966e  mov     rcx, r14
0x180049671  call    ??C?$_com_ptr_t@V?$_com_IIID@UIStream@@$1?_GUID_0000000c_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEBAPEAUIStream@@XZ; _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::operator->(void)
0x180049676  mov     r8, rax
0x180049679  mov     rcx, [rax]
0x18004967c  mov     rax, [rcx+50h]
0x180049680  lea     rdx, [rsp+930h+bstrString]
0x180049685  mov     rcx, r8
0x180049688  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004968d  mov     rcx, r14
0x180049690  call    ??C?$_com_ptr_t@V?$_com_IIID@UIStream@@$1?_GUID_0000000c_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEBAPEAUIStream@@XZ; _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::operator->(void)
0x180049695  mov     r8, rax
0x180049698  mov     rcx, [rax]
0x18004969b  mov     rax, [rcx+40h]
0x18004969f  lea     rdx, [rsp+930h+String1]
0x1800496a4  mov     rcx, r8
0x1800496a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800496ac  mov     rbx, [rsp+930h+String1]
0x1800496b1  test    rbx, rbx
0x1800496b4  jz      short loc_18004970E
0x1800496b6  cmp     dword ptr [rsp+930h+bstrString], 0EFh
0x1800496be  jnz     short loc_18004970E
0x1800496c0  lea     rdx, aMicrosoftImapi_0; "Microsoft IMAPIv2"
0x1800496c7  mov     rcx, rbx; String1
0x1800496ca  call    wcscmp_0
0x1800496cf  test    eax, eax
0x1800496d1  jnz     short loc_18004970E
0x1800496d3  lea     rcx, psz; psz
0x1800496da  call    cs:__imp_SysAllocString
0x1800496e0  mov     rbx, rax
0x1800496e3  mov     rcx, r14
0x1800496e6  call    ??C?$_com_ptr_t@V?$_com_IIID@UIStream@@$1?_GUID_0000000c_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEBAPEAUIStream@@XZ; _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::operator->(void)
0x1800496eb  mov     r8, rax
0x1800496ee  mov     rcx, [rax]
0x1800496f1  mov     rax, [rcx+48h]
0x1800496f5  mov     rdx, rbx
0x1800496f8  mov     rcx, r8
0x1800496fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049700  mov     rcx, rbx; bstrString
0x180049703  call    cs:__imp_SysFreeString
0x180049709  mov     rbx, [rsp+930h+String1]
0x18004970e  mov     rcx, rbx; bstrString
0x180049711  call    cs:__imp_SysFreeString
0x180049717  add     edi, r12d
0x18004971a  mov     ebx, [rsi+40h]
0x18004971d  cmp     edi, ebx
0x18004971f  jb      loc_180049650
0x180049725  xor     edx, edx; Val
0x180049727  mov     r8d, 800h; Size
0x18004972d  lea     rcx, [rbp+830h+var_850]; void *
0x180049731  call    memset_0
0x180049736  lea     rdi, [rbp+830h+var_850]
0x18004973a  mov     r14d, r13d
0x18004973d  test    ebx, ebx
0x18004973f  jz      loc_180049C6C
0x180049745  test    r14d, r14d
0x180049748  jnz     loc_1800498A6
0x18004974e  mov     [rdi], r12b
0x180049751  mov     dword ptr [rsp+930h+bstrString], r13d
0x180049756  lea     rbx, [rsi+48h]
0x18004975a  mov     rcx, rbx
0x18004975d  call    ??C?$_com_ptr_t@V?$_com_IIID@UIStream@@$1?_GUID_0000000c_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEBAPEAUIStream@@XZ; _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::operator->(void)
0x180049762  mov     r8, rax
0x180049765  mov     rcx, [rax]
0x180049768  mov     rax, [rcx+50h]
0x18004976c  lea     rdx, [rsp+930h+bstrString]
0x180049771  mov     rcx, r8
0x180049774  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049779  mov     al, byte ptr [rsp+930h+bstrString]
0x18004977d  mov     [rdi+1], al
0x180049780  mov     [rsp+930h+var_8B8], r13
0x180049785  mov     rcx, rbx
0x180049788  call    ??C?$_com_ptr_t@V?$_com_IIID@UIStream@@$1?_GUID_0000000c_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEBAPEAUIStream@@XZ; _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::operator->(void)
0x18004978d  mov     r8, rax
0x180049790  mov     rcx, [rax]
0x180049793  mov     rax, [rcx+40h]
0x180049797  lea     rdx, [rsp+930h+var_8B8]
0x18004979c  mov     rcx, r8
0x18004979f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800497a4  mov     rdx, [rsp+930h+var_8B8]; unsigned __int16 *
0x1800497a9  lea     rcx, [rsp+930h+pExceptionObject]; this
0x1800497ae  call    ??0_bstr_t@@QEAA@PEAG_N@Z; _bstr_t::_bstr_t(ushort *,bool)
0x1800497b3  nop
0x1800497b4  lea     rcx, [rsp+930h+pExceptionObject]
0x1800497b9  call    ??B_bstr_t@@QEBAPEADXZ; _bstr_t::operator char *(void)
0x1800497be  mov     r8, rax; char *
0x1800497c1  lea     rcx, [rdi+4]; char *
0x1800497c5  lea     edx, [r14+17h]; unsigned __int64
0x1800497c9  call    ?StringCbCopyA@@YAJPEAD_KPEBD@Z; StringCbCopyA(char *,unsigned __int64,char const *)
0x1800497ce  mov     word ptr [rdi+1Eh], 0AA55h
0x1800497d4  mov     ecx, r13d
0x1800497d7  xorps   xmm1, xmm1
0x1800497da  movsxd  rax, ecx
0x1800497dd  movdqu  xmm0, xmmword ptr [rdi+rax*2]
0x1800497e2  paddw   xmm0, xmm1
0x1800497e6  movdqa  xmm1, xmm0
0x1800497ea  add     ecx, 8
0x1800497ed  cmp     ecx, 10h
0x1800497f0  jb      short loc_1800497DA
0x1800497f2  psrldq  xmm0, 8
0x1800497f7  paddw   xmm1, xmm0
0x1800497fb  movdqa  xmm0, xmm1
0x1800497ff  psrldq  xmm0, 4
0x180049804  paddw   xmm1, xmm0
0x180049808  movdqa  xmm0, xmm1
0x18004980c  psrldq  xmm0, 2
0x180049811  paddw   xmm1, xmm0
0x180049815  movd    eax, xmm1
0x180049819  neg     ax
0x18004981c  mov     [rdi+1Ch], ax
0x180049820  mov     byte ptr [rdi+20h], 88h
0x180049824  mov     [rsp+930h+var_8D8], r13d
0x180049829  mov     rcx, rbx
0x18004982c  call    ??C?$_com_ptr_t@V?$_com_IIID@UIStream@@$1?_GUID_0000000c_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEBAPEAUIStream@@XZ; _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::operator->(void)
0x180049831  mov     rcx, rax
0x180049834  mov     rdx, [rax]
0x180049837  mov     rax, [rdx+60h]
0x18004983b  lea     rdx, [rsp+930h+var_8D8]
0x180049840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049845  mov     edx, [rsp+930h+var_8D8]
0x180049849  mov     [rdi+21h], dl
0x18004984c  mov     [rdi+22h], r13w
0x180049851  test    dl, dl
0x180049853  jnz     short loc_180049882
0x180049855  mov     dword ptr [rsp+930h+var_900], r13d
0x18004985a  mov     rcx, rbx
0x18004985d  call    ??C?$_com_ptr_t@V?$_com_IIID@UIStream@@$1?_GUID_0000000c_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEBAPEAUIStream@@XZ; _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::operator->(void)
0x180049862  mov     r8, rax
0x180049865  mov     rcx, [rax]
0x180049868  mov     rax, [rcx+70h]
0x18004986c  lea     rdx, [rsp+930h+var_900]
0x180049871  mov     rcx, r8
0x180049874  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049879  mov     eax, dword ptr [rsp+930h+var_900]
0x18004987d  shr     eax, 9
0x180049880  jmp     short loc_180049886
0x180049882  movzx   eax, r12w
0x180049886  mov     [rdi+26h], ax
0x18004988a  mov     eax, [rsi+1ACh]
0x180049890  mov     [rdi+28h], eax
0x180049893  add     rdi, 40h ; '@'
0x180049897  lea     rcx, [rsp+930h+pExceptionObject]; this
0x18004989c  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800498a1  jmp     loc_180049C5F
0x1800498a6  jle     loc_180049C5F
0x1800498ac  cmp     r14d, r12d
0x1800498af  jz      loc_18004997A
0x1800498b5  lea     ecx, [r14-1]
0x1800498b9  test    ecx, ecx
0x1800498bb  js      loc_180049AF0
0x1800498c1  movsxd  rax, ecx
0x1800498c4  mov     rbx, [rsi+rax*8+48h]
0x1800498c9  test    rbx, rbx
0x1800498cc  jnz     short loc_1800498D3
0x1800498ce  sub     ecx, r12d
0x1800498d1  jmp     short loc_1800498B9
0x1800498d3  mov     [rsp+930h+bstrString], r13
0x1800498d8  mov     [rsp+930h+var_900], r13
0x1800498dd  movsxd  rax, r14d
0x1800498e0  add     rax, 9
0x1800498e4  lea     rcx, [rsi+rax*8]
0x1800498e8  call    ??C?$_com_ptr_t@V?$_com_IIID@UIStream@@$1?_GUID_0000000c_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEBAPEAUIStream@@XZ; _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::operator->(void)
0x1800498ed  mov     rcx, rax
0x1800498f0  mov     rdx, [rax]
0x1800498f3  mov     rax, [rdx+40h]
0x1800498f7  lea     rdx, [rsp+930h+bstrString]
0x1800498fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049901  mov     rax, [rbx]
0x180049904  lea     rdx, [rsp+930h+var_900]
0x180049909  mov     rcx, rbx
0x18004990c  mov     rax, [rax+40h]
0x180049910  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049915  mov     r9, [rsp+930h+bstrString]
0x18004991a  test    r9, r9
0x18004991d  jz      short loc_18004994C
0x18004991f  mov     rcx, [rsp+930h+var_900]
0x180049924  test    rcx, rcx
0x180049927  jz      short loc_180049956
0x180049929  mov     rax, r9
0x18004992c  sub     rcx, r9
0x18004992f  movzx   r8d, word ptr [rax]
0x180049933  movzx   edx, word ptr [rax+rcx]
0x180049937  sub     r8d, edx
0x18004993a  jnz     short loc_180049944
0x18004993c  add     rax, 2
0x180049940  test    edx, edx
0x180049942  jnz     short loc_18004992F
0x180049944  test    r8d, r8d
0x180049947  setnz   bl
0x18004994a  jmp     short loc_180049959
0x18004994c  mov     bl, r13b
0x18004994f  cmp     [rsp+930h+var_900], r13
0x180049954  jz      short loc_180049959
0x180049956  mov     bl, r12b
0x180049959  mov     rcx, r9; bstrString
0x18004995c  call    cs:__imp_SysFreeString
0x180049962  mov     [rsp+930h+bstrString], r13
0x180049967  mov     rcx, [rsp+930h+var_900]; bstrString
0x18004996c  call    cs:__imp_SysFreeString
0x180049972  test    bl, bl
0x180049974  jz      loc_180049AF0
0x18004997a  lea     ebx, [r14+1]
0x18004997e  mov     eax, 1
0x180049983  cmp     ebx, [rsi+40h]
0x180049986  jnb     loc_180049A59
0x18004998c  movsxd  rax, ebx
0x18004998f  lea     r15, [rsi+rax*8]
0x180049993  cmp     [r15+48h], r13
0x180049997  jz      loc_180049A4A
0x18004999d  mov     [rsp+930h+bstrString], r13
0x1800499a2  mov     [rsp+930h+var_900], r13
0x1800499a7  movsxd  rax, r14d
0x1800499aa  add     rax, 9
0x1800499ae  lea     rcx, [rsi+rax*8]
0x1800499b2  call    ??C?$_com_ptr_t@V?$_com_IIID@UIStream@@$1?_GUID_0000000c_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEBAPEAUIStream@@XZ; _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::operator->(void)
0x1800499b7  mov     rcx, rax
0x1800499ba  mov     rdx, [rax]
0x1800499bd  mov     rax, [rdx+40h]
0x1800499c1  lea     rdx, [rsp+930h+bstrString]
0x1800499c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800499cb  lea     rcx, [r15+48h]
0x1800499cf  call    ??C?$_com_ptr_t@V?$_com_IIID@UIStream@@$1?_GUID_0000000c_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEBAPEAUIStream@@XZ; _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::operator->(void)
0x1800499d4  mov     r8, rax
0x1800499d7  mov     rcx, [rax]
0x1800499da  mov     rax, [rcx+40h]
0x1800499de  lea     rdx, [rsp+930h+var_900]
0x1800499e3  mov     rcx, r8
0x1800499e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800499eb  mov     r9, [rsp+930h+bstrString]
0x1800499f0  test    r9, r9
0x1800499f3  jz      short loc_180049A1F
0x1800499f5  mov     rcx, [rsp+930h+var_900]
0x1800499fa  test    rcx, rcx
0x1800499fd  jz      short loc_180049A56
0x1800499ff  mov     rax, r9
  ... truncated ...
```
