# CDRMStore::Delete(ushort const *,ushort const *)

- ea: `0x180035294`
- end: `0x1800355ac`
- name: `?Delete@CDRMStore@@QEAAJPEBG0@Z`
- size: `792`
- prototype: `__int64 __fastcall(const unsigned __int16 **this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x1800356f8`
- `0x180035e48`
- `0x18003631c`

## callees

- `0x180001244`
- `0x180001284`
- `0x180004654`
- `0x180017210`
- `0x180034bb0`
- `0x180035294`
- `0x1800370d8`
- `0x18003721c`
- `0x18005bd72`
- `0x18005bdc0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800353de`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800353de`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18003549f`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18003549f`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180035561`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180035561`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003547b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800354b9`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003547b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800354b9`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800354cf`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800354cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035485`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035593`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035485`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035593`

## pseudocode

```c
__int64 __fastcall CDRMStore::Delete(
        const unsigned __int16 **this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  unsigned __int16 *v5; // r13
  unsigned __int16 *v6; // rdi
  const unsigned __int16 *v7; // r9
  __int64 FirstFileW; // r12
  int FilePathString; // ebx
  __int64 v10; // rax
  __int64 v11; // rcx
  unsigned __int64 v12; // r15
  unsigned __int16 *v13; // rax
  __int64 v14; // rax
  __int64 v15; // rcx
  unsigned __int64 v16; // r14
  size_t v17; // rax
  WCHAR *cFileName; // rcx
  WCHAR *v19; // rcx
  WCHAR *v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rax
  unsigned __int16 *v23; // rax
  signed int LastError; // eax
  unsigned __int16 v26; // [rsp+28h] [rbp-E0h]
  __int64 v27; // [rsp+38h] [rbp-D0h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+40h] [rbp-C8h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+58h] [rbp-B0h] BYREF

  lpFileName[1] = (LPCWSTR)-2LL;
  lpFileName[0] = 0;
  v5 = 0;
  v6 = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = -1;
  if ( a2 )
  {
    FilePathString = 0;
    if ( *((_DWORD *)this + 1) )
    {
      FilePathString = CDRMStore::MakeFilePathString(
                         (CDRMStore *)this,
                         this[2],
                         a2,
                         v7,
                         v26,
                         (unsigned __int16 **)lpFileName);
      if ( FilePathString >= 0 )
      {
        v10 = -1;
        do
          ++v10;
        while ( a2[v10] );
        v11 = -1;
        do
          ++v11;
        while ( this[2][v11] );
        v12 = v11 + v10 + 1;
        v13 = (unsigned __int16 *)operator new(saturated_mul(v12, 2u));
        v5 = v13;
        if ( v13 )
        {
          FilePathString = StringCchCopyW(v13, v12, this[2]);
          if ( FilePathString >= 0 )
          {
            FilePathString = StringCchCatW(v5, v12, a2);
            if ( FilePathString >= 0 )
            {
              v27 = 0;
              if ( CDRMCLock::Lock((CDRMCLock *)&v27, v5) >= 0 )
              {
                FirstFileW = (__int64)FindFirstFileW(lpFileName[0], &FindFileData);
                if ( FirstFileW == -1 )
                {
                  FilePathString = -2147168454;
                }
                else
                {
                  operator delete(0);
                  v14 = -1;
                  do
                    ++v14;
                  while ( FindFileData.cFileName[v14] );
                  v15 = -1;
                  do
                    ++v15;
                  while ( this[2][v15] );
                  v16 = v14 + v15 + 1;
                  v17 = 2 * v16;
                  if ( !is_mul_ok(v16, 2u) )
                    v17 = -1;
                  while ( 1 )
                  {
                    v23 = (unsigned __int16 *)operator new(v17);
                    v6 = v23;
                    if ( !v23 )
                    {
                      FilePathString = -2147024882;
                      goto LABEL_43;
                    }
                    FilePathString = StringCchCopyW(v23, v16, this[2]);
                    if ( FilePathString < 0 )
                      goto LABEL_43;
                    FilePathString = StringCchCatW(v6, v16, FindFileData.cFileName);
                    if ( FilePathString < 0 )
                      goto LABEL_43;
                    cFileName = FindFileData.cFileName;
                    if ( v6 )
                      cFileName = v6;
                    if ( !DeleteFileW(cFileName) && GetLastError() == 5 )
                    {
                      v19 = FindFileData.cFileName;
                      if ( v6 )
                        v19 = v6;
                      if ( !SetFileAttributesW(v19, 0x80u) )
                        break;
                      v20 = FindFileData.cFileName;
                      if ( v6 )
                        v20 = v6;
                      if ( !DeleteFileW(v20) )
                        break;
                    }
                    if ( !FindNextFileW((HANDLE)FirstFileW, &FindFileData) )
                      goto LABEL_43;
                    operator delete(v6);
                    v21 = -1;
                    do
                      ++v21;
                    while ( FindFileData.cFileName[v21] );
                    v22 = -1;
                    do
                      ++v22;
                    while ( this[2][v22] );
                    v16 = v21 + v22 + 1;
                    v17 = saturated_mul(v16, 2u);
                  }
                  LastError = GetLastError();
                  FilePathString = LastError;
                  if ( LastError > 0 )
                    FilePathString = (unsigned __int16)LastError | 0x80070000;
                }
              }
LABEL_43:
              CDRMCLock::~CDRMCLock((CDRMCLock *)&v27);
            }
          }
        }
        else
        {
          FilePathString = -2147024882;
        }
      }
    }
  }
  else
  {
    FilePathString = -2147024809;
  }
  operator delete((void *)lpFileName[0]);
  operator delete(v5);
  operator delete(v6);
  if ( FirstFileW != -1 )
    FindClose((HANDLE)FirstFileW);
  return (unsigned int)FilePathString;
}

```

## disassembly

```asm
0x180035294  mov     rax, rsp
0x180035297  push    rbp
0x180035298  push    rsi
0x180035299  push    rdi
0x18003529a  push    r12
0x18003529c  push    r13
0x18003529e  push    r14
0x1800352a0  push    r15
0x1800352a2  lea     rbp, [rax-1E8h]
0x1800352a9  sub     rsp, 2B0h
0x1800352b0  mov     [rsp+2E0h+lpFileName+8], 0FFFFFFFFFFFFFFFEh
0x1800352b9  mov     [rax+18h], rbx
0x1800352bd  mov     rax, cs:__security_cookie
0x1800352c4  xor     rax, rsp
0x1800352c7  mov     [rbp+1E0h+var_40], rax
0x1800352ce  mov     r14, rdx
0x1800352d1  mov     rsi, rcx
0x1800352d4  xor     r15d, r15d
0x1800352d7  mov     [rsp+2E0h+lpFileName], r15
0x1800352dc  mov     r13d, r15d
0x1800352df  mov     edi, r15d
0x1800352e2  xor     edx, edx; Val
0x1800352e4  mov     r8d, 250h; Size
0x1800352ea  lea     rcx, [rsp+2E0h+FindFileData]; void *
0x1800352ef  call    memset_0
0x1800352f4  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800352f8  test    r14, r14
0x1800352fb  jnz     short loc_180035307
0x1800352fd  mov     ebx, 80070057h
0x180035302  jmp     loc_18003553E
0x180035307  mov     ebx, r15d
0x18003530a  cmp     [rsi+4], r15d
0x18003530e  jz      loc_18003553E
0x180035314  lea     rax, [rsp+2E0h+lpFileName]
0x180035319  mov     [rsp+2E0h+var_2B8], rax; unsigned __int16 **
0x18003531e  mov     r8, r14; unsigned __int16 *
0x180035321  mov     rdx, [rsi+10h]; unsigned __int16 *
0x180035325  mov     rcx, rsi; this
0x180035328  call    ?MakeFilePathString@CDRMStore@@AEAAJPEBG00GPEAPEAG@Z; CDRMStore::MakeFilePathString(ushort const *,ushort const *,ushort const *,ushort,ushort * *)
0x18003532d  mov     ebx, eax
0x18003532f  test    eax, eax
0x180035331  js      loc_18003553E
0x180035337  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003533b  mov     rax, r8
0x18003533e  inc     rax
0x180035341  cmp     [r14+rax*2], r15w
0x180035346  jnz     short loc_18003533E
0x180035348  mov     rdx, [rsi+10h]
0x18003534c  mov     rcx, r8
0x18003534f  inc     rcx
0x180035352  cmp     [rdx+rcx*2], r15w
0x180035357  jnz     short loc_18003534F
0x180035359  lea     r15, [rax+1]
0x18003535d  add     r15, rcx
0x180035360  mov     eax, 2
0x180035365  mul     r15
0x180035368  cmovb   rax, r8
0x18003536c  mov     rcx, rax; Size
0x18003536f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180035374  mov     r13, rax
0x180035377  test    rax, rax
0x18003537a  jnz     short loc_180035386
0x18003537c  mov     ebx, 8007000Eh
0x180035381  jmp     loc_18003553E
0x180035386  mov     r8, [rsi+10h]; unsigned __int16 *
0x18003538a  mov     rdx, r15; unsigned __int64
0x18003538d  mov     rcx, r13; unsigned __int16 *
0x180035390  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180035395  mov     ebx, eax
0x180035397  test    eax, eax
0x180035399  js      loc_18003553E
0x18003539f  mov     r8, r14; unsigned __int16 *
0x1800353a2  mov     rdx, r15; unsigned __int64
0x1800353a5  mov     rcx, r13; unsigned __int16 *
0x1800353a8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800353ad  mov     ebx, eax
0x1800353af  xor     r15d, r15d
0x1800353b2  test    eax, eax
0x1800353b4  js      loc_18003553E
0x1800353ba  mov     [rsp+2E0h+var_2B0], r15
0x1800353bf  mov     rdx, r13; unsigned __int16 *
0x1800353c2  lea     rcx, [rsp+2E0h+var_2B0]; this
0x1800353c7  call    ?Lock@CDRMCLock@@QEAAJPEAG@Z; CDRMCLock::Lock(ushort *)
0x1800353cc  test    eax, eax
0x1800353ce  js      loc_180035534
0x1800353d4  lea     rdx, [rsp+2E0h+FindFileData]; lpFindFileData
0x1800353d9  mov     rcx, [rsp+2E0h+lpFileName]; lpFileName
0x1800353de  call    cs:__imp_FindFirstFileW
0x1800353e4  mov     r12, rax
0x1800353e7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800353eb  cmp     rax, rbx
0x1800353ee  jnz     short loc_1800353FA
0x1800353f0  mov     ebx, 8004CF3Ah
0x1800353f5  jmp     loc_180035534
0x1800353fa  xor     ecx, ecx; Block
0x1800353fc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180035401  lea     rcx, [rsp+2E0h+FindFileData.cFileName]
0x180035406  mov     rax, rbx
0x180035409  inc     rax
0x18003540c  cmp     [rcx+rax*2], r15w
0x180035411  jnz     short loc_180035409
0x180035413  mov     rdx, [rsi+10h]
0x180035417  mov     rcx, rbx
0x18003541a  inc     rcx
0x18003541d  cmp     [rdx+rcx*2], r15w
0x180035422  jnz     short loc_18003541A
0x180035424  lea     r14, [rcx+1]
0x180035428  add     r14, rax
0x18003542b  mov     eax, 2
0x180035430  mul     r14
0x180035433  cmovb   rax, rbx
0x180035437  jmp     loc_18003551B
0x18003543c  mov     r8, [rsi+10h]; unsigned __int16 *
0x180035440  mov     rdx, r14; unsigned __int64
0x180035443  mov     rcx, rdi; unsigned __int16 *
0x180035446  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003544b  mov     ebx, eax
0x18003544d  test    eax, eax
0x18003544f  js      loc_180035534
0x180035455  lea     r8, [rsp+2E0h+FindFileData.cFileName]; unsigned __int16 *
0x18003545a  mov     rdx, r14; unsigned __int64
0x18003545d  mov     rcx, rdi; unsigned __int16 *
0x180035460  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180035465  mov     ebx, eax
0x180035467  test    eax, eax
0x180035469  js      loc_180035534
0x18003546f  lea     rcx, [rsp+2E0h+FindFileData.cFileName]
0x180035474  test    rdi, rdi
0x180035477  cmovnz  rcx, rdi; lpFileName
0x18003547b  call    cs:__imp_DeleteFileW
0x180035481  test    eax, eax
0x180035483  jnz     short loc_1800354C7
0x180035485  call    cs:__imp_GetLastError
0x18003548b  cmp     eax, 5
0x18003548e  jnz     short loc_1800354C7
0x180035490  lea     rcx, [rsp+2E0h+FindFileData.cFileName]
0x180035495  test    rdi, rdi
0x180035498  cmovnz  rcx, rdi; lpFileName
0x18003549c  lea     edx, [rax+7Bh]; dwFileAttributes
0x18003549f  call    cs:__imp_SetFileAttributesW
0x1800354a5  test    eax, eax
0x1800354a7  jz      loc_180035593
0x1800354ad  lea     rcx, [rsp+2E0h+FindFileData.cFileName]
0x1800354b2  test    rdi, rdi
0x1800354b5  cmovnz  rcx, rdi; lpFileName
0x1800354b9  call    cs:__imp_DeleteFileW
0x1800354bf  test    eax, eax
0x1800354c1  jz      loc_180035593
0x1800354c7  lea     rdx, [rsp+2E0h+FindFileData]; lpFindFileData
0x1800354cc  mov     rcx, r12; hFindFile
0x1800354cf  call    cs:__imp_FindNextFileW
0x1800354d5  test    eax, eax
0x1800354d7  jz      short loc_180035534
0x1800354d9  mov     rcx, rdi; Block
0x1800354dc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800354e1  lea     rax, [rsp+2E0h+FindFileData.cFileName]
0x1800354e6  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800354ea  mov     rcx, r8
0x1800354ed  inc     rcx
0x1800354f0  cmp     [rax+rcx*2], r15w
0x1800354f5  jnz     short loc_1800354ED
0x1800354f7  mov     rdx, [rsi+10h]
0x1800354fb  mov     rax, r8
0x1800354fe  inc     rax
0x180035501  cmp     [rdx+rax*2], r15w
0x180035506  jnz     short loc_1800354FE
0x180035508  lea     r14, [rax+1]
0x18003550c  add     r14, rcx
0x18003550f  mov     eax, 2
0x180035514  mul     r14
0x180035517  cmovb   rax, r8
0x18003551b  mov     rcx, rax; Size
0x18003551e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180035523  test    rax, rax
0x180035526  mov     rdi, rax
0x180035529  jnz     loc_18003543C
0x18003552f  mov     ebx, 8007000Eh
0x180035534  lea     rcx, [rsp+2E0h+var_2B0]; this
0x180035539  call    ??1CDRMCLock@@QEAA@XZ; CDRMCLock::~CDRMCLock(void)
0x18003553e  mov     rcx, [rsp+2E0h+lpFileName]; Block
0x180035543  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180035548  mov     rcx, r13; Block
0x18003554b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180035550  mov     rcx, rdi; Block
0x180035553  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180035558  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x18003555c  jz      short loc_180035567
0x18003555e  mov     rcx, r12; hFindFile
0x180035561  call    cs:__imp_FindClose
0x180035567  mov     eax, ebx
0x180035569  mov     rcx, [rbp+1E0h+var_40]
0x180035570  xor     rcx, rsp; StackCookie
0x180035573  call    __security_check_cookie
0x180035578  mov     rbx, [rsp+2E0h+arg_10]
0x180035580  add     rsp, 2B0h
0x180035587  pop     r15
0x180035589  pop     r14
0x18003558b  pop     r13
0x18003558d  pop     r12
0x18003558f  pop     rdi
0x180035590  pop     rsi
0x180035591  pop     rbp
0x180035592  retn
0x180035593  call    cs:__imp_GetLastError
0x180035599  nop
0x18003559a  mov     ebx, eax
0x18003559c  test    eax, eax
0x18003559e  jle     short loc_180035534
0x1800355a0  movzx   ebx, ax
0x1800355a3  or      ebx, 80070000h
0x1800355a9  jmp     short loc_180035534
```
