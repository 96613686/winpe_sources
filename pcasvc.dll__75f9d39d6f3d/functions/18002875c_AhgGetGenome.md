# AhgGetGenome

- ea: `0x18002875c`
- end: `0x180028986`
- name: `AhgGetGenome`
- size: `554`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800280c8`

## callees

- `0x180012920`
- `0x180018230`
- `0x18002875c`
- `0x18002898c`
- `0x180028a3c`
- `0x180028b60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002890c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028923`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028943`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002890c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028923`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028943`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800288cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002897b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800288cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002897b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800287c3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800287c3`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800288c2`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800288c2`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180028810`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180028810`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800287ed`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800287ed`

## string_xrefs

- `0x1800288fd`: `Cannot create genome handle [%d]`
- `0x180028966`: `Cannot compute genome [%d]`

## pseudocode

```c
__int64 __fastcall AhgGetGenome(unsigned __int64 *a1, const WCHAR *a2)
{
  void *v3; // rsi
  const void *v5; // rbp
  DWORD All; // ebx
  HANDLE FileW; // rax
  __int64 v8; // rdi
  HANDLE FileMappingW; // rax
  const void *v10; // rax
  const char *v12; // r9
  int v13; // r8d
  DWORD LastError; // eax
  int v15; // [rsp+70h] [rbp+8h] BYREF
  unsigned int v16; // [rsp+80h] [rbp+18h] BYREF
  unsigned __int64 v17; // [rsp+88h] [rbp+20h] BYREF

  v15 = 0;
  v3 = 0;
  v16 = 0;
  *a1 = 0;
  v17 = 0;
  v5 = 0;
  All = AhgGenomeCreate(&v17);
  if ( All )
  {
    v8 = -1;
    v12 = "Cannot create genome handle [%d]";
    v13 = 849;
    goto LABEL_18;
  }
  FileW = CreateFileW(a2, 0x80000000, 7u, 0, 3u, 0x80u, 0);
  v8 = (__int64)FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v12 = "Bad file name [%d]";
    v13 = 866;
    All = LastError;
    goto LABEL_18;
  }
  FileMappingW = CreateFileMappingW(FileW, 0, 0x11000002u, 0, 0, 0);
  v3 = FileMappingW;
  if ( !FileMappingW )
  {
    All = GetLastError();
    if ( All == 8 )
      goto LABEL_8;
    v12 = "Failed to map file [%d]";
    v13 = 879;
LABEL_18:
    AslLogCallPrintf(1, (unsigned int)"AhgGetGenome", v13, (_DWORD)v12);
    goto LABEL_8;
  }
  v10 = MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
  v5 = v10;
  if ( v10 )
  {
    All = AhgGenomeGetAll(v17, v8, v10);
    if ( All )
    {
      v12 = "Cannot get attributes [%d]";
      v13 = 903;
    }
    else
    {
      All = AhgGenomeCompute(&v15, &v16, v17);
      if ( !All )
      {
        *a1 = ((unsigned __int64)v16 << 32) | ((BYTE2(v15) | ((unsigned __int8)v15 << 8)) << 16);
        goto LABEL_8;
      }
      v12 = "Cannot compute genome [%d]";
      v13 = 913;
    }
    goto LABEL_18;
  }
  All = GetLastError();
  if ( All != 8 )
  {
    v12 = "Failed to map a view of file mapping [%d]";
    v13 = 892;
    goto LABEL_18;
  }
LABEL_8:
  if ( v17 )
    ObsoleteShellApi_Delete(v17);
  if ( v5 )
    UnmapViewOfFile(v5);
  if ( v3 )
    CloseHandle(v3);
  if ( v8 != -1 )
    CloseHandle((HANDLE)v8);
  return All;
}

```

## disassembly

```asm
0x18002875c  mov     rax, rsp
0x18002875f  push    rbx
0x180028760  push    rbp
0x180028761  push    rsi
0x180028762  push    rdi
0x180028763  push    r15
0x180028765  sub     rsp, 40h
0x180028769  mov     r15, rcx
0x18002876c  mov     dword ptr [rax+8], 0
0x180028773  xor     esi, esi
0x180028775  mov     dword ptr [rax+18h], 0
0x18002877c  mov     [rcx], rsi
0x18002877f  mov     rdi, rdx
0x180028782  lea     rcx, [rax+20h]
0x180028786  mov     qword ptr [rax+20h], 0
0x18002878e  xor     ebp, ebp
0x180028790  call    AhgGenomeCreate
0x180028795  mov     ebx, eax
0x180028797  test    eax, eax
0x180028799  jnz     loc_1800288F9
0x18002879f  mov     [rsp+68h+hTemplateFile], rsi; hTemplateFile
0x1800287a4  lea     r8d, [rsi+7]; dwShareMode
0x1800287a8  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800287b0  xor     r9d, r9d; lpSecurityAttributes
0x1800287b3  mov     edx, 80000000h; dwDesiredAccess
0x1800287b8  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x1800287c0  mov     rcx, rdi; lpFileName
0x1800287c3  call    cs:__imp_CreateFileW
0x1800287c9  mov     rdi, rax
0x1800287cc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800287d0  jz      loc_18002890C
0x1800287d6  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], rsi; lpName
0x1800287db  xor     r9d, r9d; dwMaximumSizeHigh
0x1800287de  xor     edx, edx; lpFileMappingAttributes
0x1800287e0  mov     [rsp+68h+dwCreationDisposition], esi; dwMaximumSizeLow
0x1800287e4  mov     r8d, 11000002h; flProtect
0x1800287ea  mov     rcx, rax; hFile
0x1800287ed  call    cs:__imp_CreateFileMappingW
0x1800287f3  mov     rsi, rax
0x1800287f6  test    rax, rax
0x1800287f9  jz      loc_180028923
0x1800287ff  xor     r9d, r9d; dwFileOffsetLow
0x180028802  mov     qword ptr [rsp+68h+dwCreationDisposition], rbp; dwNumberOfBytesToMap
0x180028807  xor     r8d, r8d; dwFileOffsetHigh
0x18002880a  lea     edx, [rbp+4]; dwDesiredAccess
0x18002880d  mov     rcx, rax; hFileMappingObject
0x180028810  call    cs:__imp_MapViewOfFile
0x180028816  mov     rbp, rax
0x180028819  test    rax, rax
0x18002881c  jz      loc_180028943
0x180028822  mov     rcx, [rsp+68h+arg_18]
0x18002882a  mov     r8, rax
0x18002882d  mov     rdx, rdi
0x180028830  call    AhgGenomeGetAll
0x180028835  mov     ebx, eax
0x180028837  test    eax, eax
0x180028839  jnz     loc_1800288D5
0x18002883f  mov     r8, [rsp+68h+arg_18]
0x180028847  lea     rdx, [rsp+68h+arg_10]
0x18002884f  lea     rcx, [rsp+68h+arg_0]
0x180028854  call    AhgGenomeCompute
0x180028859  mov     ebx, eax
0x18002885b  test    eax, eax
0x18002885d  jnz     loc_180028966
0x180028863  movzx   edx, [rsp+68h+arg_0]
0x180028868  movzx   eax, [rsp+68h+arg_2]
0x18002886d  shl     edx, 8
0x180028870  or      edx, eax
0x180028872  mov     eax, [rsp+68h+arg_10]
0x180028879  shl     rax, 20h
0x18002887d  shl     edx, 10h
0x180028880  or      rdx, rax
0x180028883  mov     [r15], rdx
0x180028886  cmp     [rsp+68h+arg_18], 0
0x18002888f  jz      short loc_18002889E
0x180028891  mov     rcx, [rsp+68h+arg_18]; unsigned __int64
0x180028899  call    ?ObsoleteShellApi_Delete@@YAX_K@Z; ObsoleteShellApi_Delete(unsigned __int64)
0x18002889e  test    rbp, rbp
0x1800288a1  jnz     short loc_1800288BF
0x1800288a3  test    rsi, rsi
0x1800288a6  jnz     short loc_1800288CA
0x1800288a8  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800288ac  jnz     loc_180028978
0x1800288b2  mov     eax, ebx
0x1800288b4  add     rsp, 40h
0x1800288b8  pop     r15
0x1800288ba  pop     rdi
0x1800288bb  pop     rsi
0x1800288bc  pop     rbp
0x1800288bd  pop     rbx
0x1800288be  retn
0x1800288bf  mov     rcx, rbp; lpBaseAddress
0x1800288c2  call    cs:__imp_UnmapViewOfFile
0x1800288c8  jmp     short loc_1800288A3
0x1800288ca  mov     rcx, rsi; hObject
0x1800288cd  call    cs:__imp_CloseHandle
0x1800288d3  jmp     short loc_1800288A8
0x1800288d5  lea     r9, aCannotGetAttri; "Cannot get attributes [%d]"
0x1800288dc  mov     r8d, 387h
0x1800288e2  lea     rdx, aAhggetgenome; "AhgGetGenome"
0x1800288e9  mov     [rsp+68h+dwCreationDisposition], eax
0x1800288ed  mov     ecx, 1
0x1800288f2  call    AslLogCallPrintf
0x1800288f7  jmp     short loc_180028886
0x1800288f9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800288fd  lea     r9, aCannotCreateGe; "Cannot create genome handle [%d]"
0x180028904  mov     r8d, 351h
0x18002890a  jmp     short loc_1800288E2
0x18002890c  call    cs:__imp_GetLastError
0x180028912  lea     r9, aBadFileNameD; "Bad file name [%d]"
0x180028919  mov     r8d, 362h
0x18002891f  mov     ebx, eax
0x180028921  jmp     short loc_1800288E2
0x180028923  call    cs:__imp_GetLastError
0x180028929  mov     ebx, eax
0x18002892b  cmp     eax, 8
0x18002892e  jz      loc_180028886
0x180028934  lea     r9, aFailedToMapFil; "Failed to map file [%d]"
0x18002893b  mov     r8d, 36Fh
0x180028941  jmp     short loc_1800288E2
0x180028943  call    cs:__imp_GetLastError
0x180028949  mov     ebx, eax
0x18002894b  cmp     eax, 8
0x18002894e  jz      loc_180028886
0x180028954  lea     r9, aFailedToMapAVi; "Failed to map a view of file mapping [%"...
0x18002895b  mov     r8d, 37Ch
0x180028961  jmp     loc_1800288E2
0x180028966  lea     r9, aCannotComputeG; "Cannot compute genome [%d]"
0x18002896d  mov     r8d, 391h
0x180028973  jmp     loc_1800288E2
0x180028978  mov     rcx, rdi; hObject
0x18002897b  call    cs:__imp_CloseHandle
0x180028981  jmp     loc_1800288B2
```
