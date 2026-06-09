# CreateMetaFileW

- ea: `0x18006b9e0`
- end: `0x18006bc0f`
- name: `CreateMetaFileW`
- size: `559`
- prototype: `HDC __stdcall(LPCWSTR pszFile)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800363f0`
- `0x18006b940`

## callees

- `0x18002cc34`
- `0x18002fda0`
- `0x18003286c`
- `0x18006b9e0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006b9f7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006bbbe`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006b9f7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006bbbe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006bb73`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006bb82`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006bb73`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006bb82`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18006baa7`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18006baa7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006baf5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006bb30`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006baf5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006bb30`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18006bb5f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18006bb5f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006bb50`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006bb50`
- `GDI32!pGdiSharedMemory` at `0x18006ba0f`
- `GDI32!GdiSetLastError` at `0x18006bba0`
- `GDI32!GdiSetLastError` at `0x18006bba0`

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
0x18006b9e0  push    rbx
0x18006b9e2  push    rsi
0x18006b9e3  push    rdi
0x18006b9e4  push    r14
0x18006b9e6  sub     rsp, 48h
0x18006b9ea  mov     rsi, rcx
0x18006b9ed  mov     edx, 2B8h; uBytes
0x18006b9f2  mov     ecx, 40h ; '@'; uFlags
0x18006b9f7  call    cs:__imp_LocalAlloc
0x18006b9fe  nop     dword ptr [rax+rax+00h]
0x18006ba03  mov     rdi, rax
0x18006ba06  test    rax, rax
0x18006ba09  jz      loc_18006BB8E
0x18006ba0f  mov     rdx, cs:__imp_pGdiSharedMemory
0x18006ba16  lea     rbx, [rdi+0ACh]
0x18006ba1d  mov     qword ptr [rax+8], 0FFFFFFFFFFFFFFFFh
0x18006ba25  mov     dword ptr [rax+10h], 4000h
0x18006ba2c  mov     dword ptr [rax+1Ah], 3000009h
0x18006ba33  mov     rax, [rdx]
0x18006ba36  mov     rcx, [rax+1800E8h]
0x18006ba3d  mov     [rdi+38h], rcx
0x18006ba41  mov     rax, [rdx]
0x18006ba44  mov     rcx, [rax+1800B0h]
0x18006ba4b  mov     [rdi+40h], rcx
0x18006ba4f  mov     rax, [rdx]
0x18006ba52  mov     rcx, [rax+180120h]
0x18006ba59  mov     [rdi+60h], rcx
0x18006ba5d  mov     rax, [rdx]
0x18006ba60  mov     rcx, [rax+180158h]
0x18006ba67  mov     [rdi+68h], rcx
0x18006ba6b  mov     qword ptr [rdi+70h], 0
0x18006ba73  mov     rax, [rdx]
0x18006ba76  mov     rcx, [rax+180128h]
0x18006ba7d  mov     [rdi+58h], rcx
0x18006ba81  test    rsi, rsi
0x18006ba84  jz      loc_18006BBAE
0x18006ba8a  mov     r14d, 104h
0x18006ba90  mov     [rsp+68h+FilePart], 0
0x18006ba99  mov     edx, r14d; nBufferLength
0x18006ba9c  lea     r9, [rsp+68h+FilePart]; lpFilePart
0x18006baa1  mov     r8, rbx; lpBuffer
0x18006baa4  mov     rcx, rsi; lpFileName
0x18006baa7  call    cs:__imp_GetFullPathNameW
0x18006baae  nop     dword ptr [rax+rax+00h]
0x18006bab3  test    eax, eax
0x18006bab5  jz      loc_18006BB46
0x18006babb  cmp     eax, r14d
0x18006babe  ja      loc_18006BB9B
0x18006bac4  mov     ecx, eax
0x18006bac6  mov     r14d, 80h
0x18006bacc  xor     eax, eax
0x18006bace  xor     r9d, r9d; lpSecurityAttributes
0x18006bad1  mov     [rsp+68h+hTemplateFile], rax; hTemplateFile
0x18006bad6  xor     r8d, r8d; dwShareMode
0x18006bad9  mov     [rsp+68h+dwFlagsAndAttributes], r14d; dwFlagsAndAttributes
0x18006bade  mov     edx, 40000000h; dwDesiredAccess
0x18006bae3  mov     [rdi+rcx*2+0ACh], ax
0x18006baeb  mov     rcx, rbx; lpFileName
0x18006baee  lea     esi, [rax+2]
0x18006baf1  mov     [rsp+68h+dwCreationDisposition], esi; dwCreationDisposition
0x18006baf5  call    cs:__imp_CreateFileW
0x18006bafc  nop     dword ptr [rax+rax+00h]
0x18006bb01  mov     [rdi+8], rax
0x18006bb05  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006bb09  jnz     loc_18006BBB3
0x18006bb0f  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18006bb18  lea     r8d, [r14-7Dh]; dwShareMode
0x18006bb1c  mov     [rsp+68h+dwFlagsAndAttributes], r14d; dwFlagsAndAttributes
0x18006bb21  xor     r9d, r9d; lpSecurityAttributes
0x18006bb24  mov     edx, 40000000h; dwDesiredAccess
0x18006bb29  mov     [rsp+68h+dwCreationDisposition], esi; dwCreationDisposition
0x18006bb2d  mov     rcx, rbx; lpFileName
0x18006bb30  call    cs:__imp_CreateFileW
0x18006bb37  nop     dword ptr [rax+rax+00h]
0x18006bb3c  mov     [rdi+8], rax
0x18006bb40  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006bb44  jnz     short loc_18006BBB3
0x18006bb46  mov     rcx, [rdi+8]; hObject
0x18006bb4a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18006bb4e  jz      short loc_18006BB6B
0x18006bb50  call    cs:__imp_CloseHandle
0x18006bb57  nop     dword ptr [rax+rax+00h]
0x18006bb5c  mov     rcx, rbx; lpFileName
0x18006bb5f  call    cs:__imp_DeleteFileW
0x18006bb66  nop     dword ptr [rax+rax+00h]
0x18006bb6b  mov     rcx, [rdi]; hMem
0x18006bb6e  test    rcx, rcx
0x18006bb71  jz      short loc_18006BB7F
0x18006bb73  call    cs:__imp_LocalFree
0x18006bb7a  nop     dword ptr [rax+rax+00h]
0x18006bb7f  mov     rcx, rdi; hMem
0x18006bb82  call    cs:__imp_LocalFree
0x18006bb89  nop     dword ptr [rax+rax+00h]
0x18006bb8e  xor     eax, eax
0x18006bb90  add     rsp, 48h
0x18006bb94  pop     r14
0x18006bb96  pop     rdi
0x18006bb97  pop     rsi
0x18006bb98  pop     rbx
0x18006bb99  retn
0x18006bb9b  mov     ecx, 0CEh
0x18006bba0  call    cs:__imp_GdiSetLastError
0x18006bba7  nop     dword ptr [rax+rax+00h]
0x18006bbac  jmp     short loc_18006BB46
0x18006bbae  mov     esi, 1
0x18006bbb3  mov     edx, 4000h; uBytes
0x18006bbb8  mov     [rdi+18h], si
0x18006bbbc  xor     ecx, ecx; uFlags
0x18006bbbe  call    cs:__imp_LocalAlloc
0x18006bbc5  nop     dword ptr [rax+rax+00h]
0x18006bbca  mov     [rdi], rax
0x18006bbcd  test    rax, rax
0x18006bbd0  jz      loc_18006BB46
0x18006bbd6  lea     r8, [rdi+18h]
0x18006bbda  mov     edx, 12h
0x18006bbdf  mov     rcx, rdi
0x18006bbe2  call    AttemptWrite
0x18006bbe7  test    eax, eax
0x18006bbe9  jz      loc_18006BB46
0x18006bbef  mov     edx, 660000h
0x18006bbf4  mov     rcx, rdi
0x18006bbf7  call    hCreateClientObjLink
0x18006bbfc  test    rax, rax
0x18006bbff  jz      loc_18006BB46
0x18006bc05  mov     rcx, rax
0x18006bc08  call    GdiTrackHCreate
0x18006bc0d  jmp     short loc_18006BB90
```
