# RegScan::ScanDestValues(void)

- ea: `0x180050ea0`
- end: `0x180051498`
- name: `?ScanDestValues@RegScan@@AEAAJXZ`
- size: `1528`
- prototype: `__int64 __fastcall(RegScan *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180050b6c`

## callees

- `0x180005944`
- `0x18000717c`
- `0x180007a7c`
- `0x180050adc`
- `0x180050ea0`
- `0x180055822`
- `0x18005583a`
- `0x180055880`
- `0x180055940`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180051138`
- `msvcrt!_wcsicmp` at `0x180051199`
- `msvcrt!_wcsicmp` at `0x1800511aa`
- `msvcrt!_wcsicmp` at `0x1800511f8`
- `msvcrt!_wcsicmp` at `0x180051138`
- `msvcrt!_wcsicmp` at `0x180051199`
- `msvcrt!_wcsicmp` at `0x1800511aa`
- `msvcrt!_wcsicmp` at `0x1800511f8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180051251`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800512d8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180051251`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800512d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051433`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005143d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051447`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051433`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005143d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051447`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180051282`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005131b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800513ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180051282`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005131b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800513ba`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800510b3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800510f3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800510b3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800510f3`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180050fa1`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180050fa1`

## string_xrefs

- `0x180050f0f`: `com\complus\src\comcat\regscan\regscan.cpp`
- `0x180050f55`: `com\complus\src\comcat\regscan\regscan.cpp`
- `0x18005107d`: `com\complus\src\comcat\regscan\regscan.cpp`
- `0x18005141f`: `com\complus\src\comcat\regscan\regscan.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
LSTATUS __fastcall RegScan::ScanDestValues(RegScan *this)
{
  LSTATUS result; // eax
  bool v3; // cc
  DWORD v4; // ecx
  DWORD v5; // eax
  __int64 v6; // rax
  unsigned __int64 v7; // rcx
  unsigned __int64 v8; // rax
  void *v9; // rsp
  DWORD *p_Type; // r14
  __int64 v11; // rax
  void *v12; // rsp
  __int64 i; // rax
  __int64 v14; // rax
  __int64 v15; // rcx
  const WCHAR *v16; // r15
  DWORD v17; // esi
  DWORD v18; // edi
  __int64 v19; // rax
  const wchar_t *v20; // rcx
  int j; // edi
  unsigned __int16 *v22; // r14
  unsigned __int16 *v23; // rsi
  HINSTANCE v24; // rax
  int StringW; // eax
  __int64 v26; // rcx
  unsigned __int64 v27; // rdi
  unsigned __int16 *v28; // rax
  unsigned __int16 *v29; // r12
  int v30; // edi
  HINSTANCE v31; // rax
  int v32; // r8d
  __int64 v33; // rcx
  __int64 v34; // rax
  unsigned int v35; // edi
  unsigned __int16 *v36; // rax
  __int64 v37; // rdx
  __int64 v38; // rax
  __int64 v39; // rcx
  unsigned int v40; // edi
  unsigned __int16 *v41; // rax
  DWORD Type; // [rsp+60h] [rbp+0h] BYREF
  DWORD v43; // [rsp+64h] [rbp+4h] BYREF
  DWORD cbMaxValueLen; // [rsp+68h] [rbp+8h] BYREF
  DWORD v45; // [rsp+6Ch] [rbp+Ch] BYREF
  DWORD cbData; // [rsp+70h] [rbp+10h] BYREF
  int v47; // [rsp+74h] [rbp+14h]
  wchar_t *String2; // [rsp+78h] [rbp+18h] BYREF
  const wchar_t *v49; // [rsp+80h] [rbp+20h]
  const wchar_t *v50; // [rsp+88h] [rbp+28h]
  const wchar_t *v51; // [rsp+90h] [rbp+30h]
  __int64 v52; // [rsp+98h] [rbp+38h]
  int v53; // [rsp+A0h] [rbp+40h]
  int v54; // [rsp+A4h] [rbp+44h]
  int v55; // [rsp+A8h] [rbp+48h] BYREF
  __int16 v56; // [rsp+ACh] [rbp+4Ch]
  int v57; // [rsp+B0h] [rbp+50h]
  const unsigned __int16 *v58; // [rsp+B8h] [rbp+58h]
  __int64 v59; // [rsp+C0h] [rbp+60h]
  __int64 v60; // [rsp+C8h] [rbp+68h]
  int v61; // [rsp+D0h] [rbp+70h]
  int v62; // [rsp+D4h] [rbp+74h]
  DWORD *v63; // [rsp+D8h] [rbp+78h]
  unsigned __int16 v64[8]; // [rsp+E0h] [rbp+80h] BYREF
  wchar_t v65; // [rsp+F0h] [rbp+90h]
  WCHAR Buffer[136]; // [rsp+100h] [rbp+A0h] BYREF
  WCHAR v67[136]; // [rsp+210h] [rbp+1B0h] BYREF

  if ( !*((_QWORD *)this + 6) )
  {
    LODWORD(String2) = 0;
    WORD2(String2) = 21;
    LODWORD(v49) = -1073605930;
    v50 = L"m_hkeyDest";
    v51 = 0;
    v52 = 0;
    v54 = 1;
    v53 = 1;
    CError::WriteToLog((CError *)&String2, L"com\\complus\\src\\comcat\\regscan\\regscan.cpp", 0x36Cu, L"m_hkeyDest");
  }
  if ( !*((_QWORD *)this + 5) )
  {
    LODWORD(String2) = 0;
    WORD2(String2) = 21;
    LODWORD(v49) = -1073605930;
    v50 = L"m_hkeySource";
    v51 = 0;
    v52 = 0;
    v54 = 1;
    v53 = 1;
    CError::WriteToLog((CError *)&String2, L"com\\complus\\src\\comcat\\regscan\\regscan.cpp", 0x36Du, L"m_hkeySource");
  }
  cbMaxValueLen = 0;
  result = RegQueryInfoKeyW(*((HKEY *)this + 6), 0, 0, 0, 0, 0, 0, 0, 0, &cbMaxValueLen, 0, 0);
  v3 = result <= 0;
  if ( !result )
  {
    v4 = cbMaxValueLen + 1;
    cbMaxValueLen = v4;
    v5 = *((_DWORD *)this + 15);
    if ( v5 <= v4 )
      v5 = v4;
    *((_DWORD *)this + 15) = v5;
    v6 = v5 + 1;
    v7 = (unsigned int)v6;
    v8 = v6 + 15;
    if ( v8 <= v7 )
      v8 = 0xFFFFFFFFFFFFFF0LL;
    v9 = alloca(v8 & 0xFFFFFFFFFFFFFFF0uLL);
    p_Type = &Type;
    v63 = &Type;
    v11 = v7 + 15;
    if ( v7 + 15 < v7 )
      v11 = 0xFFFFFFFFFFFFFF0LL;
    v12 = alloca(v11 & 0xFFFFFFFFFFFFFFF0uLL);
    for ( i = 0; ; i = (unsigned int)(v47 + 1) )
    {
      v47 = i;
      if ( (unsigned int)i >= *((_DWORD *)this + 6) )
        return 0;
      v14 = 2 * i;
      v15 = *((_QWORD *)this + 2);
      if ( *(_DWORD *)(v15 + 8 * v14 + 8) )
      {
        v16 = *(const WCHAR **)(v15 + 8 * v14);
        if ( !v16 )
        {
          v55 = 0;
          v56 = 21;
          v57 = -1073605930;
          v58 = L"lpValueName";
          v59 = 0;
          v60 = 0;
          v62 = 1;
          v61 = 1;
          CError::WriteToLog((CError *)&v55, L"com\\complus\\src\\comcat\\regscan\\regscan.cpp", 0x39Fu, L"lpValueName");
        }
        Type = 0;
        cbData = *((_DWORD *)this + 15);
        result = RegQueryValueExW(*((HKEY *)this + 6), v16, 0, &Type, (LPBYTE)&Type, &cbData);
        if ( result )
        {
          if ( result != 2 )
          {
            v3 = result <= 0;
            goto LABEL_6;
          }
          continue;
        }
        v43 = 0;
        v45 = *((_DWORD *)this + 15);
        result = RegQueryValueExW(*((HKEY *)this + 5), v16, 0, &v43, (LPBYTE)p_Type, &v45);
        v3 = result <= 0;
        if ( result )
          goto LABEL_6;
        v17 = Type;
        v18 = v43;
        if ( Type != v43 || cbData != v45 || memcmp_0(p_Type, &Type, v45) )
        {
          if ( v18 == 1 )
          {
            if ( v17 == 1 )
            {
              if ( !_wcsicmp((const wchar_t *)p_Type, (const wchar_t *)&Type) )
                continue;
              v17 = Type;
              v18 = v43;
            }
            if ( v18 == 1 )
            {
              if ( RegScan::IsRegisteredFileName(this, (unsigned __int16 *)p_Type) )
              {
                *((_DWORD *)this + 22) |= 8u;
                continue;
              }
              v17 = Type;
              v18 = v43;
            }
          }
          if ( v17 != 1 )
            break;
          if ( v18 != 1 )
            break;
          if ( (_WORD)Type != 95 )
            break;
          v19 = *((_QWORD *)this + 8);
          if ( !v19 )
            break;
          v20 = *(const wchar_t **)(v19 + 32);
          if ( !v20 || _wcsicmp(v20, L"Interface") || _wcsicmp((const wchar_t *)p_Type, (const wchar_t *)&Type + 1) )
            break;
        }
      }
LABEL_67:
      ;
    }
    String2 = L"HELPDIR";
    v49 = L"TypeLib";
    v50 = L"{45046D60-08CA-11CF-A90F-00AA0062BB4C}";
    v51 = L"{14E469E0-BF61-11CF-8385-8F69D8F1350B}";
    for ( j = 0; j < 4; ++j )
    {
      if ( !_wcsicmp(*((const wchar_t **)this + 4), (&String2)[j]) )
        goto LABEL_67;
    }
    memset_0(Buffer, 0, 0x102u);
    memset_0(v67, 0, 0x102u);
    v22 = 0;
    v23 = 0;
    v24 = COMResModuleInstance();
    StringW = LoadStringW(v24, 0x3B8u, Buffer, 128);
    v26 = -1;
    do
      ++v26;
    while ( *(_WORD *)(*(_QWORD *)(*((_QWORD *)this + 12) + 104LL) + 2 * v26) );
    v27 = (unsigned int)(v26 + StringW);
    v28 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v27, 2u));
    v29 = v28;
    if ( v28 )
    {
      v30 = StringCchPrintfW(v28, v27, Buffer, *(_QWORD *)(*((_QWORD *)this + 12) + 104LL));
      if ( v30 < 0 )
        goto LABEL_65;
      v31 = COMResModuleInstance();
      v32 = LoadStringW(v31, 0x3B9u, v67, 128);
      v33 = -1;
      do
        ++v33;
      while ( v16[v33] );
      v34 = -1;
      do
        ++v34;
      while ( *(_WORD *)(*((_QWORD *)this + 10) + 2 * v34) );
      v35 = v32 + v33 + v34;
      v36 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v35, 2u));
      v22 = v36;
      if ( v36 )
      {
        v30 = StringCchPrintfW(v36, v35, v67, *((_QWORD *)this + 10), v16);
        if ( v30 < 0 )
          goto LABEL_65;
        *(_OWORD *)v64 = *(_OWORD *)L"\r\n%s\r\n%s";
        v65 = aSS_2[8];
        v37 = -1;
        do
          ++v37;
        while ( v64[v37] );
        v38 = -1;
        do
          ++v38;
        while ( v22[v38] );
        v39 = -1;
        do
          ++v39;
        while ( v29[v39] );
        v40 = v39 + v37 + v38;
        v41 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v40, 2u));
        v23 = v41;
        if ( v41 )
        {
          v30 = StringCchPrintfW(v41, v40, v64, v29, v22);
          if ( v30 >= 0 )
          {
            v55 = 0;
            v56 = 22;
            v57 = -2147479190;
            v58 = v23;
            v59 = 0;
            v60 = 0;
            v61 = 0;
            v62 = 1;
            CError::WriteToLog((CError *)&v55, L"com\\complus\\src\\comcat\\regscan\\regscan.cpp", 0x483u, v23);
          }
          goto LABEL_65;
        }
      }
    }
    v30 = -2147024882;
LABEL_65:
    CoTaskMemFree(v23);
    CoTaskMemFree(v29);
    CoTaskMemFree(v22);
    if ( v30 )
      return v30;
    p_Type = v63;
    goto LABEL_67;
  }
LABEL_6:
  if ( !v3 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180050ea0  push    rbp
0x180050ea2  push    rbx
0x180050ea3  push    rsi
0x180050ea4  push    rdi
0x180050ea5  push    r12
0x180050ea7  push    r13
0x180050ea9  push    r14
0x180050eab  push    r15
0x180050ead  sub     rsp, 338h
0x180050eb4  lea     rbp, [rsp+60h]
0x180050eb9  mov     rax, cs:__security_cookie
0x180050ec0  xor     rax, rbp
0x180050ec3  mov     [rbp+310h+var_50], rax
0x180050eca  mov     rbx, rcx
0x180050ecd  mov     edi, 15h
0x180050ed2  lea     r14d, [rdi-14h]
0x180050ed6  xor     r12d, r12d
0x180050ed9  cmp     [rcx+30h], r12
0x180050edd  jnz     short loc_180050F1F
0x180050edf  mov     dword ptr [rbp+310h+String2], r12d
0x180050ee3  mov     word ptr [rbp+310h+String2+4], di
0x180050ee7  mov     dword ptr [rbp+310h+var_2F0], 0C00212D6h
0x180050eee  lea     r9, aMHkeydest; "m_hkeyDest"
0x180050ef5  mov     [rbp+310h+var_2E8], r9
0x180050ef9  mov     [rbp+310h+var_2E0], r12
0x180050efd  mov     [rbp+310h+var_2D8], r12
0x180050f01  mov     [rbp+310h+var_2CC], r14d
0x180050f05  mov     [rbp+310h+var_2D0], r14d
0x180050f09  mov     r8d, 36Ch; unsigned int
0x180050f0f  lea     rdx, aComComplusSrcC; "com\\complus\\src\\comcat\\regscan\\reg"...
0x180050f16  lea     rcx, [rbp+310h+String2]; this
0x180050f1a  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x180050f1f  cmp     [rbx+28h], r12
0x180050f23  jnz     short loc_180050F65
0x180050f25  mov     dword ptr [rbp+310h+String2], r12d
0x180050f29  mov     word ptr [rbp+310h+String2+4], di
0x180050f2d  mov     dword ptr [rbp+310h+var_2F0], 0C00212D6h
0x180050f34  lea     r9, aMHkeysource; "m_hkeySource"
0x180050f3b  mov     [rbp+310h+var_2E8], r9
0x180050f3f  mov     [rbp+310h+var_2E0], r12
0x180050f43  mov     [rbp+310h+var_2D8], r12
0x180050f47  mov     [rbp+310h+var_2CC], r14d
0x180050f4b  mov     [rbp+310h+var_2D0], r14d
0x180050f4f  mov     r8d, 36Dh; unsigned int
0x180050f55  lea     rdx, aComComplusSrcC; "com\\complus\\src\\comcat\\regscan\\reg"...
0x180050f5c  lea     rcx, [rbp+310h+String2]; this
0x180050f60  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x180050f65  mov     [rbp+310h+cbMaxValueLen], r12d
0x180050f69  mov     [rsp+370h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180050f6e  mov     [rsp+370h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x180050f73  lea     rax, [rbp+310h+cbMaxValueLen]
0x180050f77  mov     [rsp+370h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180050f7c  mov     [rsp+370h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x180050f81  mov     [rsp+370h+lpcValues], r12; lpcValues
0x180050f86  mov     [rsp+370h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x180050f8b  mov     [rsp+370h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x180050f90  mov     [rsp+370h+lpcSubKeys], r12; lpcSubKeys
0x180050f95  xor     r9d, r9d; lpReserved
0x180050f98  xor     r8d, r8d; lpcchClass
0x180050f9b  xor     edx, edx; lpClass
0x180050f9d  mov     rcx, [rbx+30h]; hKey
0x180050fa1  call    cs:__imp_RegQueryInfoKeyW
0x180050fa7  test    eax, eax
0x180050fa9  jz      short loc_180050FBE
0x180050fab  jle     loc_180051475
0x180050fb1  movzx   eax, ax
0x180050fb4  or      eax, 80070000h
0x180050fb9  jmp     loc_180051475
0x180050fbe  mov     ecx, [rbp+310h+cbMaxValueLen]
0x180050fc1  add     ecx, r14d
0x180050fc4  mov     [rbp+310h+cbMaxValueLen], ecx
0x180050fc7  mov     eax, [rbx+3Ch]
0x180050fca  cmp     eax, ecx
0x180050fcc  cmovbe  eax, ecx
0x180050fcf  mov     [rbx+3Ch], eax
0x180050fd2  inc     eax
0x180050fd4  mov     ecx, eax
0x180050fd6  add     rax, 0Fh
0x180050fda  mov     rdx, 0FFFFFFFFFFFFFF0h
0x180050fe4  cmp     rax, rcx
0x180050fe7  ja      short loc_180050FEC
0x180050fe9  mov     rax, rdx
0x180050fec  and     rax, 0FFFFFFFFFFFFFFF0h
0x180050ff0  call    _alloca_probe
0x180050ff5  sub     rsp, rax
0x180050ff8  lea     r14, [rsp+370h+Type]
0x180050ffd  mov     [rbp+310h+var_298], r14
0x180051001  lea     rax, [rcx+0Fh]
0x180051005  cmp     rax, rcx
0x180051008  ja      short loc_18005100D
0x18005100a  mov     rax, rdx
0x18005100d  and     rax, 0FFFFFFFFFFFFFFF0h
0x180051011  call    _alloca_probe
0x180051016  sub     rsp, rax
0x180051019  lea     r13, [rsp+370h+Type]
0x18005101e  mov     eax, r12d
0x180051021  lea     rdx, aLpvaluename; "lpValueName"
0x180051028  mov     [rbp+310h+var_2FC], eax
0x18005102b  cmp     eax, [rbx+18h]
0x18005102e  jnb     loc_180051473
0x180051034  add     rax, rax
0x180051037  mov     rcx, [rbx+10h]
0x18005103b  cmp     [rcx+rax*8+8], r12d
0x180051040  jz      loc_180051465
0x180051046  mov     r15, [rcx+rax*8]
0x18005104a  test    r15, r15
0x18005104d  jnz     short loc_18005108D
0x18005104f  mov     [rbp+310h+var_2C8], r12d
0x180051053  mov     [rbp+310h+var_2C4], di
0x180051057  mov     [rbp+310h+var_2C0], 0C00212D6h
0x18005105e  mov     [rbp+310h+var_2B8], rdx
0x180051062  mov     [rbp+310h+var_2B0], r12
0x180051066  mov     [rbp+310h+var_2A8], r12
0x18005106a  lea     eax, [r15+1]
0x18005106e  mov     [rbp+310h+var_29C], eax
0x180051071  mov     [rbp+310h+var_2A0], eax
0x180051074  mov     r9, rdx; unsigned __int16 *
0x180051077  mov     r8d, 39Fh; unsigned int
0x18005107d  lea     rdx, aComComplusSrcC; "com\\complus\\src\\comcat\\regscan\\reg"...
0x180051084  lea     rcx, [rbp+310h+var_2C8]; this
0x180051088  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x18005108d  mov     [rbp+310h+Type], r12d
0x180051091  mov     eax, [rbx+3Ch]
0x180051094  mov     [rbp+310h+cbData], eax
0x180051097  lea     rax, [rbp+310h+cbData]
0x18005109b  mov     [rsp+370h+lpcbMaxSubKeyLen], rax; lpcbData
0x1800510a0  mov     [rsp+370h+lpcSubKeys], r13; lpData
0x1800510a5  lea     r9, [rbp+310h+Type]; lpType
0x1800510a9  xor     r8d, r8d; lpReserved
0x1800510ac  mov     rdx, r15; lpValueName
0x1800510af  mov     rcx, [rbx+30h]; hKey
0x1800510b3  call    cs:__imp_RegQueryValueExW
0x1800510b9  test    eax, eax
0x1800510bb  jz      short loc_1800510CD
0x1800510bd  cmp     eax, 2
0x1800510c0  jz      loc_18005145E
0x1800510c6  test    eax, eax
0x1800510c8  jmp     loc_180050FAB
0x1800510cd  mov     [rbp+310h+var_30C], r12d
0x1800510d1  mov     eax, [rbx+3Ch]
0x1800510d4  mov     [rbp+310h+var_304], eax
0x1800510d7  lea     rax, [rbp+310h+var_304]
0x1800510db  mov     [rsp+370h+lpcbMaxSubKeyLen], rax; lpcbData
0x1800510e0  mov     [rsp+370h+lpcSubKeys], r14; lpData
0x1800510e5  lea     r9, [rbp+310h+var_30C]; lpType
0x1800510e9  xor     r8d, r8d; lpReserved
0x1800510ec  mov     rdx, r15; lpValueName
0x1800510ef  mov     rcx, [rbx+28h]; hKey
0x1800510f3  call    cs:__imp_RegQueryValueExW
0x1800510f9  test    eax, eax
0x1800510fb  jnz     loc_180050FAB
0x180051101  mov     esi, [rbp+310h+Type]
0x180051104  mov     edi, [rbp+310h+var_30C]
0x180051107  cmp     esi, edi
0x180051109  jnz     short loc_180051129
0x18005110b  mov     eax, [rbp+310h+var_304]
0x18005110e  cmp     [rbp+310h+cbData], eax
0x180051111  jnz     short loc_180051129
0x180051113  mov     r8d, eax; Size
0x180051116  mov     rdx, r13; Buf2
0x180051119  mov     rcx, r14; Buf1
0x18005111c  call    memcmp_0
0x180051121  test    eax, eax
0x180051123  jz      loc_180051459
0x180051129  cmp     edi, 1
0x18005112c  jnz     short loc_18005116F
0x18005112e  cmp     esi, edi
0x180051130  jnz     short loc_18005114C
0x180051132  mov     rdx, r13; String2
0x180051135  mov     rcx, r14; String1
0x180051138  call    cs:__imp__wcsicmp
0x18005113e  test    eax, eax
0x180051140  jz      loc_180051459
0x180051146  mov     esi, [rbp+310h+Type]
0x180051149  mov     edi, [rbp+310h+var_30C]
0x18005114c  cmp     edi, 1
0x18005114f  jnz     short loc_18005116F
0x180051151  mov     rdx, r14; unsigned __int16 *
0x180051154  mov     rcx, rbx; this
0x180051157  call    ?IsRegisteredFileName@RegScan@@AEAAHPEAG@Z; RegScan::IsRegisteredFileName(ushort *)
0x18005115c  test    eax, eax
0x18005115e  jz      short loc_180051169
0x180051160  or      dword ptr [rbx+58h], 8
0x180051164  jmp     loc_180051459
0x180051169  mov     esi, [rbp+310h+Type]
0x18005116c  mov     edi, [rbp+310h+var_30C]
0x18005116f  cmp     esi, 1
0x180051172  jnz     short loc_1800511B8
0x180051174  cmp     edi, esi
0x180051176  jnz     short loc_1800511B8
0x180051178  cmp     word ptr [r13+0], 5Fh ; '_'
0x18005117e  jnz     short loc_1800511B8
0x180051180  mov     rax, [rbx+40h]
0x180051184  test    rax, rax
0x180051187  jz      short loc_1800511B8
0x180051189  mov     rcx, [rax+20h]; String1
0x18005118d  test    rcx, rcx
0x180051190  jz      short loc_1800511B8
0x180051192  lea     rdx, aInterface; "Interface"
0x180051199  call    cs:__imp__wcsicmp
0x18005119f  test    eax, eax
0x1800511a1  jnz     short loc_1800511B8
0x1800511a3  lea     rdx, [r13+2]; String2
0x1800511a7  mov     rcx, r14; String1
0x1800511aa  call    cs:__imp__wcsicmp
0x1800511b0  test    eax, eax
0x1800511b2  jz      loc_180051459
0x1800511b8  lea     rax, aHelpdir; "HELPDIR"
0x1800511bf  mov     [rbp+310h+String2], rax
0x1800511c3  lea     rax, aTypelib; "TypeLib"
0x1800511ca  mov     [rbp+310h+var_2F0], rax
0x1800511ce  lea     rax, a45046d6008ca11; "{45046D60-08CA-11CF-A90F-00AA0062BB4C}"
0x1800511d5  mov     [rbp+310h+var_2E8], rax
0x1800511d9  lea     rax, a14e469e0Bf6111; "{14E469E0-BF61-11CF-8385-8F69D8F1350B}"
0x1800511e0  mov     [rbp+310h+var_2E0], rax
0x1800511e4  mov     edi, r12d
0x1800511e7  cmp     edi, 4
0x1800511ea  jge     short loc_18005120A
0x1800511ec  movsxd  rdx, edi
0x1800511ef  mov     rdx, [rbp+rdx*8+310h+String2]; String2
0x1800511f4  mov     rcx, [rbx+20h]; String1
0x1800511f8  call    cs:__imp__wcsicmp
0x1800511fe  test    eax, eax
0x180051200  jz      loc_180051459
0x180051206  inc     edi
0x180051208  jmp     short loc_1800511E7
0x18005120a  mov     edi, 102h
0x18005120f  mov     r8d, edi; Size
0x180051212  xor     edx, edx; Val
0x180051214  lea     rcx, [rbp+310h+Buffer]; void *
0x18005121b  call    memset_0
0x180051220  mov     r8d, edi; Size
0x180051223  xor     edx, edx; Val
0x180051225  lea     rcx, [rbp+310h+var_160]; void *
0x18005122c  call    memset_0
0x180051231  mov     r14, r12
0x180051234  mov     rsi, r12
0x180051237  call    ?COMResModuleInstance@@YAPEAUHINSTANCE__@@XZ; COMResModuleInstance(void)
0x18005123c  mov     rcx, rax; hInstance
0x18005123f  mov     r9d, 80h; cchBufferMax
0x180051245  lea     r8, [rbp+310h+Buffer]; lpBuffer
0x18005124c  mov     edx, 3B8h; uID
0x180051251  call    cs:__imp_LoadStringW
0x180051257  mov     rcx, [rbx+60h]
0x18005125b  mov     rdx, [rcx+68h]
0x18005125f  or      r8, 0FFFFFFFFFFFFFFFFh
0x180051263  mov     rcx, r8
0x180051266  inc     rcx
0x180051269  cmp     [rdx+rcx*2], r12w
0x18005126e  jnz     short loc_180051266
0x180051270  lea     edi, [rcx+rax]
0x180051273  mov     eax, 2
0x180051278  mul     rdi
0x18005127b  cmovb   rax, r8
0x18005127f  mov     rcx, rax; cb
0x180051282  call    cs:__imp_CoTaskMemAlloc
0x180051288  mov     r12, rax
0x18005128b  test    rax, rax
0x18005128e  jnz     short loc_18005129A
0x180051290  mov     edi, 8007000Eh
0x180051295  jmp     loc_180051430
0x18005129a  mov     r9, [rbx+60h]
0x18005129e  mov     r9, [r9+68h]
0x1800512a2  lea     r8, [rbp+310h+Buffer]; unsigned __int16 *
0x1800512a9  mov     rdx, rdi; unsigned __int64
0x1800512ac  mov     rcx, r12; unsigned __int16 *
0x1800512af  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800512b4  mov     edi, eax
0x1800512b6  test    eax, eax
0x1800512b8  js      loc_180051430
0x1800512be  call    ?COMResModuleInstance@@YAPEAUHINSTANCE__@@XZ; COMResModuleInstance(void)
0x1800512c3  mov     rcx, rax; hInstance
0x1800512c6  mov     r9d, 80h; cchBufferMax
0x1800512cc  lea     r8, [rbp+310h+var_160]; lpBuffer
0x1800512d3  mov     edx, 3B9h; uID
0x1800512d8  call    cs:__imp_LoadStringW
0x1800512de  mov     r8d, eax
0x1800512e1  or      r10, 0FFFFFFFFFFFFFFFFh
0x1800512e5  mov     rcx, r10
0x1800512e8  xor     r9d, r9d
0x1800512eb  inc     rcx
0x1800512ee  cmp     [r15+rcx*2], r9w
0x1800512f3  jnz     short loc_1800512EB
0x1800512f5  mov     rdx, [rbx+50h]
0x1800512f9  mov     rax, r10
0x1800512fc  inc     rax
0x1800512ff  cmp     [rdx+rax*2], r9w
0x180051304  jnz     short loc_1800512FC
0x180051306  lea     edi, [rcx+rax]
0x180051309  add     edi, r8d
0x18005130c  mov     eax, 2
0x180051311  mul     rdi
0x180051314  cmovb   rax, r10
0x180051318  mov     rcx, rax; cb
0x18005131b  call    cs:__imp_CoTaskMemAlloc
0x180051321  mov     r14, rax
0x180051324  test    rax, rax
0x180051327  jz      loc_180051290
0x18005132d  mov     [rsp+370h+lpcSubKeys], r15
0x180051332  mov     r9, [rbx+50h]
  ... truncated ...
```
