# _CatDBUpdateCatalogPathChangedTime(_JET_DB_STRUCT *,ushort const *,int)

- ea: `0x18001c7d4`
- end: `0x18001c99b`
- name: `?_CatDBUpdateCatalogPathChangedTime@@YAHPEAU_JET_DB_STRUCT@@PEBGH@Z`
- size: `455`
- prototype: `__int64 __fastcall(struct _JET_DB_STRUCT *, LPCWSTR lpFileName, int)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180017a04`
- `0x180019314`
- `0x18001c03c`

## callees

- `0x1800038f0`
- `0x180008b8c`
- `0x180009084`
- `0x18000a57c`
- `0x18000a59c`
- `0x18000acbc`
- `0x18000be40`
- `0x18000c7e8`
- `0x18001825c`
- `0x18001c7d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c881`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c8c7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c935`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c95a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c881`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c8c7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c935`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c95a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18001c834`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18001c834`
- `ESENT!JetBeginTransaction` at `0x18001c865`
- `ESENT!JetBeginTransaction` at `0x18001c865`
- `ESENT!JetRollback` at `0x18001c96b`
- `ESENT!JetRollback` at `0x18001c96b`
- `ESENT!JetCommitTransaction` at `0x18001c919`
- `ESENT!JetCommitTransaction` at `0x18001c919`

## pseudocode

```c
__int64 __fastcall _CatDBUpdateCatalogPathChangedTime(struct _JET_DB_STRUCT *a1, LPCWSTR lpFileName, int a3)
{
  int v6; // r14d
  unsigned int v7; // edx
  unsigned __int16 *v8; // rcx
  unsigned int v9; // esi
  JET_ERR v10; // ebp
  DWORD v11; // eax
  unsigned int v12; // edx
  unsigned __int16 *v13; // rcx
  int v14; // ebp
  DWORD v15; // eax
  unsigned int v16; // edx
  unsigned __int16 *v17; // rcx
  unsigned int v18; // r8d
  JET_ERR v19; // ebx
  DWORD v20; // eax
  DWORD Error; // eax
  int v23; // [rsp+28h] [rbp-A0h]
  __int128 FileInformation; // [rsp+30h] [rbp-98h] BYREF
  __int128 v25; // [rsp+40h] [rbp-88h]
  int v26; // [rsp+50h] [rbp-78h]
  _BYTE v27[16]; // [rsp+60h] [rbp-68h] BYREF
  __int64 v28; // [rsp+70h] [rbp-58h]

  memset_0(v27, 0, 0x40u);
  v26 = 0;
  FileInformation = 0;
  v6 = 0;
  v25 = 0;
  if ( !GetFileAttributesExW(lpFileName, GetFileExInfoStandard, &FileInformation) )
  {
    ErrLog_LogError(v8, v7, 0x561u, 0, 0, v23);
    goto LABEL_18;
  }
  v9 = 1;
  v28 = *(_QWORD *)((char *)&v25 + 4);
  if ( !a3 )
  {
    v10 = JetBeginTransaction(*((_QWORD *)a1 + 1));
    if ( (unsigned int)_CatDBJET_errFailure(v10) )
    {
      v11 = _CatDBMapJetError(v10);
      SetLastError(v11);
      ErrLog_LogError(v13, v12, 0x56Cu, 0, 0, v23);
      goto LABEL_18;
    }
    v6 = 1;
  }
  v14 = _CatDBSeekInCatNameAttrTable(a1, L"|");
  if ( !(unsigned int)_CatDBJET_errFailure(v14) )
  {
    if ( !_CatDBUpdateCatNameAttrTableAttrColumn(a1, (struct _CATALOG_ATTR_STRUCT *)v27) )
    {
      v18 = 1415;
      goto LABEL_17;
    }
    goto LABEL_14;
  }
  if ( v14 == -1601 )
  {
    if ( !(unsigned int)_CatDBAddNewRowToCatNameAttrTable(a1, L"|", (struct _CATALOG_ATTR_STRUCT *)v27) )
    {
      v18 = 1408;
      goto LABEL_17;
    }
LABEL_14:
    if ( !v6 )
      return v9;
    v19 = JetCommitTransaction(*((_QWORD *)a1 + 1), 0);
    if ( !(unsigned int)_CatDBJET_errFailure(v19) )
      return v9;
    v20 = _CatDBMapJetError(v19);
    SetLastError(v20);
    v18 = 1424;
    goto LABEL_17;
  }
  v15 = _CatDBMapJetError(v14);
  SetLastError(v15);
  v18 = 1400;
LABEL_17:
  ErrLog_LogError(v17, v16, v18, 0, 0, v23);
LABEL_18:
  v9 = 0;
  Error = _CatDBGetNonzeroLastError();
  SetLastError(Error);
  if ( v6 )
    JetRollback(*((_QWORD *)a1 + 1), 0);
  return v9;
}

```

## disassembly

```asm
0x18001c7d4  mov     [rsp+arg_10], rbx
0x18001c7d9  mov     [rsp+arg_18], rbp
0x18001c7de  push    rsi
0x18001c7df  push    rdi
0x18001c7e0  push    r14
0x18001c7e2  sub     rsp, 0B0h
0x18001c7e9  mov     rax, cs:__security_cookie
0x18001c7f0  xor     rax, rsp
0x18001c7f3  mov     [rsp+0C8h+var_28], rax
0x18001c7fb  mov     rbx, rdx
0x18001c7fe  mov     ebp, r8d
0x18001c801  xor     edx, edx; Val
0x18001c803  mov     rdi, rcx
0x18001c806  lea     rcx, [rsp+0C8h+var_68]; void *
0x18001c80b  lea     r8d, [rdx+40h]; Size
0x18001c80f  call    memset_0
0x18001c814  xorps   xmm0, xmm0
0x18001c817  lea     r8, [rsp+0C8h+FileInformation]; lpFileInformation
0x18001c81c  xor     eax, eax
0x18001c81e  xor     edx, edx; fInfoLevelId
0x18001c820  mov     rcx, rbx; lpFileName
0x18001c823  mov     [rsp+0C8h+var_78], eax
0x18001c827  movups  [rsp+0C8h+FileInformation], xmm0
0x18001c82c  xor     r14d, r14d
0x18001c82f  movups  [rsp+0C8h+var_88], xmm0
0x18001c834  call    cs:__imp_GetFileAttributesExW
0x18001c83a  test    eax, eax
0x18001c83c  jnz     short loc_18001C84E
0x18001c83e  mov     [rsp+0C8h+var_A8], r14d
0x18001c843  mov     r8d, 561h
0x18001c849  jmp     loc_18001C949
0x18001c84e  mov     rax, qword ptr [rsp+0C8h+var_88+4]
0x18001c853  mov     esi, 1
0x18001c858  mov     [rsp+0C8h+var_58], rax
0x18001c85d  test    ebp, ebp
0x18001c85f  jnz     short loc_18001C89A
0x18001c861  mov     rcx, [rdi+8]; sesid
0x18001c865  call    cs:__imp_JetBeginTransaction
0x18001c86b  mov     ecx, eax; int
0x18001c86d  mov     ebp, eax
0x18001c86f  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x18001c874  test    eax, eax
0x18001c876  jz      short loc_18001C897
0x18001c878  mov     ecx, ebp; int
0x18001c87a  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x18001c87f  mov     ecx, eax; dwErrCode
0x18001c881  call    cs:__imp_SetLastError
0x18001c887  mov     r8d, 56Ch
0x18001c88d  mov     [rsp+0C8h+var_A8], r14d
0x18001c892  jmp     loc_18001C949
0x18001c897  mov     r14d, esi
0x18001c89a  lea     rdx, WideCharStr; "|"
0x18001c8a1  mov     rcx, rdi; struct _JET_DB_STRUCT *
0x18001c8a4  call    ?_CatDBSeekInCatNameAttrTable@@YAJPEAU_JET_DB_STRUCT@@PEBG@Z; _CatDBSeekInCatNameAttrTable(_JET_DB_STRUCT *,ushort const *)
0x18001c8a9  mov     ecx, eax; int
0x18001c8ab  mov     ebp, eax
0x18001c8ad  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x18001c8b2  test    eax, eax
0x18001c8b4  jz      short loc_18001C8F5
0x18001c8b6  cmp     ebp, 0FFFFF9BFh
0x18001c8bc  jz      short loc_18001C8D5
0x18001c8be  mov     ecx, ebp; int
0x18001c8c0  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x18001c8c5  mov     ecx, eax; dwErrCode
0x18001c8c7  call    cs:__imp_SetLastError
0x18001c8cd  mov     r8d, 578h
0x18001c8d3  jmp     short loc_18001C941
0x18001c8d5  lea     r8, [rsp+0C8h+var_68]; struct _CATALOG_ATTR_STRUCT *
0x18001c8da  mov     rcx, rdi; struct _JET_DB_STRUCT *
0x18001c8dd  lea     rdx, WideCharStr; "|"
0x18001c8e4  call    ?_CatDBAddNewRowToCatNameAttrTable@@YAHPEAU_JET_DB_STRUCT@@PEBGPEAU_CATALOG_ATTR_STRUCT@@@Z; _CatDBAddNewRowToCatNameAttrTable(_JET_DB_STRUCT *,ushort const *,_CATALOG_ATTR_STRUCT *)
0x18001c8e9  test    eax, eax
0x18001c8eb  jnz     short loc_18001C90E
0x18001c8ed  mov     r8d, 580h
0x18001c8f3  jmp     short loc_18001C941
0x18001c8f5  lea     rdx, [rsp+0C8h+var_68]; struct _CATALOG_ATTR_STRUCT *
0x18001c8fa  mov     rcx, rdi; struct _JET_DB_STRUCT *
0x18001c8fd  call    ?_CatDBUpdateCatNameAttrTableAttrColumn@@YAHPEAU_JET_DB_STRUCT@@PEAU_CATALOG_ATTR_STRUCT@@@Z; _CatDBUpdateCatNameAttrTableAttrColumn(_JET_DB_STRUCT *,_CATALOG_ATTR_STRUCT *)
0x18001c902  test    eax, eax
0x18001c904  jnz     short loc_18001C90E
0x18001c906  mov     r8d, 587h
0x18001c90c  jmp     short loc_18001C941
0x18001c90e  test    r14d, r14d
0x18001c911  jz      short loc_18001C971
0x18001c913  mov     rcx, [rdi+8]; sesid
0x18001c917  xor     edx, edx; grbit
0x18001c919  call    cs:__imp_JetCommitTransaction
0x18001c91f  mov     ecx, eax; int
0x18001c921  mov     ebx, eax
0x18001c923  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x18001c928  test    eax, eax
0x18001c92a  jz      short loc_18001C971
0x18001c92c  mov     ecx, ebx; int
0x18001c92e  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x18001c933  mov     ecx, eax; dwErrCode
0x18001c935  call    cs:__imp_SetLastError
0x18001c93b  mov     r8d, 590h; unsigned int
0x18001c941  mov     [rsp+0C8h+var_A8], 0; int
0x18001c949  xor     r9d, r9d; unsigned int
0x18001c94c  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18001c951  xor     esi, esi
0x18001c953  call    ?_CatDBGetNonzeroLastError@@YAKXZ; _CatDBGetNonzeroLastError(void)
0x18001c958  mov     ecx, eax; dwErrCode
0x18001c95a  call    cs:__imp_SetLastError
0x18001c960  test    r14d, r14d
0x18001c963  jz      short loc_18001C971
0x18001c965  mov     rcx, [rdi+8]; sesid
0x18001c969  xor     edx, edx; grbit
0x18001c96b  call    cs:__imp_JetRollback
0x18001c971  mov     eax, esi
0x18001c973  mov     rcx, [rsp+0C8h+var_28]
0x18001c97b  xor     rcx, rsp; StackCookie
0x18001c97e  call    __security_check_cookie
0x18001c983  lea     r11, [rsp+0C8h+var_18]
0x18001c98b  mov     rbx, [r11+30h]
0x18001c98f  mov     rbp, [r11+38h]
0x18001c993  mov     rsp, r11
0x18001c996  pop     r14
0x18001c998  pop     rdi
0x18001c999  pop     rsi
0x18001c99a  retn
```
