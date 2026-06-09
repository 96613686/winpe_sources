# FileGetBindings

- ea: `0x180025e9c`
- end: `0x180026103`
- name: `FileGetBindings`
- size: `615`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, __int64, __int64, _QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x18001a250`

## callees

- `0x1800013fc`
- `0x180007c00`
- `0x18000a990`
- `0x18000bb78`
- `0x180025e9c`
- `0x1800265b0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180025fe3`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180025fe3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025ef5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800260ce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025ef5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800260ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025fbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026089`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025fbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026089`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180025fb0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180025fb0`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180025f22`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180025f22`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026099`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800260a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026099`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800260a2`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180026049`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180026049`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18002606d`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18002606d`
- `ntdll!wcsstr` at `0x180025f07`
- `ntdll!wcsstr` at `0x180025f07`

## string_xrefs

- `0x1800260ba`: `CRYPTNET.DLL --> Invalid File(%S):: Attributes: 0x%x Size: %d\n`

## pseudocode

```c
__int64 __fastcall FileGetBindings(LPCWSTR lpFileName, __int64 a2, __int64 a3, _QWORD *a4, _DWORD *a5)
{
  unsigned int v5; // ebx
  DWORD v8; // ecx
  const WCHAR *v9; // r14
  const wchar_t *v10; // rcx
  unsigned int v11; // edi
  _QWORD *v12; // rbx
  __int64 i; // rsi
  HANDLE FileW; // rax
  void *v15; // rbp
  DWORD LastError; // eax
  __int64 result; // rax
  HANDLE FileMappingW; // rax
  void *v19; // rsi
  LPVOID v20; // rax
  DWORD v21; // edi
  __int128 FileInformation; // [rsp+40h] [rbp-58h] BYREF
  __int128 v23; // [rsp+50h] [rbp-48h]
  unsigned int v24; // [rsp+60h] [rbp-38h]

  v24 = 0;
  v5 = 0;
  FileInformation = 0;
  v23 = 0;
  if ( a5 && *a5 > 0x10u )
    v5 = a5[4];
  if ( a3 )
  {
    v8 = -2147467263;
    goto LABEL_6;
  }
  v9 = lpFileName + 7;
  if ( !wcsstr(lpFileName, L"file://") )
    v9 = lpFileName;
  if ( !GetFileAttributesExW(v9, GetFileExInfoStandard, &FileInformation) )
  {
    v10 = L"Call_GetFileAttributesExW";
LABEL_36:
    CryptDiagAddActionWithLastError((__int64)v10);
    return 0;
  }
  v11 = v24;
  if ( (FileInformation & 0x10) != 0 || HIDWORD(v23) || !v24 || v5 && v24 > v5 )
  {
    I_CryptNetDebugErrorPrintfA(
      "CRYPTNET.DLL --> Invalid File(%S):: Attributes: 0x%x Size: %d\n",
      v9,
      (_DWORD)FileInformation,
      v24);
    SetLastError(0xDu);
    v10 = L"CheckFileAttributesAndSize";
    goto LABEL_36;
  }
  v12 = operator new(0x20u);
  if ( v12 )
  {
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      FileW = CreateFileW(v9, 0x80000000, 1u, 0, 3u, 0, 0);
      v15 = FileW;
      if ( FileW != (HANDLE)-1LL )
        break;
      LastError = GetLastError();
      if ( (LastError != 32 || (unsigned int)i >= 6) && (LastError != 5 || (_DWORD)i) )
      {
        operator delete(v12);
        return 0;
      }
      Sleep(*((_DWORD *)qword_18002BA00 + i));
    }
    if ( v11 > 0x14000 )
    {
      FileMappingW = CreateFileMappingW(FileW, 0, 2u, 0, 0, 0);
      v19 = FileMappingW;
      if ( !FileMappingW || (v20 = MapViewOfFile(FileMappingW, 4u, 0, 0, 0)) == 0 )
      {
        v21 = GetLastError();
        if ( v19 )
          CloseHandle(v19);
        CloseHandle(v15);
        operator delete(v12);
        v8 = v21;
        goto LABEL_6;
      }
      *((_DWORD *)v12 + 3) = 1;
      v12[2] = v19;
      v12[3] = v20;
    }
    else
    {
      *((_DWORD *)v12 + 3) = 0;
      v12[2] = 0;
      v12[3] = 0;
    }
    *((_DWORD *)v12 + 2) = v11;
    result = 1;
    *v12 = v15;
    *a4 = v12;
    return result;
  }
  v8 = -2147024882;
LABEL_6:
  SetLastError(v8);
  return 0;
}

```

## disassembly

```asm
0x180025e9c  mov     [rsp+arg_8], rbx
0x180025ea1  push    rbp
0x180025ea2  push    rsi
0x180025ea3  push    rdi
0x180025ea4  push    r14
0x180025ea6  push    r15
0x180025ea8  sub     rsp, 70h
0x180025eac  mov     rax, cs:__security_cookie
0x180025eb3  xor     rax, rsp
0x180025eb6  mov     [rsp+98h+var_30], rax
0x180025ebb  xor     eax, eax
0x180025ebd  xorps   xmm0, xmm0
0x180025ec0  mov     [rsp+98h+var_38], eax
0x180025ec4  xor     ebx, ebx
0x180025ec6  mov     rax, [rsp+98h+arg_20]
0x180025ece  mov     r15, r9
0x180025ed1  mov     rdi, rcx
0x180025ed4  movups  [rsp+98h+FileInformation], xmm0
0x180025ed9  movups  [rsp+98h+var_48], xmm0
0x180025ede  test    rax, rax
0x180025ee1  jz      short loc_180025EEB
0x180025ee3  cmp     dword ptr [rax], 10h
0x180025ee6  jbe     short loc_180025EEB
0x180025ee8  mov     ebx, [rax+10h]
0x180025eeb  test    r8, r8
0x180025eee  jz      short loc_180025F00
0x180025ef0  mov     ecx, 80004001h; dwErrCode
0x180025ef5  call    cs:__imp_SetLastError
0x180025efb  jmp     loc_1800260E0
0x180025f00  lea     rdx, aFile_0; "file://"
0x180025f07  call    cs:__imp_wcsstr
0x180025f0d  test    rax, rax
0x180025f10  lea     r14, [rdi+0Eh]
0x180025f14  lea     r8, [rsp+98h+FileInformation]; lpFileInformation
0x180025f19  cmovz   r14, rdi
0x180025f1d  xor     edx, edx; fInfoLevelId
0x180025f1f  mov     rcx, r14; lpFileName
0x180025f22  call    cs:__imp_GetFileAttributesExW
0x180025f28  test    eax, eax
0x180025f2a  jnz     short loc_180025F38
0x180025f2c  lea     rcx, aCallGetfileatt; "Call_GetFileAttributesExW"
0x180025f33  jmp     loc_1800260DB
0x180025f38  mov     r8d, dword ptr [rsp+98h+FileInformation]
0x180025f3d  mov     edi, [rsp+98h+var_38]
0x180025f41  test    r8b, 10h
0x180025f45  jnz     loc_1800260B7
0x180025f4b  cmp     dword ptr [rsp+98h+var_48+0Ch], 0
0x180025f50  jnz     loc_1800260B7
0x180025f56  test    edi, edi
0x180025f58  jz      loc_1800260B7
0x180025f5e  test    ebx, ebx
0x180025f60  jz      short loc_180025F6A
0x180025f62  cmp     edi, ebx
0x180025f64  ja      loc_1800260B7
0x180025f6a  mov     ecx, 20h ; ' '; uBytes
0x180025f6f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180025f74  mov     rbx, rax
0x180025f77  test    rax, rax
0x180025f7a  jnz     short loc_180025F86
0x180025f7c  mov     ecx, 8007000Eh
0x180025f81  jmp     loc_180025EF5
0x180025f86  xor     esi, esi
0x180025f88  xor     r9d, r9d; lpSecurityAttributes
0x180025f8b  mov     [rsp+98h+hTemplateFile], 0; hTemplateFile
0x180025f94  mov     [rsp+98h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180025f9c  mov     edx, 80000000h; dwDesiredAccess
0x180025fa1  mov     rcx, r14; lpFileName
0x180025fa4  mov     [rsp+98h+dwCreationDisposition], 3; dwCreationDisposition
0x180025fac  lea     r8d, [r9+1]; dwShareMode
0x180025fb0  call    cs:__imp_CreateFileW
0x180025fb6  mov     rbp, rax
0x180025fb9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180025fbd  jnz     short loc_180025FFA
0x180025fbf  call    cs:__imp_GetLastError
0x180025fc5  cmp     eax, 20h ; ' '
0x180025fc8  jnz     short loc_180025FCF
0x180025fca  cmp     esi, 6
0x180025fcd  jb      short loc_180025FD9
0x180025fcf  cmp     eax, 5
0x180025fd2  jnz     short loc_180025FED
0x180025fd4  cmp     esi, 1
0x180025fd7  jnb     short loc_180025FED
0x180025fd9  lea     rax, qword_18002BA00
0x180025fe0  mov     ecx, [rax+rsi*4]; dwMilliseconds
0x180025fe3  call    cs:__imp_Sleep
0x180025fe9  inc     esi
0x180025feb  jmp     short loc_180025F88
0x180025fed  mov     rcx, rbx; hMem
0x180025ff0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180025ff5  jmp     loc_1800260E0
0x180025ffa  cmp     edi, 14000h
0x180026000  ja      short loc_18002602C
0x180026002  mov     dword ptr [rbx+0Ch], 0
0x180026009  mov     qword ptr [rbx+10h], 0
0x180026011  mov     qword ptr [rbx+18h], 0
0x180026019  mov     [rbx+8], edi
0x18002601c  mov     eax, 1
0x180026021  mov     [rbx], rbp
0x180026024  mov     [r15], rbx
0x180026027  jmp     loc_1800260E2
0x18002602c  xor     r9d, r9d; dwMaximumSizeHigh
0x18002602f  mov     qword ptr [rsp+98h+dwFlagsAndAttributes], 0; lpName
0x180026038  xor     edx, edx; lpFileMappingAttributes
0x18002603a  mov     [rsp+98h+dwCreationDisposition], 0; dwMaximumSizeLow
0x180026042  mov     rcx, rbp; hFile
0x180026045  lea     r8d, [r9+2]; flProtect
0x180026049  call    cs:__imp_CreateFileMappingW
0x18002604f  mov     rsi, rax
0x180026052  test    rax, rax
0x180026055  jz      short loc_180026089
0x180026057  xor     r9d, r9d; dwFileOffsetLow
0x18002605a  mov     qword ptr [rsp+98h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x180026063  xor     r8d, r8d; dwFileOffsetHigh
0x180026066  mov     rcx, rax; hFileMappingObject
0x180026069  lea     edx, [r9+4]; dwDesiredAccess
0x18002606d  call    cs:__imp_MapViewOfFile
0x180026073  test    rax, rax
0x180026076  jz      short loc_180026089
0x180026078  mov     dword ptr [rbx+0Ch], 1
0x18002607f  mov     [rbx+10h], rsi
0x180026083  mov     [rbx+18h], rax
0x180026087  jmp     short loc_180026019
0x180026089  call    cs:__imp_GetLastError
0x18002608f  mov     edi, eax
0x180026091  test    rsi, rsi
0x180026094  jz      short loc_18002609F
0x180026096  mov     rcx, rsi; hObject
0x180026099  call    cs:__imp_CloseHandle
0x18002609f  mov     rcx, rbp; hObject
0x1800260a2  call    cs:__imp_CloseHandle
0x1800260a8  mov     rcx, rbx; hMem
0x1800260ab  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800260b0  mov     ecx, edi
0x1800260b2  jmp     loc_180025EF5
0x1800260b7  mov     r9d, edi
0x1800260ba  lea     rcx, aCryptnetDllInv_0; "CRYPTNET.DLL --> Invalid File(%S):: Att"...
0x1800260c1  mov     rdx, r14
0x1800260c4  call    ?I_CryptNetDebugErrorPrintfA@@YAXPEBDZZ; I_CryptNetDebugErrorPrintfA(char const *,...)
0x1800260c9  mov     ecx, 0Dh; dwErrCode
0x1800260ce  call    cs:__imp_SetLastError
0x1800260d4  lea     rcx, aCheckfileattri; "CheckFileAttributesAndSize"
0x1800260db  call    CryptDiagAddActionWithLastError
0x1800260e0  xor     eax, eax
0x1800260e2  mov     rcx, [rsp+98h+var_30]
0x1800260e7  xor     rcx, rsp; StackCookie
0x1800260ea  call    __security_check_cookie
0x1800260ef  mov     rbx, [rsp+98h+arg_8]
0x1800260f7  add     rsp, 70h
0x1800260fb  pop     r15
0x1800260fd  pop     r14
0x1800260ff  pop     rdi
0x180026100  pop     rsi
0x180026101  pop     rbp
0x180026102  retn
```
