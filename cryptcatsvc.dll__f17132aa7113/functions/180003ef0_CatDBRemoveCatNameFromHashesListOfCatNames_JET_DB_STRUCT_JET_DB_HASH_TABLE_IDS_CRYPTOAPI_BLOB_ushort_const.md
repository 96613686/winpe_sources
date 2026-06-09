# _CatDBRemoveCatNameFromHashesListOfCatNames(_JET_DB_STRUCT *,JET_DB_HASH_TABLE_IDS *,_CRYPTOAPI_BLOB *,ushort const *)

- ea: `0x180003ef0`
- end: `0x180003f7a`
- name: `?_CatDBRemoveCatNameFromHashesListOfCatNames@@YAHPEAU_JET_DB_STRUCT@@PEAUJET_DB_HASH_TABLE_IDS@@PEAU_CRYPTOAPI_BLOB@@PEBG@Z`
- size: `138`
- prototype: `__int64 __fastcall(struct _JET_DB_STRUCT *, struct JET_DB_HASH_TABLE_IDS *, struct _CRYPTOAPI_BLOB *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180003570`
- `0x1800038f0`
- `0x180003ef0`
- `0x180003f80`
- `0x18000a59c`
- `0x18000acbc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003f5a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003f5a`

## pseudocode

```c
__int64 __fastcall _CatDBRemoveCatNameFromHashesListOfCatNames(
        struct _JET_DB_STRUCT *a1,
        struct JET_DB_HASH_TABLE_IDS *a2,
        struct _CRYPTOAPI_BLOB *a3,
        const unsigned __int16 *a4)
{
  unsigned int v7; // edi
  int v8; // eax
  int v9; // ebx
  unsigned int v10; // edx
  unsigned __int16 *v11; // rcx
  unsigned int v13; // r8d
  DWORD v14; // eax
  int v15; // [rsp+28h] [rbp-30h]

  v7 = 1;
  v8 = _CatDBSeekInHashCatNameTable(a1, a2, a3);
  v9 = v8;
  if ( v8 != -1601 )
  {
    if ( v8 )
    {
      if ( !(unsigned int)_CatDBJET_errFailure(v8) )
        return v7;
      v14 = _CatDBMapJetError(v9);
      SetLastError(v14);
      v13 = 5223;
    }
    else
    {
      if ( (unsigned int)_CatDBRemoveCatNameFromMultiValuedColumn(a1, *(_QWORD *)a2, *((_DWORD *)a2 + 3), a4) )
        return v7;
      v13 = 5214;
    }
    ErrLog_LogError(v11, v10, v13, 0, 0, v15);
    return 0;
  }
  return v7;
}

```

## disassembly

```asm
0x180003ef0  push    rbx
0x180003ef2  push    rbp
0x180003ef3  push    rsi
0x180003ef4  push    rdi
0x180003ef5  push    r14
0x180003ef7  sub     rsp, 30h
0x180003efb  mov     r14, r9
0x180003efe  mov     rsi, rdx
0x180003f01  mov     rbp, rcx
0x180003f04  mov     edi, 1
0x180003f09  call    ?_CatDBSeekInHashCatNameTable@@YAJPEAU_JET_DB_STRUCT@@PEAUJET_DB_HASH_TABLE_IDS@@PEAU_CRYPTOAPI_BLOB@@@Z; _CatDBSeekInHashCatNameTable(_JET_DB_STRUCT *,JET_DB_HASH_TABLE_IDS *,_CRYPTOAPI_BLOB *)
0x180003f0e  mov     ebx, eax
0x180003f10  cmp     eax, 0FFFFF9BFh
0x180003f15  jz      short loc_180003F31
0x180003f17  test    eax, eax
0x180003f19  jnz     short loc_180003F46
0x180003f1b  mov     r8d, [rsi+0Ch]; unsigned int
0x180003f1f  mov     r9, r14; unsigned __int16 *
0x180003f22  mov     rdx, [rsi]; unsigned __int64
0x180003f25  mov     rcx, rbp; struct _JET_DB_STRUCT *
0x180003f28  call    ?_CatDBRemoveCatNameFromMultiValuedColumn@@YAHPEAU_JET_DB_STRUCT@@_KKPEBG@Z; _CatDBRemoveCatNameFromMultiValuedColumn(_JET_DB_STRUCT *,unsigned __int64,ulong,ushort const *)
0x180003f2d  test    eax, eax
0x180003f2f  jz      short loc_180003F3E
0x180003f31  mov     eax, edi
0x180003f33  add     rsp, 30h
0x180003f37  pop     r14
0x180003f39  pop     rdi
0x180003f3a  pop     rsi
0x180003f3b  pop     rbp
0x180003f3c  pop     rbx
0x180003f3d  retn
0x180003f3e  mov     r8d, 145Eh
0x180003f44  jmp     short loc_180003F66
0x180003f46  mov     ecx, ebx; int
0x180003f48  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x180003f4d  test    eax, eax
0x180003f4f  jz      short loc_180003F31
0x180003f51  mov     ecx, ebx; int
0x180003f53  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x180003f58  mov     ecx, eax; dwErrCode
0x180003f5a  call    cs:__imp_SetLastError
0x180003f60  mov     r8d, 1467h; unsigned int
0x180003f66  xor     r9d, r9d; unsigned int
0x180003f69  mov     [rsp+58h+var_38], 0; int
0x180003f71  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180003f76  xor     edi, edi
0x180003f78  jmp     short loc_180003F31
```
