# _CatDBAddValueToExistingHashCatNameRow(_JET_DB_STRUCT *,JET_DB_HASH_TABLE_IDS *,ushort const *)

- ea: `0x180003c50`
- end: `0x180003d42`
- name: `?_CatDBAddValueToExistingHashCatNameRow@@YAHPEAU_JET_DB_STRUCT@@PEAUJET_DB_HASH_TABLE_IDS@@PEBG@Z`
- size: `242`
- prototype: `int(struct _JET_DB_STRUCT *, struct JET_DB_HASH_TABLE_IDS *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180003b80`

## callees

- `0x1800015cc`
- `0x1800038f0`
- `0x180003c50`
- `0x180003ff8`
- `0x18000a59c`
- `0x18000acbc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003cf1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003d1d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003d34`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003cf1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003d1d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003d34`
- `ESENT!JetUpdate` at `0x180003cd5`
- `ESENT!JetUpdate` at `0x180003cd5`
- `ESENT!JetPrepareUpdate` at `0x180003c8c`
- `ESENT!JetPrepareUpdate` at `0x180003c8c`

## pseudocode

```c
__int64 __fastcall _CatDBAddValueToExistingHashCatNameRow(
        struct _JET_DB_STRUCT *a1,
        struct JET_DB_HASH_TABLE_IDS *a2,
        const unsigned __int16 *a3)
{
  unsigned int v6; // ebx
  JET_ERR v8; // ebp
  int v9; // ebp
  JET_ERR v10; // edi
  DWORD v11; // eax
  unsigned int v12; // edx
  unsigned __int16 *v13; // rcx
  unsigned int v14; // r8d
  DWORD v15; // eax
  DWORD v16; // eax
  int v17; // [rsp+28h] [rbp-30h]

  v6 = 1;
  if ( !(unsigned int)_CatDBCatnameAlreadyInHashesListOfCats(a1, a2, a3) )
  {
    v8 = JetPrepareUpdate(*((_QWORD *)a1 + 1), *(_QWORD *)a2, 2u);
    if ( (unsigned int)_CatDBJET_errFailure(v8) )
    {
      v15 = _CatDBMapJetError(v8);
      SetLastError(v15);
      v14 = 4941;
    }
    else
    {
      v9 = CatHelperAddToLongColumn(*((_QWORD *)a1 + 1), *(_QWORD *)a2, *((_DWORD *)a2 + 3), a3);
      if ( (unsigned int)_CatDBJET_errFailure(v9) )
      {
        v16 = _CatDBMapJetError(v9);
        SetLastError(v16);
        v14 = 4950;
      }
      else
      {
        v10 = JetUpdate(*((_QWORD *)a1 + 1), *(_QWORD *)a2, 0, 0, 0);
        if ( !(unsigned int)_CatDBJET_errFailure(v10) )
          return v6;
        v11 = _CatDBMapJetError(v10);
        SetLastError(v11);
        v14 = 4961;
      }
    }
    ErrLog_LogError(v13, v12, v14, 0, 0, v17);
    return 0;
  }
  return v6;
}

```

## disassembly

```asm
0x180003c50  push    rbx
0x180003c52  push    rbp
0x180003c53  push    rsi
0x180003c54  push    rdi
0x180003c55  push    r14
0x180003c57  sub     rsp, 30h
0x180003c5b  mov     r14, r8
0x180003c5e  mov     rdi, rdx
0x180003c61  mov     rsi, rcx
0x180003c64  mov     ebx, 1
0x180003c69  call    ?_CatDBCatnameAlreadyInHashesListOfCats@@YAHPEAU_JET_DB_STRUCT@@PEAUJET_DB_HASH_TABLE_IDS@@PEBG@Z; _CatDBCatnameAlreadyInHashesListOfCats(_JET_DB_STRUCT *,JET_DB_HASH_TABLE_IDS *,ushort const *)
0x180003c6e  test    eax, eax
0x180003c70  jz      short loc_180003C7F
0x180003c72  mov     eax, ebx
0x180003c74  add     rsp, 30h
0x180003c78  pop     r14
0x180003c7a  pop     rdi
0x180003c7b  pop     rsi
0x180003c7c  pop     rbp
0x180003c7d  pop     rbx
0x180003c7e  retn
0x180003c7f  mov     rdx, [rdi]; tableid
0x180003c82  mov     r8d, 2; prep
0x180003c88  mov     rcx, [rsi+8]; sesid
0x180003c8c  call    cs:__imp_JetPrepareUpdate
0x180003c92  mov     ecx, eax; int
0x180003c94  mov     ebp, eax
0x180003c96  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x180003c9b  test    eax, eax
0x180003c9d  jnz     short loc_180003D14
0x180003c9f  mov     r8d, [rdi+0Ch]; columnid
0x180003ca3  mov     r9, r14; lpWideCharStr
0x180003ca6  mov     rdx, [rdi]; tableid
0x180003ca9  mov     rcx, [rsi+8]; sesid
0x180003cad  call    ?CatHelperAddToLongColumn@@YAJ_K0KPEBG@Z; CatHelperAddToLongColumn(unsigned __int64,unsigned __int64,ulong,ushort const *)
0x180003cb2  mov     ecx, eax; int
0x180003cb4  mov     ebp, eax
0x180003cb6  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x180003cbb  test    eax, eax
0x180003cbd  jnz     short loc_180003D2B
0x180003cbf  mov     rdx, [rdi]; tableid
0x180003cc2  xor     r9d, r9d; cbBookmark
0x180003cc5  mov     rcx, [rsi+8]; sesid
0x180003cc9  xor     r8d, r8d; pvBookmark
0x180003ccc  mov     [rsp+58h+pcbActual], 0; pcbActual
0x180003cd5  call    cs:__imp_JetUpdate
0x180003cdb  mov     ecx, eax; int
0x180003cdd  mov     edi, eax
0x180003cdf  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x180003ce4  test    eax, eax
0x180003ce6  jz      short loc_180003C72
0x180003ce8  mov     ecx, edi; int
0x180003cea  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x180003cef  mov     ecx, eax; dwErrCode
0x180003cf1  call    cs:__imp_SetLastError
0x180003cf7  mov     r8d, 1361h; unsigned int
0x180003cfd  xor     r9d, r9d; unsigned int
0x180003d00  mov     dword ptr [rsp+58h+pcbActual], 0; int
0x180003d08  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180003d0d  xor     ebx, ebx
0x180003d0f  jmp     loc_180003C72
0x180003d14  mov     ecx, ebp; int
0x180003d16  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x180003d1b  mov     ecx, eax; dwErrCode
0x180003d1d  call    cs:__imp_SetLastError
0x180003d23  mov     r8d, 134Dh
0x180003d29  jmp     short loc_180003CFD
0x180003d2b  mov     ecx, ebp; int
0x180003d2d  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x180003d32  mov     ecx, eax; dwErrCode
0x180003d34  call    cs:__imp_SetLastError
0x180003d3a  mov     r8d, 1356h
0x180003d40  jmp     short loc_180003CFD
```
