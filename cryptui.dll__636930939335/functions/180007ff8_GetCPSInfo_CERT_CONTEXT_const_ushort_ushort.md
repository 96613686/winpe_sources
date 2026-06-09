# GetCPSInfo(_CERT_CONTEXT const *,ushort * *,ushort * *)

- ea: `0x180007ff8`
- end: `0x180008889`
- name: `?GetCPSInfo@@YAKPEBU_CERT_CONTEXT@@PEAPEAG1@Z`
- size: `2193`
- prototype: `unsigned int __fastcall(const struct _CERT_CONTEXT *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180007f18`
- `0x18000f2b0`

## callees

- `0x180001f66`
- `0x180007ff8`
- `0x180008890`
- `0x18003e58e`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800080c2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000819f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008213`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008292`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008314`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800083f3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008474`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800084f1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008583`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000865c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800086e2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008754`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800080c2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000819f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008213`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008292`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008314`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800083f3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008474`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800084f1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008583`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000865c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800086e2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008754`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008337`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008789`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800087d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800087ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000882e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000883c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000884a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008858`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008866`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008337`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008789`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800087d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800087ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000882e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000883c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000884a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008858`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008866`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008108`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000836a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008385`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800087b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008108`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000836a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008385`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800087b0`
- `CRYPT32!CertFindExtension` at `0x18000807c`
- `CRYPT32!CertFindExtension` at `0x1800083ad`
- `CRYPT32!CertFindExtension` at `0x180008539`
- `CRYPT32!CertFindExtension` at `0x18000807c`
- `CRYPT32!CertFindExtension` at `0x1800083ad`
- `CRYPT32!CertFindExtension` at `0x180008539`
- `CRYPT32!CryptDecodeObject` at `0x1800080b6`
- `CRYPT32!CryptDecodeObject` at `0x1800080fb`
- `CRYPT32!CryptDecodeObject` at `0x18000818f`
- `CRYPT32!CryptDecodeObject` at `0x1800081e3`
- `CRYPT32!CryptDecodeObject` at `0x180008284`
- `CRYPT32!CryptDecodeObject` at `0x1800082d6`
- `CRYPT32!CryptDecodeObject` at `0x1800083e7`
- `CRYPT32!CryptDecodeObject` at `0x18000842a`
- `CRYPT32!CryptDecodeObject` at `0x180008577`
- `CRYPT32!CryptDecodeObject` at `0x1800085bc`
- `CRYPT32!CryptDecodeObject` at `0x18000864e`
- `CRYPT32!CryptDecodeObject` at `0x1800086a4`
- `CRYPT32!CryptDecodeObject` at `0x1800080b6`
- `CRYPT32!CryptDecodeObject` at `0x1800080fb`
- `CRYPT32!CryptDecodeObject` at `0x18000818f`
- `CRYPT32!CryptDecodeObject` at `0x1800081e3`
- `CRYPT32!CryptDecodeObject` at `0x180008284`
- `CRYPT32!CryptDecodeObject` at `0x1800082d6`
- `CRYPT32!CryptDecodeObject` at `0x1800083e7`
- `CRYPT32!CryptDecodeObject` at `0x18000842a`
- `CRYPT32!CryptDecodeObject` at `0x180008577`
- `CRYPT32!CryptDecodeObject` at `0x1800085bc`
- `CRYPT32!CryptDecodeObject` at `0x18000864e`
- `CRYPT32!CryptDecodeObject` at `0x1800086a4`

## pseudocode

```c
__int64 __fastcall GetCPSInfo(const struct _CERT_CONTEXT *a1, HLOCAL *a2, HLOCAL *a3)
{
  _QWORD *pvStructInfo; // r13
  const unsigned __int16 **v5; // rsi
  const void **v6; // rdi
  const void **v7; // r15
  const void **v8; // r12
  PCERT_EXTENSION Extension; // rax
  PCERT_EXTENSION v10; // r14
  DWORD LastError; // ebx
  unsigned int v12; // ecx
  unsigned int v13; // edx
  __int64 v14; // rsi
  __int64 v15; // rdi
  __int64 v16; // rdi
  __int64 v17; // r15
  __int64 v18; // r8
  unsigned int v19; // eax
  _QWORD *v20; // r15
  unsigned __int16 *v21; // rax
  const void **v22; // rcx
  __int64 v23; // r8
  _WORD *v24; // rcx
  HLOCAL *v25; // r15
  __int64 v26; // rax
  SIZE_T v27; // rsi
  HLOCAL v28; // rax
  PCERT_EXTENSION v29; // rax
  PCERT_EXTENSION v30; // r14
  _WORD *v31; // rcx
  __int64 v32; // r14
  __int64 v33; // rax
  SIZE_T v34; // rbx
  HLOCAL v35; // rax
  _QWORD *v36; // rdx
  __int64 v37; // rax
  __int64 v38; // rax
  HLOCAL v39; // rax
  PCERT_EXTENSION v40; // rax
  PCERT_EXTENSION v41; // r14
  unsigned int i; // edx
  unsigned int v43; // r8d
  __int64 v44; // rdx
  __int64 v45; // rcx
  __int64 v46; // r12
  __int64 v47; // r15
  __int64 v48; // r8
  __int64 v49; // rax
  SIZE_T v50; // r15
  HLOCAL v51; // rax
  unsigned int j; // r15d
  _QWORD *v53; // rax
  __int64 v54; // rcx
  __int64 v55; // rax
  HLOCAL v56; // rax
  HLOCAL *v57; // r14
  unsigned int v59; // [rsp+48h] [rbp-21h]
  unsigned int v60; // [rsp+48h] [rbp-21h]
  unsigned int v61; // [rsp+4Ch] [rbp-1Dh]
  int v62; // [rsp+4Ch] [rbp-1Dh]
  DWORD v63; // [rsp+50h] [rbp-19h] BYREF
  DWORD v64; // [rsp+54h] [rbp-15h] BYREF
  DWORD v65; // [rsp+58h] [rbp-11h] BYREF
  __int64 v66; // [rsp+60h] [rbp-9h]
  size_t Size; // [rsp+68h] [rbp-1h]
  __int64 v68; // [rsp+70h] [rbp+7h]
  DWORD pcbStructInfo; // [rsp+D0h] [rbp+67h] BYREF
  HLOCAL *v70; // [rsp+D8h] [rbp+6Fh]
  HLOCAL *v71; // [rsp+E0h] [rbp+77h]
  DWORD v72; // [rsp+E8h] [rbp+7Fh] BYREF

  v71 = a3;
  v70 = a2;
  pvStructInfo = 0;
  pcbStructInfo = 0;
  v72 = 0;
  v63 = 0;
  v64 = 0;
  v65 = 0;
  if ( !a1 || !a2 || !a3 )
    return 87;
  *a3 = 0;
  v5 = 0;
  *a2 = 0;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  Extension = CertFindExtension("2.5.29.32", a1->pCertInfo->cExtension, a1->pCertInfo->rgExtension);
  v10 = Extension;
  if ( !Extension )
  {
    v29 = CertFindExtension("1.3.6.1.4.1.311.2.1.10", a1->pCertInfo->cExtension, a1->pCertInfo->rgExtension);
    v30 = v29;
    if ( v29 )
    {
      CryptDecodeObject(1u, (LPCSTR)0x7D0, v29->Value.pbData, v29->Value.cbData, 0, 0, &v64);
      v7 = (const void **)LocalAlloc(0x40u, v64);
      if ( !v7 )
        goto LABEL_91;
      if ( !CryptDecodeObject(1u, (LPCSTR)0x7D0, v30->Value.pbData, v30->Value.cbData, 0, v7, &v64) )
        goto LABEL_7;
      if ( !*v7 )
      {
        LastError = -2146885628;
        goto LABEL_92;
      }
      v31 = v7[1];
      v32 = -1;
      if ( v31 )
      {
        v33 = -1;
        do
          ++v33;
        while ( v31[v33] );
        v34 = 2LL * ((int)v33 + 1);
        v35 = LocalAlloc(0x40u, v34);
        *v71 = v35;
        if ( !v35 )
          goto LABEL_91;
        memcpy_0(v35, v7[1], v34);
      }
      v36 = *v7;
      if ( *(_DWORD *)*v7 == 1 )
      {
        v38 = v36[1];
        if ( !v38 )
          goto LABEL_98;
        do
          ++v32;
        while ( *(_WORD *)(v38 + 2 * v32) );
      }
      else
      {
        if ( *(_DWORD *)*v7 != 3 )
          goto LABEL_98;
        v37 = v36[1];
        if ( !v37 )
          goto LABEL_98;
        do
          ++v32;
        while ( *(_WORD *)(v37 + 2 * v32) );
      }
      v39 = LocalAlloc(0x40u, 2LL * ((int)v32 + 1));
      *v70 = v39;
      if ( !v39 )
        goto LABEL_91;
      memcpy_0(v39, *((const void **)*v7 + 1), 2LL * ((int)v32 + 1));
    }
    else
    {
      v40 = CertFindExtension("2.5.29.3", a1->pCertInfo->cExtension, a1->pCertInfo->rgExtension);
      v41 = v40;
      if ( v40 )
      {
        CryptDecodeObject(1u, "2.5.29.3", v40->Value.pbData, v40->Value.cbData, 0, 0, &pcbStructInfo);
        pvStructInfo = LocalAlloc(0x40u, pcbStructInfo);
        if ( !pvStructInfo )
          goto LABEL_91;
        if ( !CryptDecodeObject(1u, "2.5.29.3", v41->Value.pbData, v41->Value.cbData, 0, pvStructInfo, &pcbStructInfo) )
          goto LABEL_7;
        for ( i = 0; ; i = v60 + 1 )
        {
          v60 = i;
          if ( i >= *(_DWORD *)pvStructInfo )
            break;
          v43 = 0;
          v62 = 0;
          v44 = 3LL * i;
          v66 = v44;
          while ( 1 )
          {
            v45 = pvStructInfo[1];
            if ( v43 >= *(_DWORD *)(v45 + 8 * v44 + 8) )
              break;
            v46 = *(_QWORD *)(v45 + 8 * v44 + 16);
            v47 = 3LL * v43;
            if ( !strcmp_0("2.16.840.1.113733.1.7.1.1", *(const char **)(v46 + 24LL * v43)) )
            {
              CryptDecodeObject(
                1u,
                "2.16.840.1.113733.1.7.1.1",
                *(const BYTE **)(v46 + 8 * v47 + 16),
                *(_DWORD *)(v46 + 8 * v47 + 8),
                0,
                0,
                &v65);
              v8 = (const void **)LocalAlloc(0x40u, v65);
              if ( !v8 )
                goto LABEL_90;
              v48 = *(_QWORD *)(pvStructInfo[1] + 8 * v66 + 16);
              if ( !CryptDecodeObject(
                      1u,
                      "2.16.840.1.113733.1.7.1.1",
                      *(const BYTE **)(v48 + 8 * v47 + 16),
                      *(_DWORD *)(v48 + 8 * v47 + 8),
                      0,
                      v8,
                      &v65) )
              {
                LastError = GetLastError();
                v7 = 0;
                goto LABEL_92;
              }
              if ( *v8 && !*v71 )
              {
                v49 = -1;
                do
                  ++v49;
                while ( *((_WORD *)*v8 + v49) );
                v50 = 2LL * ((int)v49 + 1);
                v51 = LocalAlloc(0x40u, v50);
                *v71 = v51;
                if ( !v51 )
                {
LABEL_90:
                  v7 = 0;
                  goto LABEL_91;
                }
                memcpy_0(v51, *v8, v50);
              }
              for ( j = 0; j < *((_DWORD *)v8 + 6); ++j )
              {
                v53 = v8[4];
                v68 = 3LL * j;
                v54 = v53[3 * j];
                if ( v54 && !*v70 )
                {
                  v55 = -1;
                  do
                    ++v55;
                  while ( *(_WORD *)(v54 + 2 * v55) );
                  Size = 2LL * ((int)v55 + 1);
                  v56 = LocalAlloc(0x40u, Size);
                  *v70 = v56;
                  if ( !v56 )
                    goto LABEL_90;
                  memcpy_0(v56, *((const void **)v8[4] + v68), Size);
                }
              }
              LocalFree(v8);
            }
            v44 = v66;
            v43 = ++v62;
          }
        }
        v7 = 0;
      }
    }
LABEL_98:
    LastError = 0;
    v5 = 0;
    v6 = 0;
    v8 = 0;
    if ( !*v70 && !*v71 )
      LastError = -2146885628;
    goto LABEL_101;
  }
  CryptDecodeObject(1u, "2.5.29.32", Extension->Value.pbData, Extension->Value.cbData, 0, 0, &pcbStructInfo);
  pvStructInfo = LocalAlloc(0x40u, pcbStructInfo);
  if ( !pvStructInfo )
  {
LABEL_91:
    LastError = 14;
    goto LABEL_92;
  }
  if ( !CryptDecodeObject(1u, "2.5.29.32", v10->Value.pbData, v10->Value.cbData, 0, pvStructInfo, &pcbStructInfo) )
  {
LABEL_7:
    LastError = GetLastError();
    goto LABEL_92;
  }
  v12 = 0;
LABEL_9:
  v61 = v12;
  if ( v12 >= *(_DWORD *)pvStructInfo )
  {
    v7 = 0;
    goto LABEL_98;
  }
  v13 = 0;
  v14 = 3LL * v12;
  v66 = v14;
  while ( 1 )
  {
    v15 = pvStructInfo[1];
    v59 = v13;
    if ( v13 >= *(_DWORD *)(v15 + 8 * v14 + 8) )
    {
      v12 = v61 + 1;
      goto LABEL_9;
    }
    v16 = *(_QWORD *)(v15 + 8 * v14 + 16);
    v17 = 3LL * v13;
    if ( strcmp_0("1.3.6.1.5.5.7.2.1", *(const char **)(v16 + 24LL * v13)) )
      break;
    CryptDecodeObject(
      1u,
      (LPCSTR)0x18,
      *(const BYTE **)(v16 + 8 * v17 + 16),
      *(_DWORD *)(v16 + 8 * v17 + 8),
      0,
      0,
      &v72);
    v5 = (const unsigned __int16 **)LocalAlloc(0x40u, v72);
    if ( !v5 )
      goto LABEL_34;
    v18 = *(_QWORD *)(pvStructInfo[1] + 8 * v66 + 16);
    if ( !CryptDecodeObject(
            1u,
            (LPCSTR)0x18,
            *(const BYTE **)(v18 + 8 * v17 + 16),
            *(_DWORD *)(v18 + 8 * v17 + 8),
            0,
            v5,
            &v72) )
    {
      LastError = GetLastError();
      goto LABEL_38;
    }
    v19 = *((_DWORD *)v5 + 2);
    if ( v19 )
    {
      v20 = v70;
      if ( !*v70 )
      {
        if ( v19 + 2 < v19 )
        {
          LastError = 13;
LABEL_38:
          v6 = 0;
          goto LABEL_39;
        }
        v21 = (unsigned __int16 *)LocalAlloc(0x40u, v19 + 2);
        *v20 = v21;
        if ( !v21 )
        {
LABEL_34:
          v6 = 0;
LABEL_35:
          v7 = 0;
          goto LABEL_91;
        }
        StringCbCopyW(v21, *((unsigned int *)v5 + 2) + 2LL, v5[2]);
      }
    }
    v22 = (const void **)v5;
LABEL_31:
    LocalFree(v22);
LABEL_32:
    v14 = v66;
    v13 = v59 + 1;
  }
  if ( strcmp_0("1.3.6.1.5.5.7.2.2", *(const char **)(v16 + 8 * v17)) )
    goto LABEL_32;
  CryptDecodeObject(
    1u,
    "1.3.6.1.5.5.7.2.2",
    *(const BYTE **)(v16 + 8 * v17 + 16),
    *(_DWORD *)(v16 + 8 * v17 + 8),
    0,
    0,
    &v63);
  v6 = (const void **)LocalAlloc(0x40u, v63);
  if ( !v6 )
    goto LABEL_40;
  v23 = *(_QWORD *)(pvStructInfo[1] + 8 * v14 + 16);
  if ( CryptDecodeObject(
         1u,
         "1.3.6.1.5.5.7.2.2",
         *(const BYTE **)(v23 + 8 * v17 + 16),
         *(_DWORD *)(v23 + 8 * v17 + 8),
         0,
         v6,
         &v63) )
  {
    v24 = v6[1];
    if ( v24 )
    {
      v25 = v71;
      if ( !*v71 )
      {
        v26 = -1;
        do
          ++v26;
        while ( v24[v26] );
        v27 = 2LL * ((int)v26 + 1);
        v28 = LocalAlloc(0x40u, v27);
        *v25 = v28;
        if ( !v28 )
        {
LABEL_40:
          v5 = 0;
          goto LABEL_35;
        }
        memcpy_0(v28, v6[1], v27);
      }
    }
    v22 = v6;
    goto LABEL_31;
  }
  LastError = GetLastError();
  v5 = 0;
LABEL_39:
  v7 = 0;
LABEL_92:
  if ( *v70 )
  {
    LocalFree(*v70);
    *v70 = 0;
  }
  v57 = v71;
  if ( *v71 )
  {
    LocalFree(*v71);
    *v57 = 0;
  }
LABEL_101:
  if ( v7 )
    LocalFree(v7);
  if ( pvStructInfo )
    LocalFree(pvStructInfo);
  if ( v6 )
    LocalFree(v6);
  if ( v5 )
    LocalFree(v5);
  if ( v8 )
    LocalFree(v8);
  return LastError;
}

```

## disassembly

```asm
0x180007ff8  mov     [rsp-8+arg_10], r8
0x180007ffd  mov     [rsp-8+arg_8], rdx
0x180008002  push    rbp
0x180008003  push    rbx
0x180008004  push    rsi
0x180008005  push    rdi
0x180008006  push    r12
0x180008008  push    r13
0x18000800a  push    r14
0x18000800c  push    r15
0x18000800e  lea     rbp, [rsp-1Fh]
0x180008013  sub     rsp, 88h
0x18000801a  xor     r13d, r13d
0x18000801d  mov     rax, rdx
0x180008020  mov     [rbp+57h+arg_0], r13d
0x180008024  mov     rbx, rcx
0x180008027  mov     [rbp+57h+arg_18], r13d
0x18000802b  mov     [rbp+57h+var_70], r13d
0x18000802f  mov     [rbp+57h+var_6C], r13d
0x180008033  mov     [rbp+57h+var_68], r13d
0x180008037  test    rcx, rcx
0x18000803a  jz      loc_180008870
0x180008040  test    rax, rax
0x180008043  jz      loc_180008870
0x180008049  test    r8, r8
0x18000804c  jz      loc_180008870
0x180008052  mov     [r8], r13
0x180008055  mov     esi, r13d
0x180008058  mov     [rdx], r13
0x18000805b  mov     edi, r13d
0x18000805e  mov     rdx, [rcx+18h]
0x180008062  mov     r15d, r13d
0x180008065  lea     rcx, szStructType; "2.5.29.32"
0x18000806c  mov     r12d, r13d
0x18000806f  mov     r8, [rdx+0C8h]; rgExtensions
0x180008076  mov     edx, [rdx+0C0h]; cExtensions
0x18000807c  call    cs:__imp_CertFindExtension
0x180008082  mov     r14, rax
0x180008085  test    rax, rax
0x180008088  jz      loc_180008395
0x18000808e  mov     r9d, [r14+10h]; cbEncoded
0x180008092  lea     rax, [rbp+57h+arg_0]
0x180008096  mov     r8, [r14+18h]; pbEncoded
0x18000809a  lea     ebx, [r13+1]
0x18000809e  mov     [rsp+0C0h+pcbStructInfo], rax; pcbStructInfo
0x1800080a3  lea     rdx, szStructType; "2.5.29.32"
0x1800080aa  mov     [rsp+0C0h+pvStructInfo], r13; pvStructInfo
0x1800080af  mov     ecx, ebx; dwCertEncodingType
0x1800080b1  mov     [rsp+0C0h+dwFlags], r13d; dwFlags
0x1800080b6  call    cs:__imp_CryptDecodeObject
0x1800080bc  mov     edx, [rbp+57h+arg_0]; uBytes
0x1800080bf  lea     ecx, [rbx+3Fh]; uFlags
0x1800080c2  call    cs:__imp_LocalAlloc
0x1800080c8  xor     r9d, r9d
0x1800080cb  mov     r13, rax
0x1800080ce  test    rax, rax
0x1800080d1  jz      loc_1800087C0
0x1800080d7  mov     r8, [r14+18h]; pbEncoded
0x1800080db  lea     rax, [rbp+57h+arg_0]
0x1800080df  mov     [rsp+0C0h+pcbStructInfo], rax; pcbStructInfo
0x1800080e4  lea     rdx, szStructType; "2.5.29.32"
0x1800080eb  mov     [rsp+0C0h+pvStructInfo], r13; pvStructInfo
0x1800080f0  mov     ecx, ebx; dwCertEncodingType
0x1800080f2  mov     [rsp+0C0h+dwFlags], r9d; dwFlags
0x1800080f7  mov     r9d, [r14+10h]; cbEncoded
0x1800080fb  call    cs:__imp_CryptDecodeObject
0x180008101  xor     r9d, r9d
0x180008104  test    eax, eax
0x180008106  jnz     short loc_180008115
0x180008108  call    cs:__imp_GetLastError
0x18000810e  mov     ebx, eax
0x180008110  jmp     loc_1800087C5
0x180008115  mov     ecx, r9d
0x180008118  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000811c  mov     [rbp+57h+var_74], ecx
0x18000811f  cmp     ecx, [r13+0]
0x180008123  jnb     loc_1800087FB
0x180008129  mov     eax, ecx
0x18000812b  mov     edx, r9d
0x18000812e  lea     rsi, [rax+rax*2]
0x180008132  mov     [rbp+57h+var_60], rsi
0x180008136  mov     rdi, [r13+8]
0x18000813a  mov     [rbp+57h+var_78], edx
0x18000813d  cmp     edx, [rdi+rsi*8+8]
0x180008141  jnb     loc_18000834E
0x180008147  mov     rdi, [rdi+rsi*8+10h]
0x18000814c  lea     rcx, Str1; "1.3.6.1.5.5.7.2.1"
0x180008153  mov     eax, edx
0x180008155  lea     r15, [rax+rax*2]
0x180008159  mov     rdx, [rdi+r15*8]; Str2
0x18000815d  call    strcmp_0
0x180008162  xor     edx, edx
0x180008164  test    eax, eax
0x180008166  jnz     loc_180008243
0x18000816c  mov     r9d, [rdi+r15*8+8]; cbEncoded
0x180008171  lea     rax, [rbp+57h+arg_18]
0x180008175  mov     r8, [rdi+r15*8+10h]; pbEncoded
0x18000817a  mov     ecx, ebx; dwCertEncodingType
0x18000817c  mov     [rsp+0C0h+pcbStructInfo], rax; pcbStructInfo
0x180008181  mov     [rsp+0C0h+pvStructInfo], rdx; pvStructInfo
0x180008186  mov     [rsp+0C0h+dwFlags], edx; dwFlags
0x18000818a  mov     edx, 18h; lpszStructType
0x18000818f  call    cs:__imp_CryptDecodeObject
0x180008195  mov     edx, [rbp+57h+arg_18]; uBytes
0x180008198  mov     edi, 40h ; '@'
0x18000819d  mov     ecx, edi; uFlags
0x18000819f  call    cs:__imp_LocalAlloc
0x1800081a5  xor     r9d, r9d
0x1800081a8  mov     rsi, rax
0x1800081ab  test    rax, rax
0x1800081ae  jz      loc_180008358
0x1800081b4  mov     rcx, [r13+8]
0x1800081b8  lea     rax, [rbp+57h+arg_18]
0x1800081bc  mov     r8, [rbp+57h+var_60]
0x1800081c0  lea     edx, [rdi-28h]; lpszStructType
0x1800081c3  mov     [rsp+0C0h+pcbStructInfo], rax; pcbStructInfo
0x1800081c8  mov     [rsp+0C0h+pvStructInfo], rsi; pvStructInfo
0x1800081cd  mov     [rsp+0C0h+dwFlags], r9d; dwFlags
0x1800081d2  mov     r8, [rcx+r8*8+10h]
0x1800081d7  mov     ecx, ebx; dwCertEncodingType
0x1800081d9  mov     r9d, [r8+r15*8+8]; cbEncoded
0x1800081de  mov     r8, [r8+r15*8+10h]; pbEncoded
0x1800081e3  call    cs:__imp_CryptDecodeObject
0x1800081e9  xor     r9d, r9d
0x1800081ec  test    eax, eax
0x1800081ee  jz      loc_18000836A
0x1800081f4  mov     eax, [rsi+8]
0x1800081f7  test    eax, eax
0x1800081f9  jz      short loc_18000823B
0x1800081fb  mov     r15, [rbp+57h+arg_8]
0x1800081ff  cmp     [r15], r9
0x180008202  jnz     short loc_18000823B
0x180008204  lea     ecx, [rax+2]
0x180008207  cmp     ecx, eax
0x180008209  jb      loc_180008363
0x18000820f  mov     edx, ecx; uBytes
0x180008211  mov     ecx, edi; uFlags
0x180008213  call    cs:__imp_LocalAlloc
0x180008219  xor     r9d, r9d
0x18000821c  mov     [r15], rax
0x18000821f  test    rax, rax
0x180008222  jz      loc_180008358
0x180008228  mov     edx, [rsi+8]
0x18000822b  mov     rcx, rax; unsigned __int16 *
0x18000822e  mov     r8, [rsi+10h]; unsigned __int16 *
0x180008232  add     rdx, 2; unsigned __int64
0x180008236  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18000823b  mov     rcx, rsi
0x18000823e  jmp     loc_180008337
0x180008243  mov     rdx, [rdi+r15*8]; Str2
0x180008247  lea     rcx, a136155722; "1.3.6.1.5.5.7.2.2"
0x18000824e  call    strcmp_0
0x180008253  xor     r9d, r9d
0x180008256  test    eax, eax
0x180008258  jnz     loc_180008340
0x18000825e  mov     r8, [rdi+r15*8+10h]; pbEncoded
0x180008263  lea     rax, [rbp+57h+var_70]
0x180008267  mov     [rsp+0C0h+pcbStructInfo], rax; pcbStructInfo
0x18000826c  lea     rdx, a136155722; "1.3.6.1.5.5.7.2.2"
0x180008273  mov     [rsp+0C0h+pvStructInfo], r9; pvStructInfo
0x180008278  mov     ecx, ebx; dwCertEncodingType
0x18000827a  mov     [rsp+0C0h+dwFlags], r9d; dwFlags
0x18000827f  mov     r9d, [rdi+r15*8+8]; cbEncoded
0x180008284  call    cs:__imp_CryptDecodeObject
0x18000828a  mov     edx, [rbp+57h+var_70]; uBytes
0x18000828d  mov     ecx, 40h ; '@'; uFlags
0x180008292  call    cs:__imp_LocalAlloc
0x180008298  xor     r9d, r9d
0x18000829b  mov     rdi, rax
0x18000829e  test    rax, rax
0x1800082a1  jz      loc_180008380
0x1800082a7  mov     rcx, [r13+8]
0x1800082ab  lea     rax, [rbp+57h+var_70]
0x1800082af  mov     [rsp+0C0h+pcbStructInfo], rax; pcbStructInfo
0x1800082b4  lea     rdx, a136155722; "1.3.6.1.5.5.7.2.2"
0x1800082bb  mov     [rsp+0C0h+pvStructInfo], rdi; pvStructInfo
0x1800082c0  mov     [rsp+0C0h+dwFlags], r9d; dwFlags
0x1800082c5  mov     r8, [rcx+rsi*8+10h]
0x1800082ca  mov     ecx, ebx; dwCertEncodingType
0x1800082cc  mov     r9d, [r8+r15*8+8]; cbEncoded
0x1800082d1  mov     r8, [r8+r15*8+10h]; pbEncoded
0x1800082d6  call    cs:__imp_CryptDecodeObject
0x1800082dc  xor     edx, edx
0x1800082de  test    eax, eax
0x1800082e0  jz      loc_180008385
0x1800082e6  mov     rcx, [rdi+8]
0x1800082ea  test    rcx, rcx
0x1800082ed  jz      short loc_180008334
0x1800082ef  mov     r15, [rbp+57h+arg_10]
0x1800082f3  cmp     [r15], rdx
0x1800082f6  jnz     short loc_180008334
0x1800082f8  mov     rax, r14
0x1800082fb  inc     rax
0x1800082fe  cmp     [rcx+rax*2], dx
0x180008302  jnz     short loc_1800082FB
0x180008304  inc     eax
0x180008306  mov     ecx, 40h ; '@'; uFlags
0x18000830b  movsxd  rsi, eax
0x18000830e  add     rsi, rsi
0x180008311  mov     rdx, rsi; uBytes
0x180008314  call    cs:__imp_LocalAlloc
0x18000831a  xor     r9d, r9d
0x18000831d  mov     [r15], rax
0x180008320  test    rax, rax
0x180008323  jz      short loc_180008380
0x180008325  mov     rdx, [rdi+8]; Src
0x180008329  mov     r8, rsi; Size
0x18000832c  mov     rcx, rax; void *
0x18000832f  call    memcpy_0
0x180008334  mov     rcx, rdi; hMem
0x180008337  call    cs:__imp_LocalFree
0x18000833d  xor     r9d, r9d
0x180008340  mov     edx, [rbp+57h+var_78]
0x180008343  mov     rsi, [rbp+57h+var_60]
0x180008347  add     edx, ebx
0x180008349  jmp     loc_180008136
0x18000834e  mov     ecx, [rbp+57h+var_74]
0x180008351  add     ecx, ebx
0x180008353  jmp     loc_18000811C
0x180008358  mov     rdi, r9
0x18000835b  mov     r15, r9
0x18000835e  jmp     loc_1800087C0
0x180008363  mov     ebx, 0Dh
0x180008368  jmp     short loc_180008375
0x18000836a  call    cs:__imp_GetLastError
0x180008370  mov     ebx, eax
0x180008372  xor     r9d, r9d
0x180008375  mov     rdi, r9
0x180008378  mov     r15, r9
0x18000837b  jmp     loc_1800087C5
0x180008380  mov     rsi, r9
0x180008383  jmp     short loc_18000835B
0x180008385  call    cs:__imp_GetLastError
0x18000838b  xor     r9d, r9d
0x18000838e  mov     ebx, eax
0x180008390  mov     esi, r9d
0x180008393  jmp     short loc_180008378
0x180008395  mov     rdx, [rbx+18h]
0x180008399  lea     rcx, pszObjId; "1.3.6.1.4.1.311.2.1.10"
0x1800083a0  mov     r8, [rdx+0C8h]; rgExtensions
0x1800083a7  mov     edx, [rdx+0C0h]; cExtensions
0x1800083ad  call    cs:__imp_CertFindExtension
0x1800083b3  xor     edx, edx
0x1800083b5  mov     r14, rax
0x1800083b8  test    rax, rax
0x1800083bb  jz      loc_180008521
0x1800083c1  mov     r9d, [r14+10h]; cbEncoded
0x1800083c5  lea     rax, [rbp+57h+var_6C]
0x1800083c9  mov     r8, [r14+18h]; pbEncoded
0x1800083cd  mov     ebx, 1
0x1800083d2  mov     [rsp+0C0h+pcbStructInfo], rax; pcbStructInfo
0x1800083d7  mov     ecx, ebx; dwCertEncodingType
0x1800083d9  mov     [rsp+0C0h+pvStructInfo], rdx; pvStructInfo
0x1800083de  mov     [rsp+0C0h+dwFlags], edx; dwFlags
0x1800083e2  mov     edx, 7D0h; lpszStructType
0x1800083e7  call    cs:__imp_CryptDecodeObject
0x1800083ed  mov     edx, [rbp+57h+var_6C]; uBytes
0x1800083f0  lea     ecx, [rbx+3Fh]; uFlags
0x1800083f3  call    cs:__imp_LocalAlloc
0x1800083f9  xor     r9d, r9d
0x1800083fc  mov     r15, rax
0x1800083ff  test    rax, rax
0x180008402  jz      loc_1800087C0
0x180008408  mov     r8, [r14+18h]; pbEncoded
0x18000840c  lea     rax, [rbp+57h+var_6C]
0x180008410  mov     [rsp+0C0h+pcbStructInfo], rax; pcbStructInfo
0x180008415  mov     edx, 7D0h; lpszStructType
0x18000841a  mov     [rsp+0C0h+pvStructInfo], r15; pvStructInfo
0x18000841f  mov     ecx, ebx; dwCertEncodingType
0x180008421  mov     [rsp+0C0h+dwFlags], r9d; dwFlags
0x180008426  mov     r9d, [r14+10h]; cbEncoded
0x18000842a  call    cs:__imp_CryptDecodeObject
0x180008430  xor     r9d, r9d
0x180008433  test    eax, eax
0x180008435  jz      loc_180008108
0x18000843b  cmp     [r15], r9
0x18000843e  jnz     short loc_18000844A
0x180008440  mov     ebx, 80092004h
0x180008445  jmp     loc_1800087C5
0x18000844a  mov     rcx, [r15+8]
0x18000844e  or      r14, 0FFFFFFFFFFFFFFFFh
0x180008452  test    rcx, rcx
0x180008455  jz      short loc_18000849C
0x180008457  mov     rax, r14
0x18000845a  inc     rax
0x18000845d  cmp     [rcx+rax*2], r9w
0x180008462  jnz     short loc_18000845A
0x180008464  inc     eax
0x180008466  mov     ecx, 40h ; '@'; uFlags
0x18000846b  movsxd  rbx, eax
0x18000846e  add     rbx, rbx
0x180008471  mov     rdx, rbx; uBytes
0x180008474  call    cs:__imp_LocalAlloc
0x18000847a  mov     rcx, [rbp+57h+arg_10]
0x18000847e  mov     [rcx], rax
0x180008481  test    rax, rax
0x180008484  jz      loc_1800087C0
0x18000848a  mov     rdx, [r15+8]; Src
0x18000848e  mov     r8, rbx; Size
0x180008491  mov     rcx, rax; void *
  ... truncated ...
```
