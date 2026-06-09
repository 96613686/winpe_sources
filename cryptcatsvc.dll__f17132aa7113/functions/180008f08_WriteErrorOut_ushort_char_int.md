# _WriteErrorOut(ushort *,char *,int)

- ea: `0x180008f08`
- end: `0x18000907b`
- name: `?_WriteErrorOut@@YAXPEAGPEADH@Z`
- size: `371`
- prototype: `void(unsigned __int16 *, char *, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000a59c`
- `0x18001f81c`

## callees

- `0x180008f08`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180008f39`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180008f39`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009062`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009062`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180008ff9`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18000901e`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180008ff9`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18000901e`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180008fde`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180008fde`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180009006`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180009006`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000904a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18000904a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180008fca`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180008fca`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180008f5f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180008f95`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180008f5f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180008f95`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008f76`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008f76`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009053`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009053`

## pseudocode

```c
void __fastcall _WriteErrorOut(unsigned __int16 *a1, char *a2, int a3)
{
  DWORD v5; // eax
  DWORD v6; // ebp
  WCHAR *v7; // rax
  WCHAR *v8; // rsi
  __int64 v9; // rbx
  HANDLE FileW; // rax
  __int64 v11; // r8
  DWORD NumberOfBytesWritten; // [rsp+60h] [rbp+8h] BYREF

  NumberOfBytesWritten = 0;
  if ( g_fLogErrorsToDebugger && !a3 )
    OutputDebugStringA(a2);
  if ( g_fLogErrorsToFile )
  {
    if ( !a1 )
      a1 = (unsigned __int16 *)lpSrc;
    v5 = ExpandEnvironmentStringsW(a1, 0, 0);
    v6 = v5;
    if ( v5 )
    {
      v7 = (WCHAR *)LocalAlloc(0, 2LL * v5);
      v8 = v7;
      if ( v7 )
      {
        v9 = -1;
        if ( ExpandEnvironmentStringsW(a1, v7, v6) )
        {
          FileW = CreateFileW(v8, 0xC0000000, 0, 0, 4u, 0x80u, 0);
          v9 = (__int64)FileW;
          if ( FileW != (HANDLE)-1LL
            && (GetFileSize(FileW, 0) < 0x30D40 || SetFilePointer((HANDLE)v9, 0, 0, 0) != -1 && SetEndOfFile((HANDLE)v9))
            && SetFilePointer((HANDLE)v9, 0, 0, 2u) != -1 )
          {
            v11 = -1;
            do
              ++v11;
            while ( a2[v11] );
            WriteFile((HANDLE)v9, a2, v11, &NumberOfBytesWritten, 0);
          }
        }
        LocalFree(v8);
        if ( v9 != -1 )
          CloseHandle((HANDLE)v9);
      }
    }
  }
}

```

## disassembly

```asm
0x180008f08  mov     [rsp+arg_8], rbx
0x180008f0d  mov     [rsp+arg_10], rbp
0x180008f12  push    rsi
0x180008f13  push    rdi
0x180008f14  push    r14
0x180008f16  sub     rsp, 40h
0x180008f1a  cmp     cs:?g_fLogErrorsToDebugger@@3HA, 0; int g_fLogErrorsToDebugger
0x180008f21  mov     r14, rdx
0x180008f24  mov     rdi, rcx
0x180008f27  mov     [rsp+58h+NumberOfBytesWritten], 0
0x180008f2f  jz      short loc_180008F3F
0x180008f31  test    r8d, r8d
0x180008f34  jnz     short loc_180008F3F
0x180008f36  mov     rcx, rdx; lpOutputString
0x180008f39  call    cs:__imp_OutputDebugStringA
0x180008f3f  cmp     cs:?g_fLogErrorsToFile@@3HA, 0; int g_fLogErrorsToFile
0x180008f46  jz      loc_180009068
0x180008f4c  test    rdi, rdi
0x180008f4f  cmovz   rdi, cs:lpSrc
0x180008f57  xor     r8d, r8d; nSize
0x180008f5a  mov     rcx, rdi; lpSrc
0x180008f5d  xor     edx, edx; lpDst
0x180008f5f  call    cs:__imp_ExpandEnvironmentStringsW
0x180008f65  mov     ebp, eax
0x180008f67  test    eax, eax
0x180008f69  jz      loc_180009068
0x180008f6f  mov     edx, ebp
0x180008f71  xor     ecx, ecx; uFlags
0x180008f73  add     rdx, rdx; uBytes
0x180008f76  call    cs:__imp_LocalAlloc
0x180008f7c  mov     rsi, rax
0x180008f7f  test    rax, rax
0x180008f82  jz      loc_180009068
0x180008f88  mov     r8d, ebp; nSize
0x180008f8b  mov     rdx, rax; lpDst
0x180008f8e  mov     rcx, rdi; lpSrc
0x180008f91  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180008f95  call    cs:__imp_ExpandEnvironmentStringsW
0x180008f9b  test    eax, eax
0x180008f9d  jz      loc_180009050
0x180008fa3  mov     [rsp+58h+hTemplateFile], 0; hTemplateFile
0x180008fac  xor     r9d, r9d; lpSecurityAttributes
0x180008faf  mov     [rsp+58h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180008fb7  xor     r8d, r8d; dwShareMode
0x180008fba  mov     edx, 0C0000000h; dwDesiredAccess
0x180008fbf  mov     [rsp+58h+dwCreationDisposition], 4; dwCreationDisposition
0x180008fc7  mov     rcx, rsi; lpFileName
0x180008fca  call    cs:__imp_CreateFileW
0x180008fd0  mov     rbx, rax
0x180008fd3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180008fd7  jz      short loc_180009050
0x180008fd9  xor     edx, edx; lpFileSizeHigh
0x180008fdb  mov     rcx, rax; hFile
0x180008fde  call    cs:__imp_GetFileSize
0x180008fe4  or      edi, 0FFFFFFFFh
0x180008fe7  cmp     eax, 30D40h
0x180008fec  jb      short loc_180009010
0x180008fee  xor     r9d, r9d; dwMoveMethod
0x180008ff1  xor     r8d, r8d; lpDistanceToMoveHigh
0x180008ff4  xor     edx, edx; lDistanceToMove
0x180008ff6  mov     rcx, rbx; hFile
0x180008ff9  call    cs:__imp_SetFilePointer
0x180008fff  cmp     eax, edi
0x180009001  jz      short loc_180009050
0x180009003  mov     rcx, rbx; hFile
0x180009006  call    cs:__imp_SetEndOfFile
0x18000900c  test    eax, eax
0x18000900e  jz      short loc_180009050
0x180009010  mov     r9d, 2; dwMoveMethod
0x180009016  xor     r8d, r8d; lpDistanceToMoveHigh
0x180009019  xor     edx, edx; lDistanceToMove
0x18000901b  mov     rcx, rbx; hFile
0x18000901e  call    cs:__imp_SetFilePointer
0x180009024  cmp     eax, edi
0x180009026  jz      short loc_180009050
0x180009028  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000902c  inc     r8; nNumberOfBytesToWrite
0x18000902f  cmp     byte ptr [r14+r8], 0
0x180009034  jnz     short loc_18000902C
0x180009036  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18000903b  mov     qword ptr [rsp+58h+dwCreationDisposition], 0; lpOverlapped
0x180009044  mov     rdx, r14; lpBuffer
0x180009047  mov     rcx, rbx; hFile
0x18000904a  call    cs:__imp_WriteFile
0x180009050  mov     rcx, rsi; hMem
0x180009053  call    cs:__imp_LocalFree
0x180009059  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000905d  jz      short loc_180009068
0x18000905f  mov     rcx, rbx; hObject
0x180009062  call    cs:__imp_CloseHandle
0x180009068  mov     rbx, [rsp+58h+arg_8]
0x18000906d  mov     rbp, [rsp+58h+arg_10]
0x180009072  add     rsp, 40h
0x180009076  pop     r14
0x180009078  pop     rdi
0x180009079  pop     rsi
0x18000907a  retn
```
