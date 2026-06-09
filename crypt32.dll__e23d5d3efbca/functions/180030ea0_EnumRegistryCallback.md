# EnumRegistryCallback

- ea: `0x180030ea0`
- end: `0x1800316d4`
- name: `EnumRegistryCallback`
- size: `2100`
- prototype: `__int64 __fastcall(DWORD dwEncodingType, LPCSTR pszFuncName, LPCSTR pszOID, DWORD cValue, const DWORD *__attribute__((__org_arrdim(0,0))) rgdwValueType, const LPCWSTR *__attribute__((__org_arrdim(0,0))) rgpwszValueName, const BYTE *const *__attribute__((__org_arrdim(0,0))) rgpbValueData, const DWORD *__attribute__((__org_arrdim(0,0))) rgcbValueData)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18007dab0`

## callees

- `0x180028d60`
- `0x180030e60`
- `0x180030ea0`
- `0x1800316dc`
- `0x180031b18`
- `0x1800bf564`
- `0x1801150d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031269`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031269`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180031236`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003127c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800313f0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800316c1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180031236`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003127c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800313f0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800316c1`
- `api-ms-win-core-registry-l1-1-0!RegLoadMUIStringW` at `0x180031374`
- `api-ms-win-core-registry-l1-1-0!RegLoadMUIStringW` at `0x1800313e0`
- `api-ms-win-core-registry-l1-1-0!RegLoadMUIStringW` at `0x180031374`
- `api-ms-win-core-registry-l1-1-0!RegLoadMUIStringW` at `0x1800313e0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180031339`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180031339`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031274`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031274`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003121f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031635`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003121f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031635`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18003150f`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18003150f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031029`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003105d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031091`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800310c5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800310f9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003112d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031029`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003105d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031091`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800310c5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800310f9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003112d`

## pseudocode

```c
__int64 __fastcall EnumRegistryCallback(
        DWORD dwEncodingType,
        LPCSTR pszFuncName,
        LPCSTR pszOID,
        DWORD cValue,
        const DWORD rgdwValueType[],
        const LPCWSTR rgpwszValueName[],
        const BYTE *const rgpbValueData[],
        const DWORD rgcbValueData[])
{
  __int64 v8; // rax
  const CHAR *i; // rdi
  __int64 v13; // rbp
  __int64 v14; // rsi
  __int64 v15; // r13
  unsigned int v16; // r15d
  unsigned __int64 v17; // rax
  unsigned int v18; // r12d
  const WCHAR *v19; // r15
  DWORD v20; // ebp
  BYTE *v21; // rdi
  DWORD v22; // r14d
  int v23; // edi
  char *v24; // rbp
  DWORD v25; // ecx
  HLOCAL v26; // rdi
  DWORD LastError; // ebx
  _WORD *v28; // r14
  char *v29; // rdi
  LSTATUS v30; // eax
  DWORD v31; // ecx
  bool v32; // zf
  DWORD v33; // eax
  unsigned int v34; // eax
  int *v35; // r15
  void *v36; // rcx
  SIZE_T v37; // rdx
  char *v38; // rax
  unsigned int v39; // ecx
  char *v40; // r14
  __int64 v41; // r15
  char *v42; // rbp
  char *v43; // rsi
  _WORD *v44; // rsi
  _WORD *v45; // rsi
  unsigned int v46; // edx
  size_t v47; // r8
  void *v48; // rdx
  char *v49; // rcx
  unsigned int v50; // [rsp+40h] [rbp-A8h]
  DWORD v51; // [rsp+48h] [rbp-A0h] BYREF
  unsigned int Size; // [rsp+4Ch] [rbp-9Ch]
  unsigned int Size_4; // [rsp+50h] [rbp-98h]
  int v54; // [rsp+54h] [rbp-94h]
  int v55; // [rsp+58h] [rbp-90h]
  HKEY phkResult; // [rsp+60h] [rbp-88h] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp-80h]
  int v58; // [rsp+70h] [rbp-78h]
  void *Src; // [rsp+78h] [rbp-70h]
  void *v60; // [rsp+80h] [rbp-68h]
  void *v61; // [rsp+88h] [rbp-60h]
  void *v62; // [rsp+90h] [rbp-58h]
  DWORD pcbData; // [rsp+100h] [rbp+18h] BYREF
  DWORD v66; // [rsp+108h] [rbp+20h]

  LODWORD(v8) = 0;
  Size_4 = 0;
  v62 = 0;
  if ( pszOID )
  {
    v8 = -1;
    do
      ++v8;
    while ( pszOID[v8] );
  }
  for ( i = &pszOID[(unsigned int)v8]; i > pszOID; --i )
  {
    if ( *i == 33 )
      break;
  }
  if ( *i != 33 )
    return 1;
  LODWORD(v13) = 0;
  LODWORD(v14) = 0;
  LODWORD(v15) = 0;
  Src = 0;
  v16 = (_DWORD)i - (_DWORD)pszOID;
  hMem = 0;
  Size = (_DWORD)i - (_DWORD)pszOID;
  v55 = 0;
  v54 = 0;
  v50 = 0;
  v60 = 0;
  v61 = 0;
  v58 = o_atol_0(i + 1);
  while ( 1 )
  {
    v17 = (unsigned __int64)i--;
    if ( v17 <= (unsigned __int64)pszOID )
      break;
    if ( *i == 33 )
    {
      v16 = (_DWORD)i - (_DWORD)pszOID;
      Size = (_DWORD)i - (_DWORD)pszOID;
      break;
    }
  }
  v18 = 1;
  if ( cValue )
  {
    while ( 1 )
    {
      v66 = cValue - 1;
      v19 = rgpwszValueName[cValue - 1];
      v20 = rgdwValueType[cValue - 1];
      v21 = (BYTE *)rgpbValueData[cValue - 1];
      v22 = rgcbValueData[cValue - 1];
      if ( CompareStringW(0x409u, 1u, v19, -1, L"Name", -1) == 2 )
      {
        if ( v20 == 1 )
        {
          Src = v21;
          if ( v21 )
          {
            v14 = -1;
            do
              ++v14;
            while ( *(_WORD *)&v21[2 * v14] );
            if ( (unsigned int)v14 > 1 && *(_WORD *)v21 == 64 )
            {
              if ( hMem )
                PkiDefaultCryptFree(hMem);
              v28 = 0;
              pcbData = 0;
              v51 = 0;
              phkResult = 0;
              v29 = FormatOIDFuncRegName(dwEncodingType, pszFuncName, pszOID);
              if ( !v29 )
                goto LABEL_63;
              v30 = RegOpenKeyExA(HKEY_LOCAL_MACHINE, v29, 0, 0x20019u, &phkResult);
              if ( v30
                || (pcbData = 0, (v30 = RegLoadMUIStringW(phkResult, v19, 0, 0, &pcbData, 0, 0)) != 0) && v30 != 234 )
              {
LABEL_61:
                v31 = v30;
              }
              else
              {
                if ( pcbData <= 0xFFFF )
                {
                  hMem = (HLOCAL)PkiNonzeroAlloc(pcbData + 4LL);
                  v28 = hMem;
                  if ( hMem )
                  {
                    v51 = pcbData;
                    v30 = RegLoadMUIStringW(phkResult, v19, (LPWSTR)hMem, pcbData, &v51, 0, 0);
                    if ( v30 )
                      goto LABEL_61;
                    v33 = pcbData;
                    if ( pcbData >= v51 )
                    {
                      v33 = v51;
                      pcbData = v51;
                    }
                    v28[(unsigned __int64)v33 >> 1] = 0;
                    v28[((unsigned __int64)pcbData >> 1) + 1] = 0;
LABEL_64:
                    PkiDefaultCryptFree(v29);
LABEL_65:
                    if ( phkResult )
                      ILS_CloseRegistryKey(phkResult);
                    if ( v28 )
                    {
                      Src = v28;
                      v14 = -1;
                      do
                        ++v14;
                      while ( v28[v14] );
                    }
                    goto LABEL_31;
                  }
LABEL_63:
                  PkiDefaultCryptFree(v28);
                  v28 = 0;
                  hMem = 0;
                  if ( v29 )
                    goto LABEL_64;
                  goto LABEL_65;
                }
                v31 = -2146885629;
              }
              SetLastError(v31);
              goto LABEL_63;
            }
          }
          else
          {
            LODWORD(v14) = 0;
          }
        }
      }
      else if ( CompareStringW(0x409u, 1u, v19, -1, L"Algid", -1) == 2 )
      {
        if ( v20 == 4 )
        {
          LODWORD(v13) = v50;
          if ( v22 >= 4 )
            v55 = *(_DWORD *)v21;
          goto LABEL_32;
        }
      }
      else
      {
        if ( CompareStringW(0x409u, 1u, v19, -1, L"ExtraInfo", -1) == 2 )
        {
          v32 = v20 == 3;
          LODWORD(v13) = v50;
          if ( v32 )
          {
            Size_4 = v22;
            v62 = v21;
          }
          goto LABEL_32;
        }
        if ( CompareStringW(0x409u, 1u, v19, -1, L"Flags", -1) == 2 )
        {
          if ( v20 == 4 )
          {
            LODWORD(v13) = v50;
            if ( v22 >= 4 )
              v54 = *(_DWORD *)v21;
            goto LABEL_32;
          }
        }
        else if ( CompareStringW(0x409u, 1u, v19, -1, L"CNGAlgid", -1) == 2 )
        {
          if ( v20 == 1 )
          {
            v60 = v21;
            if ( v21 )
            {
              v13 = -1;
              do
                ++v13;
              while ( *(_WORD *)&v21[2 * v13] );
              v50 = v13;
            }
            else
            {
              LODWORD(v13) = 0;
              v50 = 0;
            }
            goto LABEL_32;
          }
        }
        else if ( CompareStringW(0x409u, 1u, v19, -1, L"CNGExtraAlgid", -1) == 2 && v20 == 1 )
        {
          v61 = v21;
          if ( v21 )
          {
            v15 = -1;
            do
              ++v15;
            while ( *(_WORD *)&v21[2 * v15] );
          }
          else
          {
            LODWORD(v15) = 0;
          }
        }
      }
LABEL_31:
      LODWORD(v13) = v50;
LABEL_32:
      cValue = v66;
      if ( !v66 )
      {
        v16 = Size;
        break;
      }
    }
  }
  if ( (unsigned int)v14 > 0xFFFFFF
    || v16 > 0xFFFFFF
    || (unsigned int)v13 > 0xFFFFFF
    || (unsigned int)v15 > 0xFFFFFF
    || Size_4 > 0xFFFFFF )
  {
    goto LABEL_82;
  }
  v23 = (2 * (v14 + v13 + v15) + 13) & 0xFFFFFFF8;
  v24 = (char *)LocalAlloc(0x40u, Size_4 + v23 + ((v16 + 8) & 0xFFFFFFF8));
  if ( !v24 )
  {
    v25 = -2147024882;
LABEL_41:
    SetLastError(v25);
    goto LABEL_42;
  }
  if ( (v54 & 1) != 0 )
  {
    v34 = dword_18015CC08;
    v35 = &dword_18015CC08;
  }
  else
  {
    v34 = dword_18015CC20;
    v35 = &dword_18015CC20;
  }
  if ( v34 > 0xFFFFF )
  {
LABEL_82:
    v25 = 534;
    goto LABEL_41;
  }
  v36 = (void *)*((_QWORD *)v35 + 1);
  v37 = (unsigned __int64)(v34 + 1) << 6;
  if ( v36 )
    v38 = (char *)LocalReAlloc(v36, v37, 2u);
  else
    v38 = (char *)LocalAlloc(0, v37);
  if ( v38 )
  {
    v39 = *v35;
    *((_QWORD *)v35 + 1) = v38;
    v40 = &v38[64 * (unsigned __int64)v39];
    *v35 = v39 + 1;
    v41 = Size;
    *(_DWORD *)v40 = 64;
    *((_QWORD *)v40 + 1) = v24;
    if ( (_DWORD)v41 )
      memcpy_0(v24, pszOID, (unsigned int)v41);
    v24[v41] = 0;
    v42 = &v24[((_DWORD)v41 + 8) & 0xFFFFFFF8];
    *((_QWORD *)v40 + 2) = v42;
    if ( (_DWORD)v14 )
    {
      memcpy_0(v42, Src, 2LL * (unsigned int)v14);
      v43 = &v42[2 * (unsigned int)v14];
    }
    else
    {
      v43 = v42;
    }
    *(_WORD *)v43 = 0;
    v44 = v43 + 2;
    *((_QWORD *)v40 + 6) = v44;
    if ( v50 )
    {
      memcpy_0(v44, v60, 2LL * v50);
      v44 += v50;
    }
    *v44 = 0;
    v45 = v44 + 1;
    *((_QWORD *)v40 + 7) = v45;
    if ( (_DWORD)v15 )
    {
      memcpy_0(v45, v61, 2LL * (unsigned int)v15);
      v45 += (unsigned int)v15;
    }
    v46 = Size_4;
    *v45 = 0;
    *((_DWORD *)v40 + 6) = v58;
    *((_DWORD *)v40 + 7) = v55;
    *((_DWORD *)v40 + 8) = v46;
    if ( v46 )
    {
      v47 = v46;
      v48 = v62;
      v49 = &v42[v23];
      *((_QWORD *)v40 + 5) = v49;
      memcpy_0(v49, v48, v47);
    }
    else
    {
      *((_QWORD *)v40 + 5) = 0;
    }
    goto LABEL_43;
  }
  SetLastError(0x8007000E);
  PkiDefaultCryptFree(v24);
LABEL_42:
  v18 = 0;
LABEL_43:
  v26 = hMem;
  if ( hMem )
  {
    LastError = GetLastError();
    LocalFree(v26);
    SetLastError(LastError);
  }
  return v18;
}

```

## disassembly

```asm
0x180030ea0  mov     r11, rsp
0x180030ea3  mov     [r11+10h], rdx
0x180030ea7  mov     [rsp+arg_0], ecx
0x180030eab  push    rbx
0x180030eac  push    rdi
0x180030ead  push    r14
0x180030eaf  sub     rsp, 0D0h
0x180030eb6  xor     edx, edx
0x180030eb8  xor     eax, eax
0x180030eba  mov     dword ptr [rsp+0E8h+Size+4], edx
0x180030ebe  mov     r14d, r9d
0x180030ec1  mov     [r11-54h], eax
0x180030ec5  mov     rbx, r8
0x180030ec8  mov     [r11-58h], rdx
0x180030ecc  test    r8, r8
0x180030ecf  jz      short loc_180030EE9
0x180030ed1  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180030ed8  nop     dword ptr [rax+rax+00000000h]
0x180030ee0  inc     rax
0x180030ee3  cmp     [r8+rax], dl
0x180030ee7  jnz     short loc_180030EE0
0x180030ee9  mov     edi, eax
0x180030eeb  add     rdi, rbx
0x180030eee  cmp     rdi, rbx
0x180030ef1  ja      short loc_180030F20
0x180030ef3  cmp     byte ptr [rdi], 21h ; '!'
0x180030ef6  mov     [rsp+0E8h+var_30], r12
0x180030efe  jz      short loc_180030F2F
0x180030f00  mov     eax, 1
0x180030f05  mov     r12, [rsp+0E8h+var_30]
0x180030f0d  add     rsp, 0D0h
0x180030f14  pop     r14
0x180030f16  pop     rdi
0x180030f17  pop     rbx
0x180030f18  retn
0x180030f20  cmp     byte ptr [rdi], 21h ; '!'
0x180030f23  jz      short loc_180030EF3
0x180030f25  dec     rdi
0x180030f28  cmp     rdi, rbx
0x180030f2b  jbe     short loc_180030EF3
0x180030f2d  jmp     short loc_180030F20
0x180030f2f  mov     [rsp+0E8h+var_20], rbp
0x180030f37  lea     rcx, [rdi+1]; String
0x180030f3b  mov     [rsp+0E8h+var_28], rsi
0x180030f43  mov     ebp, edx
0x180030f45  mov     [rsp+0E8h+var_38], r13
0x180030f4d  mov     esi, edx
0x180030f4f  mov     [rsp+0E8h+var_40], r15
0x180030f57  mov     r13d, edx
0x180030f5a  mov     r15d, edi
0x180030f5d  mov     [rsp+0E8h+Src], rdx
0x180030f62  sub     r15d, ebx
0x180030f65  mov     [rsp+0E8h+hMem], rdx
0x180030f6a  mov     dword ptr [rsp+0E8h+Size], r15d
0x180030f6f  mov     [rsp+0E8h+var_90], edx
0x180030f73  mov     [rsp+0E8h+var_94], edx
0x180030f77  mov     [rsp+0E8h+var_A8], rbp
0x180030f7c  mov     [rsp+0E8h+var_68], rdx
0x180030f84  mov     [rsp+0E8h+var_60], rdx
0x180030f8c  call    _o_atol_0
0x180030f91  mov     [rsp+0E8h+var_78], eax
0x180030f95  mov     rax, rdi
0x180030f98  dec     rdi
0x180030f9b  cmp     rax, rbx
0x180030f9e  jbe     short loc_180030FB0
0x180030fa0  cmp     byte ptr [rdi], 21h ; '!'
0x180030fa3  jnz     short loc_180030F95
0x180030fa5  mov     r15d, edi
0x180030fa8  sub     r15d, ebx
0x180030fab  mov     dword ptr [rsp+0E8h+Size], r15d
0x180030fb0  mov     r12d, 1
0x180030fb6  mov     r8d, 40h ; '@'
0x180030fbc  test    r14d, r14d
0x180030fbf  jz      loc_1800311BB
0x180030fc5  lea     rdx, aName; "Name"
0x180030fcc  nop     dword ptr [rax+00h]
0x180030fd0  mov     rcx, [rsp+0E8h+rgpwszValueName]
0x180030fd8  dec     r14d
0x180030fdb  mov     [rsp+0E8h+arg_18], r14d
0x180030fe3  mov     r9d, 0FFFFFFFFh; cchCount1
0x180030fe9  mov     [rsp+0E8h+cchCount2], 0FFFFFFFFh; cchCount2
0x180030ff1  mov     [rsp+0E8h+lpString2], rdx; lpString2
0x180030ff6  mov     edx, r12d; dwCmpFlags
0x180030ff9  mov     r15, [rcx+r14*8]
0x180030ffd  mov     rcx, [rsp+0E8h+rgdwValueType]
0x180031005  mov     r8, r15; lpString1
0x180031008  mov     ebp, [rcx+r14*4]
0x18003100c  mov     rcx, [rsp+0E8h+rgpbValueData]
0x180031014  mov     rdi, [rcx+r14*8]
0x180031018  mov     rcx, [rsp+0E8h+rgcbValueData]
0x180031020  mov     r14d, [rcx+r14*4]
0x180031024  mov     ecx, 409h; Locale
0x180031029  call    cs:__imp_CompareStringW
0x18003102f  cmp     eax, 2
0x180031032  jz      loc_180031162
0x180031038  lea     rax, aAlgid; "Algid"
0x18003103f  mov     [rsp+0E8h+cchCount2], 0FFFFFFFFh; cchCount2
0x180031047  mov     r9d, 0FFFFFFFFh; cchCount1
0x18003104d  mov     [rsp+0E8h+lpString2], rax; lpString2
0x180031052  mov     r8, r15; lpString1
0x180031055  mov     edx, r12d; dwCmpFlags
0x180031058  mov     ecx, 409h; Locale
0x18003105d  call    cs:__imp_CompareStringW
0x180031063  cmp     eax, 2
0x180031066  jz      loc_180031450
0x18003106c  lea     rax, aExtrainfo; "ExtraInfo"
0x180031073  mov     [rsp+0E8h+cchCount2], 0FFFFFFFFh; cchCount2
0x18003107b  mov     r9d, 0FFFFFFFFh; cchCount1
0x180031081  mov     [rsp+0E8h+lpString2], rax; lpString2
0x180031086  mov     r8, r15; lpString1
0x180031089  mov     edx, r12d; dwCmpFlags
0x18003108c  mov     ecx, 409h; Locale
0x180031091  call    cs:__imp_CompareStringW
0x180031097  cmp     eax, 2
0x18003109a  jz      loc_180031473
0x1800310a0  lea     rax, ValueName; "Flags"
0x1800310a7  mov     [rsp+0E8h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800310af  mov     r9d, 0FFFFFFFFh; cchCount1
0x1800310b5  mov     [rsp+0E8h+lpString2], rax; lpString2
0x1800310ba  mov     r8, r15; lpString1
0x1800310bd  mov     edx, r12d; dwCmpFlags
0x1800310c0  mov     ecx, 409h; Locale
0x1800310c5  call    cs:__imp_CompareStringW
0x1800310cb  cmp     eax, 2
0x1800310ce  jz      loc_18003164D
0x1800310d4  lea     rax, aCngalgid; "CNGAlgid"
0x1800310db  mov     [rsp+0E8h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800310e3  mov     r9d, 0FFFFFFFFh; cchCount1
0x1800310e9  mov     [rsp+0E8h+lpString2], rax; lpString2
0x1800310ee  mov     r8, r15; lpString1
0x1800310f1  mov     edx, r12d; dwCmpFlags
0x1800310f4  mov     ecx, 409h; Locale
0x1800310f9  call    cs:__imp_CompareStringW
0x1800310ff  cmp     eax, 2
0x180031102  jz      loc_18003128A
0x180031108  lea     rax, aCngextraalgid; "CNGExtraAlgid"
0x18003110f  mov     [rsp+0E8h+cchCount2], 0FFFFFFFFh; cchCount2
0x180031117  mov     r9d, 0FFFFFFFFh; cchCount1
0x18003111d  mov     [rsp+0E8h+lpString2], rax; lpString2
0x180031122  mov     r8, r15; lpString1
0x180031125  mov     edx, r12d; dwCmpFlags
0x180031128  mov     ecx, 409h; Locale
0x18003112d  call    cs:__imp_CompareStringW
0x180031133  cmp     eax, 2
0x180031136  jnz     short loc_180031193
0x180031138  cmp     ebp, r12d
0x18003113b  jnz     short loc_180031193
0x18003113d  mov     [rsp+0E8h+var_60], rdi
0x180031145  test    rdi, rdi
0x180031148  jz      loc_1800316B4
0x18003114e  mov     r13, 0FFFFFFFFFFFFFFFFh
0x180031155  inc     r13
0x180031158  cmp     word ptr [rdi+r13*2], 0
0x18003115e  jnz     short loc_180031155
0x180031160  jmp     short loc_180031193
0x180031162  cmp     ebp, r12d
0x180031165  jnz     short loc_180031193
0x180031167  mov     [rsp+0E8h+Src], rdi
0x18003116c  test    rdi, rdi
0x18003116f  jz      loc_1800316A1
0x180031175  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18003117c  nop     dword ptr [rax+00h]
0x180031180  inc     rsi
0x180031183  cmp     word ptr [rdi+rsi*2], 0
0x180031188  jnz     short loc_180031180
0x18003118a  cmp     esi, r12d
0x18003118d  ja      loc_1800312C4
0x180031193  mov     rbp, [rsp+0E8h+var_A8]
0x180031198  mov     r14d, [rsp+0E8h+arg_18]
0x1800311a0  lea     rdx, aName; "Name"
0x1800311a7  test    r14d, r14d
0x1800311aa  jnz     loc_180030FD0
0x1800311b0  mov     r15d, dword ptr [rsp+0E8h+Size]
0x1800311b5  mov     r8d, 40h ; '@'
0x1800311bb  cmp     esi, 0FFFFFFh
0x1800311c1  ja      loc_1800314EB
0x1800311c7  cmp     r15d, 0FFFFFFh
0x1800311ce  ja      loc_1800314EB
0x1800311d4  cmp     ebp, 0FFFFFFh
0x1800311da  ja      loc_1800314EB
0x1800311e0  cmp     r13d, 0FFFFFFh
0x1800311e7  ja      loc_1800314EB
0x1800311ed  mov     ecx, dword ptr [rsp+0E8h+Size+4]
0x1800311f1  cmp     ecx, 0FFFFFFh
0x1800311f7  ja      loc_1800314EB
0x1800311fd  mov     edx, 0FFFFFFF8h
0x180031202  mov     eax, r13d
0x180031205  add     eax, ebp
0x180031207  add     eax, esi
0x180031209  lea     edi, ds:0Dh[rax*2]
0x180031210  and     edi, edx
0x180031212  lea     eax, [r15+8]
0x180031216  and     edx, eax
0x180031218  add     edx, edi
0x18003121a  add     edx, ecx; uBytes
0x18003121c  mov     ecx, r8d; uFlags
0x18003121f  call    cs:__imp_LocalAlloc
0x180031225  mov     rbp, rax
0x180031228  test    rax, rax
0x18003122b  jnz     loc_1800314CC
0x180031231  mov     ecx, 8007000Eh; dwErrCode
0x180031236  call    cs:__imp_SetLastError
0x18003123c  xor     r12d, r12d
0x18003123f  mov     rdi, [rsp+0E8h+hMem]
0x180031244  mov     r15, [rsp+0E8h+var_40]
0x18003124c  mov     r13, [rsp+0E8h+var_38]
0x180031254  mov     rsi, [rsp+0E8h+var_28]
0x18003125c  mov     rbp, [rsp+0E8h+var_20]
0x180031264  test    rdi, rdi
0x180031267  jz      short loc_180031282
0x180031269  call    cs:__imp_GetLastError
0x18003126f  mov     rcx, rdi; hMem
0x180031272  mov     ebx, eax
0x180031274  call    cs:__imp_LocalFree
0x18003127a  mov     ecx, ebx; dwErrCode
0x18003127c  call    cs:__imp_SetLastError
0x180031282  mov     eax, r12d
0x180031285  jmp     loc_180030F05
0x18003128a  cmp     ebp, r12d
0x18003128d  jnz     loc_180031193
0x180031293  mov     [rsp+0E8h+var_68], rdi
0x18003129b  test    rdi, rdi
0x18003129e  jz      loc_1800316A8
0x1800312a4  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x1800312ab  nop     dword ptr [rax+rax+00h]
0x1800312b0  inc     rbp
0x1800312b3  cmp     word ptr [rdi+rbp*2], 0
0x1800312b8  jnz     short loc_1800312B0
0x1800312ba  mov     [rsp+0E8h+var_A8], rbp
0x1800312bf  jmp     loc_180031198
0x1800312c4  mov     eax, 40h ; '@'
0x1800312c9  cmp     ax, [rdi]
0x1800312cc  jnz     loc_180031193
0x1800312d2  mov     rdi, [rsp+0E8h+hMem]
0x1800312d7  test    rdi, rdi
0x1800312da  jnz     loc_18003168A
0x1800312e0  mov     rdx, [rsp+0E8h+arg_8]; char *
0x1800312e8  xor     r14d, r14d
0x1800312eb  mov     ecx, [rsp+0E8h+arg_0]; unsigned int
0x1800312f2  mov     r8, rbx; char *
0x1800312f5  mov     [rsp+0E8h+pcbData], r14d
0x1800312fd  mov     [rsp+0E8h+var_A0], r14d
0x180031302  mov     [rsp+0E8h+phkResult], 0
0x18003130b  call    ?FormatOIDFuncRegName@@YAPEADKPEBD0@Z; FormatOIDFuncRegName(ulong,char const *,char const *)
0x180031310  mov     rdi, rax
0x180031313  test    rax, rax
0x180031316  jz      loc_1800313F6
0x18003131c  lea     rax, [rsp+0E8h+phkResult]
0x180031321  mov     r9d, 20019h; samDesired
0x180031327  xor     r8d, r8d; ulOptions
0x18003132a  mov     [rsp+0E8h+lpString2], rax; phkResult
0x18003132f  mov     rdx, rdi; lpSubKey
0x180031332  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180031339  call    cs:__imp_RegOpenKeyExA
0x18003133f  test    eax, eax
0x180031341  jnz     loc_1800313EE
0x180031347  mov     rcx, [rsp+0E8h+phkResult]; hKey
0x18003134c  lea     rax, [rsp+0E8h+pcbData]
0x180031354  mov     [rsp+0E8h+pszDirectory], r14; pszDirectory
0x180031359  xor     r9d, r9d; cbOutBuf
0x18003135c  mov     [rsp+0E8h+cchCount2], r14d; Flags
0x180031361  xor     r8d, r8d; pszOutBuf
0x180031364  mov     rdx, r15; pszValue
0x180031367  mov     [rsp+0E8h+lpString2], rax; pcbData
0x18003136c  mov     [rsp+0E8h+pcbData], r14d
0x180031374  call    cs:__imp_RegLoadMUIStringW
0x18003137a  test    eax, eax
0x18003137c  jz      short loc_180031385
0x18003137e  cmp     eax, 0EAh
0x180031383  jnz     short loc_1800313EE
0x180031385  mov     eax, [rsp+0E8h+pcbData]
0x18003138c  cmp     eax, 0FFFFh
0x180031391  ja      loc_180031697
0x180031397  lea     rcx, [rax+4]; uBytes
0x18003139b  call    PkiNonzeroAlloc
0x1800313a0  mov     [rsp+0E8h+hMem], rax
0x1800313a5  mov     r14, rax
0x1800313a8  test    rax, rax
0x1800313ab  jz      short loc_1800313F6
0x1800313ad  mov     r9d, [rsp+0E8h+pcbData]; cbOutBuf
0x1800313b5  lea     rax, [rsp+0E8h+var_A0]
0x1800313ba  mov     rcx, [rsp+0E8h+phkResult]; hKey
0x1800313bf  mov     r8, r14; pszOutBuf
0x1800313c2  mov     [rsp+0E8h+pszDirectory], 0; pszDirectory
0x1800313cb  mov     rdx, r15; pszValue
0x1800313ce  mov     [rsp+0E8h+cchCount2], 0; Flags
0x1800313d6  mov     [rsp+0E8h+lpString2], rax; pcbData
0x1800313db  mov     [rsp+0E8h+var_A0], r9d
0x1800313e0  call    cs:__imp_RegLoadMUIStringW
0x1800313e6  test    eax, eax
0x1800313e8  jz      loc_180031493
0x1800313ee  mov     ecx, eax; dwErrCode
0x1800313f0  call    cs:__imp_SetLastError
0x1800313f6  mov     rcx, r14; hMem
0x1800313f9  call    PkiDefaultCryptFree
0x1800313fe  xor     r14d, r14d
0x180031401  mov     [rsp+0E8h+hMem], r14
0x180031406  test    rdi, rdi
0x180031409  jz      short loc_180031413
0x18003140b  mov     rcx, rdi; hMem
  ... truncated ...
```
