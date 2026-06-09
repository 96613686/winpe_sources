# CIssuanceLicense::CreateSelfIssuedLicenseAndIL(ushort * *,ushort * *)

- ea: `0x180009f08`
- end: `0x18000a8e5`
- name: `?CreateSelfIssuedLicenseAndIL@CIssuanceLicense@@QEAAJPEAPEAG0@Z`
- size: `2525`
- prototype: `__int64 __fastcall(CIssuanceLicense *__hidden this, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180016bb0`

## callees

- `0x180001284`
- `0x180001290`
- `0x180004654`
- `0x180009794`
- `0x180009bc4`
- `0x180009f08`
- `0x18000dd1c`
- `0x1800127e0`
- `0x180015438`
- `0x180017358`
- `0x18001f020`
- `0x18004bfb4`
- `0x18004e57c`
- `0x18005bd72`
- `0x18005bdc0`

## import_xrefs

- `msvcrt!wcsstr` at `0x18000a2a5`
- `msvcrt!wcsstr` at `0x18000a2da`
- `msvcrt!wcsstr` at `0x18000a2a5`
- `msvcrt!wcsstr` at `0x18000a2da`

## string_xrefs

- `0x180009f5d`: `<XrML version="1.2" xmlns="" purpose="Content-License"><BODY type="LICENSE" version="3.0">%s%s%s<ISSUER>%s</ISSUER><ISSUEDPRINCIPALS>%s</ISSUEDPRINCIPALS>%s<WORK>%s<RIGHTSGROUP name="Main-Rights"><RIGHTSLIST><RIGHT name = "OWNER"><ACCESS>%s</ACCESS></RIGHT></RIGHTSLIST></RIGHTSGROUP></WORK>%s%s</BODY>`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall CIssuanceLicense::CreateSelfIssuedLicenseAndIL(
        CIssuanceLicense *this,
        unsigned __int16 **a2,
        unsigned __int16 **a3)
{
  wchar_t *v5; // rsi
  unsigned __int16 *v6; // rax
  const wchar_t *v7; // rcx
  __int64 v8; // r8
  unsigned __int16 *v9; // r12
  signed int IssuanceLicenseData; // ebx
  unsigned __int16 *v11; // rdi
  unsigned __int16 *v12; // r13
  __int64 v13; // rax
  struct CKeyBlob *v14; // r15
  _WORD *v15; // rax
  __int64 v16; // rdx
  unsigned __int64 v17; // rcx
  signed __int64 v18; // rbx
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // rax
  unsigned __int64 v21; // rcx
  unsigned __int16 *v22; // rax
  void *v23; // r15
  wchar_t *v24; // rax
  wchar_t *v25; // r13
  unsigned __int16 *v26; // r8
  __int64 v27; // rax
  unsigned __int64 v28; // r15
  unsigned __int16 *v29; // rax
  unsigned __int16 *v30; // r11
  __int64 v31; // rax
  int v32; // r11d
  unsigned int v33; // r11d
  __int64 v34; // rax
  CIssuanceLicense *v35; // rcx
  unsigned int v36; // edx
  int v37; // r13d
  __int64 v38; // r8
  int v39; // ecx
  int v40; // r15d
  unsigned __int8 *v41; // rax
  const struct _DRM_CRYPTO_VERSION_PARAMETERS *v42; // rbx
  unsigned int v43; // r13d
  __int64 v44; // r15
  __int64 v45; // rcx
  __int64 v46; // rax
  unsigned __int64 v47; // r15
  unsigned __int16 *v48; // rax
  CIssuanceLicense *v49; // rcx
  __int64 v50; // r15
  int v51; // edx
  __int64 v52; // rcx
  unsigned __int64 v53; // rbx
  unsigned __int16 *v54; // rax
  const unsigned __int16 *v55; // r10
  __int64 v56; // r8
  const unsigned __int16 *v57; // rcx
  const unsigned __int16 *v58; // r9
  unsigned __int16 *v60; // [rsp+20h] [rbp-488h]
  unsigned __int16 *v61; // [rsp+70h] [rbp-438h]
  void *Block; // [rsp+78h] [rbp-430h] BYREF
  unsigned __int16 *v63; // [rsp+80h] [rbp-428h]
  unsigned int v64[2]; // [rsp+88h] [rbp-420h] BYREF
  int v65; // [rsp+90h] [rbp-418h]
  unsigned __int16 *v66; // [rsp+98h] [rbp-410h] BYREF
  unsigned __int16 *v67; // [rsp+A0h] [rbp-408h]
  unsigned __int8 *v68; // [rsp+A8h] [rbp-400h]
  unsigned int v69; // [rsp+B0h] [rbp-3F8h]
  int v70; // [rsp+B4h] [rbp-3F4h]
  int v71; // [rsp+B8h] [rbp-3F0h]
  __int64 v72; // [rsp+C0h] [rbp-3E8h]
  __int64 v73; // [rsp+C8h] [rbp-3E0h]
  __int64 v74; // [rsp+D0h] [rbp-3D8h]
  wchar_t *v75; // [rsp+D8h] [rbp-3D0h]
  __int64 v76; // [rsp+E0h] [rbp-3C8h]
  unsigned __int16 **v77; // [rsp+E8h] [rbp-3C0h]
  __int64 v78; // [rsp+F0h] [rbp-3B8h]
  unsigned __int16 v79[8]; // [rsp+100h] [rbp-3A8h] BYREF
  __int128 v80; // [rsp+110h] [rbp-398h]
  __int128 v81; // [rsp+120h] [rbp-388h]
  __int128 v82; // [rsp+130h] [rbp-378h]
  __int128 v83; // [rsp+140h] [rbp-368h]
  __int128 v84; // [rsp+150h] [rbp-358h]
  __int128 v85; // [rsp+160h] [rbp-348h]
  __int128 v86; // [rsp+170h] [rbp-338h]
  __int128 v87; // [rsp+180h] [rbp-328h]
  __int128 v88; // [rsp+190h] [rbp-318h]
  __int128 v89; // [rsp+1A0h] [rbp-308h]
  __int128 v90; // [rsp+1B0h] [rbp-2F8h]
  __int128 v91; // [rsp+1C0h] [rbp-2E8h]
  __int128 v92; // [rsp+1D0h] [rbp-2D8h]
  __int128 v93; // [rsp+1E0h] [rbp-2C8h]
  __int64 v94; // [rsp+1F0h] [rbp-2B8h]
  unsigned __int16 v95[304]; // [rsp+200h] [rbp-2A8h] BYREF

  v78 = -2;
  v77 = a2;
  v5 = 0;
  v67 = 0;
  v6 = v95;
  v7 = L"<XrML version=\"1.2\" xmlns=\"\" purpose=\"Content-License\"><BODY type=\"LICENSE\" version=\"3.0\">%s%s%s<ISSUER"
        ">%s</ISSUER><ISSUEDPRINCIPALS>%s</ISSUEDPRINCIPALS>%s<WORK>%s<RIGHTSGROUP name=\"Main-Rights\"><RIGHTSLIST><RIGH"
        "T name = \"OWNER\"><ACCESS>%s</ACCESS></RIGHT></RIGHTSLIST></RIGHTSGROUP></WORK>%s%s</BODY>";
  v8 = 4;
  do
  {
    *(_OWORD *)v6 = *(_OWORD *)v7;
    *((_OWORD *)v6 + 1) = *((_OWORD *)v7 + 1);
    *((_OWORD *)v6 + 2) = *((_OWORD *)v7 + 2);
    *((_OWORD *)v6 + 3) = *((_OWORD *)v7 + 3);
    *((_OWORD *)v6 + 4) = *((_OWORD *)v7 + 4);
    *((_OWORD *)v6 + 5) = *((_OWORD *)v7 + 5);
    *((_OWORD *)v6 + 6) = *((_OWORD *)v7 + 6);
    *((_OWORD *)v6 + 7) = *((_OWORD *)v7 + 7);
    v6 += 64;
    v7 += 64;
    --v8;
  }
  while ( v8 );
  *(_OWORD *)v6 = *(_OWORD *)v7;
  *((_OWORD *)v6 + 1) = *((_OWORD *)v7 + 1);
  *((_OWORD *)v6 + 2) = *((_OWORD *)v7 + 2);
  *((_OWORD *)v6 + 3) = *((_OWORD *)v7 + 3);
  *((_OWORD *)v6 + 4) = *((_OWORD *)v7 + 4);
  *(_OWORD *)(v6 + 39) = *(_OWORD *)(v7 + 39);
  *(_OWORD *)v79 = *(_OWORD *)L"<PRINCIPAL internal-id=\"1\"><ENABLINGBITS type=\"%S\"><VALUE encoding=\"base64\" size=\"%"
                               "d\">%s</VALUE></ENABLINGBITS></PRINCIPAL>";
  v80 = *(_OWORD *)L"AL internal-id=\"1\"><ENABLINGBITS type=\"%S\"><VALUE encoding=\"base64\" size=\"%d\">%s</VALUE></ENABLINGBITS></PRINCIPAL>";
  v81 = *(_OWORD *)L"nal-id=\"1\"><ENABLINGBITS type=\"%S\"><VALUE encoding=\"base64\" size=\"%d\">%s</VALUE></ENABLINGBITS></PRINCIPAL>";
  v82 = *(_OWORD *)L"1\"><ENABLINGBITS type=\"%S\"><VALUE encoding=\"base64\" size=\"%d\">%s</VALUE></ENABLINGBITS></PRINCIPAL>";
  v83 = *(_OWORD *)L"LINGBITS type=\"%S\"><VALUE encoding=\"base64\" size=\"%d\">%s</VALUE></ENABLINGBITS></PRINCIPAL>";
  v84 = *(_OWORD *)L" type=\"%S\"><VALUE encoding=\"base64\" size=\"%d\">%s</VALUE></ENABLINGBITS></PRINCIPAL>";
  v85 = *(_OWORD *)L"S\"><VALUE encoding=\"base64\" size=\"%d\">%s</VALUE></ENABLINGBITS></PRINCIPAL>";
  v86 = *(_OWORD *)L"E encoding=\"base64\" size=\"%d\">%s</VALUE></ENABLINGBITS></PRINCIPAL>";
  v87 = *(_OWORD *)L"ng=\"base64\" size=\"%d\">%s</VALUE></ENABLINGBITS></PRINCIPAL>";
  v88 = *(_OWORD *)L"64\" size=\"%d\">%s</VALUE></ENABLINGBITS></PRINCIPAL>";
  v89 = *(_OWORD *)L"=\"%d\">%s</VALUE></ENABLINGBITS></PRINCIPAL>";
  v90 = *(_OWORD *)L"</VALUE></ENABLINGBITS></PRINCIPAL>";
  v91 = *(_OWORD *)L"</ENABLINGBITS></PRINCIPAL>";
  v92 = *(_OWORD *)L"NGBITS></PRINCIPAL>";
  v93 = *(_OWORD *)L"/PRINCIPAL>";
  v94 = *(_QWORD *)L"AL>";
  v69 = 0;
  v64[1] = 0;
  Block = 0;
  v75 = 0;
  v66 = 0;
  v9 = 0;
  v64[0] = 0;
  v68 = 0;
  if ( !*((_QWORD *)this + 84) )
  {
    IssuanceLicenseData = -2147024809;
    v11 = 0;
LABEL_5:
    v12 = 0;
LABEL_84:
    v23 = Block;
    goto LABEL_85;
  }
  IssuanceLicenseData = CIssuanceLicense::GetIssuanceLicenseData(
                          this,
                          *((_DWORD *)this + 235),
                          *((struct CCLCPubData **)this + 118),
                          a3);
  if ( IssuanceLicenseData < 0 )
  {
    v11 = 0;
    v12 = 0;
    goto LABEL_84;
  }
  v13 = *((_QWORD *)this + 118);
  v14 = *(struct CKeyBlob **)(v13 + 176);
  v15 = *(_WORD **)(v13 + 160);
  if ( !v15 )
  {
    IssuanceLicenseData = -2147024809;
LABEL_80:
    v11 = 0;
    v12 = 0;
    v23 = Block;
    goto LABEL_85;
  }
  v16 = 0x7FFFFFFF;
  do
  {
    if ( !*v15 )
      break;
    ++v15;
    --v16;
  }
  while ( v16 );
  IssuanceLicenseData = v16 == 0 ? 0x80070057 : 0;
  v17 = (0x7FFFFFFF - v16) & -(__int64)(v16 != 0);
  if ( !v16 )
    goto LABEL_80;
  v18 = v17 + 1;
  if ( v17 + 1 < v17 )
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v17);
  v19 = HIDWORD(v18);
  if ( v18 < 0 )
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v19);
  v20 = 2LL * (unsigned int)v18;
  v21 = v19 << 33;
  if ( v21 + v20 < v20 )
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v21);
  if ( v21 + v20 )
  {
    v22 = (unsigned __int16 *)operator new[](saturated_mul(v18, 2u));
    v5 = v22;
    v67 = v22;
    if ( !v22 )
    {
      IssuanceLicenseData = -2147024882;
      v11 = 0;
      v12 = 0;
      v23 = Block;
      goto LABEL_85;
    }
    IssuanceLicenseData = StringCchCopyW(v22, v18, *(const unsigned __int16 **)(*((_QWORD *)this + 118) + 160LL));
    if ( IssuanceLicenseData < 0 )
    {
      v11 = 0;
      v12 = 0;
      v23 = Block;
      goto LABEL_85;
    }
  }
  LODWORD(v67) = *((_DWORD *)this + 218);
  v71 = *((_DWORD *)this + 210);
  v70 = *((_DWORD *)this + 206);
  if ( *((_QWORD *)this + 95) )
  {
    IssuanceLicenseData = CIssuanceLicense::MatchPubKey(this, v14);
    if ( IssuanceLicenseData < 0 )
      goto LABEL_24;
  }
  v24 = wcsstr(v5, L"</PRINCIPAL>");
  if ( !v24 )
  {
    IssuanceLicenseData = -2147168512;
LABEL_24:
    v11 = 0;
LABEL_25:
    v12 = v11;
    goto LABEL_84;
  }
  v5[v24 - v5] = 0;
  v25 = wcsstr(v5, L"<OBJECT");
  v75 = v25;
  v26 = 0;
  if ( !v25 )
  {
    IssuanceLicenseData = -2147168512;
LABEL_28:
    v11 = v26;
    goto LABEL_25;
  }
  v27 = -1;
  do
    v73 = ++v27;
  while ( v5[v27] );
  v28 = (unsigned int)v27 + 19LL;
  v29 = (unsigned __int16 *)operator new[](saturated_mul(v28, 2u));
  v9 = v29;
  v30 = 0;
  if ( !v29 )
  {
    IssuanceLicenseData = -2147024882;
LABEL_33:
    v11 = v30;
    goto LABEL_25;
  }
  IssuanceLicenseData = StringCchCopyW(v29, v28, L"<ISSUER>");
  if ( IssuanceLicenseData < 0 )
    goto LABEL_33;
  IssuanceLicenseData = StringCchCopyW(v9 + 8, v28 - 8, v25);
  if ( IssuanceLicenseData < 0 )
    goto LABEL_33;
  v31 = -1;
  do
    ++v31;
  while ( v25[v31] != (_WORD)v30 );
  IssuanceLicenseData = StringCchCopyW(&v9[(unsigned int)(v31 + 8)], v28 - (unsigned int)(v31 + 8), L"</ISSUER>");
  if ( IssuanceLicenseData < 0 )
  {
    v11 = 0;
    goto LABEL_25;
  }
  v33 = v32 + 9;
  v34 = *((_QWORD *)this + 119);
  v74 = *(_QWORD *)(v34 + 128);
  v35 = (CIssuanceLicense *)*(unsigned int *)(v34 + 136);
  v65 = *(_DWORD *)(v34 + 136);
  if ( (*((_BYTE *)this + 728) & 2) != 0 )
  {
    v36 = *(_DWORD *)(v34 + 152);
    v64[1] = v36;
    v37 = *(_DWORD *)(v34 + 156);
    v38 = *(_QWORD *)(v34 + 160);
    v72 = v38;
    v39 = *((_DWORD *)this + 174);
    if ( !v39 || (v40 = 8194, v39 != 1) )
      v40 = 4098;
    v76 = 2 * v33;
    IssuanceLicenseData = DRMEnableAndEncrypt(
                            (unsigned int)v64,
                            v40,
                            *((_QWORD *)this + 84),
                            *((_DWORD *)this + 170),
                            *((_DWORD *)this + 170),
                            v36,
                            v38,
                            v37,
                            (__int64)v9,
                            2 * v33,
                            0,
                            0,
                            0,
                            (__int64)v64);
    v26 = 0;
    if ( IssuanceLicenseData < 0 )
      goto LABEL_28;
    v41 = (unsigned __int8 *)operator new[](v64[0]);
    v68 = v41;
    if ( !v41 )
    {
      IssuanceLicenseData = -2147024882;
      v11 = 0;
      v12 = 0;
      goto LABEL_84;
    }
    IssuanceLicenseData = DRMEnableAndEncrypt(
                            (unsigned int)v64,
                            v40,
                            *((_QWORD *)this + 84),
                            *((_DWORD *)this + 170),
                            *((_DWORD *)this + 170),
                            v64[1],
                            v72,
                            v37,
                            (__int64)v9,
                            v76,
                            0,
                            0,
                            (__int64)v41,
                            (__int64)v64);
    v26 = 0;
    if ( IssuanceLicenseData < 0 )
      goto LABEL_28;
    IssuanceLicenseData = CDRMCBase::Base64EncodeData(v64[0], v68, &v64[1], &v66);
    if ( IssuanceLicenseData < 0 )
      goto LABEL_24;
    v42 = UDGetCryptoVersion(8 * v37);
    if ( !v42 )
      goto LABEL_49;
    v43 = v69;
  }
  else
  {
    v44 = *(_QWORD *)(v34 + 144);
    IssuanceLicenseData = CIssuanceLicense::CreateEnablingBitsBase64Encodeddata(
                            v35,
                            (struct CKeyBlob *)v44,
                            *((unsigned __int8 **)this + 84),
                            *((_DWORD *)this + 170),
                            v9,
                            v33,
                            &v66,
                            &v64[1]);
    if ( IssuanceLicenseData < 0 )
      goto LABEL_24;
    v42 = UDGetCryptoVersion(*(_DWORD *)(v44 + 12) & 0xFFFFFFF8);
    if ( !v42 )
    {
LABEL_49:
      IssuanceLicenseData = -2147024846;
      goto LABEL_28;
    }
    v43 = v64[1];
  }
  v45 = -1;
  do
    ++v45;
  while ( v66[v45] != (_WORD)v26 );
  v46 = -1;
  do
    ++v46;
  while ( *(_BYTE *)(*((_QWORD *)v42 + 4) + v46) != (_BYTE)v26 );
  v47 = (unsigned int)(v46 + v45 + 135);
  v48 = (unsigned __int16 *)operator new[](saturated_mul(v47, 2u));
  v63 = v48;
  if ( !v48 )
  {
    IssuanceLicenseData = -2147024882;
    v11 = 0;
    goto LABEL_5;
  }
  memset_0(v48, 0, 2 * v47);
  if ( (*((_BYTE *)this + 728) & 2) != 0 )
    v43 = 8 * v64[0];
  LODWORD(v60) = v43;
  v12 = v63;
  IssuanceLicenseData = StringCchPrintfW(v63, v47, v79, *((_QWORD *)v42 + 4), v60, v66);
  if ( IssuanceLicenseData < 0 )
  {
    v11 = 0;
    goto LABEL_84;
  }
  v50 = -1;
  do
    ++v50;
  while ( v63[v50] );
  IssuanceLicenseData = CIssuanceLicense::CreateOwnerLicenseDescriptorXml(v49, (unsigned __int16 **)&Block);
  if ( IssuanceLicenseData < 0 )
  {
    v11 = 0;
    goto LABEL_84;
  }
  v51 = v65 + v50 + (_DWORD)v67 + v71 + v70 + 2 * v73;
  v52 = -1;
  v23 = Block;
  do
    ++v52;
  while ( *((_WORD *)Block + v52) );
  v53 = (unsigned int)(v52 + 479 + v51 + *((_DWORD *)this + 198));
  v54 = (unsigned __int16 *)operator new[](saturated_mul(v53, 2u));
  v61 = v54;
  if ( v54 )
  {
    memset_0(v54, 0, 2 * v53);
    v55 = &Src;
    if ( *((_QWORD *)this + 108) )
      v55 = (const unsigned __int16 *)*((_QWORD *)this + 108);
    v56 = *((_QWORD *)this + 104);
    v57 = &Src;
    if ( *((_QWORD *)this + 102) )
      v57 = (const unsigned __int16 *)*((_QWORD *)this + 102);
    v58 = &Src;
    if ( *((_QWORD *)this + 98) )
      v58 = (const unsigned __int16 *)*((_QWORD *)this + 98);
    v11 = v61;
    IssuanceLicenseData = StringCchPrintfW(
                            v61,
                            v53,
                            v95,
                            v58,
                            &Src,
                            v23,
                            v75,
                            v74,
                            v57,
                            v56,
                            v12,
                            L"<CONDITIONLIST><REFRESH><DISTRIBUTIONPOINT><OBJECT type=\"Revocation\"><ID type=\"ascii-tag\""
                             ">Irrevocable</ID></OBJECT></DISTRIBUTIONPOINT><INTERVALTIME /></REFRESH></CONDITIONLIST>",
                            v55);
    if ( IssuanceLicenseData >= 0 )
    {
      *v77 = v61;
      v11 = 0;
    }
  }
  else
  {
    IssuanceLicenseData = -2147024882;
    v11 = 0;
  }
LABEL_85:
  operator delete(v5);
  operator delete(v23);
  operator delete(v11);
  operator delete(0);
  operator delete(v66);
  operator delete(v12);
  operator delete(v9);
  operator delete(v68);
  return (unsigned int)IssuanceLicenseData;
}

```

## disassembly

```asm
0x180009f08  push    rbx
0x180009f0a  push    rsi
0x180009f0b  push    rdi
0x180009f0c  push    r12
0x180009f0e  push    r13
0x180009f10  push    r14
0x180009f12  push    r15
0x180009f14  sub     rsp, 470h
0x180009f1b  mov     [rsp+4A8h+var_3B8], 0FFFFFFFFFFFFFFFEh
0x180009f27  mov     rax, cs:__security_cookie
0x180009f2e  xor     rax, rsp
0x180009f31  mov     [rsp+4A8h+var_48], rax
0x180009f39  mov     r9, r8; unsigned __int16 **
0x180009f3c  mov     [rsp+4A8h+var_3C0], rdx
0x180009f44  mov     rdi, rcx
0x180009f47  xor     r13d, r13d
0x180009f4a  mov     esi, r13d
0x180009f4d  mov     [rsp+4A8h+var_408], r13
0x180009f55  lea     rax, [rsp+4A8h+var_2A8]
0x180009f5d  lea     rcx, aXrmlVersion12X; "<XrML version=\"1.2\" xmlns=\"\" purpos"...
0x180009f64  mov     edx, 80h
0x180009f69  lea     r8d, [r13+4]
0x180009f6d  movups  xmm0, xmmword ptr [rcx]
0x180009f70  movups  xmmword ptr [rax], xmm0
0x180009f73  movups  xmm1, xmmword ptr [rcx+10h]
0x180009f77  movups  xmmword ptr [rax+10h], xmm1
0x180009f7b  movups  xmm0, xmmword ptr [rcx+20h]
0x180009f7f  movups  xmmword ptr [rax+20h], xmm0
0x180009f83  movups  xmm1, xmmword ptr [rcx+30h]
0x180009f87  movups  xmmword ptr [rax+30h], xmm1
0x180009f8b  movups  xmm0, xmmword ptr [rcx+40h]
0x180009f8f  movups  xmmword ptr [rax+40h], xmm0
0x180009f93  movups  xmm1, xmmword ptr [rcx+50h]
0x180009f97  movups  xmmword ptr [rax+50h], xmm1
0x180009f9b  movups  xmm0, xmmword ptr [rcx+60h]
0x180009f9f  movups  xmmword ptr [rax+60h], xmm0
0x180009fa3  movups  xmm1, xmmword ptr [rcx+70h]
0x180009fa7  movups  xmmword ptr [rax+70h], xmm1
0x180009fab  add     rax, rdx
0x180009fae  add     rcx, rdx
0x180009fb1  sub     r8, 1
0x180009fb5  jnz     short loc_180009F6D
0x180009fb7  movups  xmm0, xmmword ptr [rcx]
0x180009fba  movups  xmmword ptr [rax], xmm0
0x180009fbd  movups  xmm1, xmmword ptr [rcx+10h]
0x180009fc1  movups  xmmword ptr [rax+10h], xmm1
0x180009fc5  movups  xmm0, xmmword ptr [rcx+20h]
0x180009fc9  movups  xmmword ptr [rax+20h], xmm0
0x180009fcd  movups  xmm1, xmmword ptr [rcx+30h]
0x180009fd1  movups  xmmword ptr [rax+30h], xmm1
0x180009fd5  movups  xmm0, xmmword ptr [rcx+40h]
0x180009fd9  movups  xmmword ptr [rax+40h], xmm0
0x180009fdd  movups  xmm1, xmmword ptr [rcx+4Eh]
0x180009fe1  movups  xmmword ptr [rax+4Eh], xmm1
0x180009fe5  movaps  xmm0, xmmword ptr cs:aPrincipalInter; "<PRINCIPAL internal-id=\"1\"><ENABLINGB"...
0x180009fec  movups  xmmword ptr [rsp+4A8h+var_3A8], xmm0
0x180009ff4  movaps  xmm1, xmmword ptr cs:aPrincipalInter+10h; "AL internal-id=\"1\"><ENABLINGBITS type"...
0x180009ffb  movups  [rsp+4A8h+var_398], xmm1
0x18000a003  movaps  xmm0, xmmword ptr cs:aPrincipalInter+20h; "nal-id=\"1\"><ENABLINGBITS type=\"%S\">"...
0x18000a00a  movups  [rsp+4A8h+var_388], xmm0
0x18000a012  movaps  xmm1, xmmword ptr cs:aPrincipalInter+30h; "1\"><ENABLINGBITS type=\"%S\"><VALUE en"...
0x18000a019  movups  [rsp+4A8h+var_378], xmm1
0x18000a021  movaps  xmm0, xmmword ptr cs:aPrincipalInter+40h; "LINGBITS type=\"%S\"><VALUE encoding=\""...
0x18000a028  movups  [rsp+4A8h+var_368], xmm0
0x18000a030  movaps  xmm1, xmmword ptr cs:aPrincipalInter+50h; " type=\"%S\"><VALUE encoding=\"base64\""...
0x18000a037  movups  [rsp+4A8h+var_358], xmm1
0x18000a03f  movaps  xmm0, xmmword ptr cs:aPrincipalInter+60h; "S\"><VALUE encoding=\"base64\" size=\"%"...
0x18000a046  movups  [rsp+4A8h+var_348], xmm0
0x18000a04e  movaps  xmm1, xmmword ptr cs:aPrincipalInter+70h; "E encoding=\"base64\" size=\"%d\">%s</V"...
0x18000a055  movups  [rsp+4A8h+var_338], xmm1
0x18000a05d  movaps  xmm0, xmmword ptr cs:aPrincipalInter+80h; "ng=\"base64\" size=\"%d\">%s</VALUE></E"...
0x18000a064  movups  [rsp+4A8h+var_328], xmm0
0x18000a06c  movaps  xmm1, xmmword ptr cs:aPrincipalInter+90h; "64\" size=\"%d\">%s</VALUE></ENABLINGBI"...
0x18000a073  movups  [rsp+4A8h+var_318], xmm1
0x18000a07b  movaps  xmm0, xmmword ptr cs:aPrincipalInter+0A0h; "=\"%d\">%s</VALUE></ENABLINGBITS></PRIN"...
0x18000a082  movups  [rsp+4A8h+var_308], xmm0
0x18000a08a  movaps  xmm1, xmmword ptr cs:aPrincipalInter+0B0h; "</VALUE></ENABLINGBITS></PRINCIPAL>"
0x18000a091  movups  [rsp+4A8h+var_2F8], xmm1
0x18000a099  movaps  xmm0, xmmword ptr cs:aPrincipalInter+0C0h; "</ENABLINGBITS></PRINCIPAL>"
0x18000a0a0  movups  [rsp+4A8h+var_2E8], xmm0
0x18000a0a8  movaps  xmm1, xmmword ptr cs:aPrincipalInter+0D0h; "NGBITS></PRINCIPAL>"
0x18000a0af  movups  [rsp+4A8h+var_2D8], xmm1
0x18000a0b7  movaps  xmm0, xmmword ptr cs:aPrincipalInter+0E0h; "/PRINCIPAL>"
0x18000a0be  movups  [rsp+4A8h+var_2C8], xmm0
0x18000a0c6  mov     rax, qword ptr cs:aPrincipalInter+0F0h; "AL>"
0x18000a0cd  mov     [rsp+4A8h+var_2B8], rax
0x18000a0d5  mov     eax, r13d
0x18000a0d8  mov     [rsp+4A8h+var_3F8], eax
0x18000a0df  mov     [rsp+4A8h+var_420+4], eax
0x18000a0e6  mov     [rsp+4A8h+Block], r13
0x18000a0eb  mov     [rsp+4A8h+var_438], rax
0x18000a0f0  mov     [rsp+4A8h+var_3D0], rax
0x18000a0f8  mov     [rsp+4A8h+var_410], r13
0x18000a100  mov     r12, r13
0x18000a103  mov     [rsp+4A8h+var_420], r13d
0x18000a10b  mov     [rsp+4A8h+var_400], rax
0x18000a113  cmp     [rdi+2A0h], r13
0x18000a11a  jnz     short loc_18000A12B
0x18000a11c  mov     ebx, 80070057h
0x18000a121  mov     edi, eax
0x18000a123  mov     r13, rax
0x18000a126  jmp     loc_18000A860
0x18000a12b  mov     r8, [rdi+3B0h]; struct CCLCPubData *
0x18000a132  mov     edx, [rdi+3ACh]; unsigned int
0x18000a138  mov     rcx, rdi; this
0x18000a13b  call    ?GetIssuanceLicenseData@CIssuanceLicense@@QEAAJKPEAVCCLCPubData@@PEAPEAG@Z; CIssuanceLicense::GetIssuanceLicenseData(ulong,CCLCPubData *,ushort * *)
0x18000a140  mov     ebx, eax
0x18000a142  test    eax, eax
0x18000a144  js      loc_18000A85A
0x18000a14a  mov     rax, [rdi+3B0h]
0x18000a151  mov     r15, [rax+0B0h]
0x18000a158  mov     rax, [rax+0A0h]
0x18000a15f  test    rax, rax
0x18000a162  jz      loc_18000A80F
0x18000a168  mov     r8d, 7FFFFFFFh
0x18000a16e  mov     edx, r8d
0x18000a171  cmp     [rax], r13w
0x18000a175  jz      short loc_18000A181
0x18000a177  add     rax, 2
0x18000a17b  sub     rdx, 1
0x18000a17f  jnz     short loc_18000A171
0x18000a181  mov     rax, rdx
0x18000a184  neg     rax
0x18000a187  sbb     ecx, ecx
0x18000a189  not     ecx
0x18000a18b  mov     ebx, 80070057h
0x18000a190  and     ebx, ecx
0x18000a192  mov     rax, rdx
0x18000a195  sub     r8, rdx
0x18000a198  neg     rax
0x18000a19b  sbb     rcx, rcx
0x18000a19e  and     rcx, r8
0x18000a1a1  test    rdx, rdx
0x18000a1a4  jz      loc_18000A814
0x18000a1aa  lea     rbx, [rcx+1]
0x18000a1ae  cmp     rbx, rcx
0x18000a1b1  jb      loc_18000A8D3
0x18000a1b7  mov     rcx, rbx
0x18000a1ba  shr     rcx, 20h
0x18000a1be  mov     rax, rcx
0x18000a1c1  shr     rax, 1Fh
0x18000a1c5  test    eax, eax
0x18000a1c7  jnz     loc_18000A8D9
0x18000a1cd  mov     eax, ebx
0x18000a1cf  add     rax, rax
0x18000a1d2  shl     rcx, 21h
0x18000a1d6  lea     rdx, [rcx+rax]
0x18000a1da  cmp     rdx, rax
0x18000a1dd  jb      loc_18000A8DE
0x18000a1e3  mov     r14, 0FFFFFFFFFFFFFFFFh
0x18000a1ea  test    rdx, rdx
0x18000a1ed  jz      short loc_18000A25A
0x18000a1ef  lea     eax, [r14+3]
0x18000a1f3  mul     rbx
0x18000a1f6  cmovb   rax, r14
0x18000a1fa  mov     rcx, rax; unsigned __int64
0x18000a1fd  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000a202  mov     rsi, rax
0x18000a205  mov     [rsp+4A8h+var_408], rax
0x18000a20d  test    rax, rax
0x18000a210  jnz     short loc_18000A229
0x18000a212  mov     ebx, 8007000Eh
0x18000a217  mov     rdi, [rsp+4A8h+var_438]
0x18000a21c  mov     r13, rdi
0x18000a21f  mov     r15, [rsp+4A8h+Block]
0x18000a224  jmp     loc_18000A865
0x18000a229  mov     r8, [rdi+3B0h]
0x18000a230  mov     r8, [r8+0A0h]; unsigned __int16 *
0x18000a237  mov     rdx, rbx; unsigned __int64
0x18000a23a  mov     rcx, rax; unsigned __int16 *
0x18000a23d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000a242  mov     ebx, eax
0x18000a244  test    eax, eax
0x18000a246  jns     short loc_18000A25A
0x18000a248  mov     rdi, [rsp+4A8h+var_438]
0x18000a24d  mov     r13, rdi
0x18000a250  mov     r15, [rsp+4A8h+Block]
0x18000a255  jmp     loc_18000A865
0x18000a25a  mov     eax, [rdi+368h]
0x18000a260  mov     dword ptr [rsp+4A8h+var_408], eax
0x18000a267  mov     eax, [rdi+348h]
0x18000a26d  mov     [rsp+4A8h+var_3F0], eax
0x18000a274  mov     eax, [rdi+338h]
0x18000a27a  mov     [rsp+4A8h+var_3F4], eax
0x18000a281  cmp     [rdi+2F8h], r13
0x18000a288  jz      short loc_18000A29B
0x18000a28a  mov     rdx, r15; struct CKeyBlob *
0x18000a28d  mov     rcx, rdi; this
0x18000a290  call    ?MatchPubKey@CIssuanceLicense@@AEAAJPEAVCKeyBlob@@@Z; CIssuanceLicense::MatchPubKey(CKeyBlob *)
0x18000a295  mov     ebx, eax
0x18000a297  test    eax, eax
0x18000a299  js      short loc_18000A2B8
0x18000a29b  lea     rdx, aPrincipal_0; "</PRINCIPAL>"
0x18000a2a2  mov     rcx, rsi; Str
0x18000a2a5  call    cs:__imp_wcsstr
0x18000a2ab  mov     rcx, rax
0x18000a2ae  test    rax, rax
0x18000a2b1  jnz     short loc_18000A2C5
0x18000a2b3  mov     ebx, 8004CF00h
0x18000a2b8  mov     rdi, [rsp+4A8h+var_438]
0x18000a2bd  mov     r13, rdi
0x18000a2c0  jmp     loc_18000A860
0x18000a2c5  sub     rcx, rsi
0x18000a2c8  sar     rcx, 1
0x18000a2cb  mov     [rsi+rcx*2], r13w
0x18000a2d0  lea     rdx, aObject_0; "<OBJECT"
0x18000a2d7  mov     rcx, rsi; Str
0x18000a2da  call    cs:__imp_wcsstr
0x18000a2e0  mov     r13, rax
0x18000a2e3  mov     [rsp+4A8h+var_3D0], rax
0x18000a2eb  xor     r8d, r8d
0x18000a2ee  test    rax, rax
0x18000a2f1  jnz     short loc_18000A2FD
0x18000a2f3  mov     ebx, 8004CF00h
0x18000a2f8  mov     rdi, r8
0x18000a2fb  jmp     short loc_18000A2BD
0x18000a2fd  mov     rax, r14
0x18000a300  inc     rax
0x18000a303  mov     [rsp+4A8h+var_3E0], rax
0x18000a30b  cmp     [rsi+rax*2], r8w
0x18000a310  jnz     short loc_18000A300
0x18000a312  mov     r15d, eax
0x18000a315  add     r15, 13h
0x18000a319  mov     eax, 2
0x18000a31e  mul     r15
0x18000a321  cmovb   rax, r14
0x18000a325  mov     rcx, rax; unsigned __int64
0x18000a328  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000a32d  mov     r12, rax
0x18000a330  xor     r11d, r11d
0x18000a333  test    rax, rax
0x18000a336  jnz     short loc_18000A345
0x18000a338  mov     ebx, 8007000Eh
0x18000a33d  mov     rdi, r11
0x18000a340  jmp     loc_18000A2BD
0x18000a345  lea     r8, aIssuer_0; "<ISSUER>"
0x18000a34c  mov     rdx, r15; unsigned __int64
0x18000a34f  mov     rcx, r12; unsigned __int16 *
0x18000a352  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000a357  mov     ebx, eax
0x18000a359  test    eax, eax
0x18000a35b  js      short loc_18000A33D
0x18000a35d  lea     rdx, [r15-8]; unsigned __int64
0x18000a361  lea     rcx, [r12+10h]; unsigned __int16 *
0x18000a366  mov     r8, r13; unsigned __int16 *
0x18000a369  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000a36e  mov     ebx, eax
0x18000a370  test    eax, eax
0x18000a372  js      short loc_18000A33D
0x18000a374  mov     rax, r14
0x18000a377  inc     rax
0x18000a37a  cmp     [r13+rax*2+0], r11w
0x18000a380  jnz     short loc_18000A377
0x18000a382  lea     r11d, [rax+8]
0x18000a386  mov     eax, r11d
0x18000a389  sub     r15, rax
0x18000a38c  lea     rcx, [r12+r11*2]; unsigned __int16 *
0x18000a390  lea     r8, aIssuer_1; "</ISSUER>"
0x18000a397  mov     rdx, r15; unsigned __int64
0x18000a39a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000a39f  mov     ebx, eax
0x18000a3a1  xor     r10d, r10d
0x18000a3a4  test    eax, eax
0x18000a3a6  js      loc_18000A852
0x18000a3ac  add     r11d, 9
0x18000a3b0  mov     rax, [rdi+3B8h]
0x18000a3b7  mov     rcx, [rax+80h]
0x18000a3be  mov     [rsp+4A8h+var_3D8], rcx
0x18000a3c6  mov     ecx, [rax+88h]; this
0x18000a3cc  mov     [rsp+4A8h+var_418], ecx
0x18000a3d3  test    byte ptr [rdi+2D8h], 2
0x18000a3da  jz      loc_18000A57A
0x18000a3e0  mov     edx, [rax+98h]
0x18000a3e6  mov     [rsp+4A8h+var_420+4], edx
0x18000a3ed  mov     r13d, [rax+9Ch]
0x18000a3f4  mov     r8, [rax+0A0h]
0x18000a3fb  mov     [rsp+4A8h+var_3E8], r8
0x18000a403  mov     ecx, [rdi+2B8h]
0x18000a409  test    ecx, ecx
0x18000a40b  jz      short loc_18000A418
0x18000a40d  cmp     ecx, 1
0x18000a410  mov     r15d, 2002h
0x18000a416  jz      short loc_18000A41E
0x18000a418  mov     r15d, 1002h
0x18000a41e  lea     eax, [r11+r11]
0x18000a422  mov     [rsp+4A8h+var_3C8], rax
0x18000a42a  mov     r9d, [rdi+2A8h]
0x18000a431  lea     rcx, [rsp+4A8h+var_420]
0x18000a439  mov     [rsp+4A8h+var_440], rcx
0x18000a43e  mov     [rsp+4A8h+var_448], r10
0x18000a443  mov     dword ptr [rsp+4A8h+var_450], r10d
0x18000a448  mov     [rsp+4A8h+var_458], r10
0x18000a44d  mov     dword ptr [rsp+4A8h+var_460], eax
0x18000a451  mov     [rsp+4A8h+var_468], r12
0x18000a456  mov     dword ptr [rsp+4A8h+var_470], r13d
0x18000a45b  mov     [rsp+4A8h+var_478], r8
0x18000a460  mov     [rsp+4A8h+var_480], edx
0x18000a464  mov     dword ptr [rsp+4A8h+var_488], r9d
0x18000a469  mov     r8, [rdi+2A0h]
0x18000a470  mov     edx, r15d
  ... truncated ...
```
