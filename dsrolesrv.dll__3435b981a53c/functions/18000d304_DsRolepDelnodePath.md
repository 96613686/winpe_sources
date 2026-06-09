# DsRolepDelnodePath

- ea: `0x18000d304`
- end: `0x18000d690`
- name: `DsRolepDelnodePath`
- size: `908`
- prototype: `__int64 __fastcall(wchar_t *, unsigned __int64, char)`
- caller_count: `5`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callers

- `0x18000c228`
- `0x18000cdfc`
- `0x18000d304`
- `0x18000da4c`
- `0x18000e2fc`

## callees

- `0x180008f24`
- `0x18000d304`
- `0x18000d8fc`
- `0x18000e4d0`
- `0x180020dbc`
- `0x18002c01e`
- `0x18002c050`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000d559`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000d559`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000d3e0`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000d3e0`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000d5a6`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000d5a6`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000d636`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000d636`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000d63f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000d63f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d3f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d56a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d64c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d3f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d56a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d64c`
- `ntdll!RtlAllocateHeap` at `0x18000d39b`
- `ntdll!RtlAllocateHeap` at `0x18000d4bc`
- `ntdll!RtlAllocateHeap` at `0x18000d39b`
- `ntdll!RtlAllocateHeap` at `0x18000d4bc`
- `ntdll!RtlFreeHeap` at `0x18000d542`
- `ntdll!RtlFreeHeap` at `0x18000d5ff`
- `ntdll!RtlFreeHeap` at `0x18000d542`
- `ntdll!RtlFreeHeap` at `0x18000d5ff`

## string_xrefs

- `0x18000d65f`: `DeleteFileW on %ws failed with %lu\n`
- `0x18000d67a`: `	Removed %ws\n`
- `0x18000d5d4`: `Removal of path %ws failed with %lu\n`

## pseudocode

```c
__int64 __fastcall DsRolepDelnodePath(wchar_t *a1, unsigned __int64 a2, char a3)
{
  __int64 v5; // r13
  unsigned __int64 v6; // rbx
  wchar_t *Heap; // r14
  unsigned int v8; // ebx
  void *v9; // rdi
  DWORD LastError; // eax
  int v11; // edx
  int v12; // edx
  __int64 v13; // rax
  __int64 v14; // rax
  unsigned __int64 v15; // r15
  size_t v16; // r12
  wchar_t *v17; // rdi
  __int64 v18; // r8
  DWORD v19; // eax
  ULONG v20; // eax
  DWORD v22; // eax
  HANDLE FirstFileW; // [rsp+38h] [rbp-C8h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v26[528]; // [rsp+290h] [rbp+190h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v5 = -1;
  do
    ++v5;
  while ( a1[v5] );
  v6 = 2 * v5 + 10;
  if ( a2 >= v6 )
  {
    Heap = a1;
    StringCchCatW(a1, a2 >> 1, L"\\*.*");
    goto LABEL_8;
  }
  Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 2 * v5 + 10);
  if ( Heap )
  {
    StringCchPrintfW(Heap, v6 >> 1, L"%ws%ws", a1, L"\\*.*");
LABEL_8:
    v8 = 0;
    FirstFileW = FindFirstFileW(Heap, &FindFileData);
    v9 = FirstFileW;
    if ( FirstFileW != (HANDLE)-1LL )
      goto LABEL_13;
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError != 3 )
    {
      if ( LastError )
      {
        if ( LastError != 18 )
        {
          DsRolepLogPrintRoutine(1, "FindFirstFile on %ws failed with %lu\n", Heap, LastError);
          goto LABEL_42;
        }
      }
      else
      {
        while ( 1 )
        {
LABEL_13:
          v11 = FindFileData.cFileName[0] - 46;
          if ( FindFileData.cFileName[0] == 46 )
            v11 = FindFileData.cFileName[1];
          if ( v11 )
          {
            v12 = FindFileData.cFileName[0] - 46;
            if ( FindFileData.cFileName[0] == 46 )
            {
              v12 = FindFileData.cFileName[1] - 46;
              if ( FindFileData.cFileName[1] == 46 )
                v12 = FindFileData.cFileName[2];
            }
            if ( v12 )
            {
              v13 = -1;
              do
                ++v13;
              while ( FindFileData.cFileName[v13] );
              v14 = v5 + v13;
              v15 = 2 * v14 + 4;
              if ( v15 <= 8 )
              {
                v16 = 261;
                v17 = (wchar_t *)v26;
              }
              else
              {
                v16 = v15 >> 1;
                v17 = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 2 * v14 + 4);
                if ( !v17 )
                  v8 = 8;
              }
              if ( !v8 )
              {
                a1[v5] = 0;
                StringCchPrintfW(v17, v16, L"%ws\\%ws", a1, FindFileData.cFileName);
                if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
                {
                  LOBYTE(v18) = 1;
                  v8 = DsRolepDelnodePath(v17, v15, v18);
                }
                else
                {
                  SetFileAttributesW(v17, 0x80u);
                  if ( DeleteFileW(v17) )
                  {
                    DsRolepLogPrintRoutine(4, "\tRemoved %ws\n", v17);
                  }
                  else
                  {
                    v22 = GetLastError();
                    v8 = v22;
                    if ( v22 )
                      DsRolepLogPrintRoutine(1, "DeleteFileW on %ws failed with %lu\n", v17, v22);
                  }
                }
              }
              if ( v17 != (wchar_t *)v26 )
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v17);
              v9 = FirstFileW;
            }
          }
          if ( v8 )
            break;
          if ( !FindNextFileW(v9, &FindFileData) )
          {
            v19 = GetLastError();
            v8 = v19;
            if ( v19 )
            {
              if ( v19 != 18 )
                DsRolepLogPrintRoutine(1, "FindNextFile after on %ws failed with %lu\n", FindFileData.cFileName, v19);
              break;
            }
          }
        }
        if ( v9 != (void *)-1LL )
          FindClose(v9);
        if ( !v8 )
          goto LABEL_41;
      }
      if ( v8 != 18 )
        goto LABEL_42;
    }
LABEL_41:
    v8 = 0;
    goto LABEL_42;
  }
  v8 = 8;
LABEL_42:
  if ( a3 )
  {
    if ( !v8 )
    {
      v20 = DsRolepRemoveDirectoryOrLink(a1);
      v8 = v20;
      if ( v20 )
        DsRolepLogPrintRoutine(1, "Removal of path %ws failed with %lu\n", a1, v20);
    }
  }
  if ( Heap != a1 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  return v8;
}

```

## disassembly

```asm
0x18000d304  mov     [rsp-8+arg_10], rbx
0x18000d309  push    rbp
0x18000d30a  push    rsi
0x18000d30b  push    rdi
0x18000d30c  push    r12
0x18000d30e  push    r13
0x18000d310  push    r14
0x18000d312  push    r15
0x18000d314  lea     rbp, [rsp-3B0h]
0x18000d31c  sub     rsp, 4B0h
0x18000d323  mov     rax, cs:__security_cookie
0x18000d32a  xor     rax, rsp
0x18000d32d  mov     [rbp+3E0h+var_40], rax
0x18000d334  mov     [rsp+4E0h+var_4B0], r8b
0x18000d339  mov     rdi, rdx
0x18000d33c  mov     rsi, rcx
0x18000d33f  xor     edx, edx; Val
0x18000d341  mov     r8d, 250h; Size
0x18000d347  lea     rcx, [rsp+4E0h+FindFileData]; void *
0x18000d34c  call    memset_0
0x18000d351  or      r13, 0FFFFFFFFFFFFFFFFh
0x18000d355  xor     r15d, r15d
0x18000d358  inc     r13
0x18000d35b  cmp     [rsi+r13*2], r15w
0x18000d360  jnz     short loc_18000D358
0x18000d362  lea     rbx, ds:0Ah[r13*2]
0x18000d36a  cmp     rdi, rbx
0x18000d36d  jb      short loc_18000D389
0x18000d36f  shr     rdi, 1
0x18000d372  lea     r8, asc_18003D370; "\\*.*"
0x18000d379  mov     rdx, rdi; cchDest
0x18000d37c  mov     rcx, rsi; pszDest
0x18000d37f  mov     r14, rsi
0x18000d382  call    StringCchCatW
0x18000d387  jmp     short loc_18000D3D5
0x18000d389  mov     rcx, gs:60h
0x18000d392  mov     r8, rbx; Size
0x18000d395  xor     edx, edx; Flags
0x18000d397  mov     rcx, [rcx+30h]; HeapHandle
0x18000d39b  call    cs:__imp_RtlAllocateHeap
0x18000d3a1  mov     r14, rax
0x18000d3a4  test    rax, rax
0x18000d3a7  jnz     short loc_18000D3B1
0x18000d3a9  lea     ebx, [rax+8]
0x18000d3ac  jmp     loc_18000D5B8
0x18000d3b1  shr     rbx, 1
0x18000d3b4  lea     rax, asc_18003D370; "\\*.*"
0x18000d3bb  mov     rdx, rbx; cchDest
0x18000d3be  mov     [rsp+4E0h+var_4C0], rax
0x18000d3c3  mov     r9, rsi
0x18000d3c6  lea     r8, aWsWs_1; "%ws%ws"
0x18000d3cd  mov     rcx, r14; pszDest
0x18000d3d0  call    StringCchPrintfW
0x18000d3d5  lea     rdx, [rsp+4E0h+FindFileData]; lpFindFileData
0x18000d3da  mov     rcx, r14; lpFileName
0x18000d3dd  mov     ebx, r15d
0x18000d3e0  call    cs:__imp_FindFirstFileW
0x18000d3e6  mov     [rsp+4E0h+var_4A8], rax
0x18000d3eb  mov     rdi, rax
0x18000d3ee  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000d3f2  jnz     short loc_18000D42C
0x18000d3f4  call    cs:__imp_GetLastError
0x18000d3fa  mov     ebx, eax
0x18000d3fc  cmp     eax, 3
0x18000d3ff  jz      loc_18000D5B5
0x18000d405  test    eax, eax
0x18000d407  jz      short loc_18000D42C
0x18000d409  cmp     eax, 12h
0x18000d40c  jz      loc_18000D5B0
0x18000d412  mov     r9d, eax
0x18000d415  lea     rdx, aFindfirstfileO; "FindFirstFile on %ws failed with %lu\n"
0x18000d41c  mov     r8, r14
0x18000d41f  lea     ecx, [rdi+2]
0x18000d422  call    DsRolepLogPrintRoutine
0x18000d427  jmp     loc_18000D5B8
0x18000d42c  mov     ecx, 2Eh ; '.'
0x18000d431  movzx   edx, [rsp+4E0h+FindFileData.cFileName]
0x18000d436  movzx   eax, cx
0x18000d439  sub     edx, eax
0x18000d43b  jnz     short loc_18000D44D
0x18000d43d  movzx   edx, [rsp+4E0h+FindFileData.cFileName+2]
0x18000d442  movzx   ecx, r15w
0x18000d446  sub     edx, ecx
0x18000d448  mov     ecx, 2Eh ; '.'
0x18000d44d  test    edx, edx
0x18000d44f  jz      loc_18000D54D
0x18000d455  movzx   edx, [rsp+4E0h+FindFileData.cFileName]
0x18000d45a  movzx   eax, cx
0x18000d45d  sub     edx, eax
0x18000d45f  jnz     short loc_18000D478
0x18000d461  movzx   edx, [rsp+4E0h+FindFileData.cFileName+2]
0x18000d466  movzx   eax, cx
0x18000d469  sub     edx, eax
0x18000d46b  jnz     short loc_18000D478
0x18000d46d  movzx   edx, [rsp+4E0h+FindFileData.cFileName+4]
0x18000d472  movzx   ecx, r15w
0x18000d476  sub     edx, ecx
0x18000d478  test    edx, edx
0x18000d47a  jz      loc_18000D54D
0x18000d480  lea     rcx, [rsp+4E0h+FindFileData.cFileName]
0x18000d485  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000d489  inc     rax
0x18000d48c  cmp     [rcx+rax*2], r15w
0x18000d491  jnz     short loc_18000D489
0x18000d493  add     rax, r13
0x18000d496  lea     r15, ds:4[rax*2]
0x18000d49e  cmp     r15, 8
0x18000d4a2  jbe     short loc_18000D4CF
0x18000d4a4  mov     rcx, gs:60h
0x18000d4ad  mov     r12, r15
0x18000d4b0  mov     r8, r15; Size
0x18000d4b3  shr     r12, 1
0x18000d4b6  xor     edx, edx; Flags
0x18000d4b8  mov     rcx, [rcx+30h]; HeapHandle
0x18000d4bc  call    cs:__imp_RtlAllocateHeap
0x18000d4c2  mov     rdi, rax
0x18000d4c5  test    rax, rax
0x18000d4c8  jnz     short loc_18000D4DC
0x18000d4ca  lea     ebx, [rax+8]
0x18000d4cd  jmp     short loc_18000D4DC
0x18000d4cf  mov     r12d, 105h
0x18000d4d5  lea     rdi, [rbp+3E0h+var_250]
0x18000d4dc  test    ebx, ebx
0x18000d4de  jnz     short loc_18000D521
0x18000d4e0  xor     eax, eax
0x18000d4e2  lea     r8, aWsWs_3; "%ws\\%ws"
0x18000d4e9  mov     [rsi+r13*2], ax
0x18000d4ee  mov     r9, rsi
0x18000d4f1  lea     rax, [rsp+4E0h+FindFileData.cFileName]
0x18000d4f6  mov     rdx, r12; cchDest
0x18000d4f9  mov     rcx, rdi; pszDest
0x18000d4fc  mov     [rsp+4E0h+var_4C0], rax
0x18000d501  call    StringCchPrintfW
0x18000d506  test    byte ptr [rsp+4E0h+FindFileData.dwFileAttributes], 10h
0x18000d50b  mov     rcx, rdi; lpFileName
0x18000d50e  jz      loc_18000D631
0x18000d514  mov     r8b, 1
0x18000d517  mov     rdx, r15
0x18000d51a  call    DsRolepDelnodePath
0x18000d51f  mov     ebx, eax
0x18000d521  xor     r15d, r15d
0x18000d524  lea     rax, [rbp+3E0h+var_250]
0x18000d52b  cmp     rdi, rax
0x18000d52e  jz      short loc_18000D548
0x18000d530  mov     rcx, gs:60h
0x18000d539  mov     r8, rdi; P
0x18000d53c  xor     edx, edx; Flags
0x18000d53e  mov     rcx, [rcx+30h]; HeapHandle
0x18000d542  call    cs:__imp_RtlFreeHeap
0x18000d548  mov     rdi, [rsp+4E0h+var_4A8]
0x18000d54d  test    ebx, ebx
0x18000d54f  jnz     short loc_18000D59D
0x18000d551  lea     rdx, [rsp+4E0h+FindFileData]; lpFindFileData
0x18000d556  mov     rcx, rdi; hFindFile
0x18000d559  call    cs:__imp_FindNextFileW
0x18000d55f  lea     ecx, [rbx+2Eh]
0x18000d562  test    eax, eax
0x18000d564  jnz     loc_18000D431
0x18000d56a  call    cs:__imp_GetLastError
0x18000d570  mov     ebx, eax
0x18000d572  mov     ecx, 2Eh ; '.'
0x18000d577  test    eax, eax
0x18000d579  jz      loc_18000D431
0x18000d57f  cmp     eax, 12h
0x18000d582  jz      short loc_18000D59D
0x18000d584  mov     r9d, eax
0x18000d587  lea     r8, [rsp+4E0h+FindFileData.cFileName]
0x18000d58c  lea     rdx, aFindnextfileAf; "FindNextFile after on %ws failed with %"...
0x18000d593  mov     ecx, 1
0x18000d598  call    DsRolepLogPrintRoutine
0x18000d59d  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18000d5a1  jz      short loc_18000D5AC
0x18000d5a3  mov     rcx, rdi; hFindFile
0x18000d5a6  call    cs:__imp_FindClose
0x18000d5ac  test    ebx, ebx
0x18000d5ae  jz      short loc_18000D5B5
0x18000d5b0  cmp     ebx, 12h
0x18000d5b3  jnz     short loc_18000D5B8
0x18000d5b5  mov     ebx, r15d
0x18000d5b8  cmp     [rsp+4E0h+var_4B0], r15b
0x18000d5bd  jz      short loc_18000D5E8
0x18000d5bf  test    ebx, ebx
0x18000d5c1  jnz     short loc_18000D5E8
0x18000d5c3  mov     rcx, rsi; DosPathName
0x18000d5c6  call    DsRolepRemoveDirectoryOrLink
0x18000d5cb  mov     ebx, eax
0x18000d5cd  test    eax, eax
0x18000d5cf  jz      short loc_18000D5E8
0x18000d5d1  mov     r9d, eax
0x18000d5d4  lea     rdx, aRemovalOfPathW; "Removal of path %ws failed with %lu\n"
0x18000d5db  mov     r8, rsi
0x18000d5de  mov     ecx, 1
0x18000d5e3  call    DsRolepLogPrintRoutine
0x18000d5e8  cmp     r14, rsi
0x18000d5eb  jz      short loc_18000D605
0x18000d5ed  mov     rcx, gs:60h
0x18000d5f6  mov     r8, r14; P
0x18000d5f9  xor     edx, edx; Flags
0x18000d5fb  mov     rcx, [rcx+30h]; HeapHandle
0x18000d5ff  call    cs:__imp_RtlFreeHeap
0x18000d605  mov     eax, ebx
0x18000d607  mov     rcx, [rbp+3E0h+var_40]
0x18000d60e  xor     rcx, rsp; StackCookie
0x18000d611  call    __security_check_cookie
0x18000d616  mov     rbx, [rsp+4E0h+arg_10]
0x18000d61e  add     rsp, 4B0h
0x18000d625  pop     r15
0x18000d627  pop     r14
0x18000d629  pop     r13
0x18000d62b  pop     r12
0x18000d62d  pop     rdi
0x18000d62e  pop     rsi
0x18000d62f  pop     rbp
0x18000d630  retn
0x18000d631  mov     edx, 80h; dwFileAttributes
0x18000d636  call    cs:__imp_SetFileAttributesW
0x18000d63c  mov     rcx, rdi; lpFileName
0x18000d63f  call    cs:__imp_DeleteFileW
0x18000d645  xor     r15d, r15d
0x18000d648  test    eax, eax
0x18000d64a  jnz     short loc_18000D677
0x18000d64c  call    cs:__imp_GetLastError
0x18000d652  mov     ebx, eax
0x18000d654  test    eax, eax
0x18000d656  jz      loc_18000D524
0x18000d65c  mov     r9d, eax
0x18000d65f  lea     rdx, aDeletefilewOnW; "DeleteFileW on %ws failed with %lu\n"
0x18000d666  mov     r8, rdi
0x18000d669  lea     ecx, [r15+1]
0x18000d66d  call    DsRolepLogPrintRoutine
0x18000d672  jmp     loc_18000D524
0x18000d677  mov     r8, rdi
0x18000d67a  lea     rdx, aRemovedWs; "\tRemoved %ws\n"
0x18000d681  mov     ecx, 4
0x18000d686  call    DsRolepLogPrintRoutine
0x18000d68b  jmp     loc_18000D524
```
