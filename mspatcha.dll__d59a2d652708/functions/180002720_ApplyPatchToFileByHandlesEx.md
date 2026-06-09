# ApplyPatchToFileByHandlesEx

- ea: `0x180002720`
- end: `0x180003056`
- name: `ApplyPatchToFileByHandlesEx`
- size: `2358`
- prototype: `BOOL __stdcall(HANDLE PatchFileHandle, HANDLE OldFileHandle, HANDLE NewFileHandle, ULONG ApplyOptionFlags, PPATCH_PROGRESS_CALLBACK ProgressCallback, PVOID CallbackContext)`
- caller_count: `4`
- callee_count: `13`
- tags: `file_ops, reparse_path, installer_update, broker_com_uri`

## callers

- `0x1800026f0`
- `0x180003060`
- `0x1800031c0`
- `0x1800048d0`

## callees

- `0x180001cae`
- `0x180002720`
- `0x180003580`
- `0x1800036e0`
- `0x18000380c`
- `0x180004520`
- `0x180004678`
- `0x1800046e0`
- `0x180004940`
- `0x180006d9c`
- `0x180006dd4`
- `0x180006ee8`
- `0x180007054`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000302c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000302c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002a6b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002ad3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002e4d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002fdf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003019`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000303b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002a6b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002ad3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002e4d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002fdf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003019`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000303b`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x180002b2f`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x180002d75`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x180002b2f`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x180002d75`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800028a8`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800028a8`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x18000278f`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x18000278f`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180002af3`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180002f78`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180003004`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180002af3`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180002f78`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180003004`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180002b05`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180002f8e`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180003022`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180002b05`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180002f8e`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180003022`

## pseudocode

```c
BOOL __stdcall ApplyPatchToFileByHandlesEx(
        HANDLE PatchFileHandle,
        HANDLE OldFileHandle,
        HANDLE NewFileHandle,
        ULONG ApplyOptionFlags,
        PPATCH_PROGRESS_CALLBACK ProgressCallback,
        PVOID CallbackContext)
{
  char v6; // r13
  char *v8; // r12
  int NewFileFromPatchData; // esi
  unsigned int v10; // ebx
  LPCVOID v11; // r14
  __int64 SubAllocator; // rax
  int v13; // r14d
  DWORD FileSize; // r15d
  DWORD v15; // eax
  DWORD v16; // edx
  HANDLE v17; // r9
  size_t v18; // rcx
  unsigned int v19; // r11d
  unsigned int *v20; // rdx
  unsigned int v21; // r13d
  unsigned __int64 v22; // rax
  size_t v23; // r8
  unsigned int v24; // eax
  int v25; // r11d
  __int64 v26; // rcx
  int v27; // r8d
  int v28; // eax
  void *v29; // r13
  unsigned int v30; // r12d
  __int64 v31; // rcx
  __int64 v32; // r12
  __int64 v33; // r13
  int v34; // eax
  int v35; // eax
  int v36; // r8d
  int v37; // ecx
  DWORD v38; // ecx
  __int64 v39; // r9
  int v40; // r8d
  bool v41; // zf
  __int64 v42; // rcx
  __int64 v43; // rax
  _QWORD *v44; // rcx
  _QWORD *v45; // rbx
  const void *v47; // [rsp+60h] [rbp-C8h]
  unsigned int v48; // [rsp+90h] [rbp-98h] BYREF
  __int64 v49; // [rsp+98h] [rbp-90h] BYREF
  DWORD v50; // [rsp+A0h] [rbp-88h]
  unsigned int v51; // [rsp+A4h] [rbp-84h] BYREF
  PVOID FileBuffer; // [rsp+A8h] [rbp-80h]
  int v53[2]; // [rsp+B0h] [rbp-78h]
  LPCVOID lpBaseAddress; // [rsp+B8h] [rbp-70h]
  LPVOID v55; // [rsp+C0h] [rbp-68h]
  DWORD FileSizeHigh; // [rsp+C8h] [rbp-60h] BYREF
  unsigned int v57; // [rsp+CCh] [rbp-5Ch]
  struct _FILETIME LastWriteTime; // [rsp+D0h] [rbp-58h] BYREF
  LPVOID lpAddress; // [rsp+D8h] [rbp-50h]
  unsigned int v60; // [rsp+E0h] [rbp-48h] BYREF
  int v61; // [rsp+E4h] [rbp-44h]
  __int64 v62; // [rsp+E8h] [rbp-40h]
  char v65; // [rsp+148h] [rbp+20h]

  v65 = ApplyOptionFlags;
  v6 = ApplyOptionFlags;
  v49 = 0;
  v60 = 0;
  LastWriteTime = 0;
  lpBaseAddress = 0;
  v57 = 0;
  v8 = 0;
  FileBuffer = 0;
  FileSizeHigh = 0;
  NewFileFromPatchData = 0;
  if ( (unsigned int)MyMapViewOfFileByHandle(PatchFileHandle) )
  {
    GetFileTime(PatchFileHandle, 0, 0, &LastWriteTime);
    v48 = 0;
    v10 = v57;
    v11 = lpBaseAddress;
    SafeCompleteCrc32(lpBaseAddress, v57, &v48);
    if ( v48 == -1 )
    {
      SubAllocator = CreateSubAllocator(0x10000);
      v62 = SubAllocator;
      if ( SubAllocator )
      {
        NewFileFromPatchData = DecodePatchHeader((_DWORD)v11, v10, SubAllocator, (unsigned int)&v60, (__int64)&v49);
        if ( !NewFileFromPatchData )
          goto LABEL_101;
        NewFileFromPatchData = ProgressCallbackWrapper(
                                 ProgressCallback,
                                 CallbackContext,
                                 0,
                                 *(unsigned int *)(v49 + 28));
        if ( !NewFileFromPatchData )
          goto LABEL_101;
        v13 = 0;
        NewFileFromPatchData = 0;
        if ( (*(_DWORD *)(v49 + 4) & 0x800000) == 0 && *(_DWORD *)(v49 + 24) )
          LastWriteTime = (struct _FILETIME)(10000000 * (*(unsigned int *)(v49 + 24) + 0x2B6109100LL));
        FileSize = 0;
        v50 = 0;
        v15 = 0;
        FileSizeHigh = 0;
        v16 = 0;
        v17 = OldFileHandle;
        if ( OldFileHandle != (HANDLE)-1LL )
        {
          FileSize = GetFileSize(OldFileHandle, &FileSizeHigh);
          v50 = FileSize;
          v16 = FileSize;
          v15 = FileSizeHigh;
          v17 = OldFileHandle;
        }
        if ( v16 != *(_DWORD *)(v49 + 28) || v15 )
          goto LABEL_44;
        if ( v17 != (HANDLE)-1LL )
        {
          if ( !(unsigned int)MyMapViewOfFileByHandle(v17) )
          {
LABEL_100:
            v11 = lpBaseAddress;
LABEL_101:
            v44 = *(_QWORD **)(v62 + 8);
            do
            {
              v45 = (_QWORD *)*v44;
              VirtualFree(v44, 0, 0x8000u);
              v44 = v45;
            }
            while ( v45 );
            goto LABEL_105;
          }
          v8 = (char *)FileBuffer;
          FileSize = v50;
        }
        lpAddress = 0;
        v51 = 0;
        v18 = *(_QWORD *)(v49 + 40);
        v19 = *(_DWORD *)(v18 + 32);
        v48 = v19;
        v20 = *(unsigned int **)(v18 + 40);
        v55 = v20;
        if ( v19 && (v6 & 4) == 0 )
        {
          lpAddress = (LPVOID)SaveRetainRanges((_DWORD)v8, FileSize, v19, (_DWORD)v20, 1);
          if ( !lpAddress )
            v13 = 1;
          v19 = v48;
          v20 = (unsigned int *)v55;
        }
        if ( v13 )
        {
LABEL_37:
          if ( v8 )
            UnmapViewOfFile(v8);
LABEL_44:
          if ( !v13 )
          {
            *(_QWORD *)v53 = (char *)lpBaseAddress + v60;
            NewFileFromPatchData = 0;
            v30 = 0;
            v48 = 0;
            if ( *(_DWORD *)(v49 + 36) )
            {
              v31 = *(_QWORD *)v53;
              while ( 1 )
              {
                if ( v13 )
                  goto LABEL_100;
                if ( NewFileFromPatchData )
                  goto LABEL_97;
                v32 = 9LL * v30;
                v33 = *(_QWORD *)(v49 + 40);
                if ( *(_DWORD *)(v33 + 8 * v32 + 8) == FileSize )
                  break;
LABEL_96:
                v31 += *(unsigned int *)(v33 + 8 * v32 + 16);
                *(_QWORD *)v53 = v31;
                v30 = v48 + 1;
                v48 = v30;
                if ( v30 >= *(_DWORD *)(v49 + 36) )
                  goto LABEL_97;
              }
              if ( OldFileHandle == (HANDLE)-1LL )
              {
                v34 = 0;
                FileBuffer = 0;
              }
              else
              {
                v35 = MyMapViewOfFileByHandle(OldFileHandle);
                FileSize = v50;
                if ( !v35 )
                {
                  v13 = 1;
LABEL_95:
                  v31 = *(_QWORD *)v53;
                  goto LABEL_96;
                }
                v34 = (int)FileBuffer;
              }
              v55 = 0;
              v36 = *(_DWORD *)(v33 + 8 * v32 + 32);
              if ( v36 )
              {
                if ( (v65 & 4) == 0 )
                {
                  v55 = (LPVOID)SaveRetainRanges(v34, FileSize, v36, *(_QWORD *)(v33 + 8 * v32 + 40), 0);
                  if ( !v55 )
                    v13 = 1;
                }
              }
              if ( v13 )
              {
LABEL_93:
                if ( FileBuffer )
                  UnmapViewOfFile(FileBuffer);
                goto LABEL_95;
              }
              NormalizeOldFileImageForPatching(
                FileBuffer,
                FileSize,
                *(_DWORD *)(v49 + 4),
                0,
                *(_DWORD *)(v49 + 12),
                *(_DWORD *)(v49 + 16),
                *(_DWORD *)(v33 + 8 * v32 + 20),
                *(PPATCH_IGNORE_RANGE *)(v33 + 8 * v32 + 24),
                *(_DWORD *)(v33 + 8 * v32 + 32),
                *(PPATCH_RETAIN_RANGE *)(v33 + 8 * v32 + 40));
              v51 = 0;
              if ( !(unsigned int)SafeCompleteCrc32(FileBuffer, FileSize, &v51)
                || v51 != *(_DWORD *)(v33 + 8 * v32 + 12)
                || FileSize != *(_DWORD *)(v33 + 8 * v32 + 8) )
              {
LABEL_91:
                if ( v55 )
                  VirtualFree(v55, 0, 0x8000u);
                goto LABEL_93;
              }
              v37 = *(_DWORD *)(v49 + 28);
              if ( v37 )
              {
                v39 = *(unsigned int *)(v33 + 8 * v32 + 16);
                if ( (_DWORD)v39 )
                {
                  if ( (v65 & 4) == 0 )
                  {
                    v40 = v53[0];
                    if ( *(_QWORD *)v53 + v39 <= (unsigned __int64)lpBaseAddress + v57 )
                    {
                      if ( *(_DWORD *)(v33 + 48 + 8 * v32) )
                      {
                        NewFileFromPatchData = TransformOldFileImageForPatching(
                                                 (int)v49 + 8,
                                                 (_DWORD)FileBuffer,
                                                 FileSize,
                                                 *(_DWORD *)(v49 + 20),
                                                 v33 + 48 + 8 * v32);
                        LODWORD(v39) = *(_DWORD *)(v33 + 8 * v32 + 16);
                        v40 = v53[0];
                      }
                      else
                      {
                        NewFileFromPatchData = 1;
                      }
                      v41 = NewFileFromPatchData == 0;
                      if ( NewFileFromPatchData )
                      {
                        v42 = *(_QWORD *)(v49 + 48);
                        if ( v42 )
                          v43 = *(_QWORD *)(v42 + 8LL * v48);
                        else
                          v43 = 0;
                        NewFileFromPatchData = CreateNewFileFromPatchData(
                                                 (int)FileBuffer,
                                                 FileSize,
                                                 v40,
                                                 v39,
                                                 NewFileHandle,
                                                 *(_DWORD *)(v49 + 28),
                                                 (__int64)&LastWriteTime,
                                                 *(_DWORD *)(v49 + 32),
                                                 *(_DWORD *)(v33 + 8 * v32 + 32),
                                                 *(_QWORD *)(v33 + 8 * v32 + 40),
                                                 v55,
                                                 *(_DWORD *)(v49 + 4),
                                                 v47,
                                                 *(_DWORD *)(v49 + 56),
                                                 v43,
                                                 (__int64)ProgressCallback,
                                                 (__int64)CallbackContext);
                        v41 = NewFileFromPatchData == 0;
                      }
                      if ( v41 )
                        v13 = 1;
                      goto LABEL_91;
                    }
                    v38 = -1072807674;
                    goto LABEL_79;
                  }
                }
                else
                {
                  if ( FileSize == v37 && (v65 & 2) != 0 )
                    goto LABEL_66;
                  if ( (v65 & 4) == 0 )
                  {
                    NewFileFromPatchData = CreateNewFileFromOldFileMapped(
                                             FileBuffer,
                                             FileSize,
                                             NewFileHandle,
                                             *(_DWORD *)(v49 + 32),
                                             *(_DWORD *)(v33 + 8 * v32 + 32),
                                             *(_QWORD *)(v33 + 8 * v32 + 40),
                                             v55,
                                             (__int64)ProgressCallback,
                                             (__int64)CallbackContext);
                    if ( NewFileFromPatchData )
                      goto LABEL_91;
                    goto LABEL_80;
                  }
                }
              }
              else
              {
                if ( !FileSize && (v65 & 2) != 0 )
                {
LABEL_66:
                  v38 = -1072807675;
LABEL_79:
                  SetLastError(v38);
LABEL_80:
                  v13 = 1;
                  goto LABEL_91;
                }
                if ( (v65 & 4) == 0 )
                  SetFileTime(NewFileHandle, 0, 0, &LastWriteTime);
              }
              NewFileFromPatchData = 1;
              goto LABEL_91;
            }
LABEL_97:
            if ( !v13 && !NewFileFromPatchData )
              SetLastError(0xC00E4104);
          }
          goto LABEL_100;
        }
        v21 = 0;
        v61 = 0;
        while ( v21 < v19 )
        {
          v18 = FileSize;
          v22 = v20[3 * v21 + 2];
          if ( v22 <= FileSize )
          {
            v23 = v20[3 * v21 + 1];
            v18 = FileSize - v22;
            if ( v23 <= v18 )
            {
              memset_0(&v8[v22], 0, v23);
              v19 = v48;
              v20 = (unsigned int *)v55;
            }
          }
          v61 = ++v21;
        }
        v24 = ~(unsigned int)Crc32(v18, v8, FileSize);
        v51 = v24;
        if ( v24 != *(_DWORD *)(v49 + 32) )
        {
          NormalizeOldFileImageForPatching(
            v8,
            FileSize,
            *(_DWORD *)(v49 + 4),
            0,
            *(_DWORD *)(v49 + 12),
            *(_DWORD *)(v49 + 16),
            0,
            0,
            0,
            0);
          v24 = ~(unsigned int)Crc32(v26, v8, FileSize);
          v51 = v24;
          v25 = v48;
        }
        v27 = *(_DWORD *)(v49 + 32);
        if ( v24 == v27 )
        {
          v28 = *(_DWORD *)(v49 + 28);
          if ( FileSize == v28 )
          {
            v13 = 1;
            if ( (v65 & 1) != 0 )
            {
              SetLastError(0xC00E4105);
              NewFileFromPatchData = 0;
            }
            else
            {
              if ( (v65 & 4) == 0 )
              {
                if ( v28 )
                {
                  v29 = lpAddress;
                  NewFileFromPatchData = CreateNewFileFromOldFileMapped(
                                           v8,
                                           FileSize,
                                           NewFileHandle,
                                           v27,
                                           v25,
                                           (__int64)v55,
                                           lpAddress,
                                           (__int64)ProgressCallback,
                                           (__int64)CallbackContext);
LABEL_35:
                  if ( v29 )
                    VirtualFree(v29, 0, 0x8000u);
                  goto LABEL_37;
                }
                SetFileTime(NewFileHandle, 0, 0, &LastWriteTime);
              }
              NewFileFromPatchData = 1;
            }
          }
        }
        v29 = lpAddress;
        goto LABEL_35;
      }
    }
    else
    {
      SetLastError(0xC00E4102);
    }
LABEL_105:
    UnmapViewOfFile(v11);
  }
  if ( !NewFileFromPatchData && !GetLastError() )
    SetLastError(0x4B8u);
  return NewFileFromPatchData;
}

```

## disassembly

```asm
0x180002720  mov     rax, rsp
0x180002723  mov     [rax+20h], r9d
0x180002727  mov     [rax+18h], r8
0x18000272b  mov     [rax+10h], rdx
0x18000272f  push    rbx
0x180002730  push    rsi
0x180002731  push    rdi
0x180002732  push    r12
0x180002734  push    r13
0x180002736  push    r14
0x180002738  push    r15
0x18000273a  sub     rsp, 0F0h
0x180002741  mov     r13d, r9d
0x180002744  mov     rbx, rcx
0x180002747  xor     edi, edi
0x180002749  mov     [rax-90h], rdi
0x180002750  mov     [rax-48h], edi
0x180002753  mov     [rax-58h], rdi
0x180002757  mov     [rax-70h], rdi
0x18000275b  mov     [rax-5Ch], edi
0x18000275e  mov     r12d, edi
0x180002761  mov     [rax-80h], rdi
0x180002765  mov     [rax-60h], edi
0x180002768  mov     esi, edi
0x18000276a  lea     r8, [rax-70h]
0x18000276e  lea     rdx, [rax-5Ch]
0x180002772  call    MyMapViewOfFileByHandle
0x180002777  test    eax, eax
0x180002779  jz      loc_180003028
0x18000277f  lea     r9, [rsp+128h+LastWriteTime]; lpLastWriteTime
0x180002787  xor     r8d, r8d; lpLastAccessTime
0x18000278a  xor     edx, edx; lpCreationTime
0x18000278c  mov     rcx, rbx; hFile
0x18000278f  call    cs:__imp_GetFileTime
0x180002795  mov     [rsp+128h+var_98], edi
0x18000279c  lea     r8, [rsp+128h+var_98]
0x1800027a4  mov     ebx, [rsp+128h+var_5C]
0x1800027ab  mov     edx, ebx
0x1800027ad  mov     r14, [rsp+128h+lpBaseAddress]
0x1800027b5  mov     rcx, r14
0x1800027b8  call    SafeCompleteCrc32
0x1800027bd  cmp     [rsp+128h+var_98], 0FFFFFFFFh
0x1800027c5  jnz     loc_180003014
0x1800027cb  mov     ecx, 10000h
0x1800027d0  call    CreateSubAllocator
0x1800027d5  mov     [rsp+128h+var_40], rax
0x1800027dd  test    rax, rax
0x1800027e0  jz      loc_18000301F
0x1800027e6  lea     rcx, [rsp+128h+var_90]
0x1800027ee  mov     qword ptr [rsp+128h+NewFileCoffBase], rcx
0x1800027f3  lea     r9, [rsp+128h+var_48]
0x1800027fb  mov     r8, rax
0x1800027fe  mov     edx, ebx
0x180002800  mov     rcx, r14
0x180002803  call    DecodePatchHeader
0x180002808  mov     esi, eax
0x18000280a  test    eax, eax
0x18000280c  jz      loc_180002FED
0x180002812  mov     r9, [rsp+128h+var_90]
0x18000281a  mov     r9d, [r9+1Ch]
0x18000281e  xor     r8d, r8d
0x180002821  mov     rdx, [rsp+128h+CallbackContext]
0x180002829  mov     rcx, [rsp+128h+ProgressCallback]
0x180002831  call    ProgressCallbackWrapper
0x180002836  mov     esi, eax
0x180002838  test    eax, eax
0x18000283a  jz      loc_180002FED
0x180002840  mov     r14d, edi
0x180002843  mov     esi, edi
0x180002845  mov     rdx, [rsp+128h+var_90]
0x18000284d  test    dword ptr [rdx+4], 800000h
0x180002854  jnz     short loc_18000287A
0x180002856  cmp     [rdx+18h], edi
0x180002859  jz      short loc_18000287A
0x18000285b  mov     eax, [rdx+18h]
0x18000285e  mov     rcx, 2B6109100h
0x180002868  add     rax, rcx
0x18000286b  imul    rax, 989680h
0x180002872  mov     qword ptr [rsp+128h+LastWriteTime.dwLowDateTime], rax
0x18000287a  mov     r15d, edi
0x18000287d  mov     [rsp+128h+var_88], edi
0x180002884  mov     eax, edi
0x180002886  mov     [rsp+128h+FileSizeHigh], eax
0x18000288d  mov     edx, edi
0x18000288f  mov     r9, [rsp+128h+hFile]
0x180002897  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x18000289b  jz      short loc_1800028C9
0x18000289d  lea     rdx, [rsp+128h+FileSizeHigh]; lpFileSizeHigh
0x1800028a5  mov     rcx, r9; hFile
0x1800028a8  call    cs:__imp_GetFileSize
0x1800028ae  mov     r15d, eax
0x1800028b1  mov     [rsp+128h+var_88], eax
0x1800028b8  mov     edx, eax
0x1800028ba  mov     eax, [rsp+128h+FileSizeHigh]
0x1800028c1  mov     r9, [rsp+128h+hFile]
0x1800028c9  mov     rcx, [rsp+128h+var_90]
0x1800028d1  cmp     edx, [rcx+1Ch]
0x1800028d4  jnz     loc_180002B87
0x1800028da  test    eax, eax
0x1800028dc  jnz     loc_180002B87
0x1800028e2  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x1800028e6  jz      short loc_180002918
0x1800028e8  lea     r8, [rsp+128h+FileBuffer]
0x1800028f0  lea     rdx, [rsp+128h+var_88]
0x1800028f8  mov     rcx, r9; hFile
0x1800028fb  call    MyMapViewOfFileByHandle
0x180002900  test    eax, eax
0x180002902  jz      loc_180002FE5
0x180002908  mov     r12, [rsp+128h+FileBuffer]
0x180002910  mov     r15d, [rsp+128h+var_88]
0x180002918  mov     [rsp+128h+lpAddress], rdi
0x180002920  mov     [rsp+128h+var_84], edi
0x180002927  mov     rax, [rsp+128h+var_90]
0x18000292f  mov     rcx, [rax+28h]
0x180002933  mov     r11d, [rcx+20h]
0x180002937  mov     [rsp+128h+var_98], r11d
0x18000293f  mov     rdx, [rcx+28h]
0x180002943  mov     [rsp+128h+var_68], rdx
0x18000294b  mov     ebx, 1
0x180002950  test    r11d, r11d
0x180002953  jz      short loc_18000298F
0x180002955  test    r13b, 4
0x180002959  jnz     short loc_18000298F
0x18000295b  mov     [rsp+128h+NewFileCoffBase], ebx
0x18000295f  mov     r9, rdx
0x180002962  mov     r8d, r11d
0x180002965  mov     edx, r15d
0x180002968  mov     rcx, r12
0x18000296b  call    SaveRetainRanges
0x180002970  mov     [rsp+128h+lpAddress], rax
0x180002978  test    rax, rax
0x18000297b  cmovz   r14d, ebx
0x18000297f  mov     r11d, [rsp+128h+var_98]
0x180002987  mov     rdx, [rsp+128h+var_68]
0x18000298f  test    r14d, r14d
0x180002992  jnz     loc_180002AF9
0x180002998  mov     r13d, edi
0x18000299b  mov     [rsp+128h+var_44], edi
0x1800029a2  cmp     r13d, r11d
0x1800029a5  jnb     short loc_1800029F0
0x1800029a7  mov     ecx, r15d
0x1800029aa  mov     eax, r13d
0x1800029ad  lea     r8, [rax+rax*2]
0x1800029b1  mov     eax, [rdx+r8*4+8]
0x1800029b6  cmp     rax, rcx
0x1800029b9  ja      short loc_1800029E3
0x1800029bb  mov     r8d, [rdx+r8*4+4]; Size
0x1800029c0  sub     rcx, rax
0x1800029c3  cmp     r8, rcx
0x1800029c6  ja      short loc_1800029E3
0x1800029c8  lea     rcx, [rax+r12]; void *
0x1800029cc  xor     edx, edx; Val
0x1800029ce  call    memset_0
0x1800029d3  mov     r11d, [rsp+128h+var_98]
0x1800029db  mov     rdx, [rsp+128h+var_68]
0x1800029e3  add     r13d, ebx
0x1800029e6  mov     [rsp+128h+var_44], r13d
0x1800029ee  jmp     short loc_1800029A2
0x1800029f0  mov     r8d, r15d
0x1800029f3  mov     rdx, r12
0x1800029f6  call    Crc32
0x1800029fb  not     eax
0x1800029fd  mov     [rsp+128h+var_84], eax
0x180002a04  mov     rdx, [rsp+128h+var_90]
0x180002a0c  cmp     eax, [rdx+20h]
0x180002a0f  jz      short loc_180002A5F
0x180002a11  mov     [rsp+128h+RetainRangeArray], rdi; RetainRangeArray
0x180002a16  mov     [rsp+128h+RetainRangeCount], edi; RetainRangeCount
0x180002a1a  mov     [rsp+128h+IgnoreRangeArray], rdi; IgnoreRangeArray
0x180002a1f  mov     [rsp+128h+IgnoreRangeCount], edi; IgnoreRangeCount
0x180002a23  mov     eax, [rdx+10h]
0x180002a26  mov     [rsp+128h+NewFileCoffTime], eax; NewFileCoffTime
0x180002a2a  mov     eax, [rdx+0Ch]
0x180002a2d  mov     [rsp+128h+NewFileCoffBase], eax; NewFileCoffBase
0x180002a31  xor     r9d, r9d; OptionData
0x180002a34  mov     r8d, [rdx+4]; OptionFlags
0x180002a38  mov     edx, r15d; FileSize
0x180002a3b  mov     rcx, r12; FileBuffer
0x180002a3e  call    NormalizeOldFileImageForPatching
0x180002a43  mov     r8d, r15d
0x180002a46  mov     rdx, r12
0x180002a49  call    Crc32
0x180002a4e  not     eax
0x180002a50  mov     [rsp+128h+var_84], eax
0x180002a57  mov     r11d, [rsp+128h+var_98]
0x180002a5f  mov     rcx, [rsp+128h+var_68]
0x180002a67  jmp     short loc_180002AA2
0x180002a69  mov     ecx, eax; dwErrCode
0x180002a6b  call    cs:__imp_SetLastError
0x180002a71  xor     edi, edi
0x180002a73  lea     ebx, [rdi+1]
0x180002a76  mov     r14d, ebx
0x180002a79  mov     rcx, [rsp+128h+var_68]
0x180002a81  mov     r11d, [rsp+128h+var_98]
0x180002a89  mov     r12, [rsp+128h+FileBuffer]
0x180002a91  mov     r15d, [rsp+128h+var_88]
0x180002a99  mov     eax, [rsp+128h+var_84]
0x180002aa0  mov     esi, edi
0x180002aa2  test    r14d, r14d
0x180002aa5  jnz     short loc_180002ADB
0x180002aa7  mov     rdx, [rsp+128h+var_90]
0x180002aaf  mov     r8d, [rdx+20h]
0x180002ab3  cmp     eax, r8d
0x180002ab6  jnz     short loc_180002ADB
0x180002ab8  mov     eax, [rdx+1Ch]
0x180002abb  cmp     r15d, eax
0x180002abe  jnz     short loc_180002ADB
0x180002ac0  mov     r14d, ebx
0x180002ac3  mov     edx, [rsp+128h+arg_18]
0x180002aca  test    bl, dl
0x180002acc  jz      short loc_180002B0D
0x180002ace  mov     ecx, 0C00E4105h; dwErrCode
0x180002ad3  call    cs:__imp_SetLastError
0x180002ad9  mov     esi, edi
0x180002adb  mov     r13, [rsp+128h+lpAddress]
0x180002ae3  test    r13, r13
0x180002ae6  jz      short loc_180002AF9
0x180002ae8  xor     edx, edx; dwSize
0x180002aea  mov     r8d, 8000h; dwFreeType
0x180002af0  mov     rcx, r13; lpAddress
0x180002af3  call    cs:__imp_VirtualFree
0x180002af9  test    r12, r12
0x180002afc  jz      loc_180002B8C
0x180002b02  mov     rcx, r12; lpBaseAddress
0x180002b05  call    cs:__imp_UnmapViewOfFile
0x180002b0b  jmp     short loc_180002B8C
0x180002b0d  test    dl, 4
0x180002b10  jz      short loc_180002B16
0x180002b12  mov     esi, ebx
0x180002b14  jmp     short loc_180002ADB
0x180002b16  lea     r9, [rsp+128h+LastWriteTime]; lpLastWriteTime
0x180002b1e  test    eax, eax
0x180002b20  jnz     short loc_180002B37
0x180002b22  xor     r8d, r8d; lpLastAccessTime
0x180002b25  xor     edx, edx; lpCreationTime
0x180002b27  mov     rcx, [rsp+128h+arg_10]; hFile
0x180002b2f  call    cs:__imp_SetFileTime
0x180002b35  jmp     short loc_180002B12
0x180002b37  mov     rax, [rsp+128h+CallbackContext]
0x180002b3f  mov     [rsp+128h+RetainRangeArray], rax; __int64
0x180002b44  mov     rax, [rsp+128h+ProgressCallback]
0x180002b4c  mov     qword ptr [rsp+128h+RetainRangeCount], rax; __int64
0x180002b51  mov     r13, [rsp+128h+lpAddress]
0x180002b59  mov     [rsp+128h+IgnoreRangeArray], r13; void *
0x180002b5e  mov     qword ptr [rsp+128h+IgnoreRangeCount], rcx; __int64
0x180002b63  mov     [rsp+128h+NewFileCoffTime], r11d; int
0x180002b68  mov     [rsp+128h+NewFileCoffBase], r8d; int
0x180002b6d  mov     r8, [rsp+128h+arg_10]; hFile
0x180002b75  mov     edx, r15d; lDistanceToMove
0x180002b78  mov     rcx, r12; Src
0x180002b7b  call    CreateNewFileFromOldFileMapped
0x180002b80  mov     esi, eax
0x180002b82  jmp     loc_180002AE3
0x180002b87  mov     ebx, 1
0x180002b8c  test    r14d, r14d
0x180002b8f  jnz     loc_180002FE5
0x180002b95  mov     r12d, [rsp+128h+var_48]
0x180002b9d  add     r12, [rsp+128h+lpBaseAddress]
0x180002ba5  mov     qword ptr [rsp+128h+var_78], r12
0x180002bad  mov     esi, edi
0x180002baf  mov     r12d, edi
0x180002bb2  mov     [rsp+128h+var_98], edi
0x180002bb9  mov     rax, [rsp+128h+var_90]
0x180002bc1  cmp     [rax+24h], edi
0x180002bc4  jbe     loc_180002FD1
0x180002bca  mov     rcx, qword ptr [rsp+128h+var_78]
0x180002bd2  test    r14d, r14d
0x180002bd5  jnz     loc_180002FE5
0x180002bdb  test    esi, esi
0x180002bdd  jnz     loc_180002FD1
0x180002be3  mov     eax, r12d
0x180002be6  lea     r12, [rax+rax*8]
0x180002bea  mov     rax, [rsp+128h+var_90]
0x180002bf2  mov     r13, [rax+28h]
0x180002bf6  cmp     [r13+r12*8+8], r15d
0x180002bfb  jnz     loc_180002F9C
0x180002c01  mov     rax, [rsp+128h+hFile]
0x180002c09  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180002c0d  jnz     short loc_180002C1C
0x180002c0f  mov     rax, rdi
0x180002c12  mov     [rsp+128h+FileBuffer], rax
0x180002c1a  jmp     short loc_180002C50
0x180002c1c  lea     r8, [rsp+128h+FileBuffer]
0x180002c24  lea     rdx, [rsp+128h+var_88]
0x180002c2c  mov     rcx, rax; hFile
0x180002c2f  call    MyMapViewOfFileByHandle
0x180002c34  mov     r15d, [rsp+128h+var_88]
0x180002c3c  test    eax, eax
0x180002c3e  jnz     short loc_180002C48
0x180002c40  mov     r14d, ebx
0x180002c43  jmp     loc_180002F94
0x180002c48  mov     rax, [rsp+128h+FileBuffer]
0x180002c50  mov     [rsp+128h+var_68], rdi
0x180002c58  mov     r8d, [r13+r12*8+20h]
0x180002c5d  test    r8d, r8d
0x180002c60  jz      short loc_180002C8F
0x180002c62  test    byte ptr [rsp+128h+arg_18], 4
0x180002c6a  jnz     short loc_180002C8F
0x180002c6c  mov     [rsp+128h+NewFileCoffBase], edi
0x180002c70  mov     r9, [r13+r12*8+28h]
  ... truncated ...
```
