# _CatDBInitJet

- ea: `0x180019fe0`
- end: `0x18001a228`
- name: `_CatDBInitJet`
- size: `584`
- prototype: ``
- caller_count: `3`
- callee_count: `15`
- tags: ``

## callers

- `0x180002fd0`
- `0x180018620`
- `0x18001aa80`

## callees

- `0x180001264`
- `0x1800038f0`
- `0x18000a57c`
- `0x18000a59c`
- `0x18000acbc`
- `0x18000be40`
- `0x180018620`
- `0x180019a48`
- `0x180019fe0`
- `0x18001a290`
- `0x18001a694`
- `0x18001a89c`
- `0x18001a9d0`
- `0x18001b6d8`
- `0x18001c620`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a14b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a186`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a1b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a14b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a186`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a1b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a1ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a1e5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a1ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001a1e5`
- `ESENT!JetCreateInstanceW` at `0x18001a0a2`
- `ESENT!JetCreateInstanceW` at `0x18001a0a2`
- `ESENT!JetSetSystemParameterW` at `0x18001a01b`
- `ESENT!JetSetSystemParameterW` at `0x18001a061`
- `ESENT!JetSetSystemParameterW` at `0x18001a01b`
- `ESENT!JetSetSystemParameterW` at `0x18001a061`

## pseudocode

```c
__int64 __fastcall CatDBInitJet(int a1, int a2)
{
  unsigned int v3; // ebx
  unsigned int v4; // eax
  unsigned int v5; // edx
  unsigned __int16 *v6; // rcx
  unsigned int v7; // ebx
  unsigned int v8; // eax
  unsigned int v9; // edx
  unsigned __int16 *v10; // rcx
  unsigned int InstanceW; // ebx
  unsigned __int64 *v12; // rcx
  __int64 v13; // rcx
  unsigned int v14; // ebx
  int v15; // ebx
  const wchar_t *v16; // rcx
  unsigned int Error; // ebx
  DWORD v19; // eax
  DWORD v20; // eax
  unsigned int v21; // edx
  unsigned __int16 *v22; // rcx
  unsigned int v23; // r8d
  DWORD v24; // eax
  DWORD LastError; // eax
  DWORD v26; // eax
  int v27; // [rsp+28h] [rbp-30h]
  int v28; // [rsp+30h] [rbp-28h] BYREF
  int v29; // [rsp+38h] [rbp-20h] BYREF

  v29 = a1;
  v28 = 0;
  while ( 1 )
  {
    v3 = JetSetSystemParameterW(0, 0, 0x81u, 0x1Bu, 0);
    if ( (unsigned int)_CatDBJET_errFailure(v3) )
    {
      CatDBLogJetInitError(v3);
      v4 = _CatDBMapJetError(v3);
      ErrLog_LogError(v6, v5, 0x46Du, v4, 0, v27);
    }
    v7 = JetSetSystemParameterW(0, 0, 0x82u, 1u, 0);
    if ( (unsigned int)_CatDBJET_errFailure(v7) )
    {
      CatDBLogJetInitError(v7);
      v8 = _CatDBMapJetError(v7);
      ErrLog_LogError(v10, v9, 0x47Bu, v8, 0, v27);
    }
    InstanceW = JetCreateInstanceW(&g_JetInstance, L"Catalog Database");
    if ( (unsigned int)_CatDBJET_errFailure(InstanceW) )
    {
      g_JetInstance = 0;
      CatDBLogJetInitError(InstanceW);
      v26 = _CatDBMapJetError(InstanceW);
      SetLastError(v26);
      v23 = 1160;
      goto LABEL_28;
    }
    if ( !(unsigned int)_CatDBInitJetDatabaseParams(v12) )
    {
      LastError = GetLastError();
      CatDBLogInitError(LastError);
      v23 = 1169;
      goto LABEL_28;
    }
    g_fHasWriteJetDatabaseParams = 0;
    v14 = CatDBJetInit3W(v13, &v29);
    if ( (unsigned int)_CatDBJET_errFailure(v14) && !a2 && (unsigned int)CatDBIsCleanupJetError(v14) )
    {
      v16 = L"JetInit";
      return CatDBCleanupJet(v16, v14);
    }
    if ( (unsigned int)_CatDBJET_errFailure(v14) )
    {
      CatDBLogJetInitError(v14);
      v24 = _CatDBMapJetError(v14);
      SetLastError(v24);
      v23 = 1193;
      goto LABEL_28;
    }
    v15 = v29;
    if ( !_CatDBSyncAllDBs(v29, &v28) )
      break;
    if ( !v28 || !v15 )
      return 0;
    CatDBTermJet();
    v29 = 0;
  }
  if ( !a2 )
  {
    v19 = GetLastError();
    v14 = 0;
    v28 = 0;
    if ( v19 == 303
      || (unsigned int)_CatDBExtractJetError(v19, &v28) && (v14 = v28, (unsigned int)CatDBIsCleanupJetError(v28)) )
    {
      v16 = L"SyncAllDBs";
      return CatDBCleanupJet(v16, v14);
    }
  }
  v20 = GetLastError();
  CatDBLogInitError(v20);
  v23 = 1224;
LABEL_28:
  ErrLog_LogError(v22, v21, v23, 0, 0, v27);
  Error = _CatDBGetNonzeroLastError();
  CatDBTermJet();
  return Error;
}

```

## disassembly

```asm
0x180019fe0  mov     [rsp+arg_8], rbx
0x180019fe5  mov     [rsp+arg_10], rsi
0x180019fea  push    rdi
0x180019feb  sub     rsp, 50h
0x180019fef  mov     rax, cs:__security_cookie
0x180019ff6  xor     rax, rsp
0x180019ff9  mov     [rsp+58h+var_18], rax
0x180019ffe  xor     esi, esi
0x18001a000  mov     [rsp+58h+var_20], ecx
0x18001a004  mov     [rsp+58h+var_28], esi
0x18001a008  mov     edi, edx
0x18001a00a  xor     edx, edx; sesid
0x18001a00c  mov     [rsp+58h+szParam], rsi; szParam
0x18001a011  xor     ecx, ecx; pinstance
0x18001a013  lea     r9d, [rdx+1Bh]; lParam
0x18001a017  lea     r8d, [r9+66h]; paramid
0x18001a01b  call    cs:__imp_JetSetSystemParameterW
0x18001a021  mov     ecx, eax; int
0x18001a023  mov     ebx, eax
0x18001a025  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x18001a02a  test    eax, eax
0x18001a02c  jz      short loc_18001A04E
0x18001a02e  mov     ecx, ebx
0x18001a030  call    _CatDBLogJetInitError
0x18001a035  mov     ecx, ebx; int
0x18001a037  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x18001a03c  mov     r9d, eax; unsigned int
0x18001a03f  mov     dword ptr [rsp+58h+szParam], esi; int
0x18001a043  mov     r8d, 46Dh; unsigned int
0x18001a049  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18001a04e  xor     edx, edx; sesid
0x18001a050  mov     [rsp+58h+szParam], rsi; szParam
0x18001a055  xor     ecx, ecx; pinstance
0x18001a057  mov     r8d, 82h; paramid
0x18001a05d  lea     r9d, [rdx+1]; lParam
0x18001a061  call    cs:__imp_JetSetSystemParameterW
0x18001a067  mov     ecx, eax; int
0x18001a069  mov     ebx, eax
0x18001a06b  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x18001a070  test    eax, eax
0x18001a072  jz      short loc_18001A094
0x18001a074  mov     ecx, ebx
0x18001a076  call    _CatDBLogJetInitError
0x18001a07b  mov     ecx, ebx; int
0x18001a07d  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x18001a082  mov     r9d, eax; unsigned int
0x18001a085  mov     dword ptr [rsp+58h+szParam], esi; int
0x18001a089  mov     r8d, 47Bh; unsigned int
0x18001a08f  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18001a094  lea     rdx, szInstanceName; "Catalog Database"
0x18001a09b  lea     rcx, ?g_JetInstance@@3_KA; pinstance
0x18001a0a2  call    cs:__imp_JetCreateInstanceW
0x18001a0a8  mov     ecx, eax; int
0x18001a0aa  mov     ebx, eax
0x18001a0ac  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x18001a0b1  test    eax, eax
0x18001a0b3  jnz     loc_18001A1CE
0x18001a0b9  call    ?_CatDBInitJetDatabaseParams@@YAHPEA_K@Z; _CatDBInitJetDatabaseParams(unsigned __int64 *)
0x18001a0be  test    eax, eax
0x18001a0c0  jz      loc_18001A1B9
0x18001a0c6  lea     rdx, [rsp+58h+var_20]
0x18001a0cb  mov     cs:?g_fHasWriteJetDatabaseParams@@3HA, esi; int g_fHasWriteJetDatabaseParams
0x18001a0d1  call    _CatDBJetInit3W
0x18001a0d6  mov     ecx, eax; int
0x18001a0d8  mov     ebx, eax
0x18001a0da  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x18001a0df  test    eax, eax
0x18001a0e1  jz      short loc_18001A0F2
0x18001a0e3  test    edi, edi
0x18001a0e5  jnz     short loc_18001A0F2
0x18001a0e7  mov     ecx, ebx; int
0x18001a0e9  call    _CatDBIsCleanupJetError
0x18001a0ee  test    eax, eax
0x18001a0f0  jnz     short loc_18001A12D
0x18001a0f2  mov     ecx, ebx; int
0x18001a0f4  call    ?_CatDBJET_errFailure@@YAHJ@Z; _CatDBJET_errFailure(long)
0x18001a0f9  test    eax, eax
0x18001a0fb  jnz     loc_18001A19B
0x18001a101  mov     ebx, [rsp+58h+var_20]
0x18001a105  lea     rdx, [rsp+58h+var_28]; int *
0x18001a10a  mov     ecx, ebx; int
0x18001a10c  call    ?_CatDBSyncAllDBs@@YAHHPEAH@Z; _CatDBSyncAllDBs(int,int *)
0x18001a111  test    eax, eax
0x18001a113  jz      short loc_18001A147
0x18001a115  cmp     [rsp+58h+var_28], esi
0x18001a119  jz      short loc_18001A140
0x18001a11b  test    ebx, ebx
0x18001a11d  jz      short loc_18001A140
0x18001a11f  call    _CatDBTermJet
0x18001a124  mov     [rsp+58h+var_20], esi
0x18001a128  jmp     loc_18001A00A
0x18001a12d  lea     rcx, aJetinit_0; "JetInit"
0x18001a134  mov     edx, ebx
0x18001a136  call    _CatDBCleanupJet
0x18001a13b  jmp     loc_18001A20B
0x18001a140  mov     ebx, esi
0x18001a142  jmp     loc_18001A209
0x18001a147  test    edi, edi
0x18001a149  jnz     short loc_18001A186
0x18001a14b  call    cs:__imp_GetLastError
0x18001a151  mov     ebx, esi
0x18001a153  mov     [rsp+58h+var_28], ebx
0x18001a157  cmp     eax, 12Fh
0x18001a15c  jz      short loc_18001A17D
0x18001a15e  lea     rdx, [rsp+58h+var_28]; int *
0x18001a163  mov     ecx, eax; unsigned int
0x18001a165  call    ?_CatDBExtractJetError@@YAHKPEAJ@Z; _CatDBExtractJetError(ulong,long *)
0x18001a16a  test    eax, eax
0x18001a16c  jz      short loc_18001A186
0x18001a16e  mov     ebx, [rsp+58h+var_28]
0x18001a172  mov     ecx, ebx; int
0x18001a174  call    _CatDBIsCleanupJetError
0x18001a179  test    eax, eax
0x18001a17b  jz      short loc_18001A186
0x18001a17d  lea     rcx, aSyncalldbs; "SyncAllDBs"
0x18001a184  jmp     short loc_18001A134
0x18001a186  call    cs:__imp_GetLastError
0x18001a18c  mov     ecx, eax; unsigned int
0x18001a18e  call    _CatDBLogInitError
0x18001a193  mov     r8d, 4C8h
0x18001a199  jmp     short loc_18001A1F1
0x18001a19b  mov     ecx, ebx
0x18001a19d  call    _CatDBLogJetInitError
0x18001a1a2  mov     ecx, ebx; int
0x18001a1a4  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x18001a1a9  mov     ecx, eax; dwErrCode
0x18001a1ab  call    cs:__imp_SetLastError
0x18001a1b1  mov     r8d, 4A9h
0x18001a1b7  jmp     short loc_18001A1F1
0x18001a1b9  call    cs:__imp_GetLastError
0x18001a1bf  mov     ecx, eax; unsigned int
0x18001a1c1  call    _CatDBLogInitError
0x18001a1c6  mov     r8d, 491h
0x18001a1cc  jmp     short loc_18001A1F1
0x18001a1ce  mov     ecx, ebx
0x18001a1d0  mov     cs:?g_JetInstance@@3_KA, rsi; unsigned __int64 g_JetInstance
0x18001a1d7  call    _CatDBLogJetInitError
0x18001a1dc  mov     ecx, ebx; int
0x18001a1de  call    ?_CatDBMapJetError@@YAKJ@Z; _CatDBMapJetError(long)
0x18001a1e3  mov     ecx, eax; dwErrCode
0x18001a1e5  call    cs:__imp_SetLastError
0x18001a1eb  mov     r8d, 488h; unsigned int
0x18001a1f1  xor     r9d, r9d; unsigned int
0x18001a1f4  mov     dword ptr [rsp+58h+szParam], esi; int
0x18001a1f8  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18001a1fd  call    ?_CatDBGetNonzeroLastError@@YAKXZ; _CatDBGetNonzeroLastError(void)
0x18001a202  mov     ebx, eax
0x18001a204  call    _CatDBTermJet
0x18001a209  mov     eax, ebx
0x18001a20b  mov     rcx, [rsp+58h+var_18]
0x18001a210  xor     rcx, rsp; StackCookie
0x18001a213  call    __security_check_cookie
0x18001a218  mov     rbx, [rsp+58h+arg_8]
0x18001a21d  mov     rsi, [rsp+58h+arg_10]
0x18001a222  add     rsp, 50h
0x18001a226  pop     rdi
0x18001a227  retn
```
