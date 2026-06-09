# _pSpUtilsStringTableAddString

- ea: `0x180006360`
- end: `0x180006d67`
- name: `_pSpUtilsStringTableAddString`
- size: `2567`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180005fc0`

## callees

- `0x180006360`
- `0x180006d70`
- `0x18000c7e8`
- `0x1800209a0`
- `0x180020c1c`
- `0x180020cb8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000677b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800069f6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006a55`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006aa5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006c04`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006ced`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006d4a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000677b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800069f6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006a55`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006aa5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006c04`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006ced`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006d4a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800063f1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006524`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800063f1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006524`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180006bb3`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180006be0`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180006bb3`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180006be0`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180006835`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180006cb7`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180006835`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180006cb7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180006904`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180006904`

## pseudocode

```c
__int64 pSpUtilsStringTableAddString(__int64 a1, _WORD *a2, __int64 a3, ...)
{
  _WORD *v3; // r9
  int v4; // r15d
  int v5; // r12d
  int v6; // r14d
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rbx
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // rsi
  __int64 v12; // rdi
  __int64 v13; // rcx
  _WORD *v14; // rdx
  _WORD *v15; // r8
  _WORD *v16; // rcx
  int v17; // ecx
  unsigned int v18; // esi
  unsigned __int64 v19; // r13
  __int64 v20; // rax
  __int64 v21; // rax
  unsigned __int64 v22; // rbx
  unsigned __int64 v23; // rax
  int v24; // r10d
  __int64 v25; // rcx
  _WORD *v26; // rdx
  _WORD *v27; // r8
  __int64 v28; // r9
  __int64 v29; // r15
  int v30; // eax
  unsigned int v31; // r13d
  WCHAR *v32; // rdx
  char *v33; // r10
  unsigned int v34; // ecx
  __int64 v35; // rax
  _DWORD *v36; // rbx
  __int64 v37; // rax
  _WORD *v38; // rdx
  int v39; // r10d
  void *v40; // r14
  _WORD *v41; // rcx
  __int64 v42; // r9
  __int64 v44; // rdx
  __int64 v45; // r9
  unsigned int v46; // r12d
  __int64 v47; // rcx
  unsigned __int64 v48; // rax
  const WCHAR *v49; // rbx
  const WCHAR *v50; // r14
  int v51; // esi
  int v52; // eax
  int v53; // eax
  __int64 v54; // rax
  bool v55; // zf
  unsigned int v56; // esi
  unsigned int v57; // r9d
  _BYTE *v58; // r12
  _QWORD *v59; // r14
  HANDLE *v60; // rbx
  int v61; // r15d
  __int64 v62; // r9
  int lpDestStr; // [rsp+20h] [rbp-118h]
  unsigned int v64; // [rsp+30h] [rbp-108h]
  const WCHAR *v65; // [rsp+38h] [rbp-100h]
  unsigned int v66; // [rsp+48h] [rbp-F0h] BYREF
  int v67; // [rsp+4Ch] [rbp-ECh]
  int v68; // [rsp+50h] [rbp-E8h]
  unsigned int v69; // [rsp+54h] [rbp-E4h]
  unsigned int v70; // [rsp+58h] [rbp-E0h]
  int v71; // [rsp+5Ch] [rbp-DCh]
  int v72; // [rsp+60h] [rbp-D8h]
  int v73; // [rsp+64h] [rbp-D4h]
  char *v74; // [rsp+68h] [rbp-D0h]
  unsigned __int64 v75; // [rsp+70h] [rbp-C8h] BYREF
  _WORD *v76; // [rsp+78h] [rbp-C0h]
  __int64 v77; // [rsp+80h] [rbp-B8h]
  unsigned __int64 v78; // [rsp+88h] [rbp-B0h]
  unsigned __int64 v79; // [rsp+90h] [rbp-A8h] BYREF
  unsigned __int64 v80; // [rsp+98h] [rbp-A0h]
  _WORD *v81; // [rsp+A0h] [rbp-98h]
  __int64 v82; // [rsp+A8h] [rbp-90h]
  unsigned __int64 v83; // [rsp+B0h] [rbp-88h]
  _WORD *v84; // [rsp+B8h] [rbp-80h]
  unsigned __int64 v85; // [rsp+C0h] [rbp-78h]
  __int64 v86; // [rsp+C8h] [rbp-70h]
  char *v87; // [rsp+D0h] [rbp-68h]
  _WORD *v88; // [rsp+D8h] [rbp-60h]
  __int64 v89; // [rsp+E0h] [rbp-58h]
  __int64 v90; // [rsp+E8h] [rbp-50h]
  unsigned __int64 v91; // [rsp+F0h] [rbp-48h]
  _WORD *lpMem; // [rsp+148h] [rbp+10h]
  int v94; // [rsp+150h] [rbp+18h]
  int i; // [rsp+150h] [rbp+18h]
  __int64 v96; // [rsp+158h] [rbp+20h] BYREF
  va_list va; // [rsp+158h] [rbp+20h]
  __int64 v98; // [rsp+160h] [rbp+28h]
  va_list va1; // [rsp+168h] [rbp+30h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v96 = va_arg(va1, _QWORD);
  v98 = va_arg(va1, _QWORD);
  lpMem = a2;
  v3 = a2;
  v4 = 0;
  v66 = 0;
  v70 = 0;
  v65 = 0;
  if ( !a2 || *(_BYTE *)(a1 + 40) == 2 )
    return 0xFFFFFFFFLL;
  v5 = 0;
  v6 = 0;
  v87 = 0;
  v83 = (unsigned __int64)a2;
  v7 = -1;
  do
    ++v7;
  while ( a2[v7] );
  v8 = (unsigned int)(v7 + 1);
  v9 = (unsigned int)v8;
  v10 = 2 * v8;
  if ( v10 > 0xFFFFFFFF )
  {
    v11 = 0;
  }
  else
  {
    v11 = (unsigned __int64)HeapAlloc(hHeap, 0, (unsigned int)v10);
    v3 = lpMem;
  }
  v12 = 2147483646;
  if ( v11 )
  {
    if ( (unsigned __int64)(v9 - 1) > 0x7FFFFFFE )
    {
      v17 = -2147024809;
      if ( v9 )
        *(_WORD *)v11 = 0;
    }
    else
    {
      v13 = 2147483646;
      v14 = v3;
      v15 = (_WORD *)v11;
      do
      {
        if ( !v13 )
          break;
        if ( !*v14 )
          break;
        *v15++ = *v14++;
        --v13;
        --v9;
      }
      while ( v9 );
      v16 = v15 - 1;
      if ( v9 )
        v16 = v15;
      *v16 = 0;
      v17 = -2147024774;
      if ( v9 )
        v17 = 0;
    }
    if ( v17 < 0 )
    {
      HeapFree(hHeap, 0, (LPVOID)v11);
      v11 = 0;
      v3 = lpMem;
    }
    if ( v11 )
    {
      v75 = v11;
      if ( (v11 & 0xFFFFFFFFFFFF0000uLL) != 0 )
      {
        v62 = -1;
        do
          ++v62;
        while ( *(_WORD *)(v11 + 2 * v62) );
        LCMapStringW(0x400u, 0x100u, (LPCWSTR)v11, v62 + 1, (LPWSTR)v11, v62 + 1);
      }
      else
      {
        LCMapStringW(0x400u, 0x100u, (LPCWSTR)&v75, 1, (LPWSTR)&v75, 1);
      }
      v3 = (_WORD *)v11;
      lpMem = (_WORD *)v11;
      v83 = v11;
      v6 = 1;
      v5 = -2147483647;
    }
  }
  if ( !v6 )
    return 0xFFFFFFFFLL;
  LODWORD(v96) = 0;
  v18 = -1;
  LODWORD(v98) = -1;
  v73 = -1;
  v68 = 0;
  v72 = 0;
  v19 = (unsigned __int64)v3;
  v80 = (unsigned __int64)v3;
  v94 = v5 & 1;
  if ( (v5 & 1) == 0 )
  {
    if ( v5 >= 0 )
    {
      v78 = 0;
      if ( !v3 )
        goto LABEL_42;
      v20 = -1;
      do
        ++v20;
      while ( v3[v20] );
      v21 = (unsigned int)(v20 + 1);
      v22 = (unsigned int)v21;
      v23 = 2 * v21;
      v91 = v23;
      if ( v23 <= 0xFFFFFFFF )
      {
        v19 = (unsigned __int64)HeapAlloc(hHeap, 0, (unsigned int)v23);
        v3 = lpMem;
      }
      else
      {
        v19 = 0;
      }
      v78 = v19;
      if ( !v19 )
        goto LABEL_42;
      v67 = 0;
      if ( !v22 || (v24 = 0, v22 > 0x7FFFFFFF) )
        v24 = -2147024809;
      v67 = v24;
      if ( v24 < 0 )
      {
        if ( v22 )
          *(_WORD *)v19 = 0;
      }
      else
      {
        v25 = 2147483646;
        v86 = 2147483646;
        v26 = v3;
        v84 = v3;
        v85 = v22;
        v27 = (_WORD *)v19;
        v76 = (_WORD *)v19;
        v24 = 0;
        v28 = 0;
        v77 = 0;
        while ( v22 )
        {
          if ( !v25 || !*v26 )
            goto LABEL_38;
          *v27++ = *v26;
          v76 = v27;
          v84 = ++v26;
          v85 = --v22;
          v86 = --v25;
          v77 = ++v28;
        }
        v76 = --v27;
        v77 = v28 - 1;
        v24 = -2147024774;
LABEL_38:
        *v27 = 0;
        v67 = v24;
      }
      if ( v24 < 0 )
      {
        HeapFree(hHeap, 0, (LPVOID)v19);
        v19 = 0;
        v78 = 0;
      }
      if ( !v19 )
        goto LABEL_42;
      v79 = v19;
      if ( (v19 & 0xFFFFFFFFFFFF0000uLL) != 0 )
      {
        v45 = -1;
        do
          ++v45;
        while ( *(_WORD *)(v19 + 2 * v45) );
        LCMapStringW(0x400u, 0x100u, (LPCWSTR)v19, v45 + 1, (LPWSTR)v19, v45 + 1);
      }
      else
      {
        LCMapStringW(0x400u, 0x100u, (LPCWSTR)&v79, 1, (LPWSTR)&v79, 1);
      }
      v80 = v19;
      v4 = 1;
      v72 = 1;
    }
    v5 |= 0x80000001;
  }
  if ( (unsigned int)ComputeHashValue(v19, &v66, v5 & 0xFFFFFFFD, (__int64 *)va) )
  {
    v46 = v96;
    v47 = *(int *)(*(_QWORD *)a1 + 4LL * (unsigned int)v96);
    if ( (int)v47 >= 2036 )
    {
      v48 = *(unsigned int *)(a1 + 8);
      if ( (int)v47 < (int)v48 )
      {
        v49 = (const WCHAR *)(*(_QWORD *)a1 + v47);
        v50 = 0;
        v51 = v48 / ((unsigned __int64)*(unsigned int *)(a1 + 32) + 6) + 1;
        v68 = v51;
        v52 = v94 ^ 1;
        for ( i = v94 ^ 1; ; v52 = i )
        {
          v53 = CompareStringOrdinal(v49 + 2, -1, (LPCWCH)v19, -1, v52);
          if ( v53 == 2 )
          {
            v18 = (_DWORD)v49 - *(_DWORD *)a1;
            v73 = v18;
            goto LABEL_82;
          }
          if ( v53 == 1 && !i )
          {
            v49 = v50;
            v18 = v98;
            goto LABEL_82;
          }
          v54 = *(int *)v49;
          if ( (_DWORD)v54 == -1 )
          {
            v18 = v98;
            goto LABEL_82;
          }
          if ( (int)v54 < 2036 )
            break;
          if ( (int)v54 >= *(_DWORD *)(a1 + 8) )
            break;
          v50 = v49;
          v49 = (const WCHAR *)(*(_QWORD *)a1 + v54);
          v55 = v51-- == 1;
          v68 = v51;
          if ( v55 )
            break;
        }
        v18 = v98;
      }
    }
  }
  else
  {
    v46 = v96;
  }
  v49 = 0;
LABEL_82:
  if ( v4 )
    HeapFree(hHeap, 0, (LPVOID)v19);
  v70 = v46;
  v65 = v49;
LABEL_42:
  if ( v18 == -1 )
  {
    v29 = a1;
    v30 = *(_DWORD *)(a1 + 32);
    v31 = v30 + 2 * (v66 + 3);
    if ( (((_BYTE)v30 + 2 * ((_BYTE)v66 + 3)) & 3) != 0 )
      v31 = (v31 & 0xFFFFFFFC) + 4;
    v32 = (WCHAR *)v65;
    v33 = v87;
    while ( 1 )
    {
      v34 = *(_DWORD *)(v29 + 12);
      v35 = *(unsigned int *)(v29 + 8);
      if ( (unsigned int)v35 + v31 <= v34 )
        break;
      v56 = *(_DWORD *)(v29 + 12);
      v57 = 0x100000;
      if ( (((v34 / 0xC00) & 0x1FFFFF) + 1) << 11 < 0x100000 )
        v57 = (((v34 / 0xC00) & 0x1FFFFF) + 1) << 11;
      if ( v57 <= ~v34 )
        v56 = v57 + v34;
      v69 = v56;
      if ( v56 < v34 )
        v56 = v35 + v31;
      v69 = v56;
      v58 = *(_BYTE **)v29;
      if ( *(_BYTE *)(v29 + 40) == 1 )
      {
        v33 = (char *)HeapReAlloc(hHeap, 0, *(LPVOID *)v29, v56);
        v74 = v33;
        if ( !v33 )
        {
          v56 = v31 + *(_DWORD *)(v29 + 8);
          v69 = v56;
          v33 = (char *)HeapReAlloc(hHeap, 0, *(LPVOID *)v29, v56);
          v74 = v33;
          if ( !v33 )
          {
            HeapFree(hHeap, 0, lpMem);
            return 0xFFFFFFFFLL;
          }
        }
      }
      else if ( *(_BYTE *)(v29 + 40) == 3 )
      {
        v59 = (_QWORD *)(v29 + 64);
        v60 = (HANDLE *)(v29 + 56);
        pSetupUnmapFileAndSetEOF(*(HANDLE *)(v29 + 48), *(HANDLE *)(v29 + 56), *(LPCVOID *)(v29 + 64));
        *(_QWORD *)(v29 + 56) = 0;
        *(_QWORD *)v29 = 0;
        v61 = *(_DWORD *)(v29 + 12) + 16;
        if ( (unsigned int)pSetupMapFileForWrite(*(void **)(a1 + 48), v56 + 16, v60, v59) )
          return 0xFFFFFFFFLL;
        lpDestStr = v56 - v61 + 16;
        v29 = a1;
        if ( (unsigned int)pSetupGrowMappedFileAtOffset(*(HANDLE *)(a1 + 48), lpDestStr) )
          return 0xFFFFFFFFLL;
        v33 = (char *)(*v59 + 16LL);
        v74 = v33;
      }
      v32 = (WCHAR *)v65;
      if ( v65 )
      {
        v32 = (WCHAR *)((char *)v65 + v33 - v58);
        v65 = v32;
      }
      *(_QWORD *)v29 = v33;
      *(_DWORD *)(v29 + 12) = v56;
    }
    v36 = (_DWORD *)(*(_QWORD *)v29 + v35);
    if ( v32 )
    {
      *v36 = *(_DWORD *)v32;
      *(_DWORD *)v32 = (_DWORD)v36 - *(_DWORD *)v29;
    }
    else
    {
      v44 = 4LL * v70;
      *v36 = *(_DWORD *)(v44 + *(_QWORD *)v29);
      *(_DWORD *)(v44 + *(_QWORD *)v29) = (_DWORD)v36 - *(_DWORD *)v29;
    }
    v37 = v31;
    v38 = v36 + 1;
    v71 = 0;
    if ( !v31 || (v39 = 0, v31 > 0x7FFFFFFFuLL) )
      v39 = -2147024809;
    v71 = v39;
    if ( v39 < 0 )
    {
      if ( v31 )
        *v38 = 0;
      v40 = lpMem;
    }
    else
    {
      v90 = 2147483646;
      v40 = lpMem;
      v41 = lpMem;
      v88 = lpMem;
      v89 = v31;
      v81 = v36 + 1;
      v39 = 0;
      v42 = 0;
      v82 = 0;
      while ( v37 )
      {
        if ( !v12 || !*v41 )
          goto LABEL_57;
        *v38++ = *v41;
        v81 = v38;
        v88 = ++v41;
        v89 = --v37;
        v90 = --v12;
        v82 = ++v42;
      }
      v81 = --v38;
      v82 = v42 - 1;
      v39 = -2147024774;
LABEL_57:
      *v38 = 0;
      v71 = v39;
    }
    if ( v39 >= 0 )
    {
      v74 = (char *)v36 + 2 * v66 + 6;
      memset_0(v74, 0, *(unsigned int *)(v29 + 32));
      *(_DWORD *)(v29 + 8) += v31;
      if ( *(_BYTE *)(v29 + 40) == 3 )
        **(_DWORD **)(v29 + 64) = *(_DWORD *)(v29 + 8);
      v64 = (_DWORD)v36 - *(_DWORD *)v29;
      HeapFree(hHeap, 0, v40);
      return v64;
    }
    else
    {
      HeapFree(hHeap, 0, v40);
      return 0xFFFFFFFFLL;
    }
  }
  else
  {
    HeapFree(hHeap, 0, lpMem);
    return v18;
  }
}

```

## disassembly

```asm
0x180006360  mov     rax, rsp
0x180006363  mov     [rax+20h], r9
0x180006367  mov     [rax+18h], r8d
0x18000636b  mov     [rax+10h], rdx
0x18000636f  mov     [rax+8], rcx
0x180006373  push    rbx
0x180006374  push    rsi
0x180006375  push    rdi
0x180006376  push    r12
0x180006378  push    r13
0x18000637a  push    r14
0x18000637c  push    r15
0x18000637e  sub     rsp, 100h
0x180006385  mov     r9, rdx
0x180006388  xor     r15d, r15d
0x18000638b  mov     [rsp+138h+var_F0], r15d
0x180006390  mov     [rsp+138h+var_E0], r15d
0x180006395  mov     [rsp+138h+var_100], r15
0x18000639a  test    rdx, rdx
0x18000639d  jz      loc_180006D60
0x1800063a3  cmp     byte ptr [rcx+28h], 2
0x1800063a7  jz      loc_180006D60
0x1800063ad  mov     r12d, r15d
0x1800063b0  mov     r14d, r15d
0x1800063b3  mov     [rax-68h], r15
0x1800063b7  mov     [rsp+138h+var_88], rdx
0x1800063bf  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800063c6  inc     rax
0x1800063c9  cmp     [rdx+rax*2], r12w
0x1800063ce  jnz     short loc_1800063C6
0x1800063d0  inc     eax
0x1800063d2  mov     ebx, eax
0x1800063d4  add     rax, rax
0x1800063d7  mov     ecx, 0FFFFFFFFh
0x1800063dc  cmp     rax, rcx
0x1800063df  ja      loc_180006C76
0x1800063e5  mov     r8d, eax; dwBytes
0x1800063e8  xor     edx, edx; dwFlags
0x1800063ea  mov     rcx, cs:hHeap; hHeap
0x1800063f1  call    cs:__imp_HeapAlloc
0x1800063f7  mov     rsi, rax
0x1800063fa  mov     r9, [rsp+138h+lpMem]
0x180006402  mov     edi, 7FFFFFFEh
0x180006407  test    rsi, rsi
0x18000640a  jz      short loc_18000646C
0x18000640c  lea     rax, [rbx-1]
0x180006410  cmp     rax, rdi
0x180006413  ja      loc_180006D27
0x180006419  mov     ecx, edi
0x18000641b  mov     rdx, r9
0x18000641e  mov     r8, rsi
0x180006421  test    rcx, rcx
0x180006424  jz      short loc_180006443
0x180006426  movzx   eax, word ptr [rdx]
0x180006429  test    ax, ax
0x18000642c  jz      short loc_180006443
0x18000642e  mov     [r8], ax
0x180006432  add     r8, 2
0x180006436  add     rdx, 2
0x18000643a  dec     rcx
0x18000643d  sub     rbx, 1
0x180006441  jnz     short loc_180006421
0x180006443  lea     rcx, [r8-2]
0x180006447  test    rbx, rbx
0x18000644a  cmovnz  rcx, r8
0x18000644e  mov     [rcx], r15w
0x180006452  mov     ecx, 8007007Ah
0x180006457  cmovnz  ecx, r15d
0x18000645b  test    ecx, ecx
0x18000645d  js      loc_180006D3E
0x180006463  test    rsi, rsi
0x180006466  jnz     loc_180006C7E
0x18000646c  test    r14d, r14d
0x18000646f  jz      loc_180006D60
0x180006475  mov     [rsp+138h+var_F8], r12d
0x18000647a  lea     r14, [rsp+138h+var_100]
0x18000647f  mov     dword ptr [rsp+138h+arg_18], r15d
0x180006487  mov     esi, 0FFFFFFFFh
0x18000648c  mov     dword ptr [rsp+138h+arg_20], esi
0x180006493  mov     [rsp+138h+var_D4], esi
0x180006497  mov     [rsp+138h+var_E8], r15d
0x18000649c  mov     [rsp+138h+var_A0], r15
0x1800064a4  mov     [rsp+138h+var_D8], r15d
0x1800064a9  mov     r13, r9
0x1800064ac  mov     [rsp+138h+var_A0], r9
0x1800064b4  mov     eax, r12d
0x1800064b7  and     eax, 1
0x1800064ba  mov     [rsp+138h+arg_10], eax
0x1800064c1  jnz     loc_18000685F
0x1800064c7  test    r12d, r12d
0x1800064ca  js      loc_18000684E
0x1800064d0  xor     r15d, r15d
0x1800064d3  mov     [rsp+138h+var_B0], r15
0x1800064db  test    r9, r9
0x1800064de  jz      loc_18000661C
0x1800064e4  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800064eb  nop     dword ptr [rax+rax+00h]
0x1800064f0  inc     rax
0x1800064f3  cmp     [r9+rax*2], r15w
0x1800064f8  jnz     short loc_1800064F0
0x1800064fa  inc     eax
0x1800064fc  mov     ebx, eax
0x1800064fe  add     rax, rax
0x180006501  mov     [rsp+138h+var_48], rax
0x180006509  mov     ecx, 0FFFFFFFFh
0x18000650e  cmp     rax, rcx
0x180006511  jbe     short loc_180006518
0x180006513  mov     r13, r15
0x180006516  jmp     short loc_180006535
0x180006518  mov     r8d, eax; dwBytes
0x18000651b  xor     edx, edx; dwFlags
0x18000651d  mov     rcx, cs:hHeap; hHeap
0x180006524  call    cs:__imp_HeapAlloc
0x18000652a  mov     r13, rax
0x18000652d  mov     r9, [rsp+138h+lpMem]
0x180006535  mov     [rsp+138h+var_B0], r13
0x18000653d  test    r13, r13
0x180006540  jz      loc_18000661C
0x180006546  mov     [rsp+138h+var_EC], r15d
0x18000654b  test    rbx, rbx
0x18000654e  jz      loc_180006A2B
0x180006554  mov     r10d, r15d
0x180006557  cmp     rbx, 7FFFFFFFh
0x18000655e  ja      loc_180006A2B
0x180006564  mov     [rsp+138h+var_EC], r10d
0x180006569  test    r10d, r10d
0x18000656c  js      loc_180006A36
0x180006572  mov     rcx, rdi
0x180006575  mov     [rsp+138h+var_70], rcx
0x18000657d  mov     rdx, r9
0x180006580  mov     [rsp+138h+var_80], rdx
0x180006588  mov     [rsp+138h+var_78], rbx
0x180006590  mov     r8, r13
0x180006593  mov     [rsp+138h+var_C0], r13
0x180006598  mov     r10d, r15d
0x18000659b  mov     r9, r15
0x18000659e  mov     [rsp+138h+var_B8], r15
0x1800065a6  test    rbx, rbx
0x1800065a9  jz      loc_18000678B
0x1800065af  test    rcx, rcx
0x1800065b2  jz      short loc_1800065F8
0x1800065b4  movzx   eax, word ptr [rdx]
0x1800065b7  test    ax, ax
0x1800065ba  jz      short loc_1800065F8
0x1800065bc  mov     [r8], ax
0x1800065c0  add     r8, 2
0x1800065c4  mov     [rsp+138h+var_C0], r8
0x1800065c9  add     rdx, 2
0x1800065cd  mov     [rsp+138h+var_80], rdx
0x1800065d5  dec     rbx
0x1800065d8  mov     [rsp+138h+var_78], rbx
0x1800065e0  dec     rcx
0x1800065e3  mov     [rsp+138h+var_70], rcx
0x1800065eb  inc     r9
0x1800065ee  mov     [rsp+138h+var_B8], r9
0x1800065f6  jmp     short loc_1800065A6
0x1800065f8  test    rbx, rbx
0x1800065fb  jz      loc_18000678B
0x180006601  mov     [r8], r15w
0x180006605  mov     [rsp+138h+var_EC], r10d
0x18000660a  test    r10d, r10d
0x18000660d  js      loc_180006A49
0x180006613  test    r13, r13
0x180006616  jnz     loc_1800067EA
0x18000661c  mov     [rsp+138h+var_108], esi
0x180006620  cmp     esi, 0FFFFFFFFh
0x180006623  jnz     loc_1800069E5
0x180006629  mov     r15, [rsp+138h+arg_0]
0x180006631  mov     eax, [r15+20h]
0x180006635  mov     r13d, [rsp+138h+var_F0]
0x18000663a  add     r13d, 3
0x18000663e  lea     r13d, [rax+r13*2]
0x180006642  test    r13b, 3
0x180006646  jz      short loc_180006650
0x180006648  and     r13d, 0FFFFFFFCh
0x18000664c  add     r13d, 4
0x180006650  mov     rdx, [rsp+138h+var_100]
0x180006655  mov     r10, [rsp+138h+var_68]
0x18000665d  mov     ecx, [r15+0Ch]
0x180006661  mov     eax, [r15+8]
0x180006665  lea     r8d, [rax+r13]
0x180006669  cmp     r8d, ecx
0x18000666c  ja      loc_180006AB0
0x180006672  mov     rcx, [r15]
0x180006675  lea     rbx, [rcx+rax]
0x180006679  test    rdx, rdx
0x18000667c  jz      loc_1800067C9
0x180006682  mov     eax, [rdx]
0x180006684  mov     [rbx], eax
0x180006686  mov     eax, ebx
0x180006688  sub     eax, [r15]
0x18000668b  mov     [rdx], eax
0x18000668d  mov     eax, r13d
0x180006690  lea     rdx, [rbx+4]
0x180006694  mov     [rsp+138h+var_DC], 0
0x18000669c  test    r13d, r13d
0x18000669f  jz      loc_180006C38
0x1800066a5  xor     r10d, r10d
0x1800066a8  cmp     rax, 7FFFFFFFh
0x1800066ae  ja      loc_180006C38
0x1800066b4  mov     [rsp+138h+var_DC], r10d
0x1800066b9  test    r10d, r10d
0x1800066bc  js      loc_180006C43
0x1800066c2  mov     [rsp+138h+var_50], rdi
0x1800066ca  mov     r14, [rsp+138h+lpMem]
0x1800066d2  mov     rcx, r14
0x1800066d5  mov     [rsp+138h+var_60], rcx
0x1800066dd  mov     [rsp+138h+var_58], rax
0x1800066e5  mov     [rsp+138h+var_98], rdx
0x1800066ed  xor     r10d, r10d
0x1800066f0  xor     r9d, r9d
0x1800066f3  mov     [rsp+138h+var_90], r9
0x1800066fb  nop     dword ptr [rax+rax+00h]
0x180006700  test    rax, rax
0x180006703  jz      loc_1800067AA
0x180006709  test    rdi, rdi
0x18000670c  jz      short loc_180006757
0x18000670e  movzx   r8d, word ptr [rcx]
0x180006712  test    r8w, r8w
0x180006716  jz      short loc_180006757
0x180006718  mov     [rdx], r8w
0x18000671c  add     rdx, 2
0x180006720  mov     [rsp+138h+var_98], rdx
0x180006728  add     rcx, 2
0x18000672c  mov     [rsp+138h+var_60], rcx
0x180006734  dec     rax
0x180006737  mov     [rsp+138h+var_58], rax
0x18000673f  dec     rdi
0x180006742  mov     [rsp+138h+var_50], rdi
0x18000674a  inc     r9
0x18000674d  mov     [rsp+138h+var_90], r9
0x180006755  jmp     short loc_180006700
0x180006757  test    rax, rax
0x18000675a  jz      short loc_1800067AA
0x18000675c  xor     eax, eax
0x18000675e  mov     [rdx], ax
0x180006761  mov     [rsp+138h+var_DC], r10d
0x180006766  xor     edx, edx; Val
0x180006768  test    r10d, r10d
0x18000676b  jns     loc_1800069AD
0x180006771  mov     r8, r14; lpMem
0x180006774  mov     rcx, cs:hHeap; hHeap
0x18000677b  call    cs:__imp_HeapFree
0x180006781  mov     eax, 0FFFFFFFFh
0x180006786  jmp     loc_180006CF5
0x18000678b  sub     r8, 2
0x18000678f  mov     [rsp+138h+var_C0], r8
0x180006794  dec     r9
0x180006797  mov     [rsp+138h+var_B8], r9
0x18000679f  mov     r10d, 8007007Ah
0x1800067a5  jmp     loc_180006601
0x1800067aa  sub     rdx, 2
0x1800067ae  mov     [rsp+138h+var_98], rdx
0x1800067b6  dec     r9
0x1800067b9  mov     [rsp+138h+var_90], r9
0x1800067c1  mov     r10d, 8007007Ah
0x1800067c7  jmp     short loc_18000675C
0x1800067c9  mov     eax, [rsp+138h+var_E0]
0x1800067cd  lea     rdx, ds:0[rax*4]
0x1800067d5  mov     eax, [rdx+rcx]
0x1800067d8  mov     [rbx], eax
0x1800067da  mov     ecx, ebx
0x1800067dc  sub     ecx, [r15]
0x1800067df  mov     rax, [r15]
0x1800067e2  mov     [rdx+rax], ecx
0x1800067e5  jmp     loc_18000668D
0x1800067ea  mov     [rsp+138h+var_A8], r13
0x1800067f2  test    r13, 0FFFFFFFFFFFF0000h
0x1800067f9  jz      loc_180006A03
0x1800067ff  mov     r9, 0FFFFFFFFFFFFFFFFh
0x180006806  nop     word ptr [rax+rax+00000000h]
0x180006810  inc     r9
0x180006813  cmp     [r13+r9*2+0], r15w
0x180006819  jnz     short loc_180006810
0x18000681b  inc     r9d; cchSrc
0x18000681e  mov     [rsp+138h+cchDest], r9d; cchDest
0x180006823  mov     [rsp+138h+lpDestStr], r13; lpDestStr
0x180006828  mov     r8, r13; lpSrcStr
0x18000682b  mov     edx, 100h; dwMapFlags
0x180006830  mov     ecx, 400h; Locale
0x180006835  call    cs:__imp_LCMapStringW
0x18000683b  mov     [rsp+138h+var_A0], r13
0x180006843  mov     r15d, 1
0x180006849  mov     [rsp+138h+var_D8], r15d
0x18000684e  mov     [rsp+138h+var_F8], r12d
0x180006853  or      r12d, 80000001h
0x18000685a  mov     [rsp+138h+var_F8], r12d
0x18000685f  and     r12d, 0FFFFFFFDh
0x180006863  mov     [rsp+138h+var_F8], r12d
0x180006868  lea     r9, [rsp+138h+arg_18]
0x180006870  mov     r8d, r12d
0x180006873  lea     rdx, [rsp+138h+var_F0]
0x180006878  mov     rcx, r13
0x18000687b  call    _ComputeHashValue
0x180006880  test    eax, eax
0x180006882  jz      loc_180006A6B
0x180006888  mov     r8, [rsp+138h+arg_0]
0x180006890  mov     rdx, [r8]
0x180006893  mov     r12d, dword ptr [rsp+138h+arg_18]
0x18000689b  movsxd  rcx, dword ptr [rdx+r12*4]
  ... truncated ...
```
