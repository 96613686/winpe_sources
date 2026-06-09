# CloseMetaFile

- ea: `0x18002ae30`
- end: `0x18002b045`
- name: `CloseMetaFile`
- size: `533`
- prototype: `HMETAFILE __stdcall(HDC hdc)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x18002be20`

## callees

- `0x180023be4`
- `0x180025000`
- `0x180026cf0`
- `0x180028860`
- `0x180029c84`
- `0x18002ae30`
- `0x18002bbc8`
- `0x18002bcec`
- `0x18006c640`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18002aec6`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18002aec6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002af19`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002af50`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b028`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002af19`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002af50`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b028`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002af7a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002afc8`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002af7a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002afc8`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002afa1`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002afa1`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002b01d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002b01d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002afe9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b010`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002afe9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b010`
- `GDI32!GdiSetLastError` at `0x18002b038`
- `GDI32!GdiSetLastError` at `0x18002b038`

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

  v2 = plinkGet(hdc);
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
0x18002ae30  push    rbx
0x18002ae32  push    rbp
0x18002ae33  push    rsi
0x18002ae34  push    rdi
0x18002ae35  push    r12
0x18002ae37  push    r15
0x18002ae39  sub     rsp, 38h
0x18002ae3d  mov     rdi, rcx
0x18002ae40  call    plinkGet
0x18002ae45  mov     rbx, rax
0x18002ae48  test    rax, rax
0x18002ae4b  jnz     loc_18002AF58
0x18002ae51  mov     edx, edi
0x18002ae53  and     edx, 7F0000h
0x18002ae59  cmp     edx, 660000h
0x18002ae5f  jnz     loc_18002B033
0x18002ae65  test    rbx, rbx
0x18002ae68  jz      loc_18002B033
0x18002ae6e  xor     ebp, ebp
0x18002ae70  lea     r12d, [rbp+1]
0x18002ae74  test    [rbx+2Ah], r12b
0x18002ae78  jnz     short loc_18002AEF5
0x18002ae7a  xor     r9d, r9d
0x18002ae7d  xor     r8d, r8d
0x18002ae80  xor     edx, edx
0x18002ae82  mov     rcx, rdi
0x18002ae85  call    RecordParms
0x18002ae8a  test    eax, eax
0x18002ae8c  jz      short loc_18002AEF5
0x18002ae8e  mov     rcx, [rbx]
0x18002ae91  lea     rsi, [rbx+18h]
0x18002ae95  lea     r15d, [rbp+2]
0x18002ae99  cmp     [rsi], r15w
0x18002ae9d  jz      loc_18002AF61
0x18002aea3  movups  xmm0, xmmword ptr [rsi]
0x18002aea6  movups  xmmword ptr [rcx], xmm0
0x18002aea9  movzx   eax, word ptr [rsi+10h]
0x18002aead  mov     [rcx+10h], ax
0x18002aeb1  cmp     dword ptr [rbx+1Eh], 7FFFFFFFh
0x18002aeb8  jnb     short loc_18002AEF5
0x18002aeba  mov     edx, [rbx+1Eh]
0x18002aebd  mov     r8d, r15d; uFlags
0x18002aec0  mov     rcx, [rbx]; hMem
0x18002aec3  add     rdx, rdx; uBytes
0x18002aec6  call    cs:__imp_LocalReAlloc
0x18002aecc  test    rax, rax
0x18002aecf  jz      short loc_18002AEF5
0x18002aed1  mov     [rbx], rax
0x18002aed4  cmp     [rsi], r15w
0x18002aed8  jz      loc_18002AFFC
0x18002aede  mov     rcx, [rbx]
0x18002aee1  call    SetMetaFileBitsAlt
0x18002aee6  mov     rbp, rax
0x18002aee9  test    rax, rax
0x18002aeec  jz      short loc_18002AEF5
0x18002aeee  mov     qword ptr [rbx], 0
0x18002aef5  cmp     qword ptr [rbx+30h], 0
0x18002aefa  jnz     short loc_18002AF44
0x18002aefc  mov     rcx, [rbx+8]; hObject
0x18002af00  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002af04  jnz     loc_18002B010
0x18002af0a  mov     rcx, [rbx]; hMem
0x18002af0d  test    rcx, rcx
0x18002af10  jnz     loc_18002B028
0x18002af16  mov     rcx, rbx; hMem
0x18002af19  call    cs:__imp_LocalFree
0x18002af1f  mov     rcx, rdi
0x18002af22  call    bDeleteClientObjLink
0x18002af27  mov     rcx, rdi; void *
0x18002af2a  call    GdiTrackHDelete
0x18002af2f  mov     rcx, rbp
0x18002af32  call    GdiTrackHCreate
0x18002af37  add     rsp, 38h
0x18002af3b  pop     r15
0x18002af3d  pop     r12
0x18002af3f  pop     rdi
0x18002af40  pop     rsi
0x18002af41  pop     rbp
0x18002af42  pop     rbx
0x18002af43  retn
0x18002af44  mov     rcx, rdi
0x18002af47  call    UnlistObjects
0x18002af4c  mov     rcx, [rbx+30h]; hMem
0x18002af50  call    cs:__imp_LocalFree
0x18002af56  jmp     short loc_18002AEFC
0x18002af58  mov     rbx, [rax+20h]
0x18002af5c  jmp     loc_18002AE51
0x18002af61  mov     r8d, [rbx+14h]; nNumberOfBytesToWrite
0x18002af65  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18002af6a  mov     rdx, rcx; lpBuffer
0x18002af6d  mov     [rsp+68h+NumberOfBytesWritten], ebp
0x18002af71  mov     rcx, [rbx+8]; hFile
0x18002af75  mov     [rsp+68h+lpOverlapped], rbp; lpOverlapped
0x18002af7a  call    cs:__imp_WriteFile
0x18002af80  test    eax, eax
0x18002af82  jz      loc_18002AEF5
0x18002af88  mov     eax, [rbx+14h]
0x18002af8b  cmp     [rsp+68h+NumberOfBytesWritten], eax
0x18002af8f  jnz     loc_18002AEF5
0x18002af95  mov     rcx, [rbx+8]; hFile
0x18002af99  xor     r9d, r9d; dwMoveMethod
0x18002af9c  xor     r8d, r8d; lpDistanceToMoveHigh
0x18002af9f  xor     edx, edx; lDistanceToMove
0x18002afa1  call    cs:__imp_SetFilePointer
0x18002afa7  test    eax, eax
0x18002afa9  jnz     loc_18002AEF5
0x18002afaf  mov     rcx, [rbx+8]; hFile
0x18002afb3  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18002afb8  lea     r8d, [rax+12h]; nNumberOfBytesToWrite
0x18002afbc  mov     [rsi], r12w
0x18002afc0  mov     rdx, rsi; lpBuffer
0x18002afc3  mov     [rsp+68h+lpOverlapped], rbp; lpOverlapped
0x18002afc8  call    cs:__imp_WriteFile
0x18002afce  mov     [rsi], r15w
0x18002afd2  test    eax, eax
0x18002afd4  jz      loc_18002AEF5
0x18002afda  cmp     [rsp+68h+NumberOfBytesWritten], 12h
0x18002afdf  jnz     loc_18002AEF5
0x18002afe5  mov     rcx, [rbx+8]; hObject
0x18002afe9  call    cs:__imp_CloseHandle
0x18002afef  mov     qword ptr [rbx+8], 0FFFFFFFFFFFFFFFFh
0x18002aff7  jmp     loc_18002AED4
0x18002affc  lea     rcx, [rbx+0ACh]; lpName
0x18002b003  call    GetMetaFileW
0x18002b008  mov     rbp, rax
0x18002b00b  jmp     loc_18002AEF5
0x18002b010  call    cs:__imp_CloseHandle
0x18002b016  lea     rcx, [rbx+0ACh]; lpFileName
0x18002b01d  call    cs:__imp_DeleteFileW
0x18002b023  jmp     loc_18002AF0A
0x18002b028  call    cs:__imp_LocalFree
0x18002b02e  jmp     loc_18002AF16
0x18002b033  mov     ecx, 6
0x18002b038  call    cs:__imp_GdiSetLastError
0x18002b03e  xor     eax, eax
0x18002b040  jmp     loc_18002AF37
```
