# UriBlendMkPath

- ea: `0x18007bacc`
- end: `0x18007c24e`
- name: `UriBlendMkPath`
- size: `1922`
- prototype: `__int64 __fastcall(int, int, int, int, int, __int64, int, __int64, int, __int64, int, __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180003568`

## callees

- `0x180009900`
- `0x18000e7e0`
- `0x18003d7f0`
- `0x180040f18`
- `0x180040f60`
- `0x18007bacc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007bea5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007bea5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007bdd1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007be94`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007c22d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007bdd1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007be94`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007c22d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007bddf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007c23b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007bddf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007c23b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x18007bf89`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x18007bf89`

## pseudocode

```c
__int64 __fastcall UriBlendMkPath(
        __int64 a1,
        unsigned __int64 a2,
        wchar_t *a3,
        unsigned int a4,
        __int16 a5,
        unsigned __int16 *a6,
        unsigned int a7,
        unsigned __int16 *a8,
        unsigned int a9,
        _DWORD *a10,
        char a11,
        wchar_t **a12,
        unsigned int *a13)
{
  int v13; // edi
  unsigned int v14; // r10d
  __int64 v15; // rbx
  unsigned __int16 *v16; // r15
  _DWORD *v17; // rax
  unsigned __int64 v18; // r11
  int v19; // edi
  unsigned __int16 *v20; // rdx
  unsigned int v21; // r8d
  unsigned int v22; // ecx
  unsigned __int16 v23; // r9
  unsigned __int16 *v24; // rax
  unsigned int i; // ecx
  __int64 v26; // r9
  unsigned __int16 v27; // r11
  unsigned __int16 *v28; // rdx
  unsigned int v29; // r8d
  unsigned __int64 v30; // rdi
  unsigned __int64 v31; // r14
  unsigned __int64 v32; // r12
  int v33; // r13d
  unsigned int v34; // ecx
  unsigned __int16 v35; // r10
  unsigned int j; // ecx
  __int64 v37; // r9
  unsigned __int16 v38; // r10
  unsigned __int64 v39; // rax
  wchar_t **v40; // rsi
  wchar_t *v41; // rbx
  HANDLE ProcessHeap; // rax
  unsigned __int64 v44; // rcx
  unsigned __int64 v45; // rax
  unsigned __int64 v46; // rcx
  unsigned __int64 v47; // rax
  unsigned __int64 v48; // rsi
  SIZE_T v49; // rbx
  HANDLE v50; // rax
  wchar_t *v51; // rax
  wchar_t *v52; // r15
  unsigned __int64 v53; // r9
  wchar_t *v54; // rbx
  const unsigned __int16 *v55; // r8
  char v56; // r13
  const unsigned __int16 *k; // r8
  __int64 v58; // rax
  int v59; // r14d
  wchar_t *v60; // rcx
  unsigned __int64 v61; // rsi
  unsigned __int16 *v62; // rbx
  unsigned __int64 v63; // rcx
  enum URL_SCHEME v64; // r8d
  HANDLE v65; // rax
  unsigned __int64 v66; // [rsp+48h] [rbp-41h]
  unsigned __int16 *v67; // [rsp+50h] [rbp-39h]
  unsigned __int16 *v68; // [rsp+58h] [rbp-31h]
  unsigned __int64 v69; // [rsp+60h] [rbp-29h]
  const unsigned __int16 *pszPath; // [rsp+68h] [rbp-21h]
  unsigned __int16 *v71; // [rsp+70h] [rbp-19h]
  const unsigned __int16 *v72; // [rsp+78h] [rbp-11h]
  unsigned __int16 *v73; // [rsp+80h] [rbp-9h]
  unsigned __int64 v74; // [rsp+D8h] [rbp+4Fh]
  unsigned __int64 v75; // [rsp+E0h] [rbp+57h] BYREF
  STRSAFE_LPWSTR pszDest; // [rsp+E8h] [rbp+5Fh] BYREF
  unsigned int v77; // [rsp+F0h] [rbp+67h] BYREF

  v77 = a4;
  pszDest = a3;
  v75 = a2;
  if ( !a12 )
  {
    v13 = -2147467261;
    goto LABEL_67;
  }
  *a12 = 0;
  if ( !a13 )
  {
    v13 = -2147467261;
LABEL_66:
    v40 = a12;
    v41 = *a12;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v41);
    *v40 = 0;
LABEL_67:
    if ( a13 )
      *a13 = 0;
    return (unsigned int)v13;
  }
  v14 = a9;
  v15 = 0;
  v16 = 0;
  *a13 = 0;
  v17 = a10;
  v18 = 0;
  v72 = 0;
  v74 = 0;
  v68 = 0;
  v69 = 0;
  v66 = 0;
  if ( *a10 )
  {
    v19 = 0;
    pszPath = 0;
    v77 = 0;
    if ( v14 )
    {
      v20 = a8;
      if ( a8 )
      {
        v21 = v14;
        if ( *a8 == 64 )
        {
          v22 = 1;
          if ( v14 > 1 )
          {
            while ( 1 )
            {
              v23 = a8[v22];
              if ( !v23 || v23 == 58 )
                break;
              if ( ++v22 >= v14 )
                goto LABEL_17;
            }
            v16 = a8;
            v72 = a8;
            v66 = v22;
            v24 = &a8[v22];
            v20 = v24;
            v21 = v14 - v22;
            if ( v14 != v22 && *v24 == 58 )
            {
              v19 = 1;
              v20 = v24 + 1;
              v77 = 1;
              --v21;
            }
          }
        }
LABEL_17:
        for ( i = 0; ; ++i )
        {
          v26 = i + 1;
          if ( (unsigned int)v26 >= v21 )
          {
            v15 = 0;
            goto LABEL_30;
          }
          v15 = i;
          if ( !v20[i] || (v27 = v20[v26]) == 0 )
          {
            v15 = 0;
            goto LABEL_30;
          }
          if ( v20[i] == 58 && v27 == 58 )
            break;
        }
        if ( i )
        {
          pszPath = v20;
          v74 = i;
        }
        else
        {
          v15 = 0;
        }
        v21 += -2 - i;
        v77 = v19 | 2;
        v20 += i + 2;
LABEL_30:
        v18 = v66;
        if ( v21 )
        {
          v69 = v21;
          v68 = v20;
        }
        v17 = a10;
      }
    }
  }
  else
  {
    pszPath = 0;
    v77 = 0;
  }
  if ( v16 && v18 || *v17 == 2 || (v28 = a6) == 0 || (v29 = a7) == 0 )
  {
    v30 = 0;
    v73 = 0;
    v67 = 0;
    v31 = 0;
    v71 = 0;
    v32 = 0;
    v39 = 4;
    v33 = 0;
  }
  else
  {
    if ( !*v17 || !v14 && (a5 & 0x420) != 0 )
    {
      v15 = 0;
      v68 = 0;
      pszPath = 0;
      v66 = 0;
      v72 = 0;
      v69 = 0;
      v74 = 0;
    }
    v30 = 0;
    v73 = 0;
    v31 = 0;
    v67 = 0;
    v32 = 0;
    v71 = 0;
    v33 = 0;
    if ( *a6 == 64 )
    {
      v34 = 1;
      if ( a7 > 1 )
      {
        while ( 1 )
        {
          v35 = a6[v34];
          if ( !v35 || v35 == 58 )
            break;
          if ( ++v34 >= a7 )
            goto LABEL_52;
        }
        v30 = v34;
        v73 = a6;
        v28 = &a6[v34];
        v29 = a7 - v34;
        if ( a7 != v34 && *v28 == 58 )
        {
          --v29;
          v33 = 1;
          ++v28;
        }
      }
    }
LABEL_52:
    for ( j = 0; ; ++j )
    {
      v37 = j + 1;
      if ( (unsigned int)v37 >= v29 )
        break;
      if ( !v28[j] )
        break;
      v38 = v28[v37];
      if ( !v38 )
        break;
      if ( v28[j] == 58 && v38 == 58 )
      {
        if ( j )
        {
          v67 = v28;
          v31 = j;
        }
        v29 += -2 - j;
        v28 += j + 2;
        v33 |= 2u;
        break;
      }
    }
    if ( v29 )
    {
      v71 = v28;
      v32 = v29;
    }
    v39 = v30 + 4;
    v18 = v66;
  }
  v44 = v39 + v18;
  if ( v39 + v18 < v39
    || (v45 = v44 + v31, v44 + v31 < v44)
    || (v46 = v45 + v15, v45 + v15 < v45)
    || (v47 = v46 + v32, v46 + v32 < v46)
    || (v48 = v47 + v69, v47 + v69 < v47) )
  {
    v13 = -2147024362;
    goto LABEL_66;
  }
  v49 = 2 * v48;
  if ( !is_mul_ok(v48, 2u) )
    v49 = -1;
  v50 = GetProcessHeap();
  v51 = (wchar_t *)HeapAlloc(v50, 8u, v49);
  v52 = v51;
  if ( !v51 )
  {
    v13 = -2147024882;
    goto LABEL_66;
  }
  v53 = v66;
  v54 = v51;
  pszDest = v51;
  v75 = v48;
  if ( v66 )
  {
    v55 = v72;
  }
  else
  {
    if ( !v30 )
      goto LABEL_86;
    v55 = v73;
    v53 = v30;
  }
  v13 = StringCchCopyNExW(v51, v48, v55, v53, &pszDest, &v75, 0x1900u);
  if ( v13 < 0 )
    goto LABEL_127;
  v54 = pszDest;
LABEL_86:
  v77 |= v33;
  v56 = v77;
  if ( (v77 & 1) != 0 )
  {
    v13 = StringCchCopyNExW(v54, v75, L":", 1u, &pszDest, &v75, 0x1900u);
    if ( v13 < 0 )
      goto LABEL_127;
    v54 = pszDest;
  }
  if ( v74 )
  {
    if ( pszPath )
    {
      if ( (unsigned int)IsDosDrive(pszPath) || PathIsUNCW(pszPath) )
      {
        v67 = 0;
        v31 = 0;
      }
      v32 = 0;
      v71 = 0;
    }
    for ( k = v67; v31; --v31 )
    {
      if ( v67[v31 - 1] == 92 )
        break;
    }
  }
  else
  {
    k = v67;
  }
  v13 = StringCchCopyNExW(v54, v75, k, v31, &pszDest, &v75, 0x1900u);
  if ( v13 < 0 )
    goto LABEL_127;
  v13 = StringCchCopyNExW(pszDest, v75, pszPath, v74, &pszDest, &v75, 0x1900u);
  if ( v13 < 0 )
    goto LABEL_127;
  v58 = pszDest - v54;
  v59 = a11 & 0x10;
  if ( (a11 & 0x10) == 0 && v58 )
  {
    v77 = a11 & 0x10;
    v13 = ULongLongToULong(pszDest - v54, &v77);
    if ( v13 < 0 )
      goto LABEL_127;
    CanonicalizePath(v54, &v77, v59 + 1, 0);
    v58 = v77;
  }
  v60 = &v54[v58];
  pszDest = v60;
  v61 = v48 - (v60 - v52);
  v75 = v61;
  if ( (v56 & 2) != 0 )
  {
    v13 = StringCchCopyNExW(v60, v61, L"::", 2u, &pszDest, &v75, 0x1900u);
    if ( v13 < 0 )
      goto LABEL_127;
    v60 = pszDest;
    v61 = v75;
  }
  v62 = v60;
  if ( v32 && (!v69 || *v68 != 47 && *v68 != 92) )
  {
    if ( v68 )
    {
      do
      {
        if ( v71[v32 - 1] == 92 )
          break;
        if ( v71[v32 - 1] == 47 )
          break;
        --v32;
      }
      while ( v32 );
    }
    v13 = StringCchCopyNExW(v60, v61, v71, v32, &pszDest, &v75, 0x1900u);
    if ( v13 < 0 )
      goto LABEL_127;
    v60 = pszDest;
    v61 = v75;
  }
  v13 = StringCchCopyNExW(v60, v61, v68, v69, &pszDest, &v75, 0x1900u);
  if ( v13 < 0 )
  {
LABEL_127:
    v65 = GetProcessHeap();
    HeapFree(v65, 0, v52);
    goto LABEL_66;
  }
  v63 = pszDest - v62;
  if ( !v59 && v63 )
  {
    v77 = 0;
    v13 = ULongLongToULong(v63, &v77);
    if ( v13 >= 0 )
    {
      CorrectPathDelimiter(v62, v77, v64, 1);
      CanonicalizePath(v62, &v77, 1, 0);
      v63 = v77;
      goto LABEL_124;
    }
    goto LABEL_127;
  }
LABEL_124:
  v13 = ULongLongToULong((__int64)((__int64)v62 + 2 * v63 - (_QWORD)v52) >> 1, a13);
  if ( v13 < 0 )
    goto LABEL_127;
  *a12 = v52;
  if ( v68 )
    *a10 = 2;
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18007bacc  mov     rax, rsp
0x18007bacf  mov     [rax+20h], r9d
0x18007bad3  mov     [rax+18h], r8
0x18007bad7  mov     [rax+10h], rdx
0x18007badb  mov     [rax+8], rcx
0x18007badf  push    rbp
0x18007bae0  push    rbx
0x18007bae1  push    rsi
0x18007bae2  push    rdi
0x18007bae3  push    r12
0x18007bae5  push    r13
0x18007bae7  push    r14
0x18007bae9  push    r15
0x18007baeb  lea     rbp, [rax-47h]
0x18007baef  sub     rsp, 88h
0x18007baf6  mov     rax, [rbp+3Fh+arg_58]
0x18007bafd  test    rax, rax
0x18007bb00  jnz     short loc_18007BB0C
0x18007bb02  mov     edi, 80004003h
0x18007bb07  jmp     loc_18007BDEC
0x18007bb0c  mov     qword ptr [rax], 0
0x18007bb13  mov     rax, [rbp+3Fh+arg_60]
0x18007bb1a  test    rax, rax
0x18007bb1d  jnz     short loc_18007BB29
0x18007bb1f  mov     edi, 80004003h
0x18007bb24  jmp     loc_18007BDC7
0x18007bb29  mov     r10d, [rbp+3Fh+arg_40]
0x18007bb30  xor     ebx, ebx
0x18007bb32  xor     r15d, r15d
0x18007bb35  mov     dword ptr [rax], 0
0x18007bb3b  mov     rax, [rbp+3Fh+arg_48]
0x18007bb42  xor     r11d, r11d
0x18007bb45  mov     ecx, 40h ; '@'
0x18007bb4a  mov     [rbp+3Fh+var_50], r15
0x18007bb4e  mov     esi, 0FFFFFFFEh
0x18007bb53  mov     [rbp+3Fh+arg_0], rbx
0x18007bb57  mov     [rbp+3Fh+var_70], rbx
0x18007bb5b  mov     [rbp+3Fh+var_68], rbx
0x18007bb5f  lea     r14d, [rcx-6]
0x18007bb63  mov     [rbp+3Fh+var_80], r11
0x18007bb67  cmp     [rax], r11d
0x18007bb6a  jz      loc_18007BD2F
0x18007bb70  xor     edi, edi
0x18007bb72  mov     [rbp+3Fh+pszPath], r11
0x18007bb76  mov     [rbp+3Fh+arg_18], edi
0x18007bb79  test    r10d, r10d
0x18007bb7c  jz      loc_18007BC71
0x18007bb82  mov     rdx, [rbp+3Fh+arg_38]
0x18007bb89  test    rdx, rdx
0x18007bb8c  jz      loc_18007BC71
0x18007bb92  mov     r8d, r10d
0x18007bb95  cmp     cx, [rdx]
0x18007bb98  jnz     short loc_18007BBEF
0x18007bb9a  lea     ecx, [rbx+1]
0x18007bb9d  cmp     r10d, ecx
0x18007bba0  jbe     short loc_18007BBEF
0x18007bba2  mov     eax, ecx
0x18007bba4  movzx   r9d, word ptr [rdx+rax*2]
0x18007bba9  xor     eax, eax
0x18007bbab  cmp     ax, r9w
0x18007bbaf  jz      short loc_18007BBC0
0x18007bbb1  cmp     r14w, r9w
0x18007bbb5  jz      short loc_18007BBC0
0x18007bbb7  inc     ecx
0x18007bbb9  cmp     ecx, r10d
0x18007bbbc  jb      short loc_18007BBA2
0x18007bbbe  jmp     short loc_18007BBEF
0x18007bbc0  mov     r11d, ecx
0x18007bbc3  mov     r15, rdx
0x18007bbc6  mov     [rbp+3Fh+var_50], rdx
0x18007bbca  mov     [rbp+3Fh+var_80], r11
0x18007bbce  lea     rax, [rdx+r11*2]
0x18007bbd2  mov     rdx, rax
0x18007bbd5  sub     r8d, ecx
0x18007bbd8  jz      short loc_18007BBEF
0x18007bbda  cmp     r14w, [rax]
0x18007bbde  jnz     short loc_18007BBEF
0x18007bbe0  mov     edi, 1
0x18007bbe5  lea     rdx, [rax+2]
0x18007bbe9  mov     [rbp+3Fh+arg_18], edi
0x18007bbec  dec     r8d
0x18007bbef  xor     ecx, ecx
0x18007bbf1  lea     r9d, [rcx+1]
0x18007bbf5  cmp     r9d, r8d
0x18007bbf8  jnb     short loc_18007BC4D
0x18007bbfa  mov     ebx, ecx
0x18007bbfc  xor     eax, eax
0x18007bbfe  cmp     ax, [rdx+rbx*2]
0x18007bc02  jz      short loc_18007BC48
0x18007bc04  movzx   r11d, word ptr [rdx+r9*2]
0x18007bc09  cmp     ax, r11w
0x18007bc0d  jz      short loc_18007BC48
0x18007bc0f  cmp     r14w, [rdx+rbx*2]
0x18007bc14  jnz     short loc_18007BC1C
0x18007bc16  cmp     r14w, r11w
0x18007bc1a  jz      short loc_18007BC21
0x18007bc1c  mov     ecx, r9d
0x18007bc1f  jmp     short loc_18007BBF1
0x18007bc21  test    ecx, ecx
0x18007bc23  jz      short loc_18007BC2F
0x18007bc25  mov     [rbp+3Fh+pszPath], rdx
0x18007bc29  mov     [rbp+3Fh+arg_0], rbx
0x18007bc2d  jmp     short loc_18007BC32
0x18007bc2f  mov     rbx, rax
0x18007bc32  mov     eax, esi
0x18007bc34  sub     eax, ecx
0x18007bc36  add     r8d, eax
0x18007bc39  lea     eax, [rcx+2]
0x18007bc3c  or      edi, 2
0x18007bc3f  mov     [rbp+3Fh+arg_18], edi
0x18007bc42  lea     rdx, [rdx+rax*2]
0x18007bc46  jmp     short loc_18007BC51
0x18007bc48  mov     rbx, rax
0x18007bc4b  jmp     short loc_18007BC51
0x18007bc4d  mov     rbx, [rbp+3Fh+arg_0]
0x18007bc51  mov     r11, [rbp+3Fh+var_80]
0x18007bc55  mov     ecx, 40h ; '@'
0x18007bc5a  test    r8d, r8d
0x18007bc5d  jz      short loc_18007BC6A
0x18007bc5f  mov     eax, r8d
0x18007bc62  mov     [rbp+3Fh+var_68], rax
0x18007bc66  mov     [rbp+3Fh+var_70], rdx
0x18007bc6a  mov     rax, [rbp+3Fh+arg_48]
0x18007bc71  test    r15, r15
0x18007bc74  jz      short loc_18007BC7F
0x18007bc76  test    r11, r11
0x18007bc79  jnz     loc_18007BE14
0x18007bc7f  cmp     dword ptr [rax], 2
0x18007bc82  jz      loc_18007BE14
0x18007bc88  mov     rdx, [rbp+3Fh+arg_28]
0x18007bc8c  test    rdx, rdx
0x18007bc8f  jz      loc_18007BE14
0x18007bc95  mov     r8d, [rbp+3Fh+arg_30]
0x18007bc99  test    r8d, r8d
0x18007bc9c  jz      loc_18007BE14
0x18007bca2  cmp     dword ptr [rax], 0
0x18007bca5  jz      short loc_18007BCB5
0x18007bca7  test    r10d, r10d
0x18007bcaa  jnz     short loc_18007BCE2
0x18007bcac  test    dword ptr [rbp+3Fh+arg_20], 420h
0x18007bcb3  jz      short loc_18007BCE2
0x18007bcb5  xor     ebx, ebx
0x18007bcb7  mov     [rbp+3Fh+var_70], 0
0x18007bcbf  xor     r9d, r9d
0x18007bcc2  mov     [rbp+3Fh+pszPath], 0
0x18007bcca  mov     [rbp+3Fh+var_80], r9
0x18007bcce  mov     [rbp+3Fh+var_50], 0
0x18007bcd6  mov     [rbp+3Fh+var_68], 0
0x18007bcde  mov     [rbp+3Fh+arg_0], rbx
0x18007bce2  xor     edi, edi
0x18007bce4  mov     [rbp+3Fh+var_48], 0
0x18007bcec  xor     r14d, r14d
0x18007bcef  mov     [rbp+3Fh+var_78], rdi
0x18007bcf3  xor     r12d, r12d
0x18007bcf6  mov     [rbp+3Fh+var_58], rdi
0x18007bcfa  xor     r13d, r13d
0x18007bcfd  mov     r9, rdx
0x18007bd00  lea     r15d, [rdi+3Ah]
0x18007bd04  cmp     cx, [rdx]
0x18007bd07  jnz     short loc_18007BD5D
0x18007bd09  lea     ecx, [rdi+1]
0x18007bd0c  cmp     r8d, ecx
0x18007bd0f  jbe     short loc_18007BD5D
0x18007bd11  mov     eax, ecx
0x18007bd13  movzx   r10d, word ptr [r9+rax*2]
0x18007bd18  xor     eax, eax
0x18007bd1a  cmp     ax, r10w
0x18007bd1e  jz      short loc_18007BD3B
0x18007bd20  cmp     r15w, r10w
0x18007bd24  jz      short loc_18007BD3B
0x18007bd26  inc     ecx
0x18007bd28  cmp     ecx, r8d
0x18007bd2b  jb      short loc_18007BD11
0x18007bd2d  jmp     short loc_18007BD5D
0x18007bd2f  mov     [rbp+3Fh+pszPath], r15
0x18007bd33  mov     [rbp+3Fh+arg_18], ebx
0x18007bd36  jmp     loc_18007BC71
0x18007bd3b  mov     edi, ecx
0x18007bd3d  mov     [rbp+3Fh+var_48], rdx
0x18007bd41  lea     rdx, [rdx+rdi*2]
0x18007bd45  sub     r8d, ecx
0x18007bd48  jz      short loc_18007BD5D
0x18007bd4a  cmp     r15w, [rdx]
0x18007bd4e  jnz     short loc_18007BD5D
0x18007bd50  dec     r8d
0x18007bd53  mov     r13d, 1
0x18007bd59  add     rdx, 2
0x18007bd5d  xor     ecx, ecx
0x18007bd5f  lea     r9d, [rcx+1]
0x18007bd63  cmp     r9d, r8d
0x18007bd66  jnb     short loc_18007BDAC
0x18007bd68  mov     r11d, ecx
0x18007bd6b  xor     eax, eax
0x18007bd6d  cmp     ax, [rdx+r11*2]
0x18007bd72  jz      short loc_18007BDAC
0x18007bd74  movzx   r10d, word ptr [rdx+r9*2]
0x18007bd79  cmp     ax, r10w
0x18007bd7d  jz      short loc_18007BDAC
0x18007bd7f  cmp     r15w, [rdx+r11*2]
0x18007bd84  jnz     short loc_18007BD8C
0x18007bd86  cmp     r15w, r10w
0x18007bd8a  jz      short loc_18007BD91
0x18007bd8c  mov     ecx, r9d
0x18007bd8f  jmp     short loc_18007BD5F
0x18007bd91  test    ecx, ecx
0x18007bd93  jz      short loc_18007BD9C
0x18007bd95  mov     [rbp+3Fh+var_78], rdx
0x18007bd99  mov     r14, r11
0x18007bd9c  sub     esi, ecx
0x18007bd9e  lea     eax, [rcx+2]
0x18007bda1  add     r8d, esi
0x18007bda4  lea     rdx, [rdx+rax*2]
0x18007bda8  or      r13d, 2
0x18007bdac  test    r8d, r8d
0x18007bdaf  jz      short loc_18007BDB8
0x18007bdb1  mov     [rbp+3Fh+var_58], rdx
0x18007bdb5  mov     r12d, r8d
0x18007bdb8  lea     rax, [rdi+4]
0x18007bdbc  cmp     rax, 4
0x18007bdc0  jnb     short loc_18007BE36
0x18007bdc2  mov     edi, 80070216h
0x18007bdc7  mov     rsi, [rbp+3Fh+arg_58]
0x18007bdce  mov     rbx, [rsi]
0x18007bdd1  call    cs:__imp_GetProcessHeap
0x18007bdd7  mov     r8, rbx; lpMem
0x18007bdda  xor     edx, edx; dwFlags
0x18007bddc  mov     rcx, rax; hHeap
0x18007bddf  call    cs:__imp_HeapFree
0x18007bde5  mov     qword ptr [rsi], 0
0x18007bdec  mov     rax, [rbp+3Fh+arg_60]
0x18007bdf3  test    rax, rax
0x18007bdf6  jz      short loc_18007BDFE
0x18007bdf8  mov     dword ptr [rax], 0
0x18007bdfe  mov     eax, edi
0x18007be00  add     rsp, 88h
0x18007be07  pop     r15
0x18007be09  pop     r14
0x18007be0b  pop     r13
0x18007be0d  pop     r12
0x18007be0f  pop     rdi
0x18007be10  pop     rsi
0x18007be11  pop     rbx
0x18007be12  pop     rbp
0x18007be13  retn
0x18007be14  xor     edi, edi
0x18007be16  mov     [rbp+3Fh+var_48], 0
0x18007be1e  xor     eax, eax
0x18007be20  mov     [rbp+3Fh+var_78], rdi
0x18007be24  xor     r14d, r14d
0x18007be27  mov     [rbp+3Fh+var_58], rax
0x18007be2b  xor     r12d, r12d
0x18007be2e  lea     eax, [rdi+4]
0x18007be31  xor     r13d, r13d
0x18007be34  jmp     short loc_18007BE3A
0x18007be36  mov     r11, [rbp+3Fh+var_80]
0x18007be3a  lea     rcx, [rax+r11]
0x18007be3e  cmp     rcx, rax
0x18007be41  jb      loc_18007BDC2
0x18007be47  lea     rax, [rcx+r14]
0x18007be4b  cmp     rax, rcx
0x18007be4e  jb      loc_18007BDC2
0x18007be54  lea     rcx, [rax+rbx]
0x18007be58  cmp     rcx, rax
0x18007be5b  jb      loc_18007BDC2
0x18007be61  lea     rax, [rcx+r12]
0x18007be65  cmp     rax, rcx
0x18007be68  jb      loc_18007BDC2
0x18007be6e  mov     rsi, [rbp+3Fh+var_68]
0x18007be72  add     rsi, rax
0x18007be75  cmp     rsi, rax
0x18007be78  jb      loc_18007BDC2
0x18007be7e  mov     eax, 2
0x18007be83  mul     rsi
0x18007be86  mov     rbx, rax
0x18007be89  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18007be90  cmovb   rbx, rax
0x18007be94  call    cs:__imp_GetProcessHeap
0x18007be9a  mov     r8, rbx; dwBytes
0x18007be9d  mov     edx, 8; dwFlags
0x18007bea2  mov     rcx, rax; hHeap
0x18007bea5  call    cs:__imp_HeapAlloc
0x18007beab  mov     r15, rax
0x18007beae  test    rax, rax
0x18007beb1  jnz     short loc_18007BEBD
0x18007beb3  mov     edi, 8007000Eh
0x18007beb8  jmp     loc_18007BDC7
0x18007bebd  mov     r9, [rbp+3Fh+var_80]
0x18007bec1  mov     rbx, r15
0x18007bec4  mov     [rbp+3Fh+pszDest], rbx
0x18007bec8  mov     [rbp+3Fh+arg_8], rsi
0x18007becc  test    r9, r9
0x18007becf  jz      short loc_18007BED7
0x18007bed1  mov     r8, [rbp+3Fh+var_50]
0x18007bed5  jmp     short loc_18007BEE3
0x18007bed7  test    rdi, rdi
0x18007beda  jz      short loc_18007BF16
0x18007bedc  mov     r8, [rbp+3Fh+var_48]; unsigned __int16 *
0x18007bee0  mov     r9, rdi; unsigned __int64
0x18007bee3  lea     rax, [rbp+3Fh+arg_8]
0x18007bee7  mov     dword ptr [rsp+30h], 1900h; unsigned int
  ... truncated ...
```
