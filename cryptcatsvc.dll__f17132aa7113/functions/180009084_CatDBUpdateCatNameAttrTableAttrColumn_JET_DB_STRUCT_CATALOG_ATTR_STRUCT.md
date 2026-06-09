# _CatDBUpdateCatNameAttrTableAttrColumn(_JET_DB_STRUCT *,_CATALOG_ATTR_STRUCT *)

- ea: `0x180009084`
- end: `0x18000918e`
- name: `?_CatDBUpdateCatNameAttrTableAttrColumn@@YAHPEAU_JET_DB_STRUCT@@PEAU_CATALOG_ATTR_STRUCT@@@Z`
- size: `266`
- prototype: `int(struct _JET_DB_STRUCT *, struct _CATALOG_ATTR_STRUCT *)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18001b8f4`
- `0x18001c7d4`

## callees

- `0x1800038f0`
- `0x180009084`
- `0x18000a59c`
- `0x18000acbc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800090c3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009118`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000915e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800090c3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009118`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000915e`
- `ESENT!JetUpdate` at `0x180009142`
- `ESENT!JetUpdate` at `0x180009142`
- `ESENT!JetSetColumn` at `0x1800090fc`
- `ESENT!JetSetColumn` at `0x1800090fc`
- `ESENT!JetPrepareUpdate` at `0x1800090a7`
- `ESENT!JetPrepareUpdate` at `0x1800090a7`

## pseudocode

```c
__int64 __fastcall _CatDBUpdateCatNameAttrTableAttrColumn(struct _JET_DB_STRUCT *a1, struct _CATALOG_ATTR_STRUCT *a2)
{
  JET_ERR v4; // ebx
  DWORD v5; // eax
  unsigned int v6; // edx
  unsigned __int16 *v7; // rcx
  unsigned int v8; // r8d
  JET_ERR v9; // ebx
  DWORD v10; // eax
  unsigned int v11; // ebx
  JET_ERR v12; // edi
  DWORD v13; // eax
  JET_GRBIT grbit; // [rsp+28h] [rbp-20h]

  v4 = JetPrepareUpdate(*((_QWORD *)a1 + 1), *((_QWORD *)a1 + 8), 2u);
  if ( (unsigned int)_CatDBJET_errFailure(v4) )
  {
    v5 = _CatDBMapJetError(v4);
    SetLastError(v5);
    v8 = 7498;
LABEL_7:
    ErrLog_LogError(v7, v6, v8, 0, 0, grbit);
    return 0;
  }
  v9 = JetSetColumn(*((_QWORD *)a1 + 1), *((_QWORD *)a1 + 8), *((_DWORD *)a1 + 20), a2, 0x40u, 0, 0);
  if ( (unsigned int)_CatDBJET_errFailure(v9) )
  {
    v10 = _CatDBMapJetError(v9);
    SetLastError(v10);
    v8 = 7513;
    goto LABEL_7;
  }
  v11 = 1;
  v12 = JetUpdate(*((_QWORD *)a1 + 1), *((_QWORD *)a1 + 8), 0, 0, 0);
  if ( (unsigned int)_CatDBJET_errFailure(v12) )
  {
    v13 = _CatDBMapJetError(v12);
    SetLastError(v13);
    v8 = 7525;
    goto LABEL_7;
  }
  return v11;
}

```

## disassembly

```asm
0x180009084  mov     [rsp+arg_0], rbx
0x180009089  mov     [rsp+arg_8], rsi
0x18000908e  push    rdi
0x18000908f  sub     rsp, 40h
0x180009093  mov     rsi, rdx
0x180009096  mov     rdi, rcx
0x180009099  mov     rdx, [rcx+40h]; tableid
0x18000909d  mov     r8d, 2; prep
0x1800090a3  mov     rcx, [rcx+8]; sesid
0x1800090a7  call    cs:__imp_JetPrepareUpdate
0x1800090ad  mov     ecx, eax; int
0x1800090af  mov     ebx, eax
0x1800090b1  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x1800090b6  test    eax, eax
0x1800090b8  jz      short loc_1800090D4
0x1800090ba  mov     ecx, ebx; int
0x1800090bc  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x1800090c1  mov     ecx, eax; dwErrCode
0x1800090c3  call    cs:__imp_SetLastError
0x1800090c9  mov     r8d, 1D4Ah
0x1800090cf  jmp     loc_18000916A
0x1800090d4  mov     r8d, [rdi+50h]; columnid
0x1800090d8  mov     r9, rsi; pvData
0x1800090db  mov     rdx, [rdi+40h]; tableid
0x1800090df  mov     rcx, [rdi+8]; sesid
0x1800090e3  mov     [rsp+48h+psetinfo], 0; psetinfo
0x1800090ec  mov     [rsp+48h+grbit], 0; int
0x1800090f4  mov     [rsp+48h+cbData], 40h ; '@'; cbData
0x1800090fc  call    cs:__imp_JetSetColumn
0x180009102  mov     ecx, eax; int
0x180009104  mov     ebx, eax
0x180009106  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x18000910b  test    eax, eax
0x18000910d  jz      short loc_180009126
0x18000910f  mov     ecx, ebx; int
0x180009111  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x180009116  mov     ecx, eax; dwErrCode
0x180009118  call    cs:__imp_SetLastError
0x18000911e  mov     r8d, 1D59h
0x180009124  jmp     short loc_18000916A
0x180009126  mov     rdx, [rdi+40h]; tableid
0x18000912a  xor     r9d, r9d; cbBookmark
0x18000912d  mov     rcx, [rdi+8]; sesid
0x180009131  xor     r8d, r8d; pvBookmark
0x180009134  mov     ebx, 1
0x180009139  mov     qword ptr [rsp+48h+cbData], 0; pcbActual
0x180009142  call    cs:__imp_JetUpdate
0x180009148  mov     ecx, eax; int
0x18000914a  mov     edi, eax
0x18000914c  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x180009151  test    eax, eax
0x180009153  jz      short loc_18000917C
0x180009155  mov     ecx, edi; int
0x180009157  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x18000915c  mov     ecx, eax; dwErrCode
0x18000915e  call    cs:__imp_SetLastError
0x180009164  mov     r8d, 1D65h; unsigned int
0x18000916a  xor     r9d, r9d; unsigned int
0x18000916d  mov     [rsp+48h+cbData], 0; int
0x180009175  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18000917a  xor     ebx, ebx
0x18000917c  mov     rsi, [rsp+48h+arg_8]
0x180009181  mov     eax, ebx
0x180009183  mov     rbx, [rsp+48h+arg_0]
0x180009188  add     rsp, 40h
0x18000918c  pop     rdi
0x18000918d  retn
```
