# CreateMetaFileW

- ea: `0x180067300`
- end: `0x1800674e2`
- name: `CreateMetaFileW`
- size: `482`
- prototype: `HDC __stdcall(LPCWSTR pszFile)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18002be20`
- `0x180067270`

## callees

- `0x180023cb0`
- `0x180026cf0`
- `0x180029150`
- `0x180067300`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180067317`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006749f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180067317`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006749f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180067467`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180067470`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180067467`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180067470`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800673c1`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800673c1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180067405`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180067436`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180067405`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180067436`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180067459`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180067459`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067450`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067450`
- `GDI32!pGdiSharedMemory` at `0x180067329`
- `GDI32!GdiSetLastError` at `0x180067487`
- `GDI32!GdiSetLastError` at `0x180067487`

## pseudocode

```c
HDC __stdcall CreateMetaFileW(LPCWSTR pszFile)
{
  char *v2; // rax
  char *v3; // rdi
  DWORD FullPathNameW; // eax
  __int16 v5; // si
  HANDLE FileW; // rax
  HANDLE v7; // rax
  void *v8; // rcx
  HLOCAL v10; // rax
  __int64 ClientObjLink; // rax
  LPWSTR FilePart; // [rsp+78h] [rbp+10h] BYREF

  v2 = (char *)LocalAlloc(0x40u, 0x2B8u);
  v3 = v2;
  if ( !v2 )
    return 0;
  *((_QWORD *)v2 + 1) = -1;
  *((_DWORD *)v2 + 4) = 0x4000;
  *(_DWORD *)(v2 + 26) = 50331657;
  *((_QWORD *)v2 + 7) = *(_QWORD *)(pGdiSharedMemory + 1573096LL);
  *((_QWORD *)v2 + 8) = *(_QWORD *)(pGdiSharedMemory + 1573040LL);
  *((_QWORD *)v2 + 12) = *(_QWORD *)(pGdiSharedMemory + 1573152LL);
  *((_QWORD *)v2 + 13) = *(_QWORD *)(pGdiSharedMemory + 1573208LL);
  *((_QWORD *)v2 + 14) = 0;
  *((_QWORD *)v2 + 11) = *(_QWORD *)(pGdiSharedMemory + 1573160LL);
  if ( !pszFile )
  {
    v5 = 1;
    goto LABEL_15;
  }
  FilePart = 0;
  FullPathNameW = GetFullPathNameW(pszFile, 0x104u, (LPWSTR)v2 + 86, &FilePart);
  if ( !FullPathNameW )
  {
LABEL_7:
    v8 = (void *)*((_QWORD *)v3 + 1);
    if ( v8 != (void *)-1LL )
    {
      CloseHandle(v8);
      DeleteFileW((LPCWSTR)v3 + 86);
    }
    if ( *(_QWORD *)v3 )
      LocalFree(*(HLOCAL *)v3);
    LocalFree(v3);
    return 0;
  }
  if ( FullPathNameW > 0x104 )
  {
    GdiSetLastError(206);
    goto LABEL_7;
  }
  *(_WORD *)&v3[2 * FullPathNameW + 172] = 0;
  v5 = 2;
  FileW = CreateFileW((LPCWSTR)v3 + 86, 0x40000000u, 0, 0, 2u, 0x80u, 0);
  *((_QWORD *)v3 + 1) = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    v7 = CreateFileW((LPCWSTR)v3 + 86, 0x40000000u, 3u, 0, 2u, 0x80u, 0);
    *((_QWORD *)v3 + 1) = v7;
    if ( v7 == (HANDLE)-1LL )
      goto LABEL_7;
  }
LABEL_15:
  *((_WORD *)v3 + 12) = v5;
  v10 = LocalAlloc(0, 0x4000u);
  *(_QWORD *)v3 = v10;
  if ( !v10 )
    goto LABEL_7;
  if ( !(unsigned int)AttemptWrite(v3, 18, v3 + 24) )
    goto LABEL_7;
  ClientObjLink = hCreateClientObjLink(v3, 6684672);
  if ( !ClientObjLink )
    goto LABEL_7;
  return (HDC)GdiTrackHCreate(ClientObjLink);
}

```

## disassembly

```asm
0x180067300  push    rbx
0x180067302  push    rsi
0x180067303  push    rdi
0x180067304  push    r14
0x180067306  sub     rsp, 48h
0x18006730a  mov     rsi, rcx
0x18006730d  mov     edx, 2B8h; uBytes
0x180067312  mov     ecx, 40h ; '@'; uFlags
0x180067317  call    cs:__imp_LocalAlloc
0x18006731d  mov     rdi, rax
0x180067320  test    rax, rax
0x180067323  jz      loc_180067476
0x180067329  mov     rdx, cs:__imp_pGdiSharedMemory
0x180067330  lea     rbx, [rdi+0ACh]
0x180067337  mov     qword ptr [rax+8], 0FFFFFFFFFFFFFFFFh
0x18006733f  mov     dword ptr [rax+10h], 4000h
0x180067346  mov     dword ptr [rax+1Ah], 3000009h
0x18006734d  mov     rax, [rdx]
0x180067350  mov     rcx, [rax+1800E8h]
0x180067357  mov     [rdi+38h], rcx
0x18006735b  mov     rax, [rdx]
0x18006735e  mov     rcx, [rax+1800B0h]
0x180067365  mov     [rdi+40h], rcx
0x180067369  mov     rax, [rdx]
0x18006736c  mov     rcx, [rax+180120h]
0x180067373  mov     [rdi+60h], rcx
0x180067377  mov     rax, [rdx]
0x18006737a  mov     rcx, [rax+180158h]
0x180067381  mov     [rdi+68h], rcx
0x180067385  mov     qword ptr [rdi+70h], 0
0x18006738d  mov     rax, [rdx]
0x180067390  mov     rcx, [rax+180128h]
0x180067397  mov     [rdi+58h], rcx
0x18006739b  test    rsi, rsi
0x18006739e  jz      loc_18006748F
0x1800673a4  mov     r14d, 104h
0x1800673aa  mov     [rsp+68h+FilePart], 0
0x1800673b3  mov     edx, r14d; nBufferLength
0x1800673b6  lea     r9, [rsp+68h+FilePart]; lpFilePart
0x1800673bb  mov     r8, rbx; lpBuffer
0x1800673be  mov     rcx, rsi; lpFileName
0x1800673c1  call    cs:__imp_GetFullPathNameW
0x1800673c7  test    eax, eax
0x1800673c9  jz      short loc_180067446
0x1800673cb  cmp     eax, r14d
0x1800673ce  ja      loc_180067482
0x1800673d4  mov     ecx, eax
0x1800673d6  mov     r14d, 80h
0x1800673dc  xor     eax, eax
0x1800673de  xor     r9d, r9d; lpSecurityAttributes
0x1800673e1  mov     [rsp+68h+hTemplateFile], rax; hTemplateFile
0x1800673e6  xor     r8d, r8d; dwShareMode
0x1800673e9  mov     [rsp+68h+dwFlagsAndAttributes], r14d; dwFlagsAndAttributes
0x1800673ee  mov     edx, 40000000h; dwDesiredAccess
0x1800673f3  mov     [rdi+rcx*2+0ACh], ax
0x1800673fb  mov     rcx, rbx; lpFileName
0x1800673fe  lea     esi, [rax+2]
0x180067401  mov     [rsp+68h+dwCreationDisposition], esi; dwCreationDisposition
0x180067405  call    cs:__imp_CreateFileW
0x18006740b  mov     [rdi+8], rax
0x18006740f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180067413  jnz     short loc_180067494
0x180067415  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18006741e  lea     r8d, [r14-7Dh]; dwShareMode
0x180067422  mov     [rsp+68h+dwFlagsAndAttributes], r14d; dwFlagsAndAttributes
0x180067427  xor     r9d, r9d; lpSecurityAttributes
0x18006742a  mov     edx, 40000000h; dwDesiredAccess
0x18006742f  mov     [rsp+68h+dwCreationDisposition], esi; dwCreationDisposition
0x180067433  mov     rcx, rbx; lpFileName
0x180067436  call    cs:__imp_CreateFileW
0x18006743c  mov     [rdi+8], rax
0x180067440  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180067444  jnz     short loc_180067494
0x180067446  mov     rcx, [rdi+8]; hObject
0x18006744a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18006744e  jz      short loc_18006745F
0x180067450  call    cs:__imp_CloseHandle
0x180067456  mov     rcx, rbx; lpFileName
0x180067459  call    cs:__imp_DeleteFileW
0x18006745f  mov     rcx, [rdi]; hMem
0x180067462  test    rcx, rcx
0x180067465  jz      short loc_18006746D
0x180067467  call    cs:__imp_LocalFree
0x18006746d  mov     rcx, rdi; hMem
0x180067470  call    cs:__imp_LocalFree
0x180067476  xor     eax, eax
0x180067478  add     rsp, 48h
0x18006747c  pop     r14
0x18006747e  pop     rdi
0x18006747f  pop     rsi
0x180067480  pop     rbx
0x180067481  retn
0x180067482  mov     ecx, 0CEh
0x180067487  call    cs:__imp_GdiSetLastError
0x18006748d  jmp     short loc_180067446
0x18006748f  mov     esi, 1
0x180067494  mov     edx, 4000h; uBytes
0x180067499  mov     [rdi+18h], si
0x18006749d  xor     ecx, ecx; uFlags
0x18006749f  call    cs:__imp_LocalAlloc
0x1800674a5  mov     [rdi], rax
0x1800674a8  test    rax, rax
0x1800674ab  jz      short loc_180067446
0x1800674ad  lea     r8, [rdi+18h]
0x1800674b1  mov     edx, 12h
0x1800674b6  mov     rcx, rdi
0x1800674b9  call    AttemptWrite
0x1800674be  test    eax, eax
0x1800674c0  jz      short loc_180067446
0x1800674c2  mov     edx, 660000h
0x1800674c7  mov     rcx, rdi
0x1800674ca  call    hCreateClientObjLink
0x1800674cf  test    rax, rax
0x1800674d2  jz      loc_180067446
0x1800674d8  mov     rcx, rax
0x1800674db  call    GdiTrackHCreate
0x1800674e0  jmp     short loc_180067478
```
