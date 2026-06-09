# CSystemWriter::AddCatalogFiles(IVssCreateWriterMetadata *,bool)

- ea: `0x180004824`
- end: `0x180004a1a`
- name: `?AddCatalogFiles@CSystemWriter@@AEAA_NPEAVIVssCreateWriterMetadata@@_N@Z`
- size: `502`
- prototype: `bool __fastcall(CSystemWriter *__hidden this, struct IVssCreateWriterMetadata *, bool)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18001e890`

## callees

- `0x1800015b0`
- `0x180003d48`
- `0x180004824`
- `0x180004a20`
- `0x18000be40`
- `0x18000c7e8`
- `0x18001ea5c`
- `0x18001ee6c`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800048d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000493d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000494c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800048d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000493d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000494c`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800048a6`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800048a6`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800048cc`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800048cc`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800048e4`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800048e4`

## pseudocode

```c
char __fastcall CSystemWriter::AddCatalogFiles(
        CSystemWriter *this,
        struct IVssCreateWriterMetadata *a2,
        unsigned __int8 a3)
{
  int v3; // ebx
  __int64 FirstFileW; // rdi
  const unsigned __int16 *v7; // rax
  unsigned __int16 *v8; // rbp
  const WCHAR *v9; // rax
  WCHAR *v10; // rsi
  char v11; // r14
  DWORD v13; // eax
  int v14; // eax
  DWORD LastError; // eax
  unsigned __int16 *v16; // rax
  unsigned __int16 *v17; // r15
  int v18; // ebx
  int v19; // [rsp+28h] [rbp-2C0h]
  _WIN32_FIND_DATAW FindFileData; // [rsp+50h] [rbp-298h] BYREF

  v3 = a3;
  FirstFileW = -1;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v7 = _CatDBGetCatrootDirW(v3);
  v8 = (unsigned __int16 *)v7;
  if ( !v7 )
  {
    v10 = 0;
    goto LABEL_15;
  }
  v9 = _CATDBConstructWSTRPath(v7, L"{????????????????????????????????????}");
  v10 = (WCHAR *)v9;
  if ( !v9 )
    goto LABEL_15;
  v11 = 1;
  FirstFileW = (__int64)FindFirstFileW(v9, &FindFileData);
  if ( FirstFileW != -1 )
  {
    do
    {
      if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
      {
        v16 = _CATDBConstructWSTRPath(v8, FindFileData.cFileName);
        v17 = v16;
        if ( !v16 )
          goto LABEL_15;
        LOBYTE(v19) = 1;
        v18 = (*(__int64 (__fastcall **)(struct IVssCreateWriterMetadata *, _QWORD, const wchar_t *, unsigned __int16 *, const wchar_t *, int, _QWORD, int))(*(_QWORD *)a2 + 40LL))(
                a2,
                0,
                L"System Files",
                v16,
                L"*",
                v19,
                0,
                3855);
        _CatDBFree(v17);
        if ( v18 )
        {
          if ( v18 == -2147024892
            || v18 == -2147024888
            || v18 == -2147024882
            || v18 == -2147024784
            || v18 == -2147023738 )
          {
            v14 = -2147212303;
          }
          else
          {
            v14 = -2147212300;
          }
          goto LABEL_12;
        }
      }
    }
    while ( FindNextFileW((HANDLE)FirstFileW, &FindFileData) );
    if ( GetLastError() != 18 )
      goto LABEL_15;
    goto LABEL_7;
  }
  LastError = GetLastError();
  if ( ((LastError - 2) & 0xFFFFFFEE) != 0 || LastError == 19 )
  {
LABEL_15:
    v13 = GetLastError();
    v14 = CSystemWriter::WinErrorToWriterError(v13);
LABEL_12:
    CVssWriter::SetWriterFailure(this, v14);
    v11 = 0;
    if ( FirstFileW == -1 )
    {
LABEL_8:
      if ( !v8 )
        goto LABEL_9;
      goto LABEL_18;
    }
LABEL_7:
    FindClose((HANDLE)FirstFileW);
    goto LABEL_8;
  }
LABEL_18:
  _CatDBFree(v8);
LABEL_9:
  if ( v10 )
    _CatDBFree(v10);
  return v11;
}

```

## disassembly

```asm
0x180004824  mov     [rsp+arg_18], rbx
0x180004829  push    rbp
0x18000482a  push    rsi
0x18000482b  push    rdi
0x18000482c  push    r12
0x18000482e  push    r13
0x180004830  push    r14
0x180004832  push    r15
0x180004834  sub     rsp, 2B0h
0x18000483b  mov     rax, cs:__security_cookie
0x180004842  xor     rax, rsp
0x180004845  mov     [rsp+2E8h+var_48], rax
0x18000484d  movzx   ebx, r8b
0x180004851  mov     r12, rdx
0x180004854  mov     r13, rcx
0x180004857  xor     edx, edx; Val
0x180004859  mov     r8d, 250h; Size
0x18000485f  lea     rcx, [rsp+2E8h+FindFileData]; void *
0x180004864  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180004868  call    memset_0
0x18000486d  mov     ecx, ebx; int
0x18000486f  call    ?_CatDBGetCatrootDirW@@YAPEAGH@Z; _CatDBGetCatrootDirW(int)
0x180004874  mov     rbp, rax
0x180004877  test    rax, rax
0x18000487a  jz      loc_18000493B
0x180004880  lea     rdx, asc_180024D90; "{????????????????????????????????????}"
0x180004887  mov     rcx, rax; unsigned __int16 *
0x18000488a  call    ?_CATDBConstructWSTRPath@@YAPEAGPEBG0@Z; _CATDBConstructWSTRPath(ushort const *,ushort const *)
0x18000488f  mov     rsi, rax
0x180004892  test    rax, rax
0x180004895  jz      loc_18000493D
0x18000489b  lea     rdx, [rsp+2E8h+FindFileData]; lpFindFileData
0x1800048a0  mov     rcx, rax; lpFileName
0x1800048a3  mov     r14b, 1
0x1800048a6  call    cs:__imp_FindFirstFileW
0x1800048ac  mov     rdi, rax
0x1800048af  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800048b3  jz      loc_18000494C
0x1800048b9  test    byte ptr [rsp+2E8h+FindFileData.dwFileAttributes], 10h
0x1800048be  jnz     loc_18000496C
0x1800048c4  lea     rdx, [rsp+2E8h+FindFileData]; lpFindFileData
0x1800048c9  mov     rcx, rdi; hFindFile
0x1800048cc  call    cs:__imp_FindNextFileW
0x1800048d2  test    eax, eax
0x1800048d4  jnz     short loc_1800048B9
0x1800048d6  call    cs:__imp_GetLastError
0x1800048dc  cmp     eax, 12h
0x1800048df  jnz     short loc_18000493D
0x1800048e1  mov     rcx, rdi; hFindFile
0x1800048e4  call    cs:__imp_FindClose
0x1800048ea  test    rbp, rbp
0x1800048ed  jnz     short loc_180004962
0x1800048ef  test    rsi, rsi
0x1800048f2  jnz     loc_180004A0D
0x1800048f8  mov     al, r14b
0x1800048fb  mov     rcx, [rsp+2E8h+var_48]
0x180004903  xor     rcx, rsp; StackCookie
0x180004906  call    __security_check_cookie
0x18000490b  mov     rbx, [rsp+2E8h+arg_18]
0x180004913  add     rsp, 2B0h
0x18000491a  pop     r15
0x18000491c  pop     r14
0x18000491e  pop     r13
0x180004920  pop     r12
0x180004922  pop     rdi
0x180004923  pop     rsi
0x180004924  pop     rbp
0x180004925  retn
0x180004926  mov     edx, eax; int
0x180004928  mov     rcx, r13; this
0x18000492b  call    ?SetWriterFailure@CVssWriter@@IEAAJJ@Z; CVssWriter::SetWriterFailure(long)
0x180004930  xor     r14b, r14b
0x180004933  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180004937  jnz     short loc_1800048E1
0x180004939  jmp     short loc_1800048EA
0x18000493b  xor     esi, esi
0x18000493d  call    cs:__imp_GetLastError
0x180004943  mov     ecx, eax; unsigned int
0x180004945  call    ?WinErrorToWriterError@CSystemWriter@@CAJK@Z; CSystemWriter::WinErrorToWriterError(ulong)
0x18000494a  jmp     short loc_180004926
0x18000494c  call    cs:__imp_GetLastError
0x180004952  lea     ecx, [rax-2]
0x180004955  test    ecx, 0FFFFFFEEh
0x18000495b  jnz     short loc_18000493D
0x18000495d  cmp     eax, 13h
0x180004960  jz      short loc_18000493D
0x180004962  mov     rcx, rbp; void *
0x180004965  call    ?_CatDBFree@@YAXPEAX@Z; _CatDBFree(void *)
0x18000496a  jmp     short loc_1800048EF
0x18000496c  lea     rdx, [rsp+2E8h+FindFileData.cFileName]; unsigned __int16 *
0x180004971  mov     rcx, rbp; unsigned __int16 *
0x180004974  call    ?_CATDBConstructWSTRPath@@YAPEAGPEBG0@Z; _CATDBConstructWSTRPath(ushort const *,ushort const *)
0x180004979  mov     r15, rax
0x18000497c  test    rax, rax
0x18000497f  jz      short loc_18000493D
0x180004981  mov     rcx, [r12]
0x180004985  lea     r8, aSystemFiles; "System Files"
0x18000498c  mov     [rsp+2E8h+var_2B0], 0F0Fh
0x180004994  mov     r9, r15
0x180004997  mov     [rsp+2E8h+var_2B8], 0
0x1800049a0  xor     edx, edx
0x1800049a2  mov     [rsp+2E8h+var_2C0], r14b
0x1800049a7  mov     rax, [rcx+28h]
0x1800049ab  lea     rcx, asc_180026F2C; "*"
0x1800049b2  mov     [rsp+2E8h+var_2C8], rcx
0x1800049b7  mov     rcx, r12
0x1800049ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049bf  mov     rcx, r15; void *
0x1800049c2  mov     ebx, eax
0x1800049c4  call    ?_CatDBFree@@YAXPEAX@Z; _CatDBFree(void *)
0x1800049c9  test    ebx, ebx
0x1800049cb  jz      loc_1800048C4
0x1800049d1  cmp     ebx, 80070004h
0x1800049d7  jz      short loc_180004A03
0x1800049d9  cmp     ebx, 80070008h
0x1800049df  jz      short loc_180004A03
0x1800049e1  cmp     ebx, 8007000Eh
0x1800049e7  jz      short loc_180004A03
0x1800049e9  cmp     ebx, 80070070h
0x1800049ef  jz      short loc_180004A03
0x1800049f1  cmp     ebx, 80070486h
0x1800049f7  jz      short loc_180004A03
0x1800049f9  mov     eax, 800423F4h
0x1800049fe  jmp     loc_180004926
0x180004a03  mov     eax, 800423F1h
0x180004a08  jmp     loc_180004926
0x180004a0d  mov     rcx, rsi; void *
0x180004a10  call    ?_CatDBFree@@YAXPEAX@Z; _CatDBFree(void *)
0x180004a15  jmp     loc_1800048F8
```
