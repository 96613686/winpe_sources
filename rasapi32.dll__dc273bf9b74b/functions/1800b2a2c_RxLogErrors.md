# RxLogErrors

- ea: `0x1800b2a2c`
- end: `0x1800b2d5e`
- name: `RxLogErrors`
- size: `818`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800b1f80`
- `0x1800b6394`

## callees

- `0x1800b2a2c`
- `0x1800b7e50`
- `0x1800decfa`
- `0x1800ded50`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800b2ade`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800b2ade`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800b2b39`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800b2d04`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800b2b39`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800b2d04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2b45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2c74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2cd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2b45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2c74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2cd1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b2d1f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b2d1f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x1800b2c43`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x1800b2c43`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800b2b7e`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800b2b7e`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1800b2b87`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1800b2b87`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800b2b2d`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x1800b2b2d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800b2c62`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800b2cc1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800b2c62`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800b2cc1`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x1800b2acd`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x1800b2aff`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x1800b2acd`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x1800b2aff`
- `rtutils!TracePrintfExA` at `0x1800b2aa8`
- `rtutils!TracePrintfExA` at `0x1800b2b64`
- `rtutils!TracePrintfExA` at `0x1800b2c9e`
- `rtutils!TracePrintfExA` at `0x1800b2cfb`
- `rtutils!TracePrintfExA` at `0x1800b2aa8`
- `rtutils!TracePrintfExA` at `0x1800b2b64`
- `rtutils!TracePrintfExA` at `0x1800b2c9e`
- `rtutils!TracePrintfExA` at `0x1800b2cfb`

## string_xrefs

- `0x1800b2a8b`: `%windir%\system32\ras\script.log`
- `0x1800b2c87`: `%windir%\system32\ras\script.log`
- `0x1800b2ce4`: `%windir%\system32\ras\script.log`
- `0x1800b2c92`: `RxLogErrors(): WriteFile to %s failed with error %d\n`
- `0x1800b2cef`: `RxLogErrors(): WriteFile to %s failed with error %d\n`

## pseudocode

```c
__int64 __fastcall RxLogErrors(__int64 a1, unsigned int *a2)
{
  __int64 v4; // r15
  CHAR *v5; // rax
  CHAR *v6; // rbx
  HANDLE FileA; // rdi
  DWORD LastError; // eax
  DWORD v10; // ebx
  DWORD v11; // esi
  unsigned int v12; // r13d
  unsigned int i; // ebx
  unsigned int v14; // eax
  int v15; // eax
  CHAR *v16; // r14
  DWORD v17; // eax
  DWORD v18; // eax
  DWORD nSize; // [rsp+40h] [rbp-49h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+44h] [rbp-45h] BYREF
  LPCSTR lpString; // [rsp+48h] [rbp-41h] BYREF
  _OWORD v22[2]; // [rsp+50h] [rbp-39h] BYREF
  __int64 v23; // [rsp+70h] [rbp-19h]
  CHAR Src[40]; // [rsp+78h] [rbp-11h] BYREF

  v23 = 0;
  nSize = 0;
  memset(v22, 0, sizeof(v22));
  strcpy(Src, "%windir%\\system32\\ras\\script.log");
  if ( g_dwRasscrptTraceId != -1 )
    TracePrintfExA(g_dwRasscrptTraceId, 0xCu, "RxLogErrors");
  if ( !a1 )
    return 87;
  v4 = *(_QWORD *)(a1 + 112);
  if ( !v4 )
    return 87;
  nSize = ExpandEnvironmentStringsA(Src, 0, 0);
  v5 = (CHAR *)GlobalAlloc(0x40u, nSize + 1);
  v6 = v5;
  if ( !v5 )
    return 8;
  ExpandEnvironmentStringsA(Src, v5, nSize);
  FileA = CreateFileA(v6, 0x40000000u, 1u, 0, 2u, 0x80u, 0);
  GlobalFree(v6);
  if ( FileA == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( g_dwRasscrptTraceId != -1 )
      TracePrintfExA(g_dwRasscrptTraceId, 0xCu, "error %d creating logfile", LastError);
    return v10;
  }
  else
  {
    v11 = 0;
    SetFilePointer(FileA, 0, 0, 0);
    SetEndOfFile(FileA);
    v12 = *a2;
    for ( i = 0; i < v12; ++i )
    {
      lpString = 0;
      if ( i == -1 || i >= *a2 )
      {
        NumberOfBytesWritten = 0;
      }
      else
      {
        memmove_0(v22, (const void *)(*((_QWORD *)a2 + 1) + i * a2[5]), a2[5]);
        v14 = 0;
        NumberOfBytesWritten = 0;
        while ( v14 < 0x1B )
        {
          if ( HIDWORD(v23) == LODWORD(c_mpresids[v14]) )
          {
            v15 = HIDWORD(c_mpresids[v14]);
            if ( v15 )
            {
              ConstructMessage(&lpString, g_hinst, (unsigned __int16)v15, v4 + 1080, v23, v22);
              v16 = (CHAR *)lpString;
              if ( lpString )
              {
                nSize = lstrlenA(lpString);
                if ( !WriteFile(FileA, v16, nSize, &NumberOfBytesWritten, 0) || NumberOfBytesWritten != nSize )
                {
                  v17 = GetLastError();
                  v11 = v17;
                  if ( g_dwRasscrptTraceId != -1 )
                    TracePrintfExA(
                      g_dwRasscrptTraceId,
                      0xCu,
                      "RxLogErrors(): WriteFile to %s failed with error %d\n",
                      "%windir%\\system32\\ras\\script.log",
                      v17);
                }
                if ( !WriteFile(FileA, "\r\n", 2u, &nSize, 0) || NumberOfBytesWritten != 2 )
                {
                  v18 = GetLastError();
                  v11 = v18;
                  if ( g_dwRasscrptTraceId != -1 )
                    TracePrintfExA(
                      g_dwRasscrptTraceId,
                      0xCu,
                      "RxLogErrors(): WriteFile to %s failed with error %d\n",
                      "%windir%\\system32\\ras\\script.log",
                      v18);
                }
                GlobalFree(v16);
              }
            }
            break;
          }
          ++v14;
        }
      }
    }
    CloseHandle(FileA);
    return v11;
  }
}

```

## disassembly

```asm
0x1800b2a2c  mov     [rsp-8+arg_10], rbx
0x1800b2a31  push    rbp
0x1800b2a32  push    rsi
0x1800b2a33  push    rdi
0x1800b2a34  push    r12
0x1800b2a36  push    r13
0x1800b2a38  push    r14
0x1800b2a3a  push    r15
0x1800b2a3c  lea     rbp, [rsp-27h]
0x1800b2a41  sub     rsp, 0B0h
0x1800b2a48  mov     rax, cs:__security_cookie
0x1800b2a4f  xor     rax, rsp
0x1800b2a52  mov     [rbp+57h+var_40], rax
0x1800b2a56  movups  xmm1, xmmword ptr cs:aWindirSystem32+10h; "2\\ras\\script.log"
0x1800b2a5d  xor     eax, eax
0x1800b2a5f  mov     rbx, rcx
0x1800b2a62  mov     ecx, cs:g_dwRasscrptTraceId; dwTraceID
0x1800b2a68  xorps   xmm0, xmm0
0x1800b2a6b  mov     [rbp+57h+var_70], rax
0x1800b2a6f  mov     r12, rdx
0x1800b2a72  mov     [rbp+57h+nSize], eax
0x1800b2a75  mov     esi, 0Ch
0x1800b2a7a  mov     al, byte ptr cs:aWindirSystem32+20h; ""
0x1800b2a80  mov     [rbp+57h+var_58+10h], al
0x1800b2a83  movups  [rbp+57h+var_90], xmm0
0x1800b2a87  movups  [rbp+57h+var_80], xmm0
0x1800b2a8b  movups  xmm0, xmmword ptr cs:aWindirSystem32; "%windir%\\system32\\ras\\script.log"
0x1800b2a92  movups  xmmword ptr [rbp+57h+var_58], xmm1
0x1800b2a96  movups  xmmword ptr [rbp+57h+Src], xmm0
0x1800b2a9a  cmp     ecx, 0FFFFFFFFh
0x1800b2a9d  jz      short loc_1800B2AAE
0x1800b2a9f  lea     r8, aRxlogerrors; "RxLogErrors"
0x1800b2aa6  mov     edx, esi; dwFlags
0x1800b2aa8  call    cs:__imp_TracePrintfExA
0x1800b2aae  test    rbx, rbx
0x1800b2ab1  jz      loc_1800B2D32
0x1800b2ab7  mov     r15, [rbx+70h]
0x1800b2abb  test    r15, r15
0x1800b2abe  jz      loc_1800B2D32
0x1800b2ac4  xor     r8d, r8d; nSize
0x1800b2ac7  lea     rcx, [rbp+57h+Src]; lpSrc
0x1800b2acb  xor     edx, edx; lpDst
0x1800b2acd  call    cs:__imp_ExpandEnvironmentStringsA
0x1800b2ad3  mov     ecx, 40h ; '@'; uFlags
0x1800b2ad8  mov     [rbp+57h+nSize], eax
0x1800b2adb  lea     edx, [rax+1]; dwBytes
0x1800b2ade  call    cs:__imp_GlobalAlloc
0x1800b2ae4  mov     rbx, rax
0x1800b2ae7  test    rax, rax
0x1800b2aea  jnz     short loc_1800B2AF4
0x1800b2aec  lea     eax, [rbx+8]
0x1800b2aef  jmp     loc_1800B2D37
0x1800b2af4  mov     r8d, [rbp+57h+nSize]; nSize
0x1800b2af8  lea     rcx, [rbp+57h+Src]; lpSrc
0x1800b2afc  mov     rdx, rbx; lpDst
0x1800b2aff  call    cs:__imp_ExpandEnvironmentStringsA
0x1800b2b05  xor     r9d, r9d; lpSecurityAttributes
0x1800b2b08  mov     [rsp+0E0h+hTemplateFile], 0; hTemplateFile
0x1800b2b11  mov     [rsp+0E0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800b2b19  mov     edx, 40000000h; dwDesiredAccess
0x1800b2b1e  mov     rcx, rbx; lpFileName
0x1800b2b21  mov     [rsp+0E0h+dwCreationDisposition], 2; dwCreationDisposition
0x1800b2b29  lea     r8d, [r9+1]; dwShareMode
0x1800b2b2d  call    cs:__imp_CreateFileA
0x1800b2b33  mov     rcx, rbx; hMem
0x1800b2b36  mov     rdi, rax
0x1800b2b39  call    cs:__imp_GlobalFree
0x1800b2b3f  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800b2b43  jnz     short loc_1800B2B71
0x1800b2b45  call    cs:__imp_GetLastError
0x1800b2b4b  mov     ecx, cs:g_dwRasscrptTraceId; dwTraceID
0x1800b2b51  mov     ebx, eax
0x1800b2b53  cmp     ecx, 0FFFFFFFFh
0x1800b2b56  jz      short loc_1800B2B6A
0x1800b2b58  mov     r9d, eax
0x1800b2b5b  lea     r8, aErrorDCreating; "error %d creating logfile"
0x1800b2b62  mov     edx, esi; dwFlags
0x1800b2b64  call    cs:__imp_TracePrintfExA
0x1800b2b6a  mov     eax, ebx
0x1800b2b6c  jmp     loc_1800B2D37
0x1800b2b71  xor     r9d, r9d; dwMoveMethod
0x1800b2b74  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800b2b77  xor     edx, edx; lDistanceToMove
0x1800b2b79  mov     rcx, rdi; hFile
0x1800b2b7c  xor     esi, esi
0x1800b2b7e  call    cs:__imp_SetFilePointer
0x1800b2b84  mov     rcx, rdi; hFile
0x1800b2b87  call    cs:__imp_SetEndOfFile
0x1800b2b8d  mov     r13d, [r12]
0x1800b2b91  xor     ebx, ebx
0x1800b2b93  test    r13d, r13d
0x1800b2b96  jz      loc_1800B2D1C
0x1800b2b9c  lea     r14, c_mpresids
0x1800b2ba3  mov     [rbp+57h+lpString], 0
0x1800b2bab  cmp     ebx, 0FFFFFFFFh
0x1800b2bae  jz      loc_1800B2D29
0x1800b2bb4  cmp     ebx, [r12]
0x1800b2bb8  jnb     loc_1800B2D29
0x1800b2bbe  mov     eax, [r12+14h]
0x1800b2bc3  lea     rcx, [rbp+57h+var_90]; void *
0x1800b2bc7  mov     r8d, eax; Size
0x1800b2bca  imul    eax, ebx
0x1800b2bcd  mov     edx, eax
0x1800b2bcf  add     rdx, [r12+8]; Src
0x1800b2bd4  call    memmove_0
0x1800b2bd9  mov     edx, dword ptr [rbp+57h+var_70+4]
0x1800b2bdc  xor     eax, eax
0x1800b2bde  mov     [rbp+57h+NumberOfBytesWritten], 0
0x1800b2be5  cmp     eax, 1Bh
0x1800b2be8  jnb     loc_1800B2D11
0x1800b2bee  movsxd  rcx, eax
0x1800b2bf1  cmp     edx, [r14+rcx*8]
0x1800b2bf5  jz      short loc_1800B2BFB
0x1800b2bf7  inc     eax
0x1800b2bf9  jmp     short loc_1800B2BE5
0x1800b2bfb  mov     eax, [r14+rcx*8+4]
0x1800b2c00  test    eax, eax
0x1800b2c02  jz      loc_1800B2D11
0x1800b2c08  mov     rdx, cs:g_hinst
0x1800b2c0f  lea     r9, [r15+438h]
0x1800b2c16  movzx   r8d, ax
0x1800b2c1a  lea     rcx, [rbp+57h+lpString]
0x1800b2c1e  lea     rax, [rbp+57h+var_90]
0x1800b2c22  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rax
0x1800b2c27  mov     eax, dword ptr [rbp+57h+var_70]
0x1800b2c2a  mov     [rsp+0E0h+dwCreationDisposition], eax
0x1800b2c2e  call    ConstructMessage
0x1800b2c33  mov     r14, [rbp+57h+lpString]
0x1800b2c37  test    r14, r14
0x1800b2c3a  jz      loc_1800B2D0A
0x1800b2c40  mov     rcx, r14; lpString
0x1800b2c43  call    cs:__imp_lstrlenA
0x1800b2c49  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800b2c4d  mov     qword ptr [rsp+0E0h+dwCreationDisposition], 0; lpOverlapped
0x1800b2c56  mov     r8d, eax; nNumberOfBytesToWrite
0x1800b2c59  mov     [rbp+57h+nSize], eax
0x1800b2c5c  mov     rdx, r14; lpBuffer
0x1800b2c5f  mov     rcx, rdi; hFile
0x1800b2c62  call    cs:__imp_WriteFile
0x1800b2c68  test    eax, eax
0x1800b2c6a  jz      short loc_1800B2C74
0x1800b2c6c  mov     eax, [rbp+57h+nSize]
0x1800b2c6f  cmp     [rbp+57h+NumberOfBytesWritten], eax
0x1800b2c72  jz      short loc_1800B2CA4
0x1800b2c74  call    cs:__imp_GetLastError
0x1800b2c7a  mov     ecx, cs:g_dwRasscrptTraceId; dwTraceID
0x1800b2c80  mov     esi, eax
0x1800b2c82  cmp     ecx, 0FFFFFFFFh
0x1800b2c85  jz      short loc_1800B2CA4
0x1800b2c87  lea     r9, aWindirSystem32; "%windir%\\system32\\ras\\script.log"
0x1800b2c8e  mov     [rsp+0E0h+dwCreationDisposition], eax
0x1800b2c92  lea     r8, aRxlogerrorsWri; "RxLogErrors(): WriteFile to %s failed w"...
0x1800b2c99  mov     edx, 0Ch; dwFlags
0x1800b2c9e  call    cs:__imp_TracePrintfExA
0x1800b2ca4  lea     r9, [rbp+57h+nSize]; lpNumberOfBytesWritten
0x1800b2ca8  mov     qword ptr [rsp+0E0h+dwCreationDisposition], 0; lpOverlapped
0x1800b2cb1  mov     r8d, 2; nNumberOfBytesToWrite
0x1800b2cb7  lea     rdx, asc_1800E521C; "\r\n"
0x1800b2cbe  mov     rcx, rdi; hFile
0x1800b2cc1  call    cs:__imp_WriteFile
0x1800b2cc7  test    eax, eax
0x1800b2cc9  jz      short loc_1800B2CD1
0x1800b2ccb  cmp     [rbp+57h+NumberOfBytesWritten], 2
0x1800b2ccf  jz      short loc_1800B2D01
0x1800b2cd1  call    cs:__imp_GetLastError
0x1800b2cd7  mov     ecx, cs:g_dwRasscrptTraceId; dwTraceID
0x1800b2cdd  mov     esi, eax
0x1800b2cdf  cmp     ecx, 0FFFFFFFFh
0x1800b2ce2  jz      short loc_1800B2D01
0x1800b2ce4  lea     r9, aWindirSystem32; "%windir%\\system32\\ras\\script.log"
0x1800b2ceb  mov     [rsp+0E0h+dwCreationDisposition], eax
0x1800b2cef  lea     r8, aRxlogerrorsWri; "RxLogErrors(): WriteFile to %s failed w"...
0x1800b2cf6  mov     edx, 0Ch; dwFlags
0x1800b2cfb  call    cs:__imp_TracePrintfExA
0x1800b2d01  mov     rcx, r14; hMem
0x1800b2d04  call    cs:__imp_GlobalFree
0x1800b2d0a  lea     r14, c_mpresids
0x1800b2d11  inc     ebx
0x1800b2d13  cmp     ebx, r13d
0x1800b2d16  jb      loc_1800B2BA3
0x1800b2d1c  mov     rcx, rdi; hObject
0x1800b2d1f  call    cs:__imp_CloseHandle
0x1800b2d25  mov     eax, esi
0x1800b2d27  jmp     short loc_1800B2D37
0x1800b2d29  mov     [rbp+57h+NumberOfBytesWritten], 0
0x1800b2d30  jmp     short loc_1800B2D11
0x1800b2d32  mov     eax, 57h ; 'W'
0x1800b2d37  mov     rcx, [rbp+57h+var_40]
0x1800b2d3b  xor     rcx, rsp; StackCookie
0x1800b2d3e  call    __security_check_cookie
0x1800b2d43  mov     rbx, [rsp+0E0h+arg_10]
0x1800b2d4b  add     rsp, 0B0h
0x1800b2d52  pop     r15
0x1800b2d54  pop     r14
0x1800b2d56  pop     r13
0x1800b2d58  pop     r12
0x1800b2d5a  pop     rdi
0x1800b2d5b  pop     rsi
0x1800b2d5c  pop     rbp
0x1800b2d5d  retn
```
