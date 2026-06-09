# _CatDBDeleteCatalogEntriesFromDatabase(_JET_DB_STRUCT *,ushort const *,int)

- ea: `0x180008888`
- end: `0x180008a66`
- name: `?_CatDBDeleteCatalogEntriesFromDatabase@@YAHPEAU_JET_DB_STRUCT@@PEBGH@Z`
- size: `478`
- prototype: `__int64 __fastcall(struct _JET_DB_STRUCT *, wchar_t *Str, int)`
- caller_count: `2`
- callee_count: `12`
- tags: ``

## callers

- `0x180017a04`
- `0x180019314`

## callees

- `0x1800038f0`
- `0x180004094`
- `0x18000849c`
- `0x180008888`
- `0x180008b8c`
- `0x18000a59c`
- `0x18000ac08`
- `0x18000acbc`
- `0x18000be40`
- `0x18000c7e8`
- `0x18001aeb0`
- `0x18001ef4c`

## import_xrefs

- `CRYPT32!CertFreeCTLContext` at `0x180008a01`
- `CRYPT32!CertFreeCTLContext` at `0x180008a01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800089f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800089f1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000890c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008970`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008a37`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000890c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008970`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008a37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008a1f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008a2f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008a1f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008a2f`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180008a10`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180008a10`
- `ESENT!JetDelete` at `0x180008952`
- `ESENT!JetDelete` at `0x180008952`

## pseudocode

```c
__int64 __fastcall _CatDBDeleteCatalogEntriesFromDatabase(struct _JET_DB_STRUCT *a1, wchar_t *Str, int a3)
{
  const CTL_CONTEXT *v3; // rbx
  wchar_t *v6; // r12
  int v7; // eax
  unsigned int v8; // esi
  int v9; // edi
  DWORD v10; // eax
  unsigned int v11; // edx
  unsigned __int16 *v12; // rcx
  BOOL v13; // edi
  JET_ERR v14; // r15d
  DWORD v15; // eax
  unsigned int v16; // edx
  unsigned __int16 *v17; // rcx
  int CTLContextFromFileName; // eax
  unsigned int v19; // edx
  unsigned __int16 *v20; // rcx
  DWORD LastError; // edi
  DWORD v23; // [rsp+20h] [rbp-69h]
  int v24; // [rsp+28h] [rbp-61h]
  PCCTL_CONTEXT pCtlContext; // [rsp+30h] [rbp-59h] BYREF
  LPCVOID lpBaseAddress; // [rsp+38h] [rbp-51h] BYREF
  HANDLE hObject; // [rsp+40h] [rbp-49h] BYREF
  HANDLE v28; // [rsp+48h] [rbp-41h] BYREF
  int v29[4]; // [rsp+50h] [rbp-39h]
  _DWORD v30[16]; // [rsp+60h] [rbp-29h] BYREF

  v3 = 0;
  *(_QWORD *)v29 = Str;
  pCtlContext = 0;
  hObject = 0;
  lpBaseAddress = 0;
  v28 = (HANDLE)-1LL;
  v6 = _CatDBExtractCatBaseName(Str);
  v7 = _CatDBSeekInCatNameAttrTable(a1, v6);
  v8 = 1;
  v9 = v7;
  if ( v7 == -1601 )
    return v8;
  if ( (unsigned int)_CatDBJET_errFailure(v7) )
  {
    v10 = _CatDBMapJetError(v9);
    SetLastError(v10);
    ErrLog_LogError(v12, v11, 0x13CCu, 0, 0, v24);
  }
  else
  {
    v13 = 1;
    memset_0(v30, 0, sizeof(v30));
    if ( _CatDBRetrieveCatNameAttrTableAttrColumn(a1, (struct _CATALOG_ATTR_STRUCT *)v30) )
      v13 = v30[0] == 0;
    v14 = JetDelete(*((_QWORD *)a1 + 1), *((_QWORD *)a1 + 8));
    if ( (unsigned int)_CatDBJET_errFailure(v14) )
    {
      v15 = _CatDBMapJetError(v14);
      SetLastError(v15);
      ErrLog_LogError(v17, v16, 0x13E2u, 0, 0, v24);
    }
    else
    {
      if ( !v13 )
        return v8;
      if ( !a3 )
      {
        CTLContextFromFileName = CatUtil_CreateCTLContextFromFileName(
                                   v29[0],
                                   (int)&hObject,
                                   (int)&lpBaseAddress,
                                   (int)&pCtlContext,
                                   v23,
                                   (__int64)&v28);
        v3 = pCtlContext;
        if ( !CTLContextFromFileName
          || (unsigned int)_CatDBIterateOverCTL(
                             a1,
                             pCtlContext,
                             v6,
                             (int (*)(struct _JET_DB_STRUCT *, struct JET_DB_HASH_TABLE_IDS *, struct _CRYPTOAPI_BLOB *, const unsigned __int16 *))_CatDBRemoveCatNameFromHashesListOfCatNames) )
        {
          goto LABEL_15;
        }
      }
      if ( (unsigned int)_CatDBRemoveCatNameFromCatNameTable(a1, v6) )
        goto LABEL_15;
      ErrLog_LogError(v20, v19, 0x1412u, 0, 0, v24);
    }
  }
  v8 = 0;
LABEL_15:
  LastError = GetLastError();
  if ( v3 )
    CertFreeCTLContext(v3);
  if ( lpBaseAddress )
    UnmapViewOfFile(lpBaseAddress);
  if ( hObject )
    CloseHandle(hObject);
  if ( v28 != (HANDLE)-1LL )
    CloseHandle(v28);
  SetLastError(LastError);
  return v8;
}

```

## disassembly

```asm
0x180008888  mov     [rsp-8+arg_10], rbx
0x18000888d  push    rbp
0x18000888e  push    rsi
0x18000888f  push    rdi
0x180008890  push    r12
0x180008892  push    r13
0x180008894  push    r14
0x180008896  push    r15
0x180008898  lea     rbp, [rsp-27h]
0x18000889d  sub     rsp, 0B0h
0x1800088a4  mov     rax, cs:__security_cookie
0x1800088ab  xor     rax, rsp
0x1800088ae  mov     [rbp+57h+var_40], rax
0x1800088b2  xor     ebx, ebx
0x1800088b4  mov     qword ptr [rbp+57h+var_90], rdx
0x1800088b8  mov     r14, rcx
0x1800088bb  mov     [rbp+57h+pCtlContext], rbx
0x1800088bf  mov     rcx, rdx; Str
0x1800088c2  mov     [rbp+57h+hObject], rbx
0x1800088c6  mov     [rbp+57h+lpBaseAddress], rbx
0x1800088ca  mov     r13d, r8d
0x1800088cd  mov     [rbp+57h+var_98], 0FFFFFFFFFFFFFFFFh
0x1800088d5  call    ?_CatDBExtractCatBaseName@@YAPEBGPEBG@Z; _CatDBExtractCatBaseName(ushort const *)
0x1800088da  mov     rdx, rax; unsigned __int16 *
0x1800088dd  mov     rcx, r14; struct _JET_DB_STRUCT *
0x1800088e0  mov     r12, rax
0x1800088e3  call    ?_CatDBSeekInCatNameAttrTable@@YAJPEAU_JET_DB_STRUCT@@PEBG@Z; _CatDBSeekInCatNameAttrTable(_JET_DB_STRUCT *,ushort const *)
0x1800088e8  lea     esi, [rbx+1]
0x1800088eb  mov     edi, eax
0x1800088ed  cmp     eax, 0FFFFF9BFh
0x1800088f2  jz      loc_180008A3D
0x1800088f8  mov     ecx, eax; int
0x1800088fa  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x1800088ff  test    eax, eax
0x180008901  jz      short loc_180008921
0x180008903  mov     ecx, edi; int
0x180008905  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x18000890a  mov     ecx, eax; dwErrCode
0x18000890c  call    cs:__imp_SetLastError
0x180008912  mov     r8d, 13CCh
0x180008918  mov     [rsp+0E0h+var_C0], ebx
0x18000891c  jmp     loc_1800089E7
0x180008921  xor     edx, edx; Val
0x180008923  lea     rcx, [rbp+57h+var_80]; void *
0x180008927  mov     edi, esi
0x180008929  lea     r8d, [rdx+40h]; Size
0x18000892d  call    memset_0
0x180008932  lea     rdx, [rbp+57h+var_80]; struct _CATALOG_ATTR_STRUCT *
0x180008936  mov     rcx, r14; struct _JET_DB_STRUCT *
0x180008939  call    ?_CatDBRetrieveCatNameAttrTableAttrColumn@@YAHPEAU_JET_DB_STRUCT@@PEAU_CATALOG_ATTR_STRUCT@@@Z; _CatDBRetrieveCatNameAttrTableAttrColumn(_JET_DB_STRUCT *,_CATALOG_ATTR_STRUCT *)
0x18000893e  test    eax, eax
0x180008940  jz      short loc_18000894A
0x180008942  xor     eax, eax
0x180008944  cmp     [rbp+57h+var_80], eax
0x180008947  cmovnz  edi, eax
0x18000894a  mov     rdx, [r14+40h]; tableid
0x18000894e  mov     rcx, [r14+8]; sesid
0x180008952  call    cs:__imp_JetDelete
0x180008958  mov     ecx, eax; int
0x18000895a  mov     r15d, eax
0x18000895d  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x180008962  test    eax, eax
0x180008964  jz      short loc_180008982
0x180008966  mov     ecx, r15d; int
0x180008969  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x18000896e  mov     ecx, eax; dwErrCode
0x180008970  call    cs:__imp_SetLastError
0x180008976  mov     r8d, 13E2h
0x18000897c  mov     [rsp+0E0h+var_C0], ebx
0x180008980  jmp     short loc_1800089E7
0x180008982  test    edi, edi
0x180008984  jz      loc_180008A3D
0x18000898a  test    r13d, r13d
0x18000898d  jnz     short loc_1800089CE
0x18000898f  mov     rcx, qword ptr [rbp+57h+var_90]; int
0x180008993  lea     rax, [rbp+57h+var_98]
0x180008997  lea     r9, [rbp+57h+pCtlContext]; int
0x18000899b  mov     [rsp+0E0h+var_B8], rax; int
0x1800089a0  lea     r8, [rbp+57h+lpBaseAddress]; int
0x1800089a4  lea     rdx, [rbp+57h+hObject]; int
0x1800089a8  call    CatUtil_CreateCTLContextFromFileName
0x1800089ad  mov     rbx, [rbp+57h+pCtlContext]
0x1800089b1  test    eax, eax
0x1800089b3  jz      short loc_1800089F1
0x1800089b5  lea     r9, ?_CatDBRemoveCatNameFromHashesListOfCatNames@@YAHPEAU_JET_DB_STRUCT@@PEAUJET_DB_HASH_TABLE_IDS@@PEAU_CRYPTOAPI_BLOB@@PEBG@Z; int (*)(struct _JET_DB_STRUCT *, struct JET_DB_HASH_TABLE_IDS *, struct _CRYPTOAPI_BLOB *, const unsigned __int16 *)
0x1800089bc  mov     r8, r12; unsigned __int16 *
0x1800089bf  mov     rdx, rbx; struct _CTL_CONTEXT *
0x1800089c2  mov     rcx, r14; struct _JET_DB_STRUCT *
0x1800089c5  call    ?_CatDBIterateOverCTL@@YAHPEAU_JET_DB_STRUCT@@PEBU_CTL_CONTEXT@@PEBGP6AH0PEAUJET_DB_HASH_TABLE_IDS@@PEAU_CRYPTOAPI_BLOB@@2@Z@Z; _CatDBIterateOverCTL(_JET_DB_STRUCT *,_CTL_CONTEXT const *,ushort const *,int (*)(_JET_DB_STRUCT *,JET_DB_HASH_TABLE_IDS *,_CRYPTOAPI_BLOB *,ushort const *))
0x1800089ca  test    eax, eax
0x1800089cc  jnz     short loc_1800089F1
0x1800089ce  mov     rdx, r12; unsigned __int16 *
0x1800089d1  mov     rcx, r14; struct _JET_DB_STRUCT *
0x1800089d4  call    ?_CatDBRemoveCatNameFromCatNameTable@@YAHPEAU_JET_DB_STRUCT@@PEBG@Z; _CatDBRemoveCatNameFromCatNameTable(_JET_DB_STRUCT *,ushort const *)
0x1800089d9  test    eax, eax
0x1800089db  jnz     short loc_1800089F1
0x1800089dd  mov     [rsp+0E0h+var_C0], eax; int
0x1800089e1  mov     r8d, 1412h; unsigned int
0x1800089e7  xor     r9d, r9d; unsigned int
0x1800089ea  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x1800089ef  xor     esi, esi
0x1800089f1  call    cs:__imp_GetLastError
0x1800089f7  mov     edi, eax
0x1800089f9  test    rbx, rbx
0x1800089fc  jz      short loc_180008A07
0x1800089fe  mov     rcx, rbx; pCtlContext
0x180008a01  call    cs:__imp_CertFreeCTLContext
0x180008a07  mov     rcx, [rbp+57h+lpBaseAddress]; lpBaseAddress
0x180008a0b  test    rcx, rcx
0x180008a0e  jz      short loc_180008A16
0x180008a10  call    cs:__imp_UnmapViewOfFile
0x180008a16  mov     rcx, [rbp+57h+hObject]; hObject
0x180008a1a  test    rcx, rcx
0x180008a1d  jz      short loc_180008A25
0x180008a1f  call    cs:__imp_CloseHandle
0x180008a25  mov     rcx, [rbp+57h+var_98]; hObject
0x180008a29  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180008a2d  jz      short loc_180008A35
0x180008a2f  call    cs:__imp_CloseHandle
0x180008a35  mov     ecx, edi; dwErrCode
0x180008a37  call    cs:__imp_SetLastError
0x180008a3d  mov     eax, esi
0x180008a3f  mov     rcx, [rbp+57h+var_40]
0x180008a43  xor     rcx, rsp; StackCookie
0x180008a46  call    __security_check_cookie
0x180008a4b  mov     rbx, [rsp+0E0h+arg_10]
0x180008a53  add     rsp, 0B0h
0x180008a5a  pop     r15
0x180008a5c  pop     r14
0x180008a5e  pop     r13
0x180008a60  pop     r12
0x180008a62  pop     rdi
0x180008a63  pop     rsi
0x180008a64  pop     rbp
0x180008a65  retn
```
