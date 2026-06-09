# _CatDBAttachAndOpenDatabase(_JET_DB_STRUCT *,int,__MIDL_ICatDBSvc_0002)

- ea: `0x180001328`
- end: `0x18000147a`
- name: `?_CatDBAttachAndOpenDatabase@@YAHPEAU_JET_DB_STRUCT@@HW4__MIDL_ICatDBSvc_0002@@@Z`
- size: `338`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180002410`

## callees

- `0x180001328`
- `0x1800038f0`
- `0x1800042b0`
- `0x18000a59c`
- `0x18000acbc`
- `0x1800188dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001386`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000143e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001386`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000143e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800013a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800013e8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001422`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001463`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800013a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800013e8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001422`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001463`
- `ESENT!JetCloseDatabase` at `0x180001454`
- `ESENT!JetCloseDatabase` at `0x180001454`
- `ESENT!JetAttachDatabaseW` at `0x180001352`
- `ESENT!JetAttachDatabaseW` at `0x180001352`
- `ESENT!JetOpenDatabaseW` at `0x1800013cc`
- `ESENT!JetOpenDatabaseW` at `0x1800013cc`

## pseudocode

```c
__int64 __fastcall _CatDBAttachAndOpenDatabase(__int64 a1, int a2, unsigned int a3)
{
  unsigned int v6; // edi
  JET_GRBIT grbit; // r14d
  JET_ERR v8; // eax
  int v9; // esi
  unsigned int v10; // edx
  unsigned __int16 *v11; // rcx
  DWORD LastError; // esi
  DWORD v13; // eax
  unsigned int v14; // edx
  unsigned __int16 *v15; // rcx
  JET_ERR v16; // esi
  DWORD v17; // eax
  unsigned int v18; // edx
  unsigned __int16 *v19; // rcx
  int v20; // esi
  DWORD v21; // eax
  unsigned int v22; // edx
  unsigned __int16 *v23; // rcx
  int v25; // [rsp+28h] [rbp-40h]

  v6 = 0;
  grbit = a2 != 0;
  v8 = JetAttachDatabaseW(*(_QWORD *)(a1 + 8), *(JET_PCWSTR *)a1, grbit);
  v9 = v8;
  if ( v8 != -1811 || a2 )
  {
    if ( (unsigned int)_CatDBJET_errFailure(v8) )
    {
      v13 = _CatDBMapJetError(v9);
      SetLastError(v13);
      ErrLog_LogError(v15, v14, 0x1A68u, 0, 0, v25);
      goto LABEL_11;
    }
  }
  else if ( !(unsigned int)_CatDBCreateDBFile((struct _JET_DB_STRUCT *)a1, *(LPCWSTR *)a1) )
  {
    ErrLog_LogError(v11, v10, 0x1A62u, 0, 0, v25);
    LastError = GetLastError();
LABEL_13:
    SetLastError(LastError);
    return 0;
  }
  v16 = JetOpenDatabaseW(*(_QWORD *)(a1 + 8), *(JET_PCWSTR *)a1, 0, (JET_DBID *)(a1 + 16), grbit);
  if ( (unsigned int)_CatDBJET_errFailure(v16) )
  {
    v17 = _CatDBMapJetError(v16);
    SetLastError(v17);
    ErrLog_LogError(v19, v18, 0x1A73u, 0, 0, v25);
    goto LABEL_11;
  }
  v6 = 1;
  v20 = _CatDBOpenTables(a1, a2, a3);
  if ( (unsigned int)_CatDBJET_errFailure(v20) )
  {
    v21 = _CatDBMapJetError(v20);
    SetLastError(v21);
    ErrLog_LogError(v23, v22, 0x1A7Cu, 0, 0, v25);
LABEL_11:
    LastError = GetLastError();
    if ( v6 )
    {
      JetCloseDatabase(*(_QWORD *)(a1 + 8), *(_DWORD *)(a1 + 16), 0);
      *(_DWORD *)(a1 + 16) = 0;
    }
    goto LABEL_13;
  }
  return v6;
}

```

## disassembly

```asm
0x180001328  push    rbx
0x18000132a  push    rbp
0x18000132b  push    rsi
0x18000132c  push    rdi
0x18000132d  push    r14
0x18000132f  push    r15
0x180001331  sub     rsp, 38h
0x180001335  xor     r14d, r14d
0x180001338  mov     ebp, edx
0x18000133a  mov     r15d, r8d
0x18000133d  mov     rbx, rcx
0x180001340  xor     edi, edi
0x180001342  test    edx, edx
0x180001344  mov     rdx, [rcx]; szFilename
0x180001347  mov     rcx, [rcx+8]; sesid
0x18000134b  setnz   r14b
0x18000134f  mov     r8d, r14d; grbit
0x180001352  call    cs:__imp_JetAttachDatabaseW
0x180001358  mov     esi, eax
0x18000135a  cmp     eax, 0FFFFF8EDh
0x18000135f  jnz     short loc_180001393
0x180001361  test    ebp, ebp
0x180001363  jnz     short loc_180001393
0x180001365  mov     rdx, [rbx]; lpFileName
0x180001368  mov     rcx, rbx; struct _JET_DB_STRUCT *
0x18000136b  call    ?_CatDBCreateDBFile@@YAHPEAU_JET_DB_STRUCT@@PEBG@Z; _CatDBCreateDBFile(_JET_DB_STRUCT *,ushort const *)
0x180001370  test    eax, eax
0x180001372  jnz     short loc_1800013B9
0x180001374  xor     r9d, r9d; unsigned int
0x180001377  mov     [rsp+68h+grbit], edi; int
0x18000137b  mov     r8d, 1A62h; unsigned int
0x180001381  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x180001386  call    cs:__imp_GetLastError
0x18000138c  mov     esi, eax
0x18000138e  jmp     loc_180001461
0x180001393  mov     ecx, esi; int
0x180001395  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x18000139a  test    eax, eax
0x18000139c  jz      short loc_1800013B9
0x18000139e  mov     ecx, esi; int
0x1800013a0  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x1800013a5  mov     ecx, eax; dwErrCode
0x1800013a7  call    cs:__imp_SetLastError
0x1800013ad  mov     r8d, 1A68h
0x1800013b3  mov     [rsp+68h+grbit], edi
0x1800013b7  jmp     short loc_180001436
0x1800013b9  mov     rdx, [rbx]; szFilename
0x1800013bc  lea     r9, [rbx+10h]; pdbid
0x1800013c0  mov     rcx, [rbx+8]; sesid
0x1800013c4  xor     r8d, r8d; szConnect
0x1800013c7  mov     [rsp+68h+grbit], r14d; grbit
0x1800013cc  call    cs:__imp_JetOpenDatabaseW
0x1800013d2  mov     ecx, eax; int
0x1800013d4  mov     esi, eax
0x1800013d6  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x1800013db  test    eax, eax
0x1800013dd  jz      short loc_1800013FA
0x1800013df  mov     ecx, esi; int
0x1800013e1  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x1800013e6  mov     ecx, eax; dwErrCode
0x1800013e8  call    cs:__imp_SetLastError
0x1800013ee  mov     r8d, 1A73h
0x1800013f4  mov     [rsp+68h+grbit], edi
0x1800013f8  jmp     short loc_180001436
0x1800013fa  mov     r8d, r15d
0x1800013fd  mov     edx, ebp
0x1800013ff  mov     rcx, rbx
0x180001402  mov     edi, 1
0x180001407  call    ?_CatDBOpenTables@@YAJPEAU_JET_DB_STRUCT@@HW4__MIDL_ICatDBSvc_0002@@@Z; _CatDBOpenTables(_JET_DB_STRUCT *,int,__MIDL_ICatDBSvc_0002)
0x18000140c  mov     ecx, eax; int
0x18000140e  mov     esi, eax
0x180001410  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x180001415  test    eax, eax
0x180001417  jz      short loc_18000146B
0x180001419  mov     ecx, esi; int
0x18000141b  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x180001420  mov     ecx, eax; dwErrCode
0x180001422  call    cs:__imp_SetLastError
0x180001428  mov     r8d, 1A7Ch; unsigned int
0x18000142e  mov     [rsp+68h+grbit], 0; int
0x180001436  xor     r9d, r9d; unsigned int
0x180001439  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18000143e  call    cs:__imp_GetLastError
0x180001444  mov     esi, eax
0x180001446  test    edi, edi
0x180001448  jz      short loc_180001461
0x18000144a  mov     edx, [rbx+10h]; dbid
0x18000144d  xor     r8d, r8d; grbit
0x180001450  mov     rcx, [rbx+8]; sesid
0x180001454  call    cs:__imp_JetCloseDatabase
0x18000145a  mov     dword ptr [rbx+10h], 0
0x180001461  mov     ecx, esi; dwErrCode
0x180001463  call    cs:__imp_SetLastError
0x180001469  xor     edi, edi
0x18000146b  mov     eax, edi
0x18000146d  add     rsp, 38h
0x180001471  pop     r15
0x180001473  pop     r14
0x180001475  pop     rdi
0x180001476  pop     rsi
0x180001477  pop     rbp
0x180001478  pop     rbx
0x180001479  retn
```
