# _AppendAndReplacePathEnvVar(ushort const *,ushort const *,ushort * *)

- ea: `0x180005160`
- end: `0x180005b57`
- name: `?_AppendAndReplacePathEnvVar@@YAJPEBG0PEAPEAG@Z`
- size: `2551`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004230`

## callees

- `0x180005160`
- `0x180005b60`
- `0x180005b90`
- `0x180005bf0`
- `0x180006060`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800057ef`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800057ef`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000589c`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180005903`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000589c`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180005903`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005340`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800055eb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005604`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005a22`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005340`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800055eb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005604`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005a22`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005285`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800053af`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000563b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005752`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005285`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800053af`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000563b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005752`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005277`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005332`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000539e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800055dd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800055f6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000562d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005744`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000588b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800058f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005a14`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005277`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005332`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000539e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800055dd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800055f6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000562d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005744`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000588b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800058f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005a14`

## pseudocode

```c
__int64 __fastcall _AppendAndReplacePathEnvVar(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  unsigned __int16 *v3; // r13
  void *v6; // r15
  unsigned __int64 v7; // rbx
  unsigned __int64 v8; // rdi
  int v9; // r14d
  unsigned int v10; // edi
  __int64 v11; // rdx
  HANDLE ProcessHeap; // rax
  _WORD *v14; // rax
  unsigned __int64 v15; // r9
  const unsigned __int16 *v16; // rcx
  _WORD *v17; // rdx
  _WORD *v18; // rcx
  HANDLE v19; // rax
  unsigned int v20; // ebx
  const unsigned __int16 *v21; // r14
  unsigned __int64 v22; // r15
  HANDLE v23; // rax
  unsigned __int16 *v24; // r12
  __int64 v25; // rcx
  __int64 v26; // r8
  unsigned __int16 *v27; // rdx
  unsigned __int16 *v28; // rcx
  unsigned int v29; // r14d
  __int64 v30; // rbx
  const unsigned __int16 *v32; // rcx
  _WORD *v33; // r15
  __int64 v34; // rcx
  __int64 v35; // r10
  unsigned __int64 v36; // rsi
  unsigned __int64 v37; // rdi
  unsigned __int64 v38; // rcx
  int v39; // ebx
  unsigned __int64 v40; // rdi
  unsigned __int64 v41; // rsi
  __int64 v42; // rax
  int v43; // ebx
  HANDLE v44; // rax
  HANDLE v45; // rax
  HANDLE v46; // rax
  _WORD *v47; // rax
  unsigned __int64 v48; // r10
  unsigned __int64 v49; // r8
  _WORD *v50; // r9
  unsigned __int64 v51; // rcx
  unsigned __int16 *v52; // rdx
  _WORD *v53; // rcx
  HANDLE v54; // rax
  _WORD *v55; // rax
  __int64 v56; // rcx
  const wchar_t *v57; // rdx
  __int64 v58; // r9
  _WORD *v59; // r8
  _WORD *v60; // rcx
  wchar_t *v61; // rax
  wchar_t v62; // dx
  wchar_t v63; // ax
  unsigned __int64 v64; // rdx
  unsigned __int64 v65; // rax
  SIZE_T v66; // rbx
  HANDLE v67; // rax
  _WORD *v68; // rax
  unsigned __int64 v69; // rdx
  unsigned __int64 v70; // rcx
  unsigned __int64 v71; // rsi
  HANDLE v72; // rax
  _WORD *v73; // rax
  unsigned __int16 v74; // ax
  HANDLE v75; // rax
  int FirstComponent; // eax
  unsigned __int64 v77; // [rsp+20h] [rbp-50h]
  int v78; // [rsp+20h] [rbp-50h]
  unsigned __int64 v79; // [rsp+28h] [rbp-48h]
  _WORD *lpMem; // [rsp+30h] [rbp-40h]
  unsigned __int16 *v81; // [rsp+38h] [rbp-38h] BYREF
  _WORD *v82; // [rsp+40h] [rbp-30h] BYREF
  unsigned __int64 v83; // [rsp+48h] [rbp-28h]
  unsigned __int64 v84; // [rsp+50h] [rbp-20h]
  unsigned __int16 *v85; // [rsp+58h] [rbp-18h] BYREF
  __int64 v86; // [rsp+60h] [rbp-10h]
  __int64 v87; // [rsp+68h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  v3 = 0;
  *a3 = 0;
  v79 = 0;
  v84 = 0;
  v6 = 0;
  lpMem = 0;
  v82 = 0;
  v77 = 0;
  v83 = 0;
  if ( !a1 )
  {
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v82);
    v79 = v84;
    v77 = v83;
    lpMem = v82;
    goto LABEL_8;
  }
  v7 = -1;
  do
    ++v7;
  while ( a1[v7] );
  v8 = v7 + 1;
  if ( v7 + 1 >= v7 && is_mul_ok(v8, 2u) )
  {
    ProcessHeap = GetProcessHeap();
    v14 = HeapAlloc(ProcessHeap, 0, 2 * v8);
    if ( !v14 )
    {
      v9 = -2147024882;
      goto LABEL_24;
    }
    v77 = v7;
    v15 = v7;
    v79 = v7 + 1;
    v9 = 0;
    v84 = v7 + 1;
    v6 = v14;
    lpMem = v14;
    v82 = v14;
    *v14 = 0;
    if ( v7 != -1 )
    {
      if ( v7 > 0x7FFFFFFE || v8 > 0x7FFFFFFF )
      {
        *v14 = 0;
      }
      else
      {
        v16 = a1;
        v17 = v14;
        do
        {
          if ( !v7 )
            break;
          if ( !*v16 )
            break;
          *v17++ = *v16++;
          --v7;
          --v8;
        }
        while ( v8 );
        v18 = v17 - 1;
        if ( v8 )
          v18 = v17;
        *v18 = 0;
      }
    }
    v83 = v15;
  }
  else
  {
    v9 = -2147024362;
  }
  if ( v9 < 0 )
  {
LABEL_24:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6E,
      (unsigned int)"minio\\profapi\\env.cpp",
      (const char *)(unsigned int)v9,
      v77);
    if ( v6 )
    {
      v19 = GetProcessHeap();
      HeapFree(v19, 0, v6);
    }
    return (unsigned int)v9;
  }
LABEL_8:
  v85 = 0;
  v86 = -1;
  v87 = -1;
  if ( !a2 || !*a2 )
  {
    v10 = -2147024809;
    v11 = 16;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"minio\\profapi\\env.cpp",
      (const char *)v10,
      v77);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x73,
      (unsigned int)"minio\\profapi\\env.cpp",
      (const char *)v10,
      v78);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v85);
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v82);
    return v10;
  }
  v20 = 0;
  v21 = a2;
  do
  {
    if ( !*v21 )
      break;
    if ( *v21 == 59 )
      break;
    ++v20;
    ++v21;
  }
  while ( v21 );
  v22 = v20 + 1;
  if ( !is_mul_ok(v22, 2u) )
  {
    v10 = -2147024362;
LABEL_34:
    v11 = 30;
    goto LABEL_10;
  }
  v23 = GetProcessHeap();
  v24 = (unsigned __int16 *)HeapAlloc(v23, 8u, 2LL * (v20 + 1));
  v10 = -2147024882;
  if ( !v24 )
    goto LABEL_34;
  if ( v20 != -1 )
  {
    if ( v22 > 0x7FFFFFFF )
    {
      *v24 = 0;
    }
    else if ( v20 > 0x7FFFFFFE )
    {
      *v24 = 0;
    }
    else
    {
      v25 = v20;
      v26 = v20 + 1;
      v27 = v24;
      do
      {
        if ( !v25 )
          break;
        if ( !*a2 )
          break;
        *v27++ = *a2++;
        --v25;
        --v26;
      }
      while ( v26 );
      v28 = v27 - 1;
      if ( v26 )
        v28 = v27;
      *v28 = 0;
    }
  }
  if ( v24[v22 - 1] == 92 )
    v24[v22 - 1] = 0;
  if ( !v21 )
    goto LABEL_49;
  if ( *v21 )
  {
    if ( *v21 == 59 )
    {
      v3 = (unsigned __int16 *)(v21 + 1);
      if ( v21 != (const unsigned __int16 *)-2LL && !*v3 )
        v3 = 0;
    }
LABEL_49:
    v85 = v24;
    if ( v3 )
    {
      v29 = 0;
      goto LABEL_53;
    }
    goto LABEL_52;
  }
  v85 = v24;
LABEL_52:
  v29 = 1;
LABEL_53:
  while ( 1 )
  {
    v30 = -1;
    while ( v24[++v30] != 0 )
      ;
    v32 = a1;
    while ( v32 )
    {
      if ( !*v32 )
        break;
      v61 = wcsstr(v32, v24);
      if ( !v61 )
        break;
      v62 = v61[v30];
      v32 = &v61[v30];
      if ( v62 == 59 || !v62 || v62 == 92 && ((v74 = v32[1], v74 == 59) || !v74) )
      {
        v33 = lpMem;
        goto LABEL_103;
      }
      if ( !v32 )
        break;
      do
      {
        v63 = *v32;
        if ( !*v32 )
          break;
        ++v32;
        if ( v63 == 59 )
          break;
      }
      while ( v32 );
    }
    v33 = lpMem;
    v34 = -1;
    do
      ++v34;
    while ( lpMem[v34] );
    v35 = v77;
    if ( lpMem[v34 - 1] != 59 )
      break;
LABEL_60:
    if ( !v24 )
      goto LABEL_103;
    v36 = -1;
    do
      ++v36;
    while ( v24[v36] );
    if ( v35 == -1 )
    {
      if ( v33 )
      {
        do
          ++v35;
        while ( v33[v35] );
      }
      else
      {
        v35 = 0;
      }
      v83 = v35;
      v77 = v35;
    }
    v37 = v36 + v35 + 1;
    if ( v37 < v36 + v35 )
    {
LABEL_72:
      v39 = -2147024362;
      goto LABEL_73;
    }
    v38 = v79;
    if ( v79 == -1 )
    {
      if ( v35 != -1 )
        goto LABEL_152;
      if ( v33 )
      {
        do
          ++v35;
        while ( v33[v35] );
        v77 = v35;
        v83 = v35;
LABEL_152:
        if ( v33 )
        {
          v38 = v35 + 1;
LABEL_154:
          v84 = v38;
          v79 = v38;
          goto LABEL_69;
        }
      }
      else
      {
        v77 = 0;
        v83 = 0;
      }
      v38 = 0;
      goto LABEL_154;
    }
LABEL_69:
    if ( !v38 )
    {
      v81 = 0;
      if ( !is_mul_ok(v37, 2u) )
        goto LABEL_72;
      v46 = GetProcessHeap();
      v47 = HeapAlloc(v46, 0, 2 * v37);
      if ( v47 )
      {
        lpMem = v47;
        v39 = 0;
        v79 = v37;
        v84 = v37;
        v33 = v47;
        v82 = v47;
        *v47 = 0;
      }
      else
      {
        v39 = -2147024882;
      }
      if ( v39 < 0 )
        goto LABEL_73;
      goto LABEL_92;
    }
    if ( v37 > v38 )
    {
      v81 = 0;
      if ( !is_mul_ok(v38, 2u) )
        goto LABEL_72;
      v64 = v79 + 2048;
      if ( 2 * v38 - v79 <= 0x800 )
        v64 = 2 * v38;
      v65 = v37;
      if ( v37 <= v64 )
        v65 = v64;
      v79 = v65;
      v66 = 2 * v65;
      if ( v33 )
      {
        v67 = GetProcessHeap();
        v68 = HeapReAlloc(v67, 0, v33, v66);
      }
      else
      {
        v68 = (_WORD *)Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Alloc(2 * v65);
      }
      lpMem = v68;
      v33 = v68;
      if ( v68 )
      {
        v84 = v79;
        v82 = v68;
        goto LABEL_92;
      }
      v39 = -2147024882;
LABEL_73:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7E,
        (unsigned int)"minio\\profapi\\env.cpp",
        (const char *)(unsigned int)v39,
        v77);
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v85);
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v82);
      return (unsigned int)v39;
    }
LABEL_92:
    v48 = v77;
    v49 = v36 + 1;
    v50 = &v33[v77];
    if ( v36 != -1 )
    {
      if ( v36 > 0x7FFFFFFE || v49 > 0x7FFFFFFF )
      {
        *v50 = 0;
      }
      else
      {
        v51 = v36;
        v52 = v24;
        do
        {
          if ( !v51 )
            break;
          if ( !*v52 )
            break;
          *v50++ = *v52++;
          --v51;
          --v49;
        }
        while ( v49 );
        v53 = v50 - 1;
        if ( v49 )
          v53 = v50;
        *v53 = 0;
      }
    }
    v77 += v36;
    v83 = v36 + v48;
LABEL_103:
    if ( v29 )
    {
      if ( v29 == 1 )
      {
        v82 = 0;
        v84 = 0;
        v83 = 0;
        *a3 = v33;
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v85);
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v82);
        return 0;
      }
    }
    else if ( v3 )
    {
      v81 = 0;
      if ( v24 )
      {
        v75 = GetProcessHeap();
        HeapFree(v75, 0, v24);
        v85 = 0;
      }
      v86 = -1;
      v87 = -1;
      FirstComponent = _FindFirstComponent(v3, &v85, (const unsigned __int16 **)&v81);
      v29 = FirstComponent;
      if ( FirstComponent < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x85,
          (unsigned int)"minio\\profapi\\env.cpp",
          (const char *)(unsigned int)FirstComponent,
          v77);
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v85);
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v82);
        return v29;
      }
      v3 = v81;
      v24 = v85;
    }
  }
  if ( v77 == -1 )
  {
    if ( lpMem )
    {
      v35 = v34;
      v77 = v34;
    }
    else
    {
      v35 = 0;
      v77 = 0;
    }
  }
  v40 = v35 + 2;
  if ( v35 + 2 < (unsigned __int64)(v35 + 1) )
  {
LABEL_82:
    v43 = -2147024362;
    goto LABEL_83;
  }
  v41 = v79;
  if ( v79 == -1 )
  {
    if ( v35 == -1 )
    {
      if ( !lpMem )
      {
        v35 = 0;
        v77 = 0;
        goto LABEL_187;
      }
      v35 = v34;
      v77 = v34;
    }
    if ( lpMem )
    {
      v41 = v35 + 1;
LABEL_160:
      v84 = v41;
      v79 = v41;
      goto LABEL_79;
    }
LABEL_187:
    v41 = 0;
    goto LABEL_160;
  }
LABEL_79:
  if ( !v41 )
  {
    v81 = 0;
    if ( !is_mul_ok(v40, 2u) )
      goto LABEL_82;
    v54 = GetProcessHeap();
    v55 = HeapAlloc(v54, 0, 2 * v40);
    if ( v55 )
    {
      lpMem = v55;
      v43 = 0;
      v79 = v40;
      v84 = v40;
      v33 = v55;
      v82 = v55;
      *v55 = 0;
    }
    else
    {
      v43 = -2147024882;
    }
    if ( v43 < 0 )
      goto LABEL_83;
    goto LABEL_110;
  }
  if ( v40 <= v41 )
    goto LABEL_111;
  v81 = 0;
  v42 = 2 * v41;
  if ( !is_mul_ok(v41, 2u) )
    goto LABEL_82;
  v69 = v41 + 2048;
  v70 = v41;
  v71 = v40;
  if ( v70 <= 0x800 )
    v69 = v42;
  if ( v40 <= v69 )
    v71 = v69;
  v79 = v71;
  if ( lpMem )
  {
    v72 = GetProcessHeap();
    v73 = HeapReAlloc(v72, 0, lpMem, 2 * v71);
  }
  else
  {
    v73 = (_WORD *)Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Alloc(2 * v71);
  }
  if ( v73 )
  {
    v84 = v71;
    v33 = v73;
    lpMem = v73;
    v82 = v73;
LABEL_110:
    v35 = v77;
LABEL_111:
    v56 = 1;
    v57 = L";";
    v58 = 2;
    v59 = &v33[v35];
    do
    {
      if ( !v56 )
        break;
      if ( !*v57 )
        break;
      *v59++ = *v57++;
      --v56;
      --v58;
    }
    while ( v58 );
    v60 = v59 - 1;
    if ( v58 )
      v60 = v59;
    v77 = ++v35;
    v83 = v35;
    *v60 = 0;
    goto LABEL_60;
  }
  v43 = -2147024882;
LABEL_83:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x7B,
    (unsigned int)"minio\\profapi\\env.cpp",
    (const char *)(unsigned int)v43,
    v77);
  if ( v24 )
  {
    v44 = GetProcessHeap();
    HeapFree(v44, 0, v24);
  }
  if ( v33 )
  {
    v45 = GetProcessHeap();
    HeapFree(v45, 0, v33);
  }
  return (unsigned int)v43;
}

```

## disassembly

```asm
0x180005160  mov     [rsp-38h+arg_8], rbx
0x180005165  mov     [rsp-38h+arg_10], r8
0x18000516a  mov     [rsp-38h+Str], rcx
0x18000516f  push    rbp
0x180005170  push    rsi
0x180005171  push    rdi
0x180005172  push    r12
0x180005174  push    r13
0x180005176  push    r14
0x180005178  push    r15
0x18000517a  mov     rbp, rsp
0x18000517d  sub     rsp, 70h
0x180005181  xor     r13d, r13d
0x180005184  mov     rsi, rdx
0x180005187  mov     [r8], r13
0x18000518a  mov     edx, r13d
0x18000518d  mov     [rbp+var_48], rdx
0x180005191  mov     r12, rcx
0x180005194  mov     [rbp+var_20], rdx
0x180005198  mov     r15d, r13d
0x18000519b  mov     [rbp+lpMem], r13
0x18000519f  mov     [rbp+var_30], r13
0x1800051a3  mov     [rbp+var_50], r13
0x1800051a7  mov     [rbp+var_28], r13
0x1800051ab  test    rcx, rcx
0x1800051ae  jz      loc_180005A92
0x1800051b4  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1800051bb  nop     dword ptr [rax+rax+00h]
0x1800051c0  inc     rbx
0x1800051c3  cmp     [rcx+rbx*2], dx
0x1800051c7  jnz     short loc_1800051C0
0x1800051c9  lea     rdi, [rbx+1]
0x1800051cd  cmp     rdi, rbx
0x1800051d0  jb      short loc_1800051EA
0x1800051d2  mov     eax, 2
0x1800051d7  mov     [rbp+arg_18], r13
0x1800051db  mul     rdi
0x1800051de  mov     r14, rax
0x1800051e1  test    rdx, rdx
0x1800051e4  jz      loc_180005277
0x1800051ea  mov     r14d, 80070216h
0x1800051f0  test    r14d, r14d
0x1800051f3  js      loc_180005315
0x1800051f9  mov     [rbp+var_18], r13
0x1800051fd  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFFh
0x180005205  mov     [rbp+var_8], 0FFFFFFFFFFFFFFFFh
0x18000520d  test    rsi, rsi
0x180005210  jnz     loc_18000534E
0x180005216  mov     edi, 80070057h
0x18000521b  mov     edx, 10h; void *
0x180005220  mov     rcx, [rbp+38h]; this
0x180005224  lea     r8, aMinioProfapiEn; "minio\\profapi\\env.cpp"
0x18000522b  mov     r9d, edi; char *
0x18000522e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005233  mov     rcx, [rbp+38h]; this
0x180005237  lea     r8, aMinioProfapiEn; "minio\\profapi\\env.cpp"
0x18000523e  mov     r9d, edi; char *
0x180005241  mov     edx, 73h ; 's'; void *
0x180005246  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000524b  lea     rcx, [rbp+var_18]
0x18000524f  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180005254  lea     rcx, [rbp+var_30]
0x180005258  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18000525d  mov     eax, edi
0x18000525f  mov     rbx, [rsp+70h+arg_8]
0x180005267  add     rsp, 70h
0x18000526b  pop     r15
0x18000526d  pop     r14
0x18000526f  pop     r13
0x180005271  pop     r12
0x180005273  pop     rdi
0x180005274  pop     rsi
0x180005275  pop     rbp
0x180005276  retn
0x180005277  call    cs:__imp_GetProcessHeap
0x18000527d  mov     r8, r14; dwBytes
0x180005280  xor     edx, edx; dwFlags
0x180005282  mov     rcx, rax; hHeap
0x180005285  call    cs:__imp_HeapAlloc
0x18000528b  test    rax, rax
0x18000528e  jz      short loc_18000530F
0x180005290  mov     [rbp+var_50], rbx
0x180005294  mov     r9, rbx
0x180005297  mov     [rbp+var_48], rdi
0x18000529b  mov     r14d, r13d
0x18000529e  mov     [rbp+var_20], rdi
0x1800052a2  mov     r15, rax
0x1800052a5  mov     [rbp+lpMem], rax
0x1800052a9  mov     [rbp+var_30], rax
0x1800052ad  mov     [rax], r13w
0x1800052b1  test    rdi, rdi
0x1800052b4  jz      short loc_180005306
0x1800052b6  cmp     rbx, 7FFFFFFEh
0x1800052bd  ja      loc_180005AEA
0x1800052c3  cmp     rdi, 7FFFFFFFh
0x1800052ca  ja      loc_180005AEA
0x1800052d0  mov     rcx, r12
0x1800052d3  mov     rdx, rax
0x1800052d6  test    rbx, rbx
0x1800052d9  jz      short loc_1800052F7
0x1800052db  movzx   eax, word ptr [rcx]
0x1800052de  test    ax, ax
0x1800052e1  jz      short loc_1800052F7
0x1800052e3  mov     [rdx], ax
0x1800052e6  add     rcx, 2
0x1800052ea  add     rdx, 2
0x1800052ee  dec     rbx
0x1800052f1  sub     rdi, 1
0x1800052f5  jnz     short loc_1800052D6
0x1800052f7  test    rdi, rdi
0x1800052fa  lea     rcx, [rdx-2]
0x1800052fe  cmovnz  rcx, rdx
0x180005302  mov     [rcx], r13w
0x180005306  mov     [rbp+var_28], r9
0x18000530a  jmp     loc_1800051F0
0x18000530f  mov     r14d, 8007000Eh
0x180005315  mov     rcx, [rbp+38h]; this
0x180005319  lea     r8, aMinioProfapiEn; "minio\\profapi\\env.cpp"
0x180005320  mov     r9d, r14d; char *
0x180005323  mov     edx, 6Eh ; 'n'; void *
0x180005328  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000532d  test    r15, r15
0x180005330  jz      short loc_180005346
0x180005332  call    cs:__imp_GetProcessHeap
0x180005338  mov     r8, r15; lpMem
0x18000533b  xor     edx, edx; dwFlags
0x18000533d  mov     rcx, rax; hHeap
0x180005340  call    cs:__imp_HeapFree
0x180005346  mov     eax, r14d
0x180005349  jmp     loc_18000525F
0x18000534e  cmp     r13w, [rsi]
0x180005352  jz      loc_180005216
0x180005358  mov     ebx, r13d
0x18000535b  mov     r14, rsi
0x18000535e  xchg    ax, ax
0x180005360  movzx   eax, word ptr [r14]
0x180005364  test    ax, ax
0x180005367  jz      short loc_180005377
0x180005369  cmp     ax, 3Bh ; ';'
0x18000536d  jz      short loc_180005377
0x18000536f  inc     ebx
0x180005371  add     r14, 2
0x180005375  jnz     short loc_180005360
0x180005377  lea     r15d, [rbx+1]
0x18000537b  mov     [rbp+arg_18], r13
0x18000537f  mov     eax, 2
0x180005384  mul     r15
0x180005387  mov     rdi, rax
0x18000538a  test    rdx, rdx
0x18000538d  jz      short loc_18000539E
0x18000538f  mov     edi, 80070216h
0x180005394  mov     edx, 1Eh
0x180005399  jmp     loc_180005220
0x18000539e  call    cs:__imp_GetProcessHeap
0x1800053a4  mov     r8, rdi; dwBytes
0x1800053a7  mov     edx, 8; dwFlags
0x1800053ac  mov     rcx, rax; hHeap
0x1800053af  call    cs:__imp_HeapAlloc
0x1800053b5  mov     r12, rax
0x1800053b8  mov     eax, 8007000Eh
0x1800053bd  test    r12, r12
0x1800053c0  mov     dword ptr [rbp+arg_18], eax
0x1800053c3  mov     edi, eax
0x1800053c5  cmovnz  edi, r13d
0x1800053c9  jz      short loc_180005394
0x1800053cb  test    r15, r15
0x1800053ce  jz      short loc_180005422
0x1800053d0  cmp     r15, 7FFFFFFFh
0x1800053d7  ja      loc_180005B3E
0x1800053dd  cmp     ebx, 7FFFFFFEh
0x1800053e3  ja      loc_180005B06
0x1800053e9  mov     ecx, ebx
0x1800053eb  mov     r8, r15
0x1800053ee  mov     rdx, r12
0x1800053f1  test    rcx, rcx
0x1800053f4  jz      short loc_180005412
0x1800053f6  movzx   eax, word ptr [rsi]
0x1800053f9  test    ax, ax
0x1800053fc  jz      short loc_180005412
0x1800053fe  mov     [rdx], ax
0x180005401  add     rsi, 2
0x180005405  add     rdx, 2
0x180005409  dec     rcx
0x18000540c  sub     r8, 1
0x180005410  jnz     short loc_1800053F1
0x180005412  test    r8, r8
0x180005415  lea     rcx, [rdx-2]
0x180005419  cmovnz  rcx, rdx
0x18000541d  xor     eax, eax
0x18000541f  mov     [rcx], ax
0x180005422  mov     eax, 5Ch ; '\'
0x180005427  cmp     ax, [r12+r15*2-2]
0x18000542d  jz      loc_180005B4A
0x180005433  test    r14, r14
0x180005436  jnz     loc_1800059C0
0x18000543c  mov     [rbp+var_18], r12
0x180005440  test    r13, r13
0x180005443  jz      short loc_18000544E
0x180005445  xor     r14d, r14d
0x180005448  jmp     short loc_180005454
0x18000544a  mov     [rbp+var_18], r12
0x18000544e  mov     r14d, 1
0x180005454  mov     edi, 3Bh ; ';'
0x180005459  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180005460  cmp     word ptr [r12+rbx*2+2], 0
0x180005467  lea     rbx, [rbx+1]
0x18000546b  jnz     short loc_180005460
0x18000546d  mov     rcx, [rbp+Str]; Str
0x180005471  test    rcx, rcx
0x180005474  jnz     loc_1800057E2
0x18000547a  mov     r15, [rbp+lpMem]
0x18000547e  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180005485  inc     rcx
0x180005488  cmp     word ptr [r15+rcx*2], 0
0x18000548e  jnz     short loc_180005485
0x180005490  cmp     word ptr [r15+rcx*2-2], 3Bh ; ';'
0x180005497  mov     r10, [rbp+var_50]
0x18000549b  jnz     loc_18000555F
0x1800054a1  test    r12, r12
0x1800054a4  jz      loc_1800056DD
0x1800054aa  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x1800054b1  inc     rsi
0x1800054b4  cmp     word ptr [r12+rsi*2], 0
0x1800054ba  jnz     short loc_1800054B1
0x1800054bc  cmp     r10, 0FFFFFFFFFFFFFFFFh
0x1800054c0  jnz     short loc_1800054E3
0x1800054c2  test    r15, r15
0x1800054c5  jz      loc_180005AFE
0x1800054cb  nop     dword ptr [rax+rax+00h]
0x1800054d0  inc     r10
0x1800054d3  cmp     word ptr [r15+r10*2], 0
0x1800054d9  jnz     short loc_1800054D0
0x1800054db  mov     [rbp+var_28], r10
0x1800054df  mov     [rbp+var_50], r10
0x1800054e3  lea     rax, [rsi+r10]
0x1800054e7  lea     rdi, [rax+1]
0x1800054eb  cmp     rdi, rax
0x1800054ee  jb      short loc_180005529
0x1800054f0  mov     rcx, [rbp+var_48]
0x1800054f4  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800054f8  jz      loc_180005954
0x1800054fe  test    rcx, rcx
0x180005501  jz      loc_180005611
0x180005507  cmp     rdi, rcx
0x18000550a  jbe     loc_18000566F
0x180005510  mov     eax, 2
0x180005515  mov     [rbp+var_38], 0
0x18000551d  mul     rcx
0x180005520  test    rdx, rdx
0x180005523  jz      loc_180005854
0x180005529  mov     ebx, 80070216h
0x18000552e  mov     rcx, [rbp+38h]; this
0x180005532  lea     r8, aMinioProfapiEn; "minio\\profapi\\env.cpp"
0x180005539  mov     r9d, ebx; char *
0x18000553c  mov     edx, 7Eh ; '~'; void *
0x180005541  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005546  lea     rcx, [rbp+var_18]
0x18000554a  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18000554f  lea     rcx, [rbp+var_30]
0x180005553  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180005558  mov     eax, ebx
0x18000555a  jmp     loc_18000525F
0x18000555f  cmp     r10, 0FFFFFFFFFFFFFFFFh
0x180005563  jnz     short loc_180005575
0x180005565  test    r15, r15
0x180005568  jz      loc_180005B12
0x18000556e  mov     r10, rcx
0x180005571  mov     [rbp+var_50], rcx
0x180005575  lea     rax, [r10+1]
0x180005579  lea     rdi, [rax+1]
0x18000557d  cmp     rdi, rax
0x180005580  jb      short loc_1800055BB
0x180005582  mov     rsi, [rbp+var_48]
0x180005586  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18000558a  jz      loc_180005990
0x180005590  test    rsi, rsi
0x180005593  jz      loc_180005728
0x180005599  cmp     rdi, rsi
0x18000559c  jbe     loc_18000578A
0x1800055a2  mov     eax, 2
0x1800055a7  mov     [rbp+var_38], 0
0x1800055af  mul     rsi
0x1800055b2  test    rdx, rdx
0x1800055b5  jz      loc_1800058C3
0x1800055bb  mov     ebx, 80070216h
0x1800055c0  mov     rcx, [rbp+38h]; this
0x1800055c4  lea     r8, aMinioProfapiEn; "minio\\profapi\\env.cpp"
0x1800055cb  mov     r9d, ebx; char *
0x1800055ce  mov     edx, 7Bh ; '{'; void *
0x1800055d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800055d8  test    r12, r12
0x1800055db  jz      short loc_1800055F1
0x1800055dd  call    cs:__imp_GetProcessHeap
0x1800055e3  mov     r8, r12; lpMem
0x1800055e6  xor     edx, edx; dwFlags
0x1800055e8  mov     rcx, rax; hHeap
0x1800055eb  call    cs:__imp_HeapFree
0x1800055f1  test    r15, r15
0x1800055f4  jz      short loc_18000560A
0x1800055f6  call    cs:__imp_GetProcessHeap
  ... truncated ...
```
