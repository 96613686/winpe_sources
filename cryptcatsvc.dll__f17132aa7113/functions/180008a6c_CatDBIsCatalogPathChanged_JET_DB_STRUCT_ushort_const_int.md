# _CatDBIsCatalogPathChanged(_JET_DB_STRUCT *,ushort const *,int *)

- ea: `0x180008a6c`
- end: `0x180008b84`
- name: `?_CatDBIsCatalogPathChanged@@YAHPEAU_JET_DB_STRUCT@@PEBGPEAH@Z`
- size: `280`
- prototype: `__int64 __fastcall(struct _JET_DB_STRUCT *, LPCWSTR lpFileName, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001c03c`

## callees

- `0x1800038f0`
- `0x180004094`
- `0x180008a6c`
- `0x180008b8c`
- `0x18000a57c`
- `0x18000a59c`
- `0x18000acbc`
- `0x18000be40`
- `0x18000c7e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008b15`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008b49`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008b15`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008b49`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180008abf`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180008abf`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180008b74`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180008b74`

## pseudocode

```c
__int64 __fastcall _CatDBIsCatalogPathChanged(struct _JET_DB_STRUCT *a1, LPCWSTR lpFileName, int *a3)
{
  unsigned int v6; // edx
  unsigned __int16 *v7; // rcx
  int v8; // ebx
  unsigned int v9; // r8d
  unsigned int v10; // ebx
  DWORD Error; // eax
  DWORD v13; // eax
  LONG v14; // eax
  int v15; // [rsp+28h] [rbp-A0h]
  __int128 FileInformation; // [rsp+30h] [rbp-98h] BYREF
  FILETIME FileTime1[2]; // [rsp+40h] [rbp-88h] BYREF
  int v18; // [rsp+50h] [rbp-78h]
  _BYTE v19[16]; // [rsp+60h] [rbp-68h] BYREF
  FILETIME FileTime2; // [rsp+70h] [rbp-58h] BYREF

  memset_0(v19, 0, 0x40u);
  v18 = 0;
  FileInformation = 0;
  *(_OWORD *)&FileTime1[0].dwLowDateTime = 0;
  if ( !GetFileAttributesExW(lpFileName, GetFileExInfoStandard, &FileInformation) )
  {
    v9 = 1313;
    goto LABEL_5;
  }
  v8 = _CatDBSeekInCatNameAttrTable(a1, L"|");
  if ( (unsigned int)_CatDBJET_errFailure(v8) )
  {
    v13 = _CatDBMapJetError(v8);
    SetLastError(v13);
    v9 = 1320;
    goto LABEL_5;
  }
  if ( !_CatDBRetrieveCatNameAttrTableAttrColumn(a1, (struct _CATALOG_ATTR_STRUCT *)v19) )
  {
    v9 = 1325;
LABEL_5:
    ErrLog_LogError(v7, v6, v9, 0, 0, v15);
    v10 = 0;
    Error = _CatDBGetNonzeroLastError();
    SetLastError(Error);
    return v10;
  }
  v10 = 1;
  if ( !FileTime1[1].dwLowDateTime && !FileTime1[0].dwHighDateTime
    || (v14 = CompareFileTime((const FILETIME *)&FileTime1[0].dwHighDateTime, &FileTime2)) != 0 )
  {
    v14 = 1;
  }
  *a3 = v14;
  return v10;
}

```

## disassembly

```asm
0x180008a6c  push    rbx
0x180008a6e  push    rsi
0x180008a6f  push    rdi
0x180008a70  sub     rsp, 0B0h
0x180008a77  mov     rax, cs:__security_cookie
0x180008a7e  xor     rax, rsp
0x180008a81  mov     [rsp+0C8h+var_28], rax
0x180008a89  mov     rbx, rdx
0x180008a8c  mov     rsi, r8
0x180008a8f  xor     edx, edx; Val
0x180008a91  mov     rdi, rcx
0x180008a94  lea     rcx, [rsp+0C8h+var_68]; void *
0x180008a99  lea     r8d, [rdx+40h]; Size
0x180008a9d  call    memset_0
0x180008aa2  xorps   xmm0, xmm0
0x180008aa5  lea     r8, [rsp+0C8h+FileInformation]; lpFileInformation
0x180008aaa  xor     eax, eax
0x180008aac  xor     edx, edx; fInfoLevelId
0x180008aae  mov     rcx, rbx; lpFileName
0x180008ab1  mov     [rsp+0C8h+var_78], eax
0x180008ab5  movups  [rsp+0C8h+FileInformation], xmm0
0x180008aba  movups  xmmword ptr [rsp+0C8h+FileTime1.dwLowDateTime], xmm0
0x180008abf  call    cs:__imp_GetFileAttributesExW
0x180008ac5  test    eax, eax
0x180008ac7  jz      short loc_180008B38
0x180008ac9  lea     rdx, WideCharStr; "|"
0x180008ad0  mov     rcx, rdi; struct _JET_DB_STRUCT *
0x180008ad3  call    ?_CatDBSeekInCatNameAttrTable@@YAJPEAU_JET_DB_STRUCT@@PEBG@Z; _CatDBSeekInCatNameAttrTable(_JET_DB_STRUCT *,ushort const *)
0x180008ad8  mov     ecx, eax; int
0x180008ada  mov     ebx, eax
0x180008adc  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x180008ae1  test    eax, eax
0x180008ae3  jnz     short loc_180008B40
0x180008ae5  lea     rdx, [rsp+0C8h+var_68]; struct _CATALOG_ATTR_STRUCT *
0x180008aea  mov     rcx, rdi; struct _JET_DB_STRUCT *
0x180008aed  call    ?_CatDBRetrieveCatNameAttrTableAttrColumn@@YAHPEAU_JET_DB_STRUCT@@PEAU_CATALOG_ATTR_STRUCT@@@Z; _CatDBRetrieveCatNameAttrTableAttrColumn(_JET_DB_STRUCT *,_CATALOG_ATTR_STRUCT *)
0x180008af2  test    eax, eax
0x180008af4  jnz     short loc_180008B57
0x180008af6  mov     r8d, 52Dh; unsigned int
0x180008afc  xor     r9d, r9d; unsigned int
0x180008aff  mov     [rsp+0C8h+var_A8], 0; int
0x180008b07  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180008b0c  xor     ebx, ebx
0x180008b0e  call    ?_CatDBGetNonzeroLastError@@YAKXZ; _CatDBGetNonzeroLastError(void)
0x180008b13  mov     ecx, eax; dwErrCode
0x180008b15  call    cs:__imp_SetLastError
0x180008b1b  mov     eax, ebx
0x180008b1d  mov     rcx, [rsp+0C8h+var_28]
0x180008b25  xor     rcx, rsp; StackCookie
0x180008b28  call    __security_check_cookie
0x180008b2d  add     rsp, 0B0h
0x180008b34  pop     rdi
0x180008b35  pop     rsi
0x180008b36  pop     rbx
0x180008b37  retn
0x180008b38  mov     r8d, 521h
0x180008b3e  jmp     short loc_180008AFC
0x180008b40  mov     ecx, ebx; int
0x180008b42  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x180008b47  mov     ecx, eax; dwErrCode
0x180008b49  call    cs:__imp_SetLastError
0x180008b4f  mov     r8d, 528h
0x180008b55  jmp     short loc_180008AFC
0x180008b57  cmp     [rsp+0C8h+FileTime1.dwLowDateTime+8], 0
0x180008b5c  mov     ebx, 1
0x180008b61  jnz     short loc_180008B6A
0x180008b63  cmp     [rsp+0C8h+FileTime1.dwHighDateTime], 0
0x180008b68  jz      short loc_180008B7E
0x180008b6a  lea     rdx, [rsp+0C8h+FileTime2]; lpFileTime2
0x180008b6f  lea     rcx, [rsp+0C8h+FileTime1.dwHighDateTime]; lpFileTime1
0x180008b74  call    cs:__imp_CompareFileTime
0x180008b7a  test    eax, eax
0x180008b7c  jz      short loc_180008B80
0x180008b7e  mov     eax, ebx
0x180008b80  mov     [rsi], eax
0x180008b82  jmp     short loc_180008B1B
```
