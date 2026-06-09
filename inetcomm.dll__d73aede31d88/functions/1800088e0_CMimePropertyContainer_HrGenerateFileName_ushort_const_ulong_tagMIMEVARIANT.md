# CMimePropertyContainer::_HrGenerateFileName(ushort const *,ulong,tagMIMEVARIANT *)

- ea: `0x1800088e0`
- end: `0x180009103`
- name: `?_HrGenerateFileName@CMimePropertyContainer@@AEAAJPEBGKPEAUtagMIMEVARIANT@@@Z`
- size: `2083`
- prototype: `__int64 __fastcall(CMimePropertyContainer *this, const unsigned __int16 *, int, struct tagMIMEVARIANT *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180007a50`
- `0x180007ad0`

## callees

- `0x180008370`
- `0x1800088e0`
- `0x18000910c`
- `0x180019274`
- `0x18001bd8c`
- `0x1800579ac`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `MSOERT2!PszToUnicode` at `0x180008e91`
- `MSOERT2!PszToUnicode` at `0x180008e91`
- `MSOERT2!PszDupW` at `0x180009006`
- `MSOERT2!PszDupW` at `0x180009006`
- `MSOERT2!PszAllocA` at `0x180008f0d`
- `MSOERT2!PszAllocA` at `0x180008f0d`
- `MSOERT2!CleanupFileNameInPlaceW` at `0x180009020`
- `MSOERT2!CleanupFileNameInPlaceW` at `0x180009020`
- `MSOERT2!PszAllocW` at `0x180008a54`
- `MSOERT2!PszAllocW` at `0x180008a54`
- `SHLWAPI!StrCmpNIA` at `0x180008c0c`
- `SHLWAPI!StrCmpNIA` at `0x180008c0c`
- `SHLWAPI!__imp_StrCmpICA` at `0x180008bee`
- `SHLWAPI!__imp_StrCmpICA` at `0x180008bee`
- `ADVAPI32!RegOpenKeyExA` at `0x180008e5d`
- `ADVAPI32!RegOpenKeyExA` at `0x180008ece`
- `ADVAPI32!RegOpenKeyExA` at `0x180008e5d`
- `ADVAPI32!RegOpenKeyExA` at `0x180008ece`
- `ADVAPI32!RegQueryValueExA` at `0x180008ef9`
- `ADVAPI32!RegQueryValueExA` at `0x180008f49`
- `ADVAPI32!RegQueryValueExA` at `0x180008ef9`
- `ADVAPI32!RegQueryValueExA` at `0x180008f49`
- `ADVAPI32!RegCloseKey` at `0x180008e71`
- `ADVAPI32!RegCloseKey` at `0x180008eab`
- `ADVAPI32!RegCloseKey` at `0x180008e71`
- `ADVAPI32!RegCloseKey` at `0x180008eab`
- `KERNEL32!lstrcmpiA` at `0x18000895e`
- `KERNEL32!lstrcmpiA` at `0x18000895e`
- `KERNEL32!LeaveCriticalSection` at `0x1800089e6`
- `KERNEL32!LeaveCriticalSection` at `0x180008ba9`
- `KERNEL32!LeaveCriticalSection` at `0x180008cce`
- `KERNEL32!LeaveCriticalSection` at `0x180008d2e`
- `KERNEL32!LeaveCriticalSection` at `0x1800089e6`
- `KERNEL32!LeaveCriticalSection` at `0x180008ba9`
- `KERNEL32!LeaveCriticalSection` at `0x180008cce`
- `KERNEL32!LeaveCriticalSection` at `0x180008d2e`
- `KERNEL32!EnterCriticalSection` at `0x1800089ca`
- `KERNEL32!EnterCriticalSection` at `0x180008aed`
- `KERNEL32!EnterCriticalSection` at `0x180008c83`
- `KERNEL32!EnterCriticalSection` at `0x180008ce3`
- `KERNEL32!EnterCriticalSection` at `0x1800089ca`
- `KERNEL32!EnterCriticalSection` at `0x180008aed`
- `KERNEL32!EnterCriticalSection` at `0x180008c83`
- `KERNEL32!EnterCriticalSection` at `0x180008ce3`

## string_xrefs

- `0x180008ee7`: `Extension`
- `0x180008f2f`: `Extension`

## pseudocode

```c
__int64 __fastcall CMimePropertyContainer::_HrGenerateFileName(
        CMimePropertyContainer *this,
        const unsigned __int16 *a2,
        int a3,
        struct tagMIMEVARIANT *a4)
{
  __int64 v4; // rax
  const unsigned __int16 *v5; // r15
  const CHAR *v7; // rsi
  int v8; // r12d
  bool v9; // zf
  const wchar_t *v10; // r14
  unsigned __int16 *v11; // rdi
  int v12; // r13d
  __int64 v13; // rbx
  __int64 v14; // r12
  const wchar_t *v15; // rsi
  unsigned int v16; // edi
  unsigned __int16 *v17; // r14
  __int64 v18; // rax
  __int64 v19; // rcx
  unsigned int v20; // r15d
  unsigned __int16 *v21; // rax
  CMimePropertyContainer *v22; // r14
  __int64 v23; // rsi
  _QWORD *k; // rdx
  __int64 v25; // rcx
  struct tagMIMEVARIANT *v26; // r15
  __int64 v27; // rdx
  __int64 i; // rdx
  int v30; // edi
  __int64 j; // rdx
  int v32; // edi
  int PropertyValue; // eax
  __int64 v34; // rax
  BYTE *v35; // rax
  unsigned int v36; // r8d
  unsigned int v37; // r8d
  int v38; // eax
  __int64 v39; // rax
  int v40; // eax
  unsigned __int16 *v41; // rdx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v44; // [rsp+40h] [rbp-C0h]
  __int128 v45; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v46; // [rsp+58h] [rbp-A8h]
  int v47; // [rsp+68h] [rbp-98h]
  HKEY phkResult; // [rsp+70h] [rbp-90h] BYREF
  BYTE *v49; // [rsp+78h] [rbp-88h]
  __int64 v50; // [rsp+80h] [rbp-80h]
  CMimePropertyContainer *v51; // [rsp+88h] [rbp-78h]
  struct tagMIMEVARIANT *v52; // [rsp+90h] [rbp-70h]
  unsigned __int16 v53[8]; // [rsp+98h] [rbp-68h] BYREF
  __int128 v54; // [rsp+A8h] [rbp-58h]
  unsigned __int16 v55[4]; // [rsp+B8h] [rbp-48h] BYREF
  void *v56; // [rsp+C0h] [rbp-40h]
  __int64 v57; // [rsp+C8h] [rbp-38h]
  int v58; // [rsp+D0h] [rbp-30h]
  int v59; // [rsp+D4h] [rbp-2Ch]
  int v60; // [rsp+D8h] [rbp-28h]
  int v61; // [rsp+DCh] [rbp-24h]

  v4 = *((_QWORD *)this + 24);
  v52 = a4;
  v47 = a3;
  v5 = a2;
  v51 = this;
  v50 = 0;
  v45 = 0;
  v46 = 0;
  if ( !v4 || *(_DWORD *)v4 != 1 || v4 == -8 || (v7 = *(const CHAR **)(v4 + 8)) == 0 || v7[*(_QWORD *)(v4 + 16)] )
    v7 = "text/plain";
  v8 = -2146644475;
  if ( !a2 )
  {
    LODWORD(v45) = 2;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1392));
    if ( (unsigned int)(dword_1800F153C - 2) > 0x4C )
    {
      for ( i = *((_QWORD *)this + (unsigned __int16)word_1800F1548 + 85); i; i = *(_QWORD *)(i + 264) )
      {
        if ( *(_DWORD *)(*(_QWORD *)(i + 248) + 12LL) == dword_1800F153C )
          goto LABEL_98;
      }
    }
    else
    {
      i = *((_QWORD *)this + (unsigned int)dword_1800F153C + 6);
      if ( i )
      {
LABEL_98:
        v36 = 0;
        if ( (byte_1800F1540 & 4) != 0 )
          v36 = 32;
        PropertyValue = CMimePropertyContainer::_HrGetPropertyValue(
                          this,
                          (struct tagPROPERTY *)i,
                          v36,
                          (struct tagMIMEVARIANT *)&v45);
        goto LABEL_70;
      }
    }
    v30 = -2146644475;
    if ( !off_1800F1560 || (*off_1800F1560 & 8) == 0 || !*(_QWORD *)(off_1800F1560 + 8LL) )
    {
LABEL_57:
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1392));
      if ( v30 >= 0 )
      {
        v50 = *((_QWORD *)&v45 + 1);
        v5 = (const unsigned __int16 *)*((_QWORD *)&v45 + 1);
        if ( *((_QWORD *)&v45 + 1) )
          goto LABEL_4;
      }
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1392));
      if ( (unsigned int)(dword_1800F0834 - 2) > 0x4C )
      {
        for ( j = *((_QWORD *)this + (unsigned __int16)word_1800F0840 + 85); j; j = *(_QWORD *)(j + 264) )
        {
          if ( *(_DWORD *)(*(_QWORD *)(j + 248) + 12LL) == dword_1800F0834 )
            goto LABEL_101;
        }
      }
      else
      {
        j = *((_QWORD *)this + (unsigned int)dword_1800F0834 + 6);
        if ( j )
        {
LABEL_101:
          v37 = 0;
          if ( (byte_1800F0838 & 4) != 0 )
            v37 = 32;
          v38 = CMimePropertyContainer::_HrGetPropertyValue(
                  this,
                  (struct tagPROPERTY *)j,
                  v37,
                  (struct tagMIMEVARIANT *)&v45);
          goto LABEL_105;
        }
      }
      v32 = -2146644475;
      if ( !qword_1800F0858 || (*(_BYTE *)qword_1800F0858 & 8) == 0 || !*(_QWORD *)(qword_1800F0858 + 8) )
      {
LABEL_63:
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1392));
        if ( v32 >= 0 )
        {
          v50 = *((_QWORD *)&v45 + 1);
          v5 = (const unsigned __int16 *)*((_QWORD *)&v45 + 1);
        }
        goto LABEL_4;
      }
      v38 = CMimePropertyContainer::_HrCallSymbolTrigger(
              this,
              (struct tagPROPSYMBOL *)&rSYM_HDR_CNTDESC,
              8u,
              0,
              (struct tagMIMEVARIANT *)&v45);
LABEL_105:
      v32 = v38;
      goto LABEL_63;
    }
    PropertyValue = CMimePropertyContainer::_HrCallSymbolTrigger(
                      this,
                      (struct tagPROPSYMBOL *)&rSYM_HDR_SUBJECT,
                      8u,
                      0,
                      (struct tagMIMEVARIANT *)&v45);
LABEL_70:
    v30 = PropertyValue;
    goto LABEL_57;
  }
LABEL_4:
  if ( lstrcmpiA(v7, "message/rfc822") )
  {
    if ( StrCmpICA(v7, "message/disposition-notification") )
    {
      v10 = L".txt";
      if ( StrCmpNIA(v7, "text", 4) )
        v10 = 0;
    }
    else
    {
      v10 = L".txt";
    }
  }
  else
  {
    v9 = (*((_BYTE *)this + 36) & 0x10) == 0;
    v10 = L".nws";
    v7 = 0;
    if ( v9 )
      v10 = L".eml";
  }
  v49 = 0;
  v11 = 0;
  v44 = 0;
  v12 = -2147024882;
  v13 = -1;
  if ( !v7 )
    goto LABEL_8;
  phkResult = 0;
  hKey = 0;
  cbData = 0;
  if ( !RegOpenKeyExA(HKEY_CLASSES_ROOT, "MIME\\Database\\Content Type", 0, 0x20019u, &phkResult)
    && !RegOpenKeyExA(phkResult, v7, 0, 0x20019u, &hKey)
    && !RegQueryValueExA(hKey, "Extension", 0, 0, 0, &cbData) )
  {
    v35 = (BYTE *)PszAllocA(cbData + 1);
    v49 = v35;
    if ( v35 )
    {
      ++cbData;
      v8 = 0;
      if ( RegQueryValueExA(hKey, "Extension", 0, 0, v35, &cbData) )
        v8 = -2147467259;
    }
    else
    {
      v8 = -2147024882;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v8 >= 0 )
  {
    v34 = PszToUnicode(0, v49);
    v14 = v34;
    if ( !v34 )
    {
      v17 = 0;
      goto LABEL_20;
    }
    v15 = (const wchar_t *)v34;
  }
  else
  {
LABEL_8:
    v14 = 0;
    v15 = L".dat";
    if ( v10 )
      v15 = v10;
  }
  if ( v5 )
  {
    v39 = PszDupW(v5);
    v44 = (unsigned __int16 *)v39;
    v17 = (unsigned __int16 *)v39;
    if ( !v39 )
      goto LABEL_20;
    CleanupFileNameInPlaceW(v39);
  }
  else
  {
    EnterCriticalSection(&g_csCounter);
    v16 = g_dwCounter++;
    LeaveCriticalSection(&g_csCounter);
    StringCchPrintfW(v55, 0x1Eu, L"%05d", v16);
    StringCchPrintfW(v53, 0xAu, L"ATT%s", v55);
    v17 = v53;
  }
  v18 = -1;
  do
    ++v18;
  while ( v17[v18] );
  if ( v15 )
  {
    v19 = -1;
    do
      ++v19;
    while ( v15[v19] );
  }
  else
  {
    LODWORD(v19) = 0;
  }
  v20 = v18 + v19 + 2;
  v21 = (unsigned __int16 *)PszAllocW(v20);
  v11 = v21;
  if ( v21 )
  {
    v12 = 0;
    StringCchPrintfW(v21, (int)v20, L"%s%s", v17, v15);
  }
  v17 = v44;
LABEL_20:
  if ( v49 )
    ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
  if ( v14 )
    ((void (__fastcall *)(LPMALLOC, __int64))g_pMalloc->lpVtbl->Free)(g_pMalloc, v14);
  if ( v17 )
    ((void (__fastcall *)(LPMALLOC, unsigned __int16 *))g_pMalloc->lpVtbl->Free)(g_pMalloc, v17);
  if ( v12 >= 0 )
  {
    *(_QWORD *)&v45 = 2;
    v46 = 0u;
    *((_QWORD *)&v45 + 1) = v11;
    if ( v11 )
    {
      do
        ++v13;
      while ( v11[v13] );
      *(_QWORD *)&v46 = v13;
    }
    v22 = v51;
    v23 = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v51 + 1392));
    if ( (unsigned int)(dword_1800F176C - 2) > 0x4C )
    {
      for ( k = (_QWORD *)*((_QWORD *)v22 + (unsigned __int16)word_1800F1778 + 85); k; k = (_QWORD *)k[33] )
      {
        if ( *(_DWORD *)(k[31] + 12LL) == dword_1800F176C )
          goto LABEL_111;
      }
    }
    else
    {
      k = (_QWORD *)*((_QWORD *)v22 + (unsigned int)dword_1800F176C + 6);
      if ( k )
LABEL_111:
        v23 = k[4];
    }
    v25 = (int)v45;
    if ( (unsigned int)(v45 - 1) > 3 || (v26 = v52, v27 = *(int *)v52, (unsigned int)(v27 - 1) > 3) )
    {
      v12 = -2146644430;
    }
    else
    {
      *((_BYTE *)v52 + 4) = 0;
      *(_QWORD *)v55 = (char *)v22 + 1360;
      v56 = &rSYM_ATT_GENFNAME;
      v61 = 0;
      if ( v23 )
        v57 = v23;
      else
        v57 = *((_QWORD *)v22 + 170);
      v58 = 0;
      v59 = v47;
      v60 = 0;
      if ( (v47 & 8) != 0 && (unsigned int)(v25 - 1) <= 1 )
      {
        *(_OWORD *)v53 = 0;
        v54 = 0;
        v40 = MimeVariantStripComments((struct tagMIMEVARIANT *)&v45, (struct tagMIMEVARIANT *)v53);
        v41 = (unsigned __int16 *)&v45;
        if ( v40 >= 0 )
          v41 = v53;
        v12 = ((__int64 (__fastcall *)(unsigned __int16 *, unsigned __int16 *, struct tagMIMEVARIANT *))qword_1800CEA70[5 * *(int *)v41 + *(int *)v26])(
                v55,
                v41,
                v26);
        MimeVariantFree((struct tagMIMEVARIANT *)v53);
      }
      else
      {
        v12 = ((__int64 (__fastcall *)(unsigned __int16 *, __int128 *, struct tagMIMEVARIANT *))qword_1800CEA70[5 * v25 + v27])(
                v55,
                &v45,
                v26);
      }
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v22 + 1392));
  }
  if ( v11 )
    ((void (__fastcall *)(LPMALLOC, unsigned __int16 *))g_pMalloc->lpVtbl->Free)(g_pMalloc, v11);
  if ( v50 )
    ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800088e0  push    rbp
0x1800088e2  push    rbx
0x1800088e3  push    rsi
0x1800088e4  push    rdi
0x1800088e5  push    r12
0x1800088e7  push    r13
0x1800088e9  push    r14
0x1800088eb  push    r15
0x1800088ed  lea     rbp, [rsp-8]
0x1800088f2  sub     rsp, 108h
0x1800088f9  mov     rax, cs:__security_cookie
0x180008900  xor     rax, rsp
0x180008903  mov     [rbp+40h+var_48], rax
0x180008907  mov     rax, [rcx+0C0h]
0x18000890e  xor     r13d, r13d
0x180008911  mov     [rbp+40h+var_B0], r9
0x180008915  xorps   xmm0, xmm0
0x180008918  mov     [rsp+140h+var_D8], r8d
0x18000891d  mov     r15, rdx
0x180008920  mov     [rbp+40h+var_B8], rcx
0x180008924  mov     r14, rcx
0x180008927  mov     [rbp+40h+var_C0], r13
0x18000892b  movups  [rsp+140h+var_F8], xmm0
0x180008930  movups  [rsp+140h+var_E8], xmm0
0x180008935  test    rax, rax
0x180008938  jnz     loc_180008C3F
0x18000893e  lea     rsi, STR_MIME_TEXT_PLAIN; "text/plain"
0x180008945  mov     r12d, 800CCE05h
0x18000894b  test    rdx, rdx
0x18000894e  jz      loc_180008C74
0x180008954  lea     rdx, STR_MIME_MSG_RFC822; "message/rfc822"
0x18000895b  mov     rcx, rsi; lpString1
0x18000895e  call    cs:__imp_lstrcmpiA
0x180008964  test    eax, eax
0x180008966  jnz     loc_180008BE4
0x18000896c  test    byte ptr [r14+24h], 10h
0x180008971  lea     rax, c_wszDotEml; ".eml"
0x180008978  lea     r14, c_wszDotNws; ".nws"
0x18000897f  mov     rsi, r13
0x180008982  cmovz   r14, rax
0x180008986  mov     [rsp+140h+var_C8], r13
0x18000898b  mov     rdi, r13
0x18000898e  mov     [rsp+140h+var_100], r13
0x180008993  mov     r13d, 8007000Eh
0x180008999  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1800089a0  test    rsi, rsi
0x1800089a3  jnz     loc_180008E2E
0x1800089a9  xor     r12d, r12d
0x1800089ac  lea     rsi, c_wszDotDat; ".dat"
0x1800089b3  test    r14, r14
0x1800089b6  cmovnz  rsi, r14
0x1800089ba  test    r15, r15
0x1800089bd  jnz     loc_180009003
0x1800089c3  lea     rcx, ?g_csCounter@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800089ca  call    cs:__imp_EnterCriticalSection
0x1800089d0  mov     edi, cs:?g_dwCounter@@3KA; ulong g_dwCounter
0x1800089d6  lea     rcx, ?g_csCounter@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800089dd  lea     eax, [rdi+1]
0x1800089e0  mov     cs:?g_dwCounter@@3KA, eax; ulong g_dwCounter
0x1800089e6  call    cs:__imp_LeaveCriticalSection
0x1800089ec  mov     r9d, edi
0x1800089ef  lea     r8, a05d_0; "%05d"
0x1800089f6  mov     edx, 1Eh; unsigned __int64
0x1800089fb  lea     rcx, [rbp+40h+var_88]; unsigned __int16 *
0x1800089ff  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008a04  lea     r9, [rbp+40h+var_88]
0x180008a08  mov     edx, 0Ah; unsigned __int64
0x180008a0d  lea     r8, aAttS_0; "ATT%s"
0x180008a14  lea     rcx, [rbp+40h+var_A8]; unsigned __int16 *
0x180008a18  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008a1d  lea     r14, [rbp+40h+var_A8]
0x180008a21  mov     rax, rbx
0x180008a24  inc     rax
0x180008a27  cmp     word ptr [r14+rax*2], 0
0x180008a2d  jnz     short loc_180008A24
0x180008a2f  test    rsi, rsi
0x180008a32  jz      loc_180008D61
0x180008a38  mov     rcx, rbx
0x180008a3b  nop     dword ptr [rax+rax+00h]
0x180008a40  inc     rcx
0x180008a43  cmp     word ptr [rsi+rcx*2], 0
0x180008a48  jnz     short loc_180008A40
0x180008a4a  lea     r15d, [rcx+2]
0x180008a4e  add     r15d, eax
0x180008a51  mov     ecx, r15d
0x180008a54  call    cs:__imp_PszAllocW
0x180008a5a  mov     rdi, rax
0x180008a5d  test    rax, rax
0x180008a60  jz      short loc_180008A7F
0x180008a62  xor     r13d, r13d
0x180008a65  movsxd  rdx, r15d; unsigned __int64
0x180008a68  mov     r9, r14
0x180008a6b  mov     [rsp+140h+phkResult], rsi
0x180008a70  lea     r8, aSS_4; "%s%s"
0x180008a77  mov     rcx, rax; unsigned __int16 *
0x180008a7a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008a7f  mov     r14, [rsp+140h+var_100]
0x180008a84  mov     rdx, [rsp+140h+var_C8]
0x180008a89  test    rdx, rdx
0x180008a8c  jnz     loc_18000902B
0x180008a92  test    r12, r12
0x180008a95  jnz     loc_180009043
0x180008a9b  test    r14, r14
0x180008a9e  jnz     loc_18000905E
0x180008aa4  test    r13d, r13d
0x180008aa7  js      loc_180008BAF
0x180008aad  xor     r12d, r12d
0x180008ab0  mov     qword ptr [rsp+140h+var_F8], 2
0x180008ab9  mov     qword ptr [rsp+140h+var_E8], r12
0x180008abe  mov     qword ptr [rsp+140h+var_E8+8], r12
0x180008ac3  mov     qword ptr [rsp+140h+var_F8+8], rdi
0x180008ac8  test    rdi, rdi
0x180008acb  jz      short loc_180008ADF
0x180008acd  nop     dword ptr [rax]
0x180008ad0  inc     rbx
0x180008ad3  cmp     [rdi+rbx*2], r12w
0x180008ad8  jnz     short loc_180008AD0
0x180008ada  mov     qword ptr [rsp+140h+var_E8], rbx
0x180008adf  mov     r14, [rbp+40h+var_B8]
0x180008ae3  mov     rsi, r12
0x180008ae6  lea     rcx, [r14+570h]; lpCriticalSection
0x180008aed  call    cs:__imp_EnterCriticalSection
0x180008af3  mov     ecx, cs:dword_1800F176C
0x180008af9  lea     eax, [rcx-2]
0x180008afc  cmp     eax, 4Ch ; 'L'
0x180008aff  ja      loc_180008D9B
0x180008b05  mov     rdx, [r14+rcx*8+30h]
0x180008b0a  test    rdx, rdx
0x180008b0d  jnz     loc_180009079
0x180008b13  movsxd  rcx, dword ptr [rsp+140h+var_F8]
0x180008b18  lea     eax, [rcx-1]
0x180008b1b  cmp     eax, 3
0x180008b1e  ja      loc_180008D4D
0x180008b24  mov     r15, [rbp+40h+var_B0]
0x180008b28  movsxd  rdx, dword ptr [r15]
0x180008b2b  lea     eax, [rdx-1]
0x180008b2e  cmp     eax, 3
0x180008b31  ja      loc_180008D4D
0x180008b37  mov     [r15+4], r12b
0x180008b3b  lea     rax, [r14+550h]
0x180008b42  mov     qword ptr [rbp+40h+var_88], rax
0x180008b46  lea     r8, ?rSYM_ATT_GENFNAME@@3UtagPROPSYMBOL@@A; tagPROPSYMBOL rSYM_ATT_GENFNAME
0x180008b4d  mov     [rbp+40h+var_80], r8
0x180008b51  mov     [rbp+40h+var_64], r12d
0x180008b55  test    rsi, rsi
0x180008b58  jnz     loc_180008D58
0x180008b5e  mov     rax, [rax]
0x180008b61  mov     [rbp+40h+var_78], rax
0x180008b65  mov     eax, [rsp+140h+var_D8]
0x180008b69  mov     [rbp+40h+var_70], r12d
0x180008b6d  mov     [rbp+40h+var_6C], eax
0x180008b70  mov     [rbp+40h+var_68], r12d
0x180008b74  test    al, 8
0x180008b76  jnz     loc_180009082
0x180008b7c  lea     rcx, [rcx+rcx*4]
0x180008b80  mov     r8, r15
0x180008b83  add     rcx, rdx
0x180008b86  lea     rax, qword_1800CEA70
0x180008b8d  lea     rdx, [rsp+140h+var_F8]
0x180008b92  mov     rax, [rax+rcx*8]
0x180008b96  lea     rcx, [rbp+40h+var_88]
0x180008b9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b9f  mov     r13d, eax
0x180008ba2  lea     rcx, [r14+570h]; lpCriticalSection
0x180008ba9  call    cs:__imp_LeaveCriticalSection
0x180008baf  test    rdi, rdi
0x180008bb2  jnz     short loc_180008C24
0x180008bb4  mov     rdx, [rbp+40h+var_C0]
0x180008bb8  test    rdx, rdx
0x180008bbb  jnz     loc_1800090EB
0x180008bc1  mov     eax, r13d
0x180008bc4  mov     rcx, [rbp+40h+var_48]
0x180008bc8  xor     rcx, rsp; StackCookie
0x180008bcb  call    __security_check_cookie
0x180008bd0  add     rsp, 108h
0x180008bd7  pop     r15
0x180008bd9  pop     r14
0x180008bdb  pop     r13
0x180008bdd  pop     r12
0x180008bdf  pop     rdi
0x180008be0  pop     rsi
0x180008be1  pop     rbx
0x180008be2  pop     rbp
0x180008be3  retn
0x180008be4  lea     rdx, aMessageDisposi; "message/disposition-notification"
0x180008beb  mov     rcx, rsi; pszStr1
0x180008bee  call    cs:__imp_StrCmpICA
0x180008bf4  test    eax, eax
0x180008bf6  jz      loc_180008FE7
0x180008bfc  mov     r8d, 4; nChar
0x180008c02  lea     rdx, STR_CNT_TEXT; "text"
0x180008c09  mov     rcx, rsi; psz1
0x180008c0c  call    cs:__imp_StrCmpNIA
0x180008c12  test    eax, eax
0x180008c14  lea     r14, c_wszDotTxt; ".txt"
0x180008c1b  cmovnz  r14, r13
0x180008c1f  jmp     loc_180008986
0x180008c24  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x180008c2b  mov     rdx, rdi
0x180008c2e  mov     rax, [rcx]
0x180008c31  mov     rax, [rax+28h]
0x180008c35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c3a  jmp     loc_180008BB4
0x180008c3f  cmp     dword ptr [rax], 1
0x180008c42  jnz     loc_18000893E
0x180008c48  lea     rsi, [rax+8]
0x180008c4c  test    rsi, rsi
0x180008c4f  jz      loc_18000893E
0x180008c55  mov     rsi, [rsi]
0x180008c58  test    rsi, rsi
0x180008c5b  jz      loc_18000893E
0x180008c61  mov     rax, [rax+10h]
0x180008c65  cmp     [rsi+rax], r13b
0x180008c69  jz      loc_180008945
0x180008c6f  jmp     loc_18000893E
0x180008c74  add     rcx, 570h; lpCriticalSection
0x180008c7b  mov     dword ptr [rsp+140h+var_F8], 2
0x180008c83  call    cs:__imp_EnterCriticalSection
0x180008c89  mov     ecx, cs:dword_1800F153C
0x180008c8f  mov     r9d, 20h ; ' '
0x180008c95  lea     eax, [rcx-2]
0x180008c98  cmp     eax, 4Ch ; 'L'
0x180008c9b  ja      loc_180008DCC
0x180008ca1  mov     rdx, [r14+rcx*8+30h]; struct tagPROPERTY *
0x180008ca6  test    rdx, rdx
0x180008ca9  jnz     loc_180008F7C
0x180008caf  mov     rax, cs:off_1800F1560
0x180008cb6  mov     edi, r12d
0x180008cb9  test    rax, rax
0x180008cbc  jz      short loc_180008CC7
0x180008cbe  test    byte ptr [rax], 8
0x180008cc1  jnz     loc_180008D68
0x180008cc7  lea     rcx, [r14+570h]; lpCriticalSection
0x180008cce  call    cs:__imp_LeaveCriticalSection
0x180008cd4  test    edi, edi
0x180008cd6  jns     loc_180008F62
0x180008cdc  lea     rcx, [r14+570h]; lpCriticalSection
0x180008ce3  call    cs:__imp_EnterCriticalSection
0x180008ce9  mov     ecx, cs:dword_1800F0834
0x180008cef  lea     eax, [rcx-2]
0x180008cf2  cmp     eax, 4Ch ; 'L'
0x180008cf5  ja      loc_180008DFD
0x180008cfb  mov     rdx, [r14+rcx*8+30h]; struct tagPROPERTY *
0x180008d00  test    rdx, rdx
0x180008d03  jnz     loc_180008F9C
0x180008d09  mov     rax, cs:qword_1800F0858
0x180008d10  mov     edi, r12d
0x180008d13  test    rax, rax
0x180008d16  jz      short loc_180008D27
0x180008d18  test    byte ptr [rax], 8
0x180008d1b  jz      short loc_180008D27
0x180008d1d  cmp     [rax+8], r13
0x180008d21  jnz     loc_180008FBE
0x180008d27  lea     rcx, [r14+570h]; lpCriticalSection
0x180008d2e  call    cs:__imp_LeaveCriticalSection
0x180008d34  test    edi, edi
0x180008d36  js      loc_180008954
0x180008d3c  mov     rax, qword ptr [rsp+140h+var_F8+8]
0x180008d41  mov     [rbp+40h+var_C0], rax
0x180008d45  mov     r15, rax
0x180008d48  jmp     loc_180008954
0x180008d4d  mov     r13d, 800CCE32h
0x180008d53  jmp     loc_180008BA2
0x180008d58  mov     [rbp+40h+var_78], rsi
0x180008d5c  jmp     loc_180008B65
0x180008d61  xor     ecx, ecx
0x180008d63  jmp     loc_180008A4A
0x180008d68  cmp     [rax+8], r13
0x180008d6c  jz      loc_180008CC7
0x180008d72  lea     rax, [rsp+140h+var_F8]
0x180008d77  xor     r9d, r9d; unsigned int
0x180008d7a  mov     r8d, 8; unsigned int
0x180008d80  mov     [rsp+140h+phkResult], rax; struct tagMIMEVARIANT *
0x180008d85  lea     rdx, ?rSYM_HDR_SUBJECT@@3UtagPROPSYMBOL@@A; struct tagPROPSYMBOL *
0x180008d8c  mov     rcx, r14; this
0x180008d8f  call    ?_HrCallSymbolTrigger@CMimePropertyContainer@@AEAAJPEAUtagPROPSYMBOL@@KKPEAUtagMIMEVARIANT@@@Z; CMimePropertyContainer::_HrCallSymbolTrigger(tagPROPSYMBOL *,ulong,ulong,tagMIMEVARIANT *)
0x180008d94  mov     edi, eax
0x180008d96  jmp     loc_180008CC7
0x180008d9b  movzx   eax, cs:word_1800F1778
0x180008da2  mov     rdx, [r14+rax*8+2A8h]
0x180008daa  test    rdx, rdx
0x180008dad  jz      loc_180008B13
0x180008db3  mov     rax, [rdx+0F8h]
0x180008dba  cmp     [rax+0Ch], ecx
0x180008dbd  jz      loc_180009079
0x180008dc3  mov     rdx, [rdx+108h]
0x180008dca  jmp     short loc_180008DAA
0x180008dcc  movzx   eax, cs:word_1800F1548
0x180008dd3  mov     rdx, [r14+rax*8+2A8h]
0x180008ddb  test    rdx, rdx
0x180008dde  jz      loc_180008CAF
0x180008de4  mov     rax, [rdx+0F8h]
0x180008deb  cmp     [rax+0Ch], ecx
0x180008dee  jz      loc_180008F7C
0x180008df4  mov     rdx, [rdx+108h]
0x180008dfb  jmp     short loc_180008DDB
0x180008dfd  movzx   eax, cs:word_1800F0840
0x180008e04  mov     rdx, [r14+rax*8+2A8h]
0x180008e0c  test    rdx, rdx
0x180008e0f  jz      loc_180008D09
  ... truncated ...
```
