# I_ReaderListBuildContainerList

- ea: `0x18001f090`
- end: `0x18001f53f`
- name: `I_ReaderListBuildContainerList`
- size: `1199`
- prototype: `__int64 __fastcall(__int64 *, const void **)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18001fdfc`

## callees

- `0x180004600`
- `0x18000a980`
- `0x18000b010`
- `0x180016090`
- `0x180018b58`
- `0x180018bb4`
- `0x18001f090`
- `0x180021220`
- `0x180024380`
- `0x1800243f8`
- `0x180026010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001f0f8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001f35c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001f410`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001f0f8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001f35c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001f410`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f443`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f51a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f443`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f51a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f195`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f21b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f4cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f195`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f21b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f4cb`
- `ADVAPI32!CryptAcquireContextW` at `0x18001f18a`
- `ADVAPI32!CryptAcquireContextW` at `0x18001f18a`
- `ADVAPI32!CryptGetProvParam` at `0x18001f210`
- `ADVAPI32!CryptGetProvParam` at `0x18001f3de`
- `ADVAPI32!CryptGetProvParam` at `0x18001f210`
- `ADVAPI32!CryptGetProvParam` at `0x18001f3de`
- `ADVAPI32!CryptReleaseContext` at `0x18001f503`
- `ADVAPI32!CryptReleaseContext` at `0x18001f503`

## pseudocode

```c
__int64 __fastcall I_ReaderListBuildContainerList(__int64 *a1, const void **a2)
{
  __int64 v3; // rcx
  __int64 v4; // rax
  size_t v6; // rdi
  DWORD LastError; // esi
  wchar_t *v8; // rax
  __int64 v9; // rcx
  WCHAR *v10; // r14
  __int64 v11; // rcx
  STRSAFE_LPSTR v12; // rcx
  int v13; // edx
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rcx
  unsigned __int64 v17; // rbx
  DWORD *p_pdwDataLen; // r14
  unsigned __int64 v19; // rcx
  __int64 v20; // rcx
  unsigned __int64 v21; // rcx
  void *v22; // rsp
  void *v23; // rsp
  DWORD *v24; // rax
  DWORD v25; // r12d
  const void *v26; // rax
  __int64 v27; // rcx
  STRSAFE_LPSTR v28; // rcx
  __int64 v29; // rdx
  DWORD dwFlags; // r13d
  size_t i; // r15
  BOOL ProvParam; // eax
  size_t v33; // rdx
  _BYTE *v34; // rax
  __int64 v35; // rcx
  _BYTE *v36; // rbx
  void **v37; // r13
  void *v38; // r8
  HANDLE v39; // rcx
  size_t v40; // rbx
  DWORD v41; // eax
  __int64 v43; // [rsp+0h] [rbp-30h] BYREF
  DWORD pdwDataLen; // [rsp+30h] [rbp+0h] BYREF
  DWORD v45; // [rsp+34h] [rbp+4h] BYREF
  WCHAR *v46; // [rsp+38h] [rbp+8h] BYREF
  HCRYPTPROV phProv; // [rsp+40h] [rbp+10h] BYREF
  size_t pcchLength; // [rsp+48h] [rbp+18h] BYREF
  const void **v49; // [rsp+50h] [rbp+20h]

  v49 = a2;
  phProv = 0;
  v3 = *a1;
  v4 = -1;
  pdwDataLen = 0;
  v45 = 0;
  pcchLength = 0;
  do
    ++v4;
  while ( *(_WORD *)(v3 + 2 * v4) );
  v6 = v4 + 6;
  LastError = 8;
  v8 = (wchar_t *)HeapAlloc(hHeap, 8u, 2 * (v4 + 6));
  v46 = v8;
  v10 = v8;
  if ( !v8 )
  {
    WppTraceIndent(v9, 2);
    if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[28] & 1) != 0
      && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
    }
    goto LABEL_60;
  }
  StringCchPrintfW(v8, v6, L"\\\\.\\%s\\", *a1);
  if ( !CryptAcquireContextW(&phProv, v10, (LPCWSTR)a1[10], *((_DWORD *)a1 + 30), 0xF0000000) )
  {
    LastError = GetLastError();
    WppTraceIndent(v11, 2);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control[28] & 1) == 0
      || (unsigned __int8)WPP_GLOBAL_Control[25] < 2u )
    {
      goto LABEL_60;
    }
    v13 = 87;
    goto LABEL_13;
  }
  if ( !CryptGetProvParam(phProv, 2u, 0, &pdwDataLen, 1u) )
  {
    LastError = GetLastError();
    WppTraceIndent(v16, 2);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      || (WPP_GLOBAL_Control[28] & 1) == 0
      || (unsigned __int8)WPP_GLOBAL_Control[25] < 2u )
    {
      goto LABEL_60;
    }
    v13 = 88;
LABEL_13:
    WPP_SF_sD(
      *((_QWORD *)v12 + 2),
      v13,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      LastError);
    goto LABEL_60;
  }
  v17 = pdwDataLen;
  p_pdwDataLen = 0;
  if ( !pdwDataLen )
    goto LABEL_27;
  if ( pdwDataLen > (unsigned __int64)g_ulMaxStackAllocSize )
    goto LABEL_27;
  v19 = pdwDataLen + g_ulAdditionalProbeSize + 8;
  if ( v19 < pdwDataLen || !(unsigned int)VerifyStackAvailable(v19, v14, v15) )
    goto LABEL_27;
  v20 = v17 + 23;
  if ( v17 + 23 <= v17 + 8 )
    v20 = 0xFFFFFFFFFFFFFF0LL;
  v21 = v20 & 0xFFFFFFFFFFFFFFF0uLL;
  v22 = alloca(v21);
  v23 = alloca(v21);
  p_pdwDataLen = &pdwDataLen;
  if ( &v43 == (__int64 *)-48LL || (pdwDataLen = 1801679955, (p_pdwDataLen = (DWORD *)&v46) == 0) )
  {
LABEL_27:
    v21 = v17 + 8;
    if ( v17 + 8 >= v17 )
    {
      v24 = (DWORD *)((__int64 (*)(void))g_pfnAllocate)();
      p_pdwDataLen = v24;
      if ( v24 )
      {
        *v24 = 1885431112;
        p_pdwDataLen = v24 + 2;
      }
    }
  }
  if ( !p_pdwDataLen )
  {
    WppTraceIndent(v21, 2);
    if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[28] & 1) != 0
      && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
    }
    goto LABEL_59;
  }
  v25 = 2 * pdwDataLen + 3;
  v26 = HeapAlloc(hHeap, 8u, v25);
  *a2 = v26;
  if ( !v26 )
  {
    WppTraceIndent(v27, 2);
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[28] & 1) != 0
      && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
    {
      v29 = 90;
LABEL_40:
      WPP_SF_s(*((_QWORD *)v28 + 2), v29, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
    }
    goto LABEL_57;
  }
  dwFlags = 1;
  for ( i = 0; ; i += v40 )
  {
    v45 = pdwDataLen;
    ProvParam = CryptGetProvParam(phProv, 2u, (BYTE *)p_pdwDataLen, &v45, dwFlags);
    dwFlags = 0;
    if ( !ProvParam )
    {
      v41 = GetLastError();
      if ( v41 == 259 )
        v41 = 0;
      LastError = v41;
      goto LABEL_57;
    }
    v33 = v45;
    if ( i + v45 + 1LL > v25 )
      break;
LABEL_46:
    if ( v33 > 0x7FFFFFFF || StringLengthWorkerA((STRSAFE_PCNZCH)p_pdwDataLen, v33, &pcchLength) < 0 )
    {
      LastError = 14;
      goto LABEL_57;
    }
    v40 = ++pcchLength;
    memcpy_0((char *)*v49 + i, p_pdwDataLen, pcchLength);
  }
  v25 *= 2;
  v34 = HeapAlloc(hHeap, 8u, v25);
  v36 = v34;
  if ( v34 )
  {
    v37 = (void **)v49;
    memcpy_0(v34, *v49, i);
    v38 = *v37;
    v39 = hHeap;
    v36[i] = 0;
    HeapFree(v39, 0, v38);
    v33 = v45;
    *v37 = v36;
    dwFlags = 0;
    goto LABEL_46;
  }
  WppTraceIndent(v35, 2);
  v28 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 1) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
  {
    v29 = 91;
    goto LABEL_40;
  }
LABEL_57:
  if ( *(p_pdwDataLen - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
LABEL_59:
  v10 = v46;
LABEL_60:
  if ( phProv )
    CryptReleaseContext(phProv, 0);
  if ( v10 )
    HeapFree(hHeap, 0, v10);
  return LastError;
}

```

## disassembly

```asm
0x18001f090  push    rbp
0x18001f092  push    rbx
0x18001f093  push    rsi
0x18001f094  push    rdi
0x18001f095  push    r12
0x18001f097  push    r13
0x18001f099  push    r14
0x18001f09b  push    r15
0x18001f09d  sub     rsp, 78h
0x18001f0a1  lea     rbp, [rsp+30h]
0x18001f0a6  mov     rax, cs:__security_cookie
0x18001f0ad  xor     rax, rbp
0x18001f0b0  mov     [rbp+80h+var_50], rax
0x18001f0b4  xor     r13d, r13d
0x18001f0b7  mov     [rbp+80h+var_60], rdx
0x18001f0bb  mov     rbx, rcx
0x18001f0be  mov     [rbp+80h+phProv], r13
0x18001f0c2  mov     rcx, [rcx]
0x18001f0c5  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001f0c9  mov     [rbp+80h+pdwDataLen], r13d
0x18001f0cd  mov     r15, rdx
0x18001f0d0  mov     [rbp+80h+var_7C], r13d
0x18001f0d4  mov     [rbp+80h+pcchLength], r13
0x18001f0d8  inc     rax
0x18001f0db  cmp     [rcx+rax*2], r13w
0x18001f0e0  jnz     short loc_18001F0D8
0x18001f0e2  mov     rcx, cs:hHeap; hHeap
0x18001f0e9  lea     rdi, [rax+6]
0x18001f0ed  mov     esi, 8
0x18001f0f2  lea     r8, [rdi+rdi]; dwBytes
0x18001f0f6  mov     edx, esi; dwFlags
0x18001f0f8  call    cs:__imp_HeapAlloc
0x18001f0fe  mov     [rbp+80h+var_78], rax
0x18001f102  mov     r14, rax
0x18001f105  test    rax, rax
0x18001f108  jnz     short loc_18001F15E
0x18001f10a  lea     edi, [rsi-6]
0x18001f10d  mov     edx, edi
0x18001f10f  call    WppTraceIndent
0x18001f114  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f11b  lea     rax, WPP_GLOBAL_Control
0x18001f122  cmp     rcx, rax
0x18001f125  jz      loc_18001F4F8
0x18001f12b  test    byte ptr [rcx+1Ch], 1
0x18001f12f  jz      loc_18001F4F8
0x18001f135  cmp     [rcx+19h], dil
0x18001f139  jb      loc_18001F4F8
0x18001f13f  mov     r9, cs:WPP_pszIndent
0x18001f146  lea     edx, [rsi+4Eh]
0x18001f149  mov     rcx, [rcx+10h]
0x18001f14d  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001f154  call    WPP_SF_s
0x18001f159  jmp     loc_18001F4F8
0x18001f15e  mov     r9, [rbx]
0x18001f161  lea     r8, aS_0; "\\\\.\\%s\\"
0x18001f168  mov     rdx, rdi; cchDest
0x18001f16b  mov     rcx, r14; pszDest
0x18001f16e  call    StringCchPrintfW
0x18001f173  mov     r9d, [rbx+78h]; dwProvType
0x18001f177  lea     rcx, [rbp+80h+phProv]; phProv
0x18001f17b  mov     r8, [rbx+50h]; szProvider
0x18001f17f  mov     rdx, r14; szContainer
0x18001f182  mov     [rsp+0B0h+dwFlags], 0F0000000h; dwFlags
0x18001f18a  call    cs:__imp_CryptAcquireContextW
0x18001f190  cmp     eax, 1
0x18001f193  jz      short loc_18001F1F7
0x18001f195  call    cs:__imp_GetLastError
0x18001f19b  mov     edi, 2
0x18001f1a0  mov     esi, eax
0x18001f1a2  mov     edx, edi
0x18001f1a4  call    WppTraceIndent
0x18001f1a9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f1b0  lea     rax, WPP_GLOBAL_Control
0x18001f1b7  cmp     rcx, rax
0x18001f1ba  jz      loc_18001F4F8
0x18001f1c0  test    byte ptr [rcx+1Ch], 1
0x18001f1c4  jz      loc_18001F4F8
0x18001f1ca  cmp     [rcx+19h], dil
0x18001f1ce  jb      loc_18001F4F8
0x18001f1d4  lea     edx, [rdi+55h]
0x18001f1d7  mov     r9, cs:WPP_pszIndent
0x18001f1de  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001f1e5  mov     rcx, [rcx+10h]
0x18001f1e9  mov     [rsp+0B0h+dwFlags], esi
0x18001f1ed  call    WPP_SF_sD
0x18001f1f2  jmp     loc_18001F4F8
0x18001f1f7  mov     rcx, [rbp+80h+phProv]; hProv
0x18001f1fb  lea     r9, [rbp+80h+pdwDataLen]; pdwDataLen
0x18001f1ff  xor     r8d, r8d; pbData
0x18001f202  mov     [rsp+0B0h+dwFlags], 1; dwFlags
0x18001f20a  lea     edi, [r8+2]
0x18001f20e  mov     edx, edi; dwParam
0x18001f210  call    cs:__imp_CryptGetProvParam
0x18001f216  cmp     eax, 1
0x18001f219  jz      short loc_18001F25D
0x18001f21b  call    cs:__imp_GetLastError
0x18001f221  mov     edx, edi
0x18001f223  mov     esi, eax
0x18001f225  call    WppTraceIndent
0x18001f22a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f231  lea     rax, WPP_GLOBAL_Control
0x18001f238  cmp     rcx, rax
0x18001f23b  jz      loc_18001F4F8
0x18001f241  test    byte ptr [rcx+1Ch], 1
0x18001f245  jz      loc_18001F4F8
0x18001f24b  cmp     [rcx+19h], dil
0x18001f24f  jb      loc_18001F4F8
0x18001f255  lea     edx, [rdi+56h]
0x18001f258  jmp     loc_18001F1D7
0x18001f25d  mov     ebx, [rbp+80h+pdwDataLen]
0x18001f260  mov     r14, r13
0x18001f263  test    rbx, rbx
0x18001f266  jz      short loc_18001F2C8
0x18001f268  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18001f26f  ja      short loc_18001F2C8
0x18001f271  mov     rcx, cs:g_ulAdditionalProbeSize
0x18001f278  add     rcx, rsi
0x18001f27b  add     rcx, rbx
0x18001f27e  cmp     rcx, rbx
0x18001f281  jb      short loc_18001F2C8
0x18001f283  call    VerifyStackAvailable
0x18001f288  test    eax, eax
0x18001f28a  jz      short loc_18001F2C8
0x18001f28c  lea     rax, [rbx+8]
0x18001f290  lea     rcx, [rax+0Fh]
0x18001f294  cmp     rcx, rax
0x18001f297  ja      short loc_18001F2A3
0x18001f299  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18001f2a3  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18001f2a7  mov     rax, rcx
0x18001f2aa  call    _alloca_probe
0x18001f2af  sub     rsp, rcx
0x18001f2b2  lea     r14, [rsp+0B0h+pdwDataLen]
0x18001f2b7  test    r14, r14
0x18001f2ba  jz      short loc_18001F2C8
0x18001f2bc  mov     dword ptr [r14], 6B637453h
0x18001f2c3  add     r14, rsi
0x18001f2c6  jnz     short loc_18001F2EE
0x18001f2c8  lea     rcx, [rbx+8]
0x18001f2cc  cmp     rcx, rbx
0x18001f2cf  jb      short loc_18001F2EE
0x18001f2d1  mov     rax, cs:g_pfnAllocate
0x18001f2d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f2dd  mov     r14, rax
0x18001f2e0  test    rax, rax
0x18001f2e3  jz      short loc_18001F2EE
0x18001f2e5  mov     dword ptr [rax], 70616548h
0x18001f2eb  add     r14, rsi
0x18001f2ee  test    r14, r14
0x18001f2f1  jnz     short loc_18001F345
0x18001f2f3  mov     edx, edi
0x18001f2f5  call    WppTraceIndent
0x18001f2fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f301  lea     rax, WPP_GLOBAL_Control
0x18001f308  cmp     rcx, rax
0x18001f30b  jz      loc_18001F4F4
0x18001f311  test    byte ptr [rcx+1Ch], 1
0x18001f315  jz      loc_18001F4F4
0x18001f31b  cmp     [rcx+19h], dil
0x18001f31f  jb      loc_18001F4F4
0x18001f325  mov     r9, cs:WPP_pszIndent
0x18001f32c  lea     edx, [r14+59h]
0x18001f330  mov     rcx, [rcx+10h]
0x18001f334  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001f33b  call    WPP_SF_s
0x18001f340  jmp     loc_18001F4F4
0x18001f345  mov     eax, [rbp+80h+pdwDataLen]
0x18001f348  mov     edx, esi; dwFlags
0x18001f34a  mov     rcx, cs:hHeap; hHeap
0x18001f351  lea     r12d, ds:3[rax*2]
0x18001f359  mov     r8d, r12d; dwBytes
0x18001f35c  call    cs:__imp_HeapAlloc
0x18001f362  mov     [r15], rax
0x18001f365  test    rax, rax
0x18001f368  jnz     short loc_18001F3BD
0x18001f36a  mov     edx, edi
0x18001f36c  call    WppTraceIndent
0x18001f371  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f378  lea     rax, WPP_GLOBAL_Control
0x18001f37f  cmp     rcx, rax
0x18001f382  jz      loc_18001F4DC
0x18001f388  test    byte ptr [rcx+1Ch], 1
0x18001f38c  jz      loc_18001F4DC
0x18001f392  cmp     [rcx+19h], dil
0x18001f396  jb      loc_18001F4DC
0x18001f39c  mov     edx, 5Ah ; 'Z'
0x18001f3a1  mov     r9, cs:WPP_pszIndent
0x18001f3a8  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001f3af  mov     rcx, [rcx+10h]
0x18001f3b3  call    WPP_SF_s
0x18001f3b8  jmp     loc_18001F4DC
0x18001f3bd  mov     r13d, 1
0x18001f3c3  xor     r15d, r15d
0x18001f3c6  mov     eax, [rbp+80h+pdwDataLen]
0x18001f3c9  lea     r9, [rbp+80h+var_7C]; pdwDataLen
0x18001f3cd  mov     rcx, [rbp+80h+phProv]; hProv
0x18001f3d1  mov     r8, r14; pbData
0x18001f3d4  mov     edx, edi; dwParam
0x18001f3d6  mov     [rbp+80h+var_7C], eax
0x18001f3d9  mov     [rsp+0B0h+dwFlags], r13d; dwFlags
0x18001f3de  call    cs:__imp_CryptGetProvParam
0x18001f3e4  xor     r13d, r13d
0x18001f3e7  test    eax, eax
0x18001f3e9  jz      loc_18001F4CB
0x18001f3ef  mov     edx, [rbp+80h+var_7C]
0x18001f3f2  mov     eax, r12d
0x18001f3f5  lea     rcx, [rdx+1]
0x18001f3f9  add     rcx, r15
0x18001f3fc  cmp     rcx, rax
0x18001f3ff  jbe     short loc_18001F453
0x18001f401  mov     rcx, cs:hHeap; hHeap
0x18001f408  add     r12d, r12d
0x18001f40b  mov     r8d, r12d; dwBytes
0x18001f40e  mov     edx, esi; dwFlags
0x18001f410  call    cs:__imp_HeapAlloc
0x18001f416  mov     rbx, rax
0x18001f419  test    rax, rax
0x18001f41c  jz      short loc_18001F494
0x18001f41e  mov     r13, [rbp+80h+var_60]
0x18001f422  mov     r8, r15; Size
0x18001f425  mov     rcx, rax; void *
0x18001f428  mov     rdx, [r13+0]; Src
0x18001f42c  call    memcpy_0
0x18001f431  mov     r8, [r13+0]; lpMem
0x18001f435  xor     edx, edx; dwFlags
0x18001f437  mov     rcx, cs:hHeap; hHeap
0x18001f43e  mov     byte ptr [rbx+r15], 0
0x18001f443  call    cs:__imp_HeapFree
0x18001f449  mov     edx, [rbp+80h+var_7C]; cchMax
0x18001f44c  mov     [r13+0], rbx
0x18001f450  xor     r13d, r13d
0x18001f453  cmp     rdx, 7FFFFFFFh
0x18001f45a  ja      short loc_18001F4C4
0x18001f45c  lea     r8, [rbp+80h+pcchLength]; pcchLength
0x18001f460  mov     rcx, r14; psz
0x18001f463  call    StringLengthWorkerA
0x18001f468  test    eax, eax
0x18001f46a  js      short loc_18001F4C4
0x18001f46c  mov     rax, [rbp+80h+var_60]
0x18001f470  mov     rdx, r14; Src
0x18001f473  mov     rbx, [rbp+80h+pcchLength]
0x18001f477  inc     rbx
0x18001f47a  mov     r8, rbx; Size
0x18001f47d  mov     [rbp+80h+pcchLength], rbx
0x18001f481  mov     rcx, [rax]
0x18001f484  add     rcx, r15; void *
0x18001f487  call    memcpy_0
0x18001f48c  add     r15, rbx
0x18001f48f  jmp     loc_18001F3C6
0x18001f494  mov     edx, edi
0x18001f496  call    WppTraceIndent
0x18001f49b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f4a2  lea     rax, WPP_GLOBAL_Control
0x18001f4a9  cmp     rcx, rax
0x18001f4ac  jz      short loc_18001F4DC
0x18001f4ae  test    byte ptr [rcx+1Ch], 1
0x18001f4b2  jz      short loc_18001F4DC
0x18001f4b4  cmp     [rcx+19h], dil
0x18001f4b8  jb      short loc_18001F4DC
0x18001f4ba  mov     edx, 5Bh ; '['
0x18001f4bf  jmp     loc_18001F3A1
0x18001f4c4  mov     esi, 0Eh
0x18001f4c9  jmp     short loc_18001F4DC
0x18001f4cb  call    cs:__imp_GetLastError
0x18001f4d1  cmp     eax, 103h
0x18001f4d6  cmovz   eax, r13d
0x18001f4da  mov     esi, eax
0x18001f4dc  lea     rcx, [r14-8]
0x18001f4e0  cmp     dword ptr [rcx], 70616548h
0x18001f4e6  jnz     short loc_18001F4F4
0x18001f4e8  mov     rax, cs:g_pfnFree
0x18001f4ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f4f4  mov     r14, [rbp+80h+var_78]
0x18001f4f8  mov     rcx, [rbp+80h+phProv]; hProv
0x18001f4fc  test    rcx, rcx
0x18001f4ff  jz      short loc_18001F509
0x18001f501  xor     edx, edx; dwFlags
0x18001f503  call    cs:__imp_CryptReleaseContext
0x18001f509  test    r14, r14
0x18001f50c  jz      short loc_18001F520
0x18001f50e  mov     rcx, cs:hHeap; hHeap
0x18001f515  mov     r8, r14; lpMem
0x18001f518  xor     edx, edx; dwFlags
0x18001f51a  call    cs:__imp_HeapFree
0x18001f520  mov     eax, esi
0x18001f522  mov     rcx, [rbp+80h+var_50]
0x18001f526  xor     rcx, rbp; StackCookie
0x18001f529  call    __security_check_cookie
0x18001f52e  lea     rsp, [rbp+48h]
0x18001f532  pop     r15
0x18001f534  pop     r14
0x18001f536  pop     r13
0x18001f538  pop     r12
0x18001f53a  pop     rdi
0x18001f53b  pop     rsi
0x18001f53c  pop     rbx
0x18001f53d  pop     rbp
0x18001f53e  retn
```
