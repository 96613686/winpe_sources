# _WriteErrorOut(ushort *,char *,int)

- ea: `0x18002e334`
- end: `0x18002e491`
- name: `?_WriteErrorOut@@YAXPEAGPEADH@Z`
- size: `349`
- prototype: `void(unsigned __int16 *, char *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18002e1e0`

## callees

- `0x18002e334`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e38f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e38f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e473`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e473`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002e46a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002e46a`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18002e423`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18002e423`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002e416`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002e43b`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002e416`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002e43b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002e3e7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002e3e7`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18002e3fb`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18002e3fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e482`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e482`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002e378`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002e3b2`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002e378`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002e3b2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18002e359`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18002e359`

## string_xrefs

- `0x18002e36f`: `%SystemRoot%\System32\CatRoot2\dberr.txt`
- `0x18002e3a4`: `%SystemRoot%\System32\CatRoot2\dberr.txt`

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
0x18002e334  mov     rax, rsp
0x18002e337  mov     [rax+18h], r8d
0x18002e33b  push    rbx
0x18002e33c  push    rbp
0x18002e33d  push    rsi
0x18002e33e  push    rdi
0x18002e33f  sub     rsp, 48h
0x18002e343  cmp     cs:?g_fLogErrorsToDebugger@@3HA, 0; int g_fLogErrorsToDebugger
0x18002e34a  mov     rbp, rdx
0x18002e34d  mov     dword ptr [rax+18h], 0
0x18002e354  jz      short loc_18002E35F
0x18002e356  mov     rcx, rdx; lpOutputString
0x18002e359  call    cs:__imp_OutputDebugStringA
0x18002e35f  cmp     cs:?g_fLogErrorsToFile@@3HA, 0; int g_fLogErrorsToFile
0x18002e366  jz      loc_18002E488
0x18002e36c  xor     r8d, r8d; nSize
0x18002e36f  lea     rcx, Src; "%SystemRoot%\\System32\\CatRoot2\\dberr"...
0x18002e376  xor     edx, edx; lpDst
0x18002e378  call    cs:__imp_ExpandEnvironmentStringsW
0x18002e37e  mov     edi, eax
0x18002e380  test    eax, eax
0x18002e382  jz      loc_18002E488
0x18002e388  mov     edx, edi
0x18002e38a  xor     ecx, ecx; uFlags
0x18002e38c  add     rdx, rdx; uBytes
0x18002e38f  call    cs:__imp_LocalAlloc
0x18002e395  mov     rsi, rax
0x18002e398  test    rax, rax
0x18002e39b  jz      loc_18002E488
0x18002e3a1  mov     r8d, edi; nSize
0x18002e3a4  lea     rcx, Src; "%SystemRoot%\\System32\\CatRoot2\\dberr"...
0x18002e3ab  mov     rdx, rax; lpDst
0x18002e3ae  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002e3b2  call    cs:__imp_ExpandEnvironmentStringsW
0x18002e3b8  test    eax, eax
0x18002e3ba  jz      loc_18002E470
0x18002e3c0  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18002e3c9  xor     r9d, r9d; lpSecurityAttributes
0x18002e3cc  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002e3d4  xor     r8d, r8d; dwShareMode
0x18002e3d7  mov     edx, 0C0000000h; dwDesiredAccess
0x18002e3dc  mov     [rsp+68h+dwCreationDisposition], 4; dwCreationDisposition
0x18002e3e4  mov     rcx, rsi; lpFileName
0x18002e3e7  call    cs:__imp_CreateFileW
0x18002e3ed  mov     rbx, rax
0x18002e3f0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002e3f4  jz      short loc_18002E470
0x18002e3f6  xor     edx, edx; lpFileSizeHigh
0x18002e3f8  mov     rcx, rax; hFile
0x18002e3fb  call    cs:__imp_GetFileSize
0x18002e401  or      edi, 0FFFFFFFFh
0x18002e404  cmp     eax, 30D40h
0x18002e409  jb      short loc_18002E42D
0x18002e40b  xor     r9d, r9d; dwMoveMethod
0x18002e40e  xor     r8d, r8d; lpDistanceToMoveHigh
0x18002e411  xor     edx, edx; lDistanceToMove
0x18002e413  mov     rcx, rbx; hFile
0x18002e416  call    cs:__imp_SetFilePointer
0x18002e41c  cmp     eax, edi
0x18002e41e  jz      short loc_18002E470
0x18002e420  mov     rcx, rbx; hFile
0x18002e423  call    cs:__imp_SetEndOfFile
0x18002e429  test    eax, eax
0x18002e42b  jz      short loc_18002E470
0x18002e42d  mov     r9d, 2; dwMoveMethod
0x18002e433  xor     r8d, r8d; lpDistanceToMoveHigh
0x18002e436  xor     edx, edx; lDistanceToMove
0x18002e438  mov     rcx, rbx; hFile
0x18002e43b  call    cs:__imp_SetFilePointer
0x18002e441  cmp     eax, edi
0x18002e443  jz      short loc_18002E470
0x18002e445  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002e449  inc     r8; nNumberOfBytesToWrite
0x18002e44c  cmp     byte ptr [r8+rbp], 0
0x18002e451  jnz     short loc_18002E449
0x18002e453  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18002e45b  mov     qword ptr [rsp+68h+dwCreationDisposition], 0; lpOverlapped
0x18002e464  mov     rdx, rbp; lpBuffer
0x18002e467  mov     rcx, rbx; hFile
0x18002e46a  call    cs:__imp_WriteFile
0x18002e470  mov     rcx, rsi; hMem
0x18002e473  call    cs:__imp_LocalFree
0x18002e479  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18002e47d  jz      short loc_18002E488
0x18002e47f  mov     rcx, rbx; hObject
0x18002e482  call    cs:__imp_CloseHandle
0x18002e488  add     rsp, 48h
0x18002e48c  pop     rdi
0x18002e48d  pop     rsi
0x18002e48e  pop     rbp
0x18002e48f  pop     rbx
0x18002e490  retn
```
