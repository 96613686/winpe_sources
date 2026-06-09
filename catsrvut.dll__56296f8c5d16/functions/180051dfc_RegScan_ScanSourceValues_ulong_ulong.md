# RegScan::ScanSourceValues(ulong,ulong)

- ea: `0x180051dfc`
- end: `0x18005248a`
- name: `?ScanSourceValues@RegScan@@AEAAJKK@Z`
- size: `1678`
- prototype: `__int64 __fastcall(RegScan *__hidden this, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800514a0`

## callees

- `0x180005944`
- `0x180014ec8`
- `0x180051dfc`
- `0x180052734`
- `0x18005583a`
- `0x180055880`
- `0x180055940`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800521aa`
- `msvcrt!_wcsicmp` at `0x180052294`
- `msvcrt!_wcsicmp` at `0x1800521aa`
- `msvcrt!_wcsicmp` at `0x180052294`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052017`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052445`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052017`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052445`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180051f02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800523eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180051f02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800523eb`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180052171`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180052171`

## string_xrefs

- `0x180051e72`: `com\complus\src\comcat\regscan\regscan.cpp`
- `0x180051eb9`: `com\complus\src\comcat\regscan\regscan.cpp`
- `0x180051f89`: `com\complus\src\comcat\regscan\regscan.cpp`
- `0x180051fdb`: `com\complus\src\comcat\regscan\regscan.cpp`
- `0x180052073`: `com\complus\src\comcat\regscan\regscan.cpp`
- `0x18005221a`: `com\complus\src\comcat\regscan\regscan.cpp`
- `0x180052278`: `com\complus\src\comcat\regscan\regscan.cpp`
- `0x1800522de`: `com\complus\src\comcat\regscan\regscan.cpp`
- `0x180052350`: `com\complus\src\comcat\regscan\regscan.cpp`
- `0x1800523c1`: `com\complus\src\comcat\regscan\regscan.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
LSTATUS __fastcall RegScan::ScanSourceValues(RegScan *this, DWORD a2, unsigned int a3)
{
  unsigned __int64 v3; // r12
  DWORD v4; // r14d
  LSTATUS result; // eax
  unsigned int v7; // r15d
  _QWORD *v8; // rax
  _QWORD *v9; // r14
  unsigned int v10; // esi
  unsigned int v11; // edi
  __int64 v12; // rax
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // rcx
  unsigned __int64 v15; // rcx
  void *v16; // rsp
  void *v17; // rsp
  WCHAR *v18; // rdi
  unsigned int v19; // eax
  __int64 v20; // rcx
  unsigned __int64 v21; // rax
  unsigned __int64 v22; // rcx
  unsigned __int64 v23; // rcx
  void *v24; // rsp
  void *v25; // rsp
  WCHAR *lpData; // rsi
  DWORD v27; // r13d
  __int64 v28; // r8
  int v29; // eax
  int v30; // edx
  unsigned int v31; // r14d
  unsigned int i; // esi
  int v33; // eax
  __int64 v34; // rax
  RegScan *v35; // rcx
  __int64 v36; // rsi
  unsigned __int64 v37; // r14
  unsigned __int16 *v38; // rax
  unsigned __int16 *v39; // rdi
  int v40; // r14d
  WCHAR ValueName[2]; // [rsp+40h] [rbp+0h] BYREF
  __int16 v42; // [rsp+44h] [rbp+4h]
  int v43; // [rsp+48h] [rbp+8h]
  const unsigned __int16 *v44; // [rsp+50h] [rbp+10h]
  __int64 v45; // [rsp+58h] [rbp+18h]
  __int64 v46; // [rsp+60h] [rbp+20h]
  int v47; // [rsp+68h] [rbp+28h]
  int v48; // [rsp+6Ch] [rbp+2Ch]
  unsigned int v49; // [rsp+70h] [rbp+30h]
  DWORD Type; // [rsp+74h] [rbp+34h] BYREF
  DWORD v51; // [rsp+78h] [rbp+38h]
  DWORD cbData; // [rsp+7Ch] [rbp+3Ch] BYREF
  DWORD cchValueName; // [rsp+80h] [rbp+40h] BYREF
  wchar_t *String2; // [rsp+88h] [rbp+48h]
  unsigned __int64 v55; // [rsp+90h] [rbp+50h]
  WCHAR *v56; // [rsp+98h] [rbp+58h]

  v3 = a3;
  v49 = a3;
  v4 = a2;
  v51 = a2;
  if ( !*((_QWORD *)this + 5) )
  {
    *(_DWORD *)ValueName = 0;
    v42 = 21;
    v43 = -1073605930;
    v44 = L"m_hkeySource";
    v45 = 0;
    v46 = 0;
    v48 = 1;
    v47 = 1;
    CError::WriteToLog((CError *)ValueName, L"com\\complus\\src\\comcat\\regscan\\regscan.cpp", 0x6A1u, L"m_hkeySource");
  }
  if ( (unsigned int)v3 < *((_DWORD *)this + 6) )
  {
    *(_DWORD *)ValueName = 0;
    v42 = 21;
    v43 = -1073605930;
    v44 = L"i_cValues >= m_cValues";
    v45 = 0;
    v46 = 0;
    v48 = 1;
    v47 = 1;
    CError::WriteToLog(
      (CError *)ValueName,
      L"com\\complus\\src\\comcat\\regscan\\regscan.cpp",
      0x6A5u,
      L"i_cValues >= m_cValues");
  }
  if ( (unsigned int)v3 >= *(_DWORD *)(*((_QWORD *)this + 12) + 124LL) )
    return -2147024892;
  v7 = *((_DWORD *)this + 6);
  Type = v7;
  if ( (unsigned int)v3 > v7 )
  {
    v8 = CoTaskMemAlloc(saturated_mul(v3, 0x10u));
    v9 = v8;
    if ( !v8 )
      return -2147024882;
    memset_0(v8, 0, 16 * v3);
    if ( *((_QWORD *)this + 2) )
    {
      v10 = 0;
      if ( *((_DWORD *)this + 6) )
      {
        do
        {
          if ( !*((_QWORD *)this + 2) )
          {
            *(_DWORD *)ValueName = 0;
            v42 = 21;
            v43 = -1073605930;
            v44 = L"m_aValueName";
            v45 = 0;
            v46 = 0;
            v48 = 1;
            v47 = 1;
            CError::WriteToLog(
              (CError *)ValueName,
              L"com\\complus\\src\\comcat\\regscan\\regscan.cpp",
              0x6C5u,
              L"m_aValueName");
          }
          if ( !*(_QWORD *)(*((_QWORD *)this + 2) + 16LL * v10) )
          {
            *(_DWORD *)ValueName = 0;
            v42 = 21;
            v43 = -1073605930;
            v44 = L"m_aValueName[dwVN].m_wszValueName";
            v45 = 0;
            v46 = 0;
            v48 = 1;
            v47 = 1;
            CError::WriteToLog(
              (CError *)ValueName,
              L"com\\complus\\src\\comcat\\regscan\\regscan.cpp",
              0x6C6u,
              L"m_aValueName[dwVN].m_wszValueName");
          }
          v9[2 * v10] = *(_QWORD *)(*((_QWORD *)this + 2) + 16LL * v10);
          ++v10;
        }
        while ( v10 < *((_DWORD *)this + 6) );
        v7 = Type;
        LODWORD(v3) = v49;
      }
    }
    *((_DWORD *)this + 6) = v3;
    CoTaskMemFree(*((LPVOID *)this + 2));
    *((_QWORD *)this + 2) = v9;
    v4 = v51;
  }
  if ( *((_QWORD *)this + 2) )
  {
    v11 = 0;
    if ( v7 )
    {
      do
      {
        if ( !*((_QWORD *)this + 2) )
        {
          *(_DWORD *)ValueName = 0;
          v42 = 21;
          v43 = -1073605930;
          v44 = L"m_aValueName";
          v45 = 0;
          v46 = 0;
          v48 = 1;
          v47 = 1;
          CError::WriteToLog(
            (CError *)ValueName,
            L"com\\complus\\src\\comcat\\regscan\\regscan.cpp",
            0x6D9u,
            L"m_aValueName");
        }
        *(_DWORD *)(*((_QWORD *)this + 2) + 16LL * v11++ + 8) = 0;
      }
      while ( v11 < v7 );
      LODWORD(v3) = v49;
      v4 = v51;
    }
  }
  v12 = v4 + 1;
  if ( (unsigned int)v12 < v4 )
    return -2147024362;
  v55 = v4 + 1;
  v13 = 2 * v12;
  if ( v13 > 0xFFFFFFFF )
    return -2147024362;
  v14 = (unsigned int)v13 + 15LL;
  if ( v14 <= (unsigned int)v13 )
    v14 = 0xFFFFFFFFFFFFFF0LL;
  v15 = v14 & 0xFFFFFFFFFFFFFFF0uLL;
  v16 = alloca(v15);
  v17 = alloca(v15);
  v18 = ValueName;
  String2 = ValueName;
  v19 = *((_DWORD *)this + 15);
  v20 = v19 + 1;
  if ( (unsigned int)v20 < v19 )
    return -2147024362;
  v21 = (unsigned int)v20;
  v22 = v20 + 15;
  if ( v22 <= v21 )
    v22 = 0xFFFFFFFFFFFFFF0LL;
  v23 = v22 & 0xFFFFFFFFFFFFFFF0uLL;
  v24 = alloca(v23);
  v25 = alloca(v23);
  lpData = ValueName;
  v56 = ValueName;
  v49 = v7;
  v27 = 0;
LABEL_32:
  if ( v27 >= (unsigned int)v3 )
    return 0;
  cchValueName = v4;
  cbData = *((_DWORD *)this + 15);
  Type = 0;
  result = RegEnumValueW(*((HKEY *)this + 5), v27, v18, &cchValueName, 0, &Type, (LPBYTE)lpData, &cbData);
  if ( result == 259 )
    return 0;
  v28 = 0;
  if ( result )
  {
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  if ( !*v18 && Type == 1 && lpData )
  {
    v29 = _wcsicmp(L"PSFactoryBuffer", lpData);
    v30 = 2;
    v28 = 0;
    if ( v29 )
      v30 = 0;
    *((_DWORD *)this + 22) |= v30;
  }
  v31 = 0;
  if ( v7 )
    v31 = v27 % v7;
  for ( i = 0; i < v7; ++i )
  {
    if ( !*((_QWORD *)this + 2) )
    {
      *(_DWORD *)ValueName = 0;
      v42 = 21;
      v43 = -1073605930;
      v44 = L"m_aValueName";
      v45 = 0;
      v46 = 0;
      v48 = 1;
      v47 = 1;
      CError::WriteToLog(
        (CError *)ValueName,
        L"com\\complus\\src\\comcat\\regscan\\regscan.cpp",
        0x729u,
        L"m_aValueName");
    }
    if ( !*(_QWORD *)(*((_QWORD *)this + 2) + 16LL * v31) )
    {
      *(_DWORD *)ValueName = 0;
      v42 = 21;
      v43 = -1073605930;
      v44 = L"m_aValueName[dwRealValueIndex].m_wszValueName";
      v45 = 0;
      v46 = 0;
      v48 = 1;
      v47 = 1;
      CError::WriteToLog(
        (CError *)ValueName,
        L"com\\complus\\src\\comcat\\regscan\\regscan.cpp",
        0x72Au,
        L"m_aValueName[dwRealValueIndex].m_wszValueName");
    }
    v33 = _wcsicmp(*(const wchar_t **)(*((_QWORD *)this + 2) + 16LL * v31), String2);
    v28 = 0;
    if ( !v33 )
    {
      *(_DWORD *)(*((_QWORD *)this + 2) + 16LL * v31 + 8) = 0;
LABEL_64:
      ++v27;
      v18 = String2;
      lpData = v56;
      v4 = v51;
      goto LABEL_32;
    }
    if ( !v7 )
    {
      *(_DWORD *)ValueName = 0;
      v42 = 21;
      v43 = -1073605930;
      v44 = L"cOldValues";
      v45 = 0;
      v46 = 0;
      v48 = 1;
      v47 = 1;
      CError::WriteToLog((CError *)ValueName, L"com\\complus\\src\\comcat\\regscan\\regscan.cpp", 0x737u, L"cOldValues");
      v28 = 0;
    }
    v31 = (v31 + 1) % v7;
  }
  if ( !*((_QWORD *)this + 4) )
  {
    *(_DWORD *)ValueName = 0;
    v42 = 21;
    v43 = -1073605930;
    v44 = L"m_wszKeyName";
    v45 = 0;
    v46 = 0;
    v48 = 1;
    v47 = 1;
    CError::WriteToLog((CError *)ValueName, L"com\\complus\\src\\comcat\\regscan\\regscan.cpp", 0x745u, L"m_wszKeyName");
    v28 = 0;
  }
  v34 = *((_QWORD *)this + 8);
  if ( v34 )
  {
    *(_DWORD *)(v34 + 72) = 1;
    v35 = *(RegScan **)(v34 + 64);
    if ( v35 )
      RegScan::SetScanIsRequired(v35, 1);
  }
  v36 = 2LL * v49;
  if ( *(_QWORD *)(*((_QWORD *)this + 2) + 16LL * v49) != v28 )
  {
    *(_DWORD *)ValueName = v28;
    v42 = 21;
    v43 = -1073605930;
    v44 = L"NULL == m_aValueName[dwNextIndex].m_wszValueName";
    v45 = v28;
    v46 = v28;
    v48 = 1;
    v47 = 1;
    CError::WriteToLog(
      (CError *)ValueName,
      L"com\\complus\\src\\comcat\\regscan\\regscan.cpp",
      0x752u,
      L"NULL == m_aValueName[dwNextIndex].m_wszValueName");
  }
  v37 = v55;
  v38 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v55, 2u));
  v39 = v38;
  if ( !v38 )
    return -2147024882;
  *v38 = 0;
  v40 = StringCchCatW(v38, v37, String2);
  if ( v40 >= 0 )
  {
    *(_QWORD *)(*((_QWORD *)this + 2) + 8 * v36) = v39;
    *(_DWORD *)(*((_QWORD *)this + 2) + 8 * v36 + 8) = 1;
    ++v49;
    goto LABEL_64;
  }
  CoTaskMemFree(v39);
  return v40;
}

```

## disassembly

```asm
0x180051dfc  push    rbp
0x180051dfe  push    rbx
0x180051dff  push    rsi
0x180051e00  push    rdi
0x180051e01  push    r12
0x180051e03  push    r13
0x180051e05  push    r14
0x180051e07  push    r15
0x180051e09  sub     rsp, 0B8h
0x180051e10  lea     rbp, [rsp+40h]
0x180051e15  mov     rax, cs:__security_cookie
0x180051e1c  xor     rax, rbp
0x180051e1f  mov     [rbp+0B0h+var_50], rax
0x180051e23  mov     r12d, r8d
0x180051e26  mov     [rbp+0B0h+var_80], r12d
0x180051e2a  mov     r14d, edx
0x180051e2d  mov     [rbp+0B0h+var_78], edx
0x180051e30  mov     rbx, rcx
0x180051e33  mov     eax, 15h
0x180051e38  lea     esi, [rax-14h]
0x180051e3b  xor     r13d, r13d
0x180051e3e  cmp     [rcx+28h], r13
0x180051e42  jnz     short loc_180051E85
0x180051e44  mov     dword ptr [rbp+0B0h+ValueName], r13d
0x180051e48  mov     [rbp+0B0h+var_AC], ax
0x180051e4c  mov     [rbp+0B0h+var_A8], 0C00212D6h
0x180051e53  lea     r9, aMHkeysource; "m_hkeySource"
0x180051e5a  mov     [rbp+0B0h+var_A0], r9
0x180051e5e  mov     [rbp+0B0h+var_98], r13
0x180051e62  mov     [rbp+0B0h+var_90], r13
0x180051e66  mov     [rbp+0B0h+var_84], esi
0x180051e69  mov     [rbp+0B0h+var_88], esi
0x180051e6c  mov     r8d, 6A1h; unsigned int
0x180051e72  lea     rdx, aComComplusSrcC; "com\\complus\\src\\comcat\\regscan\\reg"...
0x180051e79  lea     rcx, [rbp+0B0h+ValueName]; this
0x180051e7d  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x180051e82  lea     eax, [rsi+14h]
0x180051e85  cmp     r12d, [rbx+18h]
0x180051e89  jnb     short loc_180051EC9
0x180051e8b  mov     dword ptr [rbp+0B0h+ValueName], r13d
0x180051e8f  mov     [rbp+0B0h+var_AC], ax
0x180051e93  mov     [rbp+0B0h+var_A8], 0C00212D6h
0x180051e9a  lea     r9, aICvaluesMCvalu; "i_cValues >= m_cValues"
0x180051ea1  mov     [rbp+0B0h+var_A0], r9
0x180051ea5  mov     [rbp+0B0h+var_98], r13
0x180051ea9  mov     [rbp+0B0h+var_90], r13
0x180051ead  mov     [rbp+0B0h+var_84], esi
0x180051eb0  mov     [rbp+0B0h+var_88], esi
0x180051eb3  mov     r8d, 6A5h; unsigned int
0x180051eb9  lea     rdx, aComComplusSrcC; "com\\complus\\src\\comcat\\regscan\\reg"...
0x180051ec0  lea     rcx, [rbp+0B0h+ValueName]; this
0x180051ec4  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x180051ec9  mov     rax, [rbx+60h]
0x180051ecd  cmp     r12d, [rax+7Ch]
0x180051ed1  jb      short loc_180051EDD
0x180051ed3  mov     eax, 80070004h
0x180051ed8  jmp     loc_18005246D
0x180051edd  mov     r15d, [rbx+18h]
0x180051ee1  mov     [rbp+0B0h+Type], r15d
0x180051ee5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180051ee9  cmp     r12d, r15d
0x180051eec  jbe     loc_180052026
0x180051ef2  mov     rdi, r12
0x180051ef5  lea     eax, [rcx+11h]
0x180051ef8  mul     r12
0x180051efb  cmovb   rax, rcx
0x180051eff  mov     rcx, rax; cb
0x180051f02  call    cs:__imp_CoTaskMemAlloc
0x180051f08  mov     r14, rax
0x180051f0b  test    rax, rax
0x180051f0e  jz      loc_180052451
0x180051f14  shl     rdi, 4
0x180051f18  mov     r8, rdi; Size
0x180051f1b  xor     edx, edx; Val
0x180051f1d  mov     rcx, rax; void *
0x180051f20  call    memset_0
0x180051f25  cmp     [rbx+10h], r13
0x180051f29  jz      loc_18005200F
0x180051f2f  mov     esi, r13d
0x180051f32  cmp     [rbx+18h], r13d
0x180051f36  jbe     loc_18005200A
0x180051f3c  lea     r15, aMAvaluenameDwv; "m_aValueName[dwVN].m_wszValueName"
0x180051f43  mov     r12d, 15h
0x180051f49  cmp     [rbx+10h], r13
0x180051f4d  jnz     short loc_180051F99
0x180051f4f  mov     dword ptr [rbp+0B0h+ValueName], r13d
0x180051f53  mov     [rbp+0B0h+var_AC], r12w
0x180051f58  mov     [rbp+0B0h+var_A8], 0C00212D6h
0x180051f5f  lea     rax, aMAvaluename; "m_aValueName"
0x180051f66  mov     [rbp+0B0h+var_A0], rax
0x180051f6a  mov     [rbp+0B0h+var_98], r13
0x180051f6e  mov     [rbp+0B0h+var_90], r13
0x180051f72  mov     [rbp+0B0h+var_84], 1
0x180051f79  mov     [rbp+0B0h+var_88], 1
0x180051f80  mov     r9, rax; unsigned __int16 *
0x180051f83  mov     r8d, 6C5h; unsigned int
0x180051f89  lea     rdx, aComComplusSrcC; "com\\complus\\src\\comcat\\regscan\\reg"...
0x180051f90  lea     rcx, [rbp+0B0h+ValueName]; this
0x180051f94  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x180051f99  mov     edi, esi
0x180051f9b  add     rdi, rdi
0x180051f9e  mov     rax, [rbx+10h]
0x180051fa2  cmp     [rax+rdi*8], r13
0x180051fa6  jnz     short loc_180051FEB
0x180051fa8  mov     dword ptr [rbp+0B0h+ValueName], r13d
0x180051fac  mov     [rbp+0B0h+var_AC], r12w
0x180051fb1  mov     [rbp+0B0h+var_A8], 0C00212D6h
0x180051fb8  mov     [rbp+0B0h+var_A0], r15
0x180051fbc  mov     [rbp+0B0h+var_98], r13
0x180051fc0  mov     [rbp+0B0h+var_90], r13
0x180051fc4  mov     [rbp+0B0h+var_84], 1
0x180051fcb  mov     [rbp+0B0h+var_88], 1
0x180051fd2  mov     r9, r15; unsigned __int16 *
0x180051fd5  mov     r8d, 6C6h; unsigned int
0x180051fdb  lea     rdx, aComComplusSrcC; "com\\complus\\src\\comcat\\regscan\\reg"...
0x180051fe2  lea     rcx, [rbp+0B0h+ValueName]; this
0x180051fe6  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x180051feb  mov     rax, [rbx+10h]
0x180051fef  mov     rcx, [rax+rdi*8]
0x180051ff3  mov     [r14+rdi*8], rcx
0x180051ff7  inc     esi
0x180051ff9  cmp     esi, [rbx+18h]
0x180051ffc  jb      loc_180051F49
0x180052002  mov     r15d, [rbp+0B0h+Type]
0x180052006  mov     r12d, [rbp+0B0h+var_80]
0x18005200a  mov     esi, 1
0x18005200f  mov     [rbx+18h], r12d
0x180052013  mov     rcx, [rbx+10h]; pv
0x180052017  call    cs:__imp_CoTaskMemFree
0x18005201d  nop
0x18005201e  mov     [rbx+10h], r14
0x180052022  mov     r14d, [rbp+0B0h+var_78]
0x180052026  xor     r8d, r8d
0x180052029  cmp     [rbx+10h], r8
0x18005202d  jz      short loc_1800520A3
0x18005202f  mov     edi, r8d
0x180052032  test    r15d, r15d
0x180052035  jz      short loc_1800520A3
0x180052037  lea     r14d, [r8+15h]
0x18005203b  lea     r12, aMAvaluename; "m_aValueName"
0x180052042  cmp     [rbx+10h], r8
0x180052046  jnz     short loc_180052086
0x180052048  mov     dword ptr [rbp+0B0h+ValueName], r8d
0x18005204c  mov     [rbp+0B0h+var_AC], r14w
0x180052051  mov     [rbp+0B0h+var_A8], 0C00212D6h
0x180052058  mov     [rbp+0B0h+var_A0], r12
0x18005205c  mov     [rbp+0B0h+var_98], r8
0x180052060  mov     [rbp+0B0h+var_90], r8
0x180052064  mov     [rbp+0B0h+var_84], esi
0x180052067  mov     [rbp+0B0h+var_88], esi
0x18005206a  mov     r9, r12; unsigned __int16 *
0x18005206d  mov     r8d, 6D9h; unsigned int
0x180052073  lea     rdx, aComComplusSrcC; "com\\complus\\src\\comcat\\regscan\\reg"...
0x18005207a  lea     rcx, [rbp+0B0h+ValueName]; this
0x18005207e  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x180052083  xor     r8d, r8d
0x180052086  mov     ecx, edi
0x180052088  add     rcx, rcx
0x18005208b  mov     rax, [rbx+10h]
0x18005208f  mov     [rax+rcx*8+8], r8d
0x180052094  add     edi, esi
0x180052096  cmp     edi, r15d
0x180052099  jb      short loc_180052042
0x18005209b  mov     r12d, [rbp+0B0h+var_80]
0x18005209f  mov     r14d, [rbp+0B0h+var_78]
0x1800520a3  lea     eax, [r14+1]
0x1800520a7  cmp     eax, r14d
0x1800520aa  jb      loc_180052468
0x1800520b0  mov     [rbp+0B0h+var_60], rax
0x1800520b4  add     rax, rax
0x1800520b7  mov     ecx, 0FFFFFFFFh
0x1800520bc  cmp     rax, rcx
0x1800520bf  ja      loc_180052468
0x1800520c5  mov     eax, eax
0x1800520c7  lea     rcx, [rax+0Fh]
0x1800520cb  mov     rdx, 0FFFFFFFFFFFFFF0h
0x1800520d5  cmp     rcx, rax
0x1800520d8  ja      short loc_1800520DD
0x1800520da  mov     rcx, rdx
0x1800520dd  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800520e1  mov     rax, rcx
0x1800520e4  call    _alloca_probe
0x1800520e9  sub     rsp, rcx
0x1800520ec  lea     rdi, [rsp+0F0h+ValueName]
0x1800520f1  mov     [rbp+0B0h+String2], rdi
0x1800520f5  mov     eax, [rbx+3Ch]
0x1800520f8  lea     ecx, [rax+1]
0x1800520fb  cmp     ecx, eax
0x1800520fd  jb      loc_180052468
0x180052103  mov     eax, ecx
0x180052105  add     rcx, 0Fh
0x180052109  cmp     rcx, rax
0x18005210c  ja      short loc_180052111
0x18005210e  mov     rcx, rdx
0x180052111  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180052115  mov     rax, rcx
0x180052118  call    _alloca_probe
0x18005211d  sub     rsp, rcx
0x180052120  lea     rsi, [rsp+0F0h+ValueName]
0x180052125  mov     [rbp+0B0h+var_58], rsi
0x180052129  mov     [rbp+0B0h+var_80], r15d
0x18005212d  mov     r13d, r8d
0x180052130  cmp     r13d, r12d
0x180052133  jnb     loc_180052464
0x180052139  mov     [rbp+0B0h+cchValueName], r14d
0x18005213d  mov     eax, [rbx+3Ch]
0x180052140  mov     [rbp+0B0h+cbData], eax
0x180052143  mov     [rbp+0B0h+Type], r8d
0x180052147  lea     rax, [rbp+0B0h+cbData]
0x18005214b  mov     [rsp+0F0h+lpcbData], rax; lpcbData
0x180052150  mov     [rsp+0F0h+lpData], rsi; lpData
0x180052155  lea     rax, [rbp+0B0h+Type]
0x180052159  mov     [rsp+0F0h+lpType], rax; lpType
0x18005215e  mov     [rsp+0F0h+lpReserved], r8; lpReserved
0x180052163  lea     r9, [rbp+0B0h+cchValueName]; lpcchValueName
0x180052167  mov     r8, rdi; lpValueName
0x18005216a  mov     edx, r13d; dwIndex
0x18005216d  mov     rcx, [rbx+28h]; hKey
0x180052171  call    cs:__imp_RegEnumValueW
0x180052177  cmp     eax, 103h
0x18005217c  jz      loc_180052464
0x180052182  xor     r8d, r8d
0x180052185  test    eax, eax
0x180052187  jnz     loc_180052458
0x18005218d  cmp     r8w, [rdi]
0x180052191  lea     edi, [rax+1]
0x180052194  jnz     short loc_1800521BF
0x180052196  cmp     [rbp+0B0h+Type], edi
0x180052199  jnz     short loc_1800521BF
0x18005219b  test    rsi, rsi
0x18005219e  jz      short loc_1800521BF
0x1800521a0  mov     rdx, rsi; String2
0x1800521a3  lea     rcx, aPsfactorybuffe; "PSFactoryBuffer"
0x1800521aa  call    cs:__imp__wcsicmp
0x1800521b0  lea     edx, [rdi+1]
0x1800521b3  xor     r8d, r8d
0x1800521b6  test    eax, eax
0x1800521b8  cmovnz  edx, r8d
0x1800521bc  or      [rbx+58h], edx
0x1800521bf  mov     r14d, r8d
0x1800521c2  test    r15d, r15d
0x1800521c5  jz      short loc_1800521D2
0x1800521c7  xor     edx, edx
0x1800521c9  mov     eax, r13d
0x1800521cc  div     r15d
0x1800521cf  mov     r14d, edx
0x1800521d2  mov     esi, r8d
0x1800521d5  cmp     esi, r15d
0x1800521d8  jnb     loc_180052312
0x1800521de  cmp     [rbx+10h], r8
0x1800521e2  jnz     short loc_18005222D
0x1800521e4  mov     dword ptr [rbp+0B0h+ValueName], r8d
0x1800521e8  mov     eax, 15h
0x1800521ed  mov     [rbp+0B0h+var_AC], ax
0x1800521f1  mov     [rbp+0B0h+var_A8], 0C00212D6h
0x1800521f8  lea     rax, aMAvaluename; "m_aValueName"
0x1800521ff  mov     [rbp+0B0h+var_A0], rax
0x180052203  mov     [rbp+0B0h+var_98], r8
0x180052207  mov     [rbp+0B0h+var_90], r8
0x18005220b  mov     [rbp+0B0h+var_84], edi
0x18005220e  mov     [rbp+0B0h+var_88], edi
0x180052211  mov     r9, rax; unsigned __int16 *
0x180052214  mov     r8d, 729h; unsigned int
0x18005221a  lea     rdx, aComComplusSrcC; "com\\complus\\src\\comcat\\regscan\\reg"...
0x180052221  lea     rcx, [rbp+0B0h+ValueName]; this
0x180052225  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x18005222a  xor     r8d, r8d
0x18005222d  mov     edi, r14d
0x180052230  add     rdi, rdi
0x180052233  mov     rax, [rbx+10h]
0x180052237  cmp     [rax+rdi*8], r8
0x18005223b  jnz     short loc_180052288
0x18005223d  mov     dword ptr [rbp+0B0h+ValueName], r8d
0x180052241  mov     eax, 15h
0x180052246  mov     [rbp+0B0h+var_AC], ax
0x18005224a  mov     [rbp+0B0h+var_A8], 0C00212D6h
0x180052251  lea     rcx, aMAvaluenameDwr; "m_aValueName[dwRealValueIndex].m_wszVal"...
0x180052258  mov     [rbp+0B0h+var_A0], rcx
0x18005225c  mov     [rbp+0B0h+var_98], r8
0x180052260  mov     [rbp+0B0h+var_90], r8
0x180052264  mov     eax, 1
0x180052269  mov     [rbp+0B0h+var_84], eax
0x18005226c  mov     [rbp+0B0h+var_88], eax
0x18005226f  mov     r9, rcx; unsigned __int16 *
0x180052272  mov     r8d, 72Ah; unsigned int
0x180052278  lea     rdx, aComComplusSrcC; "com\\complus\\src\\comcat\\regscan\\reg"...
0x18005227f  lea     rcx, [rbp+0B0h+ValueName]; this
0x180052283  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x180052288  mov     rcx, [rbx+10h]
0x18005228c  mov     rdx, [rbp+0B0h+String2]; String2
0x180052290  mov     rcx, [rcx+rdi*8]; String1
0x180052294  call    cs:__imp__wcsicmp
0x18005229a  xor     r8d, r8d
0x18005229d  test    eax, eax
0x18005229f  jz      short loc_180052304
0x1800522a1  lea     edi, [r8+1]
0x1800522a5  test    r15d, r15d
0x1800522a8  jnz     short loc_1800522F1
0x1800522aa  mov     dword ptr [rbp+0B0h+ValueName], r8d
0x1800522ae  lea     eax, [rdi+14h]
  ... truncated ...
```
