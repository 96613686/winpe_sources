# CertificateOcspGetObjectUrl

- ea: `0x180014750`
- end: `0x180014de8`
- name: `CertificateOcspGetObjectUrl`
- size: `1688`
- prototype: `__int64 __fastcall(__int64, __int64, char, __int64, ULONG *, __int64, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180013ab0`
- `0x180014750`
- `0x180014df0`
- `0x18001acb4`
- `0x180026552`
- `0x180026576`
- `0x1800265b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014956`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014a2d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014a72`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014b58`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014c77`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014cff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014d6d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014d78`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014d83`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014da5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014dd3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014956`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014a2d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014a72`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014b58`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014c77`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014cff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014d6d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014d78`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014d83`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014da5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014dd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014a1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014a5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014a1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014a5f`
- `CRYPT32!CryptMemAlloc` at `0x180014b41`
- `CRYPT32!CryptMemAlloc` at `0x180014c4d`
- `CRYPT32!CryptMemAlloc` at `0x180014b41`
- `CRYPT32!CryptMemAlloc` at `0x180014c4d`
- `CRYPT32!CryptMemFree` at `0x180014a00`
- `CRYPT32!CryptMemFree` at `0x180014db3`
- `CRYPT32!CryptMemFree` at `0x180014a00`
- `CRYPT32!CryptMemFree` at `0x180014db3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180014b02`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180014d54`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180014b02`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180014d54`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014872`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014872`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014a25`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014a6a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014a25`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014a6a`

## pseudocode

```c
__int64 __fastcall CertificateOcspGetObjectUrl(
        __int64 a1,
        __int64 a2,
        char a3,
        __int64 a4,
        ULONG *a5,
        __int64 a6,
        __int64 a7)
{
  int v8; // ebx
  __int64 result; // rax
  int v10; // r14d
  bool v11; // zf
  unsigned int v12; // r14d
  unsigned int v13; // r12d
  _QWORD *v14; // rax
  LPVOID *v15; // r13
  int v16; // ecx
  int v17; // esi
  unsigned int v18; // edi
  __int64 v19; // r13
  unsigned int v20; // r15d
  unsigned int v21; // r15d
  HLOCAL v22; // rdi
  __int64 v23; // r14
  __int64 v24; // rbx
  const WCHAR *lpString2; // rbx
  HLOCAL *v26; // r9
  unsigned int v27; // ebx
  int v28; // r8d
  __int64 k; // rdx
  __int64 v30; // rcx
  __int64 v31; // rax
  ULONG v32; // eax
  __int64 i; // rbx
  DWORD LastError; // ebx
  unsigned int j; // ebx
  void *v36; // rsi
  DWORD v37; // edi
  unsigned __int64 v38; // r9
  const WCHAR *v39; // rcx
  unsigned __int64 cchCount2; // rcx
  const WCHAR *v41; // rdx
  __int64 v42; // rax
  unsigned int v43; // r12d
  void *v44; // rax
  void *v45; // rsi
  _QWORD *v46; // rcx
  _QWORD *v47; // r15
  unsigned int v48; // esi
  __int64 v49; // rdi
  unsigned int v50; // r14d
  __int64 v51; // r12
  _WORD *v52; // rdx
  __int64 v53; // rbx
  unsigned int v54; // ebx
  unsigned int v55; // r12d
  __int64 v56; // rax
  unsigned __int64 v57; // r9
  const WCHAR *v58; // rcx
  unsigned __int64 v59; // rcx
  const WCHAR *v60; // rdx
  __int64 v61; // [rsp+40h] [rbp-C0h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-B8h]
  unsigned int v63; // [rsp+50h] [rbp-B0h]
  unsigned int v64; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD *v65; // [rsp+60h] [rbp-A0h]
  int v66; // [rsp+68h] [rbp-98h]
  int v67; // [rsp+6Ch] [rbp-94h]
  ULONG *v68; // [rsp+70h] [rbp-90h]
  __int64 v69; // [rsp+80h] [rbp-80h] BYREF
  __int64 v70; // [rsp+88h] [rbp-78h]
  __int64 v71; // [rsp+90h] [rbp-70h]
  __int64 v72; // [rsp+98h] [rbp-68h]
  _BYTE v73[8]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v74[9]; // [rsp+A8h] [rbp-58h]

  v68 = a5;
  v72 = a6;
  v71 = a7;
  v70 = a4;
  v61 = 0x400000001LL;
  if ( (a3 & 1) != 0
    && (unsigned int)ObjectContextGetRawUrlData((char *)1, "1.3.6.1.4.1.311.10.11.85", v73, (__int64)&v61) )
  {
    v8 = v61;
  }
  else
  {
    v8 = 0;
  }
  result = ObjectContextGetRawUrlData((char *)1, "1.3.6.1.5.5.7.1.1", &v73[16 * v8], (__int64)&v61 + 4);
  v10 = HIDWORD(v61);
  if ( !(_DWORD)result )
    v10 = 0;
  v11 = v8 + v10 == 0;
  v12 = v8 + v10;
  v63 = v12;
  if ( !v11 )
  {
    v13 = 0;
    v64 = 0;
    v69 = a4;
    v67 = 5;
    v14 = LocalAlloc(0x40u, 8u);
    hMem = v14;
    v15 = (LPVOID *)v14;
    if ( !v14 )
    {
      SetLastError(0x8007000E);
      SetLastError(8u);
      SetLastError(0x8007000E);
      v20 = 0;
      goto LABEL_36;
    }
    v16 = 1;
    v65 = v14;
    LODWORD(v61) = 1;
    v17 = 0;
    *v14 = 0;
    v18 = 0;
    v66 = 1;
    HIDWORD(v61) = 0;
    while ( v18 < v12 )
    {
      v19 = v74[2 * v18];
      if ( v19 )
      {
        v21 = 0;
        if ( *(_DWORD *)v19 )
        {
          v22 = hMem;
          v23 = *(_QWORD *)(v19 + 8);
          while ( 1 )
          {
            if ( v16 != 1 )
            {
LABEL_21:
              v12 = v63;
              hMem = v22;
              v18 = HIDWORD(v61);
              goto LABEL_11;
            }
            v24 = 32LL * v21;
            if ( !strcmp_0("1.3.6.1.5.5.7.48.1", *(const char **)(v24 + v23)) && *(_DWORD *)(v24 + v23 + 8) == 7 )
            {
              lpString2 = *(const WCHAR **)(v24 + v23 + 16);
              if ( lpString2 )
              {
                for ( ; *lpString2 == 32; ++lpString2 )
                  ;
                v38 = 0;
                v39 = L"http";
                do
                {
                  if ( !*v39 )
                    break;
                  ++v38;
                  ++v39;
                }
                while ( v38 < 4 );
                cchCount2 = 0;
                v41 = lpString2;
                do
                {
                  if ( !*v41 )
                    break;
                  ++cchCount2;
                  ++v41;
                }
                while ( cchCount2 < 4 );
                if ( CompareStringW(0x409u, 1u, L"http", v38, lpString2, cchCount2) == 2 )
                  break;
                v57 = 0;
                v58 = L"post";
                do
                {
                  if ( !*v58 )
                    break;
                  ++v57;
                  ++v58;
                }
                while ( v57 < 4 );
                v59 = 0;
                v60 = lpString2;
                do
                {
                  if ( !*v60 )
                    break;
                  ++v59;
                  ++v60;
                }
                while ( v59 < 4 );
                if ( CompareStringW(0x409u, 1u, L"post", v57, lpString2, v59) == 2 )
                  break;
              }
            }
            v16 = v61;
LABEL_20:
            if ( ++v21 >= *(_DWORD *)v19 )
              goto LABEL_21;
          }
          v42 = -1;
          do
            v11 = lpString2[++v42] == 0;
          while ( !v11 );
          v43 = v42 + 1;
          if ( (unsigned int)(v42 + 1) > 0xFFFF )
          {
            SetLastError(0x216u);
LABEL_59:
            SetLastError(0x8007000E);
            v16 = 0;
            LODWORD(v61) = 0;
          }
          else
          {
            v44 = CryptMemAlloc(2 * v43);
            v45 = v44;
            if ( !v44 )
              goto LABEL_59;
            memcpy_0(v44, lpString2, 2LL * v43);
            v55 = v64;
            v16 = 1;
            LODWORD(v61) = 1;
            if ( v66 != v64 )
              goto LABEL_80;
            LODWORD(v61) = CCryptUrlArray::GrowArray((CCryptUrlArray *)&v64);
            v16 = v61;
            if ( (_DWORD)v61 == 1 )
            {
              v22 = v65;
              v55 = v64;
LABEL_80:
              v56 = v55;
              v13 = v55 + 1;
              v64 = v13;
              *((_QWORD *)v22 + v56) = v45;
              v17 = 1;
              goto LABEL_20;
            }
            CryptMemFree(v45);
            v16 = v61;
            v22 = v65;
          }
          v13 = v64;
          v17 = 1;
          goto LABEL_20;
        }
      }
LABEL_11:
      HIDWORD(v61) = ++v18;
      if ( v16 != 1 )
      {
        v15 = (LPVOID *)hMem;
        v20 = v61;
        goto LABEL_36;
      }
    }
    if ( !v17 )
    {
      SetLastError(0x80092004);
      v15 = (LPVOID *)hMem;
      v20 = 0;
LABEL_36:
      for ( i = 0; (unsigned int)i < v13; i = (unsigned int)(i + 1) )
        CryptMemFree(v15[i]);
      if ( v15 )
      {
        LastError = GetLastError();
        LocalFree(v15);
        SetLastError(LastError);
      }
      for ( j = 0; j < v12; ++j )
      {
        v36 = (void *)v74[2 * j];
        if ( v36 )
        {
          v37 = GetLastError();
          LocalFree(v36);
          SetLastError(v37);
        }
      }
      return v20;
    }
    v15 = (LPVOID *)hMem;
    v26 = (HLOCAL *)&v69;
    v27 = v13;
    if ( !v70 )
      v26 = 0;
    v28 = 0;
    for ( k = 0; (unsigned int)k < v13; v28 += 2 * v31 + 2 )
    {
      v30 = *((_QWORD *)hMem + k);
      if ( v30 )
      {
        v31 = -1;
        do
          ++v31;
        while ( *(_WORD *)(v30 + 2 * v31) );
      }
      else
      {
        LODWORD(v31) = 0;
      }
      k = (unsigned int)(k + 1);
    }
    v32 = v27 * 8 + v28 + 16;
    HIDWORD(v61) = v32;
    if ( !v26 )
    {
      if ( v68 )
      {
        *v68 = v32;
LABEL_34:
        v20 = 1;
        if ( v71 )
          InitializeDefaultUrlInfo(v72);
        goto LABEL_36;
      }
LABEL_83:
      SetLastError(0x80070057);
      v20 = 0;
      goto LABEL_36;
    }
    v46 = *v26;
    hMem = v46;
    if ( v46 )
    {
      if ( !v68 || *v68 < v32 )
        goto LABEL_83;
      v47 = v46;
    }
    else
    {
      v47 = CryptMemAlloc(v32);
      if ( !v47 )
      {
        SetLastError(0x8007000E);
        v20 = 0;
        goto LABEL_36;
      }
      v46 = hMem;
    }
    v48 = 0;
    *(_DWORD *)v47 = v13;
    v49 = 0;
    v47[1] = v47 + 2;
    if ( v13 )
    {
      v50 = v64;
      v51 = (__int64)&v47[v27 + 2];
      do
      {
        *(_QWORD *)(8 * v49 + v47[1]) = v51 + v48;
        v52 = v15[v49];
        if ( v52 )
        {
          v53 = -1;
          do
            ++v53;
          while ( v52[v53] );
        }
        else
        {
          LODWORD(v53) = 0;
        }
        v54 = 2 * v53 + 2;
        memcpy_0(*(void **)(8 * v49 + v47[1]), v52, v54);
        v48 += v54;
        v49 = (unsigned int)(v49 + 1);
      }
      while ( (unsigned int)v49 < v50 );
      v12 = v63;
      v13 = v64;
      v46 = hMem;
    }
    if ( v46 != v47 && v68 )
      *v68 = HIDWORD(v61);
    goto LABEL_34;
  }
  return result;
}

```

## disassembly

```asm
0x180014750  push    rbp
0x180014752  push    rbx
0x180014753  push    rsi
0x180014754  push    rdi
0x180014755  push    r14
0x180014757  push    r15
0x180014759  lea     rbp, [rsp-8]
0x18001475e  sub     rsp, 108h
0x180014765  mov     rax, cs:__security_cookie
0x18001476c  xor     rax, rsp
0x18001476f  mov     [rbp+30h+var_40], rax
0x180014773  mov     rax, [rbp+30h+arg_20]
0x180014777  mov     r15, r9
0x18001477a  mov     [rsp+130h+var_C0], rax
0x18001477f  mov     esi, r8d
0x180014782  mov     rax, [rbp+30h+arg_28]
0x180014786  mov     rdi, rdx
0x180014789  mov     [rbp+30h+var_98], rax
0x18001478d  mov     rax, [rbp+30h+arg_30]
0x180014791  mov     [rbp+30h+var_A0], rax
0x180014795  mov     [rbp+30h+var_A8], r9
0x180014799  mov     dword ptr [rsp+130h+var_F0], 1
0x1800147a1  mov     dword ptr [rsp+130h+var_F0+4], 4
0x1800147a9  test    r8b, 1
0x1800147ad  jz      short loc_1800147E9
0x1800147af  lea     rax, [rsp+130h+var_F0]
0x1800147b4  mov     ecx, 1; char *
0x1800147b9  mov     [rsp+130h+var_100], rax; __int64
0x1800147be  mov     r9d, ecx
0x1800147c1  lea     rax, [rbp+30h+var_90]
0x1800147c5  mov     r8d, 0FFFFFFFFh
0x1800147cb  mov     qword ptr [rsp+130h+cchCount2], rax; void *
0x1800147d0  lea     rax, a13614131110118; "1.3.6.1.4.1.311.10.11.85"
0x1800147d7  mov     [rsp+130h+lpString2], rax; Str1
0x1800147dc  call    ObjectContextGetRawUrlData
0x1800147e1  test    eax, eax
0x1800147e3  jnz     loc_180014C69
0x1800147e9  xor     ebx, ebx
0x1800147eb  mov     eax, ebx
0x1800147ed  lea     rcx, [rbp+30h+var_90]
0x1800147f1  shl     rax, 4
0x1800147f5  mov     r9d, esi
0x1800147f8  add     rcx, rax
0x1800147fb  mov     r8d, 0FFFFFFFFh
0x180014801  lea     rax, [rsp+130h+var_F0+4]
0x180014806  mov     rdx, rdi
0x180014809  mov     [rsp+130h+var_100], rax; __int64
0x18001480e  lea     rax, a136155711; "1.3.6.1.5.5.7.1.1"
0x180014815  mov     qword ptr [rsp+130h+cchCount2], rcx; void *
0x18001481a  mov     ecx, 1; char *
0x18001481f  mov     [rsp+130h+lpString2], rax; Str1
0x180014824  call    ObjectContextGetRawUrlData
0x180014829  mov     r14d, dword ptr [rsp+130h+var_F0+4]
0x18001482e  xor     ecx, ecx
0x180014830  test    eax, eax
0x180014832  cmovz   r14d, ecx
0x180014836  add     r14d, ebx
0x180014839  mov     [rsp+130h+var_E0], r14d
0x18001483e  jz      loc_180014A82
0x180014844  mov     [rsp+130h+arg_0], r12
0x18001484c  mov     edx, 8; uBytes
0x180014851  xor     r12d, r12d
0x180014854  mov     [rsp+130h+var_30], r13
0x18001485c  mov     ecx, 40h ; '@'; uFlags
0x180014861  mov     [rsp+130h+var_D8], r12d
0x180014866  mov     [rbp+30h+var_B0], r15
0x18001486a  mov     [rsp+130h+var_C4], 5
0x180014872  call    cs:__imp_LocalAlloc
0x180014878  mov     [rsp+130h+hMem], rax
0x18001487d  mov     r13, rax
0x180014880  test    rax, rax
0x180014883  jz      loc_180014D68
0x180014889  mov     ecx, 1
0x18001488e  mov     [rsp+130h+var_D0], rax
0x180014893  xor     eax, eax
0x180014895  mov     dword ptr [rsp+130h+var_F0], ecx
0x180014899  xor     esi, esi
0x18001489b  mov     [r13+0], rax
0x18001489f  xor     edi, edi
0x1800148a1  mov     [rsp+130h+var_C8], ecx
0x1800148a5  mov     dword ptr [rsp+130h+var_F0+4], edi
0x1800148a9  nop     dword ptr [rax+00000000h]
0x1800148b0  cmp     edi, r14d
0x1800148b3  jnb     loc_18001494D
0x1800148b9  mov     eax, edi
0x1800148bb  add     rax, rax
0x1800148be  mov     r13, [rbp+rax*8+30h+var_88]
0x1800148c3  test    r13, r13
0x1800148c6  jnz     short loc_1800148E2
0x1800148c8  inc     edi
0x1800148ca  mov     dword ptr [rsp+130h+var_F0+4], edi
0x1800148ce  cmp     ecx, 1
0x1800148d1  jz      short loc_1800148B0
0x1800148d3  mov     r13, [rsp+130h+hMem]
0x1800148d8  mov     r15d, dword ptr [rsp+130h+var_F0]
0x1800148dd  jmp     loc_1800149F4
0x1800148e2  mov     rax, [r13+8]
0x1800148e6  xor     r15d, r15d
0x1800148e9  cmp     [r13+0], r15d
0x1800148ed  jbe     short loc_1800148C8
0x1800148ef  mov     rdi, [rsp+130h+hMem]
0x1800148f4  mov     r14, rax
0x1800148f7  cmp     ecx, 1
0x1800148fa  jnz     short loc_18001493A
0x1800148fc  mov     ebx, r15d
0x1800148ff  lea     rcx, Str1; "1.3.6.1.5.5.7.48.1"
0x180014906  shl     rbx, 5
0x18001490a  mov     rdx, [rbx+r14]; Str2
0x18001490e  call    strcmp_0
0x180014913  test    eax, eax
0x180014915  jnz     short loc_18001492D
0x180014917  cmp     dword ptr [rbx+r14+8], 7
0x18001491d  jnz     short loc_18001492D
0x18001491f  mov     rbx, [rbx+r14+10h]
0x180014924  test    rbx, rbx
0x180014927  jnz     loc_180014A9E
0x18001492d  mov     ecx, dword ptr [rsp+130h+var_F0]
0x180014931  inc     r15d
0x180014934  cmp     r15d, [r13+0]
0x180014938  jb      short loc_1800148F7
0x18001493a  mov     r14d, [rsp+130h+var_E0]
0x18001493f  mov     [rsp+130h+hMem], rdi
0x180014944  mov     edi, dword ptr [rsp+130h+var_F0+4]
0x180014948  jmp     loc_1800148C8
0x18001494d  test    esi, esi
0x18001494f  jnz     short loc_180014969
0x180014951  mov     ecx, 80092004h; dwErrCode
0x180014956  call    cs:__imp_SetLastError
0x18001495c  mov     r13, [rsp+130h+hMem]
0x180014961  xor     r15d, r15d
0x180014964  jmp     loc_1800149F4
0x180014969  mov     r13, [rsp+130h+hMem]
0x18001496e  lea     r9, [rbp+30h+var_B0]
0x180014972  xor     eax, eax
0x180014974  lea     ebx, ds:0[r12*8]
0x18001497c  cmp     [rbp+30h+var_A8], rax
0x180014980  cmovz   r9, rax
0x180014984  xor     r8d, r8d
0x180014987  xor     edx, edx
0x180014989  test    r12d, r12d
0x18001498c  jz      short loc_1800149BE
0x18001498e  xchg    ax, ax
0x180014990  mov     rcx, [r13+rdx*8+0]
0x180014995  test    rcx, rcx
0x180014998  jz      loc_180014DC7
0x18001499e  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800149a5  inc     rax
0x1800149a8  cmp     word ptr [rcx+rax*2], 0
0x1800149ad  jnz     short loc_1800149A5
0x1800149af  lea     r8d, [r8+rax*2]
0x1800149b3  inc     edx
0x1800149b5  add     r8d, 2
0x1800149b9  cmp     edx, r12d
0x1800149bc  jb      short loc_180014990
0x1800149be  lea     eax, [r8+10h]
0x1800149c2  add     eax, ebx
0x1800149c4  mov     dword ptr [rsp+130h+var_F0+4], eax
0x1800149c8  test    r9, r9
0x1800149cb  jnz     loc_180014B73
0x1800149d1  mov     rdx, [rsp+130h+var_C0]
0x1800149d6  test    rdx, rdx
0x1800149d9  jz      loc_180014C72
0x1800149df  mov     [rdx], eax
0x1800149e1  mov     rax, [rbp+30h+var_A0]
0x1800149e5  mov     r15d, 1
0x1800149eb  test    rax, rax
0x1800149ee  jnz     loc_180014CE9
0x1800149f4  xor     ebx, ebx
0x1800149f6  test    r12d, r12d
0x1800149f9  jz      short loc_180014A0D
0x1800149fb  mov     rcx, [r13+rbx*8+0]; pv
0x180014a00  call    cs:__imp_CryptMemFree
0x180014a06  inc     ebx
0x180014a08  cmp     ebx, r12d
0x180014a0b  jb      short loc_1800149FB
0x180014a0d  mov     r12, [rsp+130h+arg_0]
0x180014a15  test    r13, r13
0x180014a18  jz      short loc_180014A33
0x180014a1a  call    cs:__imp_GetLastError
0x180014a20  mov     rcx, r13; hMem
0x180014a23  mov     ebx, eax
0x180014a25  call    cs:__imp_LocalFree
0x180014a2b  mov     ecx, ebx; dwErrCode
0x180014a2d  call    cs:__imp_SetLastError
0x180014a33  mov     r13, [rsp+130h+var_30]
0x180014a3b  xor     ebx, ebx
0x180014a3d  test    r14d, r14d
0x180014a40  jz      short loc_180014A7F
0x180014a42  nop     dword ptr [rax+00h]
0x180014a46  nop     word ptr [rax+rax+00000000h]
0x180014a50  mov     eax, ebx
0x180014a52  add     rax, rax
0x180014a55  mov     rsi, [rbp+rax*8+30h+var_88]
0x180014a5a  test    rsi, rsi
0x180014a5d  jz      short loc_180014A78
0x180014a5f  call    cs:__imp_GetLastError
0x180014a65  mov     rcx, rsi; hMem
0x180014a68  mov     edi, eax
0x180014a6a  call    cs:__imp_LocalFree
0x180014a70  mov     ecx, edi; dwErrCode
0x180014a72  call    cs:__imp_SetLastError
0x180014a78  inc     ebx
0x180014a7a  cmp     ebx, r14d
0x180014a7d  jb      short loc_180014A50
0x180014a7f  mov     eax, r15d
0x180014a82  mov     rcx, [rbp+30h+var_40]
0x180014a86  xor     rcx, rsp; StackCookie
0x180014a89  call    __security_check_cookie
0x180014a8e  add     rsp, 108h
0x180014a95  pop     r15
0x180014a97  pop     r14
0x180014a99  pop     rdi
0x180014a9a  pop     rsi
0x180014a9b  pop     rbx
0x180014a9c  pop     rbp
0x180014a9d  retn
0x180014a9e  mov     eax, 20h ; ' '
0x180014aa3  cmp     ax, [rbx]
0x180014aa6  jnz     short loc_180014AB1
0x180014aa8  add     rbx, 2
0x180014aac  cmp     ax, [rbx]
0x180014aaf  jz      short loc_180014AA8
0x180014ab1  xor     r9d, r9d
0x180014ab4  lea     rcx, aHttp_0; "http"
0x180014abb  xor     eax, eax
0x180014abd  cmp     ax, [rcx]
0x180014ac0  jz      short loc_180014ACF
0x180014ac2  inc     r9; cchCount1
0x180014ac5  add     rcx, 2
0x180014ac9  cmp     r9, 4
0x180014acd  jb      short loc_180014ABB
0x180014acf  xor     ecx, ecx
0x180014ad1  mov     rdx, rbx
0x180014ad4  xor     eax, eax
0x180014ad6  cmp     ax, [rdx]
0x180014ad9  jz      short loc_180014AE8
0x180014adb  inc     rcx
0x180014ade  add     rdx, 2
0x180014ae2  cmp     rcx, 4
0x180014ae6  jb      short loc_180014AD4
0x180014ae8  mov     [rsp+130h+cchCount2], ecx; cchCount2
0x180014aec  lea     r8, aHttp_0; "http"
0x180014af3  mov     ecx, 409h; Locale
0x180014af8  mov     [rsp+130h+lpString2], rbx; lpString2
0x180014afd  mov     edx, 1; dwCmpFlags
0x180014b02  call    cs:__imp_CompareStringW
0x180014b08  cmp     eax, 2
0x180014b0b  jnz     loc_180014D91
0x180014b11  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180014b18  nop     dword ptr [rax+rax+00000000h]
0x180014b20  cmp     word ptr [rbx+rax*2+2], 0
0x180014b26  lea     rax, [rax+1]
0x180014b2a  jnz     short loc_180014B20
0x180014b2c  lea     r12d, [rax+1]
0x180014b30  cmp     r12d, 0FFFFh
0x180014b37  ja      loc_180014DA0
0x180014b3d  lea     ecx, [r12+r12]; cbSize
0x180014b41  call    cs:__imp_CryptMemAlloc
0x180014b47  mov     rsi, rax
0x180014b4a  test    rax, rax
0x180014b4d  jnz     loc_180014C85
0x180014b53  mov     ecx, 8007000Eh; dwErrCode
0x180014b58  call    cs:__imp_SetLastError
0x180014b5e  xor     ecx, ecx
0x180014b60  mov     dword ptr [rsp+130h+var_F0], ecx
0x180014b64  mov     r12d, [rsp+130h+var_D8]
0x180014b69  mov     esi, 1
0x180014b6e  jmp     loc_180014931
0x180014b73  mov     rcx, [r9]
0x180014b76  mov     [rsp+130h+hMem], rcx
0x180014b7b  test    rcx, rcx
0x180014b7e  jz      loc_180014C4B
0x180014b84  mov     rdx, [rsp+130h+var_C0]
0x180014b89  test    rdx, rdx
0x180014b8c  jz      loc_180014C72
0x180014b92  cmp     [rdx], eax
0x180014b94  jb      loc_180014CFA
0x180014b9a  mov     r15, rcx
0x180014b9d  xor     esi, esi
0x180014b9f  mov     [r15], r12d
0x180014ba2  xor     edi, edi
0x180014ba4  lea     rax, [r15+10h]
0x180014ba8  mov     [r15+8], rax
0x180014bac  test    r12d, r12d
0x180014baf  jz      short loc_180014C29
0x180014bb1  mov     r14d, [rsp+130h+var_D8]
0x180014bb6  mov     r12d, ebx
0x180014bb9  add     r12, rax
0x180014bbc  nop     dword ptr [rax+00h]
0x180014bc0  mov     rax, [r15+8]
0x180014bc4  lea     r9, ds:0[rdi*8]
0x180014bcc  mov     ecx, esi
0x180014bce  add     rcx, r12
0x180014bd1  mov     [r9+rax], rcx
0x180014bd5  mov     rdx, [r9+r13]; Src
0x180014bd9  test    rdx, rdx
0x180014bdc  jz      loc_180014DE1
0x180014be2  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180014be9  nop     dword ptr [rax+00000000h]
0x180014bf0  inc     rbx
  ... truncated ...
```
