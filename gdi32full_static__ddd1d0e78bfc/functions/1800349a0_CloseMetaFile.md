# CloseMetaFile

- ea: `0x1800349a0`
- end: `0x180034bfc`
- name: `CloseMetaFile`
- size: `604`
- prototype: `HMETAFILE __stdcall(HDC hdc)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x1800363f0`

## callees

- `0x18002cb60`
- `0x18002e090`
- `0x18002fda0`
- `0x180031ca0`
- `0x180033474`
- `0x1800349a0`
- `0x180035f10`
- `0x1800362b0`
- `0x180071070`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x180034a3a`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x180034a3a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034a93`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034ad1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034bd3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034a93`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034ad1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034bd3`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180034b01`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180034b5b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180034b01`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180034b5b`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180034b2e`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180034b2e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180034bc2`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180034bc2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034b82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034baf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034b82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034baf`
- `GDI32!GdiSetLastError` at `0x180034be9`
- `GDI32!GdiSetLastError` at `0x180034be9`

## pseudocode

```c
HMETAFILE __stdcall CloseMetaFile(HDC hdc)
{
  __int64 v2; // rax
  __int64 v3; // rbx
  HMETAFILE MetaFileW; // rbp
  _WORD *v5; // rcx
  _WORD *v6; // rsi
  HLOCAL v7; // rax
  void *v8; // rcx
  DWORD v10; // r8d
  _WORD *v11; // rdx
  void *v12; // rcx
  BOOL v13; // eax
  DWORD NumberOfBytesWritten; // [rsp+70h] [rbp+8h] BYREF

  v2 = plinkGet();
  v3 = v2;
  if ( v2 )
    v3 = *(_QWORD *)(v2 + 32);
  if ( ((unsigned int)hdc & 0x7F0000) != 0x660000 || !v3 )
  {
    GdiSetLastError(6);
    return 0;
  }
  MetaFileW = 0;
  if ( (*(_BYTE *)(v3 + 42) & 1) == 0 && (unsigned int)RecordParms(hdc, 0, 0, 0) )
  {
    v5 = *(_WORD **)v3;
    v6 = (_WORD *)(v3 + 24);
    if ( *(_WORD *)(v3 + 24) == 2 )
    {
      v10 = *(_DWORD *)(v3 + 20);
      v11 = *(_WORD **)v3;
      NumberOfBytesWritten = 0;
      if ( WriteFile(*(HANDLE *)(v3 + 8), v11, v10, &NumberOfBytesWritten, 0) )
      {
        if ( NumberOfBytesWritten == *(_DWORD *)(v3 + 20) && !SetFilePointer(*(HANDLE *)(v3 + 8), 0, 0, 0) )
        {
          v12 = *(void **)(v3 + 8);
          *v6 = 1;
          v13 = WriteFile(v12, (LPCVOID)(v3 + 24), 0x12u, &NumberOfBytesWritten, 0);
          *v6 = 2;
          if ( v13 )
          {
            if ( NumberOfBytesWritten == 18 )
            {
              CloseHandle(*(HANDLE *)(v3 + 8));
              *(_QWORD *)(v3 + 8) = -1;
LABEL_11:
              if ( *v6 == 2 )
              {
                MetaFileW = GetMetaFileW((LPCWSTR)(v3 + 172));
              }
              else
              {
                MetaFileW = (HMETAFILE)SetMetaFileBitsAlt(*(_QWORD *)v3);
                if ( MetaFileW )
                  *(_QWORD *)v3 = 0;
              }
            }
          }
        }
      }
    }
    else
    {
      *(_OWORD *)v5 = *(_OWORD *)v6;
      v5[8] = *(_WORD *)(v3 + 40);
      if ( *(_DWORD *)(v3 + 30) < 0x7FFFFFFFu )
      {
        v7 = LocalReAlloc(*(HLOCAL *)v3, 2LL * *(unsigned int *)(v3 + 30), 2u);
        if ( v7 )
        {
          *(_QWORD *)v3 = v7;
          goto LABEL_11;
        }
      }
    }
  }
  if ( *(_QWORD *)(v3 + 48) )
  {
    UnlistObjects(hdc);
    LocalFree(*(HLOCAL *)(v3 + 48));
  }
  v8 = *(void **)(v3 + 8);
  if ( v8 != (void *)-1LL )
  {
    CloseHandle(v8);
    DeleteFileW((LPCWSTR)(v3 + 172));
  }
  if ( *(_QWORD *)v3 )
    LocalFree(*(HLOCAL *)v3);
  LocalFree((HLOCAL)v3);
  bDeleteClientObjLink(hdc);
  GdiTrackHDelete(hdc);
  return (HMETAFILE)GdiTrackHCreate(MetaFileW);
}

```

## disassembly

```asm
0x1800349a0  push    rbx
0x1800349a2  push    rbp
0x1800349a3  push    rsi
0x1800349a4  push    rdi
0x1800349a5  push    r12
0x1800349a7  push    r15
0x1800349a9  sub     rsp, 38h
0x1800349ad  mov     rdi, rcx
0x1800349b0  call    plinkGet
0x1800349b5  mov     rbx, rax
0x1800349b8  test    rax, rax
0x1800349bb  jnz     loc_180034ADF
0x1800349c1  mov     edx, edi
0x1800349c3  and     edx, 7F0000h
0x1800349c9  cmp     edx, 660000h
0x1800349cf  jnz     loc_180034BE4
0x1800349d5  test    rbx, rbx
0x1800349d8  jz      loc_180034BE4
0x1800349de  xor     ebp, ebp
0x1800349e0  lea     r12d, [rbp+1]
0x1800349e4  test    [rbx+2Ah], r12b
0x1800349e8  jnz     loc_180034A6F
0x1800349ee  xor     r9d, r9d
0x1800349f1  xor     r8d, r8d
0x1800349f4  xor     edx, edx
0x1800349f6  mov     rcx, rdi
0x1800349f9  call    RecordParms
0x1800349fe  test    eax, eax
0x180034a00  jz      short loc_180034A6F
0x180034a02  mov     rcx, [rbx]
0x180034a05  lea     rsi, [rbx+18h]
0x180034a09  lea     r15d, [rbp+2]
0x180034a0d  cmp     [rsi], r15w
0x180034a11  jz      loc_180034AE8
0x180034a17  movups  xmm0, xmmword ptr [rsi]
0x180034a1a  movups  xmmword ptr [rcx], xmm0
0x180034a1d  movzx   eax, word ptr [rsi+10h]
0x180034a21  mov     [rcx+10h], ax
0x180034a25  cmp     dword ptr [rbx+1Eh], 7FFFFFFFh
0x180034a2c  jnb     short loc_180034A6F
0x180034a2e  mov     edx, [rbx+1Eh]
0x180034a31  mov     r8d, r15d; uFlags
0x180034a34  mov     rcx, [rbx]; hMem
0x180034a37  add     rdx, rdx; uBytes
0x180034a3a  call    cs:__imp_LocalReAlloc
0x180034a41  nop     dword ptr [rax+rax+00h]
0x180034a46  test    rax, rax
0x180034a49  jz      short loc_180034A6F
0x180034a4b  mov     [rbx], rax
0x180034a4e  cmp     [rsi], r15w
0x180034a52  jz      loc_180034B9B
0x180034a58  mov     rcx, [rbx]
0x180034a5b  call    SetMetaFileBitsAlt
0x180034a60  mov     rbp, rax
0x180034a63  test    rax, rax
0x180034a66  jz      short loc_180034A6F
0x180034a68  mov     qword ptr [rbx], 0
0x180034a6f  cmp     qword ptr [rbx+30h], 0
0x180034a74  jnz     short loc_180034AC5
0x180034a76  mov     rcx, [rbx+8]; hObject
0x180034a7a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180034a7e  jnz     loc_180034BAF
0x180034a84  mov     rcx, [rbx]; hMem
0x180034a87  test    rcx, rcx
0x180034a8a  jnz     loc_180034BD3
0x180034a90  mov     rcx, rbx; hMem
0x180034a93  call    cs:__imp_LocalFree
0x180034a9a  nop     dword ptr [rax+rax+00h]
0x180034a9f  mov     rcx, rdi
0x180034aa2  call    bDeleteClientObjLink
0x180034aa7  mov     rcx, rdi; void *
0x180034aaa  call    GdiTrackHDelete
0x180034aaf  mov     rcx, rbp
0x180034ab2  call    GdiTrackHCreate
0x180034ab7  add     rsp, 38h
0x180034abb  pop     r15
0x180034abd  pop     r12
0x180034abf  pop     rdi
0x180034ac0  pop     rsi
0x180034ac1  pop     rbp
0x180034ac2  pop     rbx
0x180034ac3  retn
0x180034ac5  mov     rcx, rdi
0x180034ac8  call    UnlistObjects
0x180034acd  mov     rcx, [rbx+30h]; hMem
0x180034ad1  call    cs:__imp_LocalFree
0x180034ad8  nop     dword ptr [rax+rax+00h]
0x180034add  jmp     short loc_180034A76
0x180034adf  mov     rbx, [rax+20h]
0x180034ae3  jmp     loc_1800349C1
0x180034ae8  mov     r8d, [rbx+14h]; nNumberOfBytesToWrite
0x180034aec  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180034af1  mov     rdx, rcx; lpBuffer
0x180034af4  mov     [rsp+68h+NumberOfBytesWritten], ebp
0x180034af8  mov     rcx, [rbx+8]; hFile
0x180034afc  mov     [rsp+68h+lpOverlapped], rbp; lpOverlapped
0x180034b01  call    cs:__imp_WriteFile
0x180034b08  nop     dword ptr [rax+rax+00h]
0x180034b0d  test    eax, eax
0x180034b0f  jz      loc_180034A6F
0x180034b15  mov     eax, [rbx+14h]
0x180034b18  cmp     [rsp+68h+NumberOfBytesWritten], eax
0x180034b1c  jnz     loc_180034A6F
0x180034b22  mov     rcx, [rbx+8]; hFile
0x180034b26  xor     r9d, r9d; dwMoveMethod
0x180034b29  xor     r8d, r8d; lpDistanceToMoveHigh
0x180034b2c  xor     edx, edx; lDistanceToMove
0x180034b2e  call    cs:__imp_SetFilePointer
0x180034b35  nop     dword ptr [rax+rax+00h]
0x180034b3a  test    eax, eax
0x180034b3c  jnz     loc_180034A6F
0x180034b42  mov     rcx, [rbx+8]; hFile
0x180034b46  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180034b4b  lea     r8d, [rax+12h]; nNumberOfBytesToWrite
0x180034b4f  mov     [rsi], r12w
0x180034b53  mov     rdx, rsi; lpBuffer
0x180034b56  mov     [rsp+68h+lpOverlapped], rbp; lpOverlapped
0x180034b5b  call    cs:__imp_WriteFile
0x180034b62  nop     dword ptr [rax+rax+00h]
0x180034b67  mov     [rsi], r15w
0x180034b6b  test    eax, eax
0x180034b6d  jz      loc_180034A6F
0x180034b73  cmp     [rsp+68h+NumberOfBytesWritten], 12h
0x180034b78  jnz     loc_180034A6F
0x180034b7e  mov     rcx, [rbx+8]; hObject
0x180034b82  call    cs:__imp_CloseHandle
0x180034b89  nop     dword ptr [rax+rax+00h]
0x180034b8e  mov     qword ptr [rbx+8], 0FFFFFFFFFFFFFFFFh
0x180034b96  jmp     loc_180034A4E
0x180034b9b  lea     rcx, [rbx+0ACh]; lpName
0x180034ba2  call    GetMetaFileW
0x180034ba7  mov     rbp, rax
0x180034baa  jmp     loc_180034A6F
0x180034baf  call    cs:__imp_CloseHandle
0x180034bb6  nop     dword ptr [rax+rax+00h]
0x180034bbb  lea     rcx, [rbx+0ACh]; lpFileName
0x180034bc2  call    cs:__imp_DeleteFileW
0x180034bc9  nop     dword ptr [rax+rax+00h]
0x180034bce  jmp     loc_180034A84
0x180034bd3  call    cs:__imp_LocalFree
0x180034bda  nop     dword ptr [rax+rax+00h]
0x180034bdf  jmp     loc_180034A90
0x180034be4  mov     ecx, 6
0x180034be9  call    cs:__imp_GdiSetLastError
0x180034bf0  nop     dword ptr [rax+rax+00h]
0x180034bf5  xor     eax, eax
0x180034bf7  jmp     loc_180034AB7
```
