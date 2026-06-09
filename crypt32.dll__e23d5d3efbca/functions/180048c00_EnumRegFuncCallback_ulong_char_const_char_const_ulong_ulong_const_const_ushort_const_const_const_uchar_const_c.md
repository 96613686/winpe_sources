# EnumRegFuncCallback(ulong,char const *,char const *,ulong,ulong const * const,ushort const * const * const,uchar const * const * const,ulong const * const,void *)

- ea: `0x180048c00`
- end: `0x180049005`
- name: `?EnumRegFuncCallback@@YAHKPEBD0KQEBKQEBQEBGQEBQEBE1PEAX@Z`
- size: `1029`
- prototype: `__int64 __fastcall(DWORD dwEncodingType, CHAR *pszFuncName, LPCSTR pszOID, DWORD cValue, const DWORD *__attribute__((__org_arrdim(0,0))) rgdwValueType, const LPCWSTR *__attribute__((__org_arrdim(0,0))) rgpwszValueName, const BYTE *const *__attribute__((__org_arrdim(0,0))) rgpbValueData, const DWORD *__attribute__((__org_arrdim(0,0))) rgcbValueData, struct _FUNC_SET *pvArg)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180028d60`
- `0x180029e78`
- `0x180046e10`
- `0x180048c00`
- `0x1800969a4`
- `0x1800bec20`
- `0x1800bf564`
- `0x1801150d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048fed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048fed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180118080`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180118080`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180048ff8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180048ff8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180048fc2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180048fc2`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180048dc0`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180048e0a`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180048dc0`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180048e0a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180048d1a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180048d4b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180048ed6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180048d1a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180048d4b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180048ed6`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180048c96`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180048c96`

## pseudocode

```c
__int64 __fastcall EnumRegFuncCallback(
        DWORD dwEncodingType,
        CHAR *pszFuncName,
        LPCSTR pszOID,
        DWORD cValue,
        const DWORD rgdwValueType[],
        const LPCWSTR rgpwszValueName[],
        const BYTE *const rgpbValueData[],
        const DWORD rgcbValueData[],
        struct _FUNC_SET *pvArg)
{
  BOOL v9; // r14d
  __int64 v10; // rbx
  unsigned __int64 v11; // rbp
  unsigned int v13; // edi
  const WCHAR *v14; // r12
  DWORD v15; // eax
  DWORD v16; // r15d
  int v17; // eax
  int v18; // edi
  unsigned int v19; // r14d
  _QWORD *v20; // rdi
  struct _DLL_PROC_ELEMENT *v22; // r15
  DWORD v23; // ecx
  DWORD LastError; // ebx
  DWORD v26; // [rsp+44h] [rbp-194h]
  int v28; // [rsp+4Ch] [rbp-18Ch]
  const BYTE *v29; // [rsp+50h] [rbp-188h]
  const WCHAR *lpString1; // [rsp+58h] [rbp-180h]
  const unsigned __int16 *lpSrc; // [rsp+60h] [rbp-178h]
  CHAR MultiByteStr[272]; // [rsp+80h] [rbp-158h] BYREF

  v9 = 0;
  v10 = -1;
  v11 = (unsigned __int64)pszOID;
  if ( *pszOID == 35 )
  {
    v11 = o_atol_0(pszOID + 1);
    if ( v11 > 0xFFFF )
      return 1;
  }
  else
  {
    v9 = CompareStringA(0x409u, 1u, "DEFAULT", -1, pszOID, -1) == 2;
  }
  v13 = 0;
  lpSrc = 0;
  v14 = 0;
  LOBYTE(v28) = 0;
  while ( 1 )
  {
    v15 = cValue;
    if ( !cValue )
      break;
    --cValue;
    lpString1 = rgpwszValueName[v15 - 1];
    v16 = rgdwValueType[v15 - 1];
    v29 = rgpbValueData[v15 - 1];
    v26 = rgcbValueData[v15 - 1];
    if ( CompareStringW(0x409u, 1u, lpString1, -1, L"Dll", -1) == 2 )
    {
      if ( v16 - 1 > 1 && (!v9 || v16 != 7) )
        return 1;
      lpSrc = (const unsigned __int16 *)v29;
      v13 = v26 >> 1;
    }
    else if ( CompareStringW(0x409u, 1u, lpString1, -1, L"FuncName", -1) == 2 )
    {
      if ( v16 != 1 )
        return 1;
      if ( *(_WORD *)v29 )
        v14 = (const WCHAR *)v29;
    }
    else if ( CompareStringW(0x409u, 1u, lpString1, -1, L"CryptFlags", -1) == 2 && v16 == 4 && v26 >= 4 )
    {
      v28 = *(_DWORD *)v29;
    }
  }
  if ( v13 && *lpSrc )
  {
    if ( v9 )
    {
      AddDefaultDllList(dwEncodingType, pvArg, lpSrc, v13);
      return 1;
    }
    if ( v14 )
    {
      v17 = WideCharToMultiByte(0, 0, v14, -1, 0, 0, 0, 0);
      v18 = v17;
      if ( v17 <= 0 )
        return 1;
      if ( (unsigned int)v17 > 0x104 )
      {
        pszFuncName = (CHAR *)LocalAlloc(0, v17);
        if ( !pszFuncName )
        {
          v23 = 14;
          goto LABEL_51;
        }
      }
      else
      {
        pszFuncName = MultiByteStr;
      }
      WideCharToMultiByte(0, 0, v14, -1, pszFuncName, v18, 0, 0);
    }
    if ( v11 <= 0xFFFF )
    {
      v19 = 0;
    }
    else
    {
      do
        ++v10;
      while ( *(_BYTE *)(v10 + v11) );
      v19 = v10 + 1;
    }
    v20 = (_QWORD *)PkiZeroAlloc(v19 + 32);
    if ( v20 && (v22 = AddDllProc(pszFuncName, lpSrc)) != 0 )
    {
      *(_DWORD *)v20 = dwEncodingType;
      if ( (v28 & 1) != 0 )
      {
        v20[1] = *((_QWORD *)pvArg + 7);
        *((_QWORD *)pvArg + 7) = v20;
      }
      else
      {
        v20[1] = *((_QWORD *)pvArg + 8);
        *((_QWORD *)pvArg + 8) = v20;
      }
      if ( v19 )
      {
        memcpy_0(v20 + 4, (const void *)v11, v19);
        v20[2] = v20 + 4;
      }
      else
      {
        v20[2] = v11;
      }
      v20[3] = v22;
    }
    else
    {
      PkiDefaultCryptFree(v20);
    }
    if ( !v14 || !pszFuncName || MultiByteStr == pszFuncName )
      return 1;
    LastError = GetLastError();
    LocalFree(pszFuncName);
    v23 = LastError;
LABEL_51:
    SetLastError(v23);
  }
  return 1;
}

```

## disassembly

```asm
0x180048c00  mov     [rsp+arg_0], rbx
0x180048c05  push    rbp
0x180048c06  push    rsi
0x180048c07  push    rdi
0x180048c08  push    r12
0x180048c0a  push    r13
0x180048c0c  push    r14
0x180048c0e  push    r15
0x180048c10  sub     rsp, 1A0h
0x180048c17  mov     rax, cs:__security_cookie
0x180048c1e  xor     rax, rsp
0x180048c21  mov     [rsp+1D8h+var_48], rax
0x180048c29  mov     rax, [rsp+1D8h+rgpwszValueName]
0x180048c31  xor     r14d, r14d
0x180048c34  mov     r13, [rsp+1D8h+pvArg]
0x180048c3c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180048c40  cmp     byte ptr [r8], 23h ; '#'
0x180048c44  mov     rbp, r8
0x180048c47  mov     [rsp+1D8h+var_170], rax
0x180048c4c  mov     rsi, rdx
0x180048c4f  mov     rax, [rsp+1D8h+rgpbValueData]
0x180048c57  lea     edi, [r14+1]
0x180048c5b  mov     [rsp+1D8h+var_168], rax
0x180048c60  mov     rax, [rsp+1D8h+rgcbValueData]
0x180048c68  mov     [rsp+1D8h+var_160], rax
0x180048c6d  mov     [rsp+1D8h+var_198], r9d
0x180048c72  mov     [rsp+1D8h+var_190], ecx
0x180048c76  jz      loc_180048F62
0x180048c7c  mov     [rsp+1D8h+cchCount2], ebx; cchCount2
0x180048c80  mov     r9d, ebx; cchCount1
0x180048c83  mov     [rsp+1D8h+lpString2], r8; lpString2
0x180048c88  mov     edx, edi; dwCmpFlags
0x180048c8a  lea     r8, pszOID; "DEFAULT"
0x180048c91  mov     ecx, 409h; Locale
0x180048c96  call    cs:__imp_CompareStringA
0x180048c9c  cmp     eax, 2
0x180048c9f  cmovz   r14d, edi
0x180048ca3  xor     r15d, r15d
0x180048ca6  xor     edi, edi
0x180048ca8  mov     [rsp+1D8h+lpSrc], r15
0x180048cad  xor     r12d, r12d
0x180048cb0  mov     [rsp+1D8h+var_18C], edi
0x180048cb4  mov     eax, [rsp+1D8h+var_198]
0x180048cb8  test    eax, eax
0x180048cba  jz      loc_180048D7C
0x180048cc0  mov     rcx, [rsp+1D8h+var_170]
0x180048cc5  dec     eax
0x180048cc7  mov     [rsp+1D8h+var_198], eax
0x180048ccb  mov     r9d, ebx; cchCount1
0x180048cce  mov     [rsp+1D8h+cchCount2], ebx; cchCount2
0x180048cd2  mov     rdx, [rcx+rax*8]
0x180048cd6  mov     rcx, [rsp+1D8h+rgdwValueType]
0x180048cde  mov     r8, rdx; lpString1
0x180048ce1  mov     [rsp+1D8h+lpString1], rdx
0x180048ce6  mov     edx, 1; dwCmpFlags
0x180048ceb  mov     r15d, [rcx+rax*4]
0x180048cef  mov     rcx, [rsp+1D8h+var_168]
0x180048cf4  mov     rcx, [rcx+rax*8]
0x180048cf8  mov     [rsp+1D8h+var_188], rcx
0x180048cfd  mov     rcx, [rsp+1D8h+var_160]
0x180048d02  mov     eax, [rcx+rax*4]
0x180048d05  mov     ecx, 409h; Locale
0x180048d0a  mov     [rsp+1D8h+var_194], eax
0x180048d0e  lea     rax, pwszValueName; "Dll"
0x180048d15  mov     [rsp+1D8h+lpString2], rax; lpString2
0x180048d1a  call    cs:__imp_CompareStringW
0x180048d20  cmp     eax, 2
0x180048d23  jz      loc_180048E92
0x180048d29  mov     r8, [rsp+1D8h+lpString1]; lpString1
0x180048d2e  lea     rax, aFuncname; "FuncName"
0x180048d35  mov     [rsp+1D8h+cchCount2], ebx; cchCount2
0x180048d39  mov     r9d, ebx; cchCount1
0x180048d3c  mov     edx, 1; dwCmpFlags
0x180048d41  mov     [rsp+1D8h+lpString2], rax; lpString2
0x180048d46  mov     ecx, 409h; Locale
0x180048d4b  call    cs:__imp_CompareStringW
0x180048d51  cmp     eax, 2
0x180048d54  jnz     loc_180048EB4
0x180048d5a  cmp     r15d, 1
0x180048d5e  jnz     loc_180048E62
0x180048d64  mov     rcx, [rsp+1D8h+var_188]
0x180048d69  xor     eax, eax
0x180048d6b  cmp     ax, [rcx]
0x180048d6e  jz      loc_180048CB4
0x180048d74  mov     r12, rcx
0x180048d77  jmp     loc_180048CB4
0x180048d7c  test    edi, edi
0x180048d7e  jz      loc_180048E62
0x180048d84  mov     r15, [rsp+1D8h+lpSrc]
0x180048d89  xor     eax, eax
0x180048d8b  cmp     ax, [r15]
0x180048d8f  jz      loc_180048E62
0x180048d95  test    r14d, r14d
0x180048d98  jnz     loc_180048F86
0x180048d9e  test    r12, r12
0x180048da1  jz      short loc_180048E10
0x180048da3  mov     [rsp+1D8h+lpUsedDefaultChar], rax; lpUsedDefaultChar
0x180048da8  mov     r9d, ebx; cchWideChar
0x180048dab  mov     [rsp+1D8h+lpDefaultChar], rax; lpDefaultChar
0x180048db0  mov     r8, r12; lpWideCharStr
0x180048db3  mov     [rsp+1D8h+cchCount2], eax; cbMultiByte
0x180048db7  xor     edx, edx; dwFlags
0x180048db9  xor     ecx, ecx; CodePage
0x180048dbb  mov     [rsp+1D8h+lpString2], rax; lpMultiByteStr
0x180048dc0  call    cs:__imp_WideCharToMultiByte
0x180048dc6  movsxd  rdi, eax
0x180048dc9  test    eax, eax
0x180048dcb  jle     loc_180048E62
0x180048dd1  cmp     edi, 104h
0x180048dd7  ja      loc_180048FBD
0x180048ddd  lea     rsi, [rsp+1D8h+MultiByteStr]
0x180048de5  mov     [rsp+1D8h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180048dee  mov     r9d, ebx; cchWideChar
0x180048df1  mov     [rsp+1D8h+lpDefaultChar], 0; lpDefaultChar
0x180048dfa  mov     r8, r12; lpWideCharStr
0x180048dfd  mov     [rsp+1D8h+cchCount2], edi; cbMultiByte
0x180048e01  xor     edx, edx; dwFlags
0x180048e03  xor     ecx, ecx; CodePage
0x180048e05  mov     [rsp+1D8h+lpString2], rsi; lpMultiByteStr
0x180048e0a  call    cs:__imp_WideCharToMultiByte
0x180048e10  cmp     rbp, 0FFFFh
0x180048e17  jbe     loc_180048FB5
0x180048e1d  inc     rbx
0x180048e20  cmp     byte ptr [rbx+rbp], 0
0x180048e24  jnz     short loc_180048E1D
0x180048e26  lea     r14d, [rbx+1]
0x180048e2a  lea     ecx, [r14+20h]; uBytes
0x180048e2e  call    PkiZeroAlloc
0x180048e33  mov     rdi, rax
0x180048e36  test    rax, rax
0x180048e39  jnz     loc_180048F0A
0x180048e3f  mov     rcx, rdi; hMem
0x180048e42  call    PkiDefaultCryptFree
0x180048e47  test    r12, r12
0x180048e4a  jz      short loc_180048E62
0x180048e4c  test    rsi, rsi
0x180048e4f  jz      short loc_180048E62
0x180048e51  lea     rax, [rsp+1D8h+MultiByteStr]
0x180048e59  cmp     rax, rsi
0x180048e5c  jnz     loc_180048FED
0x180048e62  mov     eax, 1
0x180048e67  mov     rcx, [rsp+1D8h+var_48]
0x180048e6f  xor     rcx, rsp; StackCookie
0x180048e72  call    __security_check_cookie
0x180048e77  mov     rbx, [rsp+1D8h+arg_0]
0x180048e7f  add     rsp, 1A0h
0x180048e86  pop     r15
0x180048e88  pop     r14
0x180048e8a  pop     r13
0x180048e8c  pop     r12
0x180048e8e  pop     rdi
0x180048e8f  pop     rsi
0x180048e90  pop     rbp
0x180048e91  retn
0x180048e92  lea     eax, [r15-1]
0x180048e96  cmp     eax, 1
0x180048e99  ja      loc_180048F9D
0x180048e9f  mov     rax, [rsp+1D8h+var_188]
0x180048ea4  mov     edi, [rsp+1D8h+var_194]
0x180048ea8  mov     [rsp+1D8h+lpSrc], rax
0x180048ead  shr     edi, 1
0x180048eaf  jmp     loc_180048CB4
0x180048eb4  mov     r8, [rsp+1D8h+lpString1]; lpString1
0x180048eb9  lea     rax, aCryptflags; "CryptFlags"
0x180048ec0  mov     [rsp+1D8h+cchCount2], ebx; cchCount2
0x180048ec4  mov     r9d, ebx; cchCount1
0x180048ec7  mov     edx, 1; dwCmpFlags
0x180048ecc  mov     [rsp+1D8h+lpString2], rax; lpString2
0x180048ed1  mov     ecx, 409h; Locale
0x180048ed6  call    cs:__imp_CompareStringW
0x180048edc  cmp     eax, 2
0x180048edf  jnz     loc_180048CB4
0x180048ee5  cmp     r15d, 4
0x180048ee9  jnz     loc_180048CB4
0x180048eef  cmp     [rsp+1D8h+var_194], r15d
0x180048ef4  jb      loc_180048CB4
0x180048efa  mov     rax, [rsp+1D8h+var_188]
0x180048eff  mov     eax, [rax]
0x180048f01  mov     [rsp+1D8h+var_18C], eax
0x180048f05  jmp     loc_180048CB4
0x180048f0a  mov     rdx, r15; lpSrc
0x180048f0d  mov     rcx, rsi; Src
0x180048f10  call    ?AddDllProc@@YAPEAU_DLL_PROC_ELEMENT@@PEBDPEBG@Z; AddDllProc(char const *,ushort const *)
0x180048f15  mov     r15, rax
0x180048f18  test    rax, rax
0x180048f1b  jz      loc_180048E3F
0x180048f21  test    byte ptr [rsp+1D8h+var_18C], 1
0x180048f26  mov     eax, [rsp+1D8h+var_190]
0x180048f2a  mov     [rdi], eax
0x180048f2c  jnz     loc_180048FDC
0x180048f32  mov     rax, [r13+40h]
0x180048f36  mov     [rdi+8], rax
0x180048f3a  mov     [r13+40h], rdi
0x180048f3e  test    r14d, r14d
0x180048f41  jz      short loc_180048F80
0x180048f43  lea     rbx, [rdi+20h]
0x180048f47  mov     r8d, r14d; Size
0x180048f4a  mov     rcx, rbx; void *
0x180048f4d  mov     rdx, rbp; Src
0x180048f50  call    memcpy_0
0x180048f55  mov     [rdi+10h], rbx
0x180048f59  mov     [rdi+18h], r15
0x180048f5d  jmp     loc_180048E47
0x180048f62  lea     rcx, [r8+1]; String
0x180048f66  call    _o_atol_0
0x180048f6b  movsxd  rbp, eax
0x180048f6e  cmp     rbp, 0FFFFh
0x180048f75  jbe     loc_180048CA3
0x180048f7b  jmp     loc_180048E62
0x180048f80  mov     [rdi+10h], rbp
0x180048f84  jmp     short loc_180048F59
0x180048f86  mov     ecx, [rsp+1D8h+var_190]; unsigned int
0x180048f8a  mov     r9d, edi; unsigned int
0x180048f8d  mov     r8, r15; unsigned __int16 *
0x180048f90  mov     rdx, r13; struct _FUNC_SET *
0x180048f93  call    ?AddDefaultDllList@@YAXKPEAU_FUNC_SET@@PEBGK@Z; AddDefaultDllList(ulong,_FUNC_SET *,ushort const *,ulong)
0x180048f98  jmp     loc_180048E62
0x180048f9d  test    r14d, r14d
0x180048fa0  jz      loc_180048E62
0x180048fa6  cmp     r15d, 7
0x180048faa  jz      loc_180048E9F
0x180048fb0  jmp     loc_180048E62
0x180048fb5  xor     r14d, r14d
0x180048fb8  jmp     loc_180048E2A
0x180048fbd  mov     rdx, rdi; uBytes
0x180048fc0  xor     ecx, ecx; uFlags
0x180048fc2  call    cs:__imp_LocalAlloc
0x180048fc8  mov     rsi, rax
0x180048fcb  test    rax, rax
0x180048fce  jnz     loc_180048DE5
0x180048fd4  lea     ecx, [rax+0Eh]; dwErrCode
0x180048fd7  jmp     loc_180118080
0x180048fdc  mov     rcx, [r13+38h]
0x180048fe0  mov     [rdi+8], rcx
0x180048fe4  mov     [r13+38h], rdi
0x180048fe8  jmp     loc_180048F3E
0x180048fed  call    cs:__imp_GetLastError
0x180048ff3  mov     rcx, rsi; hMem
0x180048ff6  mov     ebx, eax
0x180048ff8  call    cs:__imp_LocalFree
0x180048ffe  mov     ecx, ebx
0x180049000  jmp     loc_180118080
0x180118080  call    cs:__imp_SetLastError
0x180118086  nop
0x180118087  jmp     loc_180048E62
```
