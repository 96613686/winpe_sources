# CSystemWriter::TraverseDir(ushort *,void *)

- ea: `0x1800051e0`
- end: `0x18000563a`
- name: `?TraverseDir@CSystemWriter@@AEAA_NPEAGPEAX@Z`
- size: `1114`
- prototype: `bool __fastcall(CSystemWriter *__hidden this, unsigned __int16 *, void *)`
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update`

## callers

- `0x18001df9c`

## callees

- `0x1800050d8`
- `0x1800051b0`
- `0x1800051e0`
- `0x180005640`
- `0x180005fc0`
- `0x180006e24`
- `0x180006e54`
- `0x180007044`
- `0x18000aa74`
- `0x18000ad30`
- `0x18000be40`
- `0x18000c7e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800054fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005523`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800054fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005523`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180005393`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180005393`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800054ee`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800054ee`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180005518`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800055ae`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180005518`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800055ae`

## string_xrefs

- `0x180005587`: `TraverseDir : Unable to push subdirectory.`
- `0x180005593`: `TraverseDir : Unable to build file path.`
- `0x1800055d1`: `TraverseDir : Unable to pop directory.`
- `0x1800055bf`: `TraverseDir : Unable to build Directory\* path.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall CSystemWriter::TraverseDir(CSystemWriter *this, unsigned __int16 *a2, void *a3)
{
  int v4; // eax
  char v5; // r14
  _QWORD *v6; // rbx
  __int64 v7; // rax
  __int16 *v8; // rcx
  __int64 v9; // rdx
  _WORD *v10; // r9
  __int16 v11; // r8
  unsigned int v12; // r8d
  _WORD *v13; // rcx
  HANDLE FirstFileW; // rbx
  int v15; // edx
  int v16; // edx
  _QWORD *v17; // rax
  _QWORD *v18; // rdi
  int v19; // esi
  signed int v20; // eax
  DWORD v21; // eax
  DWORD LastError; // r8d
  const unsigned __int16 *v23; // rdx
  const unsigned __int16 *v25; // rdx
  HANDLE v26; // [rsp+38h] [rbp-D0h] BYREF
  _QWORD *v27; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v28; // [rsp+48h] [rbp-C0h]
  __int64 v29; // [rsp+50h] [rbp-B8h]
  _QWORD v30[3]; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v31; // [rsp+70h] [rbp-98h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+78h] [rbp-90h] BYREF
  _BYTE v33[528]; // [rsp+2C8h] [rbp+1C0h] BYREF
  WCHAR FileName[264]; // [rsp+4D8h] [rbp+3D0h] BYREF
  unsigned __int16 v35[264]; // [rsp+6E8h] [rbp+5E0h] BYREF

  v29 = -2;
  v31 = 0;
  v30[0] = v30;
  v30[1] = v30;
  v30[2] = v30;
  v4 = Traversal::DirectoryStack::Push((Traversal::DirectoryStack *)v30, a2, 0);
  if ( v4 < 0 )
  {
    v25 = L"TraverseDir : Unable to push BaseDir.";
LABEL_43:
    v12 = v4;
LABEL_46:
    CSystemWriter::LogSystemErrorEvent(0x201u, v25, v12);
    goto LABEL_37;
  }
  v5 = 1;
  while ( 2 )
  {
    v6 = (_QWORD *)v30[0];
    if ( (_QWORD *)v30[0] == v30 )
      goto LABEL_49;
    memset_0(FileName, 0, 0x208u);
    memset_0(v33, 0, 0x208u);
    if ( v6 == (_QWORD *)520 )
    {
      v12 = -2147467259;
LABEL_45:
      v25 = L"TraverseDir : Unable to pop directory.";
      goto LABEL_46;
    }
    v7 = 2147483646;
    v8 = (__int16 *)(v6 - 65);
    v9 = 260;
    v10 = v33;
    do
    {
      if ( !v7 )
        break;
      v11 = *v8;
      if ( !*v8 )
        break;
      ++v8;
      *v10++ = v11;
      --v7;
      --v9;
    }
    while ( v9 );
    v12 = v9 == 0 ? 0x8007007A : 0;
    v13 = v10 - 1;
    if ( v9 )
      v13 = v10;
    *v13 = 0;
    if ( !v9 )
      goto LABEL_45;
    if ( v6 != v30 )
    {
      if ( v6 && (_QWORD *)v6[2] == v30 )
      {
        *(_QWORD *)(*v6 + 8LL) = v6[1];
        v9 = v6[1];
        *(_QWORD *)v9 = *v6;
        v6[2] = 0;
        --v31;
      }
      Traversal::DirectoryStack::DirectoryEntry::`scalar deleting destructor'(
        (Traversal::DirectoryStack::DirectoryEntry *)(v6 - 65),
        v9);
    }
    v4 = StringCchPrintfW(FileName, 0x104u, L"%s\\*", v33);
    if ( v4 < 0 )
    {
      v25 = L"TraverseDir : Unable to build Directory\\* path.";
      goto LABEL_43;
    }
    memset_0(&FindFileData, 0, sizeof(FindFileData));
    FirstFileW = FindFirstFileW(FileName, &FindFileData);
    v26 = FirstFileW;
    if ( FirstFileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v23 = L"TraverseDir : Unable to FindFirstFile.";
      goto LABEL_36;
    }
    do
    {
      if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
      {
        v20 = StringCchPrintfW(v35, 0x104u, L"%s\\%s", v33, FindFileData.cFileName);
        if ( v20 < 0 )
        {
          CSystemWriter::LogSystemErrorEvent(0x201u, L"TraverseDir : Unable to build file path.", v20);
          FindClose(FirstFileW);
          goto LABEL_37;
        }
        if ( (unsigned int)pSetupStringTableAddString(a3, v35) != -1 )
          continue;
        LastError = 14;
        v23 = L"TraverseDir : pSetupStringTableAddString() failed.";
LABEL_36:
        CSystemWriter::LogSystemErrorEvent(0x201u, v23, LastError);
        Traversal::SearchHandle::~SearchHandle((Traversal::SearchHandle *)&v26);
LABEL_37:
        Traversal::DirectoryStack::~DirectoryStack((Traversal::DirectoryStack *)v30);
        return 0;
      }
      v15 = FindFileData.cFileName[0] - 46;
      if ( FindFileData.cFileName[0] == 46 )
        v15 = FindFileData.cFileName[1];
      if ( v15 )
      {
        v16 = FindFileData.cFileName[0] - 46;
        if ( FindFileData.cFileName[0] == 46 )
        {
          v16 = FindFileData.cFileName[1] - 46;
          if ( FindFileData.cFileName[1] == 46 )
            v16 = FindFileData.cFileName[2];
        }
        if ( v16 )
        {
          v17 = operator new(0x220u);
          v18 = v17;
          if ( v17 )
          {
            v17[67] = 0;
            v17[65] = 0;
            v17[66] = 0;
            *(_WORD *)v17 = 0;
            v27 = v17;
            LOBYTE(v28) = 0;
            v19 = StringCchPrintfW((unsigned __int16 *)v17, 0x104u, L"%s\\%s", v33, FindFileData.cFileName);
            if ( v19 >= 0 )
            {
              v18[65] = v30[0];
              v18[66] = v30;
              *(_QWORD *)(v30[0] + 8LL) = v18 + 65;
              v30[0] = v18 + 65;
              v18[67] = v30;
              ++v31;
              LOBYTE(v28) = 1;
              continue;
            }
            Traversal::DirectoryStack::EntryHolder::~EntryHolder((Traversal::DirectoryStack::EntryHolder *)&v27);
          }
          else
          {
            v19 = -2147024882;
          }
          LastError = v19;
          v23 = L"TraverseDir : Unable to push subdirectory.";
          goto LABEL_36;
        }
      }
    }
    while ( FindNextFileW(FirstFileW, &FindFileData) );
    v21 = GetLastError();
    if ( v21 == 18 )
    {
      FindClose(FirstFileW);
      continue;
    }
    break;
  }
  CSystemWriter::LogSystemErrorEvent(0x201u, L"TraverseDir : Unable to FindNextFile.", v21);
  Traversal::SearchHandle::~SearchHandle((Traversal::SearchHandle *)&v26);
  v5 = 0;
LABEL_49:
  Traversal::DirectoryStack::~DirectoryStack((Traversal::DirectoryStack *)v30);
  return v5;
}

```

## disassembly

```asm
0x1800051e0  mov     rax, rsp
0x1800051e3  push    rbp
0x1800051e4  push    rsi
0x1800051e5  push    rdi
0x1800051e6  push    r12
0x1800051e8  push    r13
0x1800051ea  push    r14
0x1800051ec  push    r15
0x1800051ee  lea     rbp, [rax-838h]
0x1800051f5  sub     rsp, 900h
0x1800051fc  mov     [rsp+930h+var_8E8], 0FFFFFFFFFFFFFFFEh
0x180005205  mov     [rax+8], rbx
0x180005209  mov     rax, cs:__security_cookie
0x180005210  xor     rax, rsp
0x180005213  mov     [rbp+830h+var_40], rax
0x18000521a  mov     r15, r8
0x18000521d  xor     r12d, r12d
0x180005220  mov     [rsp+930h+var_8C8], r12
0x180005225  lea     rax, [rsp+930h+var_8E0]
0x18000522a  mov     [rsp+930h+var_8E0], rax
0x18000522f  lea     rax, [rsp+930h+var_8E0]
0x180005234  mov     [rsp+930h+var_8D8], rax
0x180005239  lea     rax, [rsp+930h+var_8E0]
0x18000523e  mov     [rsp+930h+var_8D0], rax
0x180005243  xor     r8d, r8d; unsigned __int16 *
0x180005246  lea     rcx, [rsp+930h+var_8E0]; this
0x18000524b  call    ?Push@DirectoryStack@Traversal@@QEAAJPEAG0@Z; Traversal::DirectoryStack::Push(ushort *,ushort *)
0x180005250  test    eax, eax
0x180005252  js      loc_1800055B6
0x180005258  lea     edi, [r12+2Eh]
0x18000525d  mov     r13d, 104h
0x180005263  lea     r14d, [r12+1]
0x180005268  mov     rbx, [rsp+930h+var_8E0]
0x18000526d  lea     rax, [rsp+930h+var_8E0]
0x180005272  cmp     rbx, rax
0x180005275  jz      loc_180005615
0x18000527b  xor     edx, edx; Val
0x18000527d  mov     r8d, 208h; Size
0x180005283  lea     rcx, [rbp+830h+FileName]; void *
0x18000528a  call    memset_0
0x18000528f  xor     edx, edx; Val
0x180005291  mov     r8d, 208h; Size
0x180005297  lea     rcx, [rbp+830h+var_670]; void *
0x18000529e  call    memset_0
0x1800052a3  lea     r10, [rbx-208h]
0x1800052aa  test    r10, r10
0x1800052ad  jz      loc_1800055CB
0x1800052b3  mov     eax, 7FFFFFFEh
0x1800052b8  mov     rcx, r10
0x1800052bb  mov     rdx, r13
0x1800052be  lea     r9, [rbp+830h+var_670]
0x1800052c5  test    rax, rax
0x1800052c8  jz      short loc_1800052E8
0x1800052ca  movzx   r8d, word ptr [rcx]
0x1800052ce  test    r8w, r8w
0x1800052d2  jz      short loc_1800052E8
0x1800052d4  add     rcx, 2
0x1800052d8  mov     [r9], r8w
0x1800052dc  add     r9, 2
0x1800052e0  sub     rax, r14
0x1800052e3  sub     rdx, r14
0x1800052e6  jnz     short loc_1800052C5
0x1800052e8  mov     rax, rdx
0x1800052eb  neg     rax
0x1800052ee  sbb     r8d, r8d
0x1800052f1  not     r8d
0x1800052f4  and     r8d, 8007007Ah
0x1800052fb  lea     rcx, [r9-2]
0x1800052ff  test    rdx, rdx
0x180005302  cmovnz  rcx, r9
0x180005306  mov     [rcx], r12w
0x18000530a  jz      loc_1800055D1
0x180005310  lea     rax, [rsp+930h+var_8E0]
0x180005315  cmp     rbx, rax
0x180005318  jz      short loc_180005350
0x18000531a  test    rbx, rbx
0x18000531d  jz      short loc_180005348
0x18000531f  lea     rax, [rsp+930h+var_8E0]
0x180005324  cmp     [rbx+10h], rax
0x180005328  jnz     short loc_180005348
0x18000532a  mov     rdx, [rbx]
0x18000532d  mov     rax, [rbx+8]
0x180005331  mov     [rdx+8], rax
0x180005335  mov     rdx, [rbx+8]; unsigned int
0x180005339  mov     rax, [rbx]
0x18000533c  mov     [rdx], rax
0x18000533f  mov     [rbx+10h], r12
0x180005343  sub     [rsp+930h+var_8C8], r14
0x180005348  mov     rcx, r10; this
0x18000534b  call    ??_GDirectoryEntry@DirectoryStack@Traversal@@QEAAPEAXI@Z; Traversal::DirectoryStack::DirectoryEntry::`scalar deleting destructor'(uint)
0x180005350  lea     r9, [rbp+830h+var_670]
0x180005357  lea     r8, aS; "%s\\*"
0x18000535e  mov     rdx, r13; unsigned __int64
0x180005361  lea     rcx, [rbp+830h+FileName]; unsigned __int16 *
0x180005368  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000536d  test    eax, eax
0x18000536f  js      loc_1800055BF
0x180005375  xor     edx, edx; Val
0x180005377  mov     r8d, 250h; Size
0x18000537d  lea     rcx, [rsp+930h+FindFileData]; void *
0x180005382  call    memset_0
0x180005387  lea     rdx, [rsp+930h+FindFileData]; lpFindFileData
0x18000538c  lea     rcx, [rbp+830h+FileName]; lpFileName
0x180005393  call    cs:__imp_FindFirstFileW
0x180005399  mov     rbx, rax
0x18000539c  mov     [rsp+930h+var_900], rax
0x1800053a1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800053a5  jz      loc_180005523
0x1800053ab  test    byte ptr [rsp+930h+FindFileData.dwFileAttributes], 10h
0x1800053b0  jz      loc_1800054A0
0x1800053b6  movzx   edx, [rbp+830h+FindFileData.cFileName]
0x1800053ba  movzx   eax, di
0x1800053bd  sub     edx, eax
0x1800053bf  jnz     short loc_1800053CB
0x1800053c1  movzx   edx, [rbp+830h+FindFileData.cFileName+2]
0x1800053c5  movzx   ecx, r12w
0x1800053c9  sub     edx, ecx
0x1800053cb  test    edx, edx
0x1800053cd  jz      loc_1800054E6
0x1800053d3  movzx   edx, [rbp+830h+FindFileData.cFileName]
0x1800053d7  movzx   eax, di
0x1800053da  sub     edx, eax
0x1800053dc  jnz     short loc_1800053F3
0x1800053de  movzx   edx, [rbp+830h+FindFileData.cFileName+2]
0x1800053e2  movzx   eax, di
0x1800053e5  sub     edx, eax
0x1800053e7  jnz     short loc_1800053F3
0x1800053e9  movzx   edx, [rbp+830h+FindFileData.cFileName+4]
0x1800053ed  movzx   ecx, r12w
0x1800053f1  sub     edx, ecx
0x1800053f3  test    edx, edx
0x1800053f5  jz      loc_1800054E6
0x1800053fb  mov     ecx, 220h; unsigned __int64
0x180005400  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005405  mov     rdi, rax
0x180005408  test    rax, rax
0x18000540b  jz      loc_18000557F
0x180005411  mov     [rax+218h], r12
0x180005418  mov     [rax+208h], r12
0x18000541f  mov     [rax+210h], r12
0x180005426  mov     [rax], r12w
0x18000542a  mov     [rsp+930h+var_8F8], rax
0x18000542f  mov     byte ptr [rsp+930h+var_8F0], r12b
0x180005434  lea     rax, [rbp+830h+FindFileData.cFileName]
0x180005438  mov     [rsp+20h], rax
0x18000543d  lea     r9, [rbp+830h+var_670]
0x180005444  lea     r8, aSS; "%s\\%s"
0x18000544b  mov     rdx, r13; unsigned __int64
0x18000544e  mov     rcx, rdi; unsigned __int16 *
0x180005451  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005456  mov     esi, eax
0x180005458  test    eax, eax
0x18000545a  js      loc_1800055E7
0x180005460  lea     rcx, [rdi+208h]
0x180005467  mov     rax, [rsp+930h+var_8E0]
0x18000546c  mov     [rcx], rax
0x18000546f  lea     rax, [rsp+930h+var_8E0]
0x180005474  mov     [rcx+8], rax
0x180005478  mov     rax, [rsp+930h+var_8E0]
0x18000547d  mov     [rax+8], rcx
0x180005481  mov     [rsp+930h+var_8E0], rcx
0x180005486  lea     rax, [rsp+930h+var_8E0]
0x18000548b  mov     [rcx+10h], rax
0x18000548f  add     [rsp+930h+var_8C8], r14
0x180005494  mov     byte ptr [rsp+930h+var_8F0], r14b
0x180005499  mov     edi, 2Eh ; '.'
0x18000549e  jmp     short loc_1800054E6
0x1800054a0  lea     rax, [rbp+830h+FindFileData.cFileName]
0x1800054a4  mov     [rsp+20h], rax
0x1800054a9  lea     r9, [rbp+830h+var_670]
0x1800054b0  lea     r8, aSS; "%s\\%s"
0x1800054b7  mov     rdx, r13; unsigned __int64
0x1800054ba  lea     rcx, [rbp+830h+var_250]; unsigned __int16 *
0x1800054c1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800054c6  test    eax, eax
0x1800054c8  js      loc_180005590
0x1800054ce  lea     rdx, [rbp+830h+var_250]
0x1800054d5  mov     rcx, r15
0x1800054d8  call    pSetupStringTableAddString
0x1800054dd  cmp     eax, 0FFFFFFFFh
0x1800054e0  jz      loc_180005627
0x1800054e6  lea     rdx, [rsp+930h+FindFileData]; lpFindFileData
0x1800054eb  mov     rcx, rbx; hFindFile
0x1800054ee  call    cs:__imp_FindNextFileW
0x1800054f4  test    eax, eax
0x1800054f6  jnz     loc_1800053AB
0x1800054fc  call    cs:__imp_GetLastError
0x180005502  cmp     eax, 12h
0x180005505  jnz     loc_1800055F3
0x18000550b  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000550f  jz      loc_180005268
0x180005515  mov     rcx, rbx; hFindFile
0x180005518  call    cs:__imp_FindClose
0x18000551e  jmp     loc_180005268
0x180005523  call    cs:__imp_GetLastError
0x180005529  mov     r8d, eax; unsigned int
0x18000552c  lea     rdx, aTraversedirUna_0; "TraverseDir : Unable to FindFirstFile."
0x180005533  mov     ecx, 201h; unsigned int
0x180005538  call    ?LogSystemErrorEvent@CSystemWriter@@CAXKPEBGK@Z; CSystemWriter::LogSystemErrorEvent(ulong,ushort const *,ulong)
0x18000553d  nop
0x18000553e  lea     rcx, [rsp+930h+var_900]; this
0x180005543  call    ??1SearchHandle@Traversal@@QEAA@XZ; Traversal::SearchHandle::~SearchHandle(void)
0x180005548  nop
0x180005549  lea     rcx, [rsp+930h+var_8E0]; this
0x18000554e  call    ??1DirectoryStack@Traversal@@QEAA@XZ; Traversal::DirectoryStack::~DirectoryStack(void)
0x180005553  xor     al, al
0x180005555  mov     rcx, [rbp+830h+var_40]
0x18000555c  xor     rcx, rsp; StackCookie
0x18000555f  call    __security_check_cookie
0x180005564  mov     rbx, [rsp+930h+arg_0]
0x18000556c  add     rsp, 900h
0x180005573  pop     r15
0x180005575  pop     r14
0x180005577  pop     r13
0x180005579  pop     r12
0x18000557b  pop     rdi
0x18000557c  pop     rsi
0x18000557d  pop     rbp
0x18000557e  retn
0x18000557f  mov     esi, 8007000Eh
0x180005584  mov     r8d, esi
0x180005587  lea     rdx, aTraversedirUna; "TraverseDir : Unable to push subdirecto"...
0x18000558e  jmp     short loc_180005533
0x180005590  mov     r8d, eax; unsigned int
0x180005593  lea     rdx, aTraversedirUna_4; "TraverseDir : Unable to build file path"...
0x18000559a  mov     ecx, 201h; unsigned int
0x18000559f  call    ?LogSystemErrorEvent@CSystemWriter@@CAXKPEBGK@Z; CSystemWriter::LogSystemErrorEvent(ulong,ushort const *,ulong)
0x1800055a4  nop
0x1800055a5  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800055a9  jz      short loc_180005549
0x1800055ab  mov     rcx, rbx; hFindFile
0x1800055ae  call    cs:__imp_FindClose
0x1800055b4  jmp     short loc_180005549
0x1800055b6  lea     rdx, aTraversedirUna_3; "TraverseDir : Unable to push BaseDir."
0x1800055bd  jmp     short loc_1800055C6
0x1800055bf  lea     rdx, aTraversedirUna_2; "TraverseDir : Unable to build Directory"...
0x1800055c6  mov     r8d, eax
0x1800055c9  jmp     short loc_1800055D8
0x1800055cb  mov     r8d, 80004005h; unsigned int
0x1800055d1  lea     rdx, aTraversedirUna_5; "TraverseDir : Unable to pop directory."
0x1800055d8  mov     ecx, 201h; unsigned int
0x1800055dd  call    ?LogSystemErrorEvent@CSystemWriter@@CAXKPEBGK@Z; CSystemWriter::LogSystemErrorEvent(ulong,ushort const *,ulong)
0x1800055e2  jmp     loc_180005549
0x1800055e7  lea     rcx, [rsp+930h+var_8F8]; this
0x1800055ec  call    ??1EntryHolder@DirectoryStack@Traversal@@QEAA@XZ; Traversal::DirectoryStack::EntryHolder::~EntryHolder(void)
0x1800055f1  jmp     short loc_180005584
0x1800055f3  mov     r8d, eax; unsigned int
0x1800055f6  lea     rdx, aTraversedirUna_1; "TraverseDir : Unable to FindNextFile."
0x1800055fd  mov     ecx, 201h; unsigned int
0x180005602  call    ?LogSystemErrorEvent@CSystemWriter@@CAXKPEBGK@Z; CSystemWriter::LogSystemErrorEvent(ulong,ushort const *,ulong)
0x180005607  nop
0x180005608  lea     rcx, [rsp+930h+var_900]; this
0x18000560d  call    ??1SearchHandle@Traversal@@QEAA@XZ; Traversal::SearchHandle::~SearchHandle(void)
0x180005612  mov     r14b, r12b
0x180005615  lea     rcx, [rsp+930h+var_8E0]; this
0x18000561a  call    ??1DirectoryStack@Traversal@@QEAA@XZ; Traversal::DirectoryStack::~DirectoryStack(void)
0x18000561f  mov     al, r14b
0x180005622  jmp     loc_180005555
0x180005627  mov     r8d, 0Eh
0x18000562d  lea     rdx, aTraversedirPse; "TraverseDir : pSetupStringTableAddStrin"...
0x180005634  jmp     loc_180005533
```
