# pmfAllocMF(ulong,ulong const *,ushort const *,void *,unsigned __int64,void *)

- ea: `0x180032004`
- end: `0x1800323a0`
- name: `?pmfAllocMF@@YAPEAVMF@@KPEFBKPEBGPEAX_K2@Z`
- size: `924`
- prototype: `struct MF *(unsigned int, const unsigned int *, const unsigned __int16 *, void *, unsigned __int64, void *)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180031f30`
- `0x18003261c`
- `0x1800343a0`

## callees

- `0x18002e514`
- `0x18002fda0`
- `0x180032004`
- `0x180032f20`
- `0x1800334b8`
- `0x180034884`
- `0x1800a68d4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003204a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800320c1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003229d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003204a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800320c1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003229d`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180032171`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180032171`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800321b8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800321b8`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800321da`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800321da`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18003224d`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18003224d`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18003221e`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18003221e`
- `GDI32!GdiSetLastError` at `0x180032370`
- `GDI32!GdiSetLastError` at `0x180032370`

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
0x180032004  push    rbx
0x180032006  push    rbp
0x180032007  push    rdi
0x180032008  push    r12
0x18003200a  push    r13
0x18003200c  push    r14
0x18003200e  push    r15
0x180032010  sub     rsp, 50h
0x180032014  xor     r15d, r15d
0x180032017  mov     rbp, r9
0x18003201a  cmp     cs:gbDisableMetaFiles, r15d
0x180032021  mov     r14, r8
0x180032024  mov     rdi, rdx
0x180032027  mov     r12d, ecx
0x18003202a  jz      short loc_180032040
0x18003202c  mov     rax, r15
0x18003202f  add     rsp, 50h
0x180032033  pop     r15
0x180032035  pop     r14
0x180032037  pop     r13
0x180032039  pop     r12
0x18003203b  pop     rdi
0x18003203c  pop     rbp
0x18003203d  pop     rbx
0x18003203e  retn
0x180032040  mov     edx, 2E0h; uBytes
0x180032045  mov     ecx, 40h ; '@'; uFlags
0x18003204a  call    cs:__imp_LocalAlloc
0x180032051  nop     dword ptr [rax+rax+00h]
0x180032056  xor     r8d, r8d
0x180032059  mov     rbx, rax
0x18003205c  test    rax, rax
0x18003205f  jz      short loc_18003202C
0x180032061  mov     dword ptr [rax], 464Dh
0x180032067  mov     r13d, r8d
0x18003206a  mov     qword ptr [rax+8], 0FFFFFFFFFFFFFFFFh
0x180032072  mov     [rax+10h], r8
0x180032076  mov     [rax+18h], r8
0x18003207a  mov     [rax+20h], r8
0x18003207e  mov     rax, [rsp+88h+arg_28]
0x180032086  mov     [rbx+80h], rax
0x18003208d  mov     [rbx+88h], r8d
0x180032094  mov     [rbx+2B0h], r8
0x18003209b  mov     [rbx+2A8h], r8d
0x1800320a2  mov     [rbx+2D8h], r8
0x1800320a9  test    r14, r14
0x1800320ac  jnz     loc_180032144
0x1800320b2  test    r12b, 1
0x1800320b6  jnz     loc_18003230F
0x1800320bc  mov     edx, [rdi+30h]; uBytes
0x1800320bf  xor     ecx, ecx; uFlags
0x1800320c1  call    cs:__imp_LocalAlloc
0x1800320c8  nop     dword ptr [rax+rax+00h]
0x1800320cd  mov     [rbx+20h], rax
0x1800320d1  test    rax, rax
0x1800320d4  jz      short loc_180032137
0x1800320d6  mov     r8d, [rdi+30h]; Size
0x1800320da  mov     rdx, rdi; Src
0x1800320dd  mov     rcx, rax; void *
0x1800320e0  call    memcpy_0
0x1800320e5  mov     ecx, [rdi+30h]
0x1800320e8  xor     r8d, r8d
0x1800320eb  mov     rax, [rbx+20h]
0x1800320ef  mov     [rbx+68h], r8
0x1800320f3  mov     [rbx+5Ch], r8
0x1800320f7  mov     [rbx+50h], r8
0x1800320fb  mov     [rbx+70h], r8
0x1800320ff  mov     [rbx+40h], ecx
0x180032102  mov     [rbx+38h], rcx
0x180032106  mov     [rbx+30h], rax
0x18003210a  mov     [rbx+28h], r8d
0x18003210e  mov     rax, [rbx+30h]
0x180032112  test    rax, rax
0x180032115  jz      short loc_180032124
0x180032117  cmp     dword ptr [rax+28h], 464D4520h
0x18003211e  jz      loc_180032272
0x180032124  test    r12b, 1
0x180032128  jnz     loc_180032362
0x18003212e  test    r13d, r13d
0x180032131  jnz     loc_180032393
0x180032137  mov     rcx, rbx; hMem
0x18003213a  call    ?vFreeMF@@YAXPEAVMF@@@Z; vFreeMF(MF *)
0x18003213f  jmp     loc_18003202C
0x180032144  mov     [rsp+88h+FilePart], r8
0x180032149  lea     rdi, [rbx+9Ch]
0x180032150  mov     qword ptr [rsp+88h+FileSize], r8
0x180032155  lea     r9, [rsp+88h+FilePart]; lpFilePart
0x18003215a  mov     ebp, 104h
0x18003215f  mov     dword ptr [rbx+2A8h], 1
0x180032169  mov     r8, rdi; lpBuffer
0x18003216c  mov     edx, ebp; nBufferLength
0x18003216e  mov     rcx, r14; lpFileName
0x180032171  call    cs:__imp_GetFullPathNameW
0x180032178  nop     dword ptr [rax+rax+00h]
0x18003217d  xor     r8d, r8d
0x180032180  test    eax, eax
0x180032182  jz      short loc_180032124
0x180032184  cmp     eax, ebp
0x180032186  ja      loc_18003236B
0x18003218c  mov     [rsp+88h+hTemplateFile], r8; hTemplateFile
0x180032191  xor     r9d, r9d; lpSecurityAttributes
0x180032194  mov     edx, eax
0x180032196  mov     rcx, rdi; lpFileName
0x180032199  mov     [rsp+88h+dwFlagsAndAttributes], r8d; dwFlagsAndAttributes
0x18003219e  mov     [rsp+88h+dwCreationDisposition], 3; dwCreationDisposition
0x1800321a6  mov     [rbx+rdx*2+9Ch], r8w
0x1800321af  mov     edx, 80000000h; dwDesiredAccess
0x1800321b4  lea     r8d, [r9+1]; dwShareMode
0x1800321b8  call    cs:__imp_CreateFileW
0x1800321bf  nop     dword ptr [rax+rax+00h]
0x1800321c4  mov     [rbx+8], rax
0x1800321c8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800321cc  jz      loc_18003237C
0x1800321d2  lea     rdx, [rsp+88h+FileSize]; lpFileSize
0x1800321d7  mov     rcx, rax; hFile
0x1800321da  call    cs:__imp_GetFileSizeEx
0x1800321e1  nop     dword ptr [rax+rax+00h]
0x1800321e6  xor     r8d, r8d
0x1800321e9  test    eax, eax
0x1800321eb  jz      loc_180032124
0x1800321f1  mov     rax, qword ptr [rsp+88h+FileSize]
0x1800321f6  mov     ecx, 0FFFFFFFFh
0x1800321fb  cmp     rax, rcx
0x1800321fe  ja      loc_180032124
0x180032204  mov     rcx, [rbx+8]; hFile
0x180032208  xor     edx, edx; lpFileMappingAttributes
0x18003220a  mov     qword ptr [rsp+88h+dwFlagsAndAttributes], r8; lpName
0x18003220f  mov     r9, rax
0x180032212  shr     r9, 20h; dwMaximumSizeHigh
0x180032216  mov     [rsp+88h+dwCreationDisposition], eax; dwMaximumSizeLow
0x18003221a  lea     r8d, [rdx+2]; flProtect
0x18003221e  call    cs:__imp_CreateFileMappingW
0x180032225  nop     dword ptr [rax+rax+00h]
0x18003222a  xor     r8d, r8d; dwFileOffsetHigh
0x18003222d  mov     [rbx+10h], rax
0x180032231  mov     rcx, rax; hFileMappingObject
0x180032234  test    rax, rax
0x180032237  jz      loc_180032124
0x18003223d  mov     eax, dword ptr [rsp+88h+FileSize]
0x180032241  lea     edx, [r8+4]; dwDesiredAccess
0x180032245  xor     r9d, r9d; dwFileOffsetLow
0x180032248  mov     qword ptr [rsp+88h+dwCreationDisposition], rax; dwNumberOfBytesToMap
0x18003224d  call    cs:__imp_MapViewOfFile
0x180032254  nop     dword ptr [rax+rax+00h]
0x180032259  xor     r8d, r8d
0x18003225c  mov     [rbx+18h], rax
0x180032260  test    rax, rax
0x180032263  jz      loc_180032124
0x180032269  mov     ecx, dword ptr [rsp+88h+FileSize]
0x18003226d  jmp     loc_1800320EF
0x180032272  cmp     dword ptr [rax], 1
0x180032275  jnz     loc_180032124
0x18003227b  cmp     [rax+38h], r8w
0x180032280  jz      loc_180032124
0x180032286  test    byte ptr [rax+30h], 3
0x18003228a  jnz     loc_180032124
0x180032290  movzx   edx, word ptr [rax+38h]
0x180032294  mov     ecx, 40h ; '@'; uFlags
0x180032299  shl     rdx, 3; uBytes
0x18003229d  call    cs:__imp_LocalAlloc
0x1800322a4  nop     dword ptr [rax+rax+00h]
0x1800322a9  xor     r8d, r8d; PCSZ
0x1800322ac  mov     [rbx+2B0h], rax
0x1800322b3  test    rax, rax
0x1800322b6  jz      loc_180032124
0x1800322bc  xor     r9d, r9d; DEVMODEA *
0x1800322bf  mov     [rsp+88h+dwCreationDisposition], 1; int
0x1800322c7  xor     edx, edx; Source
0x1800322c9  lea     rcx, String1; "DISPLAY"
0x1800322d0  call    ?bCreateDCA@@YAPEAUHDC__@@PEBD00PEAU_devicemodeA@@H@Z; bCreateDCA(char const *,char const *,char const *,_devicemodeA *,int)
0x1800322d5  mov     rcx, rax
0x1800322d8  call    GdiTrackHCreate
0x1800322dd  xor     r8d, r8d
0x1800322e0  mov     [rbx+2D8h], rax
0x1800322e7  test    rax, rax
0x1800322ea  jz      loc_180032124
0x1800322f0  lea     edx, [r8+2]; iMode
0x1800322f4  mov     rcx, rax; hdc
0x1800322f7  call    SetGraphicsMode
0x1800322fc  xor     r8d, r8d
0x1800322ff  test    eax, eax
0x180032301  jz      loc_180032124
0x180032307  mov     r15, rbx
0x18003230a  jmp     loc_18003202C
0x18003230f  test    rdi, rdi
0x180032312  jz      short loc_18003233F
0x180032314  mov     ecx, [rdi+30h]
0x180032317  mov     [rbx+38h], rcx
0x18003231b  mov     [rbx+40h], ecx
0x18003231e  mov     [rbx+28h], r8d
0x180032322  mov     [rbx+30h], rdi
0x180032326  mov     [rbx+70h], r8
0x18003232a  mov     [rbx+50h], r8
0x18003232e  mov     [rbx+5Ch], r8
0x180032332  mov     [rbx+68h], r8
0x180032336  mov     [rbx+20h], rdi
0x18003233a  jmp     loc_18003210E
0x18003233f  test    rbp, rbp
0x180032342  jz      short loc_180032362
0x180032344  mov     r8, [rsp+88h+arg_20]; unsigned __int64
0x18003234c  lea     rcx, [rbx+28h]; this
0x180032350  xor     r9d, r9d; unsigned __int64
0x180032353  mov     rdx, rbp; hFile
0x180032356  call    ?Init@EMFContainer@@QEAAHPEAX_K1@Z; EMFContainer::Init(void *,unsigned __int64,unsigned __int64)
0x18003235b  xor     r8d, r8d
0x18003235e  test    eax, eax
0x180032360  jnz     short loc_180032384
0x180032362  mov     [rbx+20h], r8
0x180032366  jmp     loc_18003212E
0x18003236b  mov     ecx, 0CEh
0x180032370  call    cs:__imp_GdiSetLastError
0x180032377  nop     dword ptr [rax+rax+00h]
0x18003237c  xor     r8d, r8d
0x18003237f  jmp     loc_180032124
0x180032384  mov     r13d, 1
0x18003238a  mov     [rbx+8], rbp
0x18003238e  jmp     loc_18003210E
0x180032393  mov     qword ptr [rbx+8], 0FFFFFFFFFFFFFFFFh
0x18003239b  jmp     loc_180032137
```
