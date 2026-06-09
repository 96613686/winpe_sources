# NlOpenDebugFile(int)

- ea: `0x180040aa8`
- end: `0x180040f12`
- name: `?NlOpenDebugFile@@YAXH@Z`
- size: `1130`
- prototype: `void __fastcall(int)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x180007908`
- `0x18005fa30`
- `0x180077610`

## callees

- `0x180003320`
- `0x180003340`
- `0x180007518`
- `0x18000e910`
- `0x180040aa8`
- `0x180091010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180040c4f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180040d60`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180040d79`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180040c4f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180040d60`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180040d79`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180040cb2`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180040d47`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180040cb2`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180040d47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040bc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040cd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040cf8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040da1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040de5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040bc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040cd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040cf8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040da1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040de5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180040b73`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180040b73`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180040bb3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180040bb3`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180040cc1`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180040cc1`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180040ea4`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180040ea4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180040e60`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180040e60`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180040ce8`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180040ce8`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180040d91`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180040d91`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180040ef2`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180040ef2`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180040ed9`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180040ed9`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180040dd5`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180040dd5`
- `ntdll!RtlLeaveCriticalSection` at `0x180040b8d`
- `ntdll!RtlLeaveCriticalSection` at `0x180040e8e`
- `ntdll!RtlLeaveCriticalSection` at `0x180040f01`
- `ntdll!RtlLeaveCriticalSection` at `0x180040b8d`
- `ntdll!RtlLeaveCriticalSection` at `0x180040e8e`
- `ntdll!RtlLeaveCriticalSection` at `0x180040f01`
- `ntdll!RtlEnterCriticalSection` at `0x180040b57`
- `ntdll!RtlEnterCriticalSection` at `0x180040e26`
- `ntdll!RtlEnterCriticalSection` at `0x180040b57`
- `ntdll!RtlEnterCriticalSection` at `0x180040e26`

## string_xrefs

- `0x180040db5`: `Cannot delete %ws (%ld)\n`
- `0x180040bcf`: `Window Directory Path can't be retrieved, %lu.\n`
- `0x180040c98`: `Debug directory path (%ws) length is too long.\n`
- `0x180040d04`: `Can't create Debug directory (%ws), %lu.\n`
- `0x180040d2b`: `Debug directory path (%ws) exists as file.\n`
- `0x180040e0a`: `   Try to re-open the file.\n`
- `0x180040df4`: `Cannot rename %ws to %ws (%ld)\n`
- `0x180040e7c`: `cannot open %ws\n`

## pseudocode

```c
void __fastcall NlOpenDebugFile(int a1)
{
  void *v2; // rsp
  _BYTE *v3; // rbx
  _DWORD *v4; // rax
  unsigned __int16 *v5; // r8
  unsigned __int16 *v6; // rcx
  DWORD LastError; // eax
  __int64 v8; // rax
  __int64 v9; // rax
  unsigned int v10; // esi
  unsigned __int16 *v11; // rax
  unsigned __int64 v12; // rdx
  unsigned __int16 *v13; // rdx
  DWORD FileAttributesW; // eax
  DWORD v15; // eax
  DWORD v16; // eax
  DWORD v17; // eax
  HANDLE FileW; // rax
  __int64 v19; // [rsp-20h] [rbp-460h] BYREF
  DWORD dwCreationDisposition[2]; // [rsp+0h] [rbp-440h]
  int v21; // [rsp+20h] [rbp-420h]
  _BYTE v22[984]; // [rsp+28h] [rbp-418h] BYREF
  __int16 Buffer; // [rsp+440h] [rbp+0h] BYREF
  char v24; // [rsp+442h] [rbp+2h]
  DWORD NumberOfBytesWritten; // [rsp+448h] [rbp+8h] BYREF

  if ( (unsigned __int64)g_ulMaxStackAllocSize < 0x414
    || (unsigned __int64)(g_ulAdditionalProbeSize + 1052) < 0x414
    || !(unsigned int)VerifyStackAvailable()
    || (v2 = alloca(1056), &v19 == (__int64 *)-64LL)
    || (v21 = 1801679955, (v3 = v22) == 0) )
  {
    v4 = (_DWORD *)((__int64 (__fastcall *)(__int64))g_pfnAllocate)(1052);
    v3 = v4;
    if ( !v4 )
      goto LABEL_13;
    *v4 = 1885431112;
    v3 = v4 + 2;
    if ( v4 == (_DWORD *)-8LL )
      goto LABEL_13;
  }
  RtlEnterCriticalSection(&NlGlobalLogFileCritSect);
  if ( NlGlobalLogFile != (HANDLE)-1LL )
  {
    CloseHandle(NlGlobalLogFile);
    NlGlobalLogFile = (HANDLE)-1LL;
  }
  RtlLeaveCriticalSection(&NlGlobalLogFileCritSect);
  v5 = NlGlobalDebugSharePath;
  v6 = (unsigned __int16 *)v3;
  if ( NlGlobalDebugSharePath )
  {
    v12 = 261;
  }
  else
  {
    if ( !GetSystemWindowsDirectoryW((LPWSTR)v3, 0x105u) )
    {
      LastError = GetLastError();
      NlPrintRoutine(0x100u, L"Window Directory Path can't be retrieved, %lu.\n", LastError);
      goto LABEL_13;
    }
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)&v3[2 * v8] );
    if ( (unsigned __int64)(unsigned int)(v8 + 6) + 14 > 0x105 )
    {
      v13 = L"Debug directory path (%ws) length is too long.\n";
      goto LABEL_27;
    }
    _o_wcscat_s(v3, 261, L"\\debug");
    v9 = -1;
    do
      ++v9;
    while ( *(_WORD *)&v3[2 * v9] );
    v10 = 2 * v9 + 2;
    v11 = (unsigned __int16 *)NetpMemoryAllocate(v10);
    NlGlobalDebugSharePath = v11;
    v5 = (unsigned __int16 *)v3;
    if ( !v11 )
    {
      NlPrintRoutine(0x100u, L"Can't allocated memory for debug share (%ws).\n", v3);
      goto LABEL_13;
    }
    v6 = v11;
    v12 = (unsigned __int64)v10 >> 1;
  }
  _o_wcscpy_s(v6, v12, v5);
  FileAttributesW = GetFileAttributesW((LPCWSTR)v3);
  if ( FileAttributesW != -1 )
  {
    if ( (FileAttributesW & 0x10) != 0 )
      goto LABEL_38;
    v13 = L"Debug directory path (%ws) exists as file.\n";
LABEL_27:
    NlPrintRoutine(0x100u, v13, v3);
    goto LABEL_13;
  }
  v15 = GetLastError();
  if ( v15 != 2 )
  {
    NlPrintRoutine(0x100u, L"Can't Get File attributes(%ws), %lu.\n", v3, v15);
    goto LABEL_13;
  }
  if ( !CreateDirectoryW((LPCWSTR)v3, 0) )
  {
    v16 = GetLastError();
    NlPrintRoutine(0x100u, L"Can't create Debug directory (%ws), %lu.\n", v3, v16);
    goto LABEL_13;
  }
LABEL_38:
  _o_wcscpy_s(v3 + 522, 261, v3);
  _o_wcscat_s(v3, 261, L"\\netlogon.log");
  _o_wcscat_s(v3 + 522, 261, L"\\netlogon.bak");
  if ( a1 )
  {
    if ( !DeleteFileW((LPCWSTR)v3 + 261) )
    {
      v17 = GetLastError();
      if ( v17 != 2 )
      {
        NlPrintRoutine(0x100u, L"Cannot delete %ws (%ld)\n", v3 + 522, v17);
LABEL_44:
        NlPrintRoutine(0x100u, L"   Try to re-open the file.\n");
        a1 = 0;
        goto LABEL_45;
      }
    }
    if ( !MoveFileExW((LPCWSTR)v3, (LPCWSTR)v3 + 261, 2u) )
    {
      dwCreationDisposition[0] = GetLastError();
      NlPrintRoutine(0x100u, L"Cannot rename %ws to %ws (%ld)\n", v3, v3 + 522, *(_QWORD *)dwCreationDisposition);
      goto LABEL_44;
    }
  }
LABEL_45:
  RtlEnterCriticalSection(&NlGlobalLogFileCritSect);
  FileW = CreateFileW((LPCWSTR)v3, 0x40000000u, 3u, 0, a1 != 0 ? 2 : 4, 0x80u, 0);
  NlGlobalLogFile = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    if ( GetFileSize(FileW, 0) )
    {
      SetFilePointer(NlGlobalLogFile, 0, 0, 2u);
    }
    else
    {
      Buffer = -17425;
      v24 = -65;
      NumberOfBytesWritten = 0;
      WriteFile(NlGlobalLogFile, &Buffer, 3u, &NumberOfBytesWritten, 0);
    }
    RtlLeaveCriticalSection(&NlGlobalLogFileCritSect);
    goto LABEL_14;
  }
  NlPrintRoutine(0x100u, L"cannot open %ws\n", v3);
  RtlLeaveCriticalSection(&NlGlobalLogFileCritSect);
LABEL_13:
  NlPrintRoutine(0x100u, L"   Debug output will be written to debug terminal.\n");
LABEL_14:
  if ( v3 )
  {
    if ( *((_DWORD *)v3 - 2) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
  }
}

```

## disassembly

```asm
0x180040aa8  push    rbp
0x180040aaa  push    rbx
0x180040aab  push    rsi
0x180040aac  push    rdi
0x180040aad  push    r12
0x180040aaf  push    r14
0x180040ab1  push    r15
0x180040ab3  sub     rsp, 60h
0x180040ab7  lea     rbp, [rsp+40h]
0x180040abc  mov     rax, cs:__security_cookie
0x180040ac3  xor     rax, rbp
0x180040ac6  mov     [rbp+50h+var_40], rax
0x180040aca  xor     r15d, r15d
0x180040acd  mov     edx, 414h
0x180040ad2  cmp     cs:g_ulMaxStackAllocSize, rdx
0x180040ad9  mov     r14d, ecx
0x180040adc  mov     r12d, 100h
0x180040ae2  jb      short loc_180040B23
0x180040ae4  mov     rcx, cs:g_ulAdditionalProbeSize
0x180040aeb  add     rcx, 41Ch
0x180040af2  cmp     rcx, rdx
0x180040af5  jb      short loc_180040B23
0x180040af7  call    VerifyStackAvailable
0x180040afc  test    eax, eax
0x180040afe  jz      short loc_180040B23
0x180040b00  mov     eax, [rsp+90h+var_90]
0x180040b03  mov     eax, 420h
0x180040b08  sub     rsp, rax
0x180040b0b  lea     rbx, [rsp+4B0h+var_470]
0x180040b10  mov     eax, [rbx]
0x180040b12  test    rbx, rbx
0x180040b15  jz      short loc_180040B23
0x180040b17  mov     dword ptr [rbx], 6B637453h
0x180040b1d  add     rbx, 8
0x180040b21  jnz     short loc_180040B50
0x180040b23  mov     rax, cs:g_pfnAllocate
0x180040b2a  mov     ecx, 41Ch
0x180040b2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040b34  mov     rbx, rax
0x180040b37  test    rax, rax
0x180040b3a  jz      loc_180040BE1
0x180040b40  mov     dword ptr [rax], 70616548h
0x180040b46  add     rbx, 8
0x180040b4a  jz      loc_180040BE1
0x180040b50  lea     rcx, ?NlGlobalLogFileCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180040b57  call    cs:__imp_RtlEnterCriticalSection
0x180040b5e  nop     dword ptr [rax+rax+00h]
0x180040b63  mov     rcx, cs:?NlGlobalLogFile@@3PEAXEA; hObject
0x180040b6a  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180040b6e  cmp     rcx, rsi
0x180040b71  jz      short loc_180040B86
0x180040b73  call    cs:__imp_CloseHandle
0x180040b7a  nop     dword ptr [rax+rax+00h]
0x180040b7f  mov     cs:?NlGlobalLogFile@@3PEAXEA, rsi; void * NlGlobalLogFile
0x180040b86  lea     rcx, ?NlGlobalLogFileCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180040b8d  call    cs:__imp_RtlLeaveCriticalSection
0x180040b94  nop     dword ptr [rax+rax+00h]
0x180040b99  mov     r8, cs:?NlGlobalDebugSharePath@@3PEAGEA; ushort * NlGlobalDebugSharePath
0x180040ba0  mov     edi, 105h
0x180040ba5  mov     rcx, rbx; lpBuffer
0x180040ba8  test    r8, r8
0x180040bab  jnz     loc_180040CAF
0x180040bb1  mov     edx, edi; uSize
0x180040bb3  call    cs:__imp_GetSystemWindowsDirectoryW
0x180040bba  nop     dword ptr [rax+rax+00h]
0x180040bbf  test    eax, eax
0x180040bc1  jnz     short loc_180040C29
0x180040bc3  call    cs:__imp_GetLastError
0x180040bca  nop     dword ptr [rax+rax+00h]
0x180040bcf  lea     rdx, aWindowDirector; "Window Directory Path can't be retrieve"...
0x180040bd6  mov     ecx, r12d; unsigned int
0x180040bd9  mov     r8d, eax
0x180040bdc  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180040be1  lea     rdx, aDebugOutputWil; "   Debug output will be written to debu"...
0x180040be8  mov     ecx, r12d; unsigned int
0x180040beb  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180040bf0  test    rbx, rbx
0x180040bf3  jz      short loc_180040C0D
0x180040bf5  lea     rcx, [rbx-8]
0x180040bf9  cmp     dword ptr [rcx], 70616548h
0x180040bff  jnz     short loc_180040C0D
0x180040c01  mov     rax, cs:g_pfnFree
0x180040c08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040c0d  mov     rcx, [rbp+50h+var_40]
0x180040c11  xor     rcx, rbp; StackCookie
0x180040c14  call    __security_check_cookie
0x180040c19  lea     rsp, [rbp+20h]
0x180040c1d  pop     r15
0x180040c1f  pop     r14
0x180040c21  pop     r12
0x180040c23  pop     rdi
0x180040c24  pop     rsi
0x180040c25  pop     rbx
0x180040c26  pop     rbp
0x180040c27  retn
0x180040c29  mov     rax, rsi
0x180040c2c  inc     rax
0x180040c2f  cmp     [rbx+rax*2], r15w
0x180040c34  jnz     short loc_180040C2C
0x180040c36  lea     ecx, [rax+6]
0x180040c39  add     rcx, 0Eh
0x180040c3d  cmp     rcx, rdi
0x180040c40  ja      short loc_180040C98
0x180040c42  lea     r8, aDebug; "\\debug"
0x180040c49  mov     rdx, rdi
0x180040c4c  mov     rcx, rbx
0x180040c4f  call    cs:__imp__o_wcscat_s
0x180040c56  nop     dword ptr [rax+rax+00h]
0x180040c5b  mov     rax, rsi
0x180040c5e  inc     rax
0x180040c61  cmp     [rbx+rax*2], r15w
0x180040c66  jnz     short loc_180040C5E
0x180040c68  lea     esi, ds:2[rax*2]
0x180040c6f  mov     ecx, esi
0x180040c71  call    NetpMemoryAllocate
0x180040c76  mov     cs:?NlGlobalDebugSharePath@@3PEAGEA, rax; ushort * NlGlobalDebugSharePath
0x180040c7d  mov     r8, rbx
0x180040c80  test    rax, rax
0x180040c83  jnz     short loc_180040C8E
0x180040c85  lea     rdx, aCanTAllocatedM; "Can't allocated memory for debug share "...
0x180040c8c  jmp     short loc_180040CA2
0x180040c8e  mov     edx, esi
0x180040c90  mov     rcx, rax
0x180040c93  shr     rdx, 1
0x180040c96  jmp     short loc_180040CB2
0x180040c98  lea     rdx, aDebugDirectory_0; "Debug directory path (%ws) length is to"...
0x180040c9f  mov     r8, rbx
0x180040ca2  mov     ecx, r12d; unsigned int
0x180040ca5  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180040caa  jmp     loc_180040BE1
0x180040caf  mov     rdx, rdi
0x180040cb2  call    cs:__imp__o_wcscpy_s
0x180040cb9  nop     dword ptr [rax+rax+00h]
0x180040cbe  mov     rcx, rbx; lpFileName
0x180040cc1  call    cs:__imp_GetFileAttributesW
0x180040cc8  nop     dword ptr [rax+rax+00h]
0x180040ccd  cmp     eax, 0FFFFFFFFh
0x180040cd0  jnz     short loc_180040D27
0x180040cd2  call    cs:__imp_GetLastError
0x180040cd9  nop     dword ptr [rax+rax+00h]
0x180040cde  cmp     eax, 2
0x180040ce1  jnz     short loc_180040D1E
0x180040ce3  xor     edx, edx; lpSecurityAttributes
0x180040ce5  mov     rcx, rbx; lpPathName
0x180040ce8  call    cs:__imp_CreateDirectoryW
0x180040cef  nop     dword ptr [rax+rax+00h]
0x180040cf4  test    eax, eax
0x180040cf6  jnz     short loc_180040D37
0x180040cf8  call    cs:__imp_GetLastError
0x180040cff  nop     dword ptr [rax+rax+00h]
0x180040d04  lea     rdx, aCanTCreateDebu; "Can't create Debug directory (%ws), %lu"...
0x180040d0b  mov     r8, rbx
0x180040d0e  mov     r9d, eax
0x180040d11  mov     ecx, r12d; unsigned int
0x180040d14  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180040d19  jmp     loc_180040BE1
0x180040d1e  lea     rdx, aCanTGetFileAtt; "Can't Get File attributes(%ws), %lu.\n"
0x180040d25  jmp     short loc_180040D0B
0x180040d27  test    al, 10h
0x180040d29  jnz     short loc_180040D37
0x180040d2b  lea     rdx, aDebugDirectory; "Debug directory path (%ws) exists as fi"...
0x180040d32  jmp     loc_180040C9F
0x180040d37  lea     rsi, [rbx+20Ah]
0x180040d3e  mov     r8, rbx
0x180040d41  mov     rcx, rsi
0x180040d44  mov     rdx, rdi
0x180040d47  call    cs:__imp__o_wcscpy_s
0x180040d4e  nop     dword ptr [rax+rax+00h]
0x180040d53  lea     r8, aNetlogonLog; "\\netlogon.log"
0x180040d5a  mov     rdx, rdi
0x180040d5d  mov     rcx, rbx
0x180040d60  call    cs:__imp__o_wcscat_s
0x180040d67  nop     dword ptr [rax+rax+00h]
0x180040d6c  lea     r8, aNetlogonBak; "\\netlogon.bak"
0x180040d73  mov     rdx, rdi
0x180040d76  mov     rcx, rsi
0x180040d79  call    cs:__imp__o_wcscat_s
0x180040d80  nop     dword ptr [rax+rax+00h]
0x180040d85  test    r14d, r14d
0x180040d88  jz      loc_180040E1C
0x180040d8e  mov     rcx, rsi; lpFileName
0x180040d91  call    cs:__imp_DeleteFileW
0x180040d98  nop     dword ptr [rax+rax+00h]
0x180040d9d  test    eax, eax
0x180040d9f  jnz     short loc_180040DC9
0x180040da1  call    cs:__imp_GetLastError
0x180040da8  nop     dword ptr [rax+rax+00h]
0x180040dad  cmp     eax, 2
0x180040db0  jz      short loc_180040DC9
0x180040db2  mov     r9d, eax
0x180040db5  lea     rdx, aCannotDeleteWs; "Cannot delete %ws (%ld)\n"
0x180040dbc  mov     r8, rsi
0x180040dbf  mov     ecx, r12d; unsigned int
0x180040dc2  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180040dc7  jmp     short loc_180040E0A
0x180040dc9  mov     r8d, 2; dwFlags
0x180040dcf  mov     rdx, rsi; lpNewFileName
0x180040dd2  mov     rcx, rbx; lpExistingFileName
0x180040dd5  call    cs:__imp_MoveFileExW
0x180040ddc  nop     dword ptr [rax+rax+00h]
0x180040de1  test    eax, eax
0x180040de3  jnz     short loc_180040E1C
0x180040de5  call    cs:__imp_GetLastError
0x180040dec  nop     dword ptr [rax+rax+00h]
0x180040df1  mov     r9, rsi
0x180040df4  lea     rdx, aCannotRenameWs; "Cannot rename %ws to %ws (%ld)\n"
0x180040dfb  mov     r8, rbx
0x180040dfe  mov     [rsp+4B0h+dwCreationDisposition], eax
0x180040e02  mov     ecx, r12d; unsigned int
0x180040e05  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180040e0a  lea     rdx, aTryToReOpenThe; "   Try to re-open the file.\n"
0x180040e11  mov     ecx, r12d; unsigned int
0x180040e14  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180040e19  mov     r14d, r15d
0x180040e1c  lea     rdi, ?NlGlobalLogFileCritSect@@3U_SAFE_CRITICAL_SECTION@@A; _SAFE_CRITICAL_SECTION NlGlobalLogFileCritSect
0x180040e23  mov     rcx, rdi; CriticalSection
0x180040e26  call    cs:__imp_RtlEnterCriticalSection
0x180040e2d  nop     dword ptr [rax+rax+00h]
0x180040e32  mov     [rsp+4B0h+hTemplateFile], r15; hTemplateFile
0x180040e37  neg     r14d
0x180040e3a  mov     [rsp+4B0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180040e42  mov     edx, 40000000h; dwDesiredAccess
0x180040e47  sbb     eax, eax
0x180040e49  mov     rcx, rbx; lpFileName
0x180040e4c  xor     r9d, r9d; lpSecurityAttributes
0x180040e4f  and     eax, 0FFFFFFFEh
0x180040e52  add     eax, 4
0x180040e55  mov     [rsp+4B0h+dwCreationDisposition], eax; dwCreationDisposition
0x180040e59  lea     esi, [r9+3]
0x180040e5d  mov     r8d, esi; dwShareMode
0x180040e60  call    cs:__imp_CreateFileW
0x180040e67  nop     dword ptr [rax+rax+00h]
0x180040e6c  mov     cs:?NlGlobalLogFile@@3PEAXEA, rax; void * NlGlobalLogFile
0x180040e73  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180040e77  jnz     short loc_180040E9F
0x180040e79  mov     r8, rbx
0x180040e7c  lea     rdx, aCannotOpenWs; "cannot open %ws\n"
0x180040e83  mov     ecx, r12d; unsigned int
0x180040e86  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180040e8b  mov     rcx, rdi; CriticalSection
0x180040e8e  call    cs:__imp_RtlLeaveCriticalSection
0x180040e95  nop     dword ptr [rax+rax+00h]
0x180040e9a  jmp     loc_180040BE1
0x180040e9f  xor     edx, edx; lpFileSizeHigh
0x180040ea1  mov     rcx, rax; hFile
0x180040ea4  call    cs:__imp_GetFileSize
0x180040eab  nop     dword ptr [rax+rax+00h]
0x180040eb0  mov     rcx, cs:?NlGlobalLogFile@@3PEAXEA; hFile
0x180040eb7  test    eax, eax
0x180040eb9  jnz     short loc_180040EE7
0x180040ebb  lea     r9, [rbp+50h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180040ebf  mov     [rbp+50h+Buffer], 0BBEFh
0x180040ec5  mov     r8d, esi; nNumberOfBytesToWrite
0x180040ec8  mov     [rbp+50h+var_4E], 0BFh
0x180040ecc  lea     rdx, [rbp+50h+Buffer]; lpBuffer
0x180040ed0  mov     [rbp+50h+NumberOfBytesWritten], r15d
0x180040ed4  mov     qword ptr [rsp+4B0h+dwCreationDisposition], r15; lpOverlapped
0x180040ed9  call    cs:__imp_WriteFile
0x180040ee0  nop     dword ptr [rax+rax+00h]
0x180040ee5  jmp     short loc_180040EFE
0x180040ee7  mov     r9d, 2; dwMoveMethod
0x180040eed  xor     r8d, r8d; lpDistanceToMoveHigh
0x180040ef0  xor     edx, edx; lDistanceToMove
0x180040ef2  call    cs:__imp_SetFilePointer
0x180040ef9  nop     dword ptr [rax+rax+00h]
0x180040efe  mov     rcx, rdi; CriticalSection
0x180040f01  call    cs:__imp_RtlLeaveCriticalSection
0x180040f08  nop     dword ptr [rax+rax+00h]
0x180040f0d  jmp     loc_180040BF0
```
