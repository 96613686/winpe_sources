# pmfAllocMF(ulong,ulong const *,ushort const *,void *,unsigned __int64,void *)

- ea: `0x180028bac`
- end: `0x180028f11`
- name: `?pmfAllocMF@@YAPEAVMF@@KPEFBKPEBGPEAX_K2@Z`
- size: `869`
- prototype: `struct MF *(unsigned int, const unsigned int *, const unsigned __int16 *, void *, unsigned __int64, void *)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180028ae0`
- `0x180028f18`
- `0x18002a8b0`

## callees

- `0x1800255c4`
- `0x180026cf0`
- `0x180028bac`
- `0x180029790`
- `0x180029cc0`
- `0x18002ad20`
- `0x1800a3514`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028bf1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028c62`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028e1a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028bf1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028c62`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180028e1a`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180028d0c`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180028d0c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180028d4d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180028d4d`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180028d69`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180028d69`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180028dd0`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180028dd0`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180028da7`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180028da7`
- `GDI32!GdiSetLastError` at `0x180028ee7`
- `GDI32!GdiSetLastError` at `0x180028ee7`

## pseudocode

```c
struct MF *__fastcall pmfAllocMF(
        char a1,
        const unsigned int *a2,
        const unsigned __int16 *a3,
        void *a4,
        unsigned __int64 a5,
        void *a6)
{
  __int64 v6; // r15
  char *v12; // rax
  char *v13; // rbx
  int v14; // r13d
  HLOCAL v15; // rax
  __int64 LowPart; // rcx
  LPVOID v17; // rax
  __int64 v18; // rax
  DWORD FullPathNameW; // eax
  HANDLE FileW; // rax
  HANDLE FileMappingW; // rax
  HLOCAL v22; // rax
  HDC DCA; // rax
  HDC v24; // rax
  __int64 v25; // rcx
  _LARGE_INTEGER FileSize; // [rsp+40h] [rbp-48h] BYREF
  LPWSTR FilePart; // [rsp+48h] [rbp-40h] BYREF

  v6 = 0;
  if ( !gbDisableMetaFiles )
  {
    v12 = (char *)LocalAlloc(0x40u, 0x2E0u);
    v13 = v12;
    if ( v12 )
    {
      *(_DWORD *)v12 = 17997;
      v14 = 0;
      *((_QWORD *)v12 + 1) = -1;
      *((_QWORD *)v12 + 2) = 0;
      *((_QWORD *)v12 + 3) = 0;
      *((_QWORD *)v12 + 4) = 0;
      *((_QWORD *)v12 + 16) = a6;
      *((_DWORD *)v12 + 34) = 0;
      *((_QWORD *)v12 + 86) = 0;
      *((_DWORD *)v12 + 170) = 0;
      *((_QWORD *)v12 + 91) = 0;
      if ( a3 )
      {
        FilePart = 0;
        FileSize.QuadPart = 0;
        *((_DWORD *)v12 + 170) = 1;
        FullPathNameW = GetFullPathNameW(a3, 0x104u, (LPWSTR)v12 + 78, &FilePart);
        if ( !FullPathNameW )
          goto LABEL_11;
        if ( FullPathNameW > 0x104 )
        {
          GdiSetLastError(206);
          goto LABEL_11;
        }
        *(_WORD *)&v13[2 * FullPathNameW + 156] = 0;
        FileW = CreateFileW((LPCWSTR)v13 + 78, 0x80000000, 1u, 0, 3u, 0, 0);
        *((_QWORD *)v13 + 1) = FileW;
        if ( FileW == (HANDLE)-1LL
          || !GetFileSizeEx(FileW, &FileSize)
          || FileSize.QuadPart > 0xFFFFFFFFuLL
          || (FileMappingW = CreateFileMappingW(*((HANDLE *)v13 + 1), 0, 2u, FileSize.HighPart, FileSize.LowPart, 0),
              (*((_QWORD *)v13 + 2) = FileMappingW) == 0)
          || (v17 = MapViewOfFile(FileMappingW, 4u, 0, 0, FileSize.LowPart), (*((_QWORD *)v13 + 3) = v17) == 0) )
        {
LABEL_11:
          if ( (a1 & 1) == 0 )
            goto LABEL_12;
          goto LABEL_34;
        }
        LowPart = FileSize.LowPart;
      }
      else
      {
        if ( (a1 & 1) != 0 )
        {
          if ( a2 )
          {
            v25 = a2[12];
            *((_QWORD *)v12 + 7) = v25;
            *((_DWORD *)v12 + 16) = v25;
            *((_DWORD *)v12 + 10) = 0;
            *((_QWORD *)v12 + 6) = a2;
            *((_QWORD *)v12 + 14) = 0;
            *((_QWORD *)v12 + 10) = 0;
            *(_QWORD *)(v12 + 92) = 0;
            *((_QWORD *)v12 + 13) = 0;
            *((_QWORD *)v12 + 4) = a2;
          }
          else
          {
            if ( !a4 || !(unsigned int)EMFContainer::Init((EMFContainer *)(v12 + 40), a4, a5, 0) )
            {
LABEL_34:
              *((_QWORD *)v13 + 4) = 0;
LABEL_12:
              if ( v14 )
                *((_QWORD *)v13 + 1) = -1;
              goto LABEL_14;
            }
            v14 = 1;
            *((_QWORD *)v13 + 1) = a4;
          }
          goto LABEL_9;
        }
        v15 = LocalAlloc(0, a2[12]);
        *((_QWORD *)v13 + 4) = v15;
        if ( !v15 )
        {
LABEL_14:
          vFreeMF(v13);
          return (struct MF *)v6;
        }
        memcpy_0(v15, a2, a2[12]);
        LowPart = a2[12];
        v17 = (LPVOID)*((_QWORD *)v13 + 4);
      }
      *((_QWORD *)v13 + 13) = 0;
      *(_QWORD *)(v13 + 92) = 0;
      *((_QWORD *)v13 + 10) = 0;
      *((_QWORD *)v13 + 14) = 0;
      *((_DWORD *)v13 + 16) = LowPart;
      *((_QWORD *)v13 + 7) = LowPart;
      *((_QWORD *)v13 + 6) = v17;
      *((_DWORD *)v13 + 10) = 0;
LABEL_9:
      v18 = *((_QWORD *)v13 + 6);
      if ( v18 )
      {
        if ( *(_DWORD *)(v18 + 40) == 1179469088 && *(_DWORD *)v18 == 1 )
        {
          if ( *(_WORD *)(v18 + 56) )
          {
            if ( (*(_BYTE *)(v18 + 48) & 3) == 0 )
            {
              v22 = LocalAlloc(0x40u, 8LL * *(unsigned __int16 *)(v18 + 56));
              *((_QWORD *)v13 + 86) = v22;
              if ( v22 )
              {
                DCA = bCreateDCA("DISPLAY", 0, 0, 0, 1);
                v24 = (HDC)GdiTrackHCreate(DCA);
                *((_QWORD *)v13 + 91) = v24;
                if ( v24 )
                {
                  if ( SetGraphicsMode(v24, 2) )
                    return (struct MF *)v13;
                }
              }
            }
          }
        }
      }
      goto LABEL_11;
    }
  }
  return (struct MF *)v6;
}

```

## disassembly

```asm
0x180028bac  push    rbx
0x180028bae  push    rbp
0x180028baf  push    rdi
0x180028bb0  push    r12
0x180028bb2  push    r13
0x180028bb4  push    r14
0x180028bb6  push    r15
0x180028bb8  sub     rsp, 50h
0x180028bbc  xor     r15d, r15d
0x180028bbf  mov     rbp, r9
0x180028bc2  cmp     cs:gbDisableMetaFiles, r15d
0x180028bc9  mov     r14, r8
0x180028bcc  mov     rdi, rdx
0x180028bcf  mov     r12d, ecx
0x180028bd2  jz      short loc_180028BE7
0x180028bd4  mov     rax, r15
0x180028bd7  add     rsp, 50h
0x180028bdb  pop     r15
0x180028bdd  pop     r14
0x180028bdf  pop     r13
0x180028be1  pop     r12
0x180028be3  pop     rdi
0x180028be4  pop     rbp
0x180028be5  pop     rbx
0x180028be6  retn
0x180028be7  mov     edx, 2E0h; uBytes
0x180028bec  mov     ecx, 40h ; '@'; uFlags
0x180028bf1  call    cs:__imp_LocalAlloc
0x180028bf7  xor     r8d, r8d
0x180028bfa  mov     rbx, rax
0x180028bfd  test    rax, rax
0x180028c00  jz      short loc_180028BD4
0x180028c02  mov     dword ptr [rax], 464Dh
0x180028c08  mov     r13d, r8d
0x180028c0b  mov     qword ptr [rax+8], 0FFFFFFFFFFFFFFFFh
0x180028c13  mov     [rax+10h], r8
0x180028c17  mov     [rax+18h], r8
0x180028c1b  mov     [rax+20h], r8
0x180028c1f  mov     rax, [rsp+88h+arg_28]
0x180028c27  mov     [rbx+80h], rax
0x180028c2e  mov     [rbx+88h], r8d
0x180028c35  mov     [rbx+2B0h], r8
0x180028c3c  mov     [rbx+2A8h], r8d
0x180028c43  mov     [rbx+2D8h], r8
0x180028c4a  test    r14, r14
0x180028c4d  jnz     loc_180028CDF
0x180028c53  test    r12b, 1
0x180028c57  jnz     loc_180028E86
0x180028c5d  mov     edx, [rdi+30h]; uBytes
0x180028c60  xor     ecx, ecx; uFlags
0x180028c62  call    cs:__imp_LocalAlloc
0x180028c68  mov     [rbx+20h], rax
0x180028c6c  test    rax, rax
0x180028c6f  jz      short loc_180028CD2
0x180028c71  mov     r8d, [rdi+30h]; Size
0x180028c75  mov     rdx, rdi; Src
0x180028c78  mov     rcx, rax; void *
0x180028c7b  call    memcpy_0
0x180028c80  mov     ecx, [rdi+30h]
0x180028c83  xor     r8d, r8d
0x180028c86  mov     rax, [rbx+20h]
0x180028c8a  mov     [rbx+68h], r8
0x180028c8e  mov     [rbx+5Ch], r8
0x180028c92  mov     [rbx+50h], r8
0x180028c96  mov     [rbx+70h], r8
0x180028c9a  mov     [rbx+40h], ecx
0x180028c9d  mov     [rbx+38h], rcx
0x180028ca1  mov     [rbx+30h], rax
0x180028ca5  mov     [rbx+28h], r8d
0x180028ca9  mov     rax, [rbx+30h]
0x180028cad  test    rax, rax
0x180028cb0  jz      short loc_180028CBF
0x180028cb2  cmp     dword ptr [rax+28h], 464D4520h
0x180028cb9  jz      loc_180028DEF
0x180028cbf  test    r12b, 1
0x180028cc3  jnz     loc_180028ED9
0x180028cc9  test    r13d, r13d
0x180028ccc  jnz     loc_180028F04
0x180028cd2  mov     rcx, rbx; hMem
0x180028cd5  call    ?vFreeMF@@YAXPEAVMF@@@Z; vFreeMF(MF *)
0x180028cda  jmp     loc_180028BD4
0x180028cdf  mov     [rsp+88h+FilePart], r8
0x180028ce4  lea     rdi, [rbx+9Ch]
0x180028ceb  mov     qword ptr [rsp+88h+FileSize], r8
0x180028cf0  lea     r9, [rsp+88h+FilePart]; lpFilePart
0x180028cf5  mov     ebp, 104h
0x180028cfa  mov     dword ptr [rbx+2A8h], 1
0x180028d04  mov     r8, rdi; lpBuffer
0x180028d07  mov     edx, ebp; nBufferLength
0x180028d09  mov     rcx, r14; lpFileName
0x180028d0c  call    cs:__imp_GetFullPathNameW
0x180028d12  xor     r8d, r8d
0x180028d15  test    eax, eax
0x180028d17  jz      short loc_180028CBF
0x180028d19  cmp     eax, ebp
0x180028d1b  ja      loc_180028EE2
0x180028d21  mov     [rsp+88h+hTemplateFile], r8; hTemplateFile
0x180028d26  xor     r9d, r9d; lpSecurityAttributes
0x180028d29  mov     edx, eax
0x180028d2b  mov     rcx, rdi; lpFileName
0x180028d2e  mov     [rsp+88h+dwFlagsAndAttributes], r8d; dwFlagsAndAttributes
0x180028d33  mov     [rsp+88h+dwCreationDisposition], 3; dwCreationDisposition
0x180028d3b  mov     [rbx+rdx*2+9Ch], r8w
0x180028d44  mov     edx, 80000000h; dwDesiredAccess
0x180028d49  lea     r8d, [r9+1]; dwShareMode
0x180028d4d  call    cs:__imp_CreateFileW
0x180028d53  mov     [rbx+8], rax
0x180028d57  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180028d5b  jz      loc_180028EED
0x180028d61  lea     rdx, [rsp+88h+FileSize]; lpFileSize
0x180028d66  mov     rcx, rax; hFile
0x180028d69  call    cs:__imp_GetFileSizeEx
0x180028d6f  xor     r8d, r8d
0x180028d72  test    eax, eax
0x180028d74  jz      loc_180028CBF
0x180028d7a  mov     rax, qword ptr [rsp+88h+FileSize]
0x180028d7f  mov     ecx, 0FFFFFFFFh
0x180028d84  cmp     rax, rcx
0x180028d87  ja      loc_180028CBF
0x180028d8d  mov     rcx, [rbx+8]; hFile
0x180028d91  xor     edx, edx; lpFileMappingAttributes
0x180028d93  mov     qword ptr [rsp+88h+dwFlagsAndAttributes], r8; lpName
0x180028d98  mov     r9, rax
0x180028d9b  shr     r9, 20h; dwMaximumSizeHigh
0x180028d9f  mov     [rsp+88h+dwCreationDisposition], eax; dwMaximumSizeLow
0x180028da3  lea     r8d, [rdx+2]; flProtect
0x180028da7  call    cs:__imp_CreateFileMappingW
0x180028dad  xor     r8d, r8d; dwFileOffsetHigh
0x180028db0  mov     [rbx+10h], rax
0x180028db4  mov     rcx, rax; hFileMappingObject
0x180028db7  test    rax, rax
0x180028dba  jz      loc_180028CBF
0x180028dc0  mov     eax, dword ptr [rsp+88h+FileSize]
0x180028dc4  lea     edx, [r8+4]; dwDesiredAccess
0x180028dc8  xor     r9d, r9d; dwFileOffsetLow
0x180028dcb  mov     qword ptr [rsp+88h+dwCreationDisposition], rax; dwNumberOfBytesToMap
0x180028dd0  call    cs:__imp_MapViewOfFile
0x180028dd6  xor     r8d, r8d
0x180028dd9  mov     [rbx+18h], rax
0x180028ddd  test    rax, rax
0x180028de0  jz      loc_180028CBF
0x180028de6  mov     ecx, dword ptr [rsp+88h+FileSize]
0x180028dea  jmp     loc_180028C8A
0x180028def  cmp     dword ptr [rax], 1
0x180028df2  jnz     loc_180028CBF
0x180028df8  cmp     [rax+38h], r8w
0x180028dfd  jz      loc_180028CBF
0x180028e03  test    byte ptr [rax+30h], 3
0x180028e07  jnz     loc_180028CBF
0x180028e0d  movzx   edx, word ptr [rax+38h]
0x180028e11  mov     ecx, 40h ; '@'; uFlags
0x180028e16  shl     rdx, 3; uBytes
0x180028e1a  call    cs:__imp_LocalAlloc
0x180028e20  xor     r8d, r8d; PCSZ
0x180028e23  mov     [rbx+2B0h], rax
0x180028e2a  test    rax, rax
0x180028e2d  jz      loc_180028CBF
0x180028e33  xor     r9d, r9d; DEVMODEA *
0x180028e36  mov     [rsp+88h+dwCreationDisposition], 1; int
0x180028e3e  xor     edx, edx; Source
0x180028e40  lea     rcx, String1; "DISPLAY"
0x180028e47  call    ?bCreateDCA@@YAPEAUHDC__@@PEBD00PEAU_devicemodeA@@H@Z; bCreateDCA(char const *,char const *,char const *,_devicemodeA *,int)
0x180028e4c  mov     rcx, rax
0x180028e4f  call    GdiTrackHCreate
0x180028e54  xor     r8d, r8d
0x180028e57  mov     [rbx+2D8h], rax
0x180028e5e  test    rax, rax
0x180028e61  jz      loc_180028CBF
0x180028e67  lea     edx, [r8+2]; iMode
0x180028e6b  mov     rcx, rax; hdc
0x180028e6e  call    SetGraphicsMode
0x180028e73  xor     r8d, r8d
0x180028e76  test    eax, eax
0x180028e78  jz      loc_180028CBF
0x180028e7e  mov     r15, rbx
0x180028e81  jmp     loc_180028BD4
0x180028e86  test    rdi, rdi
0x180028e89  jz      short loc_180028EB6
0x180028e8b  mov     ecx, [rdi+30h]
0x180028e8e  mov     [rbx+38h], rcx
0x180028e92  mov     [rbx+40h], ecx
0x180028e95  mov     [rbx+28h], r8d
0x180028e99  mov     [rbx+30h], rdi
0x180028e9d  mov     [rbx+70h], r8
0x180028ea1  mov     [rbx+50h], r8
0x180028ea5  mov     [rbx+5Ch], r8
0x180028ea9  mov     [rbx+68h], r8
0x180028ead  mov     [rbx+20h], rdi
0x180028eb1  jmp     loc_180028CA9
0x180028eb6  test    rbp, rbp
0x180028eb9  jz      short loc_180028ED9
0x180028ebb  mov     r8, [rsp+88h+arg_20]; unsigned __int64
0x180028ec3  lea     rcx, [rbx+28h]; this
0x180028ec7  xor     r9d, r9d; unsigned __int64
0x180028eca  mov     rdx, rbp; hFile
0x180028ecd  call    ?Init@EMFContainer@@QEAAHPEAX_K1@Z; EMFContainer::Init(void *,unsigned __int64,unsigned __int64)
0x180028ed2  xor     r8d, r8d
0x180028ed5  test    eax, eax
0x180028ed7  jnz     short loc_180028EF5
0x180028ed9  mov     [rbx+20h], r8
0x180028edd  jmp     loc_180028CC9
0x180028ee2  mov     ecx, 0CEh
0x180028ee7  call    cs:__imp_GdiSetLastError
0x180028eed  xor     r8d, r8d
0x180028ef0  jmp     loc_180028CBF
0x180028ef5  mov     r13d, 1
0x180028efb  mov     [rbx+8], rbp
0x180028eff  jmp     loc_180028CA9
0x180028f04  mov     qword ptr [rbx+8], 0FFFFFFFFFFFFFFFFh
0x180028f0c  jmp     loc_180028CD2
```
