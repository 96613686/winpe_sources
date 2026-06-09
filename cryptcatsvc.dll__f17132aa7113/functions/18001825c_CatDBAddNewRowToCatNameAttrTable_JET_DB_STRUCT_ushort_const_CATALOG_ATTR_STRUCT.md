# _CatDBAddNewRowToCatNameAttrTable(_JET_DB_STRUCT *,ushort const *,_CATALOG_ATTR_STRUCT *)

- ea: `0x18001825c`
- end: `0x1800184c0`
- name: `?_CatDBAddNewRowToCatNameAttrTable@@YAHPEAU_JET_DB_STRUCT@@PEBGPEAU_CATALOG_ATTR_STRUCT@@@Z`
- size: `612`
- prototype: `int(struct _JET_DB_STRUCT *, const unsigned __int16 *, struct _CATALOG_ATTR_STRUCT *)`
- caller_count: `3`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180017a04`
- `0x18001b8f4`
- `0x18001c7d4`

## callees

- `0x1800038f0`
- `0x18000a59c`
- `0x18000acbc`
- `0x18000be40`
- `0x18001825c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800182c1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800182f9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001839e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800183eb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018439`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001847b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800182c1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800182f9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001839e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800183eb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018439`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001847b`
- `api-ms-win-core-localization-l1-2-0!LCMapStringEx` at `0x18001834c`
- `api-ms-win-core-localization-l1-2-0!LCMapStringEx` at `0x18001834c`
- `ESENT!JetMove` at `0x18001829b`
- `ESENT!JetMove` at `0x18001829b`
- `ESENT!JetUpdate` at `0x18001845f`
- `ESENT!JetUpdate` at `0x18001845f`
- `ESENT!JetSetColumn` at `0x180018382`
- `ESENT!JetSetColumn` at `0x1800183cf`
- `ESENT!JetSetColumn` at `0x18001841d`
- `ESENT!JetSetColumn` at `0x180018382`
- `ESENT!JetSetColumn` at `0x1800183cf`
- `ESENT!JetSetColumn` at `0x18001841d`
- `ESENT!JetPrepareUpdate` at `0x1800182dd`
- `ESENT!JetPrepareUpdate` at `0x1800182dd`

## pseudocode

```c
__int64 __fastcall _CatDBAddNewRowToCatNameAttrTable(
        struct _JET_DB_STRUCT *a1,
        const unsigned __int16 *a2,
        struct _CATALOG_ATTR_STRUCT *a3)
{
  JET_ERR v6; // eax
  int v7; // edi
  DWORD v8; // eax
  unsigned int v9; // edx
  unsigned __int16 *v10; // rcx
  unsigned int v11; // r8d
  JET_ERR v12; // edi
  DWORD v13; // eax
  __int64 v14; // rdi
  int v15; // eax
  JET_ERR v16; // esi
  DWORD v17; // eax
  JET_ERR v18; // edi
  DWORD v19; // eax
  JET_ERR v20; // edi
  DWORD v21; // eax
  unsigned int v22; // edi
  JET_ERR v23; // ebx
  DWORD v24; // eax
  int cchDest; // [rsp+28h] [rbp-260h]
  WCHAR DestStr[256]; // [rsp+50h] [rbp-238h] BYREF

  v6 = JetMove(*((_QWORD *)a1 + 1), *((_QWORD *)a1 + 8), 0x7FFFFFFF, 0);
  v7 = v6;
  if ( v6 != -1603 && (unsigned int)_CatDBJET_errFailure(v6) )
  {
    v8 = _CatDBMapJetError(v7);
    SetLastError(v8);
    v11 = 7379;
LABEL_18:
    ErrLog_LogError(v10, v9, v11, 0, 0, cchDest);
    return 0;
  }
  v12 = JetPrepareUpdate(*((_QWORD *)a1 + 1), *((_QWORD *)a1 + 8), 0);
  if ( (unsigned int)_CatDBJET_errFailure(v12) )
  {
    v13 = _CatDBMapJetError(v12);
    SetLastError(v13);
    v11 = 7391;
    goto LABEL_18;
  }
  v14 = -1;
  do
    ++v14;
  while ( a2[v14] );
  v15 = LCMapStringEx(&LocaleName, 0x200u, a2, v14, DestStr, 256, 0, 0, 0);
  if ( !v15 )
  {
    v11 = 7410;
    goto LABEL_18;
  }
  v16 = JetSetColumn(*((_QWORD *)a1 + 1), *((_QWORD *)a1 + 8), *((_DWORD *)a1 + 18), DestStr, 2 * v15, 0, 0);
  if ( (unsigned int)_CatDBJET_errFailure(v16) )
  {
    v17 = _CatDBMapJetError(v16);
    SetLastError(v17);
    v11 = 7424;
    goto LABEL_18;
  }
  v18 = JetSetColumn(*((_QWORD *)a1 + 1), *((_QWORD *)a1 + 8), *((_DWORD *)a1 + 19), a2, 2 * v14, 0, 0);
  if ( (unsigned int)_CatDBJET_errFailure(v18) )
  {
    v19 = _CatDBMapJetError(v18);
    SetLastError(v19);
    v11 = 7438;
    goto LABEL_18;
  }
  v20 = JetSetColumn(*((_QWORD *)a1 + 1), *((_QWORD *)a1 + 8), *((_DWORD *)a1 + 20), a3, 0x40u, 0, 0);
  if ( (unsigned int)_CatDBJET_errFailure(v20) )
  {
    v21 = _CatDBMapJetError(v20);
    SetLastError(v21);
    v11 = 7452;
    goto LABEL_18;
  }
  v22 = 1;
  v23 = JetUpdate(*((_QWORD *)a1 + 1), *((_QWORD *)a1 + 8), 0, 0, 0);
  if ( (unsigned int)_CatDBJET_errFailure(v23) )
  {
    v24 = _CatDBMapJetError(v23);
    SetLastError(v24);
    v11 = 7464;
    goto LABEL_18;
  }
  return v22;
}

```

## disassembly

```asm
0x18001825c  mov     [rsp+arg_18], rbx
0x180018261  push    rbp
0x180018262  push    rsi
0x180018263  push    rdi
0x180018264  push    r14
0x180018266  push    r15
0x180018268  sub     rsp, 260h
0x18001826f  mov     rax, cs:__security_cookie
0x180018276  xor     rax, rsp
0x180018279  mov     [rsp+288h+var_38], rax
0x180018281  mov     rbp, rdx
0x180018284  mov     r14, r8
0x180018287  mov     rdx, [rcx+40h]; tableid
0x18001828b  mov     rbx, rcx
0x18001828e  mov     rcx, [rcx+8]; sesid
0x180018292  xor     r9d, r9d; grbit
0x180018295  mov     r8d, 7FFFFFFFh; cRow
0x18001829b  call    cs:__imp_JetMove
0x1800182a1  xor     r15d, r15d
0x1800182a4  mov     edi, eax
0x1800182a6  cmp     eax, 0FFFFF9BDh
0x1800182ab  jz      short loc_1800182D2
0x1800182ad  mov     ecx, eax; int
0x1800182af  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x1800182b4  test    eax, eax
0x1800182b6  jz      short loc_1800182D2
0x1800182b8  mov     ecx, edi; int
0x1800182ba  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x1800182bf  mov     ecx, eax; dwErrCode
0x1800182c1  call    cs:__imp_SetLastError
0x1800182c7  mov     r8d, 1CD3h
0x1800182cd  jmp     loc_180018487
0x1800182d2  mov     rdx, [rbx+40h]; tableid
0x1800182d6  xor     r8d, r8d; prep
0x1800182d9  mov     rcx, [rbx+8]; sesid
0x1800182dd  call    cs:__imp_JetPrepareUpdate
0x1800182e3  mov     ecx, eax; int
0x1800182e5  mov     edi, eax
0x1800182e7  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x1800182ec  test    eax, eax
0x1800182ee  jz      short loc_18001830A
0x1800182f0  mov     ecx, edi; int
0x1800182f2  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x1800182f7  mov     ecx, eax; dwErrCode
0x1800182f9  call    cs:__imp_SetLastError
0x1800182ff  mov     r8d, 1CDFh
0x180018305  jmp     loc_180018487
0x18001830a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001830e  inc     rdi
0x180018311  cmp     [rbp+rdi*2+0], r15w
0x180018317  jnz     short loc_18001830E
0x180018319  mov     [rsp+288h+sortHandle], r15; sortHandle
0x18001831e  lea     rax, [rsp+288h+DestStr]
0x180018323  mov     [rsp+288h+lpReserved], r15; lpReserved
0x180018328  lea     rcx, LocaleName; lpLocaleName
0x18001832f  mov     [rsp+288h+lpVersionInformation], r15; lpVersionInformation
0x180018334  mov     r9d, edi; cchSrc
0x180018337  mov     [rsp+288h+cchDest], 100h; cchDest
0x18001833f  mov     r8, rbp; lpSrcStr
0x180018342  mov     edx, 200h; dwMapFlags
0x180018347  mov     [rsp+288h+lpDestStr], rax; lpDestStr
0x18001834c  call    cs:__imp_LCMapStringEx
0x180018352  test    eax, eax
0x180018354  jnz     short loc_180018361
0x180018356  mov     r8d, 1CF2h
0x18001835c  jmp     loc_180018487
0x180018361  mov     r8d, [rbx+48h]; columnid
0x180018365  lea     r9, [rsp+288h+DestStr]; pvData
0x18001836a  mov     rdx, [rbx+40h]; tableid
0x18001836e  add     eax, eax
0x180018370  mov     rcx, [rbx+8]; sesid
0x180018374  mov     [rsp+288h+lpVersionInformation], r15; psetinfo
0x180018379  mov     [rsp+288h+cchDest], r15d; grbit
0x18001837e  mov     dword ptr [rsp+288h+lpDestStr], eax; cbData
0x180018382  call    cs:__imp_JetSetColumn
0x180018388  mov     ecx, eax; int
0x18001838a  mov     esi, eax
0x18001838c  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x180018391  test    eax, eax
0x180018393  jz      short loc_1800183AF
0x180018395  mov     ecx, esi; int
0x180018397  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x18001839c  mov     ecx, eax; dwErrCode
0x18001839e  call    cs:__imp_SetLastError
0x1800183a4  mov     r8d, 1D00h
0x1800183aa  jmp     loc_180018487
0x1800183af  mov     r8d, [rbx+4Ch]; columnid
0x1800183b3  lea     eax, [rdi+rdi]
0x1800183b6  mov     rdx, [rbx+40h]; tableid
0x1800183ba  mov     r9, rbp; pvData
0x1800183bd  mov     rcx, [rbx+8]; sesid
0x1800183c1  mov     [rsp+288h+lpVersionInformation], r15; psetinfo
0x1800183c6  mov     [rsp+288h+cchDest], r15d; grbit
0x1800183cb  mov     dword ptr [rsp+288h+lpDestStr], eax; cbData
0x1800183cf  call    cs:__imp_JetSetColumn
0x1800183d5  mov     ecx, eax; int
0x1800183d7  mov     edi, eax
0x1800183d9  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x1800183de  test    eax, eax
0x1800183e0  jz      short loc_1800183FC
0x1800183e2  mov     ecx, edi; int
0x1800183e4  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x1800183e9  mov     ecx, eax; dwErrCode
0x1800183eb  call    cs:__imp_SetLastError
0x1800183f1  mov     r8d, 1D0Eh
0x1800183f7  jmp     loc_180018487
0x1800183fc  mov     r8d, [rbx+50h]; columnid
0x180018400  mov     r9, r14; pvData
0x180018403  mov     rdx, [rbx+40h]; tableid
0x180018407  mov     rcx, [rbx+8]; sesid
0x18001840b  mov     [rsp+288h+lpVersionInformation], r15; psetinfo
0x180018410  mov     [rsp+288h+cchDest], r15d; int
0x180018415  mov     dword ptr [rsp+288h+lpDestStr], 40h ; '@'; cbData
0x18001841d  call    cs:__imp_JetSetColumn
0x180018423  mov     ecx, eax; int
0x180018425  mov     edi, eax
0x180018427  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x18001842c  test    eax, eax
0x18001842e  jz      short loc_180018447
0x180018430  mov     ecx, edi; int
0x180018432  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x180018437  mov     ecx, eax; dwErrCode
0x180018439  call    cs:__imp_SetLastError
0x18001843f  mov     r8d, 1D1Ch
0x180018445  jmp     short loc_180018487
0x180018447  mov     rdx, [rbx+40h]; tableid
0x18001844b  xor     r9d, r9d; cbBookmark
0x18001844e  mov     rcx, [rbx+8]; sesid
0x180018452  xor     r8d, r8d; pvBookmark
0x180018455  mov     edi, 1
0x18001845a  mov     [rsp+288h+lpDestStr], r15; pcbActual
0x18001845f  call    cs:__imp_JetUpdate
0x180018465  mov     ecx, eax; int
0x180018467  mov     ebx, eax
0x180018469  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x18001846e  test    eax, eax
0x180018470  jz      short loc_180018497
0x180018472  mov     ecx, ebx; int
0x180018474  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x180018479  mov     ecx, eax; dwErrCode
0x18001847b  call    cs:__imp_SetLastError
0x180018481  mov     r8d, 1D28h; unsigned int
0x180018487  xor     r9d, r9d; unsigned int
0x18001848a  mov     dword ptr [rsp+288h+lpDestStr], r15d; int
0x18001848f  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180018494  mov     edi, r15d
0x180018497  mov     eax, edi
0x180018499  mov     rcx, [rsp+288h+var_38]
0x1800184a1  xor     rcx, rsp; StackCookie
0x1800184a4  call    __security_check_cookie
0x1800184a9  mov     rbx, [rsp+288h+arg_18]
0x1800184b1  add     rsp, 260h
0x1800184b8  pop     r15
0x1800184ba  pop     r14
0x1800184bc  pop     rdi
0x1800184bd  pop     rsi
0x1800184be  pop     rbp
0x1800184bf  retn
```
