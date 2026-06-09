# _WriteErrorOut(ushort *,char *,int)

- ea: `0x180114dd0`
- end: `0x180114f2d`
- name: `?_WriteErrorOut@@YAXPEAGPEADH@Z`
- size: `349`
- prototype: `void __fastcall(unsigned __int16 *, char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800bbe5c`

## callees

- `0x180114dd0`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180114e14`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180114e4e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180114e14`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180114e4e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180114f0f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180114f0f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180114e2b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180114e2b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180114e83`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180114e83`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180114eb2`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180114ed7`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180114eb2`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180114ed7`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180114f06`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180114f06`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180114e97`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180114e97`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180114ebf`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180114ebf`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180114df5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180114df5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180114f1e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180114f1e`

## string_xrefs

- `0x180114e0b`: `%SystemRoot%\System32\CatRoot2\dberr.txt`
- `0x180114e40`: `%SystemRoot%\System32\CatRoot2\dberr.txt`

## pseudocode

```c
void __fastcall _WriteErrorOut(unsigned __int16 *a1, char *a2)
{
  DWORD v3; // eax
  DWORD v4; // edi
  WCHAR *v5; // rax
  WCHAR *v6; // rsi
  __int64 v7; // rbx
  HANDLE FileW; // rax
  __int64 v9; // r8
  DWORD NumberOfBytesWritten; // [rsp+80h] [rbp+18h] BYREF

  NumberOfBytesWritten = 0;
  if ( g_fLogErrorsToDebugger )
    OutputDebugStringA(a2);
  if ( g_fLogErrorsToFile )
  {
    v3 = ExpandEnvironmentStringsW(L"%SystemRoot%\\System32\\CatRoot2\\dberr.txt", 0, 0);
    v4 = v3;
    if ( v3 )
    {
      v5 = (WCHAR *)LocalAlloc(0, 2LL * v3);
      v6 = v5;
      if ( v5 )
      {
        v7 = -1;
        if ( ExpandEnvironmentStringsW(L"%SystemRoot%\\System32\\CatRoot2\\dberr.txt", v5, v4) )
        {
          FileW = CreateFileW(v6, 0xC0000000, 0, 0, 4u, 0x80u, 0);
          v7 = (__int64)FileW;
          if ( FileW != (HANDLE)-1LL
            && (GetFileSize(FileW, 0) < 0x30D40 || SetFilePointer((HANDLE)v7, 0, 0, 0) != -1 && SetEndOfFile((HANDLE)v7))
            && SetFilePointer((HANDLE)v7, 0, 0, 2u) != -1 )
          {
            v9 = -1;
            do
              ++v9;
            while ( a2[v9] );
            WriteFile((HANDLE)v7, a2, v9, &NumberOfBytesWritten, 0);
          }
        }
        LocalFree(v6);
        if ( v7 != -1 )
          CloseHandle((HANDLE)v7);
      }
    }
  }
}

```

## disassembly

```asm
0x180114dd0  mov     rax, rsp
0x180114dd3  mov     [rax+18h], r8d
0x180114dd7  push    rbx
0x180114dd8  push    rbp
0x180114dd9  push    rsi
0x180114dda  push    rdi
0x180114ddb  sub     rsp, 48h
0x180114ddf  cmp     cs:?g_fLogErrorsToDebugger@@3HA, 0; int g_fLogErrorsToDebugger
0x180114de6  mov     rbp, rdx
0x180114de9  mov     dword ptr [rax+18h], 0
0x180114df0  jz      short loc_180114DFB
0x180114df2  mov     rcx, rdx; lpOutputString
0x180114df5  call    cs:__imp_OutputDebugStringA
0x180114dfb  cmp     cs:?g_fLogErrorsToFile@@3HA, 0; int g_fLogErrorsToFile
0x180114e02  jz      loc_180114F24
0x180114e08  xor     r8d, r8d; nSize
0x180114e0b  lea     rcx, aSystemrootSyst; "%SystemRoot%\\System32\\CatRoot2\\dberr"...
0x180114e12  xor     edx, edx; lpDst
0x180114e14  call    cs:__imp_ExpandEnvironmentStringsW
0x180114e1a  mov     edi, eax
0x180114e1c  test    eax, eax
0x180114e1e  jz      loc_180114F24
0x180114e24  mov     edx, edi
0x180114e26  xor     ecx, ecx; uFlags
0x180114e28  add     rdx, rdx; uBytes
0x180114e2b  call    cs:__imp_LocalAlloc
0x180114e31  mov     rsi, rax
0x180114e34  test    rax, rax
0x180114e37  jz      loc_180114F24
0x180114e3d  mov     r8d, edi; nSize
0x180114e40  lea     rcx, aSystemrootSyst; "%SystemRoot%\\System32\\CatRoot2\\dberr"...
0x180114e47  mov     rdx, rax; lpDst
0x180114e4a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180114e4e  call    cs:__imp_ExpandEnvironmentStringsW
0x180114e54  test    eax, eax
0x180114e56  jz      loc_180114F0C
0x180114e5c  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x180114e65  xor     r9d, r9d; lpSecurityAttributes
0x180114e68  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180114e70  xor     r8d, r8d; dwShareMode
0x180114e73  mov     edx, 0C0000000h; dwDesiredAccess
0x180114e78  mov     [rsp+68h+dwCreationDisposition], 4; dwCreationDisposition
0x180114e80  mov     rcx, rsi; lpFileName
0x180114e83  call    cs:__imp_CreateFileW
0x180114e89  mov     rbx, rax
0x180114e8c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180114e90  jz      short loc_180114F0C
0x180114e92  xor     edx, edx; lpFileSizeHigh
0x180114e94  mov     rcx, rax; hFile
0x180114e97  call    cs:__imp_GetFileSize
0x180114e9d  or      edi, 0FFFFFFFFh
0x180114ea0  cmp     eax, 30D40h
0x180114ea5  jb      short loc_180114EC9
0x180114ea7  xor     r9d, r9d; dwMoveMethod
0x180114eaa  xor     r8d, r8d; lpDistanceToMoveHigh
0x180114ead  xor     edx, edx; lDistanceToMove
0x180114eaf  mov     rcx, rbx; hFile
0x180114eb2  call    cs:__imp_SetFilePointer
0x180114eb8  cmp     eax, edi
0x180114eba  jz      short loc_180114F0C
0x180114ebc  mov     rcx, rbx; hFile
0x180114ebf  call    cs:__imp_SetEndOfFile
0x180114ec5  test    eax, eax
0x180114ec7  jz      short loc_180114F0C
0x180114ec9  mov     r9d, 2; dwMoveMethod
0x180114ecf  xor     r8d, r8d; lpDistanceToMoveHigh
0x180114ed2  xor     edx, edx; lDistanceToMove
0x180114ed4  mov     rcx, rbx; hFile
0x180114ed7  call    cs:__imp_SetFilePointer
0x180114edd  cmp     eax, edi
0x180114edf  jz      short loc_180114F0C
0x180114ee1  or      r8, 0FFFFFFFFFFFFFFFFh
0x180114ee5  inc     r8; nNumberOfBytesToWrite
0x180114ee8  cmp     byte ptr [r8+rbp], 0
0x180114eed  jnz     short loc_180114EE5
0x180114eef  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180114ef7  mov     qword ptr [rsp+68h+dwCreationDisposition], 0; lpOverlapped
0x180114f00  mov     rdx, rbp; lpBuffer
0x180114f03  mov     rcx, rbx; hFile
0x180114f06  call    cs:__imp_WriteFile
0x180114f0c  mov     rcx, rsi; hMem
0x180114f0f  call    cs:__imp_LocalFree
0x180114f15  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180114f19  jz      short loc_180114F24
0x180114f1b  mov     rcx, rbx; hObject
0x180114f1e  call    cs:__imp_CloseHandle
0x180114f24  add     rsp, 48h
0x180114f28  pop     rdi
0x180114f29  pop     rsi
0x180114f2a  pop     rbp
0x180114f2b  pop     rbx
0x180114f2c  retn
```
