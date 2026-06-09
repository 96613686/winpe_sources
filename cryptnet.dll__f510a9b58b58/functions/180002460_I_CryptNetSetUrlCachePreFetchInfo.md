# I_CryptNetSetUrlCachePreFetchInfo

- ea: `0x180002460`
- end: `0x18000280a`
- name: `I_CryptNetSetUrlCachePreFetchInfo`
- size: `938`
- prototype: `__int64 __fastcall(__int64, const FILETIME *, unsigned __int16 *, _DWORD *, void *)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18000ca20`
- `0x18000cfa0`

## callees

- `0x18000195c`
- `0x180002460`
- `0x180002810`
- `0x180002a90`
- `0x180002c40`
- `0x180002ca8`
- `0x180003e7c`
- `0x180005900`
- `0x1800063b0`
- `0x1800077b0`
- `0x18000a990`
- `0x1800265b0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800027ba`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800027ba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800025b5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002664`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800025b5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002664`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000263f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000263f`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800026c9`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18000273b`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800026c9`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18000273b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180002630`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180002630`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180002553`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000257c`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180002553`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000257c`

## pseudocode

```c
__int64 __fastcall I_CryptNetSetUrlCachePreFetchInfo(
        __int64 a1,
        const FILETIME *a2,
        unsigned __int16 *a3,
        _DWORD *a4,
        void *a5)
{
  unsigned __int16 *v5; // r13
  bool v7; // zf
  HANDLE FileW; // rdi
  __int64 v10; // rbx
  BOOL v11; // r14d
  unsigned int v12; // esi
  WCHAR *CacheFileName; // rax
  DWORD v14; // ecx
  __int64 i; // r15
  DWORD LastError; // eax
  unsigned __int16 *CryptnetUrlCacheDir; // rax
  __int128 v19; // [rsp+48h] [rbp-99h] BYREF
  void *v20; // [rsp+58h] [rbp-89h]
  __int64 v21; // [rsp+60h] [rbp-81h]
  HLOCAL hMem; // [rsp+68h] [rbp-79h]
  HANDLE hObject; // [rsp+70h] [rbp-71h]
  _DWORD *v24; // [rsp+78h] [rbp-69h]
  _DWORD v25[2]; // [rsp+80h] [rbp-61h] BYREF
  __int128 *v26; // [rsp+88h] [rbp-59h]
  char v27[80]; // [rsp+90h] [rbp-51h] BYREF

  v5 = a3;
  v20 = a5;
  v24 = a4;
  v7 = *a4 == 40;
  v21 = a1;
  FileW = 0;
  hObject = 0;
  v10 = 0;
  hMem = 0;
  if ( !v7 )
  {
    v14 = 87;
LABEL_17:
    SetLastError(v14);
LABEL_18:
    v12 = 0;
    goto LABEL_19;
  }
  if ( !a3 )
  {
    CryptnetUrlCacheDir = I_SchemeGetCryptnetUrlCacheDir();
    hMem = CryptnetUrlCacheDir;
    if ( !CryptnetUrlCacheDir )
      goto LABEL_18;
    v5 = CryptnetUrlCacheDir;
  }
  v11 = 0;
  v12 = 1;
  if ( a2 && !a2->dwLowDateTime )
    v11 = a2->dwHighDateTime == 0;
  I_UrlCacheGetUrlFileName(a1, v27);
  CacheFileName = (WCHAR *)I_UrlCacheGetCacheFileName(v5, L"MetaData", v20, 1);
  *(_QWORD *)&v19 = CacheFileName;
  if ( CacheFileName )
  {
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      FileW = CreateFileW(CacheFileName, 0xC0000000, 0, 0, 4u, 4u, 0);
      if ( FileW != (HANDLE)-1LL )
        break;
      LastError = GetLastError();
      if ( LastError != 32 || (unsigned int)i >= 6 )
      {
        if ( LastError != 5 )
        {
          if ( LastError == 3 )
            LastError = 2;
LABEL_30:
          SetLastError(LastError);
          FileW = 0;
          break;
        }
        if ( (_DWORD)i )
          goto LABEL_30;
      }
      Sleep(*((_DWORD *)qword_18002BA20 + i));
      CacheFileName = (WCHAR *)v19;
    }
    CacheFileName = (WCHAR *)v19;
  }
  operator delete(CacheFileName);
  if ( !FileW )
    goto LABEL_18;
  v10 = I_UrlCacheReadAndValidateMetaDataFile(FileW, 0);
  if ( !v10 )
  {
    v25[1] = 0;
    v19 = 0;
    if ( !v11 )
      goto LABEL_18;
    hObject = (HANDLE)I_UrlCacheCreateCacheFile(v5, L"Content", v20, 1);
    if ( !hObject )
      goto LABEL_18;
    if ( SetFilePointer(FileW, 0, 0, 0) == -1 )
      goto LABEL_18;
    v26 = &v19;
    LODWORD(v19) = 0;
    *((_QWORD *)&v19 + 1) = 0;
    v25[0] = 1;
    if ( !(unsigned int)I_UrlCacheWriteCryptBlobArray2(v21, FileW, hObject, v25, 0, 0, 0) )
      goto LABEL_18;
    if ( SetFilePointer(FileW, 0, 0, 0) == -1 )
      goto LABEL_18;
    v10 = I_UrlCacheReadAndValidateMetaDataFile(FileW, 0);
    if ( !v10 )
      goto LABEL_18;
  }
  if ( a2 && !v11 && CompareFileTime((const FILETIME *)(v10 + 16), a2) )
  {
    v14 = 1110;
    goto LABEL_17;
  }
  I_UrlCacheCopyCbSizeStruct(v24, v10 + 24);
  if ( *(_DWORD *)(v10 + 28) && CompareFileTime((const FILETIME *)(v10 + 48), (const FILETIME *)(v10 + 72)) > 0 )
    *(_QWORD *)(v10 + 72) = *(_QWORD *)(v10 + 48);
  if ( *(_WORD *)(v10 + 84) && !v11 )
    *(_WORD *)(v10 + 86) |= 0x8000u;
  if ( !(unsigned int)I_UrlCacheUpdateMetaData(FileW, (LPCVOID)v10, 0) )
    goto LABEL_18;
LABEL_19:
  operator delete(hMem);
  operator delete((HLOCAL)v10);
  if ( hObject )
    I_UrlCacheCloseHandle(hObject);
  if ( FileW )
    I_UrlCacheCloseHandle(FileW);
  return v12;
}

```

## disassembly

```asm
0x180002460  push    rbp
0x180002462  push    rbx
0x180002463  push    rsi
0x180002464  push    rdi
0x180002465  push    r12
0x180002467  push    r13
0x180002469  push    r14
0x18000246b  push    r15
0x18000246d  lea     rbp, [rsp-17h]
0x180002472  sub     rsp, 0F8h
0x180002479  mov     rax, cs:__security_cookie
0x180002480  xor     rax, rsp
0x180002483  mov     [rbp+4Fh+var_50], rax
0x180002487  mov     rax, [rbp+4Fh+arg_20]
0x18000248b  mov     r13, r8
0x18000248e  mov     [rsp+130h+var_D8], rax
0x180002493  mov     r12, rdx
0x180002496  xor     eax, eax
0x180002498  mov     [rbp+4Fh+var_B8], r9
0x18000249c  cmp     dword ptr [r9], 28h ; '('
0x1800024a0  mov     r15, rcx
0x1800024a3  mov     [rsp+130h+var_D0], rcx
0x1800024a8  mov     edi, eax
0x1800024aa  mov     [rbp+4Fh+hObject], rax
0x1800024ae  mov     ebx, eax
0x1800024b0  mov     [rbp+4Fh+hMem], rax
0x1800024b4  mov     [rsp+130h+nNumberOfBytesToWrite], eax
0x1800024b8  jnz     loc_1800025B0
0x1800024be  test    r8, r8
0x1800024c1  jz      loc_1800027CD
0x1800024c7  mov     r14d, eax
0x1800024ca  mov     esi, 1
0x1800024cf  test    r12, r12
0x1800024d2  jnz     loc_18000278D
0x1800024d8  lea     rdx, [rbp+4Fh+var_A0]
0x1800024dc  mov     rcx, r15
0x1800024df  call    I_UrlCacheGetUrlFileName
0x1800024e4  mov     r8, [rsp+130h+var_D8]; void *
0x1800024e9  lea     r9, [rbp+4Fh+var_A0]
0x1800024ed  lea     rdx, aMetadata; "MetaData"
0x1800024f4  mov     [rsp+130h+dwCreationDisposition], esi; int
0x1800024f8  mov     rcx, r13; Src
0x1800024fb  call    I_UrlCacheGetCacheFileName
0x180002500  mov     qword ptr [rsp+130h+var_E8], rax
0x180002505  test    rax, rax
0x180002508  jnz     loc_18000260A
0x18000250e  mov     rcx, rax; hMem
0x180002511  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002516  test    rdi, rdi
0x180002519  jz      loc_1800025BB
0x18000251f  lea     r9, [rsp+130h+nNumberOfBytesToWrite]
0x180002524  mov     qword ptr [rsp+130h+dwCreationDisposition], rbx; __int64
0x180002529  xor     r8d, r8d
0x18000252c  xor     edx, edx
0x18000252e  mov     rcx, rdi; hFile
0x180002531  call    I_UrlCacheReadAndValidateMetaDataFile
0x180002536  mov     rbx, rax
0x180002539  test    rax, rax
0x18000253c  jz      loc_18000267B
0x180002542  test    r12, r12
0x180002545  jz      short loc_180002561
0x180002547  test    r14d, r14d
0x18000254a  jnz     short loc_180002561
0x18000254c  lea     rcx, [rbx+10h]; lpFileTime1
0x180002550  mov     rdx, r12; lpFileTime2
0x180002553  call    cs:__imp_CompareFileTime
0x180002559  test    eax, eax
0x18000255b  jnz     loc_1800027F3
0x180002561  mov     rcx, [rbp+4Fh+var_B8]
0x180002565  lea     rdx, [rbx+18h]
0x180002569  call    I_UrlCacheCopyCbSizeStruct
0x18000256e  cmp     dword ptr [rbx+1Ch], 0
0x180002572  jz      short loc_18000258E
0x180002574  lea     rcx, [rbx+30h]; lpFileTime1
0x180002578  lea     rdx, [rbx+48h]; lpFileTime2
0x18000257c  call    cs:__imp_CompareFileTime
0x180002582  test    eax, eax
0x180002584  jle     short loc_18000258E
0x180002586  mov     rax, [rbx+30h]
0x18000258a  mov     [rbx+48h], rax
0x18000258e  xor     eax, eax
0x180002590  cmp     ax, [rbx+54h]
0x180002594  jnz     loc_180002776
0x18000259a  mov     r8d, [rsp+130h+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x18000259f  mov     rdx, rbx; lpBuffer
0x1800025a2  mov     rcx, rdi; hFile
0x1800025a5  call    I_UrlCacheUpdateMetaData
0x1800025aa  test    eax, eax
0x1800025ac  jz      short loc_1800025BB
0x1800025ae  jmp     short loc_1800025BD
0x1800025b0  mov     ecx, 57h ; 'W'; dwErrCode
0x1800025b5  call    cs:__imp_SetLastError
0x1800025bb  xor     esi, esi
0x1800025bd  mov     rcx, [rbp+4Fh+hMem]; hMem
0x1800025c1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800025c6  mov     rcx, rbx; hMem
0x1800025c9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800025ce  mov     rax, [rbp+4Fh+hObject]
0x1800025d2  test    rax, rax
0x1800025d5  jnz     loc_1800027FD
0x1800025db  test    rdi, rdi
0x1800025de  jz      short loc_1800025E8
0x1800025e0  mov     rcx, rdi; hObject
0x1800025e3  call    I_UrlCacheCloseHandle
0x1800025e8  mov     eax, esi
0x1800025ea  mov     rcx, [rbp+4Fh+var_50]
0x1800025ee  xor     rcx, rsp; StackCookie
0x1800025f1  call    __security_check_cookie
0x1800025f6  add     rsp, 0F8h
0x1800025fd  pop     r15
0x1800025ff  pop     r14
0x180002601  pop     r13
0x180002603  pop     r12
0x180002605  pop     rdi
0x180002606  pop     rsi
0x180002607  pop     rbx
0x180002608  pop     rbp
0x180002609  retn
0x18000260a  xor     r15d, r15d
0x18000260d  mov     [rsp+130h+hTemplateFile], rbx; hTemplateFile
0x180002612  xor     r9d, r9d; lpSecurityAttributes
0x180002615  mov     [rsp+130h+dwFlagsAndAttributes], 4; dwFlagsAndAttributes
0x18000261d  xor     r8d, r8d; dwShareMode
0x180002620  mov     edx, 0C0000000h; dwDesiredAccess
0x180002625  mov     [rsp+130h+dwCreationDisposition], 4; dwCreationDisposition
0x18000262d  mov     rcx, rax; lpFileName
0x180002630  call    cs:__imp_CreateFileW
0x180002636  mov     rdi, rax
0x180002639  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000263d  jnz     short loc_18000266C
0x18000263f  call    cs:__imp_GetLastError
0x180002645  cmp     eax, 20h ; ' '
0x180002648  jz      loc_1800027A5
0x18000264e  cmp     eax, 5
0x180002651  jz      loc_1800027E9
0x180002657  cmp     eax, 3
0x18000265a  mov     ecx, 2
0x18000265f  cmovz   eax, ecx
0x180002662  mov     ecx, eax; dwErrCode
0x180002664  call    cs:__imp_SetLastError
0x18000266a  xor     edi, edi
0x18000266c  mov     rax, qword ptr [rsp+130h+var_E8]
0x180002671  mov     r15, [rsp+130h+var_D0]
0x180002676  jmp     loc_18000250E
0x18000267b  mov     [rbp+4Fh+var_AC], 0
0x180002682  xorps   xmm0, xmm0
0x180002685  movups  [rsp+130h+var_E8], xmm0
0x18000268a  test    r14d, r14d
0x18000268d  jz      loc_1800025BB
0x180002693  mov     r8, [rsp+130h+var_D8]; void *
0x180002698  lea     rdx, aContent; "Content"
0x18000269f  mov     r9, r15
0x1800026a2  mov     [rsp+130h+dwCreationDisposition], esi; int
0x1800026a6  mov     rcx, r13; Src
0x1800026a9  call    I_UrlCacheCreateCacheFile
0x1800026ae  mov     [rbp+4Fh+hObject], rax
0x1800026b2  mov     r15, rax
0x1800026b5  test    rax, rax
0x1800026b8  jz      loc_1800025BB
0x1800026be  xor     r9d, r9d; dwMoveMethod
0x1800026c1  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800026c4  xor     edx, edx; lDistanceToMove
0x1800026c6  mov     rcx, rdi; hFile
0x1800026c9  call    cs:__imp_SetFilePointer
0x1800026cf  or      r13d, 0FFFFFFFFh
0x1800026d3  cmp     eax, r13d
0x1800026d6  jz      loc_1800025BB
0x1800026dc  mov     rcx, [rsp+130h+var_D0]
0x1800026e1  lea     rax, [rsp+130h+var_E8]
0x1800026e6  mov     [rsp+130h+hTemplateFile], 0
0x1800026ef  lea     r9, [rbp+4Fh+var_B0]
0x1800026f3  mov     qword ptr [rsp+130h+dwFlagsAndAttributes], 0
0x1800026fc  mov     r8, r15
0x1800026ff  mov     rdx, rdi
0x180002702  mov     [rbp+4Fh+var_A8], rax
0x180002706  mov     qword ptr [rsp+130h+dwCreationDisposition], 0
0x18000270f  mov     dword ptr [rsp+130h+var_E8], 0
0x180002717  mov     qword ptr [rsp+130h+var_E8+8], 0
0x180002720  mov     [rbp+4Fh+var_B0], esi
0x180002723  call    I_UrlCacheWriteCryptBlobArray2
0x180002728  test    eax, eax
0x18000272a  jz      loc_1800025BB
0x180002730  xor     r9d, r9d; dwMoveMethod
0x180002733  xor     r8d, r8d; lpDistanceToMoveHigh
0x180002736  xor     edx, edx; lDistanceToMove
0x180002738  mov     rcx, rdi; hFile
0x18000273b  call    cs:__imp_SetFilePointer
0x180002741  cmp     eax, r13d
0x180002744  jz      loc_1800025BB
0x18000274a  lea     r9, [rsp+130h+nNumberOfBytesToWrite]
0x18000274f  mov     qword ptr [rsp+130h+dwCreationDisposition], 0; __int64
0x180002758  xor     r8d, r8d
0x18000275b  xor     edx, edx
0x18000275d  mov     rcx, rdi; hFile
0x180002760  call    I_UrlCacheReadAndValidateMetaDataFile
0x180002765  mov     rbx, rax
0x180002768  test    rax, rax
0x18000276b  jz      loc_1800025BB
0x180002771  jmp     loc_180002542
0x180002776  test    r14d, r14d
0x180002779  jnz     loc_18000259A
0x18000277f  mov     eax, 8000h
0x180002784  or      [rbx+56h], ax
0x180002788  jmp     loc_18000259A
0x18000278d  cmp     [r12], eax
0x180002791  jnz     loc_1800024D8
0x180002797  cmp     [r12+4], eax
0x18000279c  cmovz   r14d, esi
0x1800027a0  jmp     loc_1800024D8
0x1800027a5  cmp     r15d, 6
0x1800027a9  jnb     loc_18000264E
0x1800027af  lea     rax, qword_18002BA20
0x1800027b6  mov     ecx, [rax+r15*4]; dwMilliseconds
0x1800027ba  call    cs:__imp_Sleep
0x1800027c0  mov     rax, qword ptr [rsp+130h+var_E8]
0x1800027c5  add     r15d, esi
0x1800027c8  jmp     loc_18000260D
0x1800027cd  call    ?I_SchemeGetCryptnetUrlCacheDir@@YAPEAGXZ; I_SchemeGetCryptnetUrlCacheDir(void)
0x1800027d2  mov     [rbp+4Fh+hMem], rax
0x1800027d6  test    rax, rax
0x1800027d9  jz      loc_1800025BB
0x1800027df  mov     r13, rax
0x1800027e2  xor     eax, eax
0x1800027e4  jmp     loc_1800024C7
0x1800027e9  cmp     r15d, esi
0x1800027ec  jb      short loc_1800027AF
0x1800027ee  jmp     loc_180002662
0x1800027f3  mov     ecx, 456h
0x1800027f8  jmp     loc_1800025B5
0x1800027fd  mov     rcx, rax; hObject
0x180002800  call    I_UrlCacheCloseHandle
0x180002805  jmp     loc_1800025DB
```
